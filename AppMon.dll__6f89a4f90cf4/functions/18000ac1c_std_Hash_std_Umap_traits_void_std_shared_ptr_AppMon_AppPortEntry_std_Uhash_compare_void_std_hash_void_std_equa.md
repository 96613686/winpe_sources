# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Try_emplace<void *,>(void * &&)

- ea: `0x18000ac1c`
- end: `0x18000ad8d`
- name: `??$_Try_emplace@PEAX$$V@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@_N@1@$$QEAPEAX@Z`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b990`

## callees

- `0x1800026fc`
- `0x18000a054`
- `0x18000aa58`
- `0x18000ac1c`
- `0x18000b278`
- `0x18000cb08`
- `0x18000d6d0`
- `0x18000d7d8`
- `0x18000db18`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ac85`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ac85`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Try_emplace<void *,>(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v5; // rsi
  __int64 v6; // rcx
  char *v7; // r14
  unsigned __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 *v16; // [rsp+30h] [rbp-20h] BYREF
  char *v17; // [rsp+38h] [rbp-18h]
  __int128 v18; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 *v19; // [rsp+70h] [rbp+20h] BYREF

  v19 = a1;
  v5 = std::_Conditionally_enabled_hash<void *,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(
    v6,
    &v18,
    a3,
    v5);
  if ( *((_QWORD *)&v18 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v18 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_180016580 == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v16 = &qword_180016578;
    v7 = (char *)operator new(0x28u);
    v17 = v7;
    v19 = a3;
    ____0V__tuple___QEAPEAX_std__V__tuple___V_1__0A___Z_S___pair_QEAXV__shared_ptr_VAppPortEntry_AppMon___std___std__AEAA_AEAV__tuple___QEAPEAX_1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v7 + 16,
      &v19);
    v8 = qword_180016580 + 1;
    if ( qword_180016580 + 1 < 0 )
      v9 = (float)(int)(v8 & 1 | (v8 >> 1)) + (float)(int)(v8 & 1 | (v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = qword_1800165A8;
    if ( qword_1800165A8 < 0 )
    {
      v10 = qword_1800165A8 & 1;
      v11 = (float)(int)(v10 | ((unsigned __int64)qword_1800165A8 >> 1))
          + (float)(int)(v10 | ((unsigned __int64)qword_1800165A8 >> 1));
    }
    else
    {
      v11 = (float)(int)qword_1800165A8;
    }
    if ( (float)(v9 / v11) > *(float *)&AppMon::PortManager::m_openedHandleTable )
    {
      v12 = std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Desired_grow_bucket_count();
      std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Forced_rehash(
        v13,
        v12);
      v18 = *(_OWORD *)std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(
                         v14,
                         &v18,
                         v7 + 16,
                         v5);
    }
    v17 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Insert_new_node_before(
                      v10,
                      v5,
                      v18,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(&v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18000ac1c  mov     [rsp-18h+arg_8], rbx
0x18000ac21  mov     [rsp-18h+arg_10], rsi
0x18000ac26  mov     [rsp-18h+arg_0], rcx
0x18000ac2b  push    rbp
0x18000ac2c  push    rdi
0x18000ac2d  push    r14
0x18000ac2f  mov     rbp, rsp
0x18000ac32  sub     rsp, 50h
0x18000ac36  mov     rdi, r8
0x18000ac39  mov     rbx, rdx
0x18000ac3c  mov     rcx, r8; unsigned __int8 *
0x18000ac3f  call    ??R?$_Conditionally_enabled_hash@PEAX$00@std@@SA_KAEBQEAX@Z; std::_Conditionally_enabled_hash<void *,1>::operator()(void * const &)
0x18000ac44  mov     rsi, rax
0x18000ac47  mov     r9, rax
0x18000ac4a  mov     r8, rdi
0x18000ac4d  lea     rdx, [rbp+var_10]
0x18000ac51  call    ??$_Find_last@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@AEBQEAX_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(void * const &,unsigned __int64)
0x18000ac56  mov     rdx, qword ptr [rbp+var_10+8]
0x18000ac5a  test    rdx, rdx
0x18000ac5d  jz      short loc_18000AC6B
0x18000ac5f  mov     [rbx], rdx
0x18000ac62  mov     byte ptr [rbx+8], 0
0x18000ac66  jmp     loc_18000AD75
0x18000ac6b  mov     rax, 666666666666666h
0x18000ac75  cmp     cs:qword_180016580, rax
0x18000ac7c  jnz     short loc_18000AC8C
0x18000ac7e  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000ac85  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ac8c  lea     rax, qword_180016578
0x18000ac93  mov     [rbp+var_20], rax
0x18000ac97  mov     [rbp+var_18], 0
0x18000ac9f  mov     ecx, 28h ; '('; Size
0x18000aca4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aca9  mov     r14, rax
0x18000acac  mov     [rbp+var_18], rax
0x18000acb0  mov     [rbp+arg_0], rdi
0x18000acb4  lea     rdx, [rbp+arg_0]
0x18000acb8  lea     rcx, [rax+10h]
0x18000acbc  call    ??$?0V?$tuple@$$QEAPEAX@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@AEAA@AEAV?$tuple@$$QEAPEAX@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x18000acc1  nop
0x18000acc2  mov     rdx, cs:qword_180016580
0x18000acc9  add     rdx, 1
0x18000accd  xorps   xmm0, xmm0
0x18000acd0  js      short loc_18000ACD9
0x18000acd2  cvtsi2ss xmm0, rdx
0x18000acd7  jmp     short loc_18000ACF1
0x18000acd9  mov     rcx, rdx
0x18000acdc  shr     rcx, 1
0x18000acdf  mov     rax, rdx
0x18000ace2  and     eax, 1
0x18000ace5  or      rcx, rax
0x18000ace8  cvtsi2ss xmm0, rcx
0x18000aced  addss   xmm0, xmm0
0x18000acf1  mov     rcx, cs:qword_1800165A8
0x18000acf8  xorps   xmm1, xmm1
0x18000acfb  test    rcx, rcx
0x18000acfe  js      short loc_18000AD07
0x18000ad00  cvtsi2ss xmm1, rcx
0x18000ad05  jmp     short loc_18000AD1C
0x18000ad07  mov     rax, rcx
0x18000ad0a  shr     rax, 1
0x18000ad0d  and     ecx, 1
0x18000ad10  or      rax, rcx
0x18000ad13  cvtsi2ss xmm1, rax
0x18000ad18  addss   xmm1, xmm1
0x18000ad1c  divss   xmm0, xmm1
0x18000ad20  comiss  xmm0, cs:?m_openedHandleTable@PortManager@AppMon@@0V?$unordered_map@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@U?$hash@PEAX@2@U?$equal_to@PEAX@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@@std@@A; std::unordered_map<void *,std::shared_ptr<AppMon::AppPortEntry>> AppMon::PortManager::m_openedHandleTable
0x18000ad27  jbe     short loc_18000AD4E
0x18000ad29  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000ad2e  mov     rdx, rax
0x18000ad31  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000ad36  mov     r9, rsi
0x18000ad39  lea     r8, [r14+10h]
0x18000ad3d  lea     rdx, [rbp+var_10]
0x18000ad41  call    ??$_Find_last@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@AEBQEAX_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(void * const &,unsigned __int64)
0x18000ad46  movups  xmm0, xmmword ptr [rax]
0x18000ad49  movdqu  [rbp+var_10], xmm0
0x18000ad4e  mov     [rbp+var_18], 0
0x18000ad56  mov     r9, r14
0x18000ad59  mov     r8, qword ptr [rbp+var_10]
0x18000ad5d  mov     rdx, rsi
0x18000ad60  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const)
0x18000ad65  mov     [rbx], rax
0x18000ad68  mov     byte ptr [rbx+8], 1
0x18000ad6c  lea     rcx, [rbp+var_20]
0x18000ad70  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(void)
0x18000ad75  mov     rax, rbx
0x18000ad78  lea     r11, [rsp+50h+var_s0]
0x18000ad7d  mov     rbx, [r11+28h]
0x18000ad81  mov     rsi, [r11+30h]
0x18000ad85  mov     rsp, r11
0x18000ad88  pop     r14
0x18000ad8a  pop     rdi
0x18000ad8b  pop     rbp
0x18000ad8c  retn
```
