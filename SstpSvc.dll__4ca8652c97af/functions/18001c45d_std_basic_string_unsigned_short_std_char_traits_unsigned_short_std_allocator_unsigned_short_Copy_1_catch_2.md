# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$2

- ea: `0x18001c45d`
- end: `0x18001c485`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$2`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008fce`
- `0x1800124fc`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  std::wstring::_Tidy(*(_QWORD **)(a2 + 128), 1, 0);
  throw;
}

```

## disassembly

```asm
0x18001c45d  mov     [rsp+arg_8], rdx
0x18001c462  push    rbp
0x18001c463  sub     rsp, 20h
0x18001c467  mov     rbp, rdx
0x18001c46a  xor     r8d, r8d
0x18001c46d  mov     dl, 1
0x18001c46f  mov     rcx, [rbp+80h]
0x18001c476  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001c47b  xor     edx, edx; pThrowInfo
0x18001c47d  xor     ecx, ecx; pExceptionObject
0x18001c47f  call    _CxxThrowException_0
```
