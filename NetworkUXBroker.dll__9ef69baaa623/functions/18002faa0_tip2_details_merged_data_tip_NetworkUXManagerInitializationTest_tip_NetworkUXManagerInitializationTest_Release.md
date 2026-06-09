# tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::Release(void)

- ea: `0x18002faa0`
- end: `0x18002fad8`
- name: `?Release@?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028304`
- `0x180028ec4`
- `0x1800367c4`

## callees

- `0x180028410`
- `0x18002faa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fac5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 76);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::~merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18002faa0  mov     [rsp+arg_0], rbx
0x18002faa5  push    rdi
0x18002faa6  sub     rsp, 20h
0x18002faaa  mov     rdi, rcx
0x18002faad  or      ebx, 0FFFFFFFFh
0x18002fab0  lock xadd [rcx+130h], ebx
0x18002fab8  sub     ebx, 1
0x18002fabb  jnz     short loc_18002FACB
0x18002fabd  call    ??1?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::~merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>(void)
0x18002fac2  mov     rcx, rdi; pv
0x18002fac5  call    cs:__imp_CoTaskMemFree
0x18002facb  mov     eax, ebx
0x18002facd  mov     rbx, [rsp+28h+arg_0]
0x18002fad2  add     rsp, 20h
0x18002fad6  pop     rdi
0x18002fad7  retn
```
