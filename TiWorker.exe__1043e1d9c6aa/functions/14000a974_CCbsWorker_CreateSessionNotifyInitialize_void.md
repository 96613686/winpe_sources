# CCbsWorker::CreateSessionNotifyInitialize(void)

- ea: `0x14000a974`
- end: `0x14000aa28`
- name: `?CreateSessionNotifyInitialize@CCbsWorker@@UEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400094e0`

## callees

- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000a974`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000a9fe`: `Error: Not reversed from impersonation on func: %s`
- `0x14000a9d6`: `CreateSessionNotifyInitialize is not implemented.`
- `0x14000a9f4`: `CCbsWorker::CreateSessionNotifyInitialize`

## pseudocode

```c
__int64 __fastcall CCbsWorker::CreateSessionNotifyInitialize(CCbsWorker *this)
{
  int v2; // eax
  unsigned int SessionNotifyInitialize; // ebx
  _BYTE v5[40]; // [rsp+30h] [rbp-28h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v5, (CCbsWorker *)((char *)this - 64));
  if ( vpCbsSessionClassFactory
    || (v2 = TiWorkerCoreInitialize(*((_DWORD *)this - 6)), SessionNotifyInitialize = v2, v2 >= 0) )
  {
    if ( vpfnCbsCreateSessionNotifyInitialize )
    {
      SessionNotifyInitialize = vpfnCbsCreateSessionNotifyInitialize();
    }
    else
    {
      SessionNotifyInitialize = -2147467263;
      CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CreateSessionNotifyInitialize is not implemented.");
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
      "CCbsWorker::CreateSessionNotifyInitialize");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v5);
  return SessionNotifyInitialize;
}

```

## disassembly

```asm
0x14000a974  push    rbx
0x14000a976  sub     rsp, 50h
0x14000a97a  mov     rbx, rcx
0x14000a97d  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000a981  lea     rcx, [rsp+58h+var_28]; this
0x14000a986  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000a98b  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpCbsSessionClassFactory
0x14000a993  jnz     short loc_14000A9C5
0x14000a995  mov     ecx, [rbx-18h]
0x14000a998  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000a99f  call    TiWorkerCoreInitialize
0x14000a9a4  mov     ebx, eax
0x14000a9a6  test    eax, eax
0x14000a9a8  jns     short loc_14000A9C5
0x14000a9aa  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000a9b1  mov     edx, eax
0x14000a9b3  mov     r8d, 1
0x14000a9b9  mov     ecx, 4000000h
0x14000a9be  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a9c3  jmp     short loc_14000A9E8
0x14000a9c5  mov     rax, cs:?vpfnCbsCreateSessionNotifyInitialize@@3P6AJXZEA; long (*vpfnCbsCreateSessionNotifyInitialize)(void)
0x14000a9cc  test    rax, rax
0x14000a9cf  jnz     short loc_14000A9E1
0x14000a9d1  mov     ebx, 80004001h
0x14000a9d6  lea     r9, aCreatesessionn_1; "CreateSessionNotifyInitialize is not im"...
0x14000a9dd  mov     edx, ebx
0x14000a9df  jmp     short loc_14000A9B3
0x14000a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9e6  mov     ebx, eax
0x14000a9e8  mov     eax, gs:179Ch
0x14000a9f0  test    eax, eax
0x14000a9f2  jz      short loc_14000AA16
0x14000a9f4  lea     rax, aCcbsworkerCrea_1; "CCbsWorker::CreateSessionNotifyInitiali"...
0x14000a9fb  xor     r8d, r8d
0x14000a9fe  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000aa05  mov     [rsp+58h+var_38], rax
0x14000aa0a  xor     edx, edx
0x14000aa0c  mov     ecx, 4000000h
0x14000aa11  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000aa16  lea     rcx, [rsp+58h+var_28]; this
0x14000aa1b  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000aa20  mov     eax, ebx
0x14000aa22  add     rsp, 50h
0x14000aa26  pop     rbx
0x14000aa27  retn
```
