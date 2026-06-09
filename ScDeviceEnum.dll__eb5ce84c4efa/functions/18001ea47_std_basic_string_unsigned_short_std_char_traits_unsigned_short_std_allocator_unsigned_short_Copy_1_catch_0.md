# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18001ea47`
- end: `0x18001ea6c`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f0c`
- `0x180009840`

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
0x18001ea47  mov     [rsp+arg_8], rdx
0x18001ea4c  push    rbp
0x18001ea4d  sub     rsp, 20h
0x18001ea51  mov     rbp, rdx
0x18001ea54  xor     r8d, r8d
0x18001ea57  mov     dl, 1
0x18001ea59  mov     rcx, [rbp+50h]
0x18001ea5d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ea62  xor     edx, edx; pThrowInfo
0x18001ea64  xor     ecx, ecx; pExceptionObject
0x18001ea66  call    _CxxThrowException_0
```
