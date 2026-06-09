# sqlite3Pragma

- ea: `0x180093bb0`
- end: `0x180097679`
- name: `sqlite3Pragma`
- size: `15049`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `115`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000213c`

## callees

- `0x18000506c`
- `0x180007190`
- `0x1800087d0`
- `0x180008be8`
- `0x18000968c`
- `0x180009760`
- `0x180009ac0`
- `0x180009e04`
- `0x18000a038`
- `0x18000a180`
- `0x18000a6bc`
- `0x18000a710`
- `0x180011bcc`
- `0x180014690`
- `0x1800146c0`
- `0x1800151f0`
- `0x180015460`
- `0x180015700`
- `0x180015750`
- `0x180015eb0`
- `0x1800168c0`
- `0x18001bc40`
- `0x18001c170`
- `0x18001cb40`
- `0x18001cb6c`
- `0x18001e090`
- `0x18001e860`
- `0x18001eb90`
- `0x18001f0f0`
- `0x18001f418`
- `0x18001f448`
- `0x18001f530`
- `0x180020a04`
- `0x180021960`
- `0x180023a80`
- `0x180024640`
- `0x180024770`
- `0x1800310a0`
- `0x180031e2c`
- `0x180031f40`
- `0x180031fb0`
- `0x1800330b8`
- `0x18003352c`
- `0x180038d00`
- `0x18003d610`
- `0x18003d760`
- `0x18003f8d0`
- `0x18003fb44`
- `0x180040e00`
- `0x180041d10`

## string_xrefs

- `0x1800970ec`: `sqlite_temp_schema`
- `0x180096e41`: `not a writable directory`
- `0x180097349`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r14
  __int64 *v8; // r12
  __int64 result; // rax
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // r13d
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r10
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  __int64 v27; // rdx
  __int64 *v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  __int64 v33; // rbx
  int AutoVacuum; // eax
  unsigned __int8 v35; // cl
  int v36; // ebx
  _DWORD *v37; // rax
  unsigned int v38; // esi
  __int64 v39; // rdx
  int v40; // r12d
  __int64 v41; // rcx
  __int64 v42; // r10
  __int64 v43; // rdi
  _DWORD *v44; // rax
  __int64 v45; // rcx
  int Int32; // eax
  __int64 v47; // rdx
  int v48; // ebx
  bool v49; // zf
  __int64 v50; // rbx
  char Boolean; // al
  __int64 v52; // rcx
  __int64 v53; // rbx
  unsigned __int64 v54; // rcx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  unsigned int v61; // ebx
  __int64 j; // rcx
  __int64 v63; // rax
  __int64 **v64; // rbx
  unsigned int v65; // r15d
  unsigned __int8 v66; // al
  unsigned int i; // ebx
  __int64 v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rdx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ebx
  __int64 n; // r12
  __int64 ii; // r13
  _QWORD *v80; // rsi
  __int64 v81; // rax
  __int64 v82; // r13
  __int64 v83; // rbx
  unsigned int v84; // eax
  unsigned int v85; // r9d
  __int64 v86; // rdx
  unsigned int v87; // eax
  __int64 v88; // rcx
  int v89; // r12d
  __int64 v90; // rcx
  __int64 v91; // rdx
  __int64 v92; // r8
  int v93; // eax
  __int64 v94; // r8
  int v95; // r10d
  int v96; // eax
  signed int v97; // ecx
  const char **v98; // rcx
  __int64 Table; // rax
  unsigned int v100; // eax
  __int64 v101; // rcx
  __int64 v102; // rbx
  int v103; // ecx
  int v104; // r8d
  int v105; // ecx
  __int64 k; // rax
  __int64 v107; // rax
  __int64 v108; // r8
  __int64 *v109; // r15
  __int64 v110; // r8
  __int64 v111; // rbx
  __int64 v112; // rax
  const char **v113; // rdx
  int v114; // ecx
  int v115; // eax
  int v116; // r8d
  int v117; // r14d
  int m; // r12d
  int v119; // r9d
  int v120; // ebx
  __int64 v121; // rax
  __int64 v122; // rbx
  unsigned int v123; // ebx
  __int64 v124; // r8
  __int64 v125; // r9
  const char *v126; // rdx
  char **jj; // rbx
  __int64 v128; // rdx
  __int64 v129; // rcx
  _DWORD *v130; // rax
  int v131; // ebx
  __int64 v132; // r9
  __int64 *v133; // rax
  __int64 v134; // r8
  __int64 v135; // rax
  __int64 v136; // rax
  unsigned int v137; // ecx
  unsigned int v138; // ecx
  unsigned int v139; // ecx
  int v140; // eax
  __int64 v141; // r9
  unsigned int v142; // eax
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // rax
  int v146; // ecx
  _QWORD *v147; // rax
  __int64 v148; // r15
  __int64 v149; // rdx
  __int64 v150; // rdx
  int v151; // eax
  int *v152; // rax
  int v153; // r9d
  _QWORD *kk; // r8
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 mm; // rdx
  int v158; // ecx
  unsigned int v159; // ebx
  __int64 v160; // rax
  __int64 v161; // r8
  __int64 v162; // r9
  __int64 v163; // r11
  __int64 v164; // rdx
  _QWORD *v165; // r12
  unsigned int v166; // eax
  __int64 v167; // rcx
  unsigned int v168; // r9d
  const char ***v169; // rdx
  const char ***v170; // r8
  __int64 v171; // rcx
  const char **v172; // rcx
  unsigned int v173; // r14d
  unsigned int v174; // ebx
  __int64 v175; // r8
  __int64 v176; // r9
  __int64 v177; // rax
  __int64 v178; // rax
  __int64 v179; // rbx
  const char **v180; // rax
  const char **v181; // rbx
  unsigned int TempRange; // eax
  __int64 v183; // r10
  int v184; // edx
  const char *v185; // r15
  int v186; // r14d
  int v187; // eax
  int v188; // r9d
  int v189; // edx
  int nn; // r8d
  int v191; // eax
  int v192; // r9d
  unsigned int v193; // ebx
  __int64 v194; // rax
  __int64 v195; // r8
  __int64 v196; // r9
  __int64 v197; // r8
  __int64 v198; // r9
  __int64 v199; // rax
  int v200; // ebx
  int v201; // r13d
  __int64 v202; // r14
  unsigned int v203; // edi
  __int64 v204; // rdx
  int v205; // r8d
  bool v206; // cc
  __int64 v207; // rcx
  char *v208; // r9
  unsigned int v209; // eax
  _BOOL8 v210; // r8
  int v211; // r11d
  int v212; // edx
  int v213; // eax
  _BYTE *v214; // r9
  int v215; // r8d
  __int64 v216; // rax
  __int16 v217; // ax
  int v218; // eax
  int v219; // ecx
  const char **v220; // rax
  unsigned int v221; // r9d
  int v222; // ecx
  int v223; // r10d
  __int64 v224; // rax
  unsigned int v225; // edx
  __int64 v226; // r8
  __int64 v227; // r9
  __int64 v228; // rax
  __int64 v229; // rdx
  __int64 v230; // r8
  __int64 v231; // r9
  __int64 v232; // r9
  __int64 v233; // r10
  __int64 v234; // rax
  char v235; // dl
  int v236; // ecx
  const char *v237; // rdx
  const char **v238; // rax
  const char **v239; // rcx
  int v240; // eax
  int v241; // ebx
  const char **v242; // r14
  __int64 v243; // rax
  char *v244; // rbx
  int v245; // ecx
  __int64 v246; // r8
  int v247; // edx
  const char **v248; // r13
  int v249; // r14d
  unsigned int v250; // ebx
  unsigned int v251; // r14d
  __int64 v252; // r8
  __int64 v253; // r9
  const char *v254; // r8
  unsigned int v255; // ebx
  __int64 v256; // r8
  __int64 v257; // r9
  __int64 v258; // r9
  unsigned int v259; // edx
  int v260; // r14d
  int v261; // r13d
  unsigned int v262; // ebx
  __int64 v263; // r8
  __int64 v264; // r9
  __int64 v265; // rax
  int v266; // r14d
  int v267; // eax
  int v268; // r12d
  __int64 v269; // rax
  unsigned int v270; // r14d
  unsigned int v271; // ebx
  __int64 v272; // r8
  __int64 v273; // r9
  __int64 v274; // rax
  unsigned int v275; // r8d
  __int64 v276; // rax
  __int64 v277; // rdx
  int v278; // ebx
  __int64 v279; // r8
  __int64 v280; // r9
  __int64 v281; // rax
  _QWORD *v282; // r15
  __int64 v283; // rax
  int v284; // r13d
  __int64 v285; // rbx
  __int64 ElementWithHash; // rax
  __int64 v287; // rax
  __int64 *v288; // rax
  __int64 v289; // rax
  unsigned int v290; // ebx
  __int64 v291; // r8
  __int64 v292; // r9
  __int64 v293; // rax
  __int64 v294; // rax
  __int64 v295; // rdx
  __int64 v296; // r8
  __int64 v297; // rax
  __int64 Op; // rax
  int v299; // r9d
  __int64 v300; // rax
  __int64 v301; // rbx
  unsigned int v302; // eax
  __int64 v303; // rbx
  unsigned int v304; // r12d
  __int64 v305; // r9
  __int64 v306; // rax
  unsigned int v307; // eax
  const char **v308; // rbx
  __int64 v309; // r9
  int v310; // r13d
  int v311; // ecx
  unsigned int v312; // r14d
  __int64 v313; // rdx
  __int64 v314; // rcx
  int v315; // r13d
  unsigned int v316; // ebx
  __int64 v317; // r8
  __int64 v318; // r9
  __int64 v319; // r8
  int v320; // r8d
  int v321; // r12d
  __int64 v322; // rax
  unsigned int v323; // edx
  int v324; // eax
  __int64 v325; // rdx
  int v326; // r13d
  __int64 v327; // r15
  int v328; // ecx
  int v329; // r8d
  unsigned int v330; // ecx
  unsigned int v331; // ecx
  unsigned int v332; // ecx
  unsigned int v333; // ecx
  _QWORD *i2; // rbx
  __int64 v335; // r13
  __int64 v336; // rdx
  int v337; // r8d
  __int64 v338; // rax
  int v339; // edx
  __int64 v340; // rax
  unsigned __int8 *v341; // rax
  int v342; // r13d
  int v343; // eax
  const char *v344; // r11
  int v345; // edx
  int v346; // eax
  int v347; // eax
  int i3; // r8d
  int v349; // r8d
  __int64 *v350; // rcx
  __int64 v351; // rax
  __int64 v352; // rbx
  __int64 v353; // rcx
  int v354; // r13d
  int v355; // eax
  __int64 i4; // rax
  __int64 v357; // rax
  int v358; // edx
  __int64 v359; // r9
  __int64 v360; // rcx
  int v361; // r8d
  int v362; // r8d
  __int64 v363; // rax
  int TempReg; // ebx
  __int64 v365; // rdx
  int v366; // r9d
  __int64 v367; // r8
  int v368; // eax
  __int64 v369; // r9
  __int64 v370; // rax
  __int64 v371; // rdx
  int v372; // r9d
  int v373; // r10d
  unsigned int v374; // ecx
  unsigned int v375; // ecx
  unsigned int v376; // ecx
  int v377; // r13d
  int v378; // ebx
  __int64 v379; // r12
  __int64 i1; // rbx
  __int64 v381; // rbx
  int v382; // ecx
  __int64 v383; // rdx
  unsigned int v384; // ecx
  unsigned int v385; // ecx
  unsigned int v386; // ecx
  unsigned int v387; // ecx
  __int64 v388; // rax
  __int64 v389; // rcx
  __int64 v390; // rax
  __int64 v391; // rbx
  __int64 v392; // rdx
  signed int v393; // eax
  __int64 v394; // r12
  __int64 v395; // rcx
  int v396; // r12d
  __int64 v397; // rcx
  __int64 v398; // rbx
  _QWORD *i5; // rax
  __int64 v400; // r8
  __int64 v401; // rax
  __int64 v402; // rax
  _QWORD *v403; // r12
  const char *v404; // rax
  unsigned int v405; // ecx
  const char *v406; // rax
  __int64 v407; // r11
  const char *v408; // r11
  __int64 v409; // rax
  __int64 v410; // rbx
  __int64 v411; // r8
  int v412; // edx
  __int64 v413; // r14
  int v414; // ecx
  __int64 v415; // r9
  __int64 v416; // r15
  __int16 v417; // ax
  int v418; // r12d
  __int64 v419; // rax
  __int64 v420; // r10
  unsigned int v421; // r11d
  __int64 v422; // rax
  int v423; // r10d
  int v424; // r11d
  int v425; // r9d
  __int64 v426; // r9
  const char *v427; // r8
  char SafetyLevel; // al
  __int64 *v429; // rcx
  __int64 v430; // rdx
  int v431; // eax
  unsigned int v432; // ecx
  unsigned int v433; // ecx
  unsigned int v434; // ecx
  unsigned __int64 v435; // rcx
  _QWORD *v436; // r8
  unsigned int v437; // r13d
  unsigned int v438; // r13d
  char v439; // r8
  __int64 v440; // rdx
  int v441; // eax
  int v442; // r11d
  int v443; // r9d
  int v444; // r8d
  __int64 v445; // [rsp+20h] [rbp-E0h]
  __int64 v446; // [rsp+20h] [rbp-E0h]
  __int64 v447; // [rsp+20h] [rbp-E0h]
  int v448; // [rsp+20h] [rbp-E0h]
  __int64 v449; // [rsp+28h] [rbp-D8h]
  __int64 v450; // [rsp+28h] [rbp-D8h]
  int v451; // [rsp+28h] [rbp-D8h]
  __int64 v452; // [rsp+28h] [rbp-D8h]
  int v453; // [rsp+30h] [rbp-D0h]
  int v454; // [rsp+30h] [rbp-D0h]
  __int64 v455; // [rsp+38h] [rbp-C8h]
  int v456; // [rsp+40h] [rbp-C0h]
  int v457; // [rsp+48h] [rbp-B8h]
  unsigned int v458; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int IndexKey; // [rsp+64h] [rbp-9Ch]
  unsigned int v460; // [rsp+68h] [rbp-98h] BYREF
  int v461; // [rsp+6Ch] [rbp-94h] BYREF
  int v462; // [rsp+70h] [rbp-90h]
  signed int v463; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 Index; // [rsp+78h] [rbp-88h] BYREF
  __int64 v465; // [rsp+80h] [rbp-80h]
  __int64 *v466; // [rsp+88h] [rbp-78h]
  char v467; // [rsp+90h] [rbp-70h]
  const char **v468; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v469; // [rsp+A0h] [rbp-60h]
  __int64 v470; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v471; // [rsp+B0h] [rbp-50h]
  __int64 v472; // [rsp+B8h] [rbp-48h] BYREF
  int v473; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v474; // [rsp+C4h] [rbp-3Ch] BYREF
  char *v475; // [rsp+C8h] [rbp-38h]
  __int64 v476; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v477; // [rsp+D8h] [rbp-28h]
  unsigned int v478; // [rsp+DCh] [rbp-24h]
  __int64 v479; // [rsp+E0h] [rbp-20h] BYREF
  int v480; // [rsp+E8h] [rbp-18h]
  unsigned int v481; // [rsp+ECh] [rbp-14h]
  __int64 v482; // [rsp+F0h] [rbp-10h]
  __int64 v483; // [rsp+F8h] [rbp-8h]
  __int64 v484; // [rsp+100h] [rbp+0h]
  const char **v485; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v486; // [rsp+110h] [rbp+10h]
  __int64 *v487; // [rsp+118h] [rbp+18h]
  __int128 v488; // [rsp+120h] [rbp+20h] BYREF
  __int128 v489; // [rsp+130h] [rbp+30h]
  _QWORD v490[5]; // [rsp+140h] [rbp+40h] BYREF

  v5 = *a1;
  v476 = *a1;
  v479 = a3;
  v472 = 0;
  v488 = 0;
  v482 = a4;
  v8 = a1;
  v489 = 0;
  Index = a2;
  v487 = a1;
  result = sqlite3GetVdbe();
  v484 = result;
  v10 = result;
  if ( result )
  {
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    v11 = Index;
    v12 = 2;
    *((_DWORD *)v8 + 14) = 2;
    result = sqlite3TwoPartName(v8, v11, a3, &v472);
    v13 = (int)result;
    v478 = result;
    if ( (int)result >= 0 )
    {
      v470 = *(_QWORD *)(v5 + 32);
      if ( (_DWORD)result != 1 || (result = sqlite3OpenTempDatabase(v8), !(_DWORD)result) )
      {
        result = sqlite3NameFromToken(v5, v472);
        v486 = (unsigned __int8 *)result;
        if ( result )
        {
          v466 = (__int64 *)(32 * v13);
          if ( a5 )
            v14 = sqlite3MPrintf(v5, "-%T", a4);
          else
            v14 = sqlite3NameFromToken(v5, a4);
          v15 = v14;
          v483 = v14;
          if ( *(_DWORD *)(v479 + 8) )
            v16 = *(__int64 *)((char *)v466 + v470);
          else
            v16 = 0;
          v465 = v16;
          if ( (unsigned int)sqlite3AuthCheck((_DWORD)v8, 19, (_DWORD)v486, v15, v16) )
            goto LABEL_734;
          v17 = v465;
          *(_QWORD *)&v488 = 0;
          *((_QWORD *)&v488 + 1) = v486;
          v489 = (unsigned __int64)v15;
          *(_DWORD *)(v5 + 664) = 0;
          v18 = sqlite3_file_control(v5, v17, 14, &v488);
          v458 = v18;
          if ( !v18 )
          {
            sqlite3VdbeSetNumCols(v10, 1);
            sqlite3VdbeSetColName(v10, 0, 0, v488, -1);
            returnSingleText(v10, v488);
            sqlite3_free(v488);
            goto LABEL_734;
          }
          if ( v18 != 12 )
          {
            if ( (_QWORD)v488 )
            {
              sqlite3ErrorMsg(v8, "%s", (const char *)v488);
              sqlite3_free(v488);
              v18 = v458;
            }
            goto LABEL_18;
          }
          v19 = pragmaLocate(v486);
          v468 = (const char **)v19;
          v22 = v19;
          if ( !v19 )
            goto LABEL_734;
          if ( (*(_BYTE *)(v19 + 9) & 1) != 0 )
          {
            if ( (unsigned int)sqlite3ReadSchema(v8) )
              goto LABEL_734;
            v22 = (__int64)v468;
          }
          if ( (*(_BYTE *)(v22 + 9) & 2) == 0 && ((*(_BYTE *)(v22 + 9) & 4) == 0 || !v15) )
          {
            setPragmaResultColumnNames(v10, v22);
            v22 = (__int64)v468;
          }
          v23 = *(unsigned __int8 *)(v22 + 8);
          if ( v23 <= 0x16 )
          {
            if ( v23 != 22 )
            {
              if ( v23 <= 0xB )
              {
                if ( v23 == 11 )
                {
                  *((_DWORD *)v8 + 14) = 3;
                  for ( i = 0; (signed int)i < *(_DWORD *)(v5 + 40); ++i )
                  {
                    v68 = *(_QWORD *)(32LL * (int)i + *(_QWORD *)(v5 + 32) + 8);
                    if ( v68 )
                    {
                      v69 = sqlite3PagerFilename(**(_QWORD **)(v68 + 8), 1);
                      sqlite3VdbeMultiLoad(v10, v72, "iss", i, *(_QWORD *)(v70 + v71), v69, v453, v455, v456, v457);
                    }
                  }
                  goto LABEL_734;
                }
                if ( v23 <= 6 )
                {
                  if ( v23 == 6 )
                  {
                    if ( v15 )
                    {
                      v461 = 1;
                      Int32 = sqlite3GetInt32(v15, &v461);
                      v48 = v461;
                      if ( Int32 )
                        sqlite3BtreeSetSpillSize(*(__int64 *)((char *)v466 + v470 + 8), (unsigned int)v461);
                      v49 = v48 == 0;
                      v50 = *(_QWORD *)(v5 + 48);
                      LOBYTE(v47) = !v49;
                      Boolean = sqlite3GetBoolean(v15, v47);
                      v52 = v50;
                      v53 = v50 | 0x20;
                      v54 = v52 & 0xFFFFFFFFFFFFFFDFuLL;
                      if ( !Boolean )
                        v53 = v54;
                      *(_QWORD *)(v5 + 48) = v53;
                      goto LABEL_89;
                    }
                    if ( (*(_BYTE *)(v5 + 48) & 0x20) != 0 )
                      AutoVacuum = sqlite3BtreeSetSpillSize(*(__int64 *)((char *)v466 + v470 + 8), 0);
                    else
                      AutoVacuum = 0;
LABEL_732:
                    v27 = AutoVacuum;
                    goto LABEL_733;
                  }
                  if ( !*(_BYTE *)(v22 + 8) )
                  {
                    v472 = 0;
                    if ( v15 && !(unsigned int)sqlite3DecOrHexToI64((char *)v15) && v472 >= 0 )
                      *(_DWORD *)(v5 + 744) = v472 & 0x7FFFFFFF;
                    v27 = *(int *)(v5 + 744);
                    goto LABEL_733;
                  }
                  v24 = v23 - 1;
                  if ( v24 )
                  {
                    v25 = v24 - 1;
                    if ( v25 )
                    {
                      v26 = v25 - 1;
                      if ( v26 )
                      {
                        if ( v26 == 2 )
                        {
                          if ( !v15 )
                          {
                            v27 = *(int *)(*(__int64 *)((char *)v466 + v470 + 24) + 116);
                            goto LABEL_733;
                          }
                          v461 = 0;
                          sqlite3GetInt32(v15, &v461);
                          v28 = v466;
                          v29 = v470;
                          *(_DWORD *)(*(__int64 *)((char *)v466 + v470 + 24) + 116) = v461;
                          v30 = *(__int64 *)((char *)v28 + v29 + 24);
                          v31 = *(__int64 *)((char *)v28 + v29 + 8);
LABEL_199:
                          sqlite3BtreeSetCacheSize(v31, *(unsigned int *)(v30 + 116));
                          goto LABEL_734;
                        }
LABEL_694:
                        if ( v15 )
                        {
                          v458 = 0;
                          sqlite3GetInt32(v15, &v458);
                          sqlite3_busy_timeout(v5, v458);
                        }
                        v27 = *(int *)(v5 + 748);
                        goto LABEL_733;
                      }
                      if ( !v15 )
                      {
                        setPragmaResultColumnNames(v10, v22);
                        v27 = (*(_QWORD *)(v5 + 48) & (unsigned __int64)v468[2]) != 0;
                        goto LABEL_733;
                      }
                      v32 = *(_QWORD *)(v22 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                      if ( *(_BYTE *)(v5 + 101) )
                        v32 = *(_QWORD *)(v22 + 16);
                      if ( (unsigned __int8)sqlite3GetBoolean(v15, 0) )
                      {
                        if ( (v32 & 1) == 0 || (*(_DWORD *)(v5 + 48) & 0x10000000) == 0 )
                          *(_QWORD *)(v5 + 48) |= v32;
                      }
                      else
                      {
                        *(_QWORD *)(v5 + 48) &= ~v32;
                        if ( v32 == 0x80000 )
                        {
                          *(_QWORD *)(v5 + 768) = 0;
                        }
                        else if ( (v32 & 1) != 0 && !(unsigned int)sqlite3_stricmp(v15, "reset") )
                        {
                          sqlite3ResetAllSchemasOfConnection(v5);
                        }
                      }
                      sqlite3VdbeAddOp3(v10, 166, 0, 0, 0);
LABEL_89:
                      setAllPagerFlags(v5);
                      goto LABEL_734;
                    }
                    v33 = *(__int64 *)((char *)v466 + v470 + 8);
                    if ( v15 )
                    {
                      if ( (unsigned int)sqlite3StrICmp(v15, "none") )
                      {
                        if ( (unsigned int)sqlite3StrICmp(v15, "full") )
                        {
                          if ( (unsigned int)sqlite3StrICmp(v15, "incremental") )
                          {
                            v463 = 0;
                            sqlite3GetInt32(v15, &v463);
                            v35 = v463;
                            if ( (unsigned int)v463 > 2 )
                              v35 = 0;
                            v12 = v35;
                          }
                        }
                        else
                        {
                          v12 = 1;
                        }
                      }
                      else
                      {
                        v12 = 0;
                      }
                      *(_BYTE *)(v5 + 106) = v12;
                      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v33, v12) && v12 - 1 <= 1 )
                      {
                        v36 = *(_DWORD *)(v10 + 144);
                        v37 = (_DWORD *)sqlite3VdbeAddOpList(v10, 5, qword_1800BE410);
                        v38 = v478;
                        v39 = v478;
                        v37[14] = v36 + 4;
                        v37[27] = v12 - 1;
                        v37[1] = v38;
                        v37[7] = v38;
                        v37[25] = v38;
                        sqlite3VdbeUsesBtree(v10, v39);
                      }
                      goto LABEL_734;
                    }
                    AutoVacuum = sqlite3BtreeGetAutoVacuum(*(__int64 *)((char *)v466 + v470 + 8));
                    goto LABEL_732;
                  }
                  v40 = *(_DWORD *)(v22 + 16);
                  sqlite3VdbeUsesBtree(v10, (unsigned int)v13);
                  if ( v15 && (*(_BYTE *)(v42 + 9) & 8) == 0 )
                  {
                    v461 = 0;
                    v43 = sqlite3VdbeAddOpList(v41, 2, &qword_1800BD2C8);
                    *(_DWORD *)(v43 + 4) = v13;
                    *(_DWORD *)(v43 + 28) = v13;
                    *(_DWORD *)(v43 + 32) = v40;
                    sqlite3GetInt32(v15, &v461);
                    *(_DWORD *)(v43 + 36) = v461;
                    *(_WORD *)(v43 + 26) = 1;
                    if ( v40 == 1 && (*(_DWORD *)(v5 + 48) & 0x10000000) != 0 )
                      *(_BYTE *)(v43 + 24) = -69;
                    goto LABEL_734;
                  }
                  v44 = (_DWORD *)sqlite3VdbeAddOpList(v41, 3, qword_1800BDF08);
                  v45 = v10;
                  v44[1] = v13;
                  v44[7] = v13;
                  v44[9] = v40;
LABEL_74:
                  sqlite3VdbeReusable(v45);
                  goto LABEL_734;
                }
                v55 = v23 - 7;
                if ( !v55 )
                {
                  if ( v15 )
                  {
                    v66 = sqlite3GetBoolean(v15, 0);
                    sqlite3RegisterLikeFunctions(v5, v66);
                  }
                  goto LABEL_734;
                }
                v56 = v55 - 1;
                if ( v56 )
                {
                  v57 = v56 - 1;
                  if ( !v57 )
                  {
                    *((_DWORD *)v8 + 14) = 1;
                    v61 = 0;
                    for ( j = 0; ; j = v61 )
                    {
                      v63 = sqlite3_compileoption_get(j);
                      v45 = v10;
                      if ( !v63 )
                        break;
                      ++v61;
                      sqlite3VdbeAddOp4(v10, 117, 0, 1, 0, v63, 0);
                      sqlite3VdbeAddOp3(v10, 84, 1, 1, 0);
                    }
                    goto LABEL_74;
                  }
                  if ( v57 != 1 )
                    goto LABEL_694;
                  v58 = sqlite3MutexAlloc(11);
                  sqlite3_mutex_enter(v58);
                  if ( !v15 )
                  {
                    v59 = sqlite3_data_directory;
LABEL_606:
                    returnSingleText(v10, v59);
LABEL_611:
                    v390 = sqlite3MutexAlloc(11);
                    sqlite3_mutex_leave(v390);
                    goto LABEL_734;
                  }
                  if ( !*(_BYTE *)v15
                    || (v60 = *(_QWORD *)v5,
                        v461 = 0,
                        !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, int *))(v60 + 56))(
                           v60,
                           v15,
                           1,
                           &v461))
                    && v461 )
                  {
                    sqlite3_free(sqlite3_data_directory);
                    if ( *(_BYTE *)v15 )
                      sqlite3_data_directory = sqlite3_mprintf("%s", (const char *)v15);
                    else
                      sqlite3_data_directory = 0;
                    goto LABEL_611;
                  }
                  goto LABEL_610;
                }
                *((_DWORD *)v8 + 14) = 2;
                v64 = *(__int64 ***)(v5 + 632);
                if ( !v64 )
                  goto LABEL_734;
                v65 = 0;
                do
                {
                  sqlite3VdbeMultiLoad(v10, 1, "is", v65, *v64[2], v449, v453, v455, v456, v457);
                  v64 = (__int64 **)*v64;
                  ++v65;
                }
                while ( v64 );
LABEL_677:
                v15 = v483;
                goto LABEL_734;
              }
              if ( (unsigned __int8)v23 <= 0x11u )
              {
                if ( (_BYTE)v23 != 17 )
                {
                  v73 = v23 - 12;
                  if ( !v73 )
                  {
                    sqlite3VdbeUsesBtree(v10, (unsigned int)v13);
                    if ( !v15 )
                    {
                      *((_DWORD *)v8 + 14) += 2;
                      v130 = (_DWORD *)sqlite3VdbeAddOpList(v129, 9, qword_1800BD6B0);
                      v130[1] = v13;
                      v130[7] = v13;
                      v130[37] = -2000;
                      goto LABEL_734;
                    }
                    v461 = 0;
                    sqlite3GetInt32(v15, &v461);
                    v131 = sqlite3AbsInt32((unsigned int)v461);
                    sqlite3BeginWriteOperation(v8, 0, v478, v132);
                    sqlite3VdbeAddOp3(v10, 100, v478, 3, v131);
                    v133 = v466;
                    v134 = v470;
                    *(_DWORD *)(*(__int64 *)((char *)v466 + v470 + 24) + 116) = v131;
                    v30 = *(__int64 *)((char *)v133 + v134 + 24);
                    v31 = *(__int64 *)((char *)v133 + v134 + 8);
                    goto LABEL_199;
                  }
                  v74 = v73 - 1;
                  if ( v74 )
                  {
                    v75 = v74 - 1;
                    if ( !v75 )
                    {
                      _mm_lfence();
                      v96 = *((_DWORD *)v8 + 14);
                      v97 = v96 + 1;
                      v96 += 5;
                      *((_DWORD *)v8 + 14) = v96;
                      v463 = v97;
                      v462 = v96;
                      v98 = *(const char ***)(*(__int64 *)((char *)v466 + *(_QWORD *)(v5 + 32) + 24) + 16);
                      while ( v98 )
                      {
                        if ( v15 )
                        {
                          Table = sqlite3LocateTable(v8, 0, v15, v465);
                          v98 = 0;
                        }
                        else
                        {
                          Table = (__int64)v98[2];
                          v98 = (const char **)*v98;
                        }
                        v485 = v98;
                        v466 = (__int64 *)Table;
                        if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                        {
                          v100 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Table + 96));
                          v101 = *(_QWORD *)(v5 + 32);
                          IndexKey = v100;
                          v102 = *(_QWORD *)(32LL * (int)v100 + v101);
                          v465 = v102;
                          sqlite3CodeVerifySchema(v8, v100);
                          sqlite3TableLock(v8, IndexKey, *((unsigned int *)v466 + 10), 0, *v466);
                          v103 = (int)v466;
                          v104 = v462 + *((__int16 *)v466 + 27);
                          if ( *((_DWORD *)v8 + 14) < v104 )
                            *((_DWORD *)v8 + 14) = v104;
                          sqlite3OpenTable((_DWORD)v8, 0, IndexKey, v103, 112);
                          sqlite3VdbeAddOp4(v10, 117, 0, v463, 0, *v466, 0);
                          v105 = 1;
                          for ( k = v466[9]; ; k = *(_QWORD *)(v472 + 8) )
                          {
                            v472 = k;
                            v460 = v105;
                            if ( !k )
                              break;
                            v107 = sqlite3FindTable(v5, *(_QWORD *)(k + 16), v102);
                            v468 = (const char **)v107;
                            if ( v107 )
                            {
                              v108 = *(unsigned int *)(v107 + 40);
                              v446 = *(_QWORD *)v107;
                              v470 = 0;
                              sqlite3TableLock(v8, IndexKey, v108, 0, v446);
                              if ( (unsigned int)sqlite3FkLocateIndex(
                                                   (_DWORD)v8,
                                                   (_DWORD)v468,
                                                   v472,
                                                   (unsigned int)&v470,
                                                   0) )
                                goto LABEL_734;
                              if ( v470 )
                              {
                                sqlite3VdbeAddOp3(v10, 112, v460, *(_DWORD *)(v470 + 88), IndexKey);
                                sqlite3VdbeSetP4KeyInfo(v8, v470);
                              }
                              else
                              {
                                sqlite3OpenTable((_DWORD)v8, v460, IndexKey, (_DWORD)v468, 112);
                              }
                            }
                            v105 = v460 + 1;
                          }
                          if ( *((_DWORD *)v8 + 13) < v105 )
                            *((_DWORD *)v8 + 13) = v105;
                          v471 = sqlite3VdbeAddOp3(v10, 36, 0, 0, 0);
                          IndexKey = 1;
                          v482 = v466[9];
                          if ( v482 )
                          {
                            v109 = v466;
                            v474 = v463 + 2;
                            v469 = v463 + 1;
                            do
                            {
                              v110 = v102;
                              v111 = v482;
                              v112 = sqlite3FindTable(v5, *(_QWORD *)(v482 + 16), v110);
                              Index = v112;
                              v470 = 0;
                              v113 = 0;
                              v468 = 0;
                              if ( v112 )
                              {
                                sqlite3FkLocateIndex((_DWORD)v8, v112, v111, (unsigned int)&v470, (__int64)&v468);
                                v113 = v468;
                              }
                              v114 = v462;
                              v115 = *((_DWORD *)v8 + 17) - 1;
                              *((_DWORD *)v8 + 17) = v115;
                              v116 = v114 + *(_DWORD *)(v111 + 40);
                              v460 = v115;
                              if ( *((_DWORD *)v8 + 14) < v116 )
                                *((_DWORD *)v8 + 14) = v116;
                              v461 = *(_DWORD *)(v111 + 40);
                              if ( v461 > 0 )
                              {
                                v117 = v114;
                                for ( m = 0; m < v461; ++m )
                                {
                                  if ( v113 )
                                    v119 = *((_DWORD *)v113 + m);
                                  else
                                    v119 = *(_DWORD *)(v111 + 16 * (m + 4LL));
                                  sqlite3ExprCodeGetColumnOfTable(v10, (_DWORD)v109, 0, v119, v117 + m);
                                  sqlite3VdbeAddOp3(v10, 50, v117 + m, v460, 0);
                                  v111 = v482;
                                  v113 = v468;
                                  v461 = *(_DWORD *)(v482 + 40);
                                }
                                v5 = v476;
                                v8 = v487;
                                v114 = v462;
                              }
                              if ( v470 )
                              {
                                v120 = *(_DWORD *)(v111 + 40);
                                v121 = sqlite3IndexAffinityStr(v5);
                                sqlite3VdbeAddOp4(v10, 96, v462, v120, 0, v121, v461);
                                v111 = v482;
                                sqlite3VdbeAddOp4Int(v10, 29, IndexKey, v460, v462, *(_DWORD *)(v482 + 40));
                              }
                              else if ( Index )
                              {
                                sqlite3VdbeAddOp3(v10, 30, IndexKey, *(_DWORD *)(v10 + 144) + 2, v114);
                                sqlite3VdbeAddOp3(v10, 9, 0, v460, 0);
                              }
                              sqlite3VdbeAddOp3(v10, (*((_DWORD *)v109 + 12) & 0x80u) != 0 ? 75 : 135, 0, v469, 0);
                              LODWORD(v447) = IndexKey - 1;
                              sqlite3VdbeMultiLoad(
                                v10,
                                v474,
                                "siX",
                                *(_QWORD *)(v111 + 16),
                                v447,
                                v450,
                                v454,
                                v455,
                                v456,
                                v457);
                              sqlite3VdbeAddOp3(v10, 84, v463, 4, 0);
                              sqlite3VdbeResolveLabel(v10, v460);
                              sqlite3DbFree(v5, v468);
                              v122 = *(_QWORD *)(v111 + 8);
                              ++IndexKey;
                              v49 = v122 == 0;
                              v482 = v122;
                              v102 = v465;
                            }
                            while ( !v49 );
                            v15 = v483;
                          }
                          v123 = v471;
                          sqlite3VdbeAddOp3(v10, 39, 0, v471 + 1, 0);
                          *(_DWORD *)(sqlite3VdbeGetOp(v10, v123, v124, v125) + 8) = *(_DWORD *)(v10 + 144);
                          v98 = v485;
                        }
                      }
                      goto LABEL_734;
                    }
                    v76 = v75 - 1;
                    if ( v76 )
                    {
                      if ( v76 == 1 )
                      {
                        v77 = (*(_DWORD *)(v5 + 44) >> 5) & 1;
                        *((_DWORD *)v8 + 14) = 6;
                        for ( n = 0; n != 23; ++n )
                        {
                          for ( ii = qword_1800D1250[n]; ii; ii = *(_QWORD *)(ii + 64) )
                            pragmaFunclistLine(v10, ii, 1, v77);
                        }
                        v80 = *(_QWORD **)(v5 + 608);
                        v15 = v483;
                        while ( v80 )
                        {
                          pragmaFunclistLine(v10, v80[2], 0, v77);
                          v80 = (_QWORD *)*v80;
                        }
                        goto LABEL_734;
                      }
                      goto LABEL_694;
                    }
                    if ( !v15 )
                      goto LABEL_734;
                    v81 = sqlite3FindTable(v5, v15, v465);
                    v82 = v81;
                    if ( !v81 )
                      goto LABEL_734;
                    if ( *(_BYTE *)(v81 + 63) )
                      goto LABEL_734;
                    v83 = *(_QWORD *)(v81 + 72);
                    if ( !v83 )
                      goto LABEL_734;
                    v84 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v81 + 96));
                    v460 = v85;
                    *((_DWORD *)v8 + 14) = 8;
                    sqlite3CodeVerifySchema(v8, v84);
                    v87 = v460;
                    v88 = 0;
                    do
                    {
                      v89 = 0;
                      if ( *(int *)(v83 + 40) > 0 )
                      {
                        do
                        {
                          LOBYTE(v88) = *(_BYTE *)(v83 + 45);
                          actionName(v88, v86, v89);
                          LOBYTE(v90) = *(_BYTE *)(v83 + 46);
                          v93 = actionName(v90, v91, v92);
                          LODWORD(v445) = v89;
                          sqlite3VdbeMultiLoad(
                            v10,
                            1,
                            "iissssss",
                            v460,
                            v445,
                            *(_QWORD *)(v83 + 16),
                            *(_QWORD *)(*(_QWORD *)(v82 + 8) + 24LL * *(int *)(v83 + 16 * (v94 + 4))),
                            *(_QWORD *)(v83 + 16 * v94 + 72),
                            v93,
                            v95);
                          ++v89;
                        }
                        while ( v89 < *(_DWORD *)(v83 + 40) );
                        v87 = v460;
                        v88 = 0;
                      }
                      v83 = *(_QWORD *)(v83 + 8);
                      v460 = ++v87;
                    }
                    while ( v83 );
                    goto LABEL_677;
                  }
                  if ( v15 )
                  {
                    if ( (*(_BYTE *)(v5 + 44) & 0x40) == 0 )
                    {
                      for ( jj = &off_1800B3510; *jj; jj += 2 )
                      {
                        if ( !(unsigned int)sqlite3StrICmp(v15, *jj) )
                        {
                          if ( *((_BYTE *)jj + 8) )
                            LOBYTE(v12) = *((_BYTE *)jj + 8);
                          LOBYTE(v128) = v12;
                          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v5 + 32) + 24LL) + 113LL) = v12;
                          sqlite3SetTextEncoding(v5, v128);
                          break;
                        }
                      }
                      if ( !*jj )
                        sqlite3ErrorMsg(v8, "unsupported encoding: %s", (const char *)v15);
                    }
                    goto LABEL_734;
                  }
                  if ( (unsigned int)sqlite3ReadSchema(v8) )
                    goto LABEL_734;
                  v126 = (&off_1800B3510)[2 * *(unsigned __int8 *)(*v8 + 100)];
LABEL_515:
                  returnSingleText(v10, v126);
                  goto LABEL_734;
                }
                v472 = 0;
                if ( v15 )
                {
                  if ( !(unsigned int)sqlite3DecOrHexToI64((char *)v15) )
                  {
                    v135 = sqlite3_hard_heap_limit64(-1);
                    if ( v472 > 0 && (!v135 || v135 > v472) )
                      sqlite3_hard_heap_limit64(v472);
                  }
                }
                v136 = sqlite3_hard_heap_limit64(-1);
LABEL_207:
                v27 = v136;
                goto LABEL_733;
              }
              v137 = v23 - 18;
              if ( !v137 )
              {
                v458 = 0;
                if ( !v15 || !(unsigned int)sqlite3GetInt32(v15, &v458) || (v315 = v458, (int)v458 <= 0) )
                  v315 = 0x7FFFFFFF;
                sqlite3BeginWriteOperation(v8, 0, (unsigned int)v13, v21);
                sqlite3VdbeAddOp3(v10, 71, v315, 1, 0);
                v316 = sqlite3VdbeAddOp3(v10, 62, v13, 0, 0);
                sqlite3VdbeAddOp3(v10, 84, 1, 0, 0);
                sqlite3VdbeAddOp3(v10, 86, 1, -1, 0);
                sqlite3VdbeAddOp3(v10, 59, 1, v316, 0);
                *(_DWORD *)(sqlite3VdbeGetOp(v10, v316, v317, v318) + 8) = *(_DWORD *)(v10 + 144);
                goto LABEL_734;
              }
              v138 = v137 - 1;
              if ( v138 )
              {
                v139 = v138 - 1;
                if ( !v139 )
                {
                  if ( v15 )
                  {
                    v300 = sqlite3FindTable(v5, v15, v465);
                    v301 = v300;
                    if ( v300 )
                    {
                      v302 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v300 + 96));
                      *((_DWORD *)v8 + 14) = 5;
                      sqlite3CodeVerifySchema(v8, v302);
                      v303 = *(_QWORD *)(v301 + 16);
                      v304 = 0;
                      while ( v303 )
                      {
                        v49 = *(_QWORD *)(v303 + 72) == 0;
                        v490[0] = "c";
                        v490[1] = "u";
                        LODWORD(v455) = !v49;
                        v490[2] = "pk";
                        LODWORD(v449) = *(_BYTE *)(v303 + 98) != 0;
                        sqlite3VdbeMultiLoad(
                          v10,
                          1,
                          "isisi",
                          v304,
                          *(_QWORD *)v303,
                          v449,
                          v490[*(_DWORD *)(v303 + 100) & 3],
                          v455,
                          v456,
                          v457);
                        v303 = *(_QWORD *)(v303 + 40);
                        ++v304;
                      }
                    }
                  }
                  goto LABEL_734;
                }
                if ( v139 != 1 )
                  goto LABEL_694;
                v465 = 0;
                v49 = *((_BYTE *)qword_1800B4ED0 + *v486) == 113;
                v467 = *((_BYTE *)qword_1800B4ED0 + *v486);
                LODWORD(v466) = v49;
                v49 = *(_QWORD *)v479 == 0;
                v140 = 100;
                *((_DWORD *)v8 + 14) = 6;
                if ( v49 )
                  LODWORD(v13) = -1;
                v463 = 100;
                v478 = v13;
                v460 = 100;
                if ( !v15 )
                  goto LABEL_223;
                if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)v482, &v460) )
                {
                  v140 = v460;
                  v463 = v460;
                  if ( (int)v460 > 0 )
                    goto LABEL_223;
                  v140 = 100;
                }
                else
                {
                  if ( (int)v13 < 0 )
                    v141 = 0;
                  else
                    v141 = *(_QWORD *)(32LL * (int)v13 + *(_QWORD *)(v5 + 32));
                  v465 = sqlite3LocateTable(v8, 0, v15, v141);
                  v140 = v460;
                }
                v463 = v140;
LABEL_223:
                sqlite3VdbeAddOp3(v10, 71, v140 - 1, 1, 0);
                v142 = 0;
                v480 = 0;
                if ( *(int *)(v5 + 40) <= 0 )
                  goto LABEL_406;
                while ( 1 )
                {
                  if ( (int)v13 < 0 || v142 == (_DWORD)v13 )
                  {
                    sqlite3CodeVerifySchema(v8, v142);
                    v143 = 32LL * v480;
                    *((_BYTE *)v8 + 35) = 0;
                    v144 = *(_QWORD *)(v5 + 32);
                    Index = v143;
                    v145 = *(_QWORD *)(v144 + v143 + 24);
                    v146 = 0;
                    v472 = v145;
                    v147 = *(_QWORD **)(v145 + 16);
                    if ( v147 )
                    {
                      v148 = v465;
                      do
                      {
                        v149 = v147[2];
                        if ( !v465 || v465 == v149 )
                        {
                          if ( *(char *)(v149 + 48) >= 0 )
                            ++v146;
                          v150 = *(_QWORD *)(v149 + 16);
                          while ( v150 )
                          {
                            v150 = *(_QWORD *)(v150 + 40);
                            ++v146;
                          }
                        }
                        v147 = (_QWORD *)*v147;
                      }
                      while ( v147 );
                      if ( v146 )
                      {
                        v151 = v146 + 1;
                        if ( !v465 )
                          v151 = v146;
                        v152 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v151 + 4);
                        if ( !v152 )
                        {
LABEL_405:
                          v15 = v483;
LABEL_406:
                          v294 = sqlite3VdbeAddOpList(v10, 7, qword_1800BDCB0);
                          v296 = v294;
                          if ( v294 )
                          {
                            *(_DWORD *)(v294 + 8) = 1 - v463;
                            *(_QWORD *)(v294 + 64) = "ok";
                            *(_BYTE *)(v294 + 49) = -1;
                            *(_BYTE *)(v294 + 121) = -1;
                            v297 = sqlite3ErrStr(11, v295, v294);
                            *(_QWORD *)(v296 + 136) = v297;
                          }
                          Op = sqlite3VdbeGetOp(v10, 0, v296, (unsigned int)(*(_DWORD *)(v10 + 144) - 2));
                          *(_DWORD *)(Op + 12) = v299;
                          goto LABEL_734;
                        }
                        v153 = 0;
                        if ( v148 )
                        {
                          v153 = 1;
                          v152[1] = 0;
                        }
                        for ( kk = *(_QWORD **)(v472 + 16); kk; kk = (_QWORD *)*kk )
                        {
                          v155 = kk[2];
                          if ( !v148 || v148 == v155 )
                          {
                            if ( *(char *)(v155 + 48) >= 0 )
                            {
                              v156 = v153++;
                              v152[v156 + 1] = *(_DWORD *)(v155 + 40);
                            }
                            for ( mm = *(_QWORD *)(v155 + 16); mm; mm = *(_QWORD *)(mm + 40) )
                              v152[++v153] = *(_DWORD *)(mm + 88);
                          }
                        }
                        *v152 = v153;
                        if ( *((_DWORD *)v8 + 14) < v153 + 8 )
                          *((_DWORD *)v8 + 14) = v153 + 8;
                        *((_BYTE *)v8 + 31) = 0;
                        *((_DWORD *)v8 + 10) = 0;
                        sqlite3VdbeAddOp4(v10, 155, 1, v153, 8, (__int64)v152, -14);
                        sqlite3VdbeChangeP5(v10, (unsigned __int8)v480);
                        v159 = sqlite3VdbeAddOp3(v158, 50, 2, 0, 0);
                        v160 = sqlite3MPrintf(
                                 v5,
                                 "*** in database %s ***\n",
                                 *(const char **)(*(_QWORD *)(v5 + 32) + Index));
                        sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v160, -6);
                        sqlite3VdbeAddOp3(v10, 111, 2, 3, 3);
                        integrityCheckResultRow(v10);
                        *(_DWORD *)(sqlite3VdbeGetOp(v10, v159, v161, v162) + 8) = *(_DWORD *)(v10 + 144);
                        sqlite3VdbeAddOp4(v10, 117, 0, 2, 0, (__int64)"wrong # of entries in index ", 0);
                        v163 = 0;
                        Index = *(_QWORD *)(v472 + 16);
                        if ( Index )
                        {
                          v164 = v465;
                          v165 = (_QWORD *)Index;
                          v166 = v465 != 0;
                          IndexKey = v166;
                          do
                          {
                            v167 = v165[2];
                            if ( !v164 || v164 == v167 )
                            {
                              v49 = *(_BYTE *)(v167 + 48) >= 0;
                              v168 = v166;
                              v460 = v166;
                              if ( v49 )
                              {
                                ++v166;
                                v169 = (const char ***)(v167 + 16);
                                IndexKey = v166;
                              }
                              else
                              {
                                v170 = (const char ***)(v167 + 16);
                                v171 = *(_QWORD *)(v167 + 16);
                                if ( v171 )
                                {
                                  do
                                  {
                                    v169 = v170;
                                    if ( (*(_DWORD *)(v171 + 100) & 3) == 2 )
                                      break;
                                    v171 = *(_QWORD *)(v171 + 40);
                                    v460 = ++v168;
                                  }
                                  while ( v171 );
                                  v166 = IndexKey;
                                }
                                else
                                {
                                  v169 = v170;
                                }
                              }
                              v172 = *v169;
                              v468 = v172;
                              if ( v172 )
                              {
                                v173 = v166 + 8;
                                do
                                {
                                  if ( !v172[9] )
                                  {
                                    v174 = sqlite3VdbeAddOp3(v10, 53, v173, 0, v168 + 8);
                                    sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)*v468, 0);
                                    sqlite3VdbeAddOp3(v10, 111, 4, 2, 3);
                                    integrityCheckResultRow(v10);
                                    v177 = sqlite3VdbeGetOp(v10, v174, v175, v176);
                                    v163 = 0;
                                    *(_DWORD *)(v177 + 8) = *(_DWORD *)(v10 + 144);
                                    v166 = IndexKey;
                                    v172 = v468;
                                  }
                                  v172 = (const char **)v172[5];
                                  ++v166;
                                  v168 = v460;
                                  ++v173;
                                  IndexKey = v166;
                                  v468 = v172;
                                }
                                while ( v172 );
                              }
                              v164 = v465;
                            }
                            v165 = (_QWORD *)*v165;
                          }
                          while ( v165 );
                          v5 = v476;
                          v8 = v487;
                        }
                        v178 = v472;
                        v179 = *(_QWORD *)(v472 + 16);
                        Index = v179;
                        if ( v179 )
                        {
                          v180 = (const char **)v465;
                          while ( 1 )
                          {
                            v181 = *(const char ***)(v179 + 16);
                            v485 = v181;
                            v473 = v163;
                            v474 = v163;
                            if ( v180 && v180 != v181 || *((_BYTE *)v181 + 63) != (_BYTE)v163 )
                              goto LABEL_385;
                            if ( v467 == 113 || *((char *)v181 + 48) >= 0 )
                            {
                              v482 = v163;
                              v460 = v163;
                            }
                            else
                            {
                              v482 = sqlite3PrimaryKeyIndex(v181);
                              TempRange = sqlite3GetTempRange(v8, *(unsigned __int16 *)(v482 + 94));
                              v184 = *(unsigned __int16 *)(v183 + 94) - 1;
                              v460 = TempRange;
                              sqlite3VdbeAddOp3(v10, 75, 1, TempRange, TempRange + v184);
                              v163 = 0;
                            }
                            sqlite3OpenTableAndIndices(
                              (_DWORD)v8,
                              (_DWORD)v181,
                              112,
                              0,
                              1,
                              v163,
                              (__int64)&v473,
                              (__int64)&v474);
                            sqlite3VdbeAddOp3(v10, 71, 0, 7, 0);
                            v185 = v181[2];
                            if ( v185 )
                            {
                              v186 = 8;
                              do
                              {
                                sqlite3VdbeAddOp3(v10, 71, 0, v186, 0);
                                v185 = (const char *)*((_QWORD *)v185 + 5);
                                ++v186;
                              }
                              while ( v185 );
                              v5 = v476;
                              v8 = v487;
                            }
                            sqlite3VdbeAddOp3(v10, 36, v473, 0, 0);
                            v187 = sqlite3VdbeAddOp3(v10, 86, 7, 1, 0);
                            v49 = *((_BYTE *)v181 + 48) >= 0;
                            LODWORD(v470) = v187;
                            if ( v49 )
                            {
                              v188 = *((__int16 *)v181 + 27);
                              v189 = -1;
                              if ( v188 > 0 )
                              {
                                for ( nn = 0; nn < v188; ++nn )
                                {
                                  v191 = v189 + 1;
                                  if ( (v181[1][24 * nn + 18] & 0x20) != 0 )
                                    v191 = v189;
                                  v189 = v191;
                                }
                              }
                              v192 = v189 - 1;
                              if ( v189 != *((__int16 *)v181 + 26) )
                                v192 = v189;
                            }
                            else
                            {
                              v192 = *(unsigned __int16 *)(sqlite3PrimaryKeyIndex(v181) + 96) - 1;
                            }
                            if ( v192 >= 0 )
                            {
                              sqlite3VdbeAddOp3(v10, 94, v473, v192, 3);
                              sqlite3VdbeTypeofColumn(v10, 3);
                            }
                            if ( v467 != 113 && v482 )
                            {
                              v193 = sqlite3VdbeAddOp4Int(v10, 41, v473, 0, v460, *(unsigned __int16 *)(v482 + 94));
                              sqlite3VdbeAddOp3(v10, 50, v460, 0, 0);
                              v194 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v485);
                              sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v194, -6);
                              integrityCheckResultRow(v10);
                              *(_DWORD *)(sqlite3VdbeGetOp(v10, v193, v195, v196) + 8) = *(_DWORD *)(v10 + 144);
                              v199 = sqlite3VdbeGetOp(v10, v193 + 1, v197, v198);
                              v200 = 0;
                              *(_DWORD *)(v199 + 8) = *(_DWORD *)(v10 + 144);
                              if ( *(_WORD *)(v482 + 94) )
                              {
                                v201 = v473;
                                v202 = v482;
                                v203 = v460;
                                do
                                {
                                  sqlite3ExprCodeLoadIndexColumn((_DWORD)v8, v202, v201, v200, v203 + v200);
                                  ++v200;
                                }
                                while ( v200 < *(unsigned __int16 *)(v202 + 94) );
                                v10 = v484;
                                v5 = v476;
                                v181 = v485;
                              }
                              else
                              {
                                v181 = v485;
                              }
                            }
                            v204 = 0;
                            v205 = (_DWORD)v181[6] & 0x10000;
                            v206 = *((_WORD *)v181 + 27) > 0;
                            v461 = v205;
                            while ( 1 )
                            {
                              v477 = v204;
                              if ( !v206 )
                                break;
                              if ( (_DWORD)v204 == *((__int16 *)v181 + 26) )
                                goto LABEL_344;
                              v207 = (__int64)&v181[1][24 * (int)v204];
                              v468 = (const char **)v207;
                              v208 = (char *)(v207 + 12);
                              if ( v205 )
                              {
                                v209 = *(_DWORD *)(v207 + 8) & 0xF0;
                                v210 = v209 > 0x10;
                                v481 = v209 > 0x10;
                              }
                              else if ( *v208 <= 65 )
                              {
                                v210 = 0;
                                v481 = 0;
                              }
                              else
                              {
                                v210 = 1;
                                v481 = 1;
                              }
                              if ( (*(_BYTE *)(v207 + 8) & 0xF) != 0 || v210 )
                              {
                                v49 = (*(_BYTE *)(v207 + 18) & 0x20) == 0;
                                IndexKey = 5;
                                if ( v49 )
                                {
                                  if ( *(_WORD *)(v207 + 16) )
                                  {
                                    v479 = 0;
                                    v213 = sqlite3ColumnExpr(v181, v207, v210, v208);
                                    LOBYTE(v214) = *v214;
                                    LOBYTE(v215) = *(_BYTE *)(v5 + 100);
                                    sqlite3ValueFromExpr(v5, v213, v215, (_DWORD)v214, (__int64)&v479);
                                    if ( v479 )
                                    {
                                      IndexKey = *((unsigned __int8 *)qword_1800B5270 + (*(_WORD *)(v479 + 20) & 0x3F));
                                      sqlite3ValueFree();
                                    }
                                    v204 = v477;
                                  }
                                  v49 = *((_BYTE *)v181 + 48) >= 0;
                                  v462 = v473;
                                  if ( v49 )
                                  {
                                    v217 = sqlite3TableColumnToStorage(v181, v204, v210, v208);
                                    v211 = v462;
                                  }
                                  else
                                  {
                                    v216 = sqlite3PrimaryKeyIndex(v181);
                                    v217 = sqlite3TableColumnToIndex(v216);
                                  }
                                  v212 = v217;
                                }
                                else
                                {
                                  sqlite3ExprCodeGetColumnOfTable(v10, (_DWORD)v181, v473, v204, 3);
                                  v211 = -1;
                                  v462 = -1;
                                  v212 = 3;
                                }
                                v218 = *((_DWORD *)v8 + 17) - 1;
                                LODWORD(v475) = v212;
                                v458 = v218;
                                v219 = v218 - 1;
                                v220 = v468;
                                *((_DWORD *)v8 + 17) = v219;
                                v471 = v219;
                                if ( ((_BYTE)v220[1] & 0xF) != 0 )
                                {
                                  LODWORD(v479) = sqlite3VdbeAddOp4Int(v10, 18, v211, v219, v212, IndexKey);
                                  if ( v462 >= 0 )
                                  {
                                    sqlite3VdbeChangeP5(v10, 13);
                                    sqlite3VdbeAddOp3(v222, 94, v223, (_DWORD)v475, 3);
                                    sqlite3ColumnDefault(v10, v181, v477, 3);
                                    v469 = sqlite3VdbeAddOp3(v10, 51, 3, v471, 0);
                                  }
                                  else
                                  {
                                    sqlite3VdbeChangeP5(v10, 15);
                                    v469 = v221;
                                  }
                                  v224 = sqlite3MPrintf(v5, "NULL value in %s.%s", *v181, *v468);
                                  sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v224, -6);
                                  v225 = v481;
                                  if ( v481 )
                                  {
                                    sqlite3VdbeAddOp3(v10, 9, 0, v458, 0);
                                    v228 = sqlite3VdbeGetOp(v10, (unsigned int)v479, v226, v227);
                                    v229 = v469;
                                    *(_DWORD *)(v228 + 8) = *(_DWORD *)(v10 + 144);
                                    *(_DWORD *)(sqlite3VdbeGetOp(v10, v229, v230, v231) + 8) = *(_DWORD *)(v10 + 144);
                                    v220 = v468;
                                    v219 = v471;
                                    goto LABEL_330;
                                  }
                                  v220 = v468;
                                  v219 = v471;
                                }
                                else
                                {
LABEL_330:
                                  v225 = v481;
                                }
                                if ( v461 )
                                {
                                  if ( v225 )
                                  {
                                    sqlite3VdbeAddOp4Int(v10, 18, v462, v219, (_DWORD)v475, IndexKey);
                                    sqlite3VdbeChangeP5(
                                      v10,
                                      *((unsigned __int8 *)&qword_1800BE458[1]
                                      + ((*((_DWORD *)v468 + 2) >> 4) & 0xFu)
                                      + 7));
                                    v234 = sqlite3MPrintf(
                                             v5,
                                             "non-%s value in %s.%s",
                                             *(const char **)(v233
                                                            + 8LL
                                                            * ((unsigned int)((unsigned __int8)*(_DWORD *)(v232 + 8) >> 4)
                                                             - 1)
                                                            + 853728),
                                             *v181,
                                             *(const char **)&v181[1][24 * v477]);
                                    goto LABEL_341;
                                  }
LABEL_342:
                                  sqlite3VdbeResolveLabel(v10, v458);
                                  integrityCheckResultRow(v10);
                                  sqlite3VdbeResolveLabel(v10, v471);
                                  LODWORD(v204) = v477;
                                  goto LABEL_343;
                                }
                                v235 = *((_BYTE *)v220 + 12);
                                if ( v235 == 66 )
                                {
                                  sqlite3VdbeAddOp4Int(v10, 18, v462, v219, (_DWORD)v475, IndexKey);
                                  sqlite3VdbeChangeP5(v10, 28);
                                  v234 = sqlite3MPrintf(
                                           v5,
                                           "NUMERIC value in %s.%s",
                                           *v181,
                                           *(_QWORD *)&v181[1][24 * v477]);
                                }
                                else
                                {
                                  if ( v235 < 67 )
                                    goto LABEL_342;
                                  sqlite3VdbeAddOp4Int(v10, 18, v462, v219, (_DWORD)v475, IndexKey);
                                  sqlite3VdbeChangeP5(v10, 27);
                                  if ( v462 >= 0 )
                                    sqlite3ExprCodeGetColumnOfTable(v236, (_DWORD)v181, v473, v477, 3);
                                  sqlite3VdbeAddOp4(v10, 96, 3, 1, 0, (__int64)"C", -1);
                                  sqlite3VdbeAddOp4Int(v10, 18, -1, v471, 3, IndexKey);
                                  sqlite3VdbeChangeP5(v10, 28);
                                  v234 = sqlite3MPrintf(
                                           v5,
                                           "TEXT value in %s.%s",
                                           *v181,
                                           *(_QWORD *)&v181[1][24 * v477]);
                                }
LABEL_341:
                                sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v234, -6);
                                goto LABEL_342;
                              }
LABEL_343:
                              v205 = v461;
LABEL_344:
                              v204 = (unsigned int)(v204 + 1);
                              v206 = (int)v204 < *((__int16 *)v181 + 27);
                            }
                            v237 = v181[4];
                            if ( v237 && (*(_DWORD *)(v5 + 48) & 0x200LL) == 0 )
                            {
                              v238 = (const char **)sqlite3ExprListDup(v5, v237, 0);
                              v468 = v238;
                              v239 = v238;
                              if ( !*(_BYTE *)(v5 + 103) )
                              {
                                v458 = *((_DWORD *)v8 + 17) - 1;
                                v469 = v458 - 1;
                                *((_DWORD *)v8 + 17) = v458 - 1;
                                *((_DWORD *)v8 + 16) = v473 + 1;
                                v240 = *(_DWORD *)v238 - 1;
                                if ( *(_DWORD *)v239 - 1 > 0 )
                                {
                                  v241 = v240;
                                  v242 = v239;
                                  do
                                    sqlite3ExprIfFalse(v8, v242[4 * (unsigned int)v241-- + 1], v458, 0);
                                  while ( v241 > 0 );
                                  v10 = v484;
                                  v5 = v476;
                                  v181 = v485;
                                  v239 = v468;
                                }
                                sqlite3ExprIfTrue(v8, v239[1], v469, 16);
                                sqlite3VdbeResolveLabel(v10, v458);
                                *((_DWORD *)v8 + 16) = 0;
                                v243 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v181);
                                sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, v243, -6);
                                integrityCheckResultRow(v10);
                                sqlite3VdbeResolveLabel(v10, v469);
                                v239 = v468;
                              }
                              sqlite3ExprListDeleteGeneric(v5, v239);
                            }
                            if ( v467 != 113 )
                            {
                              v244 = (char *)v181[2];
                              v245 = 0;
                              v462 = 0;
                              v246 = 0;
                              v475 = v244;
                              v247 = -1;
                              if ( v244 )
                              {
                                v248 = v485;
                                do
                                {
                                  v249 = *((_DWORD *)v8 + 17) - 1;
                                  v461 = 0;
                                  *((_DWORD *)v8 + 17) = v249;
                                  if ( (char *)v482 != v244 )
                                  {
                                    IndexKey = sqlite3GenerateIndexKey(
                                                 (_DWORD)v8,
                                                 (_DWORD)v244,
                                                 v473,
                                                 0,
                                                 0,
                                                 (__int64)&v461,
                                                 v246,
                                                 v247);
                                    v468 = (const char **)v244;
                                    sqlite3VdbeAddOp3(v10, 86, v462 + 8, 1, 0);
                                    v451 = *((unsigned __int16 *)v244 + 48);
                                    LODWORD(v479) = v474 + v462;
                                    v250 = sqlite3VdbeAddOp4Int(v10, 29, v474 + v462, v249, IndexKey, v451);
                                    sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"row ", 0);
                                    sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                    sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" missing from index ", 0);
                                    sqlite3VdbeAddOp3(v10, 111, 4, 3, 3);
                                    v251 = sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, *(_QWORD *)v475, 0);
                                    v469 = v251;
                                    sqlite3VdbeAddOp3(v10, 111, 4, 3, 3);
                                    v481 = integrityCheckResultRow(v10);
                                    *(_DWORD *)(sqlite3VdbeGetOp(v10, v250, v252, v253) + 8) = *(_DWORD *)(v10 + 144);
                                    if ( *((char *)v248 + 48) >= 0 )
                                    {
                                      sqlite3VdbeAddOp3(v10, 142, v479, 3, 0);
                                      v255 = sqlite3VdbeAddOp3(
                                               v10,
                                               53,
                                               3,
                                               0,
                                               *((unsigned __int16 *)v475 + 48) + IndexKey - 1);
                                      sqlite3VdbeAddOp4(
                                        v10,
                                        117,
                                        0,
                                        3,
                                        0,
                                        (__int64)"rowid not at end-of-record for row ",
                                        0);
                                      sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                      sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" of index ", 0);
                                      sqlite3VdbeAddOp3(v10, 9, 0, v251 - 1, 0);
                                      *(_DWORD *)(sqlite3VdbeGetOp(v10, v255, v256, v257) + 8) = *(_DWORD *)(v10 + 144);
                                    }
                                    v244 = v475;
                                    v258 = 0;
                                    v259 = 0;
                                    v260 = 0;
                                    v471 = 0;
                                    if ( *((_WORD *)v475 + 47) )
                                    {
                                      v261 = v462;
                                      do
                                      {
                                        v254 = "BINARY";
                                        if ( *(char **)(*((_QWORD *)v244 + 8) + 8LL * v260) != "BINARY" )
                                        {
                                          if ( !v259 )
                                          {
                                            v471 = *((_DWORD *)v8 + 17) - 1;
                                            *((_DWORD *)v8 + 17) = v471;
                                          }
                                          sqlite3VdbeAddOp3(v10, 94, v261 + v474, v260, 3);
                                          sqlite3VdbeAddOp3(v10, 52, 3, v471, v260 + IndexKey);
                                          v259 = v471;
                                          v258 = 0;
                                        }
                                        ++v260;
                                      }
                                      while ( v260 < *((unsigned __int16 *)v244 + 47) );
                                      v248 = v485;
                                      if ( v259 )
                                      {
                                        v262 = sqlite3VdbeAddOp3(v10, 9, 0, 0, 0);
                                        sqlite3VdbeResolveLabel(v10, v471);
                                        sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"row ", 0);
                                        sqlite3VdbeAddOp3(v10, 111, 7, 3, 3);
                                        sqlite3VdbeAddOp4(v10, 117, 0, 4, 0, (__int64)" values differ from index ", 0);
                                        sqlite3VdbeAddOp3(v10, 9, 0, v469 - 1, 0);
                                        v265 = sqlite3VdbeGetOp(v10, v262, v263, v264);
                                        v258 = 0;
                                        v244 = v475;
                                        *(_DWORD *)(v265 + 8) = *(_DWORD *)(v10 + 144);
                                      }
                                    }
                                    if ( v244[98] )
                                    {
                                      v266 = 0;
                                      v267 = *((_DWORD *)v8 + 17) - 1;
                                      *((_DWORD *)v8 + 17) = v267;
                                      v458 = v267;
                                      if ( *((_WORD *)v244 + 47) )
                                      {
                                        v268 = v267;
                                        do
                                        {
                                          v269 = *((_QWORD *)v244 + 1);
                                          if ( *(__int16 *)(v269 + 2LL * v266) < 0
                                            || (v248[1][24 * *(__int16 *)(v269 + 2LL * v266) + 8] & 0xF) == 0 )
                                          {
                                            sqlite3VdbeAddOp3(v10, 50, v266 + IndexKey, v268, 0);
                                          }
                                          ++v266;
                                        }
                                        while ( v266 < *((unsigned __int16 *)v244 + 47) );
                                        v8 = v487;
                                      }
                                      v270 = v458;
                                      v271 = sqlite3VdbeAddOp3(v10, 39, v462 + v474, 0, 0);
                                      sqlite3VdbeAddOp3(v10, 9, 0, v458, 0);
                                      v274 = sqlite3VdbeGetOp(v10, v271, v272, v273);
                                      v244 = v475;
                                      v275 = v462 + v474;
                                      *(_DWORD *)(v274 + 8) = *(_DWORD *)(v10 + 144);
                                      sqlite3VdbeAddOp4Int(
                                        v10,
                                        41,
                                        v275,
                                        v270,
                                        IndexKey,
                                        *((unsigned __int16 *)v244 + 47));
                                      sqlite3VdbeAddOp4(v10, 117, 0, 3, 0, (__int64)"non-unique entry in index ", 0);
                                      sqlite3VdbeAddOp3(v10, 9, 0, v469, 0);
                                      sqlite3VdbeResolveLabel(v10, v270);
                                    }
                                    v276 = sqlite3VdbeGetOp(v10, v481, v254, v258);
                                    v277 = (unsigned int)v461;
                                    *(_DWORD *)(v276 + 8) = *(_DWORD *)(v10 + 144);
                                    sqlite3ResolvePartIdxLabel(v8, v277);
                                    v245 = v462;
                                    v247 = IndexKey;
                                    v246 = (__int64)v468;
                                  }
                                  v244 = (char *)*((_QWORD *)v244 + 5);
                                  ++v245;
                                  v475 = v244;
                                  v462 = v245;
                                }
                                while ( v244 );
                                v5 = v476;
                              }
                            }
                            v278 = v470;
                            sqlite3VdbeAddOp3(v10, 39, v473, v470, 0);
                            v281 = sqlite3VdbeGetOp(v10, (unsigned int)(v278 - 1), v279, v280);
                            v163 = 0;
                            *(_DWORD *)(v281 + 8) = *(_DWORD *)(v10 + 144);
                            if ( v482 )
                              sqlite3ReleaseTempRange(v8, v460, *(unsigned __int16 *)(v482 + 94));
                            v180 = (const char **)v465;
LABEL_385:
                            v179 = *(_QWORD *)Index;
                            Index = v179;
                            if ( !v179 )
                            {
                              v178 = v472;
                              break;
                            }
                          }
                        }
                        v282 = *(_QWORD **)(v178 + 16);
                        if ( v282 )
                        {
                          v283 = v465;
                          v284 = v480;
                          do
                          {
                            v285 = v282[2];
                            if ( (!v283 || v283 == v285) && *(_BYTE *)(v285 + 63) == 1 )
                            {
                              if ( *(__int16 *)(v285 + 54) > (__int16)v163
                                || (ElementWithHash = findElementWithHash(v5 + 552, **(_QWORD **)(v285 + 72), 0),
                                    LOWORD(v163) = 0,
                                    *(_QWORD *)(ElementWithHash + 16)) )
                              {
                                sqlite3ViewGetColumnNames(v8, v285);
                                v287 = *(_QWORD *)(v285 + 80);
                                LOWORD(v163) = 0;
                                if ( v287 )
                                {
                                  v288 = *(__int64 **)(v287 + 16);
                                  if ( v288 )
                                  {
                                    v289 = *v288;
                                    if ( v289 )
                                    {
                                      if ( *(int *)v289 >= 4 && *(_QWORD *)(v289 + 192) )
                                      {
                                        sqlite3VdbeAddOp3(v10, 174, v284, 3, (_DWORD)v466);
                                        ++*(_DWORD *)(v285 + 44);
                                        sqlite3VdbeAppendP4(v10, v285, 4294967280LL);
                                        v290 = sqlite3VdbeAddOp3(v10, 50, 3, 0, 0);
                                        integrityCheckResultRow(v10);
                                        v293 = sqlite3VdbeGetOp(v10, v290, v291, v292);
                                        LOWORD(v163) = 0;
                                        *(_DWORD *)(v293 + 8) = *(_DWORD *)(v10 + 144);
                                      }
                                    }
                                  }
                                }
                              }
                              v283 = v465;
                            }
                            v282 = (_QWORD *)*v282;
                          }
                          while ( v282 );
                        }
                        LODWORD(v13) = v478;
                      }
                    }
                    v142 = v480;
                  }
                  v480 = ++v142;
                  if ( (signed int)v142 >= *(_DWORD *)(v5 + 40) )
                    goto LABEL_405;
                }
              }
              if ( !v15 )
                goto LABEL_734;
              Index = sqlite3FindIndex(v5, v15, v465);
              v305 = Index;
              if ( !Index )
              {
                v306 = sqlite3LocateTable(v8, 2, v15, v465);
                if ( !v306 )
                  goto LABEL_734;
                if ( *(char *)(v306 + 48) >= 0 )
                  goto LABEL_734;
                Index = sqlite3PrimaryKeyIndex(v306);
                v305 = Index;
                if ( !Index )
                  goto LABEL_734;
              }
              v307 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v305 + 48));
              v308 = v468;
              v310 = *(unsigned __int16 *)((-(__int64)(v468[2] != 0) & 2) + v309 + 94);
              v311 = v468[2] != 0 ? 3 : 0;
              LODWORD(v470) = (unsigned __int16)v310;
              *((_DWORD *)v8 + 14) = v311 + 3;
              v484 = *(_QWORD *)(v309 + 24);
              sqlite3CodeVerifySchema(v8, v307);
              if ( !v310 )
                goto LABEL_734;
              v312 = 0;
              do
              {
                v313 = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v312);
                if ( (v313 & 0x8000u) == 0LL )
                  v314 = *(_QWORD *)(*(_QWORD *)(v484 + 8) + 24 * v313);
                else
                  v314 = 0;
                LODWORD(v445) = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v312);
                sqlite3VdbeMultiLoad(v10, 1, "iisX", v312, v445, v314, v453, v455, v456, v457);
                if ( v308[2] )
                {
                  LODWORD(v452) = v312 < *(unsigned __int16 *)(Index + 94);
                  sqlite3VdbeMultiLoad(
                    v10,
                    4,
                    "isiX",
                    *(unsigned __int8 *)(*(_QWORD *)(Index + 56) + v312),
                    *(_QWORD *)(*(_QWORD *)(Index + 64) + 8LL * v312),
                    v452,
                    v453,
                    v455,
                    v456,
                    v457);
                }
                sqlite3VdbeAddOp3(v10, 84, 1, *((_DWORD *)v8 + 14), 0);
                ++v312;
              }
              while ( (int)v312 < (int)v470 );
LABEL_676:
              v5 = v476;
              goto LABEL_677;
            }
            v319 = 0;
            if ( v15 )
            {
              LODWORD(v466) = sqlite3Strlen30(v15);
              v321 = v320;
              v322 = sqlite3JournalModename(0, (unsigned int)v466);
              while ( 1 )
              {
                if ( !v322 )
                  goto LABEL_439;
                v324 = sqlite3_strnicmp(v15, v322, v323);
                v319 = 0;
                if ( !v324 )
                  break;
                v322 = sqlite3JournalModename((unsigned int)++v321, v325);
                v323 = (unsigned int)v466;
              }
              if ( v321 != 2 )
              {
                if ( v321 != -1 )
                {
LABEL_442:
                  v326 = *(_DWORD *)(v5 + 40) - 1;
                  if ( v326 >= 0 )
                  {
                    v327 = v479;
                    do
                    {
                      if ( *(_QWORD *)(32LL * (unsigned int)v326 + *(_QWORD *)(v5 + 32) + 8) != v319
                        && (v326 == (_DWORD)v13 || *(_DWORD *)(v327 + 8) == (_DWORD)v319) )
                      {
                        sqlite3VdbeUsesBtree(v10, (unsigned int)v326);
                        sqlite3VdbeAddOp3(v328, 4, v326, 1, v321);
                        v319 = 0;
                      }
                      --v326;
                    }
                    while ( v326 >= 0 );
                    v15 = v483;
                  }
                  v448 = v319;
                  v329 = 1;
LABEL_499:
                  sqlite3VdbeAddOp3(v10, 84, v329, 1, v448);
                  goto LABEL_734;
                }
LABEL_440:
                if ( *(_DWORD *)(v479 + 8) == (_DWORD)v319 )
                {
                  LODWORD(v13) = v319;
                  *(_DWORD *)(v479 + 8) = 1;
                }
                goto LABEL_442;
              }
              if ( (*(_DWORD *)(v5 + 48) & 0x10000000) == 0 )
                goto LABEL_442;
            }
LABEL_439:
            v321 = -1;
            goto LABEL_440;
          }
          if ( (unsigned __int8)v23 <= 0x22u )
          {
            if ( (_BYTE)v23 == 34 )
            {
              Index = 0;
              if ( v15 && !(unsigned int)sqlite3DecOrHexToI64((char *)v15) )
                sqlite3_soft_heap_limit64(Index);
              v136 = sqlite3_soft_heap_limit64(-1);
              goto LABEL_207;
            }
            if ( (unsigned __int8)v23 > 0x1Du )
            {
              v374 = v23 - 30;
              if ( v374 )
              {
                v375 = v374 - 1;
                if ( v375 )
                {
                  v376 = v375 - 1;
                  if ( v376 )
                  {
                    if ( v376 == 1 )
                    {
                      sqlite3_db_release_memory(v5);
                      goto LABEL_734;
                    }
                    goto LABEL_694;
                  }
                  v377 = -1;
                  v378 = 0;
                  v379 = *(__int64 *)((char *)v466 + v470 + 8);
                  if ( v15 )
                  {
                    if ( (unsigned int)sqlite3_stricmp(v15, "fast") )
                      v377 = (unsigned __int8)sqlite3GetBoolean(v15, 0);
                    else
                      v377 = 2;
                  }
                  if ( !*(_DWORD *)(v479 + 8) && v377 >= 0 && *(int *)(v5 + 40) > 0 )
                  {
                    do
                      sqlite3BtreeSecureDelete(
                        *(_QWORD *)(32LL * v378++ + *(_QWORD *)(v5 + 32) + 8),
                        (unsigned int)v377);
                    while ( v378 < *(_DWORD *)(v5 + 40) );
                  }
                  AutoVacuum = sqlite3BtreeSecureDelete(v379, (unsigned int)v377);
                  goto LABEL_732;
                }
                for ( i1 = 0; i1 != 74; ++i1 )
                  sqlite3VdbeMultiLoad(v10, 1, "s", (&off_1800B1290)[3 * i1], v445, v449, v453, v455, v456, v457);
                goto LABEL_677;
              }
              v381 = *(__int64 *)((char *)v466 + v470 + 8);
              if ( v15 )
              {
                v458 = 0;
                sqlite3GetInt32(v15, &v458);
                v383 = v458;
                *(_DWORD *)(v5 + 116) = v458;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v381, v383, 0, 0) == 7 )
                  sqlite3OomFault(v5);
                goto LABEL_734;
              }
              if ( v381 )
                v382 = *(_DWORD *)(*(_QWORD *)(v381 + 8) + 52LL);
              else
                v382 = 0;
              v27 = v382;
              goto LABEL_733;
            }
            if ( (_BYTE)v23 != 29 )
            {
              v330 = v23 - 23;
              if ( !v330 )
              {
                v350 = *(__int64 **)(*(__int64 *)((char *)v466 + v470 + 8) + 8);
                v351 = -2;
                Index = -2;
                v352 = *v350;
                if ( v15 )
                {
                  sqlite3DecOrHexToI64((char *)v15);
                  v351 = -1;
                }
                if ( v351 >= -1 )
                {
                  v353 = *(_QWORD *)(v352 + 328);
                  *(_QWORD *)(v352 + 208) = v351;
                  if ( v353 )
                    *(_QWORD *)(v353 + 32) = v351;
                }
                v27 = *(_QWORD *)(v352 + 208);
                goto LABEL_733;
              }
              v331 = v330 - 2;
              if ( v331 )
              {
                v332 = v331 - 1;
                if ( !v332 )
                {
                  Index = 0;
                  sqlite3CodeVerifySchema(v8, (unsigned int)v13);
                  v341 = v486;
                  v342 = *((_DWORD *)v8 + 14) + 1;
                  *((_DWORD *)v8 + 14) = v342;
                  if ( *((_BYTE *)qword_1800B4ED0 + *v341) == 112 )
                  {
                    sqlite3VdbeAddOp3(v10, 178, v13, v342, 0);
                  }
                  else
                  {
                    if ( !v15 || (unsigned int)sqlite3DecOrHexToI64((char *)v15) || (v343 = Index, Index < 0) )
                    {
                      v343 = 0;
                    }
                    else if ( Index > 4294967294LL )
                    {
                      v343 = -2;
                    }
                    sqlite3VdbeAddOp3(v10, 179, v13, v342, v343);
                  }
                  v329 = v342;
                  v448 = 0;
                  goto LABEL_499;
                }
                v333 = v332 - 1;
                if ( v333 )
                {
                  if ( v333 == 1 )
                  {
                    *((_DWORD *)v8 + 14) = 1;
                    for ( i2 = *(_QWORD **)(v5 + 560); i2; i2 = (_QWORD *)*i2 )
                      sqlite3VdbeMultiLoad(v10, 1, "s", *(_QWORD *)(i2[2] + 8LL), v445, v449, v453, v455, v456, v457);
                    goto LABEL_734;
                  }
                  goto LABEL_694;
                }
                v476 = 0;
                if ( v15 )
                {
                  sqlite3DecOrHexToI64((char *)v15);
                  v335 = v476;
                  if ( v476 < 0 )
                  {
                    v335 = qword_1800D0998;
                    v476 = qword_1800D0998;
                  }
                  v336 = v479;
                  if ( *(_DWORD *)(v479 + 8) )
                  {
                    v339 = *(_DWORD *)(v5 + 40);
                    while ( 1 )
                    {
                      v458 = --v339;
                      if ( v339 < 0 )
                        break;
                      v340 = *(_QWORD *)(32LL * (unsigned int)v339 + *(_QWORD *)(v5 + 32) + 8);
                      Index = v340;
                      if ( v340 && v339 == (_DWORD)v13 )
                      {
                        v13 = *(_QWORD *)(v340 + 8);
                        sqlite3BtreeEnter(v340);
                        *(_QWORD *)(*(_QWORD *)v13 + 160LL) = v335;
                        pagerFixMaplimit();
                        sqlite3BtreeLeave(Index);
                        v339 = v458;
                        v335 = v476;
                        LODWORD(v13) = v478;
                      }
                    }
                  }
                  else
                  {
                    v337 = *(_DWORD *)(v5 + 40);
                    *(_QWORD *)(v5 + 64) = v335;
                    while ( 1 )
                    {
                      v458 = --v337;
                      if ( v337 < 0 )
                        break;
                      v338 = *(_QWORD *)(32LL * (unsigned int)v337 + *(_QWORD *)(v5 + 32) + 8);
                      Index = v338;
                      if ( v338 && (v337 == (_DWORD)v13 || !*(_DWORD *)(v336 + 8)) )
                      {
                        v13 = *(_QWORD *)(v338 + 8);
                        sqlite3BtreeEnter(v338);
                        *(_QWORD *)(*(_QWORD *)v13 + 160LL) = v335;
                        pagerFixMaplimit();
                        sqlite3BtreeLeave(Index);
                        v336 = v479;
                        v337 = v458;
                        v335 = v476;
                        LODWORD(v13) = v478;
                      }
                    }
                  }
                }
                v476 = -1;
                v18 = sqlite3_file_control(v5, v465, 18, &v476);
                if ( v18 )
                {
                  if ( v18 == 12 )
                    goto LABEL_734;
LABEL_18:
                  ++*((_DWORD *)v8 + 12);
                  *((_DWORD *)v8 + 6) = v18;
                  goto LABEL_734;
                }
                v27 = v476;
LABEL_733:
                returnSingleInt(v10, v27);
                goto LABEL_734;
              }
              v344 = "exclusive";
              if ( !v15 )
                goto LABEL_504;
              if ( !(unsigned int)sqlite3StrICmp(v15, "exclusive") )
              {
                v345 = 1;
                goto LABEL_505;
              }
              v346 = sqlite3StrICmp(v15, "normal");
              v345 = 0;
              if ( v346 )
LABEL_504:
                v345 = -1;
LABEL_505:
              if ( !*(_DWORD *)(v479 + 8) )
              {
                if ( v345 == -1 )
                {
                  v347 = *(unsigned __int8 *)(v5 + 105);
LABEL_512:
                  if ( v347 != 1 )
                    v344 = "normal";
                  v126 = v344;
                  goto LABEL_515;
                }
                for ( i3 = 2; i3 < *(_DWORD *)(v5 + 40); i3 = v349 + 1 )
                  sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(32LL * i3 + *(_QWORD *)(v5 + 32) + 8) + 8LL));
                *(_BYTE *)(v5 + 105) = v345;
              }
              v347 = sqlite3PagerLockingMode(**(_QWORD **)(*(__int64 *)((char *)v466 + v470 + 8) + 8));
              goto LABEL_512;
            }
            if ( v15 )
            {
              v458 = 0;
              sqlite3GetInt32(v15, &v458);
              IndexKey = v458;
              if ( (v458 & 2) == 0 )
                goto LABEL_734;
              v461 = 0;
              v354 = 0;
              LODWORD(v475) = 0;
              if ( (v458 & 0x10) == 0 )
              {
                v474 = 0;
                goto LABEL_528;
              }
            }
            else
            {
              v461 = 0;
              IndexKey = 65534;
              v354 = 0;
              LODWORD(v475) = 0;
            }
            v474 = (unsigned int)(*(_DWORD *)(v5 + 744) - 1) > 0x7CE ? 0x7D0 : 0;
LABEL_528:
            v463 = *((_DWORD *)v8 + 13);
            *((_DWORD *)v8 + 13) = v463 + 1;
            if ( v465 )
            {
              v355 = v13;
              v460 = v13;
            }
            else
            {
              v355 = *(_DWORD *)(v5 + 40) - 1;
              v460 = v355;
              if ( (int)v13 > v355 )
              {
LABEL_559:
                sqlite3VdbeAddOp3(v10, 166, 0, 0, 0);
                if ( !*(_BYTE *)(v5 + 103) && v474 && v354 > 100 )
                {
                  v368 = (int)(100 * v474) / v354;
                  v369 = (unsigned int)v368;
                  if ( v368 < 100 )
                    v369 = 100;
                  v370 = sqlite3VdbeGetOp(v10, 0, v367, v369);
                  v373 = *(_DWORD *)(v10 + 144);
                  if ( v373 > 0 )
                  {
                    do
                    {
                      if ( *(_BYTE *)(v370 + 24 * v371) == 0x94 )
                        *(_DWORD *)(v370 + 24 * v371 + 8) = v372;
                      v371 = (unsigned int)(v371 + 1);
                    }
                    while ( (int)v371 < v373 );
                  }
                }
                goto LABEL_734;
              }
            }
            do
            {
              if ( (_DWORD)v13 != 1 )
              {
                sqlite3CodeVerifySchema(v8, (unsigned int)v13);
                for ( i4 = *(_QWORD *)(*(_QWORD *)(32LL * (int)v13 + *(_QWORD *)(v5 + 32) + 24) + 16LL);
                      ;
                      i4 = *(_QWORD *)Index )
                {
                  Index = i4;
                  if ( !i4 )
                    break;
                  v357 = *(_QWORD *)(i4 + 16);
                  v472 = v357;
                  if ( !*(_BYTE *)(v357 + 63) && (unsigned int)sqlite3_strnicmp(*(_QWORD *)v357, "sqlite_", 7) )
                  {
                    v358 = v472;
                    v359 = 0;
                    v458 = 0;
                    v360 = *(_QWORD *)(v472 + 16);
                    v361 = *(unsigned __int16 *)(v472 + 58);
                    v469 = v361;
                    if ( v360 )
                    {
                      do
                      {
                        v359 = (unsigned int)(v359 + 1);
                        if ( *(char *)(v360 + 100) >= 0 )
                          v361 = -1;
                        v360 = *(_QWORD *)(v360 + 40);
                      }
                      while ( v360 );
                      v458 = v359;
                      v469 = v361;
                    }
                    if ( (*(_DWORD *)(v472 + 48) & 0x100) != 0
                      || (IndexKey & 0x10000) != 0
                      || *(_QWORD *)(v472 + 16) && (v361 & 0x8000u) != 0 )
                    {
                      if ( ++v461 == 2 )
                      {
                        sqlite3BeginWriteOperation(v8, 0, (unsigned int)v13, v359);
                        v358 = v472;
                        LODWORD(v359) = v458;
                      }
                      LODWORD(v475) = v359 + (_DWORD)v475 + 1;
                      sqlite3OpenTable((_DWORD)v8, v463, v13, v358, 112);
                      if ( (v469 & 0x8000u) != 0 )
                      {
                        v458 = IndexKey & 1;
                        sqlite3VdbeAddOp3(v10, 36, v463, *(_DWORD *)(v10 + 144) + v458 + 2, 0);
                      }
                      else
                      {
                        if ( (__int16)v469 < 33 )
                          v362 = -1;
                        else
                          v362 = (__int16)v469 - 33;
                        v458 = IndexKey & 1;
                        sqlite3VdbeAddOp4Int(v10, 33, v463, *(_DWORD *)(v10 + 144) + v458 + 2, v362, (__int16)v469 + 33);
                      }
                      v363 = sqlite3MPrintf(
                               v5,
                               "ANALYZE \"%w\".\"%w\"",
                               *(_QWORD *)(32LL * (int)v13 + *(_QWORD *)(v5 + 32)),
                               *(_QWORD *)v472);
                      if ( v458 )
                      {
                        TempReg = sqlite3GetTempReg(v8, v363);
                        sqlite3VdbeAddOp4(v10, 117, 0, TempReg, v366, v365, -6);
                        sqlite3VdbeAddOp3(v10, 84, TempReg, 1, 0);
                        LODWORD(v13) = v478;
                      }
                      else
                      {
                        sqlite3VdbeAddOp4(v10, 148, v474 != 0 ? 2 : 0, v474, 0, v363, -6);
                      }
                    }
                  }
                }
                v355 = v460;
              }
              LODWORD(v13) = v13 + 1;
              v478 = v13;
            }
            while ( (int)v13 <= v355 );
            v15 = v483;
            v354 = (int)v475;
            goto LABEL_559;
          }
          if ( (unsigned __int8)v23 > 0x28u )
          {
            v432 = v23 - 41;
            if ( !v432 )
            {
              if ( v15 )
              {
                v458 = 0;
                sqlite3GetInt32(v15, &v458);
                sqlite3_wal_autocheckpoint(v5, v458);
              }
              if ( *(__int64 (__fastcall **)())(v5 + 360) == sqlite3WalDefaultHook )
                AutoVacuum = *(_DWORD *)(v5 + 368);
              else
                AutoVacuum = 0;
              goto LABEL_732;
            }
            v433 = v432 - 1;
            if ( !v433 )
            {
              v442 = 0;
              v443 = 12;
              if ( *(_QWORD *)v479 )
                v443 = v13;
              LODWORD(v466) = v443;
              if ( v15 )
              {
                if ( (unsigned int)sqlite3StrICmp(v15, "full") )
                {
                  if ( (unsigned int)sqlite3StrICmp(v15, "restart") )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v15, "truncate") )
                      v442 = 3;
                  }
                  else
                  {
                    v442 = 2;
                  }
                }
                else
                {
                  v442 = 1;
                }
              }
              v444 = (int)v466;
              *((_DWORD *)v8 + 14) = 3;
              sqlite3VdbeAddOp3(v10, 3, v444, v442, 1);
              sqlite3VdbeAddOp3(v10, 84, 1, 3, 0);
              goto LABEL_734;
            }
            v434 = v433 - 1;
            if ( !v434 )
            {
              if ( v15 && !(unsigned int)sqlite3_strnicmp(v15, "see-", 4) )
                dword_1800D0864 = strcmp_0((const char *)(v15 + 4), "7bb07b8d471d642e") == 0;
              goto LABEL_734;
            }
            if ( v434 != 1 )
              goto LABEL_694;
            if ( !v15 )
              goto LABEL_734;
            v435 = *(_QWORD *)(v22 + 16);
            if ( v435 - 2 <= 1 )
            {
              v438 = 0;
              v439 = 0;
              do
              {
                v440 = *(unsigned __int8 *)(v438 + v15);
                if ( (*((_BYTE *)&qword_1800B4FF0 + v440) & 8) == 0 )
                  break;
                v439 = ((v440 - 7 * (((char)v440 >> 6) & 1)) & 0xF) + 16 * v439;
                if ( (v438 & 1) != 0 )
                  *((_BYTE *)v490 + ((unsigned __int64)v438 >> 1)) = v439;
                ++v438;
              }
              while ( (int)v438 < 80 );
              v5 = v476;
              v436 = v490;
              v437 = v438 >> 1;
            }
            else
            {
              v436 = (_QWORD *)v15;
              v437 = v435 >= 4 ? -1 : sqlite3Strlen30(v15);
            }
            v441 = (*(_BYTE *)(v22 + 16) & 1) != 0
                 ? sqlite3_rekey_v2(v5, v465, v436, v437)
                 : sqlite3_key_v2(v5, v465, v436, v437);
            if ( v441 || !v437 )
              goto LABEL_734;
            sqlite3VdbeSetNumCols(v10, 1);
            sqlite3VdbeSetColName(v10, 0, 0, "ok", 0);
            v126 = "ok";
            goto LABEL_515;
          }
          if ( (_BYTE)v23 == 40 )
          {
            Index = 0;
            if ( v15 && !(unsigned int)sqlite3DecOrHexToI64((char *)v15) )
              sqlite3_limit(v5, 11, Index & 0x7FFFFFFF);
            AutoVacuum = sqlite3_limit(v5, 11, -1);
            goto LABEL_732;
          }
          v384 = v23 - 35;
          if ( v384 )
          {
            v385 = v384 - 1;
            if ( v385 )
            {
              v386 = v385 - 1;
              if ( !v386 )
              {
                v391 = v465;
                v392 = v465;
                *((_DWORD *)v8 + 14) = 6;
                sqlite3CodeVerifyNamedSchema(v8, v392);
                v393 = 0;
                v463 = 0;
                if ( *(int *)(v5 + 40) <= 0 )
                  goto LABEL_734;
                while ( 1 )
                {
                  v394 = v393;
                  if ( !v391 || !(unsigned int)sqlite3_stricmp(v391, *(_QWORD *)(32LL * v393 + *(_QWORD *)(v5 + 32))) )
                  {
                    v395 = *(_QWORD *)(32 * v394 + *(_QWORD *)(v5 + 32) + 24);
                    v396 = *(_DWORD *)(v395 + 12);
                    v397 = v395 + 8;
                    if ( v396 )
                    {
                      v398 = v463;
                      do
                      {
                        for ( i5 = *(_QWORD **)(v397 + 8); ; i5 = (_QWORD *)*i5 )
                        {
                          if ( !i5 )
                            goto LABEL_634;
                          v400 = i5[2];
                          if ( !*(_WORD *)(v400 + 54) )
                            break;
                        }
                        --v396;
                        v401 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v400);
                        v484 = v401;
                        if ( v401 )
                        {
                          Index = 0;
                          sqlite3LockAndPrepare(v5, v401, -1, 0, 0, (__int64)&Index, 0);
                          sqlite3_finalize(Index);
                          sqlite3DbFree(v5, v484);
                        }
                        if ( *(_BYTE *)(v5 + 103) )
                        {
                          sqlite3ErrorMsg(*(_QWORD *)(v5 + 352), "out of memory");
                          *(_DWORD *)(*(_QWORD *)(v5 + 352) + 24LL) = 7;
                        }
                        v397 = *(_QWORD *)(32 * v398 + *(_QWORD *)(v5 + 32) + 24) + 8LL;
                      }
                      while ( v396 );
LABEL_634:
                      v391 = v465;
                    }
                    v402 = *(_QWORD *)(v397 + 8);
                    Index = v402;
                    if ( v402 )
                    {
                      do
                      {
                        v403 = *(_QWORD **)(v402 + 16);
                        if ( !v15 || !(unsigned int)sqlite3_stricmp(v15, *v403) )
                        {
                          if ( *((_BYTE *)v403 + 63) == 2 )
                          {
                            v404 = "view";
                          }
                          else if ( *((_BYTE *)v403 + 63) == 1 )
                          {
                            v404 = "virtual";
                          }
                          else
                          {
                            v404 = "shadow";
                            if ( (v403[6] & 0x1000) == 0 )
                              v404 = "table";
                          }
                          v472 = (__int64)v404;
                          v405 = *((_DWORD *)v403 + 12);
                          LODWORD(v470) = (v405 >> 7) & 1;
                          v406 = (const char *)*v403;
                          LODWORD(v466) = HIWORD(v405) & 1;
                          v484 = (__int64)v406;
                          if ( (unsigned int)sqlite3_strnicmp(v406, "sqlite_", 7) )
                          {
                            v408 = (const char *)*v403;
                          }
                          else if ( (unsigned int)sqlite3StrICmp(v484 + 7, "master") )
                          {
                            if ( !(unsigned int)sqlite3StrICmp(v407 + 7, "temp_master") )
                              v408 = "sqlite_temp_schema";
                          }
                          else
                          {
                            v408 = "sqlite_schema";
                          }
                          LODWORD(v455) = v470;
                          sqlite3VdbeMultiLoad(
                            v10,
                            1,
                            "sssiii",
                            *(_QWORD *)(32LL * v463 + *(_QWORD *)(v5 + 32)),
                            v408,
                            v472,
                            *((__int16 *)v403 + 27),
                            v455,
                            (_DWORD)v466,
                            v457);
                        }
                        v402 = *(_QWORD *)Index;
                        Index = v402;
                      }
                      while ( v402 );
                      v391 = v465;
                    }
                  }
                  v393 = v463 + 1;
                  v463 = v393;
                  if ( v393 >= *(_DWORD *)(v5 + 40) )
                    goto LABEL_734;
                }
              }
              v387 = v386 - 1;
              if ( !v387 )
              {
                if ( v15 )
                {
                  changeTempStorage(v8, v15);
                  goto LABEL_734;
                }
                v27 = *(unsigned __int8 *)(v5 + 102);
                goto LABEL_733;
              }
              if ( v387 != 1 )
                goto LABEL_694;
              v388 = sqlite3MutexAlloc(11);
              sqlite3_mutex_enter(v388);
              if ( !v15 )
              {
                v59 = sqlite3_temp_directory;
                goto LABEL_606;
              }
              if ( !*(_BYTE *)v15
                || (v389 = *(_QWORD *)v5,
                    v458 = 0,
                    !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, unsigned int *))(v389 + 56))(
                       v389,
                       v15,
                       1,
                       &v458))
                && v458 )
              {
                if ( *(_BYTE *)(v5 + 102) <= 1u )
                  invalidateTempStorage(v8);
                sqlite3_free(sqlite3_temp_directory);
                if ( *(_BYTE *)v15 )
                  sqlite3_temp_directory = sqlite3_mprintf("%s", (const char *)v15);
                else
                  sqlite3_temp_directory = 0;
                goto LABEL_611;
              }
LABEL_610:
              sqlite3ErrorMsg(v8, "not a writable directory");
              goto LABEL_611;
            }
            if ( !v15 )
              goto LABEL_734;
            sqlite3CodeVerifyNamedSchema(v8, v465);
            v409 = sqlite3LocateTable(v8, 2, v15, v465);
            Index = v409;
            v410 = v409;
            if ( !v409 )
              goto LABEL_734;
            v484 = sqlite3PrimaryKeyIndex(v409);
            *((_DWORD *)v8 + 14) = 7;
            sqlite3ViewGetColumnNames(v8, v410);
            LOWORD(v412) = *(_WORD *)(v410 + 54);
            if ( (__int16)v412 <= 0 )
              goto LABEL_734;
            v413 = *(_QWORD *)(v410 + 8);
            v414 = 0;
            v415 = 0;
            v416 = Index;
            v461 = 0;
            v458 = 0;
            do
            {
              v417 = *(_WORD *)(v413 + 18);
              if ( (v417 & 0x62) == 0 || v468[2] )
              {
                if ( (v417 & 1) != 0 )
                {
                  v418 = 1;
                  if ( v484 )
                  {
                    v411 = (unsigned int)(__int16)v412;
                    if ( (int)v411 >= 1 )
                    {
                      do
                      {
                        if ( *(__int16 *)(*(_QWORD *)(v484 + 8) + 2LL * v418 - 2) == (_DWORD)v415 )
                          break;
                        ++v418;
                      }
                      while ( v418 <= (int)v411 );
                    }
                  }
                }
                else
                {
                  v418 = 0;
                }
                v419 = sqlite3ColumnExpr(v416, v413, v411, v415);
                if ( v421 < 2 && v419 )
                  Index = *(_QWORD *)(v419 + 8);
                else
                  Index = v420;
                v422 = sqlite3ColumnType(v413, &Src);
                v426 = (unsigned int)(v425 - v461);
                v427 = "issisii";
                if ( !v468[2] )
                  v427 = "issisi";
                sqlite3VdbeMultiLoad(v10, 1, v427, v426, *(_QWORD *)v413, v422, v423, Index, v418, v424);
                LODWORD(v415) = v458;
                v414 = v461;
              }
              else
              {
                v461 = ++v414;
              }
              v412 = *(__int16 *)(v416 + 54);
              v415 = (unsigned int)(v415 + 1);
              v413 += 24;
              v458 = v415;
            }
            while ( (int)v415 < v412 );
            goto LABEL_676;
          }
          if ( !v15 )
          {
            v27 = *((unsigned __int8 *)v466 + v470 + 16) - 1LL;
            goto LABEL_733;
          }
          if ( !*(_BYTE *)(v5 + 101) )
          {
            sqlite3ErrorMsg(v8, "Safety level may not be changed inside a transaction");
            goto LABEL_734;
          }
          if ( (_DWORD)v13 != 1 )
          {
            LOBYTE(v20) = 1;
            SafetyLevel = getSafetyLevel(v15, 0, v20);
            v429 = v466;
            v430 = v470;
            v431 = (SafetyLevel + 1) & 7;
            if ( !v431 )
              LOBYTE(v431) = 1;
            *((_BYTE *)v466 + v470 + 16) = v431;
            *((_BYTE *)v429 + v430 + 17) = 1;
            goto LABEL_89;
          }
LABEL_734:
          sqlite3DbFree(v5, v486);
          return sqlite3DbFree(v5, v15);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180093bb0  push    rbp
0x180093bb2  push    rbx
0x180093bb3  push    rsi
0x180093bb4  push    rdi
0x180093bb5  push    r12
0x180093bb7  push    r13
0x180093bb9  push    r14
0x180093bbb  push    r15
0x180093bbd  lea     rbp, [rsp-78h]
0x180093bc2  sub     rsp, 178h
0x180093bc9  mov     rax, cs:__security_cookie
0x180093bd0  xor     rax, rsp
0x180093bd3  mov     [rbp+0B0h+var_48], rax
0x180093bd7  mov     r14, [rcx]
0x180093bda  xorps   xmm0, xmm0
0x180093bdd  mov     rbx, r8
0x180093be0  mov     [rbp+0B0h+var_E0], r14
0x180093be4  xor     esi, esi
0x180093be6  mov     [rbp+0B0h+var_D0], rbx
0x180093bea  mov     [rbp+0B0h+var_F8], rsi
0x180093bee  mov     r15, r9
0x180093bf1  movups  [rbp+0B0h+var_90], xmm0
0x180093bf5  mov     [rbp+0B0h+var_C0], r9
0x180093bf9  mov     r12, rcx
0x180093bfc  movups  [rbp+0B0h+var_80], xmm0
0x180093c00  mov     [rsp+1B0h+var_138], rdx
0x180093c05  mov     [rbp+0B0h+var_98], rcx
0x180093c09  call    sqlite3GetVdbe
0x180093c0e  mov     [rbp+0B0h+var_B0], rax
0x180093c12  mov     rdi, rax
0x180093c15  test    rax, rax
0x180093c18  jz      loc_180097659
0x180093c1e  mov     dword ptr [rsp+1B0h+var_190], esi
0x180093c22  mov     edx, 0A6h
0x180093c27  mov     esi, 1
0x180093c2c  mov     rcx, rax
0x180093c2f  mov     r9d, esi
0x180093c32  mov     r8d, esi
0x180093c35  call    sqlite3VdbeAddOp3
0x180093c3a  mov     rdx, [rsp+1B0h+var_138]
0x180093c3f  lea     r13d, [rsi+1]
0x180093c43  lea     r9, [rbp+0B0h+var_F8]
0x180093c47  mov     [r12+38h], r13d
0x180093c4c  mov     r8, rbx
0x180093c4f  mov     rcx, r12
0x180093c52  call    sqlite3TwoPartName
0x180093c57  movsxd  rbx, eax
0x180093c5a  mov     [rbp+0B0h+var_D4], ebx
0x180093c5d  test    eax, eax
0x180093c5f  js      loc_180097659
0x180093c65  mov     rax, [r14+20h]
0x180093c69  mov     [rbp+0B0h+var_108], rax
0x180093c6d  cmp     ebx, esi
0x180093c6f  jnz     short loc_180093C81
0x180093c71  mov     rcx, r12
0x180093c74  call    sqlite3OpenTempDatabase
0x180093c79  test    eax, eax
0x180093c7b  jnz     loc_180097659
0x180093c81  mov     rdx, [rbp+0B0h+var_F8]
0x180093c85  mov     rcx, r14
0x180093c88  call    sqlite3NameFromToken
0x180093c8d  xor     ecx, ecx
0x180093c8f  mov     [rbp+0B0h+var_A0], rax
0x180093c93  test    rax, rax
0x180093c96  jz      loc_180097659
0x180093c9c  mov     rax, rbx
0x180093c9f  shl     rax, 5
0x180093ca3  cmp     [rbp+0B0h+arg_20], ecx
0x180093ca9  mov     rcx, r14
0x180093cac  mov     [rbp+0B0h+var_128], rax
0x180093cb0  jz      short loc_180093CC3
0x180093cb2  mov     r8, r15
0x180093cb5  lea     rdx, aT; "-%T"
0x180093cbc  call    sqlite3MPrintf
0x180093cc1  jmp     short loc_180093CCB
0x180093cc3  mov     rdx, r15
0x180093cc6  call    sqlite3NameFromToken
0x180093ccb  mov     r15, rax
0x180093cce  mov     [rbp+0B0h+var_B8], rax
0x180093cd2  mov     rax, [rbp+0B0h+var_D0]
0x180093cd6  xor     ecx, ecx
0x180093cd8  cmp     [rax+8], ecx
0x180093cdb  jbe     short loc_180093CEB
0x180093cdd  mov     rax, [rbp+0B0h+var_128]
0x180093ce1  mov     rcx, [rbp+0B0h+var_108]
0x180093ce5  mov     rax, [rcx+rax]
0x180093ce9  jmp     short loc_180093CEE
0x180093ceb  mov     rax, rcx
0x180093cee  mov     r8, [rbp+0B0h+var_A0]
0x180093cf2  mov     r9, r15
0x180093cf5  mov     edx, 13h
0x180093cfa  mov     [rbp+0B0h+var_130], rax
0x180093cfe  mov     rcx, r12
0x180093d01  mov     [rsp+1B0h+var_190], rax
0x180093d06  call    sqlite3AuthCheck
0x180093d0b  xor     ecx, ecx
0x180093d0d  test    eax, eax
0x180093d0f  jnz     loc_180097642
0x180093d15  mov     rax, [rbp+0B0h+var_A0]
0x180093d19  lea     r8d, [rcx+0Eh]
0x180093d1d  mov     rdx, [rbp+0B0h+var_130]
0x180093d21  lea     r9, [rbp+0B0h+var_90]
0x180093d25  mov     qword ptr [rbp+0B0h+var_90], rcx
0x180093d29  mov     qword ptr [rbp+0B0h+var_80+8], rcx
0x180093d2d  mov     qword ptr [rbp+0B0h+var_90+8], rax
0x180093d31  mov     qword ptr [rbp+0B0h+var_80], r15
0x180093d35  mov     [r14+298h], ecx
0x180093d3c  mov     rcx, r14
0x180093d3f  call    sqlite3_file_control
0x180093d44  mov     [rsp+1B0h+var_150], eax
0x180093d48  test    eax, eax
0x180093d4a  jnz     short loc_180093D8A
0x180093d4c  mov     edx, esi
0x180093d4e  mov     rcx, rdi
0x180093d51  call    sqlite3VdbeSetNumCols
0x180093d56  mov     r9, qword ptr [rbp+0B0h+var_90]
0x180093d5a  or      r13, 0FFFFFFFFFFFFFFFFh
0x180093d5e  xor     r8d, r8d
0x180093d61  mov     [rsp+1B0h+var_190], r13
0x180093d66  xor     edx, edx
0x180093d68  mov     rcx, rdi
0x180093d6b  call    sqlite3VdbeSetColName
0x180093d70  mov     rdx, qword ptr [rbp+0B0h+var_90]
0x180093d74  mov     rcx, rdi
0x180093d77  call    returnSingleText
0x180093d7c  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x180093d80  call    sqlite3_free
0x180093d85  jmp     loc_180097642
0x180093d8a  cmp     eax, 0Ch
0x180093d8d  jz      short loc_180093DC3
0x180093d8f  mov     r8, qword ptr [rbp+0B0h+var_90]
0x180093d93  test    r8, r8
0x180093d96  jz      short loc_180093DB4
0x180093d98  lea     rdx, aS_7; "%s"
0x180093d9f  mov     rcx, r12
0x180093da2  call    sqlite3ErrorMsg
0x180093da7  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x180093dab  call    sqlite3_free
0x180093db0  mov     eax, [rsp+1B0h+var_150]
0x180093db4  add     [r12+30h], esi
0x180093db9  mov     [r12+18h], eax
0x180093dbe  jmp     loc_180097642
0x180093dc3  mov     rcx, [rbp+0B0h+var_A0]
0x180093dc7  call    pragmaLocate
0x180093dcc  mov     [rbp+0B0h+var_118], rax
0x180093dd0  mov     r10, rax
0x180093dd3  test    rax, rax
0x180093dd6  jz      loc_180097642
0x180093ddc  test    [rax+9], sil
0x180093de0  jz      short loc_180093DF6
0x180093de2  mov     rcx, r12
0x180093de5  call    sqlite3ReadSchema
0x180093dea  test    eax, eax
0x180093dec  jnz     loc_180097642
0x180093df2  mov     r10, [rbp+0B0h+var_118]
0x180093df6  test    [r10+9], r13b
0x180093dfa  jnz     short loc_180093E17
0x180093dfc  test    byte ptr [r10+9], 4
0x180093e01  jz      short loc_180093E08
0x180093e03  test    r15, r15
0x180093e06  jnz     short loc_180093E17
0x180093e08  mov     rdx, r10
0x180093e0b  mov     rcx, rdi
0x180093e0e  call    setPragmaResultColumnNames
0x180093e13  mov     r10, [rbp+0B0h+var_118]
0x180093e17  movzx   ecx, byte ptr [r10+8]
0x180093e1c  cmp     ecx, 16h
0x180093e1f  ja      loc_1800964FD
0x180093e25  jz      loc_180096411
0x180093e2b  cmp     ecx, 0Bh
0x180093e2e  ja      loc_1800943B0
0x180093e34  jz      loc_180094347
0x180093e3a  cmp     ecx, 6
0x180093e3d  ja      loc_1800941CF
0x180093e43  jz      loc_18009413F
0x180093e49  xor     r12d, r12d
0x180093e4c  test    ecx, ecx
0x180093e4e  jz      loc_180094101
0x180093e54  sub     ecx, esi
0x180093e56  jz      loc_180094062
0x180093e5c  sub     ecx, esi
0x180093e5e  jz      loc_180093F77
0x180093e64  sub     ecx, esi
0x180093e66  jz      short loc_180093EC1
0x180093e68  cmp     ecx, r13d
0x180093e6b  jnz     loc_180097400
0x180093e71  test    r15, r15
0x180093e74  jnz     short loc_180093E8C
0x180093e76  mov     rax, [rbp+0B0h+var_128]
0x180093e7a  mov     rcx, [rbp+0B0h+var_108]
0x180093e7e  mov     rax, [rcx+rax+18h]
0x180093e83  movsxd  rdx, dword ptr [rax+74h]
0x180093e87  jmp     loc_18009763A
0x180093e8c  lea     rdx, [rsp+1B0h+var_144]
0x180093e91  mov     [rsp+1B0h+var_144], r12d
0x180093e96  mov     rcx, r15
0x180093e99  call    sqlite3GetInt32
0x180093e9e  mov     r8, [rbp+0B0h+var_128]
0x180093ea2  mov     r9, [rbp+0B0h+var_108]
0x180093ea6  mov     eax, [rsp+1B0h+var_144]
0x180093eaa  mov     rcx, [r9+r8+18h]
0x180093eaf  mov     [rcx+74h], eax
0x180093eb2  mov     rdx, [r9+r8+18h]
0x180093eb7  mov     rcx, [r9+r8+8]
0x180093ebc  jmp     loc_180094BA2
0x180093ec1  test    r15, r15
0x180093ec4  jnz     short loc_180093EE8
0x180093ec6  mov     rdx, r10
0x180093ec9  mov     rcx, rdi
0x180093ecc  call    setPragmaResultColumnNames
0x180093ed1  mov     rbx, [rbp+0B0h+var_118]
0x180093ed5  mov     rdx, r12
0x180093ed8  mov     rax, [r14+30h]
0x180093edc  test    [rbx+10h], rax
0x180093ee0  setnz   dl
0x180093ee3  jmp     loc_18009763A
0x180093ee8  mov     rbx, [r10+10h]
0x180093eec  mov     rcx, r15
0x180093eef  btr     rbx, 0Eh
0x180093ef4  cmp     [r14+65h], r12b
0x180093ef8  cmovnz  rbx, [r10+10h]
0x180093efd  xor     edx, edx
0x180093eff  call    sqlite3GetBoolean
0x180093f04  test    al, al
0x180093f06  jz      short loc_180093F1E
0x180093f08  test    sil, bl
0x180093f0b  jz      short loc_180093F18
0x180093f0d  mov     eax, [r14+30h]
0x180093f11  bt      rax, 1Ch
0x180093f16  jb      short loc_180093F5A
0x180093f18  or      [r14+30h], rbx
0x180093f1c  jmp     short loc_180093F5A
0x180093f1e  mov     rax, rbx
0x180093f21  not     rax
0x180093f24  and     [r14+30h], rax
0x180093f28  cmp     rbx, 80000h
0x180093f2f  jnz     short loc_180093F3A
0x180093f31  mov     [r14+300h], r12
0x180093f38  jmp     short loc_180093F5A
0x180093f3a  test    sil, bl
0x180093f3d  jz      short loc_180093F5A
0x180093f3f  lea     rdx, aReset; "reset"
0x180093f46  mov     rcx, r15
0x180093f49  call    sqlite3_stricmp
0x180093f4e  test    eax, eax
0x180093f50  jnz     short loc_180093F5A
0x180093f52  mov     rcx, r14
0x180093f55  call    sqlite3ResetAllSchemasOfConnection
0x180093f5a  xor     r9d, r9d
0x180093f5d  mov     dword ptr [rsp+1B0h+var_190], r12d
0x180093f62  xor     r8d, r8d
0x180093f65  mov     edx, 0A6h
0x180093f6a  mov     rcx, rdi
0x180093f6d  call    sqlite3VdbeAddOp3
0x180093f72  jmp     loc_1800941C2
0x180093f77  mov     rax, [rbp+0B0h+var_128]
0x180093f7b  mov     rcx, [rbp+0B0h+var_108]
0x180093f7f  mov     rbx, [rcx+rax+8]
0x180093f84  test    r15, r15
0x180093f87  jnz     short loc_180093F96
0x180093f89  mov     rcx, rbx
0x180093f8c  call    sqlite3BtreeGetAutoVacuum
0x180093f91  jmp     loc_180097637
0x180093f96  lea     rdx, aNone; "none"
0x180093f9d  mov     rcx, r15
0x180093fa0  call    sqlite3StrICmp
0x180093fa5  test    eax, eax
0x180093fa7  jnz     short loc_180093FAE
0x180093fa9  mov     r13d, r12d
0x180093fac  jmp     short loc_180093FFD
0x180093fae  lea     rdx, aFull; "full"
0x180093fb5  mov     rcx, r15
0x180093fb8  call    sqlite3StrICmp
0x180093fbd  test    eax, eax
0x180093fbf  jnz     short loc_180093FC6
0x180093fc1  mov     r13d, esi
0x180093fc4  jmp     short loc_180093FFD
0x180093fc6  lea     rdx, aIncremental; "incremental"
0x180093fcd  mov     rcx, r15
0x180093fd0  call    sqlite3StrICmp
0x180093fd5  test    eax, eax
0x180093fd7  jz      short loc_180093FFD
0x180093fd9  lea     rdx, [rsp+1B0h+var_13C]
0x180093fde  mov     [rsp+1B0h+var_13C], r12d
0x180093fe3  mov     rcx, r15
0x180093fe6  call    sqlite3GetInt32
0x180093feb  cmp     [rsp+1B0h+var_13C], r13d
0x180093ff0  movzx   ecx, byte ptr [rsp+1B0h+var_13C]
0x180093ff5  cmova   ecx, r12d
0x180093ff9  movzx   r13d, cl
0x180093ffd  mov     edx, r13d
0x180094000  mov     [r14+6Ah], r13b
0x180094004  mov     rcx, rbx
0x180094007  call    sqlite3BtreeSetAutoVacuum
0x18009400c  test    eax, eax
0x18009400e  jnz     loc_180097642
0x180094014  lea     eax, [r13-1]
0x180094018  cmp     eax, esi
0x18009401a  ja      loc_180097642
0x180094020  mov     ebx, [rdi+90h]
  ... truncated ...
```
