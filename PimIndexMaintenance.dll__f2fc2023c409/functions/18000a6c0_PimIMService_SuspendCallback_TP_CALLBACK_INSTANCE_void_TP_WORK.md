# PimIMService::SuspendCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000a6c0`
- end: `0x18000a774`
- name: `?SuspendCallback@PimIMService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `180`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800067c0`
- `0x18000a6c0`
- `0x18000c5b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a6dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a6dd`

## string_xrefs

- `0x18000a71c`: `PimIMService::SuspendCallback`
- `0x18000a75b`: `PimIMService::SuspendCallback`

## pseudocode

```c
void __fastcall PimIMService::SuspendCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  DWORD v4; // eax
  void *v5; // rax
  void *v6; // rax

  _InterlockedExchange((volatile __int32 *)Context + 150, 0);
  while ( 1 )
  {
    v4 = WaitForSingleObject(*((HANDLE *)Context + 38), 0x7530u);
    if ( !v4 )
      break;
    if ( v4 != 258 )
    {
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
      {
        v6 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v6, "PimIMService::SuspendCallback", -3, 0, -1);
      }
      return;
    }
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v5 = _t_address();
      EtwTraceMessage(&ETWMESSAGE, v5, "PimIMService::SuspendCallback", -3, 0, -1);
    }
  }
}

```

## disassembly

```asm
0x18000a6c0  push    rbx
0x18000a6c2  sub     rsp, 30h
0x18000a6c6  xor     eax, eax
0x18000a6c8  mov     rbx, rdx
0x18000a6cb  xchg    eax, [rdx+258h]
0x18000a6d1  mov     rcx, [rbx+130h]; hHandle
0x18000a6d8  mov     edx, 7530h; dwMilliseconds
0x18000a6dd  call    cs:__imp_WaitForSingleObject
0x18000a6e3  test    eax, eax
0x18000a6e5  jz      loc_18000A76E
0x18000a6eb  cmp     eax, 102h
0x18000a6f0  jnz     short loc_18000A731
0x18000a6f2  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a6f9  jz      short loc_18000A6D1
0x18000a6fb  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a700  mov     rdx, rax; void *
0x18000a703  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFFh
0x18000a70c  mov     r9, 0FFFFFFFFFFFFFFFDh
0x18000a713  mov     [rsp+38h+var_18], 0
0x18000a71c  lea     r8, aPimimserviceSu; "PimIMService::SuspendCallback"
0x18000a723  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a72a  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a72f  jmp     short loc_18000A6D1
0x18000a731  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18000a738  jz      short loc_18000A76E
0x18000a73a  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18000a73f  mov     rdx, rax; void *
0x18000a742  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFFh
0x18000a74b  mov     r9, 0FFFFFFFFFFFFFFFDh
0x18000a752  mov     [rsp+38h+var_18], 0
0x18000a75b  lea     r8, aPimimserviceSu; "PimIMService::SuspendCallback"
0x18000a762  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18000a769  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18000a76e  add     rsp, 30h
0x18000a772  pop     rbx
0x18000a773  retn
```
