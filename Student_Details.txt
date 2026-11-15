#include <stdio.h>

struct Student
{
    int roll_number;
    char name[50];
    float cut_off;
    char city[50];
    char dream[50];
};

void Read_input(struct Student s[], int size);
void Display_output(struct Student s[], int size);

int main()
{
    int count;

    printf("Enter the Student Count: ");
    scanf("%d", &count);

    if (count <= 0)
    {
        printf("Invalid student count!\n");
        return 0;
    }

    struct Student s[count];

    Read_input(s, count);
    Display_output(s, count);

    return 0;
}

void Read_input(struct Student s[], int size)
{
    int i, counter = 1;

    for (i = 0; i < size; i++)
    {
        printf("\nEnter the Student %d Details:\n", counter);

        printf("Enter the Roll Number: ");
        scanf("%d", &s[i].roll_number);

        printf("Enter the Name of the Student: ");
        scanf(" %49[^\n]", s[i].name);

        printf("Enter the Cut-off of the Student: ");
        scanf("%f", &s[i].cut_off);

        printf("Enter the City of the Student: ");
        scanf(" %49[^\n]", s[i].city);

        printf("Enter the Dream of the Student: ");
        scanf(" %49[^\n]", s[i].dream);

        counter++;
    }
}

void Display_output(struct Student s[], int size)
{
    int i, counter = 1;

    for (i = 0; i < size; i++)
    {
        printf("\nStudent %d Roll Number = %d\n",
               counter, s[i].roll_number);

        printf("Student %d Name = %s\n",
               counter, s[i].name);

        printf("Student %d Cut-off = %.2f\n",
               counter, s[i].cut_off);

        printf("Student %d City = %s\n",
               counter, s[i].city);

        printf("Student %d Dream = %s\n",
               counter, s[i].dream);

        counter++;
    }
}
