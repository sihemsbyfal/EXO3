# EXO3
/**
 * Created by Sihem on 16/10/2015.
 */
 import  java.util.Scanner;
public class Banc {
    public static void main(String[]args){

        @SuppressWarnings("resource")
        Scanner Read=new Scanner(System.in);
        System.out.println(" votre nom svp :");
        String nom=Read. nextLine();
        System.out.println(" votre numero de compte  svp :");
        String numcompte=Read. nextLine();
        System.out.println(" votre solde svp :");
        double solde=Read.nextDouble();
        System.out.println(" introduire votre taux d'interets si vous avez ;)  :");
        double taux=Read.nextDouble();
        Comptebanc compte1 = new Comptebanc(nom, numcompte, solde, taux);
        System.out.print(" vous etes lez bienvenue dans notre banque :) ");
        while(1<2){
            System.out.println(" voila Notre menue ");
            System.out.println("1/consultez votre solde");
            System.out.println("2/ajout a cet compte");
            System.out.println("3/retrait de cet compte");
            System.out.println("4/voir vos interets");

            @SuppressWarnings("unused")
            int rep;
            int rep1=Read.nextInt();
            switch(rep1){
                case 1:
                    System.out.println("votre solde est :"+compte1.getsolde()+"DA");
                    break;
                case 2:
                    System.out.println(" Combien svp   :");
                    System.out.println("mais un montant > 0   ;)");
                    double montant=Read.nextDouble();
                    System.out.print("votre solde est maintenant : ");
                    compte1.Ajouter(montant);
                    break;
                case 3:
                    System.out.println(" combien svp  :");
                    double some=Read.nextDouble();

                    System.out.println(" votre solde est maintenant : ");
                    compte1.Retrait(some);
                    break;
                case 4:
                    System.out.print("quelle est le pourcentage de votre interet ");
                    @SuppressWarnings("unused")
                    double p=Read.nextDouble();
                    System.out.print("%");
                    System.out.println("est voilà votre taux d'interets : "+compte1.calcul()+"D.A");
                    break;
                default :
                    System.out .println(" on t'excuse on a pas d'autre services merci :) ");
                    break;}
            System.out.print(compte1);











        }





    }




}

/**
 * Created by Sihem on 16/10/2015.
 */
public class Comptebanc {
    private String nom;
    private String numcompte;
    private double solde;
    private double taux;
    public Comptebanc(String nom,String numcompte,double solde,double taux){
        this.nom=nom;
        this.numcompte=numcompte;
        this.solde=solde;
        this.taux=taux;
    }




    public void Ajouter (double montant) {
        solde += montant;}
    public void Retrait (double montant) {
        solde -= montant;}

    public String toString () {
        return "Compte numéro " + numcompte + "\n ouvert au nom de " + nom +"\n le taux d'interets de client "+taux+"\n Le solde actuel du compte est de " +solde + " D.A.";}





    public double calcul(){

        return (solde*taux)/100;}



    //****************** getters ****************//
    public double getsolde()
    {return solde;}

    public String getnom(){

        return nom;
    }
    public String getnumcompte() {
        return numcompte;
    }
    //******** setters ****//
    public void settaux(double t){
        taux=t;}






}
