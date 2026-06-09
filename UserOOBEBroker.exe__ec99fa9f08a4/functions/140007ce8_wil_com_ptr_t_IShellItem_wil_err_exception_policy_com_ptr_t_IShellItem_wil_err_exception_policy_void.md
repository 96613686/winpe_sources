# wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>(void)

- ea: `0x140007ce8`
- end: `0x140007d06`
- name: `??1?$com_ptr_t@UIShellItem@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e744`
- `0x14000e756`
- `0x14000e77a`
- `0x14000e78c`
- `0x14000e7b0`

## callees

- `0x140007ce8`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IShellItem,wil::err_exception_policy>::~com_ptr_t<IShellItem,wil::err_exception_policy>(
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
0x140007ce8  sub     rsp, 28h
0x140007cec  mov     rcx, [rcx]
0x140007cef  test    rcx, rcx
0x140007cf2  jz      short loc_140007D01
0x140007cf4  mov     rax, [rcx]
0x140007cf7  mov     rax, [rax+10h]
0x140007cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007d00  nop
0x140007d01  add     rsp, 28h
0x140007d05  retn
```
