# _std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch$1

- ea: `0x18000fd0a`
- end: `0x18000fd32`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch$1`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c0c`
- `0x18000bbf0`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 128), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18000fd0a  mov     [rsp+arg_8], rdx
0x18000fd0f  push    rbp
0x18000fd10  sub     rsp, 20h
0x18000fd14  mov     rbp, rdx
0x18000fd17  xor     r8d, r8d
0x18000fd1a  mov     dl, 1
0x18000fd1c  mov     rcx, [rbp+80h]
0x18000fd23  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000fd28  xor     edx, edx; pThrowInfo
0x18000fd2a  xor     ecx, ecx; pExceptionObject
0x18000fd2c  call    _CxxThrowException_0
```
