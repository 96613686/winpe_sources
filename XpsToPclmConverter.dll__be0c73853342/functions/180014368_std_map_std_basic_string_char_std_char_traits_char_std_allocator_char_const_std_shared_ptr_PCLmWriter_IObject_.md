# std::map<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Try_emplace<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &&)

- ea: `0x180014368`
- end: `0x18001446a`
- name: `??$_Try_emplace@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@_N@1@$$QEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800149b0`

## callees

- `0x18000ec28`
- `0x18000f030`
- `0x18000f124`
- `0x18000f2ac`
- `0x18000f360`
- `0x18000f62c`
- `0x180010188`
- `0x180010464`
- `0x180014368`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::_Try_emplace<std::string const,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rbx
  __int128 v12; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v13[8]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int128 v15; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h]
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(
    a1,
    &v15);
  v6 = v16;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(
                          v7,
                          v16,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Check_grow_by_1(a1);
    *(_QWORD *)&v12 = a3;
    v17 = *a1;
    std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
      v13,
      a1);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::construct<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(
      v8,
      v14 + 32,
      v9,
      &v12);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v14,
      &v17);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v14 + 8,
      &v17);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v14 + 16,
      &v17);
    *(_BYTE *)(v14 + 24) = 0;
    *(_BYTE *)(v14 + 25) = 0;
    v10 = v14;
    v14 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(v13);
    v12 = v15;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(
                      a1,
                      &v12,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180014368  mov     [rsp-18h+arg_0], rbx
0x18001436d  mov     [rsp-18h+arg_8], rsi
0x180014372  push    rbp
0x180014373  push    rdi
0x180014374  push    r14
0x180014376  mov     rbp, rsp
0x180014379  sub     rsp, 70h
0x18001437d  mov     rsi, r8
0x180014380  mov     rdi, rdx
0x180014383  mov     r14, rcx
0x180014386  lea     rdx, [rbp+var_20]
0x18001438a  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18001438f  mov     r8, rsi
0x180014392  mov     rbx, [rbp+var_10]
0x180014396  mov     rdx, rbx
0x180014399  call    ??$_Lower_bound_duplicate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Lower_bound_duplicate<std::string>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const,std::string const &)
0x18001439e  test    al, al
0x1800143a0  jz      short loc_1800143AE
0x1800143a2  mov     [rdi], rbx
0x1800143a5  mov     byte ptr [rdi+8], 0
0x1800143a9  jmp     loc_180014452
0x1800143ae  mov     rcx, r14
0x1800143b1  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Check_grow_by_1(void)
0x1800143b6  mov     qword ptr [rbp+var_40], rsi
0x1800143ba  mov     rax, [r14]
0x1800143bd  mov     [rbp+arg_18], rax
0x1800143c1  mov     rdx, r14
0x1800143c4  lea     rcx, [rbp+var_30]
0x1800143c8  call    ??0?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x1800143cd  nop
0x1800143ce  mov     rdx, [rbp+var_28]
0x1800143d2  add     rdx, 20h ; ' '
0x1800143d6  lea     r9, [rbp+var_40]
0x1800143da  call    ??$construct@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::construct<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &,std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>> * const,std::piecewise_construct_t const &,std::tuple<std::string const &> &&,std::tuple<> &&)
0x1800143df  lea     rdx, [rbp+arg_18]
0x1800143e3  mov     rcx, [rbp+var_28]
0x1800143e7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x1800143ec  mov     rcx, [rbp+var_28]
0x1800143f0  add     rcx, 8
0x1800143f4  lea     rdx, [rbp+arg_18]
0x1800143f8  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x1800143fd  mov     rcx, [rbp+var_28]
0x180014401  add     rcx, 10h
0x180014405  lea     rdx, [rbp+arg_18]
0x180014409  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x18001440e  mov     rcx, [rbp+var_28]
0x180014412  mov     byte ptr [rcx+18h], 0
0x180014416  mov     rax, [rbp+var_28]
0x18001441a  mov     byte ptr [rax+19h], 0
0x18001441e  mov     rbx, [rbp+var_28]
0x180014422  mov     [rbp+var_28], 0
0x18001442a  lea     rcx, [rbp+var_30]
0x18001442e  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
0x180014433  movups  xmm0, [rbp+var_20]
0x180014437  movdqu  [rbp+var_40], xmm0
0x18001443c  mov     r8, rbx
0x18001443f  lea     rdx, [rbp+var_40]
0x180014443  mov     rcx, r14
0x180014446  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const)
0x18001444b  mov     [rdi], rax
0x18001444e  mov     byte ptr [rdi+8], 1
0x180014452  mov     rax, rdi
0x180014455  lea     r11, [rsp+70h+var_s0]
0x18001445a  mov     rbx, [r11+20h]
0x18001445e  mov     rsi, [r11+28h]
0x180014462  mov     rsp, r11
0x180014465  pop     r14
0x180014467  pop     rdi
0x180014468  pop     rbp
0x180014469  retn
```
