# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)

- ea: `0x18000f62c`
- end: `0x18000f654`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f1b8`
- `0x180014368`
- `0x180014470`

## callees

- `0x18000f5bc`
- `0x18000f62c`
- `0x18000f68c`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::~pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>(v2 + 32);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(a1);
}

```

## disassembly

```asm
0x18000f62c  push    rbx
0x18000f62e  sub     rsp, 20h
0x18000f632  mov     rbx, rcx
0x18000f635  mov     rcx, [rcx+8]
0x18000f639  test    rcx, rcx
0x18000f63c  jz      short loc_18000F647
0x18000f63e  add     rcx, 20h ; ' '
0x18000f642  call    ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@QEAA@XZ; std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::~pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>(void)
0x18000f647  mov     rcx, rbx
0x18000f64a  add     rsp, 20h
0x18000f64e  pop     rbx
0x18000f64f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
```
