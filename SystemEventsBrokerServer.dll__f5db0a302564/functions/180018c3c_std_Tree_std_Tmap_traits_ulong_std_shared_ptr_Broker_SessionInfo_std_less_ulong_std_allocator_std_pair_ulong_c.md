# std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *>)

- ea: `0x180018c3c`
- end: `0x180018cde`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@PEAU12@@2@@Z`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD **, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018ba8`

## callees

- `0x180006d90`
- `0x180017294`
- `0x180017700`
- `0x180018c3c`
- `0x180018e24`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Erase(
        _QWORD **a1,
        __int64 *a2)
{
  __int64 v2; // r10
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdi
  _QWORD *v7; // rax
  __int64 v9; // r10
  __int64 v10; // r10
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
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v13);
    v5 = v13;
  }
  v7 = *a1;
  v13 = v2;
  if ( v2 == *v7 && *(_BYTE *)(v4 + 25) )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::clear(a1);
  }
  else
  {
    while ( v2 != v4 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v13);
      v14 = v9;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(&v14);
      v11 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>::_Extract(
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
0x180018c3c  mov     [rsp+arg_10], rbx
0x180018c41  mov     [rsp+arg_18], rsi
0x180018c46  push    rdi
0x180018c47  sub     rsp, 20h
0x180018c4b  mov     r10, [rdx]
0x180018c4e  mov     rsi, rcx
0x180018c51  mov     rbx, [rdx+8]
0x180018c55  mov     rax, r10
0x180018c58  mov     [rsp+28h+arg_0], rax
0x180018c5d  xor     edi, edi
0x180018c5f  cmp     rax, rbx
0x180018c62  jz      short loc_180018C78
0x180018c64  inc     rdi
0x180018c67  lea     rcx, [rsp+28h+arg_0]
0x180018c6c  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180018c71  mov     rax, [rsp+28h+arg_0]
0x180018c76  jmp     short loc_180018C5F
0x180018c78  mov     rax, [rsi]
0x180018c7b  mov     [rsp+28h+arg_0], r10
0x180018c80  cmp     r10, [rax]
0x180018c83  jnz     short loc_180018CA6
0x180018c85  cmp     byte ptr [rbx+19h], 0
0x180018c89  jz      short loc_180018CA6
0x180018c8b  mov     rcx, rsi
0x180018c8e  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::clear(void)
0x180018c93  mov     rbx, [rsp+28h+arg_10]
0x180018c98  mov     rax, rdi
0x180018c9b  mov     rsi, [rsp+28h+arg_18]
0x180018ca0  add     rsp, 20h
0x180018ca4  pop     rdi
0x180018ca5  retn
0x180018ca6  cmp     r10, rbx
0x180018ca9  jz      short loc_180018C93
0x180018cab  lea     rcx, [rsp+28h+arg_0]
0x180018cb0  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180018cb5  lea     rcx, [rsp+28h+arg_8]
0x180018cba  mov     [rsp+28h+arg_8], r10
0x180018cbf  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>::operator++(void)
0x180018cc4  mov     rdx, r10
0x180018cc7  mov     rcx, rsi
0x180018cca  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>,std::_Iterator_base0>)
0x180018ccf  mov     rdx, rax
0x180018cd2  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *)
0x180018cd7  mov     r10, [rsp+28h+arg_0]
0x180018cdc  jmp     short loc_180018CA6
```
