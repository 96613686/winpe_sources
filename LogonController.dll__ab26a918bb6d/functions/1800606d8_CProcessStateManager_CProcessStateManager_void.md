# CProcessStateManager::~CProcessStateManager(void)

- ea: `0x1800606d8`
- end: `0x18006099f`
- name: `??1CProcessStateManager@@MEAA@XZ`
- size: `711`
- prototype: `void __fastcall(CProcessStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ca40`

## callees

- `0x18000df10`
- `0x18000ea44`
- `0x18000f730`
- `0x1800211d0`
- `0x180027010`
- `0x18002b2b8`
- `0x18002bc20`
- `0x180042398`
- `0x1800606d8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006083b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006084f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006083b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006084f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060923`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800607b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800607b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800607e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800607e6`
- `SHCORE!SHDeleteValueW` at `0x18006076a`
- `SHCORE!SHDeleteValueW` at `0x1800607d1`
- `SHCORE!SHDeleteValueW` at `0x18006076a`
- `SHCORE!SHDeleteValueW` at `0x1800607d1`

## pseudocode

```c
void __fastcall CProcessStateManager::~CProcessStateManager(CProcessStateManager *this)
{
  HKEY v2; // rcx
  unsigned __int64 *v3; // rdi
  unsigned __int64 i; // rsi
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)this = &CProcessStateManager::`vftable';
  *((_QWORD *)this + 1) = &CProcessStateManager::`vftable'{for `IWeakReferenceSource'};
  hkey = 0;
  *((_QWORD *)this + 2) = &CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &CProcessStateManager::`vftable'{for `Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider'};
  *((_QWORD *)this + 4) = &CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &CProcessStateManager::`vftable'{for `IUserSettingChangeCallback'};
  *((_QWORD *)this + 6) = &CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( RegOpenSessionDataKey(NtCurrentPeb()->SessionId, 0x20006u, &hkey) >= 0 )
    SHDeleteValueW(hkey, 0, L"ShouldLaunchFSIA");
  pvData = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
    L"DefaultAccountAction",
    0x10u,
    0,
    &pvData,
    &pcbData);
  if ( pvData == 2 )
    SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"DefaultAccountAction");
  v2 = hkey;
  hkey = 0;
  if ( v2 )
    RegCloseKey(v2);
  if ( *((_QWORD *)this + 71) )
  {
    *((_QWORD *)this + 71) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 528);
  if ( *((_QWORD *)this + 60) )
  {
    *((_QWORD *)this + 60) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 456);
  WindowsDeleteString(*((HSTRING *)this + 54));
  *((_QWORD *)this + 54) = 0;
  WindowsDeleteString(*((HSTRING *)this + 53));
  *((_QWORD *)this + 53) = 0;
  if ( *((_QWORD *)this + 49) )
  {
    *((_QWORD *)this + 49) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 368);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 344);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 320);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 296);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 272);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,enum Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 248);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 224);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 216);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 208);
  v3 = (unsigned __int64 *)((char *)this + 184);
  if ( *((_QWORD *)this + 22) )
  {
    for ( i = 0; i < *v3; ++i )
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(*((_QWORD *)this + 22) + 8 * i);
    CoTaskMemFree(*((LPVOID *)this + 22));
    *((_QWORD *)this + 22) = 0;
  }
  *v3 = 0;
  *((_QWORD *)this + 25) = 0;
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 168);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 160);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 152);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 144);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 136);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 128);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 96);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IRedirectionManager,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IRedirectionManager,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800606d8  mov     [rsp+arg_18], rbx
0x1800606dd  push    rbp
0x1800606de  push    rsi
0x1800606df  push    rdi
0x1800606e0  sub     rsp, 40h
0x1800606e4  mov     rbx, rcx
0x1800606e7  lea     rax, ??_7CProcessStateManager@@6B@; const CProcessStateManager::`vftable'
0x1800606ee  mov     [rcx], rax
0x1800606f1  lea     r8, [rsp+58h+hkey]; HKEY *
0x1800606f6  lea     rax, ??_7CProcessStateManager@@6BIWeakReferenceSource@@@; const CProcessStateManager::`vftable'{for `IWeakReferenceSource'}
0x1800606fd  xor     ebp, ebp
0x1800606ff  mov     [rcx+8], rax
0x180060703  mov     edx, 20006h; unsigned int
0x180060708  mov     [rsp+58h+hkey], rbp
0x18006070d  lea     rax, ??_7CProcessStateManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUserSettingManager@Controller@Logon@UI@Internal@Windows@@UITelemetryDataProvider@CredProvData@6789@UIDisplayStateProvider@CredProvData@6789@UIUserSettingChangeCallback@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>'}
0x180060714  mov     [rcx+10h], rax
0x180060718  lea     rax, ??_7CProcessStateManager@@6BITelemetryDataProvider@CredProvData@Logon@UI@Internal@Windows@@@; const CProcessStateManager::`vftable'{for `Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider'}
0x18006071f  mov     [rcx+18h], rax
0x180060723  lea     rax, ??_7CProcessStateManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIDisplayStateProvider@CredProvData@Logon@UI@Internal@Windows@@UIUserSettingChangeCallback@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>'}
0x18006072a  mov     [rcx+20h], rax
0x18006072e  lea     rax, ??_7CProcessStateManager@@6BIUserSettingChangeCallback@@@; const CProcessStateManager::`vftable'{for `IUserSettingChangeCallback'}
0x180060735  mov     [rcx+28h], rax
0x180060739  lea     rax, ??_7CProcessStateManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CProcessStateManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180060740  mov     [rcx+30h], rax
0x180060744  mov     rcx, gs:60h
0x18006074d  mov     ecx, [rcx+2C0h]; unsigned int
0x180060753  call    ?RegOpenSessionDataKey@@YAJKKPEAPEAUHKEY__@@@Z; RegOpenSessionDataKey(ulong,ulong,HKEY__ * *)
0x180060758  test    eax, eax
0x18006075a  js      short loc_180060770
0x18006075c  mov     rcx, [rsp+58h+hkey]; hkey
0x180060761  lea     r8, aShouldlaunchfs; "ShouldLaunchFSIA"
0x180060768  xor     edx, edx; pszSubKey
0x18006076a  call    cs:__imp_SHDeleteValueW
0x180060770  lea     rax, [rsp+58h+arg_8]
0x180060775  mov     [rsp+58h+arg_0], ebp
0x180060779  mov     [rsp+58h+pcbData], rax; pcbData
0x18006077e  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x180060785  lea     rax, [rsp+58h+arg_0]
0x18006078a  mov     [rsp+58h+arg_8], 4
0x180060792  mov     [rsp+58h+pvData], rax; pvData
0x180060797  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006079e  mov     rdi, 0FFFFFFFF80000002h
0x1800607a5  mov     [rsp+58h+pdwType], rbp; pdwType
0x1800607aa  mov     r9d, 10h; dwFlags
0x1800607b0  mov     rcx, rdi; hkey
0x1800607b3  call    cs:__imp_RegGetValueW
0x1800607b9  cmp     [rsp+58h+arg_0], 2
0x1800607be  jnz     short loc_1800607D7
0x1800607c0  lea     r8, aDefaultaccount; "DefaultAccountAction"
0x1800607c7  mov     rcx, rdi; hkey
0x1800607ca  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800607d1  call    cs:__imp_SHDeleteValueW
0x1800607d7  mov     rcx, [rsp+58h+hkey]; hKey
0x1800607dc  mov     [rsp+58h+hkey], rbp
0x1800607e1  test    rcx, rcx
0x1800607e4  jz      short loc_1800607EC
0x1800607e6  call    cs:__imp_RegCloseKey
0x1800607ec  mov     rcx, [rbx+238h]
0x1800607f3  test    rcx, rcx
0x1800607f6  jz      short loc_180060804
0x1800607f8  mov     [rbx+238h], rbp
0x1800607ff  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180060804  lea     rcx, [rbx+210h]
0x18006080b  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180060810  mov     rcx, [rbx+1E0h]
0x180060817  test    rcx, rcx
0x18006081a  jz      short loc_180060828
0x18006081c  mov     [rbx+1E0h], rbp
0x180060823  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180060828  lea     rcx, [rbx+1C8h]
0x18006082f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180060834  mov     rcx, [rbx+1B0h]; string
0x18006083b  call    cs:__imp_WindowsDeleteString
0x180060841  mov     [rbx+1B0h], rbp
0x180060848  mov     rcx, [rbx+1A8h]; string
0x18006084f  call    cs:__imp_WindowsDeleteString
0x180060855  mov     [rbx+1A8h], rbp
0x18006085c  mov     rcx, [rbx+188h]
0x180060863  test    rcx, rcx
0x180060866  jz      short loc_180060874
0x180060868  mov     [rbx+188h], rbp
0x18006086f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180060874  lea     rcx, [rbx+170h]
0x18006087b  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180060880  lea     rcx, [rbx+158h]
0x180060887  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18006088c  lea     rcx, [rbx+140h]
0x180060893  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180060898  lea     rcx, [rbx+128h]
0x18006089f  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x1800608a4  lea     rcx, [rbx+110h]
0x1800608ab  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x1800608b0  lea     rcx, [rbx+0F8h]
0x1800608b7  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUILockInfo@Controller@Logon@UI@Internal@Windows@@W4LockActivity@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::Controller::ILockInfo *,Windows::Internal::UI::Logon::Controller::LockActivity>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x1800608bc  lea     rcx, [rbx+0F0h]
0x1800608c3  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800608c8  lea     rcx, [rbx+0E0h]
0x1800608cf  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800608d4  lea     rcx, [rbx+0D8h]
0x1800608db  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800608e0  lea     rcx, [rbx+0D0h]
0x1800608e7  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800608ec  lea     rdi, [rbx+0B8h]
0x1800608f3  cmp     [rbx+0B0h], rbp
0x1800608fa  jz      short loc_180060930
0x1800608fc  mov     rsi, rbp
0x1800608ff  cmp     [rdi], rbp
0x180060902  jbe     short loc_18006091C
0x180060904  mov     rax, [rbx+0B0h]
0x18006090b  lea     rcx, [rax+rsi*8]
0x18006090f  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180060914  inc     rsi
0x180060917  cmp     rsi, [rdi]
0x18006091a  jb      short loc_180060904
0x18006091c  mov     rcx, [rbx+0B0h]; pv
0x180060923  call    cs:__imp_CoTaskMemFree
0x180060929  mov     [rbx+0B0h], rbp
0x180060930  lea     rcx, [rbx+0A8h]
0x180060937  mov     [rdi], rbp
0x18006093a  mov     [rbx+0C8h], rbp
0x180060941  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180060946  lea     rcx, [rbx+0A0h]
0x18006094d  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180060952  lea     rcx, [rbx+98h]
0x180060959  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18006095e  lea     rcx, [rbx+90h]
0x180060965  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18006096a  lea     rcx, [rbx+88h]
0x180060971  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180060976  lea     rcx, [rbx+80h]
0x18006097d  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180060982  lea     rcx, [rbx+60h]
0x180060986  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18006098b  mov     rcx, rbx
0x18006098e  mov     rbx, [rsp+58h+arg_18]
0x180060993  add     rsp, 40h
0x180060997  pop     rdi
0x180060998  pop     rsi
0x180060999  pop     rbp
0x18006099a  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIRedirectionManager@Controller@Logon@UI@Internal@Windows@@UIUserSettingManager@56789@UITelemetryDataProvider@CredProvData@6789@UIDisplayStateProvider@CredProvData@6789@UIUserSettingChangeCallback@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IRedirectionManager,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::UI::Logon::Controller::IRedirectionManager,Windows::Internal::UI::Logon::Controller::IUserSettingManager,Windows::Internal::UI::Logon::CredProvData::ITelemetryDataProvider,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider,IUserSettingChangeCallback,Microsoft::WRL::FtmBase>(void)
```
