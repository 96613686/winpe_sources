# sqlite3Update

- ea: `0x18009f4a0`
- end: `0x1800a1fe8`
- name: `sqlite3Update`
- size: `11080`
- prototype: ``
- caller_count: `3`
- callee_count: `58`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030790`
- `0x1800a22b0`
- `0x1800d8b00`

## callees

- `0x180003a40`
- `0x180005980`
- `0x180023dd0`
- `0x1800273a0`
- `0x18002cae0`
- `0x180030320`
- `0x1800319d0`
- `0x18003a790`
- `0x18003c1a0`
- `0x18003c730`
- `0x18003ed20`
- `0x180040850`
- `0x180043e10`
- `0x180044640`
- `0x18004dba0`
- `0x18005bf90`
- `0x1800658d0`
- `0x18006be60`
- `0x18006cde0`
- `0x18006e230`
- `0x18006e530`
- `0x180071400`
- `0x1800714d0`
- `0x1800743d0`
- `0x180075ae0`
- `0x180077210`
- `0x1800795a0`
- `0x1800798f0`
- `0x18007d540`
- `0x18007e530`
- `0x18007e670`
- `0x18007f3e0`
- `0x180082640`
- `0x180083e40`
- `0x180086450`
- `0x180086590`
- `0x180086d20`
- `0x180088910`
- `0x1800893a0`
- `0x1800896a0`
- `0x180092550`
- `0x180095500`
- `0x18009bde0`
- `0x18009c660`
- `0x18009d820`
- `0x18009da40`
- `0x18009f4a0`
- `0x1800a3040`
- `0x1800a36a0`
- `0x1800a3b40`

## string_xrefs

- `0x18009fad3`: `cannot UPDATE generated column "%s"`
- `0x1800a1f07`: `rows updated`

## pseudocode

```c
__int64 __fastcall sqlite3Update(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _QWORD *v8; // r13
  __int64 v9; // rbx
  __int64 v10; // rdi
  int *v11; // r15
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // rcx
  signed int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned int v19; // r11d
  unsigned int v20; // eax
  unsigned int v21; // esi
  bool v22; // zf
  __int64 v23; // rbx
  __int64 v24; // rdx
  int v25; // r10d
  unsigned int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // ecx
  __int64 v29; // rbx
  __int64 v30; // rax
  _QWORD *v31; // r14
  void *v32; // rsi
  int i; // ecx
  __int64 v34; // rax
  __int64 v35; // rax
  int *v36; // rdx
  char v37; // al
  char v38; // r15
  signed int v39; // r13d
  __int64 v40; // r15
  char v41; // di
  __int64 v42; // rbx
  unsigned __int8 *v43; // rcx
  int *v44; // rsi
  unsigned __int8 k; // al
  int v46; // r14d
  int v47; // r10d
  __int64 v48; // r11
  unsigned __int8 *v49; // r9
  _BYTE *m; // r8
  __int64 v51; // rax
  const char *v52; // r9
  __int64 v53; // rbx
  int v54; // eax
  unsigned __int8 v55; // cl
  unsigned int v56; // esi
  int v57; // edi
  int v58; // ebx
  __int64 v59; // rax
  __int64 v60; // r8
  __int64 v61; // rdx
  _DWORD *v62; // rdx
  __int16 v63; // ax
  int v64; // r14d
  __int64 v65; // rbx
  int v66; // r13d
  _BYTE *v67; // r12
  __int64 v68; // r8
  __int16 v69; // ax
  int v70; // esi
  int v71; // edi
  __int64 v72; // rdx
  BOOL v73; // ecx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int16 v76; // ax
  _DWORD *v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // r8
  bool v81; // di
  __int64 v82; // r10
  char v83; // cl
  __int64 v84; // rbx
  int v85; // eax
  int v86; // eax
  int v87; // edx
  int v88; // ecx
  char v89; // al
  __int64 v90; // r9
  int v91; // ebx
  __int64 (__fastcall *v92)(); // rcx
  int v93; // ebx
  int v94; // eax
  int v95; // r8d
  int v96; // ecx
  __int64 v97; // r11
  __int64 v98; // r9
  __int64 v99; // r9
  __int64 v100; // r8
  __int16 v101; // bx
  unsigned int v102; // r12d
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rax
  unsigned int v106; // edi
  __int64 v107; // rsi
  int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rdx
  int v112; // ecx
  int v113; // eax
  __int64 v114; // r10
  unsigned int v115; // ebx
  __int64 v116; // r8
  int v117; // r8d
  __int64 v118; // rcx
  int v119; // r8d
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rax
  __int64 v125; // rdx
  int v126; // eax
  __int64 v127; // rax
  __int64 v128; // r8
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rdx
  unsigned __int64 v132; // r15
  unsigned __int64 v133; // r14
  __int64 v134; // rcx
  int v135; // edi
  int v136; // eax
  __int16 v137; // ax
  __int64 v138; // rax
  int v139; // edx
  int v140; // eax
  __int64 v141; // rcx
  __int64 v142; // r10
  __int64 v143; // rcx
  __int64 v144; // rcx
  __int64 v145; // rax
  __int64 v146; // rdx
  int v147; // ecx
  __int64 v148; // rcx
  __int16 v149; // si
  unsigned int v150; // r13d
  __int64 v151; // rbx
  unsigned int v152; // r8d
  _BYTE *v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // rax
  __int64 v156; // rdx
  int v157; // edi
  __int64 v158; // rbx
  __int64 v159; // rdi
  __int64 v160; // r10
  unsigned int v161; // eax
  __int64 v162; // rcx
  __int64 v163; // rax
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int64 v166; // rcx
  __int64 v167; // rcx
  __int64 v168; // rax
  __int64 v169; // rdx
  __int64 v170; // rax
  __int64 v171; // rdx
  int v172; // edx
  __int64 *v173; // rax
  __int64 v174; // r15
  __int64 v175; // rcx
  __int64 v176; // rcx
  __int64 v177; // rcx
  __int64 v178; // rax
  __int64 v179; // rdx
  __int64 v180; // rcx
  __int64 v181; // rax
  __int64 v182; // rdx
  unsigned int v183; // edi
  unsigned int v184; // r14d
  __int64 v185; // rcx
  __int64 v186; // rcx
  __int64 v187; // rax
  __int64 v188; // r8
  __int64 v189; // rbx
  unsigned int v190; // edi
  __int64 v191; // rcx
  __int64 v192; // rax
  __int64 v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // rcx
  __int64 v196; // rax
  __int64 v197; // rdx
  __int64 v198; // rcx
  __int64 v199; // rcx
  __int64 v200; // rax
  __int64 v201; // rdx
  unsigned int j; // ebx
  __int64 v203; // rcx
  __int64 v204; // rcx
  __int64 v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rcx
  __int64 v208; // rcx
  __int64 v209; // rax
  __int64 v210; // rdx
  __int64 v211; // rcx
  __int64 v212; // rax
  __int64 v213; // rdx
  __int64 v214; // rcx
  __int64 v215; // rcx
  __int64 v216; // rax
  __int64 v217; // rdx
  __int64 v218; // rsi
  unsigned int v219; // eax
  __int64 v220; // rcx
  __int64 v221; // rcx
  __int64 v222; // rax
  __int64 v223; // rdx
  __int64 v224; // rcx
  __int64 v225; // rcx
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 v228; // r14
  int v229; // r12d
  int v230; // r15d
  __int64 v231; // rsi
  __int64 v232; // r14
  int *v233; // rax
  int v234; // ebx
  int v235; // edi
  int v236; // r12d
  signed int v237; // ebx
  int v238; // esi
  unsigned int v239; // r8d
  __int64 v240; // rcx
  __int64 RowTrigger; // rax
  __int64 v242; // rcx
  __int64 v243; // rax
  __int64 v244; // rcx
  __int64 v245; // rcx
  __int64 v246; // rax
  __int64 v247; // rdx
  __int64 v248; // r12
  int v249; // r15d
  __int64 v250; // rsi
  __int64 v251; // r14
  int *v252; // rax
  int v253; // ebx
  int v254; // edi
  __int64 v255; // rax
  signed int v256; // r9d
  unsigned int v257; // ebx
  signed int v258; // esi
  int v259; // r13d
  int v260; // r15d
  __int16 v261; // r8
  __int64 v262; // rcx
  __int16 v263; // ax
  unsigned int v264; // r8d
  __int64 v265; // rcx
  __int64 v266; // rcx
  __int64 v267; // rax
  __int64 v268; // rdx
  __int64 v269; // rdi
  unsigned int v270; // eax
  __int64 v271; // rdx
  unsigned int v272; // edi
  __int64 v273; // r15
  __int64 v274; // rsi
  __int64 v275; // rbx
  char v276; // al
  __int64 v277; // rcx
  __int64 v278; // rcx
  __int64 v279; // rax
  __int64 v280; // rcx
  int v281; // eax
  unsigned int v282; // r15d
  int v283; // r14d
  int v284; // esi
  __int64 v285; // rcx
  __int64 v286; // rax
  _DWORD *v287; // rdx
  int v288; // eax
  __int64 v289; // rcx
  __int64 v290; // rax
  int v291; // ebx
  __int16 v292; // r8
  unsigned int v293; // eax
  unsigned int v294; // r14d
  __int64 v295; // rcx
  int v296; // eax
  __int64 v297; // rcx
  __int64 v298; // rax
  __int64 v299; // rdx
  int v300; // ebx
  int v301; // edi
  __int64 v302; // rcx
  __int64 v303; // r8
  __int64 v304; // rcx
  __int64 v305; // rcx
  __int64 v306; // rax
  __int64 v307; // rdx
  __int64 v308; // rcx
  __int64 v309; // rax
  __int64 v310; // rcx
  __int64 v311; // rax
  int v312; // edi
  int v313; // eax
  __int64 v314; // rbx
  __int64 v315; // rax
  unsigned int v316; // ebx
  __int64 v317; // rcx
  __int64 v318; // rcx
  __int64 v319; // rax
  __int64 v320; // rsi
  char v321; // al
  __int64 v322; // rcx
  int v323; // r13d
  int v324; // r8d
  __int64 v325; // rcx
  __int64 v326; // rcx
  __int64 v327; // rax
  __int64 v328; // rdx
  __int64 v329; // rcx
  int v330; // edx
  __int64 result; // rax
  __int64 v332; // [rsp+28h] [rbp-E0h]
  __int64 v333; // [rsp+28h] [rbp-E0h]
  __int64 v334; // [rsp+28h] [rbp-E0h]
  int v335; // [rsp+30h] [rbp-D8h]
  char v336; // [rsp+78h] [rbp-90h]
  unsigned int v337; // [rsp+7Ch] [rbp-8Ch]
  char v338; // [rsp+80h] [rbp-88h]
  unsigned __int8 v339; // [rsp+81h] [rbp-87h]
  __int64 v340; // [rsp+88h] [rbp-80h]
  unsigned int v341; // [rsp+90h] [rbp-78h]
  unsigned int v342; // [rsp+94h] [rbp-74h]
  char v343; // [rsp+98h] [rbp-70h]
  unsigned int v344; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v345; // [rsp+A0h] [rbp-68h]
  int v346; // [rsp+A4h] [rbp-64h]
  unsigned int v347; // [rsp+A8h] [rbp-60h]
  unsigned int v348; // [rsp+A8h] [rbp-60h]
  signed int v349; // [rsp+ACh] [rbp-5Ch]
  int v350; // [rsp+ACh] [rbp-5Ch]
  __int16 v351; // [rsp+B0h] [rbp-58h]
  unsigned int v352; // [rsp+B4h] [rbp-54h]
  unsigned int v353; // [rsp+B8h] [rbp-50h]
  int v354; // [rsp+BCh] [rbp-4Ch]
  unsigned int v355; // [rsp+BCh] [rbp-4Ch]
  __int64 v356; // [rsp+C0h] [rbp-48h]
  __int64 v357; // [rsp+C8h] [rbp-40h]
  int v358; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v359; // [rsp+D8h] [rbp-30h]
  __int64 v360; // [rsp+E0h] [rbp-28h]
  unsigned int v361; // [rsp+E8h] [rbp-20h]
  int v362; // [rsp+ECh] [rbp-1Ch] BYREF
  __int64 v363; // [rsp+F0h] [rbp-18h]
  int v364; // [rsp+F8h] [rbp-10h]
  unsigned int v365; // [rsp+FCh] [rbp-Ch]
  unsigned int v366; // [rsp+100h] [rbp-8h]
  int v367; // [rsp+104h] [rbp-4h] BYREF
  unsigned int v368; // [rsp+108h] [rbp+0h]
  int v369; // [rsp+10Ch] [rbp+4h]
  _QWORD *v370; // [rsp+110h] [rbp+8h]
  int v371; // [rsp+118h] [rbp+10h]
  unsigned int v372; // [rsp+11Ch] [rbp+14h]
  __int64 v373; // [rsp+120h] [rbp+18h]
  void *v374; // [rsp+128h] [rbp+20h]
  int *v375; // [rsp+130h] [rbp+28h] BYREF
  __int64 (__fastcall *v376)(); // [rsp+138h] [rbp+30h]
  __int128 v377; // [rsp+140h] [rbp+38h]
  __int64 v378; // [rsp+150h] [rbp+48h]
  _QWORD *v379; // [rsp+158h] [rbp+50h]
  int v380; // [rsp+160h] [rbp+58h]
  int v381; // [rsp+164h] [rbp+5Ch]
  __int64 v382; // [rsp+168h] [rbp+60h]
  unsigned __int64 v383; // [rsp+170h] [rbp+68h] BYREF
  unsigned __int64 v384; // [rsp+178h] [rbp+70h]
  __int64 v385; // [rsp+180h] [rbp+78h]
  __int64 v386; // [rsp+188h] [rbp+80h]
  _QWORD v387[3]; // [rsp+190h] [rbp+88h] BYREF
  __int128 v388; // [rsp+1A8h] [rbp+A0h]
  int v389; // [rsp+1B8h] [rbp+B0h]
  __int64 v390; // [rsp+1BCh] [rbp+B4h]
  int v391; // [rsp+1C4h] [rbp+BCh]

  v8 = *(_QWORD **)a1;
  v9 = a4;
  v10 = a1;
  v11 = a3;
  v362 = 0;
  v370 = v8;
  if ( *(_DWORD *)(a1 + 48) )
    goto LABEL_584;
  v12 = sqlite3SrcListLookup(a1, a2);
  v360 = v12;
  v13 = v12;
  if ( !v12 )
    goto LABEL_584;
  v14 = *(_QWORD *)(v12 + 96);
  v349 = -32768;
  if ( v14 )
  {
    v15 = 0;
    v349 = 0;
    v16 = *(_QWORD *)(*(_QWORD *)v10 + 32LL);
    if ( *(_QWORD *)(v16 + 24) != v14 )
    {
      do
        ++v15;
      while ( *(_QWORD *)(32LL * v15 + v16 + 24) != v14 );
      v349 = v15;
    }
  }
  if ( (*(_QWORD *)(v12 + 88)
     || (v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 32LL) + 56LL)) != 0 && *(_QWORD *)(v17 + 64))
    && !*(_BYTE *)(v10 + 221) )
  {
    v18 = triggersReallyExist((_QWORD *)v10, v13, 129, v11, &v367);
    v363 = v18;
    v371 = v367;
  }
  else
  {
    v18 = 0;
    v371 = 0;
    v363 = 0;
  }
  v336 = *(_BYTE *)(v13 + 63);
  if ( *(int *)a2 <= 1 )
    v345 = 0;
  else
    v345 = *v11;
  if ( (*(_BYTE *)(v13 + 63) == 1 || *(__int16 *)(v13 + 54) <= 0) && (unsigned int)viewGetColumnNames(v10, v13)
    || (unsigned int)sqlite3IsReadOnly(v10, v13, v18) )
  {
    goto LABEL_583;
  }
  v19 = *(_DWORD *)(v10 + 52);
  v20 = v19;
  v337 = v19;
  v365 = v19;
  v21 = v19 + 1;
  *(_DWORD *)(v10 + 52) = v19 + 1;
  v22 = *(_BYTE *)(v13 + 48) >= 0;
  v366 = v19 + 1;
  if ( v22 )
  {
    v23 = 0;
    v357 = 0;
  }
  else
  {
    v23 = sqlite3PrimaryKeyIndex(v13);
    v357 = v23;
    v20 = v19;
  }
  v24 = *(_QWORD *)(v13 + 16);
  v25 = 0;
  v358 = 0;
  if ( v24 )
  {
    v26 = v21;
    v27 = v21;
    do
    {
      v28 = v27;
      if ( v23 != v24 )
      {
        v27 = v26;
        v28 = v19;
      }
      ++v25;
      v19 = v28;
      v26 = v27 + 1;
      *(_DWORD *)(v10 + 52) = ++v27;
      v24 = *(_QWORD *)(v24 + 40);
    }
    while ( v24 );
    v358 = v25;
    v337 = v28;
  }
  if ( a8 )
  {
    v19 = *(_DWORD *)(a8 + 76);
    v366 = *(_DWORD *)(a8 + 80);
    *(_DWORD *)(v10 + 52) = v20;
    v337 = v19;
  }
  *(_DWORD *)(a2 + 76) = v19;
  v29 = v25;
  v30 = sqlite3DbMallocRawNN(v8, v25 + 4LL * (v25 + *(__int16 *)(v13 + 54)) + 6);
  v356 = v30;
  v31 = (_QWORD *)v30;
  if ( !v30 )
    goto LABEL_583;
  v373 = v30 + 4LL * *(__int16 *)(v13 + 54);
  v32 = (void *)(v373 + 4 + 4 * v29);
  v374 = v32;
  memset_0(v32, 1, v29 + 1);
  *((_BYTE *)v32 + v29 + 1) = 0;
  for ( i = 0; i < *(__int16 *)(v13 + 54); *((_DWORD *)v31 + v34) = -1 )
    v34 = i++;
  v387[1] = a2;
  v35 = *(_QWORD *)(v10 + 16);
  v390 = 0;
  v391 = 0;
  v387[0] = v10;
  v387[2] = a8;
  v389 = 512;
  v340 = v35;
  v388 = 0;
  if ( !v35 )
  {
    if ( !*(_QWORD *)(v10 + 168) && (*(_BYTE *)(*(_QWORD *)v10 + 96LL) & 8) == 0 )
      *(_BYTE *)(v10 + 35) = 1;
    v340 = sqlite3VdbeCreate(v10);
    if ( !v340 )
      goto LABEL_85;
  }
  v36 = a3;
  v37 = 0;
  v38 = 0;
  v382 = 0;
  v368 = -1;
  v343 = 0;
  v338 = 0;
  if ( *a3 <= 0 )
  {
LABEL_76:
    v22 = (*(_BYTE *)(v13 + 48) & 0x60) == 0;
    v55 = v38 + v37;
    v339 = v38 + v37;
    v386 = 0;
    v56 = 0;
    v385 = 0;
    v341 = 0;
    v353 = 0;
    v361 = 0;
    v380 = 0;
    v347 = 0;
    if ( !v22 )
    {
      do
      {
        v57 = 0;
        v58 = 0;
        if ( *(__int16 *)(v13 + 54) <= 0 )
          break;
        do
        {
          if ( *((int *)v31 + v58) < 0 )
          {
            v59 = *(_QWORD *)(v13 + 8);
            if ( (*(_BYTE *)(v59 + 24LL * v58 + 18) & 0x60) != 0 )
            {
              v60 = *(unsigned __int16 *)(v59 + 24LL * v58 + 16);
              if ( (_WORD)v60 )
              {
                if ( *(_BYTE *)(v13 + 63) )
                {
                  v61 = 0;
                }
                else
                {
                  v62 = *(_DWORD **)(v13 + 80);
                  if ( v62 )
                  {
                    if ( *v62 >= (int)v60 )
                      v61 = *(_QWORD *)&v62[8 * v60 - 6];
                    else
                      v61 = 0;
                  }
                  else
                  {
                    v61 = 0;
                  }
                }
              }
              else
              {
                v61 = 0;
              }
              v375 = 0;
              v378 = 0;
              v63 = 0;
              v376 = checkConstraintExprNode;
              v379 = v31;
              v377 = 0;
              if ( v61 )
              {
                sqlite3WalkExprNN(&v375);
                v63 = WORD2(v378);
              }
              if ( !v38 )
                v63 &= ~2u;
              if ( v63 )
              {
                v57 = 1;
                *((_DWORD *)v31 + v58) = 99999;
              }
            }
          }
          ++v58;
        }
        while ( v58 < *(__int16 *)(v13 + 54) );
      }
      while ( v57 );
      v10 = a1;
      v55 = v339;
    }
    *(_QWORD *)(a2 + 88) = (*(_BYTE *)(v13 + 63) != 1) - 1LL;
    v367 = v55;
    v64 = sqlite3FkRequired(v10, v13, v31, v55);
    v369 = v64;
    if ( a5 == 5 )
      v362 = 1;
    v65 = *(_QWORD *)(v13 + 16);
    v66 = 0;
    if ( v65 )
    {
      v67 = v374;
      v68 = v356;
      while ( !v339 && v64 <= 1 && v65 != v357 )
      {
        if ( *(_QWORD *)(v65 + 72) )
        {
          v375 = 0;
          v376 = checkConstraintExprNode;
          v379 = (_QWORD *)v356;
          v377 = 0;
          v378 = 0;
          sqlite3WalkExprNN(&v375);
          v69 = WORD2(v378);
          if ( !v338 )
            v69 = WORD2(v378) & 0xFFFD;
          v68 = v356;
          if ( v69 )
            break;
        }
        v70 = 0;
        v71 = 0;
        if ( *(_WORD *)(v65 + 94) )
        {
          while ( 1 )
          {
            v72 = *(__int16 *)(*(_QWORD *)(v65 + 8) + 2LL * v71);
            if ( (v72 & 0x8000u) != 0LL )
            {
              v74 = *(_QWORD *)(v65 + 80);
              v375 = 0;
              v377 = 0;
              v378 = 0;
              v75 = *(_QWORD *)(32LL * v71 + v74 + 8);
              v76 = 0;
              v376 = checkConstraintExprNode;
              v379 = (_QWORD *)v356;
              if ( v75 )
              {
                sqlite3WalkExprNN(&v375);
                v76 = WORD2(v378);
              }
              if ( !v338 )
                v76 &= ~2u;
              v68 = v356;
              v73 = v76 != 0;
            }
            else
            {
              v73 = *(_DWORD *)(v68 + 4 * v72) >= 0;
            }
            if ( v73 )
              break;
            if ( ++v71 >= *(unsigned __int16 *)(v65 + 94) )
              goto LABEL_127;
          }
          v10 = a1;
          ++*(_DWORD *)(a1 + 56);
          v77 = (_DWORD *)(a1 + 56);
          v70 = *(_DWORD *)(a1 + 56);
          *(_DWORD *)(a1 + 56) = v70 + *(unsigned __int16 *)(v65 + 96);
          if ( a5 == 11 && *(_BYTE *)(v65 + 98) == 5 )
          {
            v362 = 1;
            goto LABEL_135;
          }
          goto LABEL_136;
        }
LABEL_127:
        v10 = a1;
LABEL_128:
        v77 = (_DWORD *)(v10 + 56);
        v67[v66 + 1] = 0;
LABEL_129:
        v78 = v373;
        v79 = v66++;
        *(_DWORD *)(v373 + 4 * v79) = v70;
        v65 = *(_QWORD *)(v65 + 40);
        if ( !v65 )
        {
          v56 = 0;
          v13 = v360;
          goto LABEL_139;
        }
      }
      v70 = ++*(_DWORD *)(v10 + 56);
      *(_DWORD *)(v10 + 56) = v70 + *(unsigned __int16 *)(v65 + 96);
LABEL_135:
      v77 = (_DWORD *)(v10 + 56);
LABEL_136:
      if ( v70 )
        goto LABEL_129;
      goto LABEL_128;
    }
    v78 = v373;
    v77 = (_DWORD *)(v10 + 56);
LABEL_139:
    *(_DWORD *)(v78 + 4LL * v66) = ++*v77;
    if ( v362 )
      memset_0(v374, 1, v358 + 1);
    if ( !*(_BYTE *)(v10 + 30) )
      *(_DWORD *)(v340 + 200) |= 0x10u;
    v80 = v363;
    v81 = v363 || v64;
    v82 = a1;
    v83 = v349;
    v84 = a1;
    if ( *(_QWORD *)(a1 + 168) )
      v84 = *(_QWORD *)(a1 + 168);
    v85 = *(_DWORD *)(v84 + 124);
    if ( !_bittest(&v85, v349) )
    {
      *(_DWORD *)(v84 + 124) = v85 | (1 << v349);
      if ( v349 == 1 )
      {
        sqlite3OpenTempDatabase(v84);
        v83 = 1;
        v82 = a1;
        v80 = v363;
      }
    }
    v86 = *(_DWORD *)(v84 + 120);
    *(_BYTE *)(v84 + 32) |= v81;
    *(_DWORD *)(v84 + 120) = v86 | (1 << v83);
    if ( *(_BYTE *)(v13 + 63) != 1 )
    {
      v87 = *(_DWORD *)(v82 + 56) + 1;
      v341 = v87;
      v56 = *(_DWORD *)(v373 + 4LL * v66);
      v347 = v56;
      *(_DWORD *)(v82 + 56) = v87;
      if ( v343 || v80 || v64 )
      {
        v88 = v87 + *(__int16 *)(v13 + 54);
        v380 = v87 + 1;
        *(_DWORD *)(v82 + 56) = v88;
      }
      else
      {
        v88 = v87;
      }
      if ( v339 || v80 || v64 )
      {
        v87 = v88 + 1;
        *(_DWORD *)(v82 + 56) = ++v88;
      }
      v353 = v87;
      v361 = v88 + 1;
      *(_DWORD *)(v82 + 56) = v88 + *(__int16 *)(v13 + 54);
    }
    v89 = v336;
    if ( v336 == 2 )
    {
      v386 = *(_QWORD *)(v82 + 368);
      *(_QWORD *)(v82 + 368) = *(_QWORD *)v13;
      v89 = 2;
      v385 = v82;
    }
    if ( v345 )
    {
      v90 = a4;
    }
    else
    {
      if ( v89 == 2 )
        sqlite3MaterializeView(v82, v13, a4, a6, a7, v337);
      v90 = a4;
      if ( a4 )
      {
        v91 = v389;
        v376 = resolveExprStep;
        v389 &= 0xF7FF6FEF;
        v92 = resolveSelectStep;
        v375 = (int *)v387[0];
        v93 = v91 & 0x8009010;
        *((_QWORD *)&v377 + 1) = 0;
        if ( (v389 & 0x80000) != 0 )
          v92 = 0;
        v379 = v387;
        v94 = *(_DWORD *)(a4 + 40);
        *(_QWORD *)&v377 = v92;
        *(_DWORD *)(v387[0] + 308LL) += v94;
        v95 = *(_DWORD *)(*(_QWORD *)v375 + 148LL);
        if ( v375[77] > v95 )
        {
          sqlite3ErrorMsg(v375, "Expression tree is too large (maximum depth %d)", v95);
          goto LABEL_575;
        }
        sqlite3WalkExprNN(&v375);
        v90 = a4;
        v375[77] -= *(_DWORD *)(a4 + 40);
        v96 = v93 | v389;
        *(_DWORD *)(a4 + 4) |= v389 & 0x8010;
        v389 = v96;
        if ( SHIDWORD(v388) > 0 || v375[12] > 0 )
        {
LABEL_575:
          v11 = a3;
          v31 = (_QWORD *)v356;
LABEL_576:
          if ( v385 )
            *(_QWORD *)(v385 + 368) = v386;
          goto LABEL_84;
        }
      }
    }
    if ( *(_BYTE *)(v13 + 63) == 1 )
    {
      v31 = (_QWORD *)v356;
      v11 = a3;
      updateVirtualTable(a1, a2, v13, (_DWORD)a3, v382, v356, v90, a5);
      goto LABEL_576;
    }
    v97 = a1;
    v372 = 0;
    v352 = --*(_DWORD *)(a1 + 68);
    if ( (v370[6] & 0x100000000LL) != 0 && !*(_QWORD *)(a1 + 176) && !*(_BYTE *)(a1 + 30) )
    {
      v98 = a8;
      if ( *(_BYTE *)(a1 + 219) || a8 )
      {
LABEL_186:
        v100 = v345;
        v381 = -1;
        if ( !v345 && *(char *)(v13 + 48) >= 0 )
        {
          v101 = 0;
          v102 = 0;
          v351 = 0;
          v344 = 0;
          v103 = *(int *)(v340 + 144);
          if ( *(_DWORD *)(v340 + 148) > (int)v103 )
          {
            *(_DWORD *)(v340 + 144) = v103 + 1;
            v104 = 3 * v103;
            v105 = *(_QWORD *)(v340 + 136);
            *(_QWORD *)(v105 + 8 * v104) = 75;
            *(_DWORD *)(v105 + 8 * v104 + 8) = v56;
            *(_QWORD *)(v105 + 8 * v104 + 16) = 0;
            *(_DWORD *)(v105 + 8 * v104 + 12) = v341;
          }
          else
          {
            LODWORD(v332) = v341;
            growOp3(v340, 75, v345, v56, v332);
            v97 = a1;
          }
          v106 = *(_DWORD *)(v97 + 52);
          v342 = v106;
          *(_DWORD *)(v97 + 52) = v106 + 1;
          v107 = *(int *)(v340 + 144);
          v354 = v107;
          if ( *(_DWORD *)(v340 + 148) > (int)v107 )
          {
            *(_DWORD *)(v340 + 144) = v107 + 1;
            v109 = 3 * v107;
            v110 = *(_QWORD *)(v340 + 136);
            *(_DWORD *)(v110 + 8 * v109) = 118;
            *(_DWORD *)(v110 + 8 * v109 + 4) = v106;
            *(_DWORD *)(v110 + 8 * v109 + 8) = 0;
            v111 = v110 + 24 * v107;
            *(_QWORD *)(v111 + 16) = 0;
            *(_DWORD *)(v111 + 12) = v347;
          }
          else
          {
            LODWORD(v332) = v347;
            v108 = growOp3(v340, 118, v106, 0, v332);
            v97 = a1;
            LODWORD(v107) = v108;
            v354 = v108;
          }
          if ( a8 )
            goto LABEL_245;
LABEL_226:
          v137 = 4;
          if ( !*(_BYTE *)(a1 + 30)
            && !v363
            && !v369
            && !v339
            && !v362
            && (!a4 || (*(_DWORD *)(a4 + 4) & 0x400000) == 0) )
          {
            v137 = 12;
          }
          v138 = sqlite3WhereBegin(a1, a2, a4, 0, 0, 0, v137, v366);
          v359 = v138;
          if ( !v138 )
            goto LABEL_575;
          v132 = *(_QWORD *)(v138 + 40);
          v139 = *(unsigned __int8 *)(v138 + 66);
          v100 = v337;
          v140 = *(_DWORD *)(v138 + 68) & 1;
          v133 = HIDWORD(v132);
          v384 = v132;
          v383 = HIDWORD(v132);
          v346 = v139;
          v364 = v140;
          if ( v139 != 1 )
          {
            v141 = a1;
            if ( *(_QWORD *)(a1 + 168) )
              v141 = *(_QWORD *)(a1 + 168);
            *(_BYTE *)(v141 + 32) = 1;
            if ( v139 == 2
              && (v132 & 0x8000000000000000uLL) == 0LL
              && HIDWORD(v132) != v337
              && *((_BYTE *)v374 + (int)(HIDWORD(v132) - v365)) )
            {
              v346 = 0;
            }
          }
LABEL_246:
          v135 = 0;
          v350 = 0;
          if ( *(char *)(v360 + 48) >= 0 )
          {
            v142 = v340;
            v143 = *(int *)(v340 + 144);
            if ( *(_DWORD *)(v340 + 148) > (int)v143 )
            {
              *(_DWORD *)(v340 + 144) = v143 + 1;
              v144 = 3 * v143;
              v145 = *(_QWORD *)(v340 + 136);
              *(_DWORD *)(v145 + 8 * v144 + 4) = v100;
              v100 = v341;
              *(_DWORD *)(v145 + 8 * v144 + 8) = v341;
              v146 = v145 + 8 * v144;
              *(_DWORD *)v146 = 135;
              *(_DWORD *)(v146 + 12) = 0;
              *(_QWORD *)(v146 + 16) = 0;
            }
            else
            {
              LODWORD(v332) = 0;
              growOp3(v340, 135, v100, v341, v332);
              v142 = v340;
              v100 = v341;
            }
            v136 = v346;
            if ( v346 )
            {
              if ( !(_DWORD)v107 )
                goto LABEL_254;
              sqlite3VdbeChangeToNoop(v142, (unsigned int)v107, v100);
            }
            else
            {
              v147 = *(_DWORD *)(a1 + 56) + 1;
              *(_DWORD *)(a1 + 56) = v147;
              *(_DWORD *)(v373 + 4LL * v66) = v147;
              v148 = *(int *)(v142 + 144);
              if ( *(_DWORD *)(v142 + 148) > (int)v148 )
              {
                *(_DWORD *)(v142 + 144) = v148 + 1;
                v154 = 3 * v148;
                v155 = *(_QWORD *)(v142 + 136);
                *(_DWORD *)(v155 + 8 * v154) = 128;
                *(_DWORD *)(v155 + 8 * v154 + 12) = v100;
                *(_QWORD *)(v155 + 8 * v154 + 16) = 0;
                v156 = v155 + 8 * v154;
                *(_DWORD *)(v156 + 4) = v342;
                *(_DWORD *)(v156 + 8) = v347;
              }
              else
              {
                LODWORD(v332) = v100;
                growOp3(v142, 128, v342, v347, v332);
              }
            }
            v136 = v346;
LABEL_254:
            v131 = v359;
LABEL_255:
            v149 = v351;
            goto LABEL_256;
          }
          v157 = v101;
          v158 = 0;
          if ( v157 > 0 )
          {
            do
            {
              sqlite3ExprCodeGetColumnOfTable(
                v340,
                v360,
                v337,
                *(__int16 *)(*(_QWORD *)(v357 + 8) + 2 * v158),
                v158 + v102);
              v158 = (unsigned int)(v158 + 1);
            }
            while ( (int)v158 < v157 );
            LODWORD(v107) = v354;
            LODWORD(v133) = v383;
            LODWORD(v132) = v384;
          }
          v136 = v346;
          if ( v346 )
          {
            if ( (_DWORD)v107 )
            {
              sqlite3VdbeChangeToNoop(v340, (unsigned int)v107, v100);
              v136 = v346;
            }
            v149 = v351;
            v131 = v359;
            v135 = v351;
            v350 = v351;
            v344 = v102;
LABEL_256:
            v150 = v352;
            v348 = v352;
            v355 = 0;
            if ( a8 )
            {
              v174 = v340;
LABEL_357:
              v184 = v342;
LABEL_358:
              v189 = a1;
LABEL_359:
              v183 = v345;
              goto LABEL_360;
            }
            if ( !v345 && v136 != 2 )
              sqlite3WhereEnd(v131);
            if ( v336 != 2 )
            {
              LODWORD(v151) = 0;
              if ( v346 )
              {
                v152 = v365;
                v153 = v374;
                if ( (v132 & 0x80000000) == 0LL )
                  *((_BYTE *)v374 + (int)(v132 - v365)) = 0;
                if ( (v133 & 0x80000000) == 0LL )
                  v153[(int)(v133 - v152)] = 0;
                if ( v346 == 2 && v358 - ((v133 & 0x80000000) == 0LL) > 0 )
                {
                  v151 = *(int *)(v340 + 144);
                  if ( *(_DWORD *)(v340 + 148) > (int)v151 )
                  {
                    *(_DWORD *)(v340 + 144) = v151 + 1;
                    v170 = *(_QWORD *)(v340 + 136);
                    *(_QWORD *)(v170 + 24 * v151) = 15;
                    v171 = v170 + 24 * v151;
                    *(_QWORD *)(v171 + 8) = 0;
                    *(_QWORD *)(v171 + 16) = 0;
                  }
                  else
                  {
                    LODWORD(v332) = 0;
                    LODWORD(v151) = growOp3(v340, 15, 0, 0, v332);
                  }
                }
              }
              sqlite3OpenTableAndIndices(a1, v360, 113, 0, v365, (__int64)v374, (__int64)&v383, (__int64)&v358);
              if ( (_DWORD)v151 )
              {
                v172 = *(_DWORD *)(v340 + 144);
                if ( (_DWORD)v151 == v172 - 1 )
                {
                  *(_DWORD *)(v340 + 144) = v172 - 1;
                }
                else
                {
                  if ( *(_BYTE *)(*(_QWORD *)v340 + 103LL) )
                    v173 = &qword_18013FEA8;
                  else
                    v173 = (__int64 *)(*(_QWORD *)(v340 + 136) + 24LL * (int)v151);
                  *((_DWORD *)v173 + 2) = v172;
                }
              }
            }
            if ( !v346 )
            {
              v98 = v357;
              v183 = v345;
              if ( v357 || v345 )
              {
                v189 = a1;
                v174 = v340;
                v184 = v342;
                v150 = *(_DWORD *)(a1 + 68) - 1;
                *(_DWORD *)(a1 + 68) = v150;
                v198 = *(int *)(v340 + 144);
                v348 = v150;
                if ( *(_DWORD *)(v340 + 148) > (int)v198 )
                {
                  *(_DWORD *)(v340 + 144) = v198 + 1;
                  v199 = 3 * v198;
                  v200 = *(_QWORD *)(v340 + 136);
                  *(_DWORD *)(v200 + 8 * v199) = 36;
                  *(_DWORD *)(v200 + 8 * v199 + 4) = v342;
                  *(_DWORD *)(v200 + 8 * v199 + 12) = 0;
                  v201 = v200 + 8 * v199;
                  *(_QWORD *)(v201 + 16) = 0;
                  *(_DWORD *)(v201 + 8) = v352;
                }
                else
                {
                  LODWORD(v332) = 0;
                  growOp3(v340, 36, v342, v352, v332);
                  v98 = v357;
                }
                v100 = *(int *)(v340 + 144);
                v355 = *(_DWORD *)(v340 + 144);
                if ( !v345 )
                {
                  v98 = v344;
                  if ( *(_DWORD *)(v340 + 148) > (int)v100 )
                  {
                    *(_DWORD *)(v340 + 144) = v100 + 1;
                    v211 = 3 * v100;
                    v212 = *(_QWORD *)(v340 + 136);
                    *(_DWORD *)(v212 + 8 * v211) = 134;
                    *(_DWORD *)(v212 + 8 * v211 + 4) = v342;
                    *(_DWORD *)(v212 + 8 * v211 + 8) = v344;
                    v213 = v212 + 24 * v100;
                    *(_DWORD *)(v213 + 12) = 0;
                    *(_QWORD *)(v213 + 16) = 0;
                  }
                  else
                  {
                    LODWORD(v332) = 0;
                    growOp3(v340, 134, v342, v344, v332);
                    v98 = v344;
                  }
                  v214 = *(int *)(v340 + 144);
                  if ( *(_DWORD *)(v340 + 148) > (int)v214 )
                  {
                    *(_DWORD *)(v340 + 144) = v214 + 1;
                    v215 = 3 * v214;
                    v216 = *(_QWORD *)(v340 + 136);
                    *(_DWORD *)(v216 + 8 * v215) = 64796;
                    *(_DWORD *)(v216 + 8 * v215 + 8) = v150;
                    *(_DWORD *)(v216 + 8 * v215 + 12) = v98;
                    v217 = v216 + 8 * v215;
                    *(_DWORD *)(v217 + 16) = 0;
                    *(_DWORD *)(v217 + 4) = v337;
                  }
                  else
                  {
                    addOp4IntSlow(v340, 28, v337, v150, v98, 0);
                  }
LABEL_360:
                  if ( v338 )
                  {
                    if ( v183 )
                    {
                      v220 = *(int *)(v174 + 144);
                      if ( *(_DWORD *)(v174 + 148) > (int)v220 )
                      {
                        *(_DWORD *)(v174 + 144) = v220 + 1;
                        v221 = 3 * v220;
                        v222 = *(_QWORD *)(v174 + 136);
                        *(_DWORD *)(v222 + 8 * v221) = 94;
                        *(_DWORD *)(v222 + 8 * v221 + 4) = v184;
                        *(_DWORD *)(v222 + 8 * v221 + 12) = v353;
                        v223 = v222 + 8 * v221;
                        LODWORD(v222) = v368;
                        *(_QWORD *)(v223 + 16) = 0;
                        *(_DWORD *)(v223 + 8) = v222;
                      }
                      else
                      {
                        LODWORD(v332) = v353;
                        growOp3(v174, 94, v184, v368, v332);
                      }
                    }
                    else if ( *(_QWORD *)(v189 + 16) )
                    {
                      v218 = v382;
                      v219 = sqlite3ExprCodeTarget(v189, v382, v353);
                      if ( v219 != v353 )
                      {
                        if ( v218 && ((*(_DWORD *)(v218 + 4) & 0x400000) != 0 || *(_BYTE *)v218 == 0xB0) )
                          sqlite3VdbeAddOp2(*(_QWORD *)(v189 + 16), 80, v219, v353);
                        else
                          sqlite3VdbeAddOp2(*(_QWORD *)(v189 + 16), 81, v219, v353);
                      }
                    }
                    v224 = *(int *)(v174 + 144);
                    if ( *(_DWORD *)(v174 + 148) > (int)v224 )
                    {
                      *(_DWORD *)(v174 + 144) = v224 + 1;
                      v225 = 3 * v224;
                      v226 = *(_QWORD *)(v174 + 136);
                      *(_DWORD *)(v226 + 8 * v225) = 13;
                      *(_DWORD *)(v226 + 8 * v225 + 4) = v353;
                      *(_QWORD *)(v226 + 8 * v225 + 8) = 0;
                      *(_QWORD *)(v226 + 8 * v225 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v332) = 0;
                      growOp3(v174, 13, v353, 0, v332);
                    }
                  }
                  if ( v343 )
                  {
                    if ( !v369 )
                    {
LABEL_378:
                      v228 = v360;
                      v229 = 0;
                      v358 = 0;
LABEL_379:
                      if ( *(_BYTE *)(v228 + 63) == 2 )
                      {
                        v230 = -1;
                        goto LABEL_393;
                      }
                      v230 = 0;
                      v231 = v363;
                      if ( v363 )
                      {
                        while ( 1 )
                        {
                          if ( *(_BYTE *)(v231 + 16) == 0x81 && (*(_BYTE *)(v231 + 17) & 3) != 0 )
                          {
                            v232 = *(_QWORD *)(v231 + 32);
                            if ( !v232 )
                              goto LABEL_401;
                            v233 = a3;
                            v234 = 0;
                            v235 = *a3;
                            if ( *a3 > 0 )
                            {
                              while ( (int)sqlite3IdListIndex(v232, *(_QWORD *)&v233[8 * v234 + 4]) < 0 )
                              {
                                v233 = a3;
                                if ( ++v234 >= v235 )
                                  goto LABEL_390;
                              }
LABEL_401:
                              v228 = v360;
                              if ( *(_BYTE *)(v231 + 18) )
                              {
                                v230 = -1;
                              }
                              else
                              {
                                RowTrigger = getRowTrigger(a1, v231, v360, a5);
                                if ( RowTrigger )
                                  v230 |= *(_DWORD *)(RowTrigger + 28);
                              }
                              goto LABEL_391;
                            }
LABEL_390:
                            v228 = v360;
                          }
LABEL_391:
                          v231 = *(_QWORD *)(v231 + 64);
                          if ( !v231 )
                          {
                            v229 = v358;
                            v150 = v348;
                            break;
                          }
                        }
                      }
LABEL_393:
                      v236 = v230 | v229;
                      v237 = 0;
                      if ( *(__int16 *)(v228 + 54) > 0 )
                      {
                        v238 = v380;
                        do
                        {
                          v239 = v238 + (__int16)sqlite3TableColumnToStorage(v228, (unsigned __int16)v237);
                          if ( v236 == -1
                            || v237 < 32 && _bittest(&v236, v237)
                            || (*(_BYTE *)(*(_QWORD *)(v228 + 8) + 24LL * v237 + 18) & 1) != 0 )
                          {
                            sqlite3ExprCodeGetColumnOfTable(v340, v228, v337, v237, v239);
                          }
                          else
                          {
                            v240 = *(int *)(v340 + 144);
                            if ( *(_DWORD *)(v340 + 148) > (int)v240 )
                            {
                              *(_DWORD *)(v340 + 144) = v240 + 1;
                              v242 = 3 * v240;
                              v243 = *(_QWORD *)(v340 + 136);
                              *(_QWORD *)(v243 + 8 * v242) = 75;
                              *(_DWORD *)(v243 + 8 * v242 + 8) = v239;
                              *(_DWORD *)(v243 + 8 * v242 + 12) = 0;
                              *(_QWORD *)(v243 + 8 * v242 + 16) = 0;
                            }
                            else
                            {
                              LODWORD(v332) = 0;
                              growOp3(v340, 75, 0, v239, v332);
                            }
                          }
                          ++v237;
                        }
                        while ( v237 < *(__int16 *)(v228 + 54) );
                        v150 = v348;
                      }
                      if ( v338 )
                      {
                        v227 = v363;
                        goto LABEL_416;
                      }
                      if ( !v357 )
                      {
                        v244 = *(int *)(v340 + 144);
                        if ( *(_DWORD *)(v340 + 148) > (int)v244 )
                        {
                          *(_DWORD *)(v340 + 144) = v244 + 1;
                          v245 = 3 * v244;
                          v246 = *(_QWORD *)(v340 + 136);
                          *(_DWORD *)(v246 + 8 * v245) = 80;
                          *(_DWORD *)(v246 + 8 * v245 + 12) = 0;
                          *(_QWORD *)(v246 + 8 * v245 + 16) = 0;
                          v247 = v246 + 8 * v245;
                          *(_DWORD *)(v247 + 4) = v341;
                          *(_DWORD *)(v247 + 8) = v353;
                          v227 = v363;
                          goto LABEL_416;
                        }
                        LODWORD(v332) = 0;
                        growOp3(v340, 80, v341, v353, v332);
                      }
                      v227 = v363;
LABEL_416:
                      v248 = v360;
                      if ( *(_BYTE *)(v360 + 63) == 2 )
                        goto LABEL_432;
                      v249 = 0;
                      v250 = v227;
                      if ( !v227 )
                        goto LABEL_431;
                      while ( 1 )
                      {
                        if ( *(_BYTE *)(v250 + 16) == 0x81 && (*(_BYTE *)(v250 + 17) & 1) != 0 )
                        {
                          v251 = *(_QWORD *)(v250 + 32);
                          if ( !v251 )
                            goto LABEL_425;
                          v252 = a3;
                          v253 = 0;
                          v254 = *a3;
                          if ( *a3 > 0 )
                            break;
                        }
LABEL_429:
                        v250 = *(_QWORD *)(v250 + 64);
                        if ( !v250 )
                        {
                          v150 = v348;
LABEL_431:
                          v381 = v249;
LABEL_432:
                          LOWORD(v256) = *(_WORD *)(v248 + 54);
                          if ( (__int16)v256 <= 0 )
                            goto LABEL_455;
                          v257 = v361;
                          v258 = 0;
                          v259 = v381;
                          v260 = v340;
                          while ( 2 )
                          {
                            if ( v258 != *(__int16 *)(v248 + 52) )
                            {
                              v261 = *(_WORD *)(*(_QWORD *)(v248 + 8) + 24LL * v258 + 18);
                              if ( (v261 & 0x60) != 0 )
                              {
                                if ( (v261 & 0x20) != 0 )
                                  --v257;
                                goto LABEL_453;
                              }
                              v262 = *(int *)(v356 + 4LL * v258);
                              if ( (int)v262 >= 0 )
                              {
                                if ( v345 )
                                {
                                  v263 = v351;
                                  if ( v336 == 2 )
                                    v263 = v256;
                                  v264 = v262 + v263;
                                  v265 = *(int *)(v340 + 144);
                                  if ( *(_DWORD *)(v340 + 148) > (int)v265 )
                                  {
                                    v260 = v340;
                                    *(_DWORD *)(v340 + 144) = v265 + 1;
                                    v266 = 3 * v265;
                                    v267 = *(_QWORD *)(v340 + 136);
                                    *(_DWORD *)(v267 + 8 * v266) = 94;
                                    *(_DWORD *)(v267 + 8 * v266 + 8) = v264;
                                    *(_DWORD *)(v267 + 8 * v266 + 12) = v257;
                                    v268 = v267 + 8 * v266;
                                    *(_QWORD *)(v268 + 16) = 0;
                                    *(_DWORD *)(v268 + 4) = v342;
                                  }
                                  else
                                  {
                                    LODWORD(v332) = v257;
                                    growOp3(v340, 94, v342, v264, v332);
                                    v260 = v340;
                                  }
                                }
                                else
                                {
                                  _mm_lfence();
                                  if ( *(_QWORD *)(a1 + 16) )
                                  {
                                    v269 = *(_QWORD *)&a3[8 * v262 + 2];
                                    v270 = sqlite3ExprCodeTarget(a1, v269, v257);
                                    if ( v270 != v257 )
                                    {
                                      if ( v269 && ((*(_DWORD *)(v269 + 4) & 0x400000) != 0 || *(_BYTE *)v269 == 0xB0) )
                                        v271 = 80;
                                      else
                                        v271 = 81;
                                      sqlite3VdbeAddOp2(*(_QWORD *)(a1 + 16), v271, v270, v257);
                                    }
                                  }
                                }
LABEL_453:
                                v256 = *(__int16 *)(v248 + 54);
                                ++v258;
                                ++v257;
                                if ( v258 >= v256 )
                                {
                                  v150 = v348;
LABEL_455:
                                  v272 = v361;
                                  v273 = a1;
                                  if ( (*(_BYTE *)(v248 + 48) & 0x60) != 0 )
                                    sqlite3ComputeGeneratedColumns(a1, v361, v248);
                                  if ( (v371 & 1) != 0 )
                                  {
                                    v274 = v340;
                                    sqlite3TableAffinity(v340, v248, v272);
                                    v275 = v363;
                                    if ( v363 )
                                    {
                                      do
                                      {
                                        v276 = *(_BYTE *)(v275 + 16);
                                        if ( (v276 == -127 || *(_BYTE *)(v275 + 18) && v276 == 127)
                                          && *(_BYTE *)(v275 + 17) == 1
                                          && (unsigned int)checkColumnOverlap(*(_QWORD *)(v275 + 32), a3) )
                                        {
                                          if ( *(_BYTE *)(v275 + 18) )
                                          {
                                            if ( !*(_QWORD *)(a1 + 168) )
                                              codeReturningTrigger(a1, v275, v248, v341);
                                          }
                                          else
                                          {
                                            sqlite3CodeRowTriggerDirect(a1, v275, v248, v341, a5, v150);
                                          }
                                        }
                                        v275 = *(_QWORD *)(v275 + 64);
                                      }
                                      while ( v275 );
                                      v274 = v340;
                                      v272 = v361;
                                    }
                                    if ( v336 != 2 )
                                    {
                                      v280 = *(int *)(v274 + 144);
                                      v281 = *(_DWORD *)(v274 + 148);
                                      if ( v357 )
                                      {
                                        v282 = v344;
                                        v283 = v340;
                                        if ( v281 <= (int)v280 )
                                        {
                                          v284 = v350;
                                          addOp4IntSlow(v340, 28, v337, v150, v344, v350);
                                          goto LABEL_486;
                                        }
                                        *(_DWORD *)(v274 + 144) = v280 + 1;
                                        v285 = 3 * v280;
                                        v286 = *(_QWORD *)(v274 + 136);
                                        v284 = v350;
                                        *(_DWORD *)(v286 + 8 * v285) = 64796;
                                        *(_DWORD *)(v286 + 8 * v285 + 12) = v344;
                                        v287 = (_DWORD *)(v286 + 8 * v285);
                                        v287[4] = v350;
                                        v287[1] = v337;
LABEL_485:
                                        v287[2] = v150;
                                      }
                                      else
                                      {
                                        if ( v281 > (int)v280 )
                                        {
                                          v282 = v344;
                                          v288 = v280 + 1;
                                          v283 = v340;
                                          v289 = 3 * v280;
                                          *(_DWORD *)(v274 + 144) = v288;
                                          v290 = *(_QWORD *)(v274 + 136);
                                          v284 = v350;
                                          *(_DWORD *)(v290 + 8 * v289) = 31;
                                          *(_QWORD *)(v290 + 8 * v289 + 16) = 0;
                                          v287 = (_DWORD *)(v290 + 8 * v289);
                                          v287[1] = v337;
                                          v287[3] = v341;
                                          goto LABEL_485;
                                        }
                                        LODWORD(v332) = v341;
                                        growOp3(v274, 31, v337, v150, v332);
                                        v284 = v350;
                                        v282 = v344;
                                        v283 = v340;
                                      }
LABEL_486:
                                      v291 = 0;
                                      if ( *(__int16 *)(v248 + 54) > 0 )
                                      {
                                        do
                                        {
                                          v292 = *(_WORD *)(*(_QWORD *)(v248 + 8) + 24LL * v291 + 18);
                                          if ( (v292 & 0x60) != 0 )
                                          {
                                            v293 = v272 - 1;
                                            if ( (v292 & 0x20) == 0 )
                                              v293 = v272;
                                            v272 = v293;
                                          }
                                          else if ( *(int *)(v356 + 4LL * v291) < 0 && v291 != *(__int16 *)(v248 + 52) )
                                          {
                                            sqlite3ExprCodeGetColumnOfTable(v283, v248, v337, v291, v272);
                                          }
                                          ++v291;
                                          ++v272;
                                        }
                                        while ( v291 < *(__int16 *)(v248 + 54) );
                                        v150 = v348;
                                        v282 = v344;
                                      }
                                      if ( (*(_BYTE *)(v248 + 48) & 0x60) != 0 )
                                        sqlite3ComputeGeneratedColumns(a1, v361, v248);
LABEL_500:
                                      v294 = a5;
                                      sqlite3GenerateConstraintChecks(
                                        a1,
                                        v248,
                                        v373,
                                        v337,
                                        v366,
                                        v353,
                                        v341,
                                        v339,
                                        a5,
                                        v150,
                                        (__int64)&v362,
                                        v356,
                                        0);
                                      if ( !v362 && !v339 )
                                        goto LABEL_506;
                                      v295 = *(int *)(v340 + 144);
                                      v296 = *(_DWORD *)(v340 + 148);
                                      if ( v357 )
                                      {
                                        if ( v296 <= (int)v295 )
                                        {
                                          v335 = v284;
                                          v274 = v340;
                                          addOp4IntSlow(v340, 28, v337, v150, v282, v335);
                                          goto LABEL_507;
                                        }
                                        *(_DWORD *)(v340 + 144) = v295 + 1;
                                        v297 = 3 * v295;
                                        v298 = *(_QWORD *)(v340 + 136);
                                        *(_DWORD *)(v298 + 8 * v297) = 64796;
                                        *(_DWORD *)(v298 + 8 * v297 + 8) = v150;
                                        *(_DWORD *)(v298 + 8 * v297 + 12) = v282;
                                        v299 = v298 + 8 * v297;
                                        *(_DWORD *)(v299 + 16) = v284;
                                        *(_DWORD *)(v299 + 4) = v337;
LABEL_506:
                                        v274 = v340;
                                      }
                                      else
                                      {
                                        v274 = v340;
                                        if ( v296 > (int)v295 )
                                        {
                                          *(_DWORD *)(v340 + 144) = v295 + 1;
                                          v305 = 3 * v295;
                                          v306 = *(_QWORD *)(v340 + 136);
                                          *(_DWORD *)(v306 + 8 * v305) = 31;
                                          *(_DWORD *)(v306 + 8 * v305 + 8) = v150;
                                          *(_DWORD *)(v306 + 8 * v305 + 12) = v341;
                                          v307 = v306 + 8 * v305;
                                          *(_QWORD *)(v307 + 16) = 0;
                                          *(_DWORD *)(v307 + 4) = v337;
                                        }
                                        else
                                        {
                                          LODWORD(v333) = v341;
                                          growOp3(v340, 31, v337, v150, v333);
                                        }
                                      }
LABEL_507:
                                      v300 = v369;
                                      v301 = v367;
                                      v273 = a1;
                                      if ( v369 )
                                        sqlite3FkCheck(a1, v248, v341, 0, v356, v367);
                                      sqlite3GenerateRowIndexDelete(a1, v248, v337, v366, v373, -1);
                                      if ( v364 )
                                      {
                                        v302 = *(int *)(v274 + 144);
                                        v303 = v337;
                                        if ( *(_DWORD *)(v274 + 148) <= (int)v302 )
                                        {
                                          LODWORD(v334) = 0;
                                          growOp3(v274, 143, v337, 0, v334);
                                          goto LABEL_512;
                                        }
                                        *(_DWORD *)(v274 + 144) = v302 + 1;
                                        v308 = 3 * v302;
                                        v309 = *(_QWORD *)(v274 + 136);
                                        *(_DWORD *)(v309 + 8 * v308) = 143;
                                        *(_DWORD *)(v309 + 8 * v308 + 4) = v337;
                                        *(_QWORD *)(v309 + 8 * v308 + 8) = 0;
                                        *(_QWORD *)(v309 + 8 * v308 + 16) = 0;
                                      }
                                      else
                                      {
LABEL_512:
                                        v303 = v337;
                                      }
                                      if ( v300 > 1 || v339 )
                                      {
                                        v304 = *(int *)(v274 + 144);
                                        if ( *(_DWORD *)(v274 + 148) > (int)v304 )
                                        {
                                          *(_DWORD *)(v274 + 144) = v304 + 1;
                                          v310 = 3 * v304;
                                          v311 = *(_QWORD *)(v274 + 136);
                                          *(_DWORD *)(v311 + 8 * v310) = 130;
                                          *(_DWORD *)(v311 + 8 * v310 + 4) = v303;
                                          *(_QWORD *)(v311 + 8 * v310 + 8) = 0;
                                          *(_QWORD *)(v311 + 8 * v310 + 16) = 0;
                                        }
                                        else
                                        {
                                          LODWORD(v334) = 0;
                                          growOp3(v274, 130, v303, 0, v334);
                                        }
                                      }
                                      if ( v300 )
                                        sqlite3FkCheck(a1, v248, 0, v353, v356, v301);
                                      v312 = v346;
                                      v313 = 4;
                                      if ( v346 == 2 )
                                        v313 = 6;
                                      sqlite3CompleteInsertion(a1, v248, v337, v366, v353, v373, v313, 0, 0);
                                      if ( v300 )
                                      {
                                        if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x4000LL) != 0 )
                                        {
                                          v314 = *(_QWORD *)(findElementWithHash(
                                                               *(_QWORD *)(v248 + 96) + 80LL,
                                                               *(_QWORD *)v248,
                                                               0)
                                                           + 16);
                                          if ( v314 )
                                          {
                                            do
                                            {
                                              if ( (unsigned int)fkParentIsModified(v248, v314, v356, v339) )
                                              {
                                                v315 = fkActionTrigger(a1, v248, v314, a3);
                                                if ( v315 )
                                                  sqlite3CodeRowTriggerDirect(a1, v315, v248, v341, 2, 0);
                                              }
                                              v314 = *(_QWORD *)(v314 + 24);
                                            }
                                            while ( v314 );
                                            v150 = v348;
                                            goto LABEL_534;
                                          }
                                        }
                                      }
LABEL_536:
                                      v316 = v372;
                                      if ( v372 )
                                      {
                                        v317 = *(int *)(v274 + 144);
                                        if ( *(_DWORD *)(v274 + 148) > (int)v317 )
                                        {
                                          *(_DWORD *)(v274 + 144) = v317 + 1;
                                          v318 = 3 * v317;
                                          v319 = *(_QWORD *)(v274 + 136);
                                          *(_DWORD *)(v319 + 8 * v318) = 86;
                                          *(_DWORD *)(v319 + 8 * v318 + 4) = v316;
                                          *(_QWORD *)(v319 + 8 * v318 + 8) = 1;
                                          *(_QWORD *)(v319 + 8 * v318 + 16) = 0;
                                        }
                                        else
                                        {
                                          LODWORD(v332) = 0;
                                          growOp3(v274, 86, v372, 1, v332);
                                        }
                                      }
                                      if ( v363 )
                                      {
                                        v320 = v363;
                                        do
                                        {
                                          v321 = *(_BYTE *)(v320 + 16);
                                          if ( (v321 == -127 || *(_BYTE *)(v320 + 18) && v321 == 127)
                                            && *(_BYTE *)(v320 + 17) == 2
                                            && (unsigned int)checkColumnOverlap(*(_QWORD *)(v320 + 32), a3) )
                                          {
                                            if ( *(_BYTE *)(v320 + 18) )
                                            {
                                              if ( !*(_QWORD *)(v273 + 168) )
                                                codeReturningTrigger(v273, v320, v248, v341);
                                            }
                                            else
                                            {
                                              sqlite3CodeRowTriggerDirect(v273, v320, v248, v341, v294, v150);
                                            }
                                          }
                                          v320 = *(_QWORD *)(v320 + 64);
                                        }
                                        while ( v320 );
                                        v312 = v346;
                                        v274 = v340;
                                      }
                                      if ( v312 != 1 )
                                      {
                                        v322 = *(_QWORD *)(v274 + 24);
                                        v323 = ~v150;
                                        v324 = *(_DWORD *)(v322 + 68) + *(_DWORD *)(v322 + 72);
                                        if ( v312 == 2 )
                                        {
                                          if ( v324 >= 0 )
                                            *(_DWORD *)(*(_QWORD *)(v322 + 80) + 4LL * v323) = *(_DWORD *)(v274 + 144);
                                          else
                                            resizeResolveLabel(v322, v274, (unsigned int)v323);
                                          sqlite3WhereEnd(v359);
                                        }
                                        else
                                        {
                                          if ( v324 >= 0 )
                                            *(_DWORD *)(*(_QWORD *)(v322 + 80) + 4LL * v323) = *(_DWORD *)(v274 + 144);
                                          else
                                            resizeResolveLabel(v322, v274, (unsigned int)v323);
                                          v325 = *(int *)(v274 + 144);
                                          if ( *(_DWORD *)(v274 + 148) > (int)v325 )
                                          {
                                            *(_DWORD *)(v274 + 144) = v325 + 1;
                                            v326 = 3 * v325;
                                            v327 = *(_QWORD *)(v274 + 136);
                                            *(_DWORD *)(v327 + 8 * v326) = 39;
                                            v328 = v327 + 8 * v326;
                                            *(_DWORD *)(v328 + 4) = v342;
                                            *(_DWORD *)(v328 + 8) = v355;
                                            *(_DWORD *)(v328 + 12) = 0;
                                            *(_QWORD *)(v328 + 16) = 0;
                                          }
                                          else
                                          {
                                            LODWORD(v332) = 0;
                                            growOp3(v274, 39, v342, v355, v332);
                                          }
                                        }
                                      }
                                      v329 = *(_QWORD *)(v274 + 24);
                                      v330 = ~v352;
                                      if ( *(_DWORD *)(v329 + 68) + *(_DWORD *)(v329 + 72) >= 0 )
                                        *(_DWORD *)(*(_QWORD *)(v329 + 80) + 4LL * v330) = *(_DWORD *)(v274 + 144);
                                      else
                                        resizeResolveLabel(v329, v274, (unsigned int)v330);
                                      if ( !*(_BYTE *)(v273 + 30)
                                        && !*(_QWORD *)(v273 + 176)
                                        && !a8
                                        && *(_QWORD *)(v273 + 160) )
                                      {
                                        autoIncrementEnd(v273);
                                      }
                                      if ( v316 )
                                        sqlite3CodeChangeCount(v274, v316, "rows updated");
                                      goto LABEL_575;
                                    }
                                  }
                                  else
                                  {
                                    if ( v336 != 2 )
                                    {
                                      v284 = v350;
                                      v282 = v344;
                                      goto LABEL_500;
                                    }
LABEL_534:
                                    v274 = v340;
                                  }
                                  v312 = v346;
                                  v294 = a5;
                                  goto LABEL_536;
                                }
                                continue;
                              }
                              if ( (v371 & 1) == 0 || v258 > 31 || _bittest(&v259, v258) )
                              {
                                sqlite3ExprCodeGetColumnOfTable(v260, v248, v337, v258, v257);
                                v364 = 0;
                                goto LABEL_453;
                              }
                            }
                            break;
                          }
                          v277 = *(int *)(v340 + 144);
                          if ( *(_DWORD *)(v340 + 148) > (int)v277 )
                          {
                            v260 = v340;
                            *(_DWORD *)(v340 + 144) = v277 + 1;
                            v278 = 3 * v277;
                            v279 = *(_QWORD *)(v340 + 136);
                            *(_QWORD *)(v279 + 8 * v278) = 75;
                            *(_DWORD *)(v279 + 8 * v278 + 8) = v257;
                            *(_DWORD *)(v279 + 8 * v278 + 12) = 0;
                            *(_QWORD *)(v279 + 8 * v278 + 16) = 0;
                          }
                          else
                          {
                            LODWORD(v332) = 0;
                            growOp3(v340, 75, 0, v257, v332);
                            v260 = v340;
                          }
                          goto LABEL_453;
                        }
                      }
                      while ( (int)sqlite3IdListIndex(v251, *(_QWORD *)&v252[8 * v253 + 4]) < 0 )
                      {
                        v252 = a3;
                        if ( ++v253 >= v254 )
                          goto LABEL_429;
                      }
LABEL_425:
                      if ( *(_BYTE *)(v250 + 18) )
                      {
                        v249 = -1;
                      }
                      else
                      {
                        v255 = getRowTrigger(a1, v250, v248, a5);
                        if ( v255 )
                          v249 |= *(_DWORD *)(v255 + 32);
                      }
                      goto LABEL_429;
                    }
                  }
                  else if ( !v369 )
                  {
                    v227 = v363;
                    if ( !v363 )
                      goto LABEL_416;
                    goto LABEL_378;
                  }
                  v228 = v360;
                  v229 = sqlite3FkOldmask(v189, v360, v100, v98);
                  v358 = v229;
                  goto LABEL_379;
                }
                if ( v336 == 2 )
                  goto LABEL_360;
                if ( v98 )
                {
                  for ( j = 0; (int)j < v149; ++j )
                  {
                    v203 = *(int *)(v340 + 144);
                    if ( *(_DWORD *)(v340 + 148) > (int)v203 )
                    {
                      *(_DWORD *)(v340 + 144) = v203 + 1;
                      v204 = 3 * v203;
                      v205 = *(_QWORD *)(v340 + 136);
                      *(_DWORD *)(v205 + 8 * v204) = 94;
                      *(_DWORD *)(v205 + 8 * v204 + 4) = v342;
                      *(_DWORD *)(v205 + 8 * v204 + 8) = j;
                      v206 = v205 + 8 * v204;
                      *(_DWORD *)(v206 + 12) = j + v102;
                      *(_QWORD *)(v206 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v332) = j + v102;
                      growOp3(v340, 94, v342, j, v332);
                    }
                  }
                  v207 = *(int *)(v340 + 144);
                  v100 = (unsigned int)v149;
                  if ( *(_DWORD *)(v340 + 148) > (int)v207 )
                  {
                    *(_DWORD *)(v340 + 144) = v207 + 1;
                    v208 = 3 * v207;
                    v209 = *(_QWORD *)(v340 + 136);
                    *(_DWORD *)(v209 + 8 * v208) = 64796;
                    *(_DWORD *)(v209 + 8 * v208 + 8) = v150;
                    *(_DWORD *)(v209 + 8 * v208 + 12) = v102;
                    v210 = v209 + 8 * v208;
                    *(_DWORD *)(v210 + 16) = v100;
                    *(_DWORD *)(v210 + 4) = v337;
                  }
                  else
                  {
                    addOp4IntSlow(v340, 28, v337, v150, v102, v100);
                  }
                  goto LABEL_358;
                }
                v190 = v341;
                sqlite3VdbeAddOp2(v340, 135, v342, v341);
              }
              else
              {
                v174 = v340;
                v184 = v342;
                v185 = *(int *)(v340 + 144);
                if ( *(_DWORD *)(v340 + 148) > (int)v185 )
                {
                  *(_DWORD *)(v340 + 144) = v185 + 1;
                  v186 = 3 * v185;
                  v187 = *(_QWORD *)(v340 + 136);
                  *(_DWORD *)(v187 + 8 * v186) = 36;
                  *(_DWORD *)(v187 + 8 * v186 + 4) = v342;
                  *(_DWORD *)(v187 + 8 * v186 + 8) = v352;
                  v188 = v187 + 8 * v186;
                  *(_DWORD *)(v188 + 12) = 0;
                  *(_QWORD *)(v188 + 16) = 0;
                }
                else
                {
                  LODWORD(v332) = v345;
                  growOp3(v340, 36, v342, v352, v332);
                }
                v189 = a1;
                v190 = v341;
                v150 = *(_DWORD *)(a1 + 68) - 1;
                *(_DWORD *)(a1 + 68) = v150;
                v100 = *(int *)(v340 + 144);
                v348 = v150;
                v355 = v100;
                if ( *(_DWORD *)(v340 + 148) > (int)v100 )
                {
                  *(_DWORD *)(v340 + 144) = v100 + 1;
                  v191 = 3 * v100;
                  v192 = *(_QWORD *)(v340 + 136);
                  *(_DWORD *)(v192 + 8 * v191) = 135;
                  *(_DWORD *)(v192 + 8 * v191 + 4) = v342;
                  *(_DWORD *)(v192 + 8 * v191 + 8) = v341;
                  v193 = v192 + 24 * v100;
                  *(_DWORD *)(v193 + 12) = 0;
                  *(_QWORD *)(v193 + 16) = 0;
                }
                else
                {
                  LODWORD(v332) = 0;
                  v355 = growOp3(v340, 135, v342, v341, v332);
                }
              }
              v194 = *(int *)(v174 + 144);
              if ( *(_DWORD *)(v174 + 148) > (int)v194 )
              {
                *(_DWORD *)(v174 + 144) = v194 + 1;
                v195 = 3 * v194;
                v196 = *(_QWORD *)(v174 + 136);
                *(_DWORD *)(v196 + 8 * v195) = 31;
                v197 = v196 + 8 * v195;
                *(_DWORD *)(v197 + 4) = v337;
                *(_DWORD *)(v197 + 8) = v150;
                *(_DWORD *)(v197 + 12) = v190;
                *(_QWORD *)(v197 + 16) = 0;
              }
              else
              {
                LODWORD(v332) = v190;
                growOp3(v174, 31, v337, v150, v332);
              }
              goto LABEL_359;
            }
            v22 = (_DWORD)v132 == v337;
            v174 = v340;
            if ( !v22 && (_DWORD)v133 != v337 )
            {
              v175 = *(int *)(v340 + 144);
              if ( *(_DWORD *)(v340 + 148) > (int)v175 )
              {
                v98 = v344;
                *(_DWORD *)(v340 + 144) = v175 + 1;
                v177 = 3 * v175;
                v178 = *(_QWORD *)(v340 + 136);
                *(_DWORD *)(v178 + 8 * v177) = 64796;
                *(_DWORD *)(v178 + 8 * v177 + 4) = v337;
                *(_DWORD *)(v178 + 8 * v177 + 8) = v352;
                v179 = v178 + 8 * v177;
                *(_DWORD *)(v179 + 12) = v344;
                *(_DWORD *)(v179 + 16) = v135;
                goto LABEL_316;
              }
              v174 = v340;
              addOp4IntSlow(v340, 28, v337, v352, v344, v135);
            }
            v98 = v344;
LABEL_316:
            if ( v346 != 1 )
            {
              v150 = *(_DWORD *)(a1 + 68) - 1;
              v348 = v150;
              *(_DWORD *)(a1 + 68) = v150;
            }
            v100 = v341;
            v176 = *(int *)(v174 + 144);
            if ( v357 )
              v100 = (unsigned int)v98;
            if ( *(_DWORD *)(v174 + 148) > (int)v176 )
            {
              *(_DWORD *)(v174 + 144) = v176 + 1;
              v180 = 3 * v176;
              v181 = *(_QWORD *)(v174 + 136);
              *(_DWORD *)(v181 + 8 * v180) = 50;
              *(_DWORD *)(v181 + 8 * v180 + 4) = v100;
              *(_DWORD *)(v181 + 8 * v180 + 8) = v352;
              v182 = v181 + 8 * v180;
              *(_DWORD *)(v182 + 12) = 0;
              *(_QWORD *)(v182 + 16) = 0;
            }
            else
            {
              LODWORD(v332) = 0;
              growOp3(v174, 50, v100, v352, v332);
            }
            goto LABEL_357;
          }
          v149 = v351;
          v159 = *(_QWORD *)(v357 + 32);
          if ( !v159 )
            v159 = computeIndexAffStr(v370, v357);
          v160 = v340;
          v100 = *(int *)(v340 + 144);
          if ( *(_DWORD *)(v340 + 148) > (int)v100 )
          {
            *(_DWORD *)(v340 + 144) = v100 + 1;
            v162 = 3 * v100;
            v163 = *(_QWORD *)(v340 + 136);
            *(_DWORD *)(v163 + 8 * v162) = 97;
            *(_DWORD *)(v163 + 8 * v162 + 4) = v102;
            *(_DWORD *)(v163 + 8 * v162 + 8) = v351;
            v164 = v163 + 24 * v100;
            *(_DWORD *)(v164 + 12) = v344;
            *(_QWORD *)(v164 + 16) = 0;
          }
          else
          {
            LODWORD(v332) = v344;
            v161 = growOp3(v340, 97, v102, (unsigned int)v351, v332);
            v160 = v340;
            v100 = v161;
          }
          if ( *(_BYTE *)(*(_QWORD *)v160 + 103LL) )
          {
            if ( v351 == -11 )
              goto LABEL_299;
            freeP4(*(_QWORD *)v160, (unsigned int)v351, v159);
          }
          else
          {
            if ( (int)v100 < 0 )
              v100 = (unsigned int)(*(_DWORD *)(v160 + 144) - 1);
            v165 = *(_QWORD *)(v160 + 136) + 24LL * (int)v100;
            if ( v351 < 0 && !*(_BYTE *)(v165 + 1) )
            {
              if ( v351 == -3 )
              {
                *(_DWORD *)(v165 + 16) = v159;
                *(_BYTE *)(v165 + 1) = -3;
              }
              else if ( v159 )
              {
                *(_QWORD *)(v165 + 16) = v159;
                *(_BYTE *)(v165 + 1) = v351;
                if ( v351 == -11 )
                  ++*(_DWORD *)(v159 + 24);
              }
              goto LABEL_299;
            }
            vdbeChangeP4Full(v160, v165, v159, (unsigned int)v351);
          }
          v160 = v340;
LABEL_299:
          v166 = *(int *)(v160 + 144);
          if ( *(_DWORD *)(v160 + 148) > (int)v166 )
          {
            v135 = 0;
            *(_DWORD *)(v160 + 144) = v166 + 1;
            v167 = 3 * v166;
            v168 = *(_QWORD *)(v160 + 136);
            *(_DWORD *)(v168 + 8 * v167) = 64906;
            *(_DWORD *)(v168 + 8 * v167 + 8) = v344;
            *(_DWORD *)(v168 + 8 * v167 + 12) = v102;
            v169 = v168 + 8 * v167;
            *(_DWORD *)(v169 + 16) = v351;
            *(_DWORD *)(v169 + 4) = v342;
            v136 = 0;
            v131 = v359;
          }
          else
          {
            addOp4IntSlow(v160, 138, v342, v344, v102, v351);
            v136 = 0;
            v131 = v359;
            v135 = 0;
          }
          goto LABEL_256;
        }
        if ( v357 )
          v101 = *(_WORD *)(v357 + 94);
        else
          v101 = 0;
        v112 = v101;
        v351 = v101;
        v102 = *(_DWORD *)(v97 + 56) + 1;
        v344 = v345 + v101 + v102;
        *(_DWORD *)(v97 + 56) = v344;
        if ( v98 )
        {
          v342 = 0;
          if ( !v345 )
          {
            LODWORD(v107) = 0;
            v354 = 0;
LABEL_245:
            v359 = 0;
            v346 = 1;
            sqlite3ExprIfFalse(v97, a4, v352, 16);
            LODWORD(v132) = a1;
            LODWORD(v133) = a1;
            v100 = v337;
            v384 = (unsigned int)a1;
            v383 = (unsigned int)a1;
            v364 = 0;
            goto LABEL_246;
          }
        }
        else
        {
          if ( v336 == 2 )
            v113 = *(__int16 *)(v360 + 54);
          else
            v113 = 0;
          v114 = v340;
          v115 = v345 + v101 + v113;
          v116 = *(unsigned int *)(v97 + 52);
          v342 = v116;
          *(_DWORD *)(v97 + 52) = v116 + 1;
          if ( v357 )
          {
            v117 = v112 - 1;
            v118 = *(int *)(v340 + 144);
            v119 = v102 + v117;
            if ( *(_DWORD *)(v340 + 148) > (int)v118 )
            {
              *(_DWORD *)(v340 + 144) = v118 + 1;
              v120 = 3 * v118;
              v121 = *(_QWORD *)(v340 + 136);
              *(_DWORD *)(v121 + 8 * v120 + 12) = v119;
              v116 = v342;
              *(_QWORD *)(v121 + 8 * v120) = 75;
              v122 = v121 + 8 * v120;
              *(_DWORD *)(v122 + 8) = v102;
              *(_QWORD *)(v122 + 16) = 0;
            }
            else
            {
              LODWORD(v332) = v119;
              growOp3(v340, 75, 0, v102, v332);
              v116 = v342;
              v114 = v340;
            }
          }
          v107 = *(int *)(v114 + 144);
          v354 = v107;
          if ( *(_DWORD *)(v114 + 148) > (int)v107 )
          {
            *(_DWORD *)(v114 + 144) = v107 + 1;
            v123 = 3 * v107;
            v124 = *(_QWORD *)(v114 + 136);
            *(_DWORD *)(v124 + 8 * v123) = 118;
            *(_DWORD *)(v124 + 8 * v123 + 4) = v116;
            *(_DWORD *)(v124 + 8 * v123 + 8) = v115;
            v125 = v124 + 24 * v107;
            *(_DWORD *)(v125 + 12) = 0;
            *(_QWORD *)(v125 + 16) = 0;
          }
          else
          {
            LODWORD(v332) = 0;
            LODWORD(v107) = growOp3(v114, 118, v116, v115, v332);
            v354 = v107;
          }
          v126 = v357;
          if ( v357 )
          {
            v127 = sqlite3KeyInfoOfIndex(a1, v357);
            v128 = v127;
            if ( v127 )
            {
              *(_WORD *)(v127 + 8) = v115;
              if ( *(_BYTE *)(*(_QWORD *)v340 + 103LL) )
              {
                if ( !*(_QWORD *)(*(_QWORD *)v340 + 776LL) )
                {
                  v22 = (*(_DWORD *)v127)-- == 1;
                  if ( v22 )
                    sqlite3DbNNFreeNN(*(_QWORD *)(v127 + 16), v127);
                }
              }
              else
              {
                v129 = 3LL * *(int *)(v340 + 144);
                v130 = *(_QWORD *)(v340 + 136);
                *(_BYTE *)(v130 + 8 * v129 - 23) = -8;
                *(_QWORD *)(v130 + 8 * v129 - 8) = v128;
              }
            }
            v126 = v357;
          }
          if ( !v345 )
          {
            v101 = v351;
            goto LABEL_226;
          }
          updateFromSelect(a1, v342, v126, (_DWORD)a3, a2, a4);
          v97 = a1;
          if ( v336 == 2 )
            v337 = v342;
          v101 = v351;
        }
        v131 = 0;
        LODWORD(v132) = a1;
        LODWORD(v133) = a1;
        v134 = v97;
        if ( *(_QWORD *)(v97 + 168) )
          v134 = *(_QWORD *)(v97 + 168);
        v135 = v101;
        v136 = 0;
        v359 = 0;
        v364 = 1;
        v346 = 0;
        *(_BYTE *)(v134 + 32) = 1;
        v350 = v101;
        v344 = v102;
        goto LABEL_255;
      }
      v99 = (unsigned int)(*(_DWORD *)(a1 + 56) + 1);
      v372 = v99;
      *(_DWORD *)(a1 + 56) = v99;
      sqlite3VdbeAddOp2(v340, 71, 0, v99);
      v97 = a1;
    }
    v98 = a8;
    goto LABEL_186;
  }
  v39 = 0;
  while ( 2 )
  {
    v40 = v39;
    v41 = 0;
    v42 = 8LL * v39;
    v43 = *(unsigned __int8 **)&v36[v42 + 4];
    v44 = &v36[v42];
    v359 = (__int64)&v36[v42];
    if ( v43 )
    {
      for ( k = *v43; *v43; k = *v43 )
      {
        ++v43;
        v41 += *((_BYTE *)qword_180114680 + k);
      }
    }
    if ( !v345 )
    {
      if ( (unsigned int)sqlite3ResolveExprNames(v387, *((_QWORD *)v44 + 1), qword_180114680) )
        goto LABEL_83;
      v36 = a3;
    }
    v46 = *(__int16 *)(v13 + 54);
    v47 = 0;
    if ( v46 <= 0 )
    {
LABEL_58:
      v31 = (_QWORD *)v356;
      goto LABEL_59;
    }
    while ( 1 )
    {
      v48 = *(_QWORD *)(v13 + 8) + 24LL * v47;
      if ( *(_BYTE *)(v48 + 14) == v41 )
        break;
LABEL_56:
      if ( ++v47 >= v46 )
      {
        v44 = (int *)v359;
        v13 = v360;
        v40 = v39;
        goto LABEL_58;
      }
    }
    v49 = *(unsigned __int8 **)&v36[v42 + 4];
    for ( m = *(_BYTE **)v48; ; ++m )
    {
      v51 = *v49;
      if ( (unsigned __int8)*m == (_DWORD)v51 )
        break;
      if ( *((unsigned __int8 *)qword_180114680 + (unsigned __int8)*m) != *((unsigned __int8 *)qword_180114680 + v51) )
        goto LABEL_56;
LABEL_55:
      ++v49;
    }
    if ( *m )
      goto LABEL_55;
    v13 = v360;
    if ( v47 == *(__int16 *)(v360 + 52) )
    {
      v44 = (int *)v359;
      v31 = (_QWORD *)v356;
      v338 = 1;
      v368 = v39;
      v382 = *(_QWORD *)(v359 + 8);
      *(_DWORD *)(v356 + 4LL * v47) = v39;
      v40 = v39;
      goto LABEL_59;
    }
    if ( v357 && (*(_BYTE *)(v48 + 18) & 1) != 0 )
    {
      v31 = (_QWORD *)v356;
      v44 = (int *)v359;
      v343 = 1;
      v40 = v39;
      *(_DWORD *)(v356 + 4LL * v47) = v39;
      goto LABEL_59;
    }
    if ( (*(_BYTE *)(v48 + 18) & 0x60) != 0 )
    {
      sqlite3ErrorMsg(a1, "cannot UPDATE generated column \"%s\"", *(const char **)v48);
      v31 = (_QWORD *)v356;
      goto LABEL_83;
    }
    v31 = (_QWORD *)v356;
    v44 = (int *)v359;
    v40 = v39;
    *(_DWORD *)(v356 + 4LL * v47) = v39;
LABEL_59:
    if ( v47 < *(__int16 *)(v13 + 54) )
    {
      if ( v47 >= 0 )
      {
        v53 = v47;
        v52 = *(const char **)(*(_QWORD *)(v13 + 8) + 24LL * v47);
      }
      else
      {
        v52 = "ROWID";
        v53 = v47;
      }
LABEL_71:
      v10 = a1;
      v54 = sqlite3AuthCheck(a1, 23, *(_QWORD *)v13, (_DWORD)v52, *(_QWORD *)(32LL * v349 + v370[4]));
      if ( v54 == 1 )
        goto LABEL_83;
      if ( v54 == 2 )
        *((_DWORD *)v31 + v53) = -1;
      v36 = a3;
      if ( ++v39 >= *a3 )
      {
        v38 = v338;
        v37 = v343;
        goto LABEL_76;
      }
      continue;
    }
    break;
  }
  if ( !v357 && (unsigned int)sqlite3IsRowid(*((_QWORD *)v44 + 2)) )
  {
    v52 = "ROWID";
    v382 = *((_QWORD *)v44 + 1);
    v53 = -1;
    v338 = 1;
    v368 = v39;
    goto LABEL_71;
  }
  sqlite3ErrorMsg(a1, "no such column: %s", *(const char **)&a3[8 * v40 + 4]);
  *(_BYTE *)(a1 + 29) = 1;
LABEL_83:
  v11 = a3;
LABEL_84:
  v8 = v370;
LABEL_85:
  if ( !v8 )
    goto LABEL_582;
  if ( (unsigned __int64)v31 < v8[62] )
  {
    if ( (unsigned __int64)v31 >= v8[60] )
    {
      *v31 = v8[59];
      v8[59] = v31;
      goto LABEL_583;
    }
    if ( (unsigned __int64)v31 >= v8[61] )
    {
      *v31 = v8[57];
      v8[57] = v31;
      goto LABEL_583;
    }
  }
  if ( v8[97] )
    measureAllocationSize(v8, v31);
  else
LABEL_582:
    sqlite3_free(v31);
LABEL_583:
  v9 = a4;
LABEL_584:
  result = sqlite3SrcListDelete(v8, a2);
  if ( v11 )
    result = exprListDeleteNN(v8, v11);
  if ( v9 )
    return sqlite3ExprDeleteNN(v8, v9);
  return result;
}

```

## disassembly

```asm
0x18009f4a0  mov     rax, rsp
0x18009f4a3  mov     [rax+20h], r9
0x18009f4a7  mov     [rax+18h], r8
0x18009f4ab  mov     [rax+10h], rdx
0x18009f4af  mov     [rax+8], rcx
0x18009f4b3  push    rbp
0x18009f4b4  push    rbx
0x18009f4b5  push    r13
0x18009f4b7  lea     rbp, [rax-108h]
0x18009f4be  sub     rsp, 1F0h
0x18009f4c5  mov     r13, [rcx]
0x18009f4c8  mov     rbx, r9
0x18009f4cb  mov     [rax-20h], rsi
0x18009f4cf  xor     esi, esi
0x18009f4d1  mov     [rax-28h], rdi
0x18009f4d5  mov     rdi, rcx
0x18009f4d8  mov     [rax-40h], r15
0x18009f4dc  mov     r15, r8
0x18009f4df  mov     [rbp+100h+var_11C], esi
0x18009f4e2  mov     [rbp+100h+var_F8], r13
0x18009f4e6  cmp     [rcx+30h], esi
0x18009f4e9  jnz     loc_1800A1F95
0x18009f4ef  mov     [rax-30h], r12
0x18009f4f3  mov     [rax-38h], r14
0x18009f4f7  mov     r14, [rbp+100h+arg_8]
0x18009f4fe  mov     rdx, r14
0x18009f501  call    sqlite3SrcListLookup
0x18009f506  mov     [rbp+100h+var_128], rax
0x18009f50a  mov     r12, rax
0x18009f50d  test    rax, rax
0x18009f510  jz      loc_1800A1F85
0x18009f516  mov     rcx, [rax+60h]
0x18009f51a  mov     [rbp+100h+var_15C], 0FFFF8000h
0x18009f521  test    rcx, rcx
0x18009f524  jz      short loc_18009F555
0x18009f526  mov     rax, [rdi]
0x18009f529  mov     r8d, esi
0x18009f52c  mov     [rbp+100h+var_15C], esi
0x18009f52f  mov     rdx, [rax+20h]
0x18009f533  cmp     [rdx+18h], rcx
0x18009f537  jz      short loc_18009F555
0x18009f539  nop     dword ptr [rax+00000000h]
0x18009f540  inc     r8d
0x18009f543  movsxd  rax, r8d
0x18009f546  shl     rax, 5
0x18009f54a  cmp     [rax+rdx+18h], rcx
0x18009f54f  jnz     short loc_18009F540
0x18009f551  mov     [rbp+100h+var_15C], r8d
0x18009f555  cmp     [r12+58h], rsi
0x18009f55a  jnz     short loc_18009F572
0x18009f55c  mov     rax, [rdi]
0x18009f55f  mov     rcx, [rax+20h]
0x18009f563  mov     rax, [rcx+38h]
0x18009f567  test    rax, rax
0x18009f56a  jz      short loc_18009F57B
0x18009f56c  cmp     [rax+40h], rsi
0x18009f570  jz      short loc_18009F57B
0x18009f572  cmp     [rdi+0DDh], sil
0x18009f579  jz      short loc_18009F587
0x18009f57b  mov     rbx, rsi
0x18009f57e  mov     [rbp+100h+var_F0], esi
0x18009f581  mov     [rbp+100h+var_118], rbx
0x18009f585  jmp     short loc_18009F5B1
0x18009f587  lea     rax, [rbp+100h+var_104]
0x18009f58b  mov     r9, r15
0x18009f58e  mov     r8d, 81h
0x18009f594  mov     [rsp+200h+var_1E0], rax
0x18009f599  mov     rdx, r12
0x18009f59c  mov     rcx, rdi
0x18009f59f  call    triggersReallyExist
0x18009f5a4  mov     rbx, rax
0x18009f5a7  mov     [rbp+100h+var_118], rax
0x18009f5ab  mov     eax, [rbp+100h+var_104]
0x18009f5ae  mov     [rbp+100h+var_F0], eax
0x18009f5b1  cmp     dword ptr [r14], 1
0x18009f5b5  movzx   ecx, byte ptr [r12+3Fh]
0x18009f5bb  mov     [rsp+200h+var_190], cl
0x18009f5bf  jle     short loc_18009F5C9
0x18009f5c1  mov     eax, [r15]
0x18009f5c4  mov     [rbp+100h+var_168], eax
0x18009f5c7  jmp     short loc_18009F5CC
0x18009f5c9  mov     [rbp+100h+var_168], esi
0x18009f5cc  cmp     cl, 1
0x18009f5cf  jz      short loc_18009F5D9
0x18009f5d1  cmp     [r12+36h], si
0x18009f5d7  jg      short loc_18009F5EC
0x18009f5d9  mov     rdx, r12
0x18009f5dc  mov     rcx, rdi
0x18009f5df  call    viewGetColumnNames
0x18009f5e4  test    eax, eax
0x18009f5e6  jnz     loc_1800A1F7E
0x18009f5ec  mov     r8, rbx
0x18009f5ef  mov     rdx, r12
0x18009f5f2  mov     rcx, rdi
0x18009f5f5  call    sqlite3IsReadOnly
0x18009f5fa  test    eax, eax
0x18009f5fc  jnz     loc_1800A1F7E
0x18009f602  mov     r11d, [rdi+34h]
0x18009f606  mov     eax, r11d
0x18009f609  mov     [rsp+74h], r11d
0x18009f60e  mov     [rbp+100h+var_10C], eax
0x18009f611  lea     esi, [r11+1]
0x18009f615  mov     [rdi+34h], esi
0x18009f618  test    byte ptr [r12+30h], 80h
0x18009f61e  mov     [rbp+100h+var_108], esi
0x18009f621  jnz     short loc_18009F62B
0x18009f623  xor     ebx, ebx
0x18009f625  mov     [rbp+100h+var_140], rbx
0x18009f629  jmp     short loc_18009F63D
0x18009f62b  mov     rcx, r12
0x18009f62e  call    sqlite3PrimaryKeyIndex
0x18009f633  mov     rbx, rax
0x18009f636  mov     [rbp+100h+var_140], rax
0x18009f63a  mov     eax, r11d
0x18009f63d  mov     rdx, [r12+10h]
0x18009f642  xor     r10d, r10d
0x18009f645  mov     [rbp+100h+var_138], r10d
0x18009f649  test    rdx, rdx
0x18009f64c  jz      short loc_18009F690
0x18009f64e  mov     r9d, esi
0x18009f651  mov     r8d, esi
0x18009f654  nop     dword ptr [rax+00h]
0x18009f658  nop     dword ptr [rax+rax+00000000h]
0x18009f660  cmp     rbx, rdx
0x18009f663  mov     ecx, r8d
0x18009f666  cmovnz  r8d, r9d
0x18009f66a  cmovnz  ecx, r11d
0x18009f66e  inc     r10d
0x18009f671  mov     r11d, ecx
0x18009f674  lea     r9d, [r8+1]
0x18009f678  mov     [rdi+34h], r9d
0x18009f67c  mov     r8d, r9d
0x18009f67f  mov     rdx, [rdx+28h]
0x18009f683  test    rdx, rdx
0x18009f686  jnz     short loc_18009F660
0x18009f688  mov     [rbp+100h+var_138], r10d
0x18009f68c  mov     [rsp+74h], ecx
0x18009f690  mov     rcx, [rbp+100h+arg_38]
0x18009f697  test    rcx, rcx
0x18009f69a  jz      short loc_18009F6AE
0x18009f69c  mov     r11d, [rcx+4Ch]
0x18009f6a0  mov     ecx, [rcx+50h]
0x18009f6a3  mov     [rbp+100h+var_108], ecx
0x18009f6a6  mov     [rdi+34h], eax
0x18009f6a9  mov     [rsp+74h], r11d
0x18009f6ae  mov     [r14+4Ch], r11d
0x18009f6b2  mov     rcx, r13
0x18009f6b5  movsx   eax, word ptr [r12+36h]
0x18009f6bb  add     eax, r10d
0x18009f6be  movsxd  rbx, r10d
0x18009f6c1  cdqe
0x18009f6c3  lea     rdx, ds:6[rax*4]
0x18009f6cb  add     rdx, rbx
0x18009f6ce  call    sqlite3DbMallocRawNN
0x18009f6d3  mov     [rbp+100h+var_148], rax
0x18009f6d7  mov     r14, rax
0x18009f6da  test    rax, rax
0x18009f6dd  jz      loc_1800A1F7E
0x18009f6e3  movsx   rcx, word ptr [r12+36h]
0x18009f6e9  lea     r8, [rbx+1]; Size
0x18009f6ed  mov     edx, 1; Val
0x18009f6f2  lea     rax, [rax+rcx*4]
0x18009f6f6  lea     rsi, [rax+4]
0x18009f6fa  mov     [rbp+100h+var_E8], rax
0x18009f6fe  lea     rsi, [rsi+rbx*4]
0x18009f702  mov     rcx, rsi; void *
0x18009f705  mov     [rbp+100h+var_E0], rsi
0x18009f709  call    memset_0
0x18009f70e  xor     r9d, r9d
0x18009f711  mov     byte ptr [rbx+rsi+1], 0
0x18009f716  mov     ecx, r9d
0x18009f719  cmp     r9w, [r12+36h]
0x18009f71f  jge     short loc_18009F738
0x18009f721  movsxd  rax, ecx
0x18009f724  inc     ecx
0x18009f726  mov     dword ptr [r14+rax*4], 0FFFFFFFFh
0x18009f72e  movsx   eax, word ptr [r12+36h]
0x18009f734  cmp     ecx, eax
0x18009f736  jl      short loc_18009F721
0x18009f738  mov     rax, [rbp+100h+arg_8]
0x18009f73f  xorps   xmm0, xmm0
0x18009f742  mov     rcx, [rbp+100h+arg_38]
0x18009f749  mov     [rbp+100h+var_70], rax
0x18009f750  mov     rax, [rdi+10h]
0x18009f754  mov     [rbp+100h+var_4C], r9
0x18009f75b  mov     [rbp+100h+var_44], r9d
0x18009f762  mov     [rbp+100h+var_78], rdi
0x18009f769  mov     [rbp+100h+var_68], rcx
0x18009f770  mov     [rbp+100h+var_50], 200h
0x18009f77a  mov     [rbp+100h+var_180], rax
0x18009f77e  movdqu  [rbp+100h+var_60], xmm0
0x18009f786  test    rax, rax
0x18009f789  jnz     short loc_18009F7B9
0x18009f78b  cmp     [rdi+0A8h], r9
0x18009f792  jnz     short loc_18009F7A1
0x18009f794  mov     rax, [rdi]
0x18009f797  test    byte ptr [rax+60h], 8
0x18009f79b  jnz     short loc_18009F7A1
0x18009f79d  mov     byte ptr [rdi+23h], 1
0x18009f7a1  mov     rcx, rdi
0x18009f7a4  call    sqlite3VdbeCreate
0x18009f7a9  mov     [rbp+100h+var_180], rax
0x18009f7ad  test    rax, rax
0x18009f7b0  jz      loc_18009FAF1
0x18009f7b6  xor     r9d, r9d
0x18009f7b9  mov     rdx, [rbp+100h+arg_10]
0x18009f7c0  xor     al, al
0x18009f7c2  xor     r15b, r15b
0x18009f7c5  mov     [rbp+100h+var_A0], r9
0x18009f7c9  mov     [rbp+100h+var_100], 0FFFFFFFFh
0x18009f7d0  mov     [rbp+100h+var_170], al
0x18009f7d3  cmp     dword ptr [rdx], 0
0x18009f7d6  mov     [rsp+78h], r15b
0x18009f7db  jle     loc_18009FA3D
0x18009f7e1  mov     r13d, r9d
0x18009f7e4  movsxd  r15, r13d
0x18009f7e7  lea     r8, qword_180114680
0x18009f7ee  mov     rbx, r15
0x18009f7f1  xor     dil, dil
0x18009f7f4  shl     rbx, 5
0x18009f7f8  mov     rcx, [rbx+rdx+10h]
0x18009f7fd  lea     rsi, [rbx+rdx]
0x18009f801  mov     [rbp+100h+var_130], rsi
0x18009f805  test    rcx, rcx
0x18009f808  jz      short loc_18009F832
0x18009f80a  movzx   eax, byte ptr [rcx]
0x18009f80d  test    al, al
0x18009f80f  jz      short loc_18009F832
0x18009f811  nop     dword ptr [rax+00h]
0x18009f815  nop     word ptr [rax+rax+00000000h]
0x18009f820  movzx   eax, al
0x18009f823  lea     rcx, [rcx+1]
0x18009f827  add     dil, [rax+r8]
0x18009f82b  movzx   eax, byte ptr [rcx]
0x18009f82e  test    al, al
0x18009f830  jnz     short loc_18009F820
0x18009f832  cmp     [rbp+100h+var_168], 0
0x18009f836  jnz     short loc_18009F85A
0x18009f838  mov     rdx, [rsi+8]
0x18009f83c  lea     rcx, [rbp+100h+var_78]
0x18009f843  call    sqlite3ResolveExprNames
0x18009f848  test    eax, eax
0x18009f84a  jnz     loc_18009FAE6
0x18009f850  mov     rdx, [rbp+100h+arg_10]
0x18009f857  xor     r9d, r9d
0x18009f85a  movsx   r14d, word ptr [r12+36h]
0x18009f860  mov     r10d, r9d
0x18009f863  test    r14d, r14d
0x18009f866  jle     loc_18009F921
0x18009f86c  mov     r15, [r12+8]
0x18009f871  lea     r12, [rbx+rdx]
0x18009f875  nop     word ptr [rax+rax+00000000h]
0x18009f880  movsxd  rbx, r10d
0x18009f883  lea     rax, [rbx+rbx*2]
0x18009f887  cmp     [r15+rax*8+0Eh], dil
0x18009f88c  lea     r11, [r15+rax*8]
0x18009f890  jnz     short loc_18009F90A
0x18009f892  mov     rsi, [r11]
0x18009f895  mov     r9, [r12+10h]
0x18009f89a  mov     r8, rsi
0x18009f89d  nop     dword ptr [rax]
0x18009f8a0  movzx   edx, byte ptr [r8]
0x18009f8a4  movzx   eax, byte ptr [r9]
0x18009f8a8  cmp     edx, eax
0x18009f8aa  jnz     short loc_18009F8E5
0x18009f8ac  test    edx, edx
0x18009f8ae  jnz     short loc_18009F902
0x18009f8b0  mov     r12, [rbp+100h+var_128]
0x18009f8b4  movsx   eax, word ptr [r12+34h]
0x18009f8ba  cmp     r10d, eax
0x18009f8bd  jnz     loc_18009F973
0x18009f8c3  mov     rsi, [rbp+100h+var_130]
0x18009f8c7  mov     r14, [rbp+100h+var_148]
0x18009f8cb  mov     byte ptr [rsp+78h], 1
0x18009f8d0  mov     [rbp+100h+var_100], r13d
0x18009f8d4  mov     rax, [rsi+8]
0x18009f8d8  mov     [rbp+100h+var_A0], rax
0x18009f8dc  mov     [r14+rbx*4], r13d
0x18009f8e0  movsxd  r15, r13d
0x18009f8e3  jmp     short loc_18009F925
0x18009f8e5  lea     rcx, qword_180114680
0x18009f8ec  movzx   ecx, byte ptr [rax+rcx]
0x18009f8f0  mov     rax, rdx
0x18009f8f3  lea     rdx, qword_180114680
0x18009f8fa  movzx   eax, byte ptr [rax+rdx]
0x18009f8fe  cmp     eax, ecx
0x18009f900  jnz     short loc_18009F90A
0x18009f902  inc     r8
0x18009f905  inc     r9
0x18009f908  jmp     short loc_18009F8A0
0x18009f90a  inc     r10d
0x18009f90d  cmp     r10d, r14d
0x18009f910  jl      loc_18009F880
0x18009f916  mov     rsi, [rbp+100h+var_130]
0x18009f91a  mov     r12, [rbp+100h+var_128]
0x18009f91e  movsxd  r15, r13d
0x18009f921  mov     r14, [rbp+100h+var_148]
0x18009f925  movsx   eax, word ptr [r12+36h]
0x18009f92b  cmp     r10d, eax
0x18009f92e  jl      loc_18009F9B5
  ... truncated ...
```
