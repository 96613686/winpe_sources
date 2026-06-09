# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>(void)

- ea: `0x18001600c`
- end: `0x180016028`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180029a2e`
- `0x180029a76`

## callees

- `0x1800036e4`
- `0x18001600c`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18001600c  sub     rsp, 28h
0x180016010  mov     rcx, [rcx+8]; Block
0x180016014  test    rcx, rcx
0x180016017  jz      short loc_180016023
0x180016019  mov     edx, 158h
0x18001601e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016023  add     rsp, 28h
0x180016027  retn
```
