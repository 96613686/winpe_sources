# std::map<uint,std::shared_ptr<PCLmWriter::IXrefEntry>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>>::_Try_emplace<uint,>(uint &&)

- ea: `0x180014538`
- end: `0x180014628`
- name: `??$_Try_emplace@I$$V@?$map@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800159d0`
- `0x180015bf0`

## callees

- `0x18000ea34`
- `0x18000ec28`
- `0x180010464`
- `0x180013d40`
- `0x180014538`
- `0x180014700`
- `0x180014898`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014588`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014588`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::map<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>>::_Try_emplace<unsigned int,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  _DWORD *v5; // r8
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  _DWORD *v10; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h]
  __int64 v14; // [rsp+B8h] [rbp+40h] BYREF

  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PCLmWriter::IXrefEntry>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>>,0>>::_Find_lower_bound<unsigned int>(
    a1,
    &v12,
    a3);
  if ( *(_BYTE *)(v13 + 25) || *v5 < *(_DWORD *)(v13 + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v10 = v5;
    v14 = *a1;
    v11 = (unsigned __int64)a1;
    v6 = std::_Allocate<16,std::_Default_allocate_traits>(56);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::construct<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,std::piecewise_construct_t const &,std::tuple<unsigned int &&>,std::tuple<>>(
      v7,
      v6 + 32,
      v8,
      &v10);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v6,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v6 + 8,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
      v6 + 16,
      &v14);
    *(_WORD *)(v6 + 24) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(
                      a1,
                      &v11,
                      v6);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v13;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180014538  push    rbp
0x18001453a  push    rbx
0x18001453b  push    rsi
0x18001453c  push    rdi
0x18001453d  mov     rbp, rsp
0x180014540  sub     rsp, 78h
0x180014544  mov     rdi, rdx
0x180014547  mov     rsi, rcx
0x18001454a  lea     rdx, [rbp+var_28]
0x18001454e  call    ??$_Find_lower_bound@I@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@1@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PCLmWriter::IXrefEntry>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>>,0>>::_Find_lower_bound<uint>(uint const &)
0x180014553  mov     rdx, [rbp+var_18]
0x180014557  cmp     byte ptr [rdx+19h], 0
0x18001455b  jnz     short loc_180014571
0x18001455d  mov     eax, [rdx+20h]
0x180014560  cmp     [r8], eax
0x180014563  jb      short loc_180014571
0x180014565  mov     [rdi], rdx
0x180014568  mov     byte ptr [rdi+8], 0
0x18001456c  jmp     loc_18001461C
0x180014571  mov     rax, 492492492492492h
0x18001457b  cmp     [rsi+8], rax
0x18001457f  jnz     short loc_18001458F
0x180014581  lea     rcx, aMapSetTooLong; "map/set too long"
0x180014588  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001458f  mov     [rbp+var_48], r8
0x180014593  mov     rax, [rsi]
0x180014596  mov     [rbp+arg_18], rax
0x18001459a  mov     qword ptr [rbp+var_38], rsi
0x18001459e  mov     qword ptr [rbp+var_38+8], 0
0x1800145a6  mov     ecx, 38h ; '8'
0x1800145ab  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800145b0  mov     rbx, rax
0x1800145b3  lea     rdx, [rax+20h]
0x1800145b7  lea     r9, [rbp+var_48]
0x1800145bb  call    ??$construct@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@$$QEAI@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAI@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::construct<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,std::piecewise_construct_t const &,std::tuple<uint &&>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>> &,std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>> * const,std::piecewise_construct_t const &,std::tuple<uint &&> &&,std::tuple<> &&)
0x1800145c0  lea     rdx, [rbp+arg_18]
0x1800145c4  mov     rcx, rbx
0x1800145c7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x1800145cc  lea     rcx, [rbx+8]
0x1800145d0  lea     rdx, [rbp+arg_18]
0x1800145d4  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x1800145d9  lea     rcx, [rbx+10h]
0x1800145dd  lea     rdx, [rbp+arg_18]
0x1800145e1  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x1800145e6  mov     word ptr [rbx+18h], 0
0x1800145ec  mov     qword ptr [rbp+var_38+8], 0
0x1800145f4  lea     rcx, [rbp+var_38]
0x1800145f8  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VIXrefEntry@PCLmWriter@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,std::shared_ptr<PCLmWriter::IXrefEntry>>,void *>>>(void)
0x1800145fd  movups  xmm0, [rbp+var_28]
0x180014601  movdqu  [rbp+var_38], xmm0
0x180014606  mov     r8, rbx
0x180014609  lea     rdx, [rbp+var_38]
0x18001460d  mov     rcx, rsi
0x180014610  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * const)
0x180014615  mov     [rdi], rax
0x180014618  mov     byte ptr [rdi+8], 1
0x18001461c  mov     rax, rdi
0x18001461f  add     rsp, 78h
0x180014623  pop     rdi
0x180014624  pop     rsi
0x180014625  pop     rbx
0x180014626  pop     rbp
0x180014627  retn
```
