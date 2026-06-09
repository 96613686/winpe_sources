# sqlite3Select

- ea: `0x18012c390`
- end: `0x18012f86f`
- name: `sqlite3Select`
- size: `13535`
- prototype: ``
- caller_count: `13`
- callee_count: `64`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c5b40`
- `0x1800d7100`
- `0x1800e6b10`
- `0x1800e7650`
- `0x180103fe0`
- `0x180104a80`
- `0x18010a820`
- `0x18011b040`
- `0x18011e380`
- `0x18011e700`
- `0x18012c390`
- `0x18015bd20`
- `0x180174050`

## callees

- `0x1800b99d0`
- `0x1800bafe0`
- `0x1800c6fc0`
- `0x1800c9320`
- `0x1800ce5c0`
- `0x1800cf1f0`
- `0x1800d0b10`
- `0x1800d14d0`
- `0x1800d4790`
- `0x1800d51e0`
- `0x1800d64b0`
- `0x1800d8770`
- `0x1800d8de0`
- `0x1800db220`
- `0x1800e6b10`
- `0x1800f01d0`
- `0x1800f08e0`
- `0x1800f40e0`
- `0x1800f4540`
- `0x1800f6f50`
- `0x1800f8d00`
- `0x1800fdf90`
- `0x180108840`
- `0x1801089d0`
- `0x180108a90`
- `0x18010b290`
- `0x18010c2b0`
- `0x18010c4b0`
- `0x18010e050`
- `0x18010f780`
- `0x18010fd20`
- `0x180110050`
- `0x180110960`
- `0x180110db0`
- `0x180110ea0`
- `0x180111210`
- `0x1801155c0`
- `0x18011d150`
- `0x18011d210`
- `0x18011de20`
- `0x18011ef50`
- `0x18011f340`
- `0x180121fc0`
- `0x18012c390`
- `0x180130690`
- `0x180137a10`
- `0x180137a80`
- `0x180137b60`
- `0x180138070`
- `0x180138140`

## string_xrefs

- `0x18012e1fd`: `USE TEMP B-TREE FOR %s`
- `0x18012f7a7`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // r13
  unsigned int v4; // r12d
  __int64 v5; // rax
  BOOL v6; // esi
  __int128 *v7; // r14
  __int64 v8; // rbx
  _QWORD *v9; // rdi
  __int64 *v10; // r8
  __int64 v11; // r10
  int v12; // r11d
  const char *v13; // r8
  _DWORD *v14; // rdx
  int *v15; // r11
  __int64 v16; // r10
  __int64 v17; // rax
  int v18; // esi
  __int64 v19; // r14
  unsigned int *v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // r15
  int v23; // eax
  char v24; // al
  __int64 v25; // rdx
  int v26; // eax
  int v27; // r10d
  unsigned int *v28; // r9
  char v29; // al
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  unsigned int *v33; // rcx
  int v34; // r8d
  int v35; // ecx
  int v36; // eax
  _BYTE *v37; // rax
  int *v38; // r14
  unsigned int v39; // r9d
  int v41; // edi
  __int64 v42; // rax
  __int64 v43; // rsi
  __int64 v44; // r8
  char *v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r14
  __int64 v49; // rax
  __int64 v50; // rcx
  int *v51; // rcx
  __int64 v52; // rbx
  __int64 v53; // rdx
  _WORD *v54; // rcx
  unsigned __int16 v55; // ax
  __int64 v56; // rdi
  int v57; // r10d
  __int64 v58; // r11
  __int64 v59; // r9
  __int64 v60; // r8
  unsigned __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rax
  int v65; // ebx
  _QWORD *v66; // rcx
  int *v67; // r10
  __int64 v68; // r15
  unsigned int *v69; // rsi
  int v70; // r14d
  __int64 v71; // rax
  char v72; // cl
  int v73; // edi
  __int64 v74; // rdi
  __int64 v75; // rsi
  int v76; // ebx
  int v77; // edx
  __int64 v78; // rcx
  _BYTE *v79; // rax
  __int64 v80; // rsi
  __int64 v81; // rbx
  int v82; // edx
  __int64 v83; // rcx
  int v84; // r8d
  __int64 v85; // rcx
  __int64 v86; // rax
  char *v87; // r14
  int v88; // eax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rax
  int v93; // edx
  int v94; // r8d
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rbx
  int v100; // edx
  __int64 v101; // rcx
  int v102; // r8d
  __int64 v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rcx
  int v106; // edx
  int v107; // r8d
  __int64 v108; // rcx
  __int64 v109; // rax
  __int64 v110; // rbx
  __int64 v111; // rdi
  __int64 v112; // rcx
  __int64 v113; // rax
  int v114; // eax
  __int64 v115; // rcx
  __int64 v116; // rax
  char *v117; // r14
  __int64 *v118; // rax
  __int64 v119; // rcx
  int v120; // edx
  int v121; // r8d
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 *v124; // rax
  __int64 v125; // rcx
  int v126; // ecx
  char *v127; // rdx
  char v128; // r14
  __int64 v129; // r15
  int *v130; // rsi
  int v131; // edi
  _BYTE *v132; // rbx
  signed __int64 v133; // rsi
  __int64 v134; // rax
  char *v135; // rbx
  __int64 v136; // rax
  int v137; // r8d
  int v138; // esi
  int *v139; // r8
  int v140; // ecx
  __int64 v141; // rdi
  __int64 v142; // rbx
  __int64 v143; // rdx
  int v144; // edx
  _DWORD *v145; // rcx
  _QWORD *v146; // r10
  __int64 v147; // r11
  unsigned int v148; // eax
  __int64 *v149; // rax
  int v150; // esi
  __int64 v151; // rax
  __int64 v152; // rdi
  __int64 v153; // rbx
  __int64 v154; // rcx
  __int64 v155; // rax
  int v156; // eax
  bool v157; // zf
  __int64 v158; // rdx
  __int64 v159; // rax
  __int64 v160; // rdi
  __int16 v161; // bx
  _DWORD *v162; // rsi
  __int64 v163; // rax
  __int64 v164; // r8
  __int64 v165; // rbx
  int v166; // r10d
  __int16 v167; // ax
  char v168; // al
  int v169; // edx
  int v170; // eax
  __int64 v171; // rax
  int v172; // esi
  unsigned int v173; // r15d
  int v174; // r14d
  int v175; // edi
  __int64 v176; // rcx
  __int64 v177; // rcx
  __int64 v178; // rax
  __int64 v179; // rcx
  int v180; // esi
  __int64 v181; // rsi
  int v182; // ebx
  __int64 v183; // rcx
  int v184; // r14d
  __int64 v185; // rcx
  int v186; // edi
  __int64 v187; // rdx
  _DWORD *v188; // r14
  int v189; // r15d
  _DWORD *v190; // rcx
  int v191; // eax
  _WORD *v192; // rcx
  int v193; // eax
  _WORD *v194; // rcx
  char *v195; // r8
  int v196; // eax
  int v197; // edx
  _DWORD *v198; // rcx
  signed __int64 v199; // r8
  char v200; // al
  int v201; // edi
  _BYTE *v202; // rbx
  signed __int64 v203; // rsi
  __int64 v204; // rsi
  int v205; // eax
  __int64 v206; // rcx
  __int64 v207; // rbx
  int v208; // eax
  _QWORD *v209; // rax
  char *v210; // rax
  __int64 *v211; // rbx
  int v212; // edi
  __int64 v213; // rdx
  _DWORD *v214; // rax
  __int64 *v215; // rbx
  int v216; // edi
  __int64 v217; // rdx
  __int64 v218; // rdx
  _QWORD *v219; // rbx
  __int64 *v220; // rax
  __int64 v221; // r8
  __int64 v222; // r11
  char *v223; // r8
  char *i; // rdx
  __int64 v225; // rax
  __int64 v226; // r9
  unsigned __int8 v227; // r14
  char v228; // bl
  char *v229; // r9
  __int64 v230; // rdx
  __int64 v231; // rax
  __int64 v232; // rax
  __int64 v233; // r10
  int *appended; // rdi
  int *v235; // rax
  __int64 v236; // rax
  __int64 v237; // rcx
  __int64 v238; // rdx
  __int64 v239; // rax
  __int64 v240; // rbx
  int *v241; // rax
  __int64 v242; // rax
  int v243; // ecx
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // r9
  __int64 v247; // rbx
  int v248; // edx
  int v249; // r8d
  __int64 v250; // rcx
  __int64 v251; // rax
  int v252; // eax
  __int64 v253; // rdx
  _DWORD *v254; // r9
  int v255; // edx
  int v256; // eax
  int v257; // r14d
  int v258; // r8d
  int v259; // ebx
  int v260; // ecx
  int v261; // eax
  __int64 v262; // rcx
  __int64 v263; // rcx
  __int64 v264; // rax
  __int64 v265; // rcx
  int v266; // edx
  __int64 v267; // rcx
  __int64 v268; // rax
  __int64 v269; // rcx
  __int64 v270; // rcx
  __int64 v271; // rax
  __int16 v272; // ax
  __int64 v273; // r9
  __int64 v274; // r14
  __int64 v275; // r8
  int v276; // ecx
  __int16 *v277; // rdx
  int v278; // eax
  int v279; // edx
  _QWORD *v280; // rdi
  int v281; // r14d
  const char *v282; // r9
  int v283; // ebx
  int v284; // r12d
  int v285; // eax
  int v286; // edx
  __int64 v287; // r9
  __int16 *v288; // r8
  int v289; // ecx
  int v290; // eax
  int v291; // eax
  char v292; // al
  int v293; // r15d
  unsigned __int8 v294; // al
  int v295; // ecx
  int v296; // eax
  __int64 v297; // r9
  __int64 v298; // rdx
  __int64 v299; // rsi
  int v300; // r14d
  unsigned int v301; // edi
  __int64 v302; // rbx
  __int64 v303; // rbx
  unsigned int v304; // eax
  int v305; // ecx
  __int64 v306; // rdx
  char v307; // al
  int v308; // ebx
  unsigned __int8 v309; // al
  __int64 v310; // rcx
  __int64 v311; // rcx
  __int64 v312; // rax
  __int64 v313; // rcx
  int v314; // edx
  __int64 v315; // rcx
  __int64 v316; // rax
  __int64 v317; // rax
  __int64 v318; // rax
  char v319; // al
  unsigned __int8 v320; // al
  __int64 v321; // rcx
  __int64 v322; // rcx
  __int64 v323; // rax
  __int64 v324; // rcx
  int v325; // edx
  unsigned int v326; // r8d
  __int64 v327; // rcx
  __int64 v328; // rax
  bool v329; // cc
  int v330; // edi
  __int64 v331; // rbx
  int v332; // eax
  __int64 v333; // rcx
  __int64 v334; // rbx
  __int64 v335; // r12
  int v336; // edx
  int v337; // r8d
  int *v338; // rsi
  _QWORD *v339; // rsi
  unsigned int v340; // edi
  _DWORD *v341; // rcx
  int v342; // r14d
  __int64 v343; // rcx
  unsigned int v344; // edx
  __int64 v345; // rcx
  __int64 v346; // rax
  __int64 v347; // rcx
  __int64 v348; // rax
  __int64 v349; // rbx
  unsigned int v350; // eax
  int v351; // ecx
  __int64 v352; // rdx
  __int64 v353; // r10
  __int64 v354; // rdx
  int v355; // r8d
  unsigned int v356; // esi
  int v357; // edi
  int v358; // eax
  __int64 v359; // rcx
  __int64 v360; // rax
  __int64 v361; // rax
  __int64 v362; // rdx
  __int64 v363; // rbx
  int v364; // edx
  __int64 v365; // rax
  __int64 v366; // rcx
  int v367; // edx
  __int64 v368; // r10
  __int64 v369; // rcx
  __int64 v370; // rcx
  __int64 v371; // rax
  __int64 v372; // rcx
  int v373; // r14d
  int v374; // r8d
  int v375; // eax
  unsigned int v376; // edx
  __int64 v377; // rcx
  __int64 v378; // rax
  __int64 v379; // rcx
  unsigned int v380; // edi
  __int64 v381; // rcx
  __int64 v382; // rax
  __int64 v383; // rcx
  __int64 v384; // rcx
  __int64 v385; // rax
  __int64 *v386; // rax
  unsigned int v387; // ebx
  __int64 v388; // r9
  __int64 v389; // rcx
  __int64 v390; // rcx
  __int64 v391; // rax
  __int64 v392; // rcx
  int v393; // edx
  __int64 v394; // rcx
  int v395; // ebx
  __int64 v396; // rcx
  __int64 v397; // rax
  __int64 v398; // rbx
  __int64 v399; // rcx
  __int64 v400; // rax
  __int64 v401; // rcx
  __int64 v402; // rcx
  __int64 v403; // rax
  __int64 v404; // rdi
  unsigned int v405; // edx
  __int64 v406; // rcx
  __int64 v407; // rax
  __int64 v408; // rcx
  __int64 v409; // rcx
  __int64 v410; // rax
  __int64 v411; // rcx
  int v412; // ebx
  __int64 v413; // rax
  int v414; // r15d
  int v415; // edx
  unsigned int v416; // ebx
  __int64 v417; // rcx
  __int64 v418; // rax
  __int64 v419; // rcx
  __int64 v420; // rcx
  __int64 v421; // rax
  __int64 v422; // rcx
  __int64 v423; // rcx
  __int64 v424; // rax
  __int64 v425; // rcx
  int v426; // edx
  __int64 v427; // rcx
  __int64 v428; // rcx
  __int64 v429; // rax
  __int64 v430; // rcx
  int v431; // edx
  __int64 v432; // rcx
  __int64 v433; // rax
  unsigned int v434; // ebx
  __int64 v435; // rdx
  __int64 v436; // r8
  __int64 v437; // r8
  __int64 v438; // rdx
  __int64 v439; // rdx
  unsigned int v440; // edi
  __int64 v441; // rsi
  _QWORD *j; // rcx
  _QWORD *v443; // r8
  __int64 v444; // r14
  _QWORD *v445; // rcx
  __int64 k; // rbx
  int v447; // r15d
  int v448; // r12d
  int v449; // eax
  __int64 m; // rax
  __int16 v451; // cx
  __int64 v452; // rcx
  __int64 v453; // rcx
  __int64 v454; // rax
  __int64 v455; // rax
  __int64 v456; // rdx
  __int64 v457; // rdx
  int v458; // edx
  __int64 v459; // rcx
  __int64 v460; // rcx
  __int64 v461; // rax
  __int64 v462; // rcx
  __int64 v463; // rcx
  __int64 v464; // rax
  const wchar_t *v465; // rax
  const char *v466; // rcx
  unsigned int v467; // edi
  __int64 v468; // rsi
  __int16 v469; // bx
  int v470; // r8d
  int v471; // edx
  _QWORD *v472; // rcx
  __int64 v473; // rcx
  __int64 v474; // rcx
  __int64 v475; // rax
  int *v476; // rax
  __int64 v477; // rax
  __int64 v478; // rbx
  unsigned int v479; // esi
  __int64 v480; // r8
  __int64 v481; // rcx
  __int64 v482; // rcx
  __int64 v483; // rax
  __int64 v484; // rcx
  __int64 v485; // rdx
  __int64 v486; // rcx
  int v487; // edx
  __int64 v488; // rcx
  __int64 v489; // rax
  int v490; // ebx
  __int64 v491; // rcx
  int v492; // edx
  __int64 v493; // rcx
  _QWORD *v494; // rdx
  int v495; // [rsp+38h] [rbp-C8h]
  int v498; // [rsp+50h] [rbp-B0h]
  __int16 v499; // [rsp+50h] [rbp-B0h]
  int *v500; // [rsp+58h] [rbp-A8h]
  int v501; // [rsp+58h] [rbp-A8h]
  __int64 v502; // [rsp+60h] [rbp-A0h]
  __int64 v503; // [rsp+68h] [rbp-98h]
  _DWORD *v504; // [rsp+68h] [rbp-98h]
  int *v505; // [rsp+70h] [rbp-90h]
  __int64 v506; // [rsp+70h] [rbp-90h]
  char v507; // [rsp+78h] [rbp-88h]
  int v508; // [rsp+7Ch] [rbp-84h] BYREF
  _DWORD *v509; // [rsp+80h] [rbp-80h]
  unsigned int v510; // [rsp+88h] [rbp-78h]
  unsigned int v511; // [rsp+8Ch] [rbp-74h]
  char *v512; // [rsp+90h] [rbp-70h]
  int v513; // [rsp+98h] [rbp-68h]
  int v514; // [rsp+9Ch] [rbp-64h]
  int v515; // [rsp+A0h] [rbp-60h]
  __int64 v516; // [rsp+A8h] [rbp-58h]
  int v517; // [rsp+B0h] [rbp-50h]
  unsigned int v518; // [rsp+B4h] [rbp-4Ch]
  int v519; // [rsp+B8h] [rbp-48h]
  __int64 v520; // [rsp+C0h] [rbp-40h]
  int v521; // [rsp+C8h] [rbp-38h]
  int v522; // [rsp+CCh] [rbp-34h]
  __int64 v523; // [rsp+D0h] [rbp-30h]
  char v524; // [rsp+D8h] [rbp-28h] BYREF
  char v525; // [rsp+D9h] [rbp-27h]
  int v526; // [rsp+DCh] [rbp-24h]
  int v527; // [rsp+E0h] [rbp-20h]
  _QWORD *v528; // [rsp+E8h] [rbp-18h]
  __int64 v529; // [rsp+F0h] [rbp-10h]
  int *v530; // [rsp+F8h] [rbp-8h]
  unsigned int v531; // [rsp+100h] [rbp+0h]
  __int64 v532; // [rsp+108h] [rbp+8h]
  __int128 v533; // [rsp+110h] [rbp+10h] BYREF
  __int128 v534; // [rsp+120h] [rbp+20h]
  __int128 v535; // [rsp+130h] [rbp+30h]
  _QWORD *v536; // [rsp+140h] [rbp+40h] BYREF
  __int64 (__fastcall *v537)(); // [rsp+148h] [rbp+48h]
  __int128 v538; // [rsp+150h] [rbp+50h]
  __int128 v539; // [rsp+160h] [rbp+60h]
  _QWORD v540[3]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v541; // [rsp+188h] [rbp+88h]
  __int128 v542; // [rsp+198h] [rbp+98h]

  v3 = (_QWORD *)a1[2];
  v4 = 0;
  v5 = *a1;
  v6 = 1;
  v516 = a3;
  v7 = (__int128 *)a3;
  v8 = a2;
  v9 = a1;
  v529 = 1;
  v532 = 0;
  v502 = v5;
  v528 = v3;
  if ( !v3 )
  {
    if ( !a1[21] && (*(_BYTE *)(v5 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v3 = (_QWORD *)sqlite3VdbeCreate(a1);
    v528 = v3;
  }
  if ( !v8 || *((_DWORD *)v9 + 12) || (unsigned int)sqlite3AuthCheck((_DWORD)v9, 21, 0, 0, 0) )
    return 1;
  if ( *(_BYTE *)v7 <= 6u )
  {
    if ( *(_QWORD *)(v8 + 72) )
    {
      sqlite3ParserAddCleanup(v9, sqlite3ExprListDeleteGeneric);
      *(_QWORD *)(v8 + 72) = 0;
    }
    *(_DWORD *)(v8 + 4) &= ~1u;
    *(_DWORD *)(v8 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(v9, v8, 0);
  v10 = &qword_1803DCAC0;
  if ( *((_DWORD *)v9 + 12) )
    goto LABEL_748;
  if ( (*(_DWORD *)(v8 + 4) & 0x800000) != 0 )
  {
    if ( (unsigned int)sameSrcAlias(*(_QWORD *)(v8 + 40) + 8LL, *(_QWORD *)(v8 + 40), &qword_1803DCAC0) )
    {
      v13 = *(const char **)(v11 + 32);
      if ( !v13 )
        v13 = **(const char ***)(v11 + 40);
      sqlite3ErrorMsg(v9, "target object/alias may not appear in FROM clause: %s", v13);
      goto LABEL_747;
    }
    *(_DWORD *)(v8 + 4) = v12 & 0xFF7FFFFF;
  }
  if ( *(_BYTE *)v7 == 9 )
    sqlite3GenerateColumnNames(v9, v8, v10);
  if ( (unsigned int)sqlite3WindowRewrite(v9, v8, v10) )
  {
LABEL_747:
    v10 = &qword_1803DCAC0;
LABEL_748:
    v493 = *((int *)v9 + 78);
    if ( (_DWORD)v493 )
    {
      v494 = (_QWORD *)v9[2];
      if ( !*(_BYTE *)(*v494 + 103LL) )
        v10 = (__int64 *)(v494[17] + 24 * v493);
      v4 = *((_DWORD *)v10 + 2);
    }
    *((_DWORD *)v9 + 78) = v4;
    return v6;
  }
  v14 = *(_DWORD **)(v8 + 72);
  v15 = *(int **)(v8 + 40);
  v16 = v502;
  LOBYTE(v4) = (*(_DWORD *)(v8 + 4) & 8) != 0;
  v519 = *(_DWORD *)(v8 + 4) & 8;
  v17 = *(_QWORD *)(v8 + 80);
  v18 = 0;
  v500 = v15;
  v511 = v4;
  v509 = v14;
  v533 = (unsigned __int64)v14;
  v534 = 0;
  v535 = 0;
  if ( !v17 )
  {
    v19 = 0;
    v17 = 0;
    if ( *v15 > 0 )
    {
      while ( 1 )
      {
        v20 = (unsigned int *)&v15[26 * v19];
        v21 = *((_QWORD *)v20 + 6);
        v22 = *((_QWORD *)v20 + 5);
        if ( (v20[17] & 0x48) != 0 )
        {
          v23 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(a2 + 48), v20[19], v20[17] & 0x40);
          v16 = v502;
          if ( !v23 || (*(_DWORD *)(v502 + 96) & 0x2000) != 0 )
          {
            v15 = v500;
          }
          else
          {
            v24 = *((_BYTE *)v20 + 68);
            if ( (v24 & 8) != 0 )
            {
              if ( (v24 & 0x10) != 0 )
              {
                *((_BYTE *)v20 + 68) = v24 & 0xF7;
              }
              else
              {
                v25 = v20[19];
                *((_BYTE *)v20 + 68) = v24 & 0xD7;
                unsetJoinExpr(*(_QWORD *)(a2 + 48), v25, 0);
              }
            }
            v15 = v500;
            if ( (v20[17] & 0x40) != 0 )
            {
              v26 = *v500;
              v27 = v18 + 1;
              if ( v18 + 1 < *v500 )
              {
                v28 = (unsigned int *)&v500[26 * v19 + 43];
                do
                {
                  v29 = *(_BYTE *)v28;
                  if ( (*(_BYTE *)v28 & 0x10) != 0 )
                  {
                    if ( (v29 & 8) != 0 )
                    {
                      *(_BYTE *)v28 = v29 & 0xEF;
                    }
                    else
                    {
                      v30 = v28[2];
                      *(_BYTE *)v28 = v29 & 0xCF;
                      unsetJoinExpr(*(_QWORD *)(a2 + 48), v30, 1);
                    }
                  }
                  v26 = *v15;
                  ++v27;
                  v28 += 26;
                }
                while ( v27 < *v15 );
                v3 = v528;
                v4 = v511;
              }
              v31 = v26 - 1;
              v32 = v31;
              if ( v31 >= 0 )
              {
                v33 = (unsigned int *)&v15[26 * v31 + 17];
                do
                {
                  *(_BYTE *)v33 &= ~0x40u;
                  if ( (*(_BYTE *)v33 & 0x10) != 0 )
                    break;
                  v33 -= 26;
                  --v32;
                }
                while ( v32 >= 0 );
              }
              v16 = v502;
            }
          }
          v14 = v509;
        }
        if ( !v21 )
          goto LABEL_72;
        v34 = *(__int16 *)(v22 + 54);
        v35 = **(_DWORD **)(v21 + 32);
        if ( v34 != v35 )
        {
          v9 = a1;
          sqlite3ErrorMsg(a1, "expected %d columns for '%s' but got %d", v34, *(const char **)v22, v35);
          goto LABEL_86;
        }
        if ( (v20[18] & 0x100) == 0 || *(_BYTE *)(*((_QWORD *)v20 + 13) + 18LL) )
        {
          v36 = *(_DWORD *)(v21 + 4);
          v8 = a2;
          if ( (v36 & 8) == 0 )
          {
            if ( !*(_QWORD *)(v21 + 72) )
              goto LABEL_65;
            if ( (*(_QWORD *)(a2 + 72) || *v15 > 1)
              && !*(_QWORD *)(v21 + 96)
              && (v36 & 0x8000000) == 0
              && (*(_DWORD *)(a2 + 4) & 0x8000000) == 0
              && (*(_DWORD *)(v16 + 96) & 0x40000) == 0 )
            {
              sqlite3ParserAddCleanup(a1, sqlite3ExprListDeleteGeneric);
              *(_QWORD *)(v21 + 72) = 0;
LABEL_65:
              v9 = a1;
              if ( (unsigned int)flattenSubquery(a1, a2, (unsigned int)v18, v4) )
              {
                if ( *((_DWORD *)a1 + 12) )
                  goto LABEL_86;
                v18 = -1;
                v19 = -1;
              }
              v16 = v502;
              v15 = *(int **)(a2 + 40);
              v500 = v15;
              if ( *(_BYTE *)(v502 + 103) )
                goto LABEL_86;
              if ( *(_BYTE *)v516 <= 8u )
              {
                v14 = v509;
              }
              else
              {
                v14 = *(_DWORD **)(a2 + 72);
                v509 = v14;
                *(_QWORD *)&v533 = v14;
              }
              goto LABEL_74;
            }
            if ( v18 || (*(_DWORD *)(a2 + 4) & 0x40000) == 0 || *v15 != 1 && (v15[43] & 0x22) == 0 )
              goto LABEL_65;
          }
          v9 = a1;
        }
        else
        {
LABEL_72:
          v9 = a1;
          v8 = a2;
        }
LABEL_74:
        v17 = *(_QWORD *)(v8 + 80);
        ++v18;
        ++v19;
        if ( v17 )
          break;
        if ( v18 >= *v15 )
        {
          v505 = v14;
LABEL_77:
          v37 = *(_BYTE **)(v8 + 48);
          if ( v37 && *v37 == 44 && (*(_DWORD *)(v16 + 96) & 0x8000) == 0 )
            propagateConstants(v9, v8);
          if ( (*(_DWORD *)(v502 + 96) & 0x201) == 0 && (unsigned int)countOfViewOptimization(v9, v8) )
          {
            if ( !*(_BYTE *)(v502 + 103) )
            {
              v38 = *(int **)(v8 + 40);
              v500 = v38;
              goto LABEL_93;
            }
LABEL_86:
            v4 = 0;
LABEL_746:
            v6 = 1;
            goto LABEL_747;
          }
          v38 = v500;
LABEL_93:
          v4 = 0;
          v41 = 0;
          v498 = 0;
          if ( *v38 > 0 )
          {
            v42 = 0;
            v503 = 0;
            while ( 1 )
            {
              v43 = (__int64)&v38[26 * v42 + 2];
              v523 = v43;
              if ( !*(_QWORD *)(v43 + 80) )
              {
                v44 = *(_QWORD *)(v43 + 16);
                if ( v44 )
                  sqlite3AuthCheck((_DWORD)a1, 20, v44, (unsigned int)&byte_1802990D8, *(_QWORD *)(v43 + 8));
              }
              v45 = *(char **)(v43 + 40);
              v512 = v45;
              if ( v45 )
              {
                if ( !*(_DWORD *)(v43 + 48) )
                  break;
              }
              v8 = a2;
LABEL_201:
              v42 = v503 + 1;
              v498 = ++v41;
              ++v503;
              if ( v41 >= *v38 )
                goto LABEL_202;
            }
            v508 = 0;
            heightOfSelect(a2, &v508);
            v46 = v502;
            *((_DWORD *)a1 + 77) += v508;
            if ( (*(_DWORD *)(v502 + 96) & 0x1000) == 0 )
            {
              if ( (*(_DWORD *)(v43 + 64) & 0x100) == 0
                || (v47 = *(_QWORD *)(v43 + 96), *(_BYTE *)(v47 + 18)) && *(int *)v47 < 2 )
              {
                pushDownWhereTerms((_DWORD)a1, (_DWORD)v45, *(_QWORD *)(a2 + 48), (_DWORD)v38, v41);
                v46 = v502;
              }
            }
            if ( (*(_DWORD *)(v46 + 96) & 0x4000000) == 0 && (*(_DWORD *)(v43 + 64) & 0x108) == 0 )
            {
              v48 = *(_QWORD *)(v43 + 40);
              v49 = v48;
              if ( v48 )
              {
                while ( (*(_BYTE *)(v49 + 4) & 9) == 0 )
                {
                  v50 = *(_QWORD *)(v49 + 80);
                  if ( v50 )
                  {
                    if ( *(_BYTE *)v49 != 0x87 )
                      break;
                  }
                  if ( *(_QWORD *)(v49 + 112) )
                    break;
                  v49 = *(_QWORD *)(v49 + 80);
                  if ( !v50 )
                    goto LABEL_113;
                }
              }
              else
              {
LABEL_113:
                v51 = *(int **)(v48 + 72);
                v52 = *(_QWORD *)(v43 + 80);
                if ( v51 )
                {
                  v53 = *v51;
                  if ( v53 > 0 )
                  {
                    v54 = v51 + 8;
                    do
                    {
                      if ( *v54 )
                      {
                        v55 = *v54 - 1;
                        if ( v55 >= 0x40u )
                          LOBYTE(v55) = 63;
                        v52 |= 1LL << v55;
                      }
                      v54 += 16;
                      --v53;
                    }
                    while ( v53 );
                  }
                }
                v56 = *(__int16 *)(*(_QWORD *)(v43 + 32) + 54LL);
                v57 = 0;
                v58 = 0;
                if ( v56 > 0 )
                {
                  v59 = 1;
                  v60 = 0;
                  do
                  {
                    v61 = 0x8000000000000000uLL;
                    if ( v57 < 63 )
                      v61 = v59;
                    if ( (v52 & v61) == 0 )
                    {
                      v62 = v48;
                      do
                      {
                        v63 = *(_QWORD *)(*(_QWORD *)(v62 + 32) + v60 + 8);
                        if ( *(_BYTE *)v63 != 121 )
                        {
                          *(_DWORD *)(v63 + 4) &= 0xFFF7DFFF;
                          *(_BYTE *)v63 = 121;
                          *(_DWORD *)(v62 + 4) |= 0x1000000u;
                        }
                        v62 = *(_QWORD *)(v62 + 80);
                      }
                      while ( v62 );
                    }
                    ++v57;
                    v59 = __ROL8__(v59, 1);
                    ++v58;
                    v60 += 32;
                  }
                  while ( v58 < v56 );
                  v3 = v528;
                }
                v41 = v498;
              }
            }
            v64 = *(_QWORD *)(v43 + 16);
            v65 = v41;
            v66 = a1;
            v67 = v500;
            v68 = a1[46];
            v69 = (unsigned int *)&v500[26 * v503];
            a1[46] = v64;
            v70 = *(_DWORD *)(a2 + 4);
            if ( (v69[18] & 0x100) != 0 )
            {
              v71 = *((_QWORD *)v69 + 13);
              v72 = *(_BYTE *)(v71 + 18);
              if ( v72 && (*(int *)v71 < 2 || v72 == 2) )
              {
                v66 = a1;
                goto LABEL_138;
              }
LABEL_154:
              v80 = v523;
              if ( (*(_DWORD *)(v523 + 64) & 0x100) != 0
                && (v81 = *(_QWORD *)(v523 + 96), v82 = *(_DWORD *)(v81 + 4), v82 > 0) )
              {
                v83 = *((int *)v3 + 36);
                v84 = *(_DWORD *)(v81 + 8);
                if ( *((_DWORD *)v3 + 37) > (int)v83 )
                {
                  *((_DWORD *)v3 + 36) = v83 + 1;
                  v91 = 3 * v83;
                  v92 = v3[17];
                  *(_DWORD *)(v92 + 8 * v91) = 10;
                  *(_DWORD *)(v92 + 8 * v91 + 4) = v84;
                  *(_DWORD *)(v92 + 8 * v91 + 8) = v82;
                  *(_DWORD *)(v92 + 8 * v91 + 12) = 0;
                  *(_QWORD *)(v92 + 8 * v91 + 16) = 0;
                }
                else
                {
                  _mm_lfence();
                  growOp3((_DWORD)v3, 10, v84, v82, 0);
                }
                v93 = *(_DWORD *)(v81 + 12);
                v94 = *(_DWORD *)(v80 + 68);
                if ( v94 != v93 )
                {
                  v95 = *((int *)v3 + 36);
                  if ( *((_DWORD *)v3 + 37) > (int)v95 )
                  {
                    *((_DWORD *)v3 + 36) = v95 + 1;
                    v96 = 3 * v95;
                    v97 = v3[17];
                    *(_DWORD *)(v97 + 8 * v96) = 115;
                    *(_DWORD *)(v97 + 8 * v96 + 4) = v94;
                    *(_DWORD *)(v97 + 8 * v96 + 8) = v93;
                    *(_DWORD *)(v97 + 8 * v96 + 12) = 0;
                    *(_QWORD *)(v97 + 8 * v96 + 16) = 0;
                  }
                  else
                  {
                    growOp3((_DWORD)v3, 115, v94, v93, 0);
                  }
                }
                v9 = a1;
                *((_WORD *)v512 + 1) = *(_WORD *)(v81 + 16);
              }
              else
              {
                v98 = isSelfJoinView(v67, v523, 0, (unsigned int)v41);
                v99 = v98;
                if ( v98 )
                {
                  v100 = *(_DWORD *)(v98 + 48);
                  if ( v100 )
                  {
                    v101 = *((int *)v3 + 36);
                    v102 = *(_DWORD *)(v98 + 52);
                    if ( *((_DWORD *)v3 + 37) > (int)v101 )
                    {
                      *((_DWORD *)v3 + 36) = v101 + 1;
                      v103 = 3 * v101;
                      v104 = v3[17];
                      *(_DWORD *)(v104 + 8 * v103) = 10;
                      *(_DWORD *)(v104 + 8 * v103 + 4) = v102;
                      *(_DWORD *)(v104 + 8 * v103 + 8) = v100;
                      *(_DWORD *)(v104 + 8 * v103 + 12) = 0;
                      *(_QWORD *)(v104 + 8 * v103 + 16) = 0;
                    }
                    else
                    {
                      growOp3((_DWORD)v3, 10, v102, v100, 0);
                    }
                  }
                  v105 = *((int *)v3 + 36);
                  v106 = *(_DWORD *)(v99 + 68);
                  v107 = *(_DWORD *)(v80 + 68);
                  if ( *((_DWORD *)v3 + 37) > (int)v105 )
                  {
                    *((_DWORD *)v3 + 36) = v105 + 1;
                    v108 = 3 * v105;
                    v109 = v3[17];
                    *(_DWORD *)(v109 + 8 * v108) = 115;
                    *(_DWORD *)(v109 + 8 * v108 + 4) = v107;
                    *(_DWORD *)(v109 + 8 * v108 + 8) = v106;
                    *(_DWORD *)(v109 + 8 * v108 + 12) = 0;
                    *(_QWORD *)(v109 + 8 * v108 + 16) = 0;
                  }
                  else
                  {
                    growOp3((_DWORD)v3, 115, v107, v106, 0);
                  }
                  v9 = a1;
                  *((_WORD *)v512 + 1) = *(_WORD *)(*(_QWORD *)(v99 + 40) + 2LL);
                }
                else
                {
                  LODWORD(v110) = 0;
                  *(_DWORD *)(v80 + 52) = ++*((_DWORD *)a1 + 14);
                  v111 = *((int *)v3 + 36);
                  if ( *((_DWORD *)v3 + 37) > (int)v111 )
                  {
                    v112 = 3 * v111;
                    *((_DWORD *)v3 + 36) = v111 + 1;
                    v113 = v3[17];
                    *(_QWORD *)(v113 + 8 * v112) = 9;
                    *(_QWORD *)(v113 + 8 * v112 + 8) = 0;
                    *(_QWORD *)(v113 + 8 * v112 + 16) = 0;
                  }
                  else
                  {
                    LODWORD(v111) = growOp3((_DWORD)v3, 9, 0, 0, 0);
                  }
                  *(_DWORD *)(v80 + 48) = v111 + 1;
                  v114 = *(_DWORD *)(v80 + 64) | 0x10;
                  *(_DWORD *)(v80 + 64) = v114;
                  if ( (v114 & 8) == 0 )
                  {
                    v110 = *((int *)v3 + 36);
                    if ( *((_DWORD *)v3 + 37) > (int)v110 )
                    {
                      v115 = 3 * v110;
                      *((_DWORD *)v3 + 36) = v110 + 1;
                      v116 = v3[17];
                      *(_QWORD *)(v116 + 8 * v115) = 15;
                      *(_QWORD *)(v116 + 8 * v115 + 8) = 0;
                      *(_QWORD *)(v116 + 8 * v115 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v110) = growOp3((_DWORD)v3, 15, 0, 0, 0);
                    }
                  }
                  HIDWORD(v536) = *(_DWORD *)(v80 + 68);
                  LOBYTE(v536) = 12;
                  v537 = 0;
                  *((_QWORD *)&v538 + 1) = 0;
                  LODWORD(v538) = 0;
                  sqlite3VdbeExplain(a1, 1, "MATERIALIZE %!S", v80);
                  v117 = v512;
                  sqlite3Select(a1, v512, &v536);
                  *(_WORD *)(*(_QWORD *)(v80 + 32) + 58LL) = *((_WORD *)v117 + 1);
                  if ( (_DWORD)v110 )
                  {
                    if ( *(_BYTE *)(*v3 + 103LL) )
                      v118 = &qword_1803DCAC0;
                    else
                      v118 = (__int64 *)(v3[17] + 24LL * (int)v110);
                    *((_DWORD *)v118 + 2) = *((_DWORD *)v3 + 36);
                  }
                  v119 = *((int *)v3 + 36);
                  v120 = v111 + 1;
                  v121 = *(_DWORD *)(v80 + 52);
                  if ( *((_DWORD *)v3 + 37) > (int)v119 )
                  {
                    *((_DWORD *)v3 + 36) = v119 + 1;
                    v122 = 3 * v119;
                    v123 = v3[17];
                    *(_DWORD *)(v123 + 8 * v122) = 67;
                    *(_DWORD *)(v123 + 8 * v122 + 4) = v121;
                    *(_DWORD *)(v123 + 8 * v122 + 8) = v120;
                    *(_DWORD *)(v123 + 8 * v122 + 12) = 0;
                    *(_QWORD *)(v123 + 8 * v122 + 16) = 0;
                  }
                  else
                  {
                    growOp3((_DWORD)v3, 67, v121, v120, 0);
                  }
                  if ( *(_BYTE *)(*v3 + 103LL) )
                    v124 = &qword_1803DCAC0;
                  else
                    v124 = (__int64 *)(v3[17] + 24LL * (int)v111);
                  v9 = a1;
                  *((_DWORD *)v124 + 2) = *((_DWORD *)v3 + 36);
                  *((_BYTE *)a1 + 31) = 0;
                  *((_DWORD *)a1 + 10) = 0;
                  if ( (*(_DWORD *)(v80 + 64) & 0x108) == 0x100 )
                  {
                    v125 = *(_QWORD *)(v80 + 96);
                    *(_DWORD *)(v125 + 4) = *(_DWORD *)(v80 + 48);
                    *(_DWORD *)(v125 + 8) = *(_DWORD *)(v80 + 52);
                    *(_DWORD *)(v125 + 12) = *(_DWORD *)(v80 + 68);
                    *(_WORD *)(v125 + 16) = *((_WORD *)v117 + 1);
                  }
                }
              }
LABEL_198:
              if ( *(_BYTE *)(v502 + 103) )
                goto LABEL_746;
              v8 = a2;
              v508 = 0;
              heightOfSelect(a2, &v508);
              v38 = v500;
              *((_DWORD *)v9 + 77) -= v508;
              v9[46] = v68;
              v41 = v498;
              goto LABEL_201;
            }
LABEL_138:
            if ( (v500[17] & 0x40) != 0 || (*(_DWORD *)(*v66 + 96LL) & 0x2000000) != 0 )
              goto LABEL_154;
            v73 = *v500;
            if ( !isSelfJoinView(v500, v69 + 2, (unsigned int)(v498 + 1), (unsigned int)*v500) )
            {
              if ( !v503 )
              {
                if ( v73 == 1 || (v67 = v500, (v500[43] & 2) != 0) || (v70 & 0x10000000) == 0 )
                {
LABEL_145:
                  v74 = *((int *)v3 + 36);
                  v75 = v523;
                  v76 = v74 + 1;
                  v77 = *((_DWORD *)a1 + 14) + 1;
                  *((_DWORD *)a1 + 14) = v77;
                  *(_DWORD *)(v75 + 52) = v77;
                  v78 = *((int *)v3 + 36);
                  if ( *((_DWORD *)v3 + 37) > (int)v78 )
                  {
                    *((_DWORD *)v3 + 36) = v78 + 1;
                    v85 = 3 * v78;
                    v86 = v3[17];
                    *(_DWORD *)(v86 + 8 * v85) = 11;
                    *(_DWORD *)(v86 + 8 * v85 + 4) = v77;
                    *(_DWORD *)(v86 + 8 * v85 + 8) = 0;
                    *(_DWORD *)(v86 + 8 * v85 + 12) = v76;
                    *(_QWORD *)(v86 + 8 * v85 + 16) = 0;
                  }
                  else
                  {
                    growOp3((_DWORD)v3, 11, v77, 0, v74 + 1);
                  }
                  HIDWORD(v536) = *(_DWORD *)(v75 + 52);
                  *(_DWORD *)(v75 + 48) = v76;
                  LOBYTE(v536) = 13;
                  v537 = 0;
                  *((_QWORD *)&v538 + 1) = 0;
                  LODWORD(v538) = 0;
                  sqlite3VdbeExplain(a1, 1, "CO-ROUTINE %!S", v75);
                  v87 = v512;
                  sqlite3Select(a1, v512, &v536);
                  *(_WORD *)(*(_QWORD *)(v75 + 32) + 58LL) = *((_WORD *)v87 + 1);
                  v88 = HIDWORD(v537);
                  v89 = *(unsigned int *)(v75 + 52);
                  *(_DWORD *)(v75 + 64) |= 0x20u;
                  *(_DWORD *)(v75 + 56) = v88;
                  sqlite3VdbeEndCoroutine(v3, v89);
                  if ( *(_BYTE *)(*v3 + 103LL) )
                  {
                    v9 = a1;
                    dword_1803DCAC8 = *((_DWORD *)v3 + 36);
                  }
                  else
                  {
                    v90 = 3 * v74;
                    v9 = a1;
                    *(_DWORD *)(v3[17] + 8 * v90 + 8) = *((_DWORD *)v3 + 36);
                  }
                  *((_BYTE *)a1 + 31) = 0;
                  *((_DWORD *)v9 + 10) = 0;
                  goto LABEL_198;
                }
LABEL_153:
                v41 = v498;
                goto LABEL_154;
              }
              if ( (v70 & 0x10000000) == 0 )
              {
                v79 = v69 + 17;
                if ( (v69[17] & 0x22) == 0 )
                {
                  while ( v65 )
                  {
                    v79 -= 104;
                    --v65;
                    if ( *(_QWORD *)(v79 - 20) || (*v79 & 0x22) != 0 )
                      goto LABEL_152;
                  }
                  goto LABEL_145;
                }
              }
            }
LABEL_152:
            v67 = v500;
            goto LABEL_153;
          }
LABEL_202:
          v126 = *(_DWORD *)(v8 + 4);
          v127 = *(char **)(v8 + 32);
          v128 = v126 & 1;
          v129 = *(_QWORD *)(v8 + 48);
          v504 = *(_DWORD **)(v8 + 56);
          v523 = *(_QWORD *)(v8 + 64);
          v512 = v127;
          v520 = v129;
          v507 = v126 & 1;
          v524 = v126 & 1;
          if ( (v126 & 9) != 1 )
            goto LABEL_216;
          if ( !v509 )
          {
            if ( !v127 )
              goto LABEL_214;
            goto LABEL_216;
          }
          v130 = v505;
          if ( v127 && *v505 == *(_DWORD *)v127 )
          {
            v131 = 0;
            if ( *v505 > 0 )
            {
              v132 = v509 + 6;
              v133 = v127 - (char *)v509;
              do
              {
                if ( *v132 != v132[v133]
                  || (unsigned int)sqlite3ExprCompare(
                                     0,
                                     *((_QWORD *)v132 - 2),
                                     *(_QWORD *)&v132[v133 - 16],
                                     0xFFFFFFFFLL) )
                {
                  goto LABEL_216;
                }
                ++v131;
                v132 += 32;
              }
              while ( v131 < *v509 );
              v8 = a2;
              v127 = v512;
              v126 = *(_DWORD *)(a2 + 4);
            }
LABEL_214:
            if ( !*(_QWORD *)(v8 + 112) )
            {
              *(_DWORD *)(v8 + 4) = v126 & 0xFFFFFFFE;
              v134 = sqlite3ExprListDup(v502, v127, 0);
              *(_DWORD *)(v8 + 4) |= 8u;
              v128 = 2;
              v507 = 2;
              v524 = 2;
              v504 = (_DWORD *)v134;
              *(_QWORD *)(v8 + 56) = v134;
            }
LABEL_216:
            v130 = v505;
          }
          v135 = v512;
          if ( v509 )
          {
            v136 = sqlite3KeyInfoFromExprList(a1, v509, 0, *(unsigned int *)v512);
            v137 = *((_DWORD *)a1 + 13);
            HIDWORD(v533) = v137;
            *((_DWORD *)a1 + 13) = v137 + 1;
            v138 = sqlite3VdbeAddOp4((_DWORD)v3, 118, v137, *v130 + *(_DWORD *)v135 + 1, 0, v136, -8);
            DWORD2(v534) = v138;
          }
          else
          {
            v138 = -1;
            DWORD2(v534) = -1;
          }
          if ( *(_BYTE *)v516 == 12 )
          {
            sqlite3VdbeAddOp2(v3, 118, *(unsigned int *)(v516 + 4), *(unsigned int *)v135);
            if ( (*(_DWORD *)(a2 + 4) & 0x800) != 0 )
            {
              v139 = (int *)v512;
              v140 = *(_DWORD *)v512;
              v141 = *(_DWORD *)v512 - 1;
              if ( *(_DWORD *)v512 - 1 > 0 )
              {
                v142 = 8LL * (*(_DWORD *)v512 - 1);
                do
                {
                  if ( (v139[v142 + 7] & 0x40) != 0 )
                    break;
                  v143 = *(_QWORD *)&v139[v142 + 2];
                  if ( v143 )
                  {
                    sqlite3ExprDeleteNN(v502, v143);
                    v139 = (int *)v512;
                  }
                  if ( *(_QWORD *)&v139[v142 + 4] )
                  {
                    sqlite3DbFreeNN(v502);
                    v139 = (int *)v512;
                  }
                  --*v139;
                  --v141;
                  v140 = *v139;
                  v142 -= 8;
                }
                while ( v141 > 0 );
                LODWORD(v129) = v520;
              }
              v144 = 0;
              if ( v140 > 0 )
              {
                v145 = v139 + 2;
                do
                {
                  if ( (v145[5] & 0x40) == 0 )
                    **(_BYTE **)v145 = 121;
                  ++v144;
                  v145 += 8;
                }
                while ( v144 < *v139 );
              }
            }
          }
          v146 = a1;
          v147 = a2;
          v148 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v148;
          v531 = v148;
          if ( (*(_DWORD *)(a2 + 4) & 0x4000) == 0 )
            *(_WORD *)(a2 + 2) = 320;
          if ( *(_QWORD *)(a2 + 96) )
          {
            computeLimitRegisters(a1, a2, v148);
            v146 = a1;
            v147 = a2;
          }
          if ( !*(_DWORD *)(v147 + 8) && v138 >= 0 )
          {
            if ( *(_BYTE *)(*v3 + 103LL) )
              v149 = &qword_1803DCAC0;
            else
              v149 = (__int64 *)(v3[17] + 24LL * v138);
            BYTE4(v535) |= 1u;
            *(_BYTE *)v149 = 119;
          }
          if ( (*(_BYTE *)(v147 + 4) & 1) != 0 )
          {
            v150 = *((_DWORD *)v146 + 13);
            v526 = v150;
            *((_DWORD *)v146 + 13) = v150 + 1;
            v151 = sqlite3KeyInfoFromExprList(v146, *(_QWORD *)(v147 + 32), 0, 0);
            v152 = *((int *)v3 + 36);
            v153 = v151;
            if ( *((_DWORD *)v3 + 37) > (int)v152 )
            {
              v154 = 3 * v152;
              *((_DWORD *)v3 + 36) = v152 + 1;
              v155 = v3[17];
              *(_DWORD *)(v155 + 8 * v154) = 118;
              *(_DWORD *)(v155 + 8 * v154 + 4) = v150;
              *(_QWORD *)(v155 + 8 * v154 + 8) = 0;
              *(_QWORD *)(v155 + 8 * v154 + 16) = 0;
            }
            else
            {
              LODWORD(v152) = growOp3((_DWORD)v3, 118, v150, 0, 0);
            }
            v156 = v152;
            if ( *(_BYTE *)(*v3 + 103LL) )
            {
              if ( !*(_QWORD *)(*v3 + 760LL) )
              {
                if ( v153 )
                {
                  v157 = (*(_DWORD *)v153)-- == 1;
                  if ( v157 )
                    sqlite3DbNNFreeNN(*(_QWORD *)(v153 + 16), v153);
                }
              }
            }
            else
            {
              if ( (int)v152 < 0 )
              {
                _mm_lfence();
                v156 = *((_DWORD *)v3 + 36) - 1;
              }
              v158 = v3[17] + 24LL * v156;
              if ( *(_BYTE *)(v158 + 1) )
              {
                vdbeChangeP4Full(v3, v158, v153, 4294967288LL);
              }
              else if ( v153 )
              {
                *(_QWORD *)(v158 + 16) = v153;
                *(_BYTE *)(v158 + 1) = -8;
              }
            }
            v159 = *((int *)v3 + 36);
            v527 = v152;
            if ( (int)v159 > 0 )
              *(_WORD *)(v3[17] + 24 * v159 - 22) = 8;
            v147 = a2;
            v525 = 3;
          }
          else
          {
            v525 = 0;
          }
          if ( !v519 && !v504 )
          {
            v160 = *(_QWORD *)(v147 + 112);
            v161 = (v128 != 0 ? 0x100 : 0) | *(_WORD *)(v147 + 4) & 0x4000;
            if ( v160 )
            {
              sqlite3WindowCodeInit(a1, v147);
              v147 = a2;
            }
            v162 = v509;
            v163 = sqlite3WhereBegin(
                     (_DWORD)a1,
                     (_DWORD)v500,
                     v129,
                     (_DWORD)v509,
                     *(_QWORD *)(v147 + 32),
                     v147,
                     v161,
                     *(__int16 *)(v147 + 2));
            v165 = v163;
            if ( v163 )
            {
              v166 = a2;
              v167 = *(_WORD *)(v163 + 72);
              if ( v167 < *(__int16 *)(a2 + 2) )
                *(_WORD *)(a2 + 2) = v167;
              if ( v128 )
              {
                v168 = v525;
                if ( *(_BYTE *)(v165 + 67) )
                  v168 = *(_BYTE *)(v165 + 67);
                v525 = v168;
              }
              if ( v162 )
              {
                v169 = 0;
                if ( *(char *)(v165 + 65) >= 0 )
                  v169 = *(char *)(v165 + 65);
                v157 = (*(_BYTE *)(v165 + 68) & 4) == 0;
                DWORD2(v533) = v169;
                if ( v157 )
                {
                  v170 = *(_DWORD *)(v165 + 48);
                }
                else
                {
                  v171 = *(unsigned __int8 *)(v165 + 64);
                  if ( *(_QWORD *)(112 * v171 + v165 + 808) )
                    v170 = *(_DWORD *)(v165 + 48);
                  else
                    v170 = *(_DWORD *)(112 * v171 + v165 + 768);
                }
                LODWORD(v535) = v170;
                if ( v169 == *v505 )
                  v162 = 0;
                *(_QWORD *)&v533 = v162;
              }
              if ( (SDWORD2(v534) & 0x80000000) == 0 && !v162 )
              {
                sqlite3VdbeChangeToNoop(v3, DWORD2(v534), v164);
                v166 = a2;
              }
              if ( !v160 )
              {
                v181 = v516;
                v9 = a1;
                selectInnerLoop(
                  (_DWORD)a1,
                  v166,
                  -1,
                  (unsigned int)&v533,
                  (__int64)&v524,
                  v516,
                  *(_DWORD *)(v165 + 48),
                  *(_DWORD *)(v165 + 52));
                sqlite3WhereEnd(v165);
                v182 = a2;
                goto LABEL_737;
              }
              v173 = *((_DWORD *)a1 + 14) + 1;
              v172 = *((_DWORD *)a1 + 17) - 1;
              *((_DWORD *)a1 + 14) = v173;
              v174 = v172 - 1;
              v175 = v172 - 2;
              *((_DWORD *)a1 + 17) = v172 - 2;
              sqlite3WindowCodeStep((_DWORD)a1, v166, v165, v173, v172);
              v176 = *((int *)v3 + 36);
              if ( *((_DWORD *)v3 + 37) > (int)v176 )
              {
                *((_DWORD *)v3 + 36) = v176 + 1;
                v177 = 3 * v176;
                v178 = v3[17];
                *(_QWORD *)(v178 + 8 * v177) = 9;
                *(_DWORD *)(v178 + 8 * v177 + 8) = v175;
                *(_DWORD *)(v178 + 8 * v177 + 12) = 0;
                *(_QWORD *)(v178 + 8 * v177 + 16) = 0;
              }
              else
              {
                growOp3((_DWORD)v3, 9, 0, v175, 0);
              }
              v179 = v3[3];
              v180 = ~v172;
              if ( *(_DWORD *)(v179 + 68) + *(_DWORD *)(v179 + 72) >= 0 )
                *(_DWORD *)(*(_QWORD *)(v179 + 80) + 4LL * v180) = *((_DWORD *)v3 + 36);
              else
                resizeResolveLabel(v179, v3, (unsigned int)v180);
              v181 = v516;
              v182 = a2;
              LODWORD(v535) = 0;
              selectInnerLoop((_DWORD)a1, a2, -1, (unsigned int)&v533, (__int64)&v524, v516, v174, v175);
              v183 = v3[3];
              v184 = ~v174;
              if ( *(_DWORD *)(v183 + 68) + *(_DWORD *)(v183 + 72) >= 0 )
                *(_DWORD *)(*(_QWORD *)(v183 + 80) + 4LL * v184) = *((_DWORD *)v3 + 36);
              else
                resizeResolveLabel(v183, v3, (unsigned int)v184);
              sqlite3VdbeAddOp1(v3, 67, v173);
              v185 = v3[3];
              v186 = ~v175;
              if ( *(_DWORD *)(v185 + 68) + *(_DWORD *)(v185 + 72) < 0 )
              {
                resizeResolveLabel(v185, v3, (unsigned int)v186);
                v9 = a1;
                goto LABEL_737;
              }
              v187 = v186;
              v9 = a1;
              goto LABEL_736;
            }
            v9 = a1;
            goto LABEL_746;
          }
          v188 = v504;
          v189 = 0;
          v513 = 0;
          v515 = 0;
          if ( v504 )
          {
            v190 = *(_DWORD **)(v147 + 32);
            v191 = *v190;
            if ( (int)*v190 > 0 )
            {
              v192 = (_WORD *)v190 + 17;
              do
              {
                --v191;
                *v192 = 0;
                v192 += 16;
              }
              while ( v191 > 0 );
            }
            v193 = *v504;
            if ( (int)*v504 > 0 )
            {
              v194 = (_WORD *)v504 + 17;
              do
              {
                --v193;
                *v194 = 0;
                v194 += 16;
              }
              while ( v193 > 0 );
            }
            if ( *(__int16 *)(v147 + 2) > 66 )
              *(_WORD *)(v147 + 2) = 66;
            v195 = (char *)v509;
            if ( v509 )
            {
              v196 = *v504;
              if ( *v504 == *v505 )
              {
                v197 = 0;
                if ( v196 > 0 )
                {
                  v198 = v504 + 6;
                  v199 = (char *)v509 - (char *)v504;
                  do
                  {
                    v200 = *((_BYTE *)v198 + v199);
                    v198 += 8;
                    ++v197;
                    *((_BYTE *)v198 - 32) = v200 & 1;
                    v196 = *v504;
                  }
                  while ( v197 < *v504 );
                  v195 = (char *)v509;
                }
                if ( v196 == *v505 )
                {
                  v201 = 0;
                  if ( v196 <= 0 )
                  {
LABEL_325:
                    v515 = 1;
                  }
                  else
                  {
                    v202 = v504 + 6;
                    v203 = v195 - (char *)v504;
                    while ( *v202 == v202[v203]
                         && !(unsigned int)sqlite3ExprCompare(
                                             0,
                                             *((_QWORD *)v202 - 2),
                                             *(_QWORD *)&v202[v203 - 16],
                                             0xFFFFFFFFLL) )
                    {
                      ++v201;
                      v202 += 32;
                      if ( v201 >= *v504 )
                        goto LABEL_325;
                    }
                  }
                }
              }
            }
          }
          else
          {
            *(_WORD *)(v147 + 2) = 0;
          }
          v9 = a1;
          v510 = *((_DWORD *)a1 + 17) - 1;
          *((_DWORD *)a1 + 17) = v510;
          v506 = sqlite3DbMallocRawNN(v502, 56);
          v204 = v506;
          if ( v506 )
          {
            *(_OWORD *)v506 = 0;
            *(_OWORD *)(v506 + 16) = 0;
            *(_OWORD *)(v506 + 32) = 0;
            *(_QWORD *)(v506 + 48) = 0;
            if ( qword_180337B50 )
            {
              v205 = qword_180337B50(300);
              v206 = *a1;
              if ( v205 )
              {
                sqlite3OomFault(v206);
                goto LABEL_331;
              }
            }
            else
            {
              v206 = *a1;
            }
            if ( v206 )
              v209 = (_QWORD *)sqlite3DbMallocRawNN(v206, 24);
            else
              v209 = (_QWORD *)sqlite3Malloc(24);
            if ( v209 )
            {
              *v209 = a1[24];
              a1[24] = v209;
              v209[2] = agginfoFree;
              v209[1] = v506;
            }
            else
            {
LABEL_331:
              v207 = *a1;
              if ( *(_QWORD *)(v506 + 24) )
                sqlite3DbFreeNN(*a1);
              if ( *(_QWORD *)(v506 + 40) )
                sqlite3DbFreeNN(v207);
              sqlite3DbFreeNN(v207);
            }
          }
          if ( !*(_BYTE *)(v502 + 103) )
          {
            *(_DWORD *)(v506 + 52) = *(_DWORD *)(a2 + 16);
            v540[1] = v500;
            v540[0] = a1;
            v540[2] = v506;
            v541 = 0;
            v542 = 0;
            if ( v504 )
              v208 = *v504;
            else
              LOWORD(v208) = 0;
            *(_WORD *)(v506 + 2) = v208;
            v210 = v512;
            *(_QWORD *)(v506 + 16) = v504;
            if ( v210 )
            {
              v211 = (__int64 *)(v210 + 8);
              v212 = 0;
              if ( *(int *)v210 > 0 )
              {
                do
                {
                  v213 = *v211;
                  v537 = analyzeAggregate;
                  *(_QWORD *)&v538 = sqlite3WalkerDepthIncrease;
                  *((_QWORD *)&v538 + 1) = sqlite3WalkerDepthDecrease;
                  LODWORD(v539) = 0;
                  *((_QWORD *)&v539 + 1) = v540;
                  v536 = 0;
                  if ( v213 )
                  {
                    sqlite3WalkExprNN(&v536);
                    v210 = v512;
                  }
                  ++v212;
                  v211 += 4;
                }
                while ( v212 < *(_DWORD *)v210 );
                v3 = v528;
                v204 = v506;
                v188 = v504;
              }
            }
            v214 = v509;
            if ( v509 )
            {
              v215 = (__int64 *)(v509 + 2);
              v216 = 0;
              if ( (int)*v509 > 0 )
              {
                do
                {
                  v217 = *v215;
                  v537 = analyzeAggregate;
                  *(_QWORD *)&v538 = sqlite3WalkerDepthIncrease;
                  *((_QWORD *)&v538 + 1) = sqlite3WalkerDepthDecrease;
                  LODWORD(v539) = 0;
                  *((_QWORD *)&v539 + 1) = v540;
                  v536 = 0;
                  if ( v217 )
                  {
                    sqlite3WalkExprNN(&v536);
                    v214 = v509;
                  }
                  ++v216;
                  v215 += 4;
                }
                while ( v216 < *v214 );
                v3 = v528;
                v204 = v506;
                v188 = v504;
              }
            }
            if ( v523 )
            {
              if ( v188 )
              {
                v536 = a1;
                v538 = 0;
                v218 = *(_QWORD *)(a2 + 64);
                *(_QWORD *)&v539 = 0;
                v537 = havingToWhereExprCb;
                *((_QWORD *)&v539 + 1) = a2;
                if ( v218 )
                  sqlite3WalkExprNN(&v536);
                v520 = *(_QWORD *)(a2 + 48);
              }
              LODWORD(v539) = 0;
              v537 = analyzeAggregate;
              v536 = 0;
              *(_QWORD *)&v538 = sqlite3WalkerDepthIncrease;
              *((_QWORD *)&v538 + 1) = sqlite3WalkerDepthDecrease;
              *((_QWORD *)&v539 + 1) = v540;
              sqlite3WalkExprNN(&v536);
            }
            v219 = (_QWORD *)a2;
            *(_DWORD *)(v204 + 36) = *(_DWORD *)(v204 + 32);
            if ( *(_QWORD *)(a2 + 56)
              || *(_QWORD *)(a2 + 64)
              || *(_DWORD *)(v204 + 48) != 1
              || (v220 = *(__int64 **)(v204 + 40), v221 = *v220, (v222 = *(_QWORD *)(*v220 + 32)) == 0)
              || *(_DWORD *)v222 != 1
              || (*(_DWORD *)(v221 + 4) & 0x1000000) != 0
              || (*(_DWORD *)(v502 + 96) & 0x10000) != 0 )
            {
LABEL_386:
              v227 = 0;
              goto LABEL_387;
            }
            v223 = *(char **)(v221 + 8);
            for ( i = v223; ; ++i )
            {
              v225 = (unsigned __int8)*i;
              v226 = (unsigned __int8)i["min" - v223];
              if ( (_BYTE)v225 == (_BYTE)v226 )
              {
                if ( !(_BYTE)v225 )
                {
                  v227 = 1;
                  v228 = (unsigned int)sqlite3ExprCanBeNull(*(_QWORD *)(v222 + 8)) != 0 ? 2 : 0;
                  goto LABEL_381;
                }
              }
              else if ( *((unsigned __int8 *)qword_18026E880 + v225) != *((unsigned __int8 *)qword_18026E880 + v226) )
              {
                v229 = (char *)("max" - v223);
                while ( 1 )
                {
                  v230 = (unsigned __int8)*v223;
                  v231 = (unsigned __int8)v223[(_QWORD)v229];
                  if ( (_BYTE)v230 == (_BYTE)v231 )
                  {
                    if ( !(_BYTE)v230 )
                    {
                      v228 = 1;
                      v227 = 2;
LABEL_381:
                      v232 = sqlite3ExprListDup(v502, v222, 0);
                      v532 = v232;
                      if ( v232 )
                        *(_BYTE *)(v232 + 24) = v228;
                      v219 = (_QWORD *)a2;
LABEL_387:
                      analyzeAggFuncArgs(v204, v540);
                      v233 = v502;
                      if ( !*(_BYTE *)(v502 + 103) )
                      {
                        if ( v504 )
                        {
                          v157 = *(_DWORD *)(v204 + 48) == 1;
                          appended = 0;
                          v530 = 0;
                          v499 = 0;
                          if ( v157 )
                          {
                            v235 = *(int **)(v204 + 40);
                            if ( v235[4] >= 0 )
                            {
                              v236 = *(_QWORD *)v235;
                              if ( v236 )
                              {
                                if ( (*(_DWORD *)(v236 + 4) & 0x1000) == 0 )
                                {
                                  v237 = *(_QWORD *)(v236 + 32);
                                  if ( v237 )
                                  {
                                    v238 = *(_QWORD *)(v237 + 8);
                                    if ( v238 )
                                    {
                                      v239 = exprDup(v502, v238, 0, 0);
                                      v233 = v502;
                                      v240 = v239;
                                    }
                                    else
                                    {
                                      v240 = 0;
                                    }
                                    v241 = (int *)sqlite3ExprListDup(v233, v504, 0);
                                    v530 = v241;
                                    appended = v241;
                                    if ( v241 )
                                    {
                                      v242 = *v241;
                                      v243 = v242 + 1;
                                      if ( appended[1] >= (int)v242 + 1 )
                                      {
                                        v244 = 8 * v242;
                                        *appended = v243;
                                        *(_OWORD *)&appended[v244 + 2] = xmmword_18026F3D0;
                                        *(_OWORD *)&appended[v244 + 6] = xmmword_18026F3E0;
                                        *(_QWORD *)&appended[v244 + 2] = v240;
                                      }
                                      else
                                      {
                                        appended = (int *)sqlite3ExprListAppendGrow(*a1, appended, v240);
                                        v530 = appended;
                                      }
                                    }
                                    else
                                    {
                                      appended = (int *)sqlite3ExprListAppendNew(*a1, v240);
                                      v530 = appended;
                                    }
                                    v499 = appended != 0 ? 0x500 : 0;
                                  }
                                }
                              }
                            }
                          }
                          *(_DWORD *)(v204 + 4) = (*((_DWORD *)a1 + 13))++;
                          v245 = sqlite3KeyInfoFromExprList(a1, v504, 0, *(unsigned int *)(v204 + 32));
                          v246 = *((int *)v3 + 36);
                          v247 = v245;
                          v248 = *(unsigned __int16 *)(v204 + 2);
                          v249 = *(_DWORD *)(v204 + 4);
                          v529 = v245;
                          LODWORD(v509) = v246;
                          if ( *((_DWORD *)v3 + 37) > (int)v246 )
                          {
                            v250 = 3 * v246;
                            *((_DWORD *)v3 + 36) = v246 + 1;
                            v251 = v3[17];
                            *(_DWORD *)(v251 + 8 * v250) = 119;
                            *(_DWORD *)(v251 + 8 * v250 + 4) = v249;
                            *(_DWORD *)(v251 + 8 * v250 + 8) = v248;
                            *(_DWORD *)(v251 + 8 * v250 + 12) = 0;
                            *(_QWORD *)(v251 + 8 * v250 + 16) = 0;
                          }
                          else
                          {
                            LODWORD(v246) = growOp3((_DWORD)v3, 119, v249, v248, 0);
                            LODWORD(v509) = v246;
                          }
                          v252 = v246;
                          if ( *(_BYTE *)(*v3 + 103LL) )
                          {
                            if ( !*(_QWORD *)(*v3 + 760LL) )
                            {
                              if ( v247 )
                              {
                                v157 = (*(_DWORD *)v247)-- == 1;
                                if ( v157 )
                                  sqlite3DbNNFreeNN(*(_QWORD *)(v247 + 16), v247);
                              }
                            }
                          }
                          else
                          {
                            if ( (int)v246 < 0 )
                            {
                              _mm_lfence();
                              v252 = *((_DWORD *)v3 + 36) - 1;
                            }
                            v253 = v3[17] + 24LL * v252;
                            if ( *(_BYTE *)(v253 + 1) )
                            {
                              vdbeChangeP4Full(v3, v253, v247, 4294967288LL);
                            }
                            else if ( v247 )
                            {
                              *(_QWORD *)(v253 + 16) = v247;
                              *(_BYTE *)(v253 + 1) = -8;
                            }
                          }
                          v254 = v504;
                          v522 = *((_DWORD *)a1 + 14) + 1;
                          v255 = v522 + 1;
                          v256 = *((_DWORD *)a1 + 17) - 1;
                          v514 = v522 + 1;
                          v257 = v522 + 3;
                          v517 = v256;
                          *((_DWORD *)a1 + 14) = v522 + 3;
                          v258 = v257 + 1;
                          v519 = v257;
                          v259 = v256 - 1;
                          v521 = v257 + 1;
                          *((_DWORD *)a1 + 17) = v256 - 1;
                          v260 = v257 + *v504;
                          v508 = v256 - 1;
                          *((_DWORD *)a1 + 14) = v260;
                          v261 = v260 + 1;
                          *((_DWORD *)a1 + 14) = *v504 + v260;
                          v262 = *((int *)v3 + 36);
                          v518 = v261;
                          if ( *((_DWORD *)v3 + 37) > (int)v262 )
                          {
                            *((_DWORD *)v3 + 36) = v262 + 1;
                            v263 = 3 * v262;
                            v264 = v3[17];
                            *(_QWORD *)(v264 + 8 * v263) = 71;
                            *(_DWORD *)(v264 + 8 * v263 + 8) = v255;
                            *(_DWORD *)(v264 + 8 * v263 + 12) = 0;
                            *(_QWORD *)(v264 + 8 * v263 + 16) = 0;
                          }
                          else
                          {
                            growOp3((_DWORD)v3, 71, 0, v255, 0);
                            v258 = v521;
                            v254 = v504;
                          }
                          v265 = *((int *)v3 + 36);
                          v266 = v257 + *v254;
                          if ( *((_DWORD *)v3 + 37) > (int)v265 )
                          {
                            *((_DWORD *)v3 + 36) = v265 + 1;
                            v267 = 3 * v265;
                            v268 = v3[17];
                            *(_QWORD *)(v268 + 8 * v267) = 75;
                            *(_DWORD *)(v268 + 8 * v267 + 8) = v258;
                            *(_DWORD *)(v268 + 8 * v267 + 12) = v266;
                            *(_QWORD *)(v268 + 8 * v267 + 16) = 0;
                          }
                          else
                          {
                            growOp3((_DWORD)v3, 75, 0, v258, v266);
                          }
                          v269 = *((int *)v3 + 36);
                          if ( *((_DWORD *)v3 + 37) > (int)v269 )
                          {
                            *((_DWORD *)v3 + 36) = v269 + 1;
                            v270 = 3 * v269;
                            v271 = v3[17];
                            *(_DWORD *)(v271 + 8 * v270) = 10;
                            *(_DWORD *)(v271 + 8 * v270 + 4) = v257;
                            *(_DWORD *)(v271 + 8 * v270 + 8) = v259;
                            *(_DWORD *)(v271 + 8 * v270 + 12) = 0;
                            *(_QWORD *)(v271 + 8 * v270 + 16) = 0;
                          }
                          else
                          {
                            growOp3((_DWORD)v3, 10, v257, v259, 0);
                          }
                          v272 = 64;
                          if ( v507 == 2 )
                            v272 = 128;
                          v520 = sqlite3WhereBegin(
                                   (_DWORD)a1,
                                   (_DWORD)v500,
                                   v520,
                                   (_DWORD)v504,
                                   (__int64)appended,
                                   a2,
                                   v499 | (unsigned __int16)(v272 | (v515 != 0 ? 0x200 : 0)),
                                   0);
                          v274 = v520;
                          if ( !v520 )
                          {
                            if ( appended )
                              exprListDeleteNN(v502);
                            goto LABEL_431;
                          }
                          if ( a1[12] )
                          {
                            v275 = *(unsigned int *)(v204 + 36);
                            *(_DWORD *)(v204 + 32) = v275;
                            if ( *(_WORD *)(v204 + 2) )
                            {
                              v276 = **(_DWORD **)(a2 + 56) - 1;
                              if ( (int)v275 > 0 )
                              {
                                v277 = (__int16 *)(*(_QWORD *)(v204 + 24) + 22LL);
                                do
                                {
                                  v278 = *v277;
                                  v277 += 12;
                                  if ( v278 <= v276 )
                                    v278 = v276;
                                  v276 = v278;
                                  --v275;
                                }
                                while ( v275 );
                              }
                              *(_WORD *)(v204 + 2) = v276 + 1;
                            }
                            analyzeAggFuncArgs(v204, v540);
                          }
                          v279 = 0;
                          *(_DWORD *)(v204 + 12) = *((_DWORD *)a1 + 14) + 1;
                          *((_DWORD *)a1 + 14) += *(_DWORD *)(v204 + 32) + *(_DWORD *)(v204 + 48);
                          if ( *(char *)(v274 + 65) >= 0 )
                            v279 = *(char *)(v274 + 65);
                          v511 = *(unsigned __int8 *)(v274 + 67);
                          if ( v279 == *v504 )
                          {
                            v280 = a1;
                            v281 = 0;
                            v501 = 0;
                          }
                          else
                          {
                            if ( !v507 || (v282 = "DISTINCT", (*(_BYTE *)(a2 + 4) & 1) != 0) )
                              v282 = "GROUP BY";
                            sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v282);
                            v283 = *v504;
                            v284 = *v504;
                            v285 = *(_DWORD *)(v204 + 32);
                            v286 = *v504;
                            v501 = 1;
                            if ( v285 > 0 )
                            {
                              v287 = (unsigned int)v285;
                              v288 = (__int16 *)(*(_QWORD *)(v204 + 24) + 22LL);
                              do
                              {
                                v289 = *v288;
                                v290 = v284 + 1;
                                v288 += 12;
                                if ( v289 < v286 )
                                  v290 = v284;
                                v284 = v290;
                                v291 = v286 + 1;
                                if ( v289 < v286 )
                                  v291 = v286;
                                v286 = v291;
                                --v287;
                              }
                              while ( v287 );
                            }
                            if ( v284 == 1 )
                            {
                              v292 = *((_BYTE *)a1 + 31);
                              if ( v292 )
                              {
                                v294 = v292 - 1;
                                *((_BYTE *)a1 + 31) = v294;
                                v293 = *((_DWORD *)a1 + v294 + 56);
                              }
                              else
                              {
                                v293 = *((_DWORD *)a1 + 14) + 1;
                                *((_DWORD *)a1 + 14) = v293;
                              }
                            }
                            else
                            {
                              v295 = *((_DWORD *)a1 + 10);
                              v293 = *((_DWORD *)a1 + 11);
                              if ( v284 > v295 )
                              {
                                v296 = *((_DWORD *)a1 + 14);
                                v293 = v296 + 1;
                                *((_DWORD *)a1 + 14) = v284 + v296;
                              }
                              else
                              {
                                *((_DWORD *)a1 + 11) = v284 + v293;
                                *((_DWORD *)a1 + 10) = v295 - v284;
                              }
                            }
                            v280 = a1;
                            sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v504, v293, 0, 0);
                            v298 = v506;
                            *(_BYTE *)v204 = 1;
                            v299 = 0;
                            v300 = 0;
                            if ( *(int *)(v506 + 32) > 0 )
                            {
                              v301 = v283 + v293;
                              do
                              {
                                v302 = *(_QWORD *)(v298 + 24);
                                if ( *(__int16 *)(v302 + v299 + 22) >= (int)(v301 - v293) )
                                {
                                  if ( a1[2] )
                                  {
                                    v303 = *(_QWORD *)(v302 + v299 + 8);
                                    v304 = sqlite3ExprCodeTarget(a1, v303, v301, v297);
                                    if ( v304 != v301 )
                                    {
                                      if ( !v303 )
                                        goto LABEL_477;
                                      while ( 1 )
                                      {
                                        v305 = *(_DWORD *)(v303 + 4);
                                        if ( (v305 & 0x82000) == 0 )
                                          break;
                                        if ( (v305 & 0x80000) != 0 )
                                        {
                                          v303 = *(_QWORD *)(*(_QWORD *)(v303 + 32) + 8LL);
                                        }
                                        else
                                        {
                                          if ( *(_BYTE *)v303 != 113 )
                                            break;
                                          v303 = *(_QWORD *)(v303 + 16);
                                        }
                                        if ( !v303 )
                                          goto LABEL_477;
                                      }
                                      if ( (v305 & 0x400000) != 0 || *(_BYTE *)v303 == 0xB0 )
                                        v306 = 80;
                                      else
LABEL_477:
                                        v306 = 81;
                                      sqlite3VdbeAddOp2(a1[2], v306, v304, v301);
                                    }
                                    v298 = v506;
                                  }
                                  ++v301;
                                }
                                ++v300;
                                v299 += 24;
                              }
                              while ( v300 < *(_DWORD *)(v298 + 32) );
                              v3 = v528;
                              v280 = a1;
                            }
                            *(_BYTE *)v298 = 0;
                            v307 = *((_BYTE *)v280 + 31);
                            if ( v307 )
                            {
                              v309 = v307 - 1;
                              *((_BYTE *)v280 + 31) = v309;
                              v308 = *((_DWORD *)v280 + v309 + 56);
                            }
                            else
                            {
                              v308 = *((_DWORD *)v280 + 14) + 1;
                              *((_DWORD *)v280 + 14) = v308;
                            }
                            v310 = *((int *)v3 + 36);
                            if ( *((_DWORD *)v3 + 37) > (int)v310 )
                            {
                              *((_DWORD *)v3 + 36) = v310 + 1;
                              v311 = 3 * v310;
                              v312 = v3[17];
                              *(_DWORD *)(v312 + 8 * v311) = 97;
                              *(_DWORD *)(v312 + 8 * v311 + 4) = v293;
                              *(_DWORD *)(v312 + 8 * v311 + 8) = v284;
                              *(_DWORD *)(v312 + 8 * v311 + 12) = v308;
                              *(_QWORD *)(v312 + 8 * v311 + 16) = 0;
                            }
                            else
                            {
                              growOp3((_DWORD)v3, 97, v293, v284, v308);
                              v298 = v506;
                            }
                            v313 = *((int *)v3 + 36);
                            v314 = *(_DWORD *)(v298 + 4);
                            if ( *((_DWORD *)v3 + 37) > (int)v313 )
                            {
                              *((_DWORD *)v3 + 36) = v313 + 1;
                              v315 = 3 * v313;
                              v316 = v3[17];
                              *(_DWORD *)(v316 + 8 * v315) = 139;
                              *(_DWORD *)(v316 + 8 * v315 + 4) = v314;
                              *(_DWORD *)(v316 + 8 * v315 + 8) = v308;
                              *(_DWORD *)(v316 + 8 * v315 + 12) = 0;
                              *(_QWORD *)(v316 + 8 * v315 + 16) = 0;
                            }
                            else
                            {
                              growOp3((_DWORD)v3, 139, v314, v308, 0);
                            }
                            if ( v308 )
                            {
                              v317 = *((unsigned __int8 *)v280 + 31);
                              if ( (unsigned __int8)v317 < 8u )
                              {
                                *((_DWORD *)v280 + v317 + 56) = v308;
                                ++*((_BYTE *)v280 + 31);
                              }
                            }
                            if ( v284 == 1 )
                            {
                              if ( v293 )
                              {
                                v318 = *((unsigned __int8 *)v280 + 31);
                                if ( (unsigned __int8)v318 < 8u )
                                {
                                  *((_DWORD *)v280 + v318 + 56) = v293;
                                  ++*((_BYTE *)v280 + 31);
                                }
                              }
                            }
                            else if ( v284 > *((_DWORD *)v280 + 10) )
                            {
                              *((_DWORD *)v280 + 10) = v284;
                              *((_DWORD *)v280 + 11) = v293;
                            }
                            sqlite3WhereEnd(v520);
                            v281 = *((_DWORD *)v280 + 13);
                            v513 = v281;
                            *(_DWORD *)(v506 + 8) = v281;
                            ++*((_DWORD *)v280 + 13);
                            v319 = *((_BYTE *)v280 + 31);
                            if ( v319 )
                            {
                              v320 = v319 - 1;
                              *((_BYTE *)v280 + 31) = v320;
                              v189 = *((_DWORD *)v280 + v320 + 56);
                            }
                            else
                            {
                              v189 = *((_DWORD *)v280 + 14) + 1;
                              *((_DWORD *)v280 + 14) = v189;
                            }
                            v321 = *((int *)v3 + 36);
                            if ( *((_DWORD *)v3 + 37) > (int)v321 )
                            {
                              *((_DWORD *)v3 + 36) = v321 + 1;
                              v322 = 3 * v321;
                              v323 = v3[17];
                              *(_DWORD *)(v323 + 8 * v322 + 12) = v284;
                              *(_QWORD *)(v323 + 8 * v322 + 16) = 0;
                              *(_DWORD *)(v323 + 8 * v322) = 121;
                              *(_DWORD *)(v323 + 8 * v322 + 4) = v281;
                              *(_DWORD *)(v323 + 8 * v322 + 8) = v189;
                            }
                            else
                            {
                              growOp3((_DWORD)v3, 121, v281, v189, v284);
                            }
                            v204 = v506;
                            v324 = *((int *)v3 + 36);
                            v325 = *(_DWORD *)(v506 + 4);
                            if ( *((_DWORD *)v3 + 37) > (int)v324 )
                            {
                              v326 = v510;
                              *((_DWORD *)v3 + 36) = v324 + 1;
                              v327 = 3 * v324;
                              v328 = v3[17];
                              *(_DWORD *)(v328 + 8 * v327) = 34;
                              *(_DWORD *)(v328 + 8 * v327 + 4) = v325;
                              *(_QWORD *)(v328 + 8 * v327 + 8) = v326;
                              *(_QWORD *)(v328 + 8 * v327 + 16) = 0;
                            }
                            else
                            {
                              growOp3((_DWORD)v3, 34, v325, v510, 0);
                            }
                            *(_BYTE *)(v506 + 1) = 1;
                          }
                          if ( v280[12] )
                          {
                            v329 = *(_DWORD *)(v204 + 48) <= 0;
                            v537 = aggregateIdxEprRefToColCallback;
                            v536 = 0;
                            v538 = 0;
                            v330 = 0;
                            v539 = 0;
                            if ( !v329 )
                            {
                              v331 = 0;
                              do
                              {
                                if ( *(_QWORD *)(v331 + *(_QWORD *)(v204 + 40)) )
                                  sqlite3WalkExprNN(&v536);
                                ++v330;
                                v331 += 32;
                              }
                              while ( v330 < *(_DWORD *)(v204 + 48) );
                            }
                          }
                          if ( v515 )
                          {
                            v332 = v501;
                            if ( (*(_BYTE *)(v502 + 96) & 4) == 0 && (v501 || (*(_BYTE *)(v520 + 68) & 8) != 0) )
                            {
                              v333 = *v3;
                              *(_QWORD *)&v533 = 0;
                              if ( !*(_BYTE *)(v333 + 103) )
                              {
                                v334 = v3[17] + 24LL * SDWORD2(v534);
                                freeP4(v333, (unsigned int)*(char *)(v334 + 1), *(_QWORD *)(v334 + 16));
                                *(_WORD *)v334 = 187;
                                *(_QWORD *)(v334 + 16) = 0;
                                goto LABEL_526;
                              }
                            }
                          }
                          else
                          {
LABEL_526:
                            v332 = v501;
                          }
                          v335 = *((int *)v3 + 36);
                          v515 = *((_DWORD *)v3 + 36);
                          if ( v332 )
                          {
                            v336 = *(_DWORD *)(v204 + 4);
                            if ( *((_DWORD *)v3 + 37) <= (int)v335 )
                            {
                              growOp3((_DWORD)v3, 133, v336, v189, v281);
                              v332 = v501;
                              goto LABEL_530;
                            }
                            v337 = v513;
                            v345 = 3 * v335;
                            *((_DWORD *)v3 + 36) = v335 + 1;
                            v346 = v3[17];
                            *(_DWORD *)(v346 + 8 * v345 + 8) = v189;
                            *(_QWORD *)(v346 + 8 * v345 + 16) = 0;
                            *(_DWORD *)(v346 + 8 * v345) = 133;
                            *(_DWORD *)(v346 + 8 * v345 + 4) = v336;
                            *(_DWORD *)(v346 + 8 * v345 + 12) = v337;
                            v332 = v501;
                          }
                          else
                          {
LABEL_530:
                            v337 = v513;
                          }
                          v338 = v504;
                          if ( (int)*v504 <= 0 )
                            goto LABEL_552;
                          v339 = v504 + 2;
                          v340 = v518;
                          v341 = v504;
                          v342 = -v518;
                          while ( 2 )
                          {
                            if ( v332 )
                            {
                              v343 = *((int *)v3 + 36);
                              v344 = v340 + v342;
                              if ( *((_DWORD *)v3 + 37) > (int)v343 )
                              {
                                *((_DWORD *)v3 + 36) = v343 + 1;
                                v347 = 3 * v343;
                                v348 = v3[17];
                                *(_DWORD *)(v348 + 8 * v347) = 94;
                                *(_DWORD *)(v348 + 8 * v347 + 4) = v337;
                                *(_DWORD *)(v348 + 8 * v347 + 8) = v344;
                                *(_DWORD *)(v348 + 8 * v347 + 12) = v340;
                                *(_QWORD *)(v348 + 8 * v347 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 94, v337, v344, v340);
                              }
                              goto LABEL_549;
                            }
                            *(_BYTE *)v506 = 1;
                            if ( a1[2] )
                            {
                              v349 = *v339;
                              v350 = sqlite3ExprCodeTarget(a1, *v339, v340, v273);
                              if ( v350 != v340 )
                              {
                                if ( !v349 )
                                  goto LABEL_547;
                                while ( 1 )
                                {
                                  v351 = *(_DWORD *)(v349 + 4);
                                  if ( (v351 & 0x82000) == 0 )
                                    break;
                                  if ( (v351 & 0x80000) != 0 )
                                  {
                                    v349 = *(_QWORD *)(*(_QWORD *)(v349 + 32) + 8LL);
                                  }
                                  else
                                  {
                                    if ( *(_BYTE *)v349 != 113 )
                                      break;
                                    v349 = *(_QWORD *)(v349 + 16);
                                  }
                                  if ( !v349 )
                                    goto LABEL_547;
                                }
                                if ( (v351 & 0x400000) != 0 || *(_BYTE *)v349 == 0xB0 )
                                  v352 = 80;
                                else
LABEL_547:
                                  v352 = 81;
                                sqlite3VdbeAddOp2(a1[2], v352, v350, v340);
                              }
LABEL_549:
                              v341 = v504;
                            }
                            v337 = v513;
                            ++v340;
                            v339 += 4;
                            v332 = v501;
                            if ( (signed int)(v342 + v340) >= *v341 )
                            {
                              LODWORD(v335) = v515;
                              v338 = v504;
LABEL_552:
                              v353 = v529;
                              if ( v529 )
                                ++*(_DWORD *)v529;
                              v354 = *((int *)v3 + 36);
                              v355 = *v338;
                              v356 = v518;
                              v357 = v521;
                              if ( *((_DWORD *)v3 + 37) > (int)v354 )
                              {
                                v359 = 3 * v354;
                                *((_DWORD *)v3 + 36) = v354 + 1;
                                v360 = v3[17];
                                *(_DWORD *)(v360 + 8 * v359) = 90;
                                *(_DWORD *)(v360 + 8 * v359 + 4) = v357;
                                *(_DWORD *)(v360 + 8 * v359 + 8) = v356;
                                *(_DWORD *)(v360 + 8 * v359 + 12) = v355;
                                *(_QWORD *)(v360 + 8 * v359 + 16) = 0;
                              }
                              else
                              {
                                v358 = growOp3((_DWORD)v3, 90, v521, v518, v355);
                                v353 = v529;
                                LODWORD(v354) = v358;
                              }
                              if ( *(_BYTE *)(*v3 + 103LL) )
                              {
                                if ( !*(_QWORD *)(*v3 + 760LL) )
                                {
                                  if ( v353 )
                                  {
                                    v157 = (*(_DWORD *)v353)-- == 1;
                                    if ( v157 )
                                      sqlite3DbNNFreeNN(*(_QWORD *)(v353 + 16), v353);
                                  }
                                }
                              }
                              else
                              {
                                if ( (int)v354 < 0 )
                                {
                                  _mm_lfence();
                                  LODWORD(v354) = *((_DWORD *)v3 + 36) - 1;
                                }
                                v361 = v3[17];
                                v157 = *(_BYTE *)(v361 + 24LL * (int)v354 + 1) == 0;
                                v362 = v361 + 24LL * (int)v354;
                                if ( v157 )
                                {
                                  if ( v353 )
                                  {
                                    *(_QWORD *)(v362 + 16) = v353;
                                    *(_BYTE *)(v362 + 1) = -8;
                                  }
                                }
                                else
                                {
                                  vdbeChangeP4Full(v3, v362, v353, 4294967288LL);
                                }
                              }
                              v363 = *((int *)v3 + 36);
                              v364 = v363 + 1;
                              if ( *((_DWORD *)v3 + 37) > (int)v363 )
                              {
                                v365 = v3[17];
                                v366 = 3 * v363;
                                *((_DWORD *)v3 + 36) = v364;
                                *(_DWORD *)(v365 + 8 * v366) = 14;
                                *(_DWORD *)(v365 + 8 * v366 + 4) = v364;
                                *(_DWORD *)(v365 + 8 * v366 + 8) = 0;
                                *(_DWORD *)(v365 + 8 * v366 + 12) = v364;
                                *(_QWORD *)(v365 + 8 * v366 + 16) = 0;
                              }
                              else
                              {
                                _mm_lfence();
                                growOp3((_DWORD)v3, 14, v364, 0, v364);
                              }
                              v367 = *v504;
                              v368 = a1[2];
                              v369 = *(int *)(v368 + 144);
                              if ( *(_DWORD *)(v368 + 148) > (int)v369 )
                              {
                                *(_DWORD *)(v368 + 144) = v369 + 1;
                                v370 = 3 * v369;
                                v371 = *(_QWORD *)(v368 + 136);
                                *(_DWORD *)(v371 + 8 * v370) = 79;
                                *(_DWORD *)(v371 + 8 * v370 + 4) = v356;
                                *(_DWORD *)(v371 + 8 * v370 + 8) = v357;
                                *(_DWORD *)(v371 + 8 * v370 + 12) = v367;
                                *(_QWORD *)(v371 + 8 * v370 + 16) = 0;
                              }
                              else
                              {
                                growOp3(v368, 79, v356, v357, v367);
                              }
                              v372 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v372 )
                              {
                                v374 = v514;
                                v375 = v372 + 1;
                                v376 = v517;
                                v377 = 3 * v372;
                                *((_DWORD *)v3 + 36) = v375;
                                v378 = v3[17];
                                v373 = v374 + 1;
                                *(_DWORD *)(v378 + 8 * v377) = 10;
                                *(_DWORD *)(v378 + 8 * v377 + 4) = v374 + 1;
                                *(_QWORD *)(v378 + 8 * v377 + 8) = v376;
                                *(_QWORD *)(v378 + 8 * v377 + 16) = 0;
                              }
                              else
                              {
                                v373 = v514 + 1;
                                growOp3((_DWORD)v3, 10, v514 + 1, v517, 0);
                                v374 = v514;
                              }
                              v379 = *((int *)v3 + 36);
                              v380 = v510;
                              if ( *((_DWORD *)v3 + 37) > (int)v379 )
                              {
                                *((_DWORD *)v3 + 36) = v379 + 1;
                                v381 = 3 * v379;
                                v382 = v3[17];
                                *(_DWORD *)(v382 + 8 * v381) = 59;
                                *(_DWORD *)(v382 + 8 * v381 + 4) = v374;
                                *(_DWORD *)(v382 + 8 * v381 + 8) = v380;
                                *(_DWORD *)(v382 + 8 * v381 + 12) = 0;
                                *(_QWORD *)(v382 + 8 * v381 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 59, v374, v510, 0);
                              }
                              v383 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v383 )
                              {
                                *((_DWORD *)v3 + 36) = v383 + 1;
                                v384 = 3 * v383;
                                v385 = v3[17];
                                *(_DWORD *)(v385 + 8 * v384 + 4) = v373 + 1;
                                *(_DWORD *)(v385 + 8 * v384 + 8) = v508;
                                *(_DWORD *)(v385 + 8 * v384) = 10;
                                *(_DWORD *)(v385 + 8 * v384 + 12) = 0;
                                *(_QWORD *)(v385 + 8 * v384 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 10, v373 + 1, v508, 0);
                              }
                              if ( *(_BYTE *)(*v3 + 103LL) )
                                v386 = &qword_1803DCAC0;
                              else
                                v386 = (__int64 *)(v3[17] + 24 * v363);
                              v387 = v522;
                              v388 = v511;
                              *((_DWORD *)v386 + 2) = *((_DWORD *)v3 + 36);
                              updateAccumulator(a1, v387, v506, v388);
                              v389 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v389 )
                              {
                                *((_DWORD *)v3 + 36) = v389 + 1;
                                v390 = 3 * v389;
                                v391 = v3[17];
                                *(_DWORD *)(v391 + 8 * v390) = 71;
                                *(_DWORD *)(v391 + 8 * v390 + 4) = 1;
                                *(_DWORD *)(v391 + 8 * v390 + 8) = v387;
                                *(_DWORD *)(v391 + 8 * v390 + 12) = 0;
                                *(_QWORD *)(v391 + 8 * v390 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 71, 1, v387, 0);
                              }
                              if ( v501 )
                              {
                                v392 = *((int *)v3 + 36);
                                v393 = *(_DWORD *)(v506 + 4);
                                if ( *((_DWORD *)v3 + 37) <= (int)v392 )
                                {
                                  growOp3((_DWORD)v3, 37, v393, v335, 0);
                                  goto LABEL_595;
                                }
                                *((_DWORD *)v3 + 36) = v392 + 1;
                                v396 = 3 * v392;
                                v397 = v3[17];
                                *(_DWORD *)(v397 + 8 * v396 + 8) = v335;
                                v4 = 0;
                                *(_DWORD *)(v397 + 8 * v396 + 12) = 0;
                                *(_QWORD *)(v397 + 8 * v396 + 16) = 0;
                                *(_DWORD *)(v397 + 8 * v396) = 37;
                                *(_DWORD *)(v397 + 8 * v396 + 4) = v393;
                              }
                              else
                              {
                                sqlite3WhereEnd(v520);
                                if ( *(_BYTE *)(*v3 + 103LL) )
                                {
LABEL_595:
                                  v4 = 0;
                                }
                                else
                                {
                                  v398 = v3[17] + 24LL * (int)v509;
                                  freeP4(*v3, (unsigned int)*(char *)(v398 + 1), *(_QWORD *)(v398 + 16));
                                  v4 = 0;
                                  *(_WORD *)v398 = 187;
                                  *(_QWORD *)(v398 + 16) = 0;
                                }
                              }
                              if ( v530 )
                                exprListDeleteNN(v502);
                              v394 = *((int *)v3 + 36);
                              v395 = v517;
                              if ( *((_DWORD *)v3 + 37) > (int)v394 )
                              {
                                *((_DWORD *)v3 + 36) = v394 + 1;
                                v399 = 3 * v394;
                                v400 = v3[17];
                                *(_DWORD *)(v400 + 8 * v399) = 10;
                                *(_DWORD *)(v400 + 8 * v399 + 4) = v373;
                                *(_DWORD *)(v400 + 8 * v399 + 8) = v395;
                                *(_DWORD *)(v400 + 8 * v399 + 12) = 0;
                                *(_QWORD *)(v400 + 8 * v399 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 10, v373, v517, 0);
                              }
                              v401 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v401 )
                              {
                                *((_DWORD *)v3 + 36) = v401 + 1;
                                v402 = 3 * v401;
                                v403 = v3[17];
                                *(_QWORD *)(v403 + 8 * v402) = 9;
                                *(_DWORD *)(v403 + 8 * v402 + 8) = v380;
                                *(_DWORD *)(v403 + 8 * v402 + 12) = 0;
                                *(_QWORD *)(v403 + 8 * v402 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 9, 0, v380, 0);
                              }
                              v404 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v404 )
                              {
                                v405 = v514;
                                v406 = 3 * v404;
                                *((_DWORD *)v3 + 36) = v404 + 1;
                                v407 = v3[17];
                                *(_DWORD *)(v407 + 8 * v406) = 71;
                                *(_DWORD *)(v407 + 8 * v406 + 4) = 1;
                                *(_QWORD *)(v407 + 8 * v406 + 8) = v405;
                                *(_QWORD *)(v407 + 8 * v406 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 71, 1, v514, 0);
                              }
                              v408 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v408 )
                              {
                                *((_DWORD *)v3 + 36) = v408 + 1;
                                v409 = 3 * v408;
                                v410 = v3[17];
                                *(_DWORD *)(v410 + 8 * v409) = 67;
                                *(_DWORD *)(v410 + 8 * v409 + 4) = v373;
                                *(_QWORD *)(v410 + 8 * v409 + 8) = 0;
                                *(_QWORD *)(v410 + 8 * v409 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 67, v373, 0, 0);
                              }
                              v411 = v3[3];
                              v412 = ~v395;
                              if ( *(_DWORD *)(v411 + 68) + *(_DWORD *)(v411 + 72) >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v411 + 80) + 4LL * v412) = *((_DWORD *)v3 + 36);
                              else
                                resizeResolveLabel(v411, v3, (unsigned int)v412);
                              v413 = *((int *)v3 + 36);
                              v414 = v522;
                              v415 = v413 + 2;
                              v416 = v413 + 1;
                              if ( *((_DWORD *)v3 + 37) > (int)v413 )
                              {
                                v417 = 3 * v413;
                                *((_DWORD *)v3 + 36) = v416;
                                v418 = v3[17];
                                *(_DWORD *)(v418 + 8 * v417) = 59;
                                *(_DWORD *)(v418 + 8 * v417 + 4) = v414;
                                *(_DWORD *)(v418 + 8 * v417 + 8) = v415;
                                *(_DWORD *)(v418 + 8 * v417 + 12) = 0;
                                *(_QWORD *)(v418 + 8 * v417 + 16) = 0;
                              }
                              else
                              {
                                _mm_lfence();
                                growOp3((_DWORD)v3, 59, v522, v415, 0);
                              }
                              v419 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v419 )
                              {
                                *((_DWORD *)v3 + 36) = v419 + 1;
                                v420 = 3 * v419;
                                v421 = v3[17];
                                *(_DWORD *)(v421 + 8 * v420) = 67;
                                *(_DWORD *)(v421 + 8 * v420 + 4) = v373;
                                *(_QWORD *)(v421 + 8 * v420 + 8) = 0;
                                *(_QWORD *)(v421 + 8 * v420 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 67, v373, 0, 0);
                              }
                              finalizeAggFunctions(a1, v506);
                              sqlite3ExprIfFalse(a1, v523, v416, 16);
                              v495 = v404;
                              v9 = a1;
                              selectInnerLoop((_DWORD)a1, a2, -1, (unsigned int)&v533, (__int64)&v524, v516, v416, v495);
                              v422 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v422 )
                              {
                                *((_DWORD *)v3 + 36) = v422 + 1;
                                v423 = 3 * v422;
                                v424 = v3[17];
                                *(_DWORD *)(v424 + 8 * v423) = 67;
                                *(_DWORD *)(v424 + 8 * v423 + 4) = v373;
                                *(_QWORD *)(v424 + 8 * v423 + 8) = 0;
                                *(_QWORD *)(v424 + 8 * v423 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 67, v373, 0, 0);
                              }
                              v425 = v3[3];
                              v426 = ~v508;
                              if ( *(_DWORD *)(v425 + 68) + *(_DWORD *)(v425 + 72) >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v425 + 80) + 4LL * v426) = *((_DWORD *)v3 + 36);
                              else
                                resizeResolveLabel(v425, v3, (unsigned int)v426);
                              resetAccumulator(a1, v506);
                              v427 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v427 )
                              {
                                *((_DWORD *)v3 + 36) = v427 + 1;
                                v428 = 3 * v427;
                                v429 = v3[17];
                                *(_QWORD *)(v429 + 8 * v428) = 71;
                                *(_DWORD *)(v429 + 8 * v428 + 8) = v414;
                                *(_DWORD *)(v429 + 8 * v428 + 12) = 0;
                                *(_QWORD *)(v429 + 8 * v428 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 71, 0, v414, 0);
                              }
                              v430 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v430 )
                              {
                                v431 = v519;
                                *((_DWORD *)v3 + 36) = v430 + 1;
                                v432 = 3 * v430;
                                v433 = v3[17];
                                *(_DWORD *)(v433 + 8 * v432) = 67;
                                *(_DWORD *)(v433 + 8 * v432 + 4) = v431;
                                *(_QWORD *)(v433 + 8 * v432 + 8) = 0;
                                *(_QWORD *)(v433 + 8 * v432 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 67, v519, 0, 0);
                              }
                              if ( v499 && v511 )
                                fixDistinctOpenEph(
                                  a1,
                                  v511,
                                  *(unsigned int *)(*(_QWORD *)(v506 + 40) + 16LL),
                                  *(unsigned int *)(*(_QWORD *)(v506 + 40) + 20LL));
                              v434 = v510;
                              v181 = v516;
LABEL_733:
                              v185 = v3[3];
                              v490 = ~v434;
                              if ( *(_DWORD *)(v185 + 68) + *(_DWORD *)(v185 + 72) < 0 )
                              {
                                resizeResolveLabel(v185, v3, (unsigned int)v490);
                                v182 = a2;
                                goto LABEL_737;
                              }
                              v187 = v490;
                              v182 = a2;
LABEL_736:
                              *(_DWORD *)(*(_QWORD *)(v185 + 80) + 4 * v187) = *((_DWORD *)v3 + 36);
LABEL_737:
                              if ( v525 == 3 )
                                sqlite3VdbeExplain(v9, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
                              if ( (_QWORD)v533 )
                                generateSortTail((_DWORD)v9, v182, (unsigned int)&v533, *(_DWORD *)v512, v181);
                              v491 = v3[3];
                              v492 = ~v531;
                              if ( *(_DWORD *)(v491 + 68) + *(_DWORD *)(v491 + 72) >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v491 + 80) + 4LL * v492) = *((_DWORD *)v3 + 36);
                              else
                                resizeResolveLabel(v491, v3, (unsigned int)v492);
                              v233 = v502;
                              v6 = *((_DWORD *)v9 + 12) > 0;
LABEL_433:
                              if ( v532 )
                                exprListDeleteNN(v233);
                              goto LABEL_747;
                            }
                            continue;
                          }
                        }
                        if ( !v219[6] )
                        {
                          v435 = v219[4];
                          if ( *(_DWORD *)v435 == 1 )
                          {
                            v436 = v219[5];
                            if ( *(_DWORD *)v436 == 1
                              && !*(_QWORD *)(v436 + 48)
                              && *(_DWORD *)(v204 + 48) == 1
                              && !v219[8] )
                            {
                              v437 = *(_QWORD *)(v436 + 40);
                              if ( !*(_BYTE *)(v437 + 63) )
                              {
                                v438 = *(_QWORD *)(v435 + 8);
                                if ( *(_BYTE *)v438 == 0xA8
                                  && *(_QWORD *)(v438 + 56) == v204
                                  && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v204 + 40) + 8LL) + 4LL) & 0x100) != 0
                                  && (*(_DWORD *)(v438 + 4) & 0x1000004) == 0
                                  && v437 )
                                {
                                  v439 = *(_QWORD *)(v437 + 96);
                                  v440 = -32768;
                                  v441 = v437;
                                  if ( v439 )
                                  {
                                    v440 = 0;
                                    for ( j = (_QWORD *)(*(_QWORD *)(*a1 + 32LL) + 24LL); *j != v439; j += 4 )
                                      ++v440;
                                  }
                                  v443 = a1;
                                  v444 = 0;
                                  v445 = a1;
                                  k = 0;
                                  v447 = *((_DWORD *)a1 + 13);
                                  *((_DWORD *)a1 + 13) = v447 + 1;
                                  v448 = *(_DWORD *)(v441 + 40);
                                  if ( a1[21] )
                                    v445 = (_QWORD *)a1[21];
                                  v449 = *((_DWORD *)v445 + 33);
                                  if ( !_bittest(&v449, v440) )
                                  {
                                    *((_DWORD *)v445 + 33) = v449 | (1 << v440);
                                    if ( v440 == 1 )
                                    {
                                      sqlite3OpenTempDatabase(v445);
                                      v443 = a1;
                                    }
                                  }
                                  if ( *(char *)(v441 + 48) < 0 )
                                  {
                                    for ( k = *(_QWORD *)(v441 + 16); k; k = *(_QWORD *)(k + 40) )
                                    {
                                      if ( (*(_DWORD *)(k + 100) & 3) == 2 )
                                        break;
                                    }
                                  }
                                  if ( (*(_BYTE *)(*(_QWORD *)(a2 + 40) + 72LL) & 1) == 0 )
                                  {
                                    for ( m = *(_QWORD *)(v441 + 16); m; m = *(_QWORD *)(m + 40) )
                                    {
                                      if ( (*(_BYTE *)(m + 100) & 4) == 0 )
                                      {
                                        v451 = *(_WORD *)(m + 92);
                                        if ( v451 < *(__int16 *)(v441 + 60)
                                          && !*(_QWORD *)(m + 72)
                                          && (!k || v451 < *(__int16 *)(k + 92)) )
                                        {
                                          k = m;
                                        }
                                      }
                                    }
                                  }
                                  if ( k )
                                  {
                                    v448 = *(_DWORD *)(k + 88);
                                    v444 = sqlite3KeyInfoOfIndex(v443, k);
                                  }
                                  v452 = *((int *)v3 + 36);
                                  if ( *((_DWORD *)v3 + 37) > (int)v452 )
                                  {
                                    *((_DWORD *)v3 + 36) = v452 + 1;
                                    v453 = 3 * v452;
                                    v454 = v3[17];
                                    *(_DWORD *)(v454 + 8 * v453) = 64880;
                                    *(_DWORD *)(v454 + 8 * v453 + 4) = v447;
                                    *(_DWORD *)(v454 + 8 * v453 + 8) = v448;
                                    *(_DWORD *)(v454 + 8 * v453 + 12) = v440;
                                    *(_DWORD *)(v454 + 8 * v453 + 16) = 1;
                                  }
                                  else
                                  {
                                    addOp4IntSlow((_DWORD)v3, 112, v447, v448, v440, 1);
                                  }
                                  if ( v444 )
                                  {
                                    if ( *(_BYTE *)(*v3 + 103LL) )
                                    {
                                      if ( !*(_QWORD *)(*v3 + 760LL) )
                                      {
                                        v157 = (*(_DWORD *)v444)-- == 1;
                                        if ( v157 )
                                          sqlite3DbNNFreeNN(*(_QWORD *)(v444 + 16), v444);
                                      }
                                    }
                                    else
                                    {
                                      v455 = v3[17];
                                      v456 = 3LL * *((int *)v3 + 36) - 3;
                                      v157 = *(_BYTE *)(v455 + 8 * v456 + 1) == 0;
                                      v457 = v455 + 8 * v456;
                                      if ( v157 )
                                      {
                                        *(_QWORD *)(v457 + 16) = v444;
                                        *(_BYTE *)(v457 + 1) = -8;
                                      }
                                      else
                                      {
                                        vdbeChangeP4Full(v3, v457, v444, 4294967288LL);
                                      }
                                    }
                                  }
                                  v4 = 0;
                                  v9 = a1;
                                  *(_DWORD *)(v506 + 12) = *((_DWORD *)a1 + 14) + 1;
                                  *((_DWORD *)a1 + 14) += *(_DWORD *)(v506 + 32) + *(_DWORD *)(v506 + 48);
                                  v458 = *(_DWORD *)(v506 + 12) + *(_DWORD *)(v506 + 32);
                                  v459 = *((int *)v3 + 36);
                                  if ( *((_DWORD *)v3 + 37) > (int)v459 )
                                  {
                                    *((_DWORD *)v3 + 36) = v459 + 1;
                                    v460 = 3 * v459;
                                    v461 = v3[17];
                                    *(_DWORD *)(v461 + 8 * v460) = 98;
                                    *(_DWORD *)(v461 + 8 * v460 + 4) = v447;
                                    *(_DWORD *)(v461 + 8 * v460 + 8) = v458;
                                    *(_DWORD *)(v461 + 8 * v460 + 12) = 0;
                                    *(_QWORD *)(v461 + 8 * v460 + 16) = 0;
                                  }
                                  else
                                  {
                                    growOp3((_DWORD)v3, 98, v447, v458, 0);
                                  }
                                  v462 = *((int *)v3 + 36);
                                  if ( *((_DWORD *)v3 + 37) > (int)v462 )
                                  {
                                    *((_DWORD *)v3 + 36) = v462 + 1;
                                    v463 = 3 * v462;
                                    v464 = v3[17];
                                    *(_DWORD *)(v464 + 8 * v463) = 122;
                                    *(_DWORD *)(v464 + 8 * v463 + 4) = v447;
                                    *(_QWORD *)(v464 + 8 * v463 + 8) = 0;
                                    *(_QWORD *)(v464 + 8 * v463 + 16) = 0;
                                  }
                                  else
                                  {
                                    growOp3((_DWORD)v3, 122, v447, 0, 0);
                                  }
                                  if ( *((_BYTE *)a1 + 299) == 2 )
                                  {
                                    if ( !k || *(char *)(v441 + 48) < 0 && (*(_DWORD *)(k + 100) & 3) == 2 )
                                    {
                                      v466 = (const char *)&byte_1802990D8;
                                      LODWORD(v529) = 0;
                                      v465 = &byte_1802990D8;
                                    }
                                    else
                                    {
                                      v465 = *(const wchar_t **)k;
                                      v466 = (const char *)&byte_1802990D8;
                                    }
                                    if ( (_DWORD)v529 )
                                      v466 = " USING COVERING INDEX ";
                                    sqlite3VdbeExplain(a1, 0, "SCAN %s%s%s", *(_QWORD *)v441, v466, v465);
                                  }
                                  goto LABEL_732;
                                }
                              }
                            }
                          }
                        }
                        v467 = 0;
                        v468 = 0;
                        v469 = 0;
                        v470 = *(_DWORD *)(v506 + 48);
                        if ( *(_DWORD *)(v506 + 36) )
                        {
                          v471 = 0;
                          if ( v470 <= 0 )
                          {
LABEL_705:
                            if ( v471 == v470 )
                            {
                              v467 = *((_DWORD *)a1 + 14) + 1;
                              *((_DWORD *)a1 + 14) = v467;
                              v473 = *((int *)v3 + 36);
                              if ( *((_DWORD *)v3 + 37) > (int)v473 )
                              {
                                *((_DWORD *)v3 + 36) = v473 + 1;
                                v474 = 3 * v473;
                                v475 = v3[17];
                                *(_QWORD *)(v475 + 8 * v474) = 71;
                                *(_DWORD *)(v475 + 8 * v474 + 8) = v467;
                                *(_DWORD *)(v475 + 8 * v474 + 12) = 0;
                                *(_QWORD *)(v475 + 8 * v474 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 71, 0, v467, 0);
                              }
                            }
                          }
                          else
                          {
                            v472 = *(_QWORD **)(v506 + 40);
                            while ( (*(_DWORD *)(*v472 + 4LL) & 0x1000000) != 0
                                 || (*(_BYTE *)(v472[1] + 4LL) & 0x20) == 0 )
                            {
                              ++v471;
                              v472 += 4;
                              if ( v471 >= v470 )
                                goto LABEL_705;
                            }
                          }
                        }
                        else if ( v470 == 1 )
                        {
                          v476 = *(int **)(v506 + 40);
                          if ( v476[4] >= 0 )
                          {
                            v468 = *(_QWORD *)(*(_QWORD *)v476 + 32LL);
                            v469 = v468 != 0 ? 0x500 : 0;
                          }
                        }
                        *(_DWORD *)(v506 + 12) = *((_DWORD *)a1 + 14) + 1;
                        *((_DWORD *)a1 + 14) += *(_DWORD *)(v506 + 32) + *(_DWORD *)(v506 + 48);
                        resetAccumulator(a1, v506);
                        v477 = sqlite3WhereBegin((_DWORD)a1, (_DWORD)v500, v520, v532, v468, a2, v469 | v227, 0);
                        v478 = v477;
                        if ( v477 )
                        {
                          v479 = *(unsigned __int8 *)(v477 + 67);
                          updateAccumulator(a1, v467, v506, *(unsigned __int8 *)(v477 + 67));
                          if ( v479 )
                          {
                            v480 = *(_QWORD *)(v506 + 40);
                            if ( v480 )
                              fixDistinctOpenEph(a1, v479, *(unsigned int *)(v480 + 16), *(unsigned int *)(v480 + 20));
                          }
                          if ( v467 )
                          {
                            v481 = *((int *)v3 + 36);
                            if ( *((_DWORD *)v3 + 37) > (int)v481 )
                            {
                              *((_DWORD *)v3 + 36) = v481 + 1;
                              v482 = 3 * v481;
                              v483 = v3[17];
                              *(_DWORD *)(v483 + 8 * v482) = 71;
                              *(_DWORD *)(v483 + 8 * v482 + 4) = 1;
                              *(_DWORD *)(v483 + 8 * v482 + 8) = v467;
                              *(_DWORD *)(v483 + 8 * v482 + 12) = 0;
                              *(_QWORD *)(v483 + 8 * v482 + 16) = 0;
                            }
                            else
                            {
                              growOp3((_DWORD)v3, 71, 1, v467, 0);
                            }
                          }
                          if ( v227 && (*(_BYTE *)(v478 + 68) & 4) != 0 && *(_BYTE *)(v478 + 65) )
                          {
                            v484 = *(unsigned __int8 *)(v478 + 64) - 1LL;
                            if ( v484 < 0 )
                            {
LABEL_727:
                              v486 = *((int *)v3 + 36);
                              v487 = *(_DWORD *)(v478 + 52);
                              if ( *((_DWORD *)v3 + 37) > (int)v486 )
                              {
                                *((_DWORD *)v3 + 36) = v486 + 1;
                                v488 = 3 * v486;
                                v489 = v3[17];
                                *(_QWORD *)(v489 + 8 * v488) = 9;
                                *(_DWORD *)(v489 + 8 * v488 + 8) = v487;
                                *(_DWORD *)(v489 + 8 * v488 + 12) = 0;
                                *(_QWORD *)(v489 + 8 * v488 + 16) = 0;
                              }
                              else
                              {
                                growOp3((_DWORD)v3, 9, 0, v487, 0);
                              }
                            }
                            else
                            {
                              v485 = v478 + 112 * v484;
                              while ( (*(_BYTE *)(*(_QWORD *)(v485 + 960) + 56LL) & 4) == 0 )
                              {
                                v485 -= 112;
                                if ( --v484 < 0 )
                                  goto LABEL_727;
                              }
                              sqlite3VdbeGoto(v3, *(unsigned int *)(v485 + 880));
                            }
                          }
                          sqlite3WhereEnd(v478);
                          v9 = a1;
                          finalizeAggFunctions(a1, v506);
LABEL_732:
                          v434 = v510;
                          *(_QWORD *)&v533 = 0;
                          sqlite3ExprIfFalse(v9, v523, v510, 16);
                          v181 = v516;
                          selectInnerLoop((_DWORD)v9, a2, -1, 0, 0, v516, v434, v434);
                          goto LABEL_733;
                        }
LABEL_431:
                        v233 = v502;
                      }
                      v9 = a1;
                      v6 = 1;
                      goto LABEL_433;
                    }
                  }
                  else if ( *((unsigned __int8 *)qword_18026E880 + v230) != *((unsigned __int8 *)qword_18026E880 + v231) )
                  {
                    goto LABEL_386;
                  }
                  ++v223;
                }
              }
            }
          }
          goto LABEL_746;
        }
      }
    }
    v7 = (__int128 *)v516;
  }
  v505 = v14;
  if ( !v17 )
    goto LABEL_77;
  v39 = multiSelect(v9, (unsigned __int8 *)v8, v7);
  if ( !*(_QWORD *)(v8 + 88) )
    sqlite3VdbeExplainPop(v9);
  return v39;
}

```

## disassembly

```asm
0x18012c390  push    rbp
0x18012c392  push    rbx
0x18012c393  push    rsi
0x18012c394  push    rdi
0x18012c395  push    r12
0x18012c397  push    r13
0x18012c399  push    r14
0x18012c39b  lea     rbp, [rsp-0B0h]
0x18012c3a3  sub     rsp, 1B0h
0x18012c3aa  mov     rax, cs:__security_cookie
0x18012c3b1  xor     rax, rsp
0x18012c3b4  mov     [rbp+0E0h+var_38], rax
0x18012c3bb  mov     r13, [rcx+10h]
0x18012c3bf  xor     r12d, r12d
0x18012c3c2  mov     rax, [rcx]
0x18012c3c5  mov     esi, 1
0x18012c3ca  mov     [rbp+0E0h+var_138], r8
0x18012c3ce  mov     r14, r8
0x18012c3d1  mov     [rsp+1E0h+var_198], rdx
0x18012c3d6  mov     rbx, rdx
0x18012c3d9  mov     [rsp+1E0h+var_1A0], rcx
0x18012c3de  mov     rdi, rcx
0x18012c3e1  mov     [rbp+0E0h+var_F0], rsi
0x18012c3e5  mov     [rbp+0E0h+var_D8], r12
0x18012c3e9  mov     [rsp+1E0h+var_180], rax
0x18012c3ee  mov     [rbp+0E0h+var_F8], r13
0x18012c3f2  test    r13, r13
0x18012c3f5  jnz     short loc_18012C416
0x18012c3f7  cmp     [rcx+0A8h], r12
0x18012c3fe  jnz     short loc_18012C40A
0x18012c400  test    byte ptr [rax+60h], 8
0x18012c404  jnz     short loc_18012C40A
0x18012c406  mov     [rcx+23h], sil
0x18012c40a  call    sqlite3VdbeCreate
0x18012c40f  mov     r13, rax
0x18012c412  mov     [rbp+0E0h+var_F8], rax
0x18012c416  test    rbx, rbx
0x18012c419  jz      loc_18012F868
0x18012c41f  cmp     [rdi+30h], r12d
0x18012c423  jnz     loc_18012F868
0x18012c429  xor     r9d, r9d
0x18012c42c  mov     [rsp+1E0h+var_1C0], r12
0x18012c431  xor     r8d, r8d
0x18012c434  mov     edx, 15h
0x18012c439  mov     rcx, rdi
0x18012c43c  call    sqlite3AuthCheck
0x18012c441  test    eax, eax
0x18012c443  jnz     loc_18012F868
0x18012c449  cmp     byte ptr [r14], 6
0x18012c44d  ja      short loc_18012C476
0x18012c44f  mov     r8, [rbx+48h]
0x18012c453  test    r8, r8
0x18012c456  jz      short loc_18012C46B
0x18012c458  lea     rdx, sqlite3ExprListDeleteGeneric
0x18012c45f  mov     rcx, rdi
0x18012c462  call    sqlite3ParserAddCleanup
0x18012c467  mov     [rbx+48h], r12
0x18012c46b  and     dword ptr [rbx+4], 0FFFFFFFEh
0x18012c46f  or      dword ptr [rbx+4], 400000h
0x18012c476  xor     r8d, r8d
0x18012c479  mov     [rsp+1E0h+arg_18], r15
0x18012c481  mov     rdx, rbx
0x18012c484  mov     rcx, rdi
0x18012c487  call    sqlite3SelectPrep
0x18012c48c  lea     r8, qword_1803DCAC0
0x18012c493  cmp     [rdi+30h], r12d
0x18012c497  jnz     loc_18012F82F
0x18012c49d  mov     r11d, [rbx+4]
0x18012c4a1  bt      r11d, 17h
0x18012c4a6  jnb     short loc_18012C4E9
0x18012c4a8  mov     r10, [rbx+28h]
0x18012c4ac  mov     rdx, r10
0x18012c4af  lea     rcx, [r10+8]
0x18012c4b3  call    sameSrcAlias
0x18012c4b8  test    eax, eax
0x18012c4ba  jz      short loc_18012C4E0
0x18012c4bc  mov     r8, [r10+20h]
0x18012c4c0  test    r8, r8
0x18012c4c3  jnz     short loc_18012C4CC
0x18012c4c5  mov     rax, [r10+28h]
0x18012c4c9  mov     r8, [rax]
0x18012c4cc  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x18012c4d3  mov     rcx, rdi
0x18012c4d6  call    sqlite3ErrorMsg
0x18012c4db  jmp     loc_18012F828
0x18012c4e0  btr     r11d, 17h
0x18012c4e5  mov     [rbx+4], r11d
0x18012c4e9  cmp     byte ptr [r14], 9
0x18012c4ed  jnz     short loc_18012C4FA
0x18012c4ef  mov     rdx, rbx
0x18012c4f2  mov     rcx, rdi
0x18012c4f5  call    sqlite3GenerateColumnNames
0x18012c4fa  mov     rdx, rbx
0x18012c4fd  mov     rcx, rdi
0x18012c500  call    sqlite3WindowRewrite
0x18012c505  test    eax, eax
0x18012c507  jnz     loc_18012F828
0x18012c50d  mov     eax, [rbx+4]
0x18012c510  xorps   xmm0, xmm0
0x18012c513  mov     rdx, [rbx+48h]
0x18012c517  and     eax, 8
0x18012c51a  mov     r11, [rbx+28h]
0x18012c51e  mov     r10, [rsp+1E0h+var_180]
0x18012c523  setnz   r12b
0x18012c527  xor     ecx, ecx
0x18012c529  mov     [rbp+0E0h+var_128], eax
0x18012c52c  mov     rax, [rbx+50h]
0x18012c530  mov     esi, ecx
0x18012c532  mov     [rsp+1E0h+var_188], r11
0x18012c537  mov     [rbp+0E0h+var_154], r12d
0x18012c53b  mov     [rbp+0E0h+var_160], rdx
0x18012c53f  movups  [rbp+0E0h+var_D0], xmm0
0x18012c543  mov     qword ptr [rbp+0E0h+var_D0], rdx
0x18012c547  movups  [rbp+0E0h+var_C0], xmm0
0x18012c54b  movups  [rbp+0E0h+var_B0], xmm0
0x18012c54f  test    rax, rax
0x18012c552  jnz     loc_18012C863
0x18012c558  mov     r14d, ecx
0x18012c55b  mov     eax, ecx
0x18012c55d  cmp     [r11], ecx
0x18012c560  jle     loc_18012C85F
0x18012c566  nop     word ptr [rax+rax+00000000h]
0x18012c570  imul    rbx, r14, 68h ; 'h'
0x18012c574  add     rbx, r11
0x18012c577  movzx   r8d, byte ptr [rbx+44h]
0x18012c57c  mov     rdi, [rbx+30h]
0x18012c580  mov     r15, [rbx+28h]
0x18012c584  test    r8b, 48h
0x18012c588  jz      loc_18012C68D
0x18012c58e  mov     rcx, [rsp+1E0h+var_198]
0x18012c593  and     r8d, 40h
0x18012c597  mov     edx, [rbx+4Ch]
0x18012c59a  mov     rcx, [rcx+30h]
0x18012c59e  call    sqlite3ExprImpliesNonNullRow
0x18012c5a3  mov     r10, [rsp+1E0h+var_180]
0x18012c5a8  test    eax, eax
0x18012c5aa  jz      loc_18012C722
0x18012c5b0  test    dword ptr [r10+60h], 2000h
0x18012c5b8  jnz     loc_18012C722
0x18012c5be  movzx   eax, byte ptr [rbx+44h]
0x18012c5c2  test    al, 8
0x18012c5c4  jz      short loc_18012C5EA
0x18012c5c6  test    al, 10h
0x18012c5c8  jz      short loc_18012C5D1
0x18012c5ca  and     al, 0F7h
0x18012c5cc  mov     [rbx+44h], al
0x18012c5cf  jmp     short loc_18012C5EA
0x18012c5d1  mov     edx, [rbx+4Ch]
0x18012c5d4  and     al, 0D7h
0x18012c5d6  mov     [rbx+44h], al
0x18012c5d9  xor     r8d, r8d
0x18012c5dc  mov     rax, [rsp+1E0h+var_198]
0x18012c5e1  mov     rcx, [rax+30h]
0x18012c5e5  call    unsetJoinExpr
0x18012c5ea  test    byte ptr [rbx+44h], 40h
0x18012c5ee  mov     r11, [rsp+1E0h+var_188]
0x18012c5f3  jz      loc_18012C689
0x18012c5f9  mov     eax, [r11]
0x18012c5fc  lea     r10d, [rsi+1]
0x18012c600  cmp     r10d, eax
0x18012c603  jge     short loc_18012C65F
0x18012c605  mov     r13, [rsp+1E0h+var_198]
0x18012c60a  mov     r12d, 1
0x18012c610  imul    r9, r14, 68h ; 'h'
0x18012c614  add     r9, 0ACh
0x18012c61b  add     r9, r11
0x18012c61e  xchg    ax, ax
0x18012c620  movzx   eax, byte ptr [r9]
0x18012c624  test    al, 10h
0x18012c626  jz      short loc_18012C648
0x18012c628  test    al, 8
0x18012c62a  jz      short loc_18012C633
0x18012c62c  and     al, 0EFh
0x18012c62e  mov     [r9], al
0x18012c631  jmp     short loc_18012C648
0x18012c633  mov     edx, [r9+8]
0x18012c637  and     al, 0CFh
0x18012c639  mov     [r9], al
0x18012c63c  mov     r8d, r12d
0x18012c63f  mov     rcx, [r13+30h]
0x18012c643  call    unsetJoinExpr
0x18012c648  mov     eax, [r11]
0x18012c64b  inc     r10d
0x18012c64e  add     r9, 68h ; 'h'
0x18012c652  cmp     r10d, eax
0x18012c655  jl      short loc_18012C620
0x18012c657  mov     r13, [rbp+0E0h+var_F8]
0x18012c65b  mov     r12d, [rbp+0E0h+var_154]
0x18012c65f  sub     eax, 1
0x18012c662  movsxd  rdx, eax
0x18012c665  js      short loc_18012C684
0x18012c667  imul    rcx, rdx, 68h ; 'h'
0x18012c66b  add     rcx, 44h ; 'D'
0x18012c66f  add     rcx, r11
0x18012c672  and     byte ptr [rcx], 0BFh
0x18012c675  test    byte ptr [rcx], 10h
0x18012c678  jnz     short loc_18012C684
0x18012c67a  sub     rcx, 68h ; 'h'
0x18012c67e  sub     rdx, 1
0x18012c682  jns     short loc_18012C672
0x18012c684  mov     r10, [rsp+1E0h+var_180]
0x18012c689  mov     rdx, [rbp+0E0h+var_160]
0x18012c68d  test    rdi, rdi
0x18012c690  jz      loc_18012C7B0
0x18012c696  mov     rax, [rdi+20h]
0x18012c69a  movsx   r8d, word ptr [r15+36h]
0x18012c69f  mov     ecx, [rax]
0x18012c6a1  cmp     r8d, ecx
0x18012c6a4  jnz     loc_18012C83C
0x18012c6aa  test    dword ptr [rbx+48h], 100h
0x18012c6b1  jz      short loc_18012C6C1
0x18012c6b3  mov     rax, [rbx+68h]
0x18012c6b7  cmp     byte ptr [rax+12h], 0
0x18012c6bb  jz      loc_18012C7B0
0x18012c6c1  mov     eax, [rdi+4]
0x18012c6c4  mov     rbx, [rsp+1E0h+var_198]
0x18012c6c9  test    al, 8
0x18012c6cb  jnz     loc_18012C7A9
0x18012c6d1  mov     r8, [rdi+48h]
0x18012c6d5  test    r8, r8
0x18012c6d8  jz      short loc_18012C749
0x18012c6da  cmp     qword ptr [rbx+48h], 0
0x18012c6df  jnz     short loc_18012C6E7
0x18012c6e1  cmp     dword ptr [r11], 1
0x18012c6e5  jle     short loc_18012C72C
0x18012c6e7  cmp     qword ptr [rdi+60h], 0
0x18012c6ec  jnz     short loc_18012C72C
0x18012c6ee  bt      eax, 1Bh
0x18012c6f2  jb      short loc_18012C72C
0x18012c6f4  test    dword ptr [rbx+4], 8000000h
0x18012c6fb  jnz     short loc_18012C72C
0x18012c6fd  test    dword ptr [r10+60h], 40000h
0x18012c705  jnz     short loc_18012C72C
0x18012c707  mov     rcx, [rsp+1E0h+var_1A0]
0x18012c70c  lea     rdx, sqlite3ExprListDeleteGeneric
0x18012c713  call    sqlite3ParserAddCleanup
0x18012c718  mov     qword ptr [rdi+48h], 0
0x18012c720  jmp     short loc_18012C749
0x18012c722  mov     r11, [rsp+1E0h+var_188]
0x18012c727  jmp     loc_18012C689
0x18012c72c  test    esi, esi
0x18012c72e  jnz     short loc_18012C749
0x18012c730  test    dword ptr [rbx+4], 40000h
0x18012c737  jz      short loc_18012C749
0x18012c739  cmp     dword ptr [r11], 1
0x18012c73d  jz      short loc_18012C7A9
0x18012c73f  test    byte ptr [r11+0ACh], 22h
0x18012c747  jnz     short loc_18012C7A9
0x18012c749  mov     rdi, [rsp+1E0h+var_1A0]
0x18012c74e  mov     r9d, r12d
0x18012c751  mov     rcx, rdi
0x18012c754  mov     r8d, esi
0x18012c757  mov     rdx, rbx
0x18012c75a  call    flattenSubquery
0x18012c75f  test    eax, eax
0x18012c761  jz      short loc_18012C779
0x18012c763  cmp     dword ptr [rdi+30h], 0
0x18012c767  jnz     loc_18012C857
0x18012c76d  mov     esi, 0FFFFFFFFh
0x18012c772  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18012c779  mov     r10, [rsp+1E0h+var_180]
0x18012c77e  mov     r11, [rbx+28h]
0x18012c782  mov     [rsp+1E0h+var_188], r11
0x18012c787  cmp     byte ptr [r10+67h], 0
0x18012c78c  jnz     loc_18012C857
0x18012c792  mov     rax, [rbp+0E0h+var_138]
0x18012c796  cmp     byte ptr [rax], 8
0x18012c799  jbe     short loc_18012C7BC
0x18012c79b  mov     rdx, [rbx+48h]
0x18012c79f  mov     [rbp+0E0h+var_160], rdx
0x18012c7a3  mov     qword ptr [rbp+0E0h+var_D0], rdx
0x18012c7a7  jmp     short loc_18012C7C0
0x18012c7a9  mov     rdi, [rsp+1E0h+var_1A0]
0x18012c7ae  jmp     short loc_18012C7C0
0x18012c7b0  mov     rdi, [rsp+1E0h+var_1A0]
0x18012c7b5  mov     rbx, [rsp+1E0h+var_198]
0x18012c7ba  jmp     short loc_18012C7C0
0x18012c7bc  mov     rdx, [rbp+0E0h+var_160]
0x18012c7c0  mov     rax, [rbx+50h]
0x18012c7c4  inc     esi
0x18012c7c6  inc     r14
0x18012c7c9  test    rax, rax
0x18012c7cc  jnz     loc_18012C85F
0x18012c7d2  cmp     esi, [r11]
0x18012c7d5  jl      loc_18012C570
0x18012c7db  mov     [rsp+1E0h+var_170], rdx
0x18012c7e0  mov     rax, [rbx+30h]
0x18012c7e4  test    rax, rax
0x18012c7e7  jz      short loc_18012C803
0x18012c7e9  cmp     byte ptr [rax], 2Ch ; ','
0x18012c7ec  jnz     short loc_18012C803
0x18012c7ee  test    dword ptr [r10+60h], 8000h
0x18012c7f6  jnz     short loc_18012C803
0x18012c7f8  mov     rdx, rbx
0x18012c7fb  mov     rcx, rdi
0x18012c7fe  call    propagateConstants
0x18012c803  mov     rsi, [rsp+1E0h+var_180]
0x18012c808  test    dword ptr [rsi+60h], 201h
0x18012c80f  jnz     loc_18012C8BD
0x18012c815  mov     rdx, rbx
  ... truncated ...
```
