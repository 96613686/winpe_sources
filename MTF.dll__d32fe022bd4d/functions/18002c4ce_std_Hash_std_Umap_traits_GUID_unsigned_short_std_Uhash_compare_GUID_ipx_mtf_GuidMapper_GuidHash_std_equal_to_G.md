# _std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short__&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch$0

- ea: `0x18002c4ce`
- end: `0x18002c502`
- name: `_std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short__&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000294c`
- `0x18000d1f8`
- `0x18000d3c0`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short____std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD **iter; // rax

  iter = (_QWORD **)std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Make_iter(
                      a1,
                      a2 + 32,
                      *(_QWORD *)(a2 + 32));
  std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::erase(
    *(_QWORD **)(a2 + 96),
    (_QWORD *)(a2 + 40),
    *iter);
  throw;
}

```

## disassembly

```asm
0x18002c4ce  mov     [rsp+arg_8], rdx
0x18002c4d3  push    rbp
0x18002c4d4  sub     rsp, 20h
0x18002c4d8  mov     rbp, rdx
0x18002c4db  mov     r8, [rbp+20h]
0x18002c4df  lea     rdx, [rbp+20h]
0x18002c4e3  call    ?_Make_iter@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Make_iter(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>,std::_Iterator_base0>)
0x18002c4e8  mov     r8, [rax]
0x18002c4eb  lea     rdx, [rbp+28h]
0x18002c4ef  mov     rcx, [rbp+60h]
0x18002c4f3  call    ?erase@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)
0x18002c4f8  xor     edx, edx; pThrowInfo
0x18002c4fa  xor     ecx, ecx; pExceptionObject
0x18002c4fc  call    _CxxThrowException_0
```
