# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Try_emplace<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18000f1b8`
- end: `0x18000f262`
- name: `??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000fe14`
- `0x180016580`
- `0x1800199e0`

## callees

- `0x18000e7fc`
- `0x18000f030`
- `0x18000f124`
- `0x18000f1b8`
- `0x18000f62c`
- `0x180010188`
- `0x180010464`

## pseudocode

```c
__int64 __fastcall std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rbx
  _BYTE v13[16]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+A8h] [rbp+20h] BYREF

  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
    a1,
    &v14);
  v6 = v15;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
                          v7,
                          v15,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Check_grow_by_1(a1);
    v8 = *a1;
    v16 = a3;
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
            (unsigned int)v13,
            (_DWORD)a1,
            v8,
            v9,
            (__int64)&v16);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(v13);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(
                      a1,
                      &v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f1b8  push    rbx
0x18000f1ba  push    rbp
0x18000f1bb  push    rsi
0x18000f1bc  push    rdi
0x18000f1bd  sub     rsp, 68h
0x18000f1c1  mov     rdi, rdx
0x18000f1c4  mov     rbp, r8
0x18000f1c7  lea     rdx, [rsp+88h+var_48]
0x18000f1cc  mov     rsi, rcx
0x18000f1cf  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18000f1d4  mov     rbx, [rsp+88h+var_38]
0x18000f1d9  mov     r8, rbp
0x18000f1dc  mov     rdx, rbx
0x18000f1df  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::string const &)
0x18000f1e4  test    al, al
0x18000f1e6  jz      short loc_18000F1F1
0x18000f1e8  mov     [rdi], rbx
0x18000f1eb  mov     byte ptr [rdi+8], 0
0x18000f1ef  jmp     short loc_18000F256
0x18000f1f1  mov     rcx, rsi
0x18000f1f4  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Check_grow_by_1(void)
0x18000f1f9  mov     r8, [rsi]
0x18000f1fc  lea     rax, [rsp+88h+arg_18]
0x18000f204  mov     rdx, rsi
0x18000f207  mov     [rsp+88h+var_68], rax
0x18000f20c  lea     rcx, [rsp+88h+var_58]
0x18000f211  mov     [rsp+88h+arg_18], rbp
0x18000f219  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::piecewise_construct_t const &,std::tuple<std::string const &> &&,std::tuple<> &&)
0x18000f21e  lea     rcx, [rsp+88h+var_58]
0x18000f223  mov     rbx, [rax+8]
0x18000f227  mov     qword ptr [rax+8], 0
0x18000f22f  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
0x18000f234  movups  xmm0, [rsp+88h+var_48]
0x18000f239  mov     r8, rbx
0x18000f23c  lea     rdx, [rsp+88h+var_48]
0x18000f241  mov     rcx, rsi
0x18000f244  movdqu  [rsp+88h+var_48], xmm0
0x18000f24a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const)
0x18000f24f  mov     [rdi], rax
0x18000f252  mov     byte ptr [rdi+8], 1
0x18000f256  mov     rax, rdi
0x18000f259  add     rsp, 68h
0x18000f25d  pop     rdi
0x18000f25e  pop     rsi
0x18000f25f  pop     rbp
0x18000f260  pop     rbx
0x18000f261  retn
```
