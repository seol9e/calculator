# calculator
#include <iostream>
#include <conio.h>
#include <stdio.h>
#include <math.h> 

using namespace std;
int f;
void lectura ( double arreglo[], int n)
{
  int i, j;
  for (i=0;i<n;i++)
    {
    cout << "Ingrese el numero:  ";
    cin >> arreglo [i];
    }
}

void escribir (double arreglo[], int n )
{
  int i, j;
  for (i=0;i<n;i++)
  {
      cout << arreglo[i] << ",";
  }
  cout<<"\n";
}
void suma(int &f){
	 int n;
     double suma=0;
	 cout<<"Ingrese cuantos valores desea sumar\n";
	 cin>>n;
	 double nas[n] ;
	 lectura(nas,n);
	 for (int i=0 ; i<n ;i++)
	 suma = nas[i]+suma;
	 cout<<"La suma de los numeros es: "<<suma;
	 }
void resta(int &f){
	 int resta=0,a,b;
	 cout<<"Digite los dos numeros a restar\n";
	 cin >>a;
	 cin >>b;
	 resta=a-b;
	 cout<<"La resta de los numeros es: "<<resta;
	 }
void multiplicacion(int &f){
	 int n;
     double mul=1;
	 cout<<"Ingrese cuantos valores desea multiplicar\n";
	 cin>>n;
	 double nas[n] ;
	 lectura(nas,n);
	 for (int i=0 ; i<n ;i++)
	 mul = nas[i]*mul;
	 cout<<"La multiplicacion de los numeros es: "<<mul;
	 }
void division(int &f){
	 double div=1,a,b;
	 cout<<"Digite los dos numeros a dividir\n";
	 cin >>a;
	 cin >>b ;
	 if (b!=0) {
	 div=a/b ;
	 cout<<"La division de los numeros es: "<<div;
	 }
	 else 
	 cout<<"Error Matematico";
	 }
void potencia(int &f){
	 double pot;
	 double a,b;
	 cout<<"Digite el numero y luego la potencia a la que desea elevarlo\n";
	 cin >>a ;
	 cin >>b;
	 pot= pow(a,b);
	 cout<<a<<" elevado a la "<<b<<" es: "<<pot;
	 }
void raiz(int &f){
	 double a,b;
	 cout<<"\nDigite un numero para calcular su raiz cuadrada\n";
	 cin>>b ;
	 a=sqrt(b) ;
	 cout<<"La raiz cudrada de "<<b<<" es:  "<<a;
	 }
void pitagoras(int f){
     double h,a,b;
     cout<<"Desea averiguar un cateto o la hipotenusa?\n1.cateto\n2.hipotenusa\n";
     cin>>f;
     if(f==1){
         cout<<"Digite el valor de la hipotenusa\n";
         cin>>h;
         cout<<"Digite el valor del cateto\n";
         cin>>a;
      if(h>a){
      b=sqrt((pow(h,2)-pow(a,2)));
      cout<<"El valor del cateto es:  "<<b;
	  }
	  else 
	  cout<<"Error Matematico\n";
	  }
	  if (f==2){
	  	 		cout<<"Digite el valor de los catetos\n";
                cin>>a;
                cin>>b;
      h=sqrt((pow(a,2)+pow(b,2)));
      cout<<"El valor de la hipotenusa es:  "<<h<<"\n";
	  }
	  }
void llenarmatriz(int mat[][100], int n, int m)
{
     int i,j;
     for(i=0;i<n;i++){
     for(j=0;j<m;j++){
     cout<<"Ingrese el valor de la matriz en la fila "<<i<<" y columna "<<j<<endl;
     cin>>mat[i][j];
     }
     }
}
void escribirmatriz(int mat[][100],int n, int m){
     int i,j;
     for(i=0;i<n;i++){
     for(j=0;j<m;j++){
     cout<<mat[i][j]<<"  ";
     }
     cout<<endl;
     }
}
void suma_matriz(int mat[][100],int nat[][100],int sum[][100],int n,int m)
{
    int i,j;
     for(i=0;i<n;i++){
     for(j=0;j<m;j++){
     sum[i][j]=mat[i][j]+nat[i][j];
     }
     }
}
void resta_matriz(int mat[][100],int nat[][100],int res[][100],int n,int m)
{
    int i,j;
     for(i=0;i<n;i++){
     for(j=0;j<m;j++){
     res[i][j]=mat[i][j]-nat[i][j];
     }
     }
} 
void multi_matriz(int mat[][100],int nat[][100],int mul[][100],int n,int m,int p )
{
     int i,j,k;
     int ac=0;
     for(i=0;i<n;i++)
     {
       for(k=0;k<p;k++)
       {
         ac=0;
         for(j=0;j<m;j++)
         {
          ac=ac+(mat[i][j]*nat[j][k]);
         }
         mul[i][k]=ac;
       }  
     }
}
void Union (double conA[], int a, double conB[], int b)
{
     int i,j;
     double conC[a+b];
     
     for ( i=0; i<a; i++)
     {
         conC[i] = conA[i];  
     }
     for (j=0; j<b; j++)    
     {
     conC[j+i]=conB [j];
     }   

escribir (conC, (a+b));
}
void interseccion (double conA[], int a, double conB[], int b)
{
     int i,j, n=0;
     double conC [a+b];
     for (i=0; i<a; i++)
     {
         for (j=0; j<b; j++)
         {
         if (conA[i] == conB[j])
         {
               conC [n] =conA[i];
               n++;
         }
         }
     }
  escribir (conC, n); 
}
void pertenece (double conA[], int a, double conB[], int b, int n)
{
     int i;
     int per=0;
     for (i=0; i<a; i++)
     {
         if ( conA[i] == n)
         {  per = per+1; }
         
         else {per = 0;}
     }
     
     if (per == 0)
     { cout<<"\nEl elemento " <<n << " NO pertenece al conjunto A\n";}
     else {  cout << "\nEl elemento " <<n<< " pertenece al conjunto A\n"; }
     
     per =0;
     for (i=0; i<b; i++)
     {
         if (conB[i] == n)
         {  per = per +1; }
         
         else { per =0;}
     }
 
     if (per == 0)
     { cout<<"\nEl elemento " <<n << " NO pertenece al conjunto B\n"; }
     else {cout << "\nEl elemento " <<n<< " pertenece al conjunto B\n";}
} 
int matrices (int &f)
{
  int matA[100][100],matB[100][100],rta[100][100];
  	cout << "\n\n\nQue desea hacer?\n";     
    while (f!=4){
     cout << "\n1.Sumar \n2.Restar \n3.Multiplicar\n4.Salir al Menu Principal\n";
     cin >> f;
     
     int a,b,c;
    if(f<=2){
    cout<<"Ingrese el numero de filas de las matrices\n";
    cin>>a;
    cout<<"Ingrese el numero de columnas de las matrices\n";
    cin>>b;
    llenarmatriz(matA,a,b);
    cout<<"La primera matriz que ingreso fue  :\n";
    escribirmatriz(matA,a,b);
    llenarmatriz(matB,a,b);
    cout<<"La segunda matriz que ingreso fue  :\n";
    escribirmatriz(matB,a,b);
    }
    else if(f==3)
    {
         cout<<"Ingrese el numero de filas de la primera matriz  : \n";
    cin>>a;
    cout<<"Ingrese el numero de columnas de la primera matriz :\n";
    cin>>b;
    cout<<"Ingrese el numero de columnas de la segunda matriz :\n";
    cin>>c;
    llenarmatriz(matA,a,b);
    cout<<"La primera matriz que ingreso fue  :\n";
    escribirmatriz(matA,a,b);
    llenarmatriz(matB,b,c);
    cout<<"La segunda matriz que ingreso fue  :\n";
    escribirmatriz(matB,b,c);
    }
    if (f==1)
    {  
          cout << "La suma de las matrices es:   \n";
          suma_matriz (matA,matB,rta,a,b);
          escribirmatriz(rta,a,b);
          system("pause");    
    }
    
   if (f==2 )
    {
         cout << "La resta de las matrices es:   \n";
          resta_matriz (matA,matB,rta,a,b);
          escribirmatriz(rta,a,b);
          system("pause");
    }
     
   if ( f==3)
    {
        cout << "La multiplicacion de las matrices es:  \n";
          multi_matriz (matA,matB,rta,a,b,c);
          escribirmatriz(rta,a,c);
          system("pause");
    }
} 
}   
int conjuntos (int &f)
{
   int a, b, n;

   cout << "Ingrese el numero de elementos del conjunto A\n";
   cin >> a;	
   double conA[a];
    cout << "Ingrese los elementos del conjunto A\n";
    lectura (conA, a);     
    cout << "Ingrese el numero de elementos del conjunto B\n";
    cin >> b;	
    double conB[b];    
    cout << "Ingrese los elementos del conjunto B\n";
    lectura (conB, b);
    cout << "\nEl conjunto A es: ";
    escribir (conA, a);    
    cout << "\nEl conjunto B es: ";
    escribir (conB, b);
	cout << "\n\n\nQue desea hacer?\n";     
    while (f!=4){
     cout << "\n1.Union \n2.Interseccion \n3.Pertenece\n4.Salir al Menu Principal\n ";
     cin >> f;
    if (f ==1)
    {
          cout << "La union es:    \n";
          Union (conA, a, conB, b); 
          system("pause");    
    }
    
   if (f==2 )
    {
         cout << "La interseccion es:  \n";
         interseccion (conA, a, conB, b);
         system("pause"); 
    }
     
   if ( f==3)
    {
         cout << "Ingrese un numero entero:\n";
         cin >> n;
         pertenece (conA, a, conB, b, n);
         system("pause");
    }    
}    
}

void seno(int &f){
	double h,b,co  ;
	cout<<"Digite la hipotenusa y el angulo ß en radianes \n";
	cin>>h ;
	cin>>b;
	co= h*sin(b) ;
	cout<<"El valor del cateto opuesto es: "<<co;
}
void coseno(int &f){
	double h,b,ca  ;
	cout<<"Digite la hipotenusa y el angulo ß en radianes\n";
	cin>>h ;
	cin>>b;
	ca= h*cos(b);
	cout<<"El valor del cateto adyacente es: "<<ca;
}
void tangente(int &f){
	double co,b,ca  ;
	cout<<"Digite el cateto adyacente y el angulo ß en radianes\n";
	cin>>ca ;
	cin>>b;
	if(b!=90){
	co= ca*tan(b);
	cout<<"El valor del cateto opuesto es: "<<co;
}
else
   cout<<"error matematico";
}
int submenut(int &f){
                      cout<<"\n\n";
                      cout<<"\nQue desea hacer?\n";
                      cout<<"1.Teorema de Pitagoras\n2.Seno\n3.Coseno\n4.Tangente\n5.Salir al Menu Principal\n";
                      cin>>f;
                      while (f!=5){
                            if(f==1)
                                    pitagoras(f);
                            if(f==2)
                                    seno(f);
                            if(f==3)
                                    coseno(f);
                            if(f==4)
                                    tangente(f);
                            getch();
                            submenut(f);
                                    }
                            
                                    }
                       
int menuprincipal(int &f) {
    cout<<"\n\n";
    system("pause");
	cout  << "\n\n\n1.Sumar \n2.Resta \n3.Multiplicacion \n4.Division \n5.Raiz Cuadrada\n6.Potenciacion\n7.Operaciones entre matrices";
	cout  << "\n8.Operaciones de conjuntos\n9.Solucion de Triangulos\n10.Salir\n"; 
	cin>>f;
	while(f!=10){
          if(f==1)
		  		   suma(f)  ;
	      if(f==2)
	              resta (f);
          if(f==3)
                  multiplicacion(f);
          if(f==4)
                  division(f);
          if(f==5)
                  raiz(f) ;
          if(f==6)
		  		  potencia(f);
          if(f==7)
		          matrices(f);	  
		  if(f==8)
		          conjuntos(f);
		  if(f==9)
		          submenut(f);  
		  
           menuprincipal(f)  ;     
				   }
	
	}
int main()
{
cout<<"Programa de calculadora\n ¿que operacion desea realizar?\n";
menuprincipal(f); 
	  
system("pause");
return 0;
}
