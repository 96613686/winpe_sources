# ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_returncode_policy> &)

- ea: `0x1800e0e64`
- end: `0x1800e14a6`
- name: `?ToJsonObject@FwtPhase@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `1602`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e0a4c`
- `0x1800e0e64`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x1800775c4`
- `0x18008019c`
- `0x180081f1c`
- `0x1800853a0`
- `0x180089ac8`
- `0x18008e380`
- `0x18008e438`
- `0x18008e584`
- `0x18008e6c0`
- `0x1800d9688`
- `0x1800e0e64`
- `0x1801fa010`

## string_xrefs

- `0x1800e0ebb`: `Windows.Data.Json.JsonObject`
- `0x1800e10b0`: `Windows.Data.Json.JsonArray`
- `0x1800e0eed`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e0f3b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e0f84`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e0fd2`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e101b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e1064`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e10e2`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e1146`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e11b7`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e1231`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e12a7`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e134a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e13c6`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`
- `0x1800e146b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtphase.cpp`

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
      v33 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_180213390);
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
0x1800e0e64  mov     [rsp+arg_10], rbx
0x1800e0e69  push    rsi
0x1800e0e6a  push    rdi
0x1800e0e6b  push    r14
0x1800e0e6d  sub     rsp, 80h
0x1800e0e74  mov     rax, cs:__security_cookie
0x1800e0e7b  xor     rax, rsp
0x1800e0e7e  mov     [rsp+98h+var_28], rax
0x1800e0e83  mov     r14, rdx
0x1800e0e86  mov     rbx, rcx
0x1800e0e89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e0e90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e0e95  test    al, al
0x1800e0e97  jz      loc_1800E145B
0x1800e0e9d  mov     [rsp+98h+var_78], 0; int
0x1800e0ea6  mov     [rsp+98h+var_30], 0
0x1800e0eaf  mov     esi, 1Ch
0x1800e0eb4  mov     r9d, esi; unsigned int
0x1800e0eb7  lea     r8d, [rsi+1]; unsigned int
0x1800e0ebb  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1800e0ec2  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x1800e0ec7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e0ecc  nop
0x1800e0ecd  lea     rdx, [rsp+98h+var_78]
0x1800e0ed2  mov     rcx, [rsp+98h+var_30]
0x1800e0ed7  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800e0edc  mov     edi, eax
0x1800e0ede  test    eax, eax
0x1800e0ee0  jns     short loc_1800E0F0E
0x1800e0ee2  mov     rcx, [rsp+98h]; this
0x1800e0eea  mov     r9d, eax; char *
0x1800e0eed  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0ef4  lea     edx, [rsi+2]; void *
0x1800e0ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0efc  nop
0x1800e0efd  lea     rcx, [rsp+98h+var_78]
0x1800e0f02  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0f07  mov     eax, edi
0x1800e0f09  jmp     loc_1800E1484
0x1800e0f0e  mov     rcx, rbx
0x1800e0f11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e0f16  mov     r8, rax; unsigned __int16 *
0x1800e0f19  lea     rdx, aEventname_0; "eventName"
0x1800e0f20  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e0f25  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1800e0f2a  mov     edi, eax
0x1800e0f2c  test    eax, eax
0x1800e0f2e  jns     short loc_1800E0F5E
0x1800e0f30  mov     rcx, [rsp+98h]; this
0x1800e0f38  mov     r9d, eax; char *
0x1800e0f3b  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0f42  mov     edx, 20h ; ' '; void *
0x1800e0f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0f4c  nop
0x1800e0f4d  lea     rcx, [rsp+98h+var_78]
0x1800e0f52  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0f57  mov     eax, edi
0x1800e0f59  jmp     loc_1800E1484
0x1800e0f5e  mov     r8d, [rbx+20h]; unsigned int
0x1800e0f62  lea     rdx, aStatus_0; "Status"
0x1800e0f69  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e0f6e  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e0f73  mov     edi, eax
0x1800e0f75  test    eax, eax
0x1800e0f77  jns     short loc_1800E0FA7
0x1800e0f79  mov     rcx, [rsp+98h]; this
0x1800e0f81  mov     r9d, eax; char *
0x1800e0f84  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0f8b  mov     edx, 21h ; '!'; void *
0x1800e0f90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0f95  nop
0x1800e0f96  lea     rcx, [rsp+98h+var_78]
0x1800e0f9b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0fa0  mov     eax, edi
0x1800e0fa2  jmp     loc_1800E1484
0x1800e0fa7  xorps   xmm2, xmm2
0x1800e0faa  cvtsi2sd xmm2, qword ptr [rbx+28h]; double
0x1800e0fb0  lea     rdx, aDurationinmill; "DurationInMilliseconds"
0x1800e0fb7  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e0fbc  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGN@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,double)
0x1800e0fc1  mov     edi, eax
0x1800e0fc3  test    eax, eax
0x1800e0fc5  jns     short loc_1800E0FF5
0x1800e0fc7  mov     rcx, [rsp+98h]; this
0x1800e0fcf  mov     r9d, eax; char *
0x1800e0fd2  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e0fd9  mov     edx, 22h ; '"'; void *
0x1800e0fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0fe3  nop
0x1800e0fe4  lea     rcx, [rsp+98h+var_78]
0x1800e0fe9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e0fee  mov     eax, edi
0x1800e0ff0  jmp     loc_1800E1484
0x1800e0ff5  mov     r8d, [rbx+30h]; unsigned int
0x1800e0ff9  lea     rdx, aErrorcode; "ErrorCode"
0x1800e1000  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e1005  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e100a  mov     edi, eax
0x1800e100c  test    eax, eax
0x1800e100e  jns     short loc_1800E103E
0x1800e1010  mov     rcx, [rsp+98h]; this
0x1800e1018  mov     r9d, eax; char *
0x1800e101b  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e1022  mov     edx, 23h ; '#'; void *
0x1800e1027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e102c  nop
0x1800e102d  lea     rcx, [rsp+98h+var_78]
0x1800e1032  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1037  mov     eax, edi
0x1800e1039  jmp     loc_1800E1484
0x1800e103e  mov     r8d, [rbx+34h]; unsigned int
0x1800e1042  lea     rdx, aRetrycount; "RetryCount"
0x1800e1049  mov     rcx, [rsp+98h+var_78]; struct Windows::Data::Json::IJsonObject *
0x1800e104e  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1800e1053  mov     edi, eax
0x1800e1055  test    eax, eax
0x1800e1057  jns     short loc_1800E1087
0x1800e1059  mov     rcx, [rsp+98h]; this
0x1800e1061  mov     r9d, eax; char *
0x1800e1064  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e106b  mov     edx, 24h ; '$'; void *
0x1800e1070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1075  nop
0x1800e1076  lea     rcx, [rsp+98h+var_78]
0x1800e107b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1080  mov     eax, edi
0x1800e1082  jmp     loc_1800E1484
0x1800e1087  mov     rax, [rbx+40h]
0x1800e108b  cmp     [rbx+38h], rax
0x1800e108f  jz      loc_1800E1427
0x1800e1095  mov     [rsp+98h+var_70], 0
0x1800e109e  mov     [rsp+98h+var_30], 0
0x1800e10a7  mov     r9d, 1Bh; unsigned int
0x1800e10ad  mov     r8d, esi; unsigned int
0x1800e10b0  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800e10b7  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x1800e10bc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800e10c1  nop
0x1800e10c2  lea     rdx, [rsp+98h+var_70]
0x1800e10c7  mov     rcx, [rsp+98h+var_30]
0x1800e10cc  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800e10d1  mov     edi, eax
0x1800e10d3  test    eax, eax
0x1800e10d5  jns     short loc_1800E1110
0x1800e10d7  mov     rcx, [rsp+98h]; this
0x1800e10df  mov     r9d, eax; char *
0x1800e10e2  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e10e9  mov     edx, 2Ah ; '*'; void *
0x1800e10ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e10f3  nop
0x1800e10f4  lea     rcx, [rsp+98h+var_70]
0x1800e10f9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e10fe  nop
0x1800e10ff  lea     rcx, [rsp+98h+var_78]
0x1800e1104  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1109  mov     eax, edi
0x1800e110b  jmp     loc_1800E1484
0x1800e1110  mov     [rsp+98h+var_68], 0
0x1800e1119  mov     rcx, [rsp+98h+var_70]
0x1800e111e  mov     rax, [rcx]
0x1800e1121  lea     r8, [rsp+98h+var_68]
0x1800e1126  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x1800e112d  mov     rax, [rax]
0x1800e1130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1135  mov     edi, eax
0x1800e1137  test    eax, eax
0x1800e1139  jns     short loc_1800E117F
0x1800e113b  mov     rcx, [rsp+98h]; this
0x1800e1143  mov     r9d, eax; char *
0x1800e1146  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e114d  mov     edx, 2Dh ; '-'; void *
0x1800e1152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1157  nop
0x1800e1158  lea     rcx, [rsp+98h+var_68]
0x1800e115d  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1162  nop
0x1800e1163  lea     rcx, [rsp+98h+var_70]
0x1800e1168  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e116d  nop
0x1800e116e  lea     rcx, [rsp+98h+var_78]
0x1800e1173  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1178  mov     eax, edi
0x1800e117a  jmp     loc_1800E1484
0x1800e117f  mov     rdi, [rbx+38h]
0x1800e1183  mov     rsi, [rbx+40h]
0x1800e1187  cmp     rdi, rsi
0x1800e118a  jz      loc_1800E1314
0x1800e1190  mov     [rsp+98h+var_60], 0
0x1800e1199  lea     rdx, [rsp+98h+var_60]
0x1800e119e  mov     rcx, rdi
0x1800e11a1  call    ?ToJsonObject@FwtPhase@Core@Autopilot@ModernDeployment@@QEBAJAEAV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; ModernDeployment::Autopilot::Core::FwtPhase::ToJsonObject(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_returncode_policy> &)
0x1800e11a6  mov     ebx, eax
0x1800e11a8  test    eax, eax
0x1800e11aa  jns     short loc_1800E11FB
0x1800e11ac  mov     rcx, [rsp+98h]; this
0x1800e11b4  mov     r9d, eax; char *
0x1800e11b7  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e11be  mov     edx, 32h ; '2'; void *
0x1800e11c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e11c8  nop
0x1800e11c9  lea     rcx, [rsp+98h+var_60]
0x1800e11ce  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e11d3  nop
0x1800e11d4  lea     rcx, [rsp+98h+var_68]
0x1800e11d9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e11de  nop
0x1800e11df  lea     rcx, [rsp+98h+var_70]
0x1800e11e4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e11e9  nop
0x1800e11ea  lea     rcx, [rsp+98h+var_78]
0x1800e11ef  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e11f4  mov     eax, ebx
0x1800e11f6  jmp     loc_1800E1484
0x1800e11fb  mov     [rsp+98h+var_58], 0
0x1800e1204  mov     rcx, [rsp+98h+var_60]
0x1800e1209  mov     rax, [rcx]
0x1800e120c  lea     r8, [rsp+98h+var_58]
0x1800e1211  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800e1218  mov     rax, [rax]
0x1800e121b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1220  mov     ebx, eax
0x1800e1222  test    eax, eax
0x1800e1224  jns     short loc_1800E1280
0x1800e1226  mov     rcx, [rsp+98h]; this
0x1800e122e  mov     r9d, eax; char *
0x1800e1231  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e1238  mov     edx, 35h ; '5'; void *
0x1800e123d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1242  nop
0x1800e1243  lea     rcx, [rsp+98h+var_58]
0x1800e1248  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e124d  nop
0x1800e124e  lea     rcx, [rsp+98h+var_60]
0x1800e1253  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1258  nop
0x1800e1259  lea     rcx, [rsp+98h+var_68]
0x1800e125e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1263  nop
0x1800e1264  lea     rcx, [rsp+98h+var_70]
0x1800e1269  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e126e  nop
0x1800e126f  lea     rcx, [rsp+98h+var_78]
0x1800e1274  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1279  mov     eax, ebx
0x1800e127b  jmp     loc_1800E1484
0x1800e1280  mov     rcx, [rsp+98h+var_68]
0x1800e1285  mov     rax, [rcx]
0x1800e1288  mov     rdx, [rsp+98h+var_58]
0x1800e128d  mov     rax, [rax+68h]
0x1800e1291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1296  mov     ebx, eax
0x1800e1298  test    eax, eax
0x1800e129a  jns     short loc_1800E12F6
0x1800e129c  mov     rcx, [rsp+98h]; this
0x1800e12a4  mov     r9d, eax; char *
0x1800e12a7  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e12ae  mov     edx, 36h ; '6'; void *
0x1800e12b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e12b8  nop
0x1800e12b9  lea     rcx, [rsp+98h+var_58]
0x1800e12be  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e12c3  nop
0x1800e12c4  lea     rcx, [rsp+98h+var_60]
0x1800e12c9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e12ce  nop
0x1800e12cf  lea     rcx, [rsp+98h+var_68]
0x1800e12d4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e12d9  nop
0x1800e12da  lea     rcx, [rsp+98h+var_70]
0x1800e12df  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e12e4  nop
0x1800e12e5  lea     rcx, [rsp+98h+var_78]
0x1800e12ea  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e12ef  mov     eax, ebx
0x1800e12f1  jmp     loc_1800E1484
0x1800e12f6  lea     rcx, [rsp+98h+var_58]
0x1800e12fb  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e1300  nop
0x1800e1301  lea     rcx, [rsp+98h+var_60]
0x1800e1306  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800e130b  add     rdi, 50h ; 'P'
0x1800e130f  jmp     loc_1800E1187
0x1800e1314  mov     [rsp+98h+var_50], 0
0x1800e131d  mov     rcx, [rsp+98h+var_70]
0x1800e1322  mov     rax, [rcx]
0x1800e1325  lea     r8, [rsp+98h+var_50]
0x1800e132a  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1800e1331  mov     rax, [rax]
0x1800e1334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1339  mov     ebx, eax
0x1800e133b  test    eax, eax
0x1800e133d  jns     short loc_1800E138E
0x1800e133f  mov     rcx, [rsp+98h]; this
0x1800e1347  mov     r9d, eax; char *
0x1800e134a  lea     r8, aOnecoreuapAdmi_92; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e1351  mov     edx, 3Ah ; ':'; void *
0x1800e1356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e135b  nop
0x1800e135c  lea     rcx, [rsp+98h+var_50]
0x1800e1361  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
  ... truncated ...
```
