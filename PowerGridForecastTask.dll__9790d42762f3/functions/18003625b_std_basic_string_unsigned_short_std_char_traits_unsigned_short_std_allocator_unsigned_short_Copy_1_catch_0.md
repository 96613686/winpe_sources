# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18003625b`
- end: `0x180036280`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180026778`
- `0x180033fb8`

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
0x18003625b  mov     [rsp+arg_8], rdx
0x180036260  push    rbp
0x180036261  sub     rsp, 20h
0x180036265  mov     rbp, rdx
0x180036268  xor     r8d, r8d
0x18003626b  mov     dl, 1
0x18003626d  mov     rcx, [rbp+50h]
0x180036271  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180036276  xor     edx, edx; pThrowInfo
0x180036278  xor     ecx, ecx; pExceptionObject
0x18003627a  call    _CxxThrowException_0
```
