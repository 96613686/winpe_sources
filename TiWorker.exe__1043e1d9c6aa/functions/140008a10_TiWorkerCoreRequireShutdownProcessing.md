# TiWorkerCoreRequireShutdownProcessing

- ea: `0x140008a10`
- end: `0x140008a68`
- name: `TiWorkerCoreRequireShutdownProcessing`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008a10`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008a30`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140008a4d`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreRequireShutdownProcessing()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 40LL))(vpTrustedInstallerService);
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
0x140008a10  sub     rsp, 28h
0x140008a14  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x140008a1b  test    rcx, rcx
0x140008a1e  jz      short loc_140008A4D
0x140008a20  mov     rax, [rcx]
0x140008a23  mov     rax, [rax+28h]
0x140008a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a2c  test    eax, eax
0x140008a2e  jns     short loc_140008A63
0x140008a30  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008a37  mov     r8d, 1
0x140008a3d  mov     edx, eax
0x140008a3f  mov     ecx, 4000000h
0x140008a44  add     rsp, 28h
0x140008a48  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008a4d  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140008a54  xor     r8d, r8d
0x140008a57  xor     edx, edx
0x140008a59  mov     ecx, 4000000h
0x140008a5e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008a63  add     rsp, 28h
0x140008a67  retn
```
