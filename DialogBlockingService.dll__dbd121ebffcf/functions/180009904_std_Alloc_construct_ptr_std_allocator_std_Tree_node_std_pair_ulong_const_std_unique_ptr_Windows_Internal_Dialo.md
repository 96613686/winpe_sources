# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *>>>(void)

- ea: `0x180009904`
- end: `0x180009920`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ced4`

## callees

- `0x180001644`
- `0x180009904`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x30u);
}

```

## disassembly

```asm
0x180009904  sub     rsp, 28h
0x180009908  mov     rcx, [rcx+8]; void *
0x18000990c  test    rcx, rcx
0x18000990f  jz      short loc_18000991B
0x180009911  mov     edx, 30h ; '0'; unsigned __int64
0x180009916  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000991b  add     rsp, 28h
0x18000991f  retn
```
