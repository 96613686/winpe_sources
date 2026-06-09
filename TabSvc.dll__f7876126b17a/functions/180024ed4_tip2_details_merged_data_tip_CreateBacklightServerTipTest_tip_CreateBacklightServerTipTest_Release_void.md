# tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(void)

- ea: `0x180024ed4`
- end: `0x180024f0c`
- name: `?Release@?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f170`
- `0x18002a1e4`
- `0x18002ab14`

## callees

- `0x18001b374`
- `0x180024ed4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ef9`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::~merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>((__int64)pv);
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180024ed4  mov     [rsp+arg_0], rbx
0x180024ed9  push    rdi
0x180024eda  sub     rsp, 20h
0x180024ede  mov     rdi, rcx
0x180024ee1  or      ebx, 0FFFFFFFFh
0x180024ee4  lock xadd [rcx+128h], ebx
0x180024eec  sub     ebx, 1
0x180024eef  jnz     short loc_180024EFF
0x180024ef1  call    ??1?$merged_data@U_tip_CreateBacklightServerTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>::~merged_data<_tip_CreateBacklightServerTipTest,_tip_CreateBacklightServerTipTest>(void)
0x180024ef6  mov     rcx, rdi; pv
0x180024ef9  call    cs:__imp_CoTaskMemFree
0x180024eff  mov     eax, ebx
0x180024f01  mov     rbx, [rsp+28h+arg_0]
0x180024f06  add     rsp, 20h
0x180024f0a  pop     rdi
0x180024f0b  retn
```
