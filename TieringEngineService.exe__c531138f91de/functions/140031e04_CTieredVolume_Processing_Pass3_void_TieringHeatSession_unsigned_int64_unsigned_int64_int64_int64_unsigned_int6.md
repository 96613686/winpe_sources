# CTieredVolume::Processing_Pass3(void *,TieringHeatSession *,unsigned __int64,unsigned __int64,__int64,__int64,unsigned __int64)

- ea: `0x140031e04`
- end: `0x140034f9b`
- name: `?Processing_Pass3@CTieredVolume@@AEAAJPEAXPEAVTieringHeatSession@@_K2_J32@Z`
- size: `12695`
- prototype: `__int64 __fastcall(JET_API_PTR ulContext, void *, struct TieringHeatSession *, __int64, unsigned __int64, __int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `47`
- tags: `file_ops`

## callers

- `0x14002eef0`

## callees

- `0x14000108c`
- `0x1400015d8`
- `0x140001a00`
- `0x140002323`
- `0x140002db0`
- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009f1c`
- `0x14000b7f8`
- `0x14000bee8`
- `0x14000e9a4`
- `0x140017824`
- `0x140017930`
- `0x140017e78`
- `0x14001cd80`
- `0x14001d058`
- `0x14001d534`
- `0x14001d5a4`
- `0x14001d7ec`
- `0x1400260cc`
- `0x140026290`
- `0x140026434`
- `0x14002670c`
- `0x14002866c`
- `0x140031e04`
- `0x140034fa4`
- `0x140035148`
- `0x1400351f8`
- `0x14003546c`
- `0x1400354b0`
- `0x140035508`
- `0x1400355b8`
- `0x140035680`
- `0x140035744`
- `0x1400357f0`
- `0x140035888`
- `0x140035934`
- `0x140035a98`
- `0x140035d68`
- `0x140035e18`
- `0x140035fc0`
- `0x1400360b8`
- `0x140036194`
- `0x14003fb76`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!malloc` at `0x140031fb4`
- `msvcrt!malloc` at `0x140031fc6`
- `msvcrt!malloc` at `0x14003217e`
- `msvcrt!malloc` at `0x140031fb4`
- `msvcrt!malloc` at `0x140031fc6`
- `msvcrt!malloc` at `0x14003217e`
- `msvcrt!free` at `0x140031fdb`
- `msvcrt!free` at `0x140034f17`
- `msvcrt!free` at `0x140034f25`
- `msvcrt!free` at `0x140034f37`
- `msvcrt!free` at `0x140031fdb`
- `msvcrt!free` at `0x140034f17`
- `msvcrt!free` at `0x140034f25`
- `msvcrt!free` at `0x140034f37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400324b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400324d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400343be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400343d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400324b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400324d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400343be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400343d9`
- `ESENT!JetDelete` at `0x140034a63`
- `ESENT!JetDelete` at `0x140034a63`
- `ESENT!JetMove` at `0x140032520`
- `ESENT!JetMove` at `0x140034426`
- `ESENT!JetMove` at `0x140032520`
- `ESENT!JetMove` at `0x140034426`

## pseudocode

```c
__int64 __fastcall CTieredVolume::Processing_Pass3(
        JET_API_PTR ulContext,
        void *a2,
        struct TieringHeatSession *a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned __int64 a8)
{
  CTieredVolume::CSmartTieringMovementSession *MovementSession; // rdi
  int v10; // ebx
  unsigned int v11; // ebx
  _QWORD *v12; // rdi
  unsigned int v13; // r14d
  int v14; // r8d
  void *v15; // rsi
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // r13d
  void *v19; // rdx
  int v20; // r8d
  unsigned int v21; // eax
  int v22; // esi
  unsigned __int64 v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // edx
  _QWORD *v29; // r10
  __int64 v30; // rdi
  __int64 v31; // r14
  __int64 v32; // rax
  unsigned int v33; // eax
  unsigned int CurrentHeatRecord; // eax
  __int64 v35; // r9
  int v36; // ebx
  int v37; // eax
  int v38; // eax
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // r10
  unsigned int v42; // r11d
  unsigned int v43; // ecx
  unsigned int v44; // r8d
  __int64 v45; // rdx
  int v46; // r9d
  int v47; // r9d
  _QWORD *v48; // rcx
  int v49; // r14d
  unsigned __int64 v50; // r8
  unsigned __int128 v51; // rax
  unsigned __int64 v52; // r8
  unsigned __int64 v53; // rbx
  __int64 v54; // rdi
  unsigned int v55; // esi
  unsigned int v56; // r11d
  _QWORD *v57; // r10
  unsigned __int64 v58; // rsi
  unsigned __int64 v59; // rdi
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rbx
  __int64 v62; // r13
  int v63; // ecx
  __int64 v64; // rbx
  __int64 v65; // rdi
  signed __int64 v66; // r13
  __int64 v67; // r13
  __int64 v68; // rbx
  __int64 v69; // rcx
  int v70; // r8d
  unsigned int v71; // eax
  _QWORD *v72; // r10
  int v73; // ecx
  __int64 v74; // rsi
  __int64 v75; // r14
  __int64 v76; // rbx
  __int64 v77; // rbx
  __int64 v78; // r8
  __int64 v79; // rbx
  int v80; // esi
  unsigned __int64 v81; // rdi
  char v82; // si
  int v83; // r11d
  unsigned __int64 v84; // rdi
  __int64 v85; // rbx
  char v86; // di
  signed int v87; // r9d
  __int64 v88; // rbx
  __int64 v89; // rbx
  __int64 v90; // rbx
  __int64 v91; // rbx
  __int64 v92; // rcx
  unsigned int v93; // edi
  __int64 v94; // rbx
  unsigned int v95; // esi
  __int64 v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // r9
  __int64 v99; // rcx
  unsigned int v100; // r14d
  int v101; // edi
  int v102; // edi
  int v103; // ebx
  _QWORD *v104; // r10
  unsigned __int64 v105; // rsi
  unsigned __int64 v106; // rdi
  int v107; // r8d
  unsigned int v108; // ebx
  int v109; // r14d
  __int64 v110; // rbx
  unsigned int v111; // r9d
  unsigned int v112; // ebx
  unsigned int v113; // r9d
  _QWORD *v114; // rcx
  unsigned int v115; // r9d
  unsigned int v116; // r13d
  int v117; // r8d
  unsigned int v118; // r14d
  TieringMovementSession **v119; // rsi
  int MovementTables; // eax
  _QWORD *v121; // rcx
  __int64 v122; // rdx
  unsigned __int64 v123; // rdx
  int v124; // r11d
  unsigned __int64 v125; // rdi
  unsigned __int64 v126; // rsi
  _QWORD *v127; // r10
  __int64 v128; // rax
  unsigned int v129; // eax
  unsigned int v130; // eax
  __int64 v131; // r9
  int v132; // ecx
  int v133; // eax
  int v134; // eax
  int v135; // eax
  int v136; // r8d
  char v137; // cl
  int v138; // edx
  int v139; // edx
  int v140; // eax
  int v141; // eax
  int v142; // eax
  unsigned __int16 i; // cx
  JET_ERR v144; // eax
  JET_ERR v145; // r8d
  int v146; // ebx
  int v147; // eax
  _QWORD *v148; // rcx
  __int64 v149; // rdx
  int v150; // esi
  int v151; // r14d
  unsigned __int64 v152; // rax
  unsigned __int64 v153; // rax
  unsigned int v154; // r13d
  __int64 v155; // r15
  __int64 v156; // rdi
  int v157; // ecx
  char v159[4]; // [rsp+80h] [rbp-80h] BYREF
  signed int v160; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 v161; // [rsp+88h] [rbp-78h]
  unsigned __int8 v162[2]; // [rsp+8Ah] [rbp-76h] BYREF
  unsigned __int16 v163[2]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v164; // [rsp+90h] [rbp-70h]
  char v165[4]; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v166; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v167; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v168; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v169; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v170; // [rsp+B0h] [rbp-50h] BYREF
  void *v171; // [rsp+B8h] [rbp-48h]
  __int64 v172; // [rsp+C0h] [rbp-40h]
  unsigned int v173; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v174; // [rsp+CCh] [rbp-34h] BYREF
  __int64 v175; // [rsp+D0h] [rbp-30h] BYREF
  int cRow; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v177; // [rsp+E0h] [rbp-20h]
  __int64 v178; // [rsp+E8h] [rbp-18h]
  int v179; // [rsp+F0h] [rbp-10h]
  int v180; // [rsp+F4h] [rbp-Ch] BYREF
  TieringHeatSession *v181; // [rsp+F8h] [rbp-8h]
  void *Block; // [rsp+100h] [rbp+0h]
  __int64 v183; // [rsp+108h] [rbp+8h]
  __int64 v184; // [rsp+110h] [rbp+10h]
  void *v185; // [rsp+118h] [rbp+18h]
  TieringMovementSession **v186; // [rsp+120h] [rbp+20h]
  __int64 v187; // [rsp+128h] [rbp+28h]
  unsigned __int64 v188; // [rsp+130h] [rbp+30h]
  unsigned __int64 v189; // [rsp+138h] [rbp+38h]
  char v190[8]; // [rsp+140h] [rbp+40h] BYREF
  int v191; // [rsp+148h] [rbp+48h]
  unsigned __int64 v192; // [rsp+150h] [rbp+50h]
  unsigned __int64 v193; // [rsp+158h] [rbp+58h]
  unsigned __int64 v194; // [rsp+160h] [rbp+60h]
  unsigned __int64 v195; // [rsp+168h] [rbp+68h]
  __int64 v196; // [rsp+170h] [rbp+70h]
  __int64 v197; // [rsp+178h] [rbp+78h]
  __int64 v198; // [rsp+180h] [rbp+80h] BYREF
  __int64 v199; // [rsp+188h] [rbp+88h] BYREF
  __int64 v200; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v201; // [rsp+198h] [rbp+98h] BYREF
  __int64 v202; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v203; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v204; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v205; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v206; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 Buf1; // [rsp+1C8h] [rbp+C8h] BYREF
  char v208[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _DWORD *v209; // [rsp+200h] [rbp+100h]
  __int64 v210; // [rsp+208h] [rbp+108h]
  __int64 v211; // [rsp+210h] [rbp+110h]
  _DWORD v212[2]; // [rsp+218h] [rbp+118h] BYREF
  unsigned int *v213; // [rsp+220h] [rbp+120h]
  __int64 v214; // [rsp+228h] [rbp+128h]
  __int64 *v215; // [rsp+230h] [rbp+130h]
  __int64 v216; // [rsp+238h] [rbp+138h]
  __int64 *v217; // [rsp+240h] [rbp+140h]
  __int64 v218; // [rsp+248h] [rbp+148h]
  unsigned __int16 **v219; // [rsp+250h] [rbp+150h]
  __int64 v220; // [rsp+258h] [rbp+158h]
  __int64 *v221; // [rsp+260h] [rbp+160h]
  __int64 v222; // [rsp+268h] [rbp+168h]
  unsigned int *v223; // [rsp+270h] [rbp+170h]
  __int64 v224; // [rsp+278h] [rbp+178h]
  unsigned int *v225; // [rsp+280h] [rbp+180h]
  __int64 v226; // [rsp+288h] [rbp+188h]
  unsigned int *v227; // [rsp+290h] [rbp+190h]
  __int64 v228; // [rsp+298h] [rbp+198h]
  int *p_cRow; // [rsp+2A0h] [rbp+1A0h]
  __int64 v230; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v231; // [rsp+2B0h] [rbp+1B0h]
  __int64 v232; // [rsp+2B8h] [rbp+1B8h]
  __int64 *v233; // [rsp+2C0h] [rbp+1C0h]
  __int64 v234; // [rsp+2C8h] [rbp+1C8h]
  __int64 *v235; // [rsp+2D0h] [rbp+1D0h]
  __int64 v236; // [rsp+2D8h] [rbp+1D8h]
  unsigned __int16 v237[8]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v187 = a4;
  v181 = a3;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::Processing_Pass3";
  CHResultImp::CHResultImp((CHResultImp *)v190);
  v166 = 0;
  v161 = *(_WORD *)(*(_QWORD *)(ulContext + 16) + 142LL);
  Buf1 = 0;
  v169 = 0;
  v162[0] = 0;
  v159[0] = 0;
  v165[0] = 0;
  v163[0] = 0;
  v180 = 0;
  v191 = 0;
  MovementSession = CTieredVolume::GetMovementSession(ulContext);
  v186 = (TieringMovementSession **)MovementSession;
  if ( !MovementSession )
  {
    v10 = -2147019873;
    v191 = -2147019873;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        ulContext + 672,
        159);
    }
    goto LABEL_738;
  }
  v179 = 0;
  v171 = 0;
  v185 = 0;
  v11 = *(_DWORD *)(ulContext + 216);
  v173 = *(_DWORD *)(ulContext + 220);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_iiZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      a6,
      a7,
      ulContext + 672);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 >= 0x1388 )
  {
    v13 = v11;
    if ( v11 > 0x7A120 )
      v13 = 500000;
  }
  else
  {
    v13 = 5000;
  }
  do
  {
    Block = malloc(8LL * v13);
    if ( Block )
    {
      v171 = malloc(8LL * v13);
      if ( v171 )
        break;
      free(Block);
      Block = 0;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      WPP_SF_LLZ(v12[2], 89, v14, v13, v13 >> 1, ulContext + 672);
      v12 = WPP_GLOBAL_Control;
    }
    v13 >>= 1;
  }
  while ( v13 >= 0x64 );
  v168 = v13;
  if ( !Block )
  {
    v15 = v171;
    v10 = -2147024882;
    v191 = -2147024882;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_DSd(
        v12[2],
        90,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        v168,
        *(_QWORD *)(*((_QWORD *)v181 + 5) + 112LL),
        14);
    goto LABEL_730;
  }
  v16 = v168;
  if ( v11 >= v168 )
    v16 = v11;
  LODWORD(v175) = v16;
  v17 = (v168 + v16 - 1) / v168;
  v170 = v17;
  if ( !v17 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      WPP_SF_Z(v12[2], 91, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, ulContext + 672);
      v12 = WPP_GLOBAL_Control;
    }
    v17 = 1;
    v170 = 1;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
  {
    WPP_SF_LLZ(v12[2], 92, v14, v17, v168, ulContext + 672);
    v12 = WPP_GLOBAL_Control;
  }
  memset_0(Block, 0, 8LL * v168);
  v15 = v171;
  memset_0(v171, 0, 8LL * v168);
  v18 = v173;
  if ( v173 < 0x1388 )
    v18 = 5000;
  v19 = v185;
  v20 = 0;
  while ( !v19 )
  {
    v19 = malloc(8LL * v18);
    v185 = v19;
    v21 = v18 >> 1;
    v20 = 0;
    if ( v19 )
      v21 = v18;
    v18 = v21;
    if ( v21 < 0x64 )
    {
      if ( !v19 )
      {
        v10 = -2147024882;
        v191 = -2147024882;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 2u )
        {
          WPP_SF_DSd(
            v12[2],
            93,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            v21,
            *(_QWORD *)(*((_QWORD *)v181 + 5) + 112LL),
            14);
          v19 = v185;
        }
        v185 = v19;
        goto LABEL_729;
      }
      break;
    }
  }
  cRow = 0x80000000;
  v22 = 0x80000000;
  v177 = 0;
  v184 = 0;
  v172 = 0;
  v178 = 0;
  v23 = 0;
  v183 = 0;
  v189 = 0;
  v192 = 0;
  v193 = 0;
  v195 = 0;
  v188 = 0;
  v194 = 0;
  v196 = 0;
  v197 = 0;
  v24 = v18;
  if ( v173 >= v18 )
    v24 = v173;
  v25 = (v18 + v24 - 1) / v18;
  v164 = v25;
  if ( !v25 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      WPP_SF_Z(v12[2], 94, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, ulContext + 672);
      v12 = WPP_GLOBAL_Control;
    }
    v25 = 1;
    v164 = 1;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
  {
    WPP_SF_LLZ(v12[2], 95, v20, v25, v168, ulContext + 672);
    v12 = WPP_GLOBAL_Control;
  }
  memset_0(v185, 0, 8LL * v18);
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_Z(v12[2], 96, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, ulContext + 672);
  *(_DWORD *)(ulContext + 184) = 5;
  if ( (unsigned int)dword_14004C098 > 4
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v206 = *(_QWORD *)(ulContext + 256);
    v204 = *(_QWORD *)(ulContext + 248);
    v173 = v170;
    v167 = v168;
    v160 = *(_DWORD *)(ulContext + 216);
    v205 = a7;
    v199 = a6;
    v200 = v187;
    LOWORD(v174) = *(_WORD *)(*(_QWORD *)(ulContext + 16) + 142LL);
    v201 = (unsigned __int16 *)(ulContext + 696);
    v198 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (unsigned __int16)v174,
      (__int64)byte_140046729,
      v26,
      v27,
      (__int64)&v198,
      &v201,
      (__int64)&v174,
      (__int64)&v200,
      (__int64)&v199,
      (__int64)&v205,
      (__int64)&v160,
      (__int64)&v167,
      (__int64)&v173,
      (__int64)&v204,
      (__int64)&v206);
  }
  LOBYTE(v28) = 0;
  v173 = 0;
  v29 = WPP_GLOBAL_Control;
  v30 = 0;
  v31 = 0;
  while ( 1 )
  {
    if ( *(_BYTE *)(ulContext + 165) != (_BYTE)v28 || *(_BYTE *)(ulContext + 166) != (_BYTE)v28 )
      goto LABEL_152;
    if ( WaitForSingleObject(*(HANDLE *)(ulContext + 768), 0) != 258
      || WaitForSingleObject(*(HANDLE *)(ulContext + 760), 0) != 258 )
    {
      break;
    }
    if ( *(_DWORD *)(ulContext + 184) != 5 )
      goto LABEL_156;
    v32 = *((_QWORD *)v181 + 5);
    if ( *(_BYTE *)(v32 + 77) )
    {
      if ( *(_BYTE *)(v32 + 76) )
        goto LABEL_156;
    }
    v180 = 0;
    v166 = 0;
    v33 = JetMove(*((_QWORD *)v181 + 1), *((_QWORD *)v181 + 3), v22, 0);
    if ( v33 == -1601 || v33 == 1039 || v33 == -1603 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = 97;
LABEL_146:
        WPP_SF_d(v29[2], v45, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v33);
LABEL_156:
        v29 = WPP_GLOBAL_Control;
        goto LABEL_157;
      }
      goto LABEL_157;
    }
    v22 = 1;
    if ( v33 == -1017 )
    {
      LOBYTE(v28) = 0;
      goto LABEL_121;
    }
    if ( v33 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v45 = 98;
        goto LABEL_146;
      }
      goto LABEL_157;
    }
    CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                          v181,
                          1u,
                          (struct TE_FILE_ID_128 *)&Buf1,
                          &v169,
                          v162,
                          (unsigned __int8 *)v159,
                          (unsigned __int8 *)v165,
                          v163,
                          v237);
    v35 = CurrentHeatRecord;
    v28 = 0;
    if ( CurrentHeatRecord == -1017 )
    {
LABEL_121:
      v29 = WPP_GLOBAL_Control;
    }
    else if ( CurrentHeatRecord )
    {
      if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
      {
        v36 = ATL::AtlHresultFromWin32(112);
      }
      else if ( CurrentHeatRecord == -1011 )
      {
        v36 = -2147024882;
      }
      else
      {
        v37 = -CurrentHeatRecord;
        if ( v37 < 0 )
          LOWORD(v37) = v35;
        v36 = v35 & 0x8E5E0000 | (unsigned __int16)v37 | 0xE5E0000;
      }
      v191 = v36;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v35);
        v29 = WPP_GLOBAL_Control;
        v28 = 0;
      }
      if ( v179 >= v28 )
        v179 = v36;
      v23 = v183;
    }
    else
    {
      v38 = memcmp_0(&Buf1, &NullGuid, 0x10u);
      LOBYTE(v28) = 0;
      if ( !v38 )
        goto LABEL_121;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iiiDDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          DWORD2(Buf1),
          Buf1,
          v169,
          v162[0],
          v159[0],
          ulContext + 672);
      }
      ++v173;
      v166 = 0;
      v167 = 0;
      TieringHeatSession::AddCurrentCountAndAgeHistory(
        v181,
        (const struct TE_FILE_ID_128 *)&Buf1,
        v169,
        0,
        v165[0],
        v163[0],
        v159[0],
        v237,
        &v180,
        &v166,
        &v167);
      v39 = v162[0];
      v40 = v163[0];
      LOBYTE(v28) = 0;
      if ( !v163[0] || (v162[0] & 0xF0) != 0 )
      {
        if ( (v159[0] & 0xC) != 0 )
        {
          if ( v163[0] )
          {
            if ( (v159[0] & 8) != 0 )
            {
              v192 += v163[0];
              v195 += v166;
              v30 += v167;
              if ( (v162[0] & 0x20) != 0 )
                v196 += v167;
            }
            else
            {
              v193 += v163[0];
              v194 += v166;
              v31 += v167;
              if ( (v162[0] & 0x10) != 0 )
                v197 += v167;
            }
          }
          goto LABEL_121;
        }
        if ( (v162[0] & 0x80u) != 0 || !v163[0] )
          goto LABEL_121;
        LOBYTE(v39) = v162[0] & 0x10;
        v41 = v166;
        v42 = v166 / v170;
        if ( v166 / v170 >= v168 )
          v42 = v168 - 1;
        if ( (_BYTE)v39 )
        {
          *((_QWORD *)Block + v42) += v163[0];
          v177 += v40;
          v172 += v41;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_iiiDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v39, *((_QWORD *)&Buf1 + 1), Buf1, v169, v40, v42);
            LOWORD(v40) = v163[0];
            v29 = WPP_GLOBAL_Control;
          }
          v43 = v167;
          v188 += v167;
        }
        else
        {
          *((_QWORD *)v171 + v42) += v163[0];
          v184 += v40;
          v178 += v41;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_iiiDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, v39, *((_QWORD *)&Buf1 + 1), Buf1, v169, v40, v42);
            LOWORD(v40) = v163[0];
            v29 = WPP_GLOBAL_Control;
          }
          v43 = v167;
        }
        v44 = v43 / v164;
        if ( v43 / v164 >= v18 )
          v44 = v18 - 1;
        v23 += v43;
        v183 = v23;
        v189 += v43 * (unsigned __int16)v40;
        *((_QWORD *)v185 + v44) += (unsigned __int16)v40;
LABEL_141:
        LOBYTE(v28) = 0;
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiiDDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Buf1),
            Buf1,
            v169,
            v162[0],
            v159[0],
            ulContext + 672);
          v29 = WPP_GLOBAL_Control;
          goto LABEL_141;
        }
      }
    }
  }
  v29 = WPP_GLOBAL_Control;
LABEL_152:
  if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 && *((_BYTE *)v29 + 25) >= 5u )
  {
    WPP_SF_Z(v29[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, ulContext + 672);
    goto LABEL_156;
  }
LABEL_157:
  v46 = *(_DWORD *)(ulContext + 184);
  if ( v46 != 5 )
  {
    v10 = -2138898426;
    v191 = -2138898426;
    if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 && *((_BYTE *)v29 + 25) >= 2u )
      WPP_SF_DZd(v29[2], 104, (unsigned int)&WPP_GLOBAL_Control, v46, ulContext + 144, 6);
    goto LABEL_728;
  }
  *(_QWORD *)(ulContext + 336) = v23 + v31 + v30;
  *(_QWORD *)(ulContext + 344) = v23;
  *(_QWORD *)(ulContext + 352) = v30;
  if ( !v23 )
  {
    *(_DWORD *)(ulContext + 360) = 0;
    memset_0((void *)(ulContext + 368), 0, 0xA0u);
    v57 = WPP_GLOBAL_Control;
LABEL_187:
    v58 = v184;
    goto LABEL_188;
  }
  v47 = v188;
  *(_DWORD *)(ulContext + 360) = 10000 * v188 / v23;
  v48 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_IIZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, (unsigned int)&WPP_GLOBAL_Control, v47, v23, ulContext + 672);
    v48 = WPP_GLOBAL_Control;
  }
  v49 = 20;
  while ( 1 )
  {
    v50 = 5 * v189 * (unsigned int)v49;
    v51 = v50 * (unsigned __int128)0x47AE147AE147AE15uLL;
    v52 = v50 / 0x64;
    v53 = 0;
    v54 = 0;
    LOBYTE(v55) = -95;
    v56 = v18;
    if ( (int)v18 > 0 )
    {
      while ( v52 > v53 )
      {
        *((_QWORD *)&v51 + 1) = *((_QWORD *)v185 + v56 - 1);
        v55 = (v164 >> 1) + v164 * (v56 - 1);
        if ( *((_QWORD *)&v51 + 1) )
        {
          if ( v53 + *((_QWORD *)&v51 + 1) * v55 > v52 )
          {
            v52 -= v53;
            *((_QWORD *)&v51 + 1) = v52 % v55;
            v54 += v52 / v55;
            break;
          }
          v54 += *((_QWORD *)&v51 + 1);
          v53 += *((_QWORD *)&v51 + 1) * v55;
        }
        if ( (int)--v56 <= 0 )
          break;
      }
    }
    if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 1) != 0 && *((_BYTE *)v48 + 25) >= 5u )
      WPP_SF_dILZ(v48[2], DWORD2(v51), v52, 5 * v49, v54, v55, ulContext + 672);
    *(_QWORD *)(ulContext + 8LL * (unsigned int)v49-- + 360) = v54;
    if ( v49 <= 0 )
      break;
    v48 = WPP_GLOBAL_Control;
  }
  v57 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_187;
  v58 = v184;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_IZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v52, v184 + v177, ulContext + 672);
    v57 = WPP_GLOBAL_Control;
  }
LABEL_188:
  if ( v177 )
  {
    v60 = v172;
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 4u )
      {
        WPP_SF_I(v57[2], 108, v52);
        v57 = WPP_GLOBAL_Control;
      }
      if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 4u )
      {
        WPP_SF_I(v57[2], 109, v52);
        v57 = WPP_GLOBAL_Control;
      }
    }
    v59 = v177;
    v188 = v60 / v177;
  }
  else
  {
    LODWORD(v188) = 0;
    v59 = 0;
  }
  if ( v58 )
  {
    v61 = v178;
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 4u )
      {
        WPP_SF_I(v57[2], 110, v52);
        v57 = WPP_GLOBAL_Control;
      }
      if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 4u )
      {
        WPP_SF_I(v57[2], 111, v52);
        v57 = WPP_GLOBAL_Control;
      }
    }
    v189 = v61 / v58;
  }
  else
  {
    LODWORD(v189) = 0;
  }
  v62 = 0;
  if ( a6 >= 1024 )
    v62 = a6 - 1024;
  v172 = v62;
  v63 = v187;
  v64 = v187 - v62 - v59 - a8;
  v65 = 0;
  if ( g_IsClientSku )
  {
    v52 = *(_QWORD *)(ulContext + 16);
    v65 = v187 * (unsigned __int64)*(unsigned __int8 *)(v52 + 148) / 0x64;
    if ( v65 > *(_QWORD *)(v52 + 152) / (__int64)*(unsigned int *)(ulContext + 316) )
      v65 = *(_QWORD *)(v52 + 152) / (__int64)*(unsigned int *)(ulContext + 316);
    v63 = v187;
  }
  if ( v57 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IZ(v57[2], 112, v52, v63, ulContext + 672);
      v57 = WPP_GLOBAL_Control;
    }
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
      {
        WPP_SF_q(v57[2], 113, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, a5 / *(unsigned int *)(ulContext + 316));
        v57 = WPP_GLOBAL_Control;
      }
      if ( v57 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
        {
          WPP_SF_q(v57[2], 114, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v62);
          v57 = WPP_GLOBAL_Control;
        }
        if ( v57 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
          {
            WPP_SF_q(v57[2], 115, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v177);
            v57 = WPP_GLOBAL_Control;
          }
          if ( v57 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
            {
              WPP_SF_q(v57[2], 116, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v64);
              v57 = WPP_GLOBAL_Control;
            }
            if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
            {
              WPP_SF_q(v57[2], 117, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v65);
              v57 = WPP_GLOBAL_Control;
            }
          }
        }
      }
    }
  }
  if ( v64 >= 0 )
  {
LABEL_245:
    if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IZ(v57[2], 119, v52, v187, ulContext + 672);
      v57 = WPP_GLOBAL_Control;
    }
  }
  else if ( v57 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_(v57[2], 118, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids);
      v57 = WPP_GLOBAL_Control;
    }
    goto LABEL_245;
  }
  v66 = v187 - a5 / *(unsigned int *)(ulContext + 316);
  if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
  {
    WPP_SF_IZ(v57[2], 120, v52, v66, ulContext + 672);
    v57 = WPP_GLOBAL_Control;
  }
  if ( v66 <= v65 )
    v67 = 0;
  else
    v67 = v66 - v65;
  if ( v57 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IIZ(v57[2], 121, v52, v67, v65, ulContext + 672);
      v57 = WPP_GLOBAL_Control;
    }
    if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IDZ(v57[2], 122, v52, v67, v161, ulContext + 672);
      v57 = WPP_GLOBAL_Control;
    }
  }
  if ( v67 < 0 )
  {
    v68 = 0;
    v183 = 0;
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
      {
        WPP_SF_I(v57[2], 123, v52);
        goto LABEL_269;
      }
      goto LABEL_277;
    }
LABEL_283:
    v67 = 0;
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
      {
        WPP_SF_I(v57[2], 126, v52);
        goto LABEL_294;
      }
      goto LABEL_295;
    }
    goto LABEL_299;
  }
  v68 = v67;
  v183 = v67;
  if ( !v67 )
  {
    v183 = 0;
    goto LABEL_277;
  }
  v52 = v161;
  if ( (unsigned __int16)(v161 - 1) > 0x62u )
  {
LABEL_278:
    if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IDZ(v57[2], 125, v52, v67, v52, ulContext + 672);
      v57 = WPP_GLOBAL_Control;
    }
    if ( v67 < 0 )
      goto LABEL_283;
    LODWORD(v52) = v161;
  }
  else
  {
    v69 = v67 * v161;
    v68 = v69 / 100;
    v183 = v69 / 100;
    if ( v57 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
      {
        WPP_SF_ID(
          v57[2],
          (unsigned __int128)(v69 * (__int128)(__int64)0xA3D70A3D70A3D70BuLL) >> 64,
          v161,
          v69 / 100,
          v161);
LABEL_269:
        v57 = WPP_GLOBAL_Control;
LABEL_277:
        v52 = v161;
      }
      goto LABEL_278;
    }
  }
  if ( !v67 || (unsigned __int16)(v52 - 1) > 0x62u )
    goto LABEL_295;
  v67 = v67 * (unsigned __int16)v52 / 100;
  if ( v57 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
    {
      WPP_SF_IDZ(v57[2], 127, v52, v67, v52, ulContext + 672);
LABEL_294:
      v57 = WPP_GLOBAL_Control;
    }
LABEL_295:
    if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 5u )
      WPP_SF_dZ(v57[2], 128, (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v170, ulContext + 672);
  }
LABEL_299:
  v70 = 0;
  *(_QWORD *)(ulContext + 192) = 0;
  v71 = (unsigned int)v175 / v170 + 1;
  v167 = v71;
  if ( v71 >= v168 )
    v71 = v168 - 1;
  v160 = v71;
  *(_QWORD *)(ulContext + 200) = 0;
  v72 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v73) = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_LLZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, 0, 0, 0, ulContext + 672);
      v73 = *(_DWORD *)(ulContext + 192);
      v72 = WPP_GLOBAL_Control;
    }
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_LLZ(v72[2], 130, v70, v160, v73, ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
  }
  if ( v68 <= 0 )
  {
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_IZ(v72[2], 131, v70, v177, ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
    LOBYTE(v161) = 1;
    v74 = v177;
    v164 = v167;
    goto LABEL_495;
  }
  v175 = 0;
  v75 = 0;
  v178 = 0;
  LOBYTE(v174) = 0;
  LOBYTE(v161) = 0;
  v164 = 0;
  v76 = a5 / *(unsigned int *)(ulContext + 316) - a8;
  if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
  {
    WPP_SF_IZ(v72[2], 132, v70, v76, ulContext + 672);
    v72 = WPP_GLOBAL_Control;
  }
  v77 = v65 + v76;
  if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
  {
    WPP_SF_IZ(v72[2], 133, v70, v77, ulContext + 672);
    v72 = WPP_GLOBAL_Control;
  }
  v78 = v172;
  if ( v77 <= 0 )
    goto LABEL_359;
  if ( v77 <= v172 )
  {
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_iiZ(
        v72[2],
        135,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        v77,
        v172,
        ulContext + 672);
      v72 = WPP_GLOBAL_Control;
      v78 = v172;
    }
    v78 -= v77;
LABEL_359:
    v172 = v78;
    goto LABEL_360;
  }
  if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
  {
    WPP_SF_iiZ(v72[2], 134, (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v77, v172, ulContext + 672);
    v72 = WPP_GLOBAL_Control;
    v78 = v172;
  }
  v79 = v77 - v78;
  v78 = 0;
  v172 = 0;
  if ( v79 > 0 )
  {
    v80 = v177;
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_IZ(v72[2], 136, 0, v79, ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
    LODWORD(v78) = 0;
    while ( (unsigned int)v78 < v168 )
    {
      v81 = *((_QWORD *)Block + (int)v78);
      if ( v81 > v79 )
      {
        *(_QWORD *)(ulContext + 200) = v79;
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_353;
        v80 -= v79;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_DIZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, v78, v78, 0, ulContext + 672);
          v72 = WPP_GLOBAL_Control;
        }
        break;
      }
      if ( v81 )
      {
        if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          WPP_SF_DIZ(v72[2], 138, v78, v78, v81, ulContext + 672);
          v72 = WPP_GLOBAL_Control;
          LODWORD(v78) = v164;
        }
        v79 -= v81;
        v80 -= v81;
      }
      LODWORD(v78) = v78 + 1;
      v164 = v78;
      if ( v79 <= 0 )
        break;
    }
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_IZ(v72[2], 139, v78, v80, ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
LABEL_353:
    v172 = 0;
    v82 = 0;
LABEL_389:
    v83 = v160;
    goto LABEL_390;
  }
LABEL_360:
  v83 = v160;
  v82 = 0;
  while ( v83 >= 0 )
  {
    if ( v82 || v78 <= 0 )
      break;
    v84 = *((_QWORD *)v171 + (unsigned int)v83);
    if ( v84 )
    {
      if ( v78 >= v84 )
      {
        v85 = *((_QWORD *)v171 + (unsigned int)v83);
      }
      else
      {
        v85 = v78;
        if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          WPP_SF_IZ(v72[2], 140, v78, v75, ulContext + 672);
          v72 = WPP_GLOBAL_Control;
        }
      }
      if ( v85 + v75 > (unsigned __int64)v67 )
      {
        if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          WPP_SF_IIIZ(v72[2], 141, v78, v85 + v75, v75 + v85 - v67, v67, ulContext + 672);
          v72 = WPP_GLOBAL_Control;
        }
        v85 = v67 - v75;
        v82 = 1;
      }
      if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        WPP_SF_IDZ(v72[2], 142, v78, v85, v160, ulContext + 672);
      v75 += v85;
      v78 = v172 - v85;
      v172 -= v85;
      v83 = v160;
      if ( v85 == v84 )
      {
        v83 = --v160;
        v85 = 0;
      }
      *(_QWORD *)(ulContext + 192) = v85;
      v72 = WPP_GLOBAL_Control;
    }
    else
    {
      v160 = --v83;
    }
  }
  if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
  {
    WPP_SF_LLZ(v72[2], 143, v78, v83, *(_DWORD *)(ulContext + 192), ulContext + 672);
    v72 = WPP_GLOBAL_Control;
    goto LABEL_389;
  }
LABEL_390:
  if ( v83 >= 0 )
  {
    v86 = v174;
    do
    {
      v78 = v175;
      if ( v82 && v175 >= v178 )
        break;
      if ( v175 <= v178 )
      {
        v87 = v164;
      }
      else
      {
        if ( !v86 )
        {
          if ( (int)v164 > v83 )
            break;
LABEL_399:
          v88 = *((_QWORD *)v171 + (unsigned int)v83);
          if ( !v88 )
          {
            v160 = --v83;
            continue;
          }
          v89 = v88 - *(_QWORD *)(ulContext + 192);
          if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
          {
            WPP_SF_IDZ(v72[2], 146, v175, v89, v83, ulContext + 672);
            v83 = v160;
          }
          v75 += v89;
          if ( v75 <= v67 )
          {
            v160 = v83 - 1;
            *(_QWORD *)(ulContext + 192) = 0;
            v72 = WPP_GLOBAL_Control;
          }
          else
          {
            v89 = v67 + v89 - v75;
            *(_QWORD *)(ulContext + 192) += v89;
            v72 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_IIIZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, v78, v75, v75 - v67, v67, ulContext + 672);
              v72 = WPP_GLOBAL_Control;
            }
            v75 = v67;
            v82 = 1;
          }
          if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
          {
            WPP_SF_IZ(v72[2], 148, v78, v89, ulContext + 672);
            v72 = WPP_GLOBAL_Control;
          }
          v178 += v89;
LABEL_433:
          v83 = v160;
          continue;
        }
        v87 = v164;
        if ( (int)v164 < v83 )
          goto LABEL_399;
      }
      if ( v86 || v87 >= v83 )
        break;
      if ( v175 > v178 )
        goto LABEL_399;
      v90 = *((_QWORD *)Block + v87);
      if ( v90 )
      {
        v91 = v90 - *(_QWORD *)(ulContext + 200);
        if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          WPP_SF_IDZ(v72[2], 144, v175, v91, v87, ulContext + 672);
          v78 = v175;
          v87 = v164;
          v83 = v160;
        }
        v78 += v91;
        v175 = v78;
        v92 = v183;
        if ( v78 > v183 )
        {
          *(_QWORD *)(ulContext + 200) += v183 + v91 - v78;
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_IIIZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              145,
              v78,
              v78,
              v91 - *(_BYTE *)(ulContext + 200),
              v92,
              ulContext + 672);
            v72 = WPP_GLOBAL_Control;
            v92 = v183;
          }
          v175 = v92;
          v86 = 1;
          goto LABEL_433;
        }
        v164 = v87 + 1;
        *(_QWORD *)(ulContext + 200) = 0;
        v72 = WPP_GLOBAL_Control;
      }
      else
      {
        v164 = v87 + 1;
      }
    }
    while ( v83 >= 0 );
  }
  if ( v72 == &WPP_GLOBAL_Control )
    goto LABEL_444;
  if ( (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
  {
    WPP_SF_LLZ(v72[2], 149, v78, v164, *(_DWORD *)(ulContext + 200), ulContext + 672);
    v72 = WPP_GLOBAL_Control;
  }
  if ( v72 == &WPP_GLOBAL_Control || (*((_BYTE *)v72 + 28) & 1) == 0 )
  {
LABEL_444:
    v93 = v160;
  }
  else
  {
    v93 = v160;
    if ( *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_LLZ(v72[2], 150, v78, v160, *(_DWORD *)(ulContext + 192), ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
  }
  v94 = v178;
  v74 = v175;
  if ( v175 <= v178 )
  {
    if ( v175 < v178 )
    {
      if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
      {
        WPP_SF_LLZ(v72[2], 156, v78, v175, v178, ulContext + 672);
        v72 = WPP_GLOBAL_Control;
      }
      if ( !*(_QWORD *)(ulContext + 192) )
      {
        do
          v99 = *((_QWORD *)v171 + (int)++v93);
        while ( !v99 );
        v160 = v93;
        *(_QWORD *)(ulContext + 192) = v99;
        v72 = WPP_GLOBAL_Control;
        v74 = v175;
      }
      if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        WPP_SF_LZ(v72[2], 157, v78, *(_DWORD *)(ulContext + 192), ulContext + 672);
      *(_QWORD *)(ulContext + 192) += v74 - v94;
      v72 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            158,
            &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            ulContext + 672);
          v72 = WPP_GLOBAL_Control;
        }
        if ( v72 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
          {
            WPP_SF_d(v72[2], 159, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v93);
            v72 = WPP_GLOBAL_Control;
          }
          if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
          {
            v97 = 160;
            v98 = *(unsigned int *)(ulContext + 192);
            goto LABEL_494;
          }
        }
      }
    }
  }
  else
  {
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
    {
      WPP_SF_LLZ(v72[2], 151, v78, v175, v178, ulContext + 672);
      v72 = WPP_GLOBAL_Control;
    }
    if ( !*(_QWORD *)(ulContext + 200) )
    {
      v95 = v164;
      do
        v96 = *((_QWORD *)Block + (int)--v95);
      while ( !v96 );
      v164 = v95;
      *(_QWORD *)(ulContext + 200) = v96;
      v72 = WPP_GLOBAL_Control;
      v94 = v178;
      v74 = v175;
    }
    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
      WPP_SF_LZ(v72[2], 152, v78, *(_DWORD *)(ulContext + 200), ulContext + 672);
    *(_QWORD *)(ulContext + 200) += v94 - v74;
    v74 = v94;
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
          ulContext + 672);
        v72 = WPP_GLOBAL_Control;
      }
      if ( v72 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          WPP_SF_d(v72[2], 154, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v164);
          v72 = WPP_GLOBAL_Control;
        }
        if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 && *((_BYTE *)v72 + 25) >= 5u )
        {
          v97 = 155;
          v98 = *(unsigned int *)(ulContext + 200);
LABEL_494:
          WPP_SF_d(v72[2], v97, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v98);
          v72 = WPP_GLOBAL_Control;
        }
      }
    }
  }
LABEL_495:
  v174 = v170 * v164;
  v100 = v170 >> 1;
  LODWORD(v175) = v170 >> 1;
  v101 = v170 >> 1;
  if ( !*(_QWORD *)(ulContext + 200) )
    v101 = -1;
  v102 = v170 * v164 + v101;
  if ( *(_QWORD *)(ulContext + 192) )
    v103 = v100 + v170 * v160;
  else
    v103 = v170 * (v160 + 1);
  if ( v103 <= 0 )
    v103 = 1;
  if ( v74 > 0
    && v102 > v103
    && v72 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v72 + 28) & 1) != 0
    && *((_BYTE *)v72 + 25) >= 3u )
  {
    WPP_SF_DDZ(v72[2], 161, (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v103, v102, ulContext + 672);
  }
  if ( v102 < 0 )
    v102 = 0;
  *(_DWORD *)(ulContext + 228) = v102;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DIDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, (unsigned __int8)v161, v102, v74, v161, ulContext + 672);
  }
  *(_DWORD *)(ulContext + 224) = v103;
  v104 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DIDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, (unsigned __int8)v161, v103, v74, v161, ulContext + 672);
    v104 = WPP_GLOBAL_Control;
  }
  v105 = 0;
  v106 = 2 * v187;
  v107 = v177;
  if ( 2 * v187 <= v192 + v177 )
  {
    if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 && *((_BYTE *)v104 + 25) >= 4u )
    {
      WPP_SF_IIIZ(v104[2], 164, v177, v192, v177, v187, ulContext + 672);
      v104 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v106 = v106 - v192 - v177;
  }
  if ( v167 < v168 )
  {
    v108 = v167;
  }
  else
  {
    v108 = v168 - 1;
    v167 = v168 - 1;
  }
  if ( v106 )
  {
    v109 = v167;
    do
    {
      if ( v109 <= 0 )
        break;
      if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 && *((_BYTE *)v104 + 25) >= 5u )
      {
        WPP_SF_d(v104[2], 165, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, (unsigned int)v109);
        v104 = WPP_GLOBAL_Control;
      }
      v110 = *((_QWORD *)v171 + v109);
      if ( v110 )
      {
        if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 && *((_BYTE *)v104 + 25) >= 5u )
        {
          WPP_SF_IDZ(v104[2], 166, v107, v110, v170 * v109, ulContext + 672);
          v104 = WPP_GLOBAL_Control;
        }
        v105 += v110;
      }
      --v109;
    }
    while ( v105 < v106 );
    v167 = v109;
    v100 = v175;
    v108 = v167;
  }
  if ( v104 != &WPP_GLOBAL_Control && (*((_BYTE *)v104 + 28) & 1) != 0 && *((_BYTE *)v104 + 25) >= 5u )
    WPP_SF_d(v104[2], 167, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v108);
  v111 = v108 + 1;
  v112 = v170;
  v113 = v100 + v170 * v111;
  *(_DWORD *)(ulContext + 212) = v113;
  v114 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      168,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      v113,
      ulContext + 672);
    v114 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)(ulContext + 212)
    && v114 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v114 + 28) & 1) != 0
    && *((_BYTE *)v114 + 25) >= 4u )
  {
    WPP_SF_dZ(v114[2], 169, (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, 0, ulContext + 672);
    v114 = WPP_GLOBAL_Control;
  }
  v115 = *(_DWORD *)(ulContext + 224);
  if ( *(_DWORD *)(ulContext + 212) > v115 )
  {
    *(_DWORD *)(ulContext + 212) = v115;
    v114 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        170,
        (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
        v115,
        ulContext + 672);
      v114 = WPP_GLOBAL_Control;
    }
  }
  v116 = v112 * (v160 + 1);
  if ( v160 < 0 )
    v117 = 0;
  else
    v117 = v112 * v160;
  v160 = v117;
  v118 = v112 * (v164 + 1);
  if ( v114 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v114 + 28) & 1) != 0 && *((_BYTE *)v114 + 25) >= 5u )
    {
      WPP_SF_LLZ(v114[2], 171, v117, v116, v117, ulContext + 672);
      v114 = WPP_GLOBAL_Control;
    }
    if ( v114 != &WPP_GLOBAL_Control && (*((_BYTE *)v114 + 28) & 1) != 0 && *((_BYTE *)v114 + 25) >= 5u )
      WPP_SF_LLZ(v114[2], 172, v117, v174, v118, ulContext + 672);
  }
  v119 = v186;
  if ( TieringMovementSession::AreMovementTablesPresent(*v186) )
  {
    MovementTables = TieringMovementSession::DeleteMovementTables(*v119);
    v10 = MovementTables;
    v191 = MovementTables;
    if ( MovementTables < 0 )
    {
      v121 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_728;
      }
      v122 = 173;
      goto LABEL_577;
    }
  }
  MovementTables = TieringMovementSession::CreateMovementTables(*v119);
  v10 = MovementTables;
  v191 = MovementTables;
  LOBYTE(v124) = 0;
  if ( MovementTables < 0 )
  {
    v121 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_728;
    }
    v122 = 174;
LABEL_577:
    WPP_SF_d(v121[2], v122, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, (unsigned int)MovementTables);
    goto LABEL_728;
  }
  v125 = 0;
  v126 = 0;
  v127 = WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( *(_BYTE *)(ulContext + 165) != (_BYTE)v124 || *(_BYTE *)(ulContext + 166) != (_BYTE)v124 )
      goto LABEL_705;
    if ( WaitForSingleObject(*(HANDLE *)(ulContext + 768), 0) != 258
      || WaitForSingleObject(*(HANDLE *)(ulContext + 760), 0) != 258 )
    {
      v127 = WPP_GLOBAL_Control;
LABEL_705:
      if ( v127 != &WPP_GLOBAL_Control && (*((_BYTE *)v127 + 28) & 1) != 0 && *((_BYTE *)v127 + 25) >= 5u )
        WPP_SF_Z(v127[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, ulContext + 672);
      goto LABEL_709;
    }
    if ( *(_DWORD *)(ulContext + 184) != 5 )
      goto LABEL_709;
    v128 = *((_QWORD *)v181 + 5);
    LODWORD(v123) = 0;
    if ( *(_BYTE *)(v128 + 77) )
    {
      if ( *(_BYTE *)(v128 + 76) )
        goto LABEL_709;
    }
    v180 = 0;
    v166 = 0;
    v129 = JetMove(*((_QWORD *)v181 + 1), *((_QWORD *)v181 + 3), cRow, 0);
    if ( v129 == -1601 || v129 == 1039 || v129 == -1603 )
      break;
    cRow = 1;
    if ( v129 == -1017 )
    {
      LOBYTE(v124) = 0;
      goto LABEL_684;
    }
    if ( v129 )
    {
      v148 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v149 = 176;
LABEL_699:
        WPP_SF_d(v148[2], v149, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v129);
        goto LABEL_709;
      }
      goto LABEL_709;
    }
    v130 = TieringHeatSession::GetCurrentHeatRecord(
             v181,
             1u,
             (struct TE_FILE_ID_128 *)&Buf1,
             &v169,
             v162,
             (unsigned __int8 *)v159,
             (unsigned __int8 *)v165,
             v163,
             v237);
    v131 = v130;
    LOBYTE(v124) = 0;
    if ( v130 == -1017 )
    {
LABEL_684:
      v127 = WPP_GLOBAL_Control;
    }
    else if ( v130 )
    {
      if ( v130 == -529 || v130 == -1092 || v130 == -1808 )
      {
        v132 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v130 == -1011 )
      {
        v132 = -2147024882;
      }
      else
      {
        v133 = -v130;
        if ( v133 < 0 )
          LOWORD(v133) = v131;
        v132 = v131 & 0x8E5E0000 | (unsigned __int16)v133 | 0xE5E0000;
      }
      v191 = v132;
      v127 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids, v131);
        goto LABEL_619;
      }
    }
    else
    {
      v134 = memcmp_0(&Buf1, &NullGuid, 0x10u);
      LOBYTE(v124) = 0;
      if ( !v134 && !v169 )
        goto LABEL_684;
      v166 = 0;
      TieringHeatSession::AddCurrentCountAndAgeHistory(
        v181,
        (const struct TE_FILE_ID_128 *)&Buf1,
        v169,
        0,
        v165[0],
        v163[0],
        v159[0],
        v237,
        &v180,
        &v166,
        0);
      LODWORD(v123) = v162[0];
      LOBYTE(v124) = 0;
      if ( !v163[0] || (v162[0] & 0xF0) != 0 )
      {
        if ( (v159[0] & 0xC) != 0 || (v162[0] & 0x80u) != 0 || !v163[0] )
          goto LABEL_684;
        if ( (v162[0] & 0x10) != 0 )
        {
          if ( v166 >= v174 )
          {
            if ( v166 >= v118 || v125 >= *(_QWORD *)(ulContext + 200) )
              goto LABEL_684;
            v140 = TieringMovementSession::AddMovementRecord(
                     *v186,
                     *((_QWORD *)*v186 + 2),
                     v166,
                     (const struct TE_FILE_ID_128 *)&Buf1,
                     v169);
            v137 = v140;
            LOBYTE(v124) = 0;
            if ( v140 )
            {
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v138 = 181;
                goto LABEL_630;
              }
            }
            else
            {
              v125 += v163[0];
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_iiiLLZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  182,
                  v136,
                  DWORD2(Buf1),
                  Buf1,
                  v169,
                  v166,
                  v125,
                  ulContext + 672);
                goto LABEL_619;
              }
            }
          }
          else
          {
            v135 = TieringMovementSession::AddMovementRecord(
                     *v186,
                     *((_QWORD *)*v186 + 2),
                     v166,
                     (const struct TE_FILE_ID_128 *)&Buf1,
                     v169);
            v137 = v135;
            LOBYTE(v124) = 0;
            if ( v135 )
            {
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v138 = 179;
LABEL_630:
                WPP_SF_iiiLZL(v127[2], v138, v136, DWORD2(Buf1), Buf1, v169, v166, ulContext + 672, v137);
                goto LABEL_619;
              }
            }
            else
            {
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                v139 = 180;
LABEL_656:
                WPP_SF_iiiLZ(v127[2], v139, v136, DWORD2(Buf1), Buf1, v169, v166, ulContext + 672);
                goto LABEL_619;
              }
            }
          }
        }
        else if ( v166 < v116 )
        {
          if ( v166 < v160 || v126 >= *(_QWORD *)(ulContext + 192) )
          {
            if ( v166 >= *(_DWORD *)(ulContext + 212) )
              goto LABEL_684;
            for ( i = 0; i < 7u; ++i )
            {
              LODWORD(v123) = 0xFFFF;
              if ( v237[i] == 0xFFFF )
                break;
            }
            if ( i <= 3u )
              goto LABEL_684;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_iiiDZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                187,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Buf1),
                Buf1,
                v169,
                v166,
                ulContext + 672);
            }
            v144 = JetDelete(*((_QWORD *)v181 + 1), *((_QWORD *)v181 + 3));
            v145 = v144;
            v124 = 0;
            switch ( v144 )
            {
              case 0:
                goto LABEL_684;
              case -529:
              case -1092:
              case -1808:
                v146 = ATL::AtlHresultFromWin32(112);
                break;
              case -1011:
                v146 = -2147024882;
                break;
              default:
                v147 = -v144;
                if ( v147 < 0 )
                  LOWORD(v147) = v145;
                v146 = v145 & 0x8E5E0000 | (unsigned __int16)v147 | 0xE5E0000;
                break;
            }
            v191 = v146;
            v127 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiiZL(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                188,
                (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
                DWORD2(Buf1),
                Buf1,
                v169,
                ulContext + 672,
                v145);
              v127 = WPP_GLOBAL_Control;
              v124 = 0;
            }
            if ( v179 >= v124 )
              v179 = v146;
          }
          else
          {
            v142 = TieringMovementSession::AddMovementRecord(
                     *v186,
                     *((_QWORD *)*v186 + 3),
                     v166,
                     (const struct TE_FILE_ID_128 *)&Buf1,
                     v169);
            v137 = v142;
            LOBYTE(v124) = 0;
            if ( v142 )
            {
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v138 = 185;
                goto LABEL_630;
              }
            }
            else
            {
              v126 += v163[0];
              v127 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_iiiLLZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  186,
                  v136,
                  DWORD2(Buf1),
                  Buf1,
                  v169,
                  v166,
                  v126,
                  ulContext + 672);
LABEL_619:
                v127 = WPP_GLOBAL_Control;
                LOBYTE(v124) = 0;
              }
            }
          }
        }
        else
        {
          v141 = TieringMovementSession::AddMovementRecord(
                   *v186,
                   *((_QWORD *)*v186 + 3),
                   v166,
                   (const struct TE_FILE_ID_128 *)&Buf1,
                   v169);
          v137 = v141;
          LOBYTE(v124) = 0;
          if ( v141 )
          {
            v127 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v138 = 183;
              goto LABEL_630;
            }
          }
          else
          {
            v127 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v139 = 184;
              goto LABEL_656;
            }
          }
        }
      }
      else
      {
        v127 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_iiiDDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            178,
            (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
            DWORD2(Buf1),
            Buf1,
            v169,
            v162[0],
            v159[0],
            ulContext + 672);
          goto LABEL_619;
        }
      }
    }
  }
  v148 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v149 = 175;
    goto LABEL_699;
  }
LABEL_709:
  v150 = v189;
  *(_DWORD *)(ulContext + 304) = v189;
  v151 = v188;
  *(_DWORD *)(ulContext + 308) = v188;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      189,
      (unsigned int)&WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids,
      v151,
      v150,
      ulContext + 672);
  }
  if ( v193 )
  {
    v152 = v194 / v193;
    v123 = v194 % v193;
  }
  else
  {
    LODWORD(v152) = 0;
  }
  *(_DWORD *)(ulContext + 296) = v152;
  if ( v192 )
  {
    v153 = v195 / v192;
    v123 = v195 % v192;
  }
  else
  {
    LODWORD(v153) = 0;
  }
  *(_DWORD *)(ulContext + 300) = v153;
  v10 = 0;
  v191 = 0;
  v154 = v173;
  *(_DWORD *)(ulContext + 208) = v173;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v155 = a7;
    v156 = v172;
  }
  else
  {
    v155 = a7;
    v156 = v172;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_IIDZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v123, 0, v172, a7, *(_DWORD *)(ulContext + 312), ulContext + 672);
  }
  if ( (unsigned int)dword_14004C098 > 5
    && (qword_14004C0A8 & 0x400000000000LL) != 0
    && (qword_14004C0B0 & 0x400000000000LL) == qword_14004C0B0 )
  {
    v203 = v196;
    v202 = v197;
    LODWORD(v175) = v150;
    cRow = v151;
    v173 = *(_DWORD *)(ulContext + 212);
    v167 = *(_DWORD *)(ulContext + 228);
    v170 = *(_DWORD *)(ulContext + 224);
    v198 = v184;
    v201 = (unsigned __int16 *)v177;
    v200 = v155;
    v199 = v156;
    v168 = v154;
    v235 = &v203;
    v236 = 8;
    v233 = &v202;
    v234 = 8;
    v231 = &v175;
    v232 = 4;
    p_cRow = &cRow;
    v230 = 4;
    v227 = &v173;
    v228 = 4;
    v225 = &v167;
    v226 = 4;
    v223 = &v170;
    v224 = 4;
    v221 = &v198;
    v222 = 8;
    v219 = &v201;
    v220 = 8;
    v217 = &v200;
    v218 = 8;
    v215 = &v199;
    v216 = 8;
    v213 = &v168;
    v214 = 4;
    v209 = v212;
    v210 = 2;
    v157 = *(unsigned __int16 *)(ulContext + 696);
    v211 = *(_QWORD *)(ulContext + 704);
    v212[0] = v157;
    v212[1] = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, byte_1400465D5, 0, 0, 16, v208);
  }
LABEL_728:
  v15 = v171;
LABEL_729:
  free(Block);
LABEL_730:
  if ( v15 )
    free(v15);
  if ( v185 )
    free(v185);
  MovementSession = (CTieredVolume::CSmartTieringMovementSession *)v186;
  if ( v10 >= 0 )
  {
    if ( v179 < 0 )
      v10 = v179;
    v191 = v10;
  }
LABEL_738:
  if ( MovementSession )
  {
    CTieredVolume::CSmartTieringMovementSession::~CSmartTieringMovementSession(MovementSession);
    operator delete(MovementSession);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v190);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140031e04  mov     [rsp-8+arg_8], rbx
0x140031e09  push    rbp
0x140031e0a  push    rsi
0x140031e0b  push    rdi
0x140031e0c  push    r12
0x140031e0e  push    r13
0x140031e10  push    r14
0x140031e12  push    r15
0x140031e14  lea     rbp, [rsp-200h]
0x140031e1c  sub     rsp, 300h
0x140031e23  mov     rax, cs:__security_cookie
0x140031e2a  xor     rax, rsp
0x140031e2d  mov     [rbp+230h+var_40], rax
0x140031e34  mov     [rbp+230h+var_208], r9
0x140031e38  mov     [rbp+230h+var_238], r8
0x140031e3c  mov     r12, rcx
0x140031e3f  mov     ecx, 8
0x140031e44  mov     rax, gs:58h
0x140031e4d  mov     rdx, [rax]
0x140031e50  lea     rax, aCtieredvolumeP_0; "CTieredVolume::Processing_Pass3"
0x140031e57  mov     [rcx+rdx], rax
0x140031e5b  lea     rcx, [rbp+230h+var_1F0]; this
0x140031e5f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140031e64  nop
0x140031e65  xor     r14d, r14d
0x140031e68  mov     [rbp+230h+var_298], r14d
0x140031e6c  mov     rax, [r12+10h]
0x140031e71  movzx   eax, word ptr [rax+8Eh]
0x140031e78  mov     [rbp+230h+var_2A8], ax
0x140031e7c  xorps   xmm0, xmm0
0x140031e7f  movups  [rbp+230h+Buf1], xmm0
0x140031e86  mov     [rbp+230h+var_288], r14
0x140031e8a  mov     [rbp+230h+var_2A6], r14b
0x140031e8e  mov     [rbp+230h+var_2B0], r14b
0x140031e92  mov     [rbp+230h+var_29C], r14b
0x140031e96  mov     [rbp+230h+var_2A4], r14w
0x140031e9b  mov     [rbp+230h+var_23C], r14d
0x140031e9f  mov     [rbp+230h+var_1E8], r14d
0x140031ea3  mov     rcx, r12; ulContext
0x140031ea6  call    ?GetMovementSession@CTieredVolume@@QEAAPEAVCSmartTieringMovementSession@1@XZ; CTieredVolume::GetMovementSession(void)
0x140031eab  mov     rdi, rax
0x140031eae  mov     [rbp+230h+var_210], rax
0x140031eb2  test    rax, rax
0x140031eb5  jnz     short loc_140031F0E
0x140031eb7  mov     ebx, 8007139Fh
0x140031ebc  mov     [rbp+230h+var_1E8], ebx
0x140031ebf  lea     rax, WPP_GLOBAL_Control
0x140031ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ecd  cmp     rcx, rax
0x140031ed0  jz      loc_140034F50
0x140031ed6  test    byte ptr [rcx+1Ch], 1
0x140031eda  jz      loc_140034F50
0x140031ee0  cmp     byte ptr [rcx+19h], 2
0x140031ee4  jb      loc_140034F50
0x140031eea  lea     r9, [r12+2A0h]
0x140031ef2  lea     edx, [rdi+57h]
0x140031ef5  mov     dword ptr [rsp+330h+var_310], ebx
0x140031ef9  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140031f00  mov     rcx, [rcx+10h]
0x140031f04  call    WPP_SF_Zd
0x140031f09  jmp     loc_140034F50
0x140031f0e  mov     [rbp+230h+var_240], r14d
0x140031f12  mov     [rbp+230h+var_278], r14
0x140031f16  mov     [rbp+230h+var_218], r14
0x140031f1a  mov     ebx, [r12+0D8h]
0x140031f22  mov     r14d, [r12+0DCh]
0x140031f2a  mov     [rbp+230h+var_268], r14d
0x140031f2e  lea     r13, WPP_GLOBAL_Control
0x140031f35  mov     r15d, 1
0x140031f3b  mov     rdi, cs:WPP_GLOBAL_Control
0x140031f42  cmp     rdi, r13
0x140031f45  jz      short loc_140031F8E
0x140031f47  test    [rdi+1Ch], r15b
0x140031f4b  jz      short loc_140031F8E
0x140031f4d  cmp     byte ptr [rdi+19h], 4
0x140031f51  jb      short loc_140031F8E
0x140031f53  lea     rax, [r12+2A0h]
0x140031f5b  lea     edx, [r15+57h]
0x140031f5f  mov     [rsp+330h+var_308], rax
0x140031f64  mov     rax, [rbp+230h+arg_30]
0x140031f6b  mov     [rsp+330h+var_310], rax
0x140031f70  mov     r9, [rbp+230h+arg_28]
0x140031f77  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140031f7e  mov     rcx, [rdi+10h]
0x140031f82  call    WPP_SF_iiZ
0x140031f87  mov     rdi, cs:WPP_GLOBAL_Control
0x140031f8e  mov     eax, 1388h
0x140031f93  cmp     ebx, eax
0x140031f95  jnb     short loc_140031F9C
0x140031f97  mov     r14d, eax
0x140031f9a  jmp     short loc_140031FAA
0x140031f9c  mov     r14d, ebx
0x140031f9f  mov     eax, 7A120h
0x140031fa4  cmp     ebx, eax
0x140031fa6  cmova   r14d, eax
0x140031faa  mov     esi, r14d
0x140031fad  shl     rsi, 3
0x140031fb1  mov     rcx, rsi; Size
0x140031fb4  call    cs:__imp_malloc
0x140031fba  mov     [rbp+230h+Block], rax
0x140031fbe  test    rax, rax
0x140031fc1  jz      short loc_140031FE7
0x140031fc3  mov     rcx, rsi; Size
0x140031fc6  call    cs:__imp_malloc
0x140031fcc  mov     [rbp+230h+var_278], rax
0x140031fd0  xor     esi, esi
0x140031fd2  test    rax, rax
0x140031fd5  jnz     short loc_140032035
0x140031fd7  mov     rcx, [rbp+230h+Block]; Block
0x140031fdb  call    cs:__imp_free
0x140031fe1  mov     [rbp+230h+Block], rsi
0x140031fe5  jmp     short loc_140031FE9
0x140031fe7  xor     esi, esi
0x140031fe9  cmp     rdi, r13
0x140031fec  jz      short loc_140032028
0x140031fee  test    [rdi+1Ch], r15b
0x140031ff2  jz      short loc_140032028
0x140031ff4  cmp     byte ptr [rdi+19h], 4
0x140031ff8  jb      short loc_140032028
0x140031ffa  lea     rax, [r12+2A0h]
0x140032002  mov     ecx, r14d
0x140032005  shr     ecx, 1
0x140032007  mov     edx, 59h ; 'Y'
0x14003200c  mov     [rsp+330h+var_308], rax
0x140032011  mov     dword ptr [rsp+330h+var_310], ecx
0x140032015  mov     r9d, r14d
0x140032018  mov     rcx, [rdi+10h]
0x14003201c  call    WPP_SF_LLZ
0x140032021  mov     rdi, cs:WPP_GLOBAL_Control
0x140032028  shr     r14d, 1
0x14003202b  cmp     r14d, 64h ; 'd'
0x14003202f  jnb     loc_140031FAA
0x140032035  mov     [rbp+230h+var_290], r14d
0x140032039  cmp     [rbp+230h+Block], rsi
0x14003203d  mov     r14d, [rbp+230h+var_268]
0x140032041  jnz     short loc_1400320A1
0x140032043  mov     rsi, [rbp+230h+var_278]
0x140032047  mov     ecx, 8007000Eh
0x14003204c  mov     ebx, ecx
0x14003204e  mov     [rbp+230h+var_1E8], ecx
0x140032051  cmp     rdi, r13
0x140032054  jz      loc_140034F1D
0x14003205a  test    [rdi+1Ch], r15b
0x14003205e  jz      loc_140034F1D
0x140032064  cmp     byte ptr [rdi+19h], 2
0x140032068  jb      loc_140034F1D
0x14003206e  mov     rax, [rbp+230h+var_238]
0x140032072  mov     rax, [rax+28h]
0x140032076  mov     edx, 5Ah ; 'Z'
0x14003207b  mov     dword ptr [rsp+330h+var_308], ecx
0x14003207f  mov     rax, [rax+70h]
0x140032083  mov     [rsp+330h+var_310], rax
0x140032088  mov     r9d, [rbp+230h+var_290]
0x14003208c  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x140032093  mov     rcx, [rdi+10h]
0x140032097  call    WPP_SF_DSd
0x14003209c  jmp     loc_140034F1D
0x1400320a1  mov     esi, [rbp+230h+var_290]
0x1400320a4  mov     eax, esi
0x1400320a6  cmp     ebx, esi
0x1400320a8  cmovnb  eax, ebx
0x1400320ab  mov     dword ptr [rbp+230h+var_260], eax
0x1400320ae  dec     eax
0x1400320b0  add     eax, esi
0x1400320b2  xor     edx, edx
0x1400320b4  div     esi
0x1400320b6  mov     ecx, eax
0x1400320b8  mov     [rbp+230h+var_280], eax
0x1400320bb  test    eax, eax
0x1400320bd  jnz     short loc_1400320F8
0x1400320bf  cmp     rdi, r13
0x1400320c2  jz      short loc_1400320F2
0x1400320c4  test    [rdi+1Ch], r15b
0x1400320c8  jz      short loc_1400320F2
0x1400320ca  cmp     byte ptr [rdi+19h], 4
0x1400320ce  jb      short loc_1400320F2
0x1400320d0  lea     r9, [r12+2A0h]
0x1400320d8  lea     edx, [rax+5Bh]
0x1400320db  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x1400320e2  mov     rcx, [rdi+10h]
0x1400320e6  call    WPP_SF_Z
0x1400320eb  mov     rdi, cs:WPP_GLOBAL_Control
0x1400320f2  mov     ecx, r15d
0x1400320f5  mov     [rbp+230h+var_280], ecx
0x1400320f8  cmp     rdi, r13
0x1400320fb  jz      short loc_140032132
0x1400320fd  test    [rdi+1Ch], r15b
0x140032101  jz      short loc_140032132
0x140032103  cmp     byte ptr [rdi+19h], 5
0x140032107  jb      short loc_140032132
0x140032109  lea     rax, [r12+2A0h]
0x140032111  mov     edx, 5Ch ; '\'
0x140032116  mov     [rsp+330h+var_308], rax
0x14003211b  mov     dword ptr [rsp+330h+var_310], esi
0x14003211f  mov     r9d, ecx
0x140032122  mov     rcx, [rdi+10h]
0x140032126  call    WPP_SF_LLZ
0x14003212b  mov     rdi, cs:WPP_GLOBAL_Control
0x140032132  mov     rbx, rsi
0x140032135  shl     rbx, 3
0x140032139  mov     r8, rbx; Size
0x14003213c  xor     edx, edx; Val
0x14003213e  mov     rcx, [rbp+230h+Block]; void *
0x140032142  call    memset_0
0x140032147  mov     r8, rbx; Size
0x14003214a  xor     edx, edx; Val
0x14003214c  mov     rsi, [rbp+230h+var_278]
0x140032150  mov     rcx, rsi; void *
0x140032153  call    memset_0
0x140032158  mov     r13d, r14d
0x14003215b  mov     eax, 1388h
0x140032160  cmp     r14d, eax
0x140032163  cmovb   r13d, eax
0x140032167  mov     rdx, [rbp+230h+var_218]
0x14003216b  xor     r8d, r8d
0x14003216e  test    rdx, rdx
0x140032171  jnz     loc_140032202
0x140032177  mov     ecx, r13d
0x14003217a  shl     rcx, 3; Size
0x14003217e  call    cs:__imp_malloc
0x140032184  mov     rdx, rax
0x140032187  mov     [rbp+230h+var_218], rax
0x14003218b  mov     eax, r13d
0x14003218e  shr     eax, 1
0x140032190  xor     r8d, r8d
0x140032193  test    rdx, rdx
0x140032196  cmovnz  eax, r13d
0x14003219a  mov     r13d, eax
0x14003219d  cmp     eax, 64h ; 'd'
0x1400321a0  jnb     short loc_14003216E
0x1400321a2  test    rdx, rdx
0x1400321a5  jnz     short loc_140032202
0x1400321a7  mov     ecx, 8007000Eh
0x1400321ac  mov     ebx, ecx
0x1400321ae  mov     [rbp+230h+var_1E8], ecx
0x1400321b1  lea     rax, WPP_GLOBAL_Control
0x1400321b8  cmp     rdi, rax
0x1400321bb  jz      short loc_1400321F9
0x1400321bd  test    [rdi+1Ch], r15b
0x1400321c1  jz      short loc_1400321F9
0x1400321c3  cmp     byte ptr [rdi+19h], 2
0x1400321c7  jb      short loc_1400321F9
0x1400321c9  mov     rax, [rbp+230h+var_238]
0x1400321cd  mov     rax, [rax+28h]
0x1400321d1  lea     edx, [r8+5Dh]
0x1400321d5  mov     dword ptr [rsp+330h+var_308], ecx
0x1400321d9  mov     rax, [rax+70h]
0x1400321dd  mov     [rsp+330h+var_310], rax
0x1400321e2  mov     r9d, r13d
0x1400321e5  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x1400321ec  mov     rcx, [rdi+10h]
0x1400321f0  call    WPP_SF_DSd
0x1400321f5  mov     rdx, [rbp+230h+var_218]
0x1400321f9  mov     [rbp+230h+var_218], rdx
0x1400321fd  jmp     loc_140034F13
0x140032202  mov     eax, 80000000h
0x140032207  mov     [rbp+230h+cRow], eax
0x14003220a  mov     esi, eax
0x14003220c  mov     [rbp+230h+var_250], r8
0x140032210  mov     [rbp+230h+var_220], r8
0x140032214  mov     [rbp+230h+var_270], r8
0x140032218  mov     [rbp+230h+var_248], r8
0x14003221c  mov     rbx, r8
0x14003221f  mov     [rbp+230h+var_228], rbx
0x140032223  mov     [rbp+230h+var_1F8], r8
0x140032227  mov     [rbp+230h+var_1E0], r8
0x14003222b  mov     [rbp+230h+var_1D8], r8
0x14003222f  mov     [rbp+230h+var_1C8], r8
0x140032233  mov     [rbp+230h+var_200], r8
0x140032237  mov     [rbp+230h+var_1D0], r8
0x14003223b  mov     [rbp+230h+var_1C0], r8
0x14003223f  mov     [rbp+230h+var_1B8], r8
0x140032243  mov     eax, r13d
0x140032246  cmp     r14d, r13d
0x140032249  cmovnb  eax, r14d
0x14003224d  dec     eax
0x14003224f  add     eax, r13d
0x140032252  xor     edx, edx
0x140032254  div     r13d
0x140032257  mov     ecx, eax
0x140032259  mov     [rbp+230h+var_2A0], eax
0x14003225c  test    eax, eax
0x14003225e  jnz     short loc_1400322A2
0x140032260  lea     r14, WPP_GLOBAL_Control
0x140032267  cmp     rdi, r14
0x14003226a  jz      short loc_14003229A
0x14003226c  test    [rdi+1Ch], r15b
0x140032270  jz      short loc_14003229A
0x140032272  cmp     byte ptr [rdi+19h], 4
0x140032276  jb      short loc_14003229A
0x140032278  lea     r9, [r12+2A0h]
0x140032280  lea     edx, [rax+5Eh]
0x140032283  lea     r8, WPP_8bfb209f87463379247f9c02e31ae6de_Traceguids
0x14003228a  mov     rcx, [rdi+10h]
0x14003228e  call    WPP_SF_Z
0x140032293  mov     rdi, cs:WPP_GLOBAL_Control
0x14003229a  mov     ecx, r15d
0x14003229d  mov     [rbp+230h+var_2A0], ecx
0x1400322a0  jmp     short loc_1400322A9
0x1400322a2  lea     r14, WPP_GLOBAL_Control
  ... truncated ...
```
