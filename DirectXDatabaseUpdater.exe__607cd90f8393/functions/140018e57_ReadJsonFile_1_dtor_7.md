# _ReadJsonFile_::_1_::dtor$7

- ea: `0x140018e57`
- end: `0x140018e63`
- name: `_ReadJsonFile_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005cac`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x140018e57  lea     rcx, [rdx+48h]
0x140018e5e  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
