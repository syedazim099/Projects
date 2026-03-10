
import java.util.Scanner;

	public class ProjectEliza {
	    public static void main(String[] args) {
	        String username;		
	        String word1; 
	        String word2; 
	        String reply; 
	        String runAgain = "yes"; 
	        
	        Scanner scnr = new Scanner(System.in); 
	        PromptBank eliza = new PromptBank(); 
	        eliza.populateQuestionsArray(); 
	        eliza.populateStatementsArray(); 
	        
	        while(runAgain.equalsIgnoreCase("yes")) {
	            String sentence = ""; 
	            System.out.println("Hello, my name is Eliza. What is your name?"); 
	            username = scnr.nextLine(); 
	            while(username.length() == 0) {
	                System.out.println("That's not a name. Please tell me what is your name?");
	                username = scnr.nextLine();
	            }
	            System.out.println("Hello, " + username + ". Tell me what is on your mind today in 1 sentence."); 
	            while(!(sentence.strip().equalsIgnoreCase("exit"))) { 
	                sentence = scnr.nextLine();
	                while(sentence.length() == 0) {		
	                    System.out.println("That's not a sentence. Please tell me what is on your mind today in 1 sentence.");
	                    sentence = scnr.nextLine();
	                }
	                String[] words = sentence.split(" "); 
	                word1 = words[0]; 
	                word2 = words[words.length - 1];
	                if(word1.equalsIgnoreCase("exit")) { 
	                    break;
	                }
	                else {
	                    if(Character.isAlphabetic(word2.charAt(word2.length() - 1))) {
	                        reply = eliza.getRandomStatementTrunk(); 
	                        reply = reply.replace("BLANK1", word1); 
	                        reply = reply.replace("BLANK2", word2); 
	                        System.out.println(reply);
	                    }
	                    else {
	                        if(word2.charAt(word2.length() - 1) == '?') { 
	                            word2 = word2.replace("?", ""); 
	                            reply = eliza.getRandomQuestionTrunk(); 
	                            reply = reply.replace("BLANK1", word1); 
	                            reply = reply.replace("BLANK2", word2); 
	                            System.out.println(reply);
	                        }
	                        else if(word2.charAt(word2.length() - 1) == '!') {
	                            word2 = word2.replace("!", ""); 
	                            reply = eliza.getRandomStatementTrunk(); 
	                            reply = reply.replace("BLANK1", word1); 
	                            reply = reply.replace("BLANK2", word2); 
	                            System.out.println("WOW! Dramatic! " + reply);
	                        } 
	                        else {
	                            word2 = word2.replace(Character.toString(word2.charAt(word2.length() - 1)), ""); 
	                            reply = eliza.getRandomStatementTrunk(); 
	                            reply = reply.replace("BLANK1", word1); 
	                            reply = reply.replace("BLANK2", word2); 
	                            System.out.println(reply);
	                        }
	                    }
	                }
	            }
	            System.out.println("Do you want to run the session again?");
	            runAgain = scnr.nextLine().strip();
	        }	
	        scnr.close();
	        System.out.println("Goodbye, until next time"); 
	        System.exit(0);
	    }
	}
