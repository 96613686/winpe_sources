# std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>,0>>::_Emplace<std::pair<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>(std::pair<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>> &&)

- ea: `0x180018e54`
- end: `0x180018f20`
- name: `??$_Emplace@U?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@1@@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012b8c`

## callees

- `0x1800133f0`
- `0x180018e54`
- `0x180018f28`
- `0x180018f58`
- `0x180018fe8`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Emplace<std::pair<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // r9
  int v4; // esi
  __int64 v8; // rax
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v13; // [rsp+20h] [rbp-58h] BYREF
  int v14; // [rsp+28h] [rbp-50h]
  int v15; // [rsp+2Ch] [rbp-4Ch]
  _BYTE v16[72]; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a1;
  v4 = 0;
  v8 = *(_QWORD *)(*a1 + 8);
  if ( *(_BYTE *)(v8 + 25) )
  {
    v9 = *(_QWORD *)(*a1 + 8);
  }
  else
  {
    do
    {
      v9 = v8;
      if ( *(_QWORD *)(v8 + 32) >= *a3 )
      {
        v4 = 1;
        v3 = v8;
      }
      else
      {
        v4 = 0;
        v8 += 16;
      }
      v8 = *(_QWORD *)v8;
    }
    while ( !*(_BYTE *)(v8 + 25) );
  }
  if ( *(_BYTE *)(v3 + 25) || *a3 < *(_QWORD *)(v3 + 32) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Check_grow_by_1(a1);
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(
            (__int64)v16,
            (__int64)a1,
            *a1,
            a3);
    v11 = *(_QWORD *)(v10 + 8);
    *(_QWORD *)(v10 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(v16);
    v13 = v9;
    v14 = v4;
    v15 = 0;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Insert_node(
                      a1,
                      &v13,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v3;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180018e54  push    rbx
0x180018e56  push    rbp
0x180018e57  push    rsi
0x180018e58  push    rdi
0x180018e59  push    r12
0x180018e5b  push    r14
0x180018e5d  sub     rsp, 48h
0x180018e61  mov     r9, [rcx]
0x180018e64  xor     esi, esi
0x180018e66  xor     r12d, r12d
0x180018e69  mov     rbx, r8
0x180018e6c  mov     rdi, rdx
0x180018e6f  mov     r14, rcx
0x180018e72  mov     rax, [r9+8]
0x180018e76  cmp     [rax+19h], sil
0x180018e7a  jnz     short loc_180018EA3
0x180018e7c  mov     rcx, [r8]
0x180018e7f  mov     rbp, rax
0x180018e82  cmp     [rax+20h], rcx
0x180018e86  jnb     short loc_180018E90
0x180018e88  xor     esi, esi
0x180018e8a  add     rax, 10h
0x180018e8e  jmp     short loc_180018E98
0x180018e90  mov     esi, 1
0x180018e95  mov     r9, rax
0x180018e98  mov     rax, [rax]
0x180018e9b  cmp     [rax+19h], r12b
0x180018e9f  jz      short loc_180018E7F
0x180018ea1  jmp     short loc_180018EA6
0x180018ea3  mov     rbp, rax
0x180018ea6  cmp     [r9+19h], r12b
0x180018eaa  jnz     short loc_180018EBE
0x180018eac  mov     rax, [r9+20h]
0x180018eb0  cmp     [r8], rax
0x180018eb3  jb      short loc_180018EBE
0x180018eb5  mov     [rdx], r9
0x180018eb8  mov     [rdx+8], r12b
0x180018ebc  jmp     short loc_180018F10
0x180018ebe  mov     rcx, r14
0x180018ec1  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Check_grow_by_1(void)
0x180018ec6  mov     r8, [r14]
0x180018ec9  lea     rcx, [rsp+78h+var_48]
0x180018ece  mov     r9, rbx
0x180018ed1  mov     rdx, r14
0x180018ed4  call    ??$?0U?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@1@$$QEAU?$pair@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *,std::pair<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>> &&)
0x180018ed9  lea     rcx, [rsp+78h+var_48]
0x180018ede  mov     rbx, [rax+8]
0x180018ee2  mov     [rax+8], r12
0x180018ee6  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(void)
0x180018eeb  mov     r8, rbx
0x180018eee  mov     [rsp+78h+var_58], rbp
0x180018ef3  lea     rdx, [rsp+78h+var_58]
0x180018ef8  mov     [rsp+78h+var_50], esi
0x180018efc  mov     rcx, r14
0x180018eff  mov     [rsp+78h+var_4C], r12d
0x180018f04  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *> * const)
0x180018f09  mov     [rdi], rax
0x180018f0c  mov     byte ptr [rdi+8], 1
0x180018f10  mov     rax, rdi
0x180018f13  add     rsp, 48h
0x180018f17  pop     r14
0x180018f19  pop     r12
0x180018f1b  pop     rdi
0x180018f1c  pop     rsi
0x180018f1d  pop     rbp
0x180018f1e  pop     rbx
0x180018f1f  retn
```
