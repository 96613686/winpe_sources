# std::_Construct_in_place<PCLmWriter::DictionaryObject,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> const &,uint &,uint &>(PCLmWriter::DictionaryObject &,std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> const &,uint &,uint &)

- ea: `0x180010a50`
- end: `0x180010a95`
- name: `??$_Construct_in_place@VDictionaryObject@PCLmWriter@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAIAEAI@std@@YAXAEAVDictionaryObject@PCLmWriter@@AEBV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@0@AEAI2@Z`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012580`

## callees

- `0x18000e87c`
- `0x180011538`

## pseudocode

```c
__int64 __fastcall std::_Construct_in_place<PCLmWriter::DictionaryObject,std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>> const &,unsigned int &,unsigned int &>(
        __int64 a1,
        _QWORD *a2,
        int *a3,
        int *a4)
{
  int v4; // ebx
  int v6; // edi
  __int64 v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *a4;
  v6 = *a3;
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(
    v8,
    a2);
  return PCLmWriter::DictionaryObject::DictionaryObject(a1, v8, v6, v4);
}

```

## disassembly

```asm
0x180010a50  mov     [rsp+arg_8], rbx
0x180010a55  mov     [rsp+arg_10], rsi
0x180010a5a  push    rdi
0x180010a5b  sub     rsp, 30h
0x180010a5f  mov     ebx, [r9]
0x180010a62  mov     rsi, rcx
0x180010a65  mov     edi, [r8]
0x180010a68  lea     rcx, [rsp+38h+var_18]
0x180010a6d  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &&)
0x180010a72  mov     r9d, ebx
0x180010a75  lea     rdx, [rsp+38h+var_18]
0x180010a7a  mov     r8d, edi
0x180010a7d  mov     rcx, rsi
0x180010a80  call    ??0DictionaryObject@PCLmWriter@@QEAA@V?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@II@Z; PCLmWriter::DictionaryObject::DictionaryObject(std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,uint,uint)
0x180010a85  mov     rbx, [rsp+38h+arg_8]
0x180010a8a  mov     rsi, [rsp+38h+arg_10]
0x180010a8f  add     rsp, 30h
0x180010a93  pop     rdi
0x180010a94  retn
```
