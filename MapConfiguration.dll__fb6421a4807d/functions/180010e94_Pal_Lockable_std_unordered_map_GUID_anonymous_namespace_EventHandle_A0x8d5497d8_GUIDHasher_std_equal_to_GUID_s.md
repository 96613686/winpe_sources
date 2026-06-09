# Pal::Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::_Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______

- ea: `0x180010e94`
- end: `0x180010eb5`
- name: `Pal::Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::_Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180041e30`

## callees

- `0x180011058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010eae`

## pseudocode

```c
void __fastcall Pal::Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::_Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______(
        struct _RTL_CRITICAL_SECTION *a1)
{
  std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::__Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___(&a1[1]);
  DeleteCriticalSection(a1);
}

```

## disassembly

```asm
0x180010e94  push    rbx
0x180010e96  sub     rsp, 20h
0x180010e9a  mov     rbx, rcx
0x180010e9d  add     rcx, 28h ; '('
0x180010ea1  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0_______Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0___
0x180010ea6  mov     rcx, rbx
0x180010ea9  add     rsp, 20h
0x180010ead  pop     rbx
0x180010eae  jmp     cs:__imp_DeleteCriticalSection
```
