# CFlightSettingsClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180017e90`
- end: `0x180018454`
- name: `?CreateInstance@CFlightSettingsClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1476`
- prototype: `int(CFlightSettingsClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009758`
- `0x18000a2f4`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x1800179c4`
- `0x180017dd8`
- `0x180017e90`
- `0x1800186fc`
- `0x180018784`
- `0x180018984`
- `0x180018a60`
- `0x1800794b0`
- `0x18007a0b4`
- `0x18007a864`
- `0x1800807bc`
- `0x180082dec`
- `0x180083ff4`
- `0x180085470`
- `0x18008d154`
- `0x180091fe0`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800181e8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800181e8`

## string_xrefs

- `0x180017ec4`: `onecore\base\flighting\flightsettings\broker\dll\flightsettingsclassfactory.cpp`
- `0x180018321`: `onecore\base\flighting\flightsettings\broker\dll\flightsettingsclassfactory.cpp`
- `0x18001837c`: `onecore\base\flighting\flightsettings\broker\dll\flightsettingsclassfactory.cpp`
- `0x180018428`: `onecore\base\flighting\flightsettings\broker\dll\flightsettingsclassfactory.cpp`
- `0x180017f6a`: `onecore\base\flighting\flightsettings\broker\libs\experimentationbroker\experimentationbroker.cpp`
- `0x180017fc8`: `onecore\base\flighting\flightsettings\broker\libs\onesettingsbroker\onesettingsbroker.cpp`
- `0x180018026`: `onecore\base\flighting\flightsettings\broker\libs\featureusagelistener\featureusagelistener.cpp`
- `0x180018084`: `onecore\base\flighting\flightsettings\broker\libs\smartfeaturerolloutbroker\smartfeaturerolloutbroker.cpp`
- `0x1800180e2`: `onecore\base\flighting\flightsettings\broker\libs\smartfeaturetuningbroker\smartfeaturetuningbroker.cpp`
- `0x180018140`: `onecore\base\flighting\flightsettings\broker\libs\undockedflightingbroker\undockedflightingbroker.cpp`
- `0x1800181ae`: `onecore\base\flighting\flightsettings\broker\libs\flagconfigurationbroker\flagconfigurationbroker.cpp`
- `0x1800182d9`: `onecore\base\flighting\flightsettings\broker\lib\fsreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFlightSettingsClassFactory::CreateInstance(
        unsigned __int64 this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  FlightSettingsAPITelemetryClass *v9; // rax
  unsigned __int64 v10; // rcx
  struct IClientObjectStubManager *v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // r9
  int v22; // eax
  void *v23; // rbx
  __int64 (__fastcall *v24)(void *, GUID *, int *); // rdi
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 v28; // rdx
  _QWORD *v29; // rdx
  int v30; // eax
  int v32[4]; // [rsp+20h] [rbp-20h] BYREF
  struct _GUID v33; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v35; // [rsp+78h] [rbp+38h] BYREF
  void *v36; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  if ( !a2 )
  {
    if ( FlightSettingsAPITelemetryClass::IsEnabled(this, 0) )
    {
      v9 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                v8,
                                                _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      v33 = *a3;
      FlightSettingsAPITelemetryClass::ClassFactoryCreateInstance_(v9, *(_BYTE *)(this + 24), &v33);
    }
    v36 = 0;
    v10 = this & -(__int64)(*(_BYTE *)(this + 24) != 0);
    v11 = (struct IClientObjectStubManager *)((v10 + 8) & -(__int64)(v10 != 0));
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_ExperimentationBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_ExperimentationBroker.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v12 = ExperimentationBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\experimentationbroker\\experimentationbroker.cpp",
          (const char *)(unsigned int)v12,
          v32[0]);
        v13 = 43;
LABEL_69:
        v21 = v7;
        goto LABEL_70;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_OneSettingsBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_OneSettingsBroker.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v14 = OneSettingsBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7C,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\onesettingsbroker\\onesettingsbroker.cpp",
          (const char *)(unsigned int)v14,
          v32[0]);
        v13 = 47;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_FeatureUsageListener.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_FeatureUsageListener.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v15 = FeatureUsageListener::s_CreateInstance(a3, &v36, v11);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\featureusagelistener\\featureusagelistener.cpp",
          (const char *)(unsigned int)v15,
          v32[0]);
        v13 = 51;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_SmartFeatureRolloutBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_SmartFeatureRolloutBroker.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v16 = SmartFeatureRolloutBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\smartfeaturerolloutbroker\\smartfeaturer"
                        "olloutbroker.cpp",
          (const char *)(unsigned int)v16,
          v32[0]);
        v13 = 55;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_SmartFeatureTuningBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_SmartFeatureTuningBroker.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v17 = SmartFeatureTuningBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\smartfeaturetuningbroker\\smartfeaturetuningbroker.cpp",
          (const char *)(unsigned int)v17,
          v32[0]);
        v13 = 59;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_UndockedFlightingBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_UndockedFlightingBroker.Data4 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v18 = UndockedFlightingBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA1,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\undockedflightingbroker\\undockedflightingbroker.cpp",
          (const char *)(unsigned int)v18,
          v32[0]);
        v13 = 63;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    if ( *(_QWORD *)(this + 28) == *(_QWORD *)&CLSID_FlagConfigurationBroker.Data1
      && *(_QWORD *)(this + 36) == *(_QWORD *)CLSID_FlagConfigurationBroker.Data4 )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker>::GetImpl'::`2'::impl) )
      {
        v7 = -2147024891;
        v13 = 73;
        goto LABEL_69;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v19 = FlagConfigurationBroker::s_CreateInstance(a3, &v36, v11);
      v7 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\flagconfigurationbroker\\flagconfigurationbroker.cpp",
          (const char *)(unsigned int)v19,
          v32[0]);
        v13 = 69;
        goto LABEL_69;
      }
      goto LABEL_51;
    }
    v35 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v35, 0);
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFlightSettingsValidator.Data1
      && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IFlightSettingsValidator.Data4
      || *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFlightSettingsWriter.Data1
      && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IFlightSettingsWriter.Data4 )
    {
      if ( (unsigned int)GetEffectiveFlightSettingsVersion() != 2 && v35 == 3 )
      {
        v13 = 95;
LABEL_68:
        v7 = -2147467262;
        goto LABEL_69;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v20 = FlightSettingsActionManager_CreateInstance(a3, &v36, v11);
      v7 = v20;
      if ( v20 < 0 )
      {
        v21 = (unsigned int)v20;
        v13 = 91;
        goto LABEL_70;
      }
    }
    else
    {
      if ( (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IFlightSettingsAPIBroker.Data1
         || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IFlightSettingsAPIBroker.Data4)
        && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1
         || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4) )
      {
        v13 = 116;
        goto LABEL_68;
      }
      if ( (unsigned int)GetEffectiveFlightSettingsAPIVersion(v35) != 2 )
      {
        v13 = 111;
        goto LABEL_68;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v22 = FlightSettingsReader::s_CreateInstance(a3, &v36, v11);
      v7 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A7,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fsreader.cpp",
          (const char *)(unsigned int)v22,
          v32[0]);
        v13 = 107;
        goto LABEL_69;
      }
    }
LABEL_51:
    if ( v11 )
    {
      SvcAddRef();
      wil::EnterCriticalSection(&v33, this + 48);
      if ( *(_BYTE *)(this + 120) )
      {
        v7 = -2147483622;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\flightsettingsclassfactory.cpp",
          (const char *)0x8000001ALL,
          v32[0]);
LABEL_54:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
LABEL_71:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
        return v7;
      }
      *(_QWORD *)v32 = 0;
      v23 = v36;
      v24 = **(__int64 (__fastcall ***)(void *, GUID *, int *))v36;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v32);
      v25 = v24(v23, &GUID_00000000_0000_0000_c000_000000000046, v32);
      v7 = v25;
      if ( v25 < 0 )
      {
        v26 = 135;
LABEL_57:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\flightsettingsclassfactory.cpp",
          (const char *)(unsigned int)v25,
          v32[0]);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v32);
        goto LABEL_54;
      }
      v27 = *(_QWORD *)v32;
      v28 = *(_QWORD *)(this + 96);
      if ( v28 == *(_QWORD *)(this + 112) )
      {
        v25 = CTSimpleArray<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<_FLIGHT_CALLBACK_CONTEXT,wistd::default_delete<_FLIGHT_CALLBACK_CONTEXT>>>>::_EnsureCapacity(
                this + 88,
                v28 + 1);
        v7 = v25;
        if ( v25 < 0 )
        {
          v26 = 136;
          goto LABEL_57;
        }
      }
      v29 = (_QWORD *)(*(_QWORD *)(this + 88) + 8 * (*(_QWORD *)(this + 96))++);
      if ( v29 )
        *v29 = v27;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v32);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
    }
    v30 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v36)(v36, a3, a4);
    v7 = v30;
    if ( v30 >= 0 )
      goto LABEL_71;
    v21 = (unsigned int)v30;
    v13 = 139;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\flightsettingsclassfactory.cpp",
      (const char *)v21,
      v32[0]);
    goto LABEL_71;
  }
  v7 = -2147221232;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\flightsettingsclassfactory.cpp",
    (const char *)0x80040110LL,
    v32[0]);
  return v7;
}

```

## disassembly

```asm
0x180017e90  mov     [rsp-28h+arg_0], rbx
0x180017e95  push    rbp
0x180017e96  push    rsi
0x180017e97  push    rdi
0x180017e98  push    r14
0x180017e9a  push    r15
0x180017e9c  mov     rbp, rsp
0x180017e9f  sub     rsp, 40h
0x180017ea3  mov     r15, r9
0x180017ea6  mov     r14, r8
0x180017ea9  mov     rsi, rcx
0x180017eac  mov     qword ptr [r9], 0
0x180017eb3  test    rdx, rdx
0x180017eb6  jz      short loc_180017EDA
0x180017eb8  mov     rcx, [rbp+28h]; this
0x180017ebc  mov     ebx, 80040110h
0x180017ec1  mov     r9d, ebx; char *
0x180017ec4  lea     r8, aOnecoreBaseFli_75; "onecore\\base\\flighting\\flightsetting"...
0x180017ecb  mov     edx, 21h ; '!'; void *
0x180017ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ed5  jmp     loc_180018441
0x180017eda  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x180017edf  test    al, al
0x180017ee1  jz      short loc_180017F07
0x180017ee3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180017eea  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180017eef  movups  xmm0, xmmword ptr [r14]
0x180017ef3  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180017ef8  lea     r8, [rbp+var_10]; struct _GUID
0x180017efc  mov     dl, [rsi+18h]; bool
0x180017eff  mov     rcx, rax; this
0x180017f02  call    ?ClassFactoryCreateInstance_@FlightSettingsAPITelemetryClass@@QEAAX_NU_GUID@@@Z; FlightSettingsAPITelemetryClass::ClassFactoryCreateInstance_(bool,_GUID)
0x180017f07  mov     [rbp+arg_18], 0
0x180017f0f  mov     al, [rsi+18h]
0x180017f12  neg     al
0x180017f14  sbb     rcx, rcx
0x180017f17  and     rcx, rsi
0x180017f1a  lea     rax, [rcx+8]
0x180017f1e  neg     rcx
0x180017f21  sbb     rdi, rdi
0x180017f24  and     rdi, rax
0x180017f27  mov     rax, [rsi+1Ch]
0x180017f2b  cmp     rax, qword ptr cs:CLSID_ExperimentationBroker.Data1
0x180017f32  jnz     short loc_180017F85
0x180017f34  mov     rax, [rsi+24h]
0x180017f38  cmp     rax, qword ptr cs:CLSID_ExperimentationBroker.Data4
0x180017f3f  jnz     short loc_180017F85
0x180017f41  lea     rcx, [rbp+arg_18]
0x180017f45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017f4a  mov     r8, rdi; struct IClientObjectStubManager *
0x180017f4d  lea     rdx, [rbp+arg_18]; void **
0x180017f51  mov     rcx, r14; struct _GUID *
0x180017f54  call    ?s_CreateInstance@ExperimentationBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; ExperimentationBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180017f59  mov     ebx, eax
0x180017f5b  test    eax, eax
0x180017f5d  jns     loc_1800182F4
0x180017f63  mov     rcx, [rbp+28h]; this
0x180017f67  mov     r9d, eax; char *
0x180017f6a  lea     r8, aOnecoreBaseFli_59; "onecore\\base\\flighting\\flightsetting"...
0x180017f71  mov     edx, 0FDh; void *
0x180017f76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f7b  mov     edx, 2Bh ; '+'
0x180017f80  jmp     loc_180018425
0x180017f85  mov     rax, [rsi+1Ch]
0x180017f89  cmp     rax, qword ptr cs:CLSID_OneSettingsBroker.Data1
0x180017f90  jnz     short loc_180017FE3
0x180017f92  mov     rax, [rsi+24h]
0x180017f96  cmp     rax, qword ptr cs:CLSID_OneSettingsBroker.Data4
0x180017f9d  jnz     short loc_180017FE3
0x180017f9f  lea     rcx, [rbp+arg_18]
0x180017fa3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017fa8  mov     r8, rdi; struct IClientObjectStubManager *
0x180017fab  lea     rdx, [rbp+arg_18]; void **
0x180017faf  mov     rcx, r14; struct _GUID *
0x180017fb2  call    ?s_CreateInstance@OneSettingsBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; OneSettingsBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180017fb7  mov     ebx, eax
0x180017fb9  test    eax, eax
0x180017fbb  jns     loc_1800182F4
0x180017fc1  mov     rcx, [rbp+28h]; this
0x180017fc5  mov     r9d, eax; char *
0x180017fc8  lea     r8, aOnecoreBaseFli_22; "onecore\\base\\flighting\\flightsetting"...
0x180017fcf  mov     edx, 7Ch ; '|'; void *
0x180017fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fd9  mov     edx, 2Fh ; '/'
0x180017fde  jmp     loc_180018425
0x180017fe3  mov     rax, [rsi+1Ch]
0x180017fe7  cmp     rax, qword ptr cs:CLSID_FeatureUsageListener.Data1
0x180017fee  jnz     short loc_180018041
0x180017ff0  mov     rax, [rsi+24h]
0x180017ff4  cmp     rax, qword ptr cs:CLSID_FeatureUsageListener.Data4
0x180017ffb  jnz     short loc_180018041
0x180017ffd  lea     rcx, [rbp+arg_18]
0x180018001  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018006  mov     r8, rdi; struct IClientObjectStubManager *
0x180018009  lea     rdx, [rbp+arg_18]; void **
0x18001800d  mov     rcx, r14; struct _GUID *
0x180018010  call    ?s_CreateInstance@FeatureUsageListener@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; FeatureUsageListener::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180018015  mov     ebx, eax
0x180018017  test    eax, eax
0x180018019  jns     loc_1800182F4
0x18001801f  mov     rcx, [rbp+28h]; this
0x180018023  mov     r9d, eax; char *
0x180018026  lea     r8, aOnecoreBaseFli_85; "onecore\\base\\flighting\\flightsetting"...
0x18001802d  mov     edx, 56h ; 'V'; void *
0x180018032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018037  mov     edx, 33h ; '3'
0x18001803c  jmp     loc_180018425
0x180018041  mov     rax, [rsi+1Ch]
0x180018045  cmp     rax, qword ptr cs:CLSID_SmartFeatureRolloutBroker.Data1
0x18001804c  jnz     short loc_18001809F
0x18001804e  mov     rax, [rsi+24h]
0x180018052  cmp     rax, qword ptr cs:CLSID_SmartFeatureRolloutBroker.Data4
0x180018059  jnz     short loc_18001809F
0x18001805b  lea     rcx, [rbp+arg_18]
0x18001805f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018064  mov     r8, rdi; struct IClientObjectStubManager *
0x180018067  lea     rdx, [rbp+arg_18]; void **
0x18001806b  mov     rcx, r14; struct _GUID *
0x18001806e  call    ?s_CreateInstance@SmartFeatureRolloutBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; SmartFeatureRolloutBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180018073  mov     ebx, eax
0x180018075  test    eax, eax
0x180018077  jns     loc_1800182F4
0x18001807d  mov     rcx, [rbp+28h]; this
0x180018081  mov     r9d, eax; char *
0x180018084  lea     r8, aOnecoreBaseFli_4; "onecore\\base\\flighting\\flightsetting"...
0x18001808b  mov     edx, 7Bh ; '{'; void *
0x180018090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018095  mov     edx, 37h ; '7'
0x18001809a  jmp     loc_180018425
0x18001809f  mov     rax, [rsi+1Ch]
0x1800180a3  cmp     rax, qword ptr cs:CLSID_SmartFeatureTuningBroker.Data1
0x1800180aa  jnz     short loc_1800180FD
0x1800180ac  mov     rax, [rsi+24h]
0x1800180b0  cmp     rax, qword ptr cs:CLSID_SmartFeatureTuningBroker.Data4
0x1800180b7  jnz     short loc_1800180FD
0x1800180b9  lea     rcx, [rbp+arg_18]
0x1800180bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800180c2  mov     r8, rdi; struct IClientObjectStubManager *
0x1800180c5  lea     rdx, [rbp+arg_18]; void **
0x1800180c9  mov     rcx, r14; struct _GUID *
0x1800180cc  call    ?s_CreateInstance@SmartFeatureTuningBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; SmartFeatureTuningBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x1800180d1  mov     ebx, eax
0x1800180d3  test    eax, eax
0x1800180d5  jns     loc_1800182F4
0x1800180db  mov     rcx, [rbp+28h]; this
0x1800180df  mov     r9d, eax; char *
0x1800180e2  lea     r8, aOnecoreBaseFli_11; "onecore\\base\\flighting\\flightsetting"...
0x1800180e9  mov     edx, 58h ; 'X'; void *
0x1800180ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800180f3  mov     edx, 3Bh ; ';'
0x1800180f8  jmp     loc_180018425
0x1800180fd  mov     rax, [rsi+1Ch]
0x180018101  cmp     rax, qword ptr cs:CLSID_UndockedFlightingBroker.Data1
0x180018108  jnz     short loc_18001815B
0x18001810a  mov     rax, [rsi+24h]
0x18001810e  cmp     rax, qword ptr cs:CLSID_UndockedFlightingBroker.Data4
0x180018115  jnz     short loc_18001815B
0x180018117  lea     rcx, [rbp+arg_18]
0x18001811b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018120  mov     r8, rdi; struct IClientObjectStubManager *
0x180018123  lea     rdx, [rbp+arg_18]; void **
0x180018127  mov     rcx, r14; struct _GUID *
0x18001812a  call    ?s_CreateInstance@UndockedFlightingBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; UndockedFlightingBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x18001812f  mov     ebx, eax
0x180018131  test    eax, eax
0x180018133  jns     loc_1800182F4
0x180018139  mov     rcx, [rbp+28h]; this
0x18001813d  mov     r9d, eax; char *
0x180018140  lea     r8, aOnecoreBaseFli_79; "onecore\\base\\flighting\\flightsetting"...
0x180018147  mov     edx, 0A1h; void *
0x18001814c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018151  mov     edx, 3Fh ; '?'
0x180018156  jmp     loc_180018425
0x18001815b  mov     rax, [rsi+1Ch]
0x18001815f  cmp     rax, qword ptr cs:CLSID_FlagConfigurationBroker.Data1
0x180018166  jnz     short loc_1800181D8
0x180018168  mov     rax, [rsi+24h]
0x18001816c  cmp     rax, qword ptr cs:CLSID_FlagConfigurationBroker.Data4
0x180018173  jnz     short loc_1800181D8
0x180018175  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker>::GetImpl(void)'::`2'::impl
0x18001817c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_Broker>::__private_IsEnabled(void)
0x180018181  test    al, al
0x180018183  jz      short loc_1800181C9
0x180018185  lea     rcx, [rbp+arg_18]
0x180018189  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001818e  mov     r8, rdi; struct IClientObjectStubManager *
0x180018191  lea     rdx, [rbp+arg_18]; void **
0x180018195  mov     rcx, r14; struct _GUID *
0x180018198  call    ?s_CreateInstance@FlagConfigurationBroker@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; FlagConfigurationBroker::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x18001819d  mov     ebx, eax
0x18001819f  test    eax, eax
0x1800181a1  jns     loc_1800182F4
0x1800181a7  mov     rcx, [rbp+28h]; this
0x1800181ab  mov     r9d, eax; char *
0x1800181ae  lea     r8, aOnecoreBaseFli_100; "onecore\\base\\flighting\\flightsetting"...
0x1800181b5  mov     edx, 0D8h; void *
0x1800181ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181bf  mov     edx, 45h ; 'E'
0x1800181c4  jmp     loc_180018425
0x1800181c9  mov     ebx, 80070005h
0x1800181ce  mov     edx, 49h ; 'I'
0x1800181d3  jmp     loc_180018425
0x1800181d8  mov     [rbp+arg_8], 0
0x1800181df  xor     r8d, r8d
0x1800181e2  lea     rdx, [rbp+arg_8]
0x1800181e6  xor     ecx, ecx
0x1800181e8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800181ee  mov     rax, [r14]
0x1800181f1  cmp     rax, qword ptr cs:IID_IFlightSettingsValidator.Data1
0x1800181f8  jnz     short loc_180018207
0x1800181fa  mov     rax, [r14+8]
0x1800181fe  cmp     rax, qword ptr cs:IID_IFlightSettingsValidator.Data4
0x180018205  jz      short loc_180018220
0x180018207  mov     rax, [r14]
0x18001820a  cmp     rax, qword ptr cs:IID_IFlightSettingsWriter.Data1
0x180018211  jnz     short loc_180018269
0x180018213  mov     rax, [r14+8]
0x180018217  cmp     rax, qword ptr cs:IID_IFlightSettingsWriter.Data4
0x18001821e  jnz     short loc_180018269
0x180018220  call    ?GetEffectiveFlightSettingsVersion@@YA?AW4FlightSettingsVersion@@XZ; GetEffectiveFlightSettingsVersion(void)
0x180018225  cmp     eax, 2
0x180018228  jz      short loc_18001823A
0x18001822a  cmp     [rbp+arg_8], 3
0x18001822e  jnz     short loc_18001823A
0x180018230  mov     edx, 5Fh ; '_'
0x180018235  jmp     loc_180018420
0x18001823a  lea     rcx, [rbp+arg_18]
0x18001823e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018243  mov     r8, rdi; struct IClientObjectStubManager *
0x180018246  lea     rdx, [rbp+arg_18]; void **
0x18001824a  mov     rcx, r14; struct _GUID *
0x18001824d  call    ?FlightSettingsActionManager_CreateInstance@@YAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; FlightSettingsActionManager_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x180018252  mov     ebx, eax
0x180018254  test    eax, eax
0x180018256  jns     loc_1800182F4
0x18001825c  mov     r9d, eax
0x18001825f  mov     edx, 5Bh ; '['
0x180018264  jmp     loc_180018428
0x180018269  mov     rax, [r14]
0x18001826c  cmp     rax, qword ptr cs:IID_IFlightSettingsAPIBroker.Data1
0x180018273  jnz     short loc_180018282
0x180018275  mov     rax, [r14+8]
0x180018279  cmp     rax, qword ptr cs:IID_IFlightSettingsAPIBroker.Data4
0x180018280  jz      short loc_1800182A3
0x180018282  mov     rax, [r14]
0x180018285  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18001828c  jnz     loc_18001841B
0x180018292  mov     rax, [r14+8]
0x180018296  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18001829d  jnz     loc_18001841B
0x1800182a3  mov     ecx, [rbp+arg_8]
0x1800182a6  call    ?GetEffectiveFlightSettingsAPIVersion@@YA?AW4FlightSettingsVersion@@K@Z; GetEffectiveFlightSettingsAPIVersion(ulong)
0x1800182ab  cmp     eax, 2
0x1800182ae  jnz     loc_180018414
0x1800182b4  lea     rcx, [rbp+arg_18]
0x1800182b8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800182bd  mov     r8, rdi; struct IClientObjectStubManager *
0x1800182c0  lea     rdx, [rbp+arg_18]; void **
0x1800182c4  mov     rcx, r14; struct _GUID *
0x1800182c7  call    ?s_CreateInstance@FlightSettingsReader@@SAJAEBU_GUID@@PEAPEAXPEAUIClientObjectStubManager@@@Z; FlightSettingsReader::s_CreateInstance(_GUID const &,void * *,IClientObjectStubManager *)
0x1800182cc  mov     ebx, eax
0x1800182ce  test    eax, eax
0x1800182d0  jns     short loc_1800182F4
0x1800182d2  mov     rcx, [rbp+28h]; this
0x1800182d6  mov     r9d, eax; char *
0x1800182d9  lea     r8, aOnecoreBaseFli_16; "onecore\\base\\flighting\\flightsetting"...
0x1800182e0  mov     edx, 2A7h; void *
0x1800182e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800182ea  mov     edx, 6Bh ; 'k'
0x1800182ef  jmp     loc_180018425
0x1800182f4  test    rdi, rdi
0x1800182f7  jz      loc_1800183EF
0x1800182fd  call    SvcAddRef
0x180018302  lea     rdx, [rsi+30h]
0x180018306  lea     rcx, [rbp+var_10]
0x18001830a  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18001830f  cmp     byte ptr [rsi+78h], 0
0x180018313  jz      short loc_180018340
0x180018315  mov     rcx, [rbp+28h]; this
0x180018319  mov     ebx, 8000001Ah
0x18001831e  mov     r9d, ebx; char *
0x180018321  lea     r8, aOnecoreBaseFli_75; "onecore\\base\\flighting\\flightsetting"...
0x180018328  mov     edx, 84h; void *
0x18001832d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018332  lea     rcx, [rbp+var_10]
0x180018336  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001833b  jmp     loc_180018438
0x180018340  mov     qword ptr [rbp+var_20], 0
0x180018348  mov     rbx, [rbp+arg_18]
0x18001834c  mov     rax, [rbx]
0x18001834f  mov     rdi, [rax]
0x180018352  lea     rcx, [rbp+var_20]
0x180018356  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001835b  lea     r8, [rbp+var_20]
0x18001835f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180018366  mov     rcx, rbx
0x180018369  mov     rax, rdi
0x18001836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018371  mov     ebx, eax
0x180018373  test    eax, eax
  ... truncated ...
```
