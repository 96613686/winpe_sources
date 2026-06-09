# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18000c8e1`
- end: `0x18000c906`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ba8`
- `0x180007be8`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 96), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18000c8e1  mov     [rsp+arg_8], rdx
0x18000c8e6  push    rbp
0x18000c8e7  sub     rsp, 20h
0x18000c8eb  mov     rbp, rdx
0x18000c8ee  xor     r8d, r8d
0x18000c8f1  mov     dl, 1
0x18000c8f3  mov     rcx, [rbp+60h]
0x18000c8f7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000c8fc  xor     edx, edx; pThrowInfo
0x18000c8fe  xor     ecx, ecx; pExceptionObject
0x18000c900  call    _CxxThrowException_0
```
