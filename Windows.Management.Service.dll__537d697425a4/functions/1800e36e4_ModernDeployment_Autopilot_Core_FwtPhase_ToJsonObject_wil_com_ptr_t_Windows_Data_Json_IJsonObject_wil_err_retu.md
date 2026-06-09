# ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_returncode_policy> &)

- ea: `0x1800e36e4`
- end: `0x1800e3d26`
- name: `?ToJsonObject@FwtPhase@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `1602`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e32c4`
- `0x1800e36e4`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180077e54`
- `0x180080bac`
- `0x1800829ec`
- `0x180086044`
- `0x18008a92c`
- `0x18008f4b4`
- `0x18008f570`
- `0x18008f6c0`
- `0x18008f800`
- `0x1800dbe0c`
- `0x1800e36e4`
- `0x180200010`

## string_xrefs

- `0x1800e373b`: `Windows.Data.Json.JsonObject`
- `0x1800e3930`: `Windows.Data.Json.JsonArray`
- `0x1800e376d`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e37bb`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3804`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3852`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e389b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e38e4`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3962`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e39c6`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3a37`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3ab1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3b27`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3bca`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3c46`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e3ceb`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(
        __int64 a1,
        struct Windows::Data::Json::IJsonObject **a2)
{
  int v4; // eax
  unsigned int v5; // edi
  const unsigned __int16 *v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rdi
  __int64 v23; // rsi
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  struct Windows::Data::Json::IJsonValue *v32; // rbx
  __int64 v33; // rax
  int v34; // eax
  unsigned int v35; // ebx
  struct Windows::Data::Json::IJsonObject *v36; // rax
  struct Windows::Data::Json::IJsonObject *v37; // rcx
  struct Windows::Data::Json::IJsonObject *v38; // [rsp+20h] [rbp-78h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-70h] BYREF
  __int64 v40; // [rsp+30h] [rbp-68h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-60h] BYREF
  __int64 v42; // [rsp+40h] [rbp-58h] BYREF
  struct Windows::Data::Json::IJsonValue *v43; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  __int64 v45; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    v38 = 0;
    v45 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v4 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v45, &v38);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v4,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v5;
    }
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v8 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v38, L"eventName", v7);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v8,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v9;
    }
    v10 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v38, L"Status", *(_DWORD *)(a1 + 32));
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v10,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v11;
    }
    v12 = Microsoft::Windows::Autopilot::JsonHelpers::Append(
            v38,
            L"DurationInMilliseconds",
            (double)(int)*(_QWORD *)(a1 + 40));
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v12,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v13;
    }
    v14 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v38, L"ErrorCode", *(_DWORD *)(a1 + 48));
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v14,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v15;
    }
    v16 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v38, L"RetryCount", *(_DWORD *)(a1 + 52));
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
        (const char *)(unsigned int)v16,
        (int)v38);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
      return v17;
    }
    if ( *(_QWORD *)(a1 + 56) != *(_QWORD *)(a1 + 64) )
    {
      v39 = 0;
      v45 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonArray",
        0x1Cu,
        0x1Bu);
      v18 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v45, &v39);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
          (const char *)(unsigned int)v18,
          (int)v38);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
        return v19;
      }
      v40 = 0;
      v20 = (**v39)(v39, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v40);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
          (const char *)(unsigned int)v20,
          (int)v38);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
        return v21;
      }
      v22 = *(_QWORD *)(a1 + 56);
      v23 = *(_QWORD *)(a1 + 64);
      while ( v22 != v23 )
      {
        v41 = 0;
        v24 = ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(v22, &v41);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x32,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
            (const char *)(unsigned int)v24,
            (int)v38);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v41);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
          return v25;
        }
        v42 = 0;
        v26 = (**v41)(v41, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v42);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
            (const char *)(unsigned int)v26,
            (int)v38);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v42);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v41);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
          return v27;
        }
        v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 104LL))(v40, v42);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x36,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
            (const char *)(unsigned int)v28,
            (int)v38);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v42);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v41);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
          wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
          return v29;
        }
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v42);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v41);
        v22 += 80;
      }
      v43 = 0;
      v30 = (**v39)(v39, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, (__int64 *)&v43);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
          (const char *)(unsigned int)v30,
          (int)v38);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v43);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
        return v31;
      }
      v32 = v43;
      v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180219390);
      v34 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v38, *(HSTRING *)(v33 + 24), v32);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
          (const char *)(unsigned int)v34,
          (int)v38);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v43);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
        return v35;
      }
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v43);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v39);
    }
    v36 = v38;
    v38 = 0;
    v37 = *a2;
    *a2 = v36;
    if ( v37 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v37 + 16LL))(v37);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v38);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtphase.cpp",
      (const char *)0x80004001LL,
      (int)v38);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800e36e4  mov     [rsp+arg_10], rbx
0x1800e36e9  push    rsi
0x1800e36ea  push    rdi
0x1800e36eb  push    r14
0x1800e36ed  sub     rsp, 80h
0x1800e36f4  mov     rax, cs:__security_cookie
0x1800e36fb  xor     rax, rsp
0x1800e36fe  mov     [rsp+98h+var_28], rax
0x1800e3703  mov     r14, rdx
0x1800e3706  mov     rbx, rcx
0x1800e3709  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e3710  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e3715  test    al, al
0x1800e3717  jz      loc_1800E3CDB
0x1800e371d  mov     [rsp+98h+var_78], 0; int
0x1800e3726  mov     [rsp+98h+var_30], 0
0x1800e372f  mov     esi, 1Ch
0x1800e3734  mov     r9d, esi; unsigned int
0x1800e3737  lea     r8d, [rsi+1]; unsigned int
0x1800e373b  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800e3742  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x1800e3747  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e374c  nop
0x1800e374d  lea     rdx, [rsp+98h+var_78]
0x1800e3752  mov     rcx, [rsp+98h+var_30]
0x1800e3757  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800e375c  mov     edi, eax
0x1800e375e  test    eax, eax
0x1800e3760  jns     short loc_1800E378E
0x1800e3762  mov     rcx, [rsp+98h]; this
0x1800e376a  mov     r9d, eax; char *
0x1800e376d  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3774  lea     edx, [rsi+2]; void *
0x1800e3777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e377c  nop
0x1800e377d  lea     rcx, [rsp+98h+var_78]
0x1800e3782  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3787  mov     eax, edi
0x1800e3789  jmp     loc_1800E3D04
0x1800e378e  mov     rcx, rbx
0x1800e3791  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e3796  mov     r8, rax; unsigned __int16 *
0x1800e3799  lea     rdx, aEventname_0; "eventName"
0x1800e37a0  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e37a5  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800e37aa  mov     edi, eax
0x1800e37ac  test    eax, eax
0x1800e37ae  jns     short loc_1800E37DE
0x1800e37b0  mov     rcx, [rsp+98h]; this
0x1800e37b8  mov     r9d, eax; char *
0x1800e37bb  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e37c2  mov     edx, 20h ; ' '; void *
0x1800e37c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e37cc  nop
0x1800e37cd  lea     rcx, [rsp+98h+var_78]
0x1800e37d2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e37d7  mov     eax, edi
0x1800e37d9  jmp     loc_1800E3D04
0x1800e37de  mov     r8d, [rbx+20h]; unsigned int
0x1800e37e2  lea     rdx, aStatus_0; "Status"
0x1800e37e9  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e37ee  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e37f3  mov     edi, eax
0x1800e37f5  test    eax, eax
0x1800e37f7  jns     short loc_1800E3827
0x1800e37f9  mov     rcx, [rsp+98h]; this
0x1800e3801  mov     r9d, eax; char *
0x1800e3804  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e380b  mov     edx, 21h ; '!'; void *
0x1800e3810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3815  nop
0x1800e3816  lea     rcx, [rsp+98h+var_78]
0x1800e381b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3820  mov     eax, edi
0x1800e3822  jmp     loc_1800E3D04
0x1800e3827  xorps   xmm2, xmm2
0x1800e382a  cvtsi2sd xmm2, qword ptr [rbx+28h]; double
0x1800e3830  lea     rdx, aDurationinmill; "DurationInMilliseconds"
0x1800e3837  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e383c  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGN@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,double)
0x1800e3841  mov     edi, eax
0x1800e3843  test    eax, eax
0x1800e3845  jns     short loc_1800E3875
0x1800e3847  mov     rcx, [rsp+98h]; this
0x1800e384f  mov     r9d, eax; char *
0x1800e3852  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3859  mov     edx, 22h ; '"'; void *
0x1800e385e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3863  nop
0x1800e3864  lea     rcx, [rsp+98h+var_78]
0x1800e3869  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e386e  mov     eax, edi
0x1800e3870  jmp     loc_1800E3D04
0x1800e3875  mov     r8d, [rbx+30h]; unsigned int
0x1800e3879  lea     rdx, aErrorcode; "ErrorCode"
0x1800e3880  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e3885  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e388a  mov     edi, eax
0x1800e388c  test    eax, eax
0x1800e388e  jns     short loc_1800E38BE
0x1800e3890  mov     rcx, [rsp+98h]; this
0x1800e3898  mov     r9d, eax; char *
0x1800e389b  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e38a2  mov     edx, 23h ; '#'; void *
0x1800e38a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e38ac  nop
0x1800e38ad  lea     rcx, [rsp+98h+var_78]
0x1800e38b2  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e38b7  mov     eax, edi
0x1800e38b9  jmp     loc_1800E3D04
0x1800e38be  mov     r8d, [rbx+34h]; unsigned int
0x1800e38c2  lea     rdx, aRetrycount; "RetryCount"
0x1800e38c9  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e38ce  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e38d3  mov     edi, eax
0x1800e38d5  test    eax, eax
0x1800e38d7  jns     short loc_1800E3907
0x1800e38d9  mov     rcx, [rsp+98h]; this
0x1800e38e1  mov     r9d, eax; char *
0x1800e38e4  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e38eb  mov     edx, 24h ; '$'; void *
0x1800e38f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e38f5  nop
0x1800e38f6  lea     rcx, [rsp+98h+var_78]
0x1800e38fb  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3900  mov     eax, edi
0x1800e3902  jmp     loc_1800E3D04
0x1800e3907  mov     rax, [rbx+40h]
0x1800e390b  cmp     [rbx+38h], rax
0x1800e390f  jz      loc_1800E3CA7
0x1800e3915  mov     [rsp+98h+var_70], 0
0x1800e391e  mov     [rsp+98h+var_30], 0
0x1800e3927  mov     r9d, 1Bh; unsigned int
0x1800e392d  mov     r8d, esi; unsigned int
0x1800e3930  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800e3937  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x1800e393c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e3941  nop
0x1800e3942  lea     rdx, [rsp+98h+var_70]
0x1800e3947  mov     rcx, [rsp+98h+var_30]
0x1800e394c  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800e3951  mov     edi, eax
0x1800e3953  test    eax, eax
0x1800e3955  jns     short loc_1800E3990
0x1800e3957  mov     rcx, [rsp+98h]; this
0x1800e395f  mov     r9d, eax; char *
0x1800e3962  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3969  mov     edx, 2Ah ; '*'; void *
0x1800e396e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3973  nop
0x1800e3974  lea     rcx, [rsp+98h+var_70]
0x1800e3979  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e397e  nop
0x1800e397f  lea     rcx, [rsp+98h+var_78]
0x1800e3984  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3989  mov     eax, edi
0x1800e398b  jmp     loc_1800E3D04
0x1800e3990  mov     [rsp+98h+var_68], 0
0x1800e3999  mov     rcx, [rsp+98h+var_70]
0x1800e399e  mov     rax, [rcx]
0x1800e39a1  lea     r8, [rsp+98h+var_68]
0x1800e39a6  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x1800e39ad  mov     rax, [rax]
0x1800e39b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e39b5  mov     edi, eax
0x1800e39b7  test    eax, eax
0x1800e39b9  jns     short loc_1800E39FF
0x1800e39bb  mov     rcx, [rsp+98h]; this
0x1800e39c3  mov     r9d, eax; char *
0x1800e39c6  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e39cd  mov     edx, 2Dh ; '-'; void *
0x1800e39d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e39d7  nop
0x1800e39d8  lea     rcx, [rsp+98h+var_68]
0x1800e39dd  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e39e2  nop
0x1800e39e3  lea     rcx, [rsp+98h+var_70]
0x1800e39e8  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e39ed  nop
0x1800e39ee  lea     rcx, [rsp+98h+var_78]
0x1800e39f3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e39f8  mov     eax, edi
0x1800e39fa  jmp     loc_1800E3D04
0x1800e39ff  mov     rdi, [rbx+38h]
0x1800e3a03  mov     rsi, [rbx+40h]
0x1800e3a07  cmp     rdi, rsi
0x1800e3a0a  jz      loc_1800E3B94
0x1800e3a10  mov     [rsp+98h+var_60], 0
0x1800e3a19  lea     rdx, [rsp+98h+var_60]
0x1800e3a1e  mov     rcx, rdi
0x1800e3a21  call    ?ToJsonObject@FwtPhase@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_returncode_policy> &)
0x1800e3a26  mov     ebx, eax
0x1800e3a28  test    eax, eax
0x1800e3a2a  jns     short loc_1800E3A7B
0x1800e3a2c  mov     rcx, [rsp+98h]; this
0x1800e3a34  mov     r9d, eax; char *
0x1800e3a37  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3a3e  mov     edx, 32h ; '2'; void *
0x1800e3a43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3a48  nop
0x1800e3a49  lea     rcx, [rsp+98h+var_60]
0x1800e3a4e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3a53  nop
0x1800e3a54  lea     rcx, [rsp+98h+var_68]
0x1800e3a59  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3a5e  nop
0x1800e3a5f  lea     rcx, [rsp+98h+var_70]
0x1800e3a64  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3a69  nop
0x1800e3a6a  lea     rcx, [rsp+98h+var_78]
0x1800e3a6f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3a74  mov     eax, ebx
0x1800e3a76  jmp     loc_1800E3D04
0x1800e3a7b  mov     [rsp+98h+var_58], 0
0x1800e3a84  mov     rcx, [rsp+98h+var_60]
0x1800e3a89  mov     rax, [rcx]
0x1800e3a8c  lea     r8, [rsp+98h+var_58]
0x1800e3a91  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800e3a98  mov     rax, [rax]
0x1800e3a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3aa0  mov     ebx, eax
0x1800e3aa2  test    eax, eax
0x1800e3aa4  jns     short loc_1800E3B00
0x1800e3aa6  mov     rcx, [rsp+98h]; this
0x1800e3aae  mov     r9d, eax; char *
0x1800e3ab1  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3ab8  mov     edx, 35h ; '5'; void *
0x1800e3abd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3ac2  nop
0x1800e3ac3  lea     rcx, [rsp+98h+var_58]
0x1800e3ac8  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3acd  nop
0x1800e3ace  lea     rcx, [rsp+98h+var_60]
0x1800e3ad3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3ad8  nop
0x1800e3ad9  lea     rcx, [rsp+98h+var_68]
0x1800e3ade  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3ae3  nop
0x1800e3ae4  lea     rcx, [rsp+98h+var_70]
0x1800e3ae9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3aee  nop
0x1800e3aef  lea     rcx, [rsp+98h+var_78]
0x1800e3af4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3af9  mov     eax, ebx
0x1800e3afb  jmp     loc_1800E3D04
0x1800e3b00  mov     rcx, [rsp+98h+var_68]
0x1800e3b05  mov     rax, [rcx]
0x1800e3b08  mov     rdx, [rsp+98h+var_58]
0x1800e3b0d  mov     rax, [rax+68h]
0x1800e3b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b16  mov     ebx, eax
0x1800e3b18  test    eax, eax
0x1800e3b1a  jns     short loc_1800E3B76
0x1800e3b1c  mov     rcx, [rsp+98h]; this
0x1800e3b24  mov     r9d, eax; char *
0x1800e3b27  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3b2e  mov     edx, 36h ; '6'; void *
0x1800e3b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3b38  nop
0x1800e3b39  lea     rcx, [rsp+98h+var_58]
0x1800e3b3e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b43  nop
0x1800e3b44  lea     rcx, [rsp+98h+var_60]
0x1800e3b49  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b4e  nop
0x1800e3b4f  lea     rcx, [rsp+98h+var_68]
0x1800e3b54  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b59  nop
0x1800e3b5a  lea     rcx, [rsp+98h+var_70]
0x1800e3b5f  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b64  nop
0x1800e3b65  lea     rcx, [rsp+98h+var_78]
0x1800e3b6a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b6f  mov     eax, ebx
0x1800e3b71  jmp     loc_1800E3D04
0x1800e3b76  lea     rcx, [rsp+98h+var_58]
0x1800e3b7b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b80  nop
0x1800e3b81  lea     rcx, [rsp+98h+var_60]
0x1800e3b86  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e3b8b  add     rdi, 50h ; 'P'
0x1800e3b8f  jmp     loc_1800E3A07
0x1800e3b94  mov     [rsp+98h+var_50], 0
0x1800e3b9d  mov     rcx, [rsp+98h+var_70]
0x1800e3ba2  mov     rax, [rcx]
0x1800e3ba5  lea     r8, [rsp+98h+var_50]
0x1800e3baa  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800e3bb1  mov     rax, [rax]
0x1800e3bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3bb9  mov     ebx, eax
0x1800e3bbb  test    eax, eax
0x1800e3bbd  jns     short loc_1800E3C0E
0x1800e3bbf  mov     rcx, [rsp+98h]; this
0x1800e3bc7  mov     r9d, eax; char *
0x1800e3bca  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3bd1  mov     edx, 3Ah ; ':'; void *
0x1800e3bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3bdb  nop
0x1800e3bdc  lea     rcx, [rsp+98h+var_50]
0x1800e3be1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
  ... truncated ...
```
