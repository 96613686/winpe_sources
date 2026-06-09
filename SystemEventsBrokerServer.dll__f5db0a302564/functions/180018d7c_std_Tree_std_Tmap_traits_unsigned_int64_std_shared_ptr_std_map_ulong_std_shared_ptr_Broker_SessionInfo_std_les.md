# std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *> *>)

- ea: `0x180018d7c`
- end: `0x180018e1e`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@PEAU12@@2@@Z`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD **, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018ce4`

## callees

- `0x180013520`
- `0x1800137c0`
- `0x180016b68`
- `0x180018d7c`
- `0x180018e24`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::_Erase(
        _QWORD **a1,
        __int64 *a2)
{
  __int64 v2; // r9
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi
  _QWORD *v7; // rax
  __int64 v9; // r9
  __int64 v10; // r9
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF
  __int64 v14; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a2;
  v4 = a2[1];
  v5 = *a2;
  v13 = *a2;
  v6 = 0;
  while ( v5 != v4 )
  {
    ++v6;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(&v13);
    v5 = v13;
  }
  v7 = *a1;
  v13 = v2;
  if ( v2 == *v7 && *(_BYTE *)(v4 + 25) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::clear(a1);
  }
  else
  {
    while ( v2 != v4 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(&v13);
      v14 = v9;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(&v14);
      v11 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Extract(
                        a1,
                        v10);
      std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(
        v12,
        v11);
      v2 = v13;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180018d7c  mov     [rsp+arg_10], rbx
0x180018d81  mov     [rsp+arg_18], rsi
0x180018d86  push    rdi
0x180018d87  sub     rsp, 20h
0x180018d8b  mov     r9, [rdx]
0x180018d8e  mov     rsi, rcx
0x180018d91  mov     rbx, [rdx+8]
0x180018d95  mov     rax, r9
0x180018d98  mov     [rsp+28h+arg_0], rax
0x180018d9d  xor     edi, edi
0x180018d9f  cmp     rax, rbx
0x180018da2  jz      short loc_180018DB8
0x180018da4  inc     rdi
0x180018da7  lea     rcx, [rsp+28h+arg_0]
0x180018dac  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x180018db1  mov     rax, [rsp+28h+arg_0]
0x180018db6  jmp     short loc_180018D9F
0x180018db8  mov     rax, [rsi]
0x180018dbb  mov     [rsp+28h+arg_0], r9
0x180018dc0  cmp     r9, [rax]
0x180018dc3  jnz     short loc_180018DE6
0x180018dc5  cmp     byte ptr [rbx+19h], 0
0x180018dc9  jz      short loc_180018DE6
0x180018dcb  mov     rcx, rsi
0x180018dce  call    ?clear@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>,0>>::clear(void)
0x180018dd3  mov     rbx, [rsp+28h+arg_10]
0x180018dd8  mov     rax, rdi
0x180018ddb  mov     rsi, [rsp+28h+arg_18]
0x180018de0  add     rsp, 20h
0x180018de4  pop     rdi
0x180018de5  retn
0x180018de6  cmp     r9, rbx
0x180018de9  jz      short loc_180018DD3
0x180018deb  lea     rcx, [rsp+28h+arg_0]
0x180018df0  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x180018df5  lea     rcx, [rsp+28h+arg_8]
0x180018dfa  mov     [rsp+28h+arg_8], r9
0x180018dff  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>::operator++(void)
0x180018e04  mov     rdx, r9
0x180018e07  mov     rcx, rsi
0x180018e0a  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>>>,std::_Iterator_base0>)
0x180018e0f  mov     rdx, rax
0x180018e12  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *)
0x180018e17  mov     r9, [rsp+28h+arg_0]
0x180018e1c  jmp     short loc_180018DE6
```
