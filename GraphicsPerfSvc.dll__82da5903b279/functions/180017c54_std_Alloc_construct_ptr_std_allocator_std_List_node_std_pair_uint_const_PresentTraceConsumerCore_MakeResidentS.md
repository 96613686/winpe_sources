# std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(void)

- ea: `0x180017c54`
- end: `0x180017c70`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180016b6c`
- `0x180017ec0`
- `0x18002fc27`

## callees

- `0x18000b550`
- `0x180017c54`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x28u);
}

```

## disassembly

```asm
0x180017c54  sub     rsp, 28h
0x180017c58  mov     rcx, [rcx+8]
0x180017c5c  test    rcx, rcx
0x180017c5f  jz      short loc_180017C6B
0x180017c61  mov     edx, 28h ; '('
0x180017c66  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017c6b  add     rsp, 28h
0x180017c6f  retn
```
