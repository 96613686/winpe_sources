# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *>>>(void)

- ea: `0x18000ba98`
- end: `0x18000bab4`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180029637`
- `0x1800299d4`

## callees

- `0x1800036e4`
- `0x18000ba98`

## pseudocode

```c
void __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>(
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
0x18000ba98  sub     rsp, 28h
0x18000ba9c  mov     rcx, [rcx+8]; Block
0x18000baa0  test    rcx, rcx
0x18000baa3  jz      short loc_18000BAAF
0x18000baa5  mov     edx, 98h
0x18000baaa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000baaf  add     rsp, 28h
0x18000bab3  retn
```
