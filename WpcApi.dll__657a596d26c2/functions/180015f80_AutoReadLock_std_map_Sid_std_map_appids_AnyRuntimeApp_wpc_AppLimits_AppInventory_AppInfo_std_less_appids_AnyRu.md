# AutoReadLock<std::map<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>>>>::~AutoReadLock<std::map<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>>>>(void)

- ea: `0x180015f80`
- end: `0x180015faa`
- name: `??1?$AutoReadLock@V?$map@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@@std@@@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180029cf7`
- `0x180029f8a`

## callees

- `0x180015f80`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall AutoReadLock<std::map<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>::~AutoReadLock<std::map<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015f80  push    rbx
0x180015f82  sub     rsp, 20h
0x180015f86  mov     rbx, rcx
0x180015f89  mov     rcx, [rcx]
0x180015f8c  test    rcx, rcx
0x180015f8f  jz      short loc_180015FA4
0x180015f91  mov     rax, [rcx]
0x180015f94  mov     rax, [rax+8]
0x180015f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9d  mov     qword ptr [rbx], 0
0x180015fa4  add     rsp, 20h
0x180015fa8  pop     rbx
0x180015fa9  retn
```
