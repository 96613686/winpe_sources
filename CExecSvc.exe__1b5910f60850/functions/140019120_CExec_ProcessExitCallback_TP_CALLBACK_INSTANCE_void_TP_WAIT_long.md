# CExec::ProcessExitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140019120`
- end: `0x140019188`
- name: `?ProcessExitCallback@CExec@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `104`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140019120`
- `0x14001a9cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140019134`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140019134`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001916b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001916b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001913a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001913a`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14001917c`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14001917c`

## pseudocode

```c
void __fastcall CExec::ProcessExitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  char *v4; // rbx
  __int64 v5; // rcx

  if ( Context )
  {
    v4 = Context;
    AcquireSRWLockExclusive(&CExec::g_ContainerProcessesLock);
    dword_14003A4C8 = GetCurrentThreadId();
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CExec::ProcessTracker>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>,0>>::erase(
      v5,
      v4 + 32);
    dword_14003A4C8 = 0;
    LOBYTE(v4) = qword_14003A4B8 == 0;
    ReleaseSRWLockExclusive(&CExec::g_ContainerProcessesLock);
    if ( (_BYTE)v4 )
      WakeConditionVariable(&CExec::g_ContainerProcessesEmptySignal);
  }
}

```

## disassembly

```asm
0x140019120  test    rdx, rdx
0x140019123  jz      short locret_140019187
0x140019125  push    rbx
0x140019126  sub     rsp, 20h
0x14001912a  lea     rcx, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; SRWLock
0x140019131  mov     rbx, rdx
0x140019134  call    cs:__imp_AcquireSRWLockExclusive
0x14001913a  call    cs:__imp_GetCurrentThreadId
0x140019140  lea     rdx, [rbx+20h]
0x140019144  mov     cs:dword_14003A4C8, eax
0x14001914a  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@UProcessTracker@CExec@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CExec::ProcessTracker>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>,0>>::erase(ulong const &)
0x14001914f  cmp     cs:qword_14003A4B8, 0
0x140019157  lea     rcx, ?g_ContainerProcessesLock@CExec@@3VVmSlimReaderWriterLock@Vml@@A; SRWLock
0x14001915e  mov     cs:dword_14003A4C8, 0
0x140019168  setz    bl
0x14001916b  call    cs:__imp_ReleaseSRWLockExclusive
0x140019171  test    bl, bl
0x140019173  jz      short loc_140019182
0x140019175  lea     rcx, ?g_ContainerProcessesEmptySignal@CExec@@3VVmConditionVariable@Vml@@A; ConditionVariable
0x14001917c  call    cs:__imp_WakeConditionVariable
0x140019182  add     rsp, 20h
0x140019186  pop     rbx
0x140019187  retn
```
