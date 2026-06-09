# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140038f3a`
- end: `0x140038f5f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003abc`
- `0x14000d500`

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
0x140038f3a  mov     [rsp+arg_8], rdx
0x140038f3f  push    rbp
0x140038f40  sub     rsp, 20h
0x140038f44  mov     rbp, rdx
0x140038f47  xor     r8d, r8d
0x140038f4a  mov     dl, 1
0x140038f4c  mov     rcx, [rbp+50h]
0x140038f50  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140038f55  xor     edx, edx; pThrowInfo
0x140038f57  xor     ecx, ecx; pExceptionObject
0x140038f59  call    _CxxThrowException_0
```
