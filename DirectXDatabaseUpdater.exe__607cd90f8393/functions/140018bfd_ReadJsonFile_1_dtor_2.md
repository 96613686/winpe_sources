# _ReadJsonFile_::_1_::dtor$2

- ea: `0x140018bfd`
- end: `0x140018c09`
- name: `_ReadJsonFile_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x140018bfd  lea     rcx, [rdx+58h]
0x140018c04  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
