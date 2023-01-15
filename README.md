## Encapsulation

### Description

In this exercise you will create one class and name it <b>Printer</b>. This class will have two member variables of type <b>int</b>, <b>tonerLevel</b> and <b>pagesPrinted</b>, and one of type <b>boolean</b> called <b>duplex</b>. All three fields will have <b>private</b> access. The constructor will accept two of these variables, <b>tonerLevel</b> and <b>duplex</b>, as parameters following these rules:

<ul>
<li><b>tonerLevel</b> must be greater than -1 but less than or equal to 100. If it does not meet these conditions then it should be initialized to -1.</li>
<li><b>duplex</b> should be initialized to the value of the parameter. </li>
</ul>

In addition, <b>pagesPrinted</b> should be initialized to 0.

Three other methods need to be defined in this way:

1. <b>addToner</b> will accept one parameter, <b>tonerAmount</b> of type <b>int</b>. First off, <b>tonerAmount</b> should be greater than 0 and less than or equal to 100. If this condition is met a second test must be included to test whether <b>tonerLevel</b> plus <b>tonerAmount</b> is greater than 100. If so, the method should return -1. If not then <b>tonerLevel</b> should have the incoming <b>tonerAmount</b> added to it and the new <b>tonerLevel</b> should then be returned by the method. Also, if the initial condition test fails, then the method should return -1.

2. <b>printPages</b> will accept one parameter, <b>pages</b> of type <b>int</b>. A variable called <b>pagesToPrint</b> should be created and initialized to the value of the incoming parameter. A conditional check should be performed on whether the <b>Printer</b> class field, <b>duplex</b>, is either "true" or "false". If "true" then a calculation must be performed to determine the number of pages needed to print the job double sided. The <b>pagesToPrint</b> value is then added to the class field <b>pagesPrinted</b>, but the value of <b>pagesToPrint</b> should be returned by the method.

3. <b>getPagesPrinted</b> has no parameters and merely returns the value of the member variable <b>pagesPrinted</b>.

### Test Code

    Printer printer = new Printer(50, true);
    System.out.println(printer.addToner(50));
    System.out.println("initial page count = " +printer.getPagesPrinted());
    int pagesPrinted = printer.printPages(4);
    System.out.println("Pages printed was " + pagesPrinted +" new total print count for printer = " +printer.getPagesPrinted());
    pagesPrinted = printer.printPages(2);
    System.out.println("Pages printed was " + pagesPrinted +" new total print count for printer = " +printer.getPagesPrinted());

### Output

    100
    initial page count = 0
    Printing in duplex mode
    Pages printed was 2 new total print count for printer = 2
    Printing in duplex mode
    Pages printed was 1 new total print count for printer = 3
