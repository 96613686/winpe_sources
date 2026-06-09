# WJFinalizeRegistryNotification

- ea: `0x18002b484`
- end: `0x18002b557`
- name: `WJFinalizeRegistryNotification`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002bed8`

## callees

- `0x18002b484`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b519`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b52f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b52f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002b4eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002b4eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b4d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b4d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002b4e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002b4e1`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b49b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b4c3`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b50b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b49b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b4c3`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b50b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b550`

## string_xrefs

- `0x18002b48d`: `WJFinalizeRegistryNotification`
- `0x18002b4b5`: `WJFinalizeRegistryNotification`
- `0x18002b4f5`: `WJFinalizeRegistryNotification`
- `0x18002b53d`: `WJFinalizeRegistryNotification`
- `0x18002b4bc`: `AutoJoinSvc/%s: Canceling thread pool wait for %s registry key change notifications.`
- `0x18002b4fc`: `AutoJoinSvc/%s: Thread pool wait for %s registry key change notifications is cancelled.`

## pseudocode

```c
__int64 __fastcall WJFinalizeRegistryNotification(__int64 a1)
{
  __int64 v2; // r8
  void *v3; // rcx

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJFinalizeRegistryNotification");
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Canceling thread pool wait for %s registry key change notifications.",
        L"WJFinalizeRegistryNotification",
        *(_QWORD *)(a1 + 32));
      SetThreadpoolWait(*(PTP_WAIT *)(a1 + 16), 0, 0);
      WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(a1 + 16), 1);
      CloseThreadpoolWait(*(PTP_WAIT *)(a1 + 16));
      v2 = *(_QWORD *)(a1 + 32);
      *(_QWORD *)(a1 + 16) = 0;
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Thread pool wait for %s registry key change notifications is cancelled.",
        L"WJFinalizeRegistryNotification",
        v2);
    }
    if ( *(_QWORD *)a1 )
    {
      RegCloseKey(*(HKEY *)a1);
      *(_QWORD *)a1 = 0;
    }
    v3 = *(void **)(a1 + 8);
    if ( v3 )
    {
      CloseHandle(v3);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  return DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJFinalizeRegistryNotification");
}

```

## disassembly

```asm
0x18002b484  push    rbx
0x18002b486  sub     rsp, 20h
0x18002b48a  mov     rbx, rcx
0x18002b48d  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002b494  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002b49b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b4a1  test    rbx, rbx
0x18002b4a4  jz      loc_18002B53D
0x18002b4aa  cmp     qword ptr [rbx+10h], 0
0x18002b4af  jz      short loc_18002B511
0x18002b4b1  mov     r8, [rbx+20h]
0x18002b4b5  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002b4bc  lea     rcx, aAutojoinsvcSCa_1; "AutoJoinSvc/%s: Canceling thread pool w"...
0x18002b4c3  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b4c9  mov     rcx, [rbx+10h]; pwa
0x18002b4cd  xor     r8d, r8d; pftTimeout
0x18002b4d0  xor     edx, edx; h
0x18002b4d2  call    cs:__imp_SetThreadpoolWait
0x18002b4d8  mov     rcx, [rbx+10h]; pwa
0x18002b4dc  mov     edx, 1; fCancelPendingCallbacks
0x18002b4e1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002b4e7  mov     rcx, [rbx+10h]; pwa
0x18002b4eb  call    cs:__imp_CloseThreadpoolWait
0x18002b4f1  mov     r8, [rbx+20h]
0x18002b4f5  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002b4fc  lea     rcx, aAutojoinsvcSTh; "AutoJoinSvc/%s: Thread pool wait for %s"...
0x18002b503  mov     qword ptr [rbx+10h], 0
0x18002b50b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b511  mov     rcx, [rbx]; hKey
0x18002b514  test    rcx, rcx
0x18002b517  jz      short loc_18002B526
0x18002b519  call    cs:__imp_RegCloseKey
0x18002b51f  mov     qword ptr [rbx], 0
0x18002b526  mov     rcx, [rbx+8]; hObject
0x18002b52a  test    rcx, rcx
0x18002b52d  jz      short loc_18002B53D
0x18002b52f  call    cs:__imp_CloseHandle
0x18002b535  mov     qword ptr [rbx+8], 0
0x18002b53d  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002b544  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002b54b  add     rsp, 20h
0x18002b54f  pop     rbx
0x18002b550  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
