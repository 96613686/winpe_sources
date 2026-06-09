# std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>,void *> *)

- ea: `0x18000e734`
- end: `0x18000e7a0`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `108`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e734`
- `0x18000f260`
- `0x18000f4f8`

## callees

- `0x180002110`
- `0x18000e734`
- `0x1800132ac`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  IPxlatInterface *v6; // rdi
  void *v7; // rsi

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (IPxlatInterface *)v3[5];
      v7 = v3;
      v3 = (_QWORD *)*v3;
      if ( v6 )
      {
        IPxlatInterface::~IPxlatInterface(v6);
        operator delete(v6, 0xE8u);
      }
      operator delete(v7, 0x30u);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000e734  push    rbx
0x18000e736  push    rbp
0x18000e737  push    rsi
0x18000e738  push    rdi
0x18000e739  push    r14
0x18000e73b  sub     rsp, 20h
0x18000e73f  cmp     byte ptr [r8+19h], 0
0x18000e744  mov     rbx, r8
0x18000e747  mov     rbp, rdx
0x18000e74a  mov     r14, rcx
0x18000e74d  jnz     short loc_18000E795
0x18000e74f  mov     r8, [rbx+10h]
0x18000e753  mov     rdx, rbp
0x18000e756  mov     rcx, r14
0x18000e759  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *> *)
0x18000e75e  mov     rdi, [rbx+28h]
0x18000e762  mov     rsi, rbx
0x18000e765  mov     rbx, [rbx]
0x18000e768  test    rdi, rdi
0x18000e76b  jz      short loc_18000E782
0x18000e76d  mov     rcx, rdi; this
0x18000e770  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000e775  mov     edx, 0E8h; unsigned __int64
0x18000e77a  mov     rcx, rdi; void *
0x18000e77d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e782  mov     edx, 30h ; '0'; unsigned __int64
0x18000e787  mov     rcx, rsi; void *
0x18000e78a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e78f  cmp     byte ptr [rbx+19h], 0
0x18000e793  jz      short loc_18000E74F
0x18000e795  add     rsp, 20h
0x18000e799  pop     r14
0x18000e79b  pop     rdi
0x18000e79c  pop     rsi
0x18000e79d  pop     rbp
0x18000e79e  pop     rbx
0x18000e79f  retn
```
