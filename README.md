# D-25679-OS-3-A3
#include <stdio.h>

int main()
{
    int n, i;

    printf("Enter number of processes: ");
    scanf("%d", &n);

    int AT[n], BT1[n], IO[n], BT2[n];
    int PCT[n], CT[n];

    // Input values
    for(i = 0; i < n; i++)
    {
        printf("\nProcess P%d\n", i);
        printf("Arrival Time (AT): ");
        scanf("%d", &AT[i]);

        printf("Burst Time 1 (BT1): ");
        scanf("%d", &BT1[i]);

        printf("IO Time: ");
        scanf("%d", &IO[i]);

        printf("Burst Time 2 (BT2): ");
        scanf("%d", &BT2[i]);
    }

    // Calculate PCT and CT
    for(i = 0; i < n; i++)
    {
        PCT[i] = AT[i] + BT1[i] + IO[i];
        CT[i] = PCT[i] + BT2[i];
    }

    // Output table
    printf("\nPID\tAT\tBT1\tIO\tBT2\tPCT\tCT\n");

    for(i = 0; i < n; i++)
    {
        printf("P%d\t%d\t%d\t%d\t%d\t%d\t%d\n",
               i, AT[i], BT1[i], IO[i], BT2[i], PCT[i], CT[i]);
    }

    return 0;
}
