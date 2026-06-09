# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$80

- ea: `0x180004ddf`
- end: `0x180004e04`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$80`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800037f0`
- `0x180004ac0`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_80(
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
0x180004ddf  mov     [rsp+arg_8], rdx
0x180004de4  push    rbp
0x180004de5  sub     rsp, 20h
0x180004de9  mov     rbp, rdx
0x180004dec  xor     r8d, r8d
0x180004def  mov     dl, 1
0x180004df1  mov     rcx, [rbp+60h]
0x180004df5  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180004dfa  xor     edx, edx; pThrowInfo
0x180004dfc  xor     ecx, ecx; pExceptionObject
0x180004dfe  call    _CxxThrowException_0
```
