# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(void)

- ea: `0x180010de4`
- end: `0x180010e00`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010db0`
- `0x18001a8e0`

## callees

- `0x180010b34`
- `0x180010de4`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x38u);
}

```

## disassembly

```asm
0x180010de4  sub     rsp, 28h
0x180010de8  mov     rcx, [rcx+8]
0x180010dec  test    rcx, rcx
0x180010def  jz      short loc_180010DFB
0x180010df1  mov     edx, 38h ; '8'
0x180010df6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010dfb  add     rsp, 28h
0x180010dff  retn
```
