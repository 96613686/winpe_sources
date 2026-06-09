# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(void)

- ea: `0x18000c8fc`
- end: `0x18000c934`
- name: `?Release@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(volatile signed __int32 *pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b23c`
- `0x18000d5b0`
- `0x18000e2fc`

## callees

- `0x18000b2ac`
- `0x18000c8fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c921`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::~merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(pv);
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c8fc  mov     [rsp+arg_0], rbx
0x18000c901  push    rdi
0x18000c902  sub     rsp, 20h
0x18000c906  mov     rdi, rcx
0x18000c909  or      ebx, 0FFFFFFFFh
0x18000c90c  lock xadd [rcx+128h], ebx
0x18000c914  sub     ebx, 1
0x18000c917  jnz     short loc_18000C927
0x18000c919  call    ??1?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::~merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(void)
0x18000c91e  mov     rcx, rdi; pv
0x18000c921  call    cs:__imp_CoTaskMemFree
0x18000c927  mov     eax, ebx
0x18000c929  mov     rbx, [rsp+28h+arg_0]
0x18000c92e  add     rsp, 20h
0x18000c932  pop     rdi
0x18000c933  retn
```
