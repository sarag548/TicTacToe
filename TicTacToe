import java.util.*;

public class TicTacToe{
    public static Scanner scanner = new Scanner(System.in);
    
    public static char[][] gameBoard = new char[3][3];
    public static int rowNumber;
    public static int columnNumber;
    public static char playerTurn = 'X';
    public static char winner;
    public static boolean isWinner = false;
    public static boolean isTie = false;
    
    public static void initializeBoard(){
        gameBoard = new char[][]{
            {'_', '_', '_'},
            {'_', '_', '_'},
            {'_', '_', '_'}
        };
    }
    
    public static void displayBoard(){
       for(char[] row : gameBoard){
           for(char mark : row){
               System.out.print(mark + " ");
           }
           System.out.println();
       }
    }
    
    public static void getPlayerInput(){
        System.out.print("Enter row number where you wish to place your mark: ");
        rowNumber = scanner.nextInt();
        System.out.println();
        System.out.print("Enter column number where you wish to place your mark: ");
        columnNumber = scanner.nextInt();
    }
    
    public static void updateBoard(){
        if((rowNumber < 0 || columnNumber < 0) || (rowNumber > 2 || columnNumber > 2)){
            System.out.println("That index is out of bounds. Try again");
        }
        else if(gameBoard[rowNumber][columnNumber] != '_'){
            System.out.println("That spot is already taken. Try again");
        }
        else{
            if(playerTurn == 'X'){
                gameBoard[rowNumber][columnNumber] = 'X';
            }
            else{
                gameBoard[rowNumber][columnNumber] = 'O';
            }
            checkForWinner();
            checkForTie();
            switchPlayerTurn();
        }
    }
    
    public static void checkForWinner(){
        for(int rowIndex=0; rowIndex<3; rowIndex++){
            if(gameBoard[rowIndex][0] == playerTurn && gameBoard[rowIndex][1] == playerTurn && gameBoard[rowIndex][2] == playerTurn){
                isWinner = true;
            }
        }
        for(int columnIndex=0; columnIndex<3; columnIndex++){
            if(gameBoard[0][columnIndex] == playerTurn && gameBoard[1][columnIndex] == playerTurn && gameBoard[2][columnIndex] == playerTurn){
                isWinner = true;
            }
        }
        if(gameBoard[0][0] == playerTurn && gameBoard[1][1] == playerTurn && gameBoard[2][2] == playerTurn){
            isWinner = true;
        }
        if(gameBoard[0][2] == playerTurn && gameBoard[1][1] == playerTurn && gameBoard[2][0] == playerTurn){
            isWinner = true;
        }
        if(isWinner == true){
            System.out.println("Game over. Player " + playerTurn + " wins!");
            System.exit(0);
        }
        
    }
    
    public static void checkForTie(){
        isTie = true;
        for(char[] row : gameBoard){
            for(char mark: row){
                if(mark == '_'){
                    isTie = false;
                }
            }
        }
        if(isTie == true){
            System.out.println("Game over. The game ended in a tie. Neither player wins");
            System.exit(0);
        }
    }
    
    public static void switchPlayerTurn(){
        if(playerTurn == 'X'){
            playerTurn = 'O';
        }
        else{
            playerTurn = 'X';
        }
    }
    
    public static void playGame(){
        initializeBoard();
        while(!isWinner && !isTie){
            displayBoard();
            System.out.println("Player turn: " + playerTurn);
            getPlayerInput();
            updateBoard();
        }
    }
    
    public static void main(String[] args){
        playGame();
    }
}
