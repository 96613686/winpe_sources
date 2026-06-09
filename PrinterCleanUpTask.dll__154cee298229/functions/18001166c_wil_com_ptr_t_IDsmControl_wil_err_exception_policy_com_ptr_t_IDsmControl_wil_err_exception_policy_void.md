# wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(void)

- ea: `0x18001166c`
- end: `0x18001168a`
- name: `??1?$com_ptr_t@UIDsmControl@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011ea8`
- `0x180017190`
- `0x18001735d`

## callees

- `0x18001166c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IDsmControl,wil::err_exception_policy>::~com_ptr_t<IDsmControl,wil::err_exception_policy>(
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
0x18001166c  sub     rsp, 28h
0x180011670  mov     rcx, [rcx]
0x180011673  test    rcx, rcx
0x180011676  jz      short loc_180011685
0x180011678  mov     rax, [rcx]
0x18001167b  mov     rax, [rax+10h]
0x18001167f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011684  nop
0x180011685  add     rsp, 28h
0x180011689  retn
```
