# CComposition::PreRender(bool *)

- ea: `0x18010e528`
- end: `0x18010e9d9`
- name: `?PreRender@CComposition@@IEAAJPEA_N@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CComposition *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18010efa0`

## callees

- `0x180042de0`
- `0x180049b14`
- `0x180053670`
- `0x180098090`
- `0x1800a8b00`
- `0x1800d3400`
- `0x18010c130`
- `0x18010e528`
- `0x180110f70`
- `0x1801111f0`
- `0x18011361c`
- `0x1801153b0`
- `0x180154d2c`
- `0x180154de0`
- `0x180154e78`
- `0x1801556d0`
- `0x1801557f8`
- `0x18015589c`
- `0x180168d40`
- `0x18017adc4`
- `0x18017ce54`
- `0x180180d20`
- `0x1801876f0`
- `0x180187a58`
- `0x18018c7f0`
- `0x18018ca74`
- `0x18018cb14`
- `0x1801a01e0`
- `0x1801a5600`
- `0x1801ab610`
- `0x1802591e0`
- `0x18025931c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e6c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e71a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e80a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e6c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e71a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010e80a`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e6d1`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e727`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e817`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e6d1`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e727`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18010e817`

## pseudocode

```c
__int64 __fastcall CComposition::PreRender(CComposition *this, bool *a2)
{
  CTreeLock *v2; // r12
  CDebugVisualImage *v4; // rbx
  unsigned int i; // edi
  __int64 v7; // rdx
  wil::details *v8; // rcx
  int v9; // eax
  int v10; // r14d
  CManipulationManager *v11; // rcx
  CManipulationManager *v12; // rcx
  int v14; // eax
  unsigned __int64 v15; // rcx
  HANDLE CurrentThread; // rax
  BOOL v17; // eax
  int v18; // eax
  unsigned __int64 v19; // rcx
  HANDLE v20; // rax
  BOOL v21; // eax
  int v22; // eax
  CComposition *v23; // rcx
  bool v24; // al
  CSceneResourceManager *v25; // rcx
  unsigned __int64 v26; // rcx
  HANDLE v27; // rax
  BOOL v28; // eax
  int v29; // eax
  int v30; // edi
  CExpressionManager *v31; // r15
  unsigned __int64 v32; // rdi
  int v33; // eax
  int v34; // edi
  int v35; // eax
  struct CDebugVisualImage *v36; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int64 CycleTime; // [rsp+78h] [rbp+48h] BYREF

  v2 = (CComposition *)((char *)this + 5696);
  *a2 = 1;
  v4 = 0;
  v36 = 0;
  CTreeLock::AcquireExclusive((CComposition *)((char *)this + 5696));
  if ( (__int64)(*((_QWORD *)this + 724) - *((_QWORD *)this + 723)) >> 3 )
    detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::clear_region();
  CComposition::DestroyDelayDeleteResources(this);
  CEffectCompilationService::HandleCompletedTasks(*((CEffectCompilationService **)this + 81));
  for ( i = 0; i < *((_DWORD *)this + 214); ++i )
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 104) + 8LL * i);
    if ( v7 )
    {
      v8 = *(wil::details **)(v7 + 48);
      if ( v8 )
      {
        if ( *(_BYTE *)(v7 + 121) && !*(_DWORD *)(v7 + 144) )
        {
          *(_BYTE *)(v7 + 121) = 0;
          wil::details::SetEvent(v8, (void *)v7);
        }
      }
    }
  }
  v9 = CComposition::BeginCompositionFrame(this);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v14 = CComposition::ProcessBatches(this);
    v10 = v14;
    if ( v14 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v14, 0xC5Eu, 0);
    }
    else
    {
      CExpressionManager::NotifyBatchProcessingComplete(*((CExpressionManager **)this + 102));
      v15 = 0;
      CycleTime = 0;
      if ( ::CycleTime )
      {
        CurrentThread = GetCurrentThread();
        v17 = QueryThreadCycleTime(CurrentThread, &CycleTime);
        v15 = CycleTime;
        if ( v17 )
          qword_1803BADB0 += CycleTime - ::CycleTime;
      }
      ::CycleTime = v15;
      v18 = CComposition::ProcessSurfaceUpdates(this);
      v10 = v18;
      if ( v18 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v18, 0xC63u, 0);
      }
      else
      {
        v19 = 0;
        CycleTime = 0;
        if ( ::CycleTime )
        {
          v20 = GetCurrentThread();
          v21 = QueryThreadCycleTime(v20, &CycleTime);
          v19 = CycleTime;
          if ( v21 )
            qword_1803BADB8 += CycleTime - ::CycleTime;
        }
        ::CycleTime = v19;
        if ( g_pDebugVisual )
        {
          v35 = CDebugVisualImage::Create(this, g_pDebugVisual, &v36);
          v4 = v36;
          if ( v35 >= 0 )
            *((_BYTE *)this + 6408) = 1;
        }
        v22 = CRenderTargetManager::CheckOcclusionState(*((CRenderTargetManager **)this + 77));
        v10 = v22;
        if ( v22 < 0 )
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v22, 0xC71u, 0);
        (*(void (__fastcall **)(CComposition *))(*(_QWORD *)this + 32LL))(this);
        v24 = CComposition::ClearCaches(v23);
        v25 = (CSceneResourceManager *)*((_QWORD *)this + 84);
        *a2 = v24;
        if ( (__int64)(*((_QWORD *)v25 + 6) - *((_QWORD *)v25 + 5)) >> 3 )
          CSceneResourceManager::EnsureSceneCompositor(v25);
        else
          CSceneResourceManager::ReleaseSceneCompositor(v25);
        if ( CComposition::TotallyOccluded(this) )
        {
          dword_1803BAD70 |= 0x200u;
          v31 = (CExpressionManager *)*((_QWORD *)this + 102);
          if ( *((_QWORD *)v31 + 64) )
          {
            v32 = *((_QWORD *)this + 110);
            CExpressionManager::Invalidate(*((CExpressionManager **)this + 102));
            CExpressionManager::UpdateExpressions(v31, v32);
          }
          CExpressionManager::ShrinkQueuedStateChanges(v31);
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 78) + 48LL))(*((_QWORD *)this + 78))
            || *((_DWORD *)this + 1482) )
          {
            *((_BYTE *)this + 6408) = 1;
          }
        }
        else
        {
          CSuperWetInkManager::DirtyActiveInk(*((CSuperWetInkManager **)this + 82));
          CComposition::UpdateAnimateResources(this);
          CComposition::UpdateExpressions(this);
          v26 = 0;
          CycleTime = 0;
          if ( ::CycleTime )
          {
            v27 = GetCurrentThread();
            v28 = QueryThreadCycleTime(v27, &CycleTime);
            v26 = CycleTime;
            if ( v28 )
              qword_1803BADC0 += CycleTime - ::CycleTime;
          }
          ::CycleTime = v26;
          DataProviderManager::PostExpressionsUpdated(*((DataProviderManager **)this + 799));
          CSceneResourceManager::FrameTick(*((CSceneResourceManager **)this + 84));
          v29 = CComposition::CleanTrees(this);
          v30 = v29;
          if ( v29 < 0 )
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v29, 0xC90u, 0);
          if ( !v10 || v10 >= 0 && v30 < 0 )
            v10 = v30;
        }
      }
    }
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v9, 0xC5Bu, 0);
  }
  v11 = (CManipulationManager *)*((_QWORD *)this + 80);
  if ( v11 )
    CManipulationManager::ReleasePendingReferences(v11);
  if ( *((_BYTE *)this + 6408) )
  {
    v33 = CComposition::CleanTrees(this);
    v34 = v33;
    if ( v33 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180329FF8, 3u, v33, 0xCAFu, 0);
    if ( !v10 || v10 >= 0 && v34 < 0 )
      v10 = v34;
  }
  CComposition::CleanPossibleDirtyInputSinkList(this);
  if ( v4 )
    CDebugVisualImage::LockAndRead(v4);
  CTreeLock::ReleaseExclusive(v2);
  if ( *((_BYTE *)this + 6456) )
  {
    v12 = *(CManipulationManager **)(*((_QWORD *)this + 79) + 24LL);
    if ( v12 )
      (*(void (__fastcall **)(CManipulationManager *))(*(_QWORD *)v12 + 16LL))(v12);
    *((_BYTE *)this + 6456) = 0;
  }
  CManipulationManager::WakeMTForMidmanipulationUpdateIfNecessary(v12);
  wil::com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>::~com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>(&v36);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18010e528  mov     [rsp-38h+arg_10], rbx
0x18010e52d  push    rbp
0x18010e52e  push    rsi
0x18010e52f  push    rdi
0x18010e530  push    r12
0x18010e532  push    r13
0x18010e534  push    r14
0x18010e536  push    r15
0x18010e538  mov     rbp, rsp
0x18010e53b  sub     rsp, 30h
0x18010e53f  lea     r12, [rcx+1640h]
0x18010e546  mov     byte ptr [rdx], 1
0x18010e549  mov     rsi, rcx
0x18010e54c  xor     r13d, r13d
0x18010e54f  mov     ebx, r13d
0x18010e552  mov     rcx, r12; this
0x18010e555  mov     [rbp+arg_0], rbx
0x18010e559  mov     r15, rdx
0x18010e55c  call    ?AcquireExclusive@CTreeLock@@QEAAXXZ; CTreeLock::AcquireExclusive(void)
0x18010e561  lea     rcx, [rsi+1698h]
0x18010e568  mov     r8, [rcx+8]
0x18010e56c  sub     r8, [rcx]
0x18010e56f  sar     r8, 3
0x18010e573  test    r8, r8
0x18010e576  jnz     loc_18010E95B
0x18010e57c  mov     rcx, rsi; this
0x18010e57f  call    ?DestroyDelayDeleteResources@CComposition@@QEAAXXZ; CComposition::DestroyDelayDeleteResources(void)
0x18010e584  mov     rcx, [rsi+288h]; this
0x18010e58b  call    ?HandleCompletedTasks@CEffectCompilationService@@QEAAXXZ; CEffectCompilationService::HandleCompletedTasks(void)
0x18010e590  mov     edi, r13d
0x18010e593  cmp     [rsi+358h], r13d
0x18010e59a  jbe     short loc_18010E5CB
0x18010e59c  mov     rax, [rsi+340h]
0x18010e5a3  mov     ecx, edi
0x18010e5a5  mov     rdx, [rax+rcx*8]; void *
0x18010e5a9  test    rdx, rdx
0x18010e5ac  jz      short loc_18010E5C1
0x18010e5ae  mov     rcx, [rdx+30h]; this
0x18010e5b2  test    rcx, rcx
0x18010e5b5  jz      short loc_18010E5C1
0x18010e5b7  cmp     [rdx+79h], r13b
0x18010e5bb  jnz     loc_18010E896
0x18010e5c1  inc     edi
0x18010e5c3  cmp     edi, [rsi+358h]
0x18010e5c9  jb      short loc_18010E59C
0x18010e5cb  mov     rcx, rsi; this
0x18010e5ce  call    ?BeginCompositionFrame@CComposition@@IEAAJXZ; CComposition::BeginCompositionFrame(void)
0x18010e5d3  mov     r14d, eax
0x18010e5d6  test    eax, eax
0x18010e5d8  jns     loc_18010E695
0x18010e5de  mov     [rsp+30h+var_8], r13; void *
0x18010e5e3  mov     [rsp+30h+var_10], 0C5Bh; unsigned int
0x18010e5eb  mov     r8d, 3; unsigned int
0x18010e5f1  lea     rdx, dword_180329FF8; int *
0x18010e5f8  mov     r9d, eax; int
0x18010e5fb  lea     ecx, [r8+11h]; unsigned int
0x18010e5ff  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010e604  mov     rcx, [rsi+280h]; this
0x18010e60b  test    rcx, rcx
0x18010e60e  jz      short loc_18010E615
0x18010e610  call    ?ReleasePendingReferences@CManipulationManager@@QEAAXXZ; CManipulationManager::ReleasePendingReferences(void)
0x18010e615  mov     al, [rsi+1908h]
0x18010e61b  test    al, al
0x18010e61d  jnz     loc_18010E965
0x18010e623  mov     rcx, rsi; this
0x18010e626  call    ?CleanPossibleDirtyInputSinkList@CComposition@@QEAAJXZ; CComposition::CleanPossibleDirtyInputSinkList(void)
0x18010e62b  test    rbx, rbx
0x18010e62e  jz      short loc_18010E638
0x18010e630  mov     rcx, rbx; this
0x18010e633  call    ?LockAndRead@CDebugVisualImage@@QEAAXXZ; CDebugVisualImage::LockAndRead(void)
0x18010e638  mov     rcx, r12; this
0x18010e63b  call    ?ReleaseExclusive@CTreeLock@@QEAAXXZ; CTreeLock::ReleaseExclusive(void)
0x18010e640  cmp     [rsi+1938h], r13b
0x18010e647  jz      short loc_18010E66C
0x18010e649  mov     rax, [rsi+278h]
0x18010e650  mov     rcx, [rax+18h]
0x18010e654  test    rcx, rcx
0x18010e657  jz      short loc_18010E665
0x18010e659  mov     rax, [rcx]
0x18010e65c  mov     rax, [rax+10h]
0x18010e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e665  mov     [rsi+1938h], r13b
0x18010e66c  call    ?WakeMTForMidmanipulationUpdateIfNecessary@CManipulationManager@@QEAAXXZ; CManipulationManager::WakeMTForMidmanipulationUpdateIfNecessary(void)
0x18010e671  lea     rcx, [rbp+arg_0]
0x18010e675  call    ??1?$com_ptr_t@VCDebugVisualImage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>::~com_ptr_t<CDebugVisualImage,wil::err_returncode_policy>(void)
0x18010e67a  mov     rbx, [rsp+30h+arg_10]
0x18010e682  mov     eax, r14d
0x18010e685  add     rsp, 30h
0x18010e689  pop     r15
0x18010e68b  pop     r14
0x18010e68d  pop     r13
0x18010e68f  pop     r12
0x18010e691  pop     rdi
0x18010e692  pop     rsi
0x18010e693  pop     rbp
0x18010e694  retn
0x18010e695  mov     rcx, rsi; this
0x18010e698  call    ?ProcessBatches@CComposition@@IEAAJXZ; CComposition::ProcessBatches(void)
0x18010e69d  mov     r14d, eax
0x18010e6a0  test    eax, eax
0x18010e6a2  js      loc_18010E8CB
0x18010e6a8  mov     rcx, [rsi+330h]; this
0x18010e6af  call    ?NotifyBatchProcessingComplete@CExpressionManager@@QEAAXXZ; CExpressionManager::NotifyBatchProcessingComplete(void)
0x18010e6b4  cmp     cs:CycleTime, r13
0x18010e6bb  mov     rcx, r13
0x18010e6be  mov     [rbp+CycleTime], rcx
0x18010e6c2  jz      short loc_18010E6F0
0x18010e6c4  call    cs:__imp_GetCurrentThread
0x18010e6ca  mov     rcx, rax; ThreadHandle
0x18010e6cd  lea     rdx, [rbp+CycleTime]; CycleTime
0x18010e6d1  call    cs:__imp_QueryThreadCycleTime
0x18010e6d7  mov     rcx, [rbp+CycleTime]
0x18010e6db  test    eax, eax
0x18010e6dd  jz      short loc_18010E6F0
0x18010e6df  mov     rax, rcx
0x18010e6e2  sub     rax, cs:CycleTime
0x18010e6e9  add     cs:qword_1803BADB0, rax
0x18010e6f0  mov     cs:CycleTime, rcx
0x18010e6f7  mov     rcx, rsi; this
0x18010e6fa  call    ?ProcessSurfaceUpdates@CComposition@@IEAAJXZ; CComposition::ProcessSurfaceUpdates(void)
0x18010e6ff  mov     r14d, eax
0x18010e702  test    eax, eax
0x18010e704  js      loc_18010E8DD
0x18010e70a  cmp     cs:CycleTime, r13
0x18010e711  mov     rcx, r13
0x18010e714  mov     [rbp+CycleTime], rcx
0x18010e718  jz      short loc_18010E746
0x18010e71a  call    cs:__imp_GetCurrentThread
0x18010e720  mov     rcx, rax; ThreadHandle
0x18010e723  lea     rdx, [rbp+CycleTime]; CycleTime
0x18010e727  call    cs:__imp_QueryThreadCycleTime
0x18010e72d  mov     rcx, [rbp+CycleTime]
0x18010e731  test    eax, eax
0x18010e733  jz      short loc_18010E746
0x18010e735  mov     rax, rcx
0x18010e738  sub     rax, cs:CycleTime
0x18010e73f  add     cs:qword_1803BADB8, rax
0x18010e746  mov     rdx, cs:?g_pDebugVisual@@3PEAVCVisual@@EA; struct CVisual *
0x18010e74d  mov     cs:CycleTime, rcx
0x18010e754  test    rdx, rdx
0x18010e757  jnz     loc_18010E9B5
0x18010e75d  mov     rcx, [rsi+268h]; this
0x18010e764  call    ?CheckOcclusionState@CRenderTargetManager@@QEAAJXZ; CRenderTargetManager::CheckOcclusionState(void)
0x18010e769  mov     r14d, eax
0x18010e76c  test    eax, eax
0x18010e76e  jns     short loc_18010E796
0x18010e770  mov     r8d, 3; unsigned int
0x18010e776  mov     [rsp+30h+var_8], r13; void *
0x18010e77b  mov     r9d, eax; int
0x18010e77e  mov     [rsp+30h+var_10], 0C71h; unsigned int
0x18010e786  lea     rdx, dword_180329FF8; int *
0x18010e78d  lea     ecx, [r8+11h]; unsigned int
0x18010e791  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010e796  mov     rax, [rsi]
0x18010e799  mov     rcx, rsi
0x18010e79c  mov     rax, [rax+20h]
0x18010e7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e7a5  call    ?ClearCaches@CComposition@@IEBA_NXZ; CComposition::ClearCaches(void)
0x18010e7aa  mov     rcx, [rsi+2A0h]; this
0x18010e7b1  mov     [r15], al
0x18010e7b4  mov     rax, [rcx+30h]
0x18010e7b8  sub     rax, [rcx+28h]
0x18010e7bc  sar     rax, 3
0x18010e7c0  test    rax, rax
0x18010e7c3  jnz     loc_18010E8C1
0x18010e7c9  call    ?ReleaseSceneCompositor@CSceneResourceManager@@AEAAXXZ; CSceneResourceManager::ReleaseSceneCompositor(void)
0x18010e7ce  mov     rcx, rsi; this
0x18010e7d1  call    ?TotallyOccluded@CComposition@@QEBA_NXZ; CComposition::TotallyOccluded(void)
0x18010e7d6  test    al, al
0x18010e7d8  jnz     loc_18010E8EF
0x18010e7de  mov     rcx, [rsi+290h]; this
0x18010e7e5  call    ?DirtyActiveInk@CSuperWetInkManager@@QEAAXXZ; CSuperWetInkManager::DirtyActiveInk(void)
0x18010e7ea  mov     rcx, rsi; this
0x18010e7ed  call    ?UpdateAnimateResources@CComposition@@IEAAXXZ; CComposition::UpdateAnimateResources(void)
0x18010e7f2  mov     rcx, rsi; this
0x18010e7f5  call    ?UpdateExpressions@CComposition@@QEAAXXZ; CComposition::UpdateExpressions(void)
0x18010e7fa  cmp     cs:CycleTime, r13
0x18010e801  mov     rcx, r13
0x18010e804  mov     [rbp+CycleTime], rcx
0x18010e808  jz      short loc_18010E836
0x18010e80a  call    cs:__imp_GetCurrentThread
0x18010e810  mov     rcx, rax; ThreadHandle
0x18010e813  lea     rdx, [rbp+CycleTime]; CycleTime
0x18010e817  call    cs:__imp_QueryThreadCycleTime
0x18010e81d  mov     rcx, [rbp+CycleTime]
0x18010e821  test    eax, eax
0x18010e823  jz      short loc_18010E836
0x18010e825  mov     rax, rcx
0x18010e828  sub     rax, cs:CycleTime
0x18010e82f  add     cs:qword_1803BADC0, rax
0x18010e836  mov     cs:CycleTime, rcx
0x18010e83d  mov     rcx, [rsi+18F8h]; this
0x18010e844  call    ?PostExpressionsUpdated@DataProviderManager@@QEAAXXZ; DataProviderManager::PostExpressionsUpdated(void)
0x18010e849  mov     rcx, [rsi+2A0h]; this
0x18010e850  call    ?FrameTick@CSceneResourceManager@@QEAAXXZ; CSceneResourceManager::FrameTick(void)
0x18010e855  mov     rcx, rsi; this
0x18010e858  call    ?CleanTrees@CComposition@@IEAAJXZ; CComposition::CleanTrees(void)
0x18010e85d  mov     edi, eax
0x18010e85f  test    eax, eax
0x18010e861  jns     short loc_18010E889
0x18010e863  mov     r8d, 3; unsigned int
0x18010e869  mov     [rsp+30h+var_8], r13; void *
0x18010e86e  mov     r9d, eax; int
0x18010e871  mov     [rsp+30h+var_10], 0C90h; unsigned int
0x18010e879  lea     rdx, dword_180329FF8; int *
0x18010e880  lea     ecx, [r8+11h]; unsigned int
0x18010e884  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010e889  test    r14d, r14d
0x18010e88c  jnz     short loc_18010E8B1
0x18010e88e  mov     r14d, edi
0x18010e891  jmp     loc_18010E604
0x18010e896  cmp     [rdx+90h], r13d
0x18010e89d  jnz     loc_18010E5C1
0x18010e8a3  mov     [rdx+79h], r13b
0x18010e8a7  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18010e8ac  jmp     loc_18010E5C1
0x18010e8b1  js      loc_18010E604
0x18010e8b7  test    edi, edi
0x18010e8b9  jns     loc_18010E604
0x18010e8bf  jmp     short loc_18010E88E
0x18010e8c1  call    ?EnsureSceneCompositor@CSceneResourceManager@@AEAAJXZ; CSceneResourceManager::EnsureSceneCompositor(void)
0x18010e8c6  jmp     loc_18010E7CE
0x18010e8cb  mov     [rsp+30h+var_8], r13
0x18010e8d0  mov     [rsp+30h+var_10], 0C5Eh
0x18010e8d8  jmp     loc_18010E5EB
0x18010e8dd  mov     [rsp+30h+var_8], r13
0x18010e8e2  mov     [rsp+30h+var_10], 0C63h
0x18010e8ea  jmp     loc_18010E5EB
0x18010e8ef  bts     cs:dword_1803BAD70, 9
0x18010e8f7  mov     r15, [rsi+330h]
0x18010e8fe  cmp     [r15+200h], r13
0x18010e905  jnz     short loc_18010E93F
0x18010e907  mov     rcx, r15; this
0x18010e90a  call    ?ShrinkQueuedStateChanges@CExpressionManager@@AEAAXXZ; CExpressionManager::ShrinkQueuedStateChanges(void)
0x18010e90f  mov     rcx, [rsi+270h]
0x18010e916  mov     rax, [rcx]
0x18010e919  mov     rax, [rax+30h]
0x18010e91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e922  test    al, al
0x18010e924  jnz     short loc_18010E933
0x18010e926  cmp     [rsi+1728h], r13d
0x18010e92d  jz      loc_18010E604
0x18010e933  mov     byte ptr [rsi+1908h], 1
0x18010e93a  jmp     loc_18010E604
0x18010e93f  mov     rdi, [rsi+370h]
0x18010e946  mov     rcx, r15; this
0x18010e949  call    ?Invalidate@CExpressionManager@@QEAAXXZ; CExpressionManager::Invalidate(void)
0x18010e94e  mov     rdx, rdi; unsigned __int64
0x18010e951  mov     rcx, r15; this
0x18010e954  call    ?UpdateExpressions@CExpressionManager@@QEAAX_K@Z; CExpressionManager::UpdateExpressions(unsigned __int64)
0x18010e959  jmp     short loc_18010E907
0x18010e95b  call    ?clear_region@?$vector_facade@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$buffer_impl@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@$07$00Vliberal_expansion_policy@detail@@@detail@@@detail@@IEAAX_K0@Z; detail::vector_facade<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,detail::buffer_impl<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>,8,1,detail::liberal_expansion_policy>>::clear_region(unsigned __int64,unsigned __int64)
0x18010e960  jmp     loc_18010E57C
0x18010e965  mov     rcx, rsi; this
0x18010e968  call    ?CleanTrees@CComposition@@IEAAJXZ; CComposition::CleanTrees(void)
0x18010e96d  mov     edi, eax
0x18010e96f  test    eax, eax
0x18010e971  jns     short loc_18010E999
0x18010e973  mov     r8d, 3; unsigned int
0x18010e979  mov     [rsp+30h+var_8], r13; void *
0x18010e97e  mov     r9d, eax; int
0x18010e981  mov     [rsp+30h+var_10], 0CAFh; unsigned int
0x18010e989  lea     rdx, dword_180329FF8; int *
0x18010e990  lea     ecx, [r8+11h]; unsigned int
0x18010e994  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18010e999  test    r14d, r14d
0x18010e99c  jz      loc_1802A4F86
0x18010e9a2  js      loc_18010E623
0x18010e9a8  test    edi, edi
0x18010e9aa  jns     loc_18010E623
0x18010e9b0  jmp     loc_1802A4F86
0x18010e9b5  lea     r8, [rbp+arg_0]; struct CDebugVisualImage **
0x18010e9b9  mov     rcx, rsi; struct CComposition *
0x18010e9bc  call    ?Create@CDebugVisualImage@@SAJPEAVCComposition@@PEAVCVisual@@PEAPEAV1@@Z; CDebugVisualImage::Create(CComposition *,CVisual *,CDebugVisualImage * *)
0x18010e9c1  mov     rbx, [rbp+arg_0]
0x18010e9c5  test    eax, eax
0x18010e9c7  js      loc_18010E75D
0x18010e9cd  mov     byte ptr [rsi+1908h], 1
0x18010e9d4  jmp     loc_18010E75D
0x1802a4f86  mov     r14d, edi
0x1802a4f89  jmp     loc_18010E623
```
