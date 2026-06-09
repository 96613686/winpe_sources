# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(void)

- ea: `0x180010db0`
- end: `0x180010ddd`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a8c0`

## callees

- `0x180005b30`
- `0x180010db0`
- `0x180010de4`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
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
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(a1);
}

```

## disassembly

```asm
0x180010db0  push    rbx
0x180010db2  sub     rsp, 20h
0x180010db6  mov     rbx, rcx
0x180010db9  mov     rcx, [rcx+8]
0x180010dbd  test    rcx, rcx
0x180010dc0  jz      short loc_180010DD0
0x180010dc2  mov     rcx, [rcx+30h]; this
0x180010dc6  test    rcx, rcx
0x180010dc9  jz      short loc_180010DD0
0x180010dcb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010dd0  mov     rcx, rbx
0x180010dd3  add     rsp, 20h
0x180010dd7  pop     rbx
0x180010dd8  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(void)
```
