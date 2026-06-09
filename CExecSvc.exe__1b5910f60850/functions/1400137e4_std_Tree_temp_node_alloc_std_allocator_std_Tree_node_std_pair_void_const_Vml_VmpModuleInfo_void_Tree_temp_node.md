# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<void * const,Vml::VmpModuleInfo>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<void * const,Vml::VmpModuleInfo>,void *>>>(void)

- ea: `0x1400137e4`
- end: `0x140013800`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@QEAXVVmpModuleInfo@Vml@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140022b41`

## callees

- `0x1400026b8`
- `0x1400137e4`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<void * const,Vml::VmpModuleInfo>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<void * const,Vml::VmpModuleInfo>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x68u);
}

```

## disassembly

```asm
0x1400137e4  sub     rsp, 28h
0x1400137e8  mov     rcx, [rcx+8]; void *
0x1400137ec  test    rcx, rcx
0x1400137ef  jz      short loc_1400137FB
0x1400137f1  mov     edx, 68h ; 'h'; unsigned __int64
0x1400137f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400137fb  add     rsp, 28h
0x1400137ff  retn
```
