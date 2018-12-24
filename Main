package perfectnumber;
/*
** Author: Amir Bin Iskandar
**
*/
import java.math.BigInteger;
import java.sql.Timestamp;
public class Main {

    public static long time, freq = 1000*60*5;//000*60*60;

    public static void main(String[] args) {
        BigInteger x;
        BigInteger prime = new BigInteger("2");
        int count = 1;
        for (; true; prime = prime.add(BigInteger.ONE)) {
            BigInteger prime2;
            if (pri(prime)) {
                prime2 = exp(prime).subtract(BigInteger.ONE);
            } else {
                continue;
            }
            if (pri(prime2)) {
                x = exp(prime.subtract(BigInteger.ONE)).multiply(prime2);
                time = System.currentTimeMillis();
                System.out.println(new Timestamp(time));
                System.out.println(count + ". f(" + prime + ") = " + x + "\n");
                count++;
            }
        }
    }
    public static boolean pri(BigInteger x) {
        boolean isPrime = false;
        BigInteger i = new BigInteger("1");
        int count = 1;
        while (count < 3) {

            if (System.currentTimeMillis() - time > freq) {
                time = System.currentTimeMillis();
                System.out.println(new Timestamp(time) + " :\nCalculating " + x+"/"+i);

            }
            if (x.equals(i)) {
                isPrime = true;
                break;
            }
            if (x.mod(i).equals(BigInteger.ZERO)) {
                count++;
            }
            i = i.add(BigInteger.ONE);
        }
        return isPrime;
    }
    public static BigInteger exp(BigInteger x) {
        BigInteger i = new BigInteger("1");
        BigInteger y = new BigInteger("2");
        BigInteger fin = new BigInteger("2");
        while (!i.equals(x)) {
            if (System.currentTimeMillis() - time > freq) {
                time = System.currentTimeMillis();
                System.out.println(new Timestamp(time) + " :\nCalculating 2^" + x);
            }
            y = y.multiply(fin);
            i = i.add(BigInteger.ONE);
        }
        return y;
    }
}
