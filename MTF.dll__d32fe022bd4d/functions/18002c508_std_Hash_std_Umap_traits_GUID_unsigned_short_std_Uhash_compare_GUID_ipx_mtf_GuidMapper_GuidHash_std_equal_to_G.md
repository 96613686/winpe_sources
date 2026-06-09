# _std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short__&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch$1

- ea: `0x18002c508`
- end: `0x18002c52c`
- name: `_std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short__&_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch$1`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000294c`
- `0x18000cd10`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Umap_traits__GUID_unsigned_short_std::_Uhash_compare__GUID_ipx::mtf::GuidMapper::GuidHash_std::equal_to__GUID____std::allocator_std::pair__GUID_const__unsigned_short____0___::_Insert_std::pair__GUID_const__unsigned_short____std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair__GUID_const__unsigned_short__________::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Destroy_if_not_nil(
    *(_QWORD **)(a2 + 96),
    *(_QWORD ***)(a2 + 120));
  throw;
}

```

## disassembly

```asm
0x18002c508  mov     [rsp+arg_8], rdx
0x18002c50d  push    rbp
0x18002c50e  sub     rsp, 20h
0x18002c512  mov     rbp, rdx
0x18002c515  mov     rdx, [rbp+78h]
0x18002c519  mov     rcx, [rbp+60h]
0x18002c51d  call    ?_Destroy_if_not_nil@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAAXV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Destroy_if_not_nil(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)
0x18002c522  xor     edx, edx; pThrowInfo
0x18002c524  xor     ecx, ecx; pExceptionObject
0x18002c526  call    _CxxThrowException_0
```
