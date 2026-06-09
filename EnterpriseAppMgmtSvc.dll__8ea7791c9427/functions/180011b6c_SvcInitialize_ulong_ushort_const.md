# SvcInitialize(ulong,ushort * * const)

- ea: `0x180011b6c`
- end: `0x180011ed1`
- name: `?SvcInitialize@@YAJKQEAPEAG@Z`
- size: `869`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012390`

## callees

- `0x180006780`
- `0x180006858`
- `0x180011b6c`
- `0x180011f54`
- `0x180012338`
- `0x18001235c`
- `0x18001c5b8`
- `0x18001f834`
- `0x180066dbe`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011da5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011cce`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180011baf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180011baf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011bce`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011e44`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011bce`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180011e44`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011bf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011e6a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011bf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180011e6a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011df4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011df4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180011ca1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180011ca1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180011cb3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180011cb3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180011cb9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180011cb9`
- `combase!__imp_CoGetSharedServiceId` at `0x180011c52`
- `combase!__imp_CoGetSharedServiceId` at `0x180011c52`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011d76`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011e8f`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011d76`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011e8f`

## string_xrefs

- `0x180011d56`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
__int64 __fastcall SvcInitialize(int a1, unsigned __int16 **const a2)
{
  int v2; // esi
  __int64 v3; // rdx
  int *v4; // rbx
  _BOOL8 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  int SharedServiceId; // ebx
  __int64 v9; // r8
  signed int LastError; // eax
  __int64 v11; // rax
  PackageManagerWrapper *v12; // rcx
  int v13; // eax
  int *v14; // rdi
  WINBOOL fPending; // [rsp+40h] [rbp-30h] BYREF
  LPVOID Context[4]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v2 = 0;
  if ( a2 && a1 == 2 && !wcscmp_0(a2[1], L"debug") )
    DebugBreak();
  fPending = 0;
  Context[0] = 0;
  InitOnceBeginInitialize(&single_EnterpriseAppMgmtLogging, 0, &fPending, Context);
  v4 = (int *)Context[0];
  if ( !Context[0] )
  {
    dword_180090F28 = 0;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180090F28);
    v4 = &dword_180090F28;
  }
  v5 = (unsigned int)McGenEventRegister_EventRegister(
                       MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT,
                       v3,
                       &MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context,
                       &MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context) == 0;
  *v4 = v5;
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, EnterpriseAppMgmtSvcStart, v6, 1, Context);
  SharedServiceId = CoGetSharedServiceId(&dword_180090A84);
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x10) != 0 )
  {
    fPending = (int)dword_180090A84;
    Context[3] = (LPVOID)4;
    Context[2] = &fPending;
    McGenEventWrite_EventWriteTransfer(v7, EnterpriseAppMgmtSvcCoGetSharedServiceId, v9, 2, Context);
  }
  if ( SharedServiceId < 0 )
    goto LABEL_25;
  g_provisioningThreadpool = CreateThreadpool(0);
  SetThreadpoolThreadMaximum(g_provisioningThreadpool, 1u);
  g_provisioningCallbackCleanupGroup = CreateThreadpoolCleanupGroup();
  if ( g_provisioningCallbackCleanupGroup )
  {
    *(_OWORD *)&g_provisioningCallbackEnvironment.RaceDll = 0;
    g_provisioningCallbackEnvironment.Pool = g_provisioningThreadpool;
    g_provisioningCallbackEnvironment.Version = 3;
    g_provisioningCallbackEnvironment.FinalizationCallback = 0;
    g_provisioningCallbackEnvironment.u.Flags = 0;
    g_provisioningCallbackEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    g_provisioningCallbackEnvironment.Size = 72;
    g_provisioningCallbackEnvironment.CleanupGroup = g_provisioningCallbackCleanupGroup;
    g_provisioningCallbackEnvironment.CleanupGroupCancelCallback = 0;
  }
  else
  {
    LastError = GetLastError();
    SharedServiceId = LastError;
    if ( LastError > 0 )
      SharedServiceId = (unsigned __int16)LastError | 0x80070000;
    if ( SharedServiceId < 0 )
      goto LABEL_25;
  }
  v11 = tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get();
  v12 = (PackageManagerWrapper *)(unsigned int)dword_180090A84;
  *(_DWORD *)(v11 + 8) = (_DWORD)dword_180090A84;
  v13 = PackageManagerWrapper::DeleteAllInstallingProductIdKeys(v12);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x111,
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v13);
  SharedServiceId = CoRegisterServerShutdownDelay(hObject, 30000);
  if ( SharedServiceId >= 0 )
  {
    SharedServiceId = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, &g_Icc);
    if ( SharedServiceId >= 0 )
    {
      SharedServiceId = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g_Icc + 24LL))(
                          g_Icc,
                          RegisterClassFactoryCallback,
                          0,
                          &IID_IContextCallback,
                          5,
                          0);
      if ( SharedServiceId >= 0 )
      {
        if ( WaitForSingleObject(hHandle, 0x1388u) != 258 )
          return (unsigned int)SharedServiceId;
        v2 = 1;
        SharedServiceId = -2147418113;
      }
    }
  }
LABEL_25:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v7,
      EnterpriseAppMgmtSvcError,
      L"SvcInitialize Failed",
      (unsigned int)SharedServiceId);
  fPending = 0;
  Context[0] = 0;
  InitOnceBeginInitialize(&single_EnterpriseAppMgmtLogging, 0, &fPending, Context);
  v14 = (int *)Context[0];
  if ( !Context[0] )
  {
    dword_180090F28 = 0;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180090F28);
    v14 = &dword_180090F28;
  }
  if ( *v14 )
  {
    McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context);
    *v14 = 0;
  }
  CoRegisterServerShutdownDelay(0, 0);
  if ( !v2 && g_Icc )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_Icc + 16LL))(g_Icc);
    g_Icc = 0;
  }
  return (unsigned int)SharedServiceId;
}

```

## disassembly

```asm
0x180011b6c  push    rbp
0x180011b6e  push    rbx
0x180011b6f  push    rsi
0x180011b70  push    rdi
0x180011b71  push    r14
0x180011b73  mov     rbp, rsp
0x180011b76  sub     rsp, 70h
0x180011b7a  mov     rax, cs:__security_cookie
0x180011b81  xor     rax, rsp
0x180011b84  mov     [rbp+var_8], rax
0x180011b88  xor     r14d, r14d
0x180011b8b  mov     rax, rdx
0x180011b8e  mov     esi, r14d
0x180011b91  test    rdx, rdx
0x180011b94  jz      short loc_180011BB5
0x180011b96  cmp     ecx, 2
0x180011b99  jnz     short loc_180011BB5
0x180011b9b  mov     rcx, [rax+8]; String1
0x180011b9f  lea     rdx, aDebug; "debug"
0x180011ba6  call    wcscmp_0
0x180011bab  test    eax, eax
0x180011bad  jnz     short loc_180011BB5
0x180011baf  call    cs:__imp_DebugBreak
0x180011bb5  lea     r9, [rbp+Context]; lpContext
0x180011bb9  mov     [rbp+fPending], r14d
0x180011bbd  lea     r8, [rbp+fPending]; fPending
0x180011bc1  mov     [rbp+Context], r14
0x180011bc5  xor     edx, edx; dwFlags
0x180011bc7  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011bce  call    cs:__imp_InitOnceBeginInitialize
0x180011bd4  mov     rbx, [rbp+Context]
0x180011bd8  test    rbx, rbx
0x180011bdb  jnz     short loc_180011C01
0x180011bdd  lea     r8, dword_180090F28; lpContext
0x180011be4  mov     cs:dword_180090F28, r14d
0x180011beb  xor     edx, edx; dwFlags
0x180011bed  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011bf4  call    cs:__imp_InitOnceComplete
0x180011bfa  lea     rbx, dword_180090F28
0x180011c01  lea     r9, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x180011c08  lea     r8, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x180011c0f  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT
0x180011c16  call    McGenEventRegister_EventRegister
0x180011c1b  test    eax, eax
0x180011c1d  mov     ecx, r14d
0x180011c20  mov     edi, 1
0x180011c25  setz    cl
0x180011c28  mov     [rbx], ecx
0x180011c2a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 4
0x180011c31  jz      short loc_180011C4B
0x180011c33  lea     rax, [rbp+Context]
0x180011c37  mov     r9d, edi
0x180011c3a  lea     rdx, EnterpriseAppMgmtSvcStart
0x180011c41  mov     [rsp+70h+ppv], rax
0x180011c46  call    McGenEventWrite_EventWriteTransfer
0x180011c4b  lea     rcx, dword_180090A84
0x180011c52  call    cs:__imp_CoGetSharedServiceId
0x180011c58  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 10h
0x180011c5f  mov     ebx, eax
0x180011c61  jz      short loc_180011C97
0x180011c63  mov     eax, cs:dword_180090A84
0x180011c69  lea     rdx, EnterpriseAppMgmtSvcCoGetSharedServiceId
0x180011c70  mov     [rbp+fPending], eax
0x180011c73  mov     r9d, 2
0x180011c79  lea     rax, [rbp+fPending]
0x180011c7d  mov     [rbp+var_10], 4
0x180011c85  mov     [rbp+var_18], rax
0x180011c89  lea     rax, [rbp+Context]
0x180011c8d  mov     [rsp+70h+ppv], rax; int
0x180011c92  call    McGenEventWrite_EventWriteTransfer
0x180011c97  test    ebx, ebx
0x180011c99  js      loc_180011E0C
0x180011c9f  xor     ecx, ecx; reserved
0x180011ca1  call    cs:__imp_CreateThreadpool
0x180011ca7  mov     rcx, rax; ptpp
0x180011caa  mov     cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * g_provisioningThreadpool
0x180011cb1  mov     edx, edi; cthrdMost
0x180011cb3  call    cs:__imp_SetThreadpoolThreadMaximum
0x180011cb9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180011cbf  mov     cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_provisioningCallbackCleanupGroup
0x180011cc6  mov     rcx, rax
0x180011cc9  test    rax, rax
0x180011ccc  jnz     short loc_180011CEC
0x180011cce  call    cs:__imp_GetLastError
0x180011cd4  mov     ebx, eax
0x180011cd6  test    eax, eax
0x180011cd8  jle     short loc_180011CE3
0x180011cda  movzx   ebx, ax
0x180011cdd  or      ebx, 80070000h
0x180011ce3  test    ebx, ebx
0x180011ce5  jns     short loc_180011D3B
0x180011ce7  jmp     loc_180011E0C
0x180011cec  mov     rax, cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_provisioningThreadpool
0x180011cf3  xorps   xmm0, xmm0
0x180011cf6  movdqa  xmmword ptr cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011cfe  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d05  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d0f  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d16  mov     dword ptr cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, r14d; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d1d  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, edi; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d23  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d2d  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rcx; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d34  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180011d3b  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x180011d40  mov     ecx, cs:dword_180090A84; this
0x180011d46  mov     [rax+8], ecx
0x180011d49  call    ?DeleteAllInstallingProductIdKeys@PackageManagerWrapper@@AEAAJXZ; PackageManagerWrapper::DeleteAllInstallingProductIdKeys(void)
0x180011d4e  test    eax, eax
0x180011d50  jns     short loc_180011D6A
0x180011d52  mov     rcx, [rbp+28h]; this
0x180011d56  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180011d5d  mov     r9d, eax; char *
0x180011d60  mov     edx, 111h; void *
0x180011d65  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011d6a  mov     rcx, cs:hObject
0x180011d71  mov     edx, 7530h
0x180011d76  call    cs:__imp_CoRegisterServerShutdownDelay
0x180011d7c  mov     ebx, eax
0x180011d7e  test    eax, eax
0x180011d80  js      loc_180011E0C
0x180011d86  lea     rax, ?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180011d8d  mov     r8d, edi; dwClsContext
0x180011d90  lea     r9, IID_IContextCallback; riid
0x180011d97  mov     [rsp+70h+ppv], rax; ppv
0x180011d9c  xor     edx, edx; pUnkOuter
0x180011d9e  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180011da5  call    cs:__imp_CoCreateInstance
0x180011dab  mov     ebx, eax
0x180011dad  test    eax, eax
0x180011daf  js      short loc_180011E0C
0x180011db1  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180011db8  lea     r9, IID_IContextCallback
0x180011dbf  mov     [rsp+70h+var_48], r14
0x180011dc4  lea     rdx, ?RegisterClassFactoryCallback@@YAJPEAUtagComCallData@@@Z; RegisterClassFactoryCallback(tagComCallData *)
0x180011dcb  xor     r8d, r8d
0x180011dce  mov     dword ptr [rsp+70h+ppv], 5
0x180011dd6  mov     rax, [rcx]
0x180011dd9  mov     rax, [rax+18h]
0x180011ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011de2  mov     ebx, eax
0x180011de4  test    eax, eax
0x180011de6  js      short loc_180011E0C
0x180011de8  mov     rcx, cs:hHandle; hHandle
0x180011def  mov     edx, 1388h; dwMilliseconds
0x180011df4  call    cs:__imp_WaitForSingleObject
0x180011dfa  cmp     eax, 102h
0x180011dff  jnz     loc_180011EB8
0x180011e05  mov     esi, edi
0x180011e07  mov     ebx, 8000FFFFh
0x180011e0c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180011e13  jz      short loc_180011E2B
0x180011e15  mov     r9d, ebx
0x180011e18  lea     r8, aSvcinitializeF; "SvcInitialize Failed"
0x180011e1f  lea     rdx, EnterpriseAppMgmtSvcError
0x180011e26  call    McTemplateU0zq_EventWriteTransfer
0x180011e2b  lea     r9, [rbp+Context]; lpContext
0x180011e2f  mov     [rbp+fPending], r14d
0x180011e33  lea     r8, [rbp+fPending]; fPending
0x180011e37  mov     [rbp+Context], r14
0x180011e3b  xor     edx, edx; dwFlags
0x180011e3d  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011e44  call    cs:__imp_InitOnceBeginInitialize
0x180011e4a  mov     rdi, [rbp+Context]
0x180011e4e  test    rdi, rdi
0x180011e51  jnz     short loc_180011E77
0x180011e53  lea     r8, dword_180090F28; lpContext
0x180011e5a  mov     cs:dword_180090F28, r14d
0x180011e61  xor     edx, edx; dwFlags
0x180011e63  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x180011e6a  call    cs:__imp_InitOnceComplete
0x180011e70  lea     rdi, dword_180090F28
0x180011e77  cmp     [rdi], r14d
0x180011e7a  jz      short loc_180011E8B
0x180011e7c  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x180011e83  call    McGenEventUnregister_EventUnregister
0x180011e88  mov     [rdi], r14d
0x180011e8b  xor     edx, edx
0x180011e8d  xor     ecx, ecx
0x180011e8f  call    cs:__imp_CoRegisterServerShutdownDelay
0x180011e95  test    esi, esi
0x180011e97  jnz     short loc_180011EB8
0x180011e99  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180011ea0  test    rcx, rcx
0x180011ea3  jz      short loc_180011EB8
0x180011ea5  mov     rax, [rcx]
0x180011ea8  mov     rax, [rax+10h]
0x180011eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb1  mov     cs:?g_Icc@@3PEAUIContextCallback@@EA, r14; IContextCallback * g_Icc
0x180011eb8  mov     eax, ebx
0x180011eba  mov     rcx, [rbp+var_8]
0x180011ebe  xor     rcx, rsp; StackCookie
0x180011ec1  call    __security_check_cookie
0x180011ec6  add     rsp, 70h
0x180011eca  pop     r14
0x180011ecc  pop     rdi
0x180011ecd  pop     rsi
0x180011ece  pop     rbx
0x180011ecf  pop     rbp
0x180011ed0  retn
```
