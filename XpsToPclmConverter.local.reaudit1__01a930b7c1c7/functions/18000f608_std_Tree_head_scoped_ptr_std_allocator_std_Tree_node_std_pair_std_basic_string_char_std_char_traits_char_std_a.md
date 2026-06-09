# std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>>(void)

- ea: `0x18000f608`
- end: `0x18000f624`
- name: `??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e87c`
- `0x18001d3ce`

## callees

- `0x18000efa8`
- `0x18000f608`

## pseudocode

```c
__int64 __fastcall std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
    return std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
             *(_QWORD **)(a1 + 8),
             *(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x18000f608  sub     rsp, 28h
0x18000f60c  cmp     qword ptr [rcx+8], 0
0x18000f611  jz      short loc_18000F61F
0x18000f613  mov     rdx, [rcx]
0x18000f616  mov     rcx, [rcx+8]
0x18000f61a  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x18000f61f  add     rsp, 28h
0x18000f623  retn
```
