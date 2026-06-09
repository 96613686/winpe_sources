# _ForEachSubKeyCount_unsigned_long_(__cdecl_)(HKEY_____std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____const_&_std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_____&_std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_____&_std::vector__GUID_std::allocator__GUID____&_std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag________&_unsigned_long_&)_std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_____&_std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_____&_std::vector__GUID_std::allocator__GUID____&_std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag________&_unsigned_long_&__::_1_::dtor$1

- ea: `0x140013c48`
- end: `0x140013c54`
- name: `_ForEachSubKeyCount_unsigned_long_(__cdecl_)(HKEY_____std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____const_&_std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_____&_std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_____&_std::vector__GUID_std::allocator__GUID____&_std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag________&_unsigned_long_&)_std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_____&_std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_____&_std::vector__GUID_std::allocator__GUID____&_std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag________&_unsigned_long_&__::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140002774`

## pseudocode

```c
__int64 __fastcall ForEachSubKeyCount_unsigned_long____cdecl___HKEY_____std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____const___std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_______std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_______std::vector__GUID_std::allocator__GUID______std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag__________unsigned_long____std::vector_APPID_PLUGIN__std::allocator_APPID_PLUGIN_______std::vector_APPID_EXECUTION_CATEGORY__std::allocator_APPID_EXECUTION_CATEGORY_______std::vector__GUID_std::allocator__GUID______std::vector_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag____std::allocator_std::unique_ptr_unsigned_short_release::Deleter_release::aifree_tag__________unsigned_long____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x140013c48  lea     rcx, [rdx+40h]
0x140013c4f  jmp     ??1?$unique_ptr@U_APPID_POLICY@@U?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAA@XZ; std::unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>::~unique_ptr<_APPID_POLICY,release::Deleter<release::aifree_tag>>(void)
```
