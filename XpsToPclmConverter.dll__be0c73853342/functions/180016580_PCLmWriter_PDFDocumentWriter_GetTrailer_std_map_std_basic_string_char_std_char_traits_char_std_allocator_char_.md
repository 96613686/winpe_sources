# PCLmWriter::PDFDocumentWriter::_GetTrailer(std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>> *)

- ea: `0x180016580`
- end: `0x180016605`
- name: `?_GetTrailer@PDFDocumentWriter@PCLmWriter@@AEAAXPEAV?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@@Z`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015de4`

## callees

- `0x18000f1b8`
- `0x18000f8d4`
- `0x1800105f4`
- `0x180016580`
- `0x18001660c`

## pseudocode

```c
void __fastcall PCLmWriter::PDFDocumentWriter::_GetTrailer(__int64 a1, __int64 *a2)
{
  _QWORD *i; // rbx
  __int64 v5; // rax
  __int64 j; // rax
  _BYTE v7[56]; // [rsp+20h] [rbp-38h] BYREF

  for ( i = **(_QWORD ***)(a1 + 40); i != *(_QWORD **)(a1 + 40); i = (_QWORD *)j )
  {
    if ( !(unsigned __int8)PCLmWriter::PDFDocumentWriter::_IgnoreTrailerEntry(a1, i + 4) )
    {
      v5 = std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
             a2,
             (__int64)v7,
             (__int64)(i + 4));
      std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(
        (__int64 *)(*(_QWORD *)v5 + 64LL),
        i + 8);
    }
    if ( *(_BYTE *)(i[2] + 25LL) )
    {
      for ( j = i[1]; !*(_BYTE *)(j + 25) && i == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
        i = (_QWORD *)j;
    }
    else
    {
      j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min();
    }
  }
}

```

## disassembly

```asm
0x180016580  push    rbx
0x180016582  push    rbp
0x180016583  push    rsi
0x180016584  push    rdi
0x180016585  sub     rsp, 38h
0x180016589  mov     rbx, [rcx+28h]
0x18001658d  mov     rbp, rdx
0x180016590  mov     rdi, rcx
0x180016593  mov     rbx, [rbx]
0x180016596  cmp     rbx, [rdi+28h]
0x18001659a  jz      short loc_1800165FC
0x18001659c  lea     rdx, [rbx+20h]
0x1800165a0  mov     rcx, rdi
0x1800165a3  call    ?_IgnoreTrailerEntry@PDFDocumentWriter@PCLmWriter@@AEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; PCLmWriter::PDFDocumentWriter::_IgnoreTrailerEntry(std::string const &)
0x1800165a8  test    al, al
0x1800165aa  jnz     short loc_1800165CD
0x1800165ac  lea     r8, [rbx+20h]
0x1800165b0  mov     rcx, rbp
0x1800165b3  lea     rdx, [rsp+58h+var_38]
0x1800165b8  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(std::string const &)
0x1800165bd  lea     rdx, [rbx+40h]
0x1800165c1  mov     rcx, [rax]
0x1800165c4  add     rcx, 40h ; '@'
0x1800165c8  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x1800165cd  mov     rcx, [rbx+10h]
0x1800165d1  cmp     byte ptr [rcx+19h], 0
0x1800165d5  jz      short loc_1800165F2
0x1800165d7  mov     rax, [rbx+8]
0x1800165db  jmp     short loc_1800165EA
0x1800165dd  cmp     rbx, [rax+10h]
0x1800165e1  jnz     short loc_1800165F7
0x1800165e3  mov     rbx, rax
0x1800165e6  mov     rax, [rax+8]
0x1800165ea  cmp     byte ptr [rax+19h], 0
0x1800165ee  jz      short loc_1800165DD
0x1800165f0  jmp     short loc_1800165F7
0x1800165f2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x1800165f7  mov     rbx, rax
0x1800165fa  jmp     short loc_180016596
0x1800165fc  add     rsp, 38h
0x180016600  pop     rdi
0x180016601  pop     rsi
0x180016602  pop     rbp
0x180016603  pop     rbx
0x180016604  retn
```
