# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>>,void *>>>(void)

- ea: `0x180018fe8`
- end: `0x180019015`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018928`
- `0x180018e54`
- `0x18001964c`

## callees

- `0x1800076a0`
- `0x180018fe8`
- `0x18001901c`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(std::_Ref_count_base **)(v2 + 48);
    if ( v3 )
      std::_Ref_count_base::_Decref(v3);
  }
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(a1);
}

```

## disassembly

```asm
0x180018fe8  push    rbx
0x180018fea  sub     rsp, 20h
0x180018fee  mov     rbx, rcx
0x180018ff1  mov     rcx, [rcx+8]
0x180018ff5  test    rcx, rcx
0x180018ff8  jz      short loc_180019008
0x180018ffa  mov     rcx, [rcx+30h]; this
0x180018ffe  test    rcx, rcx
0x180019001  jz      short loc_180019008
0x180019003  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019008  mov     rcx, rbx
0x18001900b  add     rsp, 20h
0x18001900f  pop     rbx
0x180019010  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(void)
```
