# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18000a681`
- end: `0x18000a6a6`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005c60`
- `0x180009ddb`

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
0x18000a681  mov     [rsp+arg_8], rdx
0x18000a686  push    rbp
0x18000a687  sub     rsp, 20h
0x18000a68b  mov     rbp, rdx
0x18000a68e  xor     r8d, r8d
0x18000a691  mov     dl, 1
0x18000a693  mov     rcx, [rbp+50h]
0x18000a697  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000a69c  xor     edx, edx; pThrowInfo
0x18000a69e  xor     ecx, ecx; pExceptionObject
0x18000a6a0  call    _CxxThrowException_0
```
