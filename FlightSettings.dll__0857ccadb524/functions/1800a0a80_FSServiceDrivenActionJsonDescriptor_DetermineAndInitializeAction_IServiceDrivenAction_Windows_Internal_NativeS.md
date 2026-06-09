# FSServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(IServiceDrivenAction * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,Microsoft::WRL::ComPtr<FSActionContext>)

- ea: `0x1800a0a80`
- end: `0x1800a0fec`
- name: `?DetermineAndInitializeAction@FSServiceDrivenActionJsonDescriptor@@MEAAJPEAPEAUIServiceDrivenAction@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$ComPtr@VFSActionContext@@@78@@Z`
- size: `1388`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const char **, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800acd60`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x180013da0`
- `0x1800175b4`
- `0x1800177bc`
- `0x18001d244`
- `0x18003290c`
- `0x180086644`
- `0x180086944`
- `0x18009b8c8`
- `0x18009e004`
- `0x18009e0d8`
- `0x18009e24c`
- `0x18009e36c`
- `0x18009e488`
- `0x18009e58c`
- `0x18009e660`
- `0x18009e76c`
- `0x18009e8e0`
- `0x18009e9b4`
- `0x18009eaa0`
- `0x18009eb74`
- `0x18009eca8`
- `0x18009ede0`
- `0x18009ef20`
- `0x18009f08c`
- `0x18009f160`
- `0x18009f234`
- `0x18009f320`
- `0x1800a0a80`
- `0x1800a29b4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0f2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0f2d`

## string_xrefs

- `0x1800a0aae`: `RegWrite`
- `0x1800a0b2e`: `RebootToCompleteInstall`
- `0x1800a0c63`: `FlightIdClientRemove`
- `0x1800a0d7b`: `StartWindowsUpdateScan`
- `0x1800a0df3`: `Privileged`
- `0x1800a0da2`: `ServiceControl`
- `0x1800a0ea3`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a0eda`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a0f14`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`
- `0x1800a0fae`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenactionjsondescriptor.cpp`

## pseudocode

```c
__int64 __fastcall FSServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(
        __int64 a1,
        _QWORD *a2,
        const char **a3,
        __int64 a4,
        __int64 *a5)
{
  int v8; // eax
  int v9; // ebx
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // cl
  __int64 v12; // rcx
  FlightSettingsAPITelemetryClass *v13; // rax
  const unsigned __int16 *v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int8 v19; // cl
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int8 v22; // cl
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int8 v25; // cl
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  PCWSTR StringRawBuffer; // rax
  int v31; // [rsp+20h] [rbp-30h]
  __int64 v32; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  __int64 v35; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"RegWrite",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSRegWriteServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"SetBcd",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSSetBcdServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"Reboot",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSRebootAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"RebootToCompleteInstall",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSRebootToCompleteInstallAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"ToastNotification",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSToastNotificationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"FileOperation",
                       -1) == 2 )
  {
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSFileOperationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    LODWORD(v32) = v9;
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v11, v10) )
      goto LABEL_47;
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v12,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v14 = L"FileOperation Action Initialize";
LABEL_28:
    FlightSettingsAPITelemetryClass::FSActionTrace_(v13, v14, v9);
    goto LABEL_47;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"DeviceEncryption",
                       -1) == 2 )
  {
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSDeviceEncriptionAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    LODWORD(v32) = v9;
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v16, v15) )
      goto LABEL_47;
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v17,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v14 = L"DeviceEncryption Action Initialize";
    goto LABEL_28;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"FlightIdClientAdd",
                       -1) == 2 )
  {
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSFlightClientAddAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    LODWORD(v32) = v9;
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v19, v18) )
      goto LABEL_47;
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v20,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v14 = L"FlightClientAdd Action Initialize";
    goto LABEL_28;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"FlightIdClientRemove",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSFlightClientRemoveAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"PublishWNFFlightIds",
                       -1) == 2 )
  {
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSPublishWNFFlightIdsAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    LODWORD(v32) = v9;
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v22, v21) )
      goto LABEL_47;
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v23,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v14 = L"PublishWNFFlightIDs Action Initialize";
    goto LABEL_28;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"ScheduleAsyncValidation",
                       -1) == 2 )
  {
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSScheduleAsyncValidationAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    LODWORD(v32) = v9;
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v25, v24) )
      goto LABEL_47;
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v26,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v14 = L"ScheduleAsyncValidation Action Initialize";
    goto LABEL_28;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"InjectAppData",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSInjectAppDataAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"LaunchExe",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSLaunchExeAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"StartWindowsUpdateScan",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSStartWindowsUpdateScanAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"ServiceControl",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSServiceControlAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"SendEvent",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSSendEventAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"Privileged",
                       -1) == 2 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSPrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(
           a2,
           a4,
           a5);
    goto LABEL_45;
  }
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"Allowlist",
                       -1) != 2
    && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       a3,
                       L"LaunchExeV2",
                       -1) != 2 )
  {
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         a3,
                         L"Medic",
                         -1) != 2 )
    {
      v9 = -2146698739;
      LODWORD(v32) = -2146698739;
LABEL_47:
      if ( v9 >= 0 )
        goto LABEL_57;
      goto LABEL_50;
    }
    v8 = Microsoft::WRL::Details::MakeAndInitialize<FSMedicServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(
           a2,
           a4);
LABEL_45:
    v9 = v8;
    LODWORD(v32) = v8;
    goto LABEL_47;
  }
  v9 = -2146698739;
  LODWORD(v32) = -2146698739;
LABEL_50:
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x11F,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
    (const char *)(unsigned int)v9,
    (int)"Failed initialize action: %ws",
    *a3,
    v32);
  v34 = 0;
  v27 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(a4, &v34);
  if ( v27 >= 0 )
  {
    string = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 56LL))(v34, &string);
    if ( v28 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v35 = -2147483646;
      FSRegUtils::SetFlightingRegString(&v35, 1, L"LastFailedAction", StringRawBuffer);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
        (const char *)(unsigned int)v28,
        v31);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v27,
      v31);
  }
  v35 = -2147483646;
  FSRegUtils::SetFlightingRegDWORD(&v35, 1, L"LastFailedActionHr", (unsigned int)v9);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
LABEL_57:
  if ( (unsigned int)(v9 + 2146698740) <= 1 || v9 == -2146698713 )
    v9 = Microsoft::WRL::Details::MakeAndInitialize<FSUnsupportedClientAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,long &>(
           a2,
           a4,
           &v32);
  if ( v9 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicedrivenactionjsondescriptor.cpp",
      (const char *)(unsigned int)v9,
      v31);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a4);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a0a80  mov     [rsp-28h+arg_0], rbx
0x1800a0a85  mov     [rsp-28h+arg_8], rsi
0x1800a0a8a  mov     [rsp-28h+arg_18], r9
0x1800a0a8f  push    rbp
0x1800a0a90  push    rdi
0x1800a0a91  push    r12
0x1800a0a93  push    r14
0x1800a0a95  push    r15
0x1800a0a97  mov     rbp, rsp
0x1800a0a9a  sub     rsp, 50h
0x1800a0a9e  mov     rdi, r9
0x1800a0aa1  mov     r14, r8
0x1800a0aa4  mov     rsi, rdx
0x1800a0aa7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a0aab  mov     r8, rbx
0x1800a0aae  lea     rdx, aRegwrite; "RegWrite"
0x1800a0ab5  mov     rcx, r14
0x1800a0ab8  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0abd  mov     r15, [rbp+arg_20]
0x1800a0ac1  lea     r12d, [rbx+3]
0x1800a0ac5  cmp     eax, r12d
0x1800a0ac8  jnz     short loc_1800A0ADD
0x1800a0aca  mov     r8, r15
0x1800a0acd  mov     rdx, rdi
0x1800a0ad0  mov     rcx, rsi
0x1800a0ad3  call    ??$MakeAndInitialize@VFSRegWriteServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSRegWriteServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0ad8  jmp     loc_1800A0E67
0x1800a0add  mov     r8, rbx
0x1800a0ae0  lea     rdx, aSetbcd; "SetBcd"
0x1800a0ae7  mov     rcx, r14
0x1800a0aea  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0aef  cmp     eax, r12d
0x1800a0af2  jnz     short loc_1800A0B04
0x1800a0af4  mov     rdx, rdi
0x1800a0af7  mov     rcx, rsi
0x1800a0afa  call    ??$MakeAndInitialize@VFSSetBcdServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSSetBcdServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0aff  jmp     loc_1800A0E67
0x1800a0b04  mov     r8, rbx
0x1800a0b07  lea     rdx, aReboot; "Reboot"
0x1800a0b0e  mov     rcx, r14
0x1800a0b11  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0b16  cmp     eax, r12d
0x1800a0b19  jnz     short loc_1800A0B2B
0x1800a0b1b  mov     rdx, rdi
0x1800a0b1e  mov     rcx, rsi
0x1800a0b21  call    ??$MakeAndInitialize@VFSRebootAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSRebootAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0b26  jmp     loc_1800A0E67
0x1800a0b2b  mov     r8, rbx
0x1800a0b2e  lea     rdx, aReboottocomple_0; "RebootToCompleteInstall"
0x1800a0b35  mov     rcx, r14
0x1800a0b38  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0b3d  cmp     eax, r12d
0x1800a0b40  jnz     short loc_1800A0B52
0x1800a0b42  mov     rdx, rdi
0x1800a0b45  mov     rcx, rsi
0x1800a0b48  call    ??$MakeAndInitialize@VFSRebootToCompleteInstallAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSRebootToCompleteInstallAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0b4d  jmp     loc_1800A0E67
0x1800a0b52  mov     r8, rbx
0x1800a0b55  lea     rdx, aToastnotificat; "ToastNotification"
0x1800a0b5c  mov     rcx, r14
0x1800a0b5f  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0b64  cmp     eax, r12d
0x1800a0b67  jnz     short loc_1800A0B79
0x1800a0b69  mov     rdx, rdi
0x1800a0b6c  mov     rcx, rsi
0x1800a0b6f  call    ??$MakeAndInitialize@VFSToastNotificationServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSToastNotificationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0b74  jmp     loc_1800A0E67
0x1800a0b79  mov     r8, rbx
0x1800a0b7c  lea     rdx, aFileoperation; "FileOperation"
0x1800a0b83  mov     rcx, r14
0x1800a0b86  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0b8b  cmp     eax, r12d
0x1800a0b8e  jnz     short loc_1800A0BC8
0x1800a0b90  mov     r8, r15
0x1800a0b93  mov     rdx, rdi
0x1800a0b96  mov     rcx, rsi
0x1800a0b99  call    ??$MakeAndInitialize@VFSFileOperationServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSFileOperationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0b9e  mov     ebx, eax
0x1800a0ba0  mov     dword ptr [rbp+var_20], eax
0x1800a0ba3  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a0ba8  test    al, al
0x1800a0baa  jz      loc_1800A0E76
0x1800a0bb0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a0bb7  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a0bbc  lea     rdx, aFileoperationA; "FileOperation Action Initialize"
0x1800a0bc3  jmp     loc_1800A0D1A
0x1800a0bc8  mov     r8, rbx
0x1800a0bcb  lea     rdx, aDeviceencrypti_1; "DeviceEncryption"
0x1800a0bd2  mov     rcx, r14
0x1800a0bd5  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0bda  cmp     eax, r12d
0x1800a0bdd  jnz     short loc_1800A0C14
0x1800a0bdf  mov     rdx, rdi
0x1800a0be2  mov     rcx, rsi
0x1800a0be5  call    ??$MakeAndInitialize@VFSDeviceEncriptionAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSDeviceEncriptionAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0bea  mov     ebx, eax
0x1800a0bec  mov     dword ptr [rbp+var_20], eax
0x1800a0bef  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a0bf4  test    al, al
0x1800a0bf6  jz      loc_1800A0E76
0x1800a0bfc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a0c03  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a0c08  lea     rdx, aDeviceencrypti_0; "DeviceEncryption Action Initialize"
0x1800a0c0f  jmp     loc_1800A0D1A
0x1800a0c14  mov     r8, rbx
0x1800a0c17  lea     rdx, aFlightidclient_0; "FlightIdClientAdd"
0x1800a0c1e  mov     rcx, r14
0x1800a0c21  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0c26  cmp     eax, r12d
0x1800a0c29  jnz     short loc_1800A0C60
0x1800a0c2b  mov     rdx, rdi
0x1800a0c2e  mov     rcx, rsi
0x1800a0c31  call    ??$MakeAndInitialize@VFSFlightClientAddAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSFlightClientAddAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0c36  mov     ebx, eax
0x1800a0c38  mov     dword ptr [rbp+var_20], eax
0x1800a0c3b  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a0c40  test    al, al
0x1800a0c42  jz      loc_1800A0E76
0x1800a0c48  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a0c4f  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a0c54  lea     rdx, aFlightclientad; "FlightClientAdd Action Initialize"
0x1800a0c5b  jmp     loc_1800A0D1A
0x1800a0c60  mov     r8, rbx
0x1800a0c63  lea     rdx, aFlightidclient; "FlightIdClientRemove"
0x1800a0c6a  mov     rcx, r14
0x1800a0c6d  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0c72  cmp     eax, r12d
0x1800a0c75  jnz     short loc_1800A0C87
0x1800a0c77  mov     rdx, rdi
0x1800a0c7a  mov     rcx, rsi
0x1800a0c7d  call    ??$MakeAndInitialize@VFSFlightClientRemoveAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSFlightClientRemoveAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0c82  jmp     loc_1800A0E67
0x1800a0c87  mov     r8, rbx
0x1800a0c8a  lea     rdx, aPublishwnfflig_0; "PublishWNFFlightIds"
0x1800a0c91  mov     rcx, r14
0x1800a0c94  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0c99  cmp     eax, r12d
0x1800a0c9c  jnz     short loc_1800A0CD0
0x1800a0c9e  mov     rdx, rdi
0x1800a0ca1  mov     rcx, rsi
0x1800a0ca4  call    ??$MakeAndInitialize@VFSPublishWNFFlightIdsAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSPublishWNFFlightIdsAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0ca9  mov     ebx, eax
0x1800a0cab  mov     dword ptr [rbp+var_20], eax
0x1800a0cae  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a0cb3  test    al, al
0x1800a0cb5  jz      loc_1800A0E76
0x1800a0cbb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a0cc2  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a0cc7  lea     rdx, aPublishwnfflig; "PublishWNFFlightIDs Action Initialize"
0x1800a0cce  jmp     short loc_1800A0D1A
0x1800a0cd0  mov     r8, rbx
0x1800a0cd3  lea     rdx, aScheduleasyncv; "ScheduleAsyncValidation"
0x1800a0cda  mov     rcx, r14
0x1800a0cdd  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0ce2  cmp     eax, r12d
0x1800a0ce5  jnz     short loc_1800A0D2A
0x1800a0ce7  mov     r8, r15
0x1800a0cea  mov     rdx, rdi
0x1800a0ced  mov     rcx, rsi
0x1800a0cf0  call    ??$MakeAndInitialize@VFSScheduleAsyncValidationAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSScheduleAsyncValidationAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0cf5  mov     ebx, eax
0x1800a0cf7  mov     dword ptr [rbp+var_20], eax
0x1800a0cfa  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a0cff  test    al, al
0x1800a0d01  jz      loc_1800A0E76
0x1800a0d07  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a0d0e  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a0d13  lea     rdx, aScheduleasyncv_0; "ScheduleAsyncValidation Action Initiali"...
0x1800a0d1a  mov     r8d, ebx; int
0x1800a0d1d  mov     rcx, rax; this
0x1800a0d20  call    ?FSActionTrace_@FlightSettingsAPITelemetryClass@@QEAAXPEBGJ@Z; FlightSettingsAPITelemetryClass::FSActionTrace_(ushort const *,long)
0x1800a0d25  jmp     loc_1800A0E76
0x1800a0d2a  mov     r8, rbx
0x1800a0d2d  lea     rdx, aInjectappdata; "InjectAppData"
0x1800a0d34  mov     rcx, r14
0x1800a0d37  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0d3c  cmp     eax, r12d
0x1800a0d3f  jnz     short loc_1800A0D51
0x1800a0d41  mov     rdx, rdi
0x1800a0d44  mov     rcx, rsi
0x1800a0d47  call    ??$MakeAndInitialize@VFSInjectAppDataAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSInjectAppDataAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0d4c  jmp     loc_1800A0E67
0x1800a0d51  mov     r8, rbx
0x1800a0d54  lea     rdx, aLaunchexe; "LaunchExe"
0x1800a0d5b  mov     rcx, r14
0x1800a0d5e  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0d63  cmp     eax, r12d
0x1800a0d66  jnz     short loc_1800A0D78
0x1800a0d68  mov     rdx, rdi
0x1800a0d6b  mov     rcx, rsi
0x1800a0d6e  call    ??$MakeAndInitialize@VFSLaunchExeAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSLaunchExeAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0d73  jmp     loc_1800A0E67
0x1800a0d78  mov     r8, rbx
0x1800a0d7b  lea     rdx, aStartwindowsup; "StartWindowsUpdateScan"
0x1800a0d82  mov     rcx, r14
0x1800a0d85  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0d8a  cmp     eax, r12d
0x1800a0d8d  jnz     short loc_1800A0D9F
0x1800a0d8f  mov     rdx, rdi
0x1800a0d92  mov     rcx, rsi
0x1800a0d95  call    ??$MakeAndInitialize@VFSStartWindowsUpdateScanAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSStartWindowsUpdateScanAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0d9a  jmp     loc_1800A0E67
0x1800a0d9f  mov     r8, rbx
0x1800a0da2  lea     rdx, aServicecontrol; "ServiceControl"
0x1800a0da9  mov     rcx, r14
0x1800a0dac  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0db1  cmp     eax, r12d
0x1800a0db4  jnz     short loc_1800A0DC9
0x1800a0db6  mov     r8, r15
0x1800a0db9  mov     rdx, rdi
0x1800a0dbc  mov     rcx, rsi
0x1800a0dbf  call    ??$MakeAndInitialize@VFSServiceControlAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSServiceControlAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0dc4  jmp     loc_1800A0E67
0x1800a0dc9  mov     r8, rbx
0x1800a0dcc  lea     rdx, aSendevent; "SendEvent"
0x1800a0dd3  mov     rcx, r14
0x1800a0dd6  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0ddb  cmp     eax, r12d
0x1800a0dde  jnz     short loc_1800A0DF0
0x1800a0de0  mov     r8, r15
0x1800a0de3  mov     rdx, rdi
0x1800a0de6  mov     rcx, rsi
0x1800a0de9  call    ??$MakeAndInitialize@VFSSendEventAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSSendEventAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0dee  jmp     short loc_1800A0E67
0x1800a0df0  mov     r8, rbx
0x1800a0df3  lea     rdx, aPrivileged; "Privileged"
0x1800a0dfa  mov     rcx, r14
0x1800a0dfd  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0e02  cmp     eax, r12d
0x1800a0e05  jnz     short loc_1800A0E17
0x1800a0e07  mov     r8, r15
0x1800a0e0a  mov     rdx, rdi
0x1800a0e0d  mov     rcx, rsi
0x1800a0e10  call    ??$MakeAndInitialize@VFSPrivilegedAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VFSActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VFSActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSPrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<FSActionContext> &)
0x1800a0e15  jmp     short loc_1800A0E67
0x1800a0e17  mov     r8, rbx
0x1800a0e1a  lea     rdx, aAllowlist; "Allowlist"
0x1800a0e21  mov     rcx, r14
0x1800a0e24  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0e29  cmp     eax, r12d
0x1800a0e2c  jz      short loc_1800A0E80
0x1800a0e2e  mov     r8, rbx
0x1800a0e31  lea     rdx, aLaunchexev2; "LaunchExeV2"
0x1800a0e38  mov     rcx, r14
0x1800a0e3b  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0e40  cmp     eax, r12d
0x1800a0e43  jz      short loc_1800A0E80
0x1800a0e45  mov     r8, rbx
0x1800a0e48  lea     rdx, aMedic; "Medic"
0x1800a0e4f  mov     rcx, r14
0x1800a0e52  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a0e57  cmp     eax, r12d
0x1800a0e5a  jnz     short loc_1800A0E6E
0x1800a0e5c  mov     rdx, rdi
0x1800a0e5f  mov     rcx, rsi
0x1800a0e62  call    ??$MakeAndInitialize@VFSMedicServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FSMedicServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800a0e67  mov     ebx, eax
0x1800a0e69  mov     dword ptr [rbp+var_20], eax
0x1800a0e6c  jmp     short loc_1800A0E76
0x1800a0e6e  mov     ebx, 800BFA0Dh
0x1800a0e73  mov     dword ptr [rbp+var_20], ebx
0x1800a0e76  test    ebx, ebx
0x1800a0e78  jns     loc_1800A0F7F
0x1800a0e7e  jmp     short loc_1800A0E88
0x1800a0e80  mov     ebx, 800BFA0Dh
0x1800a0e85  mov     dword ptr [rbp+var_20], ebx
0x1800a0e88  mov     rcx, [rbp+28h]; this
0x1800a0e8c  mov     rax, [r14]
0x1800a0e8f  mov     [rsp+50h+var_28], rax; char *
0x1800a0e94  lea     rax, aFailedInitiali; "Failed initialize action: %ws"
0x1800a0e9b  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800a0ea0  mov     r9d, ebx; char *
0x1800a0ea3  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a0eaa  mov     edx, 11Fh; void *
0x1800a0eaf  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800a0eb4  mov     [rbp+var_10], 0
0x1800a0ebc  lea     rdx, [rbp+var_10]
0x1800a0ec0  mov     rcx, rdi
0x1800a0ec3  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800a0ec8  mov     rcx, [rbp+28h]; this
0x1800a0ecc  mov     r14, 0FFFFFFFF80000002h
0x1800a0ed3  test    eax, eax
0x1800a0ed5  jns     short loc_1800A0EED
0x1800a0ed7  mov     r9d, eax; char *
0x1800a0eda  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a0ee1  mov     edx, 123h; void *
0x1800a0ee6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a0eeb  jmp     short loc_1800A0F59
0x1800a0eed  mov     [rbp+string], 0
0x1800a0ef5  mov     rcx, [rbp+var_10]
0x1800a0ef9  mov     rax, [rcx]
0x1800a0efc  lea     rdx, [rbp+string]
0x1800a0f00  mov     rax, [rax+38h]
0x1800a0f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0f09  mov     rcx, [rbp+28h]; this
0x1800a0f0d  test    eax, eax
0x1800a0f0f  jns     short loc_1800A0F27
0x1800a0f11  mov     r9d, eax; char *
0x1800a0f14  lea     r8, aOnecoreBaseFli_66; "onecore\\base\\flighting\\flightsetting"...
0x1800a0f1b  mov     edx, 126h; void *
  ... truncated ...
```
