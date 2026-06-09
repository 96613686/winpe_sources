# TiWorkerCoreRevokeShutdownProcessing

- ea: `0x140008ad0`
- end: `0x140008b28`
- name: `TiWorkerCoreRevokeShutdownProcessing`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008ad0`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008af0`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140008b0d`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreRevokeShutdownProcessing()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 56LL))(vpTrustedInstallerService);
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
0x140008ad0  sub     rsp, 28h
0x140008ad4  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x140008adb  test    rcx, rcx
0x140008ade  jz      short loc_140008B0D
0x140008ae0  mov     rax, [rcx]
0x140008ae3  mov     rax, [rax+38h]
0x140008ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008aec  test    eax, eax
0x140008aee  jns     short loc_140008B23
0x140008af0  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008af7  mov     r8d, 1
0x140008afd  mov     edx, eax
0x140008aff  mov     ecx, 4000000h
0x140008b04  add     rsp, 28h
0x140008b08  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008b0d  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140008b14  xor     r8d, r8d
0x140008b17  xor     edx, edx
0x140008b19  mov     ecx, 4000000h
0x140008b1e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008b23  add     rsp, 28h
0x140008b27  retn
```
