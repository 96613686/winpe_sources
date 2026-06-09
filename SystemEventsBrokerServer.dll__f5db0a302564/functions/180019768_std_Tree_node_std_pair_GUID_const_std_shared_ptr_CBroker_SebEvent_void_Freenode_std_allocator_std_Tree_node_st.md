# std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *> *)

- ea: `0x180019768`
- end: `0x180019791`
- name: `??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VSebEvent@CBroker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020480`

## callees

- `0x1800076a0`
- `0x180019768`
- `0x18001d364`

## pseudocode

```c
void __fastcall std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<CBroker::SebEvent>>,void *>>>(
        __int64 a1,
        _QWORD *a2)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)a2[7];
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  operator delete(a2, 0x40u);
}

```

## disassembly

```asm
0x180019768  push    rbx
0x18001976a  sub     rsp, 20h
0x18001976e  mov     rcx, [rdx+38h]; this
0x180019772  mov     rbx, rdx
0x180019775  test    rcx, rcx
0x180019778  jz      short loc_18001977F
0x18001977a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001977f  mov     edx, 40h ; '@'; unsigned __int64
0x180019784  mov     rcx, rbx; void *
0x180019787  add     rsp, 20h
0x18001978b  pop     rbx
0x18001978c  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
