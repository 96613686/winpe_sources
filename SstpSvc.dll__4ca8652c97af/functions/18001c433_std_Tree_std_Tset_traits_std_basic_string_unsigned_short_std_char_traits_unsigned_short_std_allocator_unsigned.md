# _std::_Tree_std::_Tset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____lessstr_std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::_Copy_::_1_::catch$0

- ea: `0x18001c433`
- end: `0x18001c457`
- name: `_std::_Tree_std::_Tset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____lessstr_std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::_Copy_::_1_::catch$0`
- size: `36`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008fce`
- `0x180011ccc`

## pseudocode

```c
void __fastcall __noreturn std::_Tree_std::_Tset_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____lessstr_std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______0___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Erase(
    *(_QWORD *)(a2 + 64),
    *(_QWORD *)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x18001c433  mov     [rsp+arg_8], rdx
0x18001c438  push    rbp
0x18001c439  sub     rsp, 20h
0x18001c43d  mov     rbp, rdx
0x18001c440  mov     rdx, [rbp+48h]
0x18001c444  mov     rcx, [rbp+40h]
0x18001c448  call    ?_Erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *)
0x18001c44d  xor     edx, edx; pThrowInfo
0x18001c44f  xor     ecx, ecx; pExceptionObject
0x18001c451  call    _CxxThrowException_0
```
