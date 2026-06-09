# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140009920`
- end: `0x140009945`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000220c`
- `0x140005974`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::string::_Tidy(*(void ***)(a2 + 80), 1, 0);
  throw;
}

```

## disassembly

```asm
0x140009920  mov     [rsp+arg_8], rdx
0x140009925  push    rbp
0x140009926  sub     rsp, 20h
0x14000992a  mov     rbp, rdx
0x14000992d  xor     r8d, r8d
0x140009930  mov     dl, 1
0x140009932  mov     rcx, [rbp+50h]
0x140009936  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000993b  xor     edx, edx; pThrowInfo
0x14000993d  xor     ecx, ecx; pExceptionObject
0x14000993f  call    _CxxThrowException_0
```
