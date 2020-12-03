# Advent-of-code-day-2-prob-1

#include <stdio.h>

#define _CRT_SECURE_NO_WARNINGS
#pragma warning(disable:4996)

int main() {

    FILE* input = fopen("C:\\Users\\Work\\Downloads\\day2 p1.txt", "r");
    int s = 0;

    int min, max;
    int cS;
    char letter;
    char c[50];
    int i;
    char useless;
    char useless2;

    // fscanf(input,"%d %d %c  %s", &min, &max, &letter, &c);
    // printf("min %d, max %d, letter %c, string %s\n", min, max, letter, c);

    while (!(feof(input))) {
        fscanf(input, "%d %c %d %c %c %s", &min, &useless2, &max, &letter, &useless, &c);
        printf("min %d, max %d, letter %c, string %s\n", min, max, letter, c);
        cS = 0;
        i = 0;

        if (c[min-1] == letter || c[max-1] == letter)
            s++;

        if (c[min-1] == letter && c[max-1] == letter)
            s--;
    }

    fclose(input);
    printf("%d valid passwords\n", s);
    return 0;
