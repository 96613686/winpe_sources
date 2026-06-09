# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000bb3f`
- end: `0x18000bb64`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000278c`
- `0x180006a38`

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
0x18000bb3f  mov     [rsp+arg_8], rdx
0x18000bb44  push    rbp
0x18000bb45  sub     rsp, 20h
0x18000bb49  mov     rbp, rdx
0x18000bb4c  xor     r8d, r8d
0x18000bb4f  mov     dl, 1
0x18000bb51  mov     rcx, [rbp+50h]
0x18000bb55  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000bb5a  xor     edx, edx; pThrowInfo
0x18000bb5c  xor     ecx, ecx; pExceptionObject
0x18000bb5e  call    _CxxThrowException_0
```
