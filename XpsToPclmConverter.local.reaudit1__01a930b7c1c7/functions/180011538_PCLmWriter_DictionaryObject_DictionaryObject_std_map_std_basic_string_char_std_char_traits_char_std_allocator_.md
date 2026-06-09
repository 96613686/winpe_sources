# PCLmWriter::DictionaryObject::DictionaryObject(std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>,uint,uint)

- ea: `0x180011538`
- end: `0x18001159d`
- name: `??0DictionaryObject@PCLmWriter@@QEAA@V?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@II@Z`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010a50`
- `0x1800199e0`

## callees

- `0x18000e87c`
- `0x18000efa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PCLmWriter::DictionaryObject::DictionaryObject(__int64 a1, _QWORD *a2, int a3, int a4)
{
  *(_DWORD *)(a1 + 8) = a3;
  *(_DWORD *)(a1 + 12) = a4;
  *(_DWORD *)(a1 + 16) = 5;
  *(_QWORD *)a1 = &PCLmWriter::DictionaryObject::`vftable';
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(
    (__int64 *)(a1 + 24),
    a2);
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    a2,
    (__int64)a2);
  return a1;
}

```

## disassembly

```asm
0x180011538  mov     [rsp+arg_10], rbx
0x18001153d  mov     [rsp+arg_8], rdx
0x180011542  mov     [rsp+arg_0], rcx
0x180011547  push    rdi
0x180011548  sub     rsp, 20h
0x18001154c  mov     rbx, rdx
0x18001154f  mov     rdi, rcx
0x180011552  mov     [rcx+8], r8d
0x180011556  mov     [rcx+0Ch], r9d
0x18001155a  mov     dword ptr [rcx+10h], 5
0x180011561  lea     rax, ??_7DictionaryObject@PCLmWriter@@6B@; const PCLmWriter::DictionaryObject::`vftable'
0x180011568  mov     [rcx], rax
0x18001156b  add     rcx, 18h
0x18001156f  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &&)
0x180011574  mov     qword ptr [rdi+28h], 0
0x18001157c  mov     qword ptr [rdi+30h], 0
0x180011584  mov     rdx, rbx
0x180011587  mov     rcx, rbx
0x18001158a  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x18001158f  mov     rax, rdi
0x180011592  mov     rbx, [rsp+28h+arg_10]
0x180011597  add     rsp, 20h
0x18001159b  pop     rdi
0x18001159c  retn
```
