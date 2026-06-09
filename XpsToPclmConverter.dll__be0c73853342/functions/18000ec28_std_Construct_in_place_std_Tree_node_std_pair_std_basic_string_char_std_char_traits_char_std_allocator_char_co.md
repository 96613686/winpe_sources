# std::_Construct_in_place<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)

- ea: `0x18000ec28`
- end: `0x18000ec2f`
- name: `??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e7fc`
- `0x180014368`
- `0x180014538`
- `0x18001869c`
- `0x180018770`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 result; // rax

  result = *a2;
  *a1 = *a2;
  return result;
}

```

## disassembly

```asm
0x18000ec28  mov     rax, [rdx]
0x18000ec2b  mov     [rcx], rax
0x18000ec2e  retn
```
