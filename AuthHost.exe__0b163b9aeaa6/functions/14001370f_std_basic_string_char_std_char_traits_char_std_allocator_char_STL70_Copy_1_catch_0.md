# _std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0

- ea: `0x14001370f`
- end: `0x140013734`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400029d3`
- `0x14000f998`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch_0(
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
0x14001370f  mov     [rsp+arg_8], rdx
0x140013714  push    rbp
0x140013715  sub     rsp, 20h
0x140013719  mov     rbp, rdx
0x14001371c  xor     r8d, r8d
0x14001371f  mov     dl, 1
0x140013721  mov     rcx, [rbp+50h]
0x140013725  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14001372a  xor     edx, edx; pThrowInfo
0x14001372c  xor     ecx, ecx; pExceptionObject
0x14001372e  call    _CxxThrowException_0
```
