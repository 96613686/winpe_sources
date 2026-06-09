# AiSvcpCleanup(ulong)

- ea: `0x180002d5c`
- end: `0x1800031c3`
- name: `?AiSvcpCleanup@@YAXK@Z`
- size: `1127`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180003bc0`
- `0x180003c80`

## callees

- `0x18000108c`
- `0x180002d5c`
- `0x180003bd0`
- `0x180008950`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002daf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002f35`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002daf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180002f35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002f42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002dbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180002f42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002dea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002f05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002dea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002f05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180002ed4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180002ed4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002da0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f26`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002da0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002f26`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002ddd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002ef8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002ddd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002ef8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180002ec7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180002ec7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002e75`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002e75`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003162`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003011`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002e40`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002e40`
- `RPCRT4!RpcBindingVectorFree` at `0x180002e1f`
- `RPCRT4!RpcBindingVectorFree` at `0x180002e1f`
- `RPCRT4!RpcServerUnregisterIf` at `0x180002e38`
- `RPCRT4!RpcServerUnregisterIf` at `0x180002e38`
- `RPCRT4!RpcEpUnregister` at `0x180002e12`
- `RPCRT4!RpcEpUnregister` at `0x180002e12`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002ff8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002ff8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002eab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002eab`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ee4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ee4`
- `ntdll!EtwEventWriteTransfer` at `0x1800030a7`
- `ntdll!EtwEventWriteTransfer` at `0x1800030a7`
- `ntdll!EtwEventUnregister` at `0x180003056`
- `ntdll!EtwEventUnregister` at `0x1800030db`
- `ntdll!EtwEventUnregister` at `0x180003056`
- `ntdll!EtwEventUnregister` at `0x1800030db`
- `ntdll!EtwUnregisterTraceGuids` at `0x180003186`
- `ntdll!EtwUnregisterTraceGuids` at `0x180003186`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000303d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000303d`
- `CRYPT32!CertCloseStore` at `0x180002f9f`
- `CRYPT32!CertCloseStore` at `0x180002f9f`
- `CRYPT32!CertControlStore` at `0x180002f77`
- `CRYPT32!CertControlStore` at `0x180002f77`
- `SLC!SLUnregisterWindowsEvent` at `0x180002fca`
- `SLC!SLUnregisterWindowsEvent` at `0x180002fca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AiSvcpCleanup(DWORD a1)
{
  RPC_STATUS v2; // eax
  HANDLE v3; // rcx
  HANDLE v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  REGHANDLE v8; // rcx
  _QWORD *v9; // rbx
  DWORD v10; // [rsp+40h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-38h] BYREF
  struct _RTL_SRWLOCK *v12; // [rsp+50h] [rbp-30h] BYREF
  __int64 v13; // [rsp+58h] [rbp-28h]

  BytesReturned = 0;
  if ( AiSvcpConfigTimer )
  {
    SetThreadpoolTimer(AiSvcpConfigTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(AiSvcpConfigTimer, 1);
    CloseThreadpoolTimer(AiSvcpConfigTimer);
    AiSvcpConfigTimer = 0;
    AiSvcpBootDelayFired = 0;
  }
  if ( AiSvcpLicenseChangeWaitObject )
  {
    WaitForThreadpoolWaitCallbacks(AiSvcpLicenseChangeWaitObject, 1);
    CloseThreadpoolWait(AiSvcpLicenseChangeWaitObject);
    AiSvcpLicenseChangeWaitObject = 0;
  }
  AiSvcpUninitializeGpCallback();
  if ( g_BindingVector )
  {
    RpcEpUnregister(qword_18000F630, g_BindingVector, 0);
    RpcBindingVectorFree(&g_BindingVector);
    g_BindingVector = 0;
  }
  v2 = RpcServerUnregisterIf(qword_18000F630, 0, 1u);
  I_RpcMapWin32Status(v2);
  if ( AiSvcDriverHandle != (HANDLE)-1LL )
  {
    DeviceIoControl(AiSvcDriverHandle, 0x22A00Cu, 0, 0, 0, 0, &BytesReturned, 0);
    if ( AiSvcDriverHandle != (HANDLE)-1LL )
    {
      CloseHandle(AiSvcDriverHandle);
      AiSvcDriverHandle = (HANDLE)-1LL;
    }
  }
  v12 = &SmLock;
  LOBYTE(v13) = 1;
  RtlAcquireSRWLockExclusive(&SmLock);
  if ( SmartlockerTpCallbackEnv )
  {
    CloseThreadpoolCleanupGroupMembers(SmartlockerTpCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(SmartlockerTpCleanupGroup);
    SmartlockerTpCallbackEnv = 0;
  }
  RtlReleaseSRWLockExclusive(&SmLock);
  if ( AiSvcpRootStoreWaitObject )
  {
    WaitForThreadpoolWaitCallbacks(AiSvcpRootStoreWaitObject, 1);
    CloseThreadpoolWait(AiSvcpRootStoreWaitObject);
    AiSvcpRootStoreWaitObject = 0;
  }
  if ( AiSvcpRootStoreTimer )
  {
    SetThreadpoolTimer(AiSvcpRootStoreTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(AiSvcpRootStoreTimer, 1);
    CloseThreadpoolTimer(AiSvcpRootStoreTimer);
    AiSvcpRootStoreTimer = 0;
  }
  v3 = AiSvcpRootStoreChangeEvent;
  if ( AiSvcpRootStoreChangeEvent )
  {
    if ( AiSvcpRootCertStore )
    {
      CertControlStore(AiSvcpRootCertStore, 0, 5u, &AiSvcpRootStoreChangeEvent);
      v3 = AiSvcpRootStoreChangeEvent;
    }
    CloseHandle(v3);
    AiSvcpRootStoreChangeEvent = 0;
  }
  if ( AiSvcpRootCertStore )
  {
    CertCloseStore(AiSvcpRootCertStore, 0);
    AiSvcpRootCertStore = 0;
  }
  v4 = AiSvcpLicenseChangeEvent;
  if ( AiSvcpLicenseChangeEvent )
  {
    if ( AiSvcpLicenseChangeRegistered )
    {
      SLUnregisterWindowsEvent(L"msft:rm/event/policychanged", AiSvcpLicenseChangeEvent);
      AiSvcpLicenseChangeRegistered = 0;
      v4 = AiSvcpLicenseChangeEvent;
    }
    CloseHandle(v4);
    AiSvcpLicenseChangeEvent = 0;
  }
  if ( AiSvcpServiceWaitStop )
  {
    UnregisterWaitEx(AiSvcpServiceWaitStop, 0);
    AiSvcpServiceWaitStop = 0;
  }
  if ( AiSvcpServiceStopEvent )
  {
    CloseHandle(AiSvcpServiceStopEvent);
    AiSvcpServiceStopEvent = 0;
  }
  if ( AiSvcpServiceStatusHandle )
  {
    AiSvcpServiceStatus.dwWin32ExitCode = a1;
    AiSvcpServiceStatus.dwCurrentState = 1;
    SetServiceStatus(AiSvcpServiceStatusHandle, &AiSvcpServiceStatus);
    AiSvcpServiceStatusHandle = 0;
  }
  if ( AiSvcSrpEventHandle )
  {
    EtwEventUnregister();
    AiSvcSrpEventHandle = 0;
  }
  if ( AiSvcEventHandle )
  {
    if ( a1 )
    {
      v10 = a1;
      v12 = (struct _RTL_SRWLOCK *)&v10;
      v13 = 4;
      v5 = EtwEventWriteTransfer(AiSvcEventHandle, AppIdServiceFailed, 0, 0, 1, &v12);
      if ( v5 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, v10, v5);
      }
    }
    EtwEventUnregister();
    AiSvcEventHandle = 0;
  }
  if ( (unsigned int)dword_180017000 > 4
    && (qword_180017010 & 0x400000000000LL) != 0
    && (qword_180017018 & 0x400000000000LL) == qword_180017018 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180017000, byte_180012B49, 0, 0, 2, &v12);
  }
  if ( byte_180017804 == 1 )
  {
    v8 = RegHandle;
    dword_180017000 = 0;
    RegHandle = 0;
    EventUnregister(v8);
    byte_180017804 = 0;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v9 )
    {
      if ( v9[1] )
      {
        EtwUnregisterTraceGuids();
        v9[1] = 0;
      }
      v9 = (_QWORD *)*v9;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x180002d5c  mov     [rsp-18h+arg_8], rbx
0x180002d61  mov     [rsp-18h+arg_10], rsi
0x180002d66  push    rbp
0x180002d67  push    rdi
0x180002d68  push    r14
0x180002d6a  mov     rbp, rsp
0x180002d6d  sub     rsp, 80h
0x180002d74  mov     rax, cs:__security_cookie
0x180002d7b  xor     rax, rsp
0x180002d7e  mov     [rbp+var_10], rax
0x180002d82  mov     ebx, ecx
0x180002d84  xor     edi, edi
0x180002d86  mov     [rbp+BytesReturned], edi
0x180002d89  lea     esi, [rdi+1]
0x180002d8c  mov     rcx, cs:?AiSvcpConfigTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002d93  test    rcx, rcx
0x180002d96  jz      short loc_180002DCF
0x180002d98  xor     r9d, r9d; msWindowLength
0x180002d9b  xor     r8d, r8d; msPeriod
0x180002d9e  xor     edx, edx; pftDueTime
0x180002da0  call    cs:__imp_SetThreadpoolTimer
0x180002da6  mov     edx, esi; fCancelPendingCallbacks
0x180002da8  mov     rcx, cs:?AiSvcpConfigTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002daf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002db5  mov     rcx, cs:?AiSvcpConfigTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002dbc  call    cs:__imp_CloseThreadpoolTimer
0x180002dc2  mov     cs:?AiSvcpConfigTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * AiSvcpConfigTimer
0x180002dc9  mov     cs:?AiSvcpBootDelayFired@@3KA, edi; ulong AiSvcpBootDelayFired
0x180002dcf  mov     rcx, cs:?AiSvcpLicenseChangeWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180002dd6  test    rcx, rcx
0x180002dd9  jz      short loc_180002DF7
0x180002ddb  mov     edx, esi; fCancelPendingCallbacks
0x180002ddd  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180002de3  mov     rcx, cs:?AiSvcpLicenseChangeWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180002dea  call    cs:__imp_CloseThreadpoolWait
0x180002df0  mov     cs:?AiSvcpLicenseChangeWaitObject@@3PEAU_TP_WAIT@@EA, rdi; _TP_WAIT * AiSvcpLicenseChangeWaitObject
0x180002df7  call    ?AiSvcpUninitializeGpCallback@@YAXXZ; AiSvcpUninitializeGpCallback(void)
0x180002dfc  mov     rdx, cs:g_BindingVector; BindingVector
0x180002e03  test    rdx, rdx
0x180002e06  jz      short loc_180002E2C
0x180002e08  xor     r8d, r8d; UuidVector
0x180002e0b  lea     rcx, qword_18000F630; IfSpec
0x180002e12  call    cs:__imp_RpcEpUnregister
0x180002e18  lea     rcx, g_BindingVector; BindingVector
0x180002e1f  call    cs:__imp_RpcBindingVectorFree
0x180002e25  mov     cs:g_BindingVector, rdi
0x180002e2c  mov     r8d, esi; WaitForCallsToComplete
0x180002e2f  xor     edx, edx; MgrTypeUuid
0x180002e31  lea     rcx, qword_18000F630; IfSpec
0x180002e38  call    cs:__imp_RpcServerUnregisterIf
0x180002e3e  mov     ecx, eax; Status
0x180002e40  call    cs:__imp_I_RpcMapWin32Status
0x180002e46  mov     rcx, cs:?AiSvcDriverHandle@@3PEAXEA; hDevice
0x180002e4d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002e51  jz      short loc_180002E99
0x180002e53  mov     [rsp+80h+lpOverlapped], rdi; lpOverlapped
0x180002e58  lea     rax, [rbp+BytesReturned]
0x180002e5c  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x180002e61  mov     [rsp+80h+nOutBufferSize], edi; nOutBufferSize
0x180002e65  mov     [rsp+80h+lpOutBuffer], rdi; lpOutBuffer
0x180002e6a  xor     r9d, r9d; nInBufferSize
0x180002e6d  xor     r8d, r8d; lpInBuffer
0x180002e70  mov     edx, 22A00Ch; dwIoControlCode
0x180002e75  call    cs:__imp_DeviceIoControl
0x180002e7b  mov     rcx, cs:?AiSvcDriverHandle@@3PEAXEA; hObject
0x180002e82  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002e86  jz      short loc_180002E99
0x180002e88  call    cs:__imp_CloseHandle
0x180002e8e  mov     cs:?AiSvcDriverHandle@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * AiSvcDriverHandle
0x180002e99  lea     r14, ?SmLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SmLock
0x180002ea0  mov     [rbp+var_30], r14
0x180002ea4  mov     byte ptr [rbp+var_28], sil
0x180002ea8  mov     rcx, r14
0x180002eab  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002eb1  nop
0x180002eb2  cmp     cs:?SmartlockerTpCallbackEnv@@3PEAU_TP_CALLBACK_ENVIRON_V3@@EA, rdi; _TP_CALLBACK_ENVIRON_V3 * SmartlockerTpCallbackEnv
0x180002eb9  jz      short loc_180002EE1
0x180002ebb  xor     r8d, r8d; pvCleanupContext
0x180002ebe  xor     edx, edx; fCancelPendingCallbacks
0x180002ec0  mov     rcx, cs:?SmartlockerTpCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180002ec7  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180002ecd  mov     rcx, cs:?SmartlockerTpCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180002ed4  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180002eda  mov     cs:?SmartlockerTpCallbackEnv@@3PEAU_TP_CALLBACK_ENVIRON_V3@@EA, rdi; _TP_CALLBACK_ENVIRON_V3 * SmartlockerTpCallbackEnv
0x180002ee1  mov     rcx, r14
0x180002ee4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002eea  mov     rcx, cs:?AiSvcpRootStoreWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180002ef1  test    rcx, rcx
0x180002ef4  jz      short loc_180002F12
0x180002ef6  mov     edx, esi; fCancelPendingCallbacks
0x180002ef8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180002efe  mov     rcx, cs:?AiSvcpRootStoreWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x180002f05  call    cs:__imp_CloseThreadpoolWait
0x180002f0b  mov     cs:?AiSvcpRootStoreWaitObject@@3PEAU_TP_WAIT@@EA, rdi; _TP_WAIT * AiSvcpRootStoreWaitObject
0x180002f12  mov     rcx, cs:?AiSvcpRootStoreTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002f19  test    rcx, rcx
0x180002f1c  jz      short loc_180002F4F
0x180002f1e  xor     r9d, r9d; msWindowLength
0x180002f21  xor     r8d, r8d; msPeriod
0x180002f24  xor     edx, edx; pftDueTime
0x180002f26  call    cs:__imp_SetThreadpoolTimer
0x180002f2c  mov     edx, esi; fCancelPendingCallbacks
0x180002f2e  mov     rcx, cs:?AiSvcpRootStoreTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002f35  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180002f3b  mov     rcx, cs:?AiSvcpRootStoreTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002f42  call    cs:__imp_CloseThreadpoolTimer
0x180002f48  mov     cs:?AiSvcpRootStoreTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * AiSvcpRootStoreTimer
0x180002f4f  mov     rcx, cs:?AiSvcpRootStoreChangeEvent@@3PEAXEA; void * AiSvcpRootStoreChangeEvent
0x180002f56  test    rcx, rcx
0x180002f59  jz      short loc_180002F91
0x180002f5b  mov     rax, cs:?AiSvcpRootCertStore@@3PEAXEA; void * AiSvcpRootCertStore
0x180002f62  test    rax, rax
0x180002f65  jz      short loc_180002F84
0x180002f67  lea     r9, ?AiSvcpRootStoreChangeEvent@@3PEAXEA; pvCtrlPara
0x180002f6e  xor     edx, edx; dwFlags
0x180002f70  lea     r8d, [rdx+5]; dwCtrlType
0x180002f74  mov     rcx, rax; hCertStore
0x180002f77  call    cs:__imp_CertControlStore
0x180002f7d  mov     rcx, cs:?AiSvcpRootStoreChangeEvent@@3PEAXEA; hObject
0x180002f84  call    cs:__imp_CloseHandle
0x180002f8a  mov     cs:?AiSvcpRootStoreChangeEvent@@3PEAXEA, rdi; void * AiSvcpRootStoreChangeEvent
0x180002f91  mov     rcx, cs:?AiSvcpRootCertStore@@3PEAXEA; hCertStore
0x180002f98  test    rcx, rcx
0x180002f9b  jz      short loc_180002FAC
0x180002f9d  xor     edx, edx; dwFlags
0x180002f9f  call    cs:__imp_CertCloseStore
0x180002fa5  mov     cs:?AiSvcpRootCertStore@@3PEAXEA, rdi; void * AiSvcpRootCertStore
0x180002fac  mov     rcx, cs:?AiSvcpLicenseChangeEvent@@3PEAXEA; void * AiSvcpLicenseChangeEvent
0x180002fb3  test    rcx, rcx
0x180002fb6  jz      short loc_180002FEA
0x180002fb8  cmp     cs:?AiSvcpLicenseChangeRegistered@@3KA, edi; ulong AiSvcpLicenseChangeRegistered
0x180002fbe  jz      short loc_180002FDD
0x180002fc0  mov     rdx, rcx
0x180002fc3  lea     rcx, aMsftRmEventPol; "msft:rm/event/policychanged"
0x180002fca  call    cs:__imp_SLUnregisterWindowsEvent
0x180002fd0  mov     cs:?AiSvcpLicenseChangeRegistered@@3KA, edi; ulong AiSvcpLicenseChangeRegistered
0x180002fd6  mov     rcx, cs:?AiSvcpLicenseChangeEvent@@3PEAXEA; hObject
0x180002fdd  call    cs:__imp_CloseHandle
0x180002fe3  mov     cs:?AiSvcpLicenseChangeEvent@@3PEAXEA, rdi; void * AiSvcpLicenseChangeEvent
0x180002fea  mov     rcx, cs:?AiSvcpServiceWaitStop@@3PEAXEA; WaitHandle
0x180002ff1  test    rcx, rcx
0x180002ff4  jz      short loc_180003005
0x180002ff6  xor     edx, edx; CompletionEvent
0x180002ff8  call    cs:__imp_UnregisterWaitEx
0x180002ffe  mov     cs:?AiSvcpServiceWaitStop@@3PEAXEA, rdi; void * AiSvcpServiceWaitStop
0x180003005  mov     rcx, cs:?AiSvcpServiceStopEvent@@3PEAXEA; hObject
0x18000300c  test    rcx, rcx
0x18000300f  jz      short loc_18000301E
0x180003011  call    cs:__imp_CloseHandle
0x180003017  mov     cs:?AiSvcpServiceStopEvent@@3PEAXEA, rdi; void * AiSvcpServiceStopEvent
0x18000301e  mov     rcx, cs:?AiSvcpServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180003025  test    rcx, rcx
0x180003028  jz      short loc_18000304A
0x18000302a  mov     cs:?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS AiSvcpServiceStatus ...
0x180003030  mov     cs:?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, esi; _SERVICE_STATUS AiSvcpServiceStatus ...
0x180003036  lea     rdx, ?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000303d  call    cs:__imp_SetServiceStatus
0x180003043  mov     cs:?AiSvcpServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rdi; SERVICE_STATUS_HANDLE__ * AiSvcpServiceStatusHandle
0x18000304a  mov     rcx, cs:?AiSvcSrpEventHandle@@3_KA; unsigned __int64 AiSvcSrpEventHandle
0x180003051  test    rcx, rcx
0x180003054  jz      short loc_180003063
0x180003056  call    cs:__imp_EtwEventUnregister
0x18000305c  mov     cs:?AiSvcSrpEventHandle@@3_KA, rdi; unsigned __int64 AiSvcSrpEventHandle
0x180003063  lea     r14, WPP_GLOBAL_Control
0x18000306a  mov     rcx, cs:?AiSvcEventHandle@@3_KA; unsigned __int64 AiSvcEventHandle
0x180003071  test    rcx, rcx
0x180003074  jz      short loc_1800030E8
0x180003076  test    ebx, ebx
0x180003078  jz      short loc_1800030DB
0x18000307a  mov     [rbp+var_40], ebx
0x18000307d  lea     rax, [rbp+var_40]
0x180003081  mov     [rbp+var_30], rax
0x180003085  mov     [rbp+var_28], 4
0x18000308d  lea     rax, [rbp+var_30]
0x180003091  mov     qword ptr [rsp+80h+nOutBufferSize], rax
0x180003096  mov     dword ptr [rsp+80h+lpOutBuffer], esi
0x18000309a  xor     r9d, r9d
0x18000309d  xor     r8d, r8d
0x1800030a0  lea     rdx, AppIdServiceFailed
0x1800030a7  call    cs:__imp_EtwEventWriteTransfer
0x1800030ad  test    eax, eax
0x1800030af  jns     short loc_1800030D4
0x1800030b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030b8  cmp     rcx, r14
0x1800030bb  jz      short loc_1800030D4
0x1800030bd  test    [rcx+1Ch], sil
0x1800030c1  jz      short loc_1800030D4
0x1800030c3  mov     dword ptr [rsp+80h+lpOutBuffer], eax
0x1800030c7  mov     r9d, [rbp+var_40]
0x1800030cb  mov     rcx, [rcx+10h]
0x1800030cf  call    WPP_SF_DD
0x1800030d4  mov     rcx, cs:?AiSvcEventHandle@@3_KA; unsigned __int64 AiSvcEventHandle
0x1800030db  call    cs:__imp_EtwEventUnregister
0x1800030e1  mov     cs:?AiSvcEventHandle@@3_KA, rdi; unsigned __int64 AiSvcEventHandle
0x1800030e8  mov     eax, cs:dword_180017000
0x1800030ee  cmp     eax, 4
0x1800030f1  jbe     short loc_180003145
0x1800030f3  mov     rcx, cs:qword_180017018
0x1800030fa  mov     rax, cs:qword_180017010
0x180003101  mov     rdx, 400000000000h
0x18000310b  test    rdx, rax
0x18000310e  jz      short loc_180003145
0x180003110  mov     rax, rcx
0x180003113  and     rax, rdx
0x180003116  cmp     rax, rcx
0x180003119  jnz     short loc_180003145
0x18000311b  lea     rax, [rbp+var_30]
0x18000311f  mov     qword ptr [rsp+80h+nOutBufferSize], rax
0x180003124  mov     dword ptr [rsp+80h+lpOutBuffer], 2
0x18000312c  xor     r9d, r9d
0x18000312f  xor     r8d, r8d
0x180003132  lea     rdx, byte_180012B49
0x180003139  lea     rcx, dword_180017000
0x180003140  call    _tlgWriteTransfer_EventWriteTransfer
0x180003145  cmp     cs:byte_180017804, sil
0x18000314c  jnz     short loc_18000316F
0x18000314e  mov     rcx, cs:RegHandle; RegHandle
0x180003155  mov     cs:dword_180017000, edi
0x18000315b  mov     cs:RegHandle, rdi
0x180003162  call    cs:__imp_EventUnregister
0x180003168  mov     cs:byte_180017804, dil
0x18000316f  mov     rbx, cs:WPP_GLOBAL_Control
0x180003176  cmp     rbx, r14
0x180003179  jz      short loc_18000319F
0x18000317b  jmp     short loc_180003193
0x18000317d  mov     rcx, [rbx+8]
0x180003181  test    rcx, rcx
0x180003184  jz      short loc_180003190
0x180003186  call    cs:__imp_EtwUnregisterTraceGuids
0x18000318c  mov     [rbx+8], rdi
0x180003190  mov     rbx, [rbx]
0x180003193  test    rbx, rbx
0x180003196  jnz     short loc_18000317D
0x180003198  mov     cs:WPP_GLOBAL_Control, r14
0x18000319f  mov     rcx, [rbp+var_10]
0x1800031a3  xor     rcx, rsp; StackCookie
0x1800031a6  call    __security_check_cookie
0x1800031ab  lea     r11, [rsp+80h+var_s0]
0x1800031b3  mov     rbx, [r11+28h]
0x1800031b7  mov     rsi, [r11+30h]
0x1800031bb  mov     rsp, r11
0x1800031be  pop     r14
0x1800031c0  pop     rdi
0x1800031c1  pop     rbp
0x1800031c2  retn
```
