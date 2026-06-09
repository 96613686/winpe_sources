# ModernDeployment::Autopilot::Core::FastWindowsTelemetry::ReportTelemetryEvents(ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)

- ea: `0x1800e038c`
- end: `0x1800e0eba`
- name: `?ReportTelemetryEvents@FastWindowsTelemetry@Core@Autopilot@ModernDeployment@@AEAAJPEAUIUploadTelemetryRequest@234@@Z`
- size: `2862`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::FastWindowsTelemetry *__hidden this, struct ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800dcd28`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x1800829ec`
- `0x180086044`
- `0x18008a92c`
- `0x18008aecc`
- `0x18008f570`
- `0x180090810`
- `0x1800dbe0c`
- `0x1800dc754`
- `0x1800dd23c`
- `0x1800ded04`
- `0x1800df4a4`
- `0x1800df8c8`
- `0x1800e01dc`
- `0x1800e026c`
- `0x1800e02fc`
- `0x1800e038c`
- `0x1800e1134`
- `0x1800e1d10`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e061f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e0ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e061f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e0ccf`

## string_xrefs

- `0x1800e06ea`: `Windows.Data.Json.JsonObject`
- `0x1800e0832`: `Windows.Data.Json.JsonArray`
- `0x1800e03e3`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e044c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e04ae`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0516`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0594`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0676`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0722`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e07b3`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e086a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0913`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e09c7`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0a7b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0b3a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0c1b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0d0a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0e2e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e0e77`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`

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
            v51 = ModernDeployment::Autopilot::Core::DrainRetryQueue(v64);
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
0x1800e038c  mov     [rsp+arg_0], rbx
0x1800e0391  mov     [rsp+arg_10], rsi
0x1800e0396  push    rdi
0x1800e0397  push    r14
0x1800e0399  push    r15
0x1800e039b  sub     rsp, 0D0h
0x1800e03a2  mov     rax, cs:__security_cookie
0x1800e03a9  xor     rax, rsp
0x1800e03ac  mov     [rsp+0E8h+var_28], rax
0x1800e03b4  mov     rbx, rdx
0x1800e03b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e03be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e03c3  xor     r15d, r15d
0x1800e03c6  test    al, al
0x1800e03c8  jz      loc_1800E0E67
0x1800e03ce  test    rbx, rbx
0x1800e03d1  jnz     short loc_1800E03FB
0x1800e03d3  mov     rcx, [rsp+0E8h]; this
0x1800e03db  mov     ebx, 80070057h
0x1800e03e0  mov     r9d, ebx; char *
0x1800e03e3  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e03ea  mov     edx, 28Eh; void *
0x1800e03ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e03f4  mov     eax, ebx
0x1800e03f6  jmp     loc_1800E0E90
0x1800e03fb  mov     rdx, rbx
0x1800e03fe  lea     rcx, [rsp+0E8h+var_B0]
0x1800e0403  call    ??0?$com_ptr_t@UIUploadTelemetryRequest@Core@Autopilot@ModernDeployment@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUploadTelemetryRequest@Core@Autopilot@ModernDeployment@@@Z; wil::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>::com_ptr_t<ModernDeployment::Autopilot::Core::IUploadTelemetryRequest,wil::err_returncode_policy>(ModernDeployment::Autopilot::Core::IUploadTelemetryRequest *)
0x1800e0408  nop
0x1800e0409  xorps   xmm0, xmm0
0x1800e040c  movups  [rsp+0E8h+var_68], xmm0
0x1800e0414  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e041c  movdqu  [rsp+0E8h+var_58], xmm1
0x1800e0425  mov     word ptr [rsp+0E8h+var_68], r15w
0x1800e042e  lea     rcx, [rsp+0E8h+var_68]
0x1800e0436  call    ModernDeployment__Autopilot__Core__GetFwtUploadUrl
0x1800e043b  mov     ebx, eax
0x1800e043d  test    eax, eax
0x1800e043f  jns     short loc_1800E047D
0x1800e0441  mov     rcx, [rsp+0E8h]; this
0x1800e0449  mov     r9d, eax; char *
0x1800e044c  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0453  mov     edx, 293h; void *
0x1800e0458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e045d  nop
0x1800e045e  lea     rcx, [rsp+0E8h+var_68]
0x1800e0466  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e046b  nop
0x1800e046c  lea     rcx, [rsp+0E8h+var_B0]
0x1800e0471  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0476  mov     eax, ebx
0x1800e0478  jmp     loc_1800E0E90
0x1800e047d  mov     qword ptr [rsp+0E8h+var_C8], r15
0x1800e0482  mov     rcx, [rsp+0E8h+var_B0]
0x1800e0487  mov     rax, [rcx]
0x1800e048a  mov     qword ptr [rsp+0E8h+var_C8], r15; int
0x1800e048f  lea     rdx, [rsp+0E8h+var_C8]
0x1800e0494  mov     rax, [rax+30h]
0x1800e0498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e049d  mov     ebx, eax
0x1800e049f  test    eax, eax
0x1800e04a1  jns     short loc_1800E04EA
0x1800e04a3  mov     rcx, [rsp+0E8h]; this
0x1800e04ab  mov     r9d, eax; char *
0x1800e04ae  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e04b5  mov     edx, 296h; void *
0x1800e04ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e04bf  nop
0x1800e04c0  lea     rcx, [rsp+0E8h+var_C8]
0x1800e04c5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e04ca  nop
0x1800e04cb  lea     rcx, [rsp+0E8h+var_68]
0x1800e04d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e04d8  nop
0x1800e04d9  lea     rcx, [rsp+0E8h+var_B0]
0x1800e04de  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e04e3  mov     eax, ebx
0x1800e04e5  jmp     loc_1800E0E90
0x1800e04ea  mov     [rsp+0E8h+var_70], r15d
0x1800e04ef  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x1800e04f4  mov     rax, [rcx]
0x1800e04f7  lea     rdx, [rsp+0E8h+var_70]
0x1800e04fc  mov     rax, [rax+38h]
0x1800e0500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0505  mov     ebx, eax
0x1800e0507  test    eax, eax
0x1800e0509  jns     short loc_1800E0552
0x1800e050b  mov     rcx, [rsp+0E8h]; this
0x1800e0513  mov     r9d, eax; char *
0x1800e0516  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e051d  mov     edx, 298h; void *
0x1800e0522  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0527  nop
0x1800e0528  lea     rcx, [rsp+0E8h+var_C8]
0x1800e052d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0532  nop
0x1800e0533  lea     rcx, [rsp+0E8h+var_68]
0x1800e053b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e0540  nop
0x1800e0541  lea     rcx, [rsp+0E8h+var_B0]
0x1800e0546  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e054b  mov     eax, ebx
0x1800e054d  jmp     loc_1800E0E90
0x1800e0552  mov     r14d, r15d
0x1800e0555  cmp     r14d, [rsp+0E8h+var_70]
0x1800e055a  jnb     loc_1800E0E12
0x1800e0560  mov     [rsp+0E8h+var_B8], r15
0x1800e0565  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x1800e056a  mov     rax, [rcx]
0x1800e056d  mov     [rsp+0E8h+var_B8], r15
0x1800e0572  lea     r8, [rsp+0E8h+var_B8]
0x1800e0577  mov     edx, r14d
0x1800e057a  mov     rax, [rax+30h]
0x1800e057e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0583  mov     ebx, eax
0x1800e0585  test    eax, eax
0x1800e0587  jns     short loc_1800E05DB
0x1800e0589  mov     rcx, [rsp+0E8h]; this
0x1800e0591  mov     r9d, eax; char *
0x1800e0594  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e059b  mov     edx, 29Dh; void *
0x1800e05a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e05a5  nop
0x1800e05a6  lea     rcx, [rsp+0E8h+var_B8]
0x1800e05ab  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e05b0  nop
0x1800e05b1  lea     rcx, [rsp+0E8h+var_C8]
0x1800e05b6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e05bb  nop
0x1800e05bc  lea     rcx, [rsp+0E8h+var_68]
0x1800e05c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e05c9  nop
0x1800e05ca  lea     rcx, [rsp+0E8h+var_B0]
0x1800e05cf  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e05d4  mov     eax, ebx
0x1800e05d6  jmp     loc_1800E0E90
0x1800e05db  mov     [rsp+0E8h+string], r15
0x1800e05e0  mov     rdi, [rsp+0E8h+var_B8]
0x1800e05e5  mov     rax, [rdi]
0x1800e05e8  mov     rbx, [rax+30h]
0x1800e05ec  xor     edx, edx
0x1800e05ee  lea     rcx, [rsp+0E8h+string]
0x1800e05f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800e05f8  lea     rdx, [rsp+0E8h+string]
0x1800e05fd  mov     rcx, rdi
0x1800e0600  mov     rax, rbx
0x1800e0603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0608  lea     rcx, [rsp+0E8h+var_68]
0x1800e0610  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e0615  mov     rbx, rax
0x1800e0618  xor     edx, edx; length
0x1800e061a  mov     rcx, [rsp+0E8h+string]; string
0x1800e061f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e0626  nop     dword ptr [rax+rax+00h]
0x1800e062b  mov     rdi, rax
0x1800e062e  call    ?IsEnabled@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@SA_NE_K@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(uchar,unsigned __int64)
0x1800e0633  test    al, al
0x1800e0635  jz      short loc_1800E0647
0x1800e0637  call    ?get@?$static_lazy@VFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@@details@wil@@QEAAPEAVFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@P6AXXZ@Z; wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get(void (*)(void))
0x1800e063c  mov     r8, rbx; unsigned __int16 *
0x1800e063f  mov     rdx, rdi; unsigned __int16 *
0x1800e0642  call    ?ReportTelemetryEventStart_@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@QEAAXPEBG0@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::ReportTelemetryEventStart_(ushort const *,ushort const *)
0x1800e0647  mov     [rsp+0E8h+var_A0], r15
0x1800e064c  mov     [rsp+0E8h+var_90], r15d
0x1800e0651  lea     r8, [rsp+0E8h+var_90]
0x1800e0656  lea     rdx, [rsp+0E8h+var_A0]
0x1800e065b  lea     rcx, [rsp+0E8h+var_B8]
0x1800e0660  call    ModernDeployment__Autopilot__Core__CreateStructuredEventJson
0x1800e0665  mov     ebx, eax
0x1800e0667  test    eax, eax
0x1800e0669  jns     short loc_1800E06D3
0x1800e066b  mov     rcx, [rsp+0E8h]; this
0x1800e0673  mov     r9d, eax; char *
0x1800e0676  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e067d  mov     edx, 2A8h; void *
0x1800e0682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0687  nop
0x1800e0688  lea     rcx, [rsp+0E8h+var_A0]
0x1800e068d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0692  nop
0x1800e0693  lea     rcx, [rsp+0E8h+string]; this
0x1800e0698  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800e069d  nop
0x1800e069e  lea     rcx, [rsp+0E8h+var_B8]
0x1800e06a3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e06a8  nop
0x1800e06a9  lea     rcx, [rsp+0E8h+var_C8]
0x1800e06ae  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e06b3  nop
0x1800e06b4  lea     rcx, [rsp+0E8h+var_68]
0x1800e06bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e06c1  nop
0x1800e06c2  lea     rcx, [rsp+0E8h+var_B0]
0x1800e06c7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e06cc  mov     eax, ebx
0x1800e06ce  jmp     loc_1800E0E90
0x1800e06d3  mov     [rsp+0E8h+var_A8], r15
0x1800e06d8  mov     [rsp+0E8h+var_30], r15
0x1800e06e0  mov     r9d, 1Ch; unsigned int
0x1800e06e6  lea     r8d, [r9+1]; unsigned int
0x1800e06ea  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800e06f1  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800e06f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e06fe  nop
0x1800e06ff  lea     rdx, [rsp+0E8h+var_A8]
0x1800e0704  mov     rcx, [rsp+0E8h+var_30]
0x1800e070c  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800e0711  mov     ebx, eax
0x1800e0713  test    eax, eax
0x1800e0715  jns     short loc_1800E078A
0x1800e0717  mov     rcx, [rsp+0E8h]; this
0x1800e071f  mov     r9d, eax; char *
0x1800e0722  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0729  mov     edx, 2ACh; void *
0x1800e072e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0733  nop
0x1800e0734  lea     rcx, [rsp+0E8h+var_A8]
0x1800e0739  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e073e  nop
0x1800e073f  lea     rcx, [rsp+0E8h+var_A0]
0x1800e0744  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0749  nop
0x1800e074a  lea     rcx, [rsp+0E8h+string]; this
0x1800e074f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800e0754  nop
0x1800e0755  lea     rcx, [rsp+0E8h+var_B8]
0x1800e075a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e075f  nop
0x1800e0760  lea     rcx, [rsp+0E8h+var_C8]
0x1800e0765  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e076a  nop
0x1800e076b  lea     rcx, [rsp+0E8h+var_68]
0x1800e0773  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e0778  nop
0x1800e0779  lea     rcx, [rsp+0E8h+var_B0]
0x1800e077e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0783  mov     eax, ebx
0x1800e0785  jmp     loc_1800E0E90
0x1800e078a  lea     r8, a10_2; "1.0"
0x1800e0791  lea     rdx, aVersion; "Version"
0x1800e0798  mov     rcx, [rsp+0E8h+var_A8]; struct Windows::Data::Json::IJsonObject *
0x1800e079d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800e07a2  mov     ebx, eax
0x1800e07a4  test    eax, eax
0x1800e07a6  jns     short loc_1800E081B
0x1800e07a8  mov     rcx, [rsp+0E8h]; this
0x1800e07b0  mov     r9d, eax; char *
0x1800e07b3  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e07ba  mov     edx, 2ADh; void *
0x1800e07bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e07c4  nop
0x1800e07c5  lea     rcx, [rsp+0E8h+var_A8]
0x1800e07ca  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e07cf  nop
0x1800e07d0  lea     rcx, [rsp+0E8h+var_A0]
0x1800e07d5  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e07da  nop
0x1800e07db  lea     rcx, [rsp+0E8h+string]; this
0x1800e07e0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800e07e5  nop
0x1800e07e6  lea     rcx, [rsp+0E8h+var_B8]
0x1800e07eb  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e07f0  nop
0x1800e07f1  lea     rcx, [rsp+0E8h+var_C8]
0x1800e07f6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e07fb  nop
0x1800e07fc  lea     rcx, [rsp+0E8h+var_68]
0x1800e0804  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e0809  nop
0x1800e080a  lea     rcx, [rsp+0E8h+var_B0]
0x1800e080f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0814  mov     eax, ebx
0x1800e0816  jmp     loc_1800E0E90
0x1800e081b  mov     [rsp+0E8h+var_98], r15
0x1800e0820  mov     [rsp+0E8h+var_30], r15
0x1800e0828  mov     r9d, 1Bh; unsigned int
0x1800e082e  lea     r8d, [r9+1]; unsigned int
0x1800e0832  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800e0839  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800e0841  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e0846  nop
0x1800e0847  lea     rdx, [rsp+0E8h+var_98]
0x1800e084c  mov     rcx, [rsp+0E8h+var_30]
0x1800e0854  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800e0859  mov     ebx, eax
0x1800e085b  test    eax, eax
0x1800e085d  jns     short loc_1800E08DD
0x1800e085f  mov     rcx, [rsp+0E8h]; this
0x1800e0867  mov     r9d, eax; char *
0x1800e086a  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0871  mov     edx, 2B0h; void *
0x1800e0876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e087b  nop
0x1800e087c  lea     rcx, [rsp+0E8h+var_98]
0x1800e0881  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0886  nop
0x1800e0887  lea     rcx, [rsp+0E8h+var_A8]
0x1800e088c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0891  nop
0x1800e0892  lea     rcx, [rsp+0E8h+var_A0]
  ... truncated ...
```
