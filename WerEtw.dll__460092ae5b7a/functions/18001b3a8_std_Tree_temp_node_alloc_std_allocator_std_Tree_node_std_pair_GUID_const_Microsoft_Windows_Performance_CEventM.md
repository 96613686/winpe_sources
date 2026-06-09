# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(void)

- ea: `0x18001b3a8`
- end: `0x18001b3c4`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800288e0`

## callees

- `0x180001894`
- `0x18001b3a8`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18001b3a8  sub     rsp, 28h
0x18001b3ac  mov     rcx, [rcx+8]; Block
0x18001b3b0  test    rcx, rcx
0x18001b3b3  jz      short loc_18001B3BF
0x18001b3b5  mov     edx, 78h ; 'x'
0x18001b3ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b3bf  add     rsp, 28h
0x18001b3c3  retn
```
