# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$20

- ea: `0x18000ced4`
- end: `0x18000cee0`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$20`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009904`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(a2 + 64);
}

```

## disassembly

```asm
0x18000ced4  lea     rcx, [rdx+40h]
0x18000cedb  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(void)
```
