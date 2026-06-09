# CComposition::CleanTrees(void)

- ea: `0x1800d3400`
- end: `0x1800d4286`
- name: `?CleanTrees@CComposition@@IEAAJXZ`
- size: `3718`
- prototype: `__int64 __fastcall(CComposition *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18010e528`

## callees

- `0x180018230`
- `0x180042854`
- `0x180042de0`
- `0x1800d3400`
- `0x1800d428c`
- `0x1800d44f0`
- `0x1800d4668`
- `0x1800d4b14`
- `0x1800d4bc4`
- `0x1800d4f18`
- `0x1800d4fa0`
- `0x1800d5880`
- `0x1800f09a0`
- `0x1800f0f10`
- `0x180110480`
- `0x18014396c`
- `0x18014a3e0`
- `0x18014a42c`
- `0x18014a638`
- `0x1801883a8`
- `0x1801dba58`
- `0x1802005b0`
- `0x180204a98`
- `0x18021a948`
- `0x18021c6e4`
- `0x180228490`
- `0x180228860`
- `0x18022943c`
- `0x180231480`
- `0x180231678`
- `0x180238bac`
- `0x1802b6010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800d3558`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800d3558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d39c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d39c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d3457`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d3457`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d39a6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d39a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d3a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d3a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3a93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d3a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d39e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d39e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d40d0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d40e0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d40d0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800d40e0`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800d39f1`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800d39f1`

## string_xrefs

- `0x1800d3d23`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall CComposition::CleanTrees(struct _RTL_CRITICAL_SECTION *this, __int64 a2, __int64 a3)
{
  int v3; // r15d
  __int64 *v5; // rdx
  CComposition *v6; // r10
  const struct CVisualTree **v7; // rbx
  const struct CVisualTree **v8; // rcx
  __int64 *v9; // r14
  __int64 *v10; // rsi
  unsigned __int64 v11; // r13
  _QWORD *v12; // r9
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 *v18; // r15
  const struct CVisualTree **v19; // rbx
  const struct CVisualTree **v20; // rdi
  _BYTE *v21; // r12
  unsigned __int64 v22; // r14
  const struct CVisualTree *v23; // r13
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // r13d
  struct _RTL_CRITICAL_SECTION *v27; // r12
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  struct _RTL_CRITICAL_SECTION_DEBUG *v29; // rsi
  __int64 v30; // r12
  __int64 v31; // r14
  __int64 v32; // r9
  _DWORD *v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 *v36; // rdx
  __int64 v37; // rdx
  int v38; // r15d
  __int64 v39; // rcx
  __int64 v40; // rax
  char v41; // cl
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  bool v48; // zf
  __int64 v49; // rax
  struct _RTL_CRITICAL_SECTION *v50; // r12
  ULONG_PTR *p_SpinCount; // rbx
  _QWORD *v52; // rax
  _QWORD *v53; // r8
  _QWORD *k; // rcx
  _QWORD *v55; // r9
  char *v56; // rdx
  PRTL_CRITICAL_SECTION_DEBUG v57; // rcx
  const char *v58; // r9
  unsigned __int64 v59; // rcx
  HANDLE CurrentThread; // rax
  BOOL v61; // eax
  HANDLE ProcessHeap; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  char v66; // cl
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  int v74; // r14d
  __int64 v75; // rax
  CPreComputeContext *v76; // rbx
  CPreComputeContext *v77; // rax
  int v78; // eax
  __int64 v79; // rax
  CPreComputeContext *v80; // rbx
  CPreComputeContext *v81; // rax
  int v82; // eax
  __int64 v83; // rcx
  unsigned int v84; // r8d
  unsigned int i; // edx
  _BYTE *v86; // rax
  CPreComputeContext *v87; // rax
  CPreComputeContext *v88; // rbx
  __int64 v89; // rax
  unsigned int v90; // r8d
  unsigned int j; // edx
  CPreComputeContext *v92; // rax
  CPreComputeContext *v93; // rbx
  __int64 v94; // rcx
  CLight **v95; // rdi
  CLight **v96; // rbx
  __int64 v97; // r10
  _QWORD *n; // rax
  __int64 ProjectedShadowCasters; // rax
  CProjectedShadowCaster **v100; // r14
  CProjectedShadowCaster **v101; // r15
  const struct D2D_RECT_F *UnoptimizedBounds; // rax
  const struct D2D_RECT_F *v103; // rax
  _QWORD *m; // rdx
  unsigned int v105; // edi
  __int64 v106; // rcx
  __int64 v107; // rax
  unsigned int ii; // esi
  _OWORD *v109; // rax
  __int64 v110; // rbx
  int v111; // [rsp+20h] [rbp-E0h]
  unsigned __int64 CycleTime; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v113; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION *v114; // [rsp+50h] [rbp-B0h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER v116; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v117[3]; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v118; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v119[7]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v120; // [rsp+C8h] [rbp-38h]
  const struct CVisualTree **v121; // [rsp+D0h] [rbp-30h] BYREF
  const struct CVisualTree **v122; // [rsp+D8h] [rbp-28h]
  _QWORD *v123; // [rsp+E0h] [rbp-20h]
  _BYTE Mem[64]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v125[3]; // [rsp+128h] [rbp+28h] BYREF
  _OWORD v126[8]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v3 = 0;
  v114 = this;
  PerformanceCount.QuadPart = 0;
  v116.QuadPart = 0;
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 4) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Dwm_Compositor_Context, &CleanTrees_Start, a3, 1, v125);
    QueryPerformanceCounter(&PerformanceCount);
  }
  EnterCriticalSection(this + 9);
  if ( PerformanceCount.QuadPart )
    QueryPerformanceCounter(&v116);
  v6 = g_pComposition;
  v7 = (const struct CVisualTree **)Mem;
  v8 = (const struct CVisualTree **)Mem;
  v121 = (const struct CVisualTree **)Mem;
  v122 = (const struct CVisualTree **)Mem;
  v123 = v125;
  v9 = (__int64 *)*((_QWORD *)g_pComposition + 775);
  v118 = v9;
  v10 = (__int64 *)*v9;
LABEL_6:
  if ( v10 != v9 )
  {
    v11 = v10[2];
    v12 = v119;
    v119[0] = off_1802BABF0;
    v13 = v11;
    CycleTime = v11;
    v119[1] = &v121;
    v14 = v11;
    v120 = v119;
    while ( 1 )
    {
      if ( !v13 )
      {
LABEL_23:
        if ( v12 )
        {
          LOBYTE(v5) = v12 != v119;
          (*(void (__fastcall **)(_QWORD *, __int64 *))(*v12 + 32LL))(v12, v5);
          v120 = 0;
        }
        *((_BYTE *)v10 + 51) = 0;
        v113 = 0;
        v18 = v10 + 3;
        if ( g_pComposition )
          v113 = *((_QWORD *)g_pComposition + 110);
        v19 = v121;
        v20 = v122;
        v21 = (char *)v10 + 50;
        v22 = v113;
        v125[0] = (char *)v10 + 50;
        while ( v19 != v20 )
        {
          v23 = *v19;
          CPreWalkVisual::CalcTransform((CPreWalkVisual *)v18, (struct CVisual *)CycleTime, *v19, v22);
          if ( *((_BYTE *)v18 + 24) )
            CPreWalkVisual::DirtyBoundsForTransformParentChild((struct CVisual *)CycleTime, v23);
          v21 = (char *)v18 + 26;
          if ( *((_BYTE *)v18 + 26) )
          {
            ProjectedShadowCasters = CVisual::GetProjectedShadowCasters(CycleTime);
            v5 = *(__int64 **)(ProjectedShadowCasters + 8);
            if ( *(__int64 **)ProjectedShadowCasters != v5 )
            {
              v100 = *(CProjectedShadowCaster ***)ProjectedShadowCasters;
              v101 = *(CProjectedShadowCaster ***)(ProjectedShadowCasters + 8);
              do
                CProjectedShadowCaster::UpdateVisualProperty(*v100++, v23);
              while ( v100 != v101 );
              v22 = v113;
              v18 = v10 + 3;
            }
          }
          ++v19;
        }
        v9 = v118;
        if ( *((_BYTE *)v18 + 27) )
        {
          if ( *((_BYTE *)v18 + 25) )
          {
            v95 = (CLight **)v18[1];
            v96 = (CLight **)*v18;
            if ( (CLight **)*v18 == v95 )
            {
              v86 = (_BYTE *)v125[0];
            }
            else
            {
              do
                CLight::IssueLightChangedNotification(*v96++);
              while ( v96 != v95 );
              v86 = (char *)v18 + 26;
            }
          }
          else
          {
            v86 = v21;
          }
          if ( *v86 )
            CVisual::DirtyProjectedShadowCasters((CVisual *)CycleTime);
        }
        v8 = v122;
        v7 = v121;
        v24 = v122 - v121;
        if ( v24 )
        {
          v8 = &v122[-v24];
          v122 = v8;
        }
        v10 = (__int64 *)*v10;
        v3 = 0;
        v6 = g_pComposition;
        goto LABEL_6;
      }
      v15 = *(_DWORD **)(v13 + 224);
      if ( (*v15 & 0x8000000) != 0 )
        break;
LABEL_16:
      if ( v14 )
      {
        v14 = *(_QWORD *)(v14 + 88);
        if ( v14 )
        {
          if ( v13 == v14 )
            goto LABEL_23;
          v14 = *(_QWORD *)(v14 + 88);
          if ( v13 == v14 )
            goto LABEL_23;
        }
      }
      v13 = *(_QWORD *)(v13 + 88);
    }
    v16 = (unsigned int)v15[1];
    v17 = 0;
    if ( (_DWORD)v16 )
    {
      while ( *((_BYTE *)v15 + v17 + 8) != 5 )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= (unsigned int)v16 )
          goto LABEL_21;
      }
    }
    else
    {
LABEL_21:
      if ( (unsigned int)v17 >= (unsigned int)v16 )
      {
        v5 = 0;
LABEL_13:
        if ( *v5 )
        {
          v117[0] = *v5;
          if ( !v12 )
          {
            std::_Xbad_function_call();
            __debugbreak();
          }
          (*(void (__fastcall **)(_QWORD *, __int64 *))(*v12 + 16LL))(v12, v117);
          v12 = v120;
        }
        goto LABEL_16;
      }
    }
    v5 = (__int64 *)((char *)v15 + v16 + 8 * v17 - (((_BYTE)v16 + 15) & 7) + 15);
    goto LABEL_13;
  }
  LODWORD(v113) = 0;
  v25 = v8 - v7;
  v26 = 0;
  if ( v25 )
    v122 = &v8[-v25];
  v121 = 0;
  if ( v7 != (const struct CVisualTree **)Mem && v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    v6 = g_pComposition;
  }
  v27 = v114;
  LOBYTE(v114[141].OwningThread) = 1;
  DebugInfo = v27[10].DebugInfo;
  v29 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&v27[10].LockCount;
  while ( DebugInfo != v29 )
  {
    v30 = *(_QWORD *)&DebugInfo->Type;
    v31 = *(_QWORD *)&DebugInfo->Type;
    v32 = *(_QWORD *)(*(_QWORD *)&DebugInfo->Type + 72LL);
    if ( v32 )
    {
      while ( 1 )
      {
        v33 = *(_DWORD **)(v32 + 224);
        if ( (*v33 & 0x8000000) != 0 )
          break;
LABEL_54:
        v32 = *(_QWORD *)(v32 + 88);
        if ( !v32 )
          goto LABEL_55;
      }
      v34 = (unsigned int)v33[1];
      v35 = 0;
      if ( (_DWORD)v34 )
      {
        while ( *((_BYTE *)v33 + v35 + 8) != 5 )
        {
          v35 = (unsigned int)(v35 + 1);
          if ( (unsigned int)v35 >= (unsigned int)v34 )
            goto LABEL_101;
        }
LABEL_51:
        v36 = (__int64 *)((char *)v33 + v34 + 8 * v35 - (((_BYTE)v34 + 15) & 7) + 15);
      }
      else
      {
LABEL_101:
        if ( (unsigned int)v35 < (unsigned int)v34 )
          goto LABEL_51;
        v36 = 0;
      }
      if ( *v36 )
        v31 = *v36;
      goto LABEL_54;
    }
LABEL_55:
    v37 = *(_QWORD *)(v31 + 72);
    if ( v37 && *(_BYTE *)(v37 + 96) )
      LODWORD(v113) = v3 + 1;
    v38 = 0;
    v39 = 0;
    if ( v6 )
      v39 = *((_QWORD *)v6 + 110);
    if ( *(_QWORD *)(v31 + 120) != v39 && v37 && *(_BYTE *)(v37 + 96) )
    {
      v76 = 0;
      v77 = *(CPreComputeContext **)&v114[15].LockCount;
      if ( !v77 )
      {
        v87 = (CPreComputeContext *)operator new(0x640u);
        v88 = v87;
        if ( v87 )
        {
          memset_0(v87, 0, 0x640u);
          v77 = CPreComputeContext::CPreComputeContext(v88);
        }
        else
        {
          v77 = 0;
        }
        v76 = v77;
      }
      v78 = CPreComputeContext::PreCompute(v77, (struct CVisualTree *)v31);
      v38 = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18B,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\visualtree.cpp",
          (const char *)(unsigned int)v78,
          v111);
        if ( v76 )
        {
          CPreComputeContext::~CPreComputeContext(v76);
          operator delete(v76, 0x640u);
        }
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v38, 0xBF3u, 0);
        v6 = g_pComposition;
        goto LABEL_81;
      }
      if ( v76 )
      {
        CPreComputeContext::~CPreComputeContext(v76);
        operator delete(v76, 0x640u);
      }
      v6 = g_pComposition;
      v38 = 0;
    }
    v40 = 0;
    if ( v6 )
      v40 = *((_QWORD *)v6 + 110);
    if ( *(_QWORD *)(v31 + 120) == v40 )
      goto LABEL_81;
    if ( *(_BYTE *)(v31 + 2628) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 232LL))(v31);
      *(_BYTE *)(v31 + 2628) = 0;
    }
    v41 = *(_BYTE *)(v31 + 2630);
    *(_QWORD *)(v31 + 120) = 0;
    *(_BYTE *)(v31 + 2437) = 0;
    *(_WORD *)(v31 + 2439) = 0;
    *(_BYTE *)(v31 + 2436) = v41 == 0;
    *(_OWORD *)(v31 + 2420) = *(_OWORD *)(*(_QWORD *)(v31 + 112) + 2504LL);
    if ( v41 )
    {
      if ( *(_BYTE *)(v31 + 2438) )
        *(_BYTE *)(v31 + 2438) = 0;
      *(_DWORD *)(v31 + 128) = 0;
      *(_BYTE *)(v31 + 564) = 0;
      if ( !*(_BYTE *)(v31 + 2438) )
        CTreeDirty::ClearDirtyRectAnnotationLists((CTreeDirty *)(v31 + 112));
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v31 + 192LL))(v31) )
    {
      v42 = (__int64)(*(_QWORD *)(v31 + 4776) - *(_QWORD *)(v31 + 4768)) >> 3;
      if ( v42 )
        *(_QWORD *)(v31 + 4776) += -8 * v42;
    }
    v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 224LL))(v31);
    v45 = v43;
    if ( v43 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 24LL))(v43, v31);
    v46 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v31 + 224LL))(v31, v44, v45);
    v47 = v46;
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 32LL))(v46);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 192LL))(v31, v47) )
    {
      v75 = *(_QWORD *)(v31 + 24);
      if ( !*(_DWORD *)(v75 + 6368) )
        goto LABEL_139;
      if ( *(_BYTE *)(v75 + 6461) )
      {
LABEL_229:
        *(_BYTE *)(v31 + 2439) = 1;
        *(_BYTE *)(v75 + 6461) = 0;
      }
      else
      {
        UnoptimizedBounds = (const struct D2D_RECT_F *)CTreeDirty::GetUnoptimizedBounds(v31 + 112, v125);
        if ( !IsEmpty(UnoptimizedBounds) )
        {
          v75 = *(_QWORD *)(v31 + 24);
          goto LABEL_229;
        }
      }
LABEL_139:
      if ( *(_DWORD *)(*(_QWORD *)(v31 + 24) + 6376LL) )
        *(_BYTE *)(v31 + 2440) = 1;
    }
    if ( !*(_BYTE *)(v31 + 2436) )
    {
      while ( 1 )
      {
        CRectangleCollection<8>::EnsureWeights(v31 + 128);
        v84 = 1;
LABEL_156:
        if ( v84 >= *(_DWORD *)(v31 + 128) )
          break;
        for ( i = 0; ; ++i )
        {
          if ( i >= v84 )
          {
            ++v84;
            goto LABEL_156;
          }
          if ( *(float *)(v31 + 8LL * (i + ((v84 * (v84 - 1)) >> 1)) + 280) < 0.5 )
            break;
        }
        CTreeDirty::Merge((CTreeDirty *)(v31 + 112), i, v84);
      }
      v38 = 0;
    }
    v48 = *(_BYTE *)(v31 + 2439) == 0;
    *(_BYTE *)(v31 + 2437) = 1;
    if ( v48 )
    {
      if ( *(_BYTE *)(v31 + 2440) )
      {
        CTreeDirty::SetFullDirty((CTreeDirty *)(v31 + 112));
        *(_BYTE *)(v31 + 2440) = 0;
      }
    }
    else
    {
      CTreeDirty::SetRedrawRects((CTreeDirty *)(v31 + 112));
      CTreeDirty::SetFullDirty((CTreeDirty *)(v31 + 112));
      *(_WORD *)(v31 + 2439) = 0;
    }
    v6 = g_pComposition;
    v49 = 0;
    if ( g_pComposition )
      v49 = *((_QWORD *)g_pComposition + 110);
    *(_QWORD *)(v31 + 120) = v49;
LABEL_81:
    if ( !v26 || v26 >= 0 && v38 < 0 )
      v26 = v38;
    if ( v31 != v30 )
    {
      v64 = 0;
      if ( v6 )
        v64 = *((_QWORD *)v6 + 110);
      if ( *(_QWORD *)(v30 + 120) != v64 )
      {
        v79 = *(_QWORD *)(v30 + 72);
        if ( v79 )
        {
          if ( *(_BYTE *)(v79 + 96) )
          {
            v80 = 0;
            v81 = *(CPreComputeContext **)&v114[15].LockCount;
            if ( !v81 )
            {
              v92 = (CPreComputeContext *)operator new(0x640u);
              v93 = v92;
              if ( v92 )
              {
                memset_0(v92, 0, 0x640u);
                v81 = CPreComputeContext::CPreComputeContext(v93);
              }
              else
              {
                v81 = 0;
              }
              v80 = v81;
            }
            v82 = CPreComputeContext::PreCompute(v81, (struct CVisualTree *)v30);
            v74 = v82;
            if ( v82 >= 0 )
            {
              if ( v80 )
                std::default_delete<CPreComputeContext>::operator()(v83, v80);
              v6 = g_pComposition;
              goto LABEL_112;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x18B,
              (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\visualtree.cpp",
              (const char *)(unsigned int)v82,
              v111);
            if ( v80 )
              std::default_delete<CPreComputeContext>::operator()(v94, v80);
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v74, 0xBFBu, 0);
            v6 = g_pComposition;
LABEL_134:
            if ( !v26 || v26 >= 0 && v74 < 0 )
              v26 = v74;
            goto LABEL_84;
          }
        }
      }
LABEL_112:
      v65 = 0;
      if ( v6 )
        v65 = *((_QWORD *)v6 + 110);
      if ( *(_QWORD *)(v30 + 120) == v65 )
      {
LABEL_133:
        v74 = 0;
        goto LABEL_134;
      }
      if ( *(_BYTE *)(v30 + 2628) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 232LL))(v30);
        *(_BYTE *)(v30 + 2628) = 0;
      }
      v66 = *(_BYTE *)(v30 + 2630);
      *(_QWORD *)(v30 + 120) = 0;
      *(_BYTE *)(v30 + 2437) = 0;
      *(_WORD *)(v30 + 2439) = 0;
      *(_BYTE *)(v30 + 2436) = v66 == 0;
      *(_OWORD *)(v30 + 2420) = *(_OWORD *)(*(_QWORD *)(v30 + 112) + 2504LL);
      if ( v66 )
      {
        if ( *(_BYTE *)(v30 + 2438) )
          *(_BYTE *)(v30 + 2438) = 0;
        *(_DWORD *)(v30 + 128) = 0;
        *(_BYTE *)(v30 + 564) = 0;
        if ( !*(_BYTE *)(v30 + 2438) )
          CTreeDirty::ClearDirtyRectAnnotationLists((CTreeDirty *)(v30 + 112));
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v30 + 192LL))(v30) )
      {
        v67 = (__int64)(*(_QWORD *)(v30 + 4776) - *(_QWORD *)(v30 + 4768)) >> 3;
        if ( v67 )
          *(_QWORD *)(v30 + 4776) += -8 * v67;
      }
      v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 224LL))(v30);
      v70 = v68;
      if ( v68 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 24LL))(v68, v30);
      v71 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v30 + 224LL))(v30, v69, v70);
      v72 = v71;
      if ( v71 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 32LL))(v71);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 192LL))(v30, v72) )
      {
LABEL_126:
        if ( !*(_BYTE *)(v30 + 2436) )
        {
          while ( 1 )
          {
            CRectangleCollection<8>::EnsureWeights(v30 + 128);
            v90 = 1;
LABEL_182:
            if ( v90 >= *(_DWORD *)(v30 + 128) )
              break;
            for ( j = 0; ; ++j )
            {
              if ( j >= v90 )
              {
                ++v90;
                goto LABEL_182;
              }
              if ( *(float *)(v30 + 8LL * (j + ((v90 * (v90 - 1)) >> 1)) + 280) < 0.5 )
                break;
            }
            CTreeDirty::Merge((CTreeDirty *)(v30 + 112), j, v90);
          }
        }
        *(_BYTE *)(v30 + 2437) = 1;
        if ( *(_BYTE *)(v30 + 2439) )
        {
          CTreeDirty::SetRedrawRects((CTreeDirty *)(v30 + 112));
          CTreeDirty::SetFullDirty((CTreeDirty *)(v30 + 112));
          *(_WORD *)(v30 + 2439) = 0;
        }
        else if ( *(_BYTE *)(v30 + 2440) )
        {
          CTreeDirty::SetFullDirty((CTreeDirty *)(v30 + 112));
          *(_BYTE *)(v30 + 2440) = 0;
        }
        v6 = g_pComposition;
        v73 = 0;
        if ( g_pComposition )
          v73 = *((_QWORD *)g_pComposition + 110);
        *(_QWORD *)(v30 + 120) = v73;
        goto LABEL_133;
      }
      v89 = *(_QWORD *)(v30 + 24);
      if ( *(_DWORD *)(v89 + 6368) )
      {
        if ( !*(_BYTE *)(v89 + 6461) )
        {
          v103 = (const struct D2D_RECT_F *)CTreeDirty::GetUnoptimizedBounds(v30 + 112, &v118);
          if ( IsEmpty(v103) )
            goto LABEL_179;
          v89 = *(_QWORD *)(v30 + 24);
        }
        *(_BYTE *)(v30 + 2439) = 1;
        *(_BYTE *)(v89 + 6461) = 0;
      }
LABEL_179:
      if ( *(_DWORD *)(*(_QWORD *)(v30 + 24) + 6376LL) )
        *(_BYTE *)(v30 + 2440) = 1;
      goto LABEL_126;
    }
LABEL_84:
    v3 = v113;
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)DebugInfo + 8);
  }
  v50 = v114;
  p_SpinCount = &v114[13].SpinCount;
  LOBYTE(v114[141].OwningThread) = 0;
  v52 = (_QWORD *)p_SpinCount[1];
  if ( v52 != (_QWORD *)*p_SpinCount )
  {
    v53 = *(_QWORD **)&v50[10].LockCount;
    for ( k = &v50[10].DebugInfo->Type; ; ++k )
    {
      v55 = v52;
      if ( k == v53 )
        break;
      for ( m = (_QWORD *)*p_SpinCount; m != v52 && *m != *k; ++m )
        ;
      v52 = (_QWORD *)p_SpinCount[1];
      v55 = v52;
      if ( m != v52 )
        break;
    }
    v56 = (char *)k;
    if ( k != v53 )
    {
      while ( ++k != v53 )
      {
        v97 = *k;
        for ( n = (_QWORD *)*p_SpinCount; n != v55 && *n != v97; ++n )
          ;
        v55 = (_QWORD *)p_SpinCount[1];
        if ( n == v55 )
        {
          *(_QWORD *)v56 = v97;
          v56 += 8;
          v55 = (_QWORD *)p_SpinCount[1];
        }
      }
    }
    detail::vector_facade<CVisualTree *,detail::buffer_impl<CVisualTree *,16,1,detail::liberal_expansion_policy>>::clear_region(
      &v50[10],
      (v56 - (char *)v50[10].DebugInfo) >> 3,
      (__int64)(*(_QWORD *)&v50[10].LockCount - (_QWORD)v56) >> 3,
      v55);
    if ( (__int64)(p_SpinCount[1] - *p_SpinCount) >> 3 )
      detail::vector_facade<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<CVisualTree,wil::err_returncode_policy>,4,1,detail::liberal_expansion_policy>>::clear_region(p_SpinCount);
  }
  if ( LOBYTE(v50[160].LockCount) )
  {
    v57 = v50[160].DebugInfo;
    LOBYTE(v50[160].LockCount) = 0;
    if ( !SetEvent(v57) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v58);
  }
  if ( v50 != (struct _RTL_CRITICAL_SECTION *)-360LL )
    LeaveCriticalSection(v50 + 9);
  if ( PerformanceCount.QuadPart )
  {
    v105 = 0;
    memset_0(v126, 0, sizeof(v126));
    v106 = *(_QWORD *)v50[15].OwningThread;
    if ( v106 )
    {
      v107 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 56LL))(v106);
      if ( v107 )
      {
        CTreeDirty::GetDirtyRects(v107 + 112, v125);
        v105 = v125[0];
        for ( ii = 0; ii < v105; v126[v110] = *v109 )
        {
          v109 = (_OWORD *)gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1>::operator[](
                             v125,
                             ii);
          v110 = ii++;
        }
      }
    }
    if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 4) != 0 )
      McTemplateU0qqxqNR3_EventWriteTransfer(
        (unsigned int)v126,
        (unsigned __int64)(1000000 * (v116.QuadPart - PerformanceCount.QuadPart)) % g_qpcFrequency.QuadPart,
        v26,
        v3,
        (unsigned __int64)(1000000 * (v116.QuadPart - PerformanceCount.QuadPart)) / g_qpcFrequency.QuadPart,
        v105);
  }
  v59 = 0;
  CycleTime = 0;
  if ( ::CycleTime )
  {
    CurrentThread = GetCurrentThread();
    v61 = QueryThreadCycleTime(CurrentThread, &CycleTime);
    v59 = CycleTime;
    if ( v61 )
      qword_1803BADC8 += CycleTime - ::CycleTime;
  }
  ::CycleTime = v59;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1800d3400  push    rbp
0x1800d3402  push    rbx
0x1800d3403  push    rsi
0x1800d3404  push    rdi
0x1800d3405  push    r12
0x1800d3407  push    r13
0x1800d3409  push    r14
0x1800d340b  push    r15
0x1800d340d  lea     rbp, [rsp-0E8h]
0x1800d3415  sub     rsp, 1E8h
0x1800d341c  mov     rax, cs:__security_cookie
0x1800d3423  xor     rax, rsp
0x1800d3426  mov     [rbp+120h+var_60], rax
0x1800d342d  xor     r15d, r15d
0x1800d3430  mov     [rsp+220h+var_1D0], rcx
0x1800d3435  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 4
0x1800d343c  mov     r12, rcx
0x1800d343f  mov     qword ptr [rsp+220h+PerformanceCount], r15
0x1800d3444  mov     qword ptr [rsp+220h+var_1C0], r15
0x1800d3449  jnz     loc_1800D40A9
0x1800d344f  lea     rcx, [r12+168h]; lpCriticalSection
0x1800d3457  call    cs:__imp_EnterCriticalSection
0x1800d345d  cmp     qword ptr [rsp+220h+PerformanceCount], r15
0x1800d3462  jnz     loc_1800D40DB
0x1800d3468  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d346f  lea     rbx, [rbp+120h+Mem]
0x1800d3473  lea     rcx, [rbp+120h+Mem]
0x1800d3477  mov     [rbp+120h+var_150], rbx
0x1800d347b  lea     rax, [rbp+120h+var_F8]
0x1800d347f  mov     [rbp+120h+var_148], rcx
0x1800d3483  mov     [rbp+120h+var_140], rax
0x1800d3487  mov     r14, [r10+1838h]
0x1800d348e  mov     [rbp+120h+var_1A0], r14
0x1800d3492  mov     rsi, [r14]
0x1800d3495  lea     rax, off_1802BABF0
0x1800d349c  cmp     rsi, r14
0x1800d349f  jz      loc_1800D3675
0x1800d34a5  mov     r13, [rsi+10h]
0x1800d34a9  lea     r9, [rbp+120h+var_190]
0x1800d34ad  mov     [rbp+120h+var_190], rax
0x1800d34b1  mov     rdi, r13
0x1800d34b4  lea     rax, [rbp+120h+var_150]
0x1800d34b8  mov     [rsp+220h+CycleTime], r13
0x1800d34bd  mov     [rbp+120h+var_188], rax
0x1800d34c1  mov     rbx, r13
0x1800d34c4  mov     [rbp+120h+var_158], r9
0x1800d34c8  nop     dword ptr [rax+rax+00000000h]
0x1800d34d0  test    rdi, rdi
0x1800d34d3  jz      loc_1800D356E
0x1800d34d9  mov     r8, [rdi+0E0h]
0x1800d34e0  test    dword ptr [r8], 8000000h
0x1800d34e7  jz      short loc_1800D353D
0x1800d34e9  mov     ecx, [r8+4]
0x1800d34ed  mov     edx, r15d
0x1800d34f0  test    ecx, ecx
0x1800d34f2  jz      short loc_1800D3565
0x1800d34f4  cmp     byte ptr [rdx+r8+8], 5
0x1800d34fa  jnz     short loc_1800D355F
0x1800d34fc  add     rcx, 0Fh
0x1800d3500  shl     rdx, 3
0x1800d3504  mov     rax, rcx
0x1800d3507  and     eax, 7
0x1800d350a  sub     rdx, rax
0x1800d350d  add     rdx, rcx
0x1800d3510  add     rdx, r8
0x1800d3513  mov     rax, [rdx]
0x1800d3516  test    rax, rax
0x1800d3519  jz      short loc_1800D353D
0x1800d351b  mov     [rsp+220h+var_1B8], rax
0x1800d3520  test    r9, r9
0x1800d3523  jz      short loc_1800D3558
0x1800d3525  mov     rax, [r9]
0x1800d3528  lea     rdx, [rsp+220h+var_1B8]
0x1800d352d  mov     rcx, r9
0x1800d3530  mov     rax, [rax+10h]
0x1800d3534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3539  mov     r9, [rbp+120h+var_158]
0x1800d353d  test    rbx, rbx
0x1800d3540  jz      short loc_1800D354F
0x1800d3542  mov     rbx, [rbx+58h]
0x1800d3546  test    rbx, rbx
0x1800d3549  jnz     loc_1800D364D
0x1800d354f  mov     rdi, [rdi+58h]
0x1800d3553  jmp     loc_1800D34D0
0x1800d3558  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800d355e  int     3; Trap to Debugger
0x1800d355f  inc     edx
0x1800d3561  cmp     edx, ecx
0x1800d3563  jb      short loc_1800D34F4
0x1800d3565  cmp     edx, ecx
0x1800d3567  jb      short loc_1800D34FC
0x1800d3569  mov     rdx, r15
0x1800d356c  jmp     short loc_1800D3513
0x1800d356e  test    r9, r9
0x1800d3571  jz      short loc_1800D3590
0x1800d3573  mov     rax, [r9]
0x1800d3576  lea     rcx, [rbp+120h+var_190]
0x1800d357a  cmp     r9, rcx
0x1800d357d  mov     rcx, r9
0x1800d3580  setnz   dl
0x1800d3583  mov     rax, [rax+20h]
0x1800d3587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d358c  mov     [rbp+120h+var_158], r15
0x1800d3590  xor     eax, eax
0x1800d3592  mov     byte ptr [rsi+33h], 0
0x1800d3596  mov     [rsp+220h+var_1D8], rax
0x1800d359b  lea     r15, [rsi+18h]
0x1800d359f  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d35a6  test    rax, rax
0x1800d35a9  jz      short loc_1800D35B7
0x1800d35ab  mov     rax, [rax+370h]
0x1800d35b2  mov     [rsp+220h+var_1D8], rax
0x1800d35b7  mov     rbx, [rbp+120h+var_150]
0x1800d35bb  lea     rax, [r15+1Ah]
0x1800d35bf  mov     rdi, [rbp+120h+var_148]
0x1800d35c3  mov     r12, rax
0x1800d35c6  mov     r14, [rsp+220h+var_1D8]
0x1800d35cb  mov     [rbp+120h+var_F8], rax
0x1800d35cf  nop
0x1800d35d0  cmp     rbx, rdi
0x1800d35d3  jz      short loc_1800D360A
0x1800d35d5  mov     r13, [rbx]
0x1800d35d8  mov     r9, r14; unsigned __int64
0x1800d35db  mov     r12, [rsp+220h+CycleTime]
0x1800d35e0  mov     r8, r13; struct CVisualTree *
0x1800d35e3  mov     rdx, r12; struct CVisual *
0x1800d35e6  mov     rcx, r15; this
0x1800d35e9  call    ?CalcTransform@CPreWalkVisual@@AEAAXPEAVCVisual@@PEBVCVisualTree@@_K@Z; CPreWalkVisual::CalcTransform(CVisual *,CVisualTree const *,unsigned __int64)
0x1800d35ee  cmp     byte ptr [r15+18h], 0
0x1800d35f3  jnz     short loc_1800D3668
0x1800d35f5  cmp     byte ptr [r15+1Ah], 0
0x1800d35fa  lea     r12, [r15+1Ah]
0x1800d35fe  jnz     loc_1800D40EB
0x1800d3604  add     rbx, 8
0x1800d3608  jmp     short loc_1800D35D0
0x1800d360a  cmp     byte ptr [r15+1Bh], 0
0x1800d360f  mov     r14, [rbp+120h+var_1A0]
0x1800d3613  jnz     loc_1800D3DE8
0x1800d3619  mov     rcx, [rbp+120h+var_148]
0x1800d361d  mov     rbx, [rbp+120h+var_150]
0x1800d3621  mov     rax, rcx
0x1800d3624  sub     rax, rbx
0x1800d3627  sar     rax, 3
0x1800d362b  test    rax, rax
0x1800d362e  jz      short loc_1800D363B
0x1800d3630  neg     rax
0x1800d3633  lea     rcx, [rcx+rax*8]
0x1800d3637  mov     [rbp+120h+var_148], rcx
0x1800d363b  mov     rsi, [rsi]
0x1800d363e  xor     r15d, r15d
0x1800d3641  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d3648  jmp     loc_1800D3495
0x1800d364d  cmp     rdi, rbx
0x1800d3650  jz      loc_1800D356E
0x1800d3656  mov     rbx, [rbx+58h]
0x1800d365a  cmp     rdi, rbx
0x1800d365d  jnz     loc_1800D354F
0x1800d3663  jmp     loc_1800D356E
0x1800d3668  mov     rdx, r13; struct CVisualTree *
0x1800d366b  mov     rcx, r12; struct CVisual *
0x1800d366e  call    ?DirtyBoundsForTransformParentChild@CPreWalkVisual@@CAXPEAVCVisual@@PEBVCVisualTree@@@Z; CPreWalkVisual::DirtyBoundsForTransformParentChild(CVisual *,CVisualTree const *)
0x1800d3673  jmp     short loc_1800D35F5
0x1800d3675  mov     rax, rcx
0x1800d3678  movaps  [rsp+220h+var_50], xmm6
0x1800d3680  sub     rax, rbx
0x1800d3683  mov     dword ptr [rsp+220h+var_1D8], r15d
0x1800d3688  sar     rax, 3
0x1800d368c  mov     r13d, r15d
0x1800d368f  test    rax, rax
0x1800d3692  jz      short loc_1800D369F
0x1800d3694  neg     rax
0x1800d3697  lea     rax, [rcx+rax*8]
0x1800d369b  mov     [rbp+120h+var_148], rax
0x1800d369f  lea     rax, [rbp+120h+Mem]
0x1800d36a3  mov     [rbp+120h+var_150], 0
0x1800d36ab  cmp     rbx, rax
0x1800d36ae  jz      short loc_1800D36B9
0x1800d36b0  test    rbx, rbx
0x1800d36b3  jnz     loc_1800D3A85
0x1800d36b9  mov     r12, [rsp+220h+var_1D0]
0x1800d36be  movss   xmm6, cs:__real@3f000000
0x1800d36c6  mov     byte ptr [r12+1618h], 1
0x1800d36cf  mov     rdi, [r12+190h]
0x1800d36d7  mov     rsi, [r12+198h]
0x1800d36df  nop
0x1800d36e0  cmp     rdi, rsi
0x1800d36e3  jz      loc_1800D38FD
0x1800d36e9  mov     r12, [rdi]
0x1800d36ec  mov     r14, r12
0x1800d36ef  mov     r9, [r12+48h]
0x1800d36f4  test    r9, r9
0x1800d36f7  jz      short loc_1800D374D
0x1800d36f9  mov     r8, [r9+0E0h]
0x1800d3700  test    dword ptr [r8], 8000000h
0x1800d3707  jz      short loc_1800D3744
0x1800d3709  mov     ecx, [r8+4]
0x1800d370d  xor     edx, edx
0x1800d370f  test    ecx, ecx
0x1800d3711  jz      loc_1800D3A48
0x1800d3717  cmp     byte ptr [rdx+r8+8], 5
0x1800d371d  jnz     loc_1800D3A3E
0x1800d3723  add     rcx, 0Fh
0x1800d3727  shl     rdx, 3
0x1800d372b  mov     rax, rcx
0x1800d372e  and     eax, 7
0x1800d3731  sub     rdx, rax
0x1800d3734  add     rdx, rcx
0x1800d3737  add     rdx, r8
0x1800d373a  mov     rax, [rdx]
0x1800d373d  test    rax, rax
0x1800d3740  cmovnz  r14, rax
0x1800d3744  mov     r9, [r9+58h]
0x1800d3748  test    r9, r9
0x1800d374b  jnz     short loc_1800D36F9
0x1800d374d  mov     rdx, [r14+48h]
0x1800d3751  test    rdx, rdx
0x1800d3754  jnz     loc_1800D3A6E
0x1800d375a  xor     r15d, r15d
0x1800d375d  mov     ecx, r15d
0x1800d3760  test    r10, r10
0x1800d3763  jz      short loc_1800D376C
0x1800d3765  mov     rcx, [r10+370h]
0x1800d376c  cmp     [r14+78h], rcx
0x1800d3770  jz      short loc_1800D377B
0x1800d3772  test    rdx, rdx
0x1800d3775  jnz     loc_1800D3CBB
0x1800d377b  mov     rax, r15
0x1800d377e  test    r10, r10
0x1800d3781  jz      short loc_1800D378A
0x1800d3783  mov     rax, [r10+370h]
0x1800d378a  cmp     [r14+78h], rax
0x1800d378e  jz      loc_1800D38DA
0x1800d3794  cmp     byte ptr [r14+0A44h], 0
0x1800d379c  jz      short loc_1800D37B8
0x1800d379e  mov     rax, [r14]
0x1800d37a1  mov     rcx, r14
0x1800d37a4  mov     rax, [rax+0E8h]
0x1800d37ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d37b0  mov     byte ptr [r14+0A44h], 0
0x1800d37b8  movzx   ecx, byte ptr [r14+0A46h]
0x1800d37c0  test    cl, cl
0x1800d37c2  mov     [r14+78h], r15
0x1800d37c6  mov     byte ptr [r14+985h], 0
0x1800d37ce  setz    al
0x1800d37d1  mov     word ptr [r14+987h], 0
0x1800d37db  mov     [r14+984h], al
0x1800d37e2  mov     rax, [r14+70h]
0x1800d37e6  movups  xmm0, xmmword ptr [rax+9C8h]
0x1800d37ed  movups  xmmword ptr [r14+974h], xmm0
0x1800d37f5  test    cl, cl
0x1800d37f7  jnz     loc_1800D3AA5
0x1800d37fd  mov     rax, [r14]
0x1800d3800  mov     rcx, r14
0x1800d3803  mov     rax, [rax+0C0h]
0x1800d380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d380f  test    al, al
0x1800d3811  jz      short loc_1800D3838
0x1800d3813  mov     rax, [r14+12A8h]
0x1800d381a  sub     rax, [r14+12A0h]
0x1800d3821  sar     rax, 3
0x1800d3825  test    rax, rax
0x1800d3828  jz      short loc_1800D3838
0x1800d382a  neg     rax
0x1800d382d  shl     rax, 3
0x1800d3831  add     [r14+12A8h], rax
0x1800d3838  mov     rax, [r14]
0x1800d383b  mov     rcx, r14
0x1800d383e  mov     rax, [rax+0E0h]
0x1800d3845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d384a  mov     r8, rax
0x1800d384d  test    rax, rax
0x1800d3850  jnz     loc_1800D3A57
0x1800d3856  mov     rax, [r14]
0x1800d3859  mov     rcx, r14
0x1800d385c  mov     rax, [rax+0E0h]
0x1800d3863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3868  mov     rdx, rax
0x1800d386b  test    rax, rax
0x1800d386e  jnz     loc_1800D4119
0x1800d3874  mov     rax, [r14]
0x1800d3877  mov     rcx, r14
0x1800d387a  mov     rax, [rax+0C0h]
0x1800d3881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3886  test    al, al
0x1800d3888  jnz     loc_1800D3C8C
0x1800d388e  cmp     byte ptr [r14+984h], 0
0x1800d3896  jz      loc_1800D3D94
0x1800d389c  cmp     byte ptr [r14+987h], 0
0x1800d38a4  mov     byte ptr [r14+985h], 1
0x1800d38ac  jnz     loc_1800D416E
0x1800d38b2  cmp     byte ptr [r14+988h], 0
0x1800d38ba  jnz     loc_1800D418F
0x1800d38c0  mov     r10, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800d38c7  mov     rax, r15
0x1800d38ca  test    r10, r10
0x1800d38cd  jz      short loc_1800D38D6
0x1800d38cf  mov     rax, [r10+370h]
0x1800d38d6  mov     [r14+78h], rax
0x1800d38da  test    r13d, r13d
0x1800d38dd  jnz     loc_1800D41A5
  ... truncated ...
```
