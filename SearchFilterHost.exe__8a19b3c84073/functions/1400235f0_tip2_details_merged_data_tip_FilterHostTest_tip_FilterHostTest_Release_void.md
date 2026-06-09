# tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::Release(void)

- ea: `0x1400235f0`
- end: `0x140023628`
- name: `?Release@?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001bb98`
- `0x140026d70`
- `0x1400271cc`

## callees

- `0x14001bc20`
- `0x1400235f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140023615`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 112);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::~merged_data<_tip_FilterHostTest,_tip_FilterHostTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1400235f0  mov     [rsp+arg_0], rbx
0x1400235f5  push    rdi
0x1400235f6  sub     rsp, 20h
0x1400235fa  mov     rdi, rcx
0x1400235fd  or      ebx, 0FFFFFFFFh
0x140023600  lock xadd [rcx+1C0h], ebx
0x140023608  sub     ebx, 1
0x14002360b  jnz     short loc_14002361B
0x14002360d  call    ??1?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>::~merged_data<_tip_FilterHostTest,_tip_FilterHostTest>(void)
0x140023612  mov     rcx, rdi; pv
0x140023615  call    cs:__imp_CoTaskMemFree
0x14002361b  mov     eax, ebx
0x14002361d  mov     rbx, [rsp+28h+arg_0]
0x140023622  add     rsp, 20h
0x140023626  pop     rdi
0x140023627  retn
```
