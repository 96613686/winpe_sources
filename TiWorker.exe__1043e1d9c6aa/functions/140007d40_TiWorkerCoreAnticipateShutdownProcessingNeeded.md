# TiWorkerCoreAnticipateShutdownProcessingNeeded

- ea: `0x140007d40`
- end: `0x140007d98`
- name: `TiWorkerCoreAnticipateShutdownProcessingNeeded`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140007d40`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140007d60`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140007d7d`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreAnticipateShutdownProcessingNeeded()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 72LL))(vpTrustedInstallerService);
    if ( v0 < 0 )
      CBSWdsLog(0x4000000u, v0, (size_t *)1, "Not able to communicate with TrustedInstaller, crashed?");
  }
  else
  {
    CBSWdsLog(0x4000000u, 0, 0, "Error: Unexpected NULL TrustedIntallerService object.");
  }
}

```

## disassembly

```asm
0x140007d40  sub     rsp, 28h
0x140007d44  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x140007d4b  test    rcx, rcx
0x140007d4e  jz      short loc_140007D7D
0x140007d50  mov     rax, [rcx]
0x140007d53  mov     rax, [rax+48h]
0x140007d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d5c  test    eax, eax
0x140007d5e  jns     short loc_140007D93
0x140007d60  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140007d67  mov     r8d, 1
0x140007d6d  mov     edx, eax
0x140007d6f  mov     ecx, 4000000h
0x140007d74  add     rsp, 28h
0x140007d78  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007d7d  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140007d84  xor     r8d, r8d
0x140007d87  xor     edx, edx
0x140007d89  mov     ecx, 4000000h
0x140007d8e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007d93  add     rsp, 28h
0x140007d97  retn
```
