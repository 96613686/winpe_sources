# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140004454`
- end: `0x140004479`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001308`
- `0x140001e9c`

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
0x140004454  mov     [rsp+arg_8], rdx
0x140004459  push    rbp
0x14000445a  sub     rsp, 20h
0x14000445e  mov     rbp, rdx
0x140004461  xor     r8d, r8d
0x140004464  mov     dl, 1
0x140004466  mov     rcx, [rbp+60h]
0x14000446a  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000446f  xor     edx, edx; pThrowInfo
0x140004471  xor     ecx, ecx; pExceptionObject
0x140004473  call    _CxxThrowException_0
```
