# sqlite3Pragma

- ea: `0x1800847e0`
- end: `0x1800885cd`
- name: `sqlite3Pragma`
- size: `15853`
- prototype: ``
- caller_count: `1`
- callee_count: `97`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c3bd8`

## callees

- `0x180002250`
- `0x18003ae40`
- `0x18003f2e8`
- `0x180045b1c`
- `0x180047054`
- `0x18004ab08`
- `0x18004c3e0`
- `0x18004c458`
- `0x180059894`
- `0x18005d760`
- `0x18005d838`
- `0x180063fb4`
- `0x18006400c`
- `0x180066304`
- `0x1800664fc`
- `0x1800693b0`
- `0x180069d64`
- `0x18006b3ec`
- `0x18006d044`
- `0x18006d0c4`
- `0x18006d144`
- `0x18006d1c4`
- `0x18006d30c`
- `0x18006ecc8`
- `0x18006ed2c`
- `0x18006f0d4`
- `0x18006f18c`
- `0x18006f370`
- `0x1800716fc`
- `0x1800717b0`
- `0x180071b08`
- `0x180073a40`
- `0x180073aec`
- `0x180074ab0`
- `0x1800752b0`
- `0x180077020`
- `0x1800773e0`
- `0x180077d9c`
- `0x180078bec`
- `0x180078c74`
- `0x180079f44`
- `0x18007c174`
- `0x18007c914`
- `0x18007ca28`
- `0x18007d478`
- `0x180080620`
- `0x1800807c0`
- `0x180080b64`
- `0x180081754`
- `0x180081a3c`

## string_xrefs

- `0x180088013`: `sqlite_temp_schema`
- `0x180087cf1`: `not a writable directory`
- `0x1800882ac`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(__int64 *a1, __int64 a2, const char **a3, __int64 a4, int a5)
{
  _QWORD *v5; // r15
  __int64 *v9; // r13
  __int64 result; // rax
  __int64 v11; // r14
  int v12; // esi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  char *v16; // r12
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  const char *v22; // r10
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  __int64 v27; // rdx
  _QWORD *v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rbx
  char v32; // al
  int v33; // r11d
  __int64 v34; // rbx
  int AutoVacuum; // eax
  unsigned int v36; // r11d
  unsigned int v37; // r13d
  unsigned int v38; // r11d
  unsigned __int8 v39; // cl
  int v40; // ebx
  _DWORD *v41; // rax
  int v42; // r13d
  __int64 v43; // rcx
  __int64 v44; // r10
  unsigned int v45; // r11d
  __int64 v46; // rbx
  _DWORD *v47; // rax
  int v48; // r9d
  __int64 v49; // r8
  unsigned int v50; // edx
  int Int32; // eax
  __int64 v52; // r8
  int v53; // edi
  char SafetyLevel; // al
  __int64 v55; // rcx
  __int64 v56; // rdx
  unsigned __int64 v57; // rcx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  unsigned int j; // ebx
  char *v65; // r8
  int v66; // r8d
  __int64 v67; // r9
  unsigned int v68; // edx
  __int64 **v69; // rbx
  unsigned int v70; // edi
  char v71; // al
  unsigned int i; // ebx
  __int64 v73; // r8
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 *v76; // rax
  __int64 v77; // rdx
  int *v78; // rax
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ebx
  __int64 m; // r13
  __int64 n; // rdi
  _QWORD *v86; // rdi
  __int64 v87; // rax
  __int64 v88; // rbx
  __int64 v89; // rcx
  int v90; // edi
  __int64 v91; // rdx
  unsigned int v92; // eax
  int v93; // r13d
  const char *v94; // r10
  const char *v95; // r9
  int v96; // eax
  unsigned int v97; // ecx
  _QWORD *v98; // rcx
  __int64 Table; // rax
  __int64 v100; // rcx
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // rbx
  int v104; // ecx
  int v105; // r8d
  int v106; // ecx
  const char *k; // rax
  __int64 v108; // rax
  int v109; // r8d
  const char **v110; // r12
  int v111; // edi
  __int64 v112; // r8
  const char *v113; // rbx
  __int64 v114; // rax
  int v115; // eax
  int v116; // ecx
  __int64 v117; // r15
  int v118; // r13d
  int v119; // r9d
  unsigned int v120; // ebx
  unsigned int v121; // eax
  const char *v122; // rbx
  bool v123; // zf
  unsigned int v124; // ebx
  char *v125; // rdx
  const char *v126; // rax
  char **v127; // rbx
  __int64 v128; // rdx
  char v129; // r11
  __int64 v130; // rcx
  int v131; // r11d
  _DWORD *v132; // rax
  int v133; // esi
  _QWORD *v134; // rcx
  __int64 v135; // rax
  unsigned int v136; // ecx
  unsigned int v137; // ecx
  unsigned int v138; // ecx
  int v139; // eax
  __int64 v140; // r9
  int v141; // eax
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rax
  int v145; // ecx
  _QWORD *v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rdx
  int v149; // eax
  int *v150; // rax
  int *v151; // rbx
  int v152; // r9d
  _QWORD *v153; // r8
  __int64 v154; // r14
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 ii; // rdx
  unsigned int v158; // eax
  __int64 v159; // rax
  unsigned int v160; // edi
  __int64 v161; // rbx
  unsigned int v162; // eax
  __int64 v163; // r11
  __int64 v164; // rdx
  _QWORD *v165; // r13
  int v166; // eax
  __int64 v167; // rcx
  int v168; // r9d
  const char **v169; // rdx
  const char **v170; // r8
  __int64 v171; // rcx
  const char *v172; // rcx
  int v173; // r15d
  unsigned int v174; // ebx
  __int64 v175; // rax
  __int64 v176; // rcx
  __int64 v177; // rax
  __int64 v178; // r10
  int TempRange; // eax
  __int64 v180; // r10
  int v181; // edx
  int v182; // r13d
  const char *v183; // r15
  int v184; // r10d
  int v185; // r8d
  __int64 v186; // r9
  int v187; // eax
  int v188; // r9d
  const char *jj; // rcx
  __int64 LastOp; // rax
  int v191; // ebx
  unsigned int v192; // edi
  __int64 v193; // rbx
  unsigned int v194; // eax
  unsigned int v195; // r10d
  int v196; // ebx
  int v197; // r14d
  __int64 v198; // r15
  int v199; // edi
  const char **v200; // rbx
  __int64 v201; // rdx
  int v202; // r8d
  bool v203; // cc
  __int64 v204; // rcx
  char *v205; // r9
  unsigned int v206; // eax
  __int64 v207; // r8
  int v208; // r11d
  int v209; // ecx
  __int64 v210; // rax
  const char *kk; // rcx
  __int16 v212; // ax
  int v213; // eax
  int v214; // edx
  const char *v215; // rax
  unsigned int v216; // eax
  int v217; // edx
  __int64 v218; // rcx
  __int64 v219; // rbx
  unsigned int v220; // eax
  unsigned int v221; // ecx
  __int64 v222; // rcx
  const char *v223; // r8
  __int64 v224; // rax
  char v225; // cl
  __int64 v226; // rax
  __int64 v227; // rax
  unsigned int v228; // eax
  __int64 v229; // rax
  __int64 v230; // rbx
  unsigned int v231; // eax
  const char *v232; // rdx
  const char *v233; // rax
  const char *v234; // rcx
  int v235; // eax
  unsigned int v236; // r14d
  int v237; // ebx
  const char *v238; // r15
  __int64 v239; // rbx
  unsigned int v240; // eax
  const char *v241; // rbx
  __int64 v242; // rdx
  int v243; // ecx
  const char **v244; // r15
  int v245; // eax
  unsigned int v246; // ebx
  unsigned int v247; // ebx
  unsigned int v248; // edx
  int v249; // r15d
  unsigned int v250; // ebx
  int v251; // edx
  int v252; // r13d
  __int64 v253; // rax
  unsigned int v254; // ebx
  int v255; // ebx
  _QWORD *v256; // rdi
  __int64 v257; // r8
  __int64 v258; // rbx
  __int64 ElementWithHash; // rax
  __int64 v260; // rax
  __int64 *v261; // rax
  __int64 v262; // rax
  unsigned int v263; // ebx
  __int64 v264; // rax
  char v265; // r9
  __int64 v266; // rax
  __int64 v267; // r8
  __int64 *v268; // rcx
  __int64 v269; // rbx
  __int64 v270; // rcx
  int v271; // edi
  __int64 v272; // rdx
  __int64 v273; // rbx
  unsigned int v274; // edi
  __int64 v275; // rcx
  __int64 v276; // rax
  __int64 v277; // rdx
  int v278; // edi
  __int64 v279; // r8
  __int64 v280; // rax
  unsigned __int16 *v281; // rdx
  int v282; // ebx
  unsigned int v283; // edi
  __int64 v284; // rdx
  __int64 v285; // rcx
  int v286; // ebx
  unsigned int v287; // ebx
  int v288; // r13d
  __int64 v289; // rcx
  unsigned int v290; // ecx
  char *v291; // rdx
  int v292; // ebx
  int v293; // ecx
  int v294; // r8d
  unsigned int v295; // ecx
  unsigned int v296; // ecx
  unsigned int v297; // ecx
  unsigned int v298; // ecx
  _QWORD *i3; // rbx
  const char **v300; // rdx
  int v301; // r12d
  __int64 v302; // rax
  __int64 v303; // rcx
  int v304; // r12d
  __int64 v305; // rax
  __int64 v306; // rcx
  unsigned __int8 *v307; // rax
  int v308; // ebx
  int v309; // eax
  int v310; // r11d
  const char *v311; // rdi
  int v312; // r8d
  int v313; // eax
  char v314; // al
  int i4; // r9d
  __int64 *v316; // rax
  __int64 v317; // rcx
  __int64 v318; // rax
  __int64 v319; // rax
  __int64 v320; // rcx
  __int64 *v321; // rcx
  __int64 v322; // rax
  __int64 v323; // rdi
  __int64 v324; // rcx
  int v325; // ebx
  int v326; // eax
  __int64 i6; // rax
  __int64 v328; // rax
  int v329; // ecx
  unsigned int v330; // r9d
  __int64 v331; // r8
  int v332; // edx
  int v333; // r8d
  char v334; // cl
  int v335; // eax
  unsigned __int8 v336; // cl
  unsigned int v337; // eax
  unsigned int v338; // eax
  int v339; // r8d
  __int64 *v340; // rcx
  int v341; // r10d
  unsigned int i5; // edx
  unsigned int v343; // ecx
  unsigned int v344; // ecx
  unsigned int v345; // ecx
  __int64 v346; // r13
  int v347; // ebx
  int v348; // r11d
  int i1; // edi
  __int64 i2; // rbx
  __int64 v351; // rbx
  int v352; // ecx
  __int64 v353; // rdx
  unsigned int v354; // ecx
  unsigned int v355; // ecx
  unsigned int v356; // ecx
  unsigned int v357; // ecx
  __int64 v358; // rax
  __int64 v359; // rax
  int v360; // eax
  int v361; // r11d
  __int64 v362; // rbx
  __int64 v363; // rbx
  __int64 v364; // rdx
  int mm; // r13d
  __int64 v366; // r11
  __int64 v367; // rdx
  __int64 v368; // rcx
  int v369; // edi
  _QWORD *nn; // rax
  __int64 v371; // r8
  __int64 v372; // rax
  __int64 v373; // r8
  _QWORD *v374; // r11
  _QWORD *v375; // rdi
  const char *v376; // rax
  unsigned int v377; // ecx
  const char *v378; // rax
  __int64 v379; // r11
  const char *v380; // r11
  __int64 v381; // rax
  __int64 v382; // rdi
  __int64 v383; // rdx
  int v384; // ecx
  __int64 v385; // r15
  int v386; // r9d
  __int64 v387; // r8
  __int16 v388; // ax
  int v389; // r13d
  __int64 v390; // rax
  __int64 v391; // r9
  unsigned int v392; // r11d
  __int64 v393; // rax
  int v394; // r10d
  int v395; // r11d
  int v396; // r8d
  __int64 v397; // r9
  const char *v398; // r8
  char v399; // al
  _QWORD *v400; // rcx
  int v401; // eax
  unsigned int v402; // ecx
  unsigned int v403; // ecx
  unsigned int v404; // ecx
  unsigned __int64 v405; // rcx
  __int64 v406; // rbx
  char *v407; // r8
  unsigned int v408; // ebx
  char v409; // r8
  __int64 v410; // rdx
  int v411; // eax
  int v412; // r9d
  int v413; // edi
  int v414; // r11d
  int v415; // r8d
  __int64 v416; // [rsp+20h] [rbp-E0h]
  __int64 v417; // [rsp+20h] [rbp-E0h]
  __int64 v418; // [rsp+28h] [rbp-D8h]
  int v419; // [rsp+28h] [rbp-D8h]
  int v420; // [rsp+28h] [rbp-D8h]
  __int64 v421; // [rsp+28h] [rbp-D8h]
  int v422; // [rsp+30h] [rbp-D0h]
  __int64 v423; // [rsp+38h] [rbp-C8h]
  int v424; // [rsp+40h] [rbp-C0h]
  int v425; // [rsp+48h] [rbp-B8h]
  unsigned int v426; // [rsp+60h] [rbp-A0h] BYREF
  int String; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v428; // [rsp+68h] [rbp-98h] BYREF
  __int64 v429; // [rsp+70h] [rbp-90h] BYREF
  __int64 Index; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v431; // [rsp+80h] [rbp-80h]
  int v432; // [rsp+84h] [rbp-7Ch] BYREF
  const char *v433; // [rsp+88h] [rbp-78h]
  __int64 v434; // [rsp+90h] [rbp-70h]
  int v435; // [rsp+98h] [rbp-68h]
  unsigned int v436; // [rsp+9Ch] [rbp-64h] BYREF
  const char **v437; // [rsp+A0h] [rbp-60h]
  char v438; // [rsp+A8h] [rbp-58h]
  int IndexKey; // [rsp+ACh] [rbp-54h]
  unsigned int v440; // [rsp+B0h] [rbp-50h]
  _QWORD *v441; // [rsp+B8h] [rbp-48h]
  __int64 v442; // [rsp+C0h] [rbp-40h]
  int v443; // [rsp+C8h] [rbp-38h]
  unsigned int v444; // [rsp+CCh] [rbp-34h] BYREF
  int v445; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v446; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v447; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v448; // [rsp+E8h] [rbp-18h]
  unsigned int v449; // [rsp+ECh] [rbp-14h]
  char *v450; // [rsp+F0h] [rbp-10h]
  __int64 v451; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v452; // [rsp+100h] [rbp+0h] BYREF
  int v453; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v454; // [rsp+110h] [rbp+10h]
  __int64 *v455; // [rsp+118h] [rbp+18h]
  __int128 v456; // [rsp+120h] [rbp+20h] BYREF
  __int128 v457; // [rsp+130h] [rbp+30h]
  _QWORD v458[5]; // [rsp+140h] [rbp+40h] BYREF

  v5 = (_QWORD *)*a1;
  v447 = *a1;
  v437 = a3;
  v446 = 0;
  v456 = 0;
  v429 = a4;
  v457 = 0;
  v9 = a1;
  v455 = a1;
  result = sqlite3GetVdbe(a1);
  Index = result;
  v11 = result;
  if ( result )
  {
    v12 = 1;
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    *((_DWORD *)v9 + 14) = 2;
    result = sqlite3TwoPartName(v9, a2, a3, &v446);
    v13 = (int)result;
    if ( (int)result >= 0 )
    {
      v441 = (_QWORD *)v5[4];
      if ( (_DWORD)result != 1 || (result = sqlite3OpenTempDatabase(v9), !(_DWORD)result) )
      {
        result = sqlite3NameFromToken(v5, v446);
        v454 = (unsigned __int8 *)result;
        if ( result )
        {
          v14 = 4 * v13;
          if ( a5 )
            v15 = sqlite3MPrintf(v5, "-%T", a4);
          else
            v15 = sqlite3NameFromToken(v5, a4);
          v16 = (char *)v15;
          v450 = (char *)v15;
          if ( *((_DWORD *)v437 + 2) )
            v17 = v441[4 * v13];
          else
            v17 = 0;
          v434 = v17;
          if ( (unsigned int)sqlite3AuthCheck((_DWORD)v9, 19, (_DWORD)v454, (_DWORD)v16, v17) )
            goto LABEL_876;
          v18 = v434;
          *(_QWORD *)&v456 = 0;
          *((_QWORD *)&v456 + 1) = v454;
          v457 = (unsigned __int64)v16;
          *((_DWORD *)v5 + 166) = 0;
          v19 = sqlite3_file_control(v5, v18, 14, &v456);
          v426 = v19;
          if ( !v19 )
          {
            sqlite3VdbeSetNumCols(v11, 1);
            sqlite3VdbeSetColName(v11, 0, 0, v456, -1);
            returnSingleText(v11, v456);
            sqlite3_free(v456);
            goto LABEL_876;
          }
          if ( v19 != 12 )
          {
            if ( (_QWORD)v456 )
            {
              sqlite3ErrorMsg(v9, "%s", (const char *)v456);
              sqlite3_free(v456);
              v19 = v426;
            }
            goto LABEL_18;
          }
          v20 = pragmaLocate(v454);
          v433 = (const char *)v20;
          v22 = (const char *)v20;
          if ( !v20 )
            goto LABEL_876;
          if ( (*(_BYTE *)(v20 + 9) & 1) != 0 )
          {
            if ( (unsigned int)sqlite3ReadSchema(v9) )
              goto LABEL_876;
            v22 = v433;
          }
          if ( (v22[9] & 2) == 0 && ((v22[9] & 4) == 0 || !v16) )
          {
            setPragmaResultColumnNames(v11, v22);
            v22 = v433;
          }
          v23 = *((unsigned __int8 *)v22 + 8);
          if ( v23 <= 0x16 )
          {
            if ( v23 != 22 )
            {
              if ( v23 <= 0xB )
              {
                if ( v23 == 11 )
                {
                  *((_DWORD *)v9 + 14) = 3;
                  for ( i = 0; (signed int)i < *((_DWORD *)v5 + 10); ++i )
                  {
                    v73 = v5[4];
                    v74 = 32LL * (int)i;
                    v75 = *(_QWORD *)(v74 + v73 + 8);
                    if ( v75 )
                    {
                      v76 = *(__int64 **)(v75 + 8);
                      v77 = *v76;
                      if ( *(_BYTE *)(*v76 + 19) || *(char **)v77 == byte_18010B000 )
                        v78 = &dword_1800FAEFC;
                      else
                        v78 = *(int **)(v77 + 216);
                      sqlite3VdbeMultiLoad(v11, 1, "iss", i, *(_QWORD *)(v74 + v73), v78, v422, v423, v424, v425);
                    }
                  }
                  goto LABEL_876;
                }
                if ( v23 <= 6 )
                {
                  if ( v23 == 6 )
                  {
                    AutoVacuum = 0;
                    if ( v16 )
                    {
                      String = 1;
                      Int32 = sqlite3GetInt32(v16, &String);
                      v53 = String;
                      if ( Int32 )
                        sqlite3BtreeSetSpillSize(v441[v14 + 1], (unsigned int)String);
                      LOBYTE(v52) = v53 != 0;
                      SafetyLevel = getSafetyLevel(v16, 1, v52);
                      v55 = v5[6];
                      v56 = v55 | 0x20;
                      v57 = v55 & 0xFFFFFFFFFFFFFFDFuLL;
                      if ( !SafetyLevel )
                        v56 = v57;
                      v5[6] = v56;
                      goto LABEL_92;
                    }
                    if ( (v5[6] & 0x20) != 0 )
                      AutoVacuum = sqlite3BtreeSetSpillSize(v441[v14 + 1], 0);
                  }
                  else
                  {
                    if ( !v22[8] )
                    {
                      Index = 0;
                      if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
                        *((_DWORD *)v5 + 186) = Index & 0x7FFFFFFF;
                      v27 = *((int *)v5 + 186);
                      goto LABEL_875;
                    }
                    v24 = v23 - 1;
                    if ( !v24 )
                    {
                      v42 = *((_DWORD *)v22 + 4);
                      sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                      if ( !v16 || (*(_BYTE *)(v44 + 9) & 8) != 0 )
                      {
                        v47 = (_DWORD *)sqlite3VdbeAddOpList(v43, 3, qword_1800FB350);
                        v47[1] = v13;
                        v47[7] = v13;
                        v47[9] = v42;
                        v48 = *(_DWORD *)(v11 + 144);
                        if ( v48 > 1 )
                        {
                          v49 = *(_QWORD *)(v11 + 136);
                          v50 = 1;
                          while ( *(_BYTE *)(v49 + 24LL * v50) != 0xA6 )
                          {
                            if ( (int)++v50 >= v48 )
                              goto LABEL_876;
                          }
                          *(_BYTE *)(v49 + 24) = -69;
                        }
                      }
                      else
                      {
                        String = 0;
                        v46 = sqlite3VdbeAddOpList(v43, v45, &qword_1800FA4E0);
                        *(_DWORD *)(v46 + 4) = v13;
                        *(_DWORD *)(v46 + 28) = v13;
                        *(_DWORD *)(v46 + 32) = v42;
                        sqlite3GetInt32(v16, &String);
                        *(_DWORD *)(v46 + 36) = String;
                        *(_WORD *)(v46 + 26) = 1;
                        if ( v42 == 1 && (v5[6] & 0x10000000) != 0 )
                          *(_BYTE *)(v46 + 24) = -69;
                      }
                      goto LABEL_876;
                    }
                    v25 = v24 - 1;
                    if ( v25 )
                    {
                      v26 = v25 - 1;
                      if ( v26 )
                      {
                        if ( v26 == 2 )
                        {
                          if ( !v16 )
                          {
                            v27 = *(int *)(v441[v14 + 3] + 116LL);
LABEL_875:
                            returnSingleInt(v11, v27);
                            goto LABEL_876;
                          }
                          String = 0;
                          sqlite3GetInt32(v16, &String);
                          v28 = v441;
                          *(_DWORD *)(v441[v14 + 3] + 116LL) = String;
                          v29 = v28[v14 + 3];
                          v30 = v28[v14 + 1];
LABEL_248:
                          sqlite3BtreeSetCacheSize(v30, *(unsigned int *)(v29 + 116));
                          goto LABEL_876;
                        }
LABEL_836:
                        if ( v16 )
                        {
                          v426 = 0;
                          sqlite3GetInt32(v16, &v426);
                          sqlite3_busy_timeout(v5, v426);
                        }
                        v27 = *((int *)v5 + 187);
                        goto LABEL_875;
                      }
                      if ( !v16 )
                      {
                        setPragmaResultColumnNames(v11, v22);
                        v27 = (v5[6] & *((_QWORD *)v433 + 2)) != 0;
                        goto LABEL_875;
                      }
                      v31 = *((_QWORD *)v22 + 2) & 0xFFFFFFFFFFFFBFFFuLL;
                      if ( *((_BYTE *)v5 + 101) )
                        v31 = *((_QWORD *)v22 + 2);
                      v32 = getSafetyLevel(v16, 1, 0);
                      v33 = 0;
                      if ( v32 )
                      {
                        if ( (v31 & 1) == 0 || (v5[6] & 0x10000000) == 0 )
                          v5[6] |= v31;
                      }
                      else
                      {
                        v5[6] &= ~v31;
                        if ( v31 == 0x80000 )
                        {
                          v5[96] = 0;
                        }
                        else if ( (v31 & 1) != 0 && !(unsigned int)sqlite3StrICmp(v16, "reset") )
                        {
                          sqlite3ResetAllSchemasOfConnection(v5);
                          v33 = 0;
                        }
                      }
                      sqlite3VdbeAddOp3(v11, 166, 0, 0, v33);
LABEL_92:
                      setAllPagerFlags(v5);
                      goto LABEL_876;
                    }
                    v34 = v441[v14 + 1];
                    if ( v16 )
                    {
                      if ( (unsigned int)sqlite3StrICmp(v16, "none") )
                      {
                        if ( (unsigned int)sqlite3StrICmp(v16, "full") )
                        {
                          if ( (unsigned int)sqlite3StrICmp(v16, "incremental") )
                          {
                            v436 = v38;
                            sqlite3GetInt32(v16, &v436);
                            v39 = v436;
                            if ( v436 > 2 )
                              v39 = 0;
                            v37 = v39;
                          }
                          else
                          {
                            v37 = 2;
                          }
                        }
                        else
                        {
                          v37 = 1;
                        }
                      }
                      else
                      {
                        v37 = v36;
                      }
                      *((_BYTE *)v5 + 106) = v37;
                      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v34, v37) && v37 - 1 <= 1 )
                      {
                        v40 = *(_DWORD *)(v11 + 144);
                        v41 = (_DWORD *)sqlite3VdbeAddOpList(v11, 5, qword_1800FB980);
                        v41[14] = v40 + 4;
                        v41[27] = v37 - 1;
                        v41[1] = v13;
                        v41[7] = v13;
                        v41[25] = v13;
                        sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                      }
                      goto LABEL_876;
                    }
                    AutoVacuum = sqlite3BtreeGetAutoVacuum(v34);
                  }
LABEL_874:
                  v27 = AutoVacuum;
                  goto LABEL_875;
                }
                v58 = v23 - 7;
                if ( !v58 )
                {
                  if ( v16 )
                  {
                    v71 = getSafetyLevel(v16, 1, 0);
                    sqlite3RegisterLikeFunctions(v5, v71 != 0);
                  }
                  goto LABEL_876;
                }
                v59 = v58 - 1;
                if ( v59 )
                {
                  v60 = v59 - 1;
                  if ( !v60 )
                  {
                    *((_DWORD *)v9 + 14) = 1;
                    for ( j = 0; j <= 0x27; ++j )
                    {
                      v65 = off_1800CD3B0[j];
                      if ( !v65 )
                        break;
                      sqlite3VdbeLoadString(v11, 1, v65);
                      sqlite3VdbeAddOp3(v11, 84, 1, 1, 0);
                    }
                    v66 = *(_DWORD *)(v11 + 144);
                    v5 = (_QWORD *)v447;
                    v16 = v450;
                    if ( v66 > 1 )
                    {
                      v67 = *(_QWORD *)(v11 + 136);
                      v68 = 1;
                      while ( *(_BYTE *)(v67 + 24LL * v68) != 0xA6 )
                      {
                        if ( (int)++v68 >= v66 )
                          goto LABEL_876;
                      }
                      *(_BYTE *)(v67 + 24) = -69;
                    }
                    goto LABEL_876;
                  }
                  if ( v60 != 1 )
                    goto LABEL_836;
                  if ( (_BYTE)word_18010EE54 )
                  {
                    v61 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
                    if ( v61 )
                      ((void (__fastcall *)(__int64))xmmword_18010EED0)(v61);
                  }
                  if ( !v16 )
                  {
                    v62 = sqlite3_data_directory;
LABEL_102:
                    returnSingleText(v11, v62);
                    goto LABEL_736;
                  }
                  if ( !*v16
                    || (v63 = *v5,
                        String = 0,
                        !(*(unsigned int (__fastcall **)(__int64, char *, __int64, int *))(v63 + 56))(
                           v63,
                           v16,
                           1,
                           &String))
                    && String )
                  {
                    sqlite3_free(sqlite3_data_directory);
                    if ( *v16 )
                      sqlite3_data_directory = sqlite3_mprintf("%s", v16);
                    else
                      sqlite3_data_directory = 0;
LABEL_736:
                    if ( (_BYTE)word_18010EE54 )
                    {
                      v359 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
                      if ( v359 )
                        ((void (__fastcall *)(__int64))xmmword_18010EEE0)(v359);
                    }
                    goto LABEL_876;
                  }
                  goto LABEL_735;
                }
                *((_DWORD *)v9 + 14) = 2;
                v69 = (__int64 **)v5[79];
                v70 = 0;
                if ( !v69 )
                  goto LABEL_876;
                do
                {
                  sqlite3VdbeMultiLoad(v11, 1, "is", v70, *v69[2], v418, v422, v423, v424, v425);
                  v69 = (__int64 **)*v69;
                  ++v70;
                }
                while ( v69 );
LABEL_819:
                v16 = v450;
                goto LABEL_876;
              }
              if ( (unsigned __int8)v23 <= 0x11u )
              {
                if ( (_BYTE)v23 != 17 )
                {
                  v79 = v23 - 12;
                  if ( !v79 )
                  {
                    sqlite3VdbeUsesBtree(v11, (unsigned int)v13);
                    if ( !v16 )
                    {
                      *((_DWORD *)v9 + 14) += v131;
                      v132 = (_DWORD *)sqlite3VdbeAddOpList(v130, 9, qword_1800FA910);
                      v132[1] = v13;
                      v132[7] = v13;
                      v132[37] = -32000;
                      goto LABEL_876;
                    }
                    String = 0;
                    sqlite3GetInt32(v16, &String);
                    v133 = String;
                    if ( String < 0 )
                    {
                      if ( String == 0x80000000 )
                        v133 = 0x7FFFFFFF;
                      else
                        v133 = -String;
                    }
                    sqlite3BeginWriteOperation(v9, 0, (unsigned int)v13);
                    sqlite3VdbeAddOp3(v11, 100, v13, 3, v133);
                    v134 = v441;
                    *(_DWORD *)(v441[v14 + 3] + 116LL) = v133;
                    v29 = v134[v14 + 3];
                    v30 = v134[v14 + 1];
                    goto LABEL_248;
                  }
                  v80 = v79 - 1;
                  if ( v80 )
                  {
                    v81 = v80 - 1;
                    if ( !v81 )
                    {
                      _mm_lfence();
                      v96 = *((_DWORD *)v9 + 14);
                      v97 = v96 + 1;
                      v96 += 5;
                      *((_DWORD *)v9 + 14) = v96;
                      v436 = v97;
                      String = v96;
                      v98 = *(_QWORD **)(*(_QWORD *)(v5[4] + v14 * 8 + 24) + 16LL);
                      while ( v98 )
                      {
                        if ( v16 )
                        {
                          Table = sqlite3LocateTable(v9, 0, v16, v434);
                          v98 = 0;
                        }
                        else
                        {
                          Table = v98[2];
                          v98 = (_QWORD *)*v98;
                        }
                        v441 = v98;
                        v437 = (const char **)Table;
                        if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                        {
                          v100 = *(_QWORD *)(Table + 96);
                          v101 = 4294934528LL;
                          v435 = -32768;
                          if ( v100 )
                          {
                            v101 = 0;
                            v102 = v5[4];
                            v435 = 0;
                            if ( *(_QWORD *)(v102 + 24) != v100 )
                            {
                              do
                                v101 = (unsigned int)(v101 + 1);
                              while ( *(_QWORD *)(32LL * (int)v101 + v102 + 24) != v100 );
                              v435 = v101;
                            }
                          }
                          v103 = *(_QWORD *)(32LL * (int)v101 + v5[4]);
                          v434 = v103;
                          sqlite3CodeVerifySchema(v9, v101);
                          sqlite3TableLock((_DWORD)v9, v435, *((_DWORD *)v437 + 10), 0, (__int64)*v437);
                          v104 = (int)v437;
                          v105 = String + *((__int16 *)v437 + 27);
                          if ( *((_DWORD *)v9 + 14) < v105 )
                            *((_DWORD *)v9 + 14) = v105;
                          sqlite3OpenTable((_DWORD)v9, 0, v435, v104, 112);
                          sqlite3VdbeLoadString(v11, v436, *v437);
                          v106 = 1;
                          for ( k = v437[9]; ; k = *(const char **)(Index + 8) )
                          {
                            Index = (__int64)k;
                            v428 = v106;
                            if ( !k )
                              break;
                            v108 = sqlite3FindTable(v5, *((_QWORD *)k + 2), v103);
                            v446 = v108;
                            if ( v108 )
                            {
                              v109 = *(_DWORD *)(v108 + 40);
                              v451 = 0;
                              sqlite3TableLock((_DWORD)v9, v435, v109, 0, *(_QWORD *)v108);
                              if ( (unsigned int)sqlite3FkLocateIndex((_DWORD)v9, v446, Index, (unsigned int)&v451, 0) )
                                goto LABEL_876;
                              if ( v451 )
                              {
                                sqlite3VdbeAddOp3(v11, 112, v428, *(_DWORD *)(v451 + 88), v435);
                                sqlite3VdbeSetP4KeyInfo(v9, v451);
                              }
                              else
                              {
                                sqlite3OpenTable((_DWORD)v9, v428, v435, v446, 112);
                              }
                            }
                            v106 = v428 + 1;
                          }
                          if ( *((_DWORD *)v9 + 13) < v106 )
                            *((_DWORD *)v9 + 13) = v106;
                          v432 = sqlite3VdbeAddOp3(v11, 36, 0, 0, 0);
                          LODWORD(v442) = 1;
                          v433 = v437[9];
                          if ( v433 )
                          {
                            v110 = v437;
                            v111 = String;
                            v448 = v436 + 2;
                            v444 = v436 + 1;
                            do
                            {
                              v112 = v103;
                              v113 = v433;
                              v114 = sqlite3FindTable(v5, *((_QWORD *)v433 + 2), v112);
                              v429 = v114;
                              v451 = 0;
                              Index = 0;
                              if ( v114 )
                                sqlite3FkLocateIndex(
                                  (_DWORD)v9,
                                  v114,
                                  (_DWORD)v113,
                                  (unsigned int)&v451,
                                  (__int64)&Index);
                              v115 = *((_DWORD *)v9 + 17) - 1;
                              *((_DWORD *)v9 + 17) = v115;
                              v116 = v111 + *((_DWORD *)v113 + 10);
                              v428 = v115;
                              if ( *((_DWORD *)v9 + 14) < v116 )
                                *((_DWORD *)v9 + 14) = v116;
                              if ( *((int *)v113 + 10) > 0 )
                              {
                                v117 = Index;
                                v118 = 0;
                                do
                                {
                                  if ( v117 )
                                    v119 = *(_DWORD *)(v117 + 4LL * v118);
                                  else
                                    v119 = *(_DWORD *)&v113[16 * v118 + 64];
                                  sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v110, 0, v119, v111 + v118);
                                  sqlite3VdbeAddOp3(v11, 50, v111 + v118, v428, 0);
                                  v113 = v433;
                                  ++v118;
                                }
                                while ( v118 < *((_DWORD *)v433 + 10) );
                                v5 = (_QWORD *)v447;
                                v9 = v455;
                              }
                              if ( v451 )
                              {
                                v446 = *(_QWORD *)(v451 + 32);
                                if ( !v446 )
                                  v446 = computeIndexAffStr(v5, v451);
                                v120 = *((_DWORD *)v113 + 10);
                                v121 = sqlite3VdbeAddOp3(v11, 96, v111, v120, 0);
                                sqlite3VdbeChangeP4(v11, v121, v446, v120);
                                v113 = v433;
                                sqlite3VdbeAddOp4Int(v11, 29, v442, v428, v111, *((_DWORD *)v433 + 10));
                              }
                              else if ( v429 )
                              {
                                sqlite3VdbeAddOp3(v11, 30, v442, *(_DWORD *)(v11 + 144) + 2, v111);
                                sqlite3VdbeAddOp3(v11, 9, 0, v428, 0);
                              }
                              sqlite3VdbeAddOp3(v11, (*((_DWORD *)v110 + 12) & 0x80u) != 0 ? 75 : 135, 0, v444, 0);
                              LODWORD(v417) = v442 - 1;
                              sqlite3VdbeMultiLoad(
                                v11,
                                v448,
                                "siX",
                                *((_QWORD *)v113 + 2),
                                v417,
                                v418,
                                v422,
                                v423,
                                v424,
                                v425);
                              sqlite3VdbeAddOp3(v11, 84, v436, 4, 0);
                              sqlite3VdbeResolveLabel(v11, v428);
                              if ( Index )
                                sqlite3DbFreeNN(v5);
                              v122 = (const char *)*((_QWORD *)v113 + 1);
                              LODWORD(v442) = v442 + 1;
                              v433 = v122;
                              v123 = v122 == 0;
                              v103 = v434;
                            }
                            while ( !v123 );
                            v16 = v450;
                          }
                          v124 = v432;
                          sqlite3VdbeAddOp3(v11, 39, 0, v432 + 1, 0);
                          sqlite3VdbeJumpHere(v11, v124);
                          v98 = v441;
                        }
                      }
                      goto LABEL_876;
                    }
                    v82 = v81 - 1;
                    if ( v82 )
                    {
                      if ( v82 == 1 )
                      {
                        v83 = (*((_DWORD *)v5 + 11) >> 5) & 1;
                        *((_DWORD *)v9 + 14) = 6;
                        for ( m = 0; m != 23; ++m )
                        {
                          for ( n = qword_18010FAE0[m]; n; n = *(_QWORD *)(n + 64) )
                            pragmaFunclistLine(v11, n, 1, v83);
                        }
                        v86 = (_QWORD *)v5[76];
                        v16 = v450;
                        while ( v86 )
                        {
                          pragmaFunclistLine(v11, v86[2], 0, v83);
                          v86 = (_QWORD *)*v86;
                        }
                        goto LABEL_876;
                      }
                      goto LABEL_836;
                    }
                    if ( !v16 )
                      goto LABEL_876;
                    v87 = sqlite3FindTable(v5, v16, v434);
                    v429 = v87;
                    if ( !v87 )
                      goto LABEL_876;
                    if ( *(_BYTE *)(v87 + 63) )
                      goto LABEL_876;
                    v88 = *(_QWORD *)(v87 + 72);
                    if ( !v88 )
                      goto LABEL_876;
                    v89 = *(_QWORD *)(v87 + 96);
                    v90 = -32768;
                    if ( v89 )
                    {
                      v91 = v5[4];
                      v90 = 0;
                      if ( *(_QWORD *)(v91 + 24) != v89 )
                      {
                        do
                          ++v90;
                        while ( *(_QWORD *)(32LL * v90 + v91 + 24) != v89 );
                      }
                    }
                    v428 = 0;
                    *((_DWORD *)v9 + 14) = 8;
                    sqlite3CodeVerifySchema(v9, (unsigned int)v90);
                    v92 = v428;
                    do
                    {
                      v93 = 0;
                      if ( *(int *)(v88 + 40) > 0 )
                      {
                        do
                        {
                          switch ( *(_BYTE *)(v88 + 45) )
                          {
                            case 7:
                              v94 = "RESTRICT";
                              break;
                            case 8:
                              v94 = "SET NULL";
                              break;
                            case 9:
                              v94 = "SET DEFAULT";
                              break;
                            case 0xA:
                              v94 = "CASCADE";
                              break;
                            default:
                              v94 = "NO ACTION";
                              break;
                          }
                          switch ( *(_BYTE *)(v88 + 46) )
                          {
                            case 7:
                              v95 = "RESTRICT";
                              break;
                            case 8:
                              v95 = "SET NULL";
                              break;
                            case 9:
                              v95 = "SET DEFAULT";
                              break;
                            case 0xA:
                              v95 = "CASCADE";
                              break;
                            default:
                              v95 = "NO ACTION";
                              break;
                          }
                          LODWORD(v416) = v93;
                          sqlite3VdbeMultiLoad(
                            v11,
                            1,
                            "iissssss",
                            v428,
                            v416,
                            *(_QWORD *)(v88 + 16),
                            *(_QWORD *)(*(_QWORD *)(v429 + 8) + 24LL * *(int *)(v88 + 16 * (v93 + 4LL))),
                            *(_QWORD *)(v88 + 16LL * v93 + 72),
                            (_DWORD)v95,
                            (_DWORD)v94);
                          ++v93;
                        }
                        while ( v93 < *(_DWORD *)(v88 + 40) );
                        v92 = v428;
                      }
                      v88 = *(_QWORD *)(v88 + 8);
                      v428 = ++v92;
                    }
                    while ( v88 );
                    goto LABEL_819;
                  }
                  if ( v16 )
                  {
                    if ( (*((_BYTE *)v5 + 44) & 0x40) == 0 )
                    {
                      v126 = "UTF8";
                      if ( !"UTF8" )
                        goto LABEL_240;
                      v127 = &off_1800CDBE0;
                      while ( (unsigned int)sqlite3StrICmp(v16, v126) )
                      {
                        v127 += 2;
                        v126 = *v127;
                        if ( !*v127 )
                          goto LABEL_240;
                      }
                      if ( *((_BYTE *)v127 + 8) )
                        v129 = *((_BYTE *)v127 + 8);
                      LOBYTE(v128) = v129;
                      *(_BYTE *)(*(_QWORD *)(v5[4] + 24LL) + 113LL) = v129;
                      sqlite3SetTextEncoding(v5, v128);
                      if ( !*v127 )
LABEL_240:
                        sqlite3ErrorMsg(v9, "unsupported encoding: %s", v16);
                    }
                    goto LABEL_876;
                  }
                  if ( !(unsigned int)sqlite3ReadSchema(v9) )
                  {
                    v125 = (&off_1800CDBE0)[2 * *(unsigned __int8 *)(*v9 + 100)];
LABEL_632:
                    returnSingleText(v11, v125);
                  }
LABEL_876:
                  result = sqlite3DbFreeNN(v5);
                  if ( v16 )
                    return sqlite3DbFreeNN(v5);
                  return result;
                }
                Index = 0;
                if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
                  sqlite3_hard_heap_limit64(-1);
                v135 = sqlite3_hard_heap_limit64(-1);
LABEL_253:
                v27 = v135;
                goto LABEL_875;
              }
              v136 = v23 - 18;
              if ( !v136 )
              {
                v426 = 0;
                if ( !v16 || !(unsigned int)sqlite3GetInt32(v16, &v426) || (v286 = v426, (int)v426 <= 0) )
                  v286 = 0x7FFFFFFF;
                sqlite3BeginWriteOperation(v9, 0, (unsigned int)v13);
                sqlite3VdbeAddOp3(v11, 71, v286, 1, 0);
                v287 = sqlite3VdbeAddOp3(v11, 62, v13, 0, 0);
                sqlite3VdbeAddOp3(v11, 84, 1, 0, 0);
                sqlite3VdbeAddOp3(v11, 86, 1, -1, 0);
                sqlite3VdbeAddOp3(v11, 59, 1, v287, 0);
                sqlite3VdbeJumpHere(v11, v287);
                goto LABEL_876;
              }
              v137 = v136 - 1;
              if ( v137 )
              {
                v138 = v137 - 1;
                if ( !v138 )
                {
                  if ( !v16 )
                    goto LABEL_876;
                  v269 = sqlite3FindTable(v5, v16, v434);
                  if ( !v269 )
                    goto LABEL_876;
                  v270 = *(_QWORD *)(v269 + 96);
                  v271 = -32768;
                  if ( v270 )
                  {
                    v272 = v5[4];
                    v271 = 0;
                    if ( *(_QWORD *)(v272 + 24) != v270 )
                    {
                      do
                        ++v271;
                      while ( *(_QWORD *)(32LL * v271 + v272 + 24) != v270 );
                    }
                  }
                  *((_DWORD *)v9 + 14) = 5;
                  sqlite3CodeVerifySchema(v9, (unsigned int)v271);
                  v273 = *(_QWORD *)(v269 + 16);
                  v274 = 0;
                  if ( !v273 )
                    goto LABEL_876;
                  do
                  {
                    v123 = *(_QWORD *)(v273 + 72) == 0;
                    v458[0] = "c";
                    v458[1] = "u";
                    LODWORD(v423) = !v123;
                    v458[2] = "pk";
                    LODWORD(v418) = *(_BYTE *)(v273 + 98) != 0;
                    sqlite3VdbeMultiLoad(
                      v11,
                      1,
                      "isisi",
                      v274,
                      *(_QWORD *)v273,
                      v418,
                      v458[*(_DWORD *)(v273 + 100) & 3],
                      v423,
                      v424,
                      v425);
                    v273 = *(_QWORD *)(v273 + 40);
                    ++v274;
                  }
                  while ( v273 );
                  goto LABEL_819;
                }
                if ( v138 != 1 )
                  goto LABEL_836;
                v434 = 0;
                v123 = *((_BYTE *)qword_1800FBAB0 + *v454) == 113;
                v438 = *((_BYTE *)qword_1800FBAB0 + *v454);
                LODWORD(v441) = v123;
                v123 = *v437 == 0;
                v139 = 100;
                *((_DWORD *)v9 + 14) = 6;
                if ( v123 )
                  LODWORD(v13) = -1;
                v436 = 100;
                v426 = v13;
                v432 = 100;
                if ( v16 )
                {
                  if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)v429, &v432) )
                  {
                    v139 = v432;
                    v436 = v432;
                    if ( v432 > 0 )
                      goto LABEL_269;
                    v139 = 100;
                  }
                  else
                  {
                    if ( (int)v13 < 0 )
                      v140 = 0;
                    else
                      v140 = *(_QWORD *)(32LL * (int)v13 + v5[4]);
                    v434 = sqlite3LocateTable(v9, 0, v16, v140);
                    v139 = v432;
                  }
                  v436 = v139;
                }
LABEL_269:
                sqlite3VdbeAddOp3(v11, 71, v139 - 1, 1, 0);
                v141 = 0;
                v435 = 0;
                if ( *((int *)v5 + 10) <= 0 )
                  goto LABEL_486;
                while ( 1 )
                {
                  if ( (int)v13 < 0 || v141 == (_DWORD)v13 )
                  {
                    sqlite3CodeVerifySchema(v9, (unsigned int)v141);
                    v142 = 32LL * v435;
                    *((_BYTE *)v9 + 35) = 0;
                    v143 = v5[4];
                    v429 = v142;
                    v144 = *(_QWORD *)(v142 + v143 + 24);
                    v145 = 0;
                    v446 = v144;
                    v146 = *(_QWORD **)(v144 + 16);
                    if ( v146 )
                    {
                      do
                      {
                        v147 = v146[2];
                        if ( !v434 || v434 == v147 )
                        {
                          if ( (*(_BYTE *)(v147 + 48) & 0x80) == 0 )
                            ++v145;
                          v148 = *(_QWORD *)(v147 + 16);
                          while ( v148 )
                          {
                            v148 = *(_QWORD *)(v148 + 40);
                            ++v145;
                          }
                        }
                        v146 = (_QWORD *)*v146;
                      }
                      while ( v146 );
                      if ( v145 )
                      {
                        v149 = v145 + 1;
                        if ( !v434 )
                          v149 = v145;
                        v150 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v149 + 4);
                        v151 = v150;
                        if ( v150 )
                        {
                          v152 = 0;
                          if ( v434 )
                          {
                            v152 = 1;
                            v150[1] = 0;
                          }
                          v153 = *(_QWORD **)(v446 + 16);
                          if ( v153 )
                          {
                            v154 = v434;
                            do
                            {
                              v155 = v153[2];
                              if ( !v154 || v154 == v155 )
                              {
                                if ( *(char *)(v155 + 48) >= 0 )
                                {
                                  v156 = v152++;
                                  v150[v156 + 1] = *(_DWORD *)(v155 + 40);
                                }
                                for ( ii = *(_QWORD *)(v155 + 16); ii; ii = *(_QWORD *)(ii + 40) )
                                  v150[++v152] = *(_DWORD *)(ii + 88);
                              }
                              v153 = (_QWORD *)*v153;
                            }
                            while ( v153 );
                            v11 = Index;
                            v9 = v455;
                          }
                          *v150 = v152;
                          if ( *((_DWORD *)v9 + 14) < v152 + 8 )
                            *((_DWORD *)v9 + 14) = v152 + 8;
                          *((_BYTE *)v9 + 31) = 0;
                          *((_DWORD *)v9 + 10) = 0;
                          v158 = sqlite3VdbeAddOp3(v11, 155, 1, v152, 8);
                          sqlite3VdbeChangeP4(v11, v158, v151, 4294967282LL);
                          v159 = *(int *)(v11 + 144);
                          if ( (int)v159 > 0 )
                            *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v159 - 22) = (unsigned __int8)v435;
                          v160 = sqlite3VdbeAddOp3(v11, 50, 2, 0, 0);
                          v161 = sqlite3MPrintf(v5, "*** in database %s ***\n", *(const char **)(v429 + v5[4]));
                          v162 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                          sqlite3VdbeChangeP4(v11, v162, v161, 4294967290LL);
                          sqlite3VdbeAddOp3(v11, 111, 2, 3, 3);
                          integrityCheckResultRow(v11);
                          sqlite3VdbeJumpHere(v11, v160);
                          sqlite3VdbeLoadString(v11, 2, "wrong # of entries in index ");
                          v163 = 0;
                          v429 = *(_QWORD *)(v446 + 16);
                          if ( v429 )
                          {
                            v164 = v434;
                            v165 = (_QWORD *)v429;
                            v166 = v434 != 0;
                            LODWORD(v442) = v166;
                            do
                            {
                              v167 = v165[2];
                              if ( !v164 || v164 == v167 )
                              {
                                v123 = *(_BYTE *)(v167 + 48) >= 0;
                                v168 = v166;
                                v432 = v166;
                                if ( v123 )
                                {
                                  ++v166;
                                  v169 = (const char **)(v167 + 16);
                                  LODWORD(v442) = v166;
                                }
                                else
                                {
                                  v170 = (const char **)(v167 + 16);
                                  v171 = *(_QWORD *)(v167 + 16);
                                  if ( v171 )
                                  {
                                    do
                                    {
                                      v169 = v170;
                                      if ( (*(_DWORD *)(v171 + 100) & 3) == 2 )
                                        break;
                                      v171 = *(_QWORD *)(v171 + 40);
                                      v432 = ++v168;
                                    }
                                    while ( v171 );
                                    v166 = v442;
                                  }
                                  else
                                  {
                                    v169 = v170;
                                  }
                                }
                                v172 = *v169;
                                v433 = v172;
                                if ( v172 )
                                {
                                  v173 = v166 + 8;
                                  do
                                  {
                                    if ( !*((_QWORD *)v172 + 9) )
                                    {
                                      v174 = sqlite3VdbeAddOp3(v11, 53, v173, 0, v168 + 8);
                                      sqlite3VdbeLoadString(v11, 4, *(_QWORD *)v433);
                                      sqlite3VdbeAddOp3(v11, 111, 4, 2, 3);
                                      integrityCheckResultRow(v11);
                                      sqlite3VdbeJumpHere(v11, v174);
                                      v166 = v442;
                                      v163 = 0;
                                      v172 = v433;
                                    }
                                    v172 = (const char *)*((_QWORD *)v172 + 5);
                                    ++v166;
                                    v168 = v432;
                                    ++v173;
                                    LODWORD(v442) = v166;
                                    v433 = v172;
                                  }
                                  while ( v172 );
                                }
                                v164 = v434;
                              }
                              v165 = (_QWORD *)*v165;
                            }
                            while ( v165 );
                            v5 = (_QWORD *)v447;
                            v9 = v455;
                          }
                          v175 = *(_QWORD *)(v446 + 16);
                          v429 = v175;
                          if ( !v175 )
                            goto LABEL_464;
                          v176 = v434;
                          while ( 1 )
                          {
                            v177 = *(_QWORD *)(v175 + 16);
                            v437 = (const char **)v177;
                            v445 = v163;
                            v428 = v163;
                            if ( v176 && v176 != v177 || *(_BYTE *)(v177 + 63) != (_BYTE)v163 )
                              goto LABEL_463;
                            if ( v438 == 113 || *(char *)(v177 + 48) >= 0 )
                            {
                              v451 = v163;
                              v432 = v163;
                            }
                            else
                            {
                              v178 = *(_QWORD *)(v177 + 16);
                              v451 = v178;
                              if ( v178 )
                              {
                                do
                                {
                                  if ( (*(_DWORD *)(v178 + 100) & 3) == 2 )
                                    break;
                                  v178 = *(_QWORD *)(v178 + 40);
                                }
                                while ( v178 );
                                v451 = v178;
                              }
                              TempRange = sqlite3GetTempRange(v9, *(unsigned __int16 *)(v178 + 94));
                              v181 = *(unsigned __int16 *)(v180 + 94) - 1;
                              v432 = TempRange;
                              sqlite3VdbeAddOp3(v11, 75, 1, TempRange, TempRange + v181);
                              LODWORD(v177) = (_DWORD)v437;
                              v163 = 0;
                            }
                            sqlite3OpenTableAndIndices(
                              (_DWORD)v9,
                              v177,
                              112,
                              0,
                              1,
                              v163,
                              (__int64)&v445,
                              (__int64)&v428);
                            sqlite3VdbeAddOp3(v11, 71, 0, 7, 0);
                            if ( v437[2] )
                            {
                              v182 = 8;
                              v183 = v437[2];
                              do
                              {
                                sqlite3VdbeAddOp3(v11, 71, 0, v182, 0);
                                v183 = (const char *)*((_QWORD *)v183 + 5);
                                ++v182;
                              }
                              while ( v183 );
                              v5 = (_QWORD *)v447;
                              v9 = v455;
                            }
                            sqlite3VdbeAddOp3(v11, 36, v445, 0, 0);
                            v453 = sqlite3VdbeAddOp3(v11, 86, 7, 1, 0);
                            if ( *((char *)v437 + 48) < 0 )
                            {
                              for ( jj = v437[2];
                                    jj && (*((_DWORD *)jj + 25) & 3) != 2;
                                    jj = (const char *)*((_QWORD *)jj + 5) )
                              {
                                ;
                              }
                              v188 = *((unsigned __int16 *)jj + 48) - 1;
                            }
                            else
                            {
                              v184 = *((__int16 *)v437 + 27);
                              v185 = -1;
                              if ( v184 > 0 )
                              {
                                v186 = 0;
                                do
                                {
                                  v187 = v185 + 1;
                                  if ( (v437[1][24 * v186 + 18] & 0x20) != 0 )
                                    v187 = v185;
                                  v186 = (unsigned int)(v186 + 1);
                                  v185 = v187;
                                }
                                while ( (int)v186 < v184 );
                              }
                              v188 = v185 - 1;
                              if ( v185 != *((__int16 *)v437 + 26) )
                                v188 = v185;
                            }
                            if ( v188 >= 0 )
                            {
                              sqlite3VdbeAddOp3(v11, 94, v445, v188, 3);
                              LastOp = sqlite3VdbeGetLastOp(v11);
                              if ( *(_DWORD *)(LastOp + 12) == 3 && *(_BYTE *)LastOp == 94 )
                                *(_WORD *)(LastOp + 2) |= 0x80u;
                            }
                            if ( v438 != 113 && v451 )
                            {
                              v191 = v432;
                              v192 = sqlite3VdbeAddOp4Int(v11, 41, v445, 0, v432, *(unsigned __int16 *)(v451 + 94));
                              sqlite3VdbeAddOp3(v11, 50, v191, 0, 0);
                              v193 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v437);
                              v194 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                              sqlite3VdbeChangeP4(v11, v194, v193, 4294967290LL);
                              integrityCheckResultRow(v11);
                              sqlite3VdbeJumpHere(v11, v192);
                              sqlite3VdbeJumpHere(v11, v192 + 1);
                              v195 = 0;
                              v196 = 0;
                              if ( !*(_WORD *)(v451 + 94) )
                                goto LABEL_363;
                              v197 = v445;
                              v198 = v451;
                              v199 = v432;
                              do
                              {
                                sqlite3ExprCodeLoadIndexColumn((_DWORD)v9, v198, v197, v196, v199 + v196);
                                ++v196;
                              }
                              while ( v196 < *(unsigned __int16 *)(v198 + 94) );
                              v11 = Index;
                              v5 = (_QWORD *)v447;
                            }
                            v195 = 0;
LABEL_363:
                            v200 = v437;
                            v201 = 0;
                            v202 = (_DWORD)v437[6] & 0x10000;
                            v203 = *((_WORD *)v437 + 27) > 0;
                            String = v202;
                            while ( 1 )
                            {
                              v431 = v201;
                              if ( !v203 )
                                break;
                              if ( (_DWORD)v201 == *((__int16 *)v200 + 26) )
                                goto LABEL_419;
                              v204 = (__int64)&v200[1][24 * (int)v201];
                              v433 = (const char *)v204;
                              v205 = (char *)(v204 + 12);
                              if ( v202 )
                              {
                                v206 = *(_DWORD *)(v204 + 8) & 0xF0;
                                v207 = v206 > 0x10;
                                v449 = v206 > 0x10;
                              }
                              else if ( *v205 <= 65 )
                              {
                                v207 = 0;
                                v449 = 0;
                              }
                              else
                              {
                                v207 = 1;
                                v449 = 1;
                              }
                              if ( (*(_BYTE *)(v204 + 8) & 0xF) != 0 || (_DWORD)v207 )
                              {
                                v123 = (*(_BYTE *)(v204 + 18) & 0x20) == 0;
                                LODWORD(v442) = 5;
                                if ( v123 )
                                {
                                  if ( *(_WORD *)(v204 + 16) )
                                  {
                                    v452 = 0;
                                    v210 = sqlite3ColumnExpr(v200, v204, v207, v205);
                                    if ( v210 )
                                    {
                                      LOBYTE(v205) = *v205;
                                      LOBYTE(v207) = *((_BYTE *)v5 + 100);
                                      valueFromExpr((_DWORD)v5, v210, v207, (_DWORD)v205, (__int64)&v452, v419);
                                      if ( v452 )
                                      {
                                        LODWORD(v442) = *((unsigned __int8 *)qword_1800FE430
                                                        + (*(_WORD *)(v452 + 20) & 0x3F));
                                        sqlite3ValueFree(v452);
                                      }
                                    }
                                    v201 = v431;
                                  }
                                  v123 = *((_BYTE *)v200 + 48) >= 0;
                                  IndexKey = v445;
                                  if ( v123 )
                                  {
                                    v212 = sqlite3TableColumnToStorage(v200, v201, v207, v205);
                                    v208 = IndexKey;
                                  }
                                  else
                                  {
                                    for ( kk = v200[2];
                                          kk && (*((_DWORD *)kk + 25) & 3) != 2;
                                          kk = (const char *)*((_QWORD *)kk + 5) )
                                    {
                                      ;
                                    }
                                    v212 = sqlite3TableColumnToIndex(kk, v201);
                                  }
                                  v209 = v212;
                                }
                                else
                                {
                                  sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v200, v445, v201, 3);
                                  v208 = -1;
                                  IndexKey = -1;
                                  v209 = 3;
                                }
                                v213 = *((_DWORD *)v9 + 17) - 1;
                                v443 = v209;
                                v444 = v213;
                                v214 = v213 - 1;
                                v215 = v433;
                                *((_DWORD *)v9 + 17) = v214;
                                v440 = v214;
                                if ( (v215[8] & 0xF) != 0 )
                                {
                                  v216 = sqlite3VdbeAddOp4Int(v11, 18, v208, v214, v209, v442);
                                  v217 = IndexKey;
                                  v218 = *(int *)(v11 + 144);
                                  LODWORD(v452) = v216;
                                  if ( IndexKey >= 0 )
                                  {
                                    if ( (int)v218 > 0 )
                                      *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v218 - 22) = 13;
                                    sqlite3VdbeAddOp3(v11, 94, v217, v443, 3);
                                    sqlite3ColumnDefault(v11, v200, v431, 3);
                                    v216 = sqlite3VdbeAddOp3(v11, 51, 3, v440, 0);
                                  }
                                  else if ( (int)v218 > 0 )
                                  {
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v218 - 22) = 15;
                                  }
                                  v448 = v216;
                                  v219 = sqlite3MPrintf(v5, "NULL value in %s.%s", *v200, *(const char **)v433);
                                  v220 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                                  sqlite3VdbeChangeP4(v11, v220, v219, 4294967290LL);
                                  v221 = v449;
                                  if ( v449 )
                                  {
                                    sqlite3VdbeAddOp3(v11, 9, 0, v444, 0);
                                    sqlite3VdbeJumpHere(v11, (unsigned int)v452);
                                    sqlite3VdbeJumpHere(v11, v448);
                                    v215 = v433;
                                    v200 = v437;
                                    v214 = v440;
                                    goto LABEL_397;
                                  }
                                  v200 = v437;
                                  v215 = v433;
                                  v214 = v440;
                                }
                                else
                                {
LABEL_397:
                                  v221 = v449;
                                }
                                if ( String )
                                {
                                  if ( v221 )
                                  {
                                    sqlite3VdbeAddOp4Int(v11, 18, IndexKey, v214, v443, v442);
                                    v222 = *(int *)(v11 + 144);
                                    v223 = v433;
                                    if ( (int)v222 > 0 )
                                      *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v222 - 22) = *((unsigned __int8 *)&qword_1800FBAB0[34]
                                                                                            + ((*((_DWORD *)v433 + 2) >> 4)
                                                                                             & 0xFu)
                                                                                            + 3);
                                    v224 = sqlite3MPrintf(
                                             v5,
                                             "non-%s value in %s.%s",
                                             off_18010E5A0[((*((_DWORD *)v223 + 2) >> 4) & 0xFu) - 1],
                                             *v200,
                                             *(const char **)&v200[1][24 * v431]);
                                    goto LABEL_416;
                                  }
LABEL_417:
                                  sqlite3VdbeResolveLabel(v11, v444);
                                  integrityCheckResultRow(v11);
                                  sqlite3VdbeResolveLabel(v11, v440);
                                  LODWORD(v201) = v431;
                                  v195 = 0;
                                  v200 = v437;
                                  goto LABEL_418;
                                }
                                v225 = v215[12];
                                if ( v225 == 66 )
                                {
                                  sqlite3VdbeAddOp4Int(v11, 18, IndexKey, v214, v443, v442);
                                  v226 = *(int *)(v11 + 144);
                                  if ( (int)v226 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v226 - 22) = 28;
                                  v224 = sqlite3MPrintf(
                                           v5,
                                           "NUMERIC value in %s.%s",
                                           *v200,
                                           *(_QWORD *)&v200[1][24 * v431]);
                                }
                                else
                                {
                                  if ( v225 < 67 )
                                    goto LABEL_417;
                                  sqlite3VdbeAddOp4Int(v11, 18, IndexKey, v214, v443, v442);
                                  v227 = *(int *)(v11 + 144);
                                  if ( (int)v227 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v227 - 22) = 27;
                                  if ( IndexKey >= 0 )
                                    sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v200, v445, v431, 3);
                                  v228 = sqlite3VdbeAddOp3(v11, 96, 3, 1, 0);
                                  sqlite3VdbeChangeP4(v11, v228, "C", 0xFFFFFFFFLL);
                                  sqlite3VdbeAddOp4Int(v11, 18, -1, v440, 3, v442);
                                  v229 = *(int *)(v11 + 144);
                                  if ( (int)v229 > 0 )
                                    *(_WORD *)(*(_QWORD *)(v11 + 136) + 24 * v229 - 22) = 28;
                                  v224 = sqlite3MPrintf(
                                           v5,
                                           "TEXT value in %s.%s",
                                           *v200,
                                           *(_QWORD *)&v200[1][24 * v431]);
                                }
LABEL_416:
                                v230 = v224;
                                v231 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                                sqlite3VdbeChangeP4(v11, v231, v230, 4294967290LL);
                                goto LABEL_417;
                              }
LABEL_418:
                              v202 = String;
LABEL_419:
                              v201 = (unsigned int)(v201 + 1);
                              v203 = (int)v201 < *((__int16 *)v200 + 27);
                            }
                            v232 = v200[4];
                            if ( v232 && (v5[6] & 0x200LL) == 0 )
                            {
                              v233 = (const char *)sqlite3ExprListDup(v5, v232, 0);
                              v195 = 0;
                              v433 = v233;
                              v234 = v233;
                              if ( !*((_BYTE *)v5 + 103) )
                              {
                                v444 = *((_DWORD *)v9 + 17) - 1;
                                v448 = v444 - 1;
                                *((_DWORD *)v9 + 17) = v444 - 1;
                                *((_DWORD *)v9 + 16) = v445 + 1;
                                v235 = *(_DWORD *)v233 - 1;
                                if ( *(_DWORD *)v234 - 1 > 0 )
                                {
                                  v236 = v444;
                                  v237 = v235;
                                  v238 = v234;
                                  do
                                    sqlite3ExprIfFalse(v9, *(_QWORD *)&v238[32 * v237-- + 8], v236, 0);
                                  while ( v237 > 0 );
                                  v11 = Index;
                                  v5 = (_QWORD *)v447;
                                  v200 = v437;
                                  v234 = v433;
                                }
                                sqlite3ExprIfTrue(v9, *((_QWORD *)v234 + 1), v448, 16);
                                sqlite3VdbeResolveLabel(v11, v444);
                                *((_DWORD *)v9 + 16) = 0;
                                v239 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v200);
                                v240 = sqlite3VdbeAddOp3(v11, 117, 0, 3, 0);
                                sqlite3VdbeChangeP4(v11, v240, v239, 4294967290LL);
                                integrityCheckResultRow(v11);
                                sqlite3VdbeResolveLabel(v11, v448);
                                v234 = v433;
                                v195 = 0;
                                v200 = v437;
                              }
                              if ( v234 )
                              {
                                exprListDeleteNN(v5, v234);
                                v195 = 0;
                              }
                            }
                            if ( v438 != 113 )
                            {
                              v241 = v200[2];
                              v242 = 0;
                              v431 = 0;
                              v243 = -1;
                              v433 = v241;
                              if ( v241 )
                              {
                                v244 = v437;
                                do
                                {
                                  v245 = *((_DWORD *)v9 + 17) - 1;
                                  v444 = v195;
                                  LODWORD(v452) = v245;
                                  *((_DWORD *)v9 + 17) = v245;
                                  if ( (const char *)v451 != v241 )
                                  {
                                    IndexKey = sqlite3GenerateIndexKey(
                                                 (_DWORD)v9,
                                                 (_DWORD)v241,
                                                 v445,
                                                 0,
                                                 v195,
                                                 (__int64)&v444,
                                                 v242,
                                                 v243);
                                    v442 = (__int64)v241;
                                    sqlite3VdbeAddOp3(v11, 86, v431 + 8, 1, 0);
                                    v420 = *((unsigned __int16 *)v241 + 48);
                                    v448 = v428 + v431;
                                    v246 = sqlite3VdbeAddOp4Int(v11, 29, v428 + v431, v452, IndexKey, v420);
                                    sqlite3VdbeLoadString(v11, 3, "row ");
                                    sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                    sqlite3VdbeLoadString(v11, 4, " missing from index ");
                                    sqlite3VdbeAddOp3(v11, 111, 4, 3, 3);
                                    String = sqlite3VdbeLoadString(v11, 4, *(_QWORD *)v433);
                                    sqlite3VdbeAddOp3(v11, 111, 4, 3, 3);
                                    v449 = integrityCheckResultRow(v11);
                                    sqlite3VdbeJumpHere(v11, v246);
                                    if ( *((char *)v244 + 48) >= 0 )
                                    {
                                      sqlite3VdbeAddOp3(v11, 142, v448, 3, 0);
                                      v247 = sqlite3VdbeAddOp3(
                                               v11,
                                               53,
                                               3,
                                               0,
                                               (unsigned int)*((unsigned __int16 *)v433 + 48) + IndexKey - 1);
                                      sqlite3VdbeLoadString(v11, 3, "rowid not at end-of-record for row ");
                                      sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                      sqlite3VdbeLoadString(v11, 4, " of index ");
                                      sqlite3VdbeAddOp3(v11, 9, 0, String - 1, 0);
                                      sqlite3VdbeJumpHere(v11, v247);
                                    }
                                    v241 = v433;
                                    v248 = 0;
                                    v440 = 0;
                                    if ( *((_WORD *)v433 + 47) )
                                    {
                                      v249 = 0;
                                      do
                                      {
                                        if ( *(char **)(*((_QWORD *)v241 + 8) + 8LL * v249) != "BINARY" )
                                        {
                                          if ( !v248 )
                                          {
                                            v440 = *((_DWORD *)v9 + 17) - 1;
                                            *((_DWORD *)v9 + 17) = v440;
                                          }
                                          sqlite3VdbeAddOp3(v11, 94, v431 + v428, v249, 3);
                                          sqlite3VdbeAddOp3(v11, 52, 3, v440, v249 + IndexKey);
                                          v248 = v440;
                                        }
                                        ++v249;
                                      }
                                      while ( v249 < *((unsigned __int16 *)v241 + 47) );
                                      v244 = v437;
                                      if ( v248 )
                                      {
                                        v250 = sqlite3VdbeAddOp3(v11, 9, 0, 0, 0);
                                        sqlite3VdbeResolveLabel(v11, v440);
                                        sqlite3VdbeLoadString(v11, 3, "row ");
                                        sqlite3VdbeAddOp3(v11, 111, 7, 3, 3);
                                        sqlite3VdbeLoadString(v11, 4, " values differ from index ");
                                        sqlite3VdbeAddOp3(v11, 9, 0, String - 1, 0);
                                        sqlite3VdbeJumpHere(v11, v250);
                                        v241 = v433;
                                      }
                                    }
                                    if ( v241[98] )
                                    {
                                      v251 = *((_DWORD *)v9 + 17) - 1;
                                      *((_DWORD *)v9 + 17) = v251;
                                      v440 = v251;
                                      if ( *((_WORD *)v241 + 47) )
                                      {
                                        v252 = 0;
                                        do
                                        {
                                          v253 = *((_QWORD *)v241 + 1);
                                          if ( *(__int16 *)(v253 + 2LL * v252) < 0
                                            || (v244[1][24 * *(__int16 *)(v253 + 2LL * v252) + 8] & 0xF) == 0 )
                                          {
                                            sqlite3VdbeAddOp3(v11, 50, v252 + IndexKey, v251, 0);
                                            v251 = v440;
                                          }
                                          ++v252;
                                        }
                                        while ( v252 < *((unsigned __int16 *)v241 + 47) );
                                        v9 = v455;
                                      }
                                      v254 = sqlite3VdbeAddOp3(v11, 39, v431 + v428, 0, 0);
                                      sqlite3VdbeAddOp3(v11, 9, 0, v440, 0);
                                      sqlite3VdbeJumpHere(v11, v254);
                                      v241 = v433;
                                      sqlite3VdbeAddOp4Int(
                                        v11,
                                        41,
                                        v431 + v428,
                                        v440,
                                        IndexKey,
                                        *((unsigned __int16 *)v433 + 47));
                                      sqlite3VdbeLoadString(v11, 3, "non-unique entry in index ");
                                      sqlite3VdbeAddOp3(v11, 9, 0, String, 0);
                                      sqlite3VdbeResolveLabel(v11, v440);
                                    }
                                    sqlite3VdbeJumpHere(v11, v449);
                                    if ( v444 )
                                    {
                                      sqlite3VdbeResolveLabel(v9[2], v444);
                                      v195 = 0;
                                    }
                                    v242 = v442;
                                    v243 = IndexKey;
                                  }
                                  v241 = (const char *)*((_QWORD *)v241 + 5);
                                  ++v431;
                                  v433 = v241;
                                }
                                while ( v241 );
                                v5 = (_QWORD *)v447;
                              }
                            }
                            v255 = v453;
                            sqlite3VdbeAddOp3(v11, 39, v445, v453, v195);
                            sqlite3VdbeJumpHere(v11, (unsigned int)(v255 - 1));
                            v163 = 0;
                            if ( v451 )
                              sqlite3ReleaseTempRange(v9, (unsigned int)v432, *(unsigned __int16 *)(v451 + 94));
                            v176 = v434;
LABEL_463:
                            v175 = *(_QWORD *)v429;
                            v429 = v175;
                            if ( !v175 )
                            {
LABEL_464:
                              v256 = *(_QWORD **)(v446 + 16);
                              if ( v256 )
                              {
                                v257 = v434;
                                do
                                {
                                  v258 = v256[2];
                                  if ( (!v257 || v257 == v258) && *(_BYTE *)(v258 + 63) == 1 )
                                  {
                                    if ( *(__int16 *)(v258 + 54) > (__int16)v163
                                      || (ElementWithHash = findElementWithHash(v5 + 69, **(_QWORD **)(v258 + 72), 0),
                                          v163 = 0,
                                          *(_QWORD *)(ElementWithHash + 16)) )
                                    {
                                      if ( *(_BYTE *)(v258 + 63) == 1 || *(__int16 *)(v258 + 54) <= (__int16)v163 )
                                      {
                                        viewGetColumnNames(v9, v258);
                                        v163 = 0;
                                      }
                                      v260 = *(_QWORD *)(v258 + 80);
                                      if ( v260 )
                                      {
                                        v261 = *(__int64 **)(v260 + 16);
                                        if ( v261 )
                                        {
                                          v262 = *v261;
                                          if ( v262 )
                                          {
                                            if ( *(int *)v262 >= 4 && *(_QWORD *)(v262 + 192) != v163 )
                                            {
                                              sqlite3VdbeAddOp3(v11, 174, v435, 3, (_DWORD)v441);
                                              ++*(_DWORD *)(v258 + 44);
                                              sqlite3VdbeAppendP4(v11, v258, 4294967280LL);
                                              v263 = sqlite3VdbeAddOp3(v11, 50, 3, 0, 0);
                                              integrityCheckResultRow(v11);
                                              sqlite3VdbeJumpHere(v11, v263);
                                              v163 = 0;
                                            }
                                          }
                                        }
                                      }
                                    }
                                    v257 = v434;
                                  }
                                  v256 = (_QWORD *)*v256;
                                }
                                while ( v256 );
                              }
                              LODWORD(v13) = v426;
                              goto LABEL_483;
                            }
                          }
                        }
LABEL_485:
                        v16 = v450;
LABEL_486:
                        v264 = sqlite3VdbeAddOpList(v11, 7, qword_1800FAF30);
                        v265 = 0;
                        if ( v264 )
                        {
                          *(_DWORD *)(v264 + 8) = 1 - v436;
                          *(_QWORD *)(v264 + 64) = "ok";
                          *(_BYTE *)(v264 + 49) = -1;
                          *(_BYTE *)(v264 + 121) = -1;
                          v266 = sqlite3ErrStr(11);
                          *(_QWORD *)(v267 + 136) = v266;
                        }
                        v268 = qword_18010FAB0;
                        if ( *(_BYTE *)(*(_QWORD *)v11 + 103LL) == v265 )
                          v268 = *(__int64 **)(v11 + 136);
                        *((_DWORD *)v268 + 3) = *(_DWORD *)(v11 + 144) - 2;
                        goto LABEL_876;
                      }
                    }
LABEL_483:
                    v141 = v435;
                  }
                  v435 = ++v141;
                  if ( v141 >= *((_DWORD *)v5 + 10) )
                    goto LABEL_485;
                }
              }
              if ( !v16 )
                goto LABEL_876;
              Index = sqlite3FindIndex(v5, v16, v434);
              v275 = Index;
              if ( !Index )
              {
                v276 = sqlite3LocateTable(v9, 2, v16, v434);
                if ( !v276 )
                  goto LABEL_876;
                if ( *(char *)(v276 + 48) >= 0 )
                  goto LABEL_876;
                v275 = *(_QWORD *)(v276 + 16);
                Index = v275;
                if ( !v275 )
                  goto LABEL_876;
                do
                {
                  if ( (*(_DWORD *)(v275 + 100) & 3) == 2 )
                    break;
                  v275 = *(_QWORD *)(v275 + 40);
                }
                while ( v275 );
                Index = v275;
                if ( !v275 )
                  goto LABEL_876;
              }
              v277 = *(_QWORD *)(v275 + 48);
              v278 = -32768;
              if ( v277 )
              {
                v279 = v5[4];
                v278 = 0;
                if ( *(_QWORD *)(v279 + 24) != v277 )
                {
                  do
                    ++v278;
                  while ( *(_QWORD *)(32LL * v278 + v279 + 24) != v277 );
                }
              }
              v280 = *((_QWORD *)v433 + 2);
              v281 = (unsigned __int16 *)(v275 + 96);
              if ( !v280 )
                v281 = (unsigned __int16 *)(v275 + 94);
              v282 = *v281;
              LODWORD(v441) = v282;
              *((_DWORD *)v9 + 14) = v280 != 0 ? 6 : 3;
              v429 = *(_QWORD *)(v275 + 24);
              sqlite3CodeVerifySchema(v9, (unsigned int)v278);
              v283 = 0;
              if ( !v282 )
                goto LABEL_876;
              do
              {
                v284 = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v283);
                if ( (v284 & 0x8000u) == 0LL )
                  v285 = *(_QWORD *)(*(_QWORD *)(v429 + 8) + 24 * v284);
                else
                  v285 = 0;
                LODWORD(v416) = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v283);
                sqlite3VdbeMultiLoad(v11, 1, "iisX", v283, v416, v285, v422, v423, v424, v425);
                if ( *((_QWORD *)v433 + 2) )
                {
                  LODWORD(v421) = v283 < *(unsigned __int16 *)(Index + 94);
                  sqlite3VdbeMultiLoad(
                    v11,
                    4,
                    "isiX",
                    *(unsigned __int8 *)(*(_QWORD *)(Index + 56) + v283),
                    *(_QWORD *)(*(_QWORD *)(Index + 64) + 8LL * v283),
                    v421,
                    v422,
                    v423,
                    v424,
                    v425);
                }
                sqlite3VdbeAddOp3(v11, 84, 1, *((_DWORD *)v9 + 14), 0);
                ++v283;
              }
              while ( (int)v283 < (int)v441 );
LABEL_818:
              v5 = (_QWORD *)v447;
              goto LABEL_819;
            }
            if ( v16 )
            {
              v289 = -1;
              do
                ++v289;
              while ( v16[v289] );
              v290 = v289 & 0x3FFFFFFF;
              v288 = 0;
              v429 = v290;
              while ( 1 )
              {
                if ( v288 == 6 )
                  goto LABEL_536;
                v291 = off_1800CC948[v288];
                if ( !v291 )
                  goto LABEL_536;
                if ( !(unsigned int)sqlite3_strnicmp(v16, v291, v290) )
                  break;
                v290 = v429;
                ++v288;
              }
              if ( v288 == 2 )
              {
                if ( (v5[6] & 0x10000000) == 0 )
                  goto LABEL_539;
LABEL_536:
                v288 = -1;
                goto LABEL_537;
              }
              if ( v288 != -1 )
                goto LABEL_539;
            }
            else
            {
              v288 = -1;
            }
LABEL_537:
            if ( !*((_DWORD *)v437 + 2) )
            {
              LODWORD(v13) = 0;
              *((_DWORD *)v437 + 2) = 1;
            }
LABEL_539:
            v292 = *((_DWORD *)v5 + 10) - 1;
            if ( v292 >= 0 )
            {
              do
              {
                if ( *(_QWORD *)(32LL * (unsigned int)v292 + v5[4] + 8)
                  && (v292 == (_DWORD)v13 || !*((_DWORD *)v437 + 2)) )
                {
                  sqlite3VdbeUsesBtree(v11, (unsigned int)v292);
                  sqlite3VdbeAddOp3(v293, 4, v292, 1, v288);
                }
                --v292;
              }
              while ( v292 >= 0 );
              v16 = v450;
            }
            v294 = 1;
LABEL_606:
            sqlite3VdbeAddOp3(v11, 84, v294, 1, 0);
            goto LABEL_876;
          }
          if ( (unsigned __int8)v23 > 0x22u )
          {
            if ( (unsigned __int8)v23 <= 0x28u )
            {
              if ( (_BYTE)v23 == 40 )
              {
                v429 = 0;
                if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
                  sqlite3_limit(v5, 11, v429 & 0x7FFFFFFF);
                v27 = *((int *)v5 + 45);
                goto LABEL_875;
              }
              v354 = v23 - 35;
              if ( !v354 )
              {
                if ( !v16 )
                {
                  v27 = LOBYTE(v441[v14 + 2]) - 1LL;
                  goto LABEL_875;
                }
                if ( !*((_BYTE *)v5 + 101) )
                {
                  sqlite3ErrorMsg(v9, "Safety level may not be changed inside a transaction");
                  goto LABEL_876;
                }
                if ( (_DWORD)v13 != 1 )
                {
                  LOBYTE(v21) = 1;
                  v399 = getSafetyLevel(v16, 0, v21);
                  v400 = v441;
                  v401 = (v399 + 1) & 7;
                  if ( !v401 )
                    LOBYTE(v401) = 1;
                  LOBYTE(v441[v14 + 2]) = v401;
                  BYTE1(v400[v14 + 2]) = 1;
                  goto LABEL_92;
                }
                goto LABEL_876;
              }
              v355 = v354 - 1;
              if ( v355 )
              {
                v356 = v355 - 1;
                if ( !v356 )
                {
                  v363 = v434;
                  v364 = v434;
                  *((_DWORD *)v9 + 14) = 6;
                  sqlite3CodeVerifyNamedSchema(v9, v364);
                  for ( mm = 0; mm < *((_DWORD *)v5 + 10); ++mm )
                  {
                    v366 = mm;
                    if ( v363 )
                    {
                      v367 = *(_QWORD *)(32LL * mm + v5[4]);
                      if ( !v367 || (unsigned int)sqlite3StrICmp(v363, v367) )
                        continue;
                    }
                    v368 = *(_QWORD *)(32 * v366 + v5[4] + 24) + 8LL;
                    v369 = *(_DWORD *)(*(_QWORD *)(32 * v366 + v5[4] + 24) + 12LL);
LABEL_768:
                    if ( v369 )
                    {
                      for ( nn = *(_QWORD **)(v368 + 8); nn; nn = (_QWORD *)*nn )
                      {
                        v371 = nn[2];
                        if ( !*(_WORD *)(v371 + 54) )
                        {
                          --v369;
                          v372 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v371);
                          Index = v372;
                          if ( v372 )
                          {
                            v429 = 0;
                            sqlite3LockAndPrepare((_DWORD)v5, v372, -1, 0, 0, (__int64)&v429, 0);
                            sqlite3_finalize(v429);
                            sqlite3DbFreeNN(v5);
                          }
                          if ( *((_BYTE *)v5 + 103) )
                          {
                            sqlite3ErrorMsg(v5[44], "out of memory", v373, 0);
                            *(_DWORD *)(v5[44] + 24LL) = 7;
                          }
                          v368 = *(_QWORD *)(32LL * mm + v5[4] + 24) + 8LL;
                          goto LABEL_768;
                        }
                      }
                    }
                    v374 = *(_QWORD **)(v368 + 8);
                    v429 = (__int64)v374;
                    if ( v374 )
                    {
                      do
                      {
                        v375 = (_QWORD *)v374[2];
                        if ( !v16 || *v375 && !(unsigned int)sqlite3StrICmp(v16, *v375) )
                        {
                          if ( *((_BYTE *)v375 + 63) == 2 )
                          {
                            v376 = "view";
                          }
                          else if ( *((_BYTE *)v375 + 63) == 1 )
                          {
                            v376 = "virtual";
                          }
                          else
                          {
                            v376 = "shadow";
                            if ( (v375[6] & 0x1000) == 0 )
                              v376 = "table";
                          }
                          Index = (__int64)v376;
                          v377 = *((_DWORD *)v375 + 12);
                          v453 = (v377 >> 7) & 1;
                          v378 = (const char *)*v375;
                          LODWORD(v441) = HIWORD(v377) & 1;
                          v446 = (__int64)v378;
                          if ( (unsigned int)sqlite3_strnicmp(v378, "sqlite_", 7) )
                          {
                            v380 = (const char *)*v375;
                          }
                          else if ( (unsigned int)sqlite3StrICmp(v446 + 7, "master") )
                          {
                            if ( !(unsigned int)sqlite3StrICmp(v379 + 7, "temp_master") )
                              v380 = "sqlite_temp_schema";
                          }
                          else
                          {
                            v380 = "sqlite_schema";
                          }
                          LODWORD(v423) = v453;
                          sqlite3VdbeMultiLoad(
                            v11,
                            1,
                            "sssiii",
                            *(_QWORD *)(32LL * mm + v5[4]),
                            v380,
                            Index,
                            *((__int16 *)v375 + 27),
                            v423,
                            (_DWORD)v441,
                            v425);
                          v374 = (_QWORD *)v429;
                        }
                        v374 = (_QWORD *)*v374;
                        v429 = (__int64)v374;
                      }
                      while ( v374 );
                      v363 = v434;
                    }
                  }
                  goto LABEL_876;
                }
                v357 = v356 - 1;
                if ( !v357 )
                {
                  if ( v16 )
                  {
                    if ( (unsigned __int8)(*v16 - 48) > 2u )
                    {
                      if ( (unsigned int)sqlite3StrICmp(v16, "file") )
                      {
                        v360 = sqlite3StrICmp(v16, "memory");
                        v12 = v360 == 0 ? v361 : 0;
                      }
                    }
                    else
                    {
                      v12 = *v16 - 48;
                    }
                    v362 = *v9;
                    if ( *(unsigned __int8 *)(*v9 + 102) != v12 && !(unsigned int)invalidateTempStorage(v9) )
                      *(_BYTE *)(v362 + 102) = v12;
                    goto LABEL_876;
                  }
                  v27 = *((unsigned __int8 *)v5 + 102);
                  goto LABEL_875;
                }
                if ( v357 != 1 )
                  goto LABEL_836;
                if ( (_BYTE)word_18010EE54 )
                {
                  v358 = ((__int64 (__fastcall *)(__int64))xmmword_18010EEC0)(11);
                  if ( v358 )
                    ((void (__fastcall *)(__int64))xmmword_18010EED0)(v358);
                }
                if ( !v16 )
                {
                  v62 = sqlite3_temp_directory;
                  goto LABEL_102;
                }
                if ( !*v16
                  || (v426 = 0,
                      !(*(unsigned int (__fastcall **)(_QWORD, char *, __int64, unsigned int *))(*v5 + 56LL))(
                         *v5,
                         v16,
                         1,
                         &v426))
                  && v426 )
                {
                  if ( *((_BYTE *)v5 + 102) == 1 )
                    invalidateTempStorage(v9);
                  sqlite3_free(sqlite3_temp_directory);
                  if ( *v16 )
                    sqlite3_temp_directory = sqlite3_mprintf("%s", v16);
                  else
                    sqlite3_temp_directory = 0;
                  goto LABEL_736;
                }
LABEL_735:
                sqlite3ErrorMsg(v9, "not a writable directory");
                goto LABEL_736;
              }
              if ( !v16 )
                goto LABEL_876;
              sqlite3CodeVerifyNamedSchema(v9, v434);
              v381 = sqlite3LocateTable(v9, 2, v16, v434);
              v382 = v381;
              if ( !v381 )
                goto LABEL_876;
              v383 = *(_QWORD *)(v381 + 16);
              Index = v383;
              if ( v383 )
              {
                do
                {
                  if ( (*(_DWORD *)(v383 + 100) & 3) == 2 )
                    break;
                  v383 = *(_QWORD *)(v383 + 40);
                }
                while ( v383 );
                Index = v383;
              }
              *((_DWORD *)v9 + 14) = 7;
              if ( *(_BYTE *)(v381 + 63) == 1 || *(__int16 *)(v381 + 54) <= 0 )
              {
                viewGetColumnNames(v9, v381);
                v383 = Index;
              }
              LOWORD(v384) = *(_WORD *)(v382 + 54);
              if ( (__int16)v384 <= 0 )
                goto LABEL_876;
              v385 = *(_QWORD *)(v382 + 8);
              v386 = 0;
              v387 = 0;
              String = 0;
              v426 = 0;
              do
              {
                v388 = *(_WORD *)(v385 + 18);
                if ( (v388 & 0x62) == 0 || *((_QWORD *)v433 + 2) )
                {
                  if ( (v388 & 1) != 0 )
                  {
                    v389 = 1;
                    if ( v383 && (__int16)v384 >= 1 )
                    {
                      do
                      {
                        if ( *(__int16 *)(*(_QWORD *)(v383 + 8) + 2LL * v389 - 2) == (_DWORD)v387 )
                          break;
                        ++v389;
                      }
                      while ( v389 <= (__int16)v384 );
                    }
                  }
                  else
                  {
                    v389 = 0;
                  }
                  v390 = sqlite3ColumnExpr(v382, v385, v387, 0);
                  if ( v392 < 2 && v390 )
                    v429 = *(_QWORD *)(v390 + 8);
                  else
                    v429 = v391;
                  v393 = sqlite3ColumnType(v385, &Src);
                  v397 = (unsigned int)(v396 - String);
                  v398 = "issisii";
                  if ( !*((_QWORD *)v433 + 2) )
                    v398 = "issisi";
                  sqlite3VdbeMultiLoad(v11, 1, v398, v397, *(_QWORD *)v385, v393, v394, v429, v389, v395);
                  LODWORD(v387) = v426;
                  v386 = String;
                }
                else
                {
                  String = ++v386;
                }
                v384 = *(__int16 *)(v382 + 54);
                v387 = (unsigned int)(v387 + 1);
                v383 = Index;
                v385 += 24;
                v426 = v387;
              }
              while ( (int)v387 < v384 );
              goto LABEL_818;
            }
            v402 = v23 - 41;
            if ( !v402 )
            {
              if ( v16 )
              {
                v426 = 0;
                sqlite3GetInt32(v16, &v426);
                sqlite3_wal_autocheckpoint(v5, v426);
              }
              if ( (__int64 (__fastcall *)())v5[45] == sqlite3WalDefaultHook )
                AutoVacuum = *((_DWORD *)v5 + 92);
              else
                AutoVacuum = 0;
              goto LABEL_874;
            }
            v403 = v402 - 1;
            if ( !v403 )
            {
              v412 = 12;
              if ( *v437 )
                v412 = v13;
              v413 = 0;
              LODWORD(v441) = v412;
              if ( v16 )
              {
                if ( (unsigned int)sqlite3StrICmp(v16, "full") )
                {
                  if ( (unsigned int)sqlite3StrICmp(v16, "restart") )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v16, "truncate") )
                      v413 = 3;
                  }
                  else
                  {
                    v413 = v414;
                  }
                }
                else
                {
                  v413 = 1;
                }
              }
              v415 = (int)v441;
              *((_DWORD *)v9 + 14) = 3;
              sqlite3VdbeAddOp3(v11, 3, v415, v413, 1);
              sqlite3VdbeAddOp3(v11, 84, 1, 3, 0);
              goto LABEL_876;
            }
            v404 = v403 - 1;
            if ( !v404 )
            {
              if ( v16 && !(unsigned int)sqlite3_strnicmp(v16, "see-", 4) )
                dword_18010EE44 = strcmp_0(v16 + 4, "7bb07b8d471d642e") == 0;
              goto LABEL_876;
            }
            if ( v404 != 1 )
              goto LABEL_836;
            if ( !v16 )
              goto LABEL_876;
            v405 = *((_QWORD *)v22 + 2);
            if ( v405 - 2 <= 1 )
            {
              v408 = 0;
              v409 = 0;
              do
              {
                v410 = (unsigned __int8)v16[v408];
                if ( (*((_BYTE *)&qword_1800FB500 + v410) & 8) == 0 )
                  break;
                v409 = ((v410 - 7 * (((char)v410 >> 6) & 1)) & 0xF) + 16 * v409;
                if ( (v408 & 1) != 0 )
                  *((_BYTE *)v458 + ((unsigned __int64)v408 >> 1)) = v409;
                ++v408;
              }
              while ( (int)v408 < 80 );
              v11 = Index;
              v407 = (char *)v458;
              LODWORD(v406) = v408 >> 1;
            }
            else
            {
              v406 = -1;
              v407 = v16;
              if ( v405 < 4 )
              {
                do
                  ++v406;
                while ( v16[v406] );
                LODWORD(v406) = v406 & 0x3FFFFFFF;
              }
            }
            v411 = (v22[16] & 1) != 0
                 ? sqlite3_rekey_v2(v5, v434, v407, (unsigned int)v406)
                 : sqlite3_key_v2(v5, v434, v407, (unsigned int)v406);
            if ( v411 || !(_DWORD)v406 )
              goto LABEL_876;
            sqlite3VdbeSetNumCols(v11, 1);
            v311 = "ok";
            sqlite3VdbeSetColName(v11, 0, 0, "ok", 0);
LABEL_631:
            v125 = (char *)v311;
            goto LABEL_632;
          }
          if ( (_BYTE)v23 == 34 )
          {
            v429 = 0;
            if ( v16 && !(unsigned int)sqlite3DecOrHexToI64(v16) )
              sqlite3_soft_heap_limit64(v429);
            v135 = sqlite3_soft_heap_limit64(-1);
            goto LABEL_253;
          }
          if ( (unsigned __int8)v23 > 0x1Du )
          {
            v343 = v23 - 30;
            if ( !v343 )
            {
              v351 = v441[v14 + 1];
              if ( v16 )
              {
                v426 = 0;
                sqlite3GetInt32(v16, &v426);
                v353 = v426;
                *((_DWORD *)v5 + 29) = v426;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v351, v353, 0, 0) == 7 )
                  sqlite3OomFault(v5);
                goto LABEL_876;
              }
              if ( v351 )
                v352 = *(_DWORD *)(*(_QWORD *)(v351 + 8) + 52LL);
              else
                v352 = 0;
              v27 = v352;
              goto LABEL_875;
            }
            v344 = v343 - 1;
            if ( v344 )
            {
              v345 = v344 - 1;
              if ( v345 )
              {
                if ( v345 == 1 )
                {
                  sqlite3_db_release_memory(v5);
                  goto LABEL_876;
                }
                goto LABEL_836;
              }
              v346 = v441[v14 + 1];
              v347 = -1;
              if ( v16 )
              {
                if ( (unsigned int)sqlite3StrICmp(v16, "fast") )
                  v347 = (unsigned __int8)getSafetyLevel(v16, 1, 0) != 0;
                else
                  v347 = v348;
              }
              if ( !*((_DWORD *)v437 + 2) && v347 >= 0 )
              {
                for ( i1 = 0; i1 < *((_DWORD *)v5 + 10); ++i1 )
                  sqlite3BtreeSecureDelete(*(_QWORD *)(32LL * i1 + v5[4] + 8), (unsigned int)v347);
              }
              AutoVacuum = sqlite3BtreeSecureDelete(v346, (unsigned int)v347);
              goto LABEL_874;
            }
            for ( i2 = 0; i2 != 74; ++i2 )
              sqlite3VdbeMultiLoad(v11, 1, "s", (&off_1800CCCC0)[3 * i2], v416, v418, v422, v423, v424, v425);
            goto LABEL_819;
          }
          if ( (_BYTE)v23 != 29 )
          {
            v295 = v23 - 23;
            if ( !v295 )
            {
              v321 = *(__int64 **)(v441[v14 + 1] + 8LL);
              v322 = -2;
              v429 = -2;
              v323 = *v321;
              if ( v16 )
              {
                sqlite3DecOrHexToI64(v16);
                v322 = -1;
              }
              if ( v322 >= -1 )
              {
                v324 = *(_QWORD *)(v323 + 328);
                *(_QWORD *)(v323 + 208) = v322;
                if ( v324 )
                  *(_QWORD *)(v324 + 32) = v322;
              }
              v27 = *(_QWORD *)(v323 + 208);
              goto LABEL_875;
            }
            v296 = v295 - 2;
            if ( v296 )
            {
              v297 = v296 - 1;
              if ( !v297 )
              {
                v429 = 0;
                sqlite3CodeVerifySchema(v9, (unsigned int)v13);
                v307 = v454;
                v308 = *((_DWORD *)v9 + 14) + 1;
                *((_DWORD *)v9 + 14) = v308;
                if ( *((_BYTE *)qword_1800FBAB0 + *v307) == 112 )
                {
                  sqlite3VdbeAddOp3(v11, 178, v13, v308, 0);
                }
                else
                {
                  if ( !v16 || (unsigned int)sqlite3DecOrHexToI64(v16) || (v309 = v429, v429 < 0) )
                  {
                    v309 = 0;
                  }
                  else if ( v429 > 4294967294LL )
                  {
                    v309 = -2;
                  }
                  sqlite3VdbeAddOp3(v11, 179, v13, v308, v309);
                }
                v294 = v308;
                goto LABEL_606;
              }
              v298 = v297 - 1;
              if ( v298 )
              {
                if ( v298 == 1 )
                {
                  *((_DWORD *)v9 + 14) = 1;
                  for ( i3 = (_QWORD *)v5[70]; i3; i3 = (_QWORD *)*i3 )
                    sqlite3VdbeMultiLoad(v11, 1, "s", *(_QWORD *)(i3[2] + 8LL), v416, v418, v422, v423, v424, v425);
                  goto LABEL_876;
                }
                goto LABEL_836;
              }
              v447 = 0;
              if ( v16 )
              {
                sqlite3DecOrHexToI64(v16);
                if ( v447 < 0 )
                  v447 = qword_18010EF78;
                v300 = v437;
                if ( *((_DWORD *)v437 + 2) )
                {
                  if ( *((_DWORD *)v5 + 10) - 1 >= 0 )
                  {
                    v304 = *((_DWORD *)v5 + 10) - 1;
                    do
                    {
                      v305 = *(_QWORD *)(32LL * (unsigned int)v304 + v5[4] + 8);
                      v446 = v305;
                      if ( v305 && v304 == (_DWORD)v13 )
                      {
                        Index = v447;
                        v306 = *(_QWORD *)(v305 + 8);
                        v429 = v306;
                        if ( *(_BYTE *)(v305 + 17) )
                        {
                          ++*(_DWORD *)(v305 + 20);
                          if ( !*(_BYTE *)(v305 + 18) )
                          {
                            btreeLockCarefully(v305);
                            v306 = v429;
                          }
                        }
                        *(_QWORD *)(*(_QWORD *)v306 + 160LL) = Index;
                        pagerFixMaplimit();
                        if ( *(_BYTE *)(v446 + 17) )
                        {
                          v123 = (*(_DWORD *)(v446 + 20))-- == 1;
                          if ( v123 )
                            unlockBtreeMutex();
                        }
                      }
                      --v304;
                    }
                    while ( v304 >= 0 );
                    goto LABEL_591;
                  }
                }
                else
                {
                  v5[8] = v447;
                  if ( *((_DWORD *)v5 + 10) - 1 >= 0 )
                  {
                    v301 = *((_DWORD *)v5 + 10) - 1;
                    do
                    {
                      v302 = *(_QWORD *)(32LL * (unsigned int)v301 + v5[4] + 8);
                      v446 = v302;
                      if ( v302 && (v301 == (_DWORD)v13 || !*((_DWORD *)v300 + 2)) )
                      {
                        Index = v447;
                        v303 = *(_QWORD *)(v302 + 8);
                        v429 = v303;
                        if ( *(_BYTE *)(v302 + 17) )
                        {
                          ++*(_DWORD *)(v302 + 20);
                          if ( !*(_BYTE *)(v302 + 18) )
                          {
                            btreeLockCarefully(v302);
                            v303 = v429;
                          }
                        }
                        *(_QWORD *)(*(_QWORD *)v303 + 160LL) = Index;
                        pagerFixMaplimit();
                        if ( *(_BYTE *)(v446 + 17) )
                        {
                          v123 = (*(_DWORD *)(v446 + 20))-- == 1;
                          if ( v123 )
                            unlockBtreeMutex();
                        }
                        v300 = v437;
                      }
                      --v301;
                    }
                    while ( v301 >= 0 );
LABEL_591:
                    v16 = v450;
                  }
                }
              }
              v447 = -1;
              v19 = sqlite3_file_control(v5, v434, 18, &v447);
              if ( !v19 )
              {
                v27 = v447;
                goto LABEL_875;
              }
              if ( v19 != 12 )
              {
LABEL_18:
                ++*((_DWORD *)v9 + 12);
                *((_DWORD *)v9 + 6) = v19;
                goto LABEL_876;
              }
              goto LABEL_876;
            }
            v310 = -1;
            v311 = "exclusive";
            if ( !v16 )
              goto LABEL_611;
            if ( !(unsigned int)sqlite3StrICmp(v16, "exclusive") )
            {
              v312 = 1;
              goto LABEL_612;
            }
            v313 = sqlite3StrICmp(v16, "normal");
            v312 = 0;
            if ( v313 )
LABEL_611:
              v312 = v310;
LABEL_612:
            if ( !*((_DWORD *)v437 + 2) )
            {
              if ( v312 == v310 )
              {
                v314 = *((_BYTE *)v5 + 105);
LABEL_629:
                if ( v314 != 1 )
                  v311 = "normal";
                goto LABEL_631;
              }
              if ( v312 >= 0 )
              {
                for ( i4 = 2; i4 < *((_DWORD *)v5 + 10); ++i4 )
                {
                  v316 = *(__int64 **)(*(_QWORD *)(32LL * i4 + v5[4] + 8) + 8LL);
                  v317 = *v316;
                  if ( !*(_BYTE *)(*v316 + 16) )
                  {
                    v318 = *(_QWORD *)(v317 + 328);
                    if ( !v318 || *(_BYTE *)(v318 + 63) != 2 )
                      *(_BYTE *)(v317 + 8) = v312;
                  }
                }
              }
              *((_BYTE *)v5 + 105) = v312;
            }
            v319 = **(_QWORD **)(v441[v14 + 1] + 8LL);
            if ( v312 >= 0 && !*(_BYTE *)(v319 + 16) )
            {
              v320 = *(_QWORD *)(v319 + 328);
              if ( !v320 || *(_BYTE *)(v320 + 63) != 2 )
                *(_BYTE *)(v319 + 8) = v312;
            }
            v314 = *(_BYTE *)(v319 + 8);
            goto LABEL_629;
          }
          if ( v16 )
          {
            v426 = 0;
            sqlite3GetInt32(v16, &v426);
            LODWORD(v442) = v426;
            if ( (v426 & 2) == 0 )
              goto LABEL_876;
            String = 0;
            v325 = 0;
            v443 = 0;
            if ( (v426 & 0x10) == 0 )
            {
              v428 = 0;
              goto LABEL_645;
            }
          }
          else
          {
            String = 0;
            v325 = 0;
            LODWORD(v442) = 65534;
            v443 = 0;
          }
          v428 = (unsigned int)(*((_DWORD *)v5 + 186) - 1) > 0x7CE ? 0x7D0 : 0;
LABEL_645:
          v436 = *((_DWORD *)v9 + 13);
          *((_DWORD *)v9 + 13) = v436 + 1;
          if ( v434 )
          {
            v326 = v13;
            v432 = v13;
          }
          else
          {
            v326 = *((_DWORD *)v5 + 10) - 1;
            v432 = v326;
            if ( (int)v13 > v326 )
            {
LABEL_680:
              sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
              if ( !*((_BYTE *)v5 + 103) && v428 && v325 > 100 )
              {
                v339 = (int)(100 * v428) / v325;
                if ( v339 < 100 )
                  v339 = 100;
                v340 = qword_18010FAB0;
                if ( !*(_BYTE *)(*(_QWORD *)v11 + 103LL) )
                  v340 = *(__int64 **)(v11 + 136);
                v341 = *(_DWORD *)(v11 + 144);
                for ( i5 = 0; (int)i5 < v341; ++i5 )
                {
                  if ( LOBYTE(v340[3 * i5]) == 0x94 )
                    LODWORD(v340[3 * i5 + 1]) = v339;
                }
              }
              goto LABEL_876;
            }
          }
          do
          {
            if ( (_DWORD)v13 != 1 )
            {
              sqlite3CodeVerifySchema(v9, (unsigned int)v13);
              for ( i6 = *(_QWORD *)(*(_QWORD *)(32LL * (int)v13 + v5[4] + 24) + 16LL); ; i6 = *(_QWORD *)v446 )
              {
                v446 = i6;
                if ( !i6 )
                  break;
                v328 = *(_QWORD *)(i6 + 16);
                Index = v328;
                if ( !*(_BYTE *)(v328 + 63) && (unsigned int)sqlite3_strnicmp(*(_QWORD *)v328, "sqlite_", 7) )
                {
                  v329 = Index;
                  v330 = 0;
                  v426 = 0;
                  v331 = *(_QWORD *)(Index + 16);
                  v332 = *(unsigned __int16 *)(Index + 58);
                  v444 = v332;
                  if ( v331 )
                  {
                    do
                    {
                      ++v330;
                      if ( *(char *)(v331 + 100) >= 0 )
                        v332 = -1;
                      v331 = *(_QWORD *)(v331 + 40);
                    }
                    while ( v331 );
                    v426 = v330;
                    v444 = v332;
                  }
                  if ( (*(_DWORD *)(Index + 48) & 0x100) != 0
                    || (v442 & 0x10000) != 0
                    || *(_QWORD *)(Index + 16) && (v332 & 0x8000u) != 0 )
                  {
                    if ( ++String == 2 )
                    {
                      sqlite3BeginWriteOperation(v9, 0, (unsigned int)v13);
                      v329 = Index;
                      v330 = v426;
                    }
                    v443 += v330 + 1;
                    sqlite3OpenTable((_DWORD)v9, v436, v13, v329, 112);
                    if ( (v444 & 0x8000u) != 0 )
                    {
                      v426 = v442 & 1;
                      sqlite3VdbeAddOp3(v11, 36, v436, *(_DWORD *)(v11 + 144) + v426 + 2, 0);
                    }
                    else
                    {
                      if ( (__int16)v444 < 33 )
                        v333 = -1;
                      else
                        v333 = (__int16)v444 - 33;
                      v426 = v442 & 1;
                      sqlite3VdbeAddOp4Int(v11, 33, v436, *(_DWORD *)(v11 + 144) + v426 + 2, v333, (__int16)v444 + 33);
                    }
                    v429 = sqlite3MPrintf(
                             v5,
                             "ANALYZE \"%w\".\"%w\"",
                             *(_QWORD *)(32LL * (int)v13 + v5[4]),
                             *(_QWORD *)Index);
                    if ( v426 )
                    {
                      v334 = *((_BYTE *)v9 + 31);
                      if ( v334 )
                      {
                        v336 = v334 - 1;
                        *((_BYTE *)v9 + 31) = v336;
                        v335 = *((_DWORD *)v9 + v336 + 58);
                      }
                      else
                      {
                        v335 = *((_DWORD *)v9 + 14) + 1;
                        *((_DWORD *)v9 + 14) = v335;
                      }
                      v426 = v335;
                      v337 = sqlite3VdbeAddOp3(v11, 117, 0, v335, 0);
                      sqlite3VdbeChangeP4(v11, v337, v429, 4294967290LL);
                      sqlite3VdbeAddOp3(v11, 84, v426, 1, 0);
                    }
                    else
                    {
                      v338 = sqlite3VdbeAddOp3(v11, 148, v428 != 0 ? 2 : 0, v428, 0);
                      sqlite3VdbeChangeP4(v11, v338, v429, 4294967290LL);
                    }
                  }
                }
              }
              v326 = v432;
            }
            LODWORD(v13) = v13 + 1;
          }
          while ( (int)v13 <= v326 );
          v16 = v450;
          v325 = v443;
          goto LABEL_680;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800847e0  push    rbp
0x1800847e2  push    rbx
0x1800847e3  push    rsi
0x1800847e4  push    rdi
0x1800847e5  push    r12
0x1800847e7  push    r13
0x1800847e9  push    r14
0x1800847eb  push    r15
0x1800847ed  lea     rbp, [rsp-78h]
0x1800847f2  sub     rsp, 178h
0x1800847f9  mov     rax, cs:__security_cookie
0x180084800  xor     rax, rsp
0x180084803  mov     [rbp+0B0h+var_48], rax
0x180084807  mov     r15, [rcx]
0x18008480a  xorps   xmm0, xmm0
0x18008480d  mov     rbx, r8
0x180084810  mov     [rbp+0B0h+var_D0], r15
0x180084814  xor     esi, esi
0x180084816  mov     [rbp+0B0h+var_110], rbx
0x18008481a  mov     [rbp+0B0h+var_D8], rsi
0x18008481e  mov     r12, r9
0x180084821  movups  [rbp+0B0h+var_90], xmm0
0x180084825  mov     [rsp+1B0h+var_140], r9
0x18008482a  mov     rdi, rdx
0x18008482d  movups  [rbp+0B0h+var_80], xmm0
0x180084831  mov     r13, rcx
0x180084834  mov     [rbp+0B0h+var_98], rcx
0x180084838  call    sqlite3GetVdbe
0x18008483d  mov     [rsp+1B0h+var_138], rax
0x180084842  mov     r14, rax
0x180084845  test    rax, rax
0x180084848  jz      loc_1800885AD
0x18008484e  mov     dword ptr [rsp+1B0h+var_190], esi
0x180084852  mov     edx, 0A6h
0x180084857  mov     esi, 1
0x18008485c  mov     rcx, rax
0x18008485f  mov     r9d, esi
0x180084862  mov     r8d, esi
0x180084865  call    sqlite3VdbeAddOp3
0x18008486a  lea     r9, [rbp+0B0h+var_D8]
0x18008486e  mov     dword ptr [r13+38h], 2
0x180084876  mov     r8, rbx
0x180084879  mov     rdx, rdi
0x18008487c  mov     rcx, r13
0x18008487f  call    sqlite3TwoPartName
0x180084884  movsxd  rdi, eax
0x180084887  test    eax, eax
0x180084889  js      loc_1800885AD
0x18008488f  mov     rax, [r15+20h]
0x180084893  mov     [rbp+0B0h+var_F8], rax
0x180084897  cmp     edi, esi
0x180084899  jnz     short loc_1800848AB
0x18008489b  mov     rcx, r13
0x18008489e  call    sqlite3OpenTempDatabase
0x1800848a3  test    eax, eax
0x1800848a5  jnz     loc_1800885AD
0x1800848ab  mov     rdx, [rbp+0B0h+var_D8]
0x1800848af  mov     rcx, r15
0x1800848b2  call    sqlite3NameFromToken
0x1800848b7  mov     [rbp+0B0h+var_A0], rax
0x1800848bb  test    rax, rax
0x1800848be  jz      loc_1800885AD
0x1800848c4  mov     rbx, rdi
0x1800848c7  mov     rcx, r15
0x1800848ca  shl     rbx, 5
0x1800848ce  cmp     [rbp+0B0h+arg_20], 0
0x1800848d5  jz      short loc_1800848E8
0x1800848d7  mov     r8, r12
0x1800848da  lea     rdx, aT; "-%T"
0x1800848e1  call    sqlite3MPrintf
0x1800848e6  jmp     short loc_1800848F0
0x1800848e8  mov     rdx, r12
0x1800848eb  call    sqlite3NameFromToken
0x1800848f0  mov     r12, rax
0x1800848f3  mov     [rbp+0B0h+var_C0], rax
0x1800848f7  mov     rax, [rbp+0B0h+var_110]
0x1800848fb  xor     ecx, ecx
0x1800848fd  cmp     [rax+8], ecx
0x180084900  jbe     short loc_18008490C
0x180084902  mov     rax, [rbp+0B0h+var_F8]
0x180084906  mov     rax, [rax+rbx]
0x18008490a  jmp     short loc_18008490F
0x18008490c  mov     rax, rcx
0x18008490f  mov     r8, [rbp+0B0h+var_A0]
0x180084913  mov     r9, r12
0x180084916  mov     edx, 13h
0x18008491b  mov     [rbp+0B0h+var_120], rax
0x18008491f  mov     rcx, r13
0x180084922  mov     [rsp+1B0h+var_190], rax
0x180084927  call    sqlite3AuthCheck
0x18008492c  xor     ecx, ecx
0x18008492e  test    eax, eax
0x180084930  jnz     loc_180088591
0x180084936  mov     rax, [rbp+0B0h+var_A0]
0x18008493a  lea     r8d, [rcx+0Eh]
0x18008493e  mov     rdx, [rbp+0B0h+var_120]
0x180084942  lea     r9, [rbp+0B0h+var_90]
0x180084946  mov     qword ptr [rbp+0B0h+var_90], rcx
0x18008494a  mov     qword ptr [rbp+0B0h+var_80+8], rcx
0x18008494e  mov     qword ptr [rbp+0B0h+var_90+8], rax
0x180084952  mov     qword ptr [rbp+0B0h+var_80], r12
0x180084956  mov     [r15+298h], ecx
0x18008495d  mov     rcx, r15
0x180084960  call    sqlite3_file_control
0x180084965  mov     [rsp+1B0h+var_150], eax
0x180084969  test    eax, eax
0x18008496b  jnz     short loc_1800849AB
0x18008496d  mov     edx, esi
0x18008496f  mov     rcx, r14
0x180084972  call    sqlite3VdbeSetNumCols
0x180084977  mov     r9, qword ptr [rbp+0B0h+var_90]
0x18008497b  xor     r8d, r8d
0x18008497e  xor     edx, edx
0x180084980  mov     [rsp+1B0h+var_190], 0FFFFFFFFFFFFFFFFh
0x180084989  mov     rcx, r14
0x18008498c  call    sqlite3VdbeSetColName
0x180084991  mov     rdx, qword ptr [rbp+0B0h+var_90]
0x180084995  mov     rcx, r14
0x180084998  call    returnSingleText
0x18008499d  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x1800849a1  call    sqlite3_free
0x1800849a6  jmp     loc_180088591
0x1800849ab  cmp     eax, 0Ch
0x1800849ae  jz      short loc_1800849E2
0x1800849b0  mov     r8, qword ptr [rbp+0B0h+var_90]
0x1800849b4  test    r8, r8
0x1800849b7  jz      short loc_1800849D5
0x1800849b9  lea     rdx, aS_7; "%s"
0x1800849c0  mov     rcx, r13
0x1800849c3  call    sqlite3ErrorMsg
0x1800849c8  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x1800849cc  call    sqlite3_free
0x1800849d1  mov     eax, [rsp+1B0h+var_150]
0x1800849d5  add     [r13+30h], esi
0x1800849d9  mov     [r13+18h], eax
0x1800849dd  jmp     loc_180088591
0x1800849e2  mov     rcx, [rbp+0B0h+var_A0]
0x1800849e6  call    pragmaLocate
0x1800849eb  mov     [rbp+0B0h+var_128], rax
0x1800849ef  mov     r10, rax
0x1800849f2  test    rax, rax
0x1800849f5  jz      loc_180088591
0x1800849fb  test    [rax+9], sil
0x1800849ff  jz      short loc_180084A15
0x180084a01  mov     rcx, r13
0x180084a04  call    sqlite3ReadSchema
0x180084a09  test    eax, eax
0x180084a0b  jnz     loc_180088591
0x180084a11  mov     r10, [rbp+0B0h+var_128]
0x180084a15  mov     r11d, 2
0x180084a1b  test    [r10+9], r11b
0x180084a1f  jnz     short loc_180084A42
0x180084a21  test    byte ptr [r10+9], 4
0x180084a26  jz      short loc_180084A2D
0x180084a28  test    r12, r12
0x180084a2b  jnz     short loc_180084A42
0x180084a2d  mov     rdx, r10
0x180084a30  mov     rcx, r14
0x180084a33  call    setPragmaResultColumnNames
0x180084a38  mov     r10, [rbp+0B0h+var_128]
0x180084a3c  mov     r11d, 2
0x180084a42  movzx   ecx, byte ptr [r10+8]
0x180084a47  cmp     ecx, 16h
0x180084a4a  ja      loc_1800872BE
0x180084a50  jz      loc_1800871CF
0x180084a56  cmp     ecx, 0Bh
0x180084a59  ja      loc_180085083
0x180084a5f  jz      loc_180084FFB
0x180084a65  cmp     ecx, 6
0x180084a68  ja      loc_180084E1F
0x180084a6e  jz      loc_180084D99
0x180084a74  xor     eax, eax
0x180084a76  test    ecx, ecx
0x180084a78  jz      loc_180084D5A
0x180084a7e  sub     ecx, esi
0x180084a80  jz      loc_180084C8C
0x180084a86  sub     ecx, esi
0x180084a88  jz      loc_180084BA1
0x180084a8e  sub     ecx, esi
0x180084a90  jz      short loc_180084AE2
0x180084a92  cmp     ecx, r11d
0x180084a95  jnz     loc_180088354
0x180084a9b  test    r12, r12
0x180084a9e  jnz     short loc_180084AB2
0x180084aa0  mov     rax, [rbp+0B0h+var_F8]
0x180084aa4  mov     rax, [rax+rbx+18h]
0x180084aa9  movsxd  rdx, dword ptr [rax+74h]
0x180084aad  jmp     loc_180088589
0x180084ab2  lea     rdx, [rsp+1B0h+var_14C]
0x180084ab7  mov     [rsp+1B0h+var_14C], eax
0x180084abb  mov     rcx, r12
0x180084abe  call    sqlite3GetInt32
0x180084ac3  mov     r8, [rbp+0B0h+var_F8]
0x180084ac7  mov     eax, [rsp+1B0h+var_14C]
0x180084acb  mov     rcx, [r8+rbx+18h]
0x180084ad0  mov     [rcx+74h], eax
0x180084ad3  mov     rdx, [r8+rbx+18h]
0x180084ad8  mov     rcx, [r8+rbx+8]
0x180084add  jmp     loc_180085912
0x180084ae2  test    r12, r12
0x180084ae5  jnz     short loc_180084B09
0x180084ae7  mov     rdx, r10
0x180084aea  mov     rcx, r14
0x180084aed  call    setPragmaResultColumnNames
0x180084af2  mov     rdx, [rbp+0B0h+var_128]
0x180084af6  mov     rax, [r15+30h]
0x180084afa  test    [rdx+10h], rax
0x180084afe  mov     rdx, r12
0x180084b01  setnz   dl
0x180084b04  jmp     loc_180088589
0x180084b09  mov     rbx, [r10+10h]
0x180084b0d  mov     edx, esi
0x180084b0f  btr     rbx, 0Eh
0x180084b14  mov     rcx, r12
0x180084b17  cmp     [r15+65h], al
0x180084b1b  cmovnz  rbx, [r10+10h]
0x180084b20  xor     r8d, r8d
0x180084b23  call    getSafetyLevel
0x180084b28  xor     r11d, r11d
0x180084b2b  test    al, al
0x180084b2d  jz      short loc_180084B45
0x180084b2f  test    sil, bl
0x180084b32  jz      short loc_180084B3F
0x180084b34  mov     eax, [r15+30h]
0x180084b38  bt      rax, 1Ch
0x180084b3d  jb      short loc_180084B84
0x180084b3f  or      [r15+30h], rbx
0x180084b43  jmp     short loc_180084B84
0x180084b45  mov     rax, rbx
0x180084b48  not     rax
0x180084b4b  and     [r15+30h], rax
0x180084b4f  cmp     rbx, 80000h
0x180084b56  jnz     short loc_180084B61
0x180084b58  mov     [r15+300h], r11
0x180084b5f  jmp     short loc_180084B84
0x180084b61  test    sil, bl
0x180084b64  jz      short loc_180084B84
0x180084b66  lea     rdx, aReset; "reset"
0x180084b6d  mov     rcx, r12
0x180084b70  call    sqlite3StrICmp
0x180084b75  test    eax, eax
0x180084b77  jnz     short loc_180084B84
0x180084b79  mov     rcx, r15
0x180084b7c  call    sqlite3ResetAllSchemasOfConnection
0x180084b81  xor     r11d, r11d
0x180084b84  xor     r9d, r9d
0x180084b87  mov     dword ptr [rsp+1B0h+var_190], r11d
0x180084b8c  xor     r8d, r8d
0x180084b8f  mov     edx, 0A6h
0x180084b94  mov     rcx, r14
0x180084b97  call    sqlite3VdbeAddOp3
0x180084b9c  jmp     loc_180084E12
0x180084ba1  mov     rax, [rbp+0B0h+var_F8]
0x180084ba5  xor     r11d, r11d
0x180084ba8  mov     rbx, [rax+rbx+8]
0x180084bad  test    r12, r12
0x180084bb0  jnz     short loc_180084BBF
0x180084bb2  mov     rcx, rbx
0x180084bb5  call    sqlite3BtreeGetAutoVacuum
0x180084bba  jmp     loc_180088586
0x180084bbf  lea     rdx, aNone; "none"
0x180084bc6  mov     rcx, r12
0x180084bc9  call    sqlite3StrICmp
0x180084bce  test    eax, eax
0x180084bd0  jnz     short loc_180084BD7
0x180084bd2  mov     r13d, r11d
0x180084bd5  jmp     short loc_180084C29
0x180084bd7  lea     rdx, aFull; "full"
0x180084bde  mov     rcx, r12
0x180084be1  call    sqlite3StrICmp
0x180084be6  test    eax, eax
0x180084be8  jnz     short loc_180084BEF
0x180084bea  mov     r13d, esi
0x180084bed  jmp     short loc_180084C29
0x180084bef  lea     rdx, aIncremental; "incremental"
0x180084bf6  mov     rcx, r12
0x180084bf9  call    sqlite3StrICmp
0x180084bfe  test    eax, eax
0x180084c00  jnz     short loc_180084C08
0x180084c02  lea     r13d, [rax+2]
0x180084c06  jmp     short loc_180084C29
0x180084c08  lea     rdx, [rbp+0B0h+var_114]
0x180084c0c  mov     [rbp+0B0h+var_114], r11d
0x180084c10  mov     rcx, r12
0x180084c13  call    sqlite3GetInt32
0x180084c18  movzx   ecx, byte ptr [rbp+0B0h+var_114]
0x180084c1c  xor     eax, eax
0x180084c1e  cmp     [rbp+0B0h+var_114], 2
0x180084c22  cmova   ecx, eax
0x180084c25  movzx   r13d, cl
0x180084c29  mov     edx, r13d
0x180084c2c  mov     [r15+6Ah], r13b
0x180084c30  mov     rcx, rbx
0x180084c33  call    sqlite3BtreeSetAutoVacuum
0x180084c38  test    eax, eax
0x180084c3a  jnz     loc_180088591
0x180084c40  lea     eax, [r13-1]
0x180084c44  cmp     eax, esi
0x180084c46  ja      loc_180088591
0x180084c4c  mov     ebx, [r14+90h]
  ... truncated ...
```
