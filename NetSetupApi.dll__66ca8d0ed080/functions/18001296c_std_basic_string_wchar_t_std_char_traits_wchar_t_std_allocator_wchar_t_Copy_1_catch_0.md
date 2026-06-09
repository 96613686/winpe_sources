# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0

- ea: `0x18001296c`
- end: `0x180012991`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007274`
- `0x18000895c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::wstring::_Tidy(*(void ***)(a2 + 96), 1, 0);
  throw;
}

```

## disassembly

```asm
0x18001296c  mov     [rsp+arg_8], rdx
0x180012971  push    rbp
0x180012972  sub     rsp, 20h
0x180012976  mov     rbp, rdx
0x180012979  xor     r8d, r8d
0x18001297c  mov     dl, 1
0x18001297e  mov     rcx, [rbp+60h]
0x180012982  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012987  xor     edx, edx; pThrowInfo
0x180012989  xor     ecx, ecx; pExceptionObject
0x18001298b  call    _CxxThrowException_0
```
