# wil::com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>::~com_ptr_t<IWindowsUpdateAdministration,wil::err_exception_policy>(void)

- ea: `0x180018298`
- end: `0x1800182b6`
- name: `??1?$com_ptr_t@UIWindowsUpdateAdministration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027c8a`
- `0x1800281ea`
- `0x1800285b1`
- `0x1800289c2`
- `0x180028ca2`
- `0x180028f09`
- `0x180028f2d`
- `0x180029038`
- `0x18002905c`

## callees

- `0x180018298`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180018298  sub     rsp, 28h
0x18001829c  mov     rcx, [rcx]
0x18001829f  test    rcx, rcx
0x1800182a2  jz      short loc_1800182B1
0x1800182a4  mov     rax, [rcx]
0x1800182a7  mov     rax, [rax+10h]
0x1800182ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182b0  nop
0x1800182b1  add     rsp, 28h
0x1800182b5  retn
```
