# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140009c07`
- end: `0x140009c2c`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001dbc`
- `0x1400071a4`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::string::_Tidy(*(void ***)(a2 + 80), 1, 0);
  throw;
}

```

## disassembly

```asm
0x140009c07  mov     [rsp+arg_8], rdx
0x140009c0c  push    rbp
0x140009c0d  sub     rsp, 20h
0x140009c11  mov     rbp, rdx
0x140009c14  xor     r8d, r8d
0x140009c17  mov     dl, 1
0x140009c19  mov     rcx, [rbp+50h]
0x140009c1d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140009c22  xor     edx, edx; pThrowInfo
0x140009c24  xor     ecx, ecx; pExceptionObject
0x140009c26  call    _CxxThrowException_0
```
