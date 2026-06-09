# CExec::TrackProcess(ulong,std::shared_ptr<CExec::ProcessTracker> &&)

- ea: `0x14001a43c`
- end: `0x14001a637`
- name: `?TrackProcess@CExec@@YAXK$$QEAV?$shared_ptr@UProcessTracker@CExec@@@std@@@Z`
- size: `507`
- prototype: `void __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002334`
- `0x14000e3c0`
- `0x14000e828`
- `0x14000e86c`
- `0x140015820`
- `0x14001a43c`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a4af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001a4af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a604`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a47b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a47b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a48e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a48e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a4b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a4b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001a466`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14001a466`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001a5f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001a5f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001a486`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14001a486`

## string_xrefs

- `0x14001a625`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
void __fastcall CExec::TrackProcess(unsigned int a1, __int64 a2)
{
  PVOID v4; // rsi
  const char *v5; // r9
  PTP_WAIT ThreadpoolWait; // r12
  struct _TP_WAIT *v7; // r15
  DWORD LastError; // ebx
  void *v9; // rsi
  _QWORD *v10; // rax
  void *inserted; // r8
  _DWORD *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  __int128 v16; // [rsp+20h] [rbp-48h]
  _QWORD v17[3]; // [rsp+38h] [rbp-30h] BYREF
  __int128 v18; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v4 = *(PVOID *)a2;
  ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)CExec::ProcessExitCallback, *(PVOID *)a2, 0);
  v7 = (struct _TP_WAIT *)*((_QWORD *)v4 + 5);
  if ( v7 )
  {
    LastError = GetLastError();
    CloseThreadpoolWait(v7);
    SetLastError(LastError);
  }
  *((_QWORD *)v4 + 5) = ThreadpoolWait;
  if ( !*(_QWORD *)(*(_QWORD *)a2 + 40LL) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11C,
      (int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v5);
  AcquireSRWLockExclusive(&CExec::g_ContainerProcessesLock);
  dword_14003A4C8 = GetCurrentThreadId();
  *(_QWORD *)&v18 = &CExec::g_ContainerProcessesLock;
  BYTE8(v18) = 1;
  v9 = CExec::g_ContainerProcesses;
  v10 = (_QWORD *)*((_QWORD *)CExec::g_ContainerProcesses + 1);
  v16 = (unsigned __int64)v10;
  inserted = CExec::g_ContainerProcesses;
  while ( !*((_BYTE *)v10 + 25) )
  {
    *(_QWORD *)&v16 = v10;
    if ( *((_DWORD *)v10 + 8) >= a1 )
    {
      DWORD2(v16) = 1;
      inserted = v10;
    }
    else
    {
      DWORD2(v16) = 0;
      v10 += 2;
    }
    v10 = (_QWORD *)*v10;
  }
  if ( *((_BYTE *)inserted + 25) || a1 < *((_DWORD *)inserted + 8) )
  {
    if ( qword_14003A4B8 == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v17[0] = &CExec::g_ContainerProcesses;
    v12 = operator new(0x38u);
    v12[8] = a1;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *(_QWORD *)v12 = v9;
    *((_QWORD *)v12 + 1) = v9;
    *((_QWORD *)v12 + 2) = v9;
    *((_WORD *)v12 + 12) = 0;
    v17[1] = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>((__int64)v17);
    v18 = v16;
    inserted = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(
                         &CExec::g_ContainerProcesses,
                         (__int64)&v18,
                         (__int64)v12);
  }
  v13 = *(_QWORD *)(a2 + 8);
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  v14 = *(_QWORD *)(a2 + 8);
  *((_QWORD *)inserted + 5) = *(_QWORD *)a2;
  v15 = (volatile signed __int32 *)*((_QWORD *)inserted + 6);
  *((_QWORD *)inserted + 6) = v14;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a2 + 40LL), **(HANDLE **)a2, 0);
  dword_14003A4C8 = 0;
  ReleaseSRWLockExclusive(&CExec::g_ContainerProcessesLock);
}

```

## disassembly

```asm
0x14001a43c  push    rbp
0x14001a43e  push    rbx
0x14001a43f  push    rsi
0x14001a440  push    rdi
0x14001a441  push    r12
0x14001a443  push    r13
0x14001a445  push    r14
0x14001a447  push    r15
0x14001a449  mov     rbp, rsp
0x14001a44c  sub     rsp, 68h
0x14001a450  mov     rdi, rdx
0x14001a453  mov     r14d, ecx
0x14001a456  mov     rsi, [rdx]
0x14001a459  xor     r8d, r8d; pcbe
0x14001a45c  mov     rdx, rsi; pv
0x14001a45f  lea     rcx, ?ProcessExitCallback@CExec@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14001a466  call    cs:__imp_CreateThreadpoolWait
0x14001a46c  mov     r12, rax
0x14001a46f  mov     r15, [rsi+28h]
0x14001a473  xor     r13d, r13d
0x14001a476  test    r15, r15
0x14001a479  jz      short loc_14001A494
0x14001a47b  call    cs:__imp_GetLastError
0x14001a481  mov     ebx, eax
0x14001a483  mov     rcx, r15; pwa
0x14001a486  call    cs:__imp_CloseThreadpoolWait
0x14001a48c  mov     ecx, ebx; dwErrCode
0x14001a48e  call    cs:__imp_SetLastError
0x14001a494  mov     [rsi+28h], r12
0x14001a498  mov     rax, [rdi]
0x14001a49b  cmp     [rax+28h], r13
0x14001a49f  jz      loc_14001A621
0x14001a4a5  lea     r12, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; Vml::VmSlimReaderWriterLock CExec::g_ContainerProcessesLock
0x14001a4ac  mov     rcx, r12; SRWLock
0x14001a4af  call    cs:__imp_AcquireSRWLockExclusive
0x14001a4b5  call    cs:__imp_GetCurrentThreadId
0x14001a4bb  mov     cs:dword_14003A4C8, eax
0x14001a4c1  mov     qword ptr [rbp+var_18], r12
0x14001a4c5  mov     byte ptr [rbp+var_18+8], 1
0x14001a4c9  mov     rsi, cs:?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x14001a4d0  mov     rax, [rsi+8]
0x14001a4d4  mov     qword ptr [rbp+var_48], rax
0x14001a4d8  mov     qword ptr [rbp+var_48+8], r13
0x14001a4dc  mov     r8, rsi
0x14001a4df  jmp     short loc_14001A502
0x14001a4e1  mov     qword ptr [rbp+var_48], rax
0x14001a4e5  cmp     [rax+20h], r14d
0x14001a4e9  jnb     short loc_14001A4F5
0x14001a4eb  mov     dword ptr [rbp+var_48+8], r13d
0x14001a4ef  add     rax, 10h
0x14001a4f3  jmp     short loc_14001A4FF
0x14001a4f5  mov     dword ptr [rbp+var_48+8], 1
0x14001a4fc  mov     r8, rax
0x14001a4ff  mov     rax, [rax]
0x14001a502  cmp     [rax+19h], r13b
0x14001a506  jz      short loc_14001A4E1
0x14001a508  cmp     [r8+19h], r13b
0x14001a50c  jnz     short loc_14001A514
0x14001a50e  cmp     r14d, [r8+20h]
0x14001a512  jnb     short loc_14001A58B
0x14001a514  mov     rax, 492492492492492h
0x14001a51e  cmp     cs:qword_14003A4B8, rax
0x14001a525  jz      loc_14001A61B
0x14001a52b  lea     r15, ?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x14001a532  mov     [rbp+var_30], r15
0x14001a536  mov     [rbp+var_28], r13
0x14001a53a  mov     ecx, 38h ; '8'; Size
0x14001a53f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a544  mov     rbx, rax
0x14001a547  mov     [rax+20h], r14d
0x14001a54b  mov     [rax+28h], r13
0x14001a54f  mov     [rax+30h], r13
0x14001a553  mov     [rax], rsi
0x14001a556  mov     [rax+8], rsi
0x14001a55a  mov     [rax+10h], rsi
0x14001a55e  mov     [rax+18h], r13w
0x14001a563  mov     [rbp+var_28], r13
0x14001a567  lea     rcx, [rbp+var_30]
0x14001a56b  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(void)
0x14001a570  movups  xmm0, [rbp+var_48]
0x14001a574  movdqu  [rbp+var_18], xmm0
0x14001a579  mov     r8, rbx
0x14001a57c  lea     rdx, [rbp+var_18]
0x14001a580  mov     rcx, r15
0x14001a583  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> * const)
0x14001a588  mov     r8, rax
0x14001a58b  mov     rax, [rdi+8]
0x14001a58f  test    rax, rax
0x14001a592  jz      short loc_14001A598
0x14001a594  lock inc dword ptr [rax+8]
0x14001a598  mov     rdx, [rdi+8]
0x14001a59c  mov     rcx, [rdi]
0x14001a59f  mov     [r8+28h], rcx
0x14001a5a3  mov     rbx, [r8+30h]
0x14001a5a7  mov     [r8+30h], rdx
0x14001a5ab  test    rbx, rbx
0x14001a5ae  jz      short loc_14001A5E6
0x14001a5b0  or      esi, 0FFFFFFFFh
0x14001a5b3  mov     eax, esi
0x14001a5b5  lock xadd [rbx+8], eax
0x14001a5ba  add     eax, esi
0x14001a5bc  jnz     short loc_14001A5E6
0x14001a5be  mov     rax, [rbx]
0x14001a5c1  mov     rcx, rbx
0x14001a5c4  mov     rax, [rax]
0x14001a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5cc  mov     eax, esi
0x14001a5ce  lock xadd [rbx+0Ch], eax
0x14001a5d3  add     eax, esi
0x14001a5d5  jnz     short loc_14001A5E6
0x14001a5d7  mov     rax, [rbx]
0x14001a5da  mov     rcx, rbx
0x14001a5dd  mov     rax, [rax+8]
0x14001a5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5e6  mov     rcx, [rdi]
0x14001a5e9  xor     r8d, r8d; pftTimeout
0x14001a5ec  mov     rdx, [rcx]; h
0x14001a5ef  mov     rcx, [rcx+28h]; pwa
0x14001a5f3  call    cs:__imp_SetThreadpoolWait
0x14001a5f9  nop
0x14001a5fa  mov     cs:dword_14003A4C8, r13d
0x14001a601  mov     rcx, r12; SRWLock
0x14001a604  call    cs:__imp_ReleaseSRWLockExclusive
0x14001a60a  add     rsp, 68h
0x14001a60e  pop     r15
0x14001a610  pop     r14
0x14001a612  pop     r13
0x14001a614  pop     r12
0x14001a616  pop     rdi
0x14001a617  pop     rsi
0x14001a618  pop     rbx
0x14001a619  pop     rbp
0x14001a61a  retn
0x14001a61b  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x14001a621  mov     rcx, [rbp+40h]; this
0x14001a625  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001a62c  mov     edx, 11Ch; void *
0x14001a631  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
