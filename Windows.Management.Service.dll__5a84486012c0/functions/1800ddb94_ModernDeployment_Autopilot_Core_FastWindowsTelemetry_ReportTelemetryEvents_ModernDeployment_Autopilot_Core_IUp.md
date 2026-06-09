# ModernDeployment::Autopilot::Core::FastWindowsTelemetry::ReportTelemetryEvents(ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)

- ea: `0x1800ddb94`
- end: `0x1800de6b6`
- name: `?ReportTelemetryEvents@FastWindowsTelemetry@Core@Autopilot@ModernDeployment@@AEAAJPEAUIUploadTelemetryRequest@234@@Z`
- size: `2850`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::FastWindowsTelemetry *__hidden this, struct ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800da570`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x180081f1c`
- `0x1800853a0`
- `0x180089ac8`
- `0x18008a014`
- `0x18008e438`
- `0x18008f6a8`
- `0x1800d9688`
- `0x1800d9fb4`
- `0x1800daa7c`
- `0x1800dc524`
- `0x1800dccbc`
- `0x1800dd0d8`
- `0x1800dd9ec`
- `0x1800dda78`
- `0x1800ddb08`
- `0x1800ddb94`
- `0x1800de934`
- `0x1800df4d8`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dde27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dde27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de4d1`

## string_xrefs

- `0x1800ddeec`: `Windows.Data.Json.JsonObject`
- `0x1800de034`: `Windows.Data.Json.JsonArray`
- `0x1800ddbeb`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddc54`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddcb6`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddd1e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddd9c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800dde78`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddf24`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800ddfb5`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de06c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de115`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de1c9`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de27d`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de33c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de41d`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de506`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de62a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800de673`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FastWindowsTelemetry::ReportTelemetryEvents(
        ModernDeployment::Autopilot::Core::FastWindowsTelemetry *this,
        struct ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *a2)
{
  int FwtUploadUrl; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int i; // r14d
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v17; // rbx
  const unsigned __int16 *StringRawBuffer; // rdi
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging *v21; // rcx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  struct Windows::Data::Json::IJsonObject *v38; // rsi
  __int64 (__fastcall *v39)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64); // rdi
  __int64 v40; // rbx
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // ebx
  const unsigned __int16 *v45; // rdi
  unsigned __int64 v46; // rdx
  unsigned __int8 v47; // cl
  bool IsEnabled; // al
  ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging *v49; // rcx
  ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging *v50; // rcx
  int v51; // eax
  int v52[2]; // [rsp+20h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+28h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+30h] [rbp-B8h] BYREF
  __int64 *v55; // [rsp+38h] [rbp-B0h] BYREF
  struct Windows::Data::Json::IJsonObject *v56; // [rsp+40h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-98h] BYREF
  unsigned int v59; // [rsp+58h] [rbp-90h] BYREF
  __int64 v60; // [rsp+60h] [rbp-88h] BYREF
  __int64 v61; // [rsp+68h] [rbp-80h] BYREF
  __int64 v62; // [rsp+70h] [rbp-78h] BYREF
  unsigned int v63; // [rsp+78h] [rbp-70h] BYREF
  _OWORD v64[2]; // [rsp+80h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v66; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    if ( a2 )
    {
      wil::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>(
        &v55,
        a2);
      v64[0] = 0;
      v64[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v64[0]) = 0;
      FwtUploadUrl = ModernDeployment::Autopilot::Core::GetFwtUploadUrl(v64);
      v5 = FwtUploadUrl;
      if ( FwtUploadUrl >= 0 )
      {
        *(_QWORD *)v52 = 0;
        v6 = *v55;
        *(_QWORD *)v52 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(v6 + 48))(v55, v52);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v63 = 0;
          v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v52 + 56LL))(*(_QWORD *)v52, &v63);
          v10 = v9;
          if ( v9 >= 0 )
          {
            for ( i = 0; i < v63; ++i )
            {
              v54 = 0;
              v12 = **(_QWORD **)v52;
              v54 = 0;
              v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v12 + 48))(*(_QWORD *)v52, i, &v54);
              v14 = v13;
              if ( v13 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x29D,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v13,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v14;
              }
              string = 0;
              v15 = v54;
              v16 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v54 + 48LL);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
                &string,
                0);
              v16(v15, &string);
              v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v64);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(v20, v19) )
              {
                wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get();
                ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::ReportTelemetryEventStart_(
                  v21,
                  StringRawBuffer,
                  v17);
              }
              v57 = 0;
              v59 = 0;
              v22 = ModernDeployment::Autopilot::Core::CreateStructuredEventJson(&v54, &v57, &v59);
              v23 = v22;
              if ( v22 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2A8,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v22,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v23;
              }
              v56 = 0;
              v66 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.Data.Json.JsonObject",
                0x1Du,
                0x1Cu);
              v24 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v66, &v56);
              v25 = v24;
              if ( v24 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2AC,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v24,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v25;
              }
              v26 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v56, L"Version", L"1.0");
              v27 = v26;
              if ( v26 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2AD,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v26,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v27;
              }
              v58 = 0;
              v66 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &hstringHeader,
                L"Windows.Data.Json.JsonArray",
                0x1Cu,
                0x1Bu);
              v28 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v66, &v58);
              v29 = v28;
              if ( v28 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B0,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v28,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v29;
              }
              v60 = 0;
              v30 = (**v58)(v58, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v60);
              v31 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B3,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v30,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v31;
              }
              v61 = 0;
              v32 = (**v57)(v57, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v61);
              v33 = v32;
              if ( v32 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B6,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v32,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v33;
              }
              v34 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 104LL))(v60, v61);
              v35 = v34;
              if ( v34 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B7,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v34,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v35;
              }
              v62 = 0;
              v36 = (**v58)(v58, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v62);
              v37 = v36;
              if ( v36 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2BA,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v36,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v62);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v37;
              }
              v38 = v56;
              v39 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64))(*(_QWORD *)v56 + 56LL);
              v40 = v62;
              v41 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &hstringHeader,
                      &ModernDeployment::Autopilot::Core::FwtTelemetrySchema::Events);
              v42 = v39(v38, *(_QWORD *)(v41 + 24), v40);
              v43 = v42;
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2BB,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v42,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v62);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return v43;
              }
              v44 = ModernDeployment::Autopilot::Core::SendTelemetry(v64, &v56, v59);
              v45 = WindowsGetStringRawBuffer(string, 0);
              IsEnabled = ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(v47, v46);
              if ( v44 < 0 )
              {
                if ( IsEnabled )
                {
                  wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get();
                  ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::ReportTelemetryEventFailed_(
                    v49,
                    v45,
                    v44);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2CB,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)v44,
                  v52[0]);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v62);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
                Windows::Internal::String::~String((Windows::Internal::String *)&string);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
                std::wstring::_Tidy_deallocate(v64);
                wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
                return (unsigned int)v44;
              }
              if ( IsEnabled )
              {
                wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get();
                ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::ReportTelemetryEventSucceeded_(
                  v50,
                  v45,
                  v44);
              }
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v62);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v61);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v60);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v58);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v56);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v57);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v54);
            }
            v51 = ModernDeployment::Autopilot::Core::DrainRetryQueue((__int64)v64);
            if ( v51 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2CF,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                (const char *)(unsigned int)v51,
                v52[0]);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
            std::wstring::_Tidy_deallocate(v64);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x298,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
              (const char *)(unsigned int)v9,
              v52[0]);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
            std::wstring::_Tidy_deallocate(v64);
            wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
            return v10;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x296,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
            (const char *)(unsigned int)v7,
            v52[0]);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(v52);
          std::wstring::_Tidy_deallocate(v64);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
          return v8;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
          (const char *)(unsigned int)FwtUploadUrl,
          v52[0]);
        std::wstring::_Tidy_deallocate(v64);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v55);
        return v5;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
        (const char *)0x80070057LL,
        v52[0]);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
      (const char *)0x80004001LL,
      v52[0]);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800ddb94  mov     [rsp+arg_0], rbx
0x1800ddb99  mov     [rsp+arg_10], rsi
0x1800ddb9e  push    rdi
0x1800ddb9f  push    r14
0x1800ddba1  push    r15
0x1800ddba3  sub     rsp, 0D0h
0x1800ddbaa  mov     rax, cs:__security_cookie
0x1800ddbb1  xor     rax, rsp
0x1800ddbb4  mov     [rsp+0E8h+var_28], rax
0x1800ddbbc  mov     rbx, rdx
0x1800ddbbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800ddbc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800ddbcb  xor     r15d, r15d
0x1800ddbce  test    al, al
0x1800ddbd0  jz      loc_1800DE663
0x1800ddbd6  test    rbx, rbx
0x1800ddbd9  jnz     short loc_1800DDC03
0x1800ddbdb  mov     rcx, [rsp+0E8h]; this
0x1800ddbe3  mov     ebx, 80070057h
0x1800ddbe8  mov     r9d, ebx; char *
0x1800ddbeb  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddbf2  mov     edx, 28Eh; void *
0x1800ddbf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddbfc  mov     eax, ebx
0x1800ddbfe  jmp     loc_1800DE68C
0x1800ddc03  mov     rdx, rbx
0x1800ddc06  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddc0b  call    ??0?$com_ptr_t@UIUploadTelemetryRequest@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUploadTelemetryRequest@Core@Autopilot@ModernDeployment@@@Z; wil::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>(ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)
0x1800ddc10  nop
0x1800ddc11  xorps   xmm0, xmm0
0x1800ddc14  movups  [rsp+0E8h+var_68], xmm0
0x1800ddc1c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ddc24  movdqu  [rsp+0E8h+var_58], xmm1
0x1800ddc2d  mov     word ptr [rsp+0E8h+var_68], r15w
0x1800ddc36  lea     rcx, [rsp+0E8h+var_68]
0x1800ddc3e  call    ModernDeployment__Autopilot__Core__GetFwtUploadUrl
0x1800ddc43  mov     ebx, eax
0x1800ddc45  test    eax, eax
0x1800ddc47  jns     short loc_1800DDC85
0x1800ddc49  mov     rcx, [rsp+0E8h]; this
0x1800ddc51  mov     r9d, eax; char *
0x1800ddc54  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddc5b  mov     edx, 293h; void *
0x1800ddc60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddc65  nop
0x1800ddc66  lea     rcx, [rsp+0E8h+var_68]
0x1800ddc6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddc73  nop
0x1800ddc74  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddc79  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddc7e  mov     eax, ebx
0x1800ddc80  jmp     loc_1800DE68C
0x1800ddc85  mov     qword ptr [rsp+0E8h+var_C8], r15
0x1800ddc8a  mov     rcx, [rsp+0E8h+var_B0]
0x1800ddc8f  mov     rax, [rcx]
0x1800ddc92  mov     qword ptr [rsp+0E8h+var_C8], r15; int
0x1800ddc97  lea     rdx, [rsp+0E8h+var_C8]
0x1800ddc9c  mov     rax, [rax+30h]
0x1800ddca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddca5  mov     ebx, eax
0x1800ddca7  test    eax, eax
0x1800ddca9  jns     short loc_1800DDCF2
0x1800ddcab  mov     rcx, [rsp+0E8h]; this
0x1800ddcb3  mov     r9d, eax; char *
0x1800ddcb6  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddcbd  mov     edx, 296h; void *
0x1800ddcc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddcc7  nop
0x1800ddcc8  lea     rcx, [rsp+0E8h+var_C8]
0x1800ddccd  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddcd2  nop
0x1800ddcd3  lea     rcx, [rsp+0E8h+var_68]
0x1800ddcdb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddce0  nop
0x1800ddce1  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddce6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddceb  mov     eax, ebx
0x1800ddced  jmp     loc_1800DE68C
0x1800ddcf2  mov     [rsp+0E8h+var_70], r15d
0x1800ddcf7  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x1800ddcfc  mov     rax, [rcx]
0x1800ddcff  lea     rdx, [rsp+0E8h+var_70]
0x1800ddd04  mov     rax, [rax+38h]
0x1800ddd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd0d  mov     ebx, eax
0x1800ddd0f  test    eax, eax
0x1800ddd11  jns     short loc_1800DDD5A
0x1800ddd13  mov     rcx, [rsp+0E8h]; this
0x1800ddd1b  mov     r9d, eax; char *
0x1800ddd1e  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddd25  mov     edx, 298h; void *
0x1800ddd2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddd2f  nop
0x1800ddd30  lea     rcx, [rsp+0E8h+var_C8]
0x1800ddd35  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddd3a  nop
0x1800ddd3b  lea     rcx, [rsp+0E8h+var_68]
0x1800ddd43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddd48  nop
0x1800ddd49  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddd4e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddd53  mov     eax, ebx
0x1800ddd55  jmp     loc_1800DE68C
0x1800ddd5a  mov     r14d, r15d
0x1800ddd5d  cmp     r14d, [rsp+0E8h+var_70]
0x1800ddd62  jnb     loc_1800DE60E
0x1800ddd68  mov     [rsp+0E8h+var_B8], r15
0x1800ddd6d  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x1800ddd72  mov     rax, [rcx]
0x1800ddd75  mov     [rsp+0E8h+var_B8], r15
0x1800ddd7a  lea     r8, [rsp+0E8h+var_B8]
0x1800ddd7f  mov     edx, r14d
0x1800ddd82  mov     rax, [rax+30h]
0x1800ddd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd8b  mov     ebx, eax
0x1800ddd8d  test    eax, eax
0x1800ddd8f  jns     short loc_1800DDDE3
0x1800ddd91  mov     rcx, [rsp+0E8h]; this
0x1800ddd99  mov     r9d, eax; char *
0x1800ddd9c  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddda3  mov     edx, 29Dh; void *
0x1800ddda8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dddad  nop
0x1800dddae  lea     rcx, [rsp+0E8h+var_B8]
0x1800dddb3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dddb8  nop
0x1800dddb9  lea     rcx, [rsp+0E8h+var_C8]
0x1800dddbe  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dddc3  nop
0x1800dddc4  lea     rcx, [rsp+0E8h+var_68]
0x1800dddcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dddd1  nop
0x1800dddd2  lea     rcx, [rsp+0E8h+var_B0]
0x1800dddd7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddddc  mov     eax, ebx
0x1800dddde  jmp     loc_1800DE68C
0x1800ddde3  mov     [rsp+0E8h+string], r15
0x1800ddde8  mov     rdi, [rsp+0E8h+var_B8]
0x1800ddded  mov     rax, [rdi]
0x1800dddf0  mov     rbx, [rax+30h]
0x1800dddf4  xor     edx, edx
0x1800dddf6  lea     rcx, [rsp+0E8h+string]
0x1800dddfb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dde00  lea     rdx, [rsp+0E8h+string]
0x1800dde05  mov     rcx, rdi
0x1800dde08  mov     rax, rbx
0x1800dde0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde10  lea     rcx, [rsp+0E8h+var_68]
0x1800dde18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dde1d  mov     rbx, rax
0x1800dde20  xor     edx, edx; length
0x1800dde22  mov     rcx, [rsp+0E8h+string]; string
0x1800dde27  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dde2d  mov     rdi, rax
0x1800dde30  call    ?IsEnabled@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@SA_NE_K@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(uchar,unsigned __int64)
0x1800dde35  test    al, al
0x1800dde37  jz      short loc_1800DDE49
0x1800dde39  call    ?get@?$static_lazy@VFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@@details@wil@@QEAAPEAVFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@P6AXXZ@Z; wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get(void (*)(void))
0x1800dde3e  mov     r8, rbx; unsigned __int16 *
0x1800dde41  mov     rdx, rdi; unsigned __int16 *
0x1800dde44  call    ?ReportTelemetryEventStart_@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@QEAAXPEBG0@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::ReportTelemetryEventStart_(ushort const *,ushort const *)
0x1800dde49  mov     [rsp+0E8h+var_A0], r15
0x1800dde4e  mov     [rsp+0E8h+var_90], r15d
0x1800dde53  lea     r8, [rsp+0E8h+var_90]
0x1800dde58  lea     rdx, [rsp+0E8h+var_A0]
0x1800dde5d  lea     rcx, [rsp+0E8h+var_B8]
0x1800dde62  call    ModernDeployment__Autopilot__Core__CreateStructuredEventJson
0x1800dde67  mov     ebx, eax
0x1800dde69  test    eax, eax
0x1800dde6b  jns     short loc_1800DDED5
0x1800dde6d  mov     rcx, [rsp+0E8h]; this
0x1800dde75  mov     r9d, eax; char *
0x1800dde78  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dde7f  mov     edx, 2A8h; void *
0x1800dde84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dde89  nop
0x1800dde8a  lea     rcx, [rsp+0E8h+var_A0]
0x1800dde8f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800dde94  nop
0x1800dde95  lea     rcx, [rsp+0E8h+string]; this
0x1800dde9a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800dde9f  nop
0x1800ddea0  lea     rcx, [rsp+0E8h+var_B8]
0x1800ddea5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddeaa  nop
0x1800ddeab  lea     rcx, [rsp+0E8h+var_C8]
0x1800ddeb0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddeb5  nop
0x1800ddeb6  lea     rcx, [rsp+0E8h+var_68]
0x1800ddebe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddec3  nop
0x1800ddec4  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddec9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddece  mov     eax, ebx
0x1800dded0  jmp     loc_1800DE68C
0x1800dded5  mov     [rsp+0E8h+var_A8], r15
0x1800ddeda  mov     [rsp+0E8h+var_30], r15
0x1800ddee2  mov     r9d, 1Ch; unsigned int
0x1800ddee8  lea     r8d, [r9+1]; unsigned int
0x1800ddeec  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800ddef3  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800ddefb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ddf00  nop
0x1800ddf01  lea     rdx, [rsp+0E8h+var_A8]
0x1800ddf06  mov     rcx, [rsp+0E8h+var_30]
0x1800ddf0e  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800ddf13  mov     ebx, eax
0x1800ddf15  test    eax, eax
0x1800ddf17  jns     short loc_1800DDF8C
0x1800ddf19  mov     rcx, [rsp+0E8h]; this
0x1800ddf21  mov     r9d, eax; char *
0x1800ddf24  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddf2b  mov     edx, 2ACh; void *
0x1800ddf30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddf35  nop
0x1800ddf36  lea     rcx, [rsp+0E8h+var_A8]
0x1800ddf3b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddf40  nop
0x1800ddf41  lea     rcx, [rsp+0E8h+var_A0]
0x1800ddf46  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddf4b  nop
0x1800ddf4c  lea     rcx, [rsp+0E8h+string]; this
0x1800ddf51  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ddf56  nop
0x1800ddf57  lea     rcx, [rsp+0E8h+var_B8]
0x1800ddf5c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddf61  nop
0x1800ddf62  lea     rcx, [rsp+0E8h+var_C8]
0x1800ddf67  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddf6c  nop
0x1800ddf6d  lea     rcx, [rsp+0E8h+var_68]
0x1800ddf75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddf7a  nop
0x1800ddf7b  lea     rcx, [rsp+0E8h+var_B0]
0x1800ddf80  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddf85  mov     eax, ebx
0x1800ddf87  jmp     loc_1800DE68C
0x1800ddf8c  lea     r8, a10_2; "1.0"
0x1800ddf93  lea     rdx, aVersion; "Version"
0x1800ddf9a  mov     rcx, [rsp+0E8h+var_A8]; struct Windows::Data::Json::IJsonObject *
0x1800ddf9f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800ddfa4  mov     ebx, eax
0x1800ddfa6  test    eax, eax
0x1800ddfa8  jns     short loc_1800DE01D
0x1800ddfaa  mov     rcx, [rsp+0E8h]; this
0x1800ddfb2  mov     r9d, eax; char *
0x1800ddfb5  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ddfbc  mov     edx, 2ADh; void *
0x1800ddfc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddfc6  nop
0x1800ddfc7  lea     rcx, [rsp+0E8h+var_A8]
0x1800ddfcc  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddfd1  nop
0x1800ddfd2  lea     rcx, [rsp+0E8h+var_A0]
0x1800ddfd7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddfdc  nop
0x1800ddfdd  lea     rcx, [rsp+0E8h+string]; this
0x1800ddfe2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ddfe7  nop
0x1800ddfe8  lea     rcx, [rsp+0E8h+var_B8]
0x1800ddfed  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddff2  nop
0x1800ddff3  lea     rcx, [rsp+0E8h+var_C8]
0x1800ddff8  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800ddffd  nop
0x1800ddffe  lea     rcx, [rsp+0E8h+var_68]
0x1800de006  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800de00b  nop
0x1800de00c  lea     rcx, [rsp+0E8h+var_B0]
0x1800de011  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800de016  mov     eax, ebx
0x1800de018  jmp     loc_1800DE68C
0x1800de01d  mov     [rsp+0E8h+var_98], r15
0x1800de022  mov     [rsp+0E8h+var_30], r15
0x1800de02a  mov     r9d, 1Bh; unsigned int
0x1800de030  lea     r8d, [r9+1]; unsigned int
0x1800de034  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800de03b  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800de043  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800de048  nop
0x1800de049  lea     rdx, [rsp+0E8h+var_98]
0x1800de04e  mov     rcx, [rsp+0E8h+var_30]
0x1800de056  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800de05b  mov     ebx, eax
0x1800de05d  test    eax, eax
0x1800de05f  jns     short loc_1800DE0DF
0x1800de061  mov     rcx, [rsp+0E8h]; this
0x1800de069  mov     r9d, eax; char *
0x1800de06c  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800de073  mov     edx, 2B0h; void *
0x1800de078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800de07d  nop
0x1800de07e  lea     rcx, [rsp+0E8h+var_98]
0x1800de083  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800de088  nop
0x1800de089  lea     rcx, [rsp+0E8h+var_A8]
0x1800de08e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800de093  nop
0x1800de094  lea     rcx, [rsp+0E8h+var_A0]
0x1800de099  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
  ... truncated ...
```
