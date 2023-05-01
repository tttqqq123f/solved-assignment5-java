Download Link: https://assignmentchef.com/product/solved-assignment5-java
<br>
<p class="ui header product-top-header" title="Assignment5.java Solution">You are required, but not limited, to turn in the following source files:

Assignment5.java (Download this file and use it as your driver program for this assignment. You need to add more codes to complete it.)Soup.javaSoupInBox.javaSoupInCylinder.javaSoupParser.java

Requirements to get full credits in Documentation

The assignment number, your name, StudentID, Lecture number/time, and a class description need to be included at the top of each class/file.A description of each method is also needed.Some additional comments inside of methods (especially for a “main” method) to explain code that are hard to follow should be written.You can look at Java programs in the text book to see how comments are added to programs.

Skills to be Applied

In addition to what has been covered in previous assignments, the use of the following items, discussed in class, will probably be needed:

InheritanceThe protected modifierThe super ReferenceAbstract classNumberFormat/DecimalFormatWrapper classesArrayList

Program Description

Class Diagram:

In Assignment #5, you will need to make use of inheritance by creating a class hierarchy for vehicles.

Soup is an abstract class, which represents the basic attributes of any soup in a container to be sold. It is used as the root of the soup hierarchy. It has the following attributes (should be protected):

Attribute nameAttribute typeDescriptionvolumeintThe volume of the soupunitPricedoubleThe price per unit of the souptotalPricedoubleThe total price of the soupsoupIdStringThe Id of the soupThe following constructor method should be provided to initialize the instance variables.

public Soup(String id, double someUnitPrice)

The instance variable volume is initialized to 0, totalPrice is initialized to 0.0, unitPrice is initialized to the value of the second parameter, and soupId is initialized to the string value of the first parameter.

The following accessor method should be provided for soupId :

public String getSoupId()

The Class Soup also has an abstract method (which should be implemented by its child classes, SoupInCylinder and SoupInBox) to compute the volume of the soup:

public abstract void computeTotalPrice();

The following public method should be provided:

public String toString()

toString method returns a string of the following format:


The SoupId:tttomatosoup591
The Volume:tt150
The Unit Price:tt0.0015
The Total Price:t$330.00



You should make use of the NumberFormat class and DecimalFormat (in java.text package) to format the total price in the dollar format (NumberFormat) and the unit price using 4 digits after their decimal point (DecimalFormat using “0.0000”).

SoupInCylinder class

SoupInCylinder is a subclass of Soup class. It represents a soup in a can (cylinder). It has the following attribute in addition to the inherited ones:

Attribute nameAttribute typeDescriptionradiusintThe radius of the cylinder of the soup.heightintThe height of the cylinder of the soup.The following constructor method should be provided:

public SoupInCylinder(String id, double someUnitPrice, int someRadius, int someHeight)

The radius is initialized to the value of the third parameter, the height is initialized to the value of the forth parameter, and the constructor of the parent class Soup should be called using the first and second parameters. Leave volume and totalPrice as their default values (defined in the parent’s constructor).

The following method should be implemented:

public void computeTotalPrice()

First, it computes the volume for the cylinder of the soup. (computed by PI*(radius*radius*height), the constant value PI is defined in the Math class. — (int) (Math.PI*(radius*radius*height)) Also, compute (radius*radius*height) first since they are all integers. PI is a float point number, so you need to cast the final value to an integer (“volume” is an integer.) Then compute the total price of the soup. (computed by volume * unitPrice)

Also, the following method should be implemented:

public String toString()

The toString() method inherited from Soup class should be used to create a new string, and display a cylinder soup’s information using the following format:


The Soup in a Cylinder Container
The Radius:tt5
The Height:tt10
The SoupId:tttomatosoup591
The Volume:tt785
The Unit Price:tt0.0022
The Total Price:t$1.73



This toString method should make use of the toString method of the parent class.

SoupInBox class

SoupInBox is a subclass of Soup class. It represents a soup in a carton. It has the following attributes:

Attribute nameAttribute typeDescriptionheightintThe height of the box of the soup.widthintThe width of the box of the soup.depthintThe depth of the box of the soup.The following constructor method should be provided:

public SoupInBox(String id, double someUnitPrice, int someHeight, int someWidth, int someDepth)

The height, width, depth are initialized to the value of the third parameter, the fourth parameter, and the fifth parameter, respectively, and the constructor of the parent class Soup should be called using the first and second parameters. Leave volume and totalPrice as their default value.

The following method should be implemented:

public void computeTotalPrice()

First, it computes the volume of the box of the soup. (computed by height*width*depth)Then compute the total price of the soup. (computed by volume * unitPrice)

Also, the following method should be implemented:

public String toString()

The toString() method inherited from the Soup class should be used to create a new string, and display a box soup’s information using the following format:


The Soup in a Box Container
The Height:tt5
The Width:tt10
The Depth:tt5
The SoupId:ttsplitPeaSoup515
The Volume:tt250
The Unit Price:tt0.0055
The Total Price:t$1.38



This toString method should make use of the toString method of the parent class.

SoupParser class

The SoupParser class is a utility class that will be used to create a soup object (either a cylinder soup object or a box soup object) from a parsable string. The SoupParser class object will never be instantiated. It must have the following method:

public static Soup parseStringToSoup(String lineToParse)

The parseStringToSoup method’s argument will be a string in the following format:

For a cylinder soup,

shape/soupId/unitPrice/radius/height

For a box soup,

shape/soupId/unitPrice/height/width/depth

A real example of this string would be:

Cylinder/tomateSoup514/0.0054/5/10

OR

Box/splitPeaSoup7192/0.0035/10/15/10

This method will parse this string, pull out the information, create a new SoupInCylinder or SoupInBox object using their constructor with attributes of the object, and return it to the calling method. The type will always be present and always be either Cylinder or Box. (It can be lower case or upper case) You may add other methods to the SoupInCylinder and SoupInBox class in order to make your life easier.

Assignment5 class

In this assignment, download Assignment5.java file by clicking the link, and use it for your assignment. You need to add code to this file. The parts you need to add are written in the Assignment5.java file, namely for the four cases “Add Soup”, “Add Compute Total Prices”, “Search for Soup”, and “List Soups”.

All input and output should be handled here. The main method should start by displaying this updated menu in this exact format:

ChoicettAction
——tt——
AttAdd Soup
CttCompute Total Prices
DttSearch for Soup
LttList Soups
QttQuit
?ttDisplay Help



Next, the following prompt should be displayed:

What action would you like to perform?


Read in the user input and execute the appropriate command. After the execution of each command, redisplay the prompt. Commands should be accepted in both lowercase and uppercase.

Add Soup

Your program should display the following prompt:

Please enter a soup information to add:


Read in the information and parse it using the soup parser.

Then add the new soup object (created by soup parser) to the soup list.

Compute Total Prices

Your program should compute total price for all soups created so far by calling computeTotalPrice method for each of them in the soup list.

After computing total prices, display the following:

total prices computed


Search for Soup

Your program should display the following prompt:

Please enter a soupId to search:


Read in the string and look up the soup list, if there exists a soup object with the same soup ID, then display the following:

soup found


Otherwise, display this:

soup not found


List Soups

List all soups in the soup list. Make use of toString method defined in SoupInBox and SoupInCylinder classes.

A real example is looked like this:

The Soup in a Cylinder ContainerThe Radius: 5The Height: 10The SoupId: chickensoup200The Volume: 0The Unit Price: 0.0054The Total Price: $0.00

The Soup in a Box ContainerThe Height: 10The Width: 15The Depth: 10The SoupId: tomatosoup03The Volume: 0The Unit Price: 0.0035The Total Price: $0.00

If there is no soup in the soup list (the list is empty), then display following:

no soup


Quit

Your program should stop executing and output nothing.

Display Help

Your program should redisplay the “choice action” menu.

Invalid Command

If an invalid command is entered, display the following line:

Unknown action


Test cases:

You can download each file individually:

Input

The following files are the test cases that will be used as input for your program (Right-click and use “Save As”):

Test Case #1Test Case #2Test Case #3Test Case #4

Output

The following files are the expected outputs of the corresponding input files from the previous section (Right-click and use “Save As”):

Test Case #1Test Case #2Test Case #3Test Case #4