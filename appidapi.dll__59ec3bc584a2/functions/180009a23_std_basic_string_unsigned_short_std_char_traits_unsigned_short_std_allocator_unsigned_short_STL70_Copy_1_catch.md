# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$0

- ea: `0x180009a23`
- end: `0x180009a4b`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000227c`
- `0x18000372c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch_0(
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
0x180009a23  mov     [rsp+arg_8], rdx
0x180009a28  push    rbp
0x180009a29  sub     rsp, 20h
0x180009a2d  mov     rbp, rdx
0x180009a30  xor     r8d, r8d
0x180009a33  mov     dl, 1
0x180009a35  mov     rcx, [rbp+90h]
0x180009a3c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009a41  xor     edx, edx; pThrowInfo
0x180009a43  xor     ecx, ecx; pExceptionObject
0x180009a45  call    _CxxThrowException_0
```
