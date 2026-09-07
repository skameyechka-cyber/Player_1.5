#include <stdio.h>
#include <windows.h>
#include <conio.h>

    void anim()
    { while (!kbhit())
    {
        system("cls");
        printf("Playing.\n\n"
               "Press enter to return to main menu.");
        Sleep(500);
        if (kbhit()) break;

        system("cls");
        printf("Playing..\n\n"
               "Press enter to return to main menu.");
        Sleep(500);
        if (kbhit()) break;

        system("cls");
        printf("Playing...\n\n"
               "Press enter to return to main menu.");
        Sleep(500);
        if (kbhit()) break;
    }

    }

int main()
{
    system("chcp 65001 > nul");

    char songname[50];
    char input[50];

    while (1)
    {
        system("cls");
        printf("------------\n"
        "|PLAYER 1.0|\n"
        "------------\n");

        printf("===========\n"
               "Tracks list\n"
               "===========\n");

        printf("\n");
        system("dir /b Music");

        printf("\n----------------\n"
              "Enter track name (enter 'exit' to exit program)\n"
              "----------------\n");

        scanf(" %[^\n]", songname);
        if (strcmp(songname, "exit") == 0)
        {
            break;
        }

        sprintf(input, "start Music\\\"%s\"", songname);
        system(input);
       anim();
    }

    return 0;
}
