# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(void)

- ea: `0x180014898`
- end: `0x1800148c5`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014538`

## callees

- `0x1800101cc`
- `0x180014844`
- `0x180014898`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(std::_Ref_count_base **)(v2 + 48);
    if ( v3 )
      std::_Ref_count_base::_Decref(v3);
  }
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(a1);
}

```

## disassembly

```asm
0x180014898  push    rbx
0x18001489a  sub     rsp, 20h
0x18001489e  mov     rbx, rcx
0x1800148a1  mov     rcx, [rcx+8]
0x1800148a5  test    rcx, rcx
0x1800148a8  jz      short loc_1800148B8
0x1800148aa  mov     rcx, [rcx+30h]; this
0x1800148ae  test    rcx, rcx
0x1800148b1  jz      short loc_1800148B8
0x1800148b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800148b8  mov     rcx, rbx
0x1800148bb  add     rsp, 20h
0x1800148bf  pop     rbx
0x1800148c0  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(void)
```
