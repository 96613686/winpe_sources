# std::_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>::~_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>(void)

- ea: `0x180011be8`
- end: `0x180011c12`
- name: `??1?$_Tree@V?$_Tmap_traits@_JV?$shared_ptr@VTimeEvent@Broker@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@2@$00@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ad8`
- `0x180018480`

## callees

- `0x180005c50`
- `0x180010b34`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>::~_Tree<std::_Tmap_traits<__int64,std::shared_ptr<Broker::TimeEvent>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>,1>>(
        void **a1)
{
  std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
    (__int64)a1,
    (__int64)a1,
    *((_QWORD *)*a1 + 1));
  std::_Deallocate<16>(*a1, 0x38u);
}

```

## disassembly

```asm
0x180011be8  push    rbx
0x180011bea  sub     rsp, 20h
0x180011bee  mov     r8, [rcx]
0x180011bf1  mov     rdx, rcx
0x180011bf4  mov     rbx, rcx
0x180011bf7  mov     r8, [r8+8]
0x180011bfb  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180011c00  mov     rcx, [rbx]
0x180011c03  mov     edx, 38h ; '8'
0x180011c08  add     rsp, 20h
0x180011c0c  pop     rbx
0x180011c0d  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
