# std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *)

- ea: `0x180018e24`
- end: `0x180018e4d`
- name: `??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800172d4`
- `0x180018c3c`
- `0x180018d7c`

## callees

- `0x1800076a0`
- `0x180018e24`
- `0x180019130`

## pseudocode

```c
void __fastcall std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(
        __int64 a1,
        _QWORD *a2)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)a2[6];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  std::_Deallocate<16>(a2, 0x38u);
}

```

## disassembly

```asm
0x180018e24  push    rbx
0x180018e26  sub     rsp, 20h
0x180018e2a  mov     rcx, [rdx+30h]; this
0x180018e2e  mov     rbx, rdx
0x180018e31  test    rcx, rcx
0x180018e34  jz      short loc_180018E3B
0x180018e36  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018e3b  mov     edx, 38h ; '8'
0x180018e40  mov     rcx, rbx
0x180018e43  add     rsp, 20h
0x180018e47  pop     rbx
0x180018e48  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
