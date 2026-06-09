# CCbsWorker::ShutdownProcessing(void)

- ea: `0x14000c6bc`
- end: `0x14000c7be`
- name: `?ShutdownProcessing@CCbsWorker@@UEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x140009970`

## callees

- `0x140002310`
- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000c6bc`
- `0x14000e328`
- `0x140016bd0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x14000c74d`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x14000c74d`

## string_xrefs

- `0x14000c787`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::ShutdownProcessing(CCbsWorker *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  _BYTE v5[24]; // [rsp+30h] [rbp-38h] BYREF
  int v6; // [rsp+48h] [rbp-20h] BYREF

  v6 = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v5, (CCbsWorker *)((char *)this - 64));
  if ( vpCbsSessionClassFactory || (v2 = TiWorkerCoreInitialize(*((_DWORD *)this - 6)), v3 = v2, v2 >= 0) )
  {
    MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v5);
    if ( vpfnCbsCoreShutdownProcessing )
    {
      GetOsSafeBootMode(&v6);
      v3 = ((__int64 (__fastcall *)(struct ITrustedInstallerService *, bool))vpfnCbsCoreShutdownProcessing)(
             vpTrustedInstallerService,
             v6 != 0);
    }
    else
    {
      v3 = -2147467263;
      CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CbsCoreShutdownProcessing is not implemented.");
    }
  }
  else
  {
    CBSWdsLog(0x4000000u, v2, (size_t *)1, "Failed to initialize CBS class factory.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000u, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::ShutdownProcessing");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v5);
  return v3;
}

```

## disassembly

```asm
0x14000c6bc  push    rbx
0x14000c6be  sub     rsp, 60h
0x14000c6c2  mov     rax, cs:__security_cookie
0x14000c6c9  xor     rax, rsp
0x14000c6cc  mov     [rsp+68h+var_18], rax
0x14000c6d1  mov     rbx, rcx
0x14000c6d4  mov     [rsp+68h+var_20], 0
0x14000c6dc  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000c6e0  lea     rcx, [rsp+68h+var_38]; this
0x14000c6e5  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000c6ea  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpCbsSessionClassFactory
0x14000c6f2  jnz     short loc_14000C724
0x14000c6f4  mov     ecx, [rbx-18h]
0x14000c6f7  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000c6fe  call    TiWorkerCoreInitialize
0x14000c703  mov     ebx, eax
0x14000c705  test    eax, eax
0x14000c707  jns     short loc_14000C724
0x14000c709  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000c710  mov     edx, eax
0x14000c712  mov     r8d, 1
0x14000c718  mov     ecx, 4000000h
0x14000c71d  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c722  jmp     short loc_14000C771
0x14000c724  lea     rcx, [rsp+68h+var_38]; this
0x14000c729  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x14000c72e  cmp     cs:?vpfnCbsCoreShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@H@ZEA, 0; long (*vpfnCbsCoreShutdownProcessing)(ITrustedInstallerService *,int)
0x14000c736  jnz     short loc_14000C748
0x14000c738  mov     ebx, 80004001h
0x14000c73d  lea     r9, aCbscoreshutdow_0; "CbsCoreShutdownProcessing is not implem"...
0x14000c744  mov     edx, ebx
0x14000c746  jmp     short loc_14000C712
0x14000c748  lea     rcx, [rsp+68h+var_20]
0x14000c74d  call    cs:__imp_GetOsSafeBootMode
0x14000c753  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000c75a  xor     edx, edx
0x14000c75c  cmp     [rsp+68h+var_20], edx
0x14000c760  mov     rax, cs:?vpfnCbsCoreShutdownProcessing@@3P6AJPEAUITrustedInstallerService@@H@ZEA; long (*vpfnCbsCoreShutdownProcessing)(ITrustedInstallerService *,int)
0x14000c767  setnbe  dl
0x14000c76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c76f  mov     ebx, eax
0x14000c771  mov     eax, gs:179Ch
0x14000c779  test    eax, eax
0x14000c77b  jz      short loc_14000C79F
0x14000c77d  lea     rax, aCcbsworkerShut; "CCbsWorker::ShutdownProcessing"
0x14000c784  xor     r8d, r8d
0x14000c787  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000c78e  mov     [rsp+68h+var_48], rax
0x14000c793  xor     edx, edx
0x14000c795  mov     ecx, 4000000h
0x14000c79a  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c79f  lea     rcx, [rsp+68h+var_38]; this
0x14000c7a4  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000c7a9  mov     eax, ebx
0x14000c7ab  mov     rcx, [rsp+68h+var_18]
0x14000c7b0  xor     rcx, rsp; StackCookie
0x14000c7b3  call    __security_check_cookie
0x14000c7b8  add     rsp, 60h
0x14000c7bc  pop     rbx
0x14000c7bd  retn
```
