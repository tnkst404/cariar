# cariar

public static void main(String[] args) {
    int num1 = getInt();
    int num2 = getInt();
    char operation = getOperation();
    int result = calc(num1, num2, operation);
    System.out.println("Результат операции: " + result);
}

public static int getInt() {
    System.out.println("Введите число:");
    Scanner scanner = new Scanner(System.in);
    int num;
    if (scanner.hasNextLine()) {
        num = scanner.nextInt();
    } else {
        System.out.println("Вы допустили ошибку при вводе числа. Попробуйте еще раз.");
        scanner.next();
        num = getInt();
    }
    return num;
}

public static char getOperation() {
    System.out.println("Введите операцию:");
    Scanner scanner = new Scanner(System.in);
    char operation;
    if (scanner.hasNext()) {
        operation = scanner.next().charAt(0);
    } else {
        System.out.println("Вы допустили ошибку при вводе операции. Попробуйте еще раз.");
        scanner.next();//рекурсия
        operation = getOperation();
    }
    return operation;
}

public void id(String... args) {
    int num1 = new ConvertToRoman().convert(scanner.nextLine());
    int num2 = new ConvertToRoman().convert(scanner.nextLine());

    char operation = getOperation();
    int result = calc(num1, num2, operation);
    System.out.println("Результат операции: " + result);
}

static class ConvertToRoman {
    private String value1;
    int num1 = toArabic(value1);

    public int toArabic(String value) {
        String value1 = value;
        String s1 = toString();
        String s = s1;
        int converts1;
        {

            if (value.equals("I")) return 1;
            if (value.equals("II")) return 2;
            if (value.equals("III")) return 3;
            if (value.equals("IV")) return 4;
            if (value.equals("V")) return 5;
            if (value.equals("VI")) return 6;
            if (value.equals("VII")) return 7;
            if (value.equals("VIII")) return 8;
            if (value.equals("IX")) return 9;
            if (value.equals("X")) return 10;
            return 0;
        }
    }

    public static int calc(int num1, int num2, char operation) {
        int result;
        switch (operation) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                result = num1 / num2;
                break;
            default:
                System.out.println("Операция не распознана. Повторите ввод.");
                result = calc(num1, num2, getOperation());

        }
        return result;


    }

    public int convert(String nextLine) {
        return 0;
    }
}
