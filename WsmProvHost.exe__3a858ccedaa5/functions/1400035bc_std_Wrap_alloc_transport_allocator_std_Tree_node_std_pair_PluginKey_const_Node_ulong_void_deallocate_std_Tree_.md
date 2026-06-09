# std::_Wrap_alloc<transport_allocator<std::_Tree_node<std::pair<PluginKey const,Node<ulong>>,void *>>>::deallocate(std::_Tree_node<std::pair<PluginKey const,Node<ulong>>,void *> *,unsigned __int64)

- ea: `0x1400035bc`
- end: `0x1400035c8`
- name: `?deallocate@?$_Wrap_alloc@V?$transport_allocator@U?$_Tree_node@U?$pair@$$CBUPluginKey@@U?$Node@K@@@std@@PEAX@std@@@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBUPluginKey@@U?$Node@K@@@std@@PEAX@2@_K@Z`
- size: `12`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140004574`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x1400035c1`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<transport_allocator<std::_Tree_node<std::pair<PluginKey const,Node<unsigned long>>,void *>>>::deallocate(
        __int64 a1,
        void *a2)
{
  WSManMemory::Free(a2, 0);
}

```

## disassembly

```asm
0x1400035bc  mov     rcx, rdx
0x1400035bf  xor     edx, edx
0x1400035c1  jmp     cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
```
