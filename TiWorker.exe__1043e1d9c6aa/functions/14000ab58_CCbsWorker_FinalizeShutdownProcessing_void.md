# CCbsWorker::FinalizeShutdownProcessing(void)

- ea: `0x14000ab58`
- end: `0x14000ac16`
- name: `?FinalizeShutdownProcessing@CCbsWorker@@UEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140009690`

## callees

- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000ab58`
- `0x14000e328`
- `0x140016bd0`
- `0x14002b010`

## string_xrefs

- `0x14000abec`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::FinalizeShutdownProcessing(CCbsWorker *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  _BYTE v5[40]; // [rsp+30h] [rbp-28h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v5, (CCbsWorker *)((char *)this - 64));
  if ( vpCbsSessionClassFactory || (v2 = TiWorkerCoreInitialize(*((_DWORD *)this - 6)), v3 = v2, v2 >= 0) )
  {
    MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v5);
    if ( vpfnCbsCoreFinalizeShutdownProcessing )
    {
      v3 = vpfnCbsCoreFinalizeShutdownProcessing();
    }
    else
    {
      v3 = -2147467263;
      CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CbsCoreFinalizeShutdownProcessing is not implemented.");
    }
  }
  else
  {
    CBSWdsLog(0x4000000u, v2, (size_t *)1, "Failed to initialize CBS class factory.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000u,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::FinalizeShutdownProcessing");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v5);
  return v3;
}

```

## disassembly

```asm
0x14000ab58  push    rbx
0x14000ab5a  sub     rsp, 50h
0x14000ab5e  mov     rbx, rcx
0x14000ab61  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000ab65  lea     rcx, [rsp+58h+var_28]; this
0x14000ab6a  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000ab6f  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpCbsSessionClassFactory
0x14000ab77  jnz     short loc_14000ABA9
0x14000ab79  mov     ecx, [rbx-18h]
0x14000ab7c  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000ab83  call    TiWorkerCoreInitialize
0x14000ab88  mov     ebx, eax
0x14000ab8a  test    eax, eax
0x14000ab8c  jns     short loc_14000ABA9
0x14000ab8e  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000ab95  mov     edx, eax
0x14000ab97  mov     r8d, 1
0x14000ab9d  mov     ecx, 4000000h
0x14000aba2  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000aba7  jmp     short loc_14000ABD6
0x14000aba9  lea     rcx, [rsp+58h+var_28]; this
0x14000abae  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000abb3  mov     rax, cs:?vpfnCbsCoreFinalizeShutdownProcessing@@3P6AJXZEA; long (*vpfnCbsCoreFinalizeShutdownProcessing)(void)
0x14000abba  test    rax, rax
0x14000abbd  jnz     short loc_14000ABCF
0x14000abbf  mov     ebx, 80004001h
0x14000abc4  lea     r9, aCbscorefinaliz; "CbsCoreFinalizeShutdownProcessing is no"...
0x14000abcb  mov     edx, ebx
0x14000abcd  jmp     short loc_14000AB97
0x14000abcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abd4  mov     ebx, eax
0x14000abd6  mov     eax, gs:179Ch
0x14000abde  test    eax, eax
0x14000abe0  jz      short loc_14000AC04
0x14000abe2  lea     rax, aCcbsworkerFina; "CCbsWorker::FinalizeShutdownProcessing"
0x14000abe9  xor     r8d, r8d
0x14000abec  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000abf3  mov     [rsp+58h+var_38], rax
0x14000abf8  xor     edx, edx
0x14000abfa  mov     ecx, 4000000h
0x14000abff  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ac04  lea     rcx, [rsp+58h+var_28]; this
0x14000ac09  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000ac0e  mov     eax, ebx
0x14000ac10  add     rsp, 50h
0x14000ac14  pop     rbx
0x14000ac15  retn
```
