# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *>>>(void)

- ea: `0x18000f23c`
- end: `0x18000f258`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800186ac`

## callees

- `0x180002110`
- `0x18000f23c`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x30u);
}

```

## disassembly

```asm
0x18000f23c  sub     rsp, 28h
0x18000f240  mov     rcx, [rcx+8]; void *
0x18000f244  test    rcx, rcx
0x18000f247  jz      short loc_18000F253
0x18000f249  mov     edx, 30h ; '0'; unsigned __int64
0x18000f24e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f253  add     rsp, 28h
0x18000f257  retn
```
