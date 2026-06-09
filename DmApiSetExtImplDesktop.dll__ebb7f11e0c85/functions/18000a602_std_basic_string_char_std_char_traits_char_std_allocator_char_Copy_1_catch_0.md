# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000a602`
- end: `0x18000a627`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005bf8`
- `0x180009ddb`

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
0x18000a602  mov     [rsp+arg_8], rdx
0x18000a607  push    rbp
0x18000a608  sub     rsp, 20h
0x18000a60c  mov     rbp, rdx
0x18000a60f  xor     r8d, r8d
0x18000a612  mov     dl, 1
0x18000a614  mov     rcx, [rbp+50h]
0x18000a618  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000a61d  xor     edx, edx; pThrowInfo
0x18000a61f  xor     ecx, ecx; pExceptionObject
0x18000a621  call    _CxxThrowException_0
```
