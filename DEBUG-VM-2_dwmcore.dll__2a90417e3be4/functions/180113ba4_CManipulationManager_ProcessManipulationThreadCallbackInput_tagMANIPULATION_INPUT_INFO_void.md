# CManipulationManager::ProcessManipulationThreadCallbackInput(tagMANIPULATION_INPUT_INFO *,void *)

- ea: `0x180113ba4`
- end: `0x180113e19`
- name: `?ProcessManipulationThreadCallbackInput@CManipulationManager@@KAHPEAUtagMANIPULATION_INPUT_INFO@@PEAX@Z`
- size: `629`
- prototype: `static int(struct tagMANIPULATION_INPUT_INFO *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180113920`

## callees

- `0x180035124`
- `0x18003d138`
- `0x180042de0`
- `0x1801104d4`
- `0x18011374c`
- `0x180113ba4`
- `0x180114458`
- `0x18011451c`
- `0x1801147a0`
- `0x180114880`
- `0x1801148e4`
- `0x1801149e8`
- `0x180168a38`
- `0x1801b26e0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180113ca5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180113ca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180113c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180113c8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180113c31`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180113c31`
- `ext-ms-win-compositor-hosting-l1-3-0!SetManipulationInputTarget` at `0x180113d51`
- `ext-ms-win-compositor-hosting-l1-3-0!SetManipulationInputTarget` at `0x180113d51`

## pseudocode

```c
__int64 __fastcall CManipulationManager::ProcessManipulationThreadCallbackInput(
        struct tagMANIPULATION_INPUT_INFO *a1,
        CManipulationManager *a2)
{
  struct CManipulationFrame *v2; // r15
  unsigned int *v5; // r14
  unsigned __int64 v6; // rbx
  unsigned int v7; // r12d
  int v8; // eax
  LARGE_INTEGER v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  unsigned int *v14; // rbx
  __int64 v15; // r8
  unsigned int near **v16; // r9
  __int64 i; // rdx
  struct CManipulationFrame *v18; // [rsp+70h] [rbp+40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+50h] BYREF
  struct CManipulationFrame *v20; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  v18 = 0;
  if ( !a1 )
    goto LABEL_10;
  v5 = (unsigned int *)((char *)a1 + 148);
  v6 = *((_QWORD *)a1 + 30);
  v7 = *((_DWORD *)a1 + 42);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      MANIPULATION_FRAME_RECEIVED,
      v7,
      *v5);
  InputTraceLogging::GestureTargeting::QueueFrame(v6, *(_QWORD *)a1, v7, *v5);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v18);
  v8 = CManipulationFrame::Create(a1, &v18);
  v2 = v18;
  if ( v8 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x15Du, 0);
LABEL_19:
    v14 = v5;
    goto LABEL_14;
  }
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v9 = PerformanceCount;
  *(LARGE_INTEGER *)((char *)v2 + (IsVailContainer() ? 0x48 : 0) + 72) = v9;
  InputTraceLogging::TelemetryDebug::GestureTargeting::QueueFrame((struct CManipulationFrame *)((char *)v2 + 32));
  v20 = v2;
  Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(&v20);
  v18 = v2;
  Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(&v18);
  v12 = CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Insert(v11, v10, &v18);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v20);
  if ( v12 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v12, 0x165u, 0);
    goto LABEL_19;
  }
  if ( GetCurrentThreadId() == CManipulationManager::s_dwManipulationThreadId && a2 )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        MANIPULATION_FRAME_QUEUED,
        v7,
        *v5);
    CManipulationManager::OnInput(a2);
    goto LABEL_10;
  }
  if ( SetEvent(hEvent) )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        MANIPULATION_FRAME_QUEUED,
        v7,
        *((unsigned int *)a1 + 37));
    goto LABEL_10;
  }
  v14 = (unsigned int *)((char *)a1 + 148);
  CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Remove(&CManipulationManager::s_InputQueue, &v18, 0, 0);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v18);
  v5 = (unsigned int *)((char *)a1 + 148);
LABEL_14:
  v18 = (struct CManipulationFrame *)CManipulationManager::s_rwPointerBufferLock;
  CReadWriteLock::AcquireExclusive((CReadWriteLock *)CManipulationManager::s_rwPointerBufferLock);
  v15 = *v14;
  v16 = &CManipulationManager::s_rgPointerIds;
  for ( i = 0; (unsigned int)i < (unsigned int)v15; v15 = *v5 )
  {
    *((_DWORD *)&CManipulationManager::s_rgPointerIds + i) = *((_DWORD *)a1 + 60 * (unsigned int)i + 41);
    i = (unsigned int)(i + 1);
  }
  if ( (*((_DWORD *)a1 + 43) & 0x180000) == 0 )
    SetManipulationInputTarget(*((unsigned int *)a1 + 42), 0, v15, &CManipulationManager::s_rgPointerIds, a1);
  CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(&v18, i, v15, v16);
LABEL_10:
  if ( v2 )
    (*(void (__fastcall **)(struct CManipulationFrame *))(*(_QWORD *)v2 + 8LL))(v2);
  return 1;
}

```

## disassembly

```asm
0x180113ba4  mov     [rsp-38h+arg_8], rbx
0x180113ba9  push    rbp
0x180113baa  push    rsi
0x180113bab  push    rdi
0x180113bac  push    r12
0x180113bae  push    r13
0x180113bb0  push    r14
0x180113bb2  push    r15
0x180113bb4  mov     rbp, rsp
0x180113bb7  sub     rsp, 30h
0x180113bbb  xor     r15d, r15d
0x180113bbe  mov     r13, rdx
0x180113bc1  mov     [rbp+arg_0], r15
0x180113bc5  mov     rsi, rcx
0x180113bc8  test    rcx, rcx
0x180113bcb  jz      loc_180113CBC
0x180113bd1  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180113bd8  lea     r14, [rcx+94h]
0x180113bdf  mov     rbx, [rcx+0F0h]
0x180113be6  mov     r12d, [rcx+0A8h]
0x180113bed  jnz     loc_180113D8B
0x180113bf3  mov     r9d, [r14]; unsigned int
0x180113bf6  mov     r8d, r12d; unsigned int
0x180113bf9  mov     rdx, [rsi]; unsigned __int64
0x180113bfc  mov     rcx, rbx; unsigned __int64
0x180113bff  call    ?QueueFrame@GestureTargeting@InputTraceLogging@@SAX_K0KK@Z; InputTraceLogging::GestureTargeting::QueueFrame(unsigned __int64,unsigned __int64,ulong,ulong)
0x180113c04  lea     rcx, [rbp+arg_0]
0x180113c08  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x180113c0d  lea     rdx, [rbp+arg_0]; struct CManipulationFrame **
0x180113c11  mov     rcx, rsi; struct tagMANIPULATION_INPUT_INFO *
0x180113c14  call    ?Create@CManipulationFrame@@SAJPEBUtagMANIPULATION_INPUT_INFO@@PEAPEAV1@@Z; CManipulationFrame::Create(tagMANIPULATION_INPUT_INFO const *,CManipulationFrame * *)
0x180113c19  mov     r15, [rbp+arg_0]
0x180113c1d  test    eax, eax
0x180113c1f  js      loc_180113D65
0x180113c25  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180113c29  mov     qword ptr [rbp+PerformanceCount], 0
0x180113c31  call    cs:__imp_QueryPerformanceCounter
0x180113c37  mov     rbx, qword ptr [rbp+PerformanceCount]
0x180113c3b  call    ?IsVailContainer@@YA_NXZ; IsVailContainer(void)
0x180113c40  neg     al
0x180113c42  lea     rcx, [r15+20h]; struct tagTELEMETRY_POINTER_FRAME_TIMES *
0x180113c46  sbb     rdx, rdx
0x180113c49  and     edx, 48h
0x180113c4c  mov     [rdx+r15+48h], rbx
0x180113c51  call    ?QueueFrame@GestureTargeting@TelemetryDebug@InputTraceLogging@@SAXAEBUtagTELEMETRY_POINTER_FRAME_TIMES@@@Z; InputTraceLogging::TelemetryDebug::GestureTargeting::QueueFrame(tagTELEMETRY_POINTER_FRAME_TIMES const &)
0x180113c56  lea     rcx, [rbp+arg_18]
0x180113c5a  mov     [rbp+arg_18], r15
0x180113c5e  call    ?InternalAddRef@?$ComPtr@UIInteractionContextWrapper@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(void)
0x180113c63  lea     rcx, [rbp+arg_0]
0x180113c67  mov     [rbp+arg_0], r15
0x180113c6b  call    ?InternalAddRef@?$ComPtr@UIInteractionContextWrapper@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(void)
0x180113c70  lea     r8, [rbp+arg_0]
0x180113c74  call    ?Insert@?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@AEAAJ_NV?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@Z; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Insert(bool,Microsoft::WRL::ComPtr<CManipulationFrame>)
0x180113c79  lea     rcx, [rbp+arg_18]
0x180113c7d  mov     ebx, eax
0x180113c7f  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x180113c84  test    ebx, ebx
0x180113c86  js      loc_180113E00
0x180113c8c  call    cs:__imp_GetCurrentThreadId
0x180113c92  cmp     eax, cs:?s_dwManipulationThreadId@CManipulationManager@@1KA; ulong CManipulationManager::s_dwManipulationThreadId
0x180113c98  jz      loc_180113DCB
0x180113c9e  mov     rcx, cs:hEvent; hEvent
0x180113ca5  call    cs:__imp_SetEvent
0x180113cab  test    eax, eax
0x180113cad  jz      short loc_180113CEA
0x180113caf  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180113cb6  jnz     loc_180113DA9
0x180113cbc  test    r15, r15
0x180113cbf  jz      short loc_180113CD0
0x180113cc1  mov     rdx, [r15]
0x180113cc4  mov     rcx, r15
0x180113cc7  mov     rax, [rdx+8]
0x180113ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113cd0  mov     rbx, [rsp+30h+arg_8]
0x180113cd5  mov     eax, 1
0x180113cda  add     rsp, 30h
0x180113cde  pop     r15
0x180113ce0  pop     r14
0x180113ce2  pop     r13
0x180113ce4  pop     r12
0x180113ce6  pop     rdi
0x180113ce7  pop     rsi
0x180113ce8  pop     rbp
0x180113ce9  retn
0x180113cea  xor     r9d, r9d
0x180113ced  lea     rdx, [rbp+arg_0]
0x180113cf1  xor     r8d, r8d
0x180113cf4  lea     rcx, ?s_InputQueue@CManipulationManager@@1V?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@A; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>> CManipulationManager::s_InputQueue
0x180113cfb  lea     rbx, [rsi+94h]
0x180113d02  call    ?Remove@?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@AEAA?AV?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@_NPEAI@Z; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Remove(bool,uint *)
0x180113d07  lea     rcx, [rbp+arg_0]
0x180113d0b  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x180113d10  mov     r14, rbx
0x180113d13  lea     rcx, ?s_rwPointerBufferLock@CManipulationManager@@1VCReadWriteLock@@A; this
0x180113d1a  mov     [rbp+arg_0], rcx
0x180113d1e  call    ?AcquireExclusive@CReadWriteLock@@QEAAXXZ; CReadWriteLock::AcquireExclusive(void)
0x180113d23  mov     r8d, [rbx]
0x180113d26  lea     r9, ?s_rgPointerIds@CManipulationManager@@1PAIA; uint near * CManipulationManager::s_rgPointerIds
0x180113d2d  xor     edx, edx
0x180113d2f  test    r8d, r8d
0x180113d32  jnz     loc_1802A5160
0x180113d38  test    dword ptr [rsi+0ACh], 180000h
0x180113d42  jnz     short loc_180113D57
0x180113d44  mov     ecx, [rsi+0A8h]
0x180113d4a  xor     edx, edx
0x180113d4c  mov     qword ptr [rsp+30h+var_10], rsi
0x180113d51  call    cs:__imp_SetManipulationInputTarget
0x180113d57  lea     rcx, [rbp+arg_0]
0x180113d5b  call    ??1?$CWriteGuard@VCReadWriteLock@@@@QEAA@XZ; CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(void)
0x180113d60  jmp     loc_180113CBC
0x180113d65  mov     [rsp+30h+var_8], 0; void *
0x180113d6e  mov     r9d, eax; int
0x180113d71  mov     [rsp+30h+var_10], 15Dh; unsigned int
0x180113d79  xor     edx, edx; int *
0x180113d7b  xor     r8d, r8d; unsigned int
0x180113d7e  lea     ecx, [rdx+14h]; unsigned int
0x180113d81  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180113d86  mov     rbx, r14
0x180113d89  jmp     short loc_180113D13
0x180113d8b  mov     r9d, [r14]
0x180113d8e  lea     rdx, MANIPULATION_FRAME_RECEIVED
0x180113d95  mov     r8d, r12d
0x180113d98  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180113d9f  call    McTemplateU0qq_EventWriteTransfer
0x180113da4  jmp     loc_180113BF3
0x180113da9  mov     r9d, [rsi+94h]
0x180113db0  lea     rdx, MANIPULATION_FRAME_QUEUED
0x180113db7  mov     r8d, r12d
0x180113dba  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180113dc1  call    McTemplateU0qq_EventWriteTransfer
0x180113dc6  jmp     loc_180113CBC
0x180113dcb  test    r13, r13
0x180113dce  jz      loc_180113C9E
0x180113dd4  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180113ddb  jz      loc_1802A5152
0x180113de1  mov     r9d, [r14]
0x180113de4  lea     rdx, MANIPULATION_FRAME_QUEUED
0x180113deb  mov     r8d, r12d
0x180113dee  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180113df5  call    McTemplateU0qq_EventWriteTransfer
0x180113dfa  nop
0x180113dfb  jmp     loc_1802A5152
0x180113e00  mov     [rsp+30h+var_8], 0
0x180113e09  mov     r9d, ebx
0x180113e0c  mov     [rsp+30h+var_10], 165h
0x180113e14  jmp     loc_180113D79
0x1802a5152  mov     rcx, r13; this
0x1802a5155  call    ?OnInput@CManipulationManager@@IEAAXXZ; CManipulationManager::OnInput(void)
0x1802a515a  nop
0x1802a515b  jmp     loc_180113CBC
0x1802a5160  mov     ecx, edx
0x1802a5162  imul    rax, rcx, 0F0h
0x1802a5169  mov     eax, [rax+rsi+0A4h]
0x1802a5170  mov     [r9+rdx*4], eax
0x1802a5174  inc     edx
0x1802a5176  mov     r8d, [r14]
0x1802a5179  cmp     edx, r8d
0x1802a517c  jb      short loc_1802A5160
0x1802a517e  jmp     loc_180113D38
```
