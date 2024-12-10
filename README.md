# Lab01- sumador 

### Nicolas Mateo Guio M.

@nguiom@unal.edu.co - Electronica Digital 1

## Informe de laboratorio

### sum1bcc_primitive:

Este codigo muestra el sumador de 1 bit siendo declarado por compuertas logicas. Primero se declaran las variables:

```
    input  A;
    input  B;
    input  Ci;
    output Cout;
    output S;
```
Ahora se crean las conexiones fisicas que van a tener:
```
    wire a_ab;
    wire x_ab;
    wire cout_t;
```
Y por ultimo las compuertas logicas:
```
    and(a_ab,A,B);
    xor(x_ab,A,B);

    xor(S,x_ab,Ci);
    and(cout_t,x_ab,Ci);

    or(Cout,cout_t,a_ab);
```
### sum1bcc

En el codigo se no se programan las puertas de manera explicita:

    reg [1:0] st;
    assign s = st[0];
    assign Cout = st[1];

Como los valores se almacenan es necesario un sistema que verifique las entradas constantemente, por lo que se usa un bucle:

    always @ (*)
    begin
        A+B+Ci;
    end

La siguiente imagen muestra una simulacion de las entradas y salidas que va a tener el sistema:

![image](/hi.jpg)
