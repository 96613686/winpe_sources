# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::operator[](std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &&)

- ea: `0x1800149b0`
- end: `0x1800149cd`
- name: `??A?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAAAEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a14`
- `0x1800152f4`
- `0x180015de4`
- `0x180016da4`
- `0x1800199e0`

## callees

- `0x180014368`

## pseudocode

```c
__int64 __fastcall std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::operator[](
        __int64 *a1,
        __int64 a2)
{
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  return *(_QWORD *)std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const,>(
                      a1,
                      (__int64)v3,
                      a2)
       + 64LL;
}

```

## disassembly

```asm
0x1800149b0  sub     rsp, 38h
0x1800149b4  mov     r8, rdx
0x1800149b7  lea     rdx, [rsp+38h+var_18]
0x1800149bc  call    ??$_Try_emplace@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const,>(std::string const &&)
0x1800149c1  mov     rax, [rax]
0x1800149c4  add     rax, 40h ; '@'
0x1800149c8  add     rsp, 38h
0x1800149cc  retn
```
