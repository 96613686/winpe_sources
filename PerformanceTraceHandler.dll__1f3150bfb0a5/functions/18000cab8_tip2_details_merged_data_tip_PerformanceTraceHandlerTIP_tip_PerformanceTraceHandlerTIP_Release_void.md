# tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(void)

- ea: `0x18000cab8`
- end: `0x18000caf0`
- name: `?Release@?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(volatile signed __int32 *pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b480`
- `0x18001303c`
- `0x1800133d8`

## callees

- `0x18000b49c`
- `0x18000cab8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cadd`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::~merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000cab8  mov     [rsp+arg_0], rbx
0x18000cabd  push    rdi
0x18000cabe  sub     rsp, 20h
0x18000cac2  mov     rdi, rcx
0x18000cac5  or      ebx, 0FFFFFFFFh
0x18000cac8  lock xadd [rcx+120h], ebx
0x18000cad0  sub     ebx, 1
0x18000cad3  jnz     short loc_18000CAE3
0x18000cad5  call    ??1?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::~merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>(void)
0x18000cada  mov     rcx, rdi; pv
0x18000cadd  call    cs:__imp_CoTaskMemFree
0x18000cae3  mov     eax, ebx
0x18000cae5  mov     rbx, [rsp+28h+arg_0]
0x18000caea  add     rsp, 20h
0x18000caee  pop     rdi
0x18000caef  retn
```
