# sqlite3Select

- ea: `0x1800971f0`
- end: `0x18009a95b`
- name: `sqlite3Select`
- size: `14187`
- prototype: ``
- caller_count: `12`
- callee_count: `62`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030790`
- `0x180042af0`
- `0x18004e7e0`
- `0x18004f6d0`
- `0x18006c2f0`
- `0x18006cf60`
- `0x180073a20`
- `0x180084b20`
- `0x180088910`
- `0x1800971f0`
- `0x1800c2290`
- `0x1800d8b00`

## callees

- `0x180005980`
- `0x180023dd0`
- `0x180025870`
- `0x180031c50`
- `0x180033e20`
- `0x180039a90`
- `0x18003a790`
- `0x18003bd50`
- `0x18003c440`
- `0x18003fa50`
- `0x180041ec0`
- `0x180044640`
- `0x180044c80`
- `0x180046c20`
- `0x18004c5e0`
- `0x18004dba0`
- `0x18004e7e0`
- `0x180057d60`
- `0x180058400`
- `0x18005bc70`
- `0x18005bf90`
- `0x18005eb40`
- `0x180060370`
- `0x1800658d0`
- `0x180071400`
- `0x1800714d0`
- `0x1800743d0`
- `0x1800753a0`
- `0x180075620`
- `0x180077210`
- `0x180078fc0`
- `0x1800795a0`
- `0x1800798f0`
- `0x18007a1f0`
- `0x18007a580`
- `0x18007a670`
- `0x18007a980`
- `0x18007f110`
- `0x180086c70`
- `0x180086d20`
- `0x180088560`
- `0x1800896a0`
- `0x18008c160`
- `0x1800971f0`
- `0x18009b310`
- `0x1800a2fd0`
- `0x1800a3040`
- `0x1800a36a0`
- `0x1800a3b40`
- `0x1800a4140`

## string_xrefs

- `0x1800992c1`: `USE TEMP B-TREE FOR %s`
- `0x18009a871`: `USE TEMP B-TREE FOR %s`

## pseudocode

```c
__int64 __fastcall sqlite3Select(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int128 *v4; // r14
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 *v7; // r13
  bool v8; // cc
  BOOL v9; // r15d
  __int64 *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdi
  int v13; // r11d
  const char *v14; // r8
  int *v15; // r10
  bool v16; // zf
  BOOL v17; // r12d
  int v18; // edi
  __int64 v19; // rdx
  unsigned int *v20; // rsi
  __int64 v21; // r14
  __int64 v22; // r15
  int v23; // eax
  char v24; // al
  signed int v25; // eax
  int i; // edx
  __int64 v27; // rcx
  char v28; // al
  char v29; // al
  int j; // edx
  __int64 v31; // rcx
  int v32; // r8d
  int v33; // ecx
  int v34; // eax
  unsigned int v35; // r9d
  __int64 v37; // rcx
  _BYTE *v38; // rax
  __int64 v39; // r12
  signed int v40; // r11d
  unsigned int *v41; // rcx
  __int64 v42; // r15
  unsigned int *v43; // r14
  __int64 v44; // r8
  __int64 v45; // rdi
  int v46; // r10d
  int v47; // r11d
  __int64 v48; // rax
  __int64 v49; // rsi
  __int64 v50; // rax
  __int64 v51; // rcx
  _DWORD *v52; // r8
  __int64 v53; // r11
  int k; // edx
  __int16 v55; // cx
  unsigned __int16 v56; // cx
  char v57; // al
  int v58; // edi
  unsigned int v59; // r9d
  __int64 v60; // r10
  unsigned __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  unsigned int *v64; // rsi
  unsigned int *v65; // rdi
  __int64 v66; // r12
  __int64 v67; // rax
  _DWORD *v68; // r15
  int v69; // r14d
  __int64 v70; // rax
  char v71; // cl
  signed int v72; // esi
  int v73; // eax
  __int64 v74; // rsi
  __int64 v75; // r8
  unsigned int v76; // edi
  __int64 v77; // rcx
  unsigned int v78; // eax
  __int64 v79; // r14
  __int64 v80; // rdi
  __int64 v81; // r9
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rdx
  unsigned int v87; // eax
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rdx
  __int64 v92; // r9
  __int64 v93; // r8
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rdi
  __int64 v100; // r9
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // rcx
  __int64 v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r9
  __int64 v108; // r8
  __int64 v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rdx
  __int64 v112; // rdi
  __int64 v113; // rsi
  __int64 v114; // rcx
  __int64 v115; // rax
  unsigned int *v116; // r8
  unsigned int v117; // r14d
  __int64 v118; // r9
  int v119; // eax
  __int64 v120; // rcx
  __int64 v121; // rax
  int v122; // eax
  unsigned int *v123; // r9
  __int64 v124; // r10
  __int64 v125; // r11
  __int64 *v126; // rax
  __int64 v127; // rcx
  __int64 v128; // r8
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rdx
  __int64 *v132; // rax
  __int64 v133; // rcx
  __int64 v134; // rdx
  int *v135; // rsi
  _DWORD *v136; // r15
  int v137; // ecx
  __int64 v138; // r14
  char v139; // r12
  _DWORD *v140; // r13
  int v141; // edi
  __int64 v142; // rax
  __int64 v143; // rdi
  __int64 v144; // r8
  int v145; // r9d
  __int64 v146; // rsi
  int v147; // ecx
  __int64 v148; // r9
  __int64 v149; // rcx
  __int64 v150; // rax
  __int64 v151; // rdx
  int v152; // eax
  __int64 v153; // rdx
  int *v154; // rdi
  int v155; // edx
  int m; // esi
  int *v157; // rdi
  __int64 v158; // rdx
  _QWORD *v159; // rcx
  int v160; // ecx
  __int64 v161; // rax
  _QWORD *v162; // rsi
  __int64 v163; // r10
  __int64 v164; // rax
  unsigned int v165; // r14d
  __int64 v166; // rax
  __int64 v167; // rsi
  __int64 v168; // rdi
  __int64 v169; // rcx
  __int64 v170; // rax
  __int64 v171; // rdx
  int v172; // eax
  __int64 v173; // rdx
  __int64 v174; // rcx
  __int64 v175; // rsi
  __int16 v176; // di
  __int64 v177; // rax
  __int64 v178; // rdi
  int v179; // r10d
  __int16 v180; // ax
  int v181; // eax
  _DWORD *v182; // r8
  int v183; // edx
  int v184; // eax
  __int64 v185; // rax
  int v186; // r14d
  int v187; // r14d
  unsigned int v188; // r12d
  int v189; // r15d
  unsigned int v190; // esi
  __int64 v191; // rcx
  __int64 v192; // rcx
  __int64 v193; // rax
  __int64 v194; // rcx
  int v195; // r14d
  int v196; // edi
  __int64 v197; // rcx
  int v198; // r15d
  __int64 v199; // rcx
  int v200; // esi
  __int64 v201; // rsi
  __int64 v202; // rdx
  int *v203; // rax
  int v204; // ecx
  _DWORD *n; // rdx
  int v206; // ecx
  _DWORD *ii; // rdx
  _DWORD *v208; // r8
  int v209; // eax
  int v210; // edx
  __int64 v211; // rcx
  int v212; // edi
  __int64 v213; // rax
  _DWORD *v214; // r8
  unsigned __int64 v215; // r12
  _QWORD *v216; // rax
  _QWORD *v217; // rcx
  _QWORD *v218; // rdi
  _QWORD *v219; // rcx
  __int64 v220; // r15
  int v221; // eax
  int *v222; // r14
  __int64 *v223; // rdi
  int v224; // esi
  __int64 v225; // rdx
  _DWORD *v226; // r14
  __int64 *v227; // rdi
  int v228; // esi
  __int64 v229; // rdx
  __int64 v230; // rdx
  _QWORD *v231; // rdi
  __int64 *v232; // rax
  __int64 v233; // r10
  __int64 v234; // r11
  _BYTE *v235; // r10
  const char *v236; // r9
  _BYTE *jj; // r8
  __int64 v238; // rdx
  __int64 v239; // rax
  unsigned __int8 v240; // r15
  char v241; // di
  const char *kk; // r8
  __int64 v243; // rdx
  __int64 v244; // rax
  __int64 v245; // rax
  __int64 v246; // r14
  int *appended; // rsi
  unsigned __int16 v248; // r13
  int *v249; // rax
  __int64 v250; // rax
  __int64 v251; // rcx
  __int64 v252; // rdx
  __int64 v253; // rdi
  int *v254; // rax
  __int64 v255; // rax
  int v256; // ecx
  __int64 v257; // rax
  __int64 v258; // rax
  __int64 v259; // r10
  __int64 v260; // rdi
  __int64 v261; // r9
  __int64 v262; // r8
  __int64 v263; // rcx
  __int64 v264; // rax
  __int64 v265; // rdx
  int v266; // eax
  __int64 v267; // rdx
  unsigned int v268; // r8d
  unsigned int v269; // eax
  unsigned int v270; // r15d
  __int64 v271; // r9
  unsigned int v272; // r14d
  unsigned int v273; // edi
  __int64 v274; // rcx
  __int64 v275; // rcx
  __int64 v276; // rax
  __int64 v277; // rcx
  unsigned int v278; // r8d
  __int64 v279; // rcx
  __int64 v280; // rax
  __int64 v281; // rcx
  __int64 v282; // rcx
  __int64 v283; // rax
  __int64 v284; // rdx
  __int16 v285; // ax
  __int64 v286; // r8
  _BYTE *v287; // r14
  unsigned int v288; // eax
  _QWORD *v289; // rdi
  int v290; // r9d
  int v291; // edx
  __int64 v292; // r8
  int v293; // eax
  int v294; // edx
  int v295; // ecx
  bool v296; // sf
  unsigned int v297; // r15d
  unsigned int v298; // esi
  const char *v299; // r9
  _QWORD *v300; // rdi
  int v301; // r15d
  signed int v302; // esi
  int v303; // r10d
  __int64 v304; // r9
  int v305; // r8d
  int v306; // edx
  int v307; // eax
  int v308; // eax
  char v309; // al
  unsigned int v310; // r13d
  unsigned __int8 v311; // al
  int v312; // ecx
  int v313; // eax
  int v314; // r14d
  __int64 v315; // rdi
  __int64 v316; // rdi
  unsigned int v317; // eax
  __int64 v318; // rdx
  char v319; // al
  unsigned int v320; // edi
  unsigned __int8 v321; // al
  __int64 v322; // rcx
  __int64 v323; // rcx
  __int64 v324; // rax
  __int64 v325; // rdx
  __int64 v326; // rcx
  __int64 v327; // r8
  __int64 v328; // rcx
  __int64 v329; // rax
  __int64 v330; // rdx
  __int64 v331; // rax
  _QWORD *v332; // rdi
  __int64 v333; // rax
  char v334; // al
  unsigned __int8 v335; // al
  __int64 v336; // rcx
  __int64 v337; // rcx
  __int64 v338; // rax
  __int64 v339; // rdx
  __int64 v340; // rcx
  __int64 v341; // rcx
  __int64 v342; // rax
  __int64 v343; // rdx
  int v344; // edi
  int v345; // edi
  __int64 v346; // r13
  __int64 v347; // r8
  __int64 v348; // rax
  __int64 v349; // rcx
  __int64 v350; // rdx
  int *v351; // rsi
  unsigned int v352; // r14d
  unsigned int v353; // esi
  _DWORD *v354; // rax
  __int64 v355; // rcx
  __int64 v356; // rcx
  __int64 v357; // rax
  __int64 v358; // rdx
  __int64 v359; // rdi
  unsigned int v360; // eax
  __int64 v361; // rdx
  _DWORD *v362; // r10
  __int64 v363; // r8
  int v364; // r9d
  unsigned int v365; // r14d
  int v366; // eax
  __int64 v367; // rcx
  __int64 v368; // rax
  __int64 v369; // rdx
  __int64 v370; // rdx
  __int64 v371; // rdi
  __int64 v372; // r8
  __int64 v373; // rax
  __int64 v374; // rcx
  __int64 v375; // rdx
  int v376; // r11d
  __int64 v377; // r10
  __int64 v378; // rcx
  __int64 v379; // rcx
  __int64 v380; // rax
  __int64 v381; // rdx
  __int64 v382; // rcx
  unsigned int v383; // r15d
  unsigned int v384; // r14d
  __int64 v385; // r8
  __int64 v386; // rcx
  __int64 v387; // rax
  __int64 v388; // rdx
  __int64 v389; // rcx
  __int64 v390; // rcx
  __int64 v391; // rax
  __int64 v392; // rdx
  __int64 v393; // rcx
  __int64 v394; // rcx
  __int64 v395; // rax
  __int64 v396; // rdx
  __int64 *v397; // rax
  unsigned int v398; // edi
  __int64 v399; // r9
  __int64 v400; // rcx
  __int64 v401; // rcx
  __int64 v402; // rax
  __int64 v403; // rdx
  __int64 v404; // rcx
  __int64 v405; // r8
  __int64 v406; // rcx
  __int64 v407; // rax
  __int64 v408; // rdx
  __int64 v409; // r8
  __int64 v410; // rcx
  __int64 v411; // rcx
  __int64 v412; // rax
  __int64 v413; // rdx
  __int64 v414; // rcx
  unsigned int v415; // r13d
  __int64 v416; // rcx
  __int64 v417; // rax
  __int64 v418; // rsi
  __int64 v419; // rcx
  __int64 v420; // rax
  __int64 v421; // rdx
  __int64 v422; // rcx
  __int64 v423; // rcx
  __int64 v424; // rax
  __int64 v425; // rcx
  int v426; // r15d
  __int64 v427; // rax
  unsigned int v428; // r15d
  unsigned int v429; // r8d
  unsigned int v430; // edi
  __int64 v431; // rcx
  __int64 v432; // rax
  __int64 v433; // rdx
  __int64 v434; // rcx
  __int64 v435; // rcx
  __int64 v436; // rax
  __int64 v437; // rcx
  __int64 v438; // rcx
  __int64 v439; // rax
  __int64 v440; // rcx
  int v441; // edx
  __int64 v442; // rcx
  __int64 v443; // rcx
  __int64 v444; // rax
  __int64 v445; // rcx
  __int64 v446; // rcx
  __int64 v447; // rax
  __int64 v448; // rdx
  __int64 v449; // r14
  const char **v450; // r14
  __int64 v451; // rdx
  const char *v452; // rcx
  signed int v453; // esi
  _QWORD *v454; // r10
  __int64 v455; // rdx
  unsigned int v456; // r13d
  __int64 v457; // r15
  const char *mm; // rdi
  _QWORD *v459; // rcx
  int v460; // eax
  const char *nn; // rax
  __int16 v462; // cx
  __int64 v463; // rcx
  __int64 v464; // rcx
  __int64 v465; // rax
  __int64 v466; // rdx
  __int64 v467; // rax
  __int64 v468; // rdx
  __int64 v469; // rdx
  _QWORD *v470; // rsi
  unsigned int v471; // r8d
  __int64 v472; // rcx
  __int64 v473; // rcx
  __int64 v474; // rax
  __int64 v475; // rdx
  __int64 v476; // rcx
  __int64 v477; // rcx
  __int64 v478; // rax
  const char *v479; // rax
  const char *v480; // rcx
  int v481; // r8d
  unsigned int v482; // esi
  __int64 v483; // rdi
  __int16 v484; // r14
  unsigned int v485; // edx
  __int64 v486; // r9
  __int64 v487; // rcx
  __int64 v488; // rcx
  __int64 v489; // rax
  int *v490; // rax
  __int64 v491; // rax
  __int64 v492; // rdi
  unsigned int v493; // r14d
  __int64 v494; // r8
  __int64 v495; // rcx
  __int64 v496; // rcx
  __int64 v497; // rax
  __int64 v498; // rdx
  int v499; // edx
  __int64 v500; // r8
  __int64 v501; // rcx
  unsigned int v502; // r8d
  int v503; // r13d
  __int64 v504; // rcx
  __int64 v505; // rax
  __int64 v506; // rcx
  int v507; // edx
  _QWORD *v508; // rdx
  __int64 v509; // [rsp+20h] [rbp-E0h]
  __int64 v510; // [rsp+20h] [rbp-E0h]
  __int64 v511; // [rsp+20h] [rbp-E0h]
  __int64 v512; // [rsp+20h] [rbp-E0h]
  __int64 v513; // [rsp+20h] [rbp-E0h]
  int v514; // [rsp+38h] [rbp-C8h]
  signed int *v515; // [rsp+40h] [rbp-C0h]
  unsigned int v516; // [rsp+40h] [rbp-C0h]
  __int64 v517; // [rsp+48h] [rbp-B8h]
  _DWORD *v518; // [rsp+48h] [rbp-B8h]
  __int64 v519; // [rsp+50h] [rbp-B0h]
  unsigned int v520; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v521; // [rsp+5Ch] [rbp-A4h]
  int v522; // [rsp+60h] [rbp-A0h]
  unsigned int v523; // [rsp+64h] [rbp-9Ch]
  int v524; // [rsp+68h] [rbp-98h]
  _DWORD *v525; // [rsp+70h] [rbp-90h]
  unsigned int v526; // [rsp+78h] [rbp-88h]
  __int64 v527; // [rsp+80h] [rbp-80h]
  __int64 v528; // [rsp+88h] [rbp-78h]
  int v529; // [rsp+90h] [rbp-70h]
  unsigned int v530; // [rsp+94h] [rbp-6Ch]
  unsigned int v531; // [rsp+98h] [rbp-68h]
  int v532; // [rsp+9Ch] [rbp-64h]
  _QWORD *v533; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall *v534)(); // [rsp+A8h] [rbp-58h]
  __int128 v535; // [rsp+B0h] [rbp-50h]
  __int128 v536; // [rsp+C0h] [rbp-40h]
  char v537; // [rsp+D0h] [rbp-30h] BYREF
  char v538; // [rsp+D1h] [rbp-2Fh]
  unsigned int v539; // [rsp+D4h] [rbp-2Ch]
  int v540; // [rsp+D8h] [rbp-28h]
  unsigned int v541; // [rsp+E0h] [rbp-20h]
  unsigned int v542; // [rsp+E4h] [rbp-1Ch]
  __int64 v543; // [rsp+E8h] [rbp-18h]
  int *v544; // [rsp+F0h] [rbp-10h]
  __int64 v545; // [rsp+F8h] [rbp-8h]
  int *v546; // [rsp+100h] [rbp+0h]
  __int64 v547; // [rsp+108h] [rbp+8h]
  __int64 v548; // [rsp+110h] [rbp+10h]
  __int128 v549; // [rsp+118h] [rbp+18h] BYREF
  __int128 v550; // [rsp+128h] [rbp+28h]
  __int128 v551; // [rsp+138h] [rbp+38h]
  _DWORD *v552; // [rsp+148h] [rbp+48h]
  _QWORD v553[3]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v554; // [rsp+168h] [rbp+68h]
  __int128 v555; // [rsp+178h] [rbp+78h]
  unsigned int v559; // [rsp+1F8h] [rbp+F8h]
  char v560; // [rsp+1F8h] [rbp+F8h]
  int v561; // [rsp+1F8h] [rbp+F8h]
  int v562; // [rsp+1F8h] [rbp+F8h]

  v3 = a1[2];
  v4 = (__int128 *)a3;
  v5 = *a1;
  v6 = a2;
  v519 = *a1;
  v7 = a1;
  v543 = v3;
  if ( !v3 )
  {
    if ( !a1[21] && (*(_BYTE *)(v5 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    v3 = sqlite3VdbeCreate(a1);
    v543 = v3;
  }
  if ( !v6 || *((_DWORD *)v7 + 12) || (unsigned int)sqlite3AuthCheck((_DWORD)v7, 21, 0, 0, 0) )
    return 1;
  v8 = *(_BYTE *)v4 <= 6u;
  v9 = 1;
  v545 = 1;
  if ( v8 )
  {
    if ( *(_QWORD *)(v6 + 72) )
    {
      sqlite3ParserAddCleanup(v7, sqlite3ExprListDelete);
      *(_QWORD *)(v6 + 72) = 0;
    }
    *(_DWORD *)(v6 + 4) &= ~1u;
    *(_DWORD *)(v6 + 4) |= 0x400000u;
  }
  sqlite3SelectPrep(v7, v6, 0);
  v10 = &qword_18013FEA8;
  if ( *((_DWORD *)v7 + 12) )
    goto LABEL_79;
  if ( (*(_DWORD *)(v6 + 4) & 0x800000) != 0 )
  {
    v11 = *(_QWORD *)(v6 + 40);
    v12 = v11 + 8;
    if ( (unsigned int)sameSrcAlias(v11 + 8, v11, &qword_18013FEA8) )
    {
      v14 = *(const char **)(v12 + 24);
      if ( !v14 )
        v14 = **(const char ***)(v12 + 32);
      sqlite3ErrorMsg(v7, "target object/alias may not appear in FROM clause: %s", v14);
      goto LABEL_78;
    }
    *(_DWORD *)(v6 + 4) = v13 & 0xFF7FFFFF;
  }
  if ( *(_BYTE *)v4 == 9 )
    sqlite3GenerateColumnNames(v7, v6, v10);
  if ( (unsigned int)sqlite3WindowRewrite(v7, v6, v10) )
  {
LABEL_78:
    v10 = &qword_18013FEA8;
LABEL_79:
    v37 = *((int *)v7 + 78);
    if ( (_DWORD)v37 )
    {
      v508 = (_QWORD *)v7[2];
      if ( !*(_BYTE *)(*v508 + 103LL) )
        v10 = (__int64 *)(v508[17] + 24 * v37);
      *((_DWORD *)v7 + 78) = *((_DWORD *)v10 + 2);
      return v9;
    }
    else
    {
      *((_DWORD *)v7 + 78) = 0;
      return v9;
    }
  }
  v15 = *(int **)(v6 + 40);
  v16 = (*(_DWORD *)(v6 + 4) & 8) == 0;
  v526 = *(_DWORD *)(v6 + 4) & 8;
  v17 = !v16;
  v18 = 0;
  v515 = v15;
  v525 = *(_DWORD **)(v6 + 72);
  v550 = 0;
  v549 = (unsigned __int64)v525;
  v551 = 0;
  if ( !*(_QWORD *)(v6 + 80) )
  {
    v19 = v519;
    while ( v18 < *v15 )
    {
      v20 = (unsigned int *)&v15[26 * v18];
      v21 = *((_QWORD *)v20 + 6);
      v22 = *((_QWORD *)v20 + 5);
      if ( (v20[17] & 0x48) != 0 )
      {
        v23 = sqlite3ExprImpliesNonNullRow(*(_QWORD *)(a2 + 48), v20[19], v20[17] & 0x40);
        v19 = v519;
        if ( !v23 || (*(_DWORD *)(v519 + 96) & 0x2000) != 0 )
        {
          v15 = v515;
        }
        else
        {
          v24 = *((_BYTE *)v20 + 68);
          if ( (v24 & 8) != 0 )
          {
            if ( (v24 & 0x10) != 0 )
              v24 &= ~8u;
            else
              v24 &= 0xD7u;
            *((_BYTE *)v20 + 68) = v24;
          }
          if ( (v24 & 0x40) != 0 )
          {
            v25 = *v515;
            for ( i = v18 + 1; i < *v515; ++i )
            {
              v27 = 26LL * i;
              v28 = v515[v27 + 17];
              if ( (v28 & 0x10) != 0 )
              {
                if ( (v28 & 8) != 0 )
                  v29 = v28 & 0xEF;
                else
                  v29 = v28 & 0xCF;
                LOBYTE(v515[v27 + 17]) = v29;
              }
              v25 = *v515;
            }
            for ( j = v25 - 1; j >= v18; --j )
            {
              v31 = 26LL * j;
              LOBYTE(v515[v31 + 17]) &= ~0x40u;
              if ( (v515[v31 + 17] & 0x10) != 0 )
                break;
            }
          }
          unsetJoinExpr(*(_QWORD *)(a2 + 48), v20[19], v515[17] & 0x40);
          v19 = v519;
        }
      }
      if ( !v21 )
        goto LABEL_70;
      v32 = *(__int16 *)(v22 + 54);
      v33 = **(_DWORD **)(v21 + 32);
      if ( v32 != v33 )
      {
        sqlite3ErrorMsg(v7, "expected %d columns for '%s' but got %d", v32, *(const char **)v22, v33);
        goto LABEL_77;
      }
      if ( (v20[18] & 0x100) != 0 && !*(_BYTE *)(*((_QWORD *)v20 + 13) + 18LL) )
      {
LABEL_70:
        v6 = a2;
LABEL_71:
        v4 = (__int128 *)a3;
        goto LABEL_72;
      }
      v34 = *(_DWORD *)(v21 + 4);
      v6 = a2;
      if ( (v34 & 8) != 0 )
        goto LABEL_71;
      if ( *(_QWORD *)(v21 + 72) )
      {
        if ( !*(_QWORD *)(a2 + 72) && *v15 <= 1
          || *(_QWORD *)(v21 + 96)
          || (v34 & 0x8000000) != 0
          || (*(_DWORD *)(a2 + 4) & 0x8000000) != 0
          || (*(_DWORD *)(v19 + 96) & 0x40000) != 0 )
        {
          if ( !v18 && (*(_DWORD *)(a2 + 4) & 0x40000) != 0 && (*v15 == 1 || (v15[43] & 0x22) != 0) )
            goto LABEL_71;
        }
        else
        {
          sqlite3ParserAddCleanup(v7, sqlite3ExprListDelete);
          *(_QWORD *)(v21 + 72) = 0;
        }
      }
      if ( (unsigned int)flattenSubquery(v7, a2, (unsigned int)v18, v17) )
      {
        if ( *((_DWORD *)v7 + 12) )
          goto LABEL_77;
        v18 = -1;
      }
      v19 = v519;
      if ( *(_BYTE *)(v519 + 103) )
        goto LABEL_77;
      v4 = (__int128 *)a3;
      v15 = *(int **)(a2 + 40);
      v515 = v15;
      if ( *(_BYTE *)a3 > 8u )
      {
        v525 = *(_DWORD **)(a2 + 72);
        *(_QWORD *)&v549 = v525;
      }
LABEL_72:
      ++v18;
      if ( *(_QWORD *)(v6 + 80) )
        goto LABEL_73;
    }
    v38 = *(_BYTE **)(v6 + 48);
    v39 = v519;
    if ( v38 && *v38 == 44 && (*(_DWORD *)(v519 + 96) & 0x8000) == 0 )
    {
      propagateConstants(v7, v6);
      v15 = v515;
    }
    if ( (*(_DWORD *)(v519 + 96) & 0x201) != 0 )
    {
LABEL_89:
      v515 = v15;
    }
    else
    {
      if ( (unsigned int)countOfViewOptimization(v7, v6) )
      {
        if ( !*(_BYTE *)(v519 + 103) )
        {
          v15 = *(int **)(v6 + 40);
          goto LABEL_89;
        }
LABEL_77:
        v9 = 1;
        goto LABEL_78;
      }
      v15 = v515;
    }
    v40 = 0;
    v559 = 0;
    if ( *v15 > 0 )
    {
      v41 = (unsigned int *)(v15 + 2);
      while ( 1 )
      {
        v42 = 26LL * v40;
        v517 = v42 * 4;
        v43 = &v41[v42];
        if ( !*(_QWORD *)&v15[v42 + 22] )
        {
          v44 = *((_QWORD *)v43 + 2);
          if ( v44 )
          {
            sqlite3AuthCheck((_DWORD)v7, 20, v44, (unsigned int)byte_180122168, *((_QWORD *)v43 + 1));
            v15 = v515;
            v40 = v559;
          }
        }
        v45 = *((_QWORD *)v43 + 5);
        v527 = v45;
        if ( v45 )
          break;
LABEL_194:
        ++v40;
        v41 = (unsigned int *)(v15 + 2);
        v559 = v40;
        if ( v40 >= *v15 )
          goto LABEL_195;
      }
      v520 = 0;
      heightOfSelect(v6, &v520);
      *((_DWORD *)v7 + 77) += v520;
      if ( (*(_DWORD *)(v39 + 96) & 0x1000) == 0 )
      {
        if ( (v43[16] & 0x100) == 0 || (v48 = *((_QWORD *)v43 + 12), *(_BYTE *)(v48 + 18)) && *(int *)v48 < 2 )
          pushDownWhereTerms((_DWORD)v7, v45, *(_QWORD *)(v6 + 48), v46, v47);
      }
      if ( (*(_DWORD *)(v39 + 96) & 0x4000000) == 0 && (v43[16] & 0x108) == 0 )
      {
        v49 = *((_QWORD *)v43 + 5);
        if ( (*(_BYTE *)(v49 + 4) & 9) == 0 )
        {
          v50 = *((_QWORD *)v43 + 5);
          while ( 1 )
          {
            v51 = *(_QWORD *)(v50 + 80);
            if ( v51 )
            {
              if ( *(_BYTE *)v50 != 0x87 )
                break;
            }
            if ( *(_QWORD *)(v50 + 112) )
              break;
            v50 = *(_QWORD *)(v50 + 80);
            if ( !v51 )
            {
              v52 = *(_DWORD **)(v49 + 72);
              v53 = *(_QWORD *)&v515[v42 + 22];
              if ( v52 )
              {
                for ( k = 0; k < *v52; ++k )
                {
                  v55 = v52[8 * k + 8];
                  if ( v55 )
                  {
                    v56 = v55 - 1;
                    v57 = 63;
                    if ( v56 < 0x40u )
                      v57 = v56;
                    v53 |= 1LL << v57;
                  }
                }
              }
              v58 = *(__int16 *)(*((_QWORD *)v43 + 4) + 54LL);
              if ( v58 > 0 )
              {
                v59 = 0;
                v60 = 1;
                do
                {
                  v61 = 0x8000000000000000uLL;
                  if ( v59 < 0x3F )
                    v61 = v60;
                  if ( (v61 & v53) == 0 )
                  {
                    v62 = v49;
                    do
                    {
                      v63 = *(_QWORD *)(32LL * v59 + *(_QWORD *)(v62 + 32) + 8);
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
                  ++v59;
                  v60 = __ROL8__(v60, 1);
                }
                while ( (int)v59 < v58 );
                v3 = v543;
              }
              break;
            }
          }
        }
      }
      v64 = (unsigned int *)v515;
      v65 = v43;
      v66 = v7[46];
      v67 = *(_QWORD *)&v515[v42 + 6];
      v68 = v43 + 16;
      v7[46] = v67;
      v69 = v43[16] & 0x100;
      if ( v69 )
      {
        v70 = *((_QWORD *)v65 + 12);
        v71 = *(_BYTE *)(v70 + 18);
        if ( !v71 || *(int *)v70 >= 2 && v71 != 2 )
          goto LABEL_148;
      }
      if ( (v515[17] & 0x40) == 0 && (*(_DWORD *)(*v7 + 96) & 0x2000000) == 0 )
      {
        v72 = *v515;
        if ( !isSelfJoinView(v515, v65, v559 + 1, (unsigned int)*v515) )
        {
          v73 = *(_DWORD *)(a2 + 4);
          if ( !v559 )
          {
            if ( v72 == 1 || (v64 = (unsigned int *)v515, (v515[43] & 2) != 0) || (v73 & 0x10000000) == 0 )
            {
LABEL_138:
              v74 = *(int *)(v3 + 144);
              v75 = (unsigned int)++*((_DWORD *)v7 + 14);
              v76 = v74 + 1;
              *(signed int *)((char *)v515 + v517 + 60) = v75;
              v77 = *(int *)(v3 + 144);
              if ( *(_DWORD *)(v3 + 148) > (int)v77 )
              {
                *(_DWORD *)(v3 + 144) = v77 + 1;
                v84 = 3 * v77;
                v85 = *(_QWORD *)(v3 + 136);
                *(_DWORD *)(v85 + 8 * v84) = 11;
                *(_DWORD *)(v85 + 8 * v84 + 4) = v75;
                *(_DWORD *)(v85 + 8 * v84 + 12) = v76;
                v86 = v85 + 8 * v84;
                *(_DWORD *)(v86 + 8) = 0;
                *(_QWORD *)(v86 + 16) = 0;
              }
              else
              {
                LODWORD(v509) = v74 + 1;
                growOp3(v3, 11, v75, 0, v509);
              }
              *((_QWORD *)&v535 + 1) = 0;
              LODWORD(v535) = 0;
              LOBYTE(v533) = 13;
              *(signed int *)((char *)v515 + v517 + 56) = v76;
              HIDWORD(v533) = *(signed int *)((char *)v515 + v517 + 60);
              v534 = 0;
              sqlite3VdbeExplain(v7, 1, "CO-ROUTINE %!S", (char *)v515 + v517 + 8);
              sqlite3Select(v7, v527, &v533);
              *(_WORD *)(*(_QWORD *)((char *)v515 + v517 + 40) + 58LL) = *(_WORD *)(v527 + 2);
              v87 = HIDWORD(v534);
              v88 = *(unsigned int *)((char *)v515 + v517 + 60);
              *v68 |= 0x20u;
              *(signed int *)((char *)v515 + v517 + 64) = v87;
              sqlite3VdbeEndCoroutine(v3, v88);
              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                dword_18013FEB0 = *(_DWORD *)(v3 + 144);
              else
                *(_DWORD *)(*(_QWORD *)(v3 + 136) + 24 * v74 + 8) = *(_DWORD *)(v3 + 144);
              *((_BYTE *)v7 + 31) = 0;
              *((_DWORD *)v7 + 10) = 0;
              goto LABEL_192;
            }
            goto LABEL_147;
          }
          if ( (v73 & 0x10000000) == 0 )
          {
            v78 = v559;
            if ( (v65[15] & 0x22) == 0 )
            {
              while ( v78 )
              {
                v65 -= 26;
                if ( !*((_QWORD *)v65 + 5) )
                {
                  --v78;
                  if ( (v65[15] & 0x22) == 0 )
                    continue;
                }
                goto LABEL_146;
              }
              goto LABEL_138;
            }
          }
        }
LABEL_146:
        v64 = (unsigned int *)v515;
      }
LABEL_147:
      if ( !v69 )
      {
        v79 = v517;
        goto LABEL_163;
      }
LABEL_148:
      v79 = v517;
      v80 = *(_QWORD *)((char *)v64 + v517 + 104);
      v81 = *(unsigned int *)(v80 + 4);
      if ( (int)v81 > 0 )
      {
        v82 = *(int *)(v3 + 144);
        v83 = *(unsigned int *)(v80 + 8);
        if ( *(_DWORD *)(v3 + 148) > (int)v82 )
        {
          *(_DWORD *)(v3 + 144) = v82 + 1;
          v89 = 3 * v82;
          v90 = *(_QWORD *)(v3 + 136);
          *(_DWORD *)(v90 + 8 * v89) = 10;
          *(_DWORD *)(v90 + 8 * v89 + 4) = v83;
          *(_DWORD *)(v90 + 8 * v89 + 8) = v81;
          v91 = v90 + 8 * v89;
          *(_DWORD *)(v91 + 12) = 0;
          *(_QWORD *)(v91 + 16) = 0;
        }
        else
        {
          LODWORD(v509) = 0;
          growOp3(v3, 10, v83, v81, v509);
        }
        v92 = *(unsigned int *)(v80 + 12);
        v93 = *(unsigned int *)((char *)v64 + v517 + 76);
        if ( (_DWORD)v93 != (_DWORD)v92 )
        {
          v94 = *(int *)(v3 + 144);
          if ( *(_DWORD *)(v3 + 148) <= (int)v94 )
          {
            LODWORD(v509) = 0;
            growOp3(v3, 115, v93, v92, v509);
            *(_WORD *)(v527 + 2) = *(_WORD *)(v80 + 16);
LABEL_192:
            if ( *(_BYTE *)(v519 + 103) )
              goto LABEL_77;
            v6 = a2;
            v520 = 0;
            heightOfSelect(a2, &v520);
            *((_DWORD *)v7 + 77) -= v520;
            v15 = v515;
            v40 = v559;
            v7[46] = v66;
            v39 = v519;
            goto LABEL_194;
          }
          *(_DWORD *)(v3 + 144) = v94 + 1;
          v95 = 3 * v94;
          v96 = *(_QWORD *)(v3 + 136);
          *(_DWORD *)(v96 + 8 * v95) = 115;
          *(_DWORD *)(v96 + 8 * v95 + 4) = v93;
          *(_DWORD *)(v96 + 8 * v95 + 8) = v92;
          v97 = v96 + 8 * v95;
          *(_DWORD *)(v97 + 12) = 0;
          *(_QWORD *)(v97 + 16) = 0;
        }
        *(_WORD *)(v527 + 2) = *(_WORD *)(v80 + 16);
        goto LABEL_192;
      }
LABEL_163:
      v98 = isSelfJoinView(v64, (char *)v64 + v79 + 8, 0, v559);
      v99 = v98;
      if ( v98 )
      {
        v100 = *(unsigned int *)(v98 + 48);
        if ( (_DWORD)v100 )
        {
          v101 = *(int *)(v3 + 144);
          v102 = *(unsigned int *)(v98 + 52);
          if ( *(_DWORD *)(v3 + 148) > (int)v101 )
          {
            *(_DWORD *)(v3 + 144) = v101 + 1;
            v103 = 3 * v101;
            v104 = *(_QWORD *)(v3 + 136);
            *(_DWORD *)(v104 + 8 * v103) = 10;
            *(_DWORD *)(v104 + 8 * v103 + 4) = v102;
            *(_DWORD *)(v104 + 8 * v103 + 8) = v100;
            v105 = v104 + 8 * v103;
            *(_DWORD *)(v105 + 12) = 0;
            *(_QWORD *)(v105 + 16) = 0;
          }
          else
          {
            LODWORD(v509) = 0;
            growOp3(v3, 10, v102, v100, v509);
          }
        }
        v106 = *(int *)(v3 + 144);
        v107 = *(unsigned int *)(v99 + 68);
        v108 = *(unsigned int *)((char *)v64 + v79 + 76);
        if ( *(_DWORD *)(v3 + 148) > (int)v106 )
        {
          *(_DWORD *)(v3 + 144) = v106 + 1;
          v109 = 3 * v106;
          v110 = *(_QWORD *)(v3 + 136);
          *(_DWORD *)(v110 + 8 * v109) = 115;
          *(_DWORD *)(v110 + 8 * v109 + 4) = v108;
          *(_DWORD *)(v110 + 8 * v109 + 8) = v107;
          v111 = v110 + 8 * v109;
          *(_DWORD *)(v111 + 12) = 0;
          *(_QWORD *)(v111 + 16) = 0;
        }
        else
        {
          LODWORD(v509) = 0;
          growOp3(v3, 115, v108, v107, v509);
        }
        *(_WORD *)(v527 + 2) = *(_WORD *)(*(_QWORD *)(v99 + 40) + 2LL);
      }
      else
      {
        ++*((_DWORD *)v7 + 14);
        LODWORD(v112) = 0;
        *(unsigned int *)((char *)v64 + v79 + 60) = *((_DWORD *)v7 + 14);
        v113 = *(int *)(v3 + 144);
        if ( *(_DWORD *)(v3 + 148) > (int)v113 )
        {
          *(_DWORD *)(v3 + 144) = v113 + 1;
          v114 = 3 * v113;
          v115 = *(_QWORD *)(v3 + 136);
          *(_QWORD *)(v115 + 8 * v114) = 9;
          *(_QWORD *)(v115 + 8 * v114 + 8) = 0;
          *(_QWORD *)(v115 + 8 * v114 + 16) = 0;
        }
        else
        {
          LODWORD(v509) = 0;
          LODWORD(v113) = growOp3(v3, 9, 0, 0, v509);
        }
        v116 = (unsigned int *)v515;
        v117 = v113 + 1;
        v118 = v517;
        *v68 |= 0x10u;
        v16 = (*(_BYTE *)v68 & 8) == 0;
        *(signed int *)((char *)v515 + v517 + 56) = v113 + 1;
        if ( v16 )
        {
          v112 = *(int *)(v3 + 144);
          if ( *(_DWORD *)(v3 + 148) > (int)v112 )
          {
            *(_DWORD *)(v3 + 144) = v112 + 1;
            v120 = 3 * v112;
            v121 = *(_QWORD *)(v3 + 136);
            *(_QWORD *)(v121 + 8 * v120) = 15;
            *(_QWORD *)(v121 + 8 * v120 + 8) = 0;
            *(_QWORD *)(v121 + 8 * v120 + 16) = 0;
          }
          else
          {
            LODWORD(v509) = 0;
            v119 = growOp3(v3, 15, 0, 0, v509);
            v116 = (unsigned int *)v515;
            LODWORD(v112) = v119;
            v118 = v517;
          }
        }
        v122 = *(unsigned int *)((char *)v116 + v118 + 76);
        LOBYTE(v533) = 12;
        HIDWORD(v533) = v122;
        v534 = 0;
        *((_QWORD *)&v535 + 1) = 0;
        LODWORD(v535) = 0;
        sqlite3VdbeExplain(v7, 1, "MATERIALIZE %!S", (char *)v116 + v118 + 8);
        sqlite3Select(v7, v527, &v533);
        v123 = (unsigned int *)v515;
        v124 = v517;
        v125 = v527;
        *(_WORD *)(*(_QWORD *)((char *)v515 + v517 + 40) + 58LL) = *(_WORD *)(v527 + 2);
        if ( (_DWORD)v112 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
            v126 = &qword_18013FEA8;
          else
            v126 = (__int64 *)(*(_QWORD *)(v3 + 136) + 24LL * (int)v112);
          *((_DWORD *)v126 + 2) = *(_DWORD *)(v3 + 144);
        }
        v127 = *(int *)(v3 + 144);
        v128 = *(unsigned int *)((char *)v515 + v517 + 60);
        if ( *(_DWORD *)(v3 + 148) > (int)v127 )
        {
          *(_DWORD *)(v3 + 144) = v127 + 1;
          v129 = 3 * v127;
          v130 = *(_QWORD *)(v3 + 136);
          *(_DWORD *)(v130 + 8 * v129) = 67;
          *(_DWORD *)(v130 + 8 * v129 + 4) = v128;
          *(_DWORD *)(v130 + 8 * v129 + 8) = v117;
          v131 = v130 + 8 * v129;
          *(_DWORD *)(v131 + 12) = 0;
          *(_QWORD *)(v131 + 16) = 0;
        }
        else
        {
          LODWORD(v509) = 0;
          growOp3(v3, 67, v128, v117, v509);
          v123 = (unsigned int *)v515;
          v124 = v517;
          v125 = v527;
        }
        if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
          v132 = &qword_18013FEA8;
        else
          v132 = (__int64 *)(*(_QWORD *)(v3 + 136) + 24LL * (int)v113);
        *((_DWORD *)v132 + 2) = *(_DWORD *)(v3 + 144);
        *((_BYTE *)v7 + 31) = 0;
        *((_DWORD *)v7 + 10) = 0;
        if ( (*v68 & 0x108) == 0x100 )
        {
          v133 = *(_QWORD *)((char *)v123 + v124 + 104);
          *(_DWORD *)(v133 + 4) = *(unsigned int *)((char *)v123 + v124 + 56);
          *(_DWORD *)(v133 + 8) = *(unsigned int *)((char *)v123 + v124 + 60);
          *(_DWORD *)(v133 + 12) = *(unsigned int *)((char *)v123 + v124 + 76);
          *(_WORD *)(v133 + 16) = *(_WORD *)(v125 + 2);
        }
      }
      goto LABEL_192;
    }
LABEL_195:
    v134 = a2;
    v135 = *(int **)(v6 + 32);
    v548 = 0;
    v136 = v525;
    v137 = *(_DWORD *)(a2 + 4);
    v138 = *(_QWORD *)(a2 + 48);
    v139 = v137 & 1;
    v140 = *(_DWORD **)(a2 + 56);
    v547 = *(_QWORD *)(a2 + 64);
    v544 = v135;
    v528 = v138;
    v518 = v140;
    v560 = v137 & 1;
    v537 = v137 & 1;
    if ( (v137 & 9) == 1 )
    {
      if ( !v525 )
      {
        if ( v135 )
          goto LABEL_208;
LABEL_206:
        if ( !*(_QWORD *)(v134 + 112) )
        {
          *(_DWORD *)(v134 + 4) = v137 & 0xFFFFFFFE;
          v140 = (_DWORD *)sqlite3ExprListDup(v519, v135, 0);
          v518 = v140;
          v139 = 2;
          v560 = 2;
          v537 = 2;
          *(_DWORD *)(a2 + 4) |= 8u;
          *(_QWORD *)(a2 + 56) = v140;
        }
        goto LABEL_208;
      }
      if ( !v135 || *v525 != *v135 )
        goto LABEL_208;
      v141 = 0;
      if ( (int)*v525 <= 0 )
        goto LABEL_206;
      while ( 1 )
      {
        v142 = 8LL * v141;
        if ( LOBYTE(v136[v142 + 6]) != LOBYTE(v135[v142 + 6])
          || (unsigned int)sqlite3ExprCompare(0, *(_QWORD *)&v136[v142 + 2], *(_QWORD *)&v135[v142 + 2], 0xFFFFFFFFLL) )
        {
          break;
        }
        if ( ++v141 >= *v136 )
        {
          v134 = a2;
          v137 = *(_DWORD *)(a2 + 4);
          goto LABEL_206;
        }
      }
    }
LABEL_208:
    if ( !v136 )
    {
      v522 = -1;
      DWORD2(v550) = -1;
      goto LABEL_226;
    }
    v143 = sqlite3KeyInfoFromExprList(a1, v136, 0, (unsigned int)*v135);
    v144 = *((unsigned int *)a1 + 13);
    HIDWORD(v549) = v144;
    *((_DWORD *)a1 + 13) = v144 + 1;
    v145 = *v135;
    v146 = *(int *)(v3 + 144);
    v147 = *v136 + 1;
    v522 = v146;
    v148 = (unsigned int)(v147 + v145);
    if ( *(_DWORD *)(v3 + 148) > (int)v146 )
    {
      *(_DWORD *)(v3 + 144) = v146 + 1;
      v149 = 3 * v146;
      v150 = *(_QWORD *)(v3 + 136);
      *(_DWORD *)(v150 + 8 * v149) = 118;
      *(_DWORD *)(v150 + 8 * v149 + 4) = v144;
      *(_DWORD *)(v150 + 8 * v149 + 8) = v148;
      v151 = v150 + 24 * v146;
      *(_DWORD *)(v151 + 12) = 0;
      *(_QWORD *)(v151 + 16) = 0;
    }
    else
    {
      LODWORD(v509) = 0;
      LODWORD(v146) = growOp3(v3, 118, v144, v148, v509);
      v522 = v146;
    }
    if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
    {
      if ( !*(_QWORD *)(*(_QWORD *)v3 + 776LL) )
      {
        if ( v143 )
        {
          v16 = (*(_DWORD *)v143)-- == 1;
          if ( v16 )
          {
            sqlite3DbNNFreeNN(*(_QWORD *)(v143 + 16), v143);
            DWORD2(v550) = v146;
LABEL_226:
            if ( *(_BYTE *)a3 == 12 )
            {
              v154 = v544;
              sqlite3VdbeAddOp2(v3, 118, *(unsigned int *)(a3 + 4), (unsigned int)*v544);
              if ( (*(_DWORD *)(a2 + 4) & 0x800) != 0 )
              {
                v155 = *v154;
                for ( m = *v154 - 1; m > 0; --m )
                {
                  v157 = &v154[8 * m];
                  if ( (v157[7] & 0x40) != 0 )
                  {
                    v154 = v544;
                    break;
                  }
                  v158 = *((_QWORD *)v157 + 1);
                  if ( v158 )
                    sqlite3ExprDeleteNN(v519, v158);
                  v159 = (_QWORD *)*((_QWORD *)v157 + 2);
                  if ( v159 )
                  {
                    if ( (unsigned __int64)v159 >= *(_QWORD *)(v519 + 496) )
                      goto LABEL_238;
                    if ( (unsigned __int64)v159 < *(_QWORD *)(v519 + 480) )
                    {
                      if ( (unsigned __int64)v159 < *(_QWORD *)(v519 + 488) )
                      {
LABEL_238:
                        if ( *(_QWORD *)(v519 + 776) )
                          measureAllocationSize(v519, *((_QWORD *)v157 + 2));
                        else
                          sqlite3_free(v159);
                        goto LABEL_241;
                      }
                      *v159 = *(_QWORD *)(v519 + 456);
                      *(_QWORD *)(v519 + 456) = v159;
                    }
                    else
                    {
                      *v159 = *(_QWORD *)(v519 + 472);
                      *(_QWORD *)(v519 + 472) = v159;
                    }
                  }
LABEL_241:
                  v154 = v544;
                  --*v544;
                  v155 = *v154;
                }
                v160 = 0;
                if ( v155 > 0 )
                {
                  do
                  {
                    v161 = 8LL * v160;
                    if ( (v154[v161 + 7] & 0x40) == 0 )
                      **(_BYTE **)&v154[v161 + 2] = 121;
                    ++v160;
                  }
                  while ( v160 < *v154 );
                }
              }
            }
            v162 = a1;
            v163 = a2;
            LODWORD(v164) = *((_DWORD *)a1 + 17) - 1;
            *((_DWORD *)a1 + 17) = v164;
            v16 = (*(_DWORD *)(a2 + 4) & 0x4000) == 0;
            LODWORD(v527) = v164;
            if ( v16 )
              *(_WORD *)(a2 + 2) = 320;
            if ( *(_QWORD *)(a2 + 96) )
            {
              v164 = computeLimitRegisters(a1, a2, (unsigned int)v164);
              v163 = a2;
            }
            if ( !*(_DWORD *)(v163 + 8) && v522 >= 0 )
            {
              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                v164 = (__int64)&qword_18013FEA8;
              else
                v164 = *(_QWORD *)(v3 + 136) + 24LL * v522;
              BYTE4(v551) |= 1u;
              *(_BYTE *)v164 = 119;
            }
            if ( (*(_BYTE *)(v163 + 4) & 1) != 0 )
            {
              v165 = *((_DWORD *)a1 + 13);
              v539 = v165;
              *((_DWORD *)a1 + 13) = v165 + 1;
              v166 = sqlite3KeyInfoFromExprList(a1, *(_QWORD *)(v163 + 32), 0, 0);
              v167 = *(int *)(v3 + 144);
              v168 = v166;
              if ( *(_DWORD *)(v3 + 148) > (int)v167 )
              {
                *(_DWORD *)(v3 + 144) = v167 + 1;
                v169 = 3 * v167;
                v170 = *(_QWORD *)(v3 + 136);
                *(_DWORD *)(v170 + 8 * v169) = 118;
                *(_DWORD *)(v170 + 8 * v169 + 4) = v165;
                v171 = v170 + 24 * v167;
                *(_QWORD *)(v171 + 8) = 0;
                *(_QWORD *)(v171 + 16) = 0;
              }
              else
              {
                LODWORD(v509) = 0;
                LODWORD(v167) = growOp3(v3, 118, v165, 0, v509);
              }
              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
              {
                if ( !*(_QWORD *)(*(_QWORD *)v3 + 776LL) )
                {
                  if ( v168 )
                  {
                    v16 = (*(_DWORD *)v168)-- == 1;
                    if ( v16 )
                      sqlite3DbNNFreeNN(*(_QWORD *)(v168 + 16), v168);
                  }
                }
              }
              else
              {
                v172 = v167;
                if ( (int)v167 < 0 )
                  v172 = *(_DWORD *)(v3 + 144) - 1;
                v173 = *(_QWORD *)(v3 + 136) + 24LL * v172;
                if ( *(_BYTE *)(v173 + 1) )
                {
                  vdbeChangeP4Full(v3, v173, v168, 4294967288LL);
                }
                else if ( v168 )
                {
                  *(_QWORD *)(v173 + 16) = v168;
                  *(_BYTE *)(v173 + 1) = -8;
                }
              }
              v164 = *(int *)(v3 + 144);
              v540 = v167;
              if ( (int)v164 > 0 )
              {
                v174 = 3 * v164;
                v164 = *(_QWORD *)(v3 + 136);
                *(_WORD *)(v164 + 8 * v174 - 22) = 8;
              }
              LODWORD(v138) = v528;
              LOBYTE(v164) = 3;
              v162 = a1;
              v163 = a2;
            }
            else
            {
              LOBYTE(v164) = 0;
            }
            v538 = v164;
            v529 = v164;
            if ( !v526 && !v140 )
            {
              v175 = *(_QWORD *)(v163 + 112);
              v7 = a1;
              v176 = (v139 != 0 ? 0x100 : 0) | *(_WORD *)(v163 + 4) & 0x4000;
              if ( v175 )
              {
                sqlite3WindowCodeInit(a1, v163);
                v163 = a2;
              }
              v177 = sqlite3WhereBegin(
                       (_DWORD)a1,
                       (_DWORD)v515,
                       v138,
                       (_DWORD)v136,
                       *(_QWORD *)(v163 + 32),
                       v163,
                       v176,
                       *(__int16 *)(v163 + 2));
              v178 = v177;
              if ( !v177 )
                goto LABEL_77;
              v179 = a2;
              v180 = *(_WORD *)(v177 + 72);
              if ( v180 < *(__int16 *)(a2 + 2) )
                *(_WORD *)(a2 + 2) = v180;
              if ( v139 )
              {
                v181 = (unsigned __int8)v529;
                if ( *(_BYTE *)(v178 + 67) )
                  v181 = *(unsigned __int8 *)(v178 + 67);
                v529 = v181;
                v538 = v181;
              }
              v182 = v136;
              if ( v136 )
              {
                v183 = 0;
                if ( *(char *)(v178 + 65) >= 0 )
                  v183 = *(char *)(v178 + 65);
                v16 = (*(_BYTE *)(v178 + 68) & 4) == 0;
                DWORD2(v549) = v183;
                if ( v16 )
                {
                  v184 = *(_DWORD *)(v178 + 48);
                }
                else
                {
                  v185 = *(unsigned __int8 *)(v178 + 64);
                  if ( *(_QWORD *)(112 * v185 + v178 + 808) )
                    v184 = *(_DWORD *)(v178 + 48);
                  else
                    v184 = *(_DWORD *)(112 * v185 + v178 + 768);
                }
                LODWORD(v551) = v184;
                if ( v183 == *v136 )
                  v182 = 0;
                *(_QWORD *)&v549 = v182;
              }
              if ( v522 >= 0 && !v182 )
              {
                sqlite3VdbeChangeToNoop(v3, (unsigned int)v522, 0);
                v179 = a2;
              }
              if ( !v175 )
              {
                v201 = a3;
                selectInnerLoop(
                  (_DWORD)a1,
                  v179,
                  -1,
                  (unsigned int)&v549,
                  (__int64)&v537,
                  a3,
                  *(_DWORD *)(v178 + 48),
                  *(_DWORD *)(v178 + 52));
                sqlite3WhereEnd(v178);
                v196 = a2;
                goto LABEL_748;
              }
              v186 = *((_DWORD *)a1 + 17);
              ++*((_DWORD *)a1 + 14);
              v187 = v186 - 1;
              v188 = *((_DWORD *)a1 + 14);
              v189 = v187 - 1;
              v190 = v187 - 2;
              *((_DWORD *)a1 + 17) = v187 - 2;
              sqlite3WindowCodeStep((_DWORD)a1, v179, v178, v188, v187);
              v191 = *(int *)(v3 + 144);
              if ( *(_DWORD *)(v3 + 148) > (int)v191 )
              {
                *(_DWORD *)(v3 + 144) = v191 + 1;
                v192 = 3 * v191;
                v193 = *(_QWORD *)(v3 + 136);
                *(_QWORD *)(v193 + 8 * v192) = 9;
                *(_DWORD *)(v193 + 8 * v192 + 8) = v190;
                *(_DWORD *)(v193 + 8 * v192 + 12) = 0;
                *(_QWORD *)(v193 + 8 * v192 + 16) = 0;
              }
              else
              {
                LODWORD(v510) = 0;
                growOp3(v3, 9, 0, v190, v510);
              }
              v194 = *(_QWORD *)(v3 + 24);
              v195 = ~v187;
              if ( *(_DWORD *)(v194 + 68) + *(_DWORD *)(v194 + 72) >= 0 )
                *(_DWORD *)(*(_QWORD *)(v194 + 80) + 4LL * v195) = *(_DWORD *)(v3 + 144);
              else
                resizeResolveLabel(v194, v3, (unsigned int)v195);
              LODWORD(v551) = 0;
              v196 = a2;
              selectInnerLoop((_DWORD)a1, a2, -1, (unsigned int)&v549, (__int64)&v537, a3, v189, v190);
              v197 = *(_QWORD *)(v3 + 24);
              v198 = ~v189;
              if ( *(_DWORD *)(v197 + 68) + *(_DWORD *)(v197 + 72) >= 0 )
                *(_DWORD *)(*(_QWORD *)(v197 + 80) + 4LL * v198) = *(_DWORD *)(v3 + 144);
              else
                resizeResolveLabel(v197, v3, (unsigned int)v198);
              sqlite3VdbeAddOp1(v3, 67, v188);
              v199 = *(_QWORD *)(v3 + 24);
              v200 = ~v190;
              if ( *(_DWORD *)(v199 + 68) + *(_DWORD *)(v199 + 72) < 0 )
              {
                resizeResolveLabel(v199, v3, (unsigned int)v200);
                v201 = a3;
LABEL_748:
                if ( (_BYTE)v529 == 3 )
                  sqlite3VdbeExplain(v7, 0, "USE TEMP B-TREE FOR %s", "DISTINCT");
                if ( (_QWORD)v549 )
                  generateSortTail((_DWORD)v7, v196, (unsigned int)&v549, *v544, v201);
                v506 = *(_QWORD *)(v3 + 24);
                v507 = ~(_DWORD)v527;
                if ( *(_DWORD *)(v506 + 68) + *(_DWORD *)(v506 + 72) >= 0 )
                  *(_DWORD *)(*(_QWORD *)(v506 + 80) + 4LL * v507) = *(_DWORD *)(v3 + 144);
                else
                  resizeResolveLabel(v506, v3, (unsigned int)v507);
                v246 = v519;
                v9 = *((_DWORD *)v7 + 12) > 0;
                goto LABEL_758;
              }
              v202 = v200;
              v201 = a3;
LABEL_747:
              *(_DWORD *)(*(_QWORD *)(v199 + 80) + 4 * v202) = *(_DWORD *)(v3 + 144);
              goto LABEL_748;
            }
            v524 = 0;
            if ( v140 )
            {
              v203 = *(int **)(v163 + 32);
              v204 = *v203;
              for ( n = v203 + 2; v204 > 0; n += 8 )
              {
                --v204;
                *((_WORD *)n + 13) = 0;
              }
              v206 = *v140;
              for ( ii = v140 + 2; v206 > 0; ii += 8 )
              {
                --v206;
                *((_WORD *)ii + 13) = 0;
              }
              if ( *(__int16 *)(v163 + 2) > 66 )
                *(_WORD *)(v163 + 2) = 66;
              v208 = v136;
              if ( v136 )
              {
                v209 = *v140;
                if ( *v140 == *v136 )
                {
                  v210 = 0;
                  if ( v209 > 0 )
                  {
                    do
                    {
                      v211 = v210++;
                      LOBYTE(v140[8 * v211 + 6]) = v136[8 * v211 + 6] & 1;
                      v209 = *v140;
                    }
                    while ( v210 < *v140 );
                  }
                  if ( v209 == *v136 )
                  {
                    v212 = 0;
                    if ( v209 <= 0 )
                    {
LABEL_332:
                      v9 = 1;
                      v524 = 1;
                      goto LABEL_335;
                    }
                    while ( 1 )
                    {
                      v213 = 8LL * v212;
                      v214 = &v208[v213];
                      if ( LOBYTE(v140[v213 + 6]) != *((_BYTE *)v214 + 24)
                        || (unsigned int)sqlite3ExprCompare(
                                           0,
                                           *(_QWORD *)&v140[v213 + 2],
                                           *((_QWORD *)v214 + 1),
                                           0xFFFFFFFFLL) )
                      {
                        break;
                      }
                      ++v212;
                      v208 = v136;
                      if ( v212 >= *v140 )
                        goto LABEL_332;
                    }
                  }
                }
              }
            }
            else
            {
              *(_WORD *)(v163 + 2) = 0;
            }
            v9 = 1;
LABEL_335:
            v521 = *((_DWORD *)v162 + 17) - 1;
            *((_DWORD *)v162 + 17) = v521;
            v215 = sqlite3DbMallocRawNN(v519, 56);
            if ( !v215 )
              goto LABEL_370;
            *(_OWORD *)v215 = 0;
            *(_OWORD *)(v215 + 16) = 0;
            *(_OWORD *)(v215 + 32) = 0;
            *(_QWORD *)(v215 + 48) = 0;
            if ( *v162 )
              v216 = (_QWORD *)sqlite3DbMallocRawNN(*v162, 24);
            else
              v216 = (_QWORD *)sqlite3Malloc(24);
            if ( v216 )
            {
              *v216 = v162[24];
              v162[24] = v216;
              v216[2] = agginfoFree;
              v216[1] = v215;
              goto LABEL_370;
            }
            v217 = *(_QWORD **)(v215 + 24);
            v218 = (_QWORD *)*v162;
            if ( v217 )
            {
              if ( !v218 )
                goto LABEL_350;
              if ( (unsigned __int64)v217 < v218[62] )
              {
                if ( (unsigned __int64)v217 >= v218[60] )
                {
                  *v217 = v218[59];
                  v218[59] = v217;
                  goto LABEL_351;
                }
                if ( (unsigned __int64)v217 >= v218[61] )
                {
                  *v217 = v218[57];
                  v218[57] = v217;
                  goto LABEL_351;
                }
              }
              if ( v218[97] )
                measureAllocationSize(*v162, *(_QWORD *)(v215 + 24));
              else
LABEL_350:
                sqlite3_free(v217);
            }
LABEL_351:
            v219 = *(_QWORD **)(v215 + 40);
            if ( v219 )
            {
              if ( v218 )
              {
                if ( (unsigned __int64)v219 < v218[62] )
                {
                  if ( (unsigned __int64)v219 >= v218[60] )
                  {
                    *v219 = v218[59];
                    v218[59] = v219;
LABEL_362:
                    if ( v215 < v218[62] )
                    {
                      if ( v215 >= v218[60] )
                      {
                        *(_QWORD *)v215 = v218[59];
                        v218[59] = v215;
                        goto LABEL_370;
                      }
                      if ( v215 >= v218[61] )
                      {
                        *(_QWORD *)v215 = v218[57];
                        v218[57] = v215;
                        goto LABEL_370;
                      }
                    }
                    if ( v218[97] )
                    {
                      measureAllocationSize(v218, v215);
                      goto LABEL_370;
                    }
LABEL_369:
                    sqlite3_free(v215);
LABEL_370:
                    if ( *(_BYTE *)(v519 + 103) )
                    {
                      v7 = a1;
                      goto LABEL_78;
                    }
                    v220 = a2;
                    *(_DWORD *)(v215 + 52) = *(_DWORD *)(a2 + 16);
                    v553[1] = v515;
                    v553[0] = v162;
                    v553[2] = v215;
                    v554 = 0;
                    v555 = 0;
                    if ( v140 )
                      v221 = *v140;
                    else
                      LOWORD(v221) = 0;
                    v222 = v544;
                    *(_WORD *)(v215 + 2) = v221;
                    *(_QWORD *)(v215 + 16) = v140;
                    if ( v222 )
                    {
                      v223 = (__int64 *)(v222 + 2);
                      v224 = 0;
                      if ( *v222 > 0 )
                      {
                        do
                        {
                          v225 = *v223;
                          v534 = analyzeAggregate;
                          *(_QWORD *)&v535 = sqlite3WalkerDepthIncrease;
                          *((_QWORD *)&v535 + 1) = sqlite3WalkerDepthDecrease;
                          LODWORD(v536) = 0;
                          *((_QWORD *)&v536 + 1) = v553;
                          v533 = 0;
                          if ( v225 )
                            sqlite3WalkExprNN(&v533);
                          ++v224;
                          v223 += 4;
                        }
                        while ( v224 < *v222 );
                        v3 = v543;
                        v140 = v518;
                        v220 = a2;
                      }
                    }
                    v226 = v525;
                    if ( v525 )
                    {
                      v227 = (__int64 *)(v525 + 2);
                      v228 = 0;
                      if ( (int)*v525 > 0 )
                      {
                        do
                        {
                          v229 = *v227;
                          v534 = analyzeAggregate;
                          *(_QWORD *)&v535 = sqlite3WalkerDepthIncrease;
                          *((_QWORD *)&v535 + 1) = sqlite3WalkerDepthDecrease;
                          LODWORD(v536) = 0;
                          *((_QWORD *)&v536 + 1) = v553;
                          v533 = 0;
                          if ( v229 )
                            sqlite3WalkExprNN(&v533);
                          ++v228;
                          v227 += 4;
                        }
                        while ( v228 < *v226 );
                        v3 = v543;
                        v140 = v518;
                        v220 = a2;
                      }
                    }
                    if ( v547 )
                    {
                      if ( v140 )
                      {
                        v230 = *(_QWORD *)(v220 + 64);
                        v533 = a1;
                        v534 = havingToWhereExprCb;
                        *(_QWORD *)&v536 = 0;
                        *((_QWORD *)&v536 + 1) = v220;
                        v535 = 0;
                        if ( v230 )
                          sqlite3WalkExprNN(&v533);
                        v528 = *(_QWORD *)(v220 + 48);
                      }
                      LODWORD(v536) = 0;
                      v534 = analyzeAggregate;
                      v533 = 0;
                      *(_QWORD *)&v535 = sqlite3WalkerDepthIncrease;
                      *((_QWORD *)&v535 + 1) = sqlite3WalkerDepthDecrease;
                      *((_QWORD *)&v536 + 1) = v553;
                      sqlite3WalkExprNN(&v533);
                    }
                    v231 = (_QWORD *)a2;
                    *(_DWORD *)(v215 + 36) = *(_DWORD *)(v215 + 32);
                    if ( *(_QWORD *)(a2 + 56)
                      || *(_QWORD *)(a2 + 64)
                      || *(_DWORD *)(v215 + 48) != 1
                      || (v232 = *(__int64 **)(v215 + 40), v233 = *v232, (v234 = *(_QWORD *)(*v232 + 32)) == 0)
                      || *(_DWORD *)v234 != 1
                      || (*(_DWORD *)(v233 + 4) & 0x1000000) != 0
                      || (*(_DWORD *)(v519 + 96) & 0x10000) != 0 )
                    {
LABEL_414:
                      v240 = 0;
                      goto LABEL_415;
                    }
                    v235 = *(_BYTE **)(v233 + 8);
                    v236 = "min";
                    for ( jj = v235; ; ++jj )
                    {
                      v238 = (unsigned __int8)*jj;
                      v239 = *(unsigned __int8 *)v236;
                      if ( (_DWORD)v238 != (_DWORD)v239 )
                        break;
                      if ( !*jj )
                      {
                        v240 = 1;
                        v241 = (unsigned int)sqlite3ExprCanBeNull(*(_QWORD *)(v234 + 8)) != 0 ? 2 : 0;
                        goto LABEL_409;
                      }
LABEL_404:
                      ++v236;
                    }
                    if ( *((unsigned __int8 *)qword_180114680 + v238) == *((unsigned __int8 *)qword_180114680 + v239) )
                      goto LABEL_404;
                    for ( kk = "max"; ; ++kk )
                    {
                      v243 = (unsigned __int8)*v235;
                      v244 = *(unsigned __int8 *)kk;
                      if ( (_DWORD)v243 == (_DWORD)v244 )
                      {
                        if ( !*v235 )
                        {
                          v241 = 1;
                          v240 = 2;
LABEL_409:
                          v245 = sqlite3ExprListDup(v519, v234, 0);
                          v548 = v245;
                          if ( v245 )
                            *(_BYTE *)(v245 + 24) = v241;
                          v231 = (_QWORD *)a2;
LABEL_415:
                          analyzeAggFuncArgs(v215, v553);
                          v246 = v519;
                          if ( *(_BYTE *)(v519 + 103) )
                          {
LABEL_459:
                            v7 = a1;
                          }
                          else
                          {
                            if ( v140 )
                            {
                              v16 = *(_DWORD *)(v215 + 48) == 1;
                              appended = 0;
                              v546 = 0;
                              v248 = 0;
                              v532 = 0;
                              if ( v16 )
                              {
                                v249 = *(int **)(v215 + 40);
                                if ( v249[4] >= 0 )
                                {
                                  v250 = *(_QWORD *)v249;
                                  if ( v250 )
                                  {
                                    if ( (*(_DWORD *)(v250 + 4) & 0x1000) == 0 )
                                    {
                                      v251 = *(_QWORD *)(v250 + 32);
                                      if ( v251 )
                                      {
                                        v252 = *(_QWORD *)(v251 + 8);
                                        if ( v252 )
                                          v253 = exprDup(v519, v252, 0, 0);
                                        else
                                          v253 = 0;
                                        v254 = (int *)sqlite3ExprListDup(v519, v518, 0);
                                        v546 = v254;
                                        appended = v254;
                                        if ( v254 )
                                        {
                                          v255 = *v254;
                                          v256 = v255 + 1;
                                          if ( appended[1] >= (int)v255 + 1 )
                                          {
                                            v257 = 8 * v255;
                                            *appended = v256;
                                            *(_OWORD *)&appended[v257 + 2] = xmmword_180114128;
                                            *(_OWORD *)&appended[v257 + 6] = xmmword_180114138;
                                            *(_QWORD *)&appended[v257 + 2] = v253;
                                          }
                                          else
                                          {
                                            appended = (int *)sqlite3ExprListAppendGrow(*a1, appended, v253);
                                            v546 = appended;
                                          }
                                        }
                                        else
                                        {
                                          appended = (int *)sqlite3ExprListAppendNew(*a1, v253);
                                          v546 = appended;
                                        }
                                        v248 = appended != 0 ? 0x500 : 0;
                                        v532 = v248;
                                      }
                                    }
                                  }
                                }
                              }
                              *(_DWORD *)(v215 + 4) = (*((_DWORD *)a1 + 13))++;
                              v258 = sqlite3KeyInfoFromExprList(a1, v518, 0, *(unsigned int *)(v215 + 32));
                              v259 = *(int *)(v3 + 144);
                              v260 = v258;
                              v261 = *(unsigned __int16 *)(v215 + 2);
                              v262 = *(unsigned int *)(v215 + 4);
                              v552 = (_DWORD *)v258;
                              v542 = v259;
                              if ( *(_DWORD *)(v3 + 148) > (int)v259 )
                              {
                                *(_DWORD *)(v3 + 144) = v259 + 1;
                                v263 = 3 * v259;
                                v264 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v264 + 8 * v263) = 119;
                                *(_DWORD *)(v264 + 8 * v263 + 4) = v262;
                                *(_DWORD *)(v264 + 8 * v263 + 8) = v261;
                                v265 = v264 + 24 * v259;
                                *(_DWORD *)(v265 + 12) = 0;
                                *(_QWORD *)(v265 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v509) = 0;
                                LODWORD(v259) = growOp3(v3, 119, v262, v261, v509);
                                v542 = v259;
                              }
                              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                              {
                                if ( !*(_QWORD *)(*(_QWORD *)v3 + 776LL) )
                                {
                                  if ( v260 )
                                  {
                                    v16 = (*(_DWORD *)v260)-- == 1;
                                    if ( v16 )
                                      sqlite3DbNNFreeNN(*(_QWORD *)(v260 + 16), v260);
                                  }
                                }
                              }
                              else
                              {
                                v266 = v259;
                                if ( (int)v259 < 0 )
                                  v266 = *(_DWORD *)(v3 + 144) - 1;
                                v267 = *(_QWORD *)(v3 + 136) + 24LL * v266;
                                if ( *(_BYTE *)(v267 + 1) )
                                {
                                  vdbeChangeP4Full(v3, v267, v260, 4294967288LL);
                                }
                                else if ( v260 )
                                {
                                  *(_QWORD *)(v267 + 16) = v260;
                                  *(_BYTE *)(v267 + 1) = -8;
                                }
                              }
                              v531 = *((_DWORD *)a1 + 14) + 1;
                              v268 = v531 + 1;
                              v269 = *((_DWORD *)a1 + 17);
                              v270 = v531 + 3;
                              v523 = v531 + 1;
                              *((_DWORD *)a1 + 14) = v531 + 3;
                              v271 = v270 + 1;
                              --v269;
                              LODWORD(v525) = v270;
                              v541 = v269;
                              v530 = v270 + 1;
                              v272 = v269 - 1;
                              *((_DWORD *)a1 + 17) = v269 - 1;
                              v273 = v270 + *v518;
                              v520 = v269 - 1;
                              *((_DWORD *)a1 + 14) = v273;
                              *((_DWORD *)a1 + 14) = v273 + *v518;
                              v274 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v274 )
                              {
                                *(_DWORD *)(v3 + 144) = v274 + 1;
                                v275 = 3 * v274;
                                v276 = *(_QWORD *)(v3 + 136);
                                *(_QWORD *)(v276 + 8 * v275) = 71;
                                *(_DWORD *)(v276 + 8 * v275 + 8) = v268;
                                *(_DWORD *)(v276 + 8 * v275 + 12) = 0;
                                *(_QWORD *)(v276 + 8 * v275 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v509) = 0;
                                growOp3(v3, 71, 0, v268, v509);
                                v271 = v530;
                              }
                              v277 = *(int *)(v3 + 144);
                              v278 = v270 + *v518;
                              if ( *(_DWORD *)(v3 + 148) > (int)v277 )
                              {
                                *(_DWORD *)(v3 + 144) = v277 + 1;
                                v279 = 3 * v277;
                                v280 = *(_QWORD *)(v3 + 136);
                                *(_QWORD *)(v280 + 8 * v279) = 75;
                                *(_DWORD *)(v280 + 8 * v279 + 8) = v271;
                                *(_DWORD *)(v280 + 8 * v279 + 12) = v278;
                                *(_QWORD *)(v280 + 8 * v279 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v509) = v270 + *v518;
                                growOp3(v3, 75, 0, v271, v509);
                              }
                              v281 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v281 )
                              {
                                *(_DWORD *)(v3 + 144) = v281 + 1;
                                v282 = 3 * v281;
                                v283 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v283 + 8 * v282) = 10;
                                *(_DWORD *)(v283 + 8 * v282 + 4) = v270;
                                *(_DWORD *)(v283 + 8 * v282 + 8) = v272;
                                v284 = v283 + 8 * v282;
                                *(_DWORD *)(v284 + 12) = 0;
                                *(_QWORD *)(v284 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v509) = 0;
                                growOp3(v3, 10, v270, v272, v509);
                              }
                              v285 = 64;
                              if ( v560 == 2 )
                                v285 = 128;
                              v545 = sqlite3WhereBegin(
                                       (_DWORD)a1,
                                       (_DWORD)v515,
                                       v528,
                                       (_DWORD)v518,
                                       (__int64)appended,
                                       a2,
                                       v248 | (unsigned __int16)(v285 | (v524 != 0 ? 0x200 : 0)),
                                       0);
                              v287 = (_BYTE *)v545;
                              if ( !v545 )
                              {
                                v246 = v519;
                                if ( appended )
                                  exprListDeleteNN(v519, appended);
                                goto LABEL_459;
                              }
                              v288 = v273 + 1;
                              v289 = a1 + 12;
                              v516 = v288;
                              if ( a1[12] )
                              {
                                v16 = *(_WORD *)(v215 + 2) == 0;
                                v290 = *(_DWORD *)(v215 + 36);
                                *(_DWORD *)(v215 + 32) = v290;
                                if ( !v16 )
                                {
                                  v291 = **(_DWORD **)(a2 + 56) - 1;
                                  if ( v290 > 0 )
                                  {
                                    v292 = 0;
                                    do
                                    {
                                      v293 = *(__int16 *)(*(_QWORD *)(v215 + 24) + 24 * v292 + 22);
                                      if ( v293 <= v291 )
                                        v293 = v291;
                                      v292 = (unsigned int)(v292 + 1);
                                      v291 = v293;
                                    }
                                    while ( (int)v292 < v290 );
                                  }
                                  v289 = a1 + 12;
                                  *(_WORD *)(v215 + 2) = v291 + 1;
                                }
                                analyzeAggFuncArgs(v215, v553);
                              }
                              v294 = 0;
                              *(_DWORD *)(v215 + 12) = *((_DWORD *)a1 + 14) + 1;
                              *((_DWORD *)a1 + 14) += *(_DWORD *)(v215 + 32) + *(_DWORD *)(v215 + 48);
                              v295 = (char)v287[65];
                              v296 = (char)v287[65] < 0;
                              v526 = (unsigned __int8)v287[67];
                              if ( !v296 )
                                v294 = v295;
                              if ( v294 == *v518 )
                              {
                                v297 = 0;
                                v561 = 0;
                                v298 = 0;
                              }
                              else
                              {
                                if ( !v560 || (v299 = "DISTINCT", (*(_BYTE *)(a2 + 4) & 1) != 0) )
                                  v299 = "GROUP BY";
                                v300 = a1;
                                sqlite3VdbeExplain(a1, 0, "USE TEMP B-TREE FOR %s", v299);
                                v301 = *v518;
                                v302 = *v518;
                                v303 = *(_DWORD *)(v215 + 32);
                                v561 = 1;
                                LODWORD(v528) = *v518;
                                if ( v303 > 0 )
                                {
                                  v304 = 0;
                                  v305 = v301;
                                  do
                                  {
                                    v306 = *(__int16 *)(*(_QWORD *)(v215 + 24) + 24 * v304 + 22);
                                    v307 = v302 + 1;
                                    if ( v306 < v305 )
                                      v307 = v302;
                                    v304 = (unsigned int)(v304 + 1);
                                    v302 = v307;
                                    v308 = v305 + 1;
                                    if ( v306 < v305 )
                                      v308 = v305;
                                    v305 = v308;
                                  }
                                  while ( (int)v304 < v303 );
                                  LODWORD(v528) = v302;
                                }
                                if ( v302 == 1 )
                                {
                                  v309 = *((_BYTE *)a1 + 31);
                                  if ( v309 )
                                  {
                                    v311 = v309 - 1;
                                    *((_BYTE *)a1 + 31) = v311;
                                    v310 = *((_DWORD *)a1 + v311 + 56);
                                  }
                                  else
                                  {
                                    v310 = *((_DWORD *)a1 + 14) + 1;
                                    *((_DWORD *)a1 + 14) = v310;
                                  }
                                }
                                else
                                {
                                  v312 = *((_DWORD *)a1 + 10);
                                  if ( v302 > v312 )
                                  {
                                    v313 = *((_DWORD *)a1 + 14);
                                    v310 = v313 + 1;
                                    *((_DWORD *)a1 + 14) = v302 + v313;
                                  }
                                  else
                                  {
                                    v310 = *((_DWORD *)a1 + 11);
                                    *((_DWORD *)a1 + 10) = v312 - v302;
                                    *((_DWORD *)a1 + 11) = v302 + v310;
                                  }
                                }
                                sqlite3ExprCodeExprList((_DWORD)a1, (_DWORD)v518, v310, 0, 0);
                                *(_BYTE *)v215 = 1;
                                v314 = 0;
                                if ( *(int *)(v215 + 32) > 0 )
                                {
                                  do
                                  {
                                    v315 = *(_QWORD *)(v215 + 24) + 24LL * v314;
                                    if ( *(__int16 *)(v315 + 22) >= v301 )
                                    {
                                      if ( a1[2] )
                                      {
                                        v316 = *(_QWORD *)(v315 + 8);
                                        v317 = sqlite3ExprCodeTarget(a1, v316, v301 + v310);
                                        if ( v317 != v301 + v310 )
                                        {
                                          if ( v316
                                            && ((*(_DWORD *)(v316 + 4) & 0x400000) != 0 || *(_BYTE *)v316 == 0xB0) )
                                          {
                                            v318 = 80;
                                          }
                                          else
                                          {
                                            v318 = 81;
                                          }
                                          sqlite3VdbeAddOp2(a1[2], v318, v317, v301 + v310);
                                        }
                                      }
                                      ++v301;
                                    }
                                    ++v314;
                                  }
                                  while ( v314 < *(_DWORD *)(v215 + 32) );
                                  v3 = v543;
                                  v302 = v528;
                                  v300 = a1;
                                }
                                *(_BYTE *)v215 = 0;
                                v319 = *((_BYTE *)v300 + 31);
                                if ( v319 )
                                {
                                  v321 = v319 - 1;
                                  *((_BYTE *)v300 + 31) = v321;
                                  v320 = *((_DWORD *)v300 + v321 + 56);
                                }
                                else
                                {
                                  v320 = *((_DWORD *)v300 + 14) + 1;
                                  *((_DWORD *)a1 + 14) = v320;
                                }
                                v322 = *(int *)(v3 + 144);
                                if ( *(_DWORD *)(v3 + 148) > (int)v322 )
                                {
                                  *(_DWORD *)(v3 + 144) = v322 + 1;
                                  v323 = 3 * v322;
                                  v324 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v324 + 8 * v323) = 97;
                                  *(_DWORD *)(v324 + 8 * v323 + 4) = v310;
                                  *(_DWORD *)(v324 + 8 * v323 + 8) = v302;
                                  v325 = v324 + 8 * v323;
                                  *(_DWORD *)(v325 + 12) = v320;
                                  *(_QWORD *)(v325 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v511) = v320;
                                  growOp3(v3, 97, v310, (unsigned int)v302, v511);
                                }
                                v326 = *(int *)(v3 + 144);
                                v327 = *(unsigned int *)(v215 + 4);
                                if ( *(_DWORD *)(v3 + 148) > (int)v326 )
                                {
                                  *(_DWORD *)(v3 + 144) = v326 + 1;
                                  v328 = 3 * v326;
                                  v329 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v329 + 8 * v328) = 139;
                                  *(_DWORD *)(v329 + 8 * v328 + 4) = v327;
                                  *(_DWORD *)(v329 + 8 * v328 + 8) = v320;
                                  v330 = v329 + 8 * v328;
                                  *(_DWORD *)(v330 + 12) = 0;
                                  *(_QWORD *)(v330 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v511) = 0;
                                  growOp3(v3, 139, v327, v320, v511);
                                }
                                if ( v320 && (v331 = *((unsigned __int8 *)a1 + 31), (unsigned __int8)v331 < 8u) )
                                {
                                  *((_DWORD *)a1 + v331 + 56) = v320;
                                  v332 = a1;
                                  ++*((_BYTE *)a1 + 31);
                                }
                                else
                                {
                                  v332 = a1;
                                }
                                if ( v302 == 1 )
                                {
                                  if ( v310 )
                                  {
                                    v333 = *((unsigned __int8 *)v332 + 31);
                                    if ( (unsigned __int8)v333 < 8u )
                                    {
                                      *((_DWORD *)v332 + v333 + 56) = v310;
                                      ++*((_BYTE *)v332 + 31);
                                    }
                                  }
                                }
                                else if ( v302 > *((_DWORD *)v332 + 10) )
                                {
                                  *((_DWORD *)v332 + 10) = v302;
                                  *((_DWORD *)v332 + 11) = v310;
                                }
                                v287 = (_BYTE *)v545;
                                sqlite3WhereEnd(v545);
                                v297 = *((_DWORD *)v332 + 13);
                                *(_DWORD *)(v215 + 8) = v297;
                                ++*((_DWORD *)v332 + 13);
                                v334 = *((_BYTE *)v332 + 31);
                                if ( v334 )
                                {
                                  v335 = v334 - 1;
                                  *((_BYTE *)v332 + 31) = v335;
                                  v298 = *((_DWORD *)v332 + v335 + 56);
                                }
                                else
                                {
                                  v298 = *((_DWORD *)v332 + 14) + 1;
                                  *((_DWORD *)v332 + 14) = v298;
                                }
                                v336 = *(int *)(v3 + 144);
                                if ( *(_DWORD *)(v3 + 148) > (int)v336 )
                                {
                                  *(_DWORD *)(v3 + 144) = v336 + 1;
                                  v337 = 3 * v336;
                                  v338 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v338 + 8 * v337) = 121;
                                  *(_DWORD *)(v338 + 8 * v337 + 4) = v297;
                                  *(_DWORD *)(v338 + 8 * v337 + 8) = v298;
                                  v339 = v338 + 8 * v337;
                                  LODWORD(v338) = v528;
                                  *(_QWORD *)(v339 + 16) = 0;
                                  *(_DWORD *)(v339 + 12) = v338;
                                }
                                else
                                {
                                  LODWORD(v511) = v528;
                                  growOp3(v3, 121, v297, v298, v511);
                                }
                                v340 = *(int *)(v3 + 144);
                                v286 = *(unsigned int *)(v215 + 4);
                                if ( *(_DWORD *)(v3 + 148) > (int)v340 )
                                {
                                  *(_DWORD *)(v3 + 144) = v340 + 1;
                                  v341 = 3 * v340;
                                  v342 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v342 + 8 * v341) = 34;
                                  *(_DWORD *)(v342 + 8 * v341 + 4) = v286;
                                  *(_DWORD *)(v342 + 8 * v341 + 12) = 0;
                                  v343 = v342 + 8 * v341;
                                  LODWORD(v342) = v521;
                                  *(_QWORD *)(v343 + 16) = 0;
                                  *(_DWORD *)(v343 + 8) = v342;
                                }
                                else
                                {
                                  LODWORD(v511) = 0;
                                  growOp3(v3, 34, v286, v521, v511);
                                }
                                *(_BYTE *)(v215 + 1) = 1;
                                v289 = v332 + 12;
                              }
                              if ( *v289 )
                              {
                                v8 = *(_DWORD *)(v215 + 48) <= 0;
                                v534 = aggregateIdxEprRefToColCallback;
                                v533 = 0;
                                v535 = 0;
                                v344 = 0;
                                v536 = 0;
                                if ( !v8 )
                                {
                                  do
                                  {
                                    if ( *(_QWORD *)(*(_QWORD *)(v215 + 40) + 24LL * v344) )
                                      sqlite3WalkExprNN(&v533);
                                    ++v344;
                                  }
                                  while ( v344 < *(_DWORD *)(v215 + 48) );
                                }
                              }
                              v345 = v561;
                              if ( v524 && (*(_BYTE *)(v519 + 96) & 4) == 0 && (v561 || (v287[68] & 8) != 0) )
                              {
                                *(_QWORD *)&v549 = 0;
                                sqlite3VdbeChangeToNoop(v3, (unsigned int)v522, v286);
                              }
                              v346 = *(int *)(v3 + 144);
                              v524 = *(_DWORD *)(v3 + 144);
                              if ( v561 )
                              {
                                v347 = *(unsigned int *)(v215 + 4);
                                if ( *(_DWORD *)(v3 + 148) > (int)v346 )
                                {
                                  *(_DWORD *)(v3 + 144) = v346 + 1;
                                  v348 = *(_QWORD *)(v3 + 136);
                                  v349 = 3 * v346;
                                  *(_DWORD *)(v348 + 8 * v349) = 133;
                                  *(_DWORD *)(v348 + 8 * v349 + 4) = v347;
                                  *(_DWORD *)(v348 + 8 * v349 + 8) = v298;
                                  v350 = v348 + 24 * v346;
                                  *(_DWORD *)(v350 + 12) = v297;
                                  *(_QWORD *)(v350 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v511) = v297;
                                  growOp3(v3, 133, v347, v298, v511);
                                }
                              }
                              v351 = v518;
                              v352 = 0;
                              if ( (int)*v518 > 0 )
                              {
                                v353 = v516;
                                v354 = v518;
                                while ( !v345 )
                                {
                                  *(_BYTE *)v215 = 1;
                                  if ( a1[2] )
                                  {
                                    v359 = *(_QWORD *)&v518[8 * v352 + 2];
                                    v360 = sqlite3ExprCodeTarget(a1, v359, v353);
                                    if ( v360 != v353 )
                                    {
                                      if ( v359 && ((*(_DWORD *)(v359 + 4) & 0x400000) != 0 || *(_BYTE *)v359 == 0xB0) )
                                        v361 = 80;
                                      else
                                        v361 = 81;
                                      sqlite3VdbeAddOp2(a1[2], v361, v360, v353);
                                    }
                                    v345 = v561;
                                    goto LABEL_562;
                                  }
LABEL_563:
                                  ++v352;
                                  ++v353;
                                  if ( (signed int)v352 >= *v354 )
                                  {
                                    LODWORD(v346) = v524;
                                    v351 = v518;
                                    goto LABEL_565;
                                  }
                                }
                                v355 = *(int *)(v3 + 144);
                                if ( *(_DWORD *)(v3 + 148) > (int)v355 )
                                {
                                  *(_DWORD *)(v3 + 144) = v355 + 1;
                                  v356 = 3 * v355;
                                  v357 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v357 + 8 * v356) = 94;
                                  *(_DWORD *)(v357 + 8 * v356 + 4) = v297;
                                  *(_DWORD *)(v357 + 8 * v356 + 8) = v352;
                                  v358 = v357 + 8 * v356;
                                  *(_DWORD *)(v358 + 12) = v353;
                                  *(_QWORD *)(v358 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v511) = v353;
                                  growOp3(v3, 94, v297, v352, v511);
                                }
LABEL_562:
                                v354 = v518;
                                goto LABEL_563;
                              }
LABEL_565:
                              v362 = v552;
                              if ( v552 )
                                ++*v552;
                              v363 = *(int *)(v3 + 144);
                              v364 = *v351;
                              v365 = v530;
                              if ( *(_DWORD *)(v3 + 148) > (int)v363 )
                              {
                                *(_DWORD *)(v3 + 144) = v363 + 1;
                                v367 = 3 * v363;
                                v368 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v368 + 8 * v367) = 90;
                                *(_DWORD *)(v368 + 8 * v367 + 4) = v365;
                                *(_DWORD *)(v368 + 8 * v367 + 8) = v516;
                                v369 = v368 + 24 * v363;
                                *(_DWORD *)(v369 + 12) = v364;
                                *(_QWORD *)(v369 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = *v351;
                                v366 = growOp3(v3, 90, v530, v516, v511);
                                v362 = v552;
                                LODWORD(v363) = v366;
                              }
                              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                              {
                                if ( !*(_QWORD *)(*(_QWORD *)v3 + 776LL) )
                                {
                                  if ( v362 )
                                  {
                                    v16 = (*v362)-- == 1;
                                    if ( v16 )
                                      sqlite3DbNNFreeNN(*((_QWORD *)v362 + 2), v362);
                                  }
                                }
                              }
                              else
                              {
                                if ( (int)v363 < 0 )
                                  LODWORD(v363) = *(_DWORD *)(v3 + 144) - 1;
                                v370 = *(_QWORD *)(v3 + 136) + 24LL * (int)v363;
                                if ( *(_BYTE *)(v370 + 1) )
                                {
                                  vdbeChangeP4Full(v3, v370, v362, 4294967288LL);
                                }
                                else if ( v362 )
                                {
                                  *(_QWORD *)(v370 + 16) = v362;
                                  *(_BYTE *)(v370 + 1) = -8;
                                }
                              }
                              v371 = *(int *)(v3 + 144);
                              v372 = (unsigned int)(v371 + 1);
                              if ( *(_DWORD *)(v3 + 148) > (int)v371 )
                              {
                                v373 = *(_QWORD *)(v3 + 136);
                                v374 = 3 * v371;
                                *(_DWORD *)(v3 + 144) = v372;
                                *(_DWORD *)(v373 + 8 * v374) = 14;
                                *(_DWORD *)(v373 + 8 * v374 + 4) = v372;
                                v375 = v373 + 24 * v371;
                                *(_DWORD *)(v375 + 8) = 0;
                                *(_DWORD *)(v375 + 12) = v372;
                                *(_QWORD *)(v375 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = v371 + 1;
                                growOp3(v3, 14, v372, 0, v511);
                              }
                              v376 = *v518;
                              v377 = a1[2];
                              v378 = *(int *)(v377 + 144);
                              if ( *(_DWORD *)(v377 + 148) > (int)v378 )
                              {
                                *(_DWORD *)(v377 + 144) = v378 + 1;
                                v379 = 3 * v378;
                                v380 = *(_QWORD *)(v377 + 136);
                                *(_DWORD *)(v380 + 8 * v379 + 4) = v516;
                                *(_QWORD *)(v380 + 8 * v379 + 16) = 0;
                                *(_DWORD *)(v380 + 8 * v379) = 79;
                                v381 = v380 + 8 * v379;
                                *(_DWORD *)(v381 + 8) = v365;
                                *(_DWORD *)(v381 + 12) = v376;
                              }
                              else
                              {
                                LODWORD(v511) = *v518;
                                growOp3(v377, 79, v516, v365, v511);
                              }
                              v382 = *(int *)(v3 + 144);
                              v383 = v541;
                              if ( *(_DWORD *)(v3 + 148) > (int)v382 )
                              {
                                v385 = v523;
                                *(_DWORD *)(v3 + 144) = v382 + 1;
                                v386 = 3 * v382;
                                v387 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v387 + 8 * v386) = 10;
                                v384 = v385 + 1;
                                *(_DWORD *)(v387 + 8 * v386 + 8) = v383;
                                *(_DWORD *)(v387 + 8 * v386 + 4) = v385 + 1;
                                v388 = v387 + 8 * v386;
                                *(_DWORD *)(v388 + 12) = 0;
                                *(_QWORD *)(v388 + 16) = 0;
                              }
                              else
                              {
                                v384 = v523 + 1;
                                LODWORD(v511) = 0;
                                growOp3(v3, 10, v523 + 1, v541, v511);
                                v385 = v523;
                              }
                              v389 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v389 )
                              {
                                *(_DWORD *)(v3 + 144) = v389 + 1;
                                v390 = 3 * v389;
                                v391 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v391 + 8 * v390) = 59;
                                *(_DWORD *)(v391 + 8 * v390 + 4) = v385;
                                *(_DWORD *)(v391 + 8 * v390 + 12) = 0;
                                v392 = v391 + 8 * v390;
                                LODWORD(v391) = v521;
                                *(_QWORD *)(v392 + 16) = 0;
                                *(_DWORD *)(v392 + 8) = v391;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 59, v385, v521, v511);
                              }
                              v393 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v393 )
                              {
                                *(_DWORD *)(v3 + 144) = v393 + 1;
                                v394 = 3 * v393;
                                v395 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v395 + 8 * v394) = 10;
                                *(_DWORD *)(v395 + 8 * v394 + 12) = 0;
                                *(_QWORD *)(v395 + 8 * v394 + 16) = 0;
                                v396 = v395 + 8 * v394;
                                *(_DWORD *)(v396 + 4) = v384 + 1;
                                *(_DWORD *)(v396 + 8) = v520;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 10, v384 + 1, v520, v511);
                              }
                              if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                                v397 = &qword_18013FEA8;
                              else
                                v397 = (__int64 *)(*(_QWORD *)(v3 + 136) + 24 * v371);
                              v398 = v531;
                              v399 = v526;
                              *((_DWORD *)v397 + 2) = *(_DWORD *)(v3 + 144);
                              updateAccumulator(a1, v398, v215, v399);
                              v400 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v400 )
                              {
                                *(_DWORD *)(v3 + 144) = v400 + 1;
                                v401 = 3 * v400;
                                v402 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v402 + 8 * v401 + 8) = v398;
                                *(_DWORD *)(v402 + 8 * v401) = 71;
                                *(_DWORD *)(v402 + 8 * v401 + 4) = 1;
                                v403 = v402 + 8 * v401;
                                *(_DWORD *)(v403 + 12) = 0;
                                *(_QWORD *)(v403 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 71, 1, v398, v511);
                              }
                              if ( v561 )
                              {
                                v404 = *(int *)(v3 + 144);
                                v405 = *(unsigned int *)(v215 + 4);
                                if ( *(_DWORD *)(v3 + 148) > (int)v404 )
                                {
                                  *(_DWORD *)(v3 + 144) = v404 + 1;
                                  v406 = 3 * v404;
                                  v407 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v407 + 8 * v406) = 37;
                                  *(_DWORD *)(v407 + 8 * v406 + 4) = v405;
                                  *(_DWORD *)(v407 + 8 * v406 + 8) = v346;
                                  v408 = v407 + 8 * v406;
                                  *(_DWORD *)(v408 + 12) = 0;
                                  *(_QWORD *)(v408 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v511) = 0;
                                  growOp3(v3, 37, v405, (unsigned int)v346, v511);
                                }
                              }
                              else
                              {
                                sqlite3WhereEnd(v545);
                                sqlite3VdbeChangeToNoop(v3, v542, v409);
                              }
                              if ( v546 )
                                exprListDeleteNN(v519, v546);
                              v410 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v410 )
                              {
                                *(_DWORD *)(v3 + 144) = v410 + 1;
                                v411 = 3 * v410;
                                v412 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v412 + 8 * v411) = 10;
                                *(_DWORD *)(v412 + 8 * v411 + 4) = v384;
                                *(_DWORD *)(v412 + 8 * v411 + 8) = v383;
                                v413 = v412 + 8 * v411;
                                *(_DWORD *)(v413 + 12) = 0;
                                *(_QWORD *)(v413 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 10, v384, v383, v511);
                              }
                              v414 = *(int *)(v3 + 144);
                              v415 = v521;
                              if ( *(_DWORD *)(v3 + 148) > (int)v414 )
                              {
                                *(_DWORD *)(v3 + 144) = v414 + 1;
                                v416 = 3 * v414;
                                v417 = *(_QWORD *)(v3 + 136);
                                *(_QWORD *)(v417 + 8 * v416) = 9;
                                *(_DWORD *)(v417 + 8 * v416 + 8) = v415;
                                *(_DWORD *)(v417 + 8 * v416 + 12) = 0;
                                *(_QWORD *)(v417 + 8 * v416 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 9, 0, v521, v511);
                              }
                              v418 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v418 )
                              {
                                *(_DWORD *)(v3 + 144) = v418 + 1;
                                v419 = 3 * v418;
                                v420 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v420 + 8 * v419) = 71;
                                *(_DWORD *)(v420 + 8 * v419 + 4) = 1;
                                *(_DWORD *)(v420 + 8 * v419 + 12) = 0;
                                v421 = v420 + 24 * v418;
                                LODWORD(v420) = v523;
                                *(_QWORD *)(v421 + 16) = 0;
                                *(_DWORD *)(v421 + 8) = v420;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 71, 1, v523, v511);
                              }
                              v422 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v422 )
                              {
                                *(_DWORD *)(v3 + 144) = v422 + 1;
                                v423 = 3 * v422;
                                v424 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v424 + 8 * v423) = 67;
                                *(_DWORD *)(v424 + 8 * v423 + 4) = v384;
                                *(_QWORD *)(v424 + 8 * v423 + 8) = 0;
                                *(_QWORD *)(v424 + 8 * v423 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 67, v384, 0, v511);
                              }
                              v425 = *(_QWORD *)(v3 + 24);
                              v426 = ~v383;
                              if ( *(_DWORD *)(v425 + 68) + *(_DWORD *)(v425 + 72) >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v425 + 80) + 4LL * v426) = *(_DWORD *)(v3 + 144);
                              else
                                resizeResolveLabel(v425, v3, (unsigned int)v426);
                              v427 = *(int *)(v3 + 144);
                              v428 = v531;
                              v429 = v427 + 2;
                              v430 = v427 + 1;
                              if ( *(_DWORD *)(v3 + 148) > (int)v427 )
                              {
                                *(_DWORD *)(v3 + 144) = v430;
                                v431 = 3 * v427;
                                v432 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v432 + 8 * v431) = 59;
                                *(_DWORD *)(v432 + 8 * v431 + 4) = v428;
                                *(_DWORD *)(v432 + 8 * v431 + 8) = v429;
                                v433 = v432 + 8 * v431;
                                *(_DWORD *)(v433 + 12) = 0;
                                *(_QWORD *)(v433 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 59, v531, v429, v511);
                              }
                              v434 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v434 )
                              {
                                *(_DWORD *)(v3 + 144) = v434 + 1;
                                v435 = 3 * v434;
                                v436 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v436 + 8 * v435) = 67;
                                *(_DWORD *)(v436 + 8 * v435 + 4) = v384;
                                *(_QWORD *)(v436 + 8 * v435 + 8) = 0;
                                *(_QWORD *)(v436 + 8 * v435 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v511) = 0;
                                growOp3(v3, 67, v384, 0, v511);
                              }
                              finalizeAggFunctions(a1, v215);
                              sqlite3ExprIfFalse(a1, v547, v430, 16);
                              v514 = v418;
                              v201 = a3;
                              selectInnerLoop((_DWORD)a1, a2, -1, (unsigned int)&v549, (__int64)&v537, a3, v430, v514);
                              v437 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v437 )
                              {
                                *(_DWORD *)(v3 + 144) = v437 + 1;
                                v438 = 3 * v437;
                                v439 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v439 + 8 * v438 + 4) = v384;
                                *(_QWORD *)(v439 + 8 * v438 + 8) = 0;
                                *(_QWORD *)(v439 + 8 * v438 + 16) = 0;
                                *(_DWORD *)(v439 + 8 * v438) = 67;
                              }
                              else
                              {
                                LODWORD(v512) = 0;
                                growOp3(v3, 67, v384, 0, v512);
                              }
                              v440 = *(_QWORD *)(v3 + 24);
                              v441 = ~v520;
                              if ( *(_DWORD *)(v440 + 68) + *(_DWORD *)(v440 + 72) >= 0 )
                                *(_DWORD *)(*(_QWORD *)(v440 + 80) + 4LL * v441) = *(_DWORD *)(v3 + 144);
                              else
                                resizeResolveLabel(v440, v3, (unsigned int)v441);
                              resetAccumulator(a1, v215);
                              v442 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v442 )
                              {
                                *(_DWORD *)(v3 + 144) = v442 + 1;
                                v443 = 3 * v442;
                                v444 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v444 + 8 * v443 + 8) = v428;
                                *(_DWORD *)(v444 + 8 * v443 + 12) = 0;
                                *(_QWORD *)(v444 + 8 * v443 + 16) = 0;
                                *(_QWORD *)(v444 + 8 * v443) = 71;
                              }
                              else
                              {
                                LODWORD(v512) = 0;
                                growOp3(v3, 71, 0, v428, v512);
                              }
                              v445 = *(int *)(v3 + 144);
                              if ( *(_DWORD *)(v3 + 148) > (int)v445 )
                              {
                                *(_DWORD *)(v3 + 144) = v445 + 1;
                                v446 = 3 * v445;
                                v447 = *(_QWORD *)(v3 + 136);
                                *(_DWORD *)(v447 + 8 * v446) = 67;
                                *(_QWORD *)(v447 + 8 * v446 + 8) = 0;
                                *(_QWORD *)(v447 + 8 * v446 + 16) = 0;
                                *(_DWORD *)(v447 + 8 * v446 + 4) = (_DWORD)v525;
                              }
                              else
                              {
                                LODWORD(v512) = 0;
                                growOp3(v3, 67, (unsigned int)v525, 0, v512);
                              }
                              if ( (_WORD)v532 && v526 )
                                fixDistinctOpenEph(
                                  a1,
                                  v526,
                                  *(unsigned int *)(*(_QWORD *)(v215 + 40) + 16LL),
                                  *(unsigned int *)(*(_QWORD *)(v215 + 40) + 20LL));
                              v196 = a2;
LABEL_743:
                              v199 = *(_QWORD *)(v3 + 24);
                              v503 = ~v415;
                              if ( *(_DWORD *)(v199 + 68) + *(_DWORD *)(v199 + 72) < 0 )
                              {
                                resizeResolveLabel(v199, v3, (unsigned int)v503);
                                v7 = a1;
                                goto LABEL_748;
                              }
                              v202 = v503;
                              v7 = a1;
                              goto LABEL_747;
                            }
                            if ( !v231[6] )
                            {
                              v448 = v231[4];
                              if ( *(_DWORD *)v448 == 1 )
                              {
                                v449 = v231[5];
                                if ( *(_DWORD *)v449 == 1
                                  && !*(_QWORD *)(v449 + 48)
                                  && *(_DWORD *)(v215 + 48) == 1
                                  && !v231[8] )
                                {
                                  v450 = *(const char ***)(v449 + 40);
                                  if ( !*((_BYTE *)v450 + 63) )
                                  {
                                    v451 = *(_QWORD *)(v448 + 8);
                                    if ( *(_BYTE *)v451 == 0xA8
                                      && *(_QWORD *)(v451 + 56) == v215
                                      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v215 + 40) + 8LL) + 4LL) & 0x100) != 0
                                      && (*(_DWORD *)(v451 + 4) & 0x1000004) == 0 )
                                    {
                                      v452 = v450[12];
                                      v453 = -32768;
                                      v454 = a1;
                                      if ( v452 )
                                      {
                                        v453 = 0;
                                        v455 = *(_QWORD *)(*a1 + 32LL);
                                        if ( *(const char **)(v455 + 24) != v452 )
                                        {
                                          do
                                            ++v453;
                                          while ( *(const char **)(32LL * v453 + v455 + 24) != v452 );
                                        }
                                      }
                                      v456 = *((_DWORD *)a1 + 13);
                                      v457 = 0;
                                      mm = 0;
                                      v459 = a1;
                                      *((_DWORD *)a1 + 13) = v456 + 1;
                                      v562 = *((_DWORD *)v450 + 10);
                                      if ( a1[21] )
                                        v459 = (_QWORD *)a1[21];
                                      v460 = *((_DWORD *)v459 + 31);
                                      if ( _bittest(&v460, v453) )
                                      {
                                        if ( v453 != 1 )
                                          goto LABEL_666;
                                      }
                                      else
                                      {
                                        *((_DWORD *)v459 + 31) = v460 | (1 << v453);
                                        if ( v453 == 1 )
                                        {
                                          sqlite3OpenTempDatabase(v459);
                                          goto LABEL_668;
                                        }
LABEL_666:
                                        if ( *(_BYTE *)(*(_QWORD *)(32LL * v453 + *(_QWORD *)(*a1 + 32LL) + 8) + 17LL) )
                                        {
                                          lockTable((_DWORD)a1, v453, *((_DWORD *)v450 + 10), 0, (__int64)*v450);
LABEL_668:
                                          v454 = a1;
                                        }
                                      }
                                      if ( *((char *)v450 + 48) < 0 )
                                      {
                                        for ( mm = v450[2]; mm; mm = (const char *)*((_QWORD *)mm + 5) )
                                        {
                                          if ( (*((_DWORD *)mm + 25) & 3) == 2 )
                                            break;
                                        }
                                      }
                                      if ( (*(_BYTE *)(*(_QWORD *)(a2 + 40) + 72LL) & 1) == 0 )
                                      {
                                        for ( nn = v450[2]; nn; nn = (const char *)*((_QWORD *)nn + 5) )
                                        {
                                          if ( (nn[100] & 4) == 0 )
                                          {
                                            v462 = *((_WORD *)nn + 46);
                                            if ( v462 < *((__int16 *)v450 + 30)
                                              && !*((_QWORD *)nn + 9)
                                              && (!mm || v462 < *((__int16 *)mm + 46)) )
                                            {
                                              mm = nn;
                                            }
                                          }
                                        }
                                      }
                                      if ( mm )
                                      {
                                        v562 = *((_DWORD *)mm + 22);
                                        v457 = sqlite3KeyInfoOfIndex(v454, mm);
                                      }
                                      v463 = *(int *)(v3 + 144);
                                      if ( *(_DWORD *)(v3 + 148) > (int)v463 )
                                      {
                                        *(_DWORD *)(v3 + 144) = v463 + 1;
                                        v464 = 3 * v463;
                                        v465 = *(_QWORD *)(v3 + 136);
                                        *(_DWORD *)(v465 + 8 * v464) = 64880;
                                        *(_DWORD *)(v465 + 8 * v464 + 4) = v456;
                                        *(_DWORD *)(v465 + 8 * v464 + 12) = v453;
                                        v466 = v465 + 8 * v464;
                                        *(_DWORD *)(v466 + 16) = 1;
                                        *(_DWORD *)(v466 + 8) = v562;
                                      }
                                      else
                                      {
                                        addOp4IntSlow(v3, 112, v456, v562, v453, 1);
                                      }
                                      if ( v457 )
                                      {
                                        if ( *(_BYTE *)(*(_QWORD *)v3 + 103LL) )
                                        {
                                          if ( !*(_QWORD *)(*(_QWORD *)v3 + 776LL) )
                                          {
                                            v16 = (*(_DWORD *)v457)-- == 1;
                                            if ( v16 )
                                              sqlite3DbNNFreeNN(*(_QWORD *)(v457 + 16), v457);
                                          }
                                        }
                                        else
                                        {
                                          v467 = *(_QWORD *)(v3 + 136);
                                          v468 = 3LL * *(int *)(v3 + 144) - 3;
                                          v16 = *(_BYTE *)(v467 + 8 * v468 + 1) == 0;
                                          v469 = v467 + 8 * v468;
                                          if ( v16 )
                                          {
                                            *(_QWORD *)(v469 + 16) = v457;
                                            *(_BYTE *)(v469 + 1) = -8;
                                          }
                                          else
                                          {
                                            vdbeChangeP4Full(v3, v469, v457, 4294967288LL);
                                          }
                                        }
                                      }
                                      v470 = a1;
                                      *(_DWORD *)(v215 + 12) = *((_DWORD *)a1 + 14) + 1;
                                      *((_DWORD *)a1 + 14) += *(_DWORD *)(v215 + 32) + *(_DWORD *)(v215 + 48);
                                      v471 = *(_DWORD *)(v215 + 12) + *(_DWORD *)(v215 + 32);
                                      v472 = *(int *)(v3 + 144);
                                      if ( *(_DWORD *)(v3 + 148) > (int)v472 )
                                      {
                                        *(_DWORD *)(v3 + 144) = v472 + 1;
                                        v473 = 3 * v472;
                                        v474 = *(_QWORD *)(v3 + 136);
                                        *(_DWORD *)(v474 + 8 * v473) = 98;
                                        *(_DWORD *)(v474 + 8 * v473 + 4) = v456;
                                        *(_DWORD *)(v474 + 8 * v473 + 8) = v471;
                                        v475 = v474 + 8 * v473;
                                        *(_DWORD *)(v475 + 12) = 0;
                                        *(_QWORD *)(v475 + 16) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v509) = 0;
                                        growOp3(v3, 98, v456, v471, v509);
                                      }
                                      v476 = *(int *)(v3 + 144);
                                      if ( *(_DWORD *)(v3 + 148) > (int)v476 )
                                      {
                                        *(_DWORD *)(v3 + 144) = v476 + 1;
                                        v477 = 3 * v476;
                                        v478 = *(_QWORD *)(v3 + 136);
                                        *(_DWORD *)(v478 + 8 * v477) = 122;
                                        *(_DWORD *)(v478 + 8 * v477 + 4) = v456;
                                        *(_QWORD *)(v478 + 8 * v477 + 8) = 0;
                                        *(_QWORD *)(v478 + 8 * v477 + 16) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v509) = 0;
                                        growOp3(v3, 122, v456, 0, v509);
                                      }
                                      if ( *((_BYTE *)a1 + 299) == 2 )
                                      {
                                        if ( !mm || *((char *)v450 + 48) < 0 && (*((_DWORD *)mm + 25) & 3) == 2 )
                                        {
                                          v480 = byte_180122168;
                                          LODWORD(v545) = 0;
                                          v479 = byte_180122168;
                                        }
                                        else
                                        {
                                          v479 = *(const char **)mm;
                                          v480 = byte_180122168;
                                        }
                                        if ( (_DWORD)v545 )
                                          v480 = " USING COVERING INDEX ";
                                        sqlite3VdbeExplain(a1, 0, "SCAN %s%s%s", *v450, v480, v479);
                                      }
LABEL_742:
                                      v415 = v521;
                                      *(_QWORD *)&v549 = 0;
                                      sqlite3ExprIfFalse(v470, v547, v521, 16);
                                      v196 = a2;
                                      selectInnerLoop((_DWORD)v470, a2, -1, 0, 0, a3, v415, v415);
                                      v201 = a3;
                                      goto LABEL_743;
                                    }
                                  }
                                }
                              }
                            }
                            v481 = *(_DWORD *)(v215 + 48);
                            v482 = 0;
                            v483 = 0;
                            v484 = 0;
                            if ( *(_DWORD *)(v215 + 36) )
                            {
                              v485 = 0;
                              if ( v481 <= 0 )
                              {
LABEL_716:
                                v7 = a1;
                                if ( v485 == v481 )
                                {
                                  ++*((_DWORD *)a1 + 14);
                                  v487 = *(int *)(v3 + 144);
                                  v482 = *((_DWORD *)a1 + 14);
                                  if ( *(_DWORD *)(v3 + 148) > (int)v487 )
                                  {
                                    *(_DWORD *)(v3 + 144) = v487 + 1;
                                    v488 = 3 * v487;
                                    v489 = *(_QWORD *)(v3 + 136);
                                    *(_QWORD *)(v489 + 8 * v488) = 71;
                                    *(_DWORD *)(v489 + 8 * v488 + 8) = v482;
                                    *(_DWORD *)(v489 + 8 * v488 + 12) = 0;
                                    *(_QWORD *)(v489 + 8 * v488 + 16) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v509) = 0;
                                    growOp3(v3, 71, 0, v482, v509);
                                  }
                                }
                              }
                              else
                              {
                                v486 = *(_QWORD *)(v215 + 40);
                                while ( (*(_DWORD *)(*(_QWORD *)(v486 + 24LL * v485) + 4LL) & 0x1000000) != 0
                                     || (*(_BYTE *)(*(_QWORD *)(v486 + 24LL * v485 + 8) + 4LL) & 0x20) == 0 )
                                {
                                  if ( (int)++v485 >= v481 )
                                    goto LABEL_716;
                                }
LABEL_723:
                                v7 = a1;
                              }
                            }
                            else
                            {
                              if ( v481 != 1 )
                                goto LABEL_723;
                              v490 = *(int **)(v215 + 40);
                              v7 = a1;
                              if ( v490[4] >= 0 )
                              {
                                v483 = *(_QWORD *)(*(_QWORD *)v490 + 32LL);
                                v484 = v483 != 0 ? 0x500 : 0;
                              }
                            }
                            *(_DWORD *)(v215 + 12) = *((_DWORD *)v7 + 14) + 1;
                            *((_DWORD *)v7 + 14) += *(_DWORD *)(v215 + 32) + *(_DWORD *)(v215 + 48);
                            resetAccumulator(v7, v215);
                            v491 = sqlite3WhereBegin((_DWORD)v7, (_DWORD)v515, v528, v548, v483, a2, v484 | v240, 0);
                            v492 = v491;
                            if ( v491 )
                            {
                              v493 = *(unsigned __int8 *)(v491 + 67);
                              updateAccumulator(v7, v482, v215, *(unsigned __int8 *)(v491 + 67));
                              if ( v493 )
                              {
                                v494 = *(_QWORD *)(v215 + 40);
                                if ( v494 )
                                  fixDistinctOpenEph(
                                    v7,
                                    v493,
                                    *(unsigned int *)(v494 + 16),
                                    *(unsigned int *)(v494 + 20));
                              }
                              if ( v482 )
                              {
                                v495 = *(int *)(v3 + 144);
                                if ( *(_DWORD *)(v3 + 148) > (int)v495 )
                                {
                                  *(_DWORD *)(v3 + 144) = v495 + 1;
                                  v496 = 3 * v495;
                                  v497 = *(_QWORD *)(v3 + 136);
                                  *(_DWORD *)(v497 + 8 * v496) = 71;
                                  *(_DWORD *)(v497 + 8 * v496 + 4) = 1;
                                  *(_DWORD *)(v497 + 8 * v496 + 8) = v482;
                                  v498 = v497 + 8 * v496;
                                  *(_DWORD *)(v498 + 12) = 0;
                                  *(_QWORD *)(v498 + 16) = 0;
                                }
                                else
                                {
                                  LODWORD(v513) = 0;
                                  growOp3(v3, 71, 1, v482, v513);
                                }
                              }
                              if ( v240 && (*(_BYTE *)(v492 + 68) & 4) != 0 && *(_BYTE *)(v492 + 65) )
                              {
                                v499 = *(unsigned __int8 *)(v492 + 64) - 1;
                                if ( v499 < 0 )
                                {
LABEL_738:
                                  v501 = *(int *)(v3 + 144);
                                  v502 = *(_DWORD *)(v492 + 52);
                                  if ( *(_DWORD *)(v3 + 148) > (int)v501 )
                                  {
                                    *(_DWORD *)(v3 + 144) = v501 + 1;
                                    v504 = 3 * v501;
                                    v505 = *(_QWORD *)(v3 + 136);
                                    *(_QWORD *)(v505 + 8 * v504) = 9;
                                    *(_DWORD *)(v505 + 8 * v504 + 8) = v502;
                                    *(_DWORD *)(v505 + 8 * v504 + 12) = 0;
                                    *(_QWORD *)(v505 + 8 * v504 + 16) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v513) = 0;
                                    growOp3(v3, 9, 0, v502, v513);
                                  }
                                }
                                else
                                {
                                  while ( 1 )
                                  {
                                    v500 = 112LL * (unsigned int)v499;
                                    if ( (*(_BYTE *)(*(_QWORD *)(v500 + v492 + 960) + 56LL) & 4) != 0 )
                                      break;
                                    if ( --v499 < 0 )
                                      goto LABEL_738;
                                  }
                                  sqlite3VdbeGoto(v3, *(unsigned int *)(v500 + v492 + 880));
                                }
                              }
                              sqlite3WhereEnd(v492);
                              finalizeAggFunctions(v7, v215);
                              v470 = a1;
                              goto LABEL_742;
                            }
                            v246 = v519;
                          }
                          v9 = 1;
LABEL_758:
                          if ( v548 )
                            exprListDeleteNN(v246, v548);
                          goto LABEL_78;
                        }
                      }
                      else if ( *((unsigned __int8 *)qword_180114680 + v243) != *((unsigned __int8 *)qword_180114680
                                                                                + v244) )
                      {
                        goto LABEL_414;
                      }
                      ++v235;
                    }
                  }
                  if ( (unsigned __int64)v219 >= v218[61] )
                  {
                    *v219 = v218[57];
                    v218[57] = v219;
                    goto LABEL_362;
                  }
                }
                if ( v218[97] )
                {
                  measureAllocationSize(v218, *(_QWORD *)(v215 + 40));
                  goto LABEL_362;
                }
              }
              sqlite3_free(v219);
            }
            if ( !v218 )
              goto LABEL_369;
            goto LABEL_362;
          }
        }
      }
    }
    else
    {
      if ( (int)v146 >= 0 )
        v152 = v146;
      else
        v152 = *(_DWORD *)(v3 + 144) - 1;
      v153 = *(_QWORD *)(v3 + 136) + 24LL * v152;
      if ( *(_BYTE *)(v153 + 1) )
      {
        vdbeChangeP4Full(v3, v153, v143, 4294967288LL);
        DWORD2(v550) = v146;
        goto LABEL_226;
      }
      if ( v143 )
      {
        *(_QWORD *)(v153 + 16) = v143;
        *(_BYTE *)(v153 + 1) = -8;
      }
    }
    DWORD2(v550) = v146;
    goto LABEL_226;
  }
LABEL_73:
  v35 = multiSelect(v7, (unsigned __int8 *)v6, v4);
  if ( !*(_QWORD *)(v6 + 88) )
    sqlite3VdbeExplainPop(v7);
  return v35;
}

```

## disassembly

```asm
0x1800971f0  mov     [rsp-8+arg_10], r8
0x1800971f5  mov     [rsp-8+arg_8], rdx
0x1800971fa  mov     [rsp-8+arg_0], rcx
0x1800971ff  push    rbp
0x180097200  push    rbx
0x180097201  push    rsi
0x180097202  push    r13
0x180097204  push    r14
0x180097206  lea     rbp, [rsp-0B0h]
0x18009720e  sub     rsp, 1B0h
0x180097215  mov     rbx, [rcx+10h]
0x180097219  mov     r14, r8
0x18009721c  mov     rax, [rcx]
0x18009721f  mov     rsi, rdx
0x180097222  mov     [rsp+1D0h+var_180], rax
0x180097227  mov     r13, rcx
0x18009722a  mov     [rbp+0D0h+var_E8], rbx
0x18009722e  test    rbx, rbx
0x180097231  jnz     short loc_180097252
0x180097233  cmp     [rcx+0A8h], rbx
0x18009723a  jnz     short loc_180097246
0x18009723c  test    byte ptr [rax+60h], 8
0x180097240  jnz     short loc_180097246
0x180097242  mov     byte ptr [rcx+23h], 1
0x180097246  call    sqlite3VdbeCreate
0x18009724b  mov     rbx, rax
0x18009724e  mov     [rbp+0D0h+var_E8], rax
0x180097252  test    rsi, rsi
0x180097255  jz      loc_18009A947
0x18009725b  cmp     dword ptr [r13+30h], 0
0x180097260  jnz     loc_18009A947
0x180097266  xor     r9d, r9d
0x180097269  mov     [rsp+1D0h+var_1B0], 0
0x180097272  xor     r8d, r8d
0x180097275  mov     edx, 15h
0x18009727a  mov     rcx, r13
0x18009727d  call    sqlite3AuthCheck
0x180097282  test    eax, eax
0x180097284  jnz     loc_18009A947
0x18009728a  cmp     byte ptr [r14], 6
0x18009728e  mov     [rsp+1D0h+var_38], r15
0x180097296  mov     r15d, 1
0x18009729c  mov     [rbp+0D0h+var_D8], r15
0x1800972a0  ja      short loc_1800972CD
0x1800972a2  mov     r8, [rsi+48h]
0x1800972a6  test    r8, r8
0x1800972a9  jz      short loc_1800972C2
0x1800972ab  lea     rdx, sqlite3ExprListDelete
0x1800972b2  mov     rcx, r13
0x1800972b5  call    sqlite3ParserAddCleanup
0x1800972ba  mov     qword ptr [rsi+48h], 0
0x1800972c2  and     dword ptr [rsi+4], 0FFFFFFFEh
0x1800972c6  or      dword ptr [rsi+4], 400000h
0x1800972cd  mov     [rsp+1D0h+var_28], rdi
0x1800972d5  xor     r8d, r8d
0x1800972d8  mov     rdx, rsi
0x1800972db  mov     [rsp+1D0h+var_30], r12
0x1800972e3  mov     rcx, r13
0x1800972e6  call    sqlite3SelectPrep
0x1800972eb  cmp     dword ptr [r13+30h], 0
0x1800972f0  lea     r8, qword_18013FEA8
0x1800972f7  jnz     loc_180097646
0x1800972fd  mov     r11d, [rsi+4]
0x180097301  bt      r11d, 17h
0x180097306  jnb     short loc_180097349
0x180097308  mov     rdx, [rsi+28h]
0x18009730c  lea     rdi, [rdx+8]
0x180097310  mov     rcx, rdi
0x180097313  call    sameSrcAlias
0x180097318  test    eax, eax
0x18009731a  jz      short loc_180097340
0x18009731c  mov     r8, [rdi+18h]
0x180097320  test    r8, r8
0x180097323  jnz     short loc_18009732C
0x180097325  mov     rax, [rdi+20h]
0x180097329  mov     r8, [rax]
0x18009732c  lea     rdx, aTargetObjectAl; "target object/alias may not appear in F"...
0x180097333  mov     rcx, r13
0x180097336  call    sqlite3ErrorMsg
0x18009733b  jmp     loc_18009763F
0x180097340  btr     r11d, 17h
0x180097345  mov     [rsi+4], r11d
0x180097349  cmp     byte ptr [r14], 9
0x18009734d  jnz     short loc_18009735A
0x18009734f  mov     rdx, rsi
0x180097352  mov     rcx, r13
0x180097355  call    sqlite3GenerateColumnNames
0x18009735a  mov     rdx, rsi
0x18009735d  mov     rcx, r13
0x180097360  call    sqlite3WindowRewrite
0x180097365  test    eax, eax
0x180097367  jnz     loc_18009763F
0x18009736d  mov     eax, [rsi+4]
0x180097370  xorps   xmm0, xmm0
0x180097373  mov     r10, [rsi+28h]
0x180097377  and     eax, 8
0x18009737a  mov     r12d, 0
0x180097380  mov     [rsp+1D0h+var_158], eax
0x180097384  mov     rax, [rsi+48h]
0x180097388  setnz   r12b
0x18009738c  xor     edi, edi
0x18009738e  mov     [rsp+1D0h+var_190], r10
0x180097393  movups  [rbp+0D0h+var_B8], xmm0
0x180097397  mov     [rsp+1D0h+var_160], rax
0x18009739c  movups  [rbp+0D0h+var_A8], xmm0
0x1800973a0  mov     qword ptr [rbp+0D0h+var_B8], rax
0x1800973a4  movups  [rbp+0D0h+var_98], xmm0
0x1800973a8  cmp     [rsi+50h], rdi
0x1800973ac  jnz     loc_1800975D9
0x1800973b2  mov     rdx, [rsp+1D0h+var_180]
0x1800973b7  cmp     edi, [r10]
0x1800973ba  jge     loc_180097663
0x1800973c0  movsxd  rax, edi
0x1800973c3  imul    rsi, rax, 68h ; 'h'
0x1800973c7  add     rsi, r10
0x1800973ca  movzx   r8d, byte ptr [rsi+44h]
0x1800973cf  mov     r14, [rsi+30h]
0x1800973d3  mov     r15, [rsi+28h]
0x1800973d7  test    r8b, 48h
0x1800973db  jz      loc_1800974B3
0x1800973e1  mov     rcx, [rbp+0D0h+arg_8]
0x1800973e8  and     r8d, 40h
0x1800973ec  mov     edx, [rsi+4Ch]
0x1800973ef  mov     rcx, [rcx+30h]
0x1800973f3  call    sqlite3ExprImpliesNonNullRow
0x1800973f8  mov     rdx, [rsp+1D0h+var_180]
0x1800973fd  test    eax, eax
0x1800973ff  jz      loc_1800974AE
0x180097405  test    dword ptr [rdx+60h], 2000h
0x18009740c  jnz     loc_1800974AE
0x180097412  movzx   eax, byte ptr [rsi+44h]
0x180097416  test    al, 8
0x180097418  jz      short loc_180097427
0x18009741a  test    al, 10h
0x18009741c  jz      short loc_180097422
0x18009741e  and     al, 0F7h
0x180097420  jmp     short loc_180097424
0x180097422  and     al, 0D7h
0x180097424  mov     [rsi+44h], al
0x180097427  mov     r10, [rsp+1D0h+var_190]
0x18009742c  test    al, 40h
0x18009742e  jz      short loc_18009748B
0x180097430  mov     eax, [r10]
0x180097433  lea     edx, [rdi+1]
0x180097436  cmp     edx, eax
0x180097438  jge     short loc_180097469
0x18009743a  nop     word ptr [rax+rax+00h]
0x180097440  movsxd  rax, edx
0x180097443  imul    rcx, rax, 68h ; 'h'
0x180097447  movzx   eax, byte ptr [rcx+r10+44h]
0x18009744d  test    al, 10h
0x18009744f  jz      short loc_180097460
0x180097451  test    al, 8
0x180097453  jz      short loc_180097459
0x180097455  and     al, 0EFh
0x180097457  jmp     short loc_18009745B
0x180097459  and     al, 0CFh
0x18009745b  mov     [rcx+r10+44h], al
0x180097460  mov     eax, [r10]
0x180097463  inc     edx
0x180097465  cmp     edx, eax
0x180097467  jl      short loc_180097440
0x180097469  lea     edx, [rax-1]
0x18009746c  cmp     edx, edi
0x18009746e  jl      short loc_18009748B
0x180097470  movsxd  rax, edx
0x180097473  imul    rcx, rax, 68h ; 'h'
0x180097477  and     byte ptr [rcx+r10+44h], 0BFh
0x18009747d  test    byte ptr [rcx+r10+44h], 10h
0x180097483  jnz     short loc_18009748B
0x180097485  dec     edx
0x180097487  cmp     edx, edi
0x180097489  jge     short loc_180097470
0x18009748b  mov     rax, [rbp+0D0h+arg_8]
0x180097492  movzx   r8d, byte ptr [r10+44h]
0x180097497  mov     edx, [rsi+4Ch]
0x18009749a  and     r8d, 40h
0x18009749e  mov     rcx, [rax+30h]
0x1800974a2  call    unsetJoinExpr
0x1800974a7  mov     rdx, [rsp+1D0h+var_180]
0x1800974ac  jmp     short loc_1800974B3
0x1800974ae  mov     r10, [rsp+1D0h+var_190]
0x1800974b3  test    r14, r14
0x1800974b6  jz      loc_1800975BE
0x1800974bc  mov     rax, [r14+20h]
0x1800974c0  movsx   r8d, word ptr [r15+36h]
0x1800974c5  mov     ecx, [rax]
0x1800974c7  cmp     r8d, ecx
0x1800974ca  jnz     loc_180097623
0x1800974d0  test    dword ptr [rsi+48h], 100h
0x1800974d7  jz      short loc_1800974E7
0x1800974d9  mov     rax, [rsi+68h]
0x1800974dd  cmp     byte ptr [rax+12h], 0
0x1800974e1  jz      loc_1800975BE
0x1800974e7  mov     eax, [r14+4]
0x1800974eb  mov     rsi, [rbp+0D0h+arg_8]
0x1800974f2  test    al, 8
0x1800974f4  jnz     loc_1800975C5
0x1800974fa  mov     r8, [r14+48h]
0x1800974fe  test    r8, r8
0x180097501  jz      short loc_180097565
0x180097503  cmp     qword ptr [rsi+48h], 0
0x180097508  jnz     short loc_180097510
0x18009750a  cmp     dword ptr [r10], 1
0x18009750e  jle     short loc_180097548
0x180097510  cmp     qword ptr [r14+60h], 0
0x180097515  jnz     short loc_180097548
0x180097517  bt      eax, 1Bh
0x18009751b  jb      short loc_180097548
0x18009751d  test    dword ptr [rsi+4], 8000000h
0x180097524  jnz     short loc_180097548
0x180097526  test    dword ptr [rdx+60h], 40000h
0x18009752d  jnz     short loc_180097548
0x18009752f  lea     rdx, sqlite3ExprListDelete
0x180097536  mov     rcx, r13
0x180097539  call    sqlite3ParserAddCleanup
0x18009753e  mov     qword ptr [r14+48h], 0
0x180097546  jmp     short loc_180097565
0x180097548  test    edi, edi
0x18009754a  jnz     short loc_180097565
0x18009754c  test    dword ptr [rsi+4], 40000h
0x180097553  jz      short loc_180097565
0x180097555  cmp     dword ptr [r10], 1
0x180097559  jz      short loc_1800975C5
0x18009755b  test    byte ptr [r10+0ACh], 22h
0x180097563  jnz     short loc_1800975C5
0x180097565  mov     r9d, r12d
0x180097568  mov     r8d, edi
0x18009756b  mov     rdx, rsi
0x18009756e  mov     rcx, r13
0x180097571  call    flattenSubquery
0x180097576  test    eax, eax
0x180097578  jz      short loc_18009758A
0x18009757a  cmp     dword ptr [r13+30h], 0
0x18009757f  jnz     loc_180097639
0x180097585  mov     edi, 0FFFFFFFFh
0x18009758a  mov     rdx, [rsp+1D0h+var_180]
0x18009758f  cmp     byte ptr [rdx+67h], 0
0x180097593  jnz     loc_180097639
0x180097599  mov     r14, [rbp+0D0h+arg_10]
0x1800975a0  mov     r10, [rsi+28h]
0x1800975a4  mov     [rsp+1D0h+var_190], r10
0x1800975a9  cmp     byte ptr [r14], 8
0x1800975ad  jbe     short loc_1800975CC
0x1800975af  mov     rax, [rsi+48h]
0x1800975b3  mov     [rsp+1D0h+var_160], rax
0x1800975b8  mov     qword ptr [rbp+0D0h+var_B8], rax
0x1800975bc  jmp     short loc_1800975CC
0x1800975be  mov     rsi, [rbp+0D0h+arg_8]
0x1800975c5  mov     r14, [rbp+0D0h+arg_10]
0x1800975cc  inc     edi
0x1800975ce  cmp     qword ptr [rsi+50h], 0
0x1800975d3  jz      loc_1800973B7
0x1800975d9  mov     r8, r14
0x1800975dc  mov     rdx, rsi
0x1800975df  mov     rcx, r13
0x1800975e2  call    multiSelect
0x1800975e7  cmp     qword ptr [rsi+58h], 0
0x1800975ec  mov     r9d, eax
0x1800975ef  jnz     short loc_1800975F9
0x1800975f1  mov     rcx, r13
0x1800975f4  call    sqlite3VdbeExplainPop
0x1800975f9  mov     eax, r9d
0x1800975fc  mov     r12, [rsp+1D0h+var_30]
0x180097604  mov     rdi, [rsp+1D0h+var_28]
0x18009760c  mov     r15, [rsp+1D0h+var_38]
0x180097614  add     rsp, 1B0h
0x18009761b  pop     r14
0x18009761d  pop     r13
0x18009761f  pop     rsi
0x180097620  pop     rbx
0x180097621  pop     rbp
0x180097622  retn
0x180097623  mov     r9, [r15]
0x180097626  lea     rdx, aExpectedDColum; "expected %d columns for '%s' but got %d"
0x18009762d  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x180097631  mov     rcx, r13
0x180097634  call    sqlite3ErrorMsg
0x180097639  mov     r15d, 1
0x18009763f  lea     r8, qword_18013FEA8
0x180097646  movsxd  rcx, dword ptr [r13+138h]
0x18009764d  test    ecx, ecx
0x18009764f  jnz     loc_18009A918
0x180097655  xor     eax, eax
0x180097657  mov     [r13+138h], eax
0x18009765e  mov     eax, r15d
0x180097661  jmp     short loc_1800975FC
0x180097663  mov     rax, [rsi+30h]
0x180097667  mov     r12, [rsp+1D0h+var_180]
0x18009766c  test    rax, rax
0x18009766f  jz      short loc_180097691
0x180097671  cmp     byte ptr [rax], 2Ch ; ','
0x180097674  jnz     short loc_180097691
0x180097676  test    dword ptr [r12+60h], 8000h
0x18009767f  jnz     short loc_180097691
0x180097681  mov     rdx, rsi
0x180097684  mov     rcx, r13
0x180097687  call    propagateConstants
0x18009768c  mov     r10, [rsp+1D0h+var_190]
0x180097691  test    dword ptr [r12+60h], 201h
  ... truncated ...
```
