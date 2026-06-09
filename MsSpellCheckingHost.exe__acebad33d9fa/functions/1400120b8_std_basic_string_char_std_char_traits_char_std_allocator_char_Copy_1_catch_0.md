# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x1400120b8`
- end: `0x1400120dd`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400020ac`
- `0x14000640c`

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
0x1400120b8  mov     [rsp+arg_8], rdx
0x1400120bd  push    rbp
0x1400120be  sub     rsp, 20h
0x1400120c2  mov     rbp, rdx
0x1400120c5  xor     r8d, r8d
0x1400120c8  mov     dl, 1
0x1400120ca  mov     rcx, [rbp+50h]
0x1400120ce  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x1400120d3  xor     edx, edx; pThrowInfo
0x1400120d5  xor     ecx, ecx; pExceptionObject
0x1400120d7  call    _CxxThrowException_0
```
