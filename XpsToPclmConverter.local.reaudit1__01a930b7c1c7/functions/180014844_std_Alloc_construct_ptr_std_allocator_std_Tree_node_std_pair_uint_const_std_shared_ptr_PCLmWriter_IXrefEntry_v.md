# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(void)

- ea: `0x180014844`
- end: `0x180014860`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014898`
- `0x18001d792`

## callees

- `0x18000edc0`
- `0x180014844`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 56);
  return result;
}

```

## disassembly

```asm
0x180014844  sub     rsp, 28h
0x180014848  mov     rcx, [rcx+8]
0x18001484c  test    rcx, rcx
0x18001484f  jz      short loc_18001485B
0x180014851  mov     edx, 38h ; '8'
0x180014856  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001485b  add     rsp, 28h
0x18001485f  retn
```
