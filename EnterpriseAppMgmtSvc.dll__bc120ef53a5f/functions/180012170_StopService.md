# StopService

- ea: `0x180012170`
- end: `0x180012382`
- name: `StopService`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800069dc`
- `0x180012170`
- `0x180012760`
- `0x180012c14`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001231a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001231a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001227f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001227f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800122ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800122ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001222a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001222a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800121a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800121a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800121b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800121b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180012191`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180012191`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001233f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001233f`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800122d5`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800122d5`

## pseudocode

```c
void StopService()
{
  __int64 v0; // r8
  LPVOID v1; // rcx
  int *v2; // rbx
  WINBOOL fPending; // [rsp+40h] [rbp-28h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-20h] BYREF

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
    McGenEventWrite_EventWriteTransfer(v1, EnterpriseAppMgmtSvcStopped, v0, 1);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&single_EnterpriseAppMgmtLogging, 0, &fPending, &Context);
  v2 = (int *)Context;
  if ( !Context )
  {
    dword_180096F28 = 0;
    v2 = &dword_180096F28;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180096F28);
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
  UpdateServiceStatus(1u, 0, 0);
}

```

## disassembly

```asm
0x180012170  push    rbx
0x180012172  sub     rsp, 60h
0x180012176  mov     rax, cs:__security_cookie
0x18001217d  xor     rax, rsp
0x180012180  mov     [rsp+68h+var_10], rax
0x180012185  mov     rcx, cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001218c  xor     r8d, r8d; pvCleanupContext
0x18001218f  xor     edx, edx; fCancelPendingCallbacks
0x180012191  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180012198  nop     dword ptr [rax+rax+00h]
0x18001219d  mov     rcx, cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x1800121a4  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800121ab  nop     dword ptr [rax+rax+00h]
0x1800121b0  mov     rcx, cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x1800121b7  call    cs:__imp_CloseThreadpool
0x1800121be  nop     dword ptr [rax+rax+00h]
0x1800121c3  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x1800121ca  test    rcx, rcx
0x1800121cd  jz      short loc_180012236
0x1800121cf  mov     rax, [rcx]
0x1800121d2  lea     r9, IID_IContextCallback
0x1800121d9  mov     [rsp+68h+var_40], 0
0x1800121e2  lea     rdx, ?RevokeClassFactoryCallback@@YAJPEAUtagComCallData@@@Z; RevokeClassFactoryCallback(tagComCallData *)
0x1800121e9  xor     r8d, r8d
0x1800121ec  mov     dword ptr [rsp+68h+var_48], 5
0x1800121f4  mov     rax, [rax+18h]
0x1800121f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121fd  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180012204  test    rcx, rcx
0x180012207  jz      short loc_180012220
0x180012209  mov     rax, [rcx]
0x18001220c  mov     rax, [rax+10h]
0x180012210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012215  mov     cs:?g_Icc@@3PEAUIContextCallback@@EA, 0; IContextCallback * g_Icc
0x180012220  mov     rcx, cs:hHandle; hHandle
0x180012227  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001222a  call    cs:__imp_WaitForSingleObject
0x180012231  nop     dword ptr [rax+rax+00h]
0x180012236  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 4
0x18001223d  jz      short loc_18001225B
0x18001223f  lea     rax, [rsp+68h+Context]
0x180012244  mov     r9d, 1
0x18001224a  lea     rdx, EnterpriseAppMgmtSvcStopped
0x180012251  mov     [rsp+68h+var_48], rax
0x180012256  call    McGenEventWrite_EventWriteTransfer
0x18001225b  lea     r9, [rsp+68h+Context]; lpContext
0x180012260  mov     [rsp+68h+fPending], 0
0x180012268  lea     r8, [rsp+68h+fPending]; fPending
0x18001226d  mov     [rsp+68h+Context], 0
0x180012276  xor     edx, edx; dwFlags
0x180012278  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x18001227f  call    cs:__imp_InitOnceBeginInitialize
0x180012286  nop     dword ptr [rax+rax+00h]
0x18001228b  mov     rbx, [rsp+68h+Context]
0x180012290  test    rbx, rbx
0x180012293  jnz     short loc_1800122BA
0x180012295  mov     cs:dword_180096F28, ebx
0x18001229b  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x1800122a2  lea     rbx, dword_180096F28
0x1800122a9  xor     edx, edx; dwFlags
0x1800122ab  mov     r8, rbx; lpContext
0x1800122ae  call    cs:__imp_InitOnceComplete
0x1800122b5  nop     dword ptr [rax+rax+00h]
0x1800122ba  cmp     dword ptr [rbx], 0
0x1800122bd  jz      short loc_1800122D1
0x1800122bf  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x1800122c6  call    McGenEventUnregister_EventUnregister
0x1800122cb  mov     dword ptr [rbx], 0
0x1800122d1  xor     edx, edx
0x1800122d3  xor     ecx, ecx
0x1800122d5  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800122dc  nop     dword ptr [rax+rax+00h]
0x1800122e1  mov     rcx, cs:hObject; hObject
0x1800122e8  lea     rax, [rcx-1]
0x1800122ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800122f0  ja      short loc_180012309
0x1800122f2  call    cs:__imp_CloseHandle
0x1800122f9  nop     dword ptr [rax+rax+00h]
0x1800122fe  mov     cs:hObject, 0
0x180012309  mov     rcx, cs:hHandle; hObject
0x180012310  lea     rax, [rcx-1]
0x180012314  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012318  ja      short loc_180012331
0x18001231a  call    cs:__imp_CloseHandle
0x180012321  nop     dword ptr [rax+rax+00h]
0x180012326  mov     cs:hHandle, 0
0x180012331  mov     rcx, cs:WaitHandle; WaitHandle
0x180012338  test    rcx, rcx
0x18001233b  jz      short loc_180012356
0x18001233d  xor     edx, edx; CompletionEvent
0x18001233f  call    cs:__imp_UnregisterWaitEx
0x180012346  nop     dword ptr [rax+rax+00h]
0x18001234b  mov     cs:WaitHandle, 0
0x180012356  xor     edx, edx; unsigned int
0x180012358  mov     cs:?g_pServiceHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, 0; _SVCHOST_GLOBAL_DATA * g_pServiceHostGlobalData
0x180012363  xor     r8d, r8d; unsigned int
0x180012366  lea     ecx, [rdx+1]; unsigned int
0x180012369  call    ?UpdateServiceStatus@@YAXKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18001236e  mov     rcx, [rsp+68h+var_10]
0x180012373  xor     rcx, rsp; StackCookie
0x180012376  call    __security_check_cookie
0x18001237b  add     rsp, 60h
0x18001237f  pop     rbx
0x180012380  retn
```
