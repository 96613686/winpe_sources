# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Try_emplace<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180014470`
- end: `0x180014530`
- name: `??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180015b6c`

## callees

- `0x18000e7fc`
- `0x18000f030`
- `0x18000f124`
- `0x18000f62c`
- `0x180010464`
- `0x180014470`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800144c0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800144c0`

## pseudocode

```c
__int64 __fastcall std::map<std::string,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // r9d
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rbx
  _BYTE v13[16]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
    (__int64)a1,
    &v14,
    a3);
  v6 = v15;
  if ( std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
         v7,
         v15) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x333333333333333LL )
      std::_Xlength_error("map/set too long");
    v9 = *a1;
    v16 = a3;
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
            (unsigned int)v13,
            (_DWORD)a1,
            v9,
            v8,
            (__int64)&v16);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(v13);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(
                      (__int64)a1,
                      (__int64)&v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180014470  push    rbx
0x180014472  push    rbp
0x180014473  push    rsi
0x180014474  push    rdi
0x180014475  sub     rsp, 68h
0x180014479  mov     rdi, rdx
0x18001447c  mov     rbp, r8
0x18001447f  lea     rdx, [rsp+88h+var_48]
0x180014484  mov     rsi, rcx
0x180014487  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18001448c  mov     rbx, [rsp+88h+var_38]
0x180014491  mov     r8, rbp
0x180014494  mov     rdx, rbx
0x180014497  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::string const &)
0x18001449c  test    al, al
0x18001449e  jz      short loc_1800144A9
0x1800144a0  mov     [rdi], rbx
0x1800144a3  mov     byte ptr [rdi+8], 0
0x1800144a7  jmp     short loc_180014524
0x1800144a9  mov     rax, 333333333333333h
0x1800144b3  cmp     [rsi+8], rax
0x1800144b7  jnz     short loc_1800144C7
0x1800144b9  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800144c0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800144c7  mov     r8, [rsi]
0x1800144ca  lea     rax, [rsp+88h+arg_18]
0x1800144d2  mov     rdx, rsi
0x1800144d5  mov     [rsp+88h+var_68], rax
0x1800144da  lea     rcx, [rsp+88h+var_58]
0x1800144df  mov     [rsp+88h+arg_18], rbp
0x1800144e7  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::piecewise_construct_t const &,std::tuple<std::string const &> &&,std::tuple<> &&)
0x1800144ec  lea     rcx, [rsp+88h+var_58]
0x1800144f1  mov     rbx, [rax+8]
0x1800144f5  mov     qword ptr [rax+8], 0
0x1800144fd  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
0x180014502  movups  xmm0, [rsp+88h+var_48]
0x180014507  mov     r8, rbx
0x18001450a  lea     rdx, [rsp+88h+var_48]
0x18001450f  mov     rcx, rsi
0x180014512  movdqu  [rsp+88h+var_48], xmm0
0x180014518  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const)
0x18001451d  mov     [rdi], rax
0x180014520  mov     byte ptr [rdi+8], 1
0x180014524  mov     rax, rdi
0x180014527  add     rsp, 68h
0x18001452b  pop     rdi
0x18001452c  pop     rsi
0x18001452d  pop     rbp
0x18001452e  pop     rbx
0x18001452f  retn
```
