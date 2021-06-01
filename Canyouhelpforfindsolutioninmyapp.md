Hello guys !!
I have problem in m'y application javaFx
How display foreign key in tableView 
I don't find solution car you help me 
This is m'y code 
He used name table in language french 
Département : départment
Employés : employée
Num_départ: number of département
Lieu_dept: location 
Matricule : id
Nom: firstname
Prénom :lastname
He used attribute to Number of department type object not type int

I have 2 table 
Departement(Num_depart,Nom_depart,lieu_depart)
employee(matricule,nom,prenom,adresse, #Num_depart)

table employee

public class employee {
    private  int matricule;
    private  String nom;
    private  String prenom;
    private  String adresse;
    private  Departement departement;

table Departement

public class Departement {
    private   int Num_depart;
    private   String Nom_depart;
    private   String lieu_depart;

public void showEmployee() throws SQLException {
        List = getEmployee();
        Matricule_Dcolumn.setCellValueFactory(new PropertyValueFactory<employee, Integer>("matricule"));
        Nom_DColumn.setCellValueFactory(new PropertyValueFactory<employee, String>("nom"));
        Prenom_DColumn.setCellValueFactory(new PropertyValueFactory<employee, String>("prenom"));
        Adress_Dcolumn.setCellValueFactory(new PropertyValueFactory<employee, String>("adresse"));
        
        Departement.setCellValueFactory(new Callback <CellDataFeatures<employee,String>,ObservableValue<String>>(){

                @Override
                public ObservableValue<String> call(CellDataFeatures<employee, String> param) {
                    return new SimpleStringProperty(param.getValue().getdepartement().getNom_depart() );
                }
            });
