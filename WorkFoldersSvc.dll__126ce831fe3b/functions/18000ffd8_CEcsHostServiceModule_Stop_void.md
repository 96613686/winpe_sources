# CEcsHostServiceModule::Stop(void)

- ea: `0x18000ffd8`
- end: `0x180010327`
- name: `?Stop@CEcsHostServiceModule@@AEAAXXZ`
- size: `847`
- prototype: `void __fastcall(CEcsHostServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ded0`

## callees

- `0x180002ab0`
- `0x180004420`
- `0x180007d34`
- `0x180007e10`
- `0x1800084ac`
- `0x180008b8c`
- `0x180009734`
- `0x18000974c`
- `0x180009774`
- `0x18000ffd8`
- `0x180010d38`
- `0x180011084`
- `0x1800110fc`
- `0x180011290`
- `0x1800112c0`
- `0x180011314`
- `0x18001133c`
- `0x18002257c`
- `0x180027850`
- `0x18006023c`
- `0x1800ba68c`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180010130`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180010130`
- `KERNEL32!FreeLibrary` at `0x1800102e3`
- `KERNEL32!FreeLibrary` at `0x1800102e3`
- `USER32!UnregisterDeviceNotification` at `0x180010220`
- `USER32!UnregisterDeviceNotification` at `0x180010220`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x180010207`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x180010207`

## string_xrefs

- `0x180010058`: `CEcsHostServiceModule::Stop`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CEcsHostServiceModule::Stop(CEcsHostServiceModule *this)
{
  _BYTE *v1; // rax
  char v2; // al
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // [rsp+40h] [rbp-88h] BYREF
  int v6; // [rsp+44h] [rbp-84h]
  char v7; // [rsp+48h] [rbp-80h]
  const char *v8; // [rsp+50h] [rbp-78h]
  __int64 v9; // [rsp+58h] [rbp-70h]
  _QWORD v10[2]; // [rsp+60h] [rbp-68h] BYREF
  int v11; // [rsp+70h] [rbp-58h] BYREF
  int v12; // [rsp+74h] [rbp-54h] BYREF
  int v13; // [rsp+78h] [rbp-50h] BYREF
  int v14; // [rsp+7Ch] [rbp-4Ch] BYREF
  __int64 v15; // [rsp+80h] [rbp-48h] BYREF
  const ATL::CAtlException *v16; // [rsp+88h] [rbp-40h] BYREF
  const ATL::CAtlException *v17; // [rsp+90h] [rbp-38h] BYREF
  const ATL::CAtlException *v18; // [rsp+98h] [rbp-30h] BYREF
  const ATL::CAtlException *v19; // [rsp+A0h] [rbp-28h] BYREF
  _BYTE v20[16]; // [rsp+A8h] [rbp-20h] BYREF

  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v2 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
  }
  if ( (v1[68] & 8) == 0 || v1[65] < 6u )
    goto LABEL_8;
  v2 = 1;
LABEL_9:
  v5 = 0;
  v6 = 954;
  v7 = v2;
  v8 = "CEcsHostServiceModule::Stop";
  v9 = 0;
  try
  {
    if ( ppv )
    {
      ((void (__fastcall *)(struct IUnknown *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))ppv->lpVtbl[1].QueryInterface)(
        ppv,
        CEcsHostServiceModule::RevokeClassObjectsCallback,
        0,
        &IID_ICallbackWithNoReentrancyToApplicationSTA,
        3,
        0);
      ATL::CComPtr<IContextCallback>::operator=(&ppv);
    }
    ServiceStatus.dwControlsAccepted = 0;
    if ( qword_1801AF848 )
    {
      try
      {
        CNetworkStatusController::StopMonitoring(qword_1801AF848);
      }
      catch ( long v11 )
      {
        v5 = v11;
      }
      catch ( std::bad_alloc )
      {
        HIWORD(v6) = 979;
        v5 = -2147024882;
      }
      catch ( std::exception )
      {
        HIWORD(v6) = 979;
        v5 = -2147418113;
      }
      catch ( const ATL::CAtlException *v16 )
      {
        HIWORD(v6) = 979;
        v5 = *(_DWORD *)v16;
      }
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            50,
            WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
            (unsigned int)v5);
        }
        v5 = 0;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&qword_1801AF848);
    }
    if ( ptpcg )
    {
      CloseThreadpoolCleanupGroupMembers(ptpcg, 0, 0);
      v15 = 0;
      EcsUniqueHandle<_TP_CLEANUP_GROUP *,Win32ThreadPoolCleanupGroupDeleter,0>::reset(&ptpcg, &v15);
    }
    if ( byte_1801AF8C8 )
      byte_1801AF8C8 = 0;
    if ( std::operator!=<CFileDownloadTask>(&pv) )
    {
      try
      {
        CSyncStateManager::Stop((CSyncStateManager *)pv);
      }
      catch ( long v12 )
      {
        v5 = v12;
      }
      catch ( std::bad_alloc )
      {
        HIWORD(v6) = 1011;
        v5 = -2147024882;
      }
      catch ( std::exception )
      {
        HIWORD(v6) = 1011;
        v5 = -2147418113;
      }
      catch ( const ATL::CAtlException *v17 )
      {
        HIWORD(v6) = 1011;
        v5 = *(_DWORD *)v17;
      }
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            51,
            WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
            (unsigned int)v5);
        }
        v5 = 0;
      }
      std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(v10);
      std::shared_ptr<CUserStateManager>::operator=(&pv, v10);
      std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v10);
    }
    ATL::CComPtr<ISyncSharePartnershipManager>::operator=(v3, 0);
    if ( RegistrationHandle )
    {
      PowerSettingUnregisterNotification(RegistrationHandle);
      RegistrationHandle = 0;
    }
    if ( Handle )
    {
      UnregisterDeviceNotification(Handle);
      Handle = 0;
    }
    v10[0] = 0;
    EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hEvent, v10);
    if ( byte_1801AF8D8 )
    {
      try
      {
        CEcsHelperLibrary::UnInit();
      }
      catch ( long v13 )
      {
        v5 = v13;
      }
      catch ( std::bad_alloc )
      {
        HIWORD(v6) = 1043;
        v5 = -2147024882;
      }
      catch ( std::exception )
      {
        HIWORD(v6) = 1043;
        v5 = -2147418113;
      }
      catch ( const ATL::CAtlException *v18 )
      {
        HIWORD(v6) = 1043;
        v5 = *(_DWORD *)v18;
      }
      if ( v5 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            52,
            WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
            (unsigned int)v5);
        }
        v5 = 0;
      }
      byte_1801AF8D8 = 0;
    }
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(&ECSHOST_Context, ECSHOST_EVENT_PROCESS_TERMINATING, v4, 1, v20);
    McGenEventUnregister_EventUnregister();
    if ( CEcsFunctionTracer::s_hResourceDll )
      FreeLibrary(CEcsFunctionTracer::s_hResourceDll);
    CSelectiveWipe::UnloadLibraries();
    CEcsAsimovTelemetry::UnInit();
  }
  catch ( long v14 )
  {
    v5 = v14;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v6) = 1064;
    v5 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v6) = 1064;
    v5 = -2147418113;
  }
  catch ( const ATL::CAtlException *v19 )
  {
    HIWORD(v6) = 1064;
    v5 = *(_DWORD *)v19;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v5);
}

```

## disassembly

```asm
0x18000ffd8  mov     [rsp+arg_0], rbx
0x18000ffdd  push    rdi
0x18000ffde  sub     rsp, 0C0h
0x18000ffe5  mov     rax, cs:__security_cookie
0x18000ffec  xor     rax, rsp
0x18000ffef  mov     [rsp+0C8h+var_10], rax
0x18000fff7  lea     rdi, WPP_GLOBAL_Control
0x18000fffe  mov     rax, cs:WPP_GLOBAL_Control
0x180010005  cmp     rax, rdi
0x180010008  jz      short loc_180010032
0x18001000a  test    byte ptr [rax+44h], 8
0x18001000e  jz      short loc_180010044
0x180010010  cmp     byte ptr [rax+41h], 6
0x180010014  jb      short loc_180010032
0x180010016  mov     edx, 31h ; '1'
0x18001001b  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x180010022  mov     rcx, [rax+38h]
0x180010026  call    WPP_SF_
0x18001002b  mov     rax, cs:WPP_GLOBAL_Control
0x180010032  test    byte ptr [rax+44h], 8
0x180010036  jz      short loc_180010044
0x180010038  cmp     byte ptr [rax+41h], 6
0x18001003c  jb      short loc_180010044
0x18001003e  mov     al, 1
0x180010040  xor     ebx, ebx
0x180010042  jmp     short loc_180010048
0x180010044  xor     ebx, ebx
0x180010046  mov     al, bl
0x180010048  mov     [rsp+0C8h+var_88], ebx
0x18001004c  mov     [rsp+0C8h+var_84], 3BAh
0x180010054  mov     [rsp+0C8h+var_80], al
0x180010058  lea     rax, aCecshostservic_13; "CEcsHostServiceModule::Stop"
0x18001005f  mov     [rsp+0C8h+var_78], rax
0x180010064  mov     [rsp+0C8h+var_70], rbx
0x180010069  mov     rcx, cs:ppv
0x180010070  test    rcx, rcx
0x180010073  jz      short loc_1800100AB
0x180010075  mov     rax, [rcx]
0x180010078  mov     [rsp+0C8h+var_A0], rbx
0x18001007d  mov     dword ptr [rsp+0C8h+var_A8], 3
0x180010085  lea     r9, IID_ICallbackWithNoReentrancyToApplicationSTA
0x18001008c  xor     r8d, r8d
0x18001008f  lea     rdx, ?RevokeClassObjectsCallback@CEcsHostServiceModule@@CAJPEAUtagComCallData@@@Z; CEcsHostServiceModule::RevokeClassObjectsCallback(tagComCallData *)
0x180010096  mov     rax, [rax+18h]
0x18001009a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009f  lea     rcx, ppv
0x1800100a6  call    ??4?$CComPtr@UIContextCallback@@@ATL@@QEAAPEAUIContextCallback@@PEAU2@@Z; ATL::CComPtr<IContextCallback>::operator=(IContextCallback *)
0x1800100ab  mov     cs:ServiceStatus.dwControlsAccepted, ebx
0x1800100b1  cmp     cs:qword_1801AF848, rbx
0x1800100b8  jz      short loc_18001011F
0x1800100ba  mov     rcx, cs:qword_1801AF848; this
0x1800100c1  call    ?StopMonitoring@CNetworkStatusController@@QEAAXXZ; CNetworkStatusController::StopMonitoring(void)
0x1800100c6  nop
0x1800100c7  jmp     short loc_1800100D8
0x1800100c9  jmp     short loc_1800100CF
0x1800100cb  jmp     short loc_1800100CF
0x1800100cd  jmp     short $+2
0x1800100cf  xor     ebx, ebx
0x1800100d1  lea     rdi, WPP_GLOBAL_Control
0x1800100d8  mov     r9d, [rsp+0C8h+var_88]
0x1800100dd  test    r9d, r9d
0x1800100e0  jns     short loc_180010113
0x1800100e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100e9  cmp     rcx, rdi
0x1800100ec  jz      short loc_18001010F
0x1800100ee  test    byte ptr [rcx+44h], 8
0x1800100f2  jz      short loc_18001010F
0x1800100f4  cmp     byte ptr [rcx+41h], 2
0x1800100f8  jb      short loc_18001010F
0x1800100fa  mov     edx, 32h ; '2'
0x1800100ff  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x180010106  mov     rcx, [rcx+38h]
0x18001010a  call    WPP_SF_d
0x18001010f  mov     [rsp+0C8h+var_88], ebx
0x180010113  lea     rcx, qword_1801AF848
0x18001011a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001011f  mov     rcx, cs:ptpcg; ptpcg
0x180010126  test    rcx, rcx
0x180010129  jz      short loc_180010152
0x18001012b  xor     r8d, r8d; pvCleanupContext
0x18001012e  xor     edx, edx; fCancelPendingCallbacks
0x180010130  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180010136  mov     [rsp+0C8h+var_48], rbx
0x18001013e  lea     rdx, [rsp+0C8h+var_48]
0x180010146  lea     rcx, ptpcg
0x18001014d  call    ?reset@?$EcsUniqueHandle@PEAU_TP_CLEANUP_GROUP@@UWin32ThreadPoolCleanupGroupDeleter@@$0A@@@QEAAXAEBQEAU_TP_CLEANUP_GROUP@@@Z; EcsUniqueHandle<_TP_CLEANUP_GROUP *,Win32ThreadPoolCleanupGroupDeleter,0>::reset(_TP_CLEANUP_GROUP * const &)
0x180010152  cmp     cs:byte_1801AF8C8, bl
0x180010158  jz      short loc_180010160
0x18001015a  mov     cs:byte_1801AF8C8, bl
0x180010160  lea     rcx, pv
0x180010167  call    ??$?9VCFileDownloadTask@@@std@@YA_NAEBV?$shared_ptr@VCFileDownloadTask@@@0@$$T@Z; std::operator!=<CFileDownloadTask>(std::shared_ptr<CFileDownloadTask> const &,std::nullptr_t)
0x18001016c  test    al, al
0x18001016e  jz      loc_1800101F4
0x180010174  mov     rcx, cs:pv; this
0x18001017b  call    ?Stop@CSyncStateManager@@QEAAXXZ; CSyncStateManager::Stop(void)
0x180010180  nop
0x180010181  jmp     short loc_180010192
0x180010183  jmp     short loc_180010189
0x180010185  jmp     short loc_180010189
0x180010187  jmp     short $+2
0x180010189  xor     ebx, ebx
0x18001018b  lea     rdi, WPP_GLOBAL_Control
0x180010192  mov     r9d, [rsp+0C8h+var_88]
0x180010197  test    r9d, r9d
0x18001019a  jns     short loc_1800101CD
0x18001019c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101a3  cmp     rcx, rdi
0x1800101a6  jz      short loc_1800101C9
0x1800101a8  test    byte ptr [rcx+44h], 8
0x1800101ac  jz      short loc_1800101C9
0x1800101ae  cmp     byte ptr [rcx+41h], 2
0x1800101b2  jb      short loc_1800101C9
0x1800101b4  mov     edx, 33h ; '3'
0x1800101b9  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x1800101c0  mov     rcx, [rcx+38h]
0x1800101c4  call    WPP_SF_d
0x1800101c9  mov     [rsp+0C8h+var_88], ebx
0x1800101cd  lea     rcx, [rsp+0C8h+var_68]
0x1800101d2  call    ??0?$shared_ptr@VCSyncStateManager@@@std@@QEAA@$$T@Z; std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(std::nullptr_t)
0x1800101d7  nop
0x1800101d8  lea     rdx, [rsp+0C8h+var_68]
0x1800101dd  lea     rcx, pv
0x1800101e4  call    ??4?$shared_ptr@VCUserStateManager@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CUserStateManager>::operator=(std::shared_ptr<CUserStateManager> &&)
0x1800101e9  nop
0x1800101ea  lea     rcx, [rsp+0C8h+var_68]
0x1800101ef  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x1800101f4  xor     edx, edx
0x1800101f6  call    ??4?$CComPtr@UISyncSharePartnershipManager@@@ATL@@QEAAPEAUISyncSharePartnershipManager@@PEAU2@@Z; ATL::CComPtr<ISyncSharePartnershipManager>::operator=(ISyncSharePartnershipManager *)
0x1800101fb  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x180010202  test    rcx, rcx
0x180010205  jz      short loc_180010214
0x180010207  call    cs:__imp_PowerSettingUnregisterNotification
0x18001020d  mov     cs:RegistrationHandle, rbx
0x180010214  mov     rcx, cs:Handle; Handle
0x18001021b  test    rcx, rcx
0x18001021e  jz      short loc_18001022D
0x180010220  call    cs:__imp_UnregisterDeviceNotification
0x180010226  mov     cs:Handle, rbx
0x18001022d  mov     [rsp+0C8h+var_68], rbx
0x180010232  lea     rdx, [rsp+0C8h+var_68]
0x180010237  lea     rcx, hEvent
0x18001023e  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x180010243  cmp     cs:byte_1801AF8D8, bl
0x180010249  jz      short loc_1800102A3
0x18001024b  call    ?UnInit@CEcsHelperLibrary@@SAXXZ; CEcsHelperLibrary::UnInit(void)
0x180010250  nop
0x180010251  jmp     short loc_180010262
0x180010253  jmp     short loc_180010259
0x180010255  jmp     short loc_180010259
0x180010257  jmp     short $+2
0x180010259  xor     ebx, ebx
0x18001025b  lea     rdi, WPP_GLOBAL_Control
0x180010262  mov     r9d, [rsp+0C8h+var_88]
0x180010267  test    r9d, r9d
0x18001026a  jns     short loc_18001029D
0x18001026c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010273  cmp     rcx, rdi
0x180010276  jz      short loc_180010299
0x180010278  test    byte ptr [rcx+44h], 8
0x18001027c  jz      short loc_180010299
0x18001027e  cmp     byte ptr [rcx+41h], 2
0x180010282  jb      short loc_180010299
0x180010284  mov     edx, 34h ; '4'
0x180010289  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x180010290  mov     rcx, [rcx+38h]
0x180010294  call    WPP_SF_d
0x180010299  mov     [rsp+0C8h+var_88], ebx
0x18001029d  mov     cs:byte_1801AF8D8, bl
0x1800102a3  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 1
0x1800102aa  jz      short loc_1800102D2
0x1800102ac  lea     rax, [rsp+0C8h+var_20]
0x1800102b4  mov     [rsp+0C8h+var_A8], rax
0x1800102b9  mov     r9d, 1
0x1800102bf  lea     rdx, ECSHOST_EVENT_PROCESS_TERMINATING
0x1800102c6  lea     rcx, ECSHOST_Context
0x1800102cd  call    McGenEventWrite_EventWriteTransfer
0x1800102d2  call    McGenEventUnregister_EventUnregister
0x1800102d7  mov     rcx, cs:?s_hResourceDll@CEcsFunctionTracer@@0PEAUHINSTANCE__@@EA; hLibModule
0x1800102de  test    rcx, rcx
0x1800102e1  jz      short loc_1800102E9
0x1800102e3  call    cs:__imp_FreeLibrary
0x1800102e9  call    ?UnloadLibraries@CSelectiveWipe@@SAJXZ; CSelectiveWipe::UnloadLibraries(void)
0x1800102ee  call    ?UnInit@CEcsAsimovTelemetry@@SAXXZ; CEcsAsimovTelemetry::UnInit(void)
0x1800102f3  nop
0x1800102f4  jmp     short loc_1800102FC
0x1800102f6  jmp     short loc_1800102FC
0x1800102f8  jmp     short loc_1800102FC
0x1800102fa  jmp     short $+2
0x1800102fc  lea     rcx, [rsp+0C8h+var_88]; this
0x180010301  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180010306  mov     rcx, [rsp+0C8h+var_10]
0x18001030e  xor     rcx, rsp; StackCookie
0x180010311  call    __security_check_cookie
0x180010316  mov     rbx, [rsp+0C8h+arg_0]
0x18001031e  add     rsp, 0C0h
0x180010325  pop     rdi
0x180010326  retn
```
