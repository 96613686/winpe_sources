# Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::SvcMain(std::span<ushort const *,-1>)

- ea: `0x140031fbc`
- end: `0x14003216d`
- name: `?SvcMain@?$service_base@VReFsDedupService@ReFs@FileSystem@Windows@@VReFsDedupServiceLogging@234@$0A@$0HFDA@$0HFDA@@Service@Win32@Microsoft@@QEAAXV?$span@PEBG$0?0@std@@@Z`
- size: `433`
- prototype: `void()`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140030600`

## callees

- `0x140004870`
- `0x14000dbe0`
- `0x14000e22c`
- `0x140015bc4`
- `0x140018710`
- `0x140018f38`
- `0x1400308c4`
- `0x140031254`
- `0x140031fbc`
- `0x140032174`
- `0x1400322b4`
- `0x14003536c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x140032097`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x140032097`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1400320dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1400320dc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140032020`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140032020`

## string_xrefs

- `0x140032051`: `onecore\base\fs\refsdedupsvc\exe\exe_service.h`
- `0x1400320ff`: `onecore\base\fs\refsdedupsvc\exe\exe_service.h`
- `0x140032041`: `RegisterServiceCtrlHandlerExW failed!`

## pseudocode

```c
void Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::SvcMain()
{
  void *v0; // rdi
  HANDLE v1; // rbx
  unsigned int v2; // eax
  wil *v3; // rcx
  const char *v4; // rbx
  const char *dwMilliseconds; // [rsp+20h] [rbp-198h]
  const char *dwFlags; // [rsp+28h] [rbp-190h]
  const char *dwFlagsa; // [rsp+28h] [rbp-190h]
  const char *dwFlagsb; // [rsp+28h] [rbp-190h]
  const char *dwFlagsc; // [rsp+28h] [rbp-190h]
  _BYTE v10[8]; // [rsp+30h] [rbp-188h] BYREF
  _BYTE v11[12]; // [rsp+38h] [rbp-180h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-174h]
  _QWORD v13[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v13);
  v13[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::StartActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity *)v13);
  *(_QWORD *)&xmmword_140244010 = RegisterServiceCtrlHandlerExW(
                                    L"refsdedupsvc",
                                    `Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::SvcMain'::`3'::_lambda_1_::_lambda_invoker_cdecl_,
                                    &Windows::FileSystem::ReFs::g_DedupServiceInstance);
  try
  {
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\exe_service.h",
      (const char *)((_QWORD)xmmword_140244010 == 0),
      (bool)"RegisterServiceCtrlHandlerExW failed!",
      dwFlagsb);
    Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::UpdateStatus(
      (LPSERVICE_STATUS)&Windows::FileSystem::ReFs::g_DedupServiceInstance,
      (char *)2,
      0);
    v0 = (void *)*((_QWORD *)&xmmword_140244010 + 1);
    v1 = phNewWaitObject;
    if ( phNewWaitObject )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v10);
      UnregisterWait(v1);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
    }
    phNewWaitObject = 0;
    v2 = RegisterWaitForSingleObject(
           &phNewWaitObject,
           v0,
           `Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::SvcMain'::`3'::_lambda_2_::_lambda_invoker_cdecl_,
           &Windows::FileSystem::ReFs::g_DedupServiceInstance,
           0xFFFFFFFF,
           8u);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\exe_service.h",
      (const char *)v2,
      (int)"Failed RegisterWait for the stop event",
      dwFlagsc);
    Windows::FileSystem::ReFs::ReFsDedupService::ServiceStart((Windows::FileSystem::ReFs::ReFsDedupService *)&Windows::FileSystem::ReFs::g_DedupServiceInstance);
    Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::UpdateStatus(
      (LPSERVICE_STATUS)&Windows::FileSystem::ReFs::g_DedupServiceInstance,
      (char *)4,
      0);
    wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v13,
      0);
  }
  catch ( winrt::hresult_error v11 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\exe_service.h",
      (const char *)v12,
      (int)"Caught winrt::hresult_error",
      dwFlagsa);
    Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::Stop(
      (LPSERVICE_STATUS)&Windows::FileSystem::ReFs::g_DedupServiceInstance,
      v12);
    winrt::hresult_error::~hresult_error((winrt::hresult_error *)v11);
  }
  catch ( std::exception )
  {
    v4 = (const char *)(unsigned int)wil::ResultFromCaughtException(v3);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\exe_service.h",
      v4,
      (int)"Caught std::exception (or derived exception)",
      dwFlags);
    Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::Stop(
      (LPSERVICE_STATUS)&Windows::FileSystem::ReFs::g_DedupServiceInstance,
      (unsigned int)v4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\exe_service.h",
      "SvcMainCallback caught unknown C++ exception",
      dwMilliseconds);
    Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::Stop(
      (LPSERVICE_STATUS)&Windows::FileSystem::ReFs::g_DedupServiceInstance,
      0x1Fu);
  }
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::~SvcMainActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity *)v13);
}

```

## disassembly

```asm
0x140031fbc  mov     [rsp+arg_0], rbx
0x140031fc1  mov     [rsp+arg_8], rsi
0x140031fc6  push    rdi
0x140031fc7  sub     rsp, 1B0h
0x140031fce  mov     rax, cs:__security_cookie
0x140031fd5  xor     rax, rsp
0x140031fd8  mov     [rsp+1B8h+var_18], rax
0x140031fe0  lea     rdx, aSvcmainactivit; "SvcMainActivity"
0x140031fe7  lea     rcx, [rsp+1B8h+var_168]; struct wil::details::IFailureCallback *
0x140031fec  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140031ff1  lea     rax, ??_7SvcMainActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::`vftable'
0x140031ff8  mov     [rsp+1B8h+var_168], rax
0x140031ffd  lea     rcx, [rsp+1B8h+var_168]; this
0x140032002  call    ?StartActivity@SvcMainActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::StartActivity(void)
0x140032007  nop
0x140032008  lea     rsi, ?g_DedupServiceInstance@ReFs@FileSystem@Windows@@3VReFsDedupService@123@A; Windows::FileSystem::ReFs::ReFsDedupService Windows::FileSystem::ReFs::g_DedupServiceInstance
0x14003200f  mov     r8, rsi; lpContext
0x140032012  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?2??SvcMain@?$service_base@VReFsDedupService@ReFs@FileSystem@Windows@@VReFsDedupServiceLogging@234@$0A@$0HFDA@$0HFDA@@Service@Win32@Microsoft@@QEAAXV?$span@PEBG$0?0@std@@@Z@SA@KKPEAX1@Z; lpHandlerProc
0x140032019  lea     rcx, ServiceName; "refsdedupsvc"
0x140032020  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140032027  nop     dword ptr [rax+rax+00h]
0x14003202c  mov     qword ptr cs:xmmword_140244010, rax
0x140032033  test    rax, rax
0x140032036  setz    al
0x140032039  mov     rcx, [rsp+1B8h]; this
0x140032041  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandlerExW failed!"
0x140032048  mov     qword ptr [rsp+1B8h+dwMilliseconds], rdx; bool
0x14003204d  movzx   r9d, al; char *
0x140032051  lea     r8, aOnecoreBaseFsR_26; "onecore\\base\\fs\\refsdedupsvc\\exe\\e"...
0x140032058  mov     edx, 8Ch; void *
0x14003205d  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x140032062  mov     r9d, 7530h
0x140032068  xor     r8d, r8d; unsigned int
0x14003206b  lea     edx, [r8+2]; char *
0x14003206f  mov     rcx, rsi; lpServiceStatus
0x140032072  call    ?UpdateStatus@?$service_base@VReFsDedupService@ReFs@FileSystem@Windows@@VReFsDedupServiceLogging@234@$0A@$0HFDA@$0HFDA@@Service@Win32@Microsoft@@AEAAXKKK@Z; Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::UpdateStatus(ulong,ulong,ulong)
0x140032077  mov     rdi, qword ptr cs:xmmword_140244010+8
0x14003207e  mov     rbx, cs:phNewWaitObject
0x140032085  test    rbx, rbx
0x140032088  jz      short loc_1400320AD
0x14003208a  lea     rcx, [rsp+1B8h+var_188]; this
0x14003208f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140032094  mov     rcx, rbx; WaitHandle
0x140032097  call    cs:__imp_UnregisterWait
0x14003209e  nop     dword ptr [rax+rax+00h]
0x1400320a3  lea     rcx, [rsp+1B8h+var_188]; this
0x1400320a8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400320ad  mov     cs:phNewWaitObject, 0
0x1400320b8  mov     dword ptr [rsp+1B8h+dwFlags], 8; char *
0x1400320c0  mov     [rsp+1B8h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400320c8  mov     r9, rsi; Context
0x1400320cb  lea     r8, ?_lambda_invoker_cdecl_@_lambda_2_@?2??SvcMain@?$service_base@VReFsDedupService@ReFs@FileSystem@Windows@@VReFsDedupServiceLogging@234@$0A@$0HFDA@$0HFDA@@Service@Win32@Microsoft@@QEAAXV?$span@PEBG$0?0@std@@@Z@SA@PEAXE@Z; Callback
0x1400320d2  mov     rdx, rdi; hObject
0x1400320d5  lea     rcx, phNewWaitObject; phNewWaitObject
0x1400320dc  call    cs:__imp_RegisterWaitForSingleObject
0x1400320e3  nop     dword ptr [rax+rax+00h]
0x1400320e8  mov     rcx, [rsp+1B8h]; this
0x1400320f0  lea     rdx, aFailedRegister; "Failed RegisterWait for the stop event"
0x1400320f7  mov     qword ptr [rsp+1B8h+dwMilliseconds], rdx; int
0x1400320fc  mov     r9d, eax; char *
0x1400320ff  lea     r8, aOnecoreBaseFsR_26; "onecore\\base\\fs\\refsdedupsvc\\exe\\e"...
0x140032106  mov     edx, 9Fh; void *
0x14003210b  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x140032110  mov     rcx, rsi; this
0x140032113  call    ?ServiceStart@ReFsDedupService@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupService::ServiceStart(void)
0x140032118  xor     r9d, r9d
0x14003211b  xor     r8d, r8d; unsigned int
0x14003211e  lea     edx, [r9+4]; char *
0x140032122  mov     rcx, rsi; lpServiceStatus
0x140032125  call    ?UpdateStatus@?$service_base@VReFsDedupService@ReFs@FileSystem@Windows@@VReFsDedupServiceLogging@234@$0A@$0HFDA@$0HFDA@@Service@Win32@Microsoft@@AEAAXKKK@Z; Microsoft::Win32::Service::service_base<Windows::FileSystem::ReFs::ReFsDedupService,Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,30000,30000>::UpdateStatus(ulong,ulong,ulong)
0x14003212a  xor     edx, edx
0x14003212c  lea     rcx, [rsp+1B8h+var_168]
0x140032131  call    ?Stop@?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140032136  nop
0x140032137  lea     rcx, [rsp+1B8h+var_168]; this
0x14003213c  call    ??1SvcMainActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::SvcMainActivity::~SvcMainActivity(void)
0x140032141  nop
0x140032142  mov     rcx, [rsp+1B8h+var_18]
0x14003214a  xor     rcx, rsp; StackCookie
0x14003214d  call    __security_check_cookie
0x140032152  lea     r11, [rsp+1B8h+var_8]
0x14003215a  mov     rbx, [r11+10h]
0x14003215e  mov     rsi, [r11+18h]
0x140032162  mov     rsp, r11
0x140032165  pop     rdi
0x140032166  retn
0x140032168  jmp     short loc_140032137
0x14003216a  jmp     short loc_140032137
```
