# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$2

- ea: `0x140013774`
- end: `0x14001379c`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$2`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400029d3`
- `0x14000fa04`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 144), a2, 0);
  throw;
}

```

## disassembly

```asm
0x140013774  mov     [rsp+arg_8], rdx
0x140013779  push    rbp
0x14001377a  sub     rsp, 20h
0x14001377e  mov     rbp, rdx
0x140013781  xor     r8d, r8d
0x140013784  mov     dl, 1
0x140013786  mov     rcx, [rbp+90h]
0x14001378d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140013792  xor     edx, edx; pThrowInfo
0x140013794  xor     ecx, ecx; pExceptionObject
0x140013796  call    _CxxThrowException_0
```
