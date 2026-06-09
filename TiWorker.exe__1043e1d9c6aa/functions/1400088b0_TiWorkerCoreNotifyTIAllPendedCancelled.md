# TiWorkerCoreNotifyTIAllPendedCancelled

- ea: `0x1400088b0`
- end: `0x140008908`
- name: `TiWorkerCoreNotifyTIAllPendedCancelled`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400088b0`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x1400088d0`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x1400088ed`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreNotifyTIAllPendedCancelled()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 64LL))(vpTrustedInstallerService);
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
0x1400088b0  sub     rsp, 28h
0x1400088b4  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x1400088bb  test    rcx, rcx
0x1400088be  jz      short loc_1400088ED
0x1400088c0  mov     rax, [rcx]
0x1400088c3  mov     rax, [rax+40h]
0x1400088c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088cc  test    eax, eax
0x1400088ce  jns     short loc_140008903
0x1400088d0  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x1400088d7  mov     r8d, 1
0x1400088dd  mov     edx, eax
0x1400088df  mov     ecx, 4000000h
0x1400088e4  add     rsp, 28h
0x1400088e8  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400088ed  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x1400088f4  xor     r8d, r8d
0x1400088f7  xor     edx, edx
0x1400088f9  mov     ecx, 4000000h
0x1400088fe  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008903  add     rsp, 28h
0x140008907  retn
```
