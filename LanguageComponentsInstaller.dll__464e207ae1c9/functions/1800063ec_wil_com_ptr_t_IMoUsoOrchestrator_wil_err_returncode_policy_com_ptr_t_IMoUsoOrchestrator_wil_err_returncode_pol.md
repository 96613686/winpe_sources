# wil::com_ptr_t<IMoUsoOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IMoUsoOrchestrator,wil::err_returncode_policy>(void)

- ea: `0x1800063ec`
- end: `0x18000640a`
- name: `??1?$com_ptr_t@UIMoUsoOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027fc6`
- `0x1800283dd`
- `0x18002917e`
- `0x180029190`

## callees

- `0x1800063ec`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IMoUsoOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IMoUsoOrchestrator,wil::err_returncode_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800063ec  sub     rsp, 28h
0x1800063f0  mov     rcx, [rcx]
0x1800063f3  test    rcx, rcx
0x1800063f6  jz      short loc_180006405
0x1800063f8  mov     rax, [rcx]
0x1800063fb  mov     rax, [rax+10h]
0x1800063ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006404  nop
0x180006405  add     rsp, 28h
0x180006409  retn
```
