# CDsmCore::_Shutdown(void)

- ea: `0x1800240dc`
- end: `0x18002436b`
- name: `?_Shutdown@CDsmCore@@AEAAXXZ`
- size: `655`
- prototype: `void __fastcall(CDsmCore *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800238e8`

## callees

- `0x1800011b4`
- `0x180009fb0`
- `0x18000ba0c`
- `0x18000e518`
- `0x18000eb38`
- `0x180017034`
- `0x180017bf0`
- `0x180018678`
- `0x1800186a4`
- `0x1800186d8`
- `0x180018dac`
- `0x180019028`
- `0x180019148`
- `0x18001af70`
- `0x180021790`
- `0x180022070`
- `0x1800240dc`
- `0x180024e94`
- `0x1800267ac`
- `0x18002c038`
- `0x180040944`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024209`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024209`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800241fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800241fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180024230`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180024230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024257`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024257`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180024293`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x180024293`

## pseudocode

```c
void __fastcall CDsmCore::_Shutdown(CDsmCore *this, __int64 a2, __int64 a3)
{
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  CNetworkEvents *v8; // rcx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  __int64 v13; // r8
  PVOID *v14; // rcx
  unsigned int ObjectCount; // eax
  _BYTE v16[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  CDsmCore::_SetCoreEvent((__int64)&g_DsmCore, 6, a3);
  EventScan::Close(xmmword_180059F20);
  ContainerManager::SetContainerManagerMode(xmmword_180059F10, 2);
  JobScheduler::Stop(xmmword_180059EC0);
  if ( DrvRecoverySpUtilsInitialized )
  {
    pSetupUninitializeUtils();
    DrvRecoverySpUtilsInitialized = 0;
  }
  TraceLoggingUnregister_EventUnregister(&dword_180059110);
  ReportSvcStatus(3u, v3, 0x2710u);
  ContainerManager::Shutdown(xmmword_180059F10);
  ReportSvcStatus(3u, v4, 0x2710u);
  CDevNotify::s_RequestShutdown();
  ReportSvcStatus(3u, v5, 0x2710u);
  DsmRpcShutdown();
  ReportSvcStatus(3u, v6, 0x2710u);
  CDevNotify::s_CompleteShutdown();
  ReportSvcStatus(3u, v7, 0x2710u);
  CNetworkEvents::Close(v8);
  ReportSvcStatus(3u, v9, 0x2710u);
  if ( pti )
  {
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
    pti = 0;
  }
  ReportSvcStatus(3u, v10, 0x2710u);
  if ( ptpp )
  {
    CloseThreadpool(ptpp);
    ptpp = 0;
  }
  ReportSvcStatus(3u, v11, 0x2710u);
  if ( CDsmMetadataTask::s_hMutex )
  {
    CloseHandle(CDsmMetadataTask::s_hMutex);
    CDsmMetadataTask::s_hMutex = 0;
  }
  if ( CDsmMetadataTask::s_pPkgSrc )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)CDsmMetadataTask::s_pPkgSrc + 80LL))(CDsmMetadataTask::s_pPkgSrc);
  ATL::CComPtrBase<IDsmMetadataPackageSource>::Release();
  ATL::CComPtrBase<IDsmPropertySource>::Release();
  CoDisconnectObject(CDsmMetadataTask::s_MetadataNotificationHandler, 0);
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&CDsmMetadataTask::s_MetadataNotificationHandler);
  CDsmMetadataTask::s_fProviderLoaded = 0;
  CDsmMetadataTask::s_fProviderAvailable = 1;
  ReportSvcStatus(3u, v12, 0x2710u);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    ObjectCount = CDevNotify::get_ObjectCount();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids, ObjectCount);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context, DsmServiceShutdown, v13, 1, v16);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    WPP_SF_(v14[2], 18, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
}

```

## disassembly

```asm
0x1800240dc  mov     [rsp+arg_0], rbp
0x1800240e1  mov     [rsp+arg_8], rsi
0x1800240e6  push    r15
0x1800240e8  sub     rsp, 50h
0x1800240ec  mov     rax, cs:__security_cookie
0x1800240f3  xor     rax, rsp
0x1800240f6  mov     [rsp+58h+var_18], rax
0x1800240fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024102  lea     r15, WPP_GLOBAL_Control
0x180024109  cmp     rcx, r15
0x18002410c  jz      short loc_180024129
0x18002410e  test    byte ptr [rcx+1Ch], 1
0x180024112  jz      short loc_180024129
0x180024114  mov     rcx, [rcx+10h]
0x180024118  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18002411f  mov     edx, 10h
0x180024124  call    WPP_SF_
0x180024129  mov     edx, 6
0x18002412e  lea     rcx, ?g_DsmCore@@3VCDsmCore@@A; CDsmCore g_DsmCore
0x180024135  call    ?_SetCoreEvent@CDsmCore@@AEAAXW4CORE_EVENT@1@@Z; CDsmCore::_SetCoreEvent(CDsmCore::CORE_EVENT)
0x18002413a  mov     rcx, qword ptr cs:xmmword_180059F20; this
0x180024141  call    ?Close@EventScan@@QEAAJXZ; EventScan::Close(void)
0x180024146  mov     rcx, qword ptr cs:xmmword_180059F10
0x18002414d  mov     edx, 2
0x180024152  call    ?SetContainerManagerMode@ContainerManager@@QEAAXW4ContainerManagerMode@@@Z; ContainerManager::SetContainerManagerMode(ContainerManagerMode)
0x180024157  mov     rcx, qword ptr cs:xmmword_180059EC0; this
0x18002415e  call    ?Stop@JobScheduler@@QEAAJXZ; JobScheduler::Stop(void)
0x180024163  cmp     cs:?DrvRecoverySpUtilsInitialized@@3HA, 0; int DrvRecoverySpUtilsInitialized
0x18002416a  jz      short loc_18002417B
0x18002416c  call    pSetupUninitializeUtils
0x180024171  mov     cs:?DrvRecoverySpUtilsInitialized@@3HA, 0; int DrvRecoverySpUtilsInitialized
0x18002417b  lea     rcx, dword_180059110
0x180024182  call    TraceLoggingUnregister_EventUnregister
0x180024187  mov     esi, 2710h
0x18002418c  mov     ebp, 3
0x180024191  mov     r8d, esi; unsigned int
0x180024194  mov     ecx, ebp; unsigned int
0x180024196  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x18002419b  mov     rcx, qword ptr cs:xmmword_180059F10; this
0x1800241a2  call    ?Shutdown@ContainerManager@@QEAAJXZ; ContainerManager::Shutdown(void)
0x1800241a7  mov     r8d, esi; unsigned int
0x1800241aa  mov     ecx, ebp; unsigned int
0x1800241ac  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800241b1  call    ?s_RequestShutdown@CDevNotify@@SAXXZ; CDevNotify::s_RequestShutdown(void)
0x1800241b6  mov     r8d, esi; unsigned int
0x1800241b9  mov     ecx, ebp; unsigned int
0x1800241bb  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800241c0  call    ?DsmRpcShutdown@@YAXXZ; DsmRpcShutdown(void)
0x1800241c5  mov     r8d, esi; unsigned int
0x1800241c8  mov     ecx, ebp; unsigned int
0x1800241ca  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800241cf  call    ?s_CompleteShutdown@CDevNotify@@SAXXZ; CDevNotify::s_CompleteShutdown(void)
0x1800241d4  mov     r8d, esi; unsigned int
0x1800241d7  mov     ecx, ebp; unsigned int
0x1800241d9  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800241de  call    ?Close@CNetworkEvents@@QEAAXXZ; CNetworkEvents::Close(void)
0x1800241e3  mov     r8d, esi; unsigned int
0x1800241e6  mov     ecx, ebp; unsigned int
0x1800241e8  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800241ed  mov     rcx, cs:pti; pti
0x1800241f4  test    rcx, rcx
0x1800241f7  jz      short loc_18002421A
0x1800241f9  lea     edx, [rbp-2]; fCancelPendingCallbacks
0x1800241fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024202  mov     rcx, cs:pti; pti
0x180024209  call    cs:__imp_CloseThreadpoolTimer
0x18002420f  mov     cs:pti, 0
0x18002421a  mov     r8d, esi; unsigned int
0x18002421d  mov     ecx, ebp; unsigned int
0x18002421f  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x180024224  mov     rcx, cs:ptpp; ptpp
0x18002422b  test    rcx, rcx
0x18002422e  jz      short loc_180024241
0x180024230  call    cs:__imp_CloseThreadpool
0x180024236  mov     cs:ptpp, 0
0x180024241  mov     r8d, esi; unsigned int
0x180024244  mov     ecx, ebp; unsigned int
0x180024246  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x18002424b  mov     rcx, cs:?s_hMutex@CDsmMetadataTask@@0PEAXEA; hObject
0x180024252  test    rcx, rcx
0x180024255  jz      short loc_180024268
0x180024257  call    cs:__imp_CloseHandle
0x18002425d  mov     cs:?s_hMutex@CDsmMetadataTask@@0PEAXEA, 0; void * CDsmMetadataTask::s_hMutex
0x180024268  mov     rcx, cs:?s_pPkgSrc@CDsmMetadataTask@@0V?$CComPtr@UIDsmMetadataPackageSource@@@ATL@@A; ATL::CComPtr<IDsmMetadataPackageSource> CDsmMetadataTask::s_pPkgSrc
0x18002426f  test    rcx, rcx
0x180024272  jz      short loc_180024280
0x180024274  mov     rax, [rcx]
0x180024277  mov     rax, [rax+50h]
0x18002427b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024280  call    ?Release@?$CComPtrBase@UIDsmMetadataPackageSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDsmMetadataPackageSource>::Release(void)
0x180024285  call    ?Release@?$CComPtrBase@UIDsmPropertySource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDsmPropertySource>::Release(void)
0x18002428a  mov     rcx, cs:?s_MetadataNotificationHandler@CDsmMetadataTask@@0V?$ComPtr@VCDsmMetadataNotificationHandler@@@WRL@Microsoft@@A; pUnk
0x180024291  xor     edx, edx; dwReserved
0x180024293  call    cs:__imp_CoDisconnectObject
0x180024299  lea     rcx, ?s_MetadataNotificationHandler@CDsmMetadataTask@@0V?$ComPtr@VCDsmMetadataNotificationHandler@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CDsmMetadataNotificationHandler> CDsmMetadataTask::s_MetadataNotificationHandler
0x1800242a0  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x1800242a5  mov     r8d, esi; unsigned int
0x1800242a8  mov     cs:?s_fProviderLoaded@CDsmMetadataTask@@0_NA, 0; bool CDsmMetadataTask::s_fProviderLoaded
0x1800242af  mov     ecx, ebp; unsigned int
0x1800242b1  mov     cs:?s_fProviderAvailable@CDsmMetadataTask@@0_NA, 1; bool CDsmMetadataTask::s_fProviderAvailable
0x1800242b8  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800242bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242c4  cmp     rcx, r15
0x1800242c7  jz      short loc_1800242FA
0x1800242c9  test    byte ptr [rcx+1Ch], 1
0x1800242cd  jz      short loc_1800242FA
0x1800242cf  call    ?get_ObjectCount@CDevNotify@@SAIXZ; CDevNotify::get_ObjectCount(void)
0x1800242d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242db  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x1800242e2  mov     edx, 11h
0x1800242e7  mov     r9d, eax
0x1800242ea  mov     rcx, [rcx+10h]
0x1800242ee  call    WPP_SF_d
0x1800242f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242fa  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180024301  jz      short loc_18002432D
0x180024303  lea     rax, [rsp+58h+var_28]
0x180024308  mov     r9d, 1
0x18002430e  lea     rdx, DsmServiceShutdown
0x180024315  mov     [rsp+58h+var_38], rax
0x18002431a  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x180024321  call    McGenEventWrite_EventWriteTransfer
0x180024326  mov     rcx, cs:WPP_GLOBAL_Control
0x18002432d  cmp     rcx, r15
0x180024330  jz      short loc_18002434D
0x180024332  test    byte ptr [rcx+1Ch], 1
0x180024336  jz      short loc_18002434D
0x180024338  mov     rcx, [rcx+10h]
0x18002433c  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x180024343  mov     edx, 12h
0x180024348  call    WPP_SF_
0x18002434d  mov     rcx, [rsp+58h+var_18]
0x180024352  xor     rcx, rsp; StackCookie
0x180024355  call    __security_check_cookie
0x18002435a  mov     rbp, [rsp+58h+arg_0]
0x18002435f  mov     rsi, [rsp+58h+arg_8]
0x180024364  add     rsp, 50h
0x180024368  pop     r15
0x18002436a  retn
```
