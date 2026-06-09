# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000fd87`
- end: `0x18000fdac`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001518`
- `0x18000257c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 96), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18000fd87  mov     [rsp+arg_8], rdx
0x18000fd8c  push    rbp
0x18000fd8d  sub     rsp, 20h
0x18000fd91  mov     rbp, rdx
0x18000fd94  xor     r8d, r8d
0x18000fd97  mov     dl, 1
0x18000fd99  mov     rcx, [rbp+60h]
0x18000fd9d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000fda2  xor     edx, edx; pThrowInfo
0x18000fda4  xor     ecx, ecx; pExceptionObject
0x18000fda6  call    _CxxThrowException_0
```
