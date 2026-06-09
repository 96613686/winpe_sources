# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000a5d8`
- end: `0x18000a5fd`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008150`
- `0x180009b3a`

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
0x18000a5d8  mov     [rsp+arg_8], rdx
0x18000a5dd  push    rbp
0x18000a5de  sub     rsp, 20h
0x18000a5e2  mov     rbp, rdx
0x18000a5e5  xor     r8d, r8d
0x18000a5e8  mov     dl, 1
0x18000a5ea  mov     rcx, [rbp+50h]
0x18000a5ee  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000a5f3  xor     edx, edx; pThrowInfo
0x18000a5f5  xor     ecx, ecx; pExceptionObject
0x18000a5f7  call    _CxxThrowException_0
```
