# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x14000587a`
- end: `0x14000589f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001e18`
- `0x1400024fc`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::string::_Tidy(*(void ***)(a2 + 96), 1, 0);
  throw;
}

```

## disassembly

```asm
0x14000587a  mov     [rsp+arg_8], rdx
0x14000587f  push    rbp
0x140005880  sub     rsp, 20h
0x140005884  mov     rbp, rdx
0x140005887  xor     r8d, r8d
0x14000588a  mov     dl, 1
0x14000588c  mov     rcx, [rbp+60h]
0x140005890  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140005895  xor     edx, edx; pThrowInfo
0x140005897  xor     ecx, ecx; pExceptionObject
0x140005899  call    _CxxThrowException_0
```
