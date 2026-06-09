# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18001472f`
- end: `0x180014754`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001cec`
- `0x180002668`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18001472f  mov     [rsp+arg_8], rdx
0x180014734  push    rbp
0x180014735  sub     rsp, 20h
0x180014739  mov     rbp, rdx
0x18001473c  xor     r8d, r8d
0x18001473f  mov     dl, 1
0x180014741  mov     rcx, [rbp+50h]
0x180014745  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18001474a  xor     edx, edx; pThrowInfo
0x18001474c  xor     ecx, ecx; pExceptionObject
0x18001474e  call    _CxxThrowException_0
```
