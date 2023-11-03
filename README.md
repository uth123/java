// A) Create a superclass called AddingNumbers
class AddingNumbers {
    // Variables
    int number1;
    int number2;

    // Constructor
    public AddingNumbers(int number1, int number2) {
        this.number1 = number1;
        this.number2 = number2;
    }

    // Method to display inputs
    public void displayInputs() {
        System.out.println("Number 1: " + number1);
        System.out.println("Number 2: " + number2);
    }
}

// B) Create a subclass called AddingBinaryNumbers that extends AddingNumbers
class AddingBinaryNumbers extends AddingNumbers {
    // Constructor
    public AddingBinaryNumbers(int number1, int number2) {
        super(number1, number2);
    }

    // Method to add binary numbers
    public String addBinary() {
        String binary1 = Integer.toBinaryString(number1);
        String binary2 = Integer.toBinaryString(number2);
        int sum = number1 + number2;
        String binarySum = Integer.toBinaryString(sum);
        return binary1 + " + " + binary2 + " = " + binarySum;
    }
}

// C) Create another subclass called AddingDecimalNumbers that extends
// AddingNumbers
class AddingDecimalNumbers extends AddingNumbers {
    // Constructor
    public AddingDecimalNumbers(int number1, int number2) {
        super(number1, number2);
    }

    // Method to add decimal numbers
    public double addDecimal() {
        double sum = number1 + number2;
        return sum;
    }
}

// D) Create a class MyEntry with the main() method
public class MyEntry {
    public static void main(String[] args) {
        // Create an object of AddingBinaryNumbers
        AddingBinaryNumbers binaryNumbers = new AddingBinaryNumbers(5, 3);
        System.out.println("Binary Numbers:");
        binaryNumbers.displayInputs();
        System.out.println(binaryNumbers.addBinary());

        // Create an object of AddingDecimalNumbers
        AddingDecimalNumbers decimalNumbers = new AddingDecimalNumbers(5, 3);
        System.out.println("\nDecimal Numbers:");
        decimalNumbers.displayInputs();
        System.out.println("Sum: " + decimalNumbers.addDecimal());
    }
}

/*
 * import java.util.Scanner;
 * 
 * public class FunGame {
 * public static void main(String[] args) {
 * Scanner scanner = new Scanner(System.in);
 * boolean validInput = false;
 * 
 * while (!validInput) {
 * System.out.println("*** Welcome to explore with Fun Game ***");
 * System.out.println("SELECT FROM THE MAIN MENU");
 * System.out.println("1. Print Hollow Mirrored Rhombus");
 * System.out.println("2. Reverse Your Name");
 * System.out.println("3. Find Vowels in your Name");
 * System.out.println("4. Reverse a Number");
 * System.out.println("5. Reverse an Array");
 * System.out.println("6. GCD of Two Numbers");
 * 
 * System.out.print("Enter your choice (1-6): ");
 * int choice = scanner.nextInt();
 * scanner.nextLine(); // Consume the newline character
 * 
 * switch (choice) {
 * case 1:
 * // Option 1: Print Hollow Mirrored Rhombus
 * System.out.print("Enter N: ");
 * int n = scanner.nextInt();
 * scanner.nextLine();
 * System.out.print("Enter Symbol: ");
 * char symbol = scanner.nextLine().charAt(0);
 * 
 * if (n > 0) {
 * printHollowMirroredRhombus(n, symbol);
 * } else {
 * System.out.println("Invalid input. N must be greater than 0.");
 * }
 * break;
 * 
 * case 2:
 * // Option 2: Reverse Your Name
 * System.out.print("Enter a String: ");
 * String inputStr = scanner.nextLine();
 * String reversedStr = reverseString(inputStr);
 * System.out.println("The reverse of the input String is: " + reversedStr);
 * break;
 * 
 * case 3:
 * // Option 3: Find Vowels in your Name
 * System.out.print("Enter your Name: ");
 * String name = scanner.nextLine();
 * String vowels = findVowelsInName(name);
 * System.out.println("The vowels available in your name: " + vowels);
 * break;
 * 
 * case 4:
 * // Option 4: Reverse a Number
 * System.out.print("Enter a Number (with more than 2 digits): ");
 * int number = scanner.nextInt();
 * if (number >= 10) {
 * int reversedNumber = reverseNumber(number);
 * System.out.println("The reverse order of your number: " + reversedNumber);
 * } else {
 * System.out.println("Invalid input. Number must have more than 2 digits.");
 * }
 * break;
 * 
 * case 5:
 * // Option 5: Reverse an Array
 * System.out.print("Enter the number of values for an integer Array: ");
 * int arraySize = scanner.nextInt();
 * if (arraySize > 0) {
 * int[] arr = new int[arraySize];
 * System.out.println("Enter " + arraySize + " Values for the integer Array:");
 * for (int i = 0; i < arraySize; i++) {
 * arr[i] = scanner.nextInt();
 * }
 * int[] reversedArray = reverseArray(arr);
 * System.out.print("The reversed Array: ");
 * for (int value : reversedArray) {
 * System.out.print(value + " ");
 * }
 * System.out.println();
 * } else {
 * System.out.println("Invalid input. Array size must be greater than 0.");
 * }
 * break;
 * 
 * case 6:
 * // Option 6: GCD of Two Numbers
 * System.out.print("Enter two Numbers to find the GCD: ");
 * int num1 = scanner.nextInt();
 * int num2 = scanner.nextInt();
 * int gcdResult = calculateGCD(num1, num2);
 * System.out.println("The GCD of " + num1 + " and " + num2 + " is " +
 * gcdResult);
 * break;
 * 
 * default:
 * System.out.println("Invalid choice. Please select a valid option (1-6).");
 * }
 * 
 * System.out.print("Do you want to continue (yes/no)? ");
 * String continueChoice = scanner.next();
 * if (continueChoice.equalsIgnoreCase("no")) {
 * validInput = true;
 * }
 * }
 * 
 * scanner.close();
 * }
 * 
 * // Function to print a hollow mirrored rhombus
 * public static void printHollowMirroredRhombus(int n, char symbol) {
 * for (int i = 0; i < n; i++) {
 * for (int j = 0; j < n + i; j++) {
 * if (j >= n - i - 1 && (j == n - i - 1 || j == n + i - 1 || i == 0 || i == n -
 * 1)) {
 * System.out.print(symbol);
 * } else {
 * System.out.print(" ");
 * }
 * }
 * System.out.println();
 * }
 * }
 * 
 * // Function to reverse a string
 * public static String reverseString(String inputStr) {
 * return new StringBuilder(inputStr).reverse().toString();
 * }
 * 
 * // Function to find and return vowels in a string
 * public static String findVowelsInName(String name) {
 * StringBuilder vowels = new StringBuilder();
 * for (char c : name.toCharArray()) {
 * if ("AEIOUaeiou".contains(String.valueOf(c))) {
 * if (vowels.length() > 0) {
 * vowels.append(", ");
 * }
 * vowels.append(c);
 * }
 * }
 * return vowels.toString();
 * }
 * 
 * // Function to reverse a number
 * public static int reverseNumber(int number) {
 * int reversedNumber = 0;
 * while (number != 0) {
 * int digit = number % 10;
 * reversedNumber = reversedNumber * 10 + digit;
 * number /= 10;
 * }
 * return reversedNumber;
 * }
 * 
 * // Function to reverse an array of integers
 * public static int[] reverseArray(int[] arr) {
 * int[] reversedArray = new int[arr.length];
 * for (int i = 0; i < arr.length; i++) {
 * reversedArray[i] = arr[arr.length - 1 - i];
 * }
 * return reversedArray;
 * }
 * 
 * // Function to calculate the Greatest Common Divisor (GCD) of two numbers
 * public static int calculateGCD(int a, int b) {
 * if (b == 0) {
 * return a;
 * }
 * return calculateGCD(b, a % b);
 * }
 * }
 */
