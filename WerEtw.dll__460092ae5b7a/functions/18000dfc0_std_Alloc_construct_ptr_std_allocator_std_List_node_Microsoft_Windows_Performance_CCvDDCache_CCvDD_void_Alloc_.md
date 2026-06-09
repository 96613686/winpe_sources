# std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x18000dfc0`
- end: `0x18000dfdc`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028635`

## callees

- `0x180001894`
- `0x18000dfc0`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
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
0x18000dfc0  sub     rsp, 28h
0x18000dfc4  mov     rcx, [rcx+8]; Block
0x18000dfc8  test    rcx, rcx
0x18000dfcb  jz      short loc_18000DFD7
0x18000dfcd  mov     edx, 0A0h
0x18000dfd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dfd7  add     rsp, 28h
0x18000dfdb  retn
```
