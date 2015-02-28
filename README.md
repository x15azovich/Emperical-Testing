# Emperical-Testing
# Tester class for Studing the improvements of merge sort

	public class EmpericalTest {
	public static void main(String[] args) {
		File f1 = new File();
		File1 f11 = new File1();
		File2 f2 = new File2();
		File3 f3 = new File3();
		File4 f4 = new File4();
		int i = 1;
		double totalTime = 0;
		double avgTime;
		double TotalTime1 = 0;
		double avgTime1;
		double avgTime2;
		double TotalTime2 = 0;
		double avgTime3;
		double TotalTime3 = 0;
		double avgTime4;
		double TotalTime4 = 0;
		double avgTime5;
		double TotalTime5 = 0;
		Comparable[] b;
		do {
			// Create a big enough array to have a big enough time to be read by
			// the stop watch but not big enough to take 11 days
			Comparable[] a = new Comparable[100000];
			b = new Comparable[100000];
			// randomly put numbers in the array and use the same array for b to
			// pass into the classes
			for (int j = 0; j < a.length; j++) {
				a[j] = (int) (Math.random() * 100);
				b[j] = a[j];// same random numbers for both classes
			}
			// test for merge
			Stopwatch s1 = new Stopwatch();

			Merge.sort(a);

			System.out.println("Processing " + i);// know where I am at for
													// testing purposes
			f1.Append("                       Trial " + i + " "
					+ s1.elapsedTime());
			totalTime += s1.elapsedTime();
			avgTime = totalTime / i;

			// run the whole improvements class to compare to regular merge sort
			Stopwatch s2 = new Stopwatch();

			MergeX.sort(a);

			f4.Append("                        Trial " + i + " "
					+ s2.elapsedTime());
			TotalTime1 += s2.elapsedTime();
			avgTime1 = TotalTime1 / i;

			// run the improvement for sub arrays
			Stopwatch s3 = new Stopwatch();
			MergeA.sort(b);
			f11.Append("                       Trial " + i + " "
					+ s3.elapsedTime());
			TotalTime2 += s2.elapsedTime();
			avgTime2 = TotalTime2 / i;

			// Calculations for Sort
			Stopwatch s4 = new Stopwatch();
			MergeY.sort(b);

			f2.Append("                       Trial " + i + " "
					+ s4.elapsedTime());
			TotalTime3 += s4.elapsedTime();
			avgTime3 = TotalTime3 / i;

			// Calculations for Aux
			Stopwatch s5 = new Stopwatch();
			MergeZ.sort(b);

			f3.Append("                        Trial " + i + " "
					+ s5.elapsedTime());
			TotalTime4 += s5.elapsedTime();
			avgTime4 = TotalTime4 / i;

			// do it 100000 times and take the average of each, putting it into
			// a text file
			i++;
		} while (i < 100000);
		f1.Append("   \n" + "    Average Time for Merge sort is " + avgTime);
		f2.Append("   \n" + "    Average Time for Sorted Arrays is " + avgTime3);
		f3.Append("   \n" + "    Average Time for Small Arrays is " + avgTime4);
		f4.Append("    \n"
				+ "     Average Time for the over all Improvements is "
				+ avgTime1);
		f11.Append("   \n" + "    Average Time for Small Arrays is " + avgTime2);
	}
}


