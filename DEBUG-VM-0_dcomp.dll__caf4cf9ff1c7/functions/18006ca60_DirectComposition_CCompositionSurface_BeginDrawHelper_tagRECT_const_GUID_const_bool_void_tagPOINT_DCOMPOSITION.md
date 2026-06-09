# DirectComposition::CCompositionSurface::BeginDrawHelper(tagRECT const *,_GUID const &,bool,void * *,tagPOINT *,DCOMPOSITION_GUTTERS *)

- ea: `0x18006ca60`
- end: `0x18006d7dc`
- name: `?BeginDrawHelper@CCompositionSurface@DirectComposition@@QEAAJPEBUtagRECT@@AEBU_GUID@@_NPEAPEAXPEAUtagPOINT@@PEAUDCOMPOSITION_GUTTERS@@@Z`
- size: `3452`
- prototype: `int(DirectComposition::CCompositionSurface *__hidden this, const struct tagRECT *, const struct _GUID *, bool, void **, struct tagPOINT *, struct DCOMPOSITION_GUTTERS *)`
- caller_count: `3`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006ca30`
- `0x1800a90c0`
- `0x1800fd910`

## callees

- `0x18001f860`
- `0x18001ff20`
- `0x180021140`
- `0x1800223f4`
- `0x180022974`
- `0x180023fa0`
- `0x180023ffc`
- `0x180025538`
- `0x180026b04`
- `0x180060644`
- `0x180060928`
- `0x180062b80`
- `0x18006a0dc`
- `0x18006c5e0`
- `0x18006c6e8`
- `0x18006ca60`
- `0x18006e0e8`
- `0x18006e6ac`
- `0x18006ee40`
- `0x18006eea4`
- `0x18006ef08`
- `0x1800df108`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d3c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d3c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ce46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ce46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ce7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cf92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ce7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cf92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ce69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cf7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006ce69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006cf7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d600`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006d600`

## pseudocode

```c
__int64 __fastcall DirectComposition::CCompositionSurface::BeginDrawHelper(
        DirectComposition::CCompositionSurface *this,
        const struct tagRECT *a2,
        struct _GUID *a3,
        char a4,
        void **a5,
        struct tagPOINT *a6,
        struct DCOMPOSITION_GUTTERS *a7)
{
  DirectComposition::CCompositionSurface *v7; // r15
  __int64 v10; // rax
  _QWORD *v11; // r13
  __int64 v12; // r9
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  LONG left; // ecx
  LONG top; // edx
  LONG right; // r8d
  unsigned __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  _BYTE *v23; // rcx
  int v24; // edi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  struct DirectComposition::CDxDevice *v28; // r12
  __int64 v29; // rcx
  __int64 v30; // rax
  struct DirectComposition::CDxDevice *v31; // rsi
  DirectComposition::CDevice *v32; // rcx
  DirectComposition::CBitmapInfoBack *v33; // rcx
  struct DCOMPOSITION_GUTTERS *v34; // rsi
  __int64 v35; // rbx
  struct tagRECT *v36; // r12
  __int64 v37; // rax
  __int64 v38; // rdi
  __int64 v39; // rsi
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rcx
  LONG bottom; // ecx
  __int64 *v44; // r15
  HANDLE ProcessHeap; // rax
  char *v46; // rax
  char *v47; // rsi
  DirectComposition::CSurfaceFactory *v48; // rcx
  __int64 v49; // rdx
  int v50; // r8d
  __int64 v51; // rcx
  struct DCOMPOSITION_GUTTERS *v52; // r8
  __int64 *v53; // rbx
  __int64 v54; // rcx
  __int64 v55; // r15
  const struct tagRECT *p_right; // r12
  HANDLE v57; // rax
  char *v58; // rax
  char *v59; // rsi
  DirectComposition::CSurfaceFactory *v60; // rcx
  int v61; // edx
  __int64 v62; // rcx
  __int64 v63; // r15
  __int128 v64; // xmm6
  __int64 v65; // rbx
  LONG v66; // r12d
  LONG v67; // eax
  LONG v68; // r9d
  __int64 v69; // r11
  LONG v70; // r10d
  DXGI_ALPHA_MODE v71; // edi
  int v72; // ecx
  int v73; // r8d
  LONG v74; // r12d
  int v75; // edx
  int v76; // ecx
  LONG v77; // r9d
  LONG v78; // eax
  LONG v79; // r10d
  struct DCOMPOSITION_GUTTERS **v80; // r8
  unsigned int v81; // edx
  LONG v82; // esi
  LONG *v83; // rcx
  LONG v84; // r9d
  char v85; // dl
  LONG v86; // r8d
  char v87; // al
  struct tagRECT v88; // xmm0
  LONG *v89; // rcx
  LONG v90; // r9d
  char v91; // dl
  LONG v92; // r8d
  char v93; // al
  struct tagRECT v94; // xmm0
  __int64 v95; // rax
  __int64 v96; // rax
  void **v97; // rcx
  struct tagPOINT *v98; // rax
  __int64 v99; // rcx
  bool v100; // zf
  char v102; // r8
  LONG v103; // edx
  __int64 v104; // rcx
  int v105; // eax
  __int64 v106; // r12
  struct tagRECT *v107; // r12
  __int64 v108; // xmm1_8
  LONG v109; // eax
  LONG v110; // eax
  LONG v111; // eax
  LONG v112; // eax
  LONG v113; // eax
  LONG v114; // eax
  __int64 v115; // rbx
  unsigned int v116; // edx
  int v117; // edx
  int v118; // ecx
  LONG v119; // eax
  __int64 v120; // rcx
  struct DirectComposition::CAtlasSurface **v121; // [rsp+28h] [rbp-E0h]
  char v123; // [rsp+59h] [rbp-AFh]
  struct tagRECT *v124; // [rsp+60h] [rbp-A8h] BYREF
  struct DirectComposition::CDxDevice *v125; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v126; // [rsp+70h] [rbp-98h] BYREF
  __int64 v127; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v128; // [rsp+80h] [rbp-88h]
  LONG v129; // [rsp+88h] [rbp-80h] BYREF
  LONG v130; // [rsp+90h] [rbp-78h] BYREF
  DirectComposition::CCompositionSurface *v131; // [rsp+98h] [rbp-70h]
  void *v132; // [rsp+A0h] [rbp-68h] BYREF
  void **v133; // [rsp+A8h] [rbp-60h]
  struct tagPOINT *v134; // [rsp+B0h] [rbp-58h]
  struct DCOMPOSITION_GUTTERS *v135; // [rsp+B8h] [rbp-50h]
  __int128 v136; // [rsp+C0h] [rbp-48h] BYREF
  struct tagRECT v137; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v138; // [rsp+E0h] [rbp-28h]
  struct tagRECT v139; // [rsp+E8h] [rbp-20h] BYREF
  struct DCOMPOSITION_GUTTERS *v140[2]; // [rsp+F8h] [rbp-10h] BYREF
  char v141; // [rsp+108h] [rbp+0h] BYREF
  __int64 *v142; // [rsp+118h] [rbp+10h]
  __int64 v143; // [rsp+120h] [rbp+18h]
  void *v144; // [rsp+128h] [rbp+20h]
  __int64 v145; // [rsp+130h] [rbp+28h]
  struct DCOMPOSITION_GUTTERS **v146; // [rsp+138h] [rbp+30h]
  __int64 v147; // [rsp+140h] [rbp+38h]
  LONG *v148; // [rsp+148h] [rbp+40h]
  __int64 v149; // [rsp+150h] [rbp+48h]
  LONG *v150; // [rsp+158h] [rbp+50h]
  __int64 v151; // [rsp+160h] [rbp+58h]
  struct tagRECT **v152; // [rsp+168h] [rbp+60h]
  __int64 v153; // [rsp+170h] [rbp+68h]
  __int64 *v154; // [rsp+178h] [rbp+70h]
  __int64 v155; // [rsp+180h] [rbp+78h]
  struct _GUID *v156; // [rsp+188h] [rbp+80h]
  void *retaddr; // [rsp+1F0h] [rbp+E8h]

  v7 = this;
  v135 = a7;
  v10 = *((_QWORD *)this + 4);
  v131 = this;
  v156 = a3;
  v11 = (_QWORD *)(*(_QWORD *)(v10 + 24) + 104LL);
  v134 = a6;
  v133 = a5;
  if ( *v11 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 32LL))(*v11) )
      *((_BYTE *)v11 + 52) = 1;
    ++*((_DWORD *)v11 + 12);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1));
  }
  v12 = 8;
  v13 = *((_QWORD *)v7 + 5);
  v132 = 0;
  v14 = *(_QWORD *)(v13 + 44);
  v128 = (__int64 *)v14;
  if ( (Microsoft_Windows_DirectCompositionEnableBits & 2) != 0 )
  {
    if ( a2 )
    {
      left = a2->left;
      top = a2->top;
      right = a2->right;
      LODWORD(v18) = a2->bottom;
    }
    else
    {
      right = v14;
      v18 = HIDWORD(v14);
      left = 0;
      top = 0;
    }
    LODWORD(v127) = v18;
    v19 = *((_QWORD *)v7 + 4);
    v130 = top;
    v129 = left;
    LODWORD(v124) = right;
    v140[0] = v7;
    LODWORD(v125) = 32;
    v20 = *(_QWORD *)(v19 + 24);
    v143 = 4;
    v145 = 4;
    v147 = 8;
    LODWORD(v126) = *(_DWORD *)(v20 + 168);
    v142 = &v126;
    v144 = &v125;
    v146 = v140;
    v148 = &v129;
    v150 = &v130;
    v152 = &v124;
    v154 = &v127;
    v121 = (struct DirectComposition::CAtlasSurface **)&v141;
    v149 = 4;
    v151 = 4;
    v153 = 4;
    v155 = 4;
    McGenEventWrite_EventWriteTransfer(v20, &DCOMPEVENT_BEGIN_DRAW_Start);
  }
  if ( !a5 || !a6 )
    goto LABEL_51;
  v21 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_e8f7fe7a_191c_466d_ad95_975678bda998.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_e8f7fe7a_191c_466d_ad95_975678bda998.Data1 )
    v21 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_e8f7fe7a_191c_466d_ad95_975678bda998.Data4;
  v22 = *((_QWORD *)v7 + 4);
  if ( !v21 && *(int *)(*(_QWORD *)(v22 + 24) + 376LL) < 1 )
    goto LABEL_51;
  v23 = (_BYTE *)(v22 + 361);
  if ( *(_DWORD *)(v22 + 352) )
  {
    v24 = -2147467259;
  }
  else
  {
    v24 = 0;
    if ( !*v23 )
      goto LABEL_16;
    if ( *((_DWORD *)v7 + 7) != 1 || *(int *)(*(_QWORD *)(v22 + 24) + 376LL) < 1 )
      goto LABEL_180;
  }
  if ( *v23 )
    goto LABEL_17;
LABEL_16:
  if ( *((_DWORD *)v7 + 7) == 2 && *(int *)(*(_QWORD *)(v22 + 24) + 376LL) < 1 )
LABEL_180:
    v24 = -2003302399;
LABEL_17:
  v25 = *((_QWORD *)v7 + 5);
  v26 = *(_QWORD *)(v25 + 44);
  if ( v24 < 0 )
    goto LABEL_25;
  if ( !(_DWORD)v26 )
  {
    v24 = -2147483634;
    goto LABEL_25;
  }
  if ( !a2 )
    goto LABEL_25;
  if ( (*(_BYTE *)(v25 + 112) & 1) == 0 && !*((_QWORD *)v7 + 6) )
  {
    if ( !a2->left && *(_QWORD *)&a2->top == __PAIR64__(v26, 0) && a2->bottom == HIDWORD(v26) )
      goto LABEL_25;
LABEL_51:
    v24 = -2147024809;
    goto LABEL_25;
  }
  if ( a2->left < 0 )
    goto LABEL_51;
  if ( a2->right <= a2->left )
    goto LABEL_51;
  if ( a2->right > (unsigned int)v26 )
    goto LABEL_51;
  if ( a2->top < 0 )
    goto LABEL_51;
  bottom = a2->bottom;
  if ( bottom <= a2->top || (unsigned int)bottom > HIDWORD(v26) )
    goto LABEL_51;
LABEL_25:
  v27 = *((_QWORD *)v7 + 4);
  v28 = 0;
  v125 = 0;
  v29 = v27 + 8;
  v30 = -v27;
  v31 = (struct DirectComposition::CDxDevice *)(v29 & -(__int64)(v30 != 0));
  if ( v24 < 0 )
    goto LABEL_159;
  v32 = *(DirectComposition::CDevice **)((v29 & -(__int64)(v30 != 0)) + 0x10);
  if ( *((_BYTE *)v32 + 921) )
  {
    v24 = DirectComposition::CDevice::CheckClientDrawNotInProgress(v32);
    if ( v24 < 0 )
    {
      v125 = 0;
      goto LABEL_159;
    }
    v125 = v31;
    v28 = v31;
    DirectComposition::MultithreadDeviceLock::Enter(v31);
  }
  v136 = 0;
  if ( !a2 )
  {
    a2 = (const struct tagRECT *)&v136;
    *((_QWORD *)&v136 + 1) = __PAIR64__(HIDWORD(v128), v14);
  }
  v33 = (DirectComposition::CBitmapInfoBack *)*((_QWORD *)v7 + 6);
  v34 = (struct DCOMPOSITION_GUTTERS *)&v127;
  if ( !a4 )
    v34 = v135;
  v140[0] = v34;
  LODWORD(v127) = 0;
  v128 = (__int64 *)((char *)v7 + 48);
  if ( v33 )
  {
    v123 = 0;
    DirectComposition::CBitmapInfoBack::EndDraw(v33);
    v53 = (__int64 *)((char *)v7 + 48);
LABEL_82:
    v65 = *v53;
    v66 = a2->left;
    v67 = a2->top;
    v68 = a2->right;
    v69 = *(_QWORD *)(v65 + 16);
    v70 = a2->bottom;
    v71 = *(_DWORD *)(v65 + 40);
    *(_OWORD *)v140 = 0;
    v72 = *(_DWORD *)(v69 + 76);
    v73 = *(_DWORD *)(v69 + 72) + (*(_DWORD *)(v69 + 88) & 1);
    v74 = v73 + v66;
    v75 = (*(_DWORD *)(v69 + 88) >> 2) & 1;
    v139.left = v74;
    v76 = v75 + v72;
    v77 = v73 + v68;
    v78 = v76 + v67;
    v139.right = v77;
    v79 = v76 + v70;
    LODWORD(v126) = v78;
    v139.top = v78;
    v139.bottom = v79;
    if ( a4 )
    {
      v116 = *(_DWORD *)v34;
      v80 = v140;
      v82 = v126;
      LODWORD(v140[0]) = v74 - (v116 & 1);
      HIDWORD(v140[0]) = v126 - ((v116 >> 2) & 1);
      LODWORD(v140[1]) = v77 + ((v116 >> 1) & 1);
      HIDWORD(v140[1]) = v79 + ((v116 >> 3) & 1);
    }
    else
    {
      v80 = 0;
      if ( v34 )
      {
        v81 = *(_DWORD *)v34;
        v82 = v126;
        v139.left = v74 - (v81 & 1);
        v139.top = v126 - ((v81 >> 2) & 1);
        v139.right = v77 + ((v81 >> 1) & 1);
        v139.bottom = v79 + ((v81 >> 3) & 1);
      }
      else
      {
        v82 = v78;
      }
    }
    v24 = DirectComposition::CAtlasSurfacePool::BeginDraw(
            *(DirectComposition::CAtlasSurfacePool **)(v69 + 64),
            &v139,
            (const struct tagRECT *)v80,
            v156,
            1,
            v71,
            &v132,
            (struct ID2D1Bitmap **)(v65 + 136),
            (struct ID2D1DrawingStateBlock **)(v65 + 152));
    if ( v24 < 0 )
    {
      if ( v123 )
        goto LABEL_158;
      goto LABEL_159;
    }
    v83 = (LONG *)(v65 + 72);
    *(struct tagRECT *)(v65 + 56) = *a2;
    if ( v65 != -72 )
    {
      v84 = *(_DWORD *)(v65 + 80);
      if ( *v83 >= v84 || (v85 = 0, *(_DWORD *)(v65 + 76) >= *(_DWORD *)(v65 + 84)) )
        v85 = 1;
      v86 = a2->left;
      if ( a2->left >= a2->right || (v87 = 0, a2->top >= a2->bottom) )
        v87 = 1;
      if ( v85 )
      {
        if ( !v87 )
        {
          v88 = *a2;
LABEL_94:
          *(struct tagRECT *)v83 = v88;
          goto LABEL_95;
        }
        *(_QWORD *)v83 = 0;
        *(_QWORD *)(v65 + 80) = 0;
      }
      else
      {
        if ( v87 )
        {
          v88 = *(struct tagRECT *)v83;
          goto LABEL_94;
        }
        if ( *v83 < v86 )
          v86 = *v83;
        *v83 = v86;
        v109 = *(_DWORD *)(v65 + 76);
        if ( v109 >= a2->top )
          v109 = a2->top;
        *(_DWORD *)(v65 + 76) = v109;
        v110 = a2->right;
        if ( v84 > v110 )
          v110 = v84;
        *(_DWORD *)(v65 + 80) = v110;
        v111 = *(_DWORD *)(v65 + 84);
        if ( v111 <= a2->bottom )
          v111 = a2->bottom;
        *(_DWORD *)(v65 + 84) = v111;
      }
    }
LABEL_95:
    v89 = (LONG *)(v65 + 88);
    if ( v65 != -88 )
    {
      v90 = *(_DWORD *)(v65 + 96);
      if ( *v89 >= v90 || (v91 = 0, *(_DWORD *)(v65 + 92) >= *(_DWORD *)(v65 + 100)) )
        v91 = 1;
      v92 = a2->left;
      if ( a2->left >= a2->right || (v93 = 0, a2->top >= a2->bottom) )
        v93 = 1;
      if ( v91 )
      {
        if ( v93 )
        {
          *(_QWORD *)v89 = 0;
          *(_QWORD *)(v65 + 96) = 0;
          goto LABEL_104;
        }
        v94 = *a2;
      }
      else
      {
        if ( !v93 )
        {
          if ( *v89 < v92 )
            v92 = *v89;
          *v89 = v92;
          v112 = *(_DWORD *)(v65 + 92);
          if ( v112 >= a2->top )
            v112 = a2->top;
          *(_DWORD *)(v65 + 92) = v112;
          v113 = a2->right;
          if ( v90 > v113 )
            v113 = v90;
          *(_DWORD *)(v65 + 96) = v113;
          v114 = *(_DWORD *)(v65 + 100);
          if ( v114 <= a2->bottom )
            v114 = a2->bottom;
          *(_DWORD *)(v65 + 100) = v114;
          goto LABEL_104;
        }
        v94 = *(struct tagRECT *)v89;
      }
      *(struct tagRECT *)v89 = v94;
    }
LABEL_104:
    *(_BYTE *)(v65 + 160) = 1;
    if ( !*((_DWORD *)v7 + 7) )
    {
      v95 = *((_QWORD *)v7 + 4);
      ++*(_DWORD *)(v95 + 356);
      ++*(_DWORD *)(*(_QWORD *)(v95 + 24) + 400LL);
    }
    v96 = *((_QWORD *)v7 + 4);
    v97 = v133;
    *((_DWORD *)v7 + 7) = 1;
    *(_BYTE *)(v96 + 361) = 1;
    *v97 = v132;
    v98 = v134;
    v134->x = v74;
    v98->y = v82;
    goto LABEL_107;
  }
  v35 = *((_QWORD *)v7 + 5);
  v123 = 1;
  if ( (*(_BYTE *)(v35 + 112) & 1) == 0 )
  {
    v44 = (__int64 *)(v35 + 16);
    v24 = 0;
    if ( !*(_QWORD *)(v35 + 16) )
    {
      v24 = DirectComposition::CBitmapInfoFront::RequestSurface(
              (DirectComposition::CBitmapInfoFront *)v35,
              *(_DWORD *)(v35 + 44),
              *(_DWORD *)(v35 + 48),
              (struct DirectComposition::CAtlasSurface **)(v35 + 16));
      if ( v24 < 0 )
        goto LABEL_132;
      *(_QWORD *)(*v44 + 96) = v35;
      if ( (Microsoft_Windows_DirectCompositionEnableBits & 8) != 0 )
        McTemplateU0xxqdd_EventWriteTransfer(v118, v117, *v44, (_DWORD)v131, 3);
    }
    v125 = v28;
    ProcessHeap = GetProcessHeap();
    v46 = (char *)HeapAlloc(ProcessHeap, 8u, 0xA8u);
    v47 = v46;
    if ( v46 )
    {
      v48 = *(DirectComposition::CSurfaceFactory **)(v35 + 24);
      v49 = *v44;
      v50 = *(_DWORD *)(v35 + 40);
      *((_DWORD *)v46 + 2) = 0;
      *(_QWORD *)v46 = &DirectComposition::CBitmapInfo::`vftable';
      *((_QWORD *)v46 + 2) = v49;
      *((_DWORD *)v46 + 10) = v50;
      *(_QWORD *)(v46 + 44) = 0;
      *((_QWORD *)v46 + 3) = v48;
      if ( v48 )
        DirectComposition::CSurfaceFactory::AddRef(v48);
      v51 = *((_QWORD *)v47 + 2);
      if ( v51 )
        CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v51 + 8));
      v52 = v140[0];
      *(_QWORD *)v47 = &DirectComposition::CBitmapInfoBack::`vftable';
      *((_DWORD *)v47 + 32) = 0x7FFFFFFF;
      *((_DWORD *)v47 + 30) = 0x7FFFFFFF;
      *((_DWORD *)v47 + 28) = 0x7FFFFFFF;
      *((_DWORD *)v47 + 26) = 0x7FFFFFFF;
      *((_DWORD *)v47 + 33) = 0x80000000;
      *((_DWORD *)v47 + 31) = 0x80000000;
      *((_DWORD *)v47 + 29) = 0x80000000;
      *((_DWORD *)v47 + 27) = 0x80000000;
      DirectComposition::CBitmapInfoBack::DirtyGuttersForUpdate((DirectComposition::CBitmapInfoBack *)v47, a2, v52);
      CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v47 + 8));
      v53 = v128;
      *v128 = (__int64)v47;
      goto LABEL_80;
    }
    v24 = -2147024882;
    v125 = v28;
LABEL_132:
    v53 = v128;
    goto LABEL_80;
  }
  LODWORD(v126) = 0;
  v138 = 0;
  v36 = &v137;
  v37 = *(_QWORD *)(v35 + 24);
  v124 = &v137;
  v137 = 0;
  v38 = *(_QWORD *)(v37 + 24);
  if ( (*(int (__fastcall **)(_QWORD, __int64, __int64 *, __int64, struct DirectComposition::CAtlasSurface **))(**(_QWORD **)(v38 + 168) + 56LL))(
         *(_QWORD *)(v38 + 168),
         2,
         &v126,
         v12,
         v121) >= 0 )
    *(_DWORD *)(v38 + 392) = v126;
  v39 = 0;
  v40 = 0;
  do
  {
    v41 = *(_QWORD *)(v35 + 24 * v39 + 128);
    if ( !v41 )
      break;
    if ( *(_QWORD *)(v41 + 96) == v35 )
    {
      if ( !v36 )
        goto LABEL_39;
      v106 = v41 + 16;
      if ( !DirectComposition::CCompositorSynchronizedObject::IsAvailable((DirectComposition::CCompositorSynchronizedObject *)(v41 + 16)) )
      {
        v36 = v124;
LABEL_39:
        if ( (_DWORD)v40 != (_DWORD)v39 )
        {
          v42 = 3 * v40;
          *(_OWORD *)(v35 + 8 * v42 + 128) = *(_OWORD *)(v35 + 24 * v39 + 128);
          *(_QWORD *)(v35 + 8 * v42 + 144) = *(_QWORD *)(v35 + 24 * v39 + 144);
        }
        v40 = (unsigned int)(v40 + 1);
        goto LABEL_120;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 32LL))(v106);
      v107 = v124;
      v108 = *(_QWORD *)(v35 + 24 * v39 + 144);
      *v124 = *(struct tagRECT *)(v35 + 24 * v39 + 128);
      *(_QWORD *)&v107[1].left = v108;
      v36 = 0;
      v124 = 0;
    }
    else
    {
      CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease(*(_QWORD *)(v35 + 24 * v39 + 128));
    }
LABEL_120:
    v39 = (unsigned int)(v39 + 1);
  }
  while ( (unsigned int)v39 < 3 );
  while ( (_DWORD)v40 != (_DWORD)v39 )
  {
    v54 = 3 * v40;
    v40 = (unsigned int)(v40 + 1);
    *(_QWORD *)(v35 + 8 * v54 + 128) = 0;
  }
  if ( !v36 )
  {
    v55 = *(_QWORD *)&v137.left;
    p_right = (const struct tagRECT *)&v137.right;
    v24 = 0;
    *(_QWORD *)(*(_QWORD *)&v137.left + 96LL) = 0;
    goto LABEL_67;
  }
  v102 = *(_BYTE *)(v35 + 112);
  v103 = *(_DWORD *)(v35 + 44);
  if ( (v102 & 0x10) != 0 )
  {
    v119 = *(_DWORD *)(v35 + 52);
    v139.right = *(_DWORD *)(v35 + 48);
    v120 = *(_QWORD *)(v35 + 24);
    v139.top = v103;
    v139.left = v119;
    LOWORD(v139.bottom) = 0;
    v105 = DirectComposition::CSurfaceManager::RequestLargeSurface(
             *(DirectComposition::CSurfaceManager **)(v120 + 320),
             (struct DirectComposition::CAtlasSurface **)&v137,
             (const struct DirectComposition::SurfaceRequestStruct *)&v139,
             0);
  }
  else
  {
    HIDWORD(v124) = *(_DWORD *)(v35 + 48);
    v104 = *(_QWORD *)(v35 + 24);
    LODWORD(v124) = v103;
    v105 = DirectComposition::CSurfaceManager::RequestSurface(
             *(DirectComposition::CSurfaceManager **)(v104 + 320),
             (enum DXGI_FORMAT)*(_DWORD *)(v35 + 52),
             (v102 & 4) != 0,
             (const struct DirectComposition::SizeU *)&v124,
             (struct DirectComposition::CAtlasSurface **)&v137);
  }
  v55 = *(_QWORD *)&v137.left;
  v24 = v105;
  if ( v105 >= 0 )
    *(_QWORD *)(*(_QWORD *)&v137.left + 96LL) = 0;
  p_right = 0;
  v124 = 0;
  if ( v105 >= 0 )
  {
LABEL_67:
    v57 = GetProcessHeap();
    v58 = (char *)HeapAlloc(v57, 8u, 0xA8u);
    v59 = v58;
    if ( !v58 )
    {
      v24 = -2147024882;
      v124 = 0;
      goto LABEL_127;
    }
    v60 = *(DirectComposition::CSurfaceFactory **)(v35 + 24);
    v61 = *(_DWORD *)(v35 + 40);
    *((_DWORD *)v58 + 2) = 0;
    *(_QWORD *)v58 = &DirectComposition::CBitmapInfo::`vftable';
    *((_QWORD *)v58 + 2) = v55;
    *((_DWORD *)v58 + 10) = v61;
    *(_QWORD *)(v58 + 44) = 0;
    *((_QWORD *)v58 + 3) = v60;
    if ( v60 )
      DirectComposition::CSurfaceFactory::AddRef(v60);
    v62 = *((_QWORD *)v59 + 2);
    if ( v62 )
      CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v62 + 8));
    *(_QWORD *)v59 = &DirectComposition::CBitmapInfoBack::`vftable';
    *((_DWORD *)v59 + 32) = 0x7FFFFFFF;
    *((_DWORD *)v59 + 30) = 0x7FFFFFFF;
    *((_DWORD *)v59 + 28) = 0x7FFFFFFF;
    *((_DWORD *)v59 + 26) = 0x7FFFFFFF;
    *((_DWORD *)v59 + 33) = 0x80000000;
    *((_DWORD *)v59 + 31) = 0x80000000;
    *((_DWORD *)v59 + 29) = 0x80000000;
    *((_DWORD *)v59 + 27) = 0x80000000;
    CMILRefCountImpl::AddReference((CMILRefCountImpl *)(v59 + 8));
    v63 = *(_QWORD *)(v35 + 120);
    v64 = 0;
    if ( v63 )
    {
      v64 = *(_OWORD *)(v63 + 88);
      DirectComposition::CBitmapInfoBack::InitializeGutterDirtiness(
        (DirectComposition::CBitmapInfoBack *)v59,
        *(struct DirectComposition::CBitmapInfoBack **)(v35 + 120));
      DirectComposition::CBitmapInfoBack::FlushD2DRendering(*(DirectComposition::CBitmapInfoBack **)(v35 + 120));
    }
    else
    {
      v63 = v35;
    }
    DirectComposition::CBitmapInfoBack::InitializeFromSurface(
      (DirectComposition::CBitmapInfoBack *)v59,
      *(struct DirectComposition::CAtlasSurface **)(v63 + 16),
      a2,
      p_right);
    DirectComposition::CBitmapInfoBack::DirtyGuttersForUpdate((DirectComposition::CBitmapInfoBack *)v59, a2, v140[0]);
    *(_OWORD *)(v59 + 88) = v64;
    if ( (Microsoft_Windows_DirectCompositionEnableBits & 8) != 0 )
    {
      *(_QWORD *)&v139.left = v131;
      LODWORD(v124) = 4;
      v129 = 0;
      v130 = 0;
      v126 = *((_QWORD *)v59 + 2);
      v142 = &v126;
      v144 = &v139;
      v146 = (struct DCOMPOSITION_GUTTERS **)&v124;
      v148 = &v130;
      v150 = &v129;
      v147 = 4;
      v149 = 4;
      v151 = 4;
      v143 = 8;
      v145 = 8;
      McGenEventWrite_EventWriteTransfer(8, &DCOMPEVENT_ATLAS_USE_INFO);
    }
    v53 = v128;
    v55 = *(_QWORD *)&v137.left;
    v124 = 0;
    *v128 = (__int64)v59;
  }
  else
  {
LABEL_127:
    v53 = v128;
  }
  if ( v55 )
    CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease(v55);
  ReleaseInterface<DirectComposition::CBitmapInfoBack>(&v124);
LABEL_80:
  if ( v24 >= 0 )
  {
    v7 = v131;
    v34 = v140[0];
    goto LABEL_82;
  }
LABEL_158:
  ReleaseInterface<DirectComposition::CBitmapInfoBack>(v128);
LABEL_159:
  v97 = v133;
  if ( v133 )
    *v133 = 0;
  if ( v134 )
  {
    v97 = 0;
    *v134 = 0;
  }
  if ( v135 )
  {
    v97 = 0;
    *(_DWORD *)v135 = 0;
  }
LABEL_107:
  if ( (Microsoft_Windows_DirectCompositionEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v97, &DCOMPEVENT_BEGIN_DRAW_Stop);
  if ( v125 )
  {
    if ( v24 < 0 )
    {
      DirectComposition::MultithreadDeviceLock::Leave(v125);
    }
    else
    {
      v115 = *((_QWORD *)v125 + 2);
      DirectComposition::CDeviceLock::AssertIsOwned((DirectComposition::CDeviceLock *)(v115 + 104));
      if ( *(_DWORD *)(v115 + 676) )
        ModuleFailFastForHRESULT(2291664897LL, retaddr);
      *(_DWORD *)(v115 + 676) = GetCurrentThreadId();
    }
  }
  if ( v11 )
  {
    if ( *v11 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 48LL))(*v11);
    v99 = *v11;
    if ( *v11 )
    {
      v100 = (*((_DWORD *)v11 + 12))-- == 1;
      if ( v100 && *((_BYTE *)v11 + 52) )
      {
        *((_BYTE *)v11 + 52) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
      }
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 1));
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18006ca60  mov     rax, rsp
0x18006ca63  mov     [rax+20h], rbx
0x18006ca67  push    rbp
0x18006ca68  push    rsi
0x18006ca69  push    rdi
0x18006ca6a  push    r12
0x18006ca6c  push    r13
0x18006ca6e  push    r14
0x18006ca70  push    r15
0x18006ca72  lea     rbp, [rax-0E8h]
0x18006ca79  sub     rsp, 1B0h
0x18006ca80  movaps  xmmword ptr [rax-48h], xmm6
0x18006ca84  mov     rax, cs:__security_cookie
0x18006ca8b  xor     rax, rsp
0x18006ca8e  mov     [rbp+0E0h+var_50], rax
0x18006ca95  mov     rax, [rbp+0E0h+arg_30]
0x18006ca9c  mov     r15, rcx
0x18006ca9f  mov     rsi, [rbp+0E0h+arg_28]
0x18006caa6  mov     rdi, r8
0x18006caa9  mov     r12, [rbp+0E0h+arg_20]
0x18006cab0  mov     r14, rdx
0x18006cab3  mov     [rbp+0E0h+var_130], rax
0x18006cab7  mov     rax, [rcx+20h]
0x18006cabb  mov     [rbp+0E0h+var_150], rcx
0x18006cabf  mov     byte ptr [rsp+1E0h+var_190], r9b
0x18006cac4  mov     [rbp+0E0h+var_60], r8
0x18006cacb  mov     r13, [rax+18h]
0x18006cacf  add     r13, 68h ; 'h'
0x18006cad3  mov     [rbp+0E0h+var_138], rsi
0x18006cad7  mov     [rbp+0E0h+var_140], r12
0x18006cadb  mov     rcx, [r13+0]
0x18006cadf  test    rcx, rcx
0x18006cae2  jz      loc_18006CE42
0x18006cae8  mov     rax, [rcx]
0x18006caeb  mov     rax, [rax+20h]
0x18006caef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006caf4  xor     r10d, r10d
0x18006caf7  test    al, al
0x18006caf9  jz      short loc_18006CB00
0x18006cafb  mov     byte ptr [r13+34h], 1
0x18006cb00  inc     dword ptr [r13+30h]
0x18006cb04  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 2
0x18006cb0b  mov     r9d, 8
0x18006cb11  mov     rbx, [r15+28h]
0x18006cb15  mov     [rbp+0E0h+var_148], r10
0x18006cb19  mov     rbx, [rbx+2Ch]
0x18006cb1d  mov     [rsp+1E0h+var_168], rbx
0x18006cb22  jz      loc_18006CBF5
0x18006cb28  test    r14, r14
0x18006cb2b  jz      loc_18006CF32
0x18006cb31  mov     ecx, [r14]
0x18006cb34  mov     edx, [r14+4]
0x18006cb38  mov     r8d, [r14+8]
0x18006cb3c  mov     eax, [r14+0Ch]
0x18006cb40  mov     dword ptr [rsp+1E0h+var_170], eax
0x18006cb44  mov     rax, [r15+20h]
0x18006cb48  mov     [rbp+0E0h+var_158], edx
0x18006cb4b  lea     rdx, DCOMPEVENT_BEGIN_DRAW_Start
0x18006cb52  mov     [rbp+0E0h+var_160], ecx
0x18006cb55  mov     dword ptr [rsp+1E0h+var_188], r8d
0x18006cb5a  mov     [rbp+0E0h+var_F0], r15
0x18006cb5e  mov     dword ptr [rsp+1E0h+var_180], 20h ; ' '
0x18006cb66  mov     rcx, [rax+18h]
0x18006cb6a  mov     [rbp+0E0h+var_C8], 4
0x18006cb72  mov     [rbp+0E0h+var_B8], 4
0x18006cb7a  mov     [rbp+0E0h+var_A8], r9
0x18006cb7e  mov     eax, [rcx+0A8h]
0x18006cb84  mov     dword ptr [rsp+1E0h+var_178], eax
0x18006cb88  lea     rax, [rsp+1E0h+var_178]
0x18006cb8d  mov     [rbp+0E0h+var_D0], rax
0x18006cb91  lea     rax, [rsp+1E0h+var_180]
0x18006cb96  mov     [rbp+0E0h+var_C0], rax
0x18006cb9a  lea     rax, [rbp+0E0h+var_F0]
0x18006cb9e  mov     [rbp+0E0h+var_B0], rax
0x18006cba2  lea     rax, [rbp+0E0h+var_160]
0x18006cba6  mov     [rbp+0E0h+var_A0], rax
0x18006cbaa  lea     rax, [rbp+0E0h+var_158]
0x18006cbae  mov     [rbp+0E0h+var_90], rax
0x18006cbb2  lea     rax, [rsp+1E0h+var_188]
0x18006cbb7  mov     [rbp+0E0h+var_80], rax
0x18006cbbb  lea     rax, [rsp+1E0h+var_170]
0x18006cbc0  mov     [rbp+0E0h+var_70], rax
0x18006cbc4  lea     rax, [rbp+0E0h+var_E0]
0x18006cbc8  mov     [rsp+1E0h+var_1C0], rax
0x18006cbcd  mov     [rbp+0E0h+var_98], 4
0x18006cbd5  mov     [rbp+0E0h+var_88], 4
0x18006cbdd  mov     [rbp+0E0h+var_78], 4
0x18006cbe5  mov     [rbp+0E0h+var_68], 4
0x18006cbed  call    McGenEventWrite_EventWriteTransfer
0x18006cbf2  xor     r10d, r10d
0x18006cbf5  test    r12, r12
0x18006cbf8  jz      loc_18006CE26
0x18006cbfe  test    rsi, rsi
0x18006cc01  jz      loc_18006CE26
0x18006cc07  mov     rax, [rdi]
0x18006cc0a  sub     rax, qword ptr cs:_GUID_e8f7fe7a_191c_466d_ad95_975678bda998.Data1
0x18006cc11  jnz     short loc_18006CC1E
0x18006cc13  mov     rax, [rdi+8]
0x18006cc17  sub     rax, qword ptr cs:_GUID_e8f7fe7a_191c_466d_ad95_975678bda998.Data4
0x18006cc1e  mov     rdx, [r15+20h]
0x18006cc22  test    rax, rax
0x18006cc25  jz      loc_18006CE30
0x18006cc2b  lea     rcx, [rdx+169h]
0x18006cc32  cmp     [rdx+160h], r10d
0x18006cc39  jnz     loc_18006CDE4
0x18006cc3f  mov     edi, r10d
0x18006cc42  cmp     [rcx], r10b
0x18006cc45  jnz     loc_18006D786
0x18006cc4b  cmp     dword ptr [r15+1Ch], 2
0x18006cc50  jz      loc_18006D681
0x18006cc56  mov     rcx, [r15+28h]
0x18006cc5a  mov     rax, [rcx+2Ch]
0x18006cc5e  test    edi, edi
0x18006cc60  js      short loc_18006CCAE
0x18006cc62  test    eax, eax
0x18006cc64  jz      loc_18006D796
0x18006cc6a  test    r14, r14
0x18006cc6d  jz      short loc_18006CCAE
0x18006cc6f  test    byte ptr [rcx+70h], 1
0x18006cc73  jnz     loc_18006CDF7
0x18006cc79  cmp     [r15+30h], r10
0x18006cc7d  jnz     loc_18006CDF7
0x18006cc83  cmp     [r14], r10d
0x18006cc86  jnz     loc_18006CE26
0x18006cc8c  cmp     [r14+8], eax
0x18006cc90  jnz     loc_18006CE26
0x18006cc96  cmp     [r14+4], r10d
0x18006cc9a  jnz     loc_18006CE26
0x18006cca0  shr     rax, 20h
0x18006cca4  cmp     [r14+0Ch], eax
0x18006cca8  jnz     loc_18006CE26
0x18006ccae  mov     rax, [r15+20h]
0x18006ccb2  mov     r12, r10
0x18006ccb5  mov     [rsp+1E0h+var_180], r10
0x18006ccba  lea     rcx, [rax+8]
0x18006ccbe  neg     rax
0x18006ccc1  sbb     rsi, rsi
0x18006ccc4  and     rsi, rcx
0x18006ccc7  test    edi, edi
0x18006ccc9  js      loc_18006D5AE
0x18006cccf  mov     rcx, [rsi+10h]; this
0x18006ccd3  cmp     [rcx+399h], r10b
0x18006ccda  jnz     loc_18006D632
0x18006cce0  xorps   xmm0, xmm0
0x18006cce3  movups  [rbp+0E0h+var_128], xmm0
0x18006cce7  test    r14, r14
0x18006ccea  jnz     short loc_18006CCFA
0x18006ccec  mov     eax, dword ptr [rsp+1E0h+var_168+4]
0x18006ccf0  lea     r14, [rbp+0E0h+var_128]
0x18006ccf4  mov     dword ptr [rbp+0E0h+var_128+0Ch], eax
0x18006ccf7  mov     dword ptr [rbp+0E0h+var_128+8], ebx
0x18006ccfa  cmp     byte ptr [rsp+1E0h+var_190], r10b
0x18006ccff  lea     rax, [r15+30h]
0x18006cd03  mov     rcx, [rax]; this
0x18006cd06  lea     rsi, [rsp+1E0h+var_170]
0x18006cd0b  cmovz   rsi, [rbp+0E0h+var_130]
0x18006cd10  mov     [rbp+0E0h+var_F0], rsi
0x18006cd14  mov     dword ptr [rsp+1E0h+var_170], r10d
0x18006cd19  mov     [rsp+1E0h+var_168], rax
0x18006cd1e  test    rcx, rcx
0x18006cd21  jnz     loc_18006D4AF
0x18006cd27  mov     rbx, [r15+28h]
0x18006cd2b  mov     byte ptr [rsp+1E0h+var_190+1], 1
0x18006cd30  test    byte ptr [rbx+70h], 1
0x18006cd34  jz      loc_18006CE54
0x18006cd3a  xor     eax, eax
0x18006cd3c  mov     dword ptr [rsp+1E0h+var_178], r10d
0x18006cd41  mov     [rbp+0E0h+var_108], rax
0x18006cd45  lea     r12, [rbp+0E0h+var_118]
0x18006cd49  mov     rax, [rbx+18h]
0x18006cd4d  lea     r8, [rsp+1E0h+var_178]
0x18006cd52  mov     edx, 2
0x18006cd57  mov     [rsp+1E0h+var_188], r12
0x18006cd5c  movups  xmmword ptr [rbp+0E0h+var_118.left], xmm0
0x18006cd60  mov     rdi, [rax+18h]
0x18006cd64  mov     rcx, [rdi+0A8h]
0x18006cd6b  mov     rax, [rcx]
0x18006cd6e  mov     rax, [rax+38h]
0x18006cd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd77  test    eax, eax
0x18006cd79  js      short loc_18006CD85
0x18006cd7b  mov     eax, dword ptr [rsp+1E0h+var_178]
0x18006cd7f  mov     [rdi+188h], eax
0x18006cd85  xor     esi, esi
0x18006cd87  xor     edi, edi
0x18006cd89  lea     r15, [rsi+rsi*2]
0x18006cd8d  mov     rax, [rbx+r15*8+80h]
0x18006cd95  test    rax, rax
0x18006cd98  jz      loc_18006CF59
0x18006cd9e  cmp     [rax+60h], rbx
0x18006cda2  jnz     loc_18006D3D1
0x18006cda8  test    r12, r12
0x18006cdab  jnz     loc_18006D45A
0x18006cdb1  cmp     edi, esi
0x18006cdb3  jz      short loc_18006CDDD
0x18006cdb5  movups  xmm0, xmmword ptr [rbx+r15*8+80h]
0x18006cdbe  lea     rcx, [rdi+rdi*2]
0x18006cdc2  movups  xmmword ptr [rbx+rcx*8+80h], xmm0
0x18006cdca  movsd   xmm1, qword ptr [rbx+r15*8+90h]
0x18006cdd4  movsd   qword ptr [rbx+rcx*8+90h], xmm1
0x18006cddd  inc     edi
0x18006cddf  jmp     loc_18006D3D9
0x18006cde4  mov     edi, 80004005h
0x18006cde9  cmp     [rcx], r10b
0x18006cdec  jnz     loc_18006CC56
0x18006cdf2  jmp     loc_18006CC4B
0x18006cdf7  mov     ecx, [r14]
0x18006cdfa  test    ecx, ecx
0x18006cdfc  js      short loc_18006CE26
0x18006cdfe  cmp     [r14+8], ecx
0x18006ce02  jle     short loc_18006CE26
0x18006ce04  cmp     [r14+8], eax
0x18006ce08  ja      short loc_18006CE26
0x18006ce0a  cmp     [r14+4], r10d
0x18006ce0e  jl      short loc_18006CE26
0x18006ce10  mov     ecx, [r14+0Ch]
0x18006ce14  cmp     ecx, [r14+4]
0x18006ce18  jle     short loc_18006CE26
0x18006ce1a  shr     rax, 20h
0x18006ce1e  cmp     ecx, eax
0x18006ce20  jbe     loc_18006CCAE
0x18006ce26  mov     edi, 80070057h
0x18006ce2b  jmp     loc_18006CCAE
0x18006ce30  mov     rax, [rdx+18h]
0x18006ce34  cmp     dword ptr [rax+178h], 1
0x18006ce3b  jl      short loc_18006CE26
0x18006ce3d  jmp     loc_18006CC2B
0x18006ce42  lea     rcx, [r13+8]; lpCriticalSection
0x18006ce46  call    cs:__imp_EnterCriticalSection
0x18006ce4c  xor     r10d, r10d
0x18006ce4f  jmp     loc_18006CB04
0x18006ce54  lea     r15, [rbx+10h]
0x18006ce58  mov     edi, r10d
0x18006ce5b  cmp     [r15], r10
0x18006ce5e  jz      loc_18006D70B
0x18006ce64  mov     [rsp+1E0h+var_180], r12
0x18006ce69  call    cs:__imp_GetProcessHeap
0x18006ce6f  mov     edx, 8; dwFlags
0x18006ce74  mov     r8d, 0A8h; dwBytes
0x18006ce7a  mov     rcx, rax; hHeap
0x18006ce7d  call    cs:__imp_HeapAlloc
0x18006ce83  mov     rsi, rax
0x18006ce86  test    rax, rax
0x18006ce89  jz      loc_18006D4C2
0x18006ce8f  mov     rcx, [rbx+18h]; this
0x18006ce93  mov     rdx, [r15]
0x18006ce96  mov     r8d, [rbx+28h]
0x18006ce9a  mov     dword ptr [rax+8], 0
0x18006cea1  lea     rax, ??_7CBitmapInfo@DirectComposition@@6B@; const DirectComposition::CBitmapInfo::`vftable'
0x18006cea8  mov     [rsi], rax
0x18006ceab  mov     [rsi+10h], rdx
0x18006ceaf  mov     [rsi+28h], r8d
0x18006ceb3  mov     qword ptr [rsi+2Ch], 0
0x18006cebb  mov     [rsi+18h], rcx
0x18006cebf  test    rcx, rcx
0x18006cec2  jz      short loc_18006CEC9
0x18006cec4  call    ?AddRef@CSurfaceFactory@DirectComposition@@UEAAKXZ; DirectComposition::CSurfaceFactory::AddRef(void)
0x18006cec9  mov     rcx, [rsi+10h]
0x18006cecd  test    rcx, rcx
0x18006ced0  jz      short loc_18006CEDB
0x18006ced2  add     rcx, 8; this
0x18006ced6  call    ?AddReference@CMILRefCountImpl@@IEAAKXZ; CMILRefCountImpl::AddReference(void)
0x18006cedb  mov     r8, [rbp+0E0h+var_F0]; struct DCOMPOSITION_GUTTERS *
0x18006cedf  lea     rax, ??_7CBitmapInfoBack@DirectComposition@@6B@; const DirectComposition::CBitmapInfoBack::`vftable'
0x18006cee6  mov     [rsi], rax
0x18006cee9  mov     rdx, r14; struct tagRECT *
0x18006ceec  mov     eax, 7FFFFFFFh
0x18006cef1  mov     rcx, rsi; this
0x18006cef4  mov     [rsi+80h], eax
0x18006cefa  mov     [rsi+78h], eax
0x18006cefd  mov     [rsi+70h], eax
0x18006cf00  mov     [rsi+68h], eax
0x18006cf03  mov     eax, 80000000h
0x18006cf08  mov     [rsi+84h], eax
0x18006cf0e  mov     [rsi+7Ch], eax
0x18006cf11  mov     [rsi+74h], eax
0x18006cf14  mov     [rsi+6Ch], eax
0x18006cf17  call    ?DirtyGuttersForUpdate@CBitmapInfoBack@DirectComposition@@QEAAXAEBUtagRECT@@PEAUDCOMPOSITION_GUTTERS@@@Z; DirectComposition::CBitmapInfoBack::DirtyGuttersForUpdate(tagRECT const &,DCOMPOSITION_GUTTERS *)
0x18006cf1c  lea     rcx, [rsi+8]; this
0x18006cf20  call    ?AddReference@CMILRefCountImpl@@IEAAKXZ; CMILRefCountImpl::AddReference(void)
0x18006cf25  mov     rbx, [rsp+1E0h+var_168]
0x18006cf2a  mov     [rbx], rsi
0x18006cf2d  jmp     loc_18006D115
0x18006cf32  mov     rax, rbx
0x18006cf35  mov     r8d, ebx
0x18006cf38  shr     rax, 20h
0x18006cf3c  mov     ecx, r10d
0x18006cf3f  mov     edx, r10d
0x18006cf42  jmp     loc_18006CB40
0x18006cf47  lea     rcx, [rdi+rdi*2]
0x18006cf4b  inc     edi
0x18006cf4d  mov     qword ptr [rbx+rcx*8+80h], 0
0x18006cf59  cmp     edi, esi
0x18006cf5b  jnz     short loc_18006CF47
0x18006cf5d  test    r12, r12
0x18006cf60  jnz     loc_18006D3E9
0x18006cf66  mov     r15, qword ptr [rbp+0E0h+var_118.left]
0x18006cf6a  lea     r12, [rbp+0E0h+var_118.right]
0x18006cf6e  xor     edi, edi
0x18006cf70  mov     [r15+60h], rdi
  ... truncated ...
```
