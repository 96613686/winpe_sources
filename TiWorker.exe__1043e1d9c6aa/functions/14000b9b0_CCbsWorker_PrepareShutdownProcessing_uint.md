# CCbsWorker::PrepareShutdownProcessing(uint)

- ea: `0x14000b9b0`
- end: `0x14000ba82`
- name: `?PrepareShutdownProcessing@CCbsWorker@@UEAAJI@Z`
- size: `210`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x1400097e0`

## callees

- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000b9b0`
- `0x14000e328`
- `0x140016bd0`
- `0x14002b010`

## string_xrefs

- `0x14000ba53`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::PrepareShutdownProcessing(CCbsWorker *this, unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _BYTE v7[40]; // [rsp+30h] [rbp-28h] BYREF

  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v7, (CCbsWorker *)((char *)this - 64));
  if ( vpCbsSessionClassFactory || (v4 = TiWorkerCoreInitialize(*((_DWORD *)this - 6)), v5 = v4, v4 >= 0) )
  {
    MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v7);
    if ( vpfnCbsCorePrepareShutdownProcessing )
    {
      v5 = vpfnCbsCorePrepareShutdownProcessing(vpTrustedInstallerService, a2);
    }
    else
    {
      v5 = -2147467263;
      CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CbsCorePrepareShutdownProcessing is not implemented.");
    }
  }
  else
  {
    CBSWdsLog(0x4000000u, v4, (size_t *)1, "Failed to initialize CBS class factory.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000u,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::PrepareShutdownProcessing");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v7);
  return v5;
}

```

## disassembly

```asm
0x14000b9b0  mov     [rsp+arg_0], rbx
0x14000b9b5  push    rdi
0x14000b9b6  sub     rsp, 50h
0x14000b9ba  mov     edi, edx
0x14000b9bc  mov     rbx, rcx
0x14000b9bf  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000b9c3  lea     rcx, [rsp+58h+var_28]; this
0x14000b9c8  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000b9cd  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpCbsSessionClassFactory
0x14000b9d5  jnz     short loc_14000BA07
0x14000b9d7  mov     ecx, [rbx-18h]
0x14000b9da  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000b9e1  call    TiWorkerCoreInitialize
0x14000b9e6  mov     ebx, eax
0x14000b9e8  test    eax, eax
0x14000b9ea  jns     short loc_14000BA07
0x14000b9ec  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000b9f3  mov     edx, eax
0x14000b9f5  mov     r8d, 1
0x14000b9fb  mov     ecx, 4000000h
0x14000ba00  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ba05  jmp     short loc_14000BA3D
0x14000ba07  lea     rcx, [rsp+58h+var_28]; this
0x14000ba0c  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000ba11  mov     rax, cs:?vpfnCbsCorePrepareShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@K@ZEA; long (*vpfnCbsCorePrepareShutdownProcessing)(ITrustedInstallerService *,ulong)
0x14000ba18  test    rax, rax
0x14000ba1b  jnz     short loc_14000BA2D
0x14000ba1d  mov     ebx, 80004001h
0x14000ba22  lea     r9, aCbscoreprepare; "CbsCorePrepareShutdownProcessing is not"...
0x14000ba29  mov     edx, ebx
0x14000ba2b  jmp     short loc_14000B9F5
0x14000ba2d  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000ba34  mov     edx, edi
0x14000ba36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba3b  mov     ebx, eax
0x14000ba3d  mov     eax, gs:179Ch
0x14000ba45  test    eax, eax
0x14000ba47  jz      short loc_14000BA6B
0x14000ba49  lea     rax, aCcbsworkerPrep; "CCbsWorker::PrepareShutdownProcessing"
0x14000ba50  xor     r8d, r8d
0x14000ba53  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000ba5a  mov     [rsp+58h+var_38], rax
0x14000ba5f  xor     edx, edx
0x14000ba61  mov     ecx, 4000000h
0x14000ba66  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000ba6b  lea     rcx, [rsp+58h+var_28]; this
0x14000ba70  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000ba75  mov     eax, ebx
0x14000ba77  mov     rbx, [rsp+58h+arg_0]
0x14000ba7c  add     rsp, 50h
0x14000ba80  pop     rdi
0x14000ba81  retn
```
