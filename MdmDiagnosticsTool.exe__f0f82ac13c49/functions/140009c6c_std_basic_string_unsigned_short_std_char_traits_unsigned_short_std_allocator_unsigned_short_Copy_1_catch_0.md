# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x140009c6c`
- end: `0x140009c91`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001dbc`
- `0x140007204`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::wstring::_Tidy(*(_QWORD **)(a2 + 80), 1, 0);
  throw;
}

```

## disassembly

```asm
0x140009c6c  mov     [rsp+arg_8], rdx
0x140009c71  push    rbp
0x140009c72  sub     rsp, 20h
0x140009c76  mov     rbp, rdx
0x140009c79  xor     r8d, r8d
0x140009c7c  mov     dl, 1
0x140009c7e  mov     rcx, [rbp+50h]
0x140009c82  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140009c87  xor     edx, edx; pThrowInfo
0x140009c89  xor     ecx, ecx; pExceptionObject
0x140009c8b  call    _CxxThrowException_0
```
