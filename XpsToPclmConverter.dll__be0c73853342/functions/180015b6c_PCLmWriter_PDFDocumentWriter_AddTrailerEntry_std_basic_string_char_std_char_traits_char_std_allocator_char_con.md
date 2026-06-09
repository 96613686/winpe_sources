# PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::shared_ptr<PCLmWriter::IObject const>)

- ea: `0x180015b6c`
- end: `0x180015be9`
- name: `?_AddTrailerEntry@PDFDocumentWriter@PCLmWriter@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@4@@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800152f4`

## callees

- `0x18000f030`
- `0x18000f124`
- `0x18000f8d4`
- `0x1800101cc`
- `0x180014470`
- `0x180015b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::PDFDocumentWriter::_AddTrailerEntry(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 *v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]

  v5 = (__int64 *)(a1 + 40);
  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
    a1 + 40,
    v10,
    a2);
  v6 = v11;
  if ( !std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
          v7,
          v11)
    || v6 == *v5 )
  {
    v8 = (__int64 *)(*(_QWORD *)std::map<std::string,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
                                  v5,
                                  (__int64)v10,
                                  a2)
                   + 64LL);
  }
  else
  {
    v8 = (__int64 *)(v6 + 64);
  }
  std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(v8, a3);
  v9 = (std::_Ref_count_base *)a3[1];
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
}

```

## disassembly

```asm
0x180015b6c  mov     [rsp+arg_10], r8
0x180015b71  push    rbx
0x180015b72  push    rbp
0x180015b73  push    rsi
0x180015b74  push    rdi
0x180015b75  sub     rsp, 48h
0x180015b79  mov     rbx, r8
0x180015b7c  mov     rbp, rdx
0x180015b7f  lea     rsi, [rcx+28h]
0x180015b83  mov     r8, rdx
0x180015b86  lea     rdx, [rsp+68h+var_48]
0x180015b8b  mov     rcx, rsi
0x180015b8e  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x180015b93  mov     r8, rbp
0x180015b96  mov     rdi, [rsp+68h+var_38]
0x180015b9b  mov     rdx, rdi
0x180015b9e  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::string const &)
0x180015ba3  test    al, al
0x180015ba5  jz      short loc_180015BB2
0x180015ba7  cmp     rdi, [rsi]
0x180015baa  jz      short loc_180015BB2
0x180015bac  lea     rcx, [rdi+40h]
0x180015bb0  jmp     short loc_180015BC9
0x180015bb2  mov     r8, rbp
0x180015bb5  lea     rdx, [rsp+68h+var_48]
0x180015bba  mov     rcx, rsi
0x180015bbd  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(std::string const &)
0x180015bc2  mov     rcx, [rax]
0x180015bc5  add     rcx, 40h ; '@'
0x180015bc9  mov     rdx, rbx
0x180015bcc  call    ??$?4$$CBVIDictionaryObject@PCLmWriter@@$0A@@?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAAAEAV01@AEBV?$shared_ptr@$$CBVIDictionaryObject@PCLmWriter@@@1@@Z; std::shared_ptr<PCLmWriter::IObject const>::operator=<PCLmWriter::IDictionaryObject const,0>(std::shared_ptr<PCLmWriter::IDictionaryObject const> const &)
0x180015bd1  nop
0x180015bd2  mov     rcx, [rbx+8]; this
0x180015bd6  test    rcx, rcx
0x180015bd9  jz      short loc_180015BE0
0x180015bdb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015be0  add     rsp, 48h
0x180015be4  pop     rdi
0x180015be5  pop     rsi
0x180015be6  pop     rbp
0x180015be7  pop     rbx
0x180015be8  retn
```
