# _lambda_6ff04c71ed6e183f6414ec44cd1a1a95_::operator()

- ea: `0x1800f6924`
- end: `0x1800f6e96`
- name: `_lambda_6ff04c71ed6e183f6414ec44cd1a1a95_::operator()`
- size: `1394`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f9580`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e43c`
- `0x180077de0`
- `0x180080bac`
- `0x1800829ec`
- `0x180084574`
- `0x180084d5c`
- `0x18008a26c`
- `0x18008d290`
- `0x1800a97b4`
- `0x1800f5ed0`
- `0x1800f6740`
- `0x1800f6924`
- `0x1800f97d4`
- `0x1801a4494`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6a63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f6a63`
- `OLEAUT32!__imp_VariantInit` at `0x1800f6c5a`
- `OLEAUT32!__imp_VariantInit` at `0x1800f6c5a`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6ca5`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6d21`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6d83`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6ca5`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6d21`
- `OLEAUT32!__imp_VariantClear` at `0x1800f6d83`

## string_xrefs

- `0x1800f6980`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\AgileHelpers.h`
- `0x1800f699c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6a0e`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6a80`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6b35`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6bb9`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6c8e`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6d0a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6e06`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\machineprovisioningprogressreporter.cpp`
- `0x1800f6ab9`: `./Device/Vendor/MSFT/DevicePreparation/BootstrapperAgent/ExecutionContext`

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
0x1800f6924  mov     [rsp+arg_10], rbx
0x1800f6929  mov     [rsp+arg_18], rsi
0x1800f692e  push    rdi
0x1800f692f  sub     rsp, 0C0h
0x1800f6936  mov     rax, cs:__security_cookie
0x1800f693d  xor     rax, rsp
0x1800f6940  mov     [rsp+0C8h+var_18], rax
0x1800f6948  mov     rsi, rdx
0x1800f694b  mov     [rsp+0C8h+var_90], 0
0x1800f6954  mov     rcx, [rcx]
0x1800f6957  mov     rax, [rcx]
0x1800f695a  lea     r8, [rsp+0C8h+var_90]
0x1800f695f  lea     rdx, _GUID_ebd8677f_dfd2_59da_ac3d_753ee1667cbb
0x1800f6966  mov     rax, [rax+18h]
0x1800f696a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f696f  mov     ebx, eax
0x1800f6971  test    eax, eax
0x1800f6973  jns     short loc_1800F69BF
0x1800f6975  mov     rcx, [rsp+0C8h]; this
0x1800f697d  mov     r9d, eax; char *
0x1800f6980  lea     r8, aOnecoreuapAdmi_53; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6987  mov     edx, 37h ; '7'; void *
0x1800f698c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6991  mov     rcx, [rsp+0C8h]; this
0x1800f6999  mov     r9d, ebx; char *
0x1800f699c  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f69a3  mov     edx, 0B9h; void *
0x1800f69a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f69ad  nop
0x1800f69ae  lea     rcx, [rsp+0C8h+var_90]
0x1800f69b3  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f69b8  mov     eax, ebx
0x1800f69ba  jmp     loc_1800F6E70
0x1800f69bf  xorps   xmm0, xmm0
0x1800f69c2  movups  [rsp+0C8h+var_58], xmm0
0x1800f69c7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800f69cf  movdqu  [rsp+0C8h+var_48], xmm1
0x1800f69d8  xor     eax, eax
0x1800f69da  mov     word ptr [rsp+0C8h+var_58], ax
0x1800f69df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppResilience>::GetImpl(void)'::`2'::impl
0x1800f69e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppResilience@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppResilience>::__private_IsEnabled(void)
0x1800f69eb  test    al, al
0x1800f69ed  jz      short loc_1800F6A3C
0x1800f69ef  lea     rcx, [rsp+0C8h+var_58]
0x1800f69f4  call    ?GetContext@DppContextUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DppContextUtils::GetContext(std::wstring &)
0x1800f69f9  mov     ebx, eax
0x1800f69fb  test    eax, eax
0x1800f69fd  jns     loc_1800F6DB3
0x1800f6a03  mov     rcx, [rsp+0C8h]; this
0x1800f6a0b  mov     r9d, eax; char *
0x1800f6a0e  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6a15  mov     edx, 0BEh; void *
0x1800f6a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6a1f  nop
0x1800f6a20  lea     rcx, [rsp+0C8h+var_58]
0x1800f6a25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6a2a  nop
0x1800f6a2b  lea     rcx, [rsp+0C8h+var_90]
0x1800f6a30  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6a35  mov     eax, ebx
0x1800f6a37  jmp     loc_1800F6E70
0x1800f6a3c  mov     [rsp+0C8h+var_98], 0
0x1800f6a45  lea     rax, [rsp+0C8h+var_98]
0x1800f6a4a  mov     qword ptr [rsp+0C8h+ppv], rax; int
0x1800f6a4f  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800f6a56  xor     edx, edx; pUnkOuter
0x1800f6a58  lea     r8d, [rdx+1]; dwClsContext
0x1800f6a5c  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800f6a63  call    cs:__imp_CoCreateInstance
0x1800f6a6a  nop     dword ptr [rax+rax+00h]
0x1800f6a6f  mov     ebx, eax
0x1800f6a71  test    eax, eax
0x1800f6a73  jns     short loc_1800F6AB9
0x1800f6a75  mov     rcx, [rsp+0C8h]; this
0x1800f6a7d  mov     r9d, eax; char *
0x1800f6a80  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6a87  mov     edx, 0C4h; void *
0x1800f6a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6a91  nop
0x1800f6a92  lea     rcx, [rsp+0C8h+var_98]
0x1800f6a97  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6a9c  nop
0x1800f6a9d  lea     rcx, [rsp+0C8h+var_58]
0x1800f6aa2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6aa7  nop
0x1800f6aa8  lea     rcx, [rsp+0C8h+var_90]
0x1800f6aad  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6ab2  mov     eax, ebx
0x1800f6ab4  jmp     loc_1800F6E70
0x1800f6ab9  lea     rdx, aDeviceVendorMs; "./Device/Vendor/MSFT/DevicePreparation/"...
0x1800f6ac0  lea     rcx, [rsp+0C8h+var_38]
0x1800f6ac8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f6acd  nop
0x1800f6ace  mov     [rsp+0C8h+var_88], 0
0x1800f6ad7  mov     rbx, [rsp+0C8h+var_98]
0x1800f6adc  mov     rax, [rbx]
0x1800f6adf  mov     rdi, [rax+50h]
0x1800f6ae3  mov     [rsp+0C8h+var_88], 0
0x1800f6aec  lea     rcx, [rsp+0C8h+var_38]
0x1800f6af4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f6af9  mov     rdx, rax
0x1800f6afc  lea     rcx, [rsp+0C8h+var_78]
0x1800f6b01  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800f6b06  nop
0x1800f6b07  lea     r8, [rsp+0C8h+var_88]
0x1800f6b0c  mov     rdx, [rax]
0x1800f6b0f  mov     rcx, rbx
0x1800f6b12  mov     rax, rdi
0x1800f6b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b1a  mov     ebx, eax
0x1800f6b1c  lea     rcx, [rsp+0C8h+var_78]
0x1800f6b21  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f6b26  test    ebx, ebx
0x1800f6b28  jns     short loc_1800F6B87
0x1800f6b2a  mov     rcx, [rsp+0C8h]; this
0x1800f6b32  mov     r9d, ebx; char *
0x1800f6b35  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6b3c  mov     edx, 0C9h; void *
0x1800f6b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6b46  nop
0x1800f6b47  lea     rcx, [rsp+0C8h+var_88]
0x1800f6b4c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6b51  nop
0x1800f6b52  lea     rcx, [rsp+0C8h+var_38]
0x1800f6b5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6b5f  nop
0x1800f6b60  lea     rcx, [rsp+0C8h+var_98]
0x1800f6b65  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6b6a  nop
0x1800f6b6b  lea     rcx, [rsp+0C8h+var_58]
0x1800f6b70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6b75  nop
0x1800f6b76  lea     rcx, [rsp+0C8h+var_90]
0x1800f6b7b  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6b80  mov     eax, ebx
0x1800f6b82  jmp     loc_1800F6E70
0x1800f6b87  mov     [rsp+0C8h+var_80], 0
0x1800f6b8f  mov     rcx, [rsp+0C8h+var_88]
0x1800f6b94  mov     rax, [rcx]
0x1800f6b97  lea     rdx, [rsp+0C8h+var_80]
0x1800f6b9c  mov     rax, [rax+0E0h]
0x1800f6ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6ba8  mov     ebx, eax
0x1800f6baa  test    eax, eax
0x1800f6bac  jns     short loc_1800F6C0B
0x1800f6bae  mov     rcx, [rsp+0C8h]; this
0x1800f6bb6  mov     r9d, eax; char *
0x1800f6bb9  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6bc0  mov     edx, 0CCh; void *
0x1800f6bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6bca  nop
0x1800f6bcb  lea     rcx, [rsp+0C8h+var_88]
0x1800f6bd0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6bd5  nop
0x1800f6bd6  lea     rcx, [rsp+0C8h+var_38]
0x1800f6bde  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6be3  nop
0x1800f6be4  lea     rcx, [rsp+0C8h+var_98]
0x1800f6be9  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6bee  nop
0x1800f6bef  lea     rcx, [rsp+0C8h+var_58]
0x1800f6bf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6bf9  nop
0x1800f6bfa  lea     rcx, [rsp+0C8h+var_90]
0x1800f6bff  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6c04  mov     eax, ebx
0x1800f6c06  jmp     loc_1800F6E70
0x1800f6c0b  cmp     [rsp+0C8h+var_80], 0
0x1800f6c10  jnz     short loc_1800F6C55
0x1800f6c12  lea     rcx, [rsp+0C8h+var_88]
0x1800f6c17  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6c1c  nop
0x1800f6c1d  lea     rcx, [rsp+0C8h+var_38]
0x1800f6c25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6c2a  nop
0x1800f6c2b  lea     rcx, [rsp+0C8h+var_98]
0x1800f6c30  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6c35  nop
0x1800f6c36  lea     rcx, [rsp+0C8h+var_58]
0x1800f6c3b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6c40  nop
0x1800f6c41  lea     rcx, [rsp+0C8h+var_90]
0x1800f6c46  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6c4b  mov     eax, 80070490h
0x1800f6c50  jmp     loc_1800F6E70
0x1800f6c55  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f6c5a  call    cs:__imp_VariantInit
0x1800f6c61  nop     dword ptr [rax+rax+00h]
0x1800f6c66  nop
0x1800f6c67  mov     rcx, [rsp+0C8h+var_88]
0x1800f6c6c  mov     rax, [rcx]
0x1800f6c6f  lea     rdx, [rsp+0C8h+pvarg]
0x1800f6c74  mov     rax, [rax+68h]
0x1800f6c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6c7d  mov     ebx, eax
0x1800f6c7f  test    eax, eax
0x1800f6c81  jns     short loc_1800F6CF2
0x1800f6c83  mov     rcx, [rsp+0C8h]; this
0x1800f6c8b  mov     r9d, eax; char *
0x1800f6c8e  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6c95  mov     edx, 0D4h; void *
0x1800f6c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6c9f  nop
0x1800f6ca0  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f6ca5  call    cs:__imp_VariantClear
0x1800f6cac  nop     dword ptr [rax+rax+00h]
0x1800f6cb1  nop
0x1800f6cb2  lea     rcx, [rsp+0C8h+var_88]
0x1800f6cb7  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6cbc  nop
0x1800f6cbd  lea     rcx, [rsp+0C8h+var_38]
0x1800f6cc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6cca  nop
0x1800f6ccb  lea     rcx, [rsp+0C8h+var_98]
0x1800f6cd0  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6cd5  nop
0x1800f6cd6  lea     rcx, [rsp+0C8h+var_58]
0x1800f6cdb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6ce0  nop
0x1800f6ce1  lea     rcx, [rsp+0C8h+var_90]
0x1800f6ce6  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6ceb  mov     eax, ebx
0x1800f6ced  jmp     loc_1800F6E70
0x1800f6cf2  cmp     word ptr [rsp+0C8h+pvarg], 8
0x1800f6cf8  jz      short loc_1800F6D6E
0x1800f6cfa  mov     rcx, [rsp+0C8h]; this
0x1800f6d02  mov     ebx, 8000FFFFh
0x1800f6d07  mov     r9d, ebx; char *
0x1800f6d0a  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6d11  mov     edx, 0D5h; void *
0x1800f6d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6d1b  nop
0x1800f6d1c  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f6d21  call    cs:__imp_VariantClear
0x1800f6d28  nop     dword ptr [rax+rax+00h]
0x1800f6d2d  nop
0x1800f6d2e  lea     rcx, [rsp+0C8h+var_88]
0x1800f6d33  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6d38  nop
0x1800f6d39  lea     rcx, [rsp+0C8h+var_38]
0x1800f6d41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6d46  nop
0x1800f6d47  lea     rcx, [rsp+0C8h+var_98]
0x1800f6d4c  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6d51  nop
0x1800f6d52  lea     rcx, [rsp+0C8h+var_58]
0x1800f6d57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6d5c  nop
0x1800f6d5d  lea     rcx, [rsp+0C8h+var_90]
0x1800f6d62  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6d67  mov     eax, ebx
0x1800f6d69  jmp     loc_1800F6E70
0x1800f6d6e  mov     rdx, qword ptr [rsp+0C8h+pvarg+8]
0x1800f6d73  lea     rcx, [rsp+0C8h+var_58]
0x1800f6d78  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800f6d7d  nop
0x1800f6d7e  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1800f6d83  call    cs:__imp_VariantClear
0x1800f6d8a  nop     dword ptr [rax+rax+00h]
0x1800f6d8f  nop
0x1800f6d90  lea     rcx, [rsp+0C8h+var_88]
0x1800f6d95  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6d9a  nop
0x1800f6d9b  lea     rcx, [rsp+0C8h+var_38]
0x1800f6da3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6da8  nop
0x1800f6da9  lea     rcx, [rsp+0C8h+var_98]
0x1800f6dae  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6db3  lea     rcx, [rsp+0C8h+var_58]
0x1800f6db8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f6dbd  mov     [rsp+0C8h+var_78], rax
0x1800f6dc2  lea     rdx, [rsp+0C8h+var_78]
0x1800f6dc7  lea     rcx, [rsp+0C8h+var_38]
0x1800f6dcf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800f6dd4  mov     rcx, [rax+18h]
0x1800f6dd8  mov     [rsp+0C8h+var_78], rcx
0x1800f6ddd  mov     [rsp+0C8h+var_98], 0
0x1800f6de6  lea     rdx, [rsp+0C8h+var_78]
0x1800f6deb  lea     rcx, [rsp+0C8h+var_98]
0x1800f6df0  call    ??$MakeAndInitialize@VDevicePreparationExecutionContext@Setup@Management@Windows@@V1234@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAVDevicePreparationExecutionContext@Setup@Management@Windows@@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Management::Setup::DevicePreparationExecutionContext,Windows::Management::Setup::DevicePreparationExecutionContext,HSTRING__ *>(Windows::Management::Setup::DevicePreparationExecutionContext * *,HSTRING__ * &&)
0x1800f6df5  mov     ebx, eax
0x1800f6df7  test    eax, eax
0x1800f6df9  jns     short loc_1800F6E3B
0x1800f6dfb  mov     rcx, [rsp+0C8h]; this
0x1800f6e03  mov     r9d, eax; char *
0x1800f6e06  lea     r8, aOnecoreuapAdmi_90; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800f6e0d  mov     edx, 0DEh; void *
0x1800f6e12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6e17  lea     rcx, [rsp+0C8h+var_98]
0x1800f6e1c  call    ??1?$com_ptr_t@VDevicePreparationExecutionContext@Setup@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Setup::DevicePreparationExecutionContext,wil::err_exception_policy>(void)
0x1800f6e21  nop
0x1800f6e22  lea     rcx, [rsp+0C8h+var_58]
0x1800f6e27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f6e2c  nop
0x1800f6e2d  lea     rcx, [rsp+0C8h+var_90]
0x1800f6e32  call    ??1?$com_ptr_t@UIDeploymentSessionHeartbeatRequested@Setup@Management@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>::~com_ptr_t<Windows::Management::Setup::IDeploymentSessionHeartbeatRequested,wil::err_returncode_policy>(void)
0x1800f6e37  mov     eax, ebx
0x1800f6e39  jmp     short loc_1800F6E70
0x1800f6e3b  mov     rdx, [rsp+0C8h+var_98]
0x1800f6e40  mov     rcx, rsi
  ... truncated ...
```
