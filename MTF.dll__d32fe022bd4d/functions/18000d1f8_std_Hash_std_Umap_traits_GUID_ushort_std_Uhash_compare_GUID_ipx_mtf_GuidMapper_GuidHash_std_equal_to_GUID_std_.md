# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Make_iter(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>,std::_Iterator_base0>)

- ea: `0x18000d1f8`
- end: `0x18000d1ff`
- name: `?_Make_iter@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002c4ce`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Make_iter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *a2 = a3;
  return a2;
}

```

## disassembly

```asm
0x18000d1f8  mov     [rdx], r8
0x18000d1fb  mov     rax, rdx
0x18000d1fe  retn
```
