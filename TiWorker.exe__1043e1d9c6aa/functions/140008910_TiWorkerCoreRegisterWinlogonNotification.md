# TiWorkerCoreRegisterWinlogonNotification

- ea: `0x140008910`
- end: `0x140008968`
- name: `TiWorkerCoreRegisterWinlogonNotification`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008910`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008930`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x14000894d`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void TiWorkerCoreRegisterWinlogonNotification()
{
  int v0; // eax

  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 112LL))(vpTrustedInstallerService);
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
0x140008910  sub     rsp, 28h
0x140008914  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000891b  test    rcx, rcx
0x14000891e  jz      short loc_14000894D
0x140008920  mov     rax, [rcx]
0x140008923  mov     rax, [rax+70h]
0x140008927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000892c  test    eax, eax
0x14000892e  jns     short loc_140008963
0x140008930  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008937  mov     r8d, 1
0x14000893d  mov     edx, eax
0x14000893f  mov     ecx, 4000000h
0x140008944  add     rsp, 28h
0x140008948  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000894d  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140008954  xor     r8d, r8d
0x140008957  xor     edx, edx
0x140008959  mov     ecx, 4000000h
0x14000895e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008963  add     rsp, 28h
0x140008967  retn
```
