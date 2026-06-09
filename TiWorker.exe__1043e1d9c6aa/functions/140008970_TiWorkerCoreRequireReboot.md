# TiWorkerCoreRequireReboot

- ea: `0x140008970`
- end: `0x1400089c8`
- name: `TiWorkerCoreRequireReboot`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008970`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008990`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x1400089ad`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreRequireReboot()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 24LL))(vpTrustedInstallerService);
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
0x140008970  sub     rsp, 28h
0x140008974  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000897b  test    rcx, rcx
0x14000897e  jz      short loc_1400089AD
0x140008980  mov     rax, [rcx]
0x140008983  mov     rax, [rax+18h]
0x140008987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000898c  test    eax, eax
0x14000898e  jns     short loc_1400089C3
0x140008990  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008997  mov     r8d, 1
0x14000899d  mov     edx, eax
0x14000899f  mov     ecx, 4000000h
0x1400089a4  add     rsp, 28h
0x1400089a8  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400089ad  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x1400089b4  xor     r8d, r8d
0x1400089b7  xor     edx, edx
0x1400089b9  mov     ecx, 4000000h
0x1400089be  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400089c3  add     rsp, 28h
0x1400089c7  retn
```
