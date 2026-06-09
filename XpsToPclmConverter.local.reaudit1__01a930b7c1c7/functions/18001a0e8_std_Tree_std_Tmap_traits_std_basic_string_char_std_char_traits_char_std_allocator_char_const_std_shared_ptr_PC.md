# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001a0e8`
- end: `0x18001a137`
- name: `?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180018c10`
- `0x180018fb0`
- `0x180019db0`

## callees

- `0x18000f030`
- `0x18000f124`
- `0x18001a0e8`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::find(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 *result; // rax
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]

  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
    (__int64)a1,
    &v8,
    a3);
  v5 = v9;
  if ( !std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
          v6,
          v9) )
    v5 = *a1;
  result = a2;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18001a0e8  mov     [rsp+arg_0], rbx
0x18001a0ed  mov     [rsp+arg_8], rsi
0x18001a0f2  push    rdi
0x18001a0f3  sub     rsp, 40h
0x18001a0f7  mov     rdi, rdx
0x18001a0fa  mov     rbx, r8
0x18001a0fd  lea     rdx, [rsp+48h+var_28]
0x18001a102  mov     rsi, rcx
0x18001a105  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18001a10a  mov     r8, rbx
0x18001a10d  mov     rbx, [rsp+48h+var_18]
0x18001a112  mov     rdx, rbx
0x18001a115  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::string const &)
0x18001a11a  test    al, al
0x18001a11c  jnz     short loc_18001A121
0x18001a11e  mov     rbx, [rsi]
0x18001a121  mov     rsi, [rsp+48h+arg_8]
0x18001a126  mov     rax, rdi
0x18001a129  mov     [rdi], rbx
0x18001a12c  mov     rbx, [rsp+48h+arg_0]
0x18001a131  add     rsp, 40h
0x18001a135  pop     rdi
0x18001a136  retn
```
