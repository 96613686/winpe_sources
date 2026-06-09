# wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::~com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>(void)

- ea: `0x180018f74`
- end: `0x180018f93`
- name: `??1?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800291a8`
- `0x1800297de`
- `0x180029b70`
- `0x18002a860`
- `0x18002abd2`
- `0x18002aea3`
- `0x18002aec7`
- `0x18002aed9`
- `0x18002b003`

## callees

- `0x180018f74`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::~com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>(
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
0x180018f74  sub     rsp, 28h
0x180018f78  mov     rcx, [rcx]
0x180018f7b  test    rcx, rcx
0x180018f7e  jz      short loc_180018F8D
0x180018f80  mov     rax, [rcx]
0x180018f83  mov     rax, [rax+10h]
0x180018f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f8c  nop
0x180018f8d  add     rsp, 28h
0x180018f91  retn
```
