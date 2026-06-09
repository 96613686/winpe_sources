# SvcInitialize(ulong,ushort * * const)

- ea: `0x180012388`
- end: `0x180012742`
- name: `?SvcInitialize@@YAJKQEAPEAG@Z`
- size: `954`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012c50`

## callees

- `0x1800069dc`
- `0x180006ac0`
- `0x180012388`
- `0x1800127c8`
- `0x180012be8`
- `0x180012c14`
- `0x18001d65c`
- `0x180020e2c`
- `0x18006c8de`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800125f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800125f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012514`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800123cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800123cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800123f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800126a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800123f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800126a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001241c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800126ce`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001241c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800126ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001264c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001264c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800124d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800124d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800124ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800124ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800124f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800124f9`
- `combase!__imp_CoGetSharedServiceId` at `0x180012480`
- `combase!__imp_CoGetSharedServiceId` at `0x180012480`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800125c2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800126f9`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800125c2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800126f9`

## string_xrefs

- `0x1800125a2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
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
    dword_180096F28 = 0;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180096F28);
    v4 = &dword_180096F28;
  }
  v5 = (unsigned int)McGenEventRegister_EventRegister(
                       MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT,
                       v3,
                       &MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context,
                       &MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context) == 0;
  *v4 = v5;
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 4) != 0 )
  {
    ppv = Context;
    McGenEventWrite_EventWriteTransfer(v5, EnterpriseAppMgmtSvcStart, v6, 1);
  }
  SharedServiceId = CoGetSharedServiceId(&dword_180096A7C);
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x10) != 0 )
  {
    fPending = (int)dword_180096A7C;
    Context[3] = (LPVOID)4;
    Context[2] = &fPending;
    ppv = Context;
    McGenEventWrite_EventWriteTransfer(v7, EnterpriseAppMgmtSvcCoGetSharedServiceId, v9, 2);
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
  v12 = (PackageManagerWrapper *)(unsigned int)dword_180096A7C;
  *(_DWORD *)(v11 + 8) = (_DWORD)dword_180096A7C;
  v13 = PackageManagerWrapper::DeleteAllInstallingProductIdKeys(v12);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v13,
      (int)ppv);
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
    dword_180096F28 = 0;
    InitOnceComplete(&single_EnterpriseAppMgmtLogging, 0, &dword_180096F28);
    v14 = &dword_180096F28;
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
0x180012388  push    rbp
0x18001238a  push    rbx
0x18001238b  push    rsi
0x18001238c  push    rdi
0x18001238d  push    r14
0x18001238f  mov     rbp, rsp
0x180012392  sub     rsp, 70h
0x180012396  mov     rax, cs:__security_cookie
0x18001239d  xor     rax, rsp
0x1800123a0  mov     [rbp+var_8], rax
0x1800123a4  xor     r14d, r14d
0x1800123a7  mov     rax, rdx
0x1800123aa  mov     esi, r14d
0x1800123ad  test    rdx, rdx
0x1800123b0  jz      short loc_1800123D7
0x1800123b2  cmp     ecx, 2
0x1800123b5  jnz     short loc_1800123D7
0x1800123b7  mov     rcx, [rax+8]; String1
0x1800123bb  lea     rdx, aDebug; "debug"
0x1800123c2  call    wcscmp_0
0x1800123c7  test    eax, eax
0x1800123c9  jnz     short loc_1800123D7
0x1800123cb  call    cs:__imp_DebugBreak
0x1800123d2  nop     dword ptr [rax+rax+00h]
0x1800123d7  lea     r9, [rbp+Context]; lpContext
0x1800123db  mov     [rbp+fPending], r14d
0x1800123df  lea     r8, [rbp+fPending]; fPending
0x1800123e3  mov     [rbp+Context], r14
0x1800123e7  xor     edx, edx; dwFlags
0x1800123e9  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x1800123f0  call    cs:__imp_InitOnceBeginInitialize
0x1800123f7  nop     dword ptr [rax+rax+00h]
0x1800123fc  mov     rbx, [rbp+Context]
0x180012400  test    rbx, rbx
0x180012403  jnz     short loc_18001242F
0x180012405  lea     r8, dword_180096F28; lpContext
0x18001240c  mov     cs:dword_180096F28, r14d
0x180012413  xor     edx, edx; dwFlags
0x180012415  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x18001241c  call    cs:__imp_InitOnceComplete
0x180012423  nop     dword ptr [rax+rax+00h]
0x180012428  lea     rbx, dword_180096F28
0x18001242f  lea     r9, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x180012436  lea     r8, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x18001243d  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT
0x180012444  call    McGenEventRegister_EventRegister
0x180012449  test    eax, eax
0x18001244b  mov     ecx, r14d
0x18001244e  mov     edi, 1
0x180012453  setz    cl
0x180012456  mov     [rbx], ecx
0x180012458  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 4
0x18001245f  jz      short loc_180012479
0x180012461  lea     rax, [rbp+Context]
0x180012465  mov     r9d, edi
0x180012468  lea     rdx, EnterpriseAppMgmtSvcStart
0x18001246f  mov     [rsp+70h+ppv], rax
0x180012474  call    McGenEventWrite_EventWriteTransfer
0x180012479  lea     rcx, dword_180096A7C
0x180012480  call    cs:__imp_CoGetSharedServiceId
0x180012487  nop     dword ptr [rax+rax+00h]
0x18001248c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 10h
0x180012493  mov     ebx, eax
0x180012495  jz      short loc_1800124CB
0x180012497  mov     eax, cs:dword_180096A7C
0x18001249d  lea     rdx, EnterpriseAppMgmtSvcCoGetSharedServiceId
0x1800124a4  mov     [rbp+fPending], eax
0x1800124a7  mov     r9d, 2
0x1800124ad  lea     rax, [rbp+fPending]
0x1800124b1  mov     [rbp+var_10], 4
0x1800124b9  mov     [rbp+var_18], rax
0x1800124bd  lea     rax, [rbp+Context]
0x1800124c1  mov     [rsp+70h+ppv], rax; int
0x1800124c6  call    McGenEventWrite_EventWriteTransfer
0x1800124cb  test    ebx, ebx
0x1800124cd  js      loc_18001266A
0x1800124d3  xor     ecx, ecx; reserved
0x1800124d5  call    cs:__imp_CreateThreadpool
0x1800124dc  nop     dword ptr [rax+rax+00h]
0x1800124e1  mov     rcx, rax; ptpp
0x1800124e4  mov     cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * g_provisioningThreadpool
0x1800124eb  mov     edx, edi; cthrdMost
0x1800124ed  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800124f4  nop     dword ptr [rax+rax+00h]
0x1800124f9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180012500  nop     dword ptr [rax+rax+00h]
0x180012505  mov     cs:?g_provisioningCallbackCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_provisioningCallbackCleanupGroup
0x18001250c  mov     rcx, rax
0x18001250f  test    rax, rax
0x180012512  jnz     short loc_180012538
0x180012514  call    cs:__imp_GetLastError
0x18001251b  nop     dword ptr [rax+rax+00h]
0x180012520  mov     ebx, eax
0x180012522  test    eax, eax
0x180012524  jle     short loc_18001252F
0x180012526  movzx   ebx, ax
0x180012529  or      ebx, 80070000h
0x18001252f  test    ebx, ebx
0x180012531  jns     short loc_180012587
0x180012533  jmp     loc_18001266A
0x180012538  mov     rax, cs:?g_provisioningThreadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * g_provisioningThreadpool
0x18001253f  xorps   xmm0, xmm0
0x180012542  movdqa  xmmword ptr cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x18001254a  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012551  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x18001255b  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012562  mov     dword ptr cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, r14d; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012569  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, edi; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x18001256f  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012579  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rcx; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012580  mov     cs:?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, r14; _TP_CALLBACK_ENVIRON_V3 g_provisioningCallbackEnvironment ...
0x180012587  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x18001258c  mov     ecx, cs:dword_180096A7C; this
0x180012592  mov     [rax+8], ecx
0x180012595  call    ?DeleteAllInstallingProductIdKeys@PackageManagerWrapper@@AEAAJXZ; PackageManagerWrapper::DeleteAllInstallingProductIdKeys(void)
0x18001259a  test    eax, eax
0x18001259c  jns     short loc_1800125B6
0x18001259e  mov     rcx, [rbp+28h]; this
0x1800125a2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800125a9  mov     r9d, eax; char *
0x1800125ac  mov     edx, 111h; void *
0x1800125b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800125b6  mov     rcx, cs:hObject
0x1800125bd  mov     edx, 7530h
0x1800125c2  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800125c9  nop     dword ptr [rax+rax+00h]
0x1800125ce  mov     ebx, eax
0x1800125d0  test    eax, eax
0x1800125d2  js      loc_18001266A
0x1800125d8  lea     rax, ?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x1800125df  mov     r8d, edi; dwClsContext
0x1800125e2  lea     r9, IID_IContextCallback; riid
0x1800125e9  mov     [rsp+70h+ppv], rax; ppv
0x1800125ee  xor     edx, edx; pUnkOuter
0x1800125f0  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800125f7  call    cs:__imp_CoCreateInstance
0x1800125fe  nop     dword ptr [rax+rax+00h]
0x180012603  mov     ebx, eax
0x180012605  test    eax, eax
0x180012607  js      short loc_18001266A
0x180012609  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180012610  lea     r9, IID_IContextCallback
0x180012617  mov     [rsp+70h+var_48], r14
0x18001261c  lea     rdx, ?RegisterClassFactoryCallback@@YAJPEAUtagComCallData@@@Z; RegisterClassFactoryCallback(tagComCallData *)
0x180012623  xor     r8d, r8d
0x180012626  mov     dword ptr [rsp+70h+ppv], 5
0x18001262e  mov     rax, [rcx]
0x180012631  mov     rax, [rax+18h]
0x180012635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001263a  mov     ebx, eax
0x18001263c  test    eax, eax
0x18001263e  js      short loc_18001266A
0x180012640  mov     rcx, cs:hHandle; hHandle
0x180012647  mov     edx, 1388h; dwMilliseconds
0x18001264c  call    cs:__imp_WaitForSingleObject
0x180012653  nop     dword ptr [rax+rax+00h]
0x180012658  cmp     eax, 102h
0x18001265d  jnz     loc_180012728
0x180012663  mov     esi, edi
0x180012665  mov     ebx, 8000FFFFh
0x18001266a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180012671  jz      short loc_180012689
0x180012673  mov     r9d, ebx
0x180012676  lea     r8, aSvcinitializeF; "SvcInitialize Failed"
0x18001267d  lea     rdx, EnterpriseAppMgmtSvcError
0x180012684  call    McTemplateU0zq_EventWriteTransfer
0x180012689  lea     r9, [rbp+Context]; lpContext
0x18001268d  mov     [rbp+fPending], r14d
0x180012691  lea     r8, [rbp+fPending]; fPending
0x180012695  mov     [rbp+Context], r14
0x180012699  xor     edx, edx; dwFlags
0x18001269b  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x1800126a2  call    cs:__imp_InitOnceBeginInitialize
0x1800126a9  nop     dword ptr [rax+rax+00h]
0x1800126ae  mov     rdi, [rbp+Context]
0x1800126b2  test    rdi, rdi
0x1800126b5  jnz     short loc_1800126E1
0x1800126b7  lea     r8, dword_180096F28; lpContext
0x1800126be  mov     cs:dword_180096F28, r14d
0x1800126c5  xor     edx, edx; dwFlags
0x1800126c7  lea     rcx, ?single_EnterpriseAppMgmtLogging@@3V?$static_lazy@VEnterpriseAppMgmtLogging@@$0A@V?$lazy_construct@VEnterpriseAppMgmtLogging@@@tlx@@@tlx@@A; lpInitOnce
0x1800126ce  call    cs:__imp_InitOnceComplete
0x1800126d5  nop     dword ptr [rax+rax+00h]
0x1800126da  lea     rdi, dword_180096F28
0x1800126e1  cmp     [rdi], r14d
0x1800126e4  jz      short loc_1800126F5
0x1800126e6  lea     rcx, MICROSOFT_WINDOWSPHONE_ENTERPRISEAPPMGMT_Context
0x1800126ed  call    McGenEventUnregister_EventUnregister
0x1800126f2  mov     [rdi], r14d
0x1800126f5  xor     edx, edx
0x1800126f7  xor     ecx, ecx
0x1800126f9  call    cs:__imp_CoRegisterServerShutdownDelay
0x180012700  nop     dword ptr [rax+rax+00h]
0x180012705  test    esi, esi
0x180012707  jnz     short loc_180012728
0x180012709  mov     rcx, cs:?g_Icc@@3PEAUIContextCallback@@EA; IContextCallback * g_Icc
0x180012710  test    rcx, rcx
0x180012713  jz      short loc_180012728
0x180012715  mov     rax, [rcx]
0x180012718  mov     rax, [rax+10h]
0x18001271c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012721  mov     cs:?g_Icc@@3PEAUIContextCallback@@EA, r14; IContextCallback * g_Icc
0x180012728  mov     eax, ebx
0x18001272a  mov     rcx, [rbp+var_8]
0x18001272e  xor     rcx, rsp; StackCookie
0x180012731  call    __security_check_cookie
0x180012736  add     rsp, 70h
0x18001273a  pop     r14
0x18001273c  pop     rdi
0x18001273d  pop     rsi
0x18001273e  pop     rbx
0x18001273f  pop     rbp
0x180012740  retn
```
