# sqlite3Pragma

- ea: `0x180050420`
- end: `0x180053d44`
- name: `sqlite3Pragma`
- size: `14628`
- prototype: ``
- caller_count: `1`
- callee_count: `119`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031b38`

## callees

- `0x180001110`
- `0x180005810`
- `0x180005c54`
- `0x180005d14`
- `0x1800073ec`
- `0x180008838`
- `0x180009f00`
- `0x18000a220`
- `0x18000a7a0`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000b220`
- `0x18000c930`
- `0x18000e808`
- `0x18000fa9c`
- `0x18000fd7c`
- `0x180010390`
- `0x180010810`
- `0x180010d10`
- `0x1800119e0`
- `0x180011d80`
- `0x180012454`
- `0x1800126ec`
- `0x1800139a4`
- `0x180013a00`
- `0x180013c28`
- `0x1800143f0`
- `0x180014434`
- `0x180014af0`
- `0x180014b90`
- `0x1800150f4`
- `0x1800157d4`
- `0x180016250`
- `0x180016398`
- `0x180016444`
- `0x180018600`
- `0x18001bdf0`
- `0x18001c02c`
- `0x18001c1c4`
- `0x18001c220`
- `0x180023b30`
- `0x180024440`
- `0x1800256c4`
- `0x180027aa0`
- `0x180028c94`
- `0x1800303e0`
- `0x1800351c8`
- `0x180036688`
- `0x180037070`
- `0x1800370c0`

## string_xrefs

- `0x1800537e7`: `not a writable directory`
- `0x180053c93`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r12
  __int64 *v9; // rdi
  __int64 result; // rax
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // rax
  char *v15; // r13
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // r10
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  __int64 v36; // rbx
  int v37; // eax
  unsigned int AutoVacuum; // edi
  int v39; // ebx
  _DWORD *v40; // rax
  int v41; // edi
  __int64 v42; // rcx
  __int64 v43; // r10
  unsigned int v44; // r11d
  __int64 v45; // rbx
  _DWORD *v46; // rax
  __int64 v47; // rcx
  int Int32; // eax
  __int64 v49; // rdx
  int v50; // edi
  __int64 v51; // rbx
  char Boolean; // al
  __int64 v53; // rcx
  __int64 v54; // rbx
  unsigned __int64 v55; // rcx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  unsigned int v62; // ebx
  __int64 j; // rcx
  __int64 v64; // rax
  __int64 **v65; // rbx
  unsigned int v66; // esi
  unsigned __int8 v67; // al
  unsigned int i; // ebx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  __int64 v82; // rax
  __int64 v83; // rbx
  unsigned int v84; // eax
  __int64 v85; // rbx
  unsigned int v86; // edi
  bool v87; // zf
  __int64 Index; // rsi
  __int64 v89; // rax
  unsigned int v90; // eax
  const char **v91; // rbx
  bool v92; // cf
  unsigned int v93; // r12d
  __int64 v94; // rdx
  __int64 v95; // rcx
  int v96; // ebx
  unsigned int v97; // ebx
  __int64 v98; // rax
  unsigned int v99; // ebx
  __int64 m; // rsi
  __int64 n; // rdi
  _QWORD *v102; // rdi
  __int64 v103; // rax
  __int64 v104; // rsi
  __int64 v105; // rbx
  unsigned int v106; // eax
  unsigned int v107; // r9d
  __int64 v108; // rdx
  unsigned int v109; // eax
  __int64 v110; // rcx
  int v111; // edi
  __int64 v112; // rcx
  __int64 v113; // rdx
  __int64 v114; // r8
  int v115; // eax
  __int64 v116; // r8
  int v117; // r10d
  int v118; // eax
  int v119; // ecx
  __int64 v120; // rax
  _QWORD *v121; // rax
  __int64 Table; // rsi
  unsigned int v123; // eax
  __int64 v124; // rcx
  __int64 v125; // rbx
  int v126; // edx
  __int64 v127; // rcx
  int v128; // eax
  __int64 v129; // rax
  __int64 v130; // r8
  unsigned int v131; // eax
  const char **v132; // rcx
  int v133; // r13d
  __int64 v134; // r8
  const char **v135; // rbx
  __int64 v136; // rax
  int v137; // eax
  int v138; // ecx
  __int64 v139; // rdi
  int k; // r12d
  int v141; // r9d
  int v142; // ebx
  __int64 v143; // rax
  const char **v144; // rbx
  const char *v145; // rdx
  char **ii; // rbx
  __int64 v147; // rdx
  char v148; // r11
  __int64 v149; // rcx
  int v150; // r11d
  _DWORD *v151; // rax
  int v152; // ebx
  __int64 v153; // rax
  __int64 v154; // r8
  int v155; // ebx
  int v156; // eax
  __int64 v157; // r9
  unsigned int v158; // eax
  __int64 v159; // rcx
  __int64 v160; // rax
  __int64 v161; // rax
  int v162; // ecx
  _QWORD *v163; // rax
  __int64 v164; // rdx
  __int64 v165; // rdx
  int v166; // eax
  int *v167; // rax
  int v168; // ebx
  _QWORD *v169; // r8
  __int64 v170; // r14
  __int64 v171; // rdx
  __int64 v172; // rcx
  __int64 jj; // rdx
  int v174; // ecx
  unsigned int v175; // ebx
  __int64 v176; // rax
  __int64 v177; // r10
  __int64 v178; // rax
  __int64 v179; // rcx
  unsigned int v180; // r12d
  __int64 v181; // rax
  unsigned int v182; // r9d
  const char ***v183; // rdx
  __int64 v184; // rcx
  const char **v185; // rax
  unsigned int v186; // edi
  unsigned int v187; // ebx
  __int64 v188; // rax
  __int64 v189; // rax
  __int64 v190; // rbx
  const char **v191; // rax
  const char **v192; // rbx
  __int64 v193; // r8
  unsigned int TempRange; // eax
  __int64 v195; // r10
  int v196; // edx
  int v197; // edi
  const char *v198; // r12
  int v199; // eax
  int v200; // r9d
  int v201; // edx
  int kk; // r8d
  int v203; // eax
  int v204; // r9d
  unsigned int v205; // ebx
  __int64 v206; // rax
  __int64 v207; // rax
  int v208; // ebx
  int v209; // r14d
  __int64 v210; // r12
  __int64 v211; // rdx
  int v212; // r8d
  bool v213; // cc
  __int64 v214; // rcx
  BOOL v215; // r8d
  int v216; // r11d
  int v217; // edx
  int v218; // eax
  _BYTE *v219; // r9
  int v220; // r8d
  __int64 v221; // rax
  __int64 v222; // rdx
  __int64 v223; // r8
  __int16 v224; // ax
  int v225; // eax
  int v226; // ecx
  const char **v227; // rax
  unsigned int v228; // r9d
  int v229; // ecx
  int v230; // r10d
  __int64 v231; // rax
  unsigned int v232; // edx
  __int64 v233; // rax
  __int64 v234; // rdx
  __int64 v235; // r9
  __int64 v236; // r10
  __int64 v237; // rax
  char v238; // dl
  int v239; // ecx
  const char *v240; // rdx
  const char **v241; // rax
  const char **v242; // rcx
  int v243; // eax
  unsigned int v244; // r14d
  int v245; // ebx
  const char **v246; // r12
  __int64 v247; // rax
  char *v248; // rbx
  int v249; // ecx
  __int64 v250; // r8
  int v251; // edx
  const char **v252; // r12
  int v253; // eax
  unsigned int v254; // ebx
  unsigned int v255; // ebx
  unsigned int v256; // edx
  int v257; // r12d
  unsigned int v258; // ebx
  __int64 v259; // rax
  int v260; // edx
  int v261; // edi
  __int64 v262; // rax
  unsigned int v263; // ebx
  __int64 v264; // rax
  unsigned int v265; // r8d
  unsigned int v266; // r9d
  __int64 v267; // rax
  __int64 v268; // rdx
  int v269; // ebx
  __int64 v270; // rax
  __int64 v271; // rbx
  __int64 v272; // r8
  __int64 v273; // rbx
  __int64 ElementWithHash; // rax
  __int64 v275; // rax
  __int64 *v276; // rax
  __int64 v277; // rax
  unsigned int v278; // ebx
  __int64 v279; // rax
  __int64 v280; // rax
  __int64 v281; // rax
  __int64 v282; // r8
  __int64 Op; // rax
  int v284; // r9d
  unsigned int v285; // ecx
  unsigned int v286; // ecx
  unsigned int v287; // ecx
  unsigned int v288; // ecx
  __int64 v289; // rdx
  int v290; // r8d
  __int64 v291; // r13
  __int64 v292; // rax
  __int64 v293; // rbx
  int v294; // edx
  __int64 v295; // r13
  __int64 v296; // rax
  __int64 v297; // rbx
  unsigned __int8 *v298; // rax
  int v299; // ebx
  int v300; // eax
  int v301; // r9d
  int v302; // r8d
  __int64 LockingMode; // rdx
  int v304; // eax
  int nn; // r8d
  int v306; // r8d
  __int64 *v307; // rcx
  __int64 v308; // rax
  __int64 v309; // rdi
  __int64 v310; // rcx
  __int64 v311; // rdx
  __int64 v312; // rcx
  unsigned int v313; // edx
  unsigned int i1; // ebx
  int v315; // eax
  __int64 v316; // rax
  int v317; // edi
  __int64 v318; // r13
  int v319; // ecx
  _QWORD *mm; // rbx
  unsigned int v321; // ecx
  unsigned int v322; // ecx
  unsigned int v323; // ecx
  int v324; // edi
  __int64 v325; // rsi
  int v326; // ebx
  __int64 i2; // rbx
  __int64 v328; // rbx
  int v329; // ecx
  __int64 v330; // rdx
  int v331; // ebx
  int v332; // eax
  const char **i3; // rax
  __int64 v334; // rdx
  _BYTE *v335; // r9
  int v336; // r8d
  const char *v337; // r10
  __int64 v338; // rcx
  unsigned int v339; // r9d
  int v340; // r8d
  int v341; // r8d
  __int64 v342; // rdx
  int TempReg; // ebx
  __int64 v344; // rdx
  int v345; // r9d
  __int64 v346; // rax
  __int64 v347; // rdx
  int v348; // r9d
  int v349; // r10d
  unsigned int v350; // ecx
  unsigned int v351; // ecx
  unsigned int v352; // ecx
  unsigned int v353; // ecx
  unsigned int v354; // ecx
  unsigned int v355; // ecx
  unsigned int v356; // ecx
  unsigned int v357; // ecx
  int v358; // r9d
  int v359; // esi
  int v360; // r11d
  int v361; // r8d
  __int64 v362; // rax
  __int64 v363; // rcx
  __int64 v364; // rax
  __int64 v365; // rsi
  __int64 v366; // rdx
  int v367; // eax
  __int64 v368; // rdi
  __int64 v369; // rcx
  int v370; // edi
  __int64 v371; // rcx
  __int64 v372; // r13
  _QWORD *i4; // rax
  __int64 v374; // r8
  __int64 v375; // rax
  __int64 v376; // rax
  _QWORD *v377; // rax
  const char *v378; // rcx
  unsigned int v379; // esi
  int v380; // ebx
  __int64 v381; // rax
  __int64 v382; // rax
  __int64 v383; // rbx
  signed int v384; // edx
  __int64 v385; // r13
  int v386; // ecx
  signed int v387; // r8d
  __int64 v388; // r12
  __int16 v389; // ax
  int v390; // edi
  __int64 v391; // rax
  __int64 v392; // r9
  unsigned int v393; // r11d
  __int64 v394; // rax
  int v395; // r10d
  int v396; // r11d
  int v397; // r8d
  __int64 v398; // r9
  const char *v399; // r8
  char SafetyLevel; // al
  __int64 v401; // rcx
  int v402; // eax
  __int64 v403; // [rsp+20h] [rbp-E0h]
  __int64 v404; // [rsp+20h] [rbp-E0h]
  __int64 v405; // [rsp+20h] [rbp-E0h]
  int v406; // [rsp+20h] [rbp-E0h]
  __int64 v407; // [rsp+28h] [rbp-D8h]
  __int64 v408; // [rsp+28h] [rbp-D8h]
  __int64 v409; // [rsp+28h] [rbp-D8h]
  int v410; // [rsp+28h] [rbp-D8h]
  int v411; // [rsp+30h] [rbp-D0h]
  int v412; // [rsp+30h] [rbp-D0h]
  __int64 v413; // [rsp+38h] [rbp-C8h]
  int v414; // [rsp+40h] [rbp-C0h]
  int v415; // [rsp+48h] [rbp-B8h]
  unsigned int v416; // [rsp+60h] [rbp-A0h] BYREF
  int v417; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v418; // [rsp+68h] [rbp-98h] BYREF
  unsigned int IndexKey; // [rsp+6Ch] [rbp-94h]
  __int64 v420; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v421; // [rsp+78h] [rbp-88h]
  int v422; // [rsp+7Ch] [rbp-84h]
  char v423; // [rsp+80h] [rbp-80h]
  int v424; // [rsp+84h] [rbp-7Ch]
  __int64 v425; // [rsp+88h] [rbp-78h]
  const char **v426; // [rsp+90h] [rbp-70h]
  __int64 v427; // [rsp+98h] [rbp-68h]
  unsigned int v428; // [rsp+A0h] [rbp-60h]
  int v429; // [rsp+A4h] [rbp-5Ch] BYREF
  int v430; // [rsp+A8h] [rbp-58h]
  const char **v431; // [rsp+B0h] [rbp-50h] BYREF
  char *v432; // [rsp+B8h] [rbp-48h]
  unsigned int v433; // [rsp+C0h] [rbp-40h]
  __int64 v434; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v435; // [rsp+D0h] [rbp-30h] BYREF
  int v436; // [rsp+D8h] [rbp-28h]
  unsigned int v437; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v438; // [rsp+E0h] [rbp-20h]
  unsigned int v439; // [rsp+E8h] [rbp-18h]
  __int64 v440; // [rsp+F0h] [rbp-10h]
  char *v441; // [rsp+F8h] [rbp-8h]
  __int64 v442; // [rsp+100h] [rbp+0h] BYREF
  __int64 v443; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v444; // [rsp+110h] [rbp+10h]
  __int64 *v445; // [rsp+118h] [rbp+18h]
  _QWORD v446[3]; // [rsp+120h] [rbp+20h]
  __int128 v447; // [rsp+138h] [rbp+38h] BYREF
  __int128 v448; // [rsp+148h] [rbp+48h]

  v5 = *a1;
  v434 = *a1;
  v443 = a3;
  v435 = 0;
  v447 = 0;
  v420 = a4;
  v448 = 0;
  v9 = a1;
  v445 = a1;
  result = sqlite3GetVdbe(a1);
  v427 = result;
  v11 = result;
  if ( result )
  {
    sqlite3VdbeAddOp3(result, 166, 1, 1, 0);
    *((_DWORD *)v9 + 15) = 2;
    result = sqlite3TwoPartName(v9, a2, a3, &v435);
    v12 = (int)result;
    v430 = result;
    if ( (int)result >= 0 )
    {
      v438 = *(_QWORD *)(v5 + 32);
      if ( (_DWORD)result != 1 || (result = sqlite3OpenTempDatabase(v9), !(_DWORD)result) )
      {
        result = sqlite3NameFromToken(v5, v435);
        v444 = (unsigned __int8 *)result;
        if ( result )
        {
          v13 = 32 * v12;
          v440 = 32 * v12;
          if ( a5 )
            v14 = sqlite3MPrintf(v5, "-%T", a4);
          else
            v14 = sqlite3NameFromToken(v5, a4);
          v15 = (char *)v14;
          v441 = (char *)v14;
          if ( *(_DWORD *)(v443 + 8) )
            v16 = *(_QWORD *)(v438 + 32 * v12);
          else
            v16 = 0;
          v425 = v16;
          if ( (unsigned int)sqlite3AuthCheck((_DWORD)v9, 19, (_DWORD)v444, (_DWORD)v15, v16) )
            goto LABEL_698;
          *(_QWORD *)&v447 = 0;
          *((_QWORD *)&v447 + 1) = v444;
          v448 = (unsigned __int64)v15;
          *(_DWORD *)(v5 + 664) = 0;
          if ( (unsigned int)sqlite3SafetyCheckOk(v5) )
          {
            v18 = *(_QWORD *)(v5 + 24);
            v418 = 1;
            sqlite3_mutex_enter(v18);
            v19 = sqlite3DbNameToBtree(v5, v425);
            v435 = v19;
            if ( v19 )
            {
              sqlite3BtreeEnter(v19);
              v20 = *(_DWORD *)(v5 + 664);
              v21 = sqlite3OsFileControl(*(_QWORD *)(**(_QWORD **)(v435 + 8) + 72LL), 14, &v447);
              v22 = v435;
              v418 = v21;
              *(_DWORD *)(v5 + 664) = v20;
              sqlite3BtreeLeave(v22);
              v13 = v440;
            }
            sqlite3_mutex_leave(*(_QWORD *)(v5 + 24));
            v17 = v418;
          }
          else
          {
            v17 = sqlite3ReportError(21, 185165, "misuse");
            v418 = v17;
          }
          if ( !v17 )
          {
            sqlite3VdbeSetNumCols(v11, 1);
            sqlite3VdbeSetColName(v11, 0, 0, v447, -1);
            returnSingleText(v11, v447);
            sqlite3_free(v447);
            goto LABEL_698;
          }
          if ( v17 != 12 )
          {
            if ( (_QWORD)v447 )
            {
              sqlite3ErrorMsg(v9, "%s", (const char *)v447);
              sqlite3_free(v447);
              v17 = v418;
            }
            goto LABEL_23;
          }
          v23 = pragmaLocate(v444);
          v426 = (const char **)v23;
          v25 = v23;
          if ( !v23 )
            goto LABEL_698;
          if ( (*(_BYTE *)(v23 + 9) & 1) != 0 )
          {
            if ( (unsigned int)sqlite3ReadSchema(v9) )
              goto LABEL_698;
            v25 = (__int64)v426;
          }
          if ( (*(_BYTE *)(v25 + 9) & 2) == 0 && ((*(_BYTE *)(v25 + 9) & 4) == 0 || !v15) )
          {
            setPragmaResultColumnNames(v11, v25);
            v25 = (__int64)v426;
          }
          v26 = *(unsigned __int8 *)(v25 + 8);
          if ( v26 <= 0x16 )
          {
            if ( v26 != 22 )
            {
              if ( v26 <= 0xC )
              {
                if ( v26 == 12 )
                {
                  *((_DWORD *)v9 + 15) = 3;
                  for ( i = 0; (signed int)i < *(_DWORD *)(v5 + 40); ++i )
                  {
                    v69 = *(_QWORD *)(32LL * (int)i + *(_QWORD *)(v5 + 32) + 8);
                    if ( v69 )
                    {
                      v70 = sqlite3PagerFilename(**(_QWORD **)(v69 + 8), 1);
                      sqlite3VdbeMultiLoad(v11, v73, "iss", i, *(_QWORD *)(v71 + v72), v70, v411, v413, v414, v415);
                    }
                  }
                  goto LABEL_698;
                }
                if ( v26 <= 7 )
                {
                  if ( v26 == 7 )
                  {
                    if ( v15 )
                    {
                      v417 = 1;
                      Int32 = sqlite3GetInt32(v15, &v417);
                      v50 = v417;
                      if ( Int32 )
                        sqlite3BtreeSetSpillSize(*(_QWORD *)(v438 + v13 + 8), (unsigned int)v417);
                      v51 = *(_QWORD *)(v5 + 48);
                      LOBYTE(v49) = v50 != 0;
                      Boolean = sqlite3GetBoolean(v15, v49);
                      v53 = v51;
                      v54 = v51 | 0x20;
                      v55 = v53 & 0xFFFFFFFFFFFFFFDFuLL;
                      if ( !Boolean )
                        v54 = v55;
                      *(_QWORD *)(v5 + 48) = v54;
                      goto LABEL_86;
                    }
                    if ( (*(_BYTE *)(v5 + 48) & 0x20) != 0 )
                      v37 = sqlite3BtreeSetSpillSize(*(_QWORD *)(v438 + v13 + 8), 0);
                    else
                      v37 = 0;
LABEL_62:
                    v31 = v37;
                    goto LABEL_697;
                  }
                  v27 = v26 - 1;
                  if ( !v27 )
                  {
                    v427 = 0;
                    if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                      *(_DWORD *)(v5 + 744) = v427 & 0x7FFFFFFF;
                    v31 = *(int *)(v5 + 744);
                    goto LABEL_697;
                  }
                  v28 = v27 - 1;
                  if ( v28 )
                  {
                    v29 = v28 - 1;
                    if ( v29 )
                    {
                      v30 = v29 - 1;
                      if ( v30 )
                      {
                        if ( v30 == 2 )
                        {
                          if ( !v15 )
                          {
                            v31 = *(int *)(*(_QWORD *)(v438 + v13 + 24) + 116LL);
                            goto LABEL_697;
                          }
                          v417 = 0;
                          sqlite3GetInt32(v15, &v417);
                          v32 = v438;
                          *(_DWORD *)(*(_QWORD *)(v438 + v13 + 24) + 116LL) = v417;
                          v33 = *(_QWORD *)(v32 + v13 + 24);
                          v34 = *(_QWORD *)(v32 + v13 + 8);
LABEL_226:
                          sqlite3BtreeSetCacheSize(v34, *(unsigned int *)(v33 + 116));
                          goto LABEL_698;
                        }
LABEL_593:
                        if ( v15 )
                        {
                          v416 = 0;
                          sqlite3GetInt32(v15, &v416);
                          sqlite3_busy_timeout(v5, v416);
                        }
                        v31 = *(int *)(v5 + 748);
                        goto LABEL_697;
                      }
                      if ( !v15 )
                      {
                        setPragmaResultColumnNames(v11, v25);
                        v31 = (*(_QWORD *)(v5 + 48) & (unsigned __int64)v426[2]) != 0;
                        goto LABEL_697;
                      }
                      v35 = *(_QWORD *)(v25 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                      if ( *(_BYTE *)(v5 + 101) )
                        v35 = *(_QWORD *)(v25 + 16);
                      if ( (unsigned __int8)sqlite3GetBoolean(v15, 0) )
                      {
                        if ( (v35 & 1) == 0 || (*(_DWORD *)(v5 + 48) & 0x10000000) == 0 )
                          *(_QWORD *)(v5 + 48) |= v35;
                      }
                      else
                      {
                        *(_QWORD *)(v5 + 48) &= ~v35;
                        if ( v35 == 0x80000 )
                        {
                          *(_QWORD *)(v5 + 768) = 0;
                        }
                        else if ( (v35 & 1) != 0 && !(unsigned int)sqlite3_stricmp(v15, "reset") )
                        {
                          sqlite3ResetAllSchemasOfConnection(v5);
                        }
                      }
                      sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
LABEL_86:
                      setAllPagerFlags(v5);
                      goto LABEL_698;
                    }
                    v36 = *(_QWORD *)(v438 + v13 + 8);
                    if ( v15 )
                    {
                      AutoVacuum = getAutoVacuum(v15);
                      *(_BYTE *)(v5 + 106) = AutoVacuum;
                      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v36, AutoVacuum) && AutoVacuum - 1 <= 1 )
                      {
                        v39 = *(_DWORD *)(v11 + 144);
                        v40 = (_DWORD *)sqlite3VdbeAddOpList(v11, 5, qword_1800A77F0);
                        v40[14] = v39 + 4;
                        v40[27] = AutoVacuum - 1;
                        v40[1] = v12;
                        v40[7] = v12;
                        v40[25] = v12;
                        sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                      }
                      goto LABEL_698;
                    }
                    v37 = sqlite3BtreeGetAutoVacuum(v36);
                    goto LABEL_62;
                  }
                  v41 = *(_DWORD *)(v25 + 16);
                  sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                  if ( v15 && (*(_BYTE *)(v43 + 9) & 8) == 0 )
                  {
                    v417 = 0;
                    v45 = sqlite3VdbeAddOpList(v42, v44, qword_1800A6560);
                    *(_DWORD *)(v45 + 4) = v12;
                    *(_DWORD *)(v45 + 28) = v12;
                    *(_DWORD *)(v45 + 32) = v41;
                    sqlite3GetInt32(v15, &v417);
                    *(_DWORD *)(v45 + 36) = v417;
                    *(_WORD *)(v45 + 26) = 1;
                    if ( v41 == 1 && (*(_DWORD *)(v5 + 48) & 0x10000000) != 0 )
                      *(_BYTE *)(v45 + 24) = -69;
                    goto LABEL_698;
                  }
                  v46 = (_DWORD *)sqlite3VdbeAddOpList(v42, 3, &qword_1800A7328);
                  v47 = v11;
                  v46[1] = v12;
                  v46[7] = v12;
                  v46[9] = v41;
LABEL_72:
                  sqlite3VdbeReusable(v47);
                  goto LABEL_698;
                }
                v56 = v26 - 8;
                if ( !v56 )
                {
                  if ( v15 )
                  {
                    v67 = sqlite3GetBoolean(v15, 0);
                    sqlite3RegisterLikeFunctions(v5, v67);
                  }
                  goto LABEL_698;
                }
                v57 = v56 - 1;
                if ( v57 )
                {
                  v58 = v57 - 1;
                  if ( !v58 )
                  {
                    *((_DWORD *)v9 + 15) = 1;
                    v62 = 0;
                    for ( j = 0; ; j = v62 )
                    {
                      v64 = sqlite3_compileoption_get(j);
                      v47 = v11;
                      if ( !v64 )
                        break;
                      ++v62;
                      sqlite3VdbeAddOp4(v11, 118, 0, 1, 0, v64, 0);
                      sqlite3VdbeAddOp3(v11, 84, 1, 1, 0);
                    }
                    goto LABEL_72;
                  }
                  if ( v58 != 1 )
                    goto LABEL_593;
                  v59 = sqlite3MutexAlloc(11);
                  sqlite3_mutex_enter(v59);
                  if ( !v15 )
                  {
                    v60 = sqlite3_data_directory;
LABEL_617:
                    returnSingleText(v11, v60);
LABEL_622:
                    v364 = sqlite3MutexAlloc(11);
                    sqlite3_mutex_leave(v364);
                    goto LABEL_698;
                  }
                  if ( !*v15
                    || (v61 = *(_QWORD *)v5,
                        v417 = 0,
                        !(*(unsigned int (__fastcall **)(__int64, char *, __int64, int *))(v61 + 56))(
                           v61,
                           v15,
                           1,
                           &v417))
                    && v417 )
                  {
                    sqlite3_free(sqlite3_data_directory);
                    if ( *v15 )
                      sqlite3_data_directory = sqlite3_mprintf("%s", v15);
                    else
                      sqlite3_data_directory = 0;
                    goto LABEL_622;
                  }
                  goto LABEL_621;
                }
                *((_DWORD *)v9 + 15) = 2;
                v65 = *(__int64 ***)(v5 + 632);
                v66 = 0;
                if ( !v65 )
                  goto LABEL_698;
                do
                {
                  sqlite3VdbeMultiLoad(v11, 1, "is", v66, *v65[2], v407, v411, v413, v414, v415);
                  v65 = (__int64 **)*v65;
                  ++v66;
                }
                while ( v65 );
LABEL_683:
                v15 = v441;
                goto LABEL_698;
              }
              v74 = v26 - 13;
              if ( !v74 )
              {
                sqlite3VdbeUsesBtree(v11, (unsigned int)v12);
                if ( !v15 )
                {
                  *((_DWORD *)v9 + 15) += v150;
                  v151 = (_DWORD *)sqlite3VdbeAddOpList(v149, 9, qword_1800A6940);
                  v151[1] = v12;
                  v151[7] = v12;
                  v151[37] = -2000;
                  goto LABEL_698;
                }
                v417 = 0;
                sqlite3GetInt32(v15, &v417);
                v152 = sqlite3AbsInt32((unsigned int)v417);
                sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                sqlite3VdbeAddOp3(v11, 100, v12, 3, v152);
                v153 = v440;
                v154 = v438;
                *(_DWORD *)(*(_QWORD *)(v438 + v440 + 24) + 116LL) = v152;
                v33 = *(_QWORD *)(v154 + v153 + 24);
                v34 = *(_QWORD *)(v154 + v153 + 8);
                goto LABEL_226;
              }
              v75 = v74 - 1;
              if ( v75 )
              {
                v76 = v75 - 1;
                if ( !v76 )
                {
                  _mm_lfence();
                  v118 = *((_DWORD *)v9 + 15);
                  v119 = v118 + 1;
                  v118 += 5;
                  *((_DWORD *)v9 + 15) = v118;
                  v417 = v118;
                  v120 = *(_QWORD *)(v5 + 32);
                  v422 = v119;
                  v121 = *(_QWORD **)(*(_QWORD *)(v120 + v13 + 24) + 16LL);
                  while ( v121 )
                  {
                    if ( v15 )
                    {
                      Table = sqlite3LocateTable(v9, 0, v15, v425);
                      v121 = 0;
                    }
                    else
                    {
                      Table = v121[2];
                      v121 = (_QWORD *)*v121;
                    }
                    v440 = (__int64)v121;
                    if ( Table && !*(_BYTE *)(Table + 63) && *(_QWORD *)(Table + 72) )
                    {
                      v123 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Table + 96));
                      v124 = *(_QWORD *)(v5 + 32);
                      IndexKey = v123;
                      v125 = *(_QWORD *)(32LL * (int)v123 + v124);
                      v425 = v125;
                      sqlite3CodeVerifySchema(v9, v123);
                      sqlite3TableLock(v9, IndexKey, *(unsigned int *)(Table + 40), 0, *(_QWORD *)Table);
                      v126 = v417 + *(__int16 *)(Table + 54);
                      if ( *((_DWORD *)v9 + 15) < v126 )
                        *((_DWORD *)v9 + 15) = v126;
                      sqlite3OpenTable((_DWORD)v9, 0, IndexKey, Table, 102);
                      sqlite3VdbeAddOp4(v11, 118, 0, v422, 0, *(_QWORD *)Table, 0);
                      v127 = *(_QWORD *)(Table + 72);
                      v128 = 1;
                      while ( 1 )
                      {
                        v435 = v127;
                        v418 = v128;
                        if ( !v127 )
                          break;
                        v129 = sqlite3FindTable(v5, *(_QWORD *)(v127 + 16), v125);
                        v427 = v129;
                        if ( v129 )
                        {
                          v130 = *(unsigned int *)(v129 + 40);
                          v404 = *(_QWORD *)v129;
                          v431 = 0;
                          sqlite3TableLock(v9, IndexKey, v130, 0, v404);
                          if ( (unsigned int)sqlite3FkLocateIndex((_DWORD)v9, v427, v435, (unsigned int)&v431, 0) )
                            goto LABEL_698;
                          if ( v431 )
                          {
                            sqlite3VdbeAddOp3(v11, 102, v418, *((_DWORD *)v431 + 22), IndexKey);
                            sqlite3VdbeSetP4KeyInfo(v9, v431);
                          }
                          else
                          {
                            sqlite3OpenTable((_DWORD)v9, v418, IndexKey, v427, 102);
                          }
                        }
                        v128 = v418 + 1;
                        v127 = *(_QWORD *)(v435 + 8);
                      }
                      if ( *((_DWORD *)v9 + 14) < v128 )
                        *((_DWORD *)v9 + 14) = v128;
                      v131 = sqlite3VdbeAddOp3(v11, 36, 0, 0, 0);
                      v132 = *(const char ***)(Table + 72);
                      v437 = v131;
                      IndexKey = 1;
                      v426 = v132;
                      if ( v132 )
                      {
                        v133 = v417;
                        v421 = v422 + 2;
                        v428 = v422 + 1;
                        do
                        {
                          v134 = v125;
                          v135 = v426;
                          v136 = sqlite3FindTable(v5, v426[2], v134);
                          v420 = v136;
                          v431 = 0;
                          v435 = 0;
                          if ( v136 )
                            sqlite3FkLocateIndex((_DWORD)v9, v136, (_DWORD)v426, (unsigned int)&v431, (__int64)&v435);
                          v137 = *((_DWORD *)v9 + 18) - 1;
                          *((_DWORD *)v9 + 18) = v137;
                          v138 = v133 + *((_DWORD *)v135 + 10);
                          v418 = v137;
                          if ( *((_DWORD *)v9 + 15) < v138 )
                            *((_DWORD *)v9 + 15) = v138;
                          v430 = *((_DWORD *)v135 + 10);
                          if ( v430 > 0 )
                          {
                            v139 = v435;
                            for ( k = 0; k < v430; ++k )
                            {
                              if ( v139 )
                                v141 = *(_DWORD *)(v139 + 4LL * k);
                              else
                                v141 = (int)v135[2 * k + 8];
                              sqlite3ExprCodeGetColumnOfTable(v11, Table, 0, v141, k + v133);
                              sqlite3VdbeAddOp3(v11, 51, k + v133, v418, 0);
                              v135 = v426;
                              v430 = *((_DWORD *)v426 + 10);
                            }
                            v5 = v434;
                            v9 = v445;
                          }
                          if ( v431 )
                          {
                            v142 = *((_DWORD *)v135 + 10);
                            v143 = sqlite3IndexAffinityStr(v5, v431);
                            sqlite3VdbeAddOp4(v11, 96, v133, v142, 0, v143, v430);
                            v135 = v426;
                            sqlite3VdbeAddOp4Int(v11, 29, IndexKey, v418, v133, *((_DWORD *)v426 + 10));
                          }
                          else if ( v420 )
                          {
                            sqlite3VdbeAddOp3(v11, 30, IndexKey, *(_DWORD *)(v11 + 144) + 2, v133);
                            sqlite3VdbeAddOp3(v11, 9, 0, v418, 0);
                          }
                          sqlite3VdbeAddOp3(v11, (*(_DWORD *)(Table + 48) & 0x80u) != 0 ? 75 : 135, 0, v428, 0);
                          LODWORD(v405) = IndexKey - 1;
                          sqlite3VdbeMultiLoad(v11, v421, "siX", v135[2], v405, v409, v412, v413, v414, v415);
                          sqlite3VdbeAddOp3(v11, 84, v422, 4, 0);
                          sqlite3VdbeResolveLabel(v11, v418);
                          sqlite3DbFree(v5, v435);
                          v144 = (const char **)v135[1];
                          ++IndexKey;
                          v426 = v144;
                          v87 = v144 == 0;
                          v125 = v425;
                        }
                        while ( !v87 );
                        v15 = v441;
                        v131 = v437;
                      }
                      sqlite3VdbeAddOp3(v11, 39, 0, v131 + 1, 0);
                      *(_DWORD *)(sqlite3VdbeGetOp(v11, v437) + 8) = *(_DWORD *)(v11 + 144);
                      v121 = (_QWORD *)v440;
                    }
                  }
                  goto LABEL_698;
                }
                v77 = v76 - 1;
                if ( !v77 )
                {
                  if ( !v15 )
                    goto LABEL_698;
                  v103 = sqlite3FindTable(v5, v15, v425);
                  v104 = v103;
                  if ( !v103 )
                    goto LABEL_698;
                  if ( *(_BYTE *)(v103 + 63) )
                    goto LABEL_698;
                  v105 = *(_QWORD *)(v103 + 72);
                  if ( !v105 )
                    goto LABEL_698;
                  v106 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v103 + 96));
                  v418 = v107;
                  *((_DWORD *)v9 + 15) = 8;
                  sqlite3CodeVerifySchema(v9, v106);
                  v109 = v418;
                  v110 = 0;
                  do
                  {
                    v111 = 0;
                    if ( *(int *)(v105 + 40) > 0 )
                    {
                      do
                      {
                        LOBYTE(v110) = *(_BYTE *)(v105 + 45);
                        actionName(v110, v108, v111);
                        LOBYTE(v112) = *(_BYTE *)(v105 + 46);
                        v115 = actionName(v112, v113, v114);
                        LODWORD(v403) = v111;
                        sqlite3VdbeMultiLoad(
                          v11,
                          1,
                          "iissssss",
                          v418,
                          v403,
                          *(_QWORD *)(v105 + 16),
                          *(_QWORD *)(*(_QWORD *)(v104 + 8) + 24LL * *(int *)(v105 + 16 * (v116 + 4))),
                          *(_QWORD *)(v105 + 16 * v116 + 72),
                          v115,
                          v117);
                        ++v111;
                      }
                      while ( v111 < *(_DWORD *)(v105 + 40) );
                      v109 = v418;
                      v110 = 0;
                    }
                    v105 = *(_QWORD *)(v105 + 8);
                    v418 = ++v109;
                  }
                  while ( v105 );
                  goto LABEL_683;
                }
                v78 = v77 - 1;
                if ( !v78 )
                {
                  v99 = (*(_DWORD *)(v5 + 44) >> 5) & 1;
                  *((_DWORD *)v9 + 15) = 6;
                  for ( m = 0; m != 23; ++m )
                  {
                    for ( n = qword_1800B5D10[m]; n; n = *(_QWORD *)(n + 64) )
                      pragmaFunclistLine(v11, n, 1, v99);
                  }
                  v102 = *(_QWORD **)(v5 + 608);
                  v15 = v441;
                  while ( v102 )
                  {
                    pragmaFunclistLine(v11, v102[2], 0, v99);
                    v102 = (_QWORD *)*v102;
                  }
                  goto LABEL_698;
                }
                v79 = v78 - 1;
                if ( v79 )
                {
                  v80 = v79 - 1;
                  if ( !v80 )
                  {
                    v417 = 0;
                    if ( !v15 || !(unsigned int)sqlite3GetInt32(v15, &v417) || (v96 = v417, v417 <= 0) )
                      v96 = 0x7FFFFFFF;
                    sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                    sqlite3VdbeAddOp3(v11, 71, v96, 1, 0);
                    v97 = sqlite3VdbeAddOp3(v11, 62, v12, 0, 0);
                    sqlite3VdbeAddOp3(v11, 84, 1, 0, 0);
                    sqlite3VdbeAddOp3(v11, 86, 1, -1, 0);
                    sqlite3VdbeAddOp3(v11, 50, 1, v97, 0);
                    *(_DWORD *)(sqlite3VdbeGetOp(v11, v97) + 8) = *(_DWORD *)(v11 + 144);
                    goto LABEL_698;
                  }
                  v81 = v80 - 1;
                  if ( v81 )
                  {
                    if ( v81 == 1 )
                    {
                      if ( v15 )
                      {
                        v82 = sqlite3FindTable(v5, v15, v425);
                        v83 = v82;
                        if ( v82 )
                        {
                          v84 = sqlite3SchemaToIndex(v5, *(_QWORD *)(v82 + 96));
                          *((_DWORD *)v9 + 15) = 5;
                          sqlite3CodeVerifySchema(v9, v84);
                          v85 = *(_QWORD *)(v83 + 16);
                          v86 = 0;
                          while ( v85 )
                          {
                            v87 = *(_QWORD *)(v85 + 72) == 0;
                            v446[0] = "c";
                            v446[1] = "u";
                            LODWORD(v413) = !v87;
                            v446[2] = "pk";
                            LODWORD(v407) = *(_BYTE *)(v85 + 98) != 0;
                            sqlite3VdbeMultiLoad(
                              v11,
                              1,
                              "isisi",
                              v86,
                              *(_QWORD *)v85,
                              v407,
                              v446[*(_DWORD *)(v85 + 100) & 3],
                              v413,
                              v414,
                              v415);
                            v85 = *(_QWORD *)(v85 + 40);
                            ++v86;
                          }
                        }
                      }
                      goto LABEL_698;
                    }
                    goto LABEL_593;
                  }
                  if ( !v15 )
                    goto LABEL_698;
                  Index = sqlite3FindIndex(v5, v15, v425);
                  if ( !Index )
                  {
                    v89 = sqlite3LocateTable(v9, 2, v15, v425);
                    if ( !v89 )
                      goto LABEL_698;
                    if ( *(char *)(v89 + 48) >= 0 )
                      goto LABEL_698;
                    Index = sqlite3PrimaryKeyIndex(v89);
                    if ( !Index )
                      goto LABEL_698;
                  }
                  v90 = sqlite3SchemaToIndex(v5, *(_QWORD *)(Index + 48));
                  v91 = v426;
                  v92 = v426[2] != 0;
                  v417 = *(unsigned __int16 *)((v92 ? 2 : 0) + Index + 94);
                  *((_DWORD *)v9 + 15) = v92 ? 6 : 3;
                  v420 = *(_QWORD *)(Index + 24);
                  sqlite3CodeVerifySchema(v9, v90);
                  if ( !v417 )
                    goto LABEL_698;
                  v93 = 0;
                  do
                  {
                    v94 = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v93);
                    if ( (v94 & 0x8000u) == 0LL )
                      v95 = *(_QWORD *)(*(_QWORD *)(v420 + 8) + 24 * v94);
                    else
                      v95 = 0;
                    LODWORD(v403) = *(__int16 *)(*(_QWORD *)(Index + 8) + 2LL * v93);
                    sqlite3VdbeMultiLoad(v11, 1, "iisX", v93, v403, v95, v411, v413, v414, v415);
                    if ( v91[2] )
                    {
                      LODWORD(v408) = v93 < *(unsigned __int16 *)(Index + 94);
                      sqlite3VdbeMultiLoad(
                        v11,
                        4,
                        "isiX",
                        *(unsigned __int8 *)(*(_QWORD *)(Index + 56) + v93),
                        *(_QWORD *)(*(_QWORD *)(Index + 64) + 8LL * v93),
                        v408,
                        v411,
                        v413,
                        v414,
                        v415);
                    }
                    sqlite3VdbeAddOp3(v11, 84, 1, *((_DWORD *)v9 + 15), 0);
                    ++v93;
                  }
                  while ( (int)v93 < v417 );
                  goto LABEL_682;
                }
                v427 = 0;
                if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                  sqlite3_hard_heap_limit64(-1);
                v98 = sqlite3_hard_heap_limit64(-1);
LABEL_696:
                v31 = v98;
                goto LABEL_697;
              }
              if ( v15 )
              {
                if ( (*(_BYTE *)(v5 + 44) & 0x40) == 0 )
                {
                  for ( ii = &off_18009D270; *ii; ii += 2 )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v15, *ii) )
                    {
                      if ( *((_BYTE *)ii + 8) )
                        v148 = *((_BYTE *)ii + 8);
                      LOBYTE(v147) = v148;
                      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v5 + 32) + 24LL) + 113LL) = v148;
                      sqlite3SetTextEncoding(v5, v147);
                      break;
                    }
                  }
                  if ( !*ii )
                    sqlite3ErrorMsg(v9, "unsupported encoding: %s", v15);
                }
                goto LABEL_698;
              }
              if ( (unsigned int)sqlite3ReadSchema(v9) )
                goto LABEL_698;
              v145 = (&off_18009D270)[2 * *(unsigned __int8 *)(*v9 + 100)];
LABEL_473:
              returnSingleText(v11, v145);
              goto LABEL_698;
            }
            v155 = v430;
            v425 = 0;
            v87 = *((_BYTE *)qword_18009E760 + *v444) == 113;
            v423 = *((_BYTE *)qword_18009E760 + *v444);
            LODWORD(v438) = v87;
            v87 = *(_QWORD *)v443 == 0;
            v156 = 100;
            *((_DWORD *)v9 + 15) = 6;
            if ( v87 )
              v155 = -1;
            v422 = 100;
            v430 = v155;
            v418 = 100;
            if ( !v15 )
              goto LABEL_238;
            if ( (unsigned int)sqlite3GetInt32(*(_QWORD *)v420, &v418) )
            {
              v156 = v418;
              v422 = v418;
              if ( (int)v418 > 0 )
                goto LABEL_238;
              v156 = 100;
            }
            else
            {
              if ( v155 < 0 )
                v157 = 0;
              else
                v157 = *(_QWORD *)(32LL * v155 + *(_QWORD *)(v5 + 32));
              v425 = sqlite3LocateTable(v9, 0, v15, v157);
              v156 = v418;
            }
            v422 = v156;
LABEL_238:
            sqlite3VdbeAddOp3(v11, 71, v156 - 1, 1, 0);
            v158 = 0;
            v436 = 0;
            if ( *(int *)(v5 + 40) <= 0 )
              goto LABEL_420;
            while ( 1 )
            {
              if ( v155 < 0 || v158 == v155 )
              {
                sqlite3CodeVerifySchema(v9, v158);
                v159 = 32LL * v436;
                *((_BYTE *)v9 + 35) = 0;
                v160 = *(_QWORD *)(v5 + 32);
                v426 = (const char **)v159;
                v161 = *(_QWORD *)(v159 + v160 + 24);
                v162 = 0;
                v435 = v161;
                v163 = *(_QWORD **)(v161 + 16);
                if ( v163 )
                {
                  do
                  {
                    v164 = v163[2];
                    if ( !v425 || v425 == v164 )
                    {
                      if ( *(char *)(v164 + 48) >= 0 )
                        ++v162;
                      v165 = *(_QWORD *)(v164 + 16);
                      while ( v165 )
                      {
                        v165 = *(_QWORD *)(v165 + 40);
                        ++v162;
                      }
                    }
                    v163 = (_QWORD *)*v163;
                  }
                  while ( v163 );
                  if ( v162 )
                  {
                    v166 = v162 + 1;
                    if ( !v425 )
                      v166 = v162;
                    v167 = (int *)sqlite3DbMallocRawNN(v5, 4LL * v166 + 4);
                    v420 = (__int64)v167;
                    if ( !v167 )
                    {
LABEL_419:
                      v15 = v441;
LABEL_420:
                      v280 = sqlite3VdbeAddOpList(v11, 7, qword_1800A6F40);
                      if ( v280 )
                      {
                        *(_DWORD *)(v280 + 8) = 1 - v422;
                        *(_BYTE *)(v280 + 49) = -1;
                        *(_QWORD *)(v280 + 64) = "ok";
                        *(_BYTE *)(v280 + 121) = -1;
                        v281 = sqlite3ErrStr(11);
                        *(_QWORD *)(v282 + 136) = v281;
                      }
                      Op = sqlite3VdbeGetOp(v11, 0);
                      *(_DWORD *)(Op + 12) = v284;
                      goto LABEL_698;
                    }
                    v168 = 0;
                    if ( v425 )
                    {
                      v168 = 1;
                      v167[1] = 0;
                    }
                    v169 = *(_QWORD **)(v435 + 16);
                    if ( v169 )
                    {
                      v170 = v425;
                      do
                      {
                        v171 = v169[2];
                        if ( !v170 || v170 == v171 )
                        {
                          if ( *(char *)(v171 + 48) >= 0 )
                          {
                            v172 = v168++;
                            v167[v172 + 1] = *(_DWORD *)(v171 + 40);
                          }
                          for ( jj = *(_QWORD *)(v171 + 16); jj; jj = *(_QWORD *)(jj + 40) )
                            v167[++v168] = *(_DWORD *)(jj + 88);
                        }
                        v169 = (_QWORD *)*v169;
                      }
                      while ( v169 );
                      v11 = v427;
                    }
                    *v167 = v168;
                    if ( *((_DWORD *)v9 + 15) < v168 + 8 )
                      *((_DWORD *)v9 + 15) = v168 + 8;
                    sqlite3VdbeAddOp3(v11, 75, 0, 8, v168 + 8);
                    *((_BYTE *)v9 + 31) = 0;
                    *((_DWORD *)v9 + 11) = 0;
                    sqlite3VdbeAddOp4(v11, 155, 1, v168, 8, v420, -14);
                    sqlite3VdbeChangeP5(v11, (unsigned __int8)v436);
                    v175 = sqlite3VdbeAddOp3(v174, 51, 2, 0, 0);
                    v176 = sqlite3MPrintf(
                             v5,
                             "*** in database %s ***\n",
                             *(const char **)((char *)v426 + *(_QWORD *)(v5 + 32)));
                    sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v176, -6);
                    sqlite3VdbeAddOp3(v11, 112, 2, 3, 3);
                    integrityCheckResultRow(v11);
                    *(_DWORD *)(sqlite3VdbeGetOp(v11, v175) + 8) = *(_DWORD *)(v11 + 144);
                    sqlite3VdbeAddOp4(v11, 118, 0, 2, 0, (__int64)"wrong # of entries in index ", 0);
                    v177 = 0;
                    v178 = *(_QWORD *)(v435 + 16);
                    v440 = v178;
                    if ( v178 )
                    {
                      v179 = v425;
                      v180 = v425 != 0;
                      do
                      {
                        v181 = *(_QWORD *)(v178 + 16);
                        if ( !v179 || v179 == v181 )
                        {
                          v87 = *(_BYTE *)(v181 + 48) >= 0;
                          v182 = v180;
                          v418 = v180;
                          if ( v87 )
                          {
                            ++v180;
                            v183 = (const char ***)(v181 + 16);
                          }
                          else
                          {
                            v184 = *(_QWORD *)(v181 + 16);
                            if ( v184 )
                            {
                              do
                              {
                                v183 = (const char ***)(v181 + 16);
                                if ( (*(_DWORD *)(v184 + 100) & 3) == 2 )
                                  break;
                                v184 = *(_QWORD *)(v184 + 40);
                                v418 = ++v182;
                              }
                              while ( v184 );
                            }
                            else
                            {
                              v183 = (const char ***)(v181 + 16);
                            }
                          }
                          v185 = *v183;
                          v426 = v185;
                          if ( v185 )
                          {
                            v186 = v180 + 8;
                            do
                            {
                              if ( !v185[9] )
                              {
                                v187 = sqlite3VdbeAddOp3(v11, 54, v186, 0, v182 + 8);
                                sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)*v426, 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 2, 3);
                                integrityCheckResultRow(v11);
                                v188 = sqlite3VdbeGetOp(v11, v187);
                                v177 = 0;
                                *(_DWORD *)(v188 + 8) = *(_DWORD *)(v11 + 144);
                                v185 = v426;
                              }
                              v185 = (const char **)v185[5];
                              ++v180;
                              v182 = v418;
                              ++v186;
                              v426 = v185;
                            }
                            while ( v185 );
                          }
                        }
                        v179 = v425;
                        v178 = *(_QWORD *)v440;
                        v440 = v178;
                      }
                      while ( v178 );
                      v5 = v434;
                      v9 = v445;
                    }
                    v189 = v435;
                    v190 = *(_QWORD *)(v435 + 16);
                    v420 = v190;
                    if ( v190 )
                    {
                      v191 = (const char **)v425;
                      while ( 1 )
                      {
                        v192 = *(const char ***)(v190 + 16);
                        v431 = v192;
                        v429 = v177;
                        v437 = v177;
                        if ( v191 && v191 != v192 || *((_BYTE *)v192 + 63) != (_BYTE)v177 )
                          goto LABEL_399;
                        if ( v423 == 113 || *((char *)v192 + 48) >= 0 )
                        {
                          v440 = v177;
                          v418 = v177;
                        }
                        else
                        {
                          v440 = sqlite3PrimaryKeyIndex(v192);
                          TempRange = sqlite3GetTempRange(v9, *(unsigned __int16 *)(v440 + 94), v193);
                          v196 = *(unsigned __int16 *)(v195 + 94) - 1;
                          v418 = TempRange;
                          sqlite3VdbeAddOp3(v11, 75, 1, TempRange, TempRange + v196);
                          v177 = 0;
                        }
                        sqlite3OpenTableAndIndices(
                          (_DWORD)v9,
                          (_DWORD)v192,
                          102,
                          0,
                          1,
                          v177,
                          (__int64)&v429,
                          (__int64)&v437);
                        sqlite3VdbeAddOp3(v11, 71, 0, 7, 0);
                        if ( v192[2] )
                        {
                          v197 = 8;
                          v198 = v192[2];
                          do
                          {
                            sqlite3VdbeAddOp3(v11, 71, 0, v197, 0);
                            v198 = (const char *)*((_QWORD *)v198 + 5);
                            ++v197;
                          }
                          while ( v198 );
                          v5 = v434;
                          v9 = v445;
                          v192 = v431;
                        }
                        sqlite3VdbeAddOp3(v11, 36, v429, 0, 0);
                        v199 = sqlite3VdbeAddOp3(v11, 86, 7, 1, 0);
                        v87 = *((_BYTE *)v192 + 48) >= 0;
                        LODWORD(v443) = v199;
                        if ( v87 )
                        {
                          v200 = *((__int16 *)v192 + 27);
                          v201 = -1;
                          if ( v200 > 0 )
                          {
                            for ( kk = 0; kk < v200; ++kk )
                            {
                              v203 = v201 + 1;
                              if ( (v192[1][24 * kk + 18] & 0x20) != 0 )
                                v203 = v201;
                              v201 = v203;
                            }
                          }
                          v204 = v201 - 1;
                          if ( v201 != *((__int16 *)v192 + 26) )
                            v204 = v201;
                        }
                        else
                        {
                          v204 = *(unsigned __int16 *)(sqlite3PrimaryKeyIndex(v192) + 96) - 1;
                        }
                        if ( v204 >= 0 )
                        {
                          sqlite3VdbeAddOp3(v11, 94, v429, v204, 3);
                          sqlite3VdbeTypeofColumn(v11, 3);
                        }
                        if ( v423 != 113 && v440 )
                        {
                          v205 = sqlite3VdbeAddOp4Int(v11, 41, v429, 0, v418, *(unsigned __int16 *)(v440 + 94));
                          sqlite3VdbeAddOp3(v11, 51, v418, 0, 0);
                          v206 = sqlite3MPrintf(v5, "row not in PRIMARY KEY order for %s", *v431);
                          sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v206, -6);
                          integrityCheckResultRow(v11);
                          *(_DWORD *)(sqlite3VdbeGetOp(v11, v205) + 8) = *(_DWORD *)(v11 + 144);
                          v207 = sqlite3VdbeGetOp(v11, v205 + 1);
                          v208 = 0;
                          *(_DWORD *)(v207 + 8) = *(_DWORD *)(v11 + 144);
                          if ( *(_WORD *)(v440 + 94) )
                          {
                            v209 = v429;
                            v210 = v440;
                            do
                            {
                              sqlite3ExprCodeLoadIndexColumn((_DWORD)v9, v210, v209, v208, v208 + v418);
                              ++v208;
                            }
                            while ( v208 < *(unsigned __int16 *)(v210 + 94) );
                            v11 = v427;
                            v5 = v434;
                            v192 = v431;
                          }
                          else
                          {
                            v192 = v431;
                          }
                        }
                        v211 = 0;
                        v212 = (_DWORD)v192[6] & 0x10000;
                        v213 = *((_WORD *)v192 + 27) > 0;
                        v417 = v212;
                        while ( 1 )
                        {
                          v433 = v211;
                          if ( !v213 )
                            break;
                          if ( (_DWORD)v211 == *((__int16 *)v192 + 26) )
                            goto LABEL_358;
                          v214 = (__int64)&v192[1][24 * (int)v211];
                          v426 = (const char **)v214;
                          if ( v212 )
                          {
                            v215 = (*(_DWORD *)(v214 + 8) & 0xF0u) > 0x10;
                            v439 = v215;
                          }
                          else if ( *(char *)(v214 + 12) <= 65 )
                          {
                            v215 = 0;
                            v439 = 0;
                          }
                          else
                          {
                            v215 = 1;
                            v439 = 1;
                          }
                          if ( (*(_BYTE *)(v214 + 8) & 0xF) != 0 || v215 )
                          {
                            v87 = (*(_BYTE *)(v214 + 18) & 0x20) == 0;
                            IndexKey = 5;
                            if ( v87 )
                            {
                              if ( *(_WORD *)(v214 + 16) )
                              {
                                v442 = 0;
                                v218 = sqlite3ColumnExpr(v192);
                                LOBYTE(v219) = *v219;
                                LOBYTE(v220) = *(_BYTE *)(v5 + 100);
                                sqlite3ValueFromExpr(v5, v218, v220, (_DWORD)v219, (__int64)&v442);
                                if ( v442 )
                                {
                                  IndexKey = *((unsigned __int8 *)qword_18009EC50 + (*(_WORD *)(v442 + 20) & 0x3F));
                                  sqlite3ValueFree();
                                }
                                v211 = v433;
                              }
                              v87 = *((_BYTE *)v192 + 48) >= 0;
                              v424 = v429;
                              if ( v87 )
                              {
                                v224 = sqlite3TableColumnToStorage(v192, v211);
                                v216 = v424;
                              }
                              else
                              {
                                v221 = sqlite3PrimaryKeyIndex(v192);
                                v224 = sqlite3TableColumnToIndex(v221, v222, v223);
                              }
                              v217 = v224;
                            }
                            else
                            {
                              sqlite3ExprCodeGetColumnOfTable(v11, (_DWORD)v192, v429, v211, 3);
                              v216 = -1;
                              v424 = -1;
                              v217 = 3;
                            }
                            v225 = *((_DWORD *)v9 + 18) - 1;
                            LODWORD(v432) = v217;
                            v416 = v225;
                            v226 = v225 - 1;
                            v227 = v426;
                            *((_DWORD *)v9 + 18) = v226;
                            v421 = v226;
                            if ( ((_BYTE)v227[1] & 0xF) != 0 )
                            {
                              LODWORD(v442) = sqlite3VdbeAddOp4Int(v11, 18, v216, v226, v217, IndexKey);
                              if ( v424 >= 0 )
                              {
                                sqlite3VdbeChangeP5(v11, 13);
                                sqlite3VdbeAddOp3(v229, 94, v230, (_DWORD)v432, 3);
                                sqlite3ColumnDefault(v11, v192, v433, 3);
                                v428 = sqlite3VdbeAddOp3(v11, 52, 3, v421, 0);
                              }
                              else
                              {
                                sqlite3VdbeChangeP5(v11, 15);
                                v428 = v228;
                              }
                              v231 = sqlite3MPrintf(v5, "NULL value in %s.%s", *v192, *v426);
                              sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v231, -6);
                              v232 = v439;
                              if ( v439 )
                              {
                                sqlite3VdbeAddOp3(v11, 9, 0, v416, 0);
                                v233 = sqlite3VdbeGetOp(v11, (unsigned int)v442);
                                v234 = v428;
                                *(_DWORD *)(v233 + 8) = *(_DWORD *)(v11 + 144);
                                *(_DWORD *)(sqlite3VdbeGetOp(v11, v234) + 8) = *(_DWORD *)(v11 + 144);
                                v227 = v426;
                                v226 = v421;
                                goto LABEL_344;
                              }
                              v227 = v426;
                              v226 = v421;
                            }
                            else
                            {
LABEL_344:
                              v232 = v439;
                            }
                            if ( v417 )
                            {
                              if ( v232 )
                              {
                                sqlite3VdbeAddOp4Int(v11, 18, v424, v226, (_DWORD)v432, IndexKey);
                                sqlite3VdbeChangeP5(
                                  v11,
                                  *((unsigned __int8 *)&qword_1800A7838[1] + ((*((_DWORD *)v426 + 2) >> 4) & 0xFu) + 7));
                                v237 = sqlite3MPrintf(
                                         v5,
                                         "non-%s value in %s.%s",
                                         *(const char **)(v236
                                                        + 8LL
                                                        * ((unsigned int)((unsigned __int8)*(_DWORD *)(v235 + 8) >> 4)
                                                         - 1)
                                                        + 742720),
                                         *v192,
                                         *(const char **)&v192[1][24 * v433]);
                                goto LABEL_355;
                              }
LABEL_356:
                              sqlite3VdbeResolveLabel(v11, v416);
                              integrityCheckResultRow(v11);
                              sqlite3VdbeResolveLabel(v11, v421);
                              LODWORD(v211) = v433;
                              goto LABEL_357;
                            }
                            v238 = *((_BYTE *)v227 + 12);
                            if ( v238 == 66 )
                            {
                              sqlite3VdbeAddOp4Int(v11, 18, v424, v226, (_DWORD)v432, IndexKey);
                              sqlite3VdbeChangeP5(v11, 28);
                              v237 = sqlite3MPrintf(v5, "NUMERIC value in %s.%s", *v192, *(_QWORD *)&v192[1][24 * v433]);
                            }
                            else
                            {
                              if ( v238 < 67 )
                                goto LABEL_356;
                              sqlite3VdbeAddOp4Int(v11, 18, v424, v226, (_DWORD)v432, IndexKey);
                              sqlite3VdbeChangeP5(v11, 27);
                              if ( v424 >= 0 )
                                sqlite3ExprCodeGetColumnOfTable(v239, (_DWORD)v192, v429, v433, 3);
                              sqlite3VdbeAddOp4(v11, 96, 3, 1, 0, (__int64)"C", -1);
                              sqlite3VdbeAddOp4Int(v11, 18, -1, v421, 3, IndexKey);
                              sqlite3VdbeChangeP5(v11, 28);
                              v237 = sqlite3MPrintf(v5, "TEXT value in %s.%s", *v192, *(_QWORD *)&v192[1][24 * v433]);
                            }
LABEL_355:
                            sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v237, -6);
                            goto LABEL_356;
                          }
LABEL_357:
                          v212 = v417;
LABEL_358:
                          v211 = (unsigned int)(v211 + 1);
                          v213 = (int)v211 < *((__int16 *)v192 + 27);
                        }
                        v240 = v192[4];
                        if ( v240 && (*(_DWORD *)(v5 + 48) & 0x200LL) == 0 )
                        {
                          v241 = (const char **)sqlite3ExprListDup(v5, v240, 0);
                          v426 = v241;
                          v242 = v241;
                          if ( !*(_BYTE *)(v5 + 103) )
                          {
                            v416 = *((_DWORD *)v9 + 18) - 1;
                            v428 = v416 - 1;
                            *((_DWORD *)v9 + 18) = v416 - 1;
                            *((_DWORD *)v9 + 17) = v429 + 1;
                            v243 = *(_DWORD *)v241 - 1;
                            if ( *(_DWORD *)v242 - 1 > 0 )
                            {
                              v244 = v416;
                              v245 = v243;
                              v246 = v242;
                              do
                                sqlite3ExprIfFalse(v9, v246[4 * (unsigned int)v245-- + 1], v244, 0);
                              while ( v245 > 0 );
                              v11 = v427;
                              v5 = v434;
                              v192 = v431;
                              v242 = v426;
                            }
                            sqlite3ExprIfTrue(v9, v242[1], v428, 16);
                            sqlite3VdbeResolveLabel(v11, v416);
                            *((_DWORD *)v9 + 17) = 0;
                            v247 = sqlite3MPrintf(v5, "CHECK constraint failed in %s", *v192);
                            sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, v247, -6);
                            integrityCheckResultRow(v11);
                            sqlite3VdbeResolveLabel(v11, v428);
                            v242 = v426;
                          }
                          sqlite3ExprListDeleteGeneric(v5, v242);
                        }
                        if ( v423 != 113 )
                        {
                          v248 = (char *)v192[2];
                          v249 = 0;
                          v424 = 0;
                          v250 = 0;
                          v432 = v248;
                          v251 = -1;
                          if ( v248 )
                          {
                            v252 = v431;
                            do
                            {
                              v253 = *((_DWORD *)v9 + 18) - 1;
                              v416 = 0;
                              LODWORD(v442) = v253;
                              *((_DWORD *)v9 + 18) = v253;
                              if ( (char *)v440 != v248 )
                              {
                                IndexKey = sqlite3GenerateIndexKey(
                                             (_DWORD)v9,
                                             (_DWORD)v248,
                                             v429,
                                             0,
                                             0,
                                             (__int64)&v416,
                                             v250,
                                             v251);
                                v426 = (const char **)v248;
                                sqlite3VdbeAddOp3(v11, 86, v424 + 8, 1, 0);
                                v410 = *((unsigned __int16 *)v248 + 48);
                                v428 = v437 + v424;
                                v254 = sqlite3VdbeAddOp4Int(v11, 29, v437 + v424, v442, IndexKey, v410);
                                sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"row ", 0);
                                sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" missing from index ", 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 3, 3);
                                v417 = sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, *(_QWORD *)v432, 0);
                                sqlite3VdbeAddOp3(v11, 112, 4, 3, 3);
                                v439 = integrityCheckResultRow(v11);
                                *(_DWORD *)(sqlite3VdbeGetOp(v11, v254) + 8) = *(_DWORD *)(v11 + 144);
                                if ( *((char *)v252 + 48) >= 0 )
                                {
                                  sqlite3VdbeAddOp3(v11, 142, v428, 3, 0);
                                  v255 = sqlite3VdbeAddOp3(
                                           v11,
                                           54,
                                           3,
                                           0,
                                           *((unsigned __int16 *)v432 + 48) + IndexKey - 1);
                                  sqlite3VdbeAddOp4(
                                    v11,
                                    118,
                                    0,
                                    3,
                                    0,
                                    (__int64)"rowid not at end-of-record for row ",
                                    0);
                                  sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                  sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" of index ", 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v417 - 1, 0);
                                  *(_DWORD *)(sqlite3VdbeGetOp(v11, v255) + 8) = *(_DWORD *)(v11 + 144);
                                }
                                v248 = v432;
                                v256 = 0;
                                v421 = 0;
                                if ( *((_WORD *)v432 + 47) )
                                {
                                  v257 = 0;
                                  do
                                  {
                                    if ( *(char **)(*((_QWORD *)v248 + 8) + 8LL * v257) != "BINARY" )
                                    {
                                      if ( !v256 )
                                      {
                                        v421 = *((_DWORD *)v9 + 18) - 1;
                                        *((_DWORD *)v9 + 18) = v421;
                                      }
                                      sqlite3VdbeAddOp3(v11, 94, v424 + v437, v257, 3);
                                      sqlite3VdbeAddOp3(v11, 53, 3, v421, v257 + IndexKey);
                                      v256 = v421;
                                    }
                                    ++v257;
                                  }
                                  while ( v257 < *((unsigned __int16 *)v248 + 47) );
                                  v252 = v431;
                                  if ( v256 )
                                  {
                                    v258 = sqlite3VdbeAddOp3(v11, 9, 0, 0, 0);
                                    sqlite3VdbeResolveLabel(v11, v421);
                                    sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"row ", 0);
                                    sqlite3VdbeAddOp3(v11, 112, 7, 3, 3);
                                    sqlite3VdbeAddOp4(v11, 118, 0, 4, 0, (__int64)" values differ from index ", 0);
                                    sqlite3VdbeAddOp3(v11, 9, 0, v417 - 1, 0);
                                    v259 = sqlite3VdbeGetOp(v11, v258);
                                    v248 = v432;
                                    *(_DWORD *)(v259 + 8) = *(_DWORD *)(v11 + 144);
                                  }
                                }
                                if ( v248[98] )
                                {
                                  v260 = *((_DWORD *)v9 + 18) - 1;
                                  *((_DWORD *)v9 + 18) = v260;
                                  v421 = v260;
                                  if ( *((_WORD *)v248 + 47) )
                                  {
                                    v261 = 0;
                                    do
                                    {
                                      v262 = *((_QWORD *)v248 + 1);
                                      if ( *(__int16 *)(v262 + 2LL * v261) < 0
                                        || (v252[1][24 * *(__int16 *)(v262 + 2LL * v261) + 8] & 0xF) == 0 )
                                      {
                                        sqlite3VdbeAddOp3(v11, 51, v261 + IndexKey, v260, 0);
                                        v260 = v421;
                                      }
                                      ++v261;
                                    }
                                    while ( v261 < *((unsigned __int16 *)v248 + 47) );
                                    v9 = v445;
                                  }
                                  v263 = sqlite3VdbeAddOp3(v11, 39, v424 + v437, 0, 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v421, 0);
                                  v264 = sqlite3VdbeGetOp(v11, v263);
                                  v248 = v432;
                                  v265 = v424 + v437;
                                  v266 = v421;
                                  *(_DWORD *)(v264 + 8) = *(_DWORD *)(v11 + 144);
                                  sqlite3VdbeAddOp4Int(v11, 41, v265, v266, IndexKey, *((unsigned __int16 *)v248 + 47));
                                  sqlite3VdbeAddOp4(v11, 118, 0, 3, 0, (__int64)"non-unique entry in index ", 0);
                                  sqlite3VdbeAddOp3(v11, 9, 0, v417, 0);
                                  sqlite3VdbeResolveLabel(v11, v421);
                                }
                                v267 = sqlite3VdbeGetOp(v11, v439);
                                v268 = v416;
                                *(_DWORD *)(v267 + 8) = *(_DWORD *)(v11 + 144);
                                sqlite3ResolvePartIdxLabel(v9, v268);
                                v249 = v424;
                                v251 = IndexKey;
                                v250 = (__int64)v426;
                              }
                              v248 = (char *)*((_QWORD *)v248 + 5);
                              ++v249;
                              v432 = v248;
                              v424 = v249;
                            }
                            while ( v248 );
                            v5 = v434;
                          }
                        }
                        v269 = v443;
                        sqlite3VdbeAddOp3(v11, 39, v429, v443, 0);
                        v270 = sqlite3VdbeGetOp(v11, (unsigned int)(v269 - 1));
                        v177 = 0;
                        *(_DWORD *)(v270 + 8) = *(_DWORD *)(v11 + 144);
                        if ( v440 )
                          sqlite3ReleaseTempRange(v9, v418, *(unsigned __int16 *)(v440 + 94));
                        v191 = (const char **)v425;
LABEL_399:
                        v190 = *(_QWORD *)v420;
                        v420 = v190;
                        if ( !v190 )
                        {
                          v189 = v435;
                          break;
                        }
                      }
                    }
                    v271 = *(_QWORD *)(v189 + 16);
                    v420 = v271;
                    if ( v271 )
                    {
                      v272 = v425;
                      do
                      {
                        v273 = *(_QWORD *)(v271 + 16);
                        if ( (!v272 || v272 == v273) && *(_BYTE *)(v273 + 63) == 1 )
                        {
                          if ( *(__int16 *)(v273 + 54) > (__int16)v177
                            || (ElementWithHash = findElementWithHash(v5 + 552, **(_QWORD **)(v273 + 72), 0),
                                LOWORD(v177) = 0,
                                *(_QWORD *)(ElementWithHash + 16)) )
                          {
                            sqlite3ViewGetColumnNames(v9, v273);
                            v275 = *(_QWORD *)(v273 + 80);
                            LOWORD(v177) = 0;
                            if ( v275 )
                            {
                              v276 = *(__int64 **)(v275 + 16);
                              if ( v276 )
                              {
                                v277 = *v276;
                                if ( v277 )
                                {
                                  if ( *(int *)v277 >= 4 && *(_QWORD *)(v277 + 192) )
                                  {
                                    sqlite3VdbeAddOp3(v11, 174, v436, 3, v438);
                                    ++*(_DWORD *)(v273 + 44);
                                    sqlite3VdbeAppendP4(v11, v273, 4294967280LL);
                                    v278 = sqlite3VdbeAddOp3(v11, 51, 3, 0, 0);
                                    integrityCheckResultRow(v11);
                                    v279 = sqlite3VdbeGetOp(v11, v278);
                                    LOWORD(v177) = 0;
                                    *(_DWORD *)(v279 + 8) = *(_DWORD *)(v11 + 144);
                                  }
                                }
                              }
                            }
                          }
                          v272 = v425;
                        }
                        v271 = *(_QWORD *)v420;
                        v420 = v271;
                      }
                      while ( v271 );
                    }
                    v155 = v430;
                  }
                }
                v158 = v436;
              }
              v436 = ++v158;
              if ( (signed int)v158 >= *(_DWORD *)(v5 + 40) )
                goto LABEL_419;
            }
          }
          if ( (unsigned __int8)v26 <= 0x22u )
          {
            if ( (_BYTE)v26 == 34 )
            {
              sqlite3_db_release_memory(v5);
              goto LABEL_698;
            }
            if ( (unsigned __int8)v26 <= 0x1Du )
            {
              if ( (_BYTE)v26 == 29 )
              {
                *((_DWORD *)v9 + 15) = 1;
                for ( mm = *(_QWORD **)(v5 + 560); mm; mm = (_QWORD *)*mm )
                  sqlite3VdbeMultiLoad(v11, 1, "s", *(_QWORD *)(mm[2] + 8LL), v403, v407, v411, v413, v414, v415);
                goto LABEL_698;
              }
              v285 = v26 - 23;
              if ( v285 )
              {
                v286 = v285 - 1;
                if ( !v286 )
                {
                  v307 = *(__int64 **)(*(_QWORD *)(v438 + v13 + 8) + 8LL);
                  v308 = -2;
                  v420 = -2;
                  v309 = *v307;
                  if ( v15 )
                  {
                    sqlite3DecOrHexToI64(v15);
                    v308 = -1;
                  }
                  if ( v308 >= -1 )
                  {
                    v310 = *(_QWORD *)(v309 + 296);
                    *(_QWORD *)(v309 + 208) = v308;
                    if ( v310 )
                      *(_QWORD *)(v310 + 32) = v308;
                  }
                  v31 = *(_QWORD *)(v309 + 208);
                  goto LABEL_697;
                }
                v287 = v286 - 2;
                if ( v287 )
                {
                  v288 = v287 - 1;
                  if ( v288 )
                  {
                    if ( v288 != 1 )
                      goto LABEL_593;
                    v434 = 0;
                    if ( !v15 )
                      goto LABEL_449;
                    sqlite3DecOrHexToI64(v15);
                    v427 = v434;
                    v289 = v443;
                    if ( *(_DWORD *)(v443 + 8) )
                    {
                      v294 = *(_DWORD *)(v5 + 40) - 1;
                      v416 = v294;
                      if ( v294 >= 0 )
                      {
                        v295 = v427;
                        do
                        {
                          v296 = *(_QWORD *)(32LL * (unsigned int)v294 + *(_QWORD *)(v5 + 32) + 8);
                          v420 = v296;
                          if ( v296 && v294 == (_DWORD)v12 )
                          {
                            v297 = *(_QWORD *)(v296 + 8);
                            sqlite3BtreeEnter(v296);
                            *(_QWORD *)(*(_QWORD *)v297 + 160LL) = v295;
                            pagerFixMaplimit();
                            sqlite3BtreeLeave(v420);
                            v294 = v416;
                            v295 = v434;
                          }
                          v416 = --v294;
                        }
                        while ( v294 >= 0 );
                        goto LABEL_448;
                      }
                    }
                    else
                    {
                      *(_QWORD *)(v5 + 64) = v434;
                      v290 = *(_DWORD *)(v5 + 40) - 1;
                      v416 = v290;
                      if ( v290 >= 0 )
                      {
                        v291 = v427;
                        do
                        {
                          v292 = *(_QWORD *)(32LL * (unsigned int)v290 + *(_QWORD *)(v5 + 32) + 8);
                          v420 = v292;
                          if ( v292 && (v290 == (_DWORD)v12 || !*(_DWORD *)(v289 + 8)) )
                          {
                            v293 = *(_QWORD *)(v292 + 8);
                            sqlite3BtreeEnter(v292);
                            *(_QWORD *)(*(_QWORD *)v293 + 160LL) = v291;
                            pagerFixMaplimit();
                            sqlite3BtreeLeave(v420);
                            v289 = v443;
                            v290 = v416;
                            v291 = v434;
                          }
                          v416 = --v290;
                        }
                        while ( v290 >= 0 );
LABEL_448:
                        v15 = v441;
                      }
                    }
LABEL_449:
                    v434 = -1;
                    v17 = sqlite3_file_control(v5, v425, 18, &v434);
                    if ( v17 )
                    {
                      if ( v17 == 12 )
                        goto LABEL_698;
LABEL_23:
                      ++*((_DWORD *)v9 + 13);
                      *((_DWORD *)v9 + 6) = v17;
                      goto LABEL_698;
                    }
                    v31 = v434;
                    goto LABEL_697;
                  }
                  v420 = 0;
                  sqlite3CodeVerifySchema(v9, (unsigned int)v12);
                  v298 = v444;
                  v299 = *((_DWORD *)v9 + 15) + 1;
                  *((_DWORD *)v9 + 15) = v299;
                  if ( *((_BYTE *)qword_18009E760 + *v298) == 112 )
                  {
                    sqlite3VdbeAddOp3(v11, 178, v12, v299, 0);
                  }
                  else
                  {
                    if ( !v15 || (unsigned int)sqlite3DecOrHexToI64(v15) || (v300 = v420, v420 < 0) )
                    {
                      v300 = 0;
                    }
                    else if ( v420 > 4294967294LL )
                    {
                      v300 = -2;
                    }
                    sqlite3VdbeAddOp3(v11, 179, v12, v299, v300);
                  }
                  v301 = 1;
                  v406 = 0;
                  v302 = v299;
LABEL_463:
                  sqlite3VdbeAddOp3(v11, 84, v302, v301, v406);
                  goto LABEL_698;
                }
                LockingMode = (unsigned int)getLockingMode(v15);
                if ( !*(_DWORD *)(v443 + 8) )
                {
                  if ( (_DWORD)LockingMode == -1 )
                  {
                    v304 = *(unsigned __int8 *)(v5 + 105);
                    goto LABEL_471;
                  }
                  for ( nn = 2; nn < *(_DWORD *)(v5 + 40); nn = v306 + 1 )
                    sqlite3PagerLockingMode(
                      **(_QWORD **)(*(_QWORD *)(32LL * nn + *(_QWORD *)(v5 + 32) + 8) + 8LL),
                      LockingMode);
                  *(_BYTE *)(v5 + 105) = LockingMode;
                }
                v304 = sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v438 + v13 + 8) + 8LL), LockingMode);
LABEL_471:
                v145 = "exclusive";
                if ( v304 != 1 )
                  v145 = "normal";
                goto LABEL_473;
              }
              v311 = 0;
              if ( !v15 )
                goto LABEL_485;
              sqlite3Strlen30(v15, 0, v24);
              v312 = 0;
              for ( i1 = v313; ; v312 = i1 )
              {
                v316 = sqlite3JournalModename(v312);
                if ( !v316 )
                  goto LABEL_485;
                v315 = sqlite3_strnicmp(v15, v316);
                v311 = 0;
                if ( !v315 )
                  break;
                ++i1;
              }
              if ( i1 == 2 )
              {
                if ( (*(_DWORD *)(v5 + 48) & 0x10000000) != 0 )
                {
LABEL_485:
                  i1 = -1;
                  goto LABEL_486;
                }
              }
              else if ( i1 == -1 )
              {
LABEL_486:
                if ( *(_DWORD *)(v443 + 8) == (_DWORD)v311 )
                {
                  LODWORD(v12) = v311;
                  *(_DWORD *)(v443 + 8) = 1;
                }
              }
              v317 = *(_DWORD *)(v5 + 40) - 1;
              if ( v317 >= 0 )
              {
                v318 = v443;
                do
                {
                  if ( *(_QWORD *)(32LL * (unsigned int)v317 + *(_QWORD *)(v5 + 32) + 8) != v311
                    && (v317 == (_DWORD)v12 || *(_DWORD *)(v318 + 8) == (_DWORD)v311) )
                  {
                    sqlite3VdbeUsesBtree(v11, (unsigned int)v317);
                    sqlite3VdbeAddOp3(v319, 4, v317, 1, i1);
                    v311 = 0;
                  }
                  --v317;
                }
                while ( v317 >= 0 );
                v15 = v441;
              }
              v406 = v311;
              v301 = 1;
LABEL_497:
              v302 = 1;
              goto LABEL_463;
            }
            v321 = v26 - 30;
            if ( v321 )
            {
              v322 = v321 - 1;
              if ( v322 )
              {
                v323 = v322 - 1;
                if ( v323 )
                {
                  if ( v323 != 1 )
                    goto LABEL_593;
                  v324 = 0;
                  v325 = *(_QWORD *)(v438 + v13 + 8);
                  v326 = -1;
                  if ( v15 )
                  {
                    if ( (unsigned int)sqlite3_stricmp(v15, "fast") )
                      v326 = (unsigned __int8)sqlite3GetBoolean(v15, 0);
                    else
                      v326 = 2;
                  }
                  if ( !*(_DWORD *)(v443 + 8) && v326 >= 0 && *(int *)(v5 + 40) > 0 )
                  {
                    do
                      sqlite3BtreeSecureDelete(
                        *(_QWORD *)(32LL * v324++ + *(_QWORD *)(v5 + 32) + 8),
                        (unsigned int)v326);
                    while ( v324 < *(_DWORD *)(v5 + 40) );
                  }
                  v37 = sqlite3BtreeSecureDelete(v325, (unsigned int)v326);
                  goto LABEL_62;
                }
                for ( i2 = 0; i2 != 67; ++i2 )
                  sqlite3VdbeMultiLoad(v11, 1, "s", (&off_18009C420)[3 * i2], v403, v407, v411, v413, v414, v415);
                goto LABEL_683;
              }
              v328 = *(_QWORD *)(v438 + v13 + 8);
              if ( v15 )
              {
                v416 = 0;
                sqlite3GetInt32(v15, &v416);
                v330 = v416;
                *(_DWORD *)(v5 + 116) = v416;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v328, v330, 0, 0) == 7 )
                  sqlite3OomFault(v5);
                goto LABEL_698;
              }
              if ( v328 )
                v329 = *(_DWORD *)(*(_QWORD *)(v328 + 8) + 52LL);
              else
                v329 = 0;
              v31 = v329;
LABEL_697:
              returnSingleInt(v11, v31);
              goto LABEL_698;
            }
            if ( v15 )
            {
              v416 = 0;
              sqlite3GetInt32(v15, &v416);
              IndexKey = v416;
              if ( (v416 & 2) == 0 )
                goto LABEL_698;
              v417 = 0;
              v331 = 0;
              LODWORD(v432) = 0;
              if ( (v416 & 0x10) == 0 )
              {
                v418 = 0;
                goto LABEL_536;
              }
            }
            else
            {
              v417 = 0;
              v331 = 0;
              IndexKey = 65534;
              LODWORD(v432) = 0;
            }
            v418 = (unsigned int)(*(_DWORD *)(v5 + 744) - 1) > 0x7CE ? 0x7D0 : 0;
LABEL_536:
            v422 = *((_DWORD *)v9 + 14);
            *((_DWORD *)v9 + 14) = v422 + 1;
            if ( v425 )
            {
              v332 = v12;
              v430 = v12;
            }
            else
            {
              v332 = *(_DWORD *)(v5 + 40) - 1;
              v430 = v332;
              if ( (int)v12 > v332 )
                goto LABEL_575;
            }
            do
            {
              if ( (_DWORD)v12 != 1 )
              {
                sqlite3CodeVerifySchema(v9, (unsigned int)v12);
                for ( i3 = *(const char ***)(*(_QWORD *)(32LL * (int)v12 + *(_QWORD *)(v5 + 32) + 24) + 16LL);
                      ;
                      i3 = (const char **)*i3 )
                {
                  v431 = i3;
                  if ( !i3 )
                    break;
                  v334 = (__int64)i3[2];
                  v420 = v334;
                  if ( !*(_BYTE *)(v334 + 63) )
                  {
                    v335 = *(_BYTE **)v334;
                    if ( !*(_QWORD *)v334 )
                      goto LABEL_551;
                    v336 = 7;
                    v337 = "sqlite_";
                    do
                    {
                      --v336;
                      if ( !*v335
                        || *((_BYTE *)qword_18009E760 + (unsigned __int8)*v335) != *((_BYTE *)qword_18009E760
                                                                                   + *(unsigned __int8 *)v337) )
                      {
                        goto LABEL_549;
                      }
                      ++v335;
                      ++v337;
                    }
                    while ( v336 > 0 );
                    --v336;
LABEL_549:
                    if ( v336 >= 0
                      && *((unsigned __int8 *)qword_18009E760 + (unsigned __int8)*v335) != *((unsigned __int8 *)qword_18009E760
                                                                                           + *(unsigned __int8 *)v337) )
                    {
LABEL_551:
                      v338 = *(_QWORD *)(v334 + 16);
                      v339 = 0;
                      v340 = *(unsigned __int16 *)(v334 + 58);
                      v428 = v340;
                      v416 = 0;
                      if ( v338 )
                      {
                        do
                        {
                          ++v339;
                          if ( *(char *)(v338 + 100) >= 0 )
                            v340 = -1;
                          v338 = *(_QWORD *)(v338 + 40);
                        }
                        while ( v338 );
                        v416 = v339;
                        v428 = v340;
                      }
                      if ( (*(_DWORD *)(v334 + 48) & 0x100) != 0
                        || (IndexKey & 0x10000) != 0
                        || *(_QWORD *)(v334 + 16) && (v340 & 0x8000u) != 0 )
                      {
                        if ( ++v417 == 2 )
                        {
                          sqlite3BeginWriteOperation(v9, 0, (unsigned int)v12);
                          LODWORD(v334) = v420;
                          v339 = v416;
                        }
                        LODWORD(v432) = v339 + (_DWORD)v432 + 1;
                        sqlite3OpenTable((_DWORD)v9, v422, v12, v334, 102);
                        if ( (v428 & 0x8000u) != 0 )
                        {
                          v416 = IndexKey & 1;
                          sqlite3VdbeAddOp3(v11, 36, v422, *(_DWORD *)(v11 + 144) + v416 + 2, 0);
                        }
                        else
                        {
                          if ( (__int16)v428 < 33 )
                            v341 = -1;
                          else
                            v341 = (__int16)v428 - 33;
                          v416 = IndexKey & 1;
                          sqlite3VdbeAddOp4Int(
                            v11,
                            33,
                            v422,
                            *(_DWORD *)(v11 + 144) + v416 + 2,
                            v341,
                            (__int16)v428 + 33);
                        }
                        v342 = sqlite3MPrintf(
                                 v5,
                                 "ANALYZE \"%w\".\"%w\"",
                                 *(_QWORD *)(32LL * (int)v12 + *(_QWORD *)(v5 + 32)),
                                 *(_QWORD *)v420);
                        if ( v416 )
                        {
                          TempReg = sqlite3GetTempReg(v9);
                          sqlite3VdbeAddOp4(v11, 118, 0, TempReg, v345, v344, -6);
                          sqlite3VdbeAddOp3(v11, 84, TempReg, 1, 0);
                        }
                        else
                        {
                          sqlite3VdbeAddOp4(v11, 148, v418 != 0 ? 2 : 0, v418, 0, v342, -6);
                        }
                      }
                    }
                    i3 = v431;
                  }
                }
                v332 = v430;
              }
              LODWORD(v12) = v12 + 1;
            }
            while ( (int)v12 <= v332 );
            v15 = v441;
            v331 = (int)v432;
LABEL_575:
            sqlite3VdbeAddOp3(v11, 166, 0, 0, 0);
            if ( !*(_BYTE *)(v5 + 103) )
            {
              if ( v418 )
              {
                if ( v331 > 100 )
                {
                  v346 = sqlite3VdbeGetOp(v11, 0);
                  v349 = *(_DWORD *)(v11 + 144);
                  if ( v349 > 0 )
                  {
                    do
                    {
                      if ( *(_BYTE *)(v346 + 24 * v347) == 0x94 )
                        *(_DWORD *)(v346 + 24 * v347 + 8) = v348;
                      v347 = (unsigned int)(v347 + 1);
                    }
                    while ( (int)v347 < v349 );
                  }
                }
              }
            }
            goto LABEL_698;
          }
          v350 = v26 - 35;
          if ( !v350 )
          {
            v420 = 0;
            if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
              sqlite3_soft_heap_limit64(v420);
            v98 = sqlite3_soft_heap_limit64(-1);
            goto LABEL_696;
          }
          v351 = v350 - 1;
          if ( v351 )
          {
            v352 = v351 - 1;
            if ( !v352 )
            {
              if ( !v15 )
                goto LABEL_698;
              sqlite3CodeVerifyNamedSchema(v9, v425);
              v382 = sqlite3LocateTable(v9, 2, v15, v425);
              v420 = v382;
              v383 = v382;
              if ( !v382 )
                goto LABEL_698;
              v427 = sqlite3PrimaryKeyIndex(v382);
              *((_DWORD *)v9 + 15) = 7;
              sqlite3ViewGetColumnNames(v9, v383);
              LOWORD(v384) = *(_WORD *)(v383 + 54);
              if ( (__int16)v384 <= 0 )
                goto LABEL_698;
              v385 = *(_QWORD *)(v383 + 8);
              v386 = 0;
              v387 = 0;
              v388 = v420;
              v417 = 0;
              v416 = 0;
              do
              {
                v389 = *(_WORD *)(v385 + 18);
                if ( (v389 & 0x62) == 0 || v426[2] )
                {
                  if ( (v389 & 1) != 0 )
                  {
                    v390 = 1;
                    if ( v427 && (__int16)v384 >= 1 )
                    {
                      do
                      {
                        if ( *(__int16 *)(*(_QWORD *)(v427 + 8) + 2LL * v390 - 2) == v387 )
                          break;
                        ++v390;
                      }
                      while ( v390 <= (__int16)v384 );
                    }
                  }
                  else
                  {
                    v390 = 0;
                  }
                  v391 = sqlite3ColumnExpr(v388);
                  if ( v393 < 2 && v391 )
                    v420 = *(_QWORD *)(v391 + 8);
                  else
                    v420 = v392;
                  v394 = sqlite3ColumnType(v385, qword_18009EEF0);
                  v398 = (unsigned int)(v397 - v417);
                  v399 = "issisii";
                  if ( !v426[2] )
                    v399 = "issisi";
                  sqlite3VdbeMultiLoad(v11, 1, v399, v398, *(_QWORD *)v385, v394, v395, v420, v390, v396);
                  v387 = v416;
                  v386 = v417;
                }
                else
                {
                  v417 = ++v386;
                }
                v384 = *(__int16 *)(v388 + 54);
                ++v387;
                v385 += 24;
                v416 = v387;
              }
              while ( v387 < v384 );
LABEL_682:
              v5 = v434;
              goto LABEL_683;
            }
            v353 = v352 - 1;
            if ( v353 )
            {
              v354 = v353 - 1;
              if ( !v354 )
              {
                if ( v15 )
                {
                  changeTempStorage(v9, v15);
                  goto LABEL_698;
                }
                v31 = *(unsigned __int8 *)(v5 + 102);
                goto LABEL_697;
              }
              v355 = v354 - 1;
              if ( !v355 )
              {
                v362 = sqlite3MutexAlloc(11);
                sqlite3_mutex_enter(v362);
                if ( !v15 )
                {
                  v60 = sqlite3_temp_directory;
                  goto LABEL_617;
                }
                if ( !*v15
                  || (v363 = *(_QWORD *)v5,
                      v416 = 0,
                      !(*(unsigned int (__fastcall **)(__int64, char *, __int64, unsigned int *))(v363 + 56))(
                         v363,
                         v15,
                         1,
                         &v416))
                  && v416 )
                {
                  if ( *(_BYTE *)(v5 + 102) <= 1u )
                    invalidateTempStorage(v9);
                  sqlite3_free(sqlite3_temp_directory);
                  if ( *v15 )
                    sqlite3_temp_directory = sqlite3_mprintf("%s", v15);
                  else
                    sqlite3_temp_directory = 0;
                  goto LABEL_622;
                }
LABEL_621:
                sqlite3ErrorMsg(v9, "not a writable directory");
                goto LABEL_622;
              }
              v356 = v355 - 1;
              if ( !v356 )
              {
                v420 = 0;
                if ( v15 && !(unsigned int)sqlite3DecOrHexToI64(v15) )
                  sqlite3_limit(v5, 11, v420 & 0x7FFFFFFF);
                v37 = sqlite3_limit(v5, 11, 0xFFFFFFFFLL);
                goto LABEL_62;
              }
              v357 = v356 - 1;
              if ( !v357 )
              {
                if ( v15 )
                {
                  v416 = 0;
                  sqlite3GetInt32(v15, &v416);
                  sqlite3_wal_autocheckpoint(v5, v416);
                }
                if ( *(__int64 (__fastcall **)())(v5 + 360) == sqlite3WalDefaultHook )
                  v37 = *(_DWORD *)(v5 + 368);
                else
                  v37 = 0;
                goto LABEL_62;
              }
              if ( v357 != 1 )
                goto LABEL_593;
              v358 = 12;
              if ( *(_QWORD *)v443 )
                v358 = v12;
              v359 = 0;
              LODWORD(v438) = v358;
              if ( v15 )
              {
                if ( (unsigned int)sqlite3StrICmp(v15, "full") )
                {
                  if ( (unsigned int)sqlite3StrICmp(v15, "restart") )
                  {
                    if ( !(unsigned int)sqlite3StrICmp(v15, "truncate") )
                      v359 = 3;
                  }
                  else
                  {
                    v359 = v360;
                  }
                }
                else
                {
                  v359 = 1;
                }
              }
              v361 = v438;
              *((_DWORD *)v9 + 15) = 3;
              sqlite3VdbeAddOp3(v11, 3, v361, v359, 1);
              v301 = 3;
              v406 = 0;
              goto LABEL_497;
            }
            v365 = v425;
            v366 = v425;
            *((_DWORD *)v9 + 15) = 6;
            sqlite3CodeVerifyNamedSchema(v9, v366);
            v367 = 0;
            v422 = 0;
            if ( *(int *)(v5 + 40) <= 0 )
              goto LABEL_698;
            while ( 1 )
            {
              v368 = v367;
              if ( v365 && (unsigned int)sqlite3_stricmp(v365, *(_QWORD *)(32LL * v367 + *(_QWORD *)(v5 + 32))) )
                goto LABEL_659;
              v369 = *(_QWORD *)(32 * v368 + *(_QWORD *)(v5 + 32) + 24);
              v370 = *(_DWORD *)(v369 + 12);
              v371 = v369 + 8;
              if ( v370 )
              {
                v372 = v422;
                do
                {
                  for ( i4 = *(_QWORD **)(v371 + 8); ; i4 = (_QWORD *)*i4 )
                  {
                    if ( !i4 )
                      goto LABEL_645;
                    v374 = i4[2];
                    if ( !*(_WORD *)(v374 + 54) )
                      break;
                  }
                  --v370;
                  v375 = sqlite3MPrintf(v5, "SELECT*FROM\"%w\"", *(_QWORD *)v374);
                  v427 = v375;
                  if ( v375 )
                  {
                    v420 = 0;
                    sqlite3LockAndPrepare(v5, v375, -1, 0, 0, (__int64)&v420, 0);
                    sqlite3_finalize(v420);
                    sqlite3DbFree(v5, v427);
                  }
                  if ( *(_BYTE *)(v5 + 103) )
                  {
                    sqlite3ErrorMsg(*(_QWORD *)(v5 + 352), "out of memory");
                    *(_DWORD *)(*(_QWORD *)(v5 + 352) + 24LL) = 7;
                  }
                  v371 = *(_QWORD *)(32 * v372 + *(_QWORD *)(v5 + 32) + 24) + 8LL;
                }
                while ( v370 );
LABEL_645:
                v15 = v441;
              }
              v376 = *(_QWORD *)(v371 + 8);
              v420 = v376;
              if ( v376 )
                break;
LABEL_659:
              v367 = v422 + 1;
              v422 = v367;
              if ( v367 >= *(_DWORD *)(v5 + 40) )
                goto LABEL_698;
            }
            while ( 1 )
            {
              v377 = *(_QWORD **)(v376 + 16);
              v427 = (__int64)v377;
              if ( !v15 )
                goto LABEL_650;
              if ( !(unsigned int)sqlite3_stricmp(v15, *v377) )
                break;
LABEL_657:
              v376 = *(_QWORD *)v420;
              v420 = v376;
              if ( !v376 )
              {
                v365 = v425;
                goto LABEL_659;
              }
            }
            v377 = (_QWORD *)v427;
LABEL_650:
            if ( *((_BYTE *)v377 + 63) == 2 )
            {
              v378 = "view";
            }
            else if ( *((_BYTE *)v377 + 63) == 1 )
            {
              v378 = "virtual";
            }
            else
            {
              v378 = "shadow";
              if ( (v377[6] & 0x1000) == 0 )
                v378 = "table";
            }
            v379 = *((_DWORD *)v377 + 12);
            v380 = *((__int16 *)v377 + 27);
            v427 = (__int64)v378;
            v381 = sqlite3PreferredTableName(*v377);
            LODWORD(v413) = (v379 >> 7) & 1;
            sqlite3VdbeMultiLoad(
              v11,
              1,
              "sssiii",
              *(_QWORD *)(32LL * v422 + *(_QWORD *)(v5 + 32)),
              v381,
              v427,
              v380,
              v413,
              HIWORD(v379) & 1,
              v415);
            goto LABEL_657;
          }
          if ( !v15 )
          {
            v31 = *(unsigned __int8 *)(v438 + v13 + 16) - 1LL;
            goto LABEL_697;
          }
          if ( !*(_BYTE *)(v5 + 101) )
          {
            sqlite3ErrorMsg(v9, "Safety level may not be changed inside a transaction");
            goto LABEL_698;
          }
          if ( (_DWORD)v12 != 1 )
          {
            LOBYTE(v24) = 1;
            SafetyLevel = getSafetyLevel(v15, 0, v24);
            v401 = v438;
            v402 = (SafetyLevel + 1) & 7;
            if ( !v402 )
              LOBYTE(v402) = 1;
            *(_BYTE *)(v438 + v13 + 16) = v402;
            *(_BYTE *)(v401 + v13 + 17) = 1;
            goto LABEL_86;
          }
LABEL_698:
          sqlite3DbFree(v5, v444);
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
0x180050420  push    rbp
0x180050422  push    rbx
0x180050423  push    rsi
0x180050424  push    rdi
0x180050425  push    r12
0x180050427  push    r13
0x180050429  push    r14
0x18005042b  push    r15
0x18005042d  lea     rbp, [rsp-68h]
0x180050432  sub     rsp, 168h
0x180050439  mov     rax, cs:__security_cookie
0x180050440  xor     rax, rsp
0x180050443  mov     [rbp+0A0h+var_48], rax
0x180050447  mov     r12, [rcx]
0x18005044a  xorps   xmm0, xmm0
0x18005044d  mov     rbx, r8
0x180050450  mov     [rbp+0A0h+var_D8], r12
0x180050454  xor     r15d, r15d
0x180050457  mov     [rbp+0A0h+var_98], rbx
0x18005045b  mov     [rbp+0A0h+var_D0], r15
0x18005045f  mov     r13, r9
0x180050462  movups  [rbp+0A0h+var_68], xmm0
0x180050466  mov     [rsp+1A0h+var_130], r9
0x18005046b  mov     rsi, rdx
0x18005046e  movups  [rbp+0A0h+var_58], xmm0
0x180050472  mov     rdi, rcx
0x180050475  mov     [rbp+0A0h+var_88], rcx
0x180050479  call    sqlite3GetVdbe
0x18005047e  mov     [rbp+0A0h+var_108], rax
0x180050482  mov     r14, rax
0x180050485  test    rax, rax
0x180050488  jz      loc_180053D24
0x18005048e  mov     dword ptr [rsp+1A0h+var_180], r15d
0x180050493  mov     edx, 0A6h
0x180050498  mov     r15d, 1
0x18005049e  mov     rcx, rax
0x1800504a1  mov     r9d, r15d
0x1800504a4  mov     r8d, r15d
0x1800504a7  call    sqlite3VdbeAddOp3
0x1800504ac  lea     r9, [rbp+0A0h+var_D0]
0x1800504b0  mov     dword ptr [rdi+3Ch], 2
0x1800504b7  mov     r8, rbx
0x1800504ba  mov     rdx, rsi
0x1800504bd  mov     rcx, rdi
0x1800504c0  call    sqlite3TwoPartName
0x1800504c5  movsxd  rsi, eax
0x1800504c8  mov     [rbp+0A0h+var_F8], esi
0x1800504cb  test    eax, eax
0x1800504cd  js      loc_180053D24
0x1800504d3  mov     rax, [r12+20h]
0x1800504d8  mov     [rbp+0A0h+var_C0], rax
0x1800504dc  cmp     esi, r15d
0x1800504df  jnz     short loc_1800504F1
0x1800504e1  mov     rcx, rdi
0x1800504e4  call    sqlite3OpenTempDatabase
0x1800504e9  test    eax, eax
0x1800504eb  jnz     loc_180053D24
0x1800504f1  mov     rdx, [rbp+0A0h+var_D0]
0x1800504f5  mov     rcx, r12
0x1800504f8  call    sqlite3NameFromToken
0x1800504fd  mov     [rbp+0A0h+var_90], rax
0x180050501  test    rax, rax
0x180050504  jz      loc_180053D24
0x18005050a  mov     rbx, rsi
0x18005050d  mov     rcx, r12
0x180050510  shl     rbx, 5
0x180050514  cmp     [rbp+0A0h+arg_20], 0
0x18005051b  mov     [rbp+0A0h+var_B0], rbx
0x18005051f  jz      short loc_180050532
0x180050521  mov     r8, r13
0x180050524  lea     rdx, aT; "-%T"
0x18005052b  call    sqlite3MPrintf
0x180050530  jmp     short loc_18005053A
0x180050532  mov     rdx, r13
0x180050535  call    sqlite3NameFromToken
0x18005053a  mov     r13, rax
0x18005053d  mov     [rbp+0A0h+var_A8], rax
0x180050541  mov     rax, [rbp+0A0h+var_98]
0x180050545  xor     ecx, ecx
0x180050547  cmp     [rax+8], ecx
0x18005054a  jbe     short loc_180050556
0x18005054c  mov     rax, [rbp+0A0h+var_C0]
0x180050550  mov     rax, [rax+rbx]
0x180050554  jmp     short loc_180050559
0x180050556  mov     rax, rcx
0x180050559  mov     r8, [rbp+0A0h+var_90]
0x18005055d  mov     r9, r13
0x180050560  mov     edx, 13h
0x180050565  mov     [rbp+0A0h+var_118], rax
0x180050569  mov     rcx, rdi
0x18005056c  mov     [rsp+1A0h+var_180], rax
0x180050571  call    sqlite3AuthCheck
0x180050576  xor     ecx, ecx
0x180050578  test    eax, eax
0x18005057a  jnz     loc_180053D0D
0x180050580  mov     rax, [rbp+0A0h+var_90]
0x180050584  mov     qword ptr [rbp+0A0h+var_68], rcx
0x180050588  mov     qword ptr [rbp+0A0h+var_58+8], rcx
0x18005058c  mov     qword ptr [rbp+0A0h+var_68+8], rax
0x180050590  mov     qword ptr [rbp+0A0h+var_58], r13
0x180050594  mov     [r12+298h], ecx
0x18005059c  mov     rcx, r12
0x18005059f  call    sqlite3SafetyCheckOk
0x1800505a4  test    eax, eax
0x1800505a6  jnz     short loc_1800505C2
0x1800505a8  lea     r8, aMisuse; "misuse"
0x1800505af  mov     edx, 2D34Dh
0x1800505b4  lea     ecx, [rax+15h]
0x1800505b7  call    sqlite3ReportError
0x1800505bc  mov     [rsp+1A0h+var_138], eax
0x1800505c0  jmp     short loc_18005063A
0x1800505c2  mov     rcx, [r12+18h]
0x1800505c7  mov     [rsp+1A0h+var_138], r15d
0x1800505cc  call    sqlite3_mutex_enter
0x1800505d1  mov     rdx, [rbp+0A0h+var_118]
0x1800505d5  mov     rcx, r12
0x1800505d8  call    sqlite3DbNameToBtree
0x1800505dd  mov     [rbp+0A0h+var_D0], rax
0x1800505e1  test    rax, rax
0x1800505e4  jz      short loc_18005062C
0x1800505e6  mov     rcx, rax
0x1800505e9  call    sqlite3BtreeEnter
0x1800505ee  mov     rax, [rbp+0A0h+var_D0]
0x1800505f2  lea     r8, [rbp+0A0h+var_68]
0x1800505f6  mov     ebx, [r12+298h]
0x1800505fe  mov     rcx, [rax+8]
0x180050602  mov     rdx, [rcx]
0x180050605  mov     rcx, [rdx+48h]
0x180050609  mov     edx, 0Eh
0x18005060e  call    sqlite3OsFileControl
0x180050613  mov     rcx, [rbp+0A0h+var_D0]
0x180050617  mov     [rsp+1A0h+var_138], eax
0x18005061b  mov     [r12+298h], ebx
0x180050623  call    sqlite3BtreeLeave
0x180050628  mov     rbx, [rbp+0A0h+var_B0]
0x18005062c  mov     rcx, [r12+18h]
0x180050631  call    sqlite3_mutex_leave
0x180050636  mov     eax, [rsp+1A0h+var_138]
0x18005063a  test    eax, eax
0x18005063c  jnz     short loc_18005067D
0x18005063e  mov     edx, r15d
0x180050641  mov     rcx, r14
0x180050644  call    sqlite3VdbeSetNumCols
0x180050649  mov     r9, qword ptr [rbp+0A0h+var_68]
0x18005064d  xor     r8d, r8d
0x180050650  xor     edx, edx
0x180050652  mov     [rsp+1A0h+var_180], 0FFFFFFFFFFFFFFFFh
0x18005065b  mov     rcx, r14
0x18005065e  call    sqlite3VdbeSetColName
0x180050663  mov     rdx, qword ptr [rbp+0A0h+var_68]
0x180050667  mov     rcx, r14
0x18005066a  call    returnSingleText
0x18005066f  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x180050673  call    sqlite3_free
0x180050678  jmp     loc_180053D0D
0x18005067d  cmp     eax, 0Ch
0x180050680  jz      short loc_1800506B3
0x180050682  mov     r8, qword ptr [rbp+0A0h+var_68]
0x180050686  test    r8, r8
0x180050689  jz      short loc_1800506A7
0x18005068b  lea     rdx, aS_7; "%s"
0x180050692  mov     rcx, rdi
0x180050695  call    sqlite3ErrorMsg
0x18005069a  mov     rcx, qword ptr [rbp+0A0h+var_68]
0x18005069e  call    sqlite3_free
0x1800506a3  mov     eax, [rsp+1A0h+var_138]
0x1800506a7  add     [rdi+34h], r15d
0x1800506ab  mov     [rdi+18h], eax
0x1800506ae  jmp     loc_180053D0D
0x1800506b3  mov     rcx, [rbp+0A0h+var_90]
0x1800506b7  call    pragmaLocate
0x1800506bc  mov     [rbp+0A0h+var_110], rax
0x1800506c0  mov     r10, rax
0x1800506c3  test    rax, rax
0x1800506c6  jz      loc_180053D0D
0x1800506cc  test    [rax+9], r15b
0x1800506d0  jz      short loc_1800506E6
0x1800506d2  mov     rcx, rdi
0x1800506d5  call    sqlite3ReadSchema
0x1800506da  test    eax, eax
0x1800506dc  jnz     loc_180053D0D
0x1800506e2  mov     r10, [rbp+0A0h+var_110]
0x1800506e6  mov     r11d, 2
0x1800506ec  test    [r10+9], r11b
0x1800506f0  jnz     short loc_180050713
0x1800506f2  test    byte ptr [r10+9], 4
0x1800506f7  jz      short loc_1800506FE
0x1800506f9  test    r13, r13
0x1800506fc  jnz     short loc_180050713
0x1800506fe  mov     rdx, r10
0x180050701  mov     rcx, r14
0x180050704  call    setPragmaResultColumnNames
0x180050709  mov     r10, [rbp+0A0h+var_110]
0x18005070d  mov     r11d, 2
0x180050713  movzx   ecx, byte ptr [r10+8]
0x180050718  cmp     ecx, 16h
0x18005071b  ja      loc_180052C3C
0x180050721  jz      loc_18005175F
0x180050727  mov     eax, 0Ch
0x18005072c  cmp     ecx, eax
0x18005072e  ja      loc_180050C4F
0x180050734  jz      loc_180050BE3
0x18005073a  cmp     ecx, 7
0x18005073d  ja      loc_180050A68
0x180050743  jz      loc_1800509DE
0x180050749  sub     ecx, r15d
0x18005074c  jz      loc_18005099E
0x180050752  sub     ecx, r15d
0x180050755  jz      loc_1800508FF
0x18005075b  sub     ecx, r15d
0x18005075e  jz      loc_180050877
0x180050764  sub     ecx, r15d
0x180050767  jz      short loc_1800507BB
0x180050769  cmp     ecx, r11d
0x18005076c  jnz     loc_180053638
0x180050772  xor     eax, eax
0x180050774  test    r13, r13
0x180050777  jnz     short loc_18005078B
0x180050779  mov     rax, [rbp+0A0h+var_C0]
0x18005077d  mov     rax, [rax+rbx+18h]
0x180050782  movsxd  rdx, dword ptr [rax+74h]
0x180050786  jmp     loc_180053D05
0x18005078b  lea     rdx, [rsp+1A0h+var_13C]
0x180050790  mov     [rsp+1A0h+var_13C], eax
0x180050794  mov     rcx, r13
0x180050797  call    sqlite3GetInt32
0x18005079c  mov     r8, [rbp+0A0h+var_C0]
0x1800507a0  mov     eax, [rsp+1A0h+var_13C]
0x1800507a4  mov     rcx, [r8+rbx+18h]
0x1800507a9  mov     [rcx+74h], eax
0x1800507ac  mov     rdx, [r8+rbx+18h]
0x1800507b1  mov     rcx, [r8+rbx+8]
0x1800507b6  jmp     loc_180051752
0x1800507bb  xor     edi, edi
0x1800507bd  test    r13, r13
0x1800507c0  jnz     short loc_1800507E4
0x1800507c2  mov     rdx, r10
0x1800507c5  mov     rcx, r14
0x1800507c8  call    setPragmaResultColumnNames
0x1800507cd  mov     rbx, [rbp+0A0h+var_110]
0x1800507d1  mov     edx, edi
0x1800507d3  mov     rax, [r12+30h]
0x1800507d8  test    [rbx+10h], rax
0x1800507dc  setnz   dl
0x1800507df  jmp     loc_180053D05
0x1800507e4  mov     rbx, [r10+10h]
0x1800507e8  mov     rcx, r13
0x1800507eb  btr     rbx, 0Eh
0x1800507f0  cmp     [r12+65h], dil
0x1800507f5  cmovnz  rbx, [r10+10h]
0x1800507fa  xor     edx, edx
0x1800507fc  call    sqlite3GetBoolean
0x180050801  test    al, al
0x180050803  jz      short loc_18005081D
0x180050805  test    r15b, bl
0x180050808  jz      short loc_180050816
0x18005080a  mov     eax, [r12+30h]
0x18005080f  bt      rax, 1Ch
0x180050814  jb      short loc_18005085B
0x180050816  or      [r12+30h], rbx
0x18005081b  jmp     short loc_18005085B
0x18005081d  mov     rax, rbx
0x180050820  not     rax
0x180050823  and     [r12+30h], rax
0x180050828  cmp     rbx, 80000h
0x18005082f  jnz     short loc_18005083B
0x180050831  mov     [r12+300h], rdi
0x180050839  jmp     short loc_18005085B
0x18005083b  test    r15b, bl
0x18005083e  jz      short loc_18005085B
0x180050840  lea     rdx, aReset; "reset"
0x180050847  mov     rcx, r13
0x18005084a  call    sqlite3_stricmp
0x18005084f  test    eax, eax
0x180050851  jnz     short loc_18005085B
0x180050853  mov     rcx, r12
0x180050856  call    sqlite3ResetAllSchemasOfConnection
0x18005085b  xor     r9d, r9d
0x18005085e  mov     dword ptr [rsp+1A0h+var_180], edi
0x180050862  xor     r8d, r8d
0x180050865  mov     edx, 0A6h
0x18005086a  mov     rcx, r14
0x18005086d  call    sqlite3VdbeAddOp3
0x180050872  jmp     loc_180050A5B
0x180050877  mov     rax, [rbp+0A0h+var_C0]
0x18005087b  mov     rbx, [rax+rbx+8]
0x180050880  test    r13, r13
0x180050883  jnz     short loc_180050895
0x180050885  mov     rcx, rbx
0x180050888  call    sqlite3BtreeGetAutoVacuum
0x18005088d  movsxd  rdx, eax
0x180050890  jmp     loc_180053D05
0x180050895  mov     rcx, r13
0x180050898  call    getAutoVacuum
0x18005089d  mov     edi, eax
0x18005089f  mov     edx, eax
0x1800508a1  mov     rcx, rbx
0x1800508a4  mov     [r12+6Ah], dil
0x1800508a9  call    sqlite3BtreeSetAutoVacuum
0x1800508ae  test    eax, eax
  ... truncated ...
```
