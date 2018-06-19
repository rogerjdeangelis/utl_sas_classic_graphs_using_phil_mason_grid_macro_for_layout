# utl_sas_classic_graphs_using_phil_mason_grid_macro_for_layout
SAS classic graphs using phil mason grid macro for layout.  Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    SAS classic graphs using phil mason grid macro for layout

    see
    https://tinyurl.com/y9dhwsuz
    https://github.com/rogerjdeangelis/utl_sas_classic_graphs_using_phil_mason_grid_macro_for_layout/blob/master/utl_sas_classic_graphs_using_phil_mason_grid_macro.png


    github
    https://tinyurl.com/y9dhwsuz
    https://github.com/rogerjdeangelis/utl_sas_classic_graphs_using_phil_mason_grid_macro_for_layout


    INPUT
    =====

     WORK.TRIG total obs=100

      N       X1         X2          Y1          Y2

      1    0.06246     0.12467     0.99805     0.99220
      2    0.12467     0.24740     0.99220     0.96891
      3    0.18640     0.36627     0.98247     0.93051
      4    0.24740     0.47943     0.96891     0.87758
      5    0.30744     0.58510     0.95157     0.81096
      6    0.36627     0.68164     0.93051     0.73169
      7    0.42368     0.76754     0.90581     0.64100
      8    0.47943     0.84147     0.87758     0.54030
      9    0.53330     0.90227     0.84592     0.43118
     10    0.58510     0.94898     0.81096     0.31532
     11    0.63461     0.98089     0.77283     0.19455
     12    0.68164     0.99749     0.73169     0.07074
    .....

    EXAMPLE OUTPUT


     1 +           AAAAAAAAAA               1 +       A AA A A  A AA A A
       |       AAAA         AAAA              |  AAAA                   A AAA
       |     AAA                AB            |BA                           AB
       |   AB                     AA          |C                             B
       |  AA                       AA         | AA                          B
       | AA                         AA        |   AA                      AA
       | B                           B        |     A A                AA
       |A                             B       |        A            AA
       |B                             B       |          A A    A A
     0 +B                             B     0 +             AAAA
       |B                             A       |            A     AA
       |AA                            B       |        A A          A A
       | A                           B        |     AA                 A
       | AA                         AA        |   AA                     AA
       |  AB                       AA         | AA                         AB
       |    B                    AAA          |C                             B
       |     AB                 AA            |AA                           AB
       |       AAAA          ABA              | AAAA                    AAAA
    -1 +           ABAAAAAAAA               1 +      AA A A A AA A A AA
       -+--------------+--------------+       -+--------------+--------------+
       -1              0              1       -1              0              1


     1 +             BBBBB                  1 +B                             B
       |           AC     BB                  |B                             A
       |          BA        C                 |B                            AA
       |         B           BA               | B                           B
       |        B             B               |  B                         AA
       |       B               B              |   B                       AA
       |      AA                B             |    B                    AAA
       |      B                  A            |     BA                 B
       |     B                   B            |       ABAAAAAAAAAAAAAAA
     0 +    B                    AA         0 +       BBBBBBBBBBBBBBBB
       |    B                     A           |     AA                AAB
       |   B                       B          |   AB                     AA
       |   B                       B          |  AA                       AA
       |  B                         B         | AA                         AA
       |  B                         B         | B                           B
       | B                           C        |A                             B
       | B                           C        |B                             B
       |BB                            D       |
     1 +F                             E    -1 +
       -+--------------+--------------+       -+--------------+--------------+
       -1              0              1       -1              0              1


    PROCESS

    proc catalog cat=work.gseg kill;
    run;quit;

    options orientation=landscape;
    filename gsf "d:\png\&pgm..png";
    goptions reset=global nodisplay  gsfname=gsf device=png target=png
    htext=6pct
    hsize=10.5in vsize=7in;

    proc gplot data=trig;
       title 'Y1 by X1';
       plot y1*x1;
    run;
       title 'Y1 by X2';
       plot y1*x2;
    run;
       title 'Y2 by X1';
       plot y2*x1;
    run;
       title 'Y2 by X2';
       plot y2*x2;
    run;

    title 'Four Marvellous Graphs';
    %grid( gplot*4, rows=2, cols=2);


    OUTPUT
    ======



    *                _               _       _
     _ __ ___   __ _| | _____     __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \   / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/  | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|   \__,_|\__,_|\__\__,_|

    ;

    data trig;
       do n=1 to 100;
          x1=sin(n/16);
          x2=sin(n/8);
          y1=cos(n/16);
          y2=cos(n/8);
          output;
       end;
    run;

    *                _
     _ __ ___   __ _| | _____   _ __ ___   __ _  ___ _ __ ___  ___
    | '_ ` _ \ / _` | |/ / _ \ | '_ ` _ \ / _` |/ __| '__/ _ \/ __|
    | | | | | | (_| |   <  __/ | | | | | | (_| | (__| | | (_) \__ \
    |_| |_| |_|\__,_|_|\_\___| |_| |_| |_|\__,_|\___|_|  \___/|___/

    ;

    /* T005130 PHIL MASON GRID MACRO */
    *********************************************************************************************************************
    /* PHIL MASON GREPLAY MACRO */
           name: grid
          title: Replay graphs in a regular grid
        product: graph
         system: all
          procs: greplay gslide
        support: saswss                      update:  10jul95

     DISCLAIMER:

           THIS INFORMATION IS PROVIDED BY SAS INSTITUTE INC. AS A SERVICE
     TO ITS USERS.  IT IS PROVIDED "AS IS".  THERE ARE NO WARRANTIES,
     EXPRESSED OR IMPLIED, AS TO MERCHANTABILITY OR FITNESS FOR A
     PARTICULAR PURPOSE REGARDING THE ACCURACY OF THE MATERIALS OR CODE
     CONTAINED HEREIN.

     The %GRID macro lets you easily replay graphs in a regular grid with
     one or more rows and one or more columns. The %GRID macro also
     supports titles and footnotes for the entire replayed graph. For
     example, if you have run GPLOT four times and want to replay these
     graphs in a 2-by-2 grid with the title 'Four Marvellous Graphs', you
     could submit the following statements:

        title 'Four Marvellous Graphs';
        %grid( gplot*4, rows=2, cols=2);

     The %GRID macro allows 10% of the vertical size of the graph for
     titles by default. You can adjust this percentage via the TOP=
     argument in %GRID. Determining the best value for TOP= requires
     trial and error in most cases. To allow space for footnotes, use
     the BOTTOM= argument.

     The graphs to replay must be stored in a graphics catalog with
     library and member names specified by the macro variables &glibrary
     and &gout. By default, SAS/GRAPH stores graphs in WORK.GSEG, which
     is the catalog that the %GRID macro uses by default.  If your
     graphs are in another catalog, you must specify &glibrary and/or
     &gout using %LET statements as shown below.

     Each graph that is stored in a catalog has a name. Each procedure
     assigns default names such as GPLOT, GPLOT1, GPLOT2, etc. Most
     SAS/GRAPH procedures let you specify the name via a NAME= option
     which takes a quoted string that must be a valid SAS name. However,
     if a graph by that name already exists in the catalog, SAS/GRAPH
     appends a number to the name; it does not replace the previous graph
     by the same name unless you specify GOPTIONS GOUTMODE=REPLACE, but
     this option causes _all_ entries in the catalog to be deleted
     every time you save a new graph, so it is not very useful. If you want
     to replace a single graph in a catalog, sometimes you can use the
     %GDELETE macro to delete the old one and later recreate a graph with
     the same name, but this does not work reliably due to a bug in
     SAS/GRAPH. By default, %GDELETE deletes _everything_ in the catalog;
     this does seem to work reliably.

     When you use BY processing, SAS/GRAPH appends numbers to the graph
     name to designate graphs for each BY group. For example, if you run
     GPLOT with three BY groups and NAME='HENRY', the graphs are named
     HENRY, HENRY1, and HENRY2. The %GRID macro lets you abbreviate this
     list of names as HENRY*3, where the repetition factor following the
     asterisk is the total number of graphs, not the number of the last
     graph.

     *********************************************************************/

    %let glibrary=WORK;
    %let gout=GSEG;

    %macro grid(  /* replay graphs in a rectangular grid */
       list,      /* list of names of graphs, separated by blanks;
                     a name may be followed by an asterisk and a
                     repetition factor with no intervening blanks;
                     for example, ABC*3 is expanded to: ABC ABC1 ABC2 */
       rows=1,    /* number of rows in the grid */
       cols=1,    /* number of columns in the grid */
       top=10,    /* percentage at top to reserve for titles */
       bottom=0); /* percentage at bottom to reserve for footnotes */

       %gtitle;
       %greplay;
       %tdef(rows=&rows,cols=&cols,top=&top,bottom=&bottom)
       %trep(&list,rows=&rows,cols=&cols)
       run; quit;
    %mend grid;


    %macro gdelete(list); /* delete list of graphs from the catalog;
                             default is _ALL_ */

       %if %bquote(&list)= %then %let list=_ALL_;
       proc greplay igout=&glibrary..&gout nofs;
          delete &list;
       run; quit;
    %mend gdelete;


    %macro gtitle; /* create graph with titles and footnotes only */

       %global titlecnt;
       %if %bquote(&titlecnt)= %then %let titlecnt=1;
                               %else %let titlecnt=%eval(&titlecnt+1);
       goptions nodisplay;
       proc gslide gout=&glibrary..&gout name="title&titlecnt";
       run;
       goptions display;
    %mend gtitle;


    %macro greplay( /* invoke PROC GREPLAY */
       tc);         /* template catalog; default is JUNK */

       %if %bquote(&tc)= %then %let tc=junk;
       proc greplay nofs tc=&tc;
          igout &glibrary..&gout;
    %mend greplay;


    %macro tdef(  /* define a template for a rectangular grid */
       rows=1,    /* number of rows in the grid */
       cols=1,    /* number of columns in the grid */
       top=10,    /* percentage at top to reserve for titles */
       bottom=0); /* percentage at bottom to reserve for footnotes */
       %global tdefname; /* returned: name of template */

       %local height width n row col lower upper left right;
       %let height=%eval((100-&top-&bottom)/&rows);
       %let width =%eval(100/&cols);
       %let tdefname=t&rows._&cols;
       tdef &tdefname
          0/ulx=0 uly=100 llx=0 lly=0 urx=100 ury=100 lrx=100 lry=0
       %let n=1;
       %do row=1 %to &rows;
          %let lower=%eval(100-&top-&row*&height);
          %let upper=%eval(&lower+&height);
          %do col=1 %to &cols;
             %let right=%eval(&col*&width);
             %let left =%eval(&right-&width);
             &n/ulx=&left uly=&upper llx=&left lly=&lower
                urx=&right ury=&upper lrx=&right lry=&lower
             %let n=%eval(&n+1);
          %end;
       %end;
       ;
       template &tdefname;
    %mend tdef;

    %macro trep( /* replay graphs using template defined by %TDEF */
       list,     /* list of names of graphs, separated by blanks;
                    a name may be followed by an asterisk and a
                    repetition factor with no intervening blanks;
                    for example, ABC*3 is expanded to: ABC ABC1 ABC2 */
       rows=,    /* (optional) number of rows in template */
       cols=);   /* (optional) number of columns in template */
                 /* rows= and cols= default to values set with %TDEF */

       %global titlecnt;
       %local i l n row col name root suffix nrep;
       %if %bquote(&rows)= %then %let rows=%scan(&tdefname,1,t_);
       %if %bquote(&cols)= %then %let cols=%scan(&tdefname,2,t_);
       treplay 0:title&titlecnt
       %let nrep=0;
       %let l=0;
       %let n=0;
       %do row=1 %to &rows;
          %do col=1 %to &cols;
             %let n=%eval(&n+1);
             %if &nrep %then %do;
                %let suffix=%eval(&suffix+1);
                %if &suffix>=&nrep %then %do;
                   %let nrep=0;
                   %goto tryagain;
                %end;
                %let name=&root&suffix;
                %goto doit;
             %end;
    %tryagain:
             %let l=%eval(&l+1);
             %let name=%qscan(&list,&l,%str( ));
             %if &name= %then %goto break;
             %let i=%index(&name,*);
             %if &i %then %do;
                %let nrep=%substr(&name,&i+1);
                %if &nrep<=0 %then %goto tryagain;
                %let root=%substr(&name,1,&i-1);
                %let name=&root;
                %let suffix=0;
             %end;
    %doit:
             &n:&name
          %end;
       %end;
    %break:
       ;
    %mend trep;

