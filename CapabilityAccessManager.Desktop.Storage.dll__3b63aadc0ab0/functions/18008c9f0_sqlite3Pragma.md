# sqlite3Pragma

- ea: `0x18008c9f0`
- end: `0x180091d04`
- name: `sqlite3Pragma`
- size: `21268`
- prototype: ``
- caller_count: `1`
- callee_count: `102`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d8b00`

## callees

- `0x180003060`
- `0x180004dd0`
- `0x180005450`
- `0x180005980`
- `0x1800094b0`
- `0x18000f510`
- `0x18000f610`
- `0x180011c10`
- `0x180016d80`
- `0x180023ba0`
- `0x180023dd0`
- `0x18002aef0`
- `0x18002b2d0`
- `0x18002b330`
- `0x1800319d0`
- `0x18003a790`
- `0x1800441f0`
- `0x180044640`
- `0x180045cc0`
- `0x180045e20`
- `0x18004c5e0`
- `0x18004dba0`
- `0x1800525d0`
- `0x180057830`
- `0x180057930`
- `0x18005bf90`
- `0x18005e410`
- `0x18005e570`
- `0x1800613f0`
- `0x180061750`
- `0x1800658d0`
- `0x1800669c0`
- `0x1800684f0`
- `0x18006a650`
- `0x18006a6e0`
- `0x18006a780`
- `0x18006a830`
- `0x18006a990`
- `0x18006d4b0`
- `0x18006d570`
- `0x180071300`
- `0x180071400`
- `0x1800714d0`
- `0x180071770`
- `0x1800743d0`
- `0x180075580`
- `0x180075ae0`
- `0x1800798f0`
- `0x180079d20`
- `0x18007a980`

## string_xrefs

- `0x18008e3da`: `sqlite_temp_schema`
- `0x18008dc04`: `not a writable directory`
- `0x18008dda1`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
__int64 __fastcall sqlite3Pragma(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  char *v5; // rbx
  __int64 v7; // rsi
  __int64 result; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  int Db; // eax
  __int64 v17; // rsi
  __int64 v18; // rsi
  __int64 v19; // rax
  char *v20; // r15
  _BYTE *v21; // r13
  _DWORD *v22; // rdi
  _QWORD *v23; // rax
  int v24; // r15d
  __int64 v25; // rcx
  int v26; // r12d
  int DbName; // eax
  __int64 v28; // rdi
  __int64 v29; // rcx
  int v30; // r13d
  _QWORD *v31; // rax
  bool v32; // zf
  __int64 v33; // rdx
  char *v34; // rdi
  __int64 v35; // rsi
  __int64 v36; // rax
  int v37; // r15d
  signed __int64 v38; // rax
  __int64 v39; // rdx
  int v40; // r14d
  __int64 v41; // rax
  __int64 v42; // rax
  size_t v43; // r15
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  char *v49; // rbx
  int v50; // eax
  char *v51; // rbx
  int v52; // eax
  __int64 v53; // rax
  __int64 v54; // r8
  __int64 v55; // rdi
  _DWORD *v56; // r15
  char v57; // al
  char *v58; // r11
  __int64 v59; // rcx
  __int64 v60; // r11
  _DWORD *v61; // rax
  int v62; // edi
  __int64 v63; // rdi
  __int64 AutoVacuum; // rdx
  __int64 v65; // rdx
  _QWORD *v66; // r12
  __int64 v67; // rdi
  int v68; // r15d
  __int64 v69; // r11
  int v70; // esi
  int v71; // eax
  unsigned int v72; // edi
  int v73; // eax
  const char *v74; // r10
  char *v75; // r8
  const char *v76; // r9
  __int64 v77; // rdx
  __int64 v78; // rax
  __int64 v79; // rdx
  char *v80; // r8
  const char *i3; // r9
  __int64 v82; // rax
  int v83; // eax
  int v84; // r8d
  __int64 *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rax
  int v88; // r10d
  __int64 v89; // r11
  char *v90; // r8
  int v91; // edx
  char *v92; // r9
  unsigned int v93; // ecx
  int i2; // edi
  __int64 v95; // rdx
  __int64 *v96; // rcx
  __int64 v97; // rax
  __int64 v98; // rdi
  __int64 v99; // rcx
  __int64 v100; // rdi
  char *v101; // r8
  const char *v102; // r9
  __int64 v103; // rdx
  __int64 v104; // rax
  unsigned int v105; // esi
  char *v106; // r9
  const char *v107; // r8
  __int64 v108; // rdx
  __int64 v109; // rax
  char *v110; // r8
  const char *v111; // r9
  __int64 v112; // rdx
  __int64 v113; // rax
  unsigned __int8 v114; // dl
  int v115; // edi
  _DWORD *v116; // rax
  unsigned int v117; // edi
  unsigned int v118; // edi
  int v119; // eax
  int Int32; // eax
  __int64 v121; // r8
  int v122; // ebx
  _QWORD *v123; // rdi
  char v124; // al
  __int64 v125; // rcx
  __int64 v126; // rdx
  unsigned __int64 v127; // rcx
  _QWORD *v128; // rdx
  int v129; // esi
  __int64 v130; // rdi
  __int64 v131; // r15
  __int64 *v132; // r12
  __int64 v133; // rcx
  int v134; // eax
  int v135; // esi
  __int64 v136; // rdi
  __int64 v137; // r14
  __int64 *v138; // r15
  __int64 v139; // rcx
  _DWORD *v140; // rcx
  int v141; // ecx
  int v142; // edi
  char *v143; // r9
  const char *v144; // r8
  __int64 v145; // rax
  char *v146; // r8
  const char *i6; // r9
  __int64 v148; // rdx
  __int64 v149; // rax
  __int64 v150; // rbx
  __int64 v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rax
  int v155; // eax
  unsigned __int64 v156; // rax
  unsigned __int64 v157; // rdi
  char SafetyLevel; // al
  __int64 v159; // rcx
  __int64 v160; // rax
  __int64 v161; // rax
  __int64 v162; // rdx
  __int16 *v163; // rsi
  __int64 v164; // r9
  int v165; // ecx
  __int64 v166; // r12
  _QWORD *v167; // r13
  int v168; // eax
  int v169; // r15d
  __int16 v170; // r8
  unsigned int v171; // r14d
  int v172; // esi
  __int64 v173; // r9
  __int64 v174; // rax
  __int64 v175; // rax
  _DWORD *v176; // rcx
  const char *v177; // r8
  int v178; // r13d
  _BYTE *v179; // rcx
  __int64 v180; // r14
  __int64 v181; // rdx
  __int64 v182; // rax
  __int64 v183; // rcx
  int v184; // esi
  _QWORD *v185; // rax
  __int64 v186; // r8
  __int64 v187; // rdi
  _QWORD *v188; // r15
  char *v189; // rax
  const char **v190; // rdi
  const char *v191; // r11
  int v192; // edx
  const char *v193; // r9
  const char *v194; // r8
  _BYTE *v195; // r8
  const char *i5; // r9
  __int64 v197; // rax
  _QWORD *Index; // rsi
  __int64 v199; // rax
  unsigned int v200; // eax
  __int64 v201; // r8
  int v202; // edx
  int v203; // r12d
  __int64 v204; // rdi
  __int64 v205; // rax
  __int64 v206; // rdi
  unsigned int v207; // eax
  _QWORD *v208; // rdi
  unsigned int v209; // esi
  unsigned int v210; // edi
  _QWORD *v211; // rdx
  __int64 **v212; // rdi
  unsigned int v213; // esi
  unsigned int v214; // esi
  __int64 k; // r14
  __int64 m; // rdi
  _QWORD *n; // rdi
  _QWORD *v218; // rdi
  __int64 i4; // rdi
  __int64 v220; // rax
  __int64 v221; // rdi
  unsigned int v222; // eax
  _DWORD *v223; // rcx
  unsigned int v224; // r14d
  __int64 v225; // rdx
  int j; // esi
  __int64 v227; // rdx
  __int64 v228; // r8
  int v229; // eax
  _QWORD *v230; // r8
  int v231; // r12d
  unsigned int v232; // r13d
  __int64 v233; // rax
  const char **v234; // rax
  _BYTE *v235; // rdi
  __int64 Table; // rax
  const char *v237; // rsi
  __int64 v238; // rcx
  signed int v239; // edi
  __int64 v240; // rdx
  _DWORD *v241; // rcx
  __int64 v242; // rdx
  int v243; // eax
  int v244; // ecx
  __int64 v245; // r14
  int v246; // r15d
  __int64 v247; // rsi
  int v248; // eax
  __int64 v249; // r13
  _DWORD *v250; // r14
  int v251; // eax
  __int64 v252; // r15
  int v253; // edi
  __int64 v254; // rcx
  __int64 v255; // rax
  __int64 v256; // r13
  _QWORD *v257; // rsi
  int v258; // edi
  unsigned int v259; // r12d
  int v260; // ecx
  int v261; // r14d
  int v262; // r9d
  unsigned int v263; // edi
  __int64 v264; // rax
  int v265; // edi
  __int64 v266; // rdx
  __int64 v267; // rcx
  int v268; // r12d
  int v269; // eax
  void (*v270)(void); // rax
  __int64 *v271; // rax
  char v272; // al
  int v273; // esi
  int v274; // r14d
  __int64 v275; // rax
  __int64 v276; // r9
  __int64 v277; // rax
  signed int v278; // r11d
  _QWORD *v279; // rax
  _DWORD *v280; // rcx
  int v281; // esi
  int v282; // eax
  int v283; // edx
  __int64 v284; // r14
  _QWORD *v285; // r8
  __int64 v286; // rax
  __int64 v287; // rax
  int ii; // ecx
  int v289; // eax
  int *v290; // rax
  int *v291; // rdi
  __int64 v292; // r10
  int v293; // r9d
  _QWORD *jj; // r8
  __int64 v295; // rdx
  __int64 v296; // rcx
  __int64 kk; // rdx
  int v298; // eax
  __int64 v299; // rdx
  __int64 v300; // rax
  int v301; // edi
  __int64 v302; // rsi
  __int64 v303; // rdi
  int v304; // eax
  __int64 v305; // rdx
  __int64 *v306; // rax
  _QWORD *v307; // r14
  const char **v308; // r14
  __int64 v309; // rdi
  int v310; // ecx
  char v311; // al
  int v312; // eax
  unsigned __int8 v313; // al
  int v314; // edx
  int v315; // r8d
  int v316; // eax
  int v317; // edx
  const char *v318; // rsi
  unsigned int v319; // edi
  int v320; // esi
  int v321; // eax
  int v322; // r9d
  int v323; // edx
  int mm; // r8d
  int v325; // eax
  int v326; // r9d
  const char *nn; // rcx
  __int64 *v328; // rax
  unsigned int v329; // edi
  __int64 v330; // rsi
  __int64 v331; // rdi
  int v332; // eax
  __int64 v333; // rdx
  __int64 *v334; // rax
  __int64 *v335; // rax
  __int64 v336; // rsi
  int v337; // edi
  unsigned int v338; // r14d
  int v339; // ebx
  __int64 v340; // rax
  __int64 v341; // r8
  int v342; // r15d
  int v343; // edx
  int v344; // edx
  __int64 v345; // rdi
  int v346; // r12d
  unsigned int v347; // r15d
  __int64 v348; // rax
  const char *v349; // rcx
  __int64 v350; // rdx
  _QWORD *v351; // rdi
  _QWORD *v352; // rcx
  int v353; // eax
  void (*v354)(void); // rax
  const char *i1; // rcx
  unsigned int v356; // edx
  int v357; // esi
  unsigned int v358; // r13d
  __int64 v359; // r14
  int v360; // edx
  __int64 v361; // rcx
  __int64 v362; // rax
  __int64 v363; // rax
  __int64 v364; // rsi
  __int64 v365; // rcx
  __int64 v366; // rcx
  __int64 v367; // rax
  __int64 v368; // rcx
  __int64 v369; // rax
  __int64 v370; // rax
  __int64 v371; // rdx
  __int64 v372; // rdi
  __int64 v373; // rcx
  __int64 v374; // rax
  __int64 v375; // rax
  __int64 v376; // rdx
  int v377; // eax
  __int64 v378; // rcx
  unsigned int v379; // edx
  __int64 v380; // rcx
  __int64 v381; // rax
  __int64 *v382; // rax
  __int64 *v383; // rax
  __int64 v384; // rcx
  int v385; // edx
  __int64 v386; // rcx
  __int64 v387; // rax
  __int64 v388; // rcx
  __int64 v389; // rax
  __int64 v390; // rdx
  __int64 v391; // rdi
  __int64 v392; // rcx
  __int64 v393; // rax
  __int64 v394; // rcx
  __int64 v395; // rax
  __int64 v396; // rdx
  char v397; // al
  __int64 v398; // rcx
  int v399; // edx
  __int64 v400; // rcx
  __int64 v401; // rax
  __int64 v402; // rax
  __int64 v403; // rax
  __int64 v404; // rdx
  __int64 v405; // rcx
  __int64 v406; // rax
  __int64 v407; // rax
  __int64 v408; // rcx
  int v409; // edi
  __int64 v410; // rcx
  __int64 v411; // rax
  __int64 v412; // rax
  int v413; // eax
  __int64 v414; // rdx
  __int64 v415; // rax
  int v416; // eax
  __int64 v417; // rcx
  int v418; // esi
  __int64 v419; // rcx
  int v420; // r13d
  int v421; // eax
  const char *v422; // rdx
  _QWORD *v423; // rdi
  __int64 v424; // r14
  _DWORD *v425; // rcx
  unsigned int v426; // esi
  unsigned int v427; // r15d
  int v428; // edi
  _DWORD *v429; // r15
  __int64 v430; // rcx
  int v431; // esi
  __int64 v432; // rax
  __int64 v433; // rdx
  __int64 v434; // rdi
  __int64 v435; // rcx
  __int64 v436; // rax
  __int64 v437; // rax
  __int64 v438; // rdx
  __int64 v439; // rcx
  int v440; // r15d
  char v441; // si
  __int64 v442; // r14
  __int64 v443; // rcx
  int v444; // r12d
  int v445; // esi
  _DWORD *v446; // r10
  int v447; // edi
  int IndexKey; // eax
  __int64 v449; // rcx
  unsigned int v450; // edx
  __int64 v451; // rcx
  __int64 v452; // rax
  int v453; // edx
  int v454; // r8d
  __int64 v455; // rsi
  __int64 v456; // rcx
  __int64 v457; // rax
  __int64 v458; // rcx
  __int64 v459; // rcx
  __int64 v460; // rax
  __int64 v461; // rcx
  __int64 v462; // rcx
  __int64 v463; // rax
  unsigned int String; // eax
  __int64 v465; // rcx
  unsigned int v466; // r15d
  __int64 v467; // rcx
  __int64 v468; // rax
  int v469; // eax
  __int64 v470; // rcx
  int v471; // edx
  __int64 *v472; // rcx
  __int64 v473; // rax
  unsigned int v474; // edx
  __int64 v475; // rcx
  __int64 v476; // rcx
  __int64 v477; // rax
  __int64 v478; // rdi
  int v479; // edx
  __int64 v480; // rcx
  __int64 v481; // rax
  __int64 v482; // rcx
  __int64 v483; // rcx
  __int64 v484; // rax
  __int64 v485; // rcx
  unsigned int v486; // edx
  __int64 v487; // rcx
  __int64 v488; // rax
  __int64 *v489; // rax
  unsigned int v490; // esi
  int v491; // edi
  int v492; // r15d
  __int64 v493; // rcx
  unsigned int v494; // edx
  __int64 v495; // rcx
  __int64 v496; // rax
  __int64 v497; // rcx
  __int64 v498; // rcx
  __int64 v499; // rax
  __int64 v500; // rdi
  __int64 v501; // rcx
  __int64 v502; // rax
  __int64 v503; // rcx
  int v504; // esi
  __int64 v505; // rcx
  __int64 v506; // rcx
  __int64 v507; // rax
  __int64 v508; // rcx
  unsigned int v509; // edx
  __int64 v510; // rcx
  __int64 v511; // rax
  __int64 *v512; // rax
  int v513; // edi
  unsigned int v514; // esi
  __int64 v515; // r15
  __int64 v516; // rdx
  __int64 v517; // rcx
  unsigned int v518; // edx
  __int64 v519; // rcx
  __int64 v520; // rax
  unsigned int v521; // edx
  __int64 v522; // rdi
  __int64 v523; // rcx
  __int64 v524; // rax
  __int64 v525; // rcx
  __int64 v526; // rcx
  __int64 v527; // rax
  __int64 *v528; // rax
  int v529; // r8d
  __int64 v530; // rcx
  int v531; // edx
  __int64 v532; // rcx
  __int64 v533; // rax
  __int64 v534; // rcx
  __int64 v535; // rcx
  __int64 v536; // rax
  __int64 v537; // rcx
  int v538; // esi
  __int64 *v539; // rax
  int v540; // r8d
  __int64 v541; // r9
  __int64 v542; // r8
  __int64 v543; // rcx
  __int64 v544; // rcx
  int v545; // edi
  unsigned int v546; // edx
  __int64 v547; // rcx
  __int64 v548; // rax
  __int64 *v549; // rax
  int v550; // r14d
  const char *v551; // rsi
  const char *v552; // rax
  __int64 v553; // rcx
  unsigned int v554; // edx
  __int64 v555; // rcx
  __int64 v556; // rax
  __int64 v557; // rdi
  unsigned int v558; // edx
  __int64 v559; // rcx
  __int64 v560; // rax
  __int64 v561; // rax
  __int64 v562; // rcx
  __int64 v563; // rcx
  __int64 v564; // rax
  __int64 *v565; // rax
  int v566; // eax
  __int64 v567; // rax
  __int64 v568; // rax
  const char *v569; // r8
  char **v570; // rdi
  char *i; // r9
  __int64 v572; // rdx
  __int64 v573; // rax
  char v574; // dl
  int v575; // esi
  __int64 v576; // rcx
  __int64 v577; // r11
  __int64 v578; // rbx
  _DWORD *v579; // rax
  char *v580; // r8
  __int64 v581; // r11
  int v582; // eax
  __int64 v583; // r11
  int v584; // edi
  int v585; // ebx
  __int64 v586; // rax
  char v587; // r15
  _DWORD *v588; // rsi
  int v589; // edx
  int v590; // r13d
  int v591; // eax
  int v592; // r12d
  _DWORD *v593; // rcx
  int v594; // eax
  _QWORD *v595; // r14
  __int64 v596; // rdi
  __int64 v597; // rax
  __int16 v598; // si
  __int64 v599; // rdi
  char v600; // al
  unsigned int v601; // esi
  unsigned __int8 v602; // al
  int v603; // eax
  __int64 v604; // rdx
  int v605; // eax
  __int64 v606; // rdx
  __int64 v607; // rax
  char *v608; // rcx
  __int64 v609; // rax
  int v610; // eax
  int v611; // edi
  __int64 v612; // [rsp+20h] [rbp-E0h]
  int v613; // [rsp+20h] [rbp-E0h]
  int v614; // [rsp+20h] [rbp-E0h]
  __int64 v615; // [rsp+20h] [rbp-E0h]
  _QWORD *v616; // [rsp+60h] [rbp-A0h]
  char *v617; // [rsp+68h] [rbp-98h]
  unsigned int v618; // [rsp+70h] [rbp-90h]
  int v619; // [rsp+70h] [rbp-90h]
  int v620; // [rsp+74h] [rbp-8Ch] BYREF
  int v621; // [rsp+78h] [rbp-88h] BYREF
  char v622; // [rsp+7Ch] [rbp-84h]
  _DWORD *v623; // [rsp+80h] [rbp-80h]
  int v624; // [rsp+88h] [rbp-78h]
  _BYTE *v625; // [rsp+90h] [rbp-70h] BYREF
  __int64 v626; // [rsp+98h] [rbp-68h] BYREF
  char *v627; // [rsp+A0h] [rbp-60h]
  __int64 v628; // [rsp+A8h] [rbp-58h] BYREF
  int v629; // [rsp+B0h] [rbp-50h] BYREF
  int v630; // [rsp+B4h] [rbp-4Ch]
  __int64 v631; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v632; // [rsp+C0h] [rbp-40h] BYREF
  int v633; // [rsp+C4h] [rbp-3Ch]
  int v634; // [rsp+C8h] [rbp-38h]
  int v635; // [rsp+CCh] [rbp-34h]
  __int64 v636; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v637; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v638; // [rsp+E0h] [rbp-20h] BYREF
  char *v639; // [rsp+E8h] [rbp-18h]
  _QWORD *v640; // [rsp+F0h] [rbp-10h]
  const char *v641; // [rsp+F8h] [rbp-8h]
  const char *v642; // [rsp+100h] [rbp+0h]
  const char *v643; // [rsp+108h] [rbp+8h]
  char *Str[4]; // [rsp+110h] [rbp+10h] BYREF

  v5 = (char *)a1[2];
  v7 = *a1;
  v623 = a1;
  v616 = (_QWORD *)v7;
  v627 = v5;
  if ( !v5 )
  {
    if ( !a1[21] && (*(_BYTE *)(v7 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    result = sqlite3VdbeCreate(a1);
    v627 = (char *)result;
    v5 = (char *)result;
    if ( !result )
      return result;
  }
  v12 = *((int *)v5 + 36);
  v631 = 0;
  if ( *((_DWORD *)v5 + 37) > (int)v12 )
  {
    *((_DWORD *)v5 + 36) = v12 + 1;
    v13 = 3 * v12;
    v14 = *((_QWORD *)v5 + 17);
    *(_DWORD *)(v14 + 8 * v13) = 166;
    *(_DWORD *)(v14 + 8 * v13 + 4) = 1;
    *(_QWORD *)(v14 + 8 * v13 + 8) = 1;
    *(_QWORD *)(v14 + 8 * v13 + 16) = 0;
  }
  else
  {
    growOp3(v5, 166, 1, 1, 0);
  }
  v15 = *a1;
  *((_DWORD *)a1 + 14) = 2;
  if ( *(_DWORD *)(a3 + 8) )
  {
    if ( *(_BYTE *)(v15 + 197) )
      return sqlite3ErrorMsg(a1, "corrupt database");
    Db = sqlite3FindDb(v15);
    v618 = Db;
    if ( Db < 0 )
      return sqlite3ErrorMsg(a1, "unknown database %T", a2);
    a2 = a3;
  }
  else
  {
    Db = *(unsigned __int8 *)(v15 + 196);
    v618 = Db;
  }
  v17 = *(_QWORD *)(v7 + 32);
  if ( Db == 1 )
  {
    result = sqlite3OpenTempDatabase(a1);
    if ( (_DWORD)result )
      return result;
  }
  result = sqlite3NameFromToken(v616, a2);
  v639 = (char *)result;
  if ( !result )
    return result;
  v18 = 32LL * (int)v618 + v17;
  if ( a5 )
    v19 = sqlite3MPrintf(v616, "-%T", a4);
  else
    v19 = sqlite3NameFromToken(v616, a4);
  v20 = (char *)v19;
  v617 = (char *)v19;
  if ( *(_DWORD *)(a3 + 8) )
    v21 = *(_BYTE **)v18;
  else
    v21 = 0;
  v22 = v623;
  v625 = v21;
  if ( (unsigned int)sqlite3AuthCheck((_DWORD)v623, 19, (_DWORD)v639, v19, (__int64)v21) )
    goto LABEL_1150;
  Str[1] = v639;
  v23 = v616;
  Str[2] = v20;
  v24 = 1;
  Str[0] = 0;
  Str[3] = 0;
  v25 = v616[3];
  *((_DWORD *)v616 + 166) = 0;
  if ( v25 )
  {
    ((void (*)(void))xmmword_18013C230)();
    v23 = v616;
  }
  v26 = 12;
  if ( v21 )
  {
    DbName = sqlite3FindDbName(v23, v21);
    if ( DbName < 0 )
    {
LABEL_43:
      v31 = v616;
      goto LABEL_44;
    }
  }
  else
  {
    DbName = 0;
  }
  _mm_lfence();
  v28 = *(_QWORD *)(32LL * (unsigned int)DbName + v616[4] + 8);
  if ( !v28 )
  {
LABEL_42:
    v22 = v623;
    goto LABEL_43;
  }
  if ( *(_BYTE *)(v28 + 17) )
  {
    ++*(_DWORD *)(v28 + 20);
    if ( !*(_BYTE *)(v28 + 18) )
      btreeLockCarefully(v28);
  }
  v29 = *(_QWORD *)(**(_QWORD **)(v28 + 8) + 72LL);
  v30 = *((_DWORD *)v616 + 166);
  if ( *(_QWORD *)v29 )
    v24 = (*(__int64 (__fastcall **)(__int64, __int64, char **))(*(_QWORD *)v29 + 80LL))(v29, 14, Str);
  else
    v24 = 12;
  v31 = v616;
  *((_DWORD *)v616 + 166) = v30;
  if ( *(_BYTE *)(v28 + 17) )
  {
    v32 = (*(_DWORD *)(v28 + 20))-- == 1;
    if ( v32 )
    {
      unlockBtreeMutex(v28);
      v21 = v625;
      goto LABEL_42;
    }
  }
  v21 = v625;
  v22 = v623;
LABEL_44:
  if ( v31[3] )
    ((void (*)(void))xmmword_18013C240)();
  if ( !v24 )
  {
    sqlite3VdbeSetNumCols(v5, 1);
    if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
    {
      v34 = Str[0];
      v35 = *((_QWORD *)v5 + 19);
      if ( !Str[0] )
      {
        if ( (*(_WORD *)(v35 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(*((_QWORD *)v5 + 19), v33);
        else
          *(_WORD *)(v35 + 20) = 1;
        goto LABEL_70;
      }
      v36 = *(_QWORD *)(v35 + 24);
      if ( v36 )
        v37 = *(_DWORD *)(v36 + 136);
      else
        v37 = 1000000000;
      v38 = strlen_0(Str[0]);
      v40 = v38;
      if ( v38 > v37 )
      {
        if ( (*(_WORD *)(v35 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v35, v39);
        else
          *(_WORD *)(v35 + 20) = 1;
        v41 = *(_QWORD *)(v35 + 24);
        if ( v41 )
        {
          v42 = *(_QWORD *)(v41 + 352);
          if ( v42 )
          {
            ++*(_DWORD *)(v42 + 48);
            *(_DWORD *)(v42 + 24) = 18;
          }
        }
        goto LABEL_70;
      }
      v43 = v38 + 1;
      v44 = 32;
      if ( v38 + 1 > 32 )
        v44 = (unsigned int)v43;
      if ( *(_DWORD *)(v35 + 32) >= (int)v44 )
      {
        v45 = *(_QWORD *)(v35 + 40);
        *(_WORD *)(v35 + 20) &= 0x2Du;
        *(_QWORD *)(v35 + 8) = v45;
LABEL_69:
        memcpy_0(*(void **)(v35 + 8), v34, v43);
        *(_WORD *)(v35 + 20) = 514;
        *(_BYTE *)(v35 + 22) = 1;
        *(_DWORD *)(v35 + 16) = v40 & 0x7FFFFFFF;
        goto LABEL_70;
      }
      if ( !(unsigned int)sqlite3VdbeMemGrow(v35, v44, 0) )
        goto LABEL_69;
    }
LABEL_70:
    if ( Str[0] )
    {
      sqlite3VdbeLoadString(v5, 1, Str[0]);
      v46 = *((int *)v5 + 36);
      if ( *((_DWORD *)v5 + 37) > (int)v46 )
      {
        *((_DWORD *)v5 + 36) = v46 + 1;
        v47 = 3 * v46;
        v48 = *((_QWORD *)v5 + 17);
        *(_DWORD *)(v48 + 8 * v47) = 84;
        *(_DWORD *)(v48 + 8 * v47 + 4) = 1;
        *(_QWORD *)(v48 + 8 * v47 + 8) = 1;
        *(_QWORD *)(v48 + 8 * v47 + 16) = 0;
      }
      else
      {
        LODWORD(v612) = 0;
        growOp3(v5, 84, 1, 1, v612);
      }
    }
    v49 = Str[0];
    if ( Str[0] )
    {
      if ( dword_18013C1B0 )
      {
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C230)();
        v50 = ((__int64 (__fastcall *)(char *))xmmword_18013C1E8)(v49);
        --qword_18013FBE8;
        qword_18013FBA0 -= v50;
        ((void (__fastcall *)(char *))xmmword_18013C1D8)(v49);
        if ( (_QWORD)xmmword_18013FC60 )
          ((void (*)(void))xmmword_18013C240)();
      }
      else
      {
        ((void (__fastcall *)(char *))xmmword_18013C1D8)(Str[0]);
      }
    }
    goto LABEL_1150;
  }
  if ( v24 != 12 )
  {
    if ( Str[0] )
    {
      sqlite3ErrorMsg(v22, "%s", Str[0]);
      v51 = Str[0];
      if ( Str[0] )
      {
        if ( dword_18013C1B0 )
        {
          if ( (_QWORD)xmmword_18013FC60 )
            ((void (*)(void))xmmword_18013C230)();
          v52 = ((__int64 (__fastcall *)(char *))xmmword_18013C1E8)(v51);
          --qword_18013FBE8;
          qword_18013FBA0 -= v52;
          ((void (__fastcall *)(char *))xmmword_18013C1D8)(v51);
          if ( (_QWORD)xmmword_18013FC60 )
          {
            ((void (*)(void))xmmword_18013C240)();
            ++v22[12];
            v22[6] = v24;
            goto LABEL_1150;
          }
        }
        else
        {
          ((void (__fastcall *)(char *))xmmword_18013C1D8)(Str[0]);
        }
      }
    }
    ++v22[12];
    v22[6] = v24;
    goto LABEL_1150;
  }
  v53 = pragmaLocate(v639);
  v638 = v53;
  v55 = v53;
  if ( !v53 )
    goto LABEL_1150;
  v56 = v623;
  if ( (*(_BYTE *)(v53 + 9) & 1) != 0 )
  {
    if ( (unsigned int)sqlite3ReadSchema(v623) )
      goto LABEL_1150;
  }
  v57 = *(_BYTE *)(v55 + 9);
  if ( (v57 & 2) == 0 )
  {
    if ( (v57 & 4) != 0 )
    {
      v58 = v617;
      if ( v617 )
        goto LABEL_99;
    }
    setPragmaResultColumnNames(v5, v55);
  }
  v58 = v617;
LABEL_99:
  switch ( *(_BYTE *)(v55 + 8) )
  {
    case 1:
      if ( !v58 || (unsigned int)sqlite3DecOrHexToI64(v58, &v637) )
      {
        v66 = v616;
      }
      else
      {
        v66 = v616;
        if ( v637 >= 0 )
          *((_DWORD *)v616 + 186) = v637 & 0x7FFFFFFF;
      }
      returnSingleInt(v5, *((int *)v66 + 186));
      goto LABEL_1151;
    case 2:
      v575 = *(_DWORD *)(v55 + 16);
      sqlite3VdbeUsesBtree(v5, v618);
      if ( v577 && (*(_BYTE *)(v55 + 9) & 8) == 0 )
      {
        v123 = v617;
        v621 = 0;
        v578 = sqlite3VdbeAddOpList(v576, 2, &qword_18010F400, 0);
        *(_DWORD *)(v578 + 4) = v618;
        *(_DWORD *)(v578 + 28) = v618;
        *(_DWORD *)(v578 + 32) = v575;
        sqlite3GetInt32(v617, &v621);
        v66 = v616;
        *(_DWORD *)(v578 + 36) = v621;
        *(_WORD *)(v578 + 26) = 1;
        if ( v575 == 1 && (v616[6] & 0x10000000) != 0 )
          *(_BYTE *)(v578 + 24) = -72;
        goto LABEL_1152;
      }
      v579 = (_DWORD *)sqlite3VdbeAddOpList(v576, 3, qword_18010F408, 0);
      v579[1] = v618;
      v579[7] = v618;
      v579[9] = v575;
LABEL_1057:
      sqlite3VdbeReusable(v5);
      goto LABEL_1150;
    case 3:
      v100 = *(_QWORD *)(v18 + 8);
      if ( !v58 )
      {
        AutoVacuum = (int)sqlite3BtreeGetAutoVacuum(*(_QWORD *)(v18 + 8));
        goto LABEL_1149;
      }
      v101 = v58;
      v102 = "none";
      while ( 2 )
      {
        v103 = (unsigned __int8)*v101;
        v104 = *(unsigned __int8 *)v102;
        if ( (_DWORD)v103 == (_DWORD)v104 )
        {
          if ( !*v101 )
          {
            v105 = 0;
            goto LABEL_222;
          }
LABEL_206:
          ++v101;
          ++v102;
          continue;
        }
        break;
      }
      if ( *((unsigned __int8 *)qword_180114680 + v103) == *((unsigned __int8 *)qword_180114680 + v104) )
        goto LABEL_206;
      v106 = v58;
      v107 = "full";
      while ( 2 )
      {
        v108 = (unsigned __int8)*v106;
        v109 = *(unsigned __int8 *)v107;
        if ( (_DWORD)v108 == (_DWORD)v109 )
        {
          if ( !*v106 )
          {
            v105 = 1;
            goto LABEL_222;
          }
          goto LABEL_212;
        }
        if ( *((unsigned __int8 *)qword_180114680 + v108) == *((unsigned __int8 *)qword_180114680 + v109) )
        {
LABEL_212:
          ++v106;
          ++v107;
          continue;
        }
        break;
      }
      v110 = v58;
      v111 = "incremental";
      while ( 2 )
      {
        v112 = (unsigned __int8)*v110;
        v113 = *(unsigned __int8 *)v111;
        if ( (_DWORD)v112 == (_DWORD)v113 )
        {
          if ( !*v110 )
          {
            v105 = 2;
            goto LABEL_222;
          }
          goto LABEL_218;
        }
        if ( *((unsigned __int8 *)qword_180114680 + v112) == *((unsigned __int8 *)qword_180114680 + v113) )
        {
LABEL_218:
          ++v110;
          ++v111;
          continue;
        }
        break;
      }
      v620 = 0;
      sqlite3GetInt32(v58, &v620);
      v114 = v620;
      if ( (unsigned int)v620 > 2 )
        v114 = 0;
      v105 = v114;
LABEL_222:
      v66 = v616;
      *((_BYTE *)v616 + 106) = v105;
      if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v100, v105) && v105 - 1 <= 1 )
      {
        v115 = *((_DWORD *)v5 + 36);
        v116 = (_DWORD *)sqlite3VdbeAddOpList(v5, 5, qword_18010F338, 0);
        v116[14] = v115 + 4;
        v116[27] = v105 - 1;
        v116[1] = v618;
        v116[7] = v618;
        v116[25] = v618;
        sqlite3VdbeUsesBtree(v5, v618);
      }
LABEL_1151:
      v123 = v617;
LABEL_1152:
      v608 = v639;
      if ( (unsigned __int64)v639 >= v66[62] )
        goto LABEL_1199;
      if ( (unsigned __int64)v639 >= v66[60] )
      {
        result = v66[59];
        *(_QWORD *)v639 = result;
        v66[59] = v608;
        goto LABEL_1188;
      }
      if ( (unsigned __int64)v639 < v66[61] )
      {
LABEL_1199:
        if ( v66[97] )
          result = measureAllocationSize(v66, v639);
        else
          result = sqlite3_free(v639);
      }
      else
      {
        result = v66[57];
        *(_QWORD *)v639 = result;
        v66[57] = v608;
      }
LABEL_1188:
      if ( v123 )
      {
        if ( (unsigned __int64)v123 >= v66[62] )
          goto LABEL_1200;
        if ( (unsigned __int64)v123 >= v66[60] )
        {
          result = v66[59];
          *v123 = result;
          v66[59] = v123;
          return result;
        }
        if ( (unsigned __int64)v123 < v66[61] )
        {
LABEL_1200:
          if ( v66[97] )
            return measureAllocationSize(v66, v123);
          else
            return sqlite3_free(v123);
        }
        else
        {
          result = v66[57];
          *v123 = result;
          v66[57] = v123;
        }
      }
      return result;
    case 4:
      if ( !v58 )
      {
        setPragmaResultColumnNames(v5, v55);
        v66 = v616;
        returnSingleInt(v5, (v616[6] & *(_QWORD *)(v55 + 16)) != 0);
        goto LABEL_1151;
      }
      v156 = *(_QWORD *)(v55 + 16);
      v66 = v616;
      v157 = v156 & 0xFFFFFFFFFFFFBFFFuLL;
      if ( *((_BYTE *)v616 + 101) )
        v157 = v156;
      SafetyLevel = getSafetyLevel(v58, 1, 0);
      v159 = v616[6];
      if ( SafetyLevel )
      {
        v616[6] = v157 | v159;
      }
      else
      {
        v616[6] = v159 & ~v157;
        if ( v157 == 0x80000 )
        {
          v616[96] = 0;
        }
        else if ( (v157 & 1) != 0 )
        {
          v123 = v617;
          if ( !(unsigned int)sqlite3StrICmp(v617, "reset") )
            sqlite3ResetAllSchemasOfConnection(v616);
LABEL_343:
          sqlite3VdbeAddOp0(v5, 166);
          setAllPagerFlags(v616);
          goto LABEL_1152;
        }
      }
      v123 = v617;
      goto LABEL_343;
    case 6:
      if ( !v58 )
      {
        AutoVacuum = *(int *)(*(_QWORD *)(v18 + 24) + 116LL);
        goto LABEL_1149;
      }
      v620 = 0;
      sqlite3GetInt32(v58, &v620);
      *(_DWORD *)(*(_QWORD *)(v18 + 24) + 116LL) = v620;
      goto LABEL_107;
    case 7:
      if ( !v58 )
      {
        v66 = v616;
        if ( (v616[6] & 0x20) != 0 )
        {
          v119 = sqlite3BtreeSetSpillSize(*(_QWORD *)(v18 + 8), 0);
          returnSingleInt(v5, v119);
        }
        else
        {
          returnSingleInt(v5, 0);
        }
        goto LABEL_1151;
      }
      v620 = 1;
      Int32 = sqlite3GetInt32(v58, &v620);
      v122 = v620;
      if ( Int32 )
        sqlite3BtreeSetSpillSize(*(_QWORD *)(v18 + 8), (unsigned int)v620);
      v123 = v617;
      LOBYTE(v121) = v122 != 0;
      v124 = getSafetyLevel(v617, 1, v121);
      v66 = v616;
      v125 = v616[6];
      v126 = v125 | 0x20;
      v127 = v125 & 0xFFFFFFFFFFFFFFDFuLL;
      if ( !v124 )
        v126 = v127;
      v616[6] = v126;
      setAllPagerFlags(v616);
      goto LABEL_1152;
    case 8:
      if ( !v58 )
        goto LABEL_1150;
      v272 = getSafetyLevel(v58, 1, 0);
      v66 = v616;
      sqlite3RegisterLikeFunctions(v616, v272 != 0);
      goto LABEL_1151;
    case 9:
      v66 = v616;
      v623[14] = 2;
      v212 = (__int64 **)v616[79];
      if ( !v212 )
        goto LABEL_1151;
      v213 = 0;
      do
      {
        sqlite3VdbeMultiLoad(v5, 1, "is", v213, *v212[2]);
        v212 = (__int64 **)*v212;
        ++v213;
      }
      while ( v212 );
      goto LABEL_1150;
    case 0xA:
      v623[14] = 1;
      while ( (unsigned int)v631 <= 0x25 )
      {
        v580 = off_180114550[(int)v631];
        if ( !v580 )
          break;
        v631 = (unsigned int)(v631 + 1);
        sqlite3VdbeLoadString(v5, 1, v580);
        sqlite3VdbeAddOp2(v5, 84, 1, 1);
      }
      goto LABEL_1057;
    case 0xB:
      if ( (_BYTE)word_18013C1B4 )
      {
        v153 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
        if ( v153 )
          ((void (__fastcall *)(__int64))xmmword_18013C230)(v153);
      }
      v123 = v617;
      if ( v617 )
      {
        if ( *v617 )
        {
          v66 = v616;
          if ( (*(unsigned int (__fastcall **)(_QWORD, char *, __int64, int *))(*v616 + 56LL))(*v616, v617, 1, &v621)
            || !v621 )
          {
            goto LABEL_304;
          }
        }
        sqlite3_free(sqlite3_data_directory);
        if ( *v617 )
          sqlite3_data_directory = sqlite3_mprintf("%s", v617);
        else
          sqlite3_data_directory = 0;
      }
      else
      {
        returnSingleText(v5, sqlite3_data_directory);
      }
      if ( (_BYTE)word_18013C1B4 )
      {
        v154 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
        if ( v154 )
          ((void (__fastcall *)(__int64))xmmword_18013C240)(v154);
      }
      v66 = v616;
      goto LABEL_1152;
    case 0xC:
      v66 = v616;
      v623[14] = 3;
      if ( *((int *)v616 + 10) > 0 )
      {
        v210 = 0;
        do
        {
          v211 = (_QWORD *)(v616[4] + 32LL * (int)v210);
          if ( v211[1] )
            sqlite3VdbeMultiLoad(v5, 1, "iss", v210, *v211);
          ++v210;
        }
        while ( (signed int)v210 < *((_DWORD *)v616 + 10) );
      }
      goto LABEL_1151;
    case 0xD:
      sqlite3VdbeUsesBtree(v5, v618);
      if ( v60 )
      {
        v620 = 0;
        sqlite3GetInt32(v60, &v620);
        v62 = v620;
        if ( v620 < 0 )
        {
          if ( v620 == 0x80000000 )
            v62 = 0x7FFFFFFF;
          else
            v62 = -v620;
        }
        sqlite3BeginWriteOperation(v56, 0, v618);
        sqlite3VdbeAddOp3((_DWORD)v5, 100, v618, 3, v62);
        *(_DWORD *)(*(_QWORD *)(v18 + 24) + 116LL) = v62;
LABEL_107:
        sqlite3BtreeSetCacheSize(*(_QWORD *)(v18 + 8), *(unsigned int *)(*(_QWORD *)(v18 + 24) + 116LL));
      }
      else
      {
        v623[14] += 2;
        v61 = (_DWORD *)sqlite3VdbeAddOpList(v59, 9, qword_18010F2E8, 0);
        v61[1] = v618;
        v61[7] = v618;
        v61[37] = -2000;
      }
      goto LABEL_1150;
    case 0xE:
      if ( v58 )
      {
        v66 = v616;
        if ( (*((_BYTE *)v616 + 44) & 0x40) != 0 )
          goto LABEL_1151;
        v569 = "UTF8";
        v570 = &off_18010F370;
        if ( !"UTF8" )
        {
LABEL_1045:
          if ( *v570 )
            goto LABEL_1151;
          goto LABEL_1046;
        }
LABEL_1039:
        for ( i = v58; ; ++i )
        {
          v572 = (unsigned __int8)*i;
          v573 = *(unsigned __int8 *)v569;
          if ( (_DWORD)v572 == (_DWORD)v573 )
          {
            if ( !*i )
            {
              v574 = 2;
              if ( *((_BYTE *)v570 + 8) )
                v574 = *((_BYTE *)v570 + 8);
              *(_BYTE *)(*(_QWORD *)(v616[4] + 24LL) + 113LL) = v574;
              sqlite3SetTextEncoding(v616);
              v58 = v617;
              goto LABEL_1045;
            }
          }
          else if ( *((unsigned __int8 *)qword_180114680 + v572) != *((unsigned __int8 *)qword_180114680 + v573) )
          {
            v569 = v570[2];
            v570 += 2;
            if ( !v569 )
            {
LABEL_1046:
              sqlite3ErrorMsg(v56, "unsupported encoding: %s", v58);
              goto LABEL_1151;
            }
            goto LABEL_1039;
          }
          ++v569;
        }
      }
      if ( !(unsigned int)sqlite3ReadSchema(v623) )
        returnSingleText(v5, (&off_18010F370)[2 * *(unsigned __int8 *)(*(_QWORD *)v623 + 100LL)]);
      goto LABEL_1150;
    case 0xF:
      _mm_lfence();
      v229 = v623[14];
      v230 = v616;
      v231 = v229 + 5;
      v623[14] = v229 + 5;
      v232 = v229 + 1;
      v233 = v616[4];
      v620 = v232;
      v629 = v231;
      v234 = *(const char ***)(*(_QWORD *)(32LL * (int)v618 + v233 + 24) + 16LL);
      if ( !v234 )
      {
        v66 = v616;
        goto LABEL_1151;
      }
      v235 = v625;
      while ( 2 )
      {
        if ( v58 )
        {
          Table = sqlite3LocateTable(v56, 0, v58, v235);
          v230 = v616;
          v237 = (const char *)Table;
          v627 = (char *)Table;
          v234 = 0;
        }
        else
        {
          v237 = v234[2];
          v234 = (const char **)*v234;
          v627 = (char *)v237;
        }
        v626 = (__int64)v234;
        if ( !v237 || v237[63] || !*((_QWORD *)v237 + 9) )
          goto LABEL_563;
        v238 = *((_QWORD *)v237 + 12);
        v239 = -32768;
        if ( v238 )
        {
          v240 = v230[4];
          v239 = 0;
          if ( *(_QWORD *)(v240 + 24) != v238 )
          {
            do
              ++v239;
            while ( *(_QWORD *)(32LL * v239 + v240 + 24) != v238 );
          }
        }
        v241 = v56;
        v242 = 32LL * v239;
        v625 = *(_BYTE **)(v242 + v230[4]);
        if ( *((_QWORD *)v56 + 21) )
          v241 = (_DWORD *)*((_QWORD *)v56 + 21);
        v243 = v241[31];
        if ( _bittest(&v243, v239) )
        {
          if ( v239 == 1 )
            goto LABEL_502;
        }
        else
        {
          v241[31] = v243 | (1 << v239);
          if ( v239 == 1 )
          {
            sqlite3OpenTempDatabase(v241);
            goto LABEL_502;
          }
        }
        if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v56 + 32LL) + v242 + 8) + 17LL) )
          lockTable((_DWORD)v56, v239, *((_DWORD *)v237 + 10), 0, *(_QWORD *)v237);
LABEL_502:
        v244 = v231 + *((__int16 *)v237 + 27);
        if ( v56[14] < v244 )
          v56[14] = v244;
        sqlite3OpenTable((_DWORD)v56, 0, v239, (_DWORD)v237, 112);
        sqlite3VdbeLoadString(v5, v232, *(_QWORD *)v237);
        v245 = *((_QWORD *)v237 + 9);
        v246 = 1;
        if ( !v245 )
          goto LABEL_515;
        do
        {
          v247 = sqlite3FindTable((__int64)v616, *(unsigned __int8 **)(v245 + 16), v625);
          if ( v247 )
          {
            v248 = (int)v623;
            v628 = 0;
            if ( v239 != 1 && *(_BYTE *)(*(_QWORD *)(32LL * v239 + *(_QWORD *)(*(_QWORD *)v623 + 32LL) + 8) + 17LL) )
            {
              lockTable((_DWORD)v623, v239, *(_DWORD *)(v247 + 40), 0, *(_QWORD *)v247);
              v248 = (int)v623;
            }
            if ( (unsigned int)sqlite3FkLocateIndex(v248, v247, v245, (unsigned int)&v628, 0) )
              goto LABEL_1150;
            v249 = v628;
            if ( v628 )
            {
              sqlite3VdbeAddOp3((_DWORD)v5, 112, v246, *(_DWORD *)(v628 + 88), v239);
              sqlite3VdbeSetP4KeyInfo(v623, v249);
            }
            else
            {
              sqlite3OpenTable((_DWORD)v623, v246, v239, v247, 112);
            }
          }
          v245 = *(_QWORD *)(v245 + 8);
          ++v246;
        }
        while ( v245 );
        v237 = v627;
        v232 = v620;
LABEL_515:
        v250 = v623;
        if ( v623[13] < v246 )
          v623[13] = v246;
        v251 = sqlite3VdbeAddOp1(v5, 36, 0);
        v252 = *((_QWORD *)v237 + 9);
        v253 = v251;
        v621 = v251;
        v630 = 1;
        if ( !v252 )
        {
LABEL_559:
          sqlite3VdbeAddOp2(v5, 39, 0, (unsigned int)(v253 + 1));
          if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
            v271 = &qword_18013FEA8;
          else
            v271 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * v253);
          v235 = v625;
          v56 = v623;
          *((_DWORD *)v271 + 2) = *((_DWORD *)v5 + 36);
          v234 = (const char **)v626;
LABEL_563:
          v230 = v616;
          v58 = v617;
          if ( !v234 )
          {
            v66 = v616;
            v123 = v617;
            goto LABEL_1152;
          }
          continue;
        }
        break;
      }
      v254 = (__int64)v616;
      while ( 1 )
      {
        v255 = sqlite3FindTable(v254, *(unsigned __int8 **)(v252 + 16), v625);
        v640 = (_QWORD *)v255;
        v628 = 0;
        v256 = 0;
        v631 = 0;
        v257 = 0;
        if ( v255 )
        {
          sqlite3FkLocateIndex((_DWORD)v250, v255, v252, (unsigned int)&v628, (__int64)&v631);
          v256 = v628;
          v257 = (_QWORD *)v631;
        }
        v258 = v629;
        v259 = v250[17] - 1;
        v250[17] = v259;
        v260 = v258 + *(_DWORD *)(v252 + 40);
        if ( v250[14] < v260 )
          v250[14] = v260;
        v261 = 0;
        if ( *(int *)(v252 + 40) > 0 )
        {
          do
          {
            if ( v257 )
              v262 = *((_DWORD *)v257 + v261);
            else
              v262 = *(_DWORD *)(v252 + 16 * (v261 + 4LL));
            v263 = v261 + v258;
            sqlite3ExprCodeGetColumnOfTable((_DWORD)v5, (_DWORD)v627, 0, v262, v263);
            sqlite3VdbeAddOp2(v5, 50, v263, v259);
            v258 = v629;
            ++v261;
          }
          while ( v261 < *(_DWORD *)(v252 + 40) );
          v256 = v628;
        }
        if ( v256 )
        {
          v264 = *(_QWORD *)(v256 + 32);
          if ( !v264 )
            v264 = computeIndexAffStr(v616, v256);
          sqlite3VdbeAddOp4((_DWORD)v5, 96, v258, *(_DWORD *)(v252 + 40), 0, v264, *(_DWORD *)(v252 + 40));
          v613 = v258;
          v265 = v630;
          sqlite3VdbeAddOp4Int((_DWORD)v5, 29, v630, v259, v613, *(_DWORD *)(v252 + 40));
        }
        else if ( v640 )
        {
          v614 = v258;
          v265 = v630;
          sqlite3VdbeAddOp3((_DWORD)v5, 30, v630, *((_DWORD *)v5 + 36) + 2, v614);
          sqlite3VdbeGoto(v5, v259);
        }
        else
        {
          v265 = v630;
        }
        v266 = 135;
        v232 = v620;
        if ( v627[48] < 0 )
          v266 = 75;
        sqlite3VdbeAddOp2(v5, v266, 0, (unsigned int)(v620 + 1));
        sqlite3VdbeMultiLoad(v5, (unsigned int)(v620 + 2), "siX", *(_QWORD *)(v252 + 16), v265 - 1);
        sqlite3VdbeAddOp2(v5, 84, (unsigned int)v620, 4);
        v267 = *((_QWORD *)v5 + 3);
        v268 = ~v259;
        if ( *(_DWORD *)(v267 + 68) + *(_DWORD *)(v267 + 72) >= 0 )
          *(_DWORD *)(*(_QWORD *)(v267 + 80) + 4LL * v268) = *((_DWORD *)v5 + 36);
        else
          resizeResolveLabel(v267, v5, (unsigned int)v268);
        v254 = (__int64)v616;
        if ( !v257 )
          goto LABEL_557;
        if ( (unsigned __int64)v257 >= v616[62] )
          break;
        if ( (unsigned __int64)v257 < v616[60] )
        {
          if ( (unsigned __int64)v257 < v616[61] )
            break;
          *v257 = v616[57];
          v616[57] = v257;
        }
        else
        {
          *v257 = v616[59];
          v616[59] = v257;
        }
LABEL_557:
        v252 = *(_QWORD *)(v252 + 8);
        v250 = v623;
        v630 = v265 + 1;
        if ( !v252 )
        {
          v231 = v629;
          v253 = v621;
          goto LABEL_559;
        }
      }
      if ( v616[97] )
      {
        measureAllocationSize(v616, v257);
      }
      else
      {
        if ( dword_18013C1B0 )
        {
          if ( (_QWORD)xmmword_18013FC60 )
            ((void (*)(void))xmmword_18013C230)();
          v269 = ((__int64 (__fastcall *)(_QWORD *))xmmword_18013C1E8)(v257);
          --qword_18013FBE8;
          qword_18013FBA0 -= v269;
          ((void (__fastcall *)(_QWORD *))xmmword_18013C1D8)(v257);
          if ( !(_QWORD)xmmword_18013FC60 )
            goto LABEL_556;
          v270 = (void (*)(void))xmmword_18013C240;
        }
        else
        {
          v270 = (void (*)(void))xmmword_18013C1D8;
        }
        v270();
      }
LABEL_556:
      v254 = (__int64)v616;
      goto LABEL_557;
    case 0x10:
      v66 = v616;
      if ( !v58 )
        goto LABEL_1151;
      v220 = sqlite3FindTable((__int64)v616, (unsigned __int8 *)v58, v21);
      if ( !v220 )
        goto LABEL_1151;
      if ( *(_BYTE *)(v220 + 63) )
        goto LABEL_1151;
      v221 = *(_QWORD *)(v220 + 72);
      if ( !v221 )
        goto LABEL_1151;
      v222 = sqlite3SchemaToIndex(v616, *(_QWORD *)(v220 + 96));
      v223 = v623;
      v224 = 0;
      v623[14] = 8;
      sqlite3CodeVerifySchema(v223, v222);
      do
      {
        for ( j = 0; j < *(_DWORD *)(v221 + 40); ++j )
        {
          actionName(*(unsigned __int8 *)(v221 + 45), v225, j);
          actionName(*(unsigned __int8 *)(v221 + 46), v227, v228);
          sqlite3VdbeMultiLoad(v5, 1, "iissssss", v224, j);
        }
        v221 = *(_QWORD *)(v221 + 8);
        ++v224;
      }
      while ( v221 );
      goto LABEL_1150;
    case 0x11:
      v214 = (*((_DWORD *)v616 + 11) >> 5) & 1;
      v623[14] = 6;
      for ( k = 0; k != 23; ++k )
      {
        for ( m = qword_18013FAE0[k]; m; m = *(_QWORD *)(m + 64) )
          pragmaFunclistLine(v5, m, 1, v214);
      }
      v66 = v616;
      for ( n = (_QWORD *)v616[76]; n; n = (_QWORD *)*n )
        pragmaFunclistLine(v5, n[2], 0, v214);
      goto LABEL_1151;
    case 0x12:
      if ( v58 )
      {
        if ( !(unsigned int)sqlite3DecOrHexToI64(v58, &v637) )
        {
          v609 = sqlite3_hard_heap_limit64(-1);
          if ( v637 > 0 && (!v609 || v609 > v637) )
            sqlite3_hard_heap_limit64(v637);
        }
      }
      v607 = sqlite3_hard_heap_limit64(-1);
      goto LABEL_1148;
    case 0x13:
      v620 = 0;
      if ( !v58 || !(unsigned int)sqlite3GetInt32(v58, &v620) || (v117 = v620, v620 <= 0) )
        v117 = 0x7FFFFFFF;
      sqlite3BeginWriteOperation(v56, 0, v618);
      sqlite3VdbeAddOp2(v5, 71, v117, 1);
      v118 = sqlite3VdbeAddOp1(v5, 62, v618);
      sqlite3VdbeAddOp1(v5, 84, 1);
      sqlite3VdbeAddOp2(v5, 86, 1, 0xFFFFFFFFLL);
      sqlite3VdbeAddOp2(v5, 59, 1, v118);
      sqlite3VdbeJumpHere(v5, v118);
      goto LABEL_1150;
    case 0x14:
      v66 = v616;
      if ( !v58 )
        goto LABEL_1151;
      Index = (_QWORD *)sqlite3FindIndex(v616, v58, v21);
      if ( !Index )
      {
        v199 = sqlite3LocateTable(v623, 2, v617, v21);
        if ( !v199 )
          goto LABEL_1151;
        if ( *(char *)(v199 + 48) >= 0 )
          goto LABEL_1151;
        Index = (_QWORD *)sqlite3PrimaryKeyIndex(v199);
        if ( !Index )
          goto LABEL_1151;
      }
      v200 = sqlite3SchemaToIndex(v616, Index[6]);
      v201 = 96;
      if ( !*(_QWORD *)(v55 + 16) )
        v201 = 94;
      v202 = 6;
      v203 = *(unsigned __int16 *)((char *)Index + v201);
      if ( !*(_QWORD *)(v55 + 16) )
        v202 = 3;
      v623[14] = v202;
      sqlite3CodeVerifySchema(v56, v200);
      v204 = 0;
      if ( v203 )
      {
        do
        {
          sqlite3VdbeMultiLoad(v5, 1, "iisX", (unsigned int)v204, *(__int16 *)(Index[1] + 2 * v204));
          if ( *(_QWORD *)(v638 + 16) )
            sqlite3VdbeMultiLoad(v5, 4, "isiX", *(unsigned __int8 *)(Index[7] + v204), *(_QWORD *)(Index[8] + 8 * v204));
          sqlite3VdbeAddOp2(v5, 84, 1, (unsigned int)v623[14]);
          v204 = (unsigned int)(v204 + 1);
        }
        while ( (int)v204 < v203 );
      }
      goto LABEL_1150;
    case 0x15:
      v66 = v616;
      if ( !v58 )
        goto LABEL_1151;
      v205 = sqlite3FindTable((__int64)v616, (unsigned __int8 *)v58, v21);
      v206 = v205;
      if ( !v205 )
        goto LABEL_1151;
      v207 = sqlite3SchemaToIndex(v616, *(_QWORD *)(v205 + 96));
      v623[14] = 5;
      sqlite3CodeVerifySchema(v56, v207);
      v208 = *(_QWORD **)(v206 + 16);
      v209 = 0;
      if ( !v208 )
        goto LABEL_1151;
      do
      {
        v641 = "c";
        v642 = "u";
        v643 = "pk";
        sqlite3VdbeMultiLoad(v5, 1, "isisi", v209, *v208);
        v208 = (_QWORD *)v208[5];
        ++v209;
      }
      while ( v208 );
      goto LABEL_1150;
    case 0x16:
      v273 = v618;
      v32 = *(_QWORD *)a3 == 0;
      v274 = 100;
      v637 = (__int64)v5;
      v631 = 0;
      v275 = (unsigned __int8)*v639;
      v620 = 100;
      LODWORD(v625) = 100;
      v622 = *((_BYTE *)qword_180114680 + v275);
      if ( v32 )
        v273 = -1;
      v623[14] = 6;
      v619 = v273;
      if ( !v58 )
        goto LABEL_578;
      if ( (unsigned int)sqlite3GetInt32(v58, &v625) )
      {
        v274 = (int)v625;
        v620 = (int)v625;
        if ( (int)v625 > 0 )
          goto LABEL_578;
        v274 = 100;
      }
      else
      {
        if ( v273 < 0 )
          v276 = 0;
        else
          v276 = *(_QWORD *)(32LL * v273 + v616[4]);
        v277 = sqlite3LocateTable(v56, 0, v617, v276);
        v274 = (int)v625;
        v631 = v277;
      }
      v620 = v274;
LABEL_578:
      sqlite3VdbeAddOp2(v5, 71, (unsigned int)(v274 - 1), 1);
      v66 = v616;
      v278 = 0;
      v630 = 0;
      if ( *((int *)v616 + 10) <= 0 )
        goto LABEL_1031;
      v279 = v616;
      while ( 1 )
      {
        if ( v273 < 0 || v278 == v273 )
        {
          v280 = v56;
          v281 = 0;
          if ( *((_QWORD *)v56 + 21) )
            v280 = (_DWORD *)*((_QWORD *)v56 + 21);
          v282 = v280[31];
          if ( !_bittest(&v282, v278) )
          {
            v280[31] = v282 | (1 << v278);
            if ( v278 == 1 )
            {
              sqlite3OpenTempDatabase(v280);
              v278 = v630;
            }
          }
          v283 = 0;
          *((_BYTE *)v56 + 35) = 0;
          v284 = *(_QWORD *)(32LL * v278 + v616[4] + 24);
          v285 = *(_QWORD **)(v284 + 16);
          if ( !v285 )
            goto LABEL_1027;
          do
          {
            v286 = v285[2];
            if ( !v631 || v631 == v286 )
            {
              if ( *(char *)(v286 + 48) >= 0 )
                ++v283;
              v287 = *(_QWORD *)(v286 + 16);
              for ( ii = 0; v287; ++ii )
              {
                v287 = *(_QWORD *)(v287 + 40);
                ++v283;
              }
              if ( ii > v281 )
                v281 = ii;
            }
            v285 = (_QWORD *)*v285;
          }
          while ( v285 );
          if ( v283 )
          {
            v289 = v283 + 1;
            if ( !v631 )
              v289 = v283;
            v290 = (int *)sqlite3DbMallocRawNN(v616, 4LL * v289 + 4);
            v291 = v290;
            if ( !v290 )
            {
LABEL_1030:
              v66 = v616;
              v274 = v620;
LABEL_1031:
              v568 = sqlite3VdbeAddOpList(v5, 7, qword_18010F350, 0);
              if ( v568 )
              {
                *(_BYTE *)(v568 + 49) = -1;
                *(_QWORD *)(v568 + 64) = "ok";
                *(_DWORD *)(v568 + 8) = 1 - v274;
                *(_QWORD *)(v568 + 136) = "database disk image is malformed";
                *(_BYTE *)(v568 + 121) = -1;
              }
              sqlite3VdbeChangeP3(v5, 0, (unsigned int)(*((_DWORD *)v5 + 36) - 2));
              goto LABEL_1151;
            }
            v292 = v631;
            v293 = 0;
            if ( v631 )
            {
              v293 = 1;
              v290[1] = 0;
            }
            for ( jj = *(_QWORD **)(v284 + 16); jj; jj = (_QWORD *)*jj )
            {
              v295 = jj[2];
              if ( !v292 || v292 == v295 )
              {
                if ( *(char *)(v295 + 48) >= 0 )
                {
                  v296 = v293++;
                  v290[v296 + 1] = *(_DWORD *)(v295 + 40);
                }
                for ( kk = *(_QWORD *)(v295 + 16); kk; kk = *(_QWORD *)(kk + 40) )
                  v290[++v293] = *(_DWORD *)(kk + 88);
              }
            }
            *v290 = v293;
            if ( v56[14] < v281 + 8 )
              v56[14] = v281 + 8;
            *((_BYTE *)v56 + 31) = 0;
            v56[10] = 0;
            v298 = sqlite3VdbeAddOp3((_DWORD)v5, 155, 2, v293, 1);
            if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
            {
              sqlite3DbNNFreeNN(*(_QWORD *)v5, v291);
            }
            else
            {
              if ( v298 < 0 )
                v298 = *((_DWORD *)v5 + 36) - 1;
              v299 = *((_QWORD *)v5 + 17) + 24LL * v298;
              if ( *(_BYTE *)(v299 + 1) )
              {
                vdbeChangeP4Full(v5, v299, v291, 4294967282LL);
              }
              else
              {
                *(_QWORD *)(v299 + 16) = v291;
                *(_BYTE *)(v299 + 1) = -14;
              }
            }
            v300 = *((int *)v5 + 36);
            v301 = v630;
            if ( (int)v300 > 0 )
              *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v300 - 22) = (unsigned __int8)v630;
            v302 = (int)sqlite3VdbeAddOp1(v5, 50, 2);
            v303 = sqlite3MPrintf(v616, "*** in database %s ***\n", *(const char **)(32LL * v301 + v616[4]));
            v304 = sqlite3VdbeAddOp3((_DWORD)v5, 117, 0, 3, 0);
            if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
            {
              if ( v303 )
                sqlite3DbNNFreeNN(*(_QWORD *)v5, v303);
            }
            else
            {
              if ( v304 < 0 )
                v304 = *((_DWORD *)v5 + 36) - 1;
              v305 = *((_QWORD *)v5 + 17) + 24LL * v304;
              if ( *(_BYTE *)(v305 + 1) )
              {
                vdbeChangeP4Full(v5, v305, v303, 4294967290LL);
              }
              else if ( v303 )
              {
                *(_QWORD *)(v305 + 16) = v303;
                *(_BYTE *)(v305 + 1) = -6;
              }
            }
            sqlite3VdbeAddOp3((_DWORD)v5, 111, 2, 3, 3);
            integrityCheckResultRow(v5);
            if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
              v306 = &qword_18013FEA8;
            else
              v306 = (__int64 *)(*((_QWORD *)v5 + 17) + 24 * v302);
            *((_DWORD *)v306 + 2) = *((_DWORD *)v5 + 36);
            v307 = *(_QWORD **)(v284 + 16);
            v640 = v307;
            while ( v307 )
            {
              v308 = (const char **)v307[2];
              v626 = (__int64)v308;
              if ( *((_BYTE *)v308 + 63) || v631 && (const char **)v631 != v308 )
                goto LABEL_1025;
              if ( v622 == 113 || *((char *)v308 + 48) >= 0 )
              {
                v628 = 0;
                v633 = 0;
                goto LABEL_654;
              }
              v309 = (__int64)v308[2];
              v628 = v309;
              if ( v309 )
              {
                do
                {
                  if ( (*(_DWORD *)(v309 + 100) & 3) == 2 )
                    break;
                  v309 = *(_QWORD *)(v309 + 40);
                }
                while ( v309 );
                v628 = v309;
              }
              v310 = *(unsigned __int16 *)(v309 + 94);
              if ( v310 == 1 )
              {
                v311 = *((_BYTE *)v56 + 31);
                if ( !v311 )
                {
                  v312 = v56[14] + 1;
                  v633 = v312;
LABEL_651:
                  v56[14] = v312;
                  goto LABEL_652;
                }
                v313 = v311 - 1;
                *((_BYTE *)v56 + 31) = v313;
                v633 = v56[v313 + 56];
              }
              else
              {
                v314 = v56[10];
                if ( v310 > v314 )
                {
                  v316 = v56[14];
                  v317 = v316 + 1;
                  v312 = v310 + v316;
                  v633 = v317;
                  goto LABEL_651;
                }
                v633 = v56[11];
                v315 = v633;
                v56[10] = v314 - v310;
                v56[11] = v315 + v310;
              }
LABEL_652:
              sqlite3VdbeAddOp3((_DWORD)v5, 75, 1, v633, *(unsigned __int16 *)(v309 + 94) + v633 - 1);
LABEL_654:
              sqlite3OpenTableAndIndices((_DWORD)v56, (_DWORD)v308, 112, 0, 1, 0, (__int64)&v632, (__int64)&v629);
              sqlite3VdbeAddOp2(v5, 71, 0, 7);
              v318 = v308[2];
              if ( v318 )
              {
                v319 = 8;
                do
                {
                  sqlite3VdbeAddOp2(v5, 71, 0, v319);
                  v318 = (const char *)*((_QWORD *)v318 + 5);
                  ++v319;
                }
                while ( v318 );
              }
              v320 = v632;
              sqlite3VdbeAddOp2(v5, 36, v632, 0);
              v321 = sqlite3VdbeAddOp2(v5, 86, 7, 1);
              v32 = *((_BYTE *)v308 + 48) >= 0;
              v621 = v321;
              if ( v32 )
              {
                v322 = *((__int16 *)v308 + 27);
                v323 = -1;
                if ( v322 > 0 )
                {
                  for ( mm = 0; mm < v322; ++mm )
                  {
                    v325 = v323 + 1;
                    if ( (v308[1][24 * mm + 18] & 0x20) != 0 )
                      v325 = v323;
                    v323 = v325;
                  }
                }
                v326 = v323 - 1;
                if ( v323 != *((__int16 *)v308 + 26) )
                  v326 = v323;
              }
              else
              {
                for ( nn = v308[2]; nn; nn = (const char *)*((_QWORD *)nn + 5) )
                {
                  if ( (*((_DWORD *)nn + 25) & 3) == 2 )
                    break;
                }
                v326 = *((unsigned __int16 *)nn + 48) - 1;
              }
              if ( v326 >= 0 )
              {
                sqlite3VdbeAddOp3((_DWORD)v5, 94, v320, v326, 3);
                v328 = *(_BYTE *)(*(_QWORD *)v5 + 103LL)
                     ? &qword_18013FEA8
                     : (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (*((_DWORD *)v5 + 36) - 1));
                if ( *((_DWORD *)v328 + 3) == 3 && *(_BYTE *)v328 == 94 )
                  *((_WORD *)v328 + 1) |= 0x80u;
              }
              if ( v622 != 113 && v628 )
              {
                v329 = v633;
                v330 = (int)sqlite3VdbeAddOp4Int((_DWORD)v5, 41, v320, 0, v633, *(unsigned __int16 *)(v628 + 94));
                sqlite3VdbeAddOp1(v5, 50, v329);
                v331 = sqlite3MPrintf(v616, "row not in PRIMARY KEY order for %s", *v308);
                v332 = sqlite3VdbeAddOp3((_DWORD)v5, 117, 0, 3, 0);
                if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                {
                  if ( v331 )
                    sqlite3DbNNFreeNN(*(_QWORD *)v5, v331);
                }
                else
                {
                  if ( v332 < 0 )
                    v332 = *((_DWORD *)v5 + 36) - 1;
                  v333 = *((_QWORD *)v5 + 17) + 24LL * v332;
                  if ( *(_BYTE *)(v333 + 1) )
                  {
                    vdbeChangeP4Full(v5, v333, v331, 4294967290LL);
                  }
                  else if ( v331 )
                  {
                    *(_QWORD *)(v333 + 16) = v331;
                    *(_BYTE *)(v333 + 1) = -6;
                  }
                }
                integrityCheckResultRow(v5);
                if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  v334 = &qword_18013FEA8;
                else
                  v334 = (__int64 *)(*((_QWORD *)v5 + 17) + 24 * v330);
                *((_DWORD *)v334 + 2) = *((_DWORD *)v5 + 36);
                if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  v335 = &qword_18013FEA8;
                else
                  v335 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * ((int)v330 + 1));
                v336 = v628;
                v337 = 0;
                *((_DWORD *)v335 + 2) = *((_DWORD *)v5 + 36);
                if ( *(_WORD *)(v336 + 94) )
                {
                  v338 = v632;
                  v339 = v633;
                  do
                  {
                    v340 = *(_QWORD *)(v336 + 8);
                    v341 = (unsigned int)(v337 + v339);
                    if ( *(_WORD *)(v340 + 2LL * v337) == 0xFFFE )
                    {
                      v56[16] = v338 + 1;
                      sqlite3ExprCodeCopy(v56, *(_QWORD *)(32LL * v337 + *(_QWORD *)(v336 + 80) + 8), v341);
                      v56[16] = 0;
                    }
                    else
                    {
                      sqlite3ExprCodeGetColumnOfTable(
                        *((_QWORD *)v56 + 2),
                        *(_QWORD *)(v336 + 24),
                        v338,
                        *(__int16 *)(v340 + 2LL * v337),
                        v341);
                    }
                    ++v337;
                  }
                  while ( v337 < *(unsigned __int16 *)(v336 + 94) );
                  v5 = v627;
                  v308 = (const char **)v626;
                }
                v320 = v632;
              }
              v342 = 0;
              v343 = (_DWORD)v308[6] & 0x10000;
              v634 = 0;
              LODWORD(v625) = v343;
              if ( *((__int16 *)v308 + 27) > 0 )
              {
                while ( 1 )
                {
                  if ( v342 == *((__int16 *)v308 + 26) )
                    goto LABEL_854;
                  v32 = v343 == 0;
                  v344 = 0;
                  v345 = (__int64)&v308[1][24 * v342];
                  v627 = (char *)v345;
                  LOBYTE(v344) = v32 ? *(_BYTE *)(v345 + 12) > 65 : (*(_DWORD *)(v345 + 8) & 0xF0u) > 0x10;
                  v32 = (*(_BYTE *)(v345 + 8) & 0xF) == 0;
                  v635 = v344;
                  if ( !v32 || v344 )
                    break;
LABEL_853:
                  v343 = (int)v625;
LABEL_854:
                  v421 = *((__int16 *)v308 + 27);
                  v634 = ++v342;
                  if ( v342 >= v421 )
                  {
                    v627 = v5;
                    goto LABEL_856;
                  }
                  v320 = v632;
                }
                v32 = (*(_BYTE *)(v345 + 18) & 0x20) == 0;
                v624 = 5;
                if ( !v32 )
                {
                  sqlite3ExprCodeGetColumnOfTable((_DWORD)v5, (_DWORD)v308, v320, v342, 3);
                  v346 = -1;
                  v347 = 3;
                  goto LABEL_749;
                }
                v348 = *(unsigned __int16 *)(v345 + 16);
                if ( (_WORD)v348 )
                {
                  v32 = *((_BYTE *)v308 + 63) == 0;
                  v636 = 0;
                  if ( v32 )
                  {
                    v349 = v308[10];
                    if ( v349 )
                    {
                      if ( *(_DWORD *)v349 >= (int)v348 )
                      {
                        v350 = *(_QWORD *)&v349[32 * v348 - 24];
                        if ( v350 )
                        {
                          valueFromExpr(
                            (_DWORD)v616,
                            v350,
                            *((unsigned __int8 *)v616 + 100),
                            *(unsigned __int8 *)(v345 + 12),
                            (__int64)&v636,
                            0);
                          v351 = (_QWORD *)v636;
                          if ( !v636 )
                            goto LABEL_737;
                          v624 = *((unsigned __int8 *)qword_18010E020 + (*(_WORD *)(v636 + 20) & 0x3F));
                          if ( (*(_WORD *)(v636 + 20) & 0x9000) != 0 || *(_DWORD *)(v636 + 32) )
                            vdbeMemClear(v636);
                          v352 = (_QWORD *)v351[3];
                          if ( v352 )
                          {
                            if ( (unsigned __int64)v351 < v352[62] )
                            {
                              if ( (unsigned __int64)v351 >= v352[60] )
                              {
                                *v351 = v352[59];
                                v352[59] = v351;
                                goto LABEL_737;
                              }
                              if ( (unsigned __int64)v351 >= v352[61] )
                              {
                                *v351 = v352[57];
                                v352[57] = v351;
                                goto LABEL_737;
                              }
                            }
                            if ( v352[97] )
                            {
                              measureAllocationSize(v352, v351);
                              goto LABEL_737;
                            }
                          }
                          if ( dword_18013C1B0 )
                          {
                            if ( (_QWORD)xmmword_18013FC60 )
                              ((void (*)(void))xmmword_18013C230)();
                            v353 = ((__int64 (__fastcall *)(_QWORD *))xmmword_18013C1E8)(v351);
                            --qword_18013FBE8;
                            qword_18013FBA0 -= v353;
                            ((void (__fastcall *)(_QWORD *))xmmword_18013C1D8)(v351);
                            if ( (_QWORD)xmmword_18013FC60 )
                            {
                              v354 = (void (*)(void))xmmword_18013C240;
                              goto LABEL_736;
                            }
                          }
                          else
                          {
                            v354 = (void (*)(void))xmmword_18013C1D8;
LABEL_736:
                            v354();
                          }
LABEL_737:
                          v345 = (__int64)v627;
                        }
                      }
                    }
                  }
                }
                v346 = v320;
                if ( *((char *)v308 + 48) >= 0 )
                {
                  v347 = (__int16)sqlite3TableColumnToStorage(v308, (unsigned __int16)v342);
                }
                else
                {
                  for ( i1 = v308[2]; i1; i1 = (const char *)*((_QWORD *)i1 + 5) )
                  {
                    if ( (*((_DWORD *)i1 + 25) & 3) == 2 )
                      break;
                  }
                  if ( *((_WORD *)i1 + 48) )
                  {
                    v356 = 0;
                    while ( (_WORD)v342 != *(_WORD *)(*((_QWORD *)i1 + 1) + 2LL * v356) )
                    {
                      if ( (int)++v356 >= *((unsigned __int16 *)i1 + 48) )
                        goto LABEL_746;
                    }
                  }
                  else
                  {
LABEL_746:
                    LOWORD(v356) = -1;
                  }
                  v347 = (__int16)v356;
                }
LABEL_749:
                v357 = v623[17] - 1;
                LODWORD(v636) = v357;
                v358 = v357 - 1;
                v623[17] = v357 - 1;
                if ( (*(_BYTE *)(v345 + 8) & 0xF) != 0 )
                {
                  v359 = *((int *)v5 + 36);
                  if ( *((_DWORD *)v5 + 37) > (int)v359 )
                  {
                    v360 = v624;
                    v361 = 3 * v359;
                    *((_DWORD *)v5 + 36) = v359 + 1;
                    v362 = *((_QWORD *)v5 + 17);
                    *(_DWORD *)(v362 + 8 * v361) = 64786;
                    *(_DWORD *)(v362 + 8 * v361 + 4) = v346;
                    *(_DWORD *)(v362 + 8 * v361 + 8) = v358;
                    *(_DWORD *)(v362 + 8 * v361 + 12) = v347;
                    *(_DWORD *)(v362 + 8 * v361 + 16) = v360;
                  }
                  else
                  {
                    LODWORD(v359) = addOp4IntSlow((_DWORD)v5, 18, v346, v358, v347, v624);
                  }
                  v363 = *(int *)(v637 + 144);
                  if ( v346 >= 0 )
                  {
                    if ( (int)v363 > 0 )
                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v363 - 22) = 13;
                    v365 = *((int *)v5 + 36);
                    if ( *((_DWORD *)v5 + 37) > (int)v365 )
                    {
                      *((_DWORD *)v5 + 36) = v365 + 1;
                      v366 = 3 * v365;
                      v367 = *((_QWORD *)v5 + 17);
                      *(_DWORD *)(v367 + 8 * v366) = 94;
                      *(_DWORD *)(v367 + 8 * v366 + 4) = v346;
                      *(_DWORD *)(v367 + 8 * v366 + 8) = v347;
                      *(_DWORD *)(v367 + 8 * v366 + 12) = 3;
                      *(_QWORD *)(v367 + 8 * v366 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v615) = 3;
                      growOp3(v5, 94, (unsigned int)v346, v347, v615);
                    }
                    v364 = *((int *)v5 + 36);
                    if ( *((_DWORD *)v5 + 37) > (int)v364 )
                    {
                      v368 = 3 * v364;
                      *((_DWORD *)v5 + 36) = v364 + 1;
                      v369 = *((_QWORD *)v5 + 17);
                      *(_DWORD *)(v369 + 8 * v368) = 51;
                      *(_DWORD *)(v369 + 8 * v368 + 4) = 3;
                      *(_DWORD *)(v369 + 8 * v368 + 8) = v358;
                      *(_DWORD *)(v369 + 8 * v368 + 12) = 0;
                      *(_QWORD *)(v369 + 8 * v368 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v615) = 0;
                      LODWORD(v364) = growOp3(v5, 51, 3, v358, v615);
                    }
                  }
                  else
                  {
                    if ( (int)v363 > 0 )
                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v363 - 22) = 15;
                    LODWORD(v364) = v359;
                  }
                  v370 = sqlite3MPrintf(v616, "NULL value in %s.%s", *(const char **)v626, *(const char **)v345);
                  v371 = *((int *)v5 + 36);
                  v372 = v370;
                  if ( *((_DWORD *)v5 + 37) > (int)v371 )
                  {
                    v373 = 3 * v371;
                    *((_DWORD *)v5 + 36) = v371 + 1;
                    v374 = *((_QWORD *)v5 + 17);
                    *(_QWORD *)(v374 + 8 * v373) = 117;
                    *(_QWORD *)(v374 + 8 * v373 + 8) = 3;
                    *(_QWORD *)(v374 + 8 * v373 + 16) = 0;
                  }
                  else
                  {
                    LODWORD(v615) = 0;
                    LODWORD(v371) = growOp3(v5, 117, 0, 3, v615);
                  }
                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( v372 )
                      sqlite3DbNNFreeNN(*(_QWORD *)v5, v372);
                  }
                  else
                  {
                    if ( (int)v371 < 0 )
                      LODWORD(v371) = *((_DWORD *)v5 + 36) - 1;
                    v375 = *((_QWORD *)v5 + 17);
                    v32 = *(_BYTE *)(v375 + 24LL * (int)v371 + 1) == 0;
                    v376 = v375 + 24LL * (int)v371;
                    if ( v32 )
                    {
                      if ( v372 )
                      {
                        *(_QWORD *)(v376 + 16) = v372;
                        *(_BYTE *)(v376 + 1) = -6;
                      }
                    }
                    else
                    {
                      vdbeChangeP4Full(v5, v376, v372, 4294967290LL);
                    }
                  }
                  v377 = v635;
                  if ( v635 )
                  {
                    v378 = *((int *)v5 + 36);
                    if ( *((_DWORD *)v5 + 37) > (int)v378 )
                    {
                      v379 = v636;
                      *((_DWORD *)v5 + 36) = v378 + 1;
                      v380 = 3 * v378;
                      v381 = *((_QWORD *)v5 + 17);
                      *(_QWORD *)(v381 + 8 * v380) = 9;
                      *(_QWORD *)(v381 + 8 * v380 + 8) = v379;
                      *(_QWORD *)(v381 + 8 * v380 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v615) = 0;
                      growOp3(v5, 9, 0, (unsigned int)v636, v615);
                    }
                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                      v382 = &qword_18013FEA8;
                    else
                      v382 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v359);
                    *((_DWORD *)v382 + 2) = *((_DWORD *)v5 + 36);
                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                      v383 = &qword_18013FEA8;
                    else
                      v383 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v364);
                    v345 = (__int64)v627;
                    v357 = v636;
                    *((_DWORD *)v383 + 2) = *((_DWORD *)v5 + 36);
                    goto LABEL_788;
                  }
                  v345 = (__int64)v627;
                  v357 = v636;
                }
                else
                {
LABEL_788:
                  v377 = v635;
                }
                if ( (_DWORD)v625 )
                {
                  if ( v377 )
                  {
                    v384 = *((int *)v5 + 36);
                    if ( *((_DWORD *)v5 + 37) > (int)v384 )
                    {
                      v385 = v624;
                      *((_DWORD *)v5 + 36) = v384 + 1;
                      v386 = 3 * v384;
                      v387 = *((_QWORD *)v5 + 17);
                      *(_DWORD *)(v387 + 8 * v386) = 64786;
                      *(_DWORD *)(v387 + 8 * v386 + 4) = v346;
                      *(_DWORD *)(v387 + 8 * v386 + 8) = v358;
                      *(_DWORD *)(v387 + 8 * v386 + 12) = v347;
                      *(_DWORD *)(v387 + 8 * v386 + 16) = v385;
                    }
                    else
                    {
                      addOp4IntSlow((_DWORD)v5, 18, v346, v358, v347, v624);
                    }
                    v388 = *((int *)v5 + 36);
                    if ( (int)v388 > 0 )
                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v388 - 22) = *((unsigned __int8 *)&qword_18013D168
                                                                          + ((*(_DWORD *)(v345 + 8) >> 4) & 0xFu)
                                                                          - 1);
                    v342 = v634;
                    v389 = sqlite3MPrintf(
                             v616,
                             "non-%s value in %s.%s",
                             off_18013C388[((*(_DWORD *)(v345 + 8) >> 4) & 0xFu) - 1],
                             *(const char **)v626,
                             *(const char **)(*(_QWORD *)(v626 + 8) + 24LL * v634));
                    v390 = *((int *)v5 + 36);
                    v391 = v389;
                    if ( *((_DWORD *)v5 + 37) > (int)v390 )
                    {
                      v392 = 3 * v390;
                      *((_DWORD *)v5 + 36) = v390 + 1;
                      v393 = *((_QWORD *)v5 + 17);
                      *(_QWORD *)(v393 + 8 * v392) = 117;
                      *(_QWORD *)(v393 + 8 * v392 + 8) = 3;
                      *(_QWORD *)(v393 + 8 * v392 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v615) = 0;
                      LODWORD(v390) = growOp3(v5, 117, 0, 3, v615);
                    }
                    v394 = *(_QWORD *)v5;
                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                      goto LABEL_801;
                    if ( (int)v390 < 0 )
                      LODWORD(v390) = *((_DWORD *)v5 + 36) - 1;
                    v395 = *((_QWORD *)v5 + 17);
                    v32 = *(_BYTE *)(v395 + 24LL * (int)v390 + 1) == 0;
                    v396 = v395 + 24LL * (int)v390;
                    if ( !v32 )
                    {
LABEL_844:
                      vdbeChangeP4Full(v5, v396, v391, 4294967290LL);
                      goto LABEL_846;
                    }
LABEL_820:
                    if ( v391 )
                    {
                      *(_QWORD *)(v396 + 16) = v391;
                      *(_BYTE *)(v396 + 1) = -6;
                    }
                    goto LABEL_846;
                  }
LABEL_845:
                  v342 = v634;
                  goto LABEL_846;
                }
                v397 = *(_BYTE *)(v345 + 12);
                if ( v397 == 66 )
                {
                  v398 = *((int *)v5 + 36);
                  if ( *((_DWORD *)v5 + 37) > (int)v398 )
                  {
                    v399 = v624;
                    *((_DWORD *)v5 + 36) = v398 + 1;
                    v400 = 3 * v398;
                    v401 = *((_QWORD *)v5 + 17);
                    *(_DWORD *)(v401 + 8 * v400) = 64786;
                    *(_DWORD *)(v401 + 8 * v400 + 4) = v346;
                    *(_DWORD *)(v401 + 8 * v400 + 8) = v358;
                    *(_DWORD *)(v401 + 8 * v400 + 12) = v347;
                    *(_DWORD *)(v401 + 8 * v400 + 16) = v399;
                  }
                  else
                  {
                    addOp4IntSlow((_DWORD)v5, 18, v346, v358, v347, v624);
                  }
                  v402 = *((int *)v5 + 36);
                  if ( (int)v402 > 0 )
                    *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v402 - 22) = 28;
                  v342 = v634;
                  v403 = sqlite3MPrintf(
                           v616,
                           "NUMERIC value in %s.%s",
                           *(const char **)v626,
                           *(const char **)(*(_QWORD *)(v626 + 8) + 24LL * v634));
                  v404 = *((int *)v5 + 36);
                  v391 = v403;
                  if ( *((_DWORD *)v5 + 37) > (int)v404 )
                  {
                    v405 = 3 * v404;
                    *((_DWORD *)v5 + 36) = v404 + 1;
                    v406 = *((_QWORD *)v5 + 17);
                    *(_QWORD *)(v406 + 8 * v405) = 117;
                    *(_QWORD *)(v406 + 8 * v405 + 8) = 3;
                    *(_QWORD *)(v406 + 8 * v405 + 16) = 0;
                  }
                  else
                  {
                    LODWORD(v615) = 0;
                    LODWORD(v404) = growOp3(v5, 117, 0, 3, v615);
                  }
                  v394 = *(_QWORD *)v5;
                  if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( (int)v404 < 0 )
                      LODWORD(v404) = *((_DWORD *)v5 + 36) - 1;
                    v407 = *((_QWORD *)v5 + 17);
                    v32 = *(_BYTE *)(v407 + 24LL * (int)v404 + 1) == 0;
                    v396 = v407 + 24LL * (int)v404;
                    if ( !v32 )
                      goto LABEL_844;
                    goto LABEL_820;
                  }
LABEL_801:
                  if ( v391 )
                    goto LABEL_840;
                }
                else
                {
                  if ( v397 < 67 )
                    goto LABEL_845;
                  v408 = *((int *)v5 + 36);
                  v409 = v624;
                  if ( *((_DWORD *)v5 + 37) > (int)v408 )
                  {
                    *((_DWORD *)v5 + 36) = v408 + 1;
                    v410 = 3 * v408;
                    v411 = *((_QWORD *)v5 + 17);
                    *(_DWORD *)(v411 + 8 * v410) = 64786;
                    *(_DWORD *)(v411 + 8 * v410 + 4) = v346;
                    *(_DWORD *)(v411 + 8 * v410 + 8) = v358;
                    *(_DWORD *)(v411 + 8 * v410 + 12) = v347;
                    *(_DWORD *)(v411 + 8 * v410 + 16) = v409;
                  }
                  else
                  {
                    addOp4IntSlow((_DWORD)v5, 18, v346, v358, v347, v624);
                  }
                  v412 = *((int *)v5 + 36);
                  if ( (int)v412 > 0 )
                    *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v412 - 22) = 27;
                  v342 = v634;
                  if ( v346 >= 0 )
                    sqlite3ExprCodeGetColumnOfTable((_DWORD)v5, v626, v632, v634, 3);
                  v413 = sqlite3VdbeAddOp3((_DWORD)v5, 96, 3, 1, 0);
                  if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( v413 < 0 )
                      v413 = *((_DWORD *)v5 + 36) - 1;
                    v414 = *((_QWORD *)v5 + 17) + 24LL * v413;
                    if ( *(_BYTE *)(v414 + 1) )
                    {
                      vdbeChangeP4Full(v5, v414, "C", 0xFFFFFFFFLL);
                    }
                    else
                    {
                      *(_BYTE *)(v414 + 1) = -1;
                      *(_QWORD *)(v414 + 16) = "C";
                    }
                  }
                  sqlite3VdbeAddOp4Int((_DWORD)v5, 18, -1, v358, 3, v409);
                  v415 = *((int *)v5 + 36);
                  if ( (int)v415 > 0 )
                    *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v415 - 22) = 28;
                  v391 = sqlite3MPrintf(
                           v616,
                           "TEXT value in %s.%s",
                           *(const char **)v626,
                           *(const char **)(*(_QWORD *)(v626 + 8) + 24LL * v342));
                  v416 = sqlite3VdbeAddOp3((_DWORD)v5, 117, 0, 3, 0);
                  v394 = *(_QWORD *)v5;
                  if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( v416 < 0 )
                      v416 = *((_DWORD *)v5 + 36) - 1;
                    v396 = *((_QWORD *)v5 + 17) + 24LL * v416;
                    if ( *(_BYTE *)(v396 + 1) )
                      goto LABEL_844;
                    goto LABEL_820;
                  }
                  if ( v391 )
LABEL_840:
                    sqlite3DbNNFreeNN(v394, v391);
                }
LABEL_846:
                v417 = *((_QWORD *)v5 + 3);
                v418 = ~v357;
                if ( *(_DWORD *)(v417 + 68) + *(_DWORD *)(v417 + 72) >= 0 )
                  *(_DWORD *)(*(_QWORD *)(v417 + 80) + 4LL * v418) = *((_DWORD *)v5 + 36);
                else
                  resizeResolveLabel(v417, v5, (unsigned int)v418);
                integrityCheckResultRow(v5);
                v419 = *((_QWORD *)v5 + 3);
                v420 = ~v358;
                if ( *(_DWORD *)(v419 + 68) + *(_DWORD *)(v419 + 72) >= 0 )
                  *(_DWORD *)(*(_QWORD *)(v419 + 80) + 4LL * v420) = *((_DWORD *)v5 + 36);
                else
                  resizeResolveLabel(v419, v5, (unsigned int)v420);
                v308 = (const char **)v626;
                goto LABEL_853;
              }
LABEL_856:
              v422 = v308[4];
              if ( v422 )
              {
                v423 = v616;
                if ( (v616[6] & 0x200LL) == 0 )
                {
                  v424 = sqlite3ExprListDup(v616, v422, 0);
                  if ( !*((_BYTE *)v616 + 103) )
                  {
                    v425 = v623;
                    v426 = v623[17] - 1;
                    v623[16] = v632 + 1;
                    v427 = v426 - 1;
                    v425[17] = v426 - 1;
                    v428 = *(_DWORD *)v424 - 1;
                    LODWORD(v625) = v426 - 1;
                    if ( v428 > 0 )
                    {
                      v429 = v425;
                      do
                        sqlite3ExprIfFalse(v429, *(_QWORD *)(32LL * (unsigned int)v428-- + v424 + 8), v426, 0);
                      while ( v428 > 0 );
                      v427 = (unsigned int)v625;
                      v425 = v623;
                    }
                    sqlite3ExprIfTrue(v425, *(_QWORD *)(v424 + 8), v427, 16);
                    v430 = *((_QWORD *)v5 + 3);
                    v431 = ~v426;
                    if ( *(_DWORD *)(v430 + 68) + *(_DWORD *)(v430 + 72) >= 0 )
                      *(_DWORD *)(*(_QWORD *)(v430 + 80) + 4LL * v431) = *((_DWORD *)v5 + 36);
                    else
                      resizeResolveLabel(v430, v5, (unsigned int)v431);
                    v623[16] = 0;
                    v432 = sqlite3MPrintf(v616, "CHECK constraint failed in %s", *(const char **)v626);
                    v433 = *((int *)v5 + 36);
                    v434 = v432;
                    if ( *((_DWORD *)v5 + 37) > (int)v433 )
                    {
                      v435 = 3 * v433;
                      *((_DWORD *)v5 + 36) = v433 + 1;
                      v436 = *((_QWORD *)v5 + 17);
                      *(_QWORD *)(v436 + 8 * v435) = 117;
                      *(_QWORD *)(v436 + 8 * v435 + 8) = 3;
                      *(_QWORD *)(v436 + 8 * v435 + 16) = 0;
                    }
                    else
                    {
                      LODWORD(v615) = 0;
                      LODWORD(v433) = growOp3(v5, 117, 0, 3, v615);
                    }
                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                    {
                      if ( v434 )
                        sqlite3DbNNFreeNN(*(_QWORD *)v5, v434);
                    }
                    else
                    {
                      if ( (int)v433 < 0 )
                        LODWORD(v433) = *((_DWORD *)v5 + 36) - 1;
                      v437 = *((_QWORD *)v5 + 17);
                      v32 = *(_BYTE *)(v437 + 24LL * (int)v433 + 1) == 0;
                      v438 = v437 + 24LL * (int)v433;
                      if ( v32 )
                      {
                        if ( v434 )
                        {
                          *(_QWORD *)(v438 + 16) = v434;
                          *(_BYTE *)(v438 + 1) = -6;
                        }
                      }
                      else
                      {
                        vdbeChangeP4Full(v5, v438, v434, 4294967290LL);
                      }
                    }
                    integrityCheckResultRow(v5);
                    v439 = *((_QWORD *)v5 + 3);
                    v440 = ~v427;
                    if ( *(_DWORD *)(v439 + 68) + *(_DWORD *)(v439 + 72) >= 0 )
                      *(_DWORD *)(*(_QWORD *)(v439 + 80) + 4LL * v440) = *((_DWORD *)v5 + 36);
                    else
                      resizeResolveLabel(v439, v5, (unsigned int)v440);
                    v423 = v616;
                  }
                  if ( v424 )
                    exprListDeleteNN(v423, v424);
                  v308 = (const char **)v626;
                }
              }
              v441 = v622;
              if ( v622 != 113 )
              {
                v442 = (__int64)v308[2];
                v443 = 0;
                v624 = 0;
                v444 = -1;
                v445 = 0;
                if ( v442 )
                {
                  v446 = v623;
                  do
                  {
                    v447 = v446[17] - 1;
                    v446[17] = v447;
                    if ( v628 != v442 )
                    {
                      IndexKey = sqlite3GenerateIndexKey((_DWORD)v446, v442, v632, 0, 0, (__int64)&v638, v443, v444);
                      v449 = *((int *)v5 + 36);
                      v450 = v445 + 8;
                      v444 = IndexKey;
                      if ( *((_DWORD *)v5 + 37) > (int)v449 )
                      {
                        *((_DWORD *)v5 + 36) = v449 + 1;
                        v451 = 3 * v449;
                        v452 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v452 + 8 * v451) = 86;
                        *(_DWORD *)(v452 + 8 * v451 + 4) = v450;
                        *(_QWORD *)(v452 + 8 * v451 + 8) = 1;
                        *(_QWORD *)(v452 + 8 * v451 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 0;
                        growOp3(v5, 86, v450, 1, v615);
                      }
                      v453 = *(unsigned __int16 *)(v442 + 96);
                      v454 = v445 + v629;
                      v455 = *((int *)v5 + 36);
                      if ( *((_DWORD *)v5 + 37) > (int)v455 )
                      {
                        v456 = 3 * v455;
                        *((_DWORD *)v5 + 36) = v455 + 1;
                        v457 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v457 + 8 * v456) = 64797;
                        *(_DWORD *)(v457 + 8 * v456 + 4) = v454;
                        *(_DWORD *)(v457 + 8 * v456 + 8) = v447;
                        *(_DWORD *)(v457 + 8 * v456 + 12) = v444;
                        *(_DWORD *)(v457 + 8 * v456 + 16) = v453;
                      }
                      else
                      {
                        LODWORD(v455) = addOp4IntSlow((_DWORD)v5, 29, v454, v447, v444, v453);
                      }
                      sqlite3VdbeLoadString(v5, 3, "row ");
                      v458 = *((int *)v5 + 36);
                      if ( *((_DWORD *)v5 + 37) > (int)v458 )
                      {
                        *((_DWORD *)v5 + 36) = v458 + 1;
                        v459 = 3 * v458;
                        v460 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v460 + 8 * v459) = 111;
                        *(_DWORD *)(v460 + 8 * v459 + 4) = 7;
                        *(_DWORD *)(v460 + 8 * v459 + 8) = 3;
                        *(_DWORD *)(v460 + 8 * v459 + 12) = 3;
                        *(_QWORD *)(v460 + 8 * v459 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 3;
                        growOp3(v5, 111, 7, 3, v615);
                      }
                      sqlite3VdbeLoadString(v5, 4, " missing from index ");
                      v461 = *((int *)v5 + 36);
                      if ( *((_DWORD *)v5 + 37) > (int)v461 )
                      {
                        *((_DWORD *)v5 + 36) = v461 + 1;
                        v462 = 3 * v461;
                        v463 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v463 + 8 * v462) = 111;
                        *(_DWORD *)(v463 + 8 * v462 + 4) = 4;
                        *(_DWORD *)(v463 + 8 * v462 + 8) = 3;
                        *(_DWORD *)(v463 + 8 * v462 + 12) = 3;
                        *(_QWORD *)(v463 + 8 * v462 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 3;
                        growOp3(v5, 111, 4, 3, v615);
                      }
                      String = sqlite3VdbeLoadString(v5, 4, *(_QWORD *)v442);
                      v465 = *((int *)v5 + 36);
                      v466 = String;
                      LODWORD(v625) = String;
                      if ( *((_DWORD *)v5 + 37) > (int)v465 )
                      {
                        *((_DWORD *)v5 + 36) = v465 + 1;
                        v467 = 3 * v465;
                        v468 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v468 + 8 * v467) = 111;
                        *(_DWORD *)(v468 + 8 * v467 + 4) = 4;
                        *(_DWORD *)(v468 + 8 * v467 + 8) = 3;
                        *(_DWORD *)(v468 + 8 * v467 + 12) = 3;
                        *(_QWORD *)(v468 + 8 * v467 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 3;
                        growOp3(v5, 111, 4, 3, v615);
                      }
                      v469 = integrityCheckResultRow(v5);
                      v470 = *(_QWORD *)v5;
                      v471 = *((_DWORD *)v5 + 36);
                      v635 = v469;
                      if ( *(_BYTE *)(v470 + 103) )
                        v472 = &qword_18013FEA8;
                      else
                        v472 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v455);
                      v473 = v626;
                      *((_DWORD *)v472 + 2) = v471;
                      if ( *(char *)(v473 + 48) >= 0 )
                      {
                        v474 = v629 + v624;
                        v475 = *((int *)v5 + 36);
                        if ( *((_DWORD *)v5 + 37) > (int)v475 )
                        {
                          *((_DWORD *)v5 + 36) = v475 + 1;
                          v476 = 3 * v475;
                          v477 = *((_QWORD *)v5 + 17);
                          *(_DWORD *)(v477 + 8 * v476) = 142;
                          *(_DWORD *)(v477 + 8 * v476 + 4) = v474;
                          *(_QWORD *)(v477 + 8 * v476 + 8) = 3;
                          *(_QWORD *)(v477 + 8 * v476 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 0;
                          growOp3(v5, 142, v474, 3, v615);
                        }
                        v478 = *((int *)v5 + 36);
                        v479 = v444 + *(unsigned __int16 *)(v442 + 96) - 1;
                        if ( *((_DWORD *)v5 + 37) > (int)v478 )
                        {
                          v480 = 3 * v478;
                          *((_DWORD *)v5 + 36) = v478 + 1;
                          v481 = *((_QWORD *)v5 + 17);
                          *(_DWORD *)(v481 + 8 * v480) = 53;
                          *(_QWORD *)(v481 + 8 * v480 + 4) = 3;
                          *(_DWORD *)(v481 + 8 * v480 + 12) = v479;
                          *(_QWORD *)(v481 + 8 * v480 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = v444 + *(unsigned __int16 *)(v442 + 96) - 1;
                          LODWORD(v478) = growOp3(v5, 53, 3, 0, v615);
                        }
                        sqlite3VdbeLoadString(v5, 3, "rowid not at end-of-record for row ");
                        v482 = *((int *)v5 + 36);
                        if ( *((_DWORD *)v5 + 37) > (int)v482 )
                        {
                          *((_DWORD *)v5 + 36) = v482 + 1;
                          v483 = 3 * v482;
                          v484 = *((_QWORD *)v5 + 17);
                          *(_DWORD *)(v484 + 8 * v483) = 111;
                          *(_DWORD *)(v484 + 8 * v483 + 4) = 7;
                          *(_DWORD *)(v484 + 8 * v483 + 8) = 3;
                          *(_DWORD *)(v484 + 8 * v483 + 12) = 3;
                          *(_QWORD *)(v484 + 8 * v483 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 3;
                          growOp3(v5, 111, 7, 3, v615);
                        }
                        sqlite3VdbeLoadString(v5, 4, " of index ");
                        v485 = *((int *)v5 + 36);
                        v486 = v466 - 1;
                        if ( *((_DWORD *)v5 + 37) > (int)v485 )
                        {
                          *((_DWORD *)v5 + 36) = v485 + 1;
                          v487 = 3 * v485;
                          v488 = *((_QWORD *)v5 + 17);
                          *(_QWORD *)(v488 + 8 * v487) = 9;
                          *(_DWORD *)(v488 + 8 * v487 + 8) = v486;
                          *(_DWORD *)(v488 + 8 * v487 + 12) = 0;
                          *(_QWORD *)(v488 + 8 * v487 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 0;
                          growOp3(v5, 9, 0, v486, v615);
                        }
                        if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                          v489 = &qword_18013FEA8;
                        else
                          v489 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v478);
                        *((_DWORD *)v489 + 2) = *((_DWORD *)v5 + 36);
                      }
                      v490 = 0;
                      v491 = 0;
                      if ( *(_WORD *)(v442 + 94) )
                      {
                        v492 = v624;
                        do
                        {
                          if ( *(char **)(*(_QWORD *)(v442 + 64) + 8LL * v491) != "BINARY" )
                          {
                            if ( !v490 )
                            {
                              v490 = v623[17] - 1;
                              v623[17] = v490;
                            }
                            v493 = *((int *)v5 + 36);
                            v494 = v492 + v629;
                            if ( *((_DWORD *)v5 + 37) > (int)v493 )
                            {
                              *((_DWORD *)v5 + 36) = v493 + 1;
                              v495 = 3 * v493;
                              v496 = *((_QWORD *)v5 + 17);
                              *(_DWORD *)(v496 + 8 * v495) = 94;
                              *(_DWORD *)(v496 + 8 * v495 + 4) = v494;
                              *(_DWORD *)(v496 + 8 * v495 + 8) = v491;
                              *(_DWORD *)(v496 + 8 * v495 + 12) = 3;
                              *(_QWORD *)(v496 + 8 * v495 + 16) = 0;
                            }
                            else
                            {
                              LODWORD(v615) = 3;
                              growOp3(v5, 94, v494, (unsigned int)v491, v615);
                            }
                            v497 = *((int *)v5 + 36);
                            if ( *((_DWORD *)v5 + 37) > (int)v497 )
                            {
                              *((_DWORD *)v5 + 36) = v497 + 1;
                              v498 = 3 * v497;
                              v499 = *((_QWORD *)v5 + 17);
                              *(_DWORD *)(v499 + 8 * v498) = 52;
                              *(_DWORD *)(v499 + 8 * v498 + 4) = 3;
                              *(_DWORD *)(v499 + 8 * v498 + 8) = v490;
                              *(_DWORD *)(v499 + 8 * v498 + 12) = v491 + v444;
                              *(_QWORD *)(v499 + 8 * v498 + 16) = 0;
                            }
                            else
                            {
                              LODWORD(v615) = v491 + v444;
                              growOp3(v5, 52, 3, v490, v615);
                            }
                          }
                          ++v491;
                        }
                        while ( v491 < *(unsigned __int16 *)(v442 + 94) );
                        v466 = (unsigned int)v625;
                        if ( v490 )
                        {
                          v500 = *((int *)v5 + 36);
                          if ( *((_DWORD *)v5 + 37) > (int)v500 )
                          {
                            v501 = 3 * v500;
                            *((_DWORD *)v5 + 36) = v500 + 1;
                            v502 = *((_QWORD *)v5 + 17);
                            *(_QWORD *)(v502 + 8 * v501) = 9;
                            *(_QWORD *)(v502 + 8 * v501 + 8) = 0;
                            *(_QWORD *)(v502 + 8 * v501 + 16) = 0;
                          }
                          else
                          {
                            LODWORD(v615) = 0;
                            LODWORD(v500) = growOp3(v5, 9, 0, 0, v615);
                          }
                          v503 = *((_QWORD *)v5 + 3);
                          v504 = ~v490;
                          if ( *(_DWORD *)(v503 + 68) + *(_DWORD *)(v503 + 72) >= 0 )
                            *(_DWORD *)(*(_QWORD *)(v503 + 80) + 4LL * v504) = *((_DWORD *)v5 + 36);
                          else
                            resizeResolveLabel(v503, v5, (unsigned int)v504);
                          sqlite3VdbeLoadString(v5, 3, "row ");
                          v505 = *((int *)v5 + 36);
                          if ( *((_DWORD *)v5 + 37) > (int)v505 )
                          {
                            *((_DWORD *)v5 + 36) = v505 + 1;
                            v506 = 3 * v505;
                            v507 = *((_QWORD *)v5 + 17);
                            *(_DWORD *)(v507 + 8 * v506) = 111;
                            *(_DWORD *)(v507 + 8 * v506 + 4) = 7;
                            *(_DWORD *)(v507 + 8 * v506 + 8) = 3;
                            *(_DWORD *)(v507 + 8 * v506 + 12) = 3;
                            *(_QWORD *)(v507 + 8 * v506 + 16) = 0;
                          }
                          else
                          {
                            LODWORD(v615) = 3;
                            growOp3(v5, 111, 7, 3, v615);
                          }
                          sqlite3VdbeLoadString(v5, 4, " values differ from index ");
                          v508 = *((int *)v5 + 36);
                          v509 = v466 - 1;
                          if ( *((_DWORD *)v5 + 37) > (int)v508 )
                          {
                            *((_DWORD *)v5 + 36) = v508 + 1;
                            v510 = 3 * v508;
                            v511 = *((_QWORD *)v5 + 17);
                            *(_QWORD *)(v511 + 8 * v510) = 9;
                            *(_DWORD *)(v511 + 8 * v510 + 8) = v509;
                            *(_DWORD *)(v511 + 8 * v510 + 12) = 0;
                            *(_QWORD *)(v511 + 8 * v510 + 16) = 0;
                          }
                          else
                          {
                            LODWORD(v615) = 0;
                            growOp3(v5, 9, 0, v509, v615);
                          }
                          if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                            v512 = &qword_18013FEA8;
                          else
                            v512 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v500);
                          *((_DWORD *)v512 + 2) = *((_DWORD *)v5 + 36);
                        }
                      }
                      if ( *(_BYTE *)(v442 + 98) )
                      {
                        v513 = 0;
                        v514 = v623[17] - 1;
                        v623[17] = v514;
                        if ( *(_WORD *)(v442 + 94) )
                        {
                          v515 = v626;
                          do
                          {
                            v516 = *(__int16 *)(*(_QWORD *)(v442 + 8) + 2LL * v513);
                            if ( (v516 & 0x8000u) != 0LL
                              || (*(_BYTE *)(*(_QWORD *)(v515 + 8) + 24 * v516 + 8) & 0xF) == 0 )
                            {
                              v517 = *((int *)v5 + 36);
                              v518 = v513 + v444;
                              if ( *((_DWORD *)v5 + 37) > (int)v517 )
                              {
                                *((_DWORD *)v5 + 36) = v517 + 1;
                                v519 = 3 * v517;
                                v520 = *((_QWORD *)v5 + 17);
                                *(_DWORD *)(v520 + 8 * v519) = 50;
                                *(_DWORD *)(v520 + 8 * v519 + 4) = v518;
                                *(_DWORD *)(v520 + 8 * v519 + 8) = v514;
                                *(_DWORD *)(v520 + 8 * v519 + 12) = 0;
                                *(_QWORD *)(v520 + 8 * v519 + 16) = 0;
                              }
                              else
                              {
                                LODWORD(v615) = 0;
                                growOp3(v5, 50, v518, v514, v615);
                              }
                            }
                            ++v513;
                          }
                          while ( v513 < *(unsigned __int16 *)(v442 + 94) );
                          v466 = (unsigned int)v625;
                        }
                        v521 = v629 + v624;
                        v522 = *((int *)v5 + 36);
                        if ( *((_DWORD *)v5 + 37) > (int)v522 )
                        {
                          v523 = 3 * v522;
                          *((_DWORD *)v5 + 36) = v522 + 1;
                          v524 = *((_QWORD *)v5 + 17);
                          *(_DWORD *)(v524 + 8 * v523) = 39;
                          *(_DWORD *)(v524 + 8 * v523 + 4) = v521;
                          *(_QWORD *)(v524 + 8 * v523 + 8) = 0;
                          *(_QWORD *)(v524 + 8 * v523 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 0;
                          LODWORD(v522) = growOp3(v5, 39, v521, 0, v615);
                        }
                        v525 = *((int *)v5 + 36);
                        if ( *((_DWORD *)v5 + 37) > (int)v525 )
                        {
                          *((_DWORD *)v5 + 36) = v525 + 1;
                          v526 = 3 * v525;
                          v527 = *((_QWORD *)v5 + 17);
                          *(_QWORD *)(v527 + 8 * v526) = 9;
                          *(_DWORD *)(v527 + 8 * v526 + 8) = v514;
                          *(_DWORD *)(v527 + 8 * v526 + 12) = 0;
                          *(_QWORD *)(v527 + 8 * v526 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 0;
                          growOp3(v5, 9, 0, v514, v615);
                        }
                        if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                          v528 = &qword_18013FEA8;
                        else
                          v528 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v522);
                        v529 = v629 + v624;
                        *((_DWORD *)v528 + 2) = *((_DWORD *)v5 + 36);
                        v530 = *((int *)v5 + 36);
                        v531 = *(unsigned __int16 *)(v442 + 94);
                        if ( *((_DWORD *)v5 + 37) > (int)v530 )
                        {
                          *((_DWORD *)v5 + 36) = v530 + 1;
                          v532 = 3 * v530;
                          v533 = *((_QWORD *)v5 + 17);
                          *(_DWORD *)(v533 + 8 * v532) = 64809;
                          *(_DWORD *)(v533 + 8 * v532 + 4) = v529;
                          *(_DWORD *)(v533 + 8 * v532 + 8) = v514;
                          *(_DWORD *)(v533 + 8 * v532 + 12) = v444;
                          *(_DWORD *)(v533 + 8 * v532 + 16) = v531;
                        }
                        else
                        {
                          addOp4IntSlow((_DWORD)v5, 41, v529, v514, v444, v531);
                        }
                        sqlite3VdbeLoadString(v5, 3, "non-unique entry in index ");
                        v534 = *((int *)v5 + 36);
                        if ( *((_DWORD *)v5 + 37) > (int)v534 )
                        {
                          *((_DWORD *)v5 + 36) = v534 + 1;
                          v535 = 3 * v534;
                          v536 = *((_QWORD *)v5 + 17);
                          *(_QWORD *)(v536 + 8 * v535) = 9;
                          *(_DWORD *)(v536 + 8 * v535 + 8) = v466;
                          *(_DWORD *)(v536 + 8 * v535 + 12) = 0;
                          *(_QWORD *)(v536 + 8 * v535 + 16) = 0;
                        }
                        else
                        {
                          LODWORD(v615) = 0;
                          growOp3(v5, 9, 0, v466, v615);
                        }
                        v537 = *((_QWORD *)v5 + 3);
                        v538 = ~v514;
                        if ( *(_DWORD *)(v537 + 68) + *(_DWORD *)(v537 + 72) >= 0 )
                          *(_DWORD *)(*(_QWORD *)(v537 + 80) + 4LL * v538) = *((_DWORD *)v5 + 36);
                        else
                          resizeResolveLabel(v537, v5, (unsigned int)v538);
                      }
                      if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                        v539 = &qword_18013FEA8;
                      else
                        v539 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * v635);
                      v540 = v638;
                      v446 = v623;
                      *((_DWORD *)v539 + 2) = *((_DWORD *)v5 + 36);
                      if ( v540 )
                      {
                        v541 = *((_QWORD *)v446 + 2);
                        v542 = (unsigned int)~v540;
                        v543 = *(_QWORD *)(v541 + 24);
                        if ( *(_DWORD *)(v543 + 68) + *(_DWORD *)(v543 + 72) >= 0 )
                        {
                          *(_DWORD *)(*(_QWORD *)(v543 + 80) + 4LL * (int)v542) = *(_DWORD *)(v541 + 144);
                        }
                        else
                        {
                          resizeResolveLabel(v543, *((_QWORD *)v446 + 2), v542);
                          v446 = v623;
                        }
                      }
                      v445 = v624;
                      v443 = v442;
                    }
                    v442 = *(_QWORD *)(v442 + 40);
                    v624 = ++v445;
                  }
                  while ( v442 );
                }
                v441 = v622;
              }
              v544 = *((int *)v5 + 36);
              v545 = v621;
              if ( *((_DWORD *)v5 + 37) > (int)v544 )
              {
                v546 = v632;
                *((_DWORD *)v5 + 36) = v544 + 1;
                v547 = 3 * v544;
                v548 = *((_QWORD *)v5 + 17);
                *(_DWORD *)(v548 + 8 * v547) = 39;
                *(_DWORD *)(v548 + 8 * v547 + 4) = v546;
                *(_DWORD *)(v548 + 8 * v547 + 8) = v545;
                *(_DWORD *)(v548 + 8 * v547 + 12) = 0;
                *(_QWORD *)(v548 + 8 * v547 + 16) = 0;
              }
              else
              {
                LODWORD(v615) = 0;
                growOp3(v5, 39, v632, (unsigned int)v621, v615);
              }
              if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                v549 = &qword_18013FEA8;
              else
                v549 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (v545 - 1));
              *((_DWORD *)v549 + 2) = *((_DWORD *)v5 + 36);
              if ( v441 == 113 )
              {
                v56 = v623;
              }
              else
              {
                sqlite3VdbeLoadString(v5, 2, "wrong # of entries in index ");
                v550 = 0;
                v551 = *(const char **)(v626 + 16);
                if ( v551 )
                {
                  v552 = (const char *)v628;
                  do
                  {
                    if ( v552 != v551 )
                    {
                      v553 = *((int *)v5 + 36);
                      v554 = v550 + v629;
                      if ( *((_DWORD *)v5 + 37) > (int)v553 )
                      {
                        *((_DWORD *)v5 + 36) = v553 + 1;
                        v555 = 3 * v553;
                        v556 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v556 + 8 * v555) = 98;
                        *(_DWORD *)(v556 + 8 * v555 + 4) = v554;
                        *(_QWORD *)(v556 + 8 * v555 + 8) = 3;
                        *(_QWORD *)(v556 + 8 * v555 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 0;
                        growOp3(v5, 98, v554, 3, v615);
                      }
                      v557 = *((int *)v5 + 36);
                      v558 = v550 + 8;
                      if ( *((_DWORD *)v5 + 37) > (int)v557 )
                      {
                        v559 = 3 * v557;
                        *((_DWORD *)v5 + 36) = v557 + 1;
                        v560 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v560 + 8 * v559) = 53;
                        *(_DWORD *)(v560 + 8 * v559 + 4) = v558;
                        *(_DWORD *)(v560 + 8 * v559 + 8) = 0;
                        *(_DWORD *)(v560 + 8 * v559 + 12) = 3;
                        *(_QWORD *)(v560 + 8 * v559 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 3;
                        LODWORD(v557) = growOp3(v5, 53, v558, 0, v615);
                      }
                      v561 = *((int *)v5 + 36);
                      if ( (int)v561 > 0 )
                        *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v561 - 22) = 144;
                      sqlite3VdbeLoadString(v5, 4, *(_QWORD *)v551);
                      v562 = *((int *)v5 + 36);
                      if ( *((_DWORD *)v5 + 37) > (int)v562 )
                      {
                        *((_DWORD *)v5 + 36) = v562 + 1;
                        v563 = 3 * v562;
                        v564 = *((_QWORD *)v5 + 17);
                        *(_DWORD *)(v564 + 8 * v563) = 111;
                        *(_DWORD *)(v564 + 8 * v563 + 4) = 4;
                        *(_DWORD *)(v564 + 8 * v563 + 8) = 2;
                        *(_DWORD *)(v564 + 8 * v563 + 12) = 3;
                        *(_QWORD *)(v564 + 8 * v563 + 16) = 0;
                      }
                      else
                      {
                        LODWORD(v615) = 3;
                        growOp3(v5, 111, 4, 2, v615);
                      }
                      integrityCheckResultRow(v5);
                      if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                        v565 = &qword_18013FEA8;
                      else
                        v565 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v557);
                      *((_DWORD *)v565 + 2) = *((_DWORD *)v5 + 36);
                      v552 = (const char *)v628;
                    }
                    v551 = (const char *)*((_QWORD *)v551 + 5);
                    ++v550;
                  }
                  while ( v551 );
                }
                v56 = v623;
                if ( v628 )
                {
                  v566 = *(unsigned __int16 *)(v628 + 94);
                  if ( v566 == 1 )
                  {
                    if ( v633 )
                    {
                      v567 = *((unsigned __int8 *)v623 + 31);
                      if ( (unsigned __int8)v567 < 8u )
                      {
                        v623[v567 + 56] = v633;
                        ++*((_BYTE *)v56 + 31);
                      }
                    }
                  }
                  else if ( v566 > v623[10] )
                  {
                    v623[10] = v566;
                    v56[11] = v633;
                  }
                }
              }
LABEL_1025:
              v307 = (_QWORD *)*v640;
              v640 = v307;
            }
            v279 = v616;
            v278 = v630;
          }
          else
          {
LABEL_1027:
            v279 = v616;
          }
          v273 = v619;
        }
        v630 = ++v278;
        if ( v278 >= *((_DWORD *)v279 + 10) )
          goto LABEL_1030;
      }
    case 0x17:
      if ( !v58 )
        goto LABEL_177;
      v88 = strlen_0(v58) & 0x3FFFFFFF;
      v89 = 0;
      while ( 2 )
      {
        v628 = v89;
        if ( (_DWORD)v89 == 6 )
          goto LABEL_177;
        v90 = off_18010F1B8[(int)v89];
        if ( !v90 )
          goto LABEL_177;
        v91 = v88;
        v92 = v617;
        if ( !v88 )
          goto LABEL_171;
        do
        {
          --v91;
          if ( !*v92
            || *((_BYTE *)qword_180114680 + (unsigned __int8)*v92) != *((_BYTE *)qword_180114680 + (unsigned __int8)*v90) )
          {
            goto LABEL_172;
          }
          ++v92;
          ++v90;
        }
        while ( v91 > 0 );
LABEL_171:
        --v91;
LABEL_172:
        if ( v91 >= 0
          && *((unsigned __int8 *)qword_180114680 + (unsigned __int8)*v92) != *((unsigned __int8 *)qword_180114680
                                                                              + (unsigned __int8)*v90) )
        {
          v89 = (unsigned int)(v89 + 1);
          continue;
        }
        break;
      }
      if ( (_DWORD)v89 == 2 )
      {
        if ( (v616[6] & 0x10000000) == 0 )
          goto LABEL_181;
LABEL_177:
        LODWORD(v89) = -1;
        v628 = -1;
      }
      else if ( (_DWORD)v89 != -1 )
      {
        goto LABEL_181;
      }
      if ( !*(_DWORD *)(a3 + 8) )
      {
        v93 = 0;
        *(_DWORD *)(a3 + 8) = 1;
        v618 = 0;
LABEL_182:
        v66 = v616;
        for ( i2 = *((_DWORD *)v616 + 10) - 1; i2 >= 0; v93 = v618 )
        {
          v95 = 32LL * (unsigned int)i2;
          if ( *(_QWORD *)(v95 + v616[4] + 8) && (i2 == v93 || !*(_DWORD *)(a3 + 8)) )
          {
            *((_DWORD *)v5 + 51) |= 1 << i2;
            if ( i2 != 1 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 32LL) + v95 + 8) + 17LL) )
              *((_DWORD *)v5 + 52) |= 1 << i2;
            sqlite3VdbeAddOp3((_DWORD)v5, 4, i2, 1, v89);
          }
          --i2;
          LODWORD(v89) = v628;
        }
        sqlite3VdbeAddOp2(v5, 84, 1, 1);
        goto LABEL_1151;
      }
LABEL_181:
      v93 = v618;
      goto LABEL_182;
    case 0x18:
      v96 = *(__int64 **)(*(_QWORD *)(v18 + 8) + 8LL);
      v97 = -2;
      v631 = -2;
      v98 = *v96;
      if ( v58 )
      {
        sqlite3DecOrHexToI64(v58, &v631);
        v97 = v631;
        if ( v631 < -1 )
          v97 = -1;
      }
      if ( v97 >= -1 )
      {
        v99 = *(_QWORD *)(v98 + 296);
        *(_QWORD *)(v98 + 208) = v97;
        if ( v99 )
          *(_QWORD *)(v99 + 32) = v97;
      }
      AutoVacuum = *(_QWORD *)(v98 + 208);
      goto LABEL_1149;
    case 0x1A:
      v74 = "exclusive";
      if ( !v58 )
        goto LABEL_147;
      v75 = v58;
      v76 = "exclusive";
      while ( 2 )
      {
        v77 = (unsigned __int8)*v75;
        v78 = *(unsigned __int8 *)v76;
        if ( (_DWORD)v77 == (_DWORD)v78 )
        {
          if ( !*v75 )
          {
            v79 = 1;
            goto LABEL_148;
          }
        }
        else if ( *((unsigned __int8 *)qword_180114680 + v77) != *((unsigned __int8 *)qword_180114680 + v78) )
        {
          v80 = v58;
          for ( i3 = "normal"; ; ++i3 )
          {
            v79 = (unsigned __int8)*v80;
            v82 = *(unsigned __int8 *)i3;
            if ( (_DWORD)v79 == (_DWORD)v82 )
            {
              if ( !*v80 )
                goto LABEL_148;
            }
            else if ( *((unsigned __int8 *)qword_180114680 + v79) != *((unsigned __int8 *)qword_180114680 + v82) )
            {
LABEL_147:
              v79 = 0xFFFFFFFFLL;
LABEL_148:
              v66 = v616;
              if ( !*(_DWORD *)(a3 + 8) )
              {
                if ( (_DWORD)v79 == -1 )
                {
                  v83 = *((unsigned __int8 *)v616 + 105);
LABEL_160:
                  if ( v83 != 1 )
                    v74 = "normal";
                  returnSingleText(v5, v74);
                  goto LABEL_1151;
                }
                if ( *((int *)v616 + 10) > 2 )
                {
                  v84 = 2;
                  do
                  {
                    v85 = *(__int64 **)(*(_QWORD *)(32LL * v84 + v616[4] + 8) + 8LL);
                    v86 = *v85;
                    if ( !*(_BYTE *)(*v85 + 16) )
                    {
                      v87 = *(_QWORD *)(v86 + 296);
                      if ( !v87 || *(_BYTE *)(v87 + 63) != 2 )
                        *(_BYTE *)(v86 + 8) = v79;
                    }
                    ++v84;
                  }
                  while ( v84 < *((_DWORD *)v616 + 10) );
                }
                *((_BYTE *)v616 + 105) = v79;
              }
              v83 = sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v18 + 8) + 8LL), v79);
              goto LABEL_160;
            }
            ++v80;
          }
        }
        ++v75;
        ++v76;
        continue;
      }
    case 0x1B:
      v631 = 0;
      sqlite3CodeVerifySchema(v623, v618);
      ++v623[14];
      v72 = v56[14];
      if ( *((_BYTE *)qword_180114680 + (unsigned __int8)*v639) == 112 )
      {
        sqlite3VdbeAddOp2(v5, 177, v618, v72);
      }
      else
      {
        if ( !v617 || (unsigned int)sqlite3DecOrHexToI64(v617, &v631) || (v73 = v631, v631 < 0) )
        {
          v73 = 0;
        }
        else if ( v631 > 4294967294LL )
        {
          v73 = -2;
        }
        sqlite3VdbeAddOp3((_DWORD)v5, 178, v618, v72, v73);
      }
      sqlite3VdbeAddOp2(v5, 84, v72, 1);
      goto LABEL_1150;
    case 0x1C:
      if ( !v58 )
        goto LABEL_259;
      sqlite3DecOrHexToI64(v58, &v626);
      if ( v626 < 0 )
        v626 = qword_18013C2D8;
      if ( *(_DWORD *)(a3 + 8) )
      {
        v66 = v616;
        v135 = *((_DWORD *)v616 + 10) - 1;
        if ( v135 >= 0 )
        {
          do
          {
            v136 = *(_QWORD *)(32LL * (unsigned int)v135 + v616[4] + 8);
            if ( v136 && v135 == v618 )
            {
              v137 = v626;
              v138 = *(__int64 **)(v136 + 8);
              if ( *(_BYTE *)(v136 + 17) )
              {
                ++*(_DWORD *)(v136 + 20);
                if ( !*(_BYTE *)(v136 + 18) )
                  btreeLockCarefully(v136);
              }
              v139 = *v138;
              *(_QWORD *)(v139 + 160) = v137;
              pagerFixMaplimit(v139);
              if ( *(_BYTE *)(v136 + 17) )
              {
                v32 = (*(_DWORD *)(v136 + 20))-- == 1;
                if ( v32 )
                  unlockBtreeMutex(v136);
              }
            }
            --v135;
          }
          while ( v135 >= 0 );
          v5 = v627;
        }
      }
      else
      {
        v128 = v616;
        v129 = *((_DWORD *)v616 + 10) - 1;
        v616[8] = v626;
        if ( v129 < 0 )
        {
          v66 = v616;
        }
        else
        {
          do
          {
            v130 = *(_QWORD *)(32LL * (unsigned int)v129 + v128[4] + 8);
            if ( v130 && (v129 == v618 || !*(_DWORD *)(a3 + 8)) )
            {
              v131 = v626;
              v132 = *(__int64 **)(v130 + 8);
              if ( *(_BYTE *)(v130 + 17) )
              {
                ++*(_DWORD *)(v130 + 20);
                if ( !*(_BYTE *)(v130 + 18) )
                  btreeLockCarefully(v130);
              }
              v133 = *v132;
              *(_QWORD *)(v133 + 160) = v131;
              pagerFixMaplimit(v133);
              if ( *(_BYTE *)(v130 + 17) )
              {
                v32 = (*(_DWORD *)(v130 + 20))-- == 1;
                if ( v32 )
                  unlockBtreeMutex(v130);
              }
              v128 = v616;
            }
            --v129;
          }
          while ( v129 >= 0 );
          v21 = v625;
LABEL_259:
          v66 = v616;
        }
      }
      v626 = -1;
      v134 = sqlite3_file_control(v66, v21, 18, &v626);
      if ( !v134 )
      {
        returnSingleInt(v5, v626);
        goto LABEL_1151;
      }
      v123 = v617;
      if ( v134 != 12 )
      {
        v140 = v623;
        ++v623[12];
        v140[6] = v134;
      }
      goto LABEL_1152;
    case 0x1D:
      v66 = v616;
      v623[14] = 1;
      v218 = (_QWORD *)v616[70];
      if ( !v218 )
        goto LABEL_1151;
      do
      {
        sqlite3VdbeMultiLoad(v5, 1, "s", *(_QWORD *)(v218[2] + 8LL), v612);
        v218 = (_QWORD *)*v218;
      }
      while ( v218 );
      goto LABEL_1150;
    case 0x1E:
      if ( v58 )
      {
        v621 = 0;
        sqlite3GetInt32(v58, &v621);
        v587 = v621;
        if ( (v621 & 2) == 0 )
          goto LABEL_1150;
      }
      else
      {
        v587 = -2;
      }
      v32 = v625 == 0;
      v588 = v623;
      v589 = v618;
      v590 = v623[13];
      v623[13] = v590 + 1;
      if ( v32 )
      {
        v66 = v616;
        v591 = *((_DWORD *)v616 + 10) - 1;
        v620 = v591;
        if ( (int)v618 > v591 )
          goto LABEL_1143;
      }
      else
      {
        v591 = v618;
        v620 = v618;
      }
      v592 = __ROL4__(1, v618);
      v621 = v592;
      while ( 1 )
      {
        if ( v589 != 1 )
        {
          v593 = v588;
          if ( *((_QWORD *)v588 + 21) )
            v593 = (_DWORD *)*((_QWORD *)v588 + 21);
          v594 = v593[31];
          if ( (v592 & v594) == 0 )
            v593[31] = v594 | (1 << v589);
          v595 = *(_QWORD **)(*(_QWORD *)(32LL * v589 + v616[4] + 24) + 16LL);
          if ( v595 )
          {
            do
            {
              v596 = v595[2];
              if ( (*(_DWORD *)(v596 + 48) & 0x100) != 0 )
              {
                v597 = *(_QWORD *)(v596 + 16);
                if ( v597 )
                {
                  while ( *(char *)(v597 + 100) < 0 )
                  {
                    v597 = *(_QWORD *)(v597 + 40);
                    if ( !v597 )
                      goto LABEL_1111;
                  }
                }
                else
                {
LABEL_1111:
                  v598 = *(_WORD *)(v596 + 58) + 46;
                  if ( *(_WORD *)(v596 + 58) != 0xFFD2 )
                  {
                    sqlite3OpenTable((_DWORD)v623, v590, v589, v596, 112);
                    sqlite3VdbeAddOp3((_DWORD)v5, 33, v590, (v587 & 1) + 2 + *((_DWORD *)v5 + 36), v598);
                    v589 = v618;
                  }
                  v588 = v623;
                }
                v599 = sqlite3MPrintf(
                         v616,
                         "ANALYZE \"%w\".\"%w\"",
                         *(_QWORD *)(32LL * v589 + v616[4]),
                         *(_QWORD *)v596);
                if ( (v587 & 1) != 0 )
                {
                  v600 = *((_BYTE *)v588 + 31);
                  if ( v600 )
                  {
                    v602 = v600 - 1;
                    *((_BYTE *)v588 + 31) = v602;
                    v601 = v588[v602 + 56];
                  }
                  else
                  {
                    v601 = v588[14] + 1;
                    v623[14] = v601;
                  }
                  v603 = sqlite3VdbeAddOp3((_DWORD)v5, 117, 0, v601, 0);
                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( v599 )
                      sqlite3DbNNFreeNN(*(_QWORD *)v5, v599);
                  }
                  else
                  {
                    if ( v603 < 0 )
                      v603 = *((_DWORD *)v5 + 36) - 1;
                    v604 = *((_QWORD *)v5 + 17) + 24LL * v603;
                    if ( *(_BYTE *)(v604 + 1) )
                    {
                      vdbeChangeP4Full(v5, v604, v599, 4294967290LL);
                    }
                    else if ( v599 )
                    {
                      *(_QWORD *)(v604 + 16) = v599;
                      *(_BYTE *)(v604 + 1) = -6;
                    }
                  }
                  sqlite3VdbeAddOp2(v5, 84, v601, 1);
                }
                else
                {
                  v605 = sqlite3VdbeAddOp3((_DWORD)v5, 148, 0, 0, 0);
                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                  {
                    if ( v599 )
                      sqlite3DbNNFreeNN(*(_QWORD *)v5, v599);
                  }
                  else
                  {
                    if ( v605 < 0 )
                      v605 = *((_DWORD *)v5 + 36) - 1;
                    v606 = *((_QWORD *)v5 + 17) + 24LL * v605;
                    if ( *(_BYTE *)(v606 + 1) )
                    {
                      vdbeChangeP4Full(v5, v606, v599, 4294967290LL);
                    }
                    else if ( v599 )
                    {
                      *(_QWORD *)(v606 + 16) = v599;
                      *(_BYTE *)(v606 + 1) = -6;
                    }
                  }
                }
                v589 = v618;
              }
              v595 = (_QWORD *)*v595;
              v588 = v623;
            }
            while ( v595 );
            v592 = v621;
          }
          v591 = v620;
        }
        ++v589;
        v592 = __ROL4__(v592, 1);
        v618 = v589;
        v621 = v592;
        if ( v589 > v591 )
        {
          v66 = v616;
LABEL_1143:
          sqlite3VdbeAddOp0(v5, 166);
          goto LABEL_1151;
        }
      }
    case 0x1F:
      v63 = *(_QWORD *)(v18 + 8);
      if ( !v58 )
      {
        if ( v63 )
          AutoVacuum = *(int *)(*(_QWORD *)(v63 + 8) + 52LL);
        else
          AutoVacuum = 0;
        goto LABEL_1149;
      }
      v620 = 0;
      sqlite3GetInt32(v58, &v620);
      v65 = (unsigned int)v620;
      v66 = v616;
      *((_DWORD *)v616 + 29) = v620;
      if ( (unsigned int)sqlite3BtreeSetPageSize(v63, v65, 0, 0) == 7 )
        sqlite3OomFault(v616);
      goto LABEL_1151;
    case 0x20:
      for ( i4 = 0; i4 != 67; ++i4 )
        sqlite3VdbeMultiLoad(v5, 1, "s", (&off_18010EAA0)[3 * i4], v612);
      goto LABEL_1150;
    case 0x21:
      v67 = *(_QWORD *)(v18 + 8);
      v68 = -1;
      if ( !v58 )
        goto LABEL_117;
      if ( (unsigned int)sqlite3StrICmp(v58, "fast") )
      {
        v70 = 0;
        v68 = (unsigned __int8)getSafetyLevel(v69, 1, 0) != 0;
      }
      else
      {
        v68 = 2;
LABEL_117:
        v70 = 0;
      }
      v66 = v616;
      if ( !*(_DWORD *)(a3 + 8) && v68 >= 0 && *((int *)v616 + 10) > 0 )
      {
        do
          sqlite3BtreeSecureDelete(*(_QWORD *)(32LL * v70++ + v616[4] + 8), (unsigned int)v68);
        while ( v70 < *((_DWORD *)v616 + 10) );
      }
      v71 = sqlite3BtreeSecureDelete(v67, (unsigned int)v68);
      returnSingleInt(v5, v71);
      goto LABEL_1151;
    case 0x22:
      v66 = v616;
      if ( v616[3] )
        ((void (*)(void))xmmword_18013C230)();
      if ( !*((_BYTE *)v616 + 111) )
        btreeEnterAll(v616);
      if ( *((int *)v616 + 10) > 0 )
      {
        v585 = 0;
        do
        {
          v586 = *(_QWORD *)(32LL * v585 + v616[4] + 8);
          if ( v586 )
            ((void (__fastcall *)(_QWORD))qword_18013C2B8)(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(v586 + 8) + 288LL)
                                                                     + 72LL));
          ++v585;
        }
        while ( v585 < *((_DWORD *)v616 + 10) );
      }
      if ( !*((_BYTE *)v616 + 111) )
        btreeLeaveAll(v616);
      if ( v616[3] )
        ((void (*)(void))xmmword_18013C240)();
      goto LABEL_1151;
    case 0x23:
      if ( v58 && !(unsigned int)sqlite3DecOrHexToI64(v58, &v637) )
        sqlite3_soft_heap_limit64(v637);
      v607 = sqlite3_soft_heap_limit64(-1);
LABEL_1148:
      AutoVacuum = v607;
      goto LABEL_1149;
    case 0x24:
      if ( v58 )
      {
        v66 = v616;
        if ( *((_BYTE *)v616 + 101) )
        {
          if ( v618 != 1 )
          {
            LOBYTE(v54) = 1;
            v155 = ((unsigned __int8)getSafetyLevel(v58, 0, v54) + 1) & 7;
            *(_BYTE *)(v18 + 17) = 1;
            if ( !v155 )
              LOBYTE(v155) = 1;
            *(_BYTE *)(v18 + 16) = v155;
            setAllPagerFlags(v616);
          }
        }
        else
        {
          sqlite3ErrorMsg(v623, "Safety level may not be changed inside a transaction");
        }
        goto LABEL_1151;
      }
      AutoVacuum = *(unsigned __int8 *)(v18 + 16) - 1LL;
LABEL_1149:
      returnSingleInt(v5, AutoVacuum);
      goto LABEL_1150;
    case 0x25:
      if ( !v58 )
        goto LABEL_1150;
      sqlite3CodeVerifyNamedSchema(v623, v21);
      v160 = sqlite3LocateTable(v623, 2, v617, v21);
      v628 = v160;
      if ( !v160 )
        goto LABEL_1150;
      v161 = sqlite3PrimaryKeyIndex(v160);
      v623[14] = 7;
      v163 = (__int16 *)(v162 + 54);
      v32 = *(_BYTE *)(v162 + 63) == 1;
      v164 = v161;
      v627 = (char *)(v162 + 54);
      v626 = v161;
      if ( v32 || *v163 <= 0 )
      {
        viewGetColumnNames(v56, v162);
        v162 = v628;
        v164 = v626;
        v627 = (char *)v163;
      }
      LOWORD(v165) = *v163;
      if ( *v163 <= 0 )
        goto LABEL_1150;
      v166 = *(_QWORD *)(v162 + 8);
      v167 = (_QWORD *)(v55 + 16);
      v168 = 0;
      v169 = 0;
      v620 = 0;
      while ( 1 )
      {
        v170 = *(_WORD *)(v166 + 18);
        v171 = 0;
        if ( (v170 & 0x62) == 0 )
          goto LABEL_362;
        if ( *v167 )
          break;
        v167 = (_QWORD *)(v55 + 16);
        v620 = v168 + 1;
LABEL_387:
        v165 = *v163;
        ++v169;
        v168 = v620;
        v166 += 24;
        v164 = v626;
        if ( v169 >= v165 )
          goto LABEL_1150;
      }
      if ( (v170 & 0x20) != 0 )
        v171 = 2;
      else
        v171 = (v170 & 0x40 | 0x20u) >> 5;
LABEL_362:
      if ( (v170 & 1) != 0 )
      {
        v172 = 1;
        if ( v164 )
        {
          if ( (__int16)v165 >= 1 )
          {
            v173 = *(_QWORD *)(v164 + 8);
            do
            {
              if ( *(__int16 *)(v173 + 2LL * v172 - 2) == v169 )
                break;
              ++v172;
            }
            while ( v172 <= (__int16)v165 );
          }
          v162 = v628;
        }
      }
      v174 = *(unsigned __int16 *)(v166 + 16);
      if ( (_WORD)v174 )
      {
        if ( *(_BYTE *)(v162 + 63) )
        {
          v175 = 0;
        }
        else
        {
          v176 = *(_DWORD **)(v162 + 80);
          if ( v176 )
          {
            if ( *v176 >= (int)v174 )
              v175 = *(_QWORD *)&v176[8 * v174 - 6];
            else
              v175 = 0;
          }
          else
          {
            v175 = 0;
          }
        }
      }
      else
      {
        v175 = 0;
      }
      if ( v171 < 2 && v175 )
        v631 = *(_QWORD *)(v175 + 8);
      else
        v631 = 0;
      v621 = *(_DWORD *)(v166 + 8) & 0xF;
      if ( (v170 & 4) != 0 )
      {
        strlen_0(*(const char **)v166);
        v55 = v638;
      }
      v177 = "issisi";
      if ( *v167 )
        v177 = "issisii";
      sqlite3VdbeMultiLoad(v5, 1, v177, (unsigned int)(v169 - v620), *(_QWORD *)v166);
      v162 = v628;
      v163 = (__int16 *)v627;
      goto LABEL_387;
    case 0x26:
      v623[14] = 6;
      sqlite3CodeVerifyNamedSchema(v56, v21);
      v66 = v616;
      v178 = 0;
      if ( *((int *)v616 + 10) <= 0 )
        goto LABEL_1151;
      v179 = v625;
      while ( 1 )
      {
        v180 = 32LL * v178;
        if ( !v179 )
          goto LABEL_394;
        v181 = *(_QWORD *)(v180 + v66[4]);
        if ( v181 )
          break;
LABEL_430:
        if ( ++v178 >= *((_DWORD *)v66 + 10) )
          goto LABEL_1151;
      }
      if ( (unsigned int)sqlite3StrICmp(v179, v181) )
        goto LABEL_429;
LABEL_394:
      v182 = v66[4];
      v183 = *(_QWORD *)(v180 + v182 + 24) + 8LL;
      v184 = *(_DWORD *)(*(_QWORD *)(v180 + v182 + 24) + 12LL);
      if ( v184 )
      {
        do
        {
          v185 = *(_QWORD **)(v183 + 8);
          if ( !v185 )
            break;
          while ( 1 )
          {
            v186 = v185[2];
            if ( !*(_WORD *)(v186 + 54) )
              break;
            v185 = (_QWORD *)*v185;
            if ( !v185 )
              goto LABEL_404;
          }
          --v184;
          v187 = sqlite3MPrintf(v66, "SELECT*FROM\"%w\"", *(_QWORD *)v186);
          if ( v187 )
          {
            v631 = 0;
            sqlite3LockAndPrepare((_DWORD)v66, v187, -1, 0, 0, (__int64)&v631, 0);
            sqlite3_finalize(v631);
            sqlite3DbFreeNN(v66, v187);
          }
          if ( *((_BYTE *)v66 + 103) )
          {
            sqlite3ErrorMsg(v66[44], "out of memory");
            *(_DWORD *)(v66[44] + 24LL) = 7;
          }
          v183 = *(_QWORD *)(v180 + v66[4] + 24) + 8LL;
        }
        while ( v184 );
LABEL_404:
        v5 = v627;
      }
      v188 = *(_QWORD **)(v183 + 8);
      if ( !v188 )
        goto LABEL_429;
      v189 = v617;
LABEL_407:
      v190 = (const char **)v188[2];
      if ( v189 )
      {
        if ( !*v190 )
          goto LABEL_428;
        if ( (unsigned int)sqlite3StrICmp(v189, *v190) )
          goto LABEL_427;
      }
      v191 = *v190;
      if ( !*v190 )
        goto LABEL_426;
      v192 = 7;
      v193 = "sqlite_";
      v194 = *v190;
      do
      {
        --v192;
        if ( !*v194
          || *((_BYTE *)qword_180114680 + *(unsigned __int8 *)v194) != *((_BYTE *)qword_180114680
                                                                       + *(unsigned __int8 *)v193) )
        {
          goto LABEL_416;
        }
        ++v194;
        ++v193;
      }
      while ( v192 > 0 );
      --v192;
LABEL_416:
      if ( v192 >= 0
        && *((unsigned __int8 *)qword_180114680 + *(unsigned __int8 *)v194) != *((unsigned __int8 *)qword_180114680
                                                                               + *(unsigned __int8 *)v193) )
      {
        goto LABEL_426;
      }
      v195 = v191 + 7;
      for ( i5 = "master"; ; ++i5 )
      {
        v197 = *(unsigned __int8 *)i5;
        if ( (unsigned __int8)*v195 == (_DWORD)v197 )
        {
          if ( !*v195 )
          {
            v191 = "sqlite_schema";
            goto LABEL_426;
          }
        }
        else if ( *((unsigned __int8 *)qword_180114680 + (unsigned __int8)*v195) != *((unsigned __int8 *)qword_180114680
                                                                                    + v197) )
        {
          if ( !(unsigned int)sqlite3StrICmp(v191 + 7, "temp_master") )
            v191 = "sqlite_temp_schema";
LABEL_426:
          v66 = v616;
          sqlite3VdbeMultiLoad(v5, 1, "sssiii", *(_QWORD *)(32LL * v178 + v616[4]), (_DWORD)v191);
LABEL_427:
          v189 = v617;
LABEL_428:
          v188 = (_QWORD *)*v188;
          if ( !v188 )
          {
LABEL_429:
            v179 = v625;
            goto LABEL_430;
          }
          goto LABEL_407;
        }
        ++v195;
      }
    case 0x27:
      if ( !v58 )
      {
        v66 = v616;
        returnSingleInt(v5, *((unsigned __int8 *)v616 + 102));
        goto LABEL_1151;
      }
      v141 = *v58;
      if ( (unsigned __int8)(*v58 - 48) <= 2u )
      {
        v142 = v141 - 48;
        goto LABEL_293;
      }
      v143 = v58;
      v144 = "file";
      while ( 2 )
      {
        v145 = *(unsigned __int8 *)v144;
        if ( (unsigned __int8)v141 == (_DWORD)v145 )
        {
          if ( !(_BYTE)v141 )
          {
            v142 = 1;
LABEL_293:
            v150 = *(_QWORD *)v623;
            if ( *(unsigned __int8 *)(*(_QWORD *)v623 + 102LL) != v142 )
            {
              v66 = v616;
              if ( !(unsigned int)invalidateTempStorage(v623) )
                *(_BYTE *)(v150 + 102) = v142;
              goto LABEL_1151;
            }
LABEL_1150:
            v66 = v616;
            goto LABEL_1151;
          }
        }
        else if ( *((unsigned __int8 *)qword_180114680 + (unsigned __int8)v141) != *((unsigned __int8 *)qword_180114680
                                                                                   + v145) )
        {
          v146 = v58;
          for ( i6 = "memory"; ; ++i6 )
          {
            v148 = (unsigned __int8)*v146;
            v149 = *(unsigned __int8 *)i6;
            if ( (_DWORD)v148 == (_DWORD)v149 )
            {
              if ( !*v146 )
              {
                v142 = 2;
                goto LABEL_293;
              }
            }
            else if ( *((unsigned __int8 *)qword_180114680 + v148) != *((unsigned __int8 *)qword_180114680 + v149) )
            {
              v142 = 0;
              goto LABEL_293;
            }
            ++v146;
          }
        }
        LOBYTE(v141) = *++v143;
        ++v144;
        continue;
      }
    case 0x28:
      if ( (_BYTE)word_18013C1B4 )
      {
        v151 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
        if ( v151 )
          ((void (__fastcall *)(__int64))xmmword_18013C230)(v151);
      }
      v123 = v617;
      if ( v617 )
      {
        v66 = v616;
        if ( *v617
          && ((*(unsigned int (__fastcall **)(_QWORD, char *, __int64, int *))(*v616 + 56LL))(*v616, v617, 1, &v621)
           || !v621) )
        {
LABEL_304:
          sqlite3ErrorMsg(v56, "not a writable directory");
        }
        else
        {
          if ( *((_BYTE *)v616 + 102) <= 1u )
            invalidateTempStorage(v56);
          sqlite3_free(sqlite3_temp_directory);
          if ( *v617 )
            sqlite3_temp_directory = (char *)sqlite3_mprintf("%s", v617);
          else
            sqlite3_temp_directory = 0;
        }
      }
      else
      {
        returnSingleText(v5, sqlite3_temp_directory);
        v66 = v616;
      }
      if ( (_BYTE)word_18013C1B4 )
      {
        v152 = ((__int64 (__fastcall *)(__int64))xmmword_18013C220)(11);
        if ( v152 )
          ((void (__fastcall *)(__int64))xmmword_18013C240)(v152);
      }
      goto LABEL_1152;
    case 0x29:
      if ( !v58 || (unsigned int)sqlite3DecOrHexToI64(v58, &v637) )
      {
        v66 = v616;
      }
      else
      {
        v66 = v616;
        if ( v637 >= 0 )
        {
          v610 = v637 & 0x7FFFFFFF;
          if ( ((unsigned int)v637 & 0x7FFFFFFF) > 8 )
            v610 = 8;
          *((_DWORD *)v616 + 45) = v610;
        }
      }
      returnSingleInt(v5, *((int *)v66 + 45));
      goto LABEL_1151;
    case 0x2A:
      v584 = 0;
      if ( v58 )
      {
        v621 = 0;
        sqlite3GetInt32(v58, &v621);
        v66 = v616;
        sqlite3_wal_autocheckpoint(v616, (unsigned int)v621);
      }
      else
      {
        v66 = v616;
      }
      if ( (__int64 (__fastcall *)())v66[45] == sqlite3WalDefaultHook )
        v584 = *((_DWORD *)v66 + 92);
      returnSingleInt(v5, v584);
      goto LABEL_1151;
    case 0x2B:
      if ( *(_QWORD *)a3 )
        v26 = v618;
      if ( v58 )
      {
        if ( (unsigned int)sqlite3StrICmp(v58, "full") )
        {
          if ( (unsigned int)sqlite3StrICmp(v581, "restart") )
          {
            v32 = (unsigned int)sqlite3StrICmp(v583, "truncate") == 0;
            v582 = 0;
            if ( v32 )
              v582 = 3;
          }
          else
          {
            v582 = 2;
          }
        }
        else
        {
          v582 = 1;
        }
      }
      else
      {
        v582 = 0;
      }
      v623[14] = 3;
      sqlite3VdbeAddOp3((_DWORD)v5, 3, v26, v582, 1);
      sqlite3VdbeAddOp2(v5, 84, 1, 3);
      goto LABEL_1150;
    default:
      if ( v58 )
      {
        v621 = 0;
        sqlite3GetInt32(v58, &v621);
        v611 = v621;
        v66 = v616;
        if ( v621 <= 0 )
        {
          sqlite3_busy_handler(v616, 0, 0);
        }
        else
        {
          sqlite3_busy_handler(v616, sqliteDefaultBusyCallback, v616);
          *((_DWORD *)v616 + 187) = v611;
        }
      }
      else
      {
        v66 = v616;
      }
      returnSingleInt(v5, *((int *)v66 + 187));
      goto LABEL_1151;
  }
}

```

## disassembly

```asm
0x18008c9f0  push    rbp
0x18008c9f2  push    rbx
0x18008c9f3  push    rsi
0x18008c9f4  push    rdi
0x18008c9f5  push    r13
0x18008c9f7  push    r14
0x18008c9f9  push    r15
0x18008c9fb  lea     rbp, [rsp-50h]
0x18008ca00  sub     rsp, 150h
0x18008ca07  mov     rax, cs:__security_cookie
0x18008ca0e  xor     rax, rsp
0x18008ca11  mov     [rbp+80h+var_50], rax
0x18008ca15  mov     rbx, [rcx+10h]
0x18008ca19  mov     r15, r9
0x18008ca1c  mov     rsi, [rcx]
0x18008ca1f  mov     r14, r8
0x18008ca22  mov     [rbp+80h+var_100], rcx
0x18008ca26  mov     rdi, rdx
0x18008ca29  mov     [rsp+180h+var_120], rsi
0x18008ca2e  mov     r13, rcx
0x18008ca31  mov     [rbp+80h+var_E0], rbx
0x18008ca35  test    rbx, rbx
0x18008ca38  jnz     short loc_18008CA62
0x18008ca3a  cmp     [rcx+0A8h], rbx
0x18008ca41  jnz     short loc_18008CA4D
0x18008ca43  test    byte ptr [rsi+60h], 8
0x18008ca47  jnz     short loc_18008CA4D
0x18008ca49  mov     byte ptr [rcx+23h], 1
0x18008ca4d  call    sqlite3VdbeCreate
0x18008ca52  mov     [rbp+80h+var_E0], rax
0x18008ca56  mov     rbx, rax
0x18008ca59  test    rax, rax
0x18008ca5c  jz      loc_180091C39
0x18008ca62  movsxd  rcx, dword ptr [rbx+90h]
0x18008ca69  mov     [rsp+180h+var_38], r12
0x18008ca71  xor     r12d, r12d
0x18008ca74  mov     [rbp+80h+var_C8], r12
0x18008ca78  cmp     [rbx+94h], ecx
0x18008ca7e  jg      short loc_18008CA9F
0x18008ca80  mov     eax, 1
0x18008ca85  mov     dword ptr [rsp+180h+var_160], r12d
0x18008ca8a  mov     r9d, eax
0x18008ca8d  mov     r8d, eax
0x18008ca90  mov     edx, 0A6h
0x18008ca95  mov     rcx, rbx
0x18008ca98  call    growOp3
0x18008ca9d  jmp     short loc_18008CACD
0x18008ca9f  lea     eax, [rcx+1]
0x18008caa2  mov     edx, 1
0x18008caa7  mov     [rbx+90h], eax
0x18008caad  lea     rcx, [rcx+rcx*2]
0x18008cab1  mov     rax, [rbx+88h]
0x18008cab8  mov     dword ptr [rax+rcx*8], 0A6h
0x18008cabf  mov     [rax+rcx*8+4], edx
0x18008cac3  mov     [rax+rcx*8+8], rdx
0x18008cac8  mov     [rax+rcx*8+10h], r12
0x18008cacd  mov     rax, [r13+0]
0x18008cad1  mov     dword ptr [r13+38h], 2
0x18008cad9  cmp     dword ptr [r14+8], 0
0x18008cade  jbe     short loc_18008CB2C
0x18008cae0  cmp     byte ptr [rax+0C5h], 0
0x18008cae7  jz      short loc_18008CAFD
0x18008cae9  lea     rdx, aCorruptDatabas; "corrupt database"
0x18008caf0  mov     rcx, r13
0x18008caf3  call    sqlite3ErrorMsg
0x18008caf8  jmp     loc_180091C31
0x18008cafd  mov     rdx, rdi
0x18008cb00  mov     rcx, rax
0x18008cb03  call    sqlite3FindDb
0x18008cb08  mov     [rsp+180h+var_110], eax
0x18008cb0c  test    eax, eax
0x18008cb0e  jns     short loc_18008CB27
0x18008cb10  mov     r8, rdi
0x18008cb13  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x18008cb1a  mov     rcx, r13
0x18008cb1d  call    sqlite3ErrorMsg
0x18008cb22  jmp     loc_180091C31
0x18008cb27  mov     rdi, r14
0x18008cb2a  jmp     short loc_18008CB37
0x18008cb2c  movzx   eax, byte ptr [rax+0C4h]
0x18008cb33  mov     [rsp+180h+var_110], eax
0x18008cb37  test    eax, eax
0x18008cb39  js      loc_180091C31
0x18008cb3f  mov     rsi, [rsi+20h]
0x18008cb43  cmp     eax, 1
0x18008cb46  jnz     short loc_18008CB58
0x18008cb48  mov     rcx, r13
0x18008cb4b  call    sqlite3OpenTempDatabase
0x18008cb50  test    eax, eax
0x18008cb52  jnz     loc_180091C31
0x18008cb58  mov     rdx, rdi
0x18008cb5b  mov     rdi, [rsp+180h+var_120]
0x18008cb60  mov     rcx, rdi
0x18008cb63  call    sqlite3NameFromToken
0x18008cb68  mov     [rbp+80h+var_98], rax
0x18008cb6c  test    rax, rax
0x18008cb6f  jz      loc_180091C31
0x18008cb75  movsxd  rax, [rsp+180h+var_110]
0x18008cb7a  mov     rcx, rdi
0x18008cb7d  shl     rax, 5
0x18008cb81  add     rsi, rax
0x18008cb84  cmp     [rbp+80h+arg_20], 0
0x18008cb8b  jz      short loc_18008CB9E
0x18008cb8d  mov     r8, r15
0x18008cb90  lea     rdx, aT; "-%T"
0x18008cb97  call    sqlite3MPrintf
0x18008cb9c  jmp     short loc_18008CBA6
0x18008cb9e  mov     rdx, r15
0x18008cba1  call    sqlite3NameFromToken
0x18008cba6  cmp     dword ptr [r14+8], 0
0x18008cbab  mov     r15, rax
0x18008cbae  mov     [rsp+180h+var_118], rax
0x18008cbb3  jbe     short loc_18008CBBA
0x18008cbb5  mov     r13, [rsi]
0x18008cbb8  jmp     short loc_18008CBBD
0x18008cbba  mov     r13, r12
0x18008cbbd  mov     rdi, [rbp+80h+var_100]
0x18008cbc1  mov     r9, r15
0x18008cbc4  mov     r8, [rbp+80h+var_98]
0x18008cbc8  mov     rcx, rdi
0x18008cbcb  mov     edx, 13h
0x18008cbd0  mov     [rbp+80h+var_F0], r13
0x18008cbd4  mov     [rsp+180h+var_160], r13
0x18008cbd9  call    sqlite3AuthCheck
0x18008cbde  test    eax, eax
0x18008cbe0  jnz     loc_1800919E6
0x18008cbe6  mov     rax, [rbp+80h+var_98]
0x18008cbea  mov     [rbp+80h+var_68], rax
0x18008cbee  mov     rax, [rsp+180h+var_120]
0x18008cbf3  mov     [rbp+80h+var_60], r15
0x18008cbf7  mov     r15d, 1
0x18008cbfd  mov     [rbp+80h+Str], r12
0x18008cc01  mov     [rbp+80h+var_58], r12
0x18008cc05  mov     rcx, [rax+18h]
0x18008cc09  mov     [rax+298h], r12d
0x18008cc10  test    rcx, rcx
0x18008cc13  jz      short loc_18008CC26
0x18008cc15  mov     rax, qword ptr cs:xmmword_18013C230
0x18008cc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cc21  mov     rax, [rsp+180h+var_120]
0x18008cc26  mov     r12d, 0Ch
0x18008cc2c  test    r13, r13
0x18008cc2f  jz      short loc_18008CC46
0x18008cc31  mov     rdx, r13
0x18008cc34  mov     rcx, rax
0x18008cc37  call    sqlite3FindDbName
0x18008cc3c  test    eax, eax
0x18008cc3e  js      loc_18008CCDC
0x18008cc44  jmp     short loc_18008CC48
0x18008cc46  xor     eax, eax
0x18008cc48  lfence
0x18008cc4b  mov     ecx, eax
0x18008cc4d  mov     rax, [rsp+180h+var_120]
0x18008cc52  shl     rcx, 5
0x18008cc56  mov     rax, [rax+20h]
0x18008cc5a  mov     rdi, [rcx+rax+8]
0x18008cc5f  test    rdi, rdi
0x18008cc62  jz      short loc_18008CCD8
0x18008cc64  cmp     byte ptr [rdi+11h], 0
0x18008cc68  jz      short loc_18008CC7B
0x18008cc6a  inc     dword ptr [rdi+14h]
0x18008cc6d  cmp     byte ptr [rdi+12h], 0
0x18008cc71  jnz     short loc_18008CC7B
0x18008cc73  mov     rcx, rdi
0x18008cc76  call    btreeLockCarefully
0x18008cc7b  mov     rax, [rdi+8]
0x18008cc7f  mov     rcx, [rax]
0x18008cc82  mov     rax, [rsp+180h+var_120]
0x18008cc87  mov     rcx, [rcx+48h]
0x18008cc8b  mov     r13d, [rax+298h]
0x18008cc92  mov     rax, [rcx]
0x18008cc95  test    rax, rax
0x18008cc98  jnz     short loc_18008CC9F
0x18008cc9a  mov     r15d, r12d
0x18008cc9d  jmp     short loc_18008CCB4
0x18008cc9f  mov     rax, [rax+50h]
0x18008cca3  lea     r8, [rbp+80h+Str]
0x18008cca7  mov     edx, 0Eh
0x18008ccac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ccb1  mov     r15d, eax
0x18008ccb4  mov     rax, [rsp+180h+var_120]
0x18008ccb9  mov     [rax+298h], r13d
0x18008ccc0  cmp     byte ptr [rdi+11h], 0
0x18008ccc4  jz      short loc_18008CD45
0x18008ccc6  sub     dword ptr [rdi+14h], 1
0x18008ccca  jnz     short loc_18008CD45
0x18008cccc  mov     rcx, rdi
0x18008cccf  call    unlockBtreeMutex
0x18008ccd4  mov     r13, [rbp+80h+var_F0]
0x18008ccd8  mov     rdi, [rbp+80h+var_100]
0x18008ccdc  mov     rax, [rsp+180h+var_120]
0x18008cce1  mov     rcx, [rax+18h]
0x18008cce5  test    rcx, rcx
0x18008cce8  jz      short loc_18008CCF6
0x18008ccea  mov     rax, qword ptr cs:xmmword_18013C240
0x18008ccf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ccf6  test    r15d, r15d
0x18008ccf9  jnz     loc_18008CF15
0x18008ccff  mov     r12d, 1
0x18008cd05  mov     rcx, rbx
0x18008cd08  mov     edx, r12d
0x18008cd0b  call    sqlite3VdbeSetNumCols
0x18008cd10  mov     rax, [rbx]
0x18008cd13  cmp     [rax+67h], r15b
0x18008cd17  jnz     loc_18008CE17
0x18008cd1d  mov     rdi, [rbp+80h+Str]
0x18008cd21  mov     rsi, [rbx+98h]
0x18008cd28  test    rdi, rdi
0x18008cd2b  jnz     short loc_18008CD59
0x18008cd2d  mov     eax, 9000h
0x18008cd32  test    [rsi+14h], ax
0x18008cd36  jz      short loc_18008CD4F
0x18008cd38  mov     rcx, rsi
0x18008cd3b  call    vdbeMemClearExternAndSetNull
0x18008cd40  jmp     loc_18008CE17
0x18008cd45  mov     r13, [rbp+80h+var_F0]
0x18008cd49  mov     rdi, [rbp+80h+var_100]
0x18008cd4d  jmp     short loc_18008CCE1
0x18008cd4f  mov     [rsi+14h], r12w
0x18008cd54  jmp     loc_18008CE17
0x18008cd59  mov     rax, [rsi+18h]
0x18008cd5d  test    rax, rax
0x18008cd60  jz      short loc_18008CD6B
0x18008cd62  mov     r15d, [rax+88h]
0x18008cd69  jmp     short loc_18008CD71
0x18008cd6b  mov     r15d, 3B9ACA00h
0x18008cd71  mov     rcx, rdi; Str
0x18008cd74  call    strlen_0
0x18008cd79  movsxd  rcx, r15d
0x18008cd7c  mov     r14, rax
0x18008cd7f  cmp     rax, rcx
0x18008cd82  jle     short loc_18008CDBF
0x18008cd84  mov     eax, 9000h
0x18008cd89  test    [rsi+14h], ax
0x18008cd8d  jz      short loc_18008CD99
0x18008cd8f  mov     rcx, rsi
0x18008cd92  call    vdbeMemClearExternAndSetNull
0x18008cd97  jmp     short loc_18008CD9E
0x18008cd99  mov     [rsi+14h], r12w
0x18008cd9e  mov     rax, [rsi+18h]
0x18008cda2  test    rax, rax
0x18008cda5  jz      short loc_18008CE17
0x18008cda7  mov     rax, [rax+160h]
0x18008cdae  test    rax, rax
0x18008cdb1  jz      short loc_18008CE17
0x18008cdb3  inc     dword ptr [rax+30h]
0x18008cdb6  mov     dword ptr [rax+18h], 12h
0x18008cdbd  jmp     short loc_18008CE17
0x18008cdbf  lea     r15, [rax+1]
0x18008cdc3  mov     edx, 20h ; ' '
0x18008cdc8  cmp     r15, rdx
0x18008cdcb  cmovg   edx, r15d
0x18008cdcf  cmp     [rsi+20h], edx
0x18008cdd2  jge     short loc_18008CDE5
0x18008cdd4  xor     r8d, r8d
0x18008cdd7  mov     rcx, rsi
0x18008cdda  call    sqlite3VdbeMemGrow
0x18008cddf  test    eax, eax
0x18008cde1  jnz     short loc_18008CE17
0x18008cde3  jmp     short loc_18008CDF2
0x18008cde5  mov     rax, [rsi+28h]
0x18008cde9  and     word ptr [rsi+14h], 2Dh
0x18008cdee  mov     [rsi+8], rax
0x18008cdf2  mov     rcx, [rsi+8]; void *
0x18008cdf6  mov     r8, r15; Size
0x18008cdf9  mov     rdx, rdi; Src
0x18008cdfc  call    memcpy_0
0x18008ce01  mov     edi, 7FFFFFFFh
0x18008ce06  mov     word ptr [rsi+14h], 202h
0x18008ce0c  and     r14d, edi
0x18008ce0f  mov     [rsi+16h], r12b
0x18008ce13  mov     [rsi+10h], r14d
0x18008ce17  mov     r8, [rbp+80h+Str]
0x18008ce1b  test    r8, r8
0x18008ce1e  jz      short loc_18008CE83
0x18008ce20  mov     edx, r12d
0x18008ce23  mov     rcx, rbx
0x18008ce26  call    sqlite3VdbeLoadString
0x18008ce2b  movsxd  rcx, dword ptr [rbx+90h]
0x18008ce32  cmp     [rbx+94h], ecx
0x18008ce38  jg      short loc_18008CE57
0x18008ce3a  mov     r9d, r12d
0x18008ce3d  mov     dword ptr [rsp+180h+var_160], 0
0x18008ce45  mov     r8d, r12d
0x18008ce48  mov     edx, 54h ; 'T'
0x18008ce4d  mov     rcx, rbx
0x18008ce50  call    growOp3
0x18008ce55  jmp     short loc_18008CE83
0x18008ce57  lea     eax, [rcx+1]
0x18008ce5a  xor     edx, edx
0x18008ce5c  mov     [rbx+90h], eax
0x18008ce62  lea     rcx, [rcx+rcx*2]
0x18008ce66  mov     rax, [rbx+88h]
0x18008ce6d  mov     dword ptr [rax+rcx*8], 54h ; 'T'
0x18008ce74  mov     [rax+rcx*8+4], r12d
0x18008ce79  mov     [rax+rcx*8+8], r12
0x18008ce7e  mov     [rax+rcx*8+10h], rdx
0x18008ce83  mov     rbx, [rbp+80h+Str]
0x18008ce87  test    rbx, rbx
0x18008ce8a  jz      loc_1800919E6
  ... truncated ...
```
