# TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported

- ea: `0x140008a70`
- end: `0x140008ac8`
- name: `TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008a70`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008a90`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140008aad`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreRequireShutdownProcessingWithRevokeUnsupported()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 48LL))(vpTrustedInstallerService);
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
0x140008a70  sub     rsp, 28h
0x140008a74  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x140008a7b  test    rcx, rcx
0x140008a7e  jz      short loc_140008AAD
0x140008a80  mov     rax, [rcx]
0x140008a83  mov     rax, [rax+30h]
0x140008a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a8c  test    eax, eax
0x140008a8e  jns     short loc_140008AC3
0x140008a90  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008a97  mov     r8d, 1
0x140008a9d  mov     edx, eax
0x140008a9f  mov     ecx, 4000000h
0x140008aa4  add     rsp, 28h
0x140008aa8  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008aad  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140008ab4  xor     r8d, r8d
0x140008ab7  xor     edx, edx
0x140008ab9  mov     ecx, 4000000h
0x140008abe  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008ac3  add     rsp, 28h
0x140008ac7  retn
```
