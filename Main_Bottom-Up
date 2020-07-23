import java.util.Scanner;

public class Main {
    static long mod = 1000000009;
    static long[][] A = new long[100000+1][4]; // n을 1, 2, 3의 합으로 나타내는 방법의 수를 저장하는 배열
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int cnt = sc.nextInt();
        add123();
        for (int i=0;i<cnt;i++) {
            int num = sc.nextInt();
            System.out.println((A[num][1] + A[num][2] + A[num][3])%mod);
        }
    }

    public static void add123() {
        // Bottom-UP 방식
        // A[i][j] = i를 1, 2, 3의 합으로 만드는 방법의수, j는 마지막으로 더한 수
        // 점화식 : A[n] = A[n][1] + A[n][2] + A[n][3]
        // A[n][1] = A[n-1][2] + A[n-1][3]
        // A[n][2] = A[n-2][1] + A[n-2][3]
        // A[n][3] = A[n-3][1] + A[n-3][2]

        // 예외처리 (중복 피하기 위함)
        A[1][1] = 1%mod;
        A[2][2] = 1%mod;
        A[3][1] = (A[2][2] + A[2][3])%mod;
        A[3][2] = (A[1][1] + A[1][3])%mod;
        A[3][3] = 1%mod;
        for (int i=4;i<100001;i++) {
            A[i][1] = A[i-1][2] + A[i-1][3]; // 마지막에 1을 더해서 n을 만드는 경우의 수
            A[i][2] = A[i-2][1] + A[i-2][3]; // 마지막에 2을 더해서 n을 만드는 경우의 수
            A[i][3] = A[i-3][1] + A[i-3][2]; // 마지막에 3을 더해서 n을 만드는 경우의 수
            A[i][1] %= mod;
            A[i][2] %= mod;
            A[i][3] %= mod;
        }
    }
}
