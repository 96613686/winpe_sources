# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)

- ea: `0x18000f5bc`
- end: `0x18000f5d8`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eccc`
- `0x18000f62c`
- `0x18000f65c`
- `0x18001d3f2`
- `0x18001d404`

## callees

- `0x18000edc0`
- `0x18000f5bc`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 80);
  return result;
}

```

## disassembly

```asm
0x18000f5bc  sub     rsp, 28h
0x18000f5c0  mov     rcx, [rcx+8]
0x18000f5c4  test    rcx, rcx
0x18000f5c7  jz      short loc_18000F5D3
0x18000f5c9  mov     edx, 50h ; 'P'
0x18000f5ce  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f5d3  add     rsp, 28h
0x18000f5d7  retn
```
