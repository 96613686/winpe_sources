# _lambda_6ff04c71ed6e183f6414ec44cd1a1a95_::operator()

- ea: `0x1800f3ac4`
- end: `0x1800f4018`
- name: `_lambda_6ff04c71ed6e183f6414ec44cd1a1a95_::operator()`
- size: `1364`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f66a0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006defc`
- `0x18007755c`
- `0x18008019c`
- `0x180081f1c`
- `0x1800839bc`
- `0x1800841e8`
- `0x18008939c`
- `0x18008c244`
- `0x1800a7fac`
- `0x1800f3090`
- `0x1800f38ec`
- `0x1800f3ac4`
- `0x1800f68e8`
- `0x18019f050`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3c03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f3c03`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3df4`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3df4`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3e39`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3eaf`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3f0b`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3e39`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3eaf`
- `OLEAUT32!__imp_VariantClear` at `0x1800f3f0b`

## string_xrefs

- `0x1800f3b20`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\AgileHelpers.h`
- `0x1800f3c53`: `./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext`
- `0x1800f3b3c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3bae`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3c1a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3ccf`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3d53`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3e22`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3e98`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f3f88`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall lambda_6ff04c71ed6e183f6414ec44cd1a1a95_::operator()(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int Context; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  LPVOID v10; // rbx
  __int64 (__fastcall *v11)(LPVOID, _QWORD, __int64 *); // rdi
  __int64 v12; // rdx
  _QWORD *bstr; // rax
  int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // ebx
  int ppv; // [rsp+20h] [rbp-A8h]
  int ppva; // [rsp+20h] [rbp-A8h]
  LPVOID v23; // [rsp+30h] [rbp-98h] BYREF
  __int64 v24; // [rsp+38h] [rbp-90h] BYREF
  __int64 v25; // [rsp+40h] [rbp-88h] BYREF
  int v26; // [rsp+48h] [rbp-80h] BYREF
  __int64 v27; // [rsp+50h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-70h] BYREF
  _OWORD v29[2]; // [rsp+70h] [rbp-58h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v24 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)*a1 + 24LL))(
         *a1,
         &GUID_ebd8677f_dfd2_59da_ac3d_753ee1667cbb,
         &v24);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\AgileHelpers.h",
      (const char *)(unsigned int)v3,
      ppv);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningpro"
                    "gressreporter.cpp",
      (const char *)v4,
      ppva);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
    return v4;
  }
  v29[0] = 0;
  v29[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v29[0]) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl'::`2'::impl) )
  {
    Context = Microsoft::Windows::Autopilot::DppContextUtils::GetContext(v29);
    v7 = Context;
    if ( Context < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)(unsigned int)Context,
        ppv);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return v7;
    }
  }
  else
  {
    v23 = 0;
    v8 = CoCreateInstance(
           &GUID_66d0db14_5638_475f_a386_629522d8c461,
           0,
           1u,
           &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
           &v23);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)(unsigned int)v8,
        ppv);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return v9;
    }
    std::wstring::wstring(v30, L"./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext");
    v25 = 0;
    v10 = v23;
    v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v23 + 80LL);
    v25 = 0;
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    bstr = (_QWORD *)wil::make_bstr(&v27, v12);
    v14 = v11(v10, *bstr, &v25);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)(unsigned int)v14,
        ppv);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return (unsigned int)v14;
    }
    v26 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 224LL))(v25, &v26);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)(unsigned int)v15,
        ppv);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return v16;
    }
    if ( !v26 )
    {
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return 2147943568LL;
    }
    VariantInit(&pvarg);
    v17 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v25 + 104LL))(v25, &pvarg);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)(unsigned int)v17,
        ppv);
      VariantClear(&pvarg);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return v18;
    }
    if ( pvarg.vt != 8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningp"
                      "rogressreporter.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
      VariantClear(&pvarg);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
      std::wstring::_Tidy_deallocate(v30);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
      std::wstring::_Tidy_deallocate(v29);
      wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
      return 2147549183LL;
    }
    std::wstring::assign(v29, pvarg.llVal);
    VariantClear(&pvarg);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v25);
    std::wstring::_Tidy_deallocate(v30);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v23);
  }
  v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
  v27 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v30, &v27) + 24);
  v23 = 0;
  v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Management::Setup::DevicePreparationExecutionContext,Windows::Management::Setup::DevicePreparationExecutionContext,HSTRING__ *>(
          &v23,
          &v27);
  v20 = v19;
  if ( v19 >= 0 )
  {
    Windows::Internal::CMarshaledInterfaceResult<Windows::Management::Setup::IDevicePreparationExecutionContext>::Set(
      a2,
      v23);
    wil::com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>(&v23);
    std::wstring::_Tidy_deallocate(v29);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\machineprovisioningpro"
                    "gressreporter.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    wil::com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>(&v23);
    std::wstring::_Tidy_deallocate(v29);
    wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(&v24);
    return v20;
  }
}

```

## disassembly

```asm
0x1800f3ac4  mov     [rsp+arg_10], rbx
0x1800f3ac9  mov     [rsp+arg_18], rsi
0x1800f3ace  push    rdi
0x1800f3acf  sub     rsp, 0C0h
0x1800f3ad6  mov     rax, cs:__security_cookie
0x1800f3add  xor     rax, rsp
0x1800f3ae0  mov     [rsp+0C8h+var_18], rax
0x1800f3ae8  mov     rsi, rdx
0x1800f3aeb  mov     [rsp+0C8h+var_90], 0
0x1800f3af4  mov     rcx, [rcx]
0x1800f3af7  mov     rax, [rcx]
0x1800f3afa  lea     r8, [rsp+0C8h+var_90]
0x1800f3aff  lea     rdx, _GUID_ebd8677f_dfd2_59da_ac3d_753ee1667cbb
0x1800f3b06  mov     rax, [rax+18h]
0x1800f3b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3b0f  mov     ebx, eax
0x1800f3b11  test    eax, eax
0x1800f3b13  jns     short loc_1800F3B5F
0x1800f3b15  mov     rcx, [rsp+0C8h]; this
0x1800f3b1d  mov     r9d, eax; char *
0x1800f3b20  lea     r8, aOnecoreuapAdmi_53; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3b27  mov     edx, 37h ; '7'; void *
0x1800f3b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3b31  mov     rcx, [rsp+0C8h]; this
0x1800f3b39  mov     r9d, ebx; char *
0x1800f3b3c  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3b43  mov     edx, 0B9h; void *
0x1800f3b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3b4d  nop
0x1800f3b4e  lea     rcx, [rsp+0C8h+var_90]
0x1800f3b53  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3b58  mov     eax, ebx
0x1800f3b5a  jmp     loc_1800F3FF2
0x1800f3b5f  xorps   xmm0, xmm0
0x1800f3b62  movups  [rsp+0C8h+var_58], xmm0
0x1800f3b67  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800f3b6f  movdqu  [rsp+0C8h+var_48], xmm1
0x1800f3b78  xor     eax, eax
0x1800f3b7a  mov     word ptr [rsp+0C8h+var_58], ax
0x1800f3b7f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl(void)'::`2'::impl
0x1800f3b86  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(void)
0x1800f3b8b  test    al, al
0x1800f3b8d  jz      short loc_1800F3BDC
0x1800f3b8f  lea     rcx, [rsp+0C8h+var_58]
0x1800f3b94  call    ?GetContext@DppContextUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DppContextUtils::GetContext(std::wstring &)
0x1800f3b99  mov     ebx, eax
0x1800f3b9b  test    eax, eax
0x1800f3b9d  jns     loc_1800F3F35
0x1800f3ba3  mov     rcx, [rsp+0C8h]; this
0x1800f3bab  mov     r9d, eax; char *
0x1800f3bae  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3bb5  mov     edx, 0BEh; void *
0x1800f3bba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3bbf  nop
0x1800f3bc0  lea     rcx, [rsp+0C8h+var_58]
0x1800f3bc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3bca  nop
0x1800f3bcb  lea     rcx, [rsp+0C8h+var_90]
0x1800f3bd0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3bd5  mov     eax, ebx
0x1800f3bd7  jmp     loc_1800F3FF2
0x1800f3bdc  mov     [rsp+0C8h+var_98], 0
0x1800f3be5  lea     rax, [rsp+0C8h+var_98]
0x1800f3bea  mov     qword ptr [rsp+0C8h+ppv], rax; int
0x1800f3bef  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800f3bf6  xor     edx, edx; pUnkOuter
0x1800f3bf8  lea     r8d, [rdx+1]; dwClsContext
0x1800f3bfc  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800f3c03  call    cs:__imp_CoCreateInstance
0x1800f3c09  mov     ebx, eax
0x1800f3c0b  test    eax, eax
0x1800f3c0d  jns     short loc_1800F3C53
0x1800f3c0f  mov     rcx, [rsp+0C8h]; this
0x1800f3c17  mov     r9d, eax; char *
0x1800f3c1a  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3c21  mov     edx, 0C4h; void *
0x1800f3c26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3c2b  nop
0x1800f3c2c  lea     rcx, [rsp+0C8h+var_98]
0x1800f3c31  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3c36  nop
0x1800f3c37  lea     rcx, [rsp+0C8h+var_58]
0x1800f3c3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3c41  nop
0x1800f3c42  lea     rcx, [rsp+0C8h+var_90]
0x1800f3c47  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3c4c  mov     eax, ebx
0x1800f3c4e  jmp     loc_1800F3FF2
0x1800f3c53  lea     rdx, aDeviceVendorMs; "./Device/Vendor/MSFT/DevicePreparation/"...
0x1800f3c5a  lea     rcx, [rsp+0C8h+var_38]
0x1800f3c62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f3c67  nop
0x1800f3c68  mov     [rsp+0C8h+var_88], 0
0x1800f3c71  mov     rbx, [rsp+0C8h+var_98]
0x1800f3c76  mov     rax, [rbx]
0x1800f3c79  mov     rdi, [rax+50h]
0x1800f3c7d  mov     [rsp+0C8h+var_88], 0
0x1800f3c86  lea     rcx, [rsp+0C8h+var_38]
0x1800f3c8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f3c93  mov     rdx, rax
0x1800f3c96  lea     rcx, [rsp+0C8h+var_78]
0x1800f3c9b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f3ca0  nop
0x1800f3ca1  lea     r8, [rsp+0C8h+var_88]
0x1800f3ca6  mov     rdx, [rax]
0x1800f3ca9  mov     rcx, rbx
0x1800f3cac  mov     rax, rdi
0x1800f3caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3cb4  mov     ebx, eax
0x1800f3cb6  lea     rcx, [rsp+0C8h+var_78]
0x1800f3cbb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f3cc0  test    ebx, ebx
0x1800f3cc2  jns     short loc_1800F3D21
0x1800f3cc4  mov     rcx, [rsp+0C8h]; this
0x1800f3ccc  mov     r9d, ebx; char *
0x1800f3ccf  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3cd6  mov     edx, 0C9h; void *
0x1800f3cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3ce0  nop
0x1800f3ce1  lea     rcx, [rsp+0C8h+var_88]
0x1800f3ce6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3ceb  nop
0x1800f3cec  lea     rcx, [rsp+0C8h+var_38]
0x1800f3cf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3cf9  nop
0x1800f3cfa  lea     rcx, [rsp+0C8h+var_98]
0x1800f3cff  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3d04  nop
0x1800f3d05  lea     rcx, [rsp+0C8h+var_58]
0x1800f3d0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3d0f  nop
0x1800f3d10  lea     rcx, [rsp+0C8h+var_90]
0x1800f3d15  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3d1a  mov     eax, ebx
0x1800f3d1c  jmp     loc_1800F3FF2
0x1800f3d21  mov     [rsp+0C8h+var_80], 0
0x1800f3d29  mov     rcx, [rsp+0C8h+var_88]
0x1800f3d2e  mov     rax, [rcx]
0x1800f3d31  lea     rdx, [rsp+0C8h+var_80]
0x1800f3d36  mov     rax, [rax+0E0h]
0x1800f3d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3d42  mov     ebx, eax
0x1800f3d44  test    eax, eax
0x1800f3d46  jns     short loc_1800F3DA5
0x1800f3d48  mov     rcx, [rsp+0C8h]; this
0x1800f3d50  mov     r9d, eax; char *
0x1800f3d53  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3d5a  mov     edx, 0CCh; void *
0x1800f3d5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3d64  nop
0x1800f3d65  lea     rcx, [rsp+0C8h+var_88]
0x1800f3d6a  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3d6f  nop
0x1800f3d70  lea     rcx, [rsp+0C8h+var_38]
0x1800f3d78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3d7d  nop
0x1800f3d7e  lea     rcx, [rsp+0C8h+var_98]
0x1800f3d83  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3d88  nop
0x1800f3d89  lea     rcx, [rsp+0C8h+var_58]
0x1800f3d8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3d93  nop
0x1800f3d94  lea     rcx, [rsp+0C8h+var_90]
0x1800f3d99  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3d9e  mov     eax, ebx
0x1800f3da0  jmp     loc_1800F3FF2
0x1800f3da5  cmp     [rsp+0C8h+var_80], 0
0x1800f3daa  jnz     short loc_1800F3DEF
0x1800f3dac  lea     rcx, [rsp+0C8h+var_88]
0x1800f3db1  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3db6  nop
0x1800f3db7  lea     rcx, [rsp+0C8h+var_38]
0x1800f3dbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3dc4  nop
0x1800f3dc5  lea     rcx, [rsp+0C8h+var_98]
0x1800f3dca  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3dcf  nop
0x1800f3dd0  lea     rcx, [rsp+0C8h+var_58]
0x1800f3dd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3dda  nop
0x1800f3ddb  lea     rcx, [rsp+0C8h+var_90]
0x1800f3de0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3de5  mov     eax, 80070490h
0x1800f3dea  jmp     loc_1800F3FF2
0x1800f3def  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f3df4  call    cs:__imp_VariantInit
0x1800f3dfa  nop
0x1800f3dfb  mov     rcx, [rsp+0C8h+var_88]
0x1800f3e00  mov     rax, [rcx]
0x1800f3e03  lea     rdx, [rsp+0C8h+pvarg]
0x1800f3e08  mov     rax, [rax+68h]
0x1800f3e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3e11  mov     ebx, eax
0x1800f3e13  test    eax, eax
0x1800f3e15  jns     short loc_1800F3E80
0x1800f3e17  mov     rcx, [rsp+0C8h]; this
0x1800f3e1f  mov     r9d, eax; char *
0x1800f3e22  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3e29  mov     edx, 0D4h; void *
0x1800f3e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3e33  nop
0x1800f3e34  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f3e39  call    cs:__imp_VariantClear
0x1800f3e3f  nop
0x1800f3e40  lea     rcx, [rsp+0C8h+var_88]
0x1800f3e45  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3e4a  nop
0x1800f3e4b  lea     rcx, [rsp+0C8h+var_38]
0x1800f3e53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3e58  nop
0x1800f3e59  lea     rcx, [rsp+0C8h+var_98]
0x1800f3e5e  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3e63  nop
0x1800f3e64  lea     rcx, [rsp+0C8h+var_58]
0x1800f3e69  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3e6e  nop
0x1800f3e6f  lea     rcx, [rsp+0C8h+var_90]
0x1800f3e74  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3e79  mov     eax, ebx
0x1800f3e7b  jmp     loc_1800F3FF2
0x1800f3e80  cmp     word ptr [rsp+0C8h+pvarg], 8
0x1800f3e86  jz      short loc_1800F3EF6
0x1800f3e88  mov     rcx, [rsp+0C8h]; this
0x1800f3e90  mov     ebx, 8000FFFFh
0x1800f3e95  mov     r9d, ebx; char *
0x1800f3e98  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3e9f  mov     edx, 0D5h; void *
0x1800f3ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3ea9  nop
0x1800f3eaa  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f3eaf  call    cs:__imp_VariantClear
0x1800f3eb5  nop
0x1800f3eb6  lea     rcx, [rsp+0C8h+var_88]
0x1800f3ebb  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3ec0  nop
0x1800f3ec1  lea     rcx, [rsp+0C8h+var_38]
0x1800f3ec9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3ece  nop
0x1800f3ecf  lea     rcx, [rsp+0C8h+var_98]
0x1800f3ed4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3ed9  nop
0x1800f3eda  lea     rcx, [rsp+0C8h+var_58]
0x1800f3edf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3ee4  nop
0x1800f3ee5  lea     rcx, [rsp+0C8h+var_90]
0x1800f3eea  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3eef  mov     eax, ebx
0x1800f3ef1  jmp     loc_1800F3FF2
0x1800f3ef6  mov     rdx, qword ptr [rsp+0C8h+pvarg+8]
0x1800f3efb  lea     rcx, [rsp+0C8h+var_58]
0x1800f3f00  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800f3f05  nop
0x1800f3f06  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f3f0b  call    cs:__imp_VariantClear
0x1800f3f11  nop
0x1800f3f12  lea     rcx, [rsp+0C8h+var_88]
0x1800f3f17  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3f1c  nop
0x1800f3f1d  lea     rcx, [rsp+0C8h+var_38]
0x1800f3f25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3f2a  nop
0x1800f3f2b  lea     rcx, [rsp+0C8h+var_98]
0x1800f3f30  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3f35  lea     rcx, [rsp+0C8h+var_58]
0x1800f3f3a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f3f3f  mov     [rsp+0C8h+var_78], rax
0x1800f3f44  lea     rdx, [rsp+0C8h+var_78]
0x1800f3f49  lea     rcx, [rsp+0C8h+var_38]
0x1800f3f51  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800f3f56  mov     rcx, [rax+18h]
0x1800f3f5a  mov     [rsp+0C8h+var_78], rcx
0x1800f3f5f  mov     [rsp+0C8h+var_98], 0
0x1800f3f68  lea     rdx, [rsp+0C8h+var_78]
0x1800f3f6d  lea     rcx, [rsp+0C8h+var_98]
0x1800f3f72  call    ??$MakeAndInitialize@VDevicePreparationExecutionContext@Setup@Management@Windows@@V1234@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAVDevicePreparationExecutionContext@Setup@Management@Windows@@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Management::Setup::DevicePreparationExecutionContext,Windows::Management::Setup::DevicePreparationExecutionContext,HSTRING__ *>(Windows::Management::Setup::DevicePreparationExecutionContext * *,HSTRING__ * &&)
0x1800f3f77  mov     ebx, eax
0x1800f3f79  test    eax, eax
0x1800f3f7b  jns     short loc_1800F3FBD
0x1800f3f7d  mov     rcx, [rsp+0C8h]; this
0x1800f3f85  mov     r9d, eax; char *
0x1800f3f88  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f3f8f  mov     edx, 0DEh; void *
0x1800f3f94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3f99  lea     rcx, [rsp+0C8h+var_98]
0x1800f3f9e  call    ??1?$com_ptr_t@VDevicePreparationExecutionContext@Setup@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>(void)
0x1800f3fa3  nop
0x1800f3fa4  lea     rcx, [rsp+0C8h+var_58]
0x1800f3fa9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3fae  nop
0x1800f3faf  lea     rcx, [rsp+0C8h+var_90]
0x1800f3fb4  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f3fb9  mov     eax, ebx
0x1800f3fbb  jmp     short loc_1800F3FF2
0x1800f3fbd  mov     rdx, [rsp+0C8h+var_98]
0x1800f3fc2  mov     rcx, rsi
0x1800f3fc5  call    ?Set@?$CMarshaledInterfaceResult@UIDevicePreparationExecutionContext@Setup@Management@Windows@@@Internal@Windows@@QEAAJPEAUIDevicePreparationExecutionContext@Setup@Management@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::Management::Setup::IDevicePreparationExecutionContext>::Set(Windows::Management::Setup::IDevicePreparationExecutionContext *)
0x1800f3fca  lea     rcx, [rsp+0C8h+var_98]
0x1800f3fcf  call    ??1?$com_ptr_t@VDevicePreparationExecutionContext@Setup@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>(void)
0x1800f3fd4  nop
0x1800f3fd5  lea     rcx, [rsp+0C8h+var_58]
  ... truncated ...
```
