# CInkStroke::Draw(CCanvas *,tagXFORM const *,tagXFORM const *,float,DrAt *)

- ea: `0x18000f0d0`
- end: `0x1800102e0`
- name: `?Draw@CInkStroke@@QEBAJPEAVCCanvas@@PEBUtagXFORM@@1MPEAVDrAt@@@Z`
- size: `4624`
- prototype: `int(CInkStroke *__hidden this, struct CCanvas *, const struct tagXFORM *, const struct tagXFORM *, float, struct DrAt *)`
- caller_count: `3`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x18007d988`
- `0x18008c540`
- `0x18009804c`

## callees

- `0x18000ba4c`
- `0x18000bf60`
- `0x18000dd20`
- `0x18000ec00`
- `0x18000ee90`
- `0x18000ef00`
- `0x18000f0d0`
- `0x1800102f0`
- `0x180010410`
- `0x180010918`
- `0x180018350`
- `0x18001dc70`
- `0x180020738`
- `0x180022590`
- `0x1800240dc`
- `0x18002418c`
- `0x180025c54`
- `0x18002b6b8`
- `0x18002b6e0`
- `0x180038e0c`
- `0x1800397d8`
- `0x180039f98`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x180044ab0`
- `0x180098bb4`
- `0x180098f70`
- `0x180099a84`
- `0x180099c34`
- `0x180099ed8`
- `0x18009f380`
- `0x180104ec2`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f198`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f65a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f198`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f65a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f68b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f68b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f926`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f926`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000f8e5`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000f8e5`
- `GDI32!CreateSolidBrush` at `0x18000fdf7`
- `GDI32!CreateSolidBrush` at `0x18000fdf7`
- `GDI32!SetPolyFillMode` at `0x18000fddd`
- `GDI32!SetPolyFillMode` at `0x18000fddd`
- `GDI32!SetROP2` at `0x18001022b`
- `GDI32!SetROP2` at `0x18001022b`
- `GDI32!GetDeviceCaps` at `0x18000fb4f`
- `GDI32!GetDeviceCaps` at `0x18000fb4f`
- `GDI32!CreatePen` at `0x18000fe35`
- `GDI32!CreatePen` at `0x18000fe35`
- `GDI32!SelectObject` at `0x18000fd53`
- `GDI32!SelectObject` at `0x18000fe21`
- `GDI32!SelectObject` at `0x18000fe7d`
- `GDI32!SelectObject` at `0x18000fd53`
- `GDI32!SelectObject` at `0x18000fe21`
- `GDI32!SelectObject` at `0x18000fe7d`
- `GDI32!DeleteObject` at `0x18000fcea`
- `GDI32!DeleteObject` at `0x18000fd60`
- `GDI32!DeleteObject` at `0x18000fcea`
- `GDI32!DeleteObject` at `0x18000fd60`
- `gdiplus!GdipDeleteRegion` at `0x18000fd0c`
- `gdiplus!GdipDeleteRegion` at `0x18000fd0c`
- `gdiplus!GdipGetSmoothingMode` at `0x18000ff19`
- `gdiplus!GdipGetSmoothingMode` at `0x18000ff19`
- `gdiplus!GdipSetSmoothingMode` at `0x18000fd85`
- `gdiplus!GdipSetSmoothingMode` at `0x18000ff4b`
- `gdiplus!GdipSetSmoothingMode` at `0x18000fd85`
- `gdiplus!GdipSetSmoothingMode` at `0x18000ff4b`
- `gdiplus!GdipDeletePen` at `0x18000fd9e`
- `gdiplus!GdipDeletePen` at `0x18000fd9e`
- `gdiplus!GdipAlloc` at `0x18000fedc`
- `gdiplus!GdipAlloc` at `0x18000fedc`
- `gdiplus!GdipFree` at `0x18000fd15`
- `gdiplus!GdipFree` at `0x18000fda7`
- `gdiplus!GdipFree` at `0x18000fd15`
- `gdiplus!GdipFree` at `0x18000fda7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkStroke::Draw(
        CInkStroke *this,
        struct CCanvas *a2,
        struct tagXFORM *a3,
        struct tagXFORM *a4,
        float a5,
        struct DrAt *a6)
{
  struct DrAt *v7; // r14
  unsigned __int8 *v8; // rax
  unsigned int v10; // ebx
  unsigned __int64 v11; // r13
  int *v12; // rbx
  int **v13; // rax
  int *v14; // r15
  __int64 v15; // r12
  __int64 v16; // rdx
  int *v17; // rcx
  int *v18; // rcx
  unsigned __int64 v19; // r15
  int *v20; // r8
  int v21; // eax
  char *v22; // r15
  int *v23; // rdx
  bool v24; // al
  __int64 v25; // r15
  unsigned int *v26; // rax
  unsigned int v27; // ebx
  int *v28; // r13
  int *v29; // r15
  int **v30; // r12
  int *v31; // rbx
  int *v32; // rcx
  int **v33; // rax
  unsigned __int64 v34; // r12
  int *v35; // rdx
  unsigned __int64 v36; // rbx
  __int64 v37; // rcx
  int *v38; // r8
  int v39; // eax
  int *v40; // rbx
  int *v41; // rdx
  bool v42; // cl
  int **v43; // rbx
  unsigned int v44; // r13d
  COLORREF *v45; // rax
  unsigned int v46; // ebx
  __int64 v47; // r12
  int *v48; // rbx
  int **v49; // rax
  int *v50; // r15
  __int64 v51; // r12
  __int64 v52; // rdx
  int *v53; // rcx
  int *v54; // rcx
  int *v55; // r15
  int *v56; // r12
  int *v57; // r8
  int v58; // eax
  char *v59; // r15
  int *v60; // rdx
  bool v61; // al
  __int64 v62; // r15
  char *v63; // rax
  int *v64; // rbx
  volatile signed __int32 *v65; // r15
  int *v66; // r12
  int **v67; // rdx
  int *v68; // rax
  int *v69; // r9
  void *v70; // r9
  int *v71; // rcx
  void *v72; // r11
  int *v73; // rcx
  int *v74; // r10
  unsigned __int64 v75; // rax
  int *v76; // r15
  int *v77; // r8
  int v78; // eax
  volatile signed __int32 *v79; // rdx
  int *v80; // r8
  bool v81; // al
  unsigned __int64 v82; // rcx
  struct tagXFORM *v83; // r15
  __int64 v84; // rax
  __int64 v85; // r12
  __int64 v86; // rax
  int v87; // ebx
  _QWORD *v88; // rdi
  __int64 v89; // rax
  unsigned __int64 v90; // r12
  int v91; // ebx
  double v92; // xmm6_8
  struct CFiller *Filler; // r15
  void *v94; // rcx
  _QWORD *v95; // rbx
  void *v96; // rax
  void *v97; // rdx
  HDC v98; // rcx
  __int64 v99; // rbx
  int v100; // eax
  _QWORD *v101; // rbx
  HDC v102; // rcx
  signed int v103; // ebx
  COLORREF v104; // r14d
  HBRUSH SolidBrush; // rax
  signed int LastError; // eax
  HPEN Pen; // rax
  Gdiplus::SolidBrush *v108; // rax
  __int64 v109; // rax
  __int64 v110; // rbx
  int SmoothingMode; // eax
  unsigned int v112; // ecx
  __int64 v113; // rbx
  int v114; // eax
  char v115; // r12
  __int64 v116; // rax
  unsigned int v117; // edi
  unsigned int v118; // eax
  struct tagXFORM *v119; // r13
  unsigned int v120; // r8d
  unsigned int v121; // r14d
  __int64 v122; // r9
  __int64 v123; // r10
  __int64 v124; // r8
  int *v125; // r11
  __int64 v126; // r8
  int *v127; // rax
  unsigned int v128; // ebx
  float v129; // xmm0_4
  double Adjusted; // xmm0_8
  bool v131; // r13
  int *v132; // r14
  const struct tagXFORM *v133; // rax
  HDC v134; // rcx
  bool v135; // [rsp+30h] [rbp-D0h]
  bool v136; // [rsp+48h] [rbp-B8h]
  char v137; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v138; // [rsp+51h] [rbp-AFh]
  int *v139; // [rsp+58h] [rbp-A8h] BYREF
  bool v140; // [rsp+60h] [rbp-A0h]
  unsigned __int64 pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  int *v142; // [rsp+70h] [rbp-90h] BYREF
  void *Buf1; // [rsp+78h] [rbp-88h] BYREF
  int *v144; // [rsp+80h] [rbp-80h]
  COLORREF color; // [rsp+88h] [rbp-78h]
  struct tagXFORM *v146; // [rsp+90h] [rbp-70h]
  struct tagXFORM *v147; // [rsp+98h] [rbp-68h]
  _QWORD v148[2]; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v149; // [rsp+B0h] [rbp-50h]
  CInkStroke *v150; // [rsp+B8h] [rbp-48h]
  void **v151; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v152[3]; // [rsp+C8h] [rbp-38h] BYREF
  struct tagXFORM v153; // [rsp+F8h] [rbp-8h] BYREF
  struct tagXFORM v154; // [rsp+110h] [rbp+10h] BYREF
  struct tagXFORM v155; // [rsp+128h] [rbp+28h] BYREF

  v147 = a4;
  v146 = a3;
  v150 = this;
  v7 = a6;
  if ( !a6 )
  {
    v7 = *(struct DrAt **)(*(_QWORD *)(*((_QWORD *)this + 2) + 136LL) + 40LL);
    v139 = (int *)v7;
    if ( !v7 )
    {
      SmartPtrBase::unref((SmartPtrBase *)&v139);
      return 2147500037LL;
    }
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    SmartPtrBase::unref((SmartPtrBase *)&v139);
  }
  if ( dword_18016C394 != (*((_DWORD *)v7 + 14) & dword_18016C394) )
  {
    v8 = (unsigned __int8 *)&dword_18016C39C;
    goto LABEL_47;
  }
  v10 = dword_18016C390;
  v148[0] = &dword_18016D438;
  EnterCriticalSection(&stru_18016D440);
  CInkModule::CGuidMgr::Manage(&xmmword_18016D500, &v142, &KNOWN_GUIDS + v10);
  LeaveCriticalSection(&stru_18016D440);
  v11 = *((_QWORD *)v7 + 4);
  v12 = v142;
  if ( !v11 )
    goto LABEL_39;
  v13 = (int **)*((_QWORD *)v7 + 3);
  v14 = *v13;
  if ( v142 == *v13 )
  {
LABEL_38:
    v25 = *((_QWORD *)v7 + 3);
    goto LABEL_41;
  }
  if ( !v142 )
    goto LABEL_39;
  if ( !v14 )
    goto LABEL_15;
  if ( memcmp_0(v142 + 4, v14 + 4, 0x10u) < 0 )
  {
LABEL_39:
    v15 = 32 * v11;
    goto LABEL_40;
  }
  if ( v12 == v14 || !v12 || memcmp_0(v14 + 4, v12 + 4, 0x10u) >= 0 )
    goto LABEL_38;
LABEL_15:
  v15 = 32 * v11;
  v16 = *((_QWORD *)v7 + 3);
  v17 = *(int **)(32 * v11 + v16 - 32);
  if ( v12 == v17 )
    goto LABEL_20;
  if ( v17 )
  {
    if ( !v12 )
      goto LABEL_20;
    if ( memcmp_0(v17 + 4, v12 + 4, 0x10u) >= 0 )
    {
      v16 = *((_QWORD *)v7 + 3);
LABEL_20:
      v18 = 0;
      v139 = 0;
      v19 = v11 >> 1;
      if ( v11 >> 1 )
      {
        while ( 1 )
        {
          v20 = *(int **)(32 * v19 + v16);
          if ( v12 == v20 )
            goto LABEL_27;
          if ( v20 )
          {
            if ( !v12 )
              goto LABEL_27;
            v21 = memcmp_0(v20 + 4, v12 + 4, 0x10u);
            v16 = *((_QWORD *)v7 + 3);
            if ( v21 >= 0 )
              break;
          }
          v18 = (int *)v19;
          v139 = (int *)v19;
LABEL_28:
          v19 = ((unsigned __int64)v18 + v11) >> 1;
          if ( (unsigned __int64)v18 >= v19 )
            goto LABEL_29;
        }
        v18 = v139;
LABEL_27:
        v11 = v19;
        goto LABEL_28;
      }
LABEL_29:
      v22 = (char *)(v19 + 1);
      v23 = *(int **)(32LL * (_QWORD)v22 + *((_QWORD *)v7 + 3));
      if ( v23 == v12 )
      {
        v24 = 1;
      }
      else if ( v12 )
      {
        if ( v23 )
          v24 = memcmp_0(v12 + 4, v23 + 4, 0x10u) >= 0;
        else
          v24 = 1;
      }
      else
      {
        v24 = 0;
      }
      if ( v24 )
      {
        v25 = *((_QWORD *)v7 + 3) + 32LL * (_QWORD)v22;
        goto LABEL_41;
      }
    }
  }
LABEL_40:
  v25 = v15 + *((_QWORD *)v7 + 3);
LABEL_41:
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(int *, __int64))v12)(v12, 1);
  if ( *((_QWORD *)v7 + 3) + 32LL * *((_QWORD *)v7 + 4) == v25 )
  {
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v8 = *(unsigned __int8 **)(v25 + 8);
LABEL_47:
  v138 = *v8;
  if ( dword_18016C384 == (*((_DWORD *)v7 + 14) & dword_18016C384) )
  {
    v27 = dword_18016C380;
    v148[0] = &dword_18016D438;
    EnterCriticalSection(&stru_18016D440);
    CInkModule::CGuidMgr::Manage(&xmmword_18016D500, &v142, &KNOWN_GUIDS + v27);
    LeaveCriticalSection(&stru_18016D440);
    v28 = (int *)*((_QWORD *)v7 + 4);
    v29 = v142;
    if ( v28 )
    {
      v30 = (int **)*((_QWORD *)v7 + 3);
      v31 = *v30;
      if ( v142 == *v30 )
        goto LABEL_81;
      if ( v142 )
      {
        if ( !v31 )
        {
LABEL_57:
          v32 = v30[4 * (_QWORD)v28 - 4];
          if ( v29 != v32 && (!v32 || v29 && memcmp_0(v32 + 4, v29 + 4, 0x10u) < 0) )
          {
            v33 = v30;
LABEL_83:
            v40 = v28;
LABEL_84:
            v43 = &v33[4 * (_QWORD)v40];
            if ( v29 && _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
              (**(void (__fastcall ***)(int *, __int64))v29)(v29, 1);
            if ( (int **)(*((_QWORD *)v7 + 3) + 32LL * *((_QWORD *)v7 + 4)) == v43 )
            {
              LODWORD(pExceptionObject) = -2147024809;
              throw (long *)&pExceptionObject;
            }
            v26 = (unsigned int *)v43[1];
            goto LABEL_90;
          }
          v34 = 0;
          v35 = v28;
          v139 = v28;
          v36 = (unsigned __int64)v28 >> 1;
          if ( !((unsigned __int64)v28 >> 1) )
          {
LABEL_72:
            v40 = (int *)(v36 + 1);
            v41 = *(int **)(32LL * (_QWORD)v40 + *((_QWORD *)v7 + 3));
            if ( v41 == v29 )
            {
              v42 = 1;
            }
            else if ( v29 )
            {
              if ( v41 )
                v42 = memcmp_0(v29 + 4, v41 + 4, 0x10u) >= 0;
              else
                v42 = 1;
            }
            else
            {
              v42 = 0;
            }
            v33 = (int **)*((_QWORD *)v7 + 3);
            if ( v42 )
              goto LABEL_84;
            goto LABEL_83;
          }
          v37 = *((_QWORD *)v7 + 3);
          while ( 1 )
          {
            v38 = *(int **)(32 * v36 + v37);
            if ( v29 == v38 )
              break;
            if ( v38 )
            {
              if ( !v29 )
                break;
              v39 = memcmp_0(v38 + 4, v29 + 4, 0x10u);
              v37 = *((_QWORD *)v7 + 3);
              if ( v39 >= 0 )
                break;
              v35 = v139;
            }
            v34 = v36;
LABEL_71:
            v36 = ((unsigned __int64)v35 + v34) >> 1;
            if ( v34 >= v36 )
              goto LABEL_72;
          }
          v35 = (int *)v36;
          v139 = (int *)v36;
          goto LABEL_71;
        }
        if ( memcmp_0(v142 + 4, v31 + 4, 0x10u) >= 0 )
        {
          if ( v29 != v31 && v29 && memcmp_0(v31 + 4, v29 + 4, 0x10u) < 0 )
            goto LABEL_57;
LABEL_81:
          v40 = 0;
          v33 = v30;
          goto LABEL_84;
        }
      }
    }
    v33 = (int **)*((_QWORD *)v7 + 3);
    goto LABEL_83;
  }
  v26 = (unsigned int *)&dword_18016C38C;
LABEL_90:
  v44 = *v26;
  if ( (*v26 & 0x10000000) != 0 )
    return 0;
  LODWORD(v144) = *v26 & 0x10;
  v140 = (_DWORD)v144 != 0;
  if ( dword_18016C344 != (*((_DWORD *)v7 + 14) & dword_18016C344) )
  {
    v45 = (COLORREF *)&dword_18016C34C;
    goto LABEL_135;
  }
  v46 = dword_18016C340;
  v148[0] = &dword_18016D438;
  EnterCriticalSection(&stru_18016D440);
  CInkModule::CGuidMgr::Manage(&xmmword_18016D500, &v142, &KNOWN_GUIDS + v46);
  LeaveCriticalSection(&stru_18016D440);
  v47 = *((_QWORD *)v7 + 4);
  v48 = v142;
  if ( !v47 )
    goto LABEL_127;
  v49 = (int **)*((_QWORD *)v7 + 3);
  v50 = *v49;
  if ( v142 == *v49 )
  {
LABEL_126:
    v62 = *((_QWORD *)v7 + 3);
    goto LABEL_129;
  }
  if ( !v142 )
    goto LABEL_127;
  if ( !v50 )
    goto LABEL_101;
  if ( memcmp_0(v142 + 4, v50 + 4, 0x10u) < 0 )
  {
LABEL_127:
    v51 = 32 * v47;
    goto LABEL_128;
  }
  if ( v48 == v50 || !v48 || memcmp_0(v50 + 4, v48 + 4, 0x10u) >= 0 )
    goto LABEL_126;
LABEL_101:
  v51 = 32 * v47;
  v142 = (int *)v51;
  v52 = *((_QWORD *)v7 + 3);
  v53 = *(int **)(v51 + v52 - 32);
  if ( v48 != v53 )
  {
    if ( !v53 )
      goto LABEL_128;
    if ( v48 )
    {
      if ( memcmp_0(v53 + 4, v48 + 4, 0x10u) >= 0 )
      {
        v52 = *((_QWORD *)v7 + 3);
        goto LABEL_106;
      }
LABEL_128:
      v62 = v51 + *((_QWORD *)v7 + 3);
      goto LABEL_129;
    }
  }
LABEL_106:
  v54 = 0;
  v139 = 0;
  v55 = (int *)(*((_QWORD *)v7 + 4) >> 1);
  if ( !v55 )
    goto LABEL_117;
  v56 = (int *)*((_QWORD *)v7 + 4);
  do
  {
    v57 = *(int **)(32LL * (_QWORD)v55 + v52);
    if ( v48 != v57 )
    {
      if ( !v57 )
        goto LABEL_112;
      if ( v48 )
      {
        v58 = memcmp_0(v57 + 4, v48 + 4, 0x10u);
        v52 = *((_QWORD *)v7 + 3);
        if ( v58 < 0 )
        {
LABEL_112:
          v54 = v55;
          v139 = v55;
          goto LABEL_115;
        }
        v54 = v139;
      }
    }
    v56 = v55;
LABEL_115:
    v55 = (int *)(((unsigned __int64)v56 + (unsigned __int64)v54) >> 1);
  }
  while ( v54 < v55 );
  v51 = (__int64)v142;
LABEL_117:
  v59 = (char *)v55 + 1;
  v60 = *(int **)(32LL * (_QWORD)v59 + *((_QWORD *)v7 + 3));
  if ( v60 == v48 )
  {
    v61 = 1;
  }
  else if ( v48 )
  {
    if ( v60 )
      v61 = memcmp_0(v48 + 4, v60 + 4, 0x10u) >= 0;
    else
      v61 = 1;
  }
  else
  {
    v61 = 0;
  }
  if ( !v61 )
    goto LABEL_128;
  v62 = *((_QWORD *)v7 + 3) + 32LL * (_QWORD)v59;
LABEL_129:
  if ( v48 && _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(int *, __int64))v48)(v48, 1);
  if ( *((_QWORD *)v7 + 3) + 32LL * *((_QWORD *)v7 + 4) == v62 )
  {
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v45 = *(COLORREF **)(v62 + 8);
LABEL_135:
  color = *v45;
  v137 = 0;
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + (unsigned int)tls_index)
                                                                 + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
    {
      `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
      dwFlags = 0;
      `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
      atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
      Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    }
  }
  if ( !`WinHeap::GetDefault'::`2'::s_WinHeap )
    goto LABEL_175;
  v63 = (char *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 0x20u);
  v64 = (int *)v63;
  if ( !v63 )
    goto LABEL_175;
  *((_DWORD *)v63 + 2) = 0;
  *(_QWORD *)v63 = &SGuid::`vftable';
  *((struct _GUID *)v63 + 1) = stru_180121570;
  *(_QWORD *)v63 = &SGuid::`vftable';
  v148[0] = v63;
  v65 = (volatile signed __int32 *)(v63 + 8);
  v149 = (volatile signed __int32 *)(v63 + 8);
  _InterlockedIncrement((volatile signed __int32 *)v63 + 2);
  v66 = (int *)*((_QWORD *)v7 + 4);
  if ( !v66 )
    goto LABEL_173;
  v67 = (int **)*((_QWORD *)v7 + 3);
  v68 = *v67;
  v142 = v68;
  if ( v68 == v64 )
  {
LABEL_145:
    v69 = v64;
    if ( v64 != v68 )
      goto LABEL_146;
    goto LABEL_178;
  }
  if ( v68 )
  {
    if ( memcmp_0(v64 + 4, v68 + 4, 0x10u) < 0 )
      goto LABEL_173;
    v68 = v142;
    v67 = (int **)*((_QWORD *)v7 + 3);
    goto LABEL_145;
  }
  v69 = v64;
LABEL_146:
  v70 = v69 + 4;
  Buf1 = v70;
  if ( v68 )
  {
    if ( memcmp_0(v68 + 4, v70, 0x10u) < 0 )
    {
      v67 = (int **)*((_QWORD *)v7 + 3);
      v70 = Buf1;
      goto LABEL_151;
    }
LABEL_178:
    v79 = 0;
    goto LABEL_179;
  }
  Buf1 = v70;
LABEL_151:
  v71 = v67[4 * (_QWORD)v66 - 4];
  if ( v64 == v71 )
  {
    v72 = v70;
  }
  else
  {
    if ( !v71 || memcmp_0(v71 + 4, v64 + 4, 0x10u) < 0 )
      goto LABEL_173;
    v67 = (int **)*((_QWORD *)v7 + 3);
    v70 = Buf1;
    v72 = v64 + 4;
  }
  v73 = 0;
  v139 = 0;
  v74 = v66;
  v142 = v66;
  v75 = (unsigned __int64)v66 >> 1;
  if ( !((unsigned __int64)v66 >> 1) )
    goto LABEL_167;
  v76 = (int *)((unsigned __int64)v66 >> 1);
  while ( 2 )
  {
    v77 = v67[4 * (_QWORD)v76];
    if ( v64 == v77 )
      goto LABEL_164;
    if ( !v77 )
      goto LABEL_162;
    v78 = memcmp_0(v77 + 4, v72, 0x10u);
    v67 = (int **)*((_QWORD *)v7 + 3);
    if ( v78 >= 0 )
    {
      v73 = v139;
LABEL_164:
      v74 = v76;
      v142 = v76;
      goto LABEL_165;
    }
    v74 = v142;
LABEL_162:
    v73 = v76;
    v139 = v76;
LABEL_165:
    v76 = (int *)(((unsigned __int64)v73 + (unsigned __int64)v74) >> 1);
    v70 = Buf1;
    v72 = Buf1;
    if ( v73 < v76 )
      continue;
    break;
  }
  pExceptionObject = ((unsigned __int64)v73 + (unsigned __int64)v74) >> 1;
  v65 = v149;
  v75 = pExceptionObject;
LABEL_167:
  v79 = (volatile signed __int32 *)(v75 + 1);
  v149 = (volatile signed __int32 *)(v75 + 1);
  v80 = *(int **)(32 * (v75 + 1) + *((_QWORD *)v7 + 3));
  if ( v80 == v64 )
  {
    v81 = 1;
  }
  else if ( v80 )
  {
    v81 = memcmp_0(v70, v80 + 4, 0x10u) >= 0;
    v79 = v149;
  }
  else
  {
    v81 = 1;
  }
  if ( !v81 )
  {
LABEL_173:
    if ( _InterlockedExchangeAdd(v65, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(int *, __int64))v64)(v64, 1);
    goto LABEL_175;
  }
LABEL_179:
  v84 = *((_QWORD *)v7 + 3);
  v85 = v84 + 32LL * (_QWORD)v66;
  v86 = 32LL * (_QWORD)v79 + v84;
  if ( v85 == v86 )
    goto LABEL_173;
  v87 = **(_DWORD **)(v86 + 8);
  SmartPtr<SmartAdapt<tagXFORM>>::~SmartPtr<SmartAdapt<tagXFORM>>(v148);
  if ( v87 != 13 )
  {
    v138 = 0;
    CCanvas::UseGDI(a2, 1);
    CCanvas::SetROP(a2, v87);
    v137 = 1;
  }
LABEL_175:
  memset(&v154, 0, sizeof(v154));
  if ( (GetDeviceCaps(*((HDC *)a2 + 31), 2) & 0xFFFFFFFD) != 0 || *((_DWORD *)a2 + 61) )
  {
    v83 = v147;
  }
  else
  {
    v83 = (struct tagXFORM *)CCanvas::AdjustXformForPrinter(a2, v147, &v154);
    v147 = v83;
  }
  memset(&v153, 0, sizeof(v153));
  if ( v83 )
  {
    if ( v146 )
    {
      CXform::Multiply(&v153, v146, v83);
      v146 = &v153;
    }
    else
    {
      v146 = v83;
    }
  }
  v88 = (_QWORD *)*((_QWORD *)v150 + 2);
  if ( v88[3] )
  {
    v89 = v88[2];
    v82 = *(unsigned int *)(v89 + 24);
    v90 = *(_QWORD *)(v89 + 8) / v82;
  }
  else
  {
    LODWORD(v90) = 0;
  }
  LODWORD(pExceptionObject) = 0;
  LODWORD(Buf1) = 4;
  CInkModule::Manage(v82, &v139, qword_180121510);
  if ( DrAt::GetAttribute(v7, (const struct SGPtr *)&v139, (unsigned int *)&Buf1, &pExceptionObject) < 0
    || (v91 = pExceptionObject) == 0 )
  {
    v91 = 0;
  }
  SmartPtr<SmartAdapt<tagXFORM>>::~SmartPtr<SmartAdapt<tagXFORM>>(&v139);
  v92 = (double)v91;
  Filler = CInkStroke::CInkStrokeImpl::GetFiller(
             (CInkStroke::CInkStrokeImpl *)v88,
             v83,
             0,
             v90,
             v44,
             (double)v91,
             a5,
             v7,
             0,
             v136);
  LOBYTE(v148[0]) = Filler != 0;
  v148[1] = Filler;
  if ( Filler )
  {
    if ( *((_DWORD *)a2 + 61) )
    {
      v94 = (void *)*((_QWORD *)a2 + 41);
      if ( v94 )
        DeleteObject(v94);
      *((_QWORD *)a2 + 41) = 0;
    }
    else
    {
      v95 = (_QWORD *)*((_QWORD *)a2 + 29);
      if ( v95 )
      {
        GdipDeleteRegion(*v95);
        GdipFree(v95);
      }
      *((_QWORD *)a2 + 29) = 0;
    }
    if ( *((_DWORD *)a2 + 61) )
    {
      v96 = (void *)*((_QWORD *)a2 + 34);
      if ( v96 )
      {
        v97 = (void *)*((_QWORD *)a2 + 33);
        if ( v96 != v97 )
        {
          v98 = (HDC)*((_QWORD *)a2 + 31);
          if ( v98 )
            SelectObject(v98, v97);
          DeleteObject(*((HGDIOBJ *)a2 + 34));
          *((_QWORD *)a2 + 34) = *((_QWORD *)a2 + 33);
        }
      }
    }
    else
    {
      v99 = *((_QWORD *)a2 + 1);
      if ( v99 )
      {
        v100 = GdipSetSmoothingMode(*(_QWORD *)v99, *((unsigned int *)a2 + 8));
        if ( v100 )
          *(_DWORD *)(v99 + 8) = v100;
      }
      v101 = (_QWORD *)*((_QWORD *)a2 + 2);
      if ( v101 )
      {
        GdipDeletePen(*v101);
        GdipFree(v101);
        *((_QWORD *)a2 + 2) = 0;
      }
    }
    if ( *((_DWORD *)a2 + 61) )
    {
      v102 = (HDC)*((_QWORD *)a2 + 31);
      if ( !v102 )
      {
        v103 = -2147467261;
        goto LABEL_279;
      }
      *((_DWORD *)a2 + 74) = SetPolyFillMode(v102, 2);
      v104 = color;
      *((_DWORD *)a2 + 80) = color;
      SolidBrush = CreateSolidBrush(v104);
      *((_QWORD *)a2 + 36) = SolidBrush;
      if ( !SolidBrush )
      {
        LastError = GetLastError();
        v103 = LastError;
        if ( LastError <= 0 )
        {
LABEL_221:
          if ( v103 < 0 )
            goto LABEL_279;
LABEL_237:
          v115 = v137;
          if ( v137 )
          {
            *((_BYTE *)a2 + 40) = 1;
            v116 = *((_QWORD *)Filler + 6);
            if ( v116 )
              v117 = *(_DWORD *)(v116 + 96);
            else
              v117 = *((_DWORD *)Filler + 4);
            v118 = 0;
            if ( v117 )
            {
              v119 = v146;
              do
              {
                v120 = (v118 != 0) + 256;
                v121 = v118 - 1;
                if ( !v118 )
                  v121 = 0;
                if ( v121 + v120 > v117 )
                  v120 = v117 - v121;
                if ( !CFiller::Enumerate(Filler, v121, v120, v119, a2, 0) )
                  (*(void (__fastcall **)(struct CCanvas *))(*(_QWORD *)a2 + 40LL))(a2);
                v118 = v121 + 256;
              }
              while ( v121 + 256 < v117 );
            }
          }
          else if ( !CFiller::Enumerate(Filler, v146, a2, 0) )
          {
            (*(void (__fastcall **)(struct CCanvas *))(*(_QWORD *)a2 + 40LL))(a2);
          }
          CCanvas::ResetBrush(a2);
LABEL_280:
          if ( v115 && *((_DWORD *)a2 + 61) )
          {
            v134 = (HDC)*((_QWORD *)a2 + 31);
            if ( v134 )
            {
              SetROP2(v134, *((_DWORD *)a2 + 75));
              *((_DWORD *)a2 + 76) = *((_DWORD *)a2 + 75);
              *((_DWORD *)a2 + 75) = 0;
            }
            if ( *((_DWORD *)a2 + 61) )
            {
              CCanvas::ResetBrush(a2);
              CCanvas::ResetPen(a2);
              CCanvas::ResetRgn(a2);
              *((_DWORD *)a2 + 61) = 0;
            }
          }
          if ( LOBYTE(v148[0]) )
          {
            if ( Filler )
              (**(void (__fastcall ***)(struct CFiller *, __int64))Filler)(Filler, 1);
          }
          return (unsigned int)v103;
        }
LABEL_220:
        v103 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_221;
      }
      *((_QWORD *)a2 + 35) = SelectObject(*((HDC *)a2 + 31), SolidBrush);
      Pen = CreatePen(0, 0, v104);
      *((_QWORD *)a2 + 34) = Pen;
      if ( !Pen )
      {
        LastError = GetLastError();
        v103 = LastError;
        if ( LastError <= 0 )
          goto LABEL_221;
        goto LABEL_220;
      }
      *((_DWORD *)a2 + 77) = 0;
      *((_QWORD *)a2 + 33) = SelectObject(*((HDC *)a2 + 31), Pen);
LABEL_236:
      v103 = 0;
      goto LABEL_237;
    }
    if ( !*((_QWORD *)a2 + 1) )
    {
      v103 = -2147467261;
      goto LABEL_279;
    }
    LODWORD(Buf1) = BYTE2(color) | color & 0xFF00 | (((unsigned __int8)color | ((unsigned __int8)~v138 << 8)) << 16);
    v108 = (Gdiplus::SolidBrush *)GdipAlloc(24);
    if ( v108 )
    {
      v109 = Gdiplus::SolidBrush::SolidBrush(v108, (const struct Gdiplus::Color *)&Buf1);
      *((_QWORD *)a2 + 3) = v109;
      if ( v109 )
      {
        v110 = *((_QWORD *)a2 + 1);
        LODWORD(pExceptionObject) = -1;
        SmoothingMode = GdipGetSmoothingMode(*(_QWORD *)v110, &pExceptionObject);
        if ( SmoothingMode )
          *(_DWORD *)(v110 + 8) = SmoothingMode;
        *((_DWORD *)a2 + 8) = pExceptionObject;
        v112 = 4;
        if ( !(_DWORD)v144 )
          v112 = 0;
        *((_DWORD *)a2 + 9) = v112;
        v113 = *((_QWORD *)a2 + 1);
        if ( v113 )
        {
          v114 = GdipSetSmoothingMode(*(_QWORD *)v113, v112);
          if ( v114 )
            *(_DWORD *)(v113 + 8) = v114;
        }
        *((_BYTE *)a2 + 200) = v138;
        goto LABEL_236;
      }
    }
    else
    {
      *((_QWORD *)a2 + 3) = 0;
    }
    v103 = -2147024882;
    goto LABEL_279;
  }
  if ( !*(_BYTE *)(v88[5] + 24LL) || !CPacketList::GetPacketCount((CPacketList *)(v88 + 2)) )
    goto LABEL_290;
  v123 = v88[2];
  v124 = 32LL * *(unsigned int *)(v122 + 28);
  v150 = 0;
  if ( is_mul_ok(0, *(unsigned int *)(v124 + v123 + 24)) && *(_QWORD *)(v124 + v123 + 8) )
    v125 = *(int **)(v124 + v123);
  else
    v125 = 0;
  v144 = v125;
  v126 = 32LL * *(unsigned int *)(v122 + 32);
  if ( is_mul_ok(0, *(unsigned int *)(v126 + v123 + 24)) && *(_QWORD *)(v126 + v123 + 8) )
    v127 = *(int **)(v126 + v123);
  else
    v127 = 0;
  v139 = v127;
  if ( !v125 || !v127 )
  {
LABEL_290:
    if ( v137 )
    {
      CCanvas::ResetROP(a2);
      CCanvas::UseGDI(a2, 0);
    }
    return 0;
  }
  v128 = *(_DWORD *)DrAt::GetKnownAttr(v7, 0);
  v129 = *(float *)DrAt::GetKnownAttr(v7, 2u);
  Adjusted = GetAdjusted(v129, v147, v128, a5);
  v103 = CCanvas::SetPen(a2, v128, Adjusted, color, v138, v140, v135);
  if ( v103 >= 0 )
  {
    v131 = v44 & 1;
    if ( v131 )
    {
      v151 = &CBezier::`vftable';
      memset(v152, 0, sizeof(v152));
      v132 = v139;
      v131 = CBezier::ConstructToFit((CBezier *)&v151, (const struct CXform *)(v88 + 27), v144, v139, v90, v92);
      if ( v131 )
        v131 = CCanvas::DrawBezier(a2, v146, (const struct CPointArray *)v152);
      CBezier::~CBezier((CBezier *)&v151);
    }
    else
    {
      v132 = v139;
    }
    if ( !v131 )
    {
      memset(&v155, 0, sizeof(v155));
      v133 = CXform::Combine((CXform *)(v88 + 27), &v155, v146);
      v103 = CCanvas::DrawPolyline(a2, v133, v90, v144, v132);
    }
LABEL_279:
    v115 = v137;
    goto LABEL_280;
  }
  if ( v137 )
  {
    CCanvas::ResetROP(a2);
    CCanvas::UseGDI(a2, 0);
  }
  AutoPtr<CFiller>::~AutoPtr<CFiller>(v148);
  return (unsigned int)v103;
}

```

## disassembly

```asm
0x18000f0d0  mov     rax, rsp
0x18000f0d3  push    rbp
0x18000f0d4  push    rbx
0x18000f0d5  push    rsi
0x18000f0d6  push    rdi
0x18000f0d7  push    r12
0x18000f0d9  push    r13
0x18000f0db  push    r14
0x18000f0dd  push    r15
0x18000f0df  lea     rbp, [rsp-78h]
0x18000f0e4  sub     rsp, 178h
0x18000f0eb  movaps  xmmword ptr [rax-58h], xmm6
0x18000f0ef  movaps  xmmword ptr [rax-68h], xmm7
0x18000f0f3  mov     rax, cs:__security_cookie
0x18000f0fa  xor     rax, rsp
0x18000f0fd  mov     [rbp+0B0h+var_70], rax
0x18000f101  mov     [rbp+0B0h+var_118], r9
0x18000f105  mov     [rbp+0B0h+var_120], r8
0x18000f109  mov     rsi, rdx
0x18000f10c  mov     [rbp+0B0h+var_F8], rcx
0x18000f110  movss   xmm7, [rbp+0B0h+arg_20]
0x18000f118  mov     r14, [rbp+0B0h+arg_28]
0x18000f11f  test    r14, r14
0x18000f122  jnz     short loc_18000F14C
0x18000f124  mov     rax, [rcx+10h]
0x18000f128  mov     rcx, [rax+88h]
0x18000f12f  mov     r14, [rcx+28h]
0x18000f133  mov     [rsp+1B0h+var_158], r14
0x18000f138  lea     rcx, [rsp+1B0h+var_158]; this
0x18000f13d  test    r14, r14
0x18000f140  jz      short loc_18000F178
0x18000f142  lock inc dword ptr [r14+8]
0x18000f147  call    ?unref@SmartPtrBase@@IEAAXXZ; SmartPtrBase::unref(void)
0x18000f14c  mov     eax, cs:dword_18016C394
0x18000f152  and     eax, [r14+38h]
0x18000f156  lea     rdx, dword_18016D438
0x18000f15d  lea     r15, KNOWN_GUIDS
0x18000f164  cmp     cs:dword_18016C394, eax
0x18000f16a  jz      short loc_18000F187
0x18000f16c  lea     rax, dword_18016C39C
0x18000f173  jmp     loc_18000F3C0
0x18000f178  call    ?unref@SmartPtrBase@@IEAAXXZ; SmartPtrBase::unref(void)
0x18000f17d  mov     eax, 80004005h
0x18000f182  jmp     loc_1800102B0
0x18000f187  mov     ebx, cs:dword_18016C390
0x18000f18d  mov     [rbp+0B0h+var_110], rdx
0x18000f191  lea     rcx, stru_18016D440; lpCriticalSection
0x18000f198  call    cs:__imp_EnterCriticalSection
0x18000f19e  nop
0x18000f19f  mov     r8d, ebx
0x18000f1a2  shl     r8, 4
0x18000f1a6  add     r8, r15
0x18000f1a9  lea     rdx, [rsp+1B0h+var_140]
0x18000f1ae  lea     rcx, xmmword_18016D500
0x18000f1b5  call    ?Manage@CGuidMgr@CInkModule@@QEAA?AVSGPtr@@AEBU_GUID@@@Z; CInkModule::CGuidMgr::Manage(_GUID const &)
0x18000f1ba  nop
0x18000f1bb  lea     rcx, stru_18016D440; lpCriticalSection
0x18000f1c2  call    cs:__imp_LeaveCriticalSection
0x18000f1c8  mov     r13, [r14+20h]
0x18000f1cc  mov     rbx, [rsp+1B0h+var_140]
0x18000f1d1  test    r13, r13
0x18000f1d4  jz      loc_18000F349
0x18000f1da  mov     rax, [r14+18h]
0x18000f1de  mov     r15, [rax]
0x18000f1e1  cmp     rbx, r15
0x18000f1e4  jz      loc_18000F33C
0x18000f1ea  test    rbx, rbx
0x18000f1ed  jz      loc_18000F349
0x18000f1f3  test    r15, r15
0x18000f1f6  jz      short loc_18000F245
0x18000f1f8  lea     rdx, [r15+10h]; Buf2
0x18000f1fc  lea     rcx, [rbx+10h]; Buf1
0x18000f200  mov     r8d, 10h; Size
0x18000f206  call    memcmp_0
0x18000f20b  test    eax, eax
0x18000f20d  js      loc_18000F349
0x18000f213  cmp     rbx, r15
0x18000f216  jz      loc_18000F33C
0x18000f21c  test    r15, r15
0x18000f21f  jz      short loc_18000F245
0x18000f221  test    rbx, rbx
0x18000f224  jz      loc_18000F33C
0x18000f22a  lea     rdx, [rbx+10h]; Buf2
0x18000f22e  lea     rcx, [r15+10h]; Buf1
0x18000f232  mov     r8d, 10h; Size
0x18000f238  call    memcmp_0
0x18000f23d  test    eax, eax
0x18000f23f  jns     loc_18000F33C
0x18000f245  mov     r12, r13
0x18000f248  shl     r12, 5
0x18000f24c  mov     rdx, [r14+18h]
0x18000f250  mov     rcx, [r12+rdx-20h]
0x18000f255  cmp     rbx, rcx
0x18000f258  jz      short loc_18000F287
0x18000f25a  test    rcx, rcx
0x18000f25d  jz      loc_18000F350
0x18000f263  test    rbx, rbx
0x18000f266  jz      short loc_18000F287
0x18000f268  lea     rdx, [rbx+10h]; Buf2
0x18000f26c  add     rcx, 10h; Buf1
0x18000f270  mov     r8d, 10h; Size
0x18000f276  call    memcmp_0
0x18000f27b  test    eax, eax
0x18000f27d  js      loc_18000F350
0x18000f283  mov     rdx, [r14+18h]
0x18000f287  xor     ecx, ecx
0x18000f289  mov     [rsp+1B0h+var_158], rcx
0x18000f28e  mov     r15, r13
0x18000f291  shr     r15, 1
0x18000f294  jz      short loc_18000F2E9
0x18000f296  mov     rax, r15
0x18000f299  shl     rax, 5
0x18000f29d  mov     r8, [rax+rdx]
0x18000f2a1  cmp     rbx, r8
0x18000f2a4  jz      short loc_18000F2DA
0x18000f2a6  test    r8, r8
0x18000f2a9  jz      short loc_18000F2CB
0x18000f2ab  test    rbx, rbx
0x18000f2ae  jz      short loc_18000F2DA
0x18000f2b0  lea     rdx, [rbx+10h]; Buf2
0x18000f2b4  lea     rcx, [r8+10h]; Buf1
0x18000f2b8  mov     r8d, 10h; Size
0x18000f2be  call    memcmp_0
0x18000f2c3  mov     rdx, [r14+18h]
0x18000f2c7  test    eax, eax
0x18000f2c9  jns     short loc_18000F2D5
0x18000f2cb  mov     rcx, r15
0x18000f2ce  mov     [rsp+1B0h+var_158], rcx
0x18000f2d3  jmp     short loc_18000F2DD
0x18000f2d5  mov     rcx, [rsp+1B0h+var_158]
0x18000f2da  mov     r13, r15
0x18000f2dd  lea     r15, [rcx+r13]
0x18000f2e1  shr     r15, 1
0x18000f2e4  cmp     rcx, r15
0x18000f2e7  jb      short loc_18000F296
0x18000f2e9  inc     r15
0x18000f2ec  mov     rcx, r15
0x18000f2ef  shl     rcx, 5
0x18000f2f3  mov     rax, [r14+18h]
0x18000f2f7  mov     rdx, [rcx+rax]
0x18000f2fb  cmp     rdx, rbx
0x18000f2fe  jnz     short loc_18000F304
0x18000f300  mov     al, 1
0x18000f302  jmp     short loc_18000F32E
0x18000f304  test    rbx, rbx
0x18000f307  jnz     short loc_18000F30D
0x18000f309  xor     al, al
0x18000f30b  jmp     short loc_18000F32E
0x18000f30d  test    rdx, rdx
0x18000f310  jnz     short loc_18000F316
0x18000f312  mov     al, 1
0x18000f314  jmp     short loc_18000F32E
0x18000f316  add     rdx, 10h; Buf2
0x18000f31a  lea     rcx, [rbx+10h]; Buf1
0x18000f31e  mov     r8d, 10h; Size
0x18000f324  call    memcmp_0
0x18000f329  test    eax, eax
0x18000f32b  setns   al
0x18000f32e  test    al, al
0x18000f330  jz      short loc_18000F350
0x18000f332  shl     r15, 5
0x18000f336  add     r15, [r14+18h]
0x18000f33a  jmp     short loc_18000F357
0x18000f33c  xor     r15d, r15d
0x18000f33f  shl     r15, 5
0x18000f343  add     r15, [r14+18h]
0x18000f347  jmp     short loc_18000F357
0x18000f349  mov     r12, r13
0x18000f34c  shl     r12, 5
0x18000f350  mov     r15, [r14+18h]
0x18000f354  add     r15, r12
0x18000f357  test    rbx, rbx
0x18000f35a  jz      short loc_18000F383
0x18000f35c  mov     eax, 0FFFFFFFFh
0x18000f361  lock xadd [rbx+8], eax
0x18000f366  cmp     eax, 1
0x18000f369  jnz     short loc_18000F383
0x18000f36b  test    rbx, rbx
0x18000f36e  jz      short loc_18000F383
0x18000f370  mov     rax, [rbx]
0x18000f373  mov     edx, 1
0x18000f378  mov     rcx, rbx
0x18000f37b  mov     rax, [rax]
0x18000f37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f383  mov     rax, [r14+20h]
0x18000f387  shl     rax, 5
0x18000f38b  add     rax, [r14+18h]
0x18000f38f  cmp     rax, r15
0x18000f392  jnz     short loc_18000F3AE
0x18000f394  mov     dword ptr [rsp+1B0h+pExceptionObject], 80070057h
0x18000f39c  lea     rdx, _TI1J; pThrowInfo
0x18000f3a3  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x18000f3a8  call    _CxxThrowException_0
0x18000f3ae  mov     rax, [r15+8]
0x18000f3b2  lea     rdx, dword_18016D438
0x18000f3b9  lea     r15, KNOWN_GUIDS
0x18000f3c0  movzx   eax, byte ptr [rax]
0x18000f3c3  mov     [rsp+1B0h+var_15F], al
0x18000f3c7  mov     eax, cs:dword_18016C384
0x18000f3cd  and     eax, [r14+38h]
0x18000f3d1  cmp     cs:dword_18016C384, eax
0x18000f3d7  jz      short loc_18000F3E5
0x18000f3d9  lea     rax, dword_18016C38C
0x18000f3e0  jmp     loc_18000F608
0x18000f3e5  mov     ebx, cs:dword_18016C380
0x18000f3eb  mov     [rbp+0B0h+var_110], rdx
0x18000f3ef  lea     rcx, stru_18016D440; lpCriticalSection
0x18000f3f6  call    cs:__imp_EnterCriticalSection
0x18000f3fc  nop
0x18000f3fd  mov     r8d, ebx
0x18000f400  shl     r8, 4
0x18000f404  add     r8, r15
0x18000f407  lea     rdx, [rsp+1B0h+var_140]
0x18000f40c  lea     rcx, xmmword_18016D500
0x18000f413  call    ?Manage@CGuidMgr@CInkModule@@QEAA?AVSGPtr@@AEBU_GUID@@@Z; CInkModule::CGuidMgr::Manage(_GUID const &)
0x18000f418  nop
0x18000f419  lea     rcx, stru_18016D440; lpCriticalSection
0x18000f420  call    cs:__imp_LeaveCriticalSection
0x18000f426  mov     r13, [r14+20h]
0x18000f42a  mov     r15, [rsp+1B0h+var_140]
0x18000f42f  test    r13, r13
0x18000f432  jz      loc_18000F59E
0x18000f438  mov     r12, [r14+18h]
0x18000f43c  mov     rbx, [r12]
0x18000f440  cmp     r15, rbx
0x18000f443  jz      loc_18000F597
0x18000f449  test    r15, r15
0x18000f44c  jz      loc_18000F59E
0x18000f452  test    rbx, rbx
0x18000f455  jz      short loc_18000F4A4
0x18000f457  lea     rdx, [rbx+10h]; Buf2
0x18000f45b  lea     rcx, [r15+10h]; Buf1
0x18000f45f  mov     r8d, 10h; Size
0x18000f465  call    memcmp_0
0x18000f46a  test    eax, eax
0x18000f46c  js      loc_18000F59E
0x18000f472  cmp     r15, rbx
0x18000f475  jz      loc_18000F597
0x18000f47b  test    rbx, rbx
0x18000f47e  jz      short loc_18000F4A4
0x18000f480  test    r15, r15
0x18000f483  jz      loc_18000F597
0x18000f489  lea     rdx, [r15+10h]; Buf2
0x18000f48d  lea     rcx, [rbx+10h]; Buf1
0x18000f491  mov     r8d, 10h; Size
0x18000f497  call    memcmp_0
0x18000f49c  test    eax, eax
0x18000f49e  jns     loc_18000F597
0x18000f4a4  mov     rax, r13
0x18000f4a7  shl     rax, 5
0x18000f4ab  mov     rcx, [rax+r12-20h]
0x18000f4b0  cmp     r15, rcx
0x18000f4b3  jz      short loc_18000F4DE
0x18000f4b5  test    rcx, rcx
0x18000f4b8  jz      short loc_18000F4D6
0x18000f4ba  test    r15, r15
0x18000f4bd  jz      short loc_18000F4DE
0x18000f4bf  lea     rdx, [r15+10h]; Buf2
0x18000f4c3  add     rcx, 10h; Buf1
0x18000f4c7  mov     r8d, 10h; Size
0x18000f4cd  call    memcmp_0
0x18000f4d2  test    eax, eax
0x18000f4d4  jns     short loc_18000F4DE
0x18000f4d6  mov     rax, r12
0x18000f4d9  jmp     loc_18000F5A2
0x18000f4de  xor     r12d, r12d
0x18000f4e1  mov     rdx, r13
0x18000f4e4  mov     [rsp+1B0h+var_158], rdx
0x18000f4e9  mov     rbx, r13
0x18000f4ec  shr     rbx, 1
0x18000f4ef  jz      short loc_18000F548
0x18000f4f1  mov     rcx, [r14+18h]
0x18000f4f5  mov     rax, rbx
0x18000f4f8  shl     rax, 5
0x18000f4fc  mov     r8, [rax+rcx]
0x18000f500  cmp     r15, r8
0x18000f503  jz      short loc_18000F534
0x18000f505  test    r8, r8
0x18000f508  jz      short loc_18000F52F
0x18000f50a  test    r15, r15
0x18000f50d  jz      short loc_18000F534
0x18000f50f  lea     rdx, [r15+10h]; Buf2
0x18000f513  lea     rcx, [r8+10h]; Buf1
0x18000f517  mov     r8d, 10h; Size
0x18000f51d  call    memcmp_0
0x18000f522  mov     rcx, [r14+18h]
0x18000f526  test    eax, eax
0x18000f528  jns     short loc_18000F534
0x18000f52a  mov     rdx, [rsp+1B0h+var_158]
0x18000f52f  mov     r12, rbx
0x18000f532  jmp     short loc_18000F53C
0x18000f534  mov     rdx, rbx
0x18000f537  mov     [rsp+1B0h+var_158], rbx
0x18000f53c  lea     rbx, [r12+rdx]
0x18000f540  shr     rbx, 1
0x18000f543  cmp     r12, rbx
0x18000f546  jb      short loc_18000F4F5
0x18000f548  inc     rbx
0x18000f54b  mov     rcx, rbx
0x18000f54e  shl     rcx, 5
  ... truncated ...
```
