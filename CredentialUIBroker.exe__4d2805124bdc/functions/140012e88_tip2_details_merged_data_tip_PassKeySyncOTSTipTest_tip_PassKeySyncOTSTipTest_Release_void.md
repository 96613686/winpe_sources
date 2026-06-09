# tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::Release(void)

- ea: `0x140012e88`
- end: `0x140012ec0`
- name: `?Release@?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008e8c`
- `0x14001ad78`
- `0x14001bb28`

## callees

- `0x140008ecc`
- `0x140012e88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012ead`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140012ead`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::~merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140012e88  mov     [rsp+arg_0], rbx
0x140012e8d  push    rdi
0x140012e8e  sub     rsp, 20h
0x140012e92  mov     rdi, rcx
0x140012e95  or      ebx, 0FFFFFFFFh
0x140012e98  lock xadd [rcx+120h], ebx
0x140012ea0  sub     ebx, 1
0x140012ea3  jnz     short loc_140012EB3
0x140012ea5  call    ??1?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::~merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>(void)
0x140012eaa  mov     rcx, rdi; pv
0x140012ead  call    cs:__imp_CoTaskMemFree
0x140012eb3  mov     eax, ebx
0x140012eb5  mov     rbx, [rsp+28h+arg_0]
0x140012eba  add     rsp, 20h
0x140012ebe  pop     rdi
0x140012ebf  retn
```
