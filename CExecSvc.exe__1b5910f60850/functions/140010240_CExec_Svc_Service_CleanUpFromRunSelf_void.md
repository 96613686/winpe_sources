# CExec::Svc::Service::CleanUpFromRunSelf(void)

- ea: `0x140010240`
- end: `0x1400103d8`
- name: `?CleanUpFromRunSelf@Service@Svc@CExec@@QEAAXXZ`
- size: `408`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1400138a4`
- `0x140022bbe`

## callees

- `0x140002334`
- `0x1400026b8`
- `0x14000e3a4`
- `0x140010240`
- `0x140015274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010259`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010259`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400102b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400102b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400102fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400102fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400102ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400102ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400103b7`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1400103b7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001031d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001031d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001032c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001032c`
- `RPCRT4!RpcServerUnregisterIf` at `0x140010278`
- `RPCRT4!RpcServerUnregisterIf` at `0x140010278`

## pseudocode

```c
void __fastcall CExec::Svc::Service::CleanUpFromRunSelf(HANDLE *this)
{
  __int64 v1; // r8
  const char *v2; // r9
  _QWORD *v3; // rax
  void *v4; // rdx
  __int64 v5; // rdx
  __int64 *v6; // rbx
  __int64 v7; // rdi
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v11; // [rsp+20h] [rbp-10h] BYREF
  __int64 v12; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]

  if ( !ResetEvent(this[30]) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v1, v2);
  RpcServerUnregisterIf(qword_140025E80, 0, 1u);
  v12 = 0;
  v3 = operator new(0x38u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v11 = v3;
  AcquireSRWLockExclusive(&CExec::g_ContainerProcessesLock);
  GetCurrentThreadId();
  v4 = v11;
  v11 = CExec::g_ContainerProcesses;
  CExec::g_ContainerProcesses = v4;
  v5 = v12;
  v12 = qword_14003A4B8;
  qword_14003A4B8 = v5;
  dword_14003A4C8 = 0;
  ReleaseSRWLockExclusive(&CExec::g_ContainerProcessesLock);
  v6 = *(__int64 **)v11;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v7 = v6[5];
    SetThreadpoolWait(*(PTP_WAIT *)(v7 + 40), 0, 0);
    WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(v7 + 40), 1);
    v8 = (__int64 **)v6[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v6 = j;
    }
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(
    &v11,
    &v11,
    *((_QWORD *)v11 + 1));
  operator delete(v11);
  if ( g_VmlEtwTrace )
    EventWrite(*((_QWORD *)g_VmlEtwTrace + 2), &MSCEXEC_SERVICE_STOPPED, 0, 0);
}

```

## disassembly

```asm
0x140010240  mov     [rsp-8+arg_8], rbx
0x140010245  mov     [rsp-8+arg_10], rdi
0x14001024a  push    rbp
0x14001024b  mov     rbp, rsp
0x14001024e  sub     rsp, 30h
0x140010252  mov     rcx, [rcx+0F0h]; hEvent
0x140010259  call    cs:__imp_ResetEvent
0x14001025f  mov     rcx, [rbp+8]; this
0x140010263  test    eax, eax
0x140010265  jz      loc_1400103CD
0x14001026b  xor     edx, edx; MgrTypeUuid
0x14001026d  lea     rcx, qword_140025E80; IfSpec
0x140010274  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x140010278  call    cs:__imp_RpcServerUnregisterIf
0x14001027e  mov     ecx, 38h ; '8'; Size
0x140010283  mov     [rbp+var_10], 0
0x14001028b  mov     [rbp+var_8], 0
0x140010293  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010298  lea     rcx, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; SRWLock
0x14001029f  mov     [rax], rax
0x1400102a2  mov     [rax+8], rax
0x1400102a6  mov     [rax+10h], rax
0x1400102aa  mov     word ptr [rax+18h], 101h
0x1400102b0  mov     [rbp+var_10], rax
0x1400102b4  call    cs:__imp_AcquireSRWLockExclusive
0x1400102ba  call    cs:__imp_GetCurrentThreadId
0x1400102c0  mov     rdx, [rbp+var_10]
0x1400102c4  lea     rcx, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; SRWLock
0x1400102cb  mov     rax, cs:?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x1400102d2  mov     [rbp+var_10], rax
0x1400102d6  mov     rax, cs:qword_14003A4B8
0x1400102dd  mov     cs:?g_ContainerProcesses@CExec@@3V?$map@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@@std@@A, rdx; std::map<ulong,std::shared_ptr<CExec::ProcessTracker>> CExec::g_ContainerProcesses
0x1400102e4  mov     rdx, [rbp+var_8]
0x1400102e8  mov     [rbp+var_8], rax
0x1400102ec  mov     cs:qword_14003A4B8, rdx
0x1400102f3  mov     cs:dword_14003A4C8, 0
0x1400102fd  call    cs:__imp_ReleaseSRWLockExclusive
0x140010303  mov     rbx, [rbp+var_10]
0x140010307  mov     rbx, [rbx]
0x14001030a  cmp     byte ptr [rbx+19h], 0
0x14001030e  jnz     short loc_140010377
0x140010310  mov     rdi, [rbx+28h]
0x140010314  xor     r8d, r8d; pftTimeout
0x140010317  xor     edx, edx; h
0x140010319  mov     rcx, [rdi+28h]; pwa
0x14001031d  call    cs:__imp_SetThreadpoolWait
0x140010323  mov     rcx, [rdi+28h]; pwa
0x140010327  mov     edx, 1; fCancelPendingCallbacks
0x14001032c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140010332  mov     rcx, [rbx+10h]
0x140010336  cmp     byte ptr [rcx+19h], 0
0x14001033a  jz      short loc_14001035A
0x14001033c  mov     rax, [rbx+8]
0x140010340  jmp     short loc_14001034F
0x140010342  cmp     rbx, [rax+10h]
0x140010346  jnz     short loc_140010355
0x140010348  mov     rbx, rax
0x14001034b  mov     rax, [rax+8]
0x14001034f  cmp     byte ptr [rax+19h], 0
0x140010353  jz      short loc_140010342
0x140010355  mov     rbx, rax
0x140010358  jmp     short loc_14001030A
0x14001035a  mov     rbx, rcx
0x14001035d  mov     rcx, [rcx]
0x140010360  cmp     byte ptr [rcx+19h], 0
0x140010364  jnz     short loc_14001030A
0x140010366  mov     rax, [rcx]
0x140010369  mov     rbx, rcx
0x14001036c  mov     rcx, rax
0x14001036f  cmp     byte ptr [rax+19h], 0
0x140010373  jz      short loc_140010366
0x140010375  jmp     short loc_14001030A
0x140010377  mov     r8, [rbp+var_10]
0x14001037b  lea     rdx, [rbp+var_10]
0x14001037f  lea     rcx, [rbp+var_10]
0x140010383  mov     r8, [r8+8]
0x140010387  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> *)
0x14001038c  mov     rcx, [rbp+var_10]; void *
0x140010390  mov     edx, 38h ; '8'; unsigned __int64
0x140010395  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001039a  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x1400103a1  test    rcx, rcx
0x1400103a4  jz      short loc_1400103BD
0x1400103a6  mov     rcx, [rcx+10h]; RegHandle
0x1400103aa  lea     rdx, MSCEXEC_SERVICE_STOPPED; EventDescriptor
0x1400103b1  xor     r9d, r9d; UserData
0x1400103b4  xor     r8d, r8d; UserDataCount
0x1400103b7  call    cs:__imp_EventWrite
0x1400103bd  mov     rbx, [rsp+30h+arg_8]
0x1400103c2  mov     rdi, [rsp+30h+arg_10]
0x1400103c7  add     rsp, 30h
0x1400103cb  pop     rbp
0x1400103cc  retn
0x1400103cd  mov     edx, 0A06h; void *
0x1400103d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
