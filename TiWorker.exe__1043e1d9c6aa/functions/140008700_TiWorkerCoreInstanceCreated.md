# TiWorkerCoreInstanceCreated

- ea: `0x140008700`
- end: `0x140008721`
- name: `TiWorkerCoreInstanceCreated`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x140008730`
- `0x140009760`

## callees

- `0x140008700`
- `0x14002b010`

## pseudocode

```c
__int64 TiWorkerCoreInstanceCreated()
{
  __int64 result; // rax

  if ( vpTrustedInstallerService )
    return (*(__int64 (__fastcall **)(struct ITrustedInstallerService *))(*(_QWORD *)vpTrustedInstallerService + 96LL))(vpTrustedInstallerService);
  return result;
}

```

## disassembly

```asm
0x140008700  sub     rsp, 28h
0x140008704  mov     rcx, cs:?vpTrustedInstallerService@@3PEAUITrustedInstallerService@@EA; ITrustedInstallerService * vpTrustedInstallerService
0x14000870b  test    rcx, rcx
0x14000870e  jz      short loc_14000871C
0x140008710  mov     rax, [rcx]
0x140008713  mov     rax, [rax+60h]
0x140008717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000871c  add     rsp, 28h
0x140008720  retn
```
