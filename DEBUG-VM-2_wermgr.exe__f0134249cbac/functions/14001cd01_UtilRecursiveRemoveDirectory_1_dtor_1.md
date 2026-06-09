# _UtilRecursiveRemoveDirectory_::_1_::dtor$1

- ea: `0x14001cd01`
- end: `0x14001cd0d`
- name: `_UtilRecursiveRemoveDirectory_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400048c8`

## pseudocode

```c
__int64 __fastcall UtilRecursiveRemoveDirectory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2 + 80);
}

```

## disassembly

```asm
0x14001cd01  lea     rcx, [rdx+50h]
0x14001cd08  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
