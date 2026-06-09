# TiWorkerCoreUnregisterWinlogonNotification

- ea: `0x140008c10`
- end: `0x140008c6a`
- name: `TiWorkerCoreUnregisterWinlogonNotification`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140008c10`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x140008c32`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140008c4f`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
void __fastcall TiWorkerCoreUnregisterWinlogonNotification(unsigned int a1)
{
  int v1; // eax

  if ( vpTrustedInstallerService )
  {
    v1 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *, _QWORD))(*(_QWORD *)vpTrustedInstallerService
                                                                              + 120LL))(
           vpTrustedInstallerService,
           a1);
    if ( v1 < 0 )
      CBSWdsLog(0x4000000u, v1, (size_t *)1, "Not able to communicate with TrustedInstaller, crashed?");
  }
  else
  {
    CBSWdsLog(0x4000000u, 0, 0, "Error: Unexpected NULL TrustedIntallerService object.");
  }
}

```

## disassembly

```asm
0x140008c10  sub     rsp, 28h
0x140008c14  mov     edx, ecx
0x140008c16  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x140008c1d  test    rcx, rcx
0x140008c20  jz      short loc_140008C4F
0x140008c22  mov     rax, [rcx]
0x140008c25  mov     rax, [rax+78h]
0x140008c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c2e  test    eax, eax
0x140008c30  jns     short loc_140008C65
0x140008c32  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008c39  mov     r8d, 1
0x140008c3f  mov     edx, eax
0x140008c41  mov     ecx, 4000000h
0x140008c46  add     rsp, 28h
0x140008c4a  jmp     ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008c4f  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x140008c56  xor     r8d, r8d
0x140008c59  xor     edx, edx
0x140008c5b  mov     ecx, 4000000h
0x140008c60  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008c65  add     rsp, 28h
0x140008c69  retn
```
