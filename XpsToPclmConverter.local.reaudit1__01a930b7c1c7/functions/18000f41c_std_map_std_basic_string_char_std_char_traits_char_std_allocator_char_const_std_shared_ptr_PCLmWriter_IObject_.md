# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)

- ea: `0x18000f41c`
- end: `0x18000f442`
- name: `??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180010290`
- `0x180014a14`
- `0x1800152f4`
- `0x1800158e4`
- `0x180015de4`
- `0x180016da4`
- `0x1800199e0`

## callees

- `0x18001009c`

## pseudocode

```c
_QWORD *__fastcall std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Alloc_sentinel_and_proxy();
  return a1;
}

```

## disassembly

```asm
0x18000f41c  push    rbx
0x18000f41e  sub     rsp, 20h
0x18000f422  mov     rbx, rcx
0x18000f425  mov     qword ptr [rcx], 0
0x18000f42c  mov     qword ptr [rcx+8], 0
0x18000f434  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000f439  mov     rax, rbx
0x18000f43c  add     rsp, 20h
0x18000f440  pop     rbx
0x18000f441  retn
```
