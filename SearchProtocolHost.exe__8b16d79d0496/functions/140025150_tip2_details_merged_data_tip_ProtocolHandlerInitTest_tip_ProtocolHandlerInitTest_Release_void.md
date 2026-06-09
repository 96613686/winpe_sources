# tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::Release(void)

- ea: `0x140025150`
- end: `0x140025188`
- name: `?Release@?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000eeb8`
- `0x140037c28`
- `0x140038c48`

## callees

- `0x14000efb8`
- `0x140025150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025175`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 78);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::~merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140025150  mov     [rsp+arg_0], rbx
0x140025155  push    rdi
0x140025156  sub     rsp, 20h
0x14002515a  mov     rdi, rcx
0x14002515d  or      ebx, 0FFFFFFFFh
0x140025160  lock xadd [rcx+138h], ebx
0x140025168  sub     ebx, 1
0x14002516b  jnz     short loc_14002517B
0x14002516d  call    ??1?$merged_data@U_tip_ProtocolHandlerInitTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>::~merged_data<_tip_ProtocolHandlerInitTest,_tip_ProtocolHandlerInitTest>(void)
0x140025172  mov     rcx, rdi; pv
0x140025175  call    cs:__imp_CoTaskMemFree
0x14002517b  mov     eax, ebx
0x14002517d  mov     rbx, [rsp+28h+arg_0]
0x140025182  add     rsp, 20h
0x140025186  pop     rdi
0x140025187  retn
```
