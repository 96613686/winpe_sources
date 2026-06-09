# GameInputServer::~GameInputServer(void)

- ea: `0x18002d6b0`
- end: `0x18002da6d`
- name: `??1GameInputServer@@AEAA@XZ`
- size: `957`
- prototype: `void __fastcall(ULONG_PTR dwData)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x18003adb0`
- `0x18003fef0`

## callees

- `0x180001540`
- `0x18000c11c`
- `0x18002d3b0`
- `0x18002d434`
- `0x18002d50c`
- `0x18002d59c`
- `0x18002d6b0`
- `0x18002da74`
- `0x18002dd78`
- `0x180041ef8`
- `0x180042fd0`
- `0x18004458c`
- `0x180048eb4`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002d8fd`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002d8fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d81d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d81d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d76f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d7a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d76f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d7a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d85d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d85d`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18002d78c`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18002d78c`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18002d7b3`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x18002d7b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d9a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d7c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d9a6`

## pseudocode

```c
void __fastcall GameInputServer::~GameInputServer(ULONG_PTR dwData)
{
  __int64 v1; // rdx
  _QWORD *v2; // rbp
  void **v4; // rdx
  __int64 v5; // rcx
  void *v6; // rbx
  __int64 **v7; // r15
  __int64 **i; // rsi
  __int64 *v9; // rax
  RTL_SRWLOCK *v10; // rdi
  GameInputServer::BufferListEntry *j; // rbx
  GameInputServer::BufferListEntry *v12; // rdx
  GameInputServer::BufferListEntry **v13; // rax
  const struct std::nothrow_t *v14; // rdx
  GameInputServerDevice *v15; // rbx
  const struct std::nothrow_t *v16; // rdx
  __int64 *v17; // rcx
  __int64 v18; // rax
  PVOID v19; // rbx
  const struct std::nothrow_t *v20; // rdx
  int v21; // r8d
  int v22; // r9d
  void *v23; // rcx
  __int64 v24; // rcx
  GameInputServer::ClientListEntry **v25; // rbx
  const struct std::nothrow_t *v26; // rdx
  GameInputServer::ClientListEntry *v27; // rdi
  GameInputServer::ClientListEntry **v28; // rax
  __int64 v29; // rcx
  int v30; // [rsp+80h] [rbp+8h] BYREF
  const char *v31; // [rsp+88h] [rbp+10h] BYREF
  const char *v32; // [rsp+90h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(dwData + 240);
  *(_QWORD *)dwData = &GameInputServer::`vftable';
  v2 = (_QWORD *)(dwData + 232);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 56LL))(*v2);
    *(_QWORD *)(dwData + 240) = 0;
  }
  v4 = *(void ***)(dwData + 248);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 72LL))(*v2);
    *(_QWORD *)(dwData + 248) = 0;
  }
  v5 = *v2;
  if ( *v2 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( *(_QWORD *)(dwData + 136) )
    PnpApiWrapper::Details::UnregisterDeviceEventHandler((PnpApiWrapper::Details *)(dwData + 136), v4);
  if ( *(_QWORD *)(dwData + 144) )
    PnpApiWrapper::Details::UnregisterDeviceEventHandler((PnpApiWrapper::Details *)(dwData + 144), v4);
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)(dwData + 40), 0);
  if ( v6 )
  {
    if ( WaitForSingleObject(v6, 0) )
    {
      QueueUserAPC(GameInputServer::TerminateWorkerThreadApcThunk, v6, dwData);
      if ( WaitForSingleObject(v6, 0x1F4u) )
        SuspendThread(v6);
    }
    CloseHandle(v6);
  }
  v7 = (__int64 **)(dwData + 80);
  for ( i = *(__int64 ***)(dwData + 80); i != v7; i = (__int64 **)*i )
  {
    GameInputServerDevice::StopProcessingInput((GameInputServerDevice *)((unsigned __int64)(i - 6) & -(__int64)(i != 0)));
    v9 = (__int64 *)(dwData + 56);
    v10 = *(RTL_SRWLOCK **)(dwData + 56);
    while ( v10 != (RTL_SRWLOCK *)v9 )
    {
      for ( j = (GameInputServer::BufferListEntry *)v10[4].Ptr; ; j = *(GameInputServer::BufferListEntry **)j )
      {
        if ( j == (GameInputServer::BufferListEntry *)&v10[4] )
          goto LABEL_27;
        if ( *((_QWORD *)j + 2) == ((unsigned __int64)(i - 6) & -(__int64)(i != 0)) )
          break;
      }
      AcquireSRWLockExclusive(v10 + 3);
      v12 = *(GameInputServer::BufferListEntry **)j;
      if ( *(GameInputServer::BufferListEntry **)(*(_QWORD *)j + 8LL) != j )
        goto LABEL_35;
      v13 = (GameInputServer::BufferListEntry **)*((_QWORD *)j + 1);
      if ( *v13 != j )
        goto LABEL_35;
      *v13 = v12;
      *((_QWORD *)v12 + 1) = v13;
      --LODWORD(v10[6].Ptr);
      GameInputServer::BufferListEntry::~BufferListEntry(j);
      operator delete(j, v14);
      ReleaseSRWLockExclusive(v10 + 3);
LABEL_27:
      v10 = (RTL_SRWLOCK *)v10->Ptr;
      v9 = (__int64 *)(dwData + 56);
    }
  }
  while ( 1 )
  {
    v17 = *v7;
    v18 = **v7;
    if ( (__int64 **)(*v7)[1] != v7 || *(__int64 **)(v18 + 8) != v17 )
LABEL_35:
      __fastfail(3u);
    *v7 = (__int64 *)v18;
    *(_QWORD *)(v18 + 8) = v7;
    if ( v17 == (__int64 *)v7 )
      break;
    v15 = (GameInputServerDevice *)((unsigned __int64)(v17 - 6)
                                  & ((unsigned __int128)-(__int128)(unsigned __int64)v17 >> 64));
    if ( v15 )
    {
      GameInputServerDevice::~GameInputServerDevice(v15);
      operator delete(v15, v16);
    }
    --*(_DWORD *)(dwData + 96);
  }
  v19 = qword_180069878;
  if ( qword_180069878 )
  {
    ControllerWatcher::~ControllerWatcher((ControllerWatcher *)qword_180069878);
    operator delete(v19, v20);
  }
  qword_180069878 = 0;
  if ( (unsigned int)Feature_52580392__private_IsEnabledDeviceUsageNoInline() && *(_QWORD *)(dwData + 264) )
  {
    RtlUnsubscribeWnfStateChangeNotification();
    *(_QWORD *)(dwData + 264) = 0;
  }
  if ( (unsigned int)dword_180069000 > 4
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    v30 = 126;
    v31 = "GameInputServer: Destroyed";
    v32 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      qword_180069018,
      (unsigned int)qword_1800600A8,
      v21,
      v22,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v31);
  }
  v23 = *(void **)(dwData + 280);
  if ( v23 )
  {
    CloseHandle(v23);
    *(_QWORD *)(dwData + 280) = 0;
  }
  v24 = *v2;
  if ( *v2 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  RouterKeyboardBugFix::~RouterKeyboardBugFix((RouterKeyboardBugFix *)(dwData + 176));
  NtList<GameInputServer::WorkItemListEntry>::~NtList<GameInputServer::WorkItemListEntry>(dwData + 152);
  NtList<GameInputServer::WorkItemListEntry>::~NtList<GameInputServer::WorkItemListEntry>(dwData + 104);
  NtList<GameInputServerDevice>::~NtList<GameInputServerDevice>(dwData + 80);
  v25 = (GameInputServer::ClientListEntry **)(dwData + 56);
  while ( 1 )
  {
    v27 = *v25;
    v28 = *(GameInputServer::ClientListEntry ***)*v25;
    if ( *((GameInputServer::ClientListEntry ***)*v25 + 1) != v25 || v28[1] != v27 )
      goto LABEL_35;
    *v25 = (GameInputServer::ClientListEntry *)v28;
    v28[1] = (GameInputServer::ClientListEntry *)v25;
    if ( v27 == (GameInputServer::ClientListEntry *)v25 )
      break;
    GameInputServer::ClientListEntry::~ClientListEntry(v27);
    operator delete(v27, v26);
    --*(_DWORD *)(dwData + 72);
  }
  v29 = *(_QWORD *)(dwData + 32);
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    *(_QWORD *)(dwData + 32) = 0;
  }
}

```

## disassembly

```asm
0x18002d6b0  mov     [rsp+arg_18], rbx
0x18002d6b5  push    rbp
0x18002d6b6  push    rsi
0x18002d6b7  push    rdi
0x18002d6b8  push    r12
0x18002d6ba  push    r13
0x18002d6bc  push    r14
0x18002d6be  push    r15
0x18002d6c0  sub     rsp, 40h
0x18002d6c4  mov     rdx, [rcx+0F0h]
0x18002d6cb  lea     rax, ??_7GameInputServer@@6B@; const GameInputServer::`vftable'
0x18002d6d2  xor     r12d, r12d
0x18002d6d5  mov     [rcx], rax
0x18002d6d8  lea     rbp, [rcx+0E8h]
0x18002d6df  mov     r14, rcx
0x18002d6e2  test    rdx, rdx
0x18002d6e5  jz      short loc_18002D6FE
0x18002d6e7  mov     rcx, [rbp+0]
0x18002d6eb  mov     rax, [rcx]
0x18002d6ee  mov     rax, [rax+38h]
0x18002d6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6f7  mov     [r14+0F0h], r12
0x18002d6fe  mov     rdx, [r14+0F8h]
0x18002d705  test    rdx, rdx
0x18002d708  jz      short loc_18002D721
0x18002d70a  mov     rcx, [rbp+0]
0x18002d70e  mov     rax, [rcx]
0x18002d711  mov     rax, [rax+48h]
0x18002d715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d71a  mov     [r14+0F8h], r12
0x18002d721  mov     rcx, [rbp+0]
0x18002d725  test    rcx, rcx
0x18002d728  jz      short loc_18002D73A
0x18002d72a  mov     [rbp+0], r12
0x18002d72e  mov     rax, [rcx]
0x18002d731  mov     rax, [rax+10h]
0x18002d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d73a  lea     rcx, [r14+88h]; this
0x18002d741  cmp     [rcx], r12
0x18002d744  jz      short loc_18002D74B
0x18002d746  call    ?UnregisterDeviceEventHandler@Details@PnpApiWrapper@@YAJAEAPEAX@Z; PnpApiWrapper::Details::UnregisterDeviceEventHandler(void * &)
0x18002d74b  lea     rcx, [r14+90h]; this
0x18002d752  cmp     [rcx], r12
0x18002d755  jz      short loc_18002D75C
0x18002d757  call    ?UnregisterDeviceEventHandler@Details@PnpApiWrapper@@YAJAEAPEAX@Z; PnpApiWrapper::Details::UnregisterDeviceEventHandler(void * &)
0x18002d75c  nop
0x18002d75d  mov     rbx, r12
0x18002d760  xchg    rbx, [r14+28h]
0x18002d764  nop
0x18002d765  test    rbx, rbx
0x18002d768  jz      short loc_18002D7CE
0x18002d76a  xor     edx, edx; dwMilliseconds
0x18002d76c  mov     rcx, rbx; hHandle
0x18002d76f  call    cs:__imp_WaitForSingleObject
0x18002d776  nop     dword ptr [rax+rax+00h]
0x18002d77b  test    eax, eax
0x18002d77d  jz      short loc_18002D7BF
0x18002d77f  mov     r8, r14; dwData
0x18002d782  lea     rcx, ?TerminateWorkerThreadApcThunk@GameInputServer@@CAX_K@Z; pfnAPC
0x18002d789  mov     rdx, rbx; hThread
0x18002d78c  call    cs:__imp_QueueUserAPC
0x18002d793  nop     dword ptr [rax+rax+00h]
0x18002d798  mov     edx, 1F4h; dwMilliseconds
0x18002d79d  mov     rcx, rbx; hHandle
0x18002d7a0  call    cs:__imp_WaitForSingleObject
0x18002d7a7  nop     dword ptr [rax+rax+00h]
0x18002d7ac  test    eax, eax
0x18002d7ae  jz      short loc_18002D7BF
0x18002d7b0  mov     rcx, rbx; hThread
0x18002d7b3  call    cs:__imp_SuspendThread
0x18002d7ba  nop     dword ptr [rax+rax+00h]
0x18002d7bf  mov     rcx, rbx; hObject
0x18002d7c2  call    cs:__imp_CloseHandle
0x18002d7c9  nop     dword ptr [rax+rax+00h]
0x18002d7ce  lea     r15, [r14+50h]
0x18002d7d2  mov     rsi, [r15]
0x18002d7d5  cmp     rsi, r15
0x18002d7d8  jz      loc_18002D8AF
0x18002d7de  lea     rcx, [rsi-30h]
0x18002d7e2  mov     rax, rsi
0x18002d7e5  neg     rax
0x18002d7e8  sbb     r12, r12
0x18002d7eb  and     r12, rcx
0x18002d7ee  mov     rcx, r12; this
0x18002d7f1  call    ?StopProcessingInput@GameInputServerDevice@@QEAAXXZ; GameInputServerDevice::StopProcessingInput(void)
0x18002d7f6  lea     rax, [r14+38h]
0x18002d7fa  mov     rdi, [rax]
0x18002d7fd  cmp     rdi, rax
0x18002d800  jz      short loc_18002D872
0x18002d802  lea     rax, [rdi+20h]
0x18002d806  mov     rbx, [rax]
0x18002d809  cmp     rbx, rax
0x18002d80c  jz      short loc_18002D869
0x18002d80e  cmp     [rbx+10h], r12
0x18002d812  jz      short loc_18002D819
0x18002d814  mov     rbx, [rbx]
0x18002d817  jmp     short loc_18002D809
0x18002d819  lea     rcx, [rdi+18h]; SRWLock
0x18002d81d  call    cs:__imp_AcquireSRWLockExclusive
0x18002d824  nop     dword ptr [rax+rax+00h]
0x18002d829  mov     rdx, [rbx]
0x18002d82c  cmp     [rdx+8], rbx
0x18002d830  jnz     loc_18002D8BB
0x18002d836  mov     rax, [rbx+8]
0x18002d83a  cmp     [rax], rbx
0x18002d83d  jnz     short loc_18002D8BB
0x18002d83f  mov     [rax], rdx
0x18002d842  mov     rcx, rbx; this
0x18002d845  mov     [rdx+8], rax
0x18002d849  dec     dword ptr [rdi+30h]
0x18002d84c  call    ??1BufferListEntry@GameInputServer@@QEAA@XZ; GameInputServer::BufferListEntry::~BufferListEntry(void)
0x18002d851  mov     rcx, rbx; P
0x18002d854  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d859  lea     rcx, [rdi+18h]; SRWLock
0x18002d85d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d864  nop     dword ptr [rax+rax+00h]
0x18002d869  mov     rdi, [rdi]
0x18002d86c  lea     rax, [r14+38h]
0x18002d870  jmp     short loc_18002D7FD
0x18002d872  mov     rsi, [rsi]
0x18002d875  jmp     loc_18002D7D5
0x18002d87a  cmp     [rax+8], rcx
0x18002d87e  jnz     short loc_18002D8BB
0x18002d880  mov     [r15], rax
0x18002d883  mov     [rax+8], r15
0x18002d887  cmp     rcx, r15
0x18002d88a  jz      short loc_18002D8C2
0x18002d88c  lea     rax, [rcx-30h]
0x18002d890  neg     rcx
0x18002d893  sbb     rbx, rbx
0x18002d896  and     rbx, rax
0x18002d899  jz      short loc_18002D8AB
0x18002d89b  mov     rcx, rbx; this
0x18002d89e  call    ??1GameInputServerDevice@@QEAA@XZ; GameInputServerDevice::~GameInputServerDevice(void)
0x18002d8a3  mov     rcx, rbx; P
0x18002d8a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d8ab  dec     dword ptr [r15+10h]
0x18002d8af  mov     rcx, [r15]
0x18002d8b2  mov     rax, [rcx]
0x18002d8b5  cmp     [rcx+8], r15
0x18002d8b9  jz      short loc_18002D87A
0x18002d8bb  mov     ecx, 3
0x18002d8c0  int     29h; Win8: RtlFailFast(ecx)
0x18002d8c2  mov     rbx, cs:qword_180069878
0x18002d8c9  xor     r12d, r12d
0x18002d8cc  test    rbx, rbx
0x18002d8cf  jz      short loc_18002D8E1
0x18002d8d1  mov     rcx, rbx; this
0x18002d8d4  call    ??1ControllerWatcher@@QEAA@XZ; ControllerWatcher::~ControllerWatcher(void)
0x18002d8d9  mov     rcx, rbx; P
0x18002d8dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d8e1  mov     cs:qword_180069878, r12
0x18002d8e8  call    Feature_52580392__private_IsEnabledDeviceUsageNoInline
0x18002d8ed  test    eax, eax
0x18002d8ef  jz      short loc_18002D910
0x18002d8f1  mov     rcx, [r14+108h]
0x18002d8f8  test    rcx, rcx
0x18002d8fb  jz      short loc_18002D910
0x18002d8fd  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18002d904  nop     dword ptr [rax+rax+00h]
0x18002d909  mov     [r14+108h], r12
0x18002d910  mov     eax, cs:dword_180069000
0x18002d916  cmp     eax, 4
0x18002d919  jbe     short loc_18002D99A
0x18002d91b  mov     rcx, cs:qword_180069018
0x18002d922  mov     edx, 400h
0x18002d927  mov     rax, cs:qword_180069010
0x18002d92e  test    rdx, rax
0x18002d931  jz      short loc_18002D99A
0x18002d933  mov     rax, rcx
0x18002d936  and     rax, rdx
0x18002d939  cmp     rax, rcx
0x18002d93c  jnz     short loc_18002D99A
0x18002d93e  lea     rax, aGameinputserve_2; "GameInputServer: Destroyed"
0x18002d945  mov     [rsp+78h+arg_0], 7Eh ; '~'
0x18002d950  mov     [rsp+78h+arg_8], rax
0x18002d958  lea     rdx, qword_1800600A8
0x18002d95f  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18002d966  mov     [rsp+78h+arg_10], rax
0x18002d96e  lea     rax, [rsp+78h+arg_8]
0x18002d976  mov     [rsp+78h+var_48], rax
0x18002d97b  lea     rax, [rsp+78h+arg_0]
0x18002d983  mov     [rsp+78h+var_50], rax
0x18002d988  lea     rax, [rsp+78h+arg_10]
0x18002d990  mov     [rsp+78h+var_58], rax
0x18002d995  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002d99a  mov     rcx, [r14+118h]; hObject
0x18002d9a1  test    rcx, rcx
0x18002d9a4  jz      short loc_18002D9B9
0x18002d9a6  call    cs:__imp_CloseHandle
0x18002d9ad  nop     dword ptr [rax+rax+00h]
0x18002d9b2  mov     [r14+118h], r12
0x18002d9b9  mov     rcx, [rbp+0]
0x18002d9bd  test    rcx, rcx
0x18002d9c0  jz      short loc_18002D9D2
0x18002d9c2  mov     [rbp+0], r12
0x18002d9c6  mov     rax, [rcx]
0x18002d9c9  mov     rax, [rax+10h]
0x18002d9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9d2  lea     rcx, [r14+0B0h]; this
0x18002d9d9  call    ??1RouterKeyboardBugFix@@QEAA@XZ; RouterKeyboardBugFix::~RouterKeyboardBugFix(void)
0x18002d9de  lea     rcx, [r14+98h]
0x18002d9e5  call    ??1?$NtList@UWorkItemListEntry@GameInputServer@@@@QEAA@XZ; NtList<GameInputServer::WorkItemListEntry>::~NtList<GameInputServer::WorkItemListEntry>(void)
0x18002d9ea  lea     rcx, [r14+68h]
0x18002d9ee  call    ??1?$NtList@UWorkItemListEntry@GameInputServer@@@@QEAA@XZ; NtList<GameInputServer::WorkItemListEntry>::~NtList<GameInputServer::WorkItemListEntry>(void)
0x18002d9f3  mov     rcx, r15
0x18002d9f6  call    ??1?$NtList@VGameInputServerDevice@@@@QEAA@XZ; NtList<GameInputServerDevice>::~NtList<GameInputServerDevice>(void)
0x18002d9fb  lea     rbx, [r14+38h]
0x18002d9ff  jmp     short loc_18002DA2A
0x18002da01  cmp     [rax+8], rdi
0x18002da05  jnz     loc_18002D8BB
0x18002da0b  mov     [rbx], rax
0x18002da0e  mov     [rax+8], rbx
0x18002da12  cmp     rdi, rbx
0x18002da15  jz      short loc_18002DA3B
0x18002da17  mov     rcx, rdi; this
0x18002da1a  call    ??1ClientListEntry@GameInputServer@@QEAA@XZ; GameInputServer::ClientListEntry::~ClientListEntry(void)
0x18002da1f  mov     rcx, rdi; P
0x18002da22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002da27  dec     dword ptr [rbx+10h]
0x18002da2a  mov     rdi, [rbx]
0x18002da2d  mov     rax, [rdi]
0x18002da30  cmp     [rdi+8], rbx
0x18002da34  jz      short loc_18002DA01
0x18002da36  jmp     loc_18002D8BB
0x18002da3b  mov     rcx, [r14+20h]
0x18002da3f  test    rcx, rcx
0x18002da42  jz      short loc_18002DA54
0x18002da44  mov     rax, [rcx]
0x18002da47  mov     rax, [rax+10h]
0x18002da4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da50  mov     [r14+20h], r12
0x18002da54  mov     rbx, [rsp+78h+arg_18]
0x18002da5c  add     rsp, 40h
0x18002da60  pop     r15
0x18002da62  pop     r14
0x18002da64  pop     r13
0x18002da66  pop     r12
0x18002da68  pop     rdi
0x18002da69  pop     rsi
0x18002da6a  pop     rbp
0x18002da6b  retn
```
