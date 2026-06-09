# std::map<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)

- ea: `0x180018928`
- end: `0x180018a02`
- name: `??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018754`

## callees

- `0x1800133f0`
- `0x180017ad4`
- `0x180018928`
- `0x180018f28`
- `0x180018fe8`
- `0x1800191ec`

## pseudocode

```c
__int64 __fastcall std::map<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>::_Try_emplace<unsigned __int64 const &,>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rbx
  _BYTE v11[8]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h]
  __int128 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h]

  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Find_lower_bound<unsigned __int64>(
    a1,
    &v13,
    a3);
  if ( *(_BYTE *)(v14 + 25) || *v6 < *(_QWORD *)(v14 + 32) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Check_grow_by_1(a1);
    v7 = *a1;
    std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(
      v11,
      a1);
    v8 = v12;
    *(_QWORD *)(v12 + 32) = *a3;
    *(_QWORD *)(v8 + 40) = 0;
    *(_QWORD *)(v8 + 48) = 0;
    *(_QWORD *)v12 = v7;
    *(_QWORD *)(v12 + 8) = v7;
    *(_QWORD *)(v12 + 16) = v7;
    *(_BYTE *)(v12 + 24) = 0;
    *(_BYTE *)(v12 + 25) = 0;
    v9 = v12;
    v12 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(v11);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Insert_node(
                      a1,
                      &v13,
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v14;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180018928  push    rbp
0x18001892a  push    rbx
0x18001892b  push    rsi
0x18001892c  push    rdi
0x18001892d  push    r14
0x18001892f  mov     rbp, rsp
0x180018932  sub     rsp, 50h
0x180018936  mov     rdi, rdx
0x180018939  mov     rsi, r8
0x18001893c  lea     rdx, [rbp+var_20]
0x180018940  mov     r14, rcx
0x180018943  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x180018948  mov     rdx, [rbp+var_10]
0x18001894c  cmp     byte ptr [rdx+19h], 0
0x180018950  jnz     short loc_180018967
0x180018952  mov     rax, [rdx+20h]
0x180018956  cmp     [r8], rax
0x180018959  jb      short loc_180018967
0x18001895b  mov     [rdi], rdx
0x18001895e  mov     byte ptr [rdi+8], 0
0x180018962  jmp     loc_1800189F4
0x180018967  mov     rcx, r14
0x18001896a  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Check_grow_by_1(void)
0x18001896f  mov     rbx, [r14]
0x180018972  lea     rcx, [rbp+var_30]
0x180018976  mov     rdx, r14
0x180018979  call    ??0?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>> &)
0x18001897e  mov     rcx, [rbp+var_28]
0x180018982  mov     rax, [rsi]
0x180018985  mov     [rcx+20h], rax
0x180018989  mov     qword ptr [rcx+28h], 0
0x180018991  mov     qword ptr [rcx+30h], 0
0x180018999  lea     rcx, [rbp+var_30]
0x18001899d  mov     rax, [rbp+var_28]
0x1800189a1  mov     [rax], rbx
0x1800189a4  mov     rax, [rbp+var_28]
0x1800189a8  mov     [rax+8], rbx
0x1800189ac  mov     rax, [rbp+var_28]
0x1800189b0  mov     [rax+10h], rbx
0x1800189b4  mov     rax, [rbp+var_28]
0x1800189b8  mov     byte ptr [rax+18h], 0
0x1800189bc  mov     rax, [rbp+var_28]
0x1800189c0  mov     byte ptr [rax+19h], 0
0x1800189c4  mov     rbx, [rbp+var_28]
0x1800189c8  mov     [rbp+var_28], 0
0x1800189d0  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(void)
0x1800189d5  movups  xmm0, [rbp+var_20]
0x1800189d9  mov     r8, rbx
0x1800189dc  lea     rdx, [rbp+var_20]
0x1800189e0  mov     rcx, r14
0x1800189e3  movdqu  [rbp+var_20], xmm0
0x1800189e8  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> * const)
0x1800189ed  mov     [rdi], rax
0x1800189f0  mov     byte ptr [rdi+8], 1
0x1800189f4  mov     rax, rdi
0x1800189f7  add     rsp, 50h
0x1800189fb  pop     r14
0x1800189fd  pop     rdi
0x1800189fe  pop     rsi
0x1800189ff  pop     rbx
0x180018a00  pop     rbp
0x180018a01  retn
```
