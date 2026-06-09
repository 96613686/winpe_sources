# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000c864`
- end: `0x18000c889`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ba8`
- `0x180007b88`

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
0x18000c864  mov     [rsp+arg_8], rdx
0x18000c869  push    rbp
0x18000c86a  sub     rsp, 20h
0x18000c86e  mov     rbp, rdx
0x18000c871  xor     r8d, r8d
0x18000c874  mov     dl, 1
0x18000c876  mov     rcx, [rbp+50h]
0x18000c87a  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000c87f  xor     edx, edx; pThrowInfo
0x18000c881  xor     ecx, ecx; pExceptionObject
0x18000c883  call    _CxxThrowException_0
```
