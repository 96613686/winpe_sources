# RmAccessCheckOnSelf

- ea: `0x180019450`
- end: `0x180019481`
- name: `RmAccessCheckOnSelf`
- size: `49`
- prototype: `CLIENT_CALL_RETURN __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000e8a0`
- `0x180019338`
- `0x180019450`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RmAccessCheckOnSelf(int a1)
{
  CLIENT_CALL_RETURN result; // rax
  struct ResourceManagerProxy *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  result.Simple = GetResourceManagerProxy(&v3);
  if ( SLODWORD(result.Simple) >= 0 )
    return ResourceManagerProxy::RmAccessCheck((__int64)v3, a1);
  return result;
}

```

## disassembly

```asm
0x180019450  push    rbx
0x180019452  sub     rsp, 20h
0x180019456  mov     ebx, ecx
0x180019458  mov     [rsp+28h+arg_8], 0
0x180019461  lea     rcx, [rsp+28h+arg_8]; struct ResourceManagerProxy **
0x180019466  call    ?GetResourceManagerProxy@@YAJPEAPEAVResourceManagerProxy@@@Z; GetResourceManagerProxy(ResourceManagerProxy * *)
0x18001946b  test    eax, eax
0x18001946d  js      short loc_18001947B
0x18001946f  mov     rcx, [rsp+28h+arg_8]
0x180019474  mov     edx, ebx
0x180019476  call    ?RmAccessCheck@ResourceManagerProxy@@QEAAJW4RmResourceType@@@Z; ResourceManagerProxy::RmAccessCheck(RmResourceType)
0x18001947b  add     rsp, 20h
0x18001947f  pop     rbx
0x180019480  retn
```
