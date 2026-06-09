# _UtilVerifyFilePath_::_1_::dtor$0

- ea: `0x14001cbcf`
- end: `0x14001cbdb`
- name: `_UtilVerifyFilePath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400048c8`

## pseudocode

```c
__int64 __fastcall UtilVerifyFilePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2 + 96);
}

```

## disassembly

```asm
0x14001cbcf  lea     rcx, [rdx+60h]
0x14001cbd6  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
