# _std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0

- ea: `0x1800096e7`
- end: `0x18000970f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001638`
- `0x18000227c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 144), a2, 0);
  throw;
}

```

## disassembly

```asm
0x1800096e7  mov     [rsp+arg_8], rdx
0x1800096ec  push    rbp
0x1800096ed  sub     rsp, 20h
0x1800096f1  mov     rbp, rdx
0x1800096f4  xor     r8d, r8d
0x1800096f7  mov     dl, 1
0x1800096f9  mov     rcx, [rbp+90h]
0x180009700  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180009705  xor     edx, edx; pThrowInfo
0x180009707  xor     ecx, ecx; pExceptionObject
0x180009709  call    _CxxThrowException_0
```
