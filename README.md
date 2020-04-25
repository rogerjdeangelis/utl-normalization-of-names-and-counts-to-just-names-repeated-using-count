# utl-normalization-of-names-and-counts-to-just-names-repeated-using-count
Normalization of names and counts to just names repeated using count
    Normalization of names and counts to just names repeated using count

    github
    https://tinyurl.com/y8m3vmzl
    https://github.com/rogerjdeangelis/utl-normalization-of-names-and-counts-to-just-names-repeated-using-count

    *_                   _
    (_)_ __  _ __  _   _| |_
    | | '_ \| '_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    ;

    SAS Forum
    https://tinyurl.com/yas2t8fy
    https://communities.sas.com/t5/SAS-Data-Management/multivaraite-data-to-univariate-with-varaible-names-as-count/m-p/642959

    data have;
     input id onions patattoes milk egg;
    cards4;
    1 2 3 1 4
    ;;;;
    run;quit;

     WORK.HAVE total obs=1

     ID    ONIONS    PATATTOES    MILK    EGG

      1       2          3          1      4

    *            _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| '_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    ;

    WORK.WANT total obs=10

      ID    NAM

       1    ONIONS
       1    ONIONS
       1    PATATTOES
       1    PATATTOES
       1    PATATTOES
       1    MILK
       1    EGG
       1    EGG
       1    EGG
       1    EGG

    *
     _ __  _ __ ___   ___ ___  ___ ___
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    ;


    data want;
     set have;
     array fods onions--egg;
     do over fods;
       nam=vname(fods);
       items=fods;
       do i=1 to items;
         output;
       end;
     end;
     keep id nam ;
    run;quit;



