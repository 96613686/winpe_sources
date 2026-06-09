# WJWorkplaceJoinTriggerEventCallback

- ea: `0x18002c140`
- end: `0x18002c1ca`
- name: `WJWorkplaceJoinTriggerEventCallback`
- size: `138`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002c140`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c1aa`
- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x18002c17e`
- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x18002c17e`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002c199`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002c199`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c157`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c172`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c157`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c172`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c1c3`

## string_xrefs

- `0x18002c192`: `AutoJoinSvc/%s: Failed to write the auto join trigger event with error 0x%08x.`

## pseudocode

```c
void __fastcall WJWorkplaceJoinTriggerEventCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  int v4; // eax

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJWorkplaceJoinTriggerEventCallback");
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Writing the auto join trigger event after sleeping for %d seconds.",
    L"WJWorkplaceJoinTriggerEventCallback",
    (unsigned int)g_AutoJoinTriggerEventDelay);
  v4 = DsrWriteAutoJoinSvcTriggerEvent((unsigned int)g_AutoJoinTriggerEventDelay);
  if ( v4 < 0 )
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to write the auto join trigger event with error 0x%08x.",
      L"WJWorkplaceJoinTriggerEventCallback",
      (unsigned int)v4);
  SetThreadpoolTimer(Timer, 0, 0, 0);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJWorkplaceJoinTriggerEventCallback");
}

```

## disassembly

```asm
0x18002c140  push    rbx
0x18002c142  sub     rsp, 20h
0x18002c146  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002c14d  mov     rbx, r8
0x18002c150  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002c157  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c15d  mov     r8d, cs:g_AutoJoinTriggerEventDelay
0x18002c164  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002c16b  lea     rcx, aAutojoinsvcSWr; "AutoJoinSvc/%s: Writing the auto join t"...
0x18002c172  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c178  mov     ecx, cs:g_AutoJoinTriggerEventDelay
0x18002c17e  call    cs:__imp_DsrWriteAutoJoinSvcTriggerEvent
0x18002c184  test    eax, eax
0x18002c186  jns     short loc_18002C19F
0x18002c188  mov     r8d, eax
0x18002c18b  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002c192  lea     rcx, aAutojoinsvcSFa_13; "AutoJoinSvc/%s: Failed to write the aut"...
0x18002c199  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002c19f  xor     r9d, r9d; msWindowLength
0x18002c1a2  xor     r8d, r8d; msPeriod
0x18002c1a5  xor     edx, edx; pftDueTime
0x18002c1a7  mov     rcx, rbx; pti
0x18002c1aa  call    cs:__imp_SetThreadpoolTimer
0x18002c1b0  lea     rdx, aWjworkplacejoi; "WJWorkplaceJoinTriggerEventCallback"
0x18002c1b7  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002c1be  add     rsp, 20h
0x18002c1c2  pop     rbx
0x18002c1c3  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
