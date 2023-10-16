Selection Sort is a simple sorting algorithm that repeatedly finds the minimum element from the unsorted part of the array and puts it at the beginning. The algorithm maintains two sub-arrays: one that is sorted and the other that is unsorted. The sorted sub-array is built up from left to right.

public class SelectionSort {
    
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        
        // Traverse through all array elements
        for (int i = 0; i < n - 1; i++) {
            // Find the minimum element in the unsorted part of the array
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }

            // Swap the found minimum element with the first element
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }

    public static void main(String[] args) {
        int[] myArray = {64, 25, 12, 22, 11};
        
        System.out.println("Original Array:");
        printArray(myArray);

        // Applying Selection Sort
        selectionSort(myArray);

        System.out.println("Sorted Array:");
        printArray(myArray);
    }

    public static void printArray(int[] arr) {
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }
}
