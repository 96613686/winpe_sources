# ParquetWriterOutputter::SetupParquetSchema(void)

- ea: `0x180016ad0`
- end: `0x180018adc`
- name: `?SetupParquetSchema@ParquetWriterOutputter@@AEAAXXZ`
- size: `8204`
- prototype: `void __fastcall(ParquetWriterOutputter *__hidden this)`
- caller_count: `1`
- callee_count: `53`
- tags: `registry_config, installer_update`

## callers

- `0x180018bf0`

## callees

- `0x18000f260`
- `0x180010640`
- `0x1800107b0`
- `0x180010860`
- `0x180010a60`
- `0x180010be0`
- `0x180010c60`
- `0x180010d50`
- `0x180010f40`
- `0x180010fd0`
- `0x1800111b0`
- `0x180011650`
- `0x1800116c0`
- `0x1800118b0`
- `0x1800119a0`
- `0x180011af0`
- `0x180011d80`
- `0x180011ee0`
- `0x180012130`
- `0x180012190`
- `0x180012620`
- `0x1800129b0`
- `0x180012b50`
- `0x180012c10`
- `0x180012f20`
- `0x180012f80`
- `0x1800158a0`
- `0x180016ad0`
- `0x18001a8d0`
- `0x18001ac30`
- `0x18001ac80`
- `0x18001b0e0`
- `0x18001b180`
- `0x180028850`
- `0x180028870`
- `0x180029370`
- `0x18002ade0`
- `0x18002ae00`
- `0x18002ae20`
- `0x18002ae40`
- `0x18002cc50`
- `0x18002f530`
- `0x18002f890`
- `0x1802f0fb0`
- `0x180305670`
- `0x180305b20`
- `0x18030c190`
- `0x18030c3f0`
- `0x18030c414`
- `0x18030c490`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
void __fastcall ParquetWriterOutputter::SetupParquetSchema(ParquetWriterOutputter *this)
{
  __int64 v2; // r14
  unsigned __int64 v3; // rdi
  __int64 v4; // rax
  bool v5; // cf
  unsigned __int64 v6; // rax
  unsigned __int64 *v7; // rax
  _QWORD *v8; // rbx
  unsigned int v9; // r12d
  _QWORD *v10; // r13
  _QWORD *v11; // rdx
  char *v12; // rcx
  int v13; // edi
  int v14; // eax
  __int64 v15; // rsi
  _DWORD *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // r13
  __int64 v20; // rsi
  ColumnChunkBuffer *v21; // rax
  ColumnChunkBuffer *v22; // rbx
  __int64 *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  std::_Ref_count_base *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r13
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  __int64 v30; // r13
  __int64 v31; // rsi
  ColumnChunkBuffer *v32; // rax
  ColumnChunkBuffer *v33; // rbx
  __int64 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  std::_Ref_count_base *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r13
  __int64 v40; // rsi
  ColumnChunkBuffer *v41; // rax
  ColumnChunkBuffer *v42; // rbx
  __int64 v43; // r8
  __int64 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  std::_Ref_count_base *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r13
  __int64 v50; // rsi
  ColumnChunkBuffer *v51; // rax
  ColumnChunkBuffer *v52; // rbx
  __int64 v53; // r8
  __int64 *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rdx
  std::_Ref_count_base *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // r13
  __int64 v60; // rsi
  ColumnChunkBuffer *v61; // rax
  ColumnChunkBuffer *v62; // rbx
  __int64 v63; // r8
  __int64 *v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rdx
  std::_Ref_count_base *v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // r13
  __int64 v70; // rbx
  ColumnChunkBuffer *v71; // rax
  ColumnChunkBuffer *v72; // rsi
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // r13
  __int64 v76; // rbx
  ColumnChunkBuffer *v77; // rax
  ColumnChunkBuffer *v78; // rsi
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 v81; // r13
  __int64 v82; // rbx
  ColumnChunkBuffer *v83; // rax
  ColumnChunkBuffer *v84; // rsi
  __int64 v85; // rax
  __int64 v86; // rcx
  __int64 v87; // r13
  __int64 v88; // rbx
  std::_Ref_count_base *v89; // rax
  std::_Ref_count_base *v90; // rsi
  __int64 v91; // rax
  int v92; // r12d
  __int64 v93; // rcx
  __int64 v94; // r13
  __int64 v95; // rbx
  std::_Ref_count_base *v96; // rax
  std::_Ref_count_base *v97; // rsi
  __int64 v98; // rdx
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // r13
  __int64 v102; // rbx
  ColumnChunkBuffer *v103; // rax
  ColumnChunkBuffer *v104; // rsi
  int v105; // edx
  __int64 v106; // rax
  __int64 v107; // rcx
  __int64 v108; // r13
  __int64 v109; // rbx
  ColumnChunkBuffer *v110; // rax
  ColumnChunkBuffer *v111; // rsi
  int v112; // edx
  __int64 v113; // rax
  __int64 v114; // rcx
  __int64 v115; // r13
  __int64 v116; // rbx
  std::_Ref_count_base *v117; // rax
  std::_Ref_count_base *v118; // rsi
  __int64 v119; // rax
  int v120; // r12d
  __int64 v121; // rcx
  __int64 *v122; // rax
  _QWORD *v123; // rcx
  _QWORD *v124; // rcx
  __int64 v125; // rdx
  __int64 v126; // r13
  __int64 v127; // rbx
  ColumnChunkBuffer *v128; // rax
  ColumnChunkBuffer *v129; // rsi
  __int64 v130; // rax
  __int64 v131; // rcx
  __int64 v132; // r13
  __int64 v133; // rbx
  ColumnChunkBuffer *v134; // rax
  ColumnChunkBuffer *v135; // rsi
  __int64 v136; // rax
  __int64 v137; // rcx
  __int64 v138; // r13
  __int64 v139; // rbx
  ColumnChunkBuffer *v140; // rax
  ColumnChunkBuffer *v141; // rsi
  __int64 v142; // rax
  __int64 v143; // rcx
  ColumnChunkBuffer *v144; // rax
  ColumnChunkBuffer *v145; // rsi
  __int64 v146; // rax
  __int64 v147; // rbx
  __int64 v148; // rcx
  __int64 v149; // rbx
  __int64 v150; // r13
  __int64 v151; // rbx
  ColumnChunkBuffer *v152; // rax
  ColumnChunkBuffer *v153; // rsi
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rbx
  __int64 v157; // rsi
  ColumnChunkBuffer *v158; // rax
  ColumnChunkBuffer *v159; // r13
  __int64 v160; // rax
  __int64 v161; // rax
  ColumnChunkBuffer *v162; // rax
  ColumnChunkBuffer *v163; // r13
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 v166; // r13
  __int64 v167; // rbx
  ColumnChunkBuffer *v168; // rax
  ColumnChunkBuffer *v169; // rsi
  __int64 v170; // rax
  __int64 v171; // rax
  unsigned __int64 v172; // r13
  __int64 v173; // rbx
  ColumnChunkBuffer *v174; // rax
  ColumnChunkBuffer *v175; // rsi
  __int64 v176; // rax
  __int64 v177; // rax
  ColumnChunkBuffer *v178; // rax
  ColumnChunkBuffer *v179; // rsi
  __int64 v180; // rax
  __int64 v181; // rax
  __int64 v182; // rdx
  unsigned __int8 v183; // r13
  int v184; // ecx
  int v185; // ecx
  int v186; // ecx
  wchar_t **v187; // r13
  __int64 v188; // rsi
  ColumnChunkBuffer *v189; // rax
  ColumnChunkBuffer *v190; // rbx
  __int64 v191; // rbx
  __int64 v192; // rax
  __int64 v193; // rbx
  char *v194; // rax
  char *v195; // rsi
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rbx
  char *v199; // rax
  char *v200; // rsi
  __int64 v201; // rax
  __int64 v202; // rax
  wchar_t **v203; // r13
  __int64 v204; // rsi
  ColumnChunkBuffer *v205; // rax
  ColumnChunkBuffer *v206; // rbx
  __int64 v207; // rbx
  __int64 v208; // rax
  __int64 v209; // r13
  __int64 v210; // rbx
  char *v211; // rax
  char *v212; // rsi
  __int64 v213; // rax
  __int64 v214; // rax
  __int64 v215; // r13
  __int64 v216; // rbx
  _QWORD *v217; // rax
  _QWORD *v218; // rsi
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // rcx
  __int64 v222; // rcx
  __int64 v223; // rsi
  BOOL v224; // r13d
  void *v225; // rax
  int v226; // ebx
  int v227; // eax
  __int64 v228; // rax
  struct Node *v229; // rax
  struct Node *v230; // rbx
  std::_Ref_count_base *v231; // rbx
  __int64 v232; // rax
  char *v233; // rax
  __int64 v234; // rax
  __int64 v235; // rax
  unsigned __int8 v236; // [rsp+48h] [rbp-C0h]
  __int64 v237; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v238; // [rsp+58h] [rbp-B0h] BYREF
  ColumnChunkBuffer *v239; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v240; // [rsp+70h] [rbp-98h] BYREF
  __int64 v241; // [rsp+80h] [rbp-88h]
  std::_Ref_count_base *v242; // [rsp+88h] [rbp-80h] BYREF
  ColumnChunkBuffer *v243; // [rsp+90h] [rbp-78h] BYREF
  ColumnChunkBuffer *v244; // [rsp+98h] [rbp-70h] BYREF
  ColumnChunkBuffer *v245; // [rsp+A0h] [rbp-68h] BYREF
  ColumnChunkBuffer *v246; // [rsp+A8h] [rbp-60h] BYREF
  ColumnChunkBuffer *v247; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v248; // [rsp+B8h] [rbp-50h] BYREF
  char *v249; // [rsp+C0h] [rbp-48h] BYREF
  char *v250; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v251; // [rsp+D0h] [rbp-38h] BYREF
  char *v252; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD *v253; // [rsp+E0h] [rbp-28h] BYREF
  std::_Ref_count_base *v254; // [rsp+E8h] [rbp-20h]
  __int64 v255; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v256; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v257; // [rsp+100h] [rbp-8h] BYREF
  __int64 v258; // [rsp+108h] [rbp+0h] BYREF
  __int64 v259; // [rsp+110h] [rbp+8h] BYREF
  __int64 v260; // [rsp+118h] [rbp+10h] BYREF
  __int64 v261; // [rsp+120h] [rbp+18h] BYREF
  __int64 v262; // [rsp+128h] [rbp+20h] BYREF
  char v263[8]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v264; // [rsp+138h] [rbp+30h] BYREF
  __int64 v265; // [rsp+140h] [rbp+38h] BYREF
  __int64 v266; // [rsp+148h] [rbp+40h] BYREF
  __int64 v267; // [rsp+150h] [rbp+48h] BYREF
  std::_Ref_count_base *v268; // [rsp+158h] [rbp+50h]
  __int64 v269; // [rsp+160h] [rbp+58h] BYREF
  std::_Ref_count_base *v270; // [rsp+168h] [rbp+60h]
  _BYTE v271[16]; // [rsp+170h] [rbp+68h] BYREF
  __m128i si128; // [rsp+180h] [rbp+78h]
  ColumnChunkBuffer *v273; // [rsp+190h] [rbp+88h]
  __int64 v274; // [rsp+198h] [rbp+90h]
  ColumnChunkBuffer *v275; // [rsp+1A0h] [rbp+98h]
  __int64 v276; // [rsp+1A8h] [rbp+A0h]
  ColumnChunkBuffer *v277; // [rsp+1B0h] [rbp+A8h]
  __int64 v278; // [rsp+1B8h] [rbp+B0h]
  ColumnChunkBuffer *v279; // [rsp+1C0h] [rbp+B8h]
  __int64 v280; // [rsp+1C8h] [rbp+C0h]
  ColumnChunkBuffer *v281; // [rsp+1D0h] [rbp+C8h]
  __int64 v282; // [rsp+1D8h] [rbp+D0h]
  ColumnChunkBuffer *v283; // [rsp+1E0h] [rbp+D8h]
  ColumnChunkBuffer *v284; // [rsp+1E8h] [rbp+E0h]
  ColumnChunkBuffer *v285; // [rsp+1F0h] [rbp+E8h]
  ColumnChunkBuffer *v286; // [rsp+1F8h] [rbp+F0h]
  ColumnChunkBuffer *v287; // [rsp+200h] [rbp+F8h]
  ColumnChunkBuffer *v288; // [rsp+208h] [rbp+100h]
  ColumnChunkBuffer *v289; // [rsp+210h] [rbp+108h]
  ColumnChunkBuffer *v290; // [rsp+218h] [rbp+110h]
  ColumnChunkBuffer *v291; // [rsp+220h] [rbp+118h]
  ColumnChunkBuffer *v292; // [rsp+228h] [rbp+120h]
  ColumnChunkBuffer *v293; // [rsp+230h] [rbp+128h]
  ColumnChunkBuffer *v294; // [rsp+238h] [rbp+130h]
  ColumnChunkBuffer *v295; // [rsp+240h] [rbp+138h]
  ColumnChunkBuffer *v296; // [rsp+248h] [rbp+140h]
  ColumnChunkBuffer *v297; // [rsp+250h] [rbp+148h]
  ColumnChunkBuffer *v298; // [rsp+258h] [rbp+150h]
  char *v299; // [rsp+260h] [rbp+158h]
  char *v300; // [rsp+268h] [rbp+160h]
  ColumnChunkBuffer *v301; // [rsp+270h] [rbp+168h]
  char *v302; // [rsp+278h] [rbp+170h]
  _QWORD *v303; // [rsp+280h] [rbp+178h]
  char v304[8]; // [rsp+288h] [rbp+180h] BYREF
  std::_Ref_count_base *v305; // [rsp+290h] [rbp+188h]
  char v306[8]; // [rsp+298h] [rbp+190h] BYREF
  std::_Ref_count_base *v307; // [rsp+2A0h] [rbp+198h]
  char v308[8]; // [rsp+2A8h] [rbp+1A0h] BYREF
  std::_Ref_count_base *v309; // [rsp+2B0h] [rbp+1A8h]
  char v310[8]; // [rsp+2B8h] [rbp+1B0h] BYREF
  std::_Ref_count_base *v311; // [rsp+2C0h] [rbp+1B8h]
  char v312[8]; // [rsp+2C8h] [rbp+1C0h] BYREF
  std::_Ref_count_base *v313; // [rsp+2D0h] [rbp+1C8h]
  char v314[8]; // [rsp+2D8h] [rbp+1D0h] BYREF
  std::_Ref_count_base *v315; // [rsp+2E0h] [rbp+1D8h]
  char v316[8]; // [rsp+2E8h] [rbp+1E0h] BYREF
  std::_Ref_count_base *v317; // [rsp+2F0h] [rbp+1E8h]
  char v318[8]; // [rsp+2F8h] [rbp+1F0h] BYREF
  std::_Ref_count_base *v319; // [rsp+300h] [rbp+1F8h]
  char v320[8]; // [rsp+308h] [rbp+200h] BYREF
  std::_Ref_count_base *v321; // [rsp+310h] [rbp+208h]
  char v322[8]; // [rsp+318h] [rbp+210h] BYREF
  std::_Ref_count_base *v323; // [rsp+320h] [rbp+218h]
  char v324; // [rsp+328h] [rbp+220h] BYREF
  std::_Ref_count_base *v325; // [rsp+330h] [rbp+228h]
  char v326; // [rsp+338h] [rbp+230h] BYREF
  std::_Ref_count_base *v327; // [rsp+340h] [rbp+238h]
  char v328[8]; // [rsp+348h] [rbp+240h] BYREF
  std::_Ref_count_base *v329; // [rsp+350h] [rbp+248h]
  char v330[8]; // [rsp+358h] [rbp+250h] BYREF
  std::_Ref_count_base *v331; // [rsp+360h] [rbp+258h]
  char v332[8]; // [rsp+368h] [rbp+260h] BYREF
  std::_Ref_count_base *v333; // [rsp+370h] [rbp+268h]
  char v334[8]; // [rsp+378h] [rbp+270h] BYREF
  std::_Ref_count_base *v335; // [rsp+380h] [rbp+278h]
  char v336[8]; // [rsp+388h] [rbp+280h] BYREF
  std::_Ref_count_base *v337; // [rsp+390h] [rbp+288h]
  char v338[8]; // [rsp+398h] [rbp+290h] BYREF
  std::_Ref_count_base *v339; // [rsp+3A0h] [rbp+298h]
  char v340[8]; // [rsp+3A8h] [rbp+2A0h] BYREF
  std::_Ref_count_base *v341; // [rsp+3B0h] [rbp+2A8h]
  char v342[8]; // [rsp+3B8h] [rbp+2B0h] BYREF
  std::_Ref_count_base *v343; // [rsp+3C0h] [rbp+2B8h]
  char v344[8]; // [rsp+3C8h] [rbp+2C0h] BYREF
  std::_Ref_count_base *v345; // [rsp+3D0h] [rbp+2C8h]
  char v346[8]; // [rsp+3D8h] [rbp+2D0h] BYREF
  std::_Ref_count_base *v347; // [rsp+3E0h] [rbp+2D8h]
  char v348[8]; // [rsp+3E8h] [rbp+2E0h] BYREF
  std::_Ref_count_base *v349; // [rsp+3F0h] [rbp+2E8h]
  char v350[8]; // [rsp+3F8h] [rbp+2F0h] BYREF
  std::_Ref_count_base *v351; // [rsp+400h] [rbp+2F8h]
  char v352[8]; // [rsp+408h] [rbp+300h] BYREF
  std::_Ref_count_base *v353; // [rsp+410h] [rbp+308h]
  char v354[8]; // [rsp+418h] [rbp+310h] BYREF
  std::_Ref_count_base *v355; // [rsp+420h] [rbp+318h]
  char v356[8]; // [rsp+428h] [rbp+320h] BYREF
  std::_Ref_count_base *v357; // [rsp+430h] [rbp+328h]
  char v358[16]; // [rsp+438h] [rbp+330h] BYREF
  char v359[16]; // [rsp+448h] [rbp+340h] BYREF
  __int64 v360; // [rsp+458h] [rbp+350h]
  _BYTE pExceptionObject[24]; // [rsp+460h] [rbp+358h] BYREF
  _BYTE v362[32]; // [rsp+478h] [rbp+370h] BYREF
  char v363[32]; // [rsp+498h] [rbp+390h] BYREF
  char v364[32]; // [rsp+4B8h] [rbp+3B0h] BYREF
  char v365[32]; // [rsp+4D8h] [rbp+3D0h] BYREF
  char v366[32]; // [rsp+4F8h] [rbp+3F0h] BYREF
  int v367; // [rsp+518h] [rbp+410h] BYREF
  __int64 v368; // [rsp+520h] [rbp+418h] BYREF
  __int64 v369; // [rsp+528h] [rbp+420h] BYREF
  __int128 v370; // [rsp+530h] [rbp+428h]
  _BYTE v371[16]; // [rsp+540h] [rbp+438h] BYREF
  __int64 v372; // [rsp+550h] [rbp+448h]
  __int64 v373; // [rsp+558h] [rbp+450h]

  v360 = -2;
  v2 = 0;
  _CheckForDebuggerJustMyCode(&byte_1804EA0FE);
  v3 = *((int *)this + 10);
  v4 = 8 * v3;
  if ( !is_mul_ok(v3, 8u) )
    v4 = -1;
  v5 = __CFADD__(v4, 8);
  v6 = v4 + 8;
  if ( v5 )
    v6 = -1;
  v7 = (unsigned __int64 *)operator new[](v6);
  if ( v7 )
  {
    *v7 = v3;
    v8 = v7 + 1;
    `eh vector constructor iterator'(
      v7 + 1,
      8u,
      v3,
      std::unique_ptr<__int64 [0]>::unique_ptr<__int64 [0]>,
      std::unique_ptr<ParquetFileWrite>::~unique_ptr<ParquetFileWrite>);
  }
  else
  {
    v8 = 0;
  }
  v9 = 1;
  v10 = (_QWORD *)((char *)this + 112);
  if ( (__int64 *)((char *)this + 112) == &v237 )
  {
    if ( !v8 )
      goto LABEL_14;
    v11 = v8;
    v12 = (char *)&v237;
  }
  else
  {
    v11 = (_QWORD *)*v10;
    *v10 = v8;
    if ( !v11 )
      goto LABEL_14;
    v12 = (char *)this + 112;
  }
  std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>::operator()<std::unique_ptr<ColumnChunkBuffer>,0>(
    v12,
    v11);
LABEL_14:
  v369 = 0;
  v370 = 0;
  v13 = 0;
  v367 = 0;
  if ( *((int *)this + 10) > 0 )
  {
    v14 = 0;
    while ( 1 )
    {
      v15 = *((_QWORD *)this + 4) + 24LL * v14;
      if ( *(_WORD *)(v15 + 16) == 0xFFFF )
      {
        v16 = (_DWORD *)*((_QWORD *)this + 9);
        if ( *((_DWORD **)this + 10) == v16 )
        {
          std::vector<int>::_Emplace_reallocate<int const &>((char *)this + 64, v16, &v367);
          v13 = v367;
        }
        else
        {
          *v16 = v13;
          *((_QWORD *)this + 9) += 4LL;
        }
      }
      v372 = 0;
      v373 = 15;
      v371[0] = 0;
      v237 = v13;
      v17 = 24LL * v13;
      if ( (unsigned int)convert_ucs2_to_utf8(*(LPCWCH *)(*((_QWORD *)this + 4) + v17), v371) == 1 )
      {
        v232 = std::to_string(v365);
        v233 = (char *)std::operator+<char>(v366, "Malformed column name at column-ordinal=", v232);
        std::logic_error::logic_error((std::exception *)pExceptionObject, v233);
        throw (std::logic_error *)pExceptionObject;
      }
      LODWORD(v18) = -1;
      v368 = 0;
      switch ( *(_DWORD *)(v15 + 12) )
      {
        case 1:
          v19 = v17 + *((_QWORD *)this + 4);
          v20 = *((_QWORD *)this + 3);
          v21 = (ColumnChunkBuffer *)operator new(0x80u);
          v22 = v21;
          v273 = v21;
          if ( v21 )
          {
            memset(v21, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v22,
              *(const wchar_t **)v19,
              *(const struct SqlSetOptions **)(v20 + 160),
              *(_BYTE *)(v19 + 20));
            *(_QWORD *)v22 = &TypedColumnChunkBuffer<1,0,0,0>::`vftable';
            *((_QWORD *)v22 + 13) = 0;
            *((_QWORD *)v22 + 14) = 0;
            *((_QWORD *)v22 + 15) = 0;
            v23 = (__int64 *)parquet::LogicalType::None(v304);
            v24 = *v23;
            v25 = v23[1];
            *v23 = 0;
            v23[1] = 0;
            *((_QWORD *)v22 + 13) = v24;
            v274 = v25;
            v26 = (std::_Ref_count_base *)*((_QWORD *)v22 + 14);
            *((_QWORD *)v22 + 14) = v25;
            if ( v26 )
              std::_Ref_count_base::_Decref(v26);
            if ( v305 )
              std::_Ref_count_base::_Decref(v305);
          }
          else
          {
            v22 = 0;
          }
          v9 |= 2u;
          v27 = *((_QWORD *)this + 14);
          v28 = v237;
          v29 = *(void (__fastcall ****)(_QWORD, __int64))(v27 + 8 * v237);
          *(_QWORD *)(v27 + 8 * v237) = v22;
          if ( v29 )
            goto LABEL_57;
          goto LABEL_239;
        case 2:
          v30 = v17 + *((_QWORD *)this + 4);
          v31 = *((_QWORD *)this + 3);
          v32 = (ColumnChunkBuffer *)operator new(0x80u);
          v33 = v32;
          v275 = v32;
          if ( v32 )
          {
            memset(v32, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v33,
              *(const wchar_t **)v30,
              *(const struct SqlSetOptions **)(v31 + 160),
              *(_BYTE *)(v30 + 20));
            *(_QWORD *)v33 = &TypedColumnChunkBuffer<2,0,0,0>::`vftable';
            *((_QWORD *)v33 + 13) = 0;
            *((_QWORD *)v33 + 14) = 0;
            *((_QWORD *)v33 + 15) = 0;
            v34 = (__int64 *)parquet::LogicalType::Int(v306, 8, 0);
            v35 = *v34;
            v36 = v34[1];
            *v34 = 0;
            v34[1] = 0;
            *((_QWORD *)v33 + 13) = v35;
            v276 = v36;
            v37 = (std::_Ref_count_base *)*((_QWORD *)v33 + 14);
            *((_QWORD *)v33 + 14) = v36;
            if ( v37 )
              std::_Ref_count_base::_Decref(v37);
            if ( v307 )
              std::_Ref_count_base::_Decref(v307);
          }
          else
          {
            v33 = 0;
          }
          v9 |= 4u;
          v38 = *((_QWORD *)this + 14);
          v28 = v237;
          v29 = *(void (__fastcall ****)(_QWORD, __int64))(v38 + 8 * v237);
          *(_QWORD *)(v38 + 8 * v237) = v33;
          if ( v29 )
            goto LABEL_57;
          goto LABEL_239;
        case 3:
          v39 = v17 + *((_QWORD *)this + 4);
          v40 = *((_QWORD *)this + 3);
          v41 = (ColumnChunkBuffer *)operator new(0x80u);
          v42 = v41;
          v277 = v41;
          if ( v41 )
          {
            memset(v41, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v42,
              *(const wchar_t **)v39,
              *(const struct SqlSetOptions **)(v40 + 160),
              *(_BYTE *)(v39 + 20));
            *(_QWORD *)v42 = &TypedColumnChunkBuffer<3,0,0,0>::`vftable';
            *((_QWORD *)v42 + 13) = 0;
            *((_QWORD *)v42 + 14) = 0;
            *((_QWORD *)v42 + 15) = 0;
            LOBYTE(v43) = 1;
            v44 = (__int64 *)parquet::LogicalType::Int(v308, 16, v43);
            v45 = *v44;
            v46 = v44[1];
            *v44 = 0;
            v44[1] = 0;
            *((_QWORD *)v42 + 13) = v45;
            v278 = v46;
            v47 = (std::_Ref_count_base *)*((_QWORD *)v42 + 14);
            *((_QWORD *)v42 + 14) = v46;
            if ( v47 )
              std::_Ref_count_base::_Decref(v47);
            if ( v309 )
              std::_Ref_count_base::_Decref(v309);
          }
          else
          {
            v42 = 0;
          }
          v9 |= 8u;
          v48 = *((_QWORD *)this + 14);
          v28 = v237;
          v29 = *(void (__fastcall ****)(_QWORD, __int64))(v48 + 8 * v237);
          *(_QWORD *)(v48 + 8 * v237) = v42;
          if ( v29 )
            goto LABEL_57;
          goto LABEL_239;
        case 4:
          v49 = v17 + *((_QWORD *)this + 4);
          v50 = *((_QWORD *)this + 3);
          v51 = (ColumnChunkBuffer *)operator new(0x80u);
          v52 = v51;
          v279 = v51;
          if ( v51 )
          {
            memset(v51, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v52,
              *(const wchar_t **)v49,
              *(const struct SqlSetOptions **)(v50 + 160),
              *(_BYTE *)(v49 + 20));
            *(_QWORD *)v52 = &TypedColumnChunkBuffer<4,0,0,0>::`vftable';
            *((_QWORD *)v52 + 13) = 0;
            *((_QWORD *)v52 + 14) = 0;
            *((_QWORD *)v52 + 15) = 0;
            LOBYTE(v53) = 1;
            v54 = (__int64 *)parquet::LogicalType::Int(v310, 32, v53);
            v55 = *v54;
            v56 = v54[1];
            *v54 = 0;
            v54[1] = 0;
            *((_QWORD *)v52 + 13) = v55;
            v280 = v56;
            v57 = (std::_Ref_count_base *)*((_QWORD *)v52 + 14);
            *((_QWORD *)v52 + 14) = v56;
            if ( v57 )
              std::_Ref_count_base::_Decref(v57);
            if ( v311 )
              std::_Ref_count_base::_Decref(v311);
          }
          else
          {
            v52 = 0;
          }
          v9 |= 0x10u;
          v58 = *((_QWORD *)this + 14);
          v28 = v237;
          v29 = *(void (__fastcall ****)(_QWORD, __int64))(v58 + 8 * v237);
          *(_QWORD *)(v58 + 8 * v237) = v52;
          if ( v29 )
LABEL_57:
            (**v29)(v29, 1);
          goto LABEL_239;
        case 5:
          v59 = v17 + *((_QWORD *)this + 4);
          v60 = *((_QWORD *)this + 3);
          v61 = (ColumnChunkBuffer *)operator new(0x80u);
          v62 = v61;
          v281 = v61;
          if ( v61 )
          {
            memset(v61, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v62,
              *(const wchar_t **)v59,
              *(const struct SqlSetOptions **)(v60 + 160),
              *(_BYTE *)(v59 + 20));
            *(_QWORD *)v62 = &TypedColumnChunkBuffer<5,0,0,0>::`vftable';
            *((_QWORD *)v62 + 13) = 0;
            *((_QWORD *)v62 + 14) = 0;
            *((_QWORD *)v62 + 15) = 0;
            LOBYTE(v63) = 1;
            v64 = (__int64 *)parquet::LogicalType::Int(v312, 64, v63);
            v65 = *v64;
            v66 = v64[1];
            *v64 = 0;
            v64[1] = 0;
            *((_QWORD *)v62 + 13) = v65;
            v282 = v66;
            v67 = (std::_Ref_count_base *)*((_QWORD *)v62 + 14);
            *((_QWORD *)v62 + 14) = v66;
            if ( v67 )
              std::_Ref_count_base::_Decref(v67);
            if ( v313 )
              std::_Ref_count_base::_Decref(v313);
          }
          else
          {
            v62 = 0;
          }
          v9 |= 0x20u;
          v28 = v237;
          v68 = *((_QWORD *)this + 14) + 8 * v237;
          v269 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v68, v62);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v269);
          goto LABEL_239;
        case 6:
          v182 = *((_QWORD *)this + 4);
          *(_QWORD *)&v238 = v17 + v182;
          v183 = *(_BYTE *)(v17 + v182 + 16);
          LOBYTE(v368) = v183;
          v236 = *(_BYTE *)(v17 + v182 + 17);
          BYTE1(v368) = v236;
          if ( v183 )
          {
            if ( v183 > 9u )
            {
              if ( v183 > 0x12u )
              {
                v184 = 0;
                if ( v183 <= 0x26u )
                  v184 = 3;
              }
              else
              {
                v184 = 2;
              }
            }
            else
            {
              v184 = 1;
            }
          }
          else
          {
            v184 = 0;
          }
          v185 = v184 - 1;
          if ( v185 )
          {
            v186 = v185 - 1;
            if ( v186 )
            {
              if ( v186 != 1 )
              {
                v234 = std::wstring::wstring(v363, off_180371A10[*(int *)(v182 + 24LL * v367 + 12)]);
                v235 = std::operator+<wchar_t>(v364, v234, L"(38+,*)");
                ISqlHostException::Throw_UnsupportedSqlType(v235, 4);
              }
              LODWORD(v18) = ParquetDecimal::GetPhysicalSize(v183);
              v187 = (wchar_t **)(v17 + *((_QWORD *)this + 4));
              v188 = *((_QWORD *)this + 3);
              v189 = (ColumnChunkBuffer *)operator new(0x80u);
              v190 = v189;
              v298 = v189;
              if ( v189 )
              {
                memset(v189, 0, 0x80u);
                v191 = TypedColumnChunkBuffer<6,3,0,0>::TypedColumnChunkBuffer<6,3,0,0>(
                         v190,
                         *v187,
                         *(struct SqlSetOptions **)(v188 + 160),
                         (__int64)&v368);
              }
              else
              {
                v191 = 0;
              }
              v248 = v191;
              v192 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                       (char *)this + 112,
                       v237);
              v248 = 0;
              std::unique_ptr<ColumnChunkBuffer>::reset(v192, v191);
              std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v248);
            }
            else
            {
              v193 = *((_QWORD *)this + 3);
              v194 = (char *)operator new(0x80u);
              v195 = v194;
              v299 = v194;
              if ( v194 )
              {
                memset(v194, 0, 0x80u);
                ColumnChunkBuffer::ColumnChunkBuffer(
                  (ColumnChunkBuffer *)v195,
                  *(const wchar_t **)v238,
                  *(const struct SqlSetOptions **)(v193 + 160),
                  *(_BYTE *)(v238 + 20));
                *(_QWORD *)v195 = &TypedColumnChunkBuffer<6,2,0,0>::`vftable';
                std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>(v195 + 104);
                std::unique_ptr<__int64 [0]>::unique_ptr<__int64 [0]>(v195 + 120);
                v196 = parquet::LogicalType::Decimal(v350, v183, v236);
                std::shared_ptr<parquet::LogicalType const>::operator=(v195 + 104, v196);
                if ( v351 )
                  std::_Ref_count_base::_Decref(v351);
              }
              else
              {
                v195 = 0;
              }
              v249 = v195;
              v197 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                       (char *)this + 112,
                       v237);
              v249 = 0;
              std::unique_ptr<ColumnChunkBuffer>::reset(v197, v195);
              std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v249);
            }
          }
          else
          {
            v198 = *((_QWORD *)this + 3);
            v199 = (char *)operator new(0x80u);
            v200 = v199;
            v300 = v199;
            if ( v199 )
            {
              memset(v199, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                (ColumnChunkBuffer *)v200,
                *(const wchar_t **)v238,
                *(const struct SqlSetOptions **)(v198 + 160),
                *(_BYTE *)(v238 + 20));
              *(_QWORD *)v200 = &TypedColumnChunkBuffer<6,1,0,0>::`vftable';
              std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>(v200 + 104);
              std::unique_ptr<__int64 [0]>::unique_ptr<__int64 [0]>(v200 + 120);
              v201 = parquet::LogicalType::Decimal(v352, v183, v236);
              std::shared_ptr<parquet::LogicalType const>::operator=(v200 + 104, v201);
              if ( v353 )
                std::_Ref_count_base::_Decref(v353);
            }
            else
            {
              v200 = 0;
            }
            v250 = v200;
            v9 |= 0x80000000;
            v202 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                     (char *)this + 112,
                     v237);
            v250 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v202, v200);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v250);
          }
          goto LABEL_238;
        case 7:
          v69 = v17 + *((_QWORD *)this + 4);
          v70 = *((_QWORD *)this + 3);
          v71 = (ColumnChunkBuffer *)operator new(0x80u);
          v72 = v71;
          v283 = v71;
          if ( v71 )
          {
            memset(v71, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v72,
              *(const wchar_t **)v69,
              *(const struct SqlSetOptions **)(v70 + 160),
              *(_BYTE *)(v69 + 20));
            *(_QWORD *)v72 = &TypedColumnChunkBuffer<7,0,0,0>::`vftable';
            *((_QWORD *)v72 + 13) = 0;
            *((_QWORD *)v72 + 14) = 0;
            *((_QWORD *)v72 + 15) = 0;
            v73 = parquet::LogicalType::None(v314);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v72 + 104, v73);
            if ( v315 )
              std::_Ref_count_base::_Decref(v315);
          }
          else
          {
            v72 = 0;
          }
          v9 |= 0x40u;
          v28 = v237;
          v74 = *((_QWORD *)this + 14) + 8 * v237;
          v255 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v74, v72);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v255);
          goto LABEL_239;
        case 8:
          v75 = v17 + *((_QWORD *)this + 4);
          v76 = *((_QWORD *)this + 3);
          v77 = (ColumnChunkBuffer *)operator new(0x80u);
          v78 = v77;
          v284 = v77;
          if ( v77 )
          {
            memset(v77, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v78,
              *(const wchar_t **)v75,
              *(const struct SqlSetOptions **)(v76 + 160),
              *(_BYTE *)(v75 + 20));
            *(_QWORD *)v78 = &TypedColumnChunkBuffer<8,0,0,0>::`vftable';
            *((_QWORD *)v78 + 13) = 0;
            *((_QWORD *)v78 + 14) = 0;
            *((_QWORD *)v78 + 15) = 0;
            v79 = parquet::LogicalType::None(v316);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v78 + 104, v79);
            if ( v317 )
              std::_Ref_count_base::_Decref(v317);
          }
          else
          {
            v78 = 0;
          }
          v9 |= 0x80u;
          v28 = v237;
          v80 = *((_QWORD *)this + 14) + 8 * v237;
          v256 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v80, v78);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v256);
          goto LABEL_239;
        case 9:
          v236 = *(_BYTE *)(*((_QWORD *)this + 4) + v17 + 16);
          LOBYTE(v368) = v236;
          if ( ParquetWriterConfig::IsTimeDateTime2EncodeToInt96(*((ParquetWriterConfig **)this + 18)) )
          {
            v115 = v17 + *((_QWORD *)this + 4);
            v116 = *((_QWORD *)this + 3);
            v117 = (std::_Ref_count_base *)operator new(0x80u);
            v118 = v117;
            v254 = v117;
            if ( v117 )
            {
              memset(v117, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v118,
                *(const wchar_t **)v115,
                *(const struct SqlSetOptions **)(v116 + 160),
                *(_BYTE *)(v115 + 20));
              *(_QWORD *)v118 = &TypedColumnChunkBuffer<9,0,0,1>::`vftable';
              *((_QWORD *)v118 + 13) = 0;
              *((_QWORD *)v118 + 14) = 0;
              *((_QWORD *)v118 + 15) = 0;
              v119 = parquet::LogicalType::None(v328);
              v120 = v9 | 0x40000;
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v118 + 104, v119);
              if ( (v120 & 0x100000) != 0 )
              {
                v120 &= ~0x100000u;
                if ( v254 )
                  std::_Ref_count_base::_Decref(v254);
              }
              if ( (v120 & 0x80000) != 0 )
              {
                v120 &= ~0x80000u;
                if ( v254 )
                  std::_Ref_count_base::_Decref(v254);
              }
              v9 = v120 & 0xFFFBFFFF;
              if ( v329 )
                std::_Ref_count_base::_Decref(v329);
              *((_BYTE *)v118 + 40) = v236;
            }
            else
            {
              v118 = 0;
            }
            v9 |= 0x20000u;
            v28 = v237;
            v121 = *((_QWORD *)this + 14) + 8 * v237;
            v262 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v121, v118);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v262);
          }
          else
          {
            v122 = (__int64 *)std::make_unique<TypedColumnChunkBuffer<9,0,0,0>,wchar_t const * const &,SqlSetOptions const * const &,bool const &,ColumnChunkBuffer::SizeInfo &,0>(
                                (unsigned int)v263,
                                (int)v17 + *((_DWORD *)this + 8),
                                (unsigned int)*((_QWORD *)this + 3) + 160,
                                (int)v17 + *((_DWORD *)this + 8) + 20,
                                (__int64)&v368);
            v123 = (_QWORD *)*v10;
            v28 = v237;
            v124 = &v123[v237];
            v125 = *v122;
            *v122 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v124, v125);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(v263);
          }
          goto LABEL_239;
        case 0xA:
          v81 = v17 + *((_QWORD *)this + 4);
          v82 = *((_QWORD *)this + 3);
          v83 = (ColumnChunkBuffer *)operator new(0x80u);
          v84 = v83;
          v285 = v83;
          if ( v83 )
          {
            memset(v83, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v84,
              *(const wchar_t **)v81,
              *(const struct SqlSetOptions **)(v82 + 160),
              *(_BYTE *)(v81 + 20));
            *(_QWORD *)v84 = &TypedColumnChunkBuffer<10,0,0,0>::`vftable';
            *((_QWORD *)v84 + 13) = 0;
            *((_QWORD *)v84 + 14) = 0;
            *((_QWORD *)v84 + 15) = 0;
            v85 = parquet::LogicalType::Date(v318);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v84 + 104, v85);
            if ( v319 )
              std::_Ref_count_base::_Decref(v319);
          }
          else
          {
            v84 = 0;
          }
          v9 |= 0x100u;
          v28 = v237;
          v86 = *((_QWORD *)this + 14) + 8 * v237;
          v257 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v86, v84);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v257);
          goto LABEL_239;
        case 0xB:
          v236 = *(_BYTE *)(*((_QWORD *)this + 4) + v17 + 16);
          LOBYTE(v368) = v236;
          if ( v236 == 7 && ParquetWriterConfig::IsTimeDateTime2EncodeToInt96(*((ParquetWriterConfig **)this + 18)) )
          {
            v87 = v17 + *((_QWORD *)this + 4);
            v88 = *((_QWORD *)this + 3);
            v89 = (std::_Ref_count_base *)operator new(0x80u);
            v90 = v89;
            v270 = v89;
            if ( v89 )
            {
              memset(v89, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v90,
                *(const wchar_t **)v87,
                *(const struct SqlSetOptions **)(v88 + 160),
                *(_BYTE *)(v87 + 20));
              *(_QWORD *)v90 = &TypedColumnChunkBuffer<11,0,0,1>::`vftable';
              *((_QWORD *)v90 + 13) = 0;
              *((_QWORD *)v90 + 14) = 0;
              *((_QWORD *)v90 + 15) = 0;
              v91 = parquet::LogicalType::None(v320);
              v92 = v9 | 0x400;
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v90 + 104, v91);
              if ( (v92 & 0x800) != 0 )
              {
                v92 &= ~0x800u;
                if ( v270 )
                  std::_Ref_count_base::_Decref(v270);
              }
              v9 = v92 & 0xFFFFFBFF;
              if ( v321 )
                std::_Ref_count_base::_Decref(v321);
              *((_BYTE *)v90 + 40) = 7;
            }
            else
            {
              v90 = 0;
            }
            v9 |= 0x200u;
            v28 = v237;
            v93 = *((_QWORD *)this + 14) + 8 * v237;
            v258 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v93, v90);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v258);
          }
          else
          {
            v94 = v17 + *((_QWORD *)this + 4);
            v95 = *((_QWORD *)this + 3);
            v96 = (std::_Ref_count_base *)operator new(0x80u);
            v97 = v96;
            v268 = v96;
            if ( v96 )
            {
              memset(v96, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v97,
                *(const wchar_t **)v94,
                *(const struct SqlSetOptions **)(v95 + 160),
                *(_BYTE *)(v94 + 20));
              *(_QWORD *)v97 = &TypedColumnChunkBuffer<11,0,0,0>::`vftable';
              *((_QWORD *)v97 + 13) = 0;
              *((_QWORD *)v97 + 14) = 0;
              *((_QWORD *)v97 + 15) = 0;
              LOBYTE(v98) = 1;
              v99 = parquet::LogicalType::Time(v322, v98, 2);
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v97 + 104, v99);
              v9 &= ~0x4000u;
              if ( v323 )
                std::_Ref_count_base::_Decref(v323);
              if ( (v9 & 0x2000) != 0 )
              {
                v9 &= ~0x2000u;
                if ( v268 )
                  std::_Ref_count_base::_Decref(v268);
              }
              *((_BYTE *)v97 + 40) = v236;
            }
            else
            {
              v97 = 0;
            }
            v9 |= 0x1000u;
            v28 = v237;
            v100 = *((_QWORD *)this + 14) + 8 * v237;
            v259 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v100, v97);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v259);
          }
          goto LABEL_239;
        case 0xC:
          v132 = v17 + *((_QWORD *)this + 4);
          *(_QWORD *)&v238 = *(unsigned __int16 *)(v132 + 16);
          v133 = *((_QWORD *)this + 3);
          v134 = (ColumnChunkBuffer *)operator new(0x80u);
          v135 = v134;
          v289 = v134;
          if ( v134 )
          {
            memset(v134, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v135,
              *(const wchar_t **)v132,
              *(const struct SqlSetOptions **)(v133 + 160),
              *(_BYTE *)(v132 + 20));
            *(_QWORD *)v135 = &TypedColumnChunkBuffer<12,0,0,0>::`vftable';
            *((_QWORD *)v135 + 13) = 0;
            *((_QWORD *)v135 + 14) = 0;
            *((_QWORD *)v135 + 15) = 0;
            v136 = parquet::LogicalType::String(v332);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v135 + 104, v136);
            if ( v333 )
              std::_Ref_count_base::_Decref(v333);
            *((_QWORD *)v135 + 4) = 4 * v238;
          }
          else
          {
            v135 = 0;
          }
          v9 |= 0x400000u;
          v28 = v237;
          v137 = *((_QWORD *)this + 14) + 8 * v237;
          v265 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v137, v135);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v265);
          goto LABEL_239;
        case 0xD:
          v166 = v17 + *((_QWORD *)this + 4);
          v239 = (ColumnChunkBuffer *)*(unsigned __int16 *)(v166 + 16);
          v167 = *((_QWORD *)this + 3);
          v168 = (ColumnChunkBuffer *)operator new(0x80u);
          v169 = v168;
          v295 = v168;
          if ( v168 )
          {
            memset(v168, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v169,
              *(const wchar_t **)v166,
              *(const struct SqlSetOptions **)(v167 + 160),
              *(_BYTE *)(v166 + 20));
            *(_QWORD *)v169 = &TypedColumnChunkBuffer<13,0,0,0>::`vftable';
            std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>((char *)v169 + 104);
            *((_QWORD *)v169 + 15) = 0;
            v170 = parquet::LogicalType::String(v344);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v169 + 104, v170);
            if ( v345 )
              std::_Ref_count_base::_Decref(v345);
            *((_QWORD *)v169 + 4) = 3LL * (_QWORD)v239;
          }
          else
          {
            v169 = 0;
          }
          v239 = v169;
          v9 |= 0x10000000u;
          v171 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v239 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v171, v169);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v239);
          goto LABEL_238;
        case 0xE:
          v138 = v17 + *((_QWORD *)this + 4);
          *(_QWORD *)&v238 = *(unsigned __int16 *)(v138 + 16);
          v139 = *((_QWORD *)this + 3);
          if ( (unsigned __int64)v238 <= 0x1F40 )
          {
            v140 = (ColumnChunkBuffer *)operator new(0x80u);
            v141 = v140;
            v290 = v140;
            if ( v140 )
            {
              memset(v140, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v141,
                *(const wchar_t **)v138,
                *(const struct SqlSetOptions **)(v139 + 160),
                *(_BYTE *)(v138 + 20));
              *(_QWORD *)v141 = &TypedColumnChunkBuffer<14,0,0,0>::`vftable';
              *((_QWORD *)v141 + 13) = 0;
              *((_QWORD *)v141 + 14) = 0;
              *((_QWORD *)v141 + 15) = 0;
              v142 = parquet::LogicalType::String(v334);
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v141 + 104, v142);
              if ( v335 )
                std::_Ref_count_base::_Decref(v335);
              *((_QWORD *)v141 + 4) = 4 * v238;
            }
            else
            {
              v141 = 0;
            }
            v9 |= 0x800000u;
            v28 = v237;
            v143 = *((_QWORD *)this + 14) + 8 * v237;
            v266 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v143, v141);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v266);
            goto LABEL_239;
          }
          v144 = (ColumnChunkBuffer *)operator new(0x80u);
          v145 = v144;
          v291 = v144;
          if ( v144 )
          {
            memset(v144, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v145,
              *(const wchar_t **)v138,
              *(const struct SqlSetOptions **)(v139 + 160),
              *(_BYTE *)(v138 + 20));
            *(_QWORD *)v145 = &TypedColumnChunkBuffer<14,0,1,0>::`vftable';
            *((_QWORD *)v145 + 13) = 0;
            *((_QWORD *)v145 + 14) = 0;
            *((_QWORD *)v145 + 15) = 0;
            v146 = parquet::LogicalType::String(v336);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v145 + 104, v146);
            if ( v337 )
              std::_Ref_count_base::_Decref(v337);
            *((_QWORD *)v145 + 4) = 4 * v238;
          }
          else
          {
            v145 = 0;
          }
          v9 |= 0x1000000u;
          v147 = v237;
          v148 = *((_QWORD *)this + 14) + 8 * v237;
          v267 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v148, v145);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v267);
          v149 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v147);
          goto LABEL_155;
        case 0xF:
          *(_QWORD *)&v238 = v17 + *((_QWORD *)this + 4);
          v172 = *(unsigned __int16 *)(v238 + 16);
          v173 = *((_QWORD *)this + 3);
          if ( v172 <= 0x1F40 )
          {
            v174 = (ColumnChunkBuffer *)operator new(0x80u);
            v175 = v174;
            v296 = v174;
            if ( v174 )
            {
              memset(v174, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v175,
                *(const wchar_t **)v238,
                *(const struct SqlSetOptions **)(v173 + 160),
                *(_BYTE *)(v238 + 20));
              *(_QWORD *)v175 = &TypedColumnChunkBuffer<15,0,0,0>::`vftable';
              std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>((char *)v175 + 104);
              *((_QWORD *)v175 + 15) = 0;
              v176 = parquet::LogicalType::String(v346);
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v175 + 104, v176);
              if ( v347 )
                std::_Ref_count_base::_Decref(v347);
              *((_QWORD *)v175 + 4) = 3 * v172;
            }
            else
            {
              v175 = 0;
            }
            v246 = v175;
            v9 |= 0x20000000u;
            v177 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                     (char *)this + 112,
                     v237);
            v246 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v177, v175);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v246);
            goto LABEL_238;
          }
          v178 = (ColumnChunkBuffer *)operator new(0x80u);
          v179 = v178;
          v297 = v178;
          if ( v178 )
          {
            memset(v178, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v179,
              *(const wchar_t **)v238,
              *(const struct SqlSetOptions **)(v173 + 160),
              *(_BYTE *)(v238 + 20));
            *(_QWORD *)v179 = &TypedColumnChunkBuffer<15,0,1,0>::`vftable';
            std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>((char *)v179 + 104);
            *((_QWORD *)v179 + 15) = 0;
            v180 = parquet::LogicalType::String(v348);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v179 + 104, v180);
            if ( v349 )
              std::_Ref_count_base::_Decref(v349);
            *((_QWORD *)v179 + 4) = 3 * v172;
          }
          else
          {
            v179 = 0;
          }
          v247 = v179;
          v9 |= 0x40000000u;
          v181 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v247 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v181, v179);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v247);
          goto LABEL_175;
        case 0x10:
          v150 = v17 + *((_QWORD *)this + 4);
          v18 = *(unsigned __int16 *)(v150 + 16);
          v368 = v18;
          v151 = *((_QWORD *)this + 3);
          v152 = (ColumnChunkBuffer *)operator new(0x80u);
          v153 = v152;
          v292 = v152;
          if ( v152 )
          {
            memset(v152, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v153,
              *(const wchar_t **)v150,
              *(const struct SqlSetOptions **)(v151 + 160),
              *(_BYTE *)(v150 + 20));
            *(_QWORD *)v153 = &TypedColumnChunkBuffer<16,0,0,0>::`vftable';
            *((_QWORD *)v153 + 13) = 0;
            *((_QWORD *)v153 + 14) = 0;
            *((_QWORD *)v153 + 15) = 0;
            v154 = parquet::LogicalType::None(v338);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v153 + 104, v154);
            if ( v339 )
              std::_Ref_count_base::_Decref(v339);
            *((_QWORD *)v153 + 4) = v18;
          }
          else
          {
            v153 = 0;
          }
          v243 = v153;
          v9 |= 0x2000000u;
          v28 = v237;
          v155 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v243 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v155, v153);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v243);
          goto LABEL_239;
        case 0x11:
          *(_QWORD *)&v238 = v17 + *((_QWORD *)this + 4);
          v156 = *(unsigned __int16 *)(v238 + 16);
          v368 = v156;
          v157 = *((_QWORD *)this + 3);
          if ( (unsigned __int16)v156 > 0x1F40u )
          {
            v162 = (ColumnChunkBuffer *)operator new(0x80u);
            v163 = v162;
            v294 = v162;
            if ( v162 )
            {
              memset(v162, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v163,
                *(const wchar_t **)v238,
                *(const struct SqlSetOptions **)(v157 + 160),
                *(_BYTE *)(v238 + 20));
              *(_QWORD *)v163 = &TypedColumnChunkBuffer<17,0,1,0>::`vftable';
              *((_QWORD *)v163 + 13) = 0;
              *((_QWORD *)v163 + 14) = 0;
              *((_QWORD *)v163 + 15) = 0;
              v164 = parquet::LogicalType::None(v342);
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v163 + 104, v164);
              if ( v343 )
                std::_Ref_count_base::_Decref(v343);
              *((_QWORD *)v163 + 4) = v156;
            }
            else
            {
              v163 = 0;
            }
            v245 = v163;
            v9 |= 0x8000000u;
            v165 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                     (char *)this + 112,
                     v237);
            v245 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v165, v163);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v245);
LABEL_175:
            v149 = *(_QWORD *)std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                                (char *)this + 112,
                                v237);
LABEL_155:
            *(_QWORD *)(v149 + 96) = ParquetWriterConfig::GetMaxLobSize(*((ParquetWriterConfig **)this + 18));
          }
          else
          {
            v158 = (ColumnChunkBuffer *)operator new(0x80u);
            v159 = v158;
            v293 = v158;
            if ( v158 )
            {
              memset(v158, 0, 0x80u);
              ColumnChunkBuffer::ColumnChunkBuffer(
                v159,
                *(const wchar_t **)v238,
                *(const struct SqlSetOptions **)(v157 + 160),
                *(_BYTE *)(v238 + 20));
              *(_QWORD *)v159 = &TypedColumnChunkBuffer<17,0,0,0>::`vftable';
              *((_QWORD *)v159 + 13) = 0;
              *((_QWORD *)v159 + 14) = 0;
              *((_QWORD *)v159 + 15) = 0;
              v160 = parquet::LogicalType::None(v340);
              std::shared_ptr<parquet::LogicalType const>::operator=((char *)v159 + 104, v160);
              if ( v341 )
                std::_Ref_count_base::_Decref(v341);
              *((_QWORD *)v159 + 4) = v156;
            }
            else
            {
              v159 = 0;
            }
            v244 = v159;
            v9 |= 0x4000000u;
            v161 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                     (char *)this + 112,
                     v237);
            v244 = 0;
            std::unique_ptr<ColumnChunkBuffer>::reset(v161, v159);
            std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v244);
          }
LABEL_238:
          v28 = v237;
LABEL_239:
          v221 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v28);
          LODWORD(v238) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v221 + 8LL))(v221);
          v222 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v237);
          v223 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v222 + 16LL))(v222, v358);
          v241 = v223;
          v224 = *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8 * v237) + 24LL) != 0;
          v225 = operator new(0x70u);
          v226 = (int)v225;
          *(_QWORD *)&v240 = v225;
          if ( v225 )
          {
            memset(v225, 0, 0x70u);
            v227 = std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>(v359, v223);
            v228 = parquet::schema::PrimitiveNode::PrimitiveNode(v226, (unsigned int)v371, v224, v227, v238, v18, -1);
          }
          else
          {
            v228 = 0;
          }
          v238 = 0;
          std::shared_ptr<parquet::schema::Node>::_Setp<parquet::schema::PrimitiveNode>(&v238, v228, v236);
          std::shared_ptr<parquet::schema::GroupNode>::~shared_ptr<parquet::schema::GroupNode>(v223);
          if ( *((_QWORD *)&v370 + 1) == (_QWORD)v370 )
          {
            std::vector<std::shared_ptr<parquet::schema::Node>>::_Emplace_reallocate<std::shared_ptr<parquet::schema::Node>>(
              &v369,
              v370,
              &v238);
          }
          else
          {
            std::_Default_allocator_traits<std::allocator<std::shared_ptr<parquet::schema::Node>>>::construct<std::shared_ptr<parquet::schema::Node>,std::shared_ptr<parquet::schema::Node>>(
              &v369,
              v370,
              &v238);
            *(_QWORD *)&v370 = v370 + 16;
          }
          if ( *((_QWORD *)&v238 + 1) )
            std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v238 + 1));
          std::string::_Tidy_deallocate(v371);
          v13 = v367 + 1;
          v367 = v13;
          v14 = v13;
          if ( v13 >= *((_DWORD *)this + 10) )
            goto LABEL_249;
          v10 = (_QWORD *)((char *)this + 112);
          break;
        case 0x12:
          LODWORD(v18) = 16;
          v215 = v17 + *((_QWORD *)this + 4);
          v216 = *((_QWORD *)this + 3);
          v217 = operator new(0x80u);
          v218 = v217;
          v303 = v217;
          if ( v217 )
          {
            memset(v217, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              (ColumnChunkBuffer *)v218,
              *(const wchar_t **)v215,
              *(const struct SqlSetOptions **)(v216 + 160),
              *(_BYTE *)(v215 + 20));
            *v218 = &TypedColumnChunkBuffer<18,0,0,0>::`vftable';
            std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>(v218 + 13);
            std::unique_ptr<__int64 [0]>::unique_ptr<__int64 [0]>(v218 + 15);
            v219 = parquet::LogicalType::UUID(v356);
            std::shared_ptr<parquet::LogicalType const>::operator=(v218 + 13, v219);
            if ( v357 )
              std::_Ref_count_base::_Decref(v357);
            v218[4] = 16;
          }
          else
          {
            v218 = 0;
          }
          v253 = v218;
          v220 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v253 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v220, v218);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v253);
          goto LABEL_238;
        case 0x13:
          LODWORD(v18) = 34;
          v126 = v17 + *((_QWORD *)this + 4);
          v127 = *((_QWORD *)this + 3);
          v128 = (ColumnChunkBuffer *)operator new(0x80u);
          v129 = v128;
          v288 = v128;
          if ( v128 )
          {
            memset(v128, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v129,
              *(const wchar_t **)v126,
              *(const struct SqlSetOptions **)(v127 + 160),
              *(_BYTE *)(v126 + 20));
            *(_QWORD *)v129 = &TypedColumnChunkBuffer<19,0,0,0>::`vftable';
            *((_QWORD *)v129 + 13) = 0;
            *((_QWORD *)v129 + 14) = 0;
            *((_QWORD *)v129 + 15) = 0;
            v130 = parquet::LogicalType::String(v330);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v129 + 104, v130);
            if ( v331 )
              std::_Ref_count_base::_Decref(v331);
            *((_QWORD *)v129 + 4) = 34;
          }
          else
          {
            v129 = 0;
          }
          v9 |= 0x200000u;
          v28 = v237;
          v131 = *((_QWORD *)this + 14) + 8 * v237;
          v264 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v131, v129);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v264);
          goto LABEL_239;
        case 0x14:
          v108 = v17 + *((_QWORD *)this + 4);
          v109 = *((_QWORD *)this + 3);
          v110 = (ColumnChunkBuffer *)operator new(0x80u);
          v111 = v110;
          v287 = v110;
          if ( v110 )
          {
            memset(v110, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v111,
              *(const wchar_t **)v108,
              *(const struct SqlSetOptions **)(v109 + 160),
              *(_BYTE *)(v108 + 20));
            *(_QWORD *)v111 = &TypedColumnChunkBuffer<20,0,0,0>::`vftable';
            *((_QWORD *)v111 + 13) = 0;
            *((_QWORD *)v111 + 14) = 0;
            *((_QWORD *)v111 + 15) = 0;
            LOBYTE(v112) = 1;
            v113 = parquet::LogicalType::Timestamp((unsigned int)&v326, v112, 2, 0, 0);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v111 + 104, v113);
            if ( v327 )
              std::_Ref_count_base::_Decref(v327);
          }
          else
          {
            v111 = 0;
          }
          v9 |= 0x10000u;
          v28 = v237;
          v114 = *((_QWORD *)this + 14) + 8 * v237;
          v261 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v114, v111);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v261);
          goto LABEL_239;
        case 0x15:
          v101 = v17 + *((_QWORD *)this + 4);
          v102 = *((_QWORD *)this + 3);
          v103 = (ColumnChunkBuffer *)operator new(0x80u);
          v104 = v103;
          v286 = v103;
          if ( v103 )
          {
            memset(v103, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              v104,
              *(const wchar_t **)v101,
              *(const struct SqlSetOptions **)(v102 + 160),
              *(_BYTE *)(v101 + 20));
            *(_QWORD *)v104 = &TypedColumnChunkBuffer<21,0,0,0>::`vftable';
            *((_QWORD *)v104 + 13) = 0;
            *((_QWORD *)v104 + 14) = 0;
            *((_QWORD *)v104 + 15) = 0;
            LOBYTE(v105) = 1;
            v106 = parquet::LogicalType::Timestamp((unsigned int)&v324, v105, 2, 0, 0);
            std::shared_ptr<parquet::LogicalType const>::operator=((char *)v104 + 104, v106);
            if ( v325 )
              std::_Ref_count_base::_Decref(v325);
          }
          else
          {
            v104 = 0;
          }
          v9 |= 0x8000u;
          v28 = v237;
          v107 = *((_QWORD *)this + 14) + 8 * v237;
          v260 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v107, v104);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v260);
          goto LABEL_239;
        case 0x16:
          v209 = v17 + *((_QWORD *)this + 4);
          v210 = *((_QWORD *)this + 3);
          v211 = (char *)operator new(0x80u);
          v212 = v211;
          v302 = v211;
          if ( v211 )
          {
            memset(v211, 0, 0x80u);
            ColumnChunkBuffer::ColumnChunkBuffer(
              (ColumnChunkBuffer *)v212,
              *(const wchar_t **)v209,
              *(const struct SqlSetOptions **)(v210 + 160),
              *(_BYTE *)(v209 + 20));
            *(_QWORD *)v212 = &TypedColumnChunkBuffer<22,0,0,0>::`vftable';
            std::shared_ptr<parquet::LogicalType const>::shared_ptr<parquet::LogicalType const>(v212 + 104);
            std::unique_ptr<__int64 [0]>::unique_ptr<__int64 [0]>(v212 + 120);
            v213 = parquet::LogicalType::Decimal(v354, 10, 4);
            std::shared_ptr<parquet::LogicalType const>::operator=(v212 + 104, v213);
            if ( v355 )
              std::_Ref_count_base::_Decref(v355);
          }
          else
          {
            v212 = 0;
          }
          v252 = v212;
          v214 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v252 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v214, v212);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v252);
          goto LABEL_238;
        case 0x17:
          LODWORD(v18) = 12;
          v203 = (wchar_t **)(v17 + *((_QWORD *)this + 4));
          v204 = *((_QWORD *)this + 3);
          v205 = (ColumnChunkBuffer *)operator new(0x80u);
          v206 = v205;
          v301 = v205;
          if ( v205 )
          {
            memset(v205, 0, 0x80u);
            v207 = TypedColumnChunkBuffer<23,0,0,0>::TypedColumnChunkBuffer<23,0,0,0>(
                     v206,
                     *v203,
                     *(struct SqlSetOptions **)(v204 + 160));
          }
          else
          {
            v207 = 0;
          }
          v251 = v207;
          v208 = std::unique_ptr<std::unique_ptr<ColumnChunkBuffer> [0],std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>>::operator[](
                   (char *)this + 112,
                   v237);
          v251 = 0;
          std::unique_ptr<ColumnChunkBuffer>::reset(v208, v207);
          std::unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>::~unique_ptr<TypedColumnChunkBuffer<16,0,0,0>>(&v251);
          goto LABEL_238;
        default:
          std::wstring::wstring(v362, off_180371A10[*(int *)(*((_QWORD *)this + 4) + 24LL * v367 + 12)]);
          ISqlHostException::Throw_UnsupportedSqlType(v362, 5);
      }
    }
  }
LABEL_249:
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v271[0] = 0;
  std::string::assign(v271, "schema", 6u);
  v229 = (struct Node *)operator new(0xB0u);
  v230 = v229;
  *(_QWORD *)&v240 = v229;
  if ( v229 )
  {
    memset(v229, 0, 0xB0u);
    v2 = parquet::schema::GroupNode::GroupNode(v230, 0, -1);
  }
  v240 = 0;
  std::shared_ptr<parquet::schema::Node>::_Setp<parquet::schema::GroupNode>(&v240, v2, v236);
  v231 = (std::_Ref_count_base *)*((_QWORD *)&v240 + 1);
  if ( *((_QWORD *)&v240 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v240 + 1) + 8LL));
    v231 = (std::_Ref_count_base *)*((_QWORD *)&v240 + 1);
  }
  v242 = v231;
  v241 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v240;
  std::swap<std::_Ref_count_base *,void>(&v242, (char *)this + 128);
  if ( v242 )
    std::_Ref_count_base::_Decref(v242);
  if ( v231 )
    std::_Ref_count_base::_Decref(v231);
  std::string::_Tidy_deallocate(v271);
  if ( v369 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<parquet::schema::Node>>>(v369, v370, &v369);
    std::allocator<std::shared_ptr<parquet::schema::Node>>::deallocate(
      &v369,
      v369,
      (*((_QWORD *)&v370 + 1) - v369) >> 4);
  }
}

```

## disassembly

```asm
0x180016ad0  mov     rax, rsp
0x180016ad3  push    rbp
0x180016ad4  push    r12
0x180016ad6  push    r13
0x180016ad8  push    r14
0x180016ada  push    r15
0x180016adc  lea     rbp, [rax-488h]
0x180016ae3  sub     rsp, 560h
0x180016aea  mov     [rbp+480h+var_130], 0FFFFFFFFFFFFFFFEh
0x180016af5  mov     [rax+10h], rbx
0x180016af9  mov     [rax+18h], rsi
0x180016afd  mov     [rax+20h], rdi
0x180016b01  mov     rax, cs:__security_cookie
0x180016b08  xor     rax, rsp
0x180016b0b  mov     [rbp+480h+var_28], rax
0x180016b12  mov     r15, rcx
0x180016b15  xor     r14d, r14d
0x180016b18  mov     dword ptr [rsp+580h+var_540+4], r14d
0x180016b1d  lea     rcx, byte_1804EA0FE
0x180016b24  call    __CheckForDebuggerJustMyCode
0x180016b29  movsxd  rdi, dword ptr [r15+28h]
0x180016b2d  mov     eax, 8
0x180016b32  mul     rdi
0x180016b35  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180016b3c  cmovo   rax, rsi
0x180016b40  add     rax, 8
0x180016b44  cmovb   rax, rsi
0x180016b48  mov     rcx, rax; unsigned __int64
0x180016b4b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016b50  test    rax, rax
0x180016b53  jz      short loc_180016B7F
0x180016b55  mov     [rax], rdi
0x180016b58  lea     rbx, [rax+8]
0x180016b5c  lea     rax, ??1?$unique_ptr@VParquetFileWrite@@U?$default_delete@VParquetFileWrite@@@std@@@std@@QEAA@XZ; std::unique_ptr<ParquetFileWrite>::~unique_ptr<ParquetFileWrite>(void)
0x180016b63  mov     [rsp+580h+var_560], rax; void (*)(void *)
0x180016b68  lea     r9, ??$?0U?$default_delete@$$BY0A@_J@std@@$0A@@?$unique_ptr@$$BY0A@_JU?$default_delete@$$BY0A@_J@std@@@std@@QEAA@XZ; void (*)(void *)
0x180016b6f  mov     r8, rdi; unsigned __int64
0x180016b72  lea     edx, [rsi+9]; unsigned __int64
0x180016b75  mov     rcx, rbx; void *
0x180016b78  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180016b7d  jmp     short loc_180016B82
0x180016b7f  mov     rbx, r14
0x180016b82  mov     r12d, 1
0x180016b88  mov     dword ptr [rsp+580h+var_540+4], r12d
0x180016b8d  lea     r13, [r15+70h]
0x180016b91  lea     rax, [rsp+580h+var_538]
0x180016b96  cmp     r13, rax
0x180016b99  jz      short loc_180016BAD
0x180016b9b  mov     rdx, [r13+0]
0x180016b9f  mov     [r13+0], rbx
0x180016ba3  test    rdx, rdx
0x180016ba6  jz      short loc_180016BBF
0x180016ba8  mov     rcx, r13
0x180016bab  jmp     short loc_180016BBA
0x180016bad  test    rbx, rbx
0x180016bb0  jz      short loc_180016BBF
0x180016bb2  mov     rdx, rbx
0x180016bb5  lea     rcx, [rsp+580h+var_538]
0x180016bba  call    ??$?RV?$unique_ptr@VColumnChunkBuffer@@U?$default_delete@VColumnChunkBuffer@@@std@@@std@@$0A@@?$default_delete@$$BY0A@V?$unique_ptr@VColumnChunkBuffer@@U?$default_delete@VColumnChunkBuffer@@@std@@@std@@@std@@QEBAXPEAV?$unique_ptr@VColumnChunkBuffer@@U?$default_delete@VColumnChunkBuffer@@@std@@@1@@Z; std::default_delete<std::unique_ptr<ColumnChunkBuffer> [0]>::operator()<std::unique_ptr<ColumnChunkBuffer>,0>(std::unique_ptr<ColumnChunkBuffer> *)
0x180016bbf  mov     [rbp+480h+var_60], r14
0x180016bc6  xorps   xmm0, xmm0
0x180016bc9  movdqu  [rbp+480h+var_58], xmm0
0x180016bd1  mov     edi, r14d
0x180016bd4  mov     [rbp+480h+var_70], r14d
0x180016bdb  cmp     [r15+28h], r14d
0x180016bdf  jle     loc_180018845
0x180016be5  mov     eax, r14d
0x180016be8  mov     r8d, 0FFFFh
0x180016bee  cdqe
0x180016bf0  lea     rcx, [rax+rax*2]
0x180016bf4  mov     rax, [r15+20h]
0x180016bf8  lea     rsi, [rax+rcx*8]
0x180016bfc  cmp     [rsi+10h], r8w
0x180016c01  jnz     short loc_180016C2C
0x180016c03  lea     rcx, [r15+40h]
0x180016c07  mov     rdx, [rcx+8]
0x180016c0b  cmp     [rcx+10h], rdx
0x180016c0f  jz      short loc_180016C1A
0x180016c11  mov     [rdx], edi
0x180016c13  add     qword ptr [rcx+8], 4
0x180016c18  jmp     short loc_180016C2C
0x180016c1a  lea     r8, [rbp+480h+var_70]
0x180016c21  call    ??$_Emplace_reallocate@AEBH@?$vector@HV?$allocator@H@std@@@std@@QEAAPEAHQEAHAEBH@Z; std::vector<int>::_Emplace_reallocate<int const &>(int * const,int const &)
0x180016c26  mov     edi, [rbp+480h+var_70]
0x180016c2c  mov     [rbp+480h+var_38], r14
0x180016c33  mov     [rbp+480h+var_30], 0Fh
0x180016c3e  mov     [rbp+480h+var_48], 0
0x180016c45  movsxd  rax, edi
0x180016c48  mov     qword ptr [rsp+580h+var_538], rax
0x180016c4d  lea     rax, [rax+rax*2]
0x180016c51  lea     rbx, ds:0[rax*8]
0x180016c59  mov     rcx, [r15+20h]
0x180016c5d  lea     rdx, [rbp+480h+var_48]; void *
0x180016c64  mov     rcx, [rcx+rbx]; lpWideCharStr
0x180016c68  call    ?convert_ucs2_to_utf8@@YA?AW4utilerror@@PEB_WAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; convert_ucs2_to_utf8(wchar_t const *,std::string &)
0x180016c6d  cmp     eax, 1
0x180016c70  jz      loc_1800189DF
0x180016c76  mov     edi, 0FFFFFFFFh
0x180016c7b  mov     [rbp+480h+var_68], r14
0x180016c82  mov     eax, [rsi+0Ch]
0x180016c85  dec     eax; switch 23 cases
0x180016c87  lea     r8, cs:180000000h
0x180016c8e  cmp     eax, 16h
0x180016c91  ja      def_180016CA4; jumptable 0000000180016CA4 default case
0x180016c97  cdqe
0x180016c99  mov     ecx, ds:(jpt_180016CA4 - 180000000h)[r8+rax*4]
0x180016ca1  add     rcx, r8
0x180016ca4  jmp     rcx; switch jump
0x180016ca6  mov     r13, [r15+20h]; jumptable 0000000180016CA4 case 1
0x180016caa  add     r13, rbx
0x180016cad  mov     rsi, [r15+18h]
0x180016cb1  mov     ecx, 80h; Size
0x180016cb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016cbb  mov     rbx, rax
0x180016cbe  mov     [rbp+480h+var_3F8], rax
0x180016cc5  test    rax, rax
0x180016cc8  jz      loc_180016D59
0x180016cce  xor     edx, edx; Val
0x180016cd0  mov     r8d, 80h; Size
0x180016cd6  mov     rcx, rax; void *
0x180016cd9  call    memset
0x180016cde  movzx   r9d, byte ptr [r13+14h]; bool
0x180016ce3  mov     r8, [rsi+0A0h]; struct SqlSetOptions *
0x180016cea  mov     rdx, [r13+0]; wchar_t *
0x180016cee  mov     rcx, rbx; this
0x180016cf1  call    ??0ColumnChunkBuffer@@QEAA@PEB_WPEBUSqlSetOptions@@_N@Z; ColumnChunkBuffer::ColumnChunkBuffer(wchar_t const *,SqlSetOptions const *,bool)
0x180016cf6  nop
0x180016cf7  lea     rax, ??_7?$TypedColumnChunkBuffer@$00$0A@$0A@$0A@@@6B@; const TypedColumnChunkBuffer<1,0,0,0>::`vftable'
0x180016cfe  mov     [rbx], rax
0x180016d01  mov     [rbx+68h], r14
0x180016d05  mov     [rbx+70h], r14
0x180016d09  mov     [rbx+78h], r14
0x180016d0d  lea     rcx, [rbp+480h+var_300]
0x180016d14  call    ?None@LogicalType@parquet@@SA?AV?$shared_ptr@$$CBVLogicalType@parquet@@@std@@XZ; parquet::LogicalType::None(void)
0x180016d19  mov     rcx, [rax]
0x180016d1c  mov     rdx, [rax+8]
0x180016d20  mov     [rax], r14
0x180016d23  mov     [rax+8], r14
0x180016d27  mov     [rbx+68h], rcx
0x180016d2b  mov     [rbp+480h+var_3F0], rdx
0x180016d32  mov     rcx, [rbx+70h]; this
0x180016d36  mov     [rbx+70h], rdx
0x180016d3a  test    rcx, rcx
0x180016d3d  jz      short loc_180016D45
0x180016d3f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d44  nop
0x180016d45  mov     rcx, [rbp+480h+var_2F8]; this
0x180016d4c  test    rcx, rcx
0x180016d4f  jz      short loc_180016D57
0x180016d51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016d56  nop
0x180016d57  jmp     short loc_180016D5C
0x180016d59  mov     rbx, r14
0x180016d5c  or      r12d, 2
0x180016d60  mov     dword ptr [rsp+580h+var_540+4], r12d
0x180016d65  mov     rax, [r15+70h]
0x180016d69  mov     r13, qword ptr [rsp+580h+var_538]
0x180016d6e  mov     rcx, [rax+r13*8]
0x180016d72  mov     [rax+r13*8], rbx
0x180016d76  test    rcx, rcx
0x180016d79  jz      loc_1800186EF
0x180016d7f  mov     rax, [rcx]
0x180016d82  mov     edx, 1
0x180016d87  mov     rax, [rax]
0x180016d8a  call    cs:__guard_dispatch_icall_fptr
0x180016d90  jmp     loc_1800186EF
0x180016d95  mov     r13, [r15+20h]; jumptable 0000000180016CA4 case 2
0x180016d99  add     r13, rbx
0x180016d9c  mov     rsi, [r15+18h]
0x180016da0  mov     ecx, 80h; Size
0x180016da5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016daa  mov     rbx, rax
0x180016dad  mov     [rbp+480h+var_3E8], rax
0x180016db4  test    rax, rax
0x180016db7  jz      loc_180016E4F
0x180016dbd  xor     edx, edx; Val
0x180016dbf  mov     r8d, 80h; Size
0x180016dc5  mov     rcx, rax; void *
0x180016dc8  call    memset
0x180016dcd  movzx   r9d, byte ptr [r13+14h]; bool
0x180016dd2  mov     r8, [rsi+0A0h]; struct SqlSetOptions *
0x180016dd9  mov     rdx, [r13+0]; wchar_t *
0x180016ddd  mov     rcx, rbx; this
0x180016de0  call    ??0ColumnChunkBuffer@@QEAA@PEB_WPEBUSqlSetOptions@@_N@Z; ColumnChunkBuffer::ColumnChunkBuffer(wchar_t const *,SqlSetOptions const *,bool)
0x180016de5  nop
0x180016de6  lea     rax, ??_7?$TypedColumnChunkBuffer@$01$0A@$0A@$0A@@@6B@; const TypedColumnChunkBuffer<2,0,0,0>::`vftable'
0x180016ded  mov     [rbx], rax
0x180016df0  mov     [rbx+68h], r14
0x180016df4  mov     [rbx+70h], r14
0x180016df8  mov     [rbx+78h], r14
0x180016dfc  xor     r8d, r8d
0x180016dff  lea     edx, [r8+8]
0x180016e03  lea     rcx, [rbp+480h+var_2F0]
0x180016e0a  call    ?Int@LogicalType@parquet@@SA?AV?$shared_ptr@$$CBVLogicalType@parquet@@@std@@H_N@Z; parquet::LogicalType::Int(int,bool)
0x180016e0f  mov     rcx, [rax]
0x180016e12  mov     rdx, [rax+8]
0x180016e16  mov     [rax], r14
0x180016e19  mov     [rax+8], r14
0x180016e1d  mov     [rbx+68h], rcx
0x180016e21  mov     [rbp+480h+var_3E0], rdx
0x180016e28  mov     rcx, [rbx+70h]; this
0x180016e2c  mov     [rbx+70h], rdx
0x180016e30  test    rcx, rcx
0x180016e33  jz      short loc_180016E3B
0x180016e35  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016e3a  nop
0x180016e3b  mov     rcx, [rbp+480h+var_2E8]; this
0x180016e42  test    rcx, rcx
0x180016e45  jz      short loc_180016E4D
0x180016e47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016e4c  nop
0x180016e4d  jmp     short loc_180016E52
0x180016e4f  mov     rbx, r14
0x180016e52  or      r12d, 4
0x180016e56  mov     dword ptr [rsp+580h+var_540+4], r12d
0x180016e5b  mov     rax, [r15+70h]
0x180016e5f  mov     r13, qword ptr [rsp+580h+var_538]
0x180016e64  mov     rcx, [rax+r13*8]
0x180016e68  mov     [rax+r13*8], rbx
0x180016e6c  test    rcx, rcx
0x180016e6f  jz      loc_1800186EF
0x180016e75  mov     rax, [rcx]
0x180016e78  mov     edx, 1
0x180016e7d  mov     rax, [rax]
0x180016e80  call    cs:__guard_dispatch_icall_fptr
0x180016e86  jmp     loc_1800186EF
0x180016e8b  mov     r13, [r15+20h]; jumptable 0000000180016CA4 case 3
0x180016e8f  add     r13, rbx
0x180016e92  mov     rsi, [r15+18h]
0x180016e96  mov     ecx, 80h; Size
0x180016e9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016ea0  mov     rbx, rax
0x180016ea3  mov     [rbp+480h+var_3D8], rax
0x180016eaa  test    rax, rax
0x180016ead  jz      loc_180016F46
0x180016eb3  xor     edx, edx; Val
0x180016eb5  mov     r8d, 80h; Size
0x180016ebb  mov     rcx, rax; void *
0x180016ebe  call    memset
0x180016ec3  movzx   r9d, byte ptr [r13+14h]; bool
0x180016ec8  mov     r8, [rsi+0A0h]; struct SqlSetOptions *
0x180016ecf  mov     rdx, [r13+0]; wchar_t *
0x180016ed3  mov     rcx, rbx; this
0x180016ed6  call    ??0ColumnChunkBuffer@@QEAA@PEB_WPEBUSqlSetOptions@@_N@Z; ColumnChunkBuffer::ColumnChunkBuffer(wchar_t const *,SqlSetOptions const *,bool)
0x180016edb  nop
0x180016edc  lea     rax, ??_7?$TypedColumnChunkBuffer@$02$0A@$0A@$0A@@@6B@; const TypedColumnChunkBuffer<3,0,0,0>::`vftable'
0x180016ee3  mov     [rbx], rax
0x180016ee6  mov     [rbx+68h], r14
0x180016eea  mov     [rbx+70h], r14
0x180016eee  mov     [rbx+78h], r14
0x180016ef2  mov     r8b, 1
0x180016ef5  mov     edx, 10h
0x180016efa  lea     rcx, [rbp+480h+var_2E0]
0x180016f01  call    ?Int@LogicalType@parquet@@SA?AV?$shared_ptr@$$CBVLogicalType@parquet@@@std@@H_N@Z; parquet::LogicalType::Int(int,bool)
0x180016f06  mov     rcx, [rax]
0x180016f09  mov     rdx, [rax+8]
0x180016f0d  mov     [rax], r14
0x180016f10  mov     [rax+8], r14
0x180016f14  mov     [rbx+68h], rcx
0x180016f18  mov     [rbp+480h+var_3D0], rdx
0x180016f1f  mov     rcx, [rbx+70h]; this
0x180016f23  mov     [rbx+70h], rdx
0x180016f27  test    rcx, rcx
0x180016f2a  jz      short loc_180016F32
0x180016f2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016f31  nop
0x180016f32  mov     rcx, [rbp+480h+var_2D8]; this
0x180016f39  test    rcx, rcx
0x180016f3c  jz      short loc_180016F44
0x180016f3e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016f43  nop
0x180016f44  jmp     short loc_180016F49
0x180016f46  mov     rbx, r14
0x180016f49  or      r12d, 8
0x180016f4d  mov     dword ptr [rsp+580h+var_540+4], r12d
0x180016f52  mov     rax, [r15+70h]
0x180016f56  mov     r13, qword ptr [rsp+580h+var_538]
0x180016f5b  mov     rcx, [rax+r13*8]
0x180016f5f  mov     [rax+r13*8], rbx
0x180016f63  test    rcx, rcx
0x180016f66  jz      loc_1800186EF
0x180016f6c  mov     rax, [rcx]
0x180016f6f  mov     edx, 1
0x180016f74  mov     rax, [rax]
0x180016f77  call    cs:__guard_dispatch_icall_fptr
0x180016f7d  jmp     loc_1800186EF
0x180016f82  mov     r13, [r15+20h]; jumptable 0000000180016CA4 case 4
0x180016f86  add     r13, rbx
0x180016f89  mov     rsi, [r15+18h]
0x180016f8d  mov     ecx, 80h; Size
0x180016f92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016f97  mov     rbx, rax
0x180016f9a  mov     [rbp+480h+var_3C8], rax
0x180016fa1  test    rax, rax
0x180016fa4  jz      loc_18001703D
0x180016faa  xor     edx, edx; Val
0x180016fac  mov     r8d, 80h; Size
0x180016fb2  mov     rcx, rax; void *
0x180016fb5  call    memset
0x180016fba  movzx   r9d, byte ptr [r13+14h]; bool
  ... truncated ...
```
