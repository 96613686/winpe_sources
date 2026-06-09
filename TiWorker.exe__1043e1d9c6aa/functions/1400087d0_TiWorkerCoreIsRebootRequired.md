# TiWorkerCoreIsRebootRequired

- ea: `0x1400087d0`
- end: `0x140008853`
- name: `TiWorkerCoreIsRebootRequired`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140002310`
- `0x1400087d0`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000880c`: `Not able to communicate with TrustedInstaller, crashed?`
- `0x140008827`: `Error: Unexpected NULL TrustedIntallerService object.`

## pseudocode

```c
__int64 TiWorkerCoreIsRebootRequired()
{
  int v0; // eax
  unsigned int v2; // [rsp+20h] [rbp-18h] BYREF

  v2 = 0;
  if ( vpTrustedInstallerService )
  {
    v0 = (*(__int64 (__fastcall **)(struct ITrustedInstallerService *, unsigned int *))(*(_QWORD *)vpTrustedInstallerService
                                                                                      + 32LL))(
           vpTrustedInstallerService,
           &v2);
    if ( v0 < 0 )
      CBSWdsLog(0x4000000u, v0, (size_t *)1, "Not able to communicate with TrustedInstaller, crashed?");
  }
  else
  {
    CBSWdsLog(0x4000000u, 0, 0, "Error: Unexpected NULL TrustedIntallerService object.");
  }
  return v2;
}

```

## disassembly

```asm
0x1400087d0  sub     rsp, 38h
0x1400087d4  mov     rax, cs:__security_cookie
0x1400087db  xor     rax, rsp
0x1400087de  mov     [rsp+38h+var_10], rax
0x1400087e3  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x1400087ea  mov     [rsp+38h+var_18], 0
0x1400087f2  test    rcx, rcx
0x1400087f5  jz      short loc_140008827
0x1400087f7  mov     rax, [rcx]
0x1400087fa  lea     rdx, [rsp+38h+var_18]
0x1400087ff  mov     rax, [rax+20h]
0x140008803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008808  test    eax, eax
0x14000880a  jns     short loc_14000883D
0x14000880c  lea     r9, aNotAbleToCommu; "Not able to communicate with TrustedIns"...
0x140008813  mov     r8d, 1
0x140008819  mov     edx, eax
0x14000881b  mov     ecx, 4000000h
0x140008820  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140008825  jmp     short loc_14000883D
0x140008827  lea     r9, aErrorUnexpecte_1; "Error: Unexpected NULL TrustedIntallerS"...
0x14000882e  xor     r8d, r8d
0x140008831  xor     edx, edx
0x140008833  mov     ecx, 4000000h
0x140008838  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000883d  mov     eax, [rsp+38h+var_18]
0x140008841  mov     rcx, [rsp+38h+var_10]
0x140008846  xor     rcx, rsp; StackCookie
0x140008849  call    __security_check_cookie
0x14000884e  add     rsp, 38h
0x140008852  retn
```
