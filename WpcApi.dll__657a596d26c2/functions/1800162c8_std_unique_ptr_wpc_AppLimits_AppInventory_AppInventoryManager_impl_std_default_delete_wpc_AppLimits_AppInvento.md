# std::unique_ptr<wpc::AppLimits::AppInventory::AppInventoryManager::impl,std::default_delete<wpc::AppLimits::AppInventory::AppInventoryManager::impl>>::~unique_ptr<wpc::AppLimits::AppInventory::AppInventoryManager::impl,std::default_delete<wpc::AppLimits::AppInventory::AppInventoryManager::impl>>(void)

- ea: `0x1800162c8`
- end: `0x1800162f2`
- name: `??1?$unique_ptr@Vimpl@AppInventoryManager@AppInventory@AppLimits@wpc@@U?$default_delete@Vimpl@AppInventoryManager@AppInventory@AppLimits@wpc@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180029b3d`

## callees

- `0x1800036e4`
- `0x18001613c`
- `0x1800162c8`

## pseudocode

```c
void __fastcall std::unique_ptr<wpc::AppLimits::AppInventory::AppInventoryManager::impl>::~unique_ptr<wpc::AppLimits::AppInventory::AppInventoryManager::impl>(
        void ***a1)
{
  void **v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::~_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>(v1 + 2);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800162c8  push    rbx
0x1800162ca  sub     rsp, 20h
0x1800162ce  mov     rbx, [rcx]
0x1800162d1  test    rbx, rbx
0x1800162d4  jz      short loc_1800162EC
0x1800162d6  lea     rcx, [rbx+10h]
0x1800162da  call    ??1?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::~_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>(void)
0x1800162df  mov     edx, 20h ; ' '
0x1800162e4  mov     rcx, rbx; Block
0x1800162e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800162ec  add     rsp, 20h
0x1800162f0  pop     rbx
0x1800162f1  retn
```
