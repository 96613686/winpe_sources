# StopService

- ea: `0x180011980`
- end: `0x180011b63`
- name: `StopService`
- size: `483`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006780`
- `0x180011980`
- `0x18001235c`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ae7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ae7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011a6d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011a6d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011a96`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011a96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011a26`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011a26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800119b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800119b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800119bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800119bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800119a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800119a5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011b45`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011b45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180011b02`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180011b02`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011ab2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011ab2`

## pseudocode

```c
BOOL StopService()
{
  __int64 v0; // r8
  LPVOID v1; // rcx
  int *v2; // rbx
  WINBOOL fPending; // [rsp+40h] [rbp-28h] BYREF
  LPVOID Context[2]; // [rsp+48h] [rbp-20h] BYREF

  CloseThreadpoolCleanupGroupMembers(g_provisioningCallbackCleanupGroup, 0, 0);
  CloseThreadpoolCleanupGroup(g_provisioningCallbackCleanupGroup);
  CloseThreadpool(g_provisioningThreadpool);
  v1 = g_Icc;
  if ( g_Icc )
  {
    (*(void (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_Icc + 24LL))(
      g_Icc,
      RevokeClassFactoryCallback,
      0,
      &IID_IContextCallback,
      5,
      0);
    if ( g_Icc )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_Icc + 16LL))(g_Icc);
      g_Icc = 0;
    }
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
  }
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v1, EnterpriseAppMgmtSvcStopped, v0, 1, Context);
  fPending = 0;
  Context[0] = 0;
  InitOnceBeginInitialize(&single_EnterpriseAppMgmtLogging, 0, &fPending, Context);
  v2 = (int *)Context[0];
  if ( !Context[0] )
  {
    v2 = &dword_180090F28;
    dword_180090F28 = 0;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180090F28);
  }
  if ( *v2 )
  {
    McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context);
    *v2 = 0;
  }
  CoRegisterServerShutdownDelay(0, 0);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( (char *)hHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hHandle);
    hHandle = 0;
  }
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  g_pServiceHostGlobalData = 0;
  ServiceStatus.dwControlsAccepted = 1;
  ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  return SetServiceStatus(hServiceStatus, &ServiceStatus);
}

```

## disassembly

```asm
0x180011980  mov     [rsp+arg_0], rbx
0x180011985  push    rdi
0x180011986  sub     rsp, 60h
0x18001198a  mov     rax, cs:__security_cookie
0x180011991  xor     rax, rsp
0x180011994  mov     [rsp+68h+var_10], rax
0x180011999  mov     rcx, cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x1800119a0  xor     r8d, r8d; pvCleanupContext
0x1800119a3  xor     edx, edx; fCancelPendingCallbacks
0x1800119a5  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800119ab  mov     rcx, cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x1800119b2  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800119b8  mov     rcx, cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x1800119bf  call    cs:__imp_CloseThreadpool
0x1800119c5  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x1800119cc  xor     edi, edi
0x1800119ce  test    rcx, rcx
0x1800119d1  jz      short loc_180011A2C
0x1800119d3  mov     rax, [rcx]
0x1800119d6  lea     r9, IID_IContextCallback
0x1800119dd  mov     [rsp+68h+var_40], rdi
0x1800119e2  lea     rdx, ?RevokeClassFactoryCallback@@YAJPEAUtagComCallData@@@Z; RevokeClassFactoryCallback(tagComCallData *)
0x1800119e9  xor     r8d, r8d
0x1800119ec  mov     dword ptr [rsp+68h+var_48], 5
0x1800119f4  mov     rax, [rax+18h]
0x1800119f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119fd  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180011a04  test    rcx, rcx
0x180011a07  jz      short loc_180011A1C
0x180011a09  mov     rax, [rcx]
0x180011a0c  mov     rax, [rax+10h]
0x180011a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a15  mov     cs:?g_Icc@@3PEAUIContextCallback@@EA, rdi; IContextCallback * g_Icc
0x180011a1c  mov     rcx, cs:hHandle; hHandle
0x180011a23  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011a26  call    cs:__imp_WaitForSingleObject
0x180011a2c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 4
0x180011a33  jz      short loc_180011A51
0x180011a35  lea     rax, [rsp+68h+Context]
0x180011a3a  mov     r9d, 1
0x180011a40  lea     rdx, EnterpriseAppMgmtSvcStopped
0x180011a47  mov     [rsp+68h+var_48], rax
0x180011a4c  call    McGenEventWrite_EventWriteTransfer
0x180011a51  lea     r9, [rsp+68h+Context]; lpContext
0x180011a56  mov     [rsp+68h+fPending], edi
0x180011a5a  lea     r8, [rsp+68h+fPending]; fPending
0x180011a5f  mov     [rsp+68h+Context], rdi
0x180011a64  xor     edx, edx; dwFlags
0x180011a66  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011a6d  call    cs:__imp_InitOnceBeginInitialize
0x180011a73  mov     rbx, [rsp+68h+Context]
0x180011a78  test    rbx, rbx
0x180011a7b  jnz     short loc_180011A9C
0x180011a7d  lea     rbx, dword_180090F28
0x180011a84  mov     cs:dword_180090F28, edi
0x180011a8a  mov     r8, rbx; lpContext
0x180011a8d  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011a94  xor     edx, edx; dwFlags
0x180011a96  call    cs:__imp_InitOnceComplete
0x180011a9c  cmp     [rbx], edi
0x180011a9e  jz      short loc_180011AAE
0x180011aa0  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x180011aa7  call    McGenEventUnregister_EventUnregister
0x180011aac  mov     [rbx], edi
0x180011aae  xor     edx, edx
0x180011ab0  xor     ecx, ecx
0x180011ab2  call    cs:__imp_CoRegisterServerShutdownDelay
0x180011ab8  mov     rcx, cs:hObject; hObject
0x180011abf  lea     rax, [rcx-1]
0x180011ac3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011ac7  ja      short loc_180011AD6
0x180011ac9  call    cs:__imp_CloseHandle
0x180011acf  mov     cs:hObject, rdi
0x180011ad6  mov     rcx, cs:hHandle; hObject
0x180011add  lea     rax, [rcx-1]
0x180011ae1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011ae5  ja      short loc_180011AF4
0x180011ae7  call    cs:__imp_CloseHandle
0x180011aed  mov     cs:hHandle, rdi
0x180011af4  mov     rcx, cs:WaitHandle; WaitHandle
0x180011afb  test    rcx, rcx
0x180011afe  jz      short loc_180011B0F
0x180011b00  xor     edx, edx; CompletionEvent
0x180011b02  call    cs:__imp_UnregisterWaitEx
0x180011b08  mov     cs:WaitHandle, rdi
0x180011b0f  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180011b16  lea     rdx, ServiceStatus; lpServiceStatus
0x180011b1d  mov     cs:?g_pServiceHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rdi; _SVCHOST_GLOBAL_DATA * g_pServiceHostGlobalData
0x180011b24  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180011b2e  mov     cs:ServiceStatus.dwCurrentState, 1
0x180011b38  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x180011b3e  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rdi
0x180011b45  call    cs:__imp_SetServiceStatus
0x180011b4b  mov     rcx, [rsp+68h+var_10]
0x180011b50  xor     rcx, rsp; StackCookie
0x180011b53  call    __security_check_cookie
0x180011b58  mov     rbx, [rsp+68h+arg_0]
0x180011b5d  add     rsp, 60h
0x180011b61  pop     rdi
0x180011b62  retn
```
