# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18002c999`
- end: `0x18002c9be`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000294c`
- `0x180010140`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18002c999  mov     [rsp+arg_8], rdx
0x18002c99e  push    rbp
0x18002c99f  sub     rsp, 20h
0x18002c9a3  mov     rbp, rdx
0x18002c9a6  xor     r8d, r8d
0x18002c9a9  mov     dl, 1
0x18002c9ab  mov     rcx, [rbp+50h]
0x18002c9af  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002c9b4  xor     edx, edx; pThrowInfo
0x18002c9b6  xor     ecx, ecx; pExceptionObject
0x18002c9b8  call    _CxxThrowException_0
```
