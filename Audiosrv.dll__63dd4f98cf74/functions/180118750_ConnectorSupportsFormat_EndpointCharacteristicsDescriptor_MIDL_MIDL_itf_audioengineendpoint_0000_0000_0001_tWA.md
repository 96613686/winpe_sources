# ConnectorSupportsFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID)

- ea: `0x180118750`
- end: `0x180118d2a`
- name: `?ConnectorSupportsFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@@Z`
- size: `1498`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct tWAVEFORMATEX *, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fb90`
- `0x180118d30`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x180029eec`
- `0x1800424ec`
- `0x180044bd8`
- `0x180061f5c`
- `0x180063564`
- `0x1800cd8d0`
- `0x180118664`
- `0x180118750`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801188f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011894d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118c62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118c6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118cd5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118ce0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801188f1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011894d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118c62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118c6d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118cd5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118ce0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011899f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011899f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118cfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011887b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118cfe`

## string_xrefs

- `0x180118810`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011884e`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801188db`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118935`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801189bb`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118a13`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118a81`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118acb`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118b35`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118bda`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ConnectorSupportsFormat(
        struct EndpointCharacteristicsDescriptor *a1,
        __int64 a2,
        struct tWAVEFORMATEX *a3,
        struct _GUID *a4)
{
  int v5; // r14d
  unsigned int v6; // esi
  int SharedModeEnginePeriodicity; // eax
  __int64 v9; // rbx
  HRESULT Instance; // ebx
  __int64 v11; // rax
  int v12; // eax
  void *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64 *, const struct _tagpropertykey *, PROPVARIANT *); // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, PROPVARIANT, __int64 **); // rbx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 *v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  __int64 v32; // rax
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  int v35; // eax
  void *v36; // rcx
  void *v37; // rcx
  int ppv; // [rsp+20h] [rbp-A9h]
  int ppva; // [rsp+20h] [rbp-A9h]
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  __int64 *v41; // [rsp+58h] [rbp-71h] BYREF
  __int64 *v42; // [rsp+60h] [rbp-69h] BYREF
  __int64 v43; // [rsp+68h] [rbp-61h] BYREF
  __int64 *v44; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v45; // [rsp+78h] [rbp-51h] BYREF
  __int64 v46; // [rsp+80h] [rbp-49h] BYREF
  __int64 v47; // [rsp+88h] [rbp-41h] BYREF
  PROPVARIANT v48[2]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-29h]
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-11h]
  int v52; // [rsp+C0h] [rbp-9h] BYREF
  _DWORD v53[3]; // [rsp+C4h] [rbp-5h] BYREF
  __int128 v54; // [rsp+D0h] [rbp+7h] BYREF
  __int64 p_pv; // [rsp+E0h] [rbp+17h] BYREF
  struct KSDATAFORMAT_WAVEFORMATEX *v56; // [rsp+E8h] [rbp+1Fh] BYREF
  int v57; // [rsp+F0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v5 = a2;
  v6 = 0;
  if ( (((_DWORD)a2 - 1) & 0xFFFFFFFD) != 0 )
  {
    v54 = (__int128)*a4;
    SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(*((_QWORD *)a1 + 1), a2, a3, &v54);
    if ( SharedModeEnginePeriodicity < 0 )
      return (unsigned int)SharedModeEnginePeriodicity;
    return v6;
  }
  *(_QWORD *)&v54 = 0;
  v9 = *(_QWORD *)a1;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v54, a2);
  wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(v9 + 40, &v54);
  pv = 0;
  p_pv = (__int64)&pv;
  v56 = 0;
  LOBYTE(v57) = 1;
  Instance = CreateKSFormatFromWFXFormat(a3, &v56);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_10;
  }
  v41 = 0;
  v11 = *(_QWORD *)v54;
  v41 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v11 + 32))(v54, 0, &v41);
  Instance = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)v12,
      ppv);
LABEL_9:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
LABEL_10:
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
LABEL_56:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v54);
    return (unsigned int)Instance;
  }
  *(_OWORD *)pvar = 0;
  v51 = 0;
  v14 = *v41;
  p_pv = 0x4C7D1B2C233164C8LL;
  v56 = (struct KSDATAFORMAT_WAVEFORMATEX *)0x67257A6871B668BCLL;
  v57 = 1;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, PROPVARIANT *))(v14 + 40))(v41, &p_pv, pvar);
  Instance = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)v15,
      ppv);
LABEL_14:
    PropVariantClear(pvar);
    goto LABEL_9;
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v16 = *(__int64 (__fastcall **)(__int64 *, const struct _tagpropertykey *, PROPVARIANT *))(*v41 + 40);
  if ( v5 == 3 )
  {
    v17 = v16(v41, &PKEY_Endpoint_KeywordDetector_ConnectorId, v48);
    Instance = v17;
    if ( v17 < 0 )
    {
      v18 = 449;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)(unsigned int)v17,
        ppv);
LABEL_19:
      PropVariantClear(v48);
      goto LABEL_14;
    }
  }
  else
  {
    v17 = v16(v41, &PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId, v48);
    Instance = v17;
    if ( v17 < 0 )
    {
      v18 = 453;
      goto LABEL_18;
    }
  }
  v43 = 0;
  p_pv = (__int64)&v43;
  v56 = 0;
  LOBYTE(v57) = 1;
  Instance = CoCreateInstance(
               &CLSID_MMDeviceEnumerator,
               0,
               0x17u,
               &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
               (LPVOID *)&v56);
  wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>(&p_pv);
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
LABEL_24:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
    goto LABEL_19;
  }
  v42 = 0;
  v20 = v43;
  v21 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, __int64 **))(*(_QWORD *)v43 + 40LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v42, v19);
  v22 = v21(v20, pvar[1], &v42);
  Instance = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)v22,
      ppva);
LABEL_27:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
    goto LABEL_24;
  }
  v45 = 0;
  v23 = *v42;
  p_pv = (__int64)&v45;
  v56 = 0;
  LOBYTE(v57) = 1;
  Instance = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v23 + 24))(
               v42,
               &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
               23);
  wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(&p_pv);
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)Instance,
      (int)&v56);
LABEL_30:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
    goto LABEL_27;
  }
  v44 = 0;
  v24 = *v45;
  v44 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v24 + 56))(v45, LODWORD(v48[1]), &v44);
  Instance = v25;
  if ( v25 < 0 )
  {
    v26 = (unsigned int)v25;
    v27 = 466;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)v26,
      (int)&v56);
LABEL_34:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    goto LABEL_30;
  }
  v28 = v44;
  if ( !v44 )
  {
    Instance = -2147023728;
    v26 = 2147943568LL;
    v27 = 467;
    goto LABEL_33;
  }
  if ( v5 == 1 )
  {
    v46 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v44)(
            v44,
            &GUID_9c2c4058_23f5_41de_877a_df3af236a09e,
            &v46);
    Instance = v29;
    if ( v29 < 0 )
    {
      v30 = 472;
LABEL_40:
      v31 = (unsigned int)v29;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)v31,
        (int)&v56);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
      goto LABEL_34;
    }
    v52 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 24LL))(v46, &v52);
    Instance = v29;
    if ( v29 < 0 )
    {
      v30 = 476;
      goto LABEL_40;
    }
    if ( v52 != 3 )
    {
      Instance = -2147418113;
      v31 = 2147549183LL;
      v30 = 477;
      goto LABEL_41;
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
    v28 = v44;
  }
  v47 = 0;
  v32 = *v28;
  p_pv = (__int64)&v47;
  v56 = 0;
  LOBYTE(v57) = 1;
  Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, struct KSDATAFORMAT_WAVEFORMATEX **))(v32 + 104))(
               v28,
               1,
               &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
               &v56);
  wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(&p_pv);
  if ( Instance < 0 )
  {
    v33 = (unsigned int)Instance;
    v34 = 481;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)v33,
      (int)&v56);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
    goto LABEL_34;
  }
  v53[0] = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _DWORD *))(*(_QWORD *)v47 + 24LL))(
          v47,
          pv,
          *(unsigned int *)pv,
          v53);
  Instance = v35;
  if ( v35 < 0 )
  {
    v33 = (unsigned int)v35;
    v34 = 484;
    goto LABEL_49;
  }
  if ( !v53[0] )
  {
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
    PropVariantClear(v48);
    PropVariantClear(pvar);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    v36 = pv;
    pv = 0;
    if ( v36 )
      CoTaskMemFree(v36);
    Instance = -2004287480;
    goto LABEL_56;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v47);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
  PropVariantClear(v48);
  PropVariantClear(pvar);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
  v37 = pv;
  pv = 0;
  if ( v37 )
    CoTaskMemFree(v37);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v54);
  return 0;
}

```

## disassembly

```asm
0x180118750  push    rbp
0x180118752  push    rbx
0x180118753  push    rsi
0x180118754  push    rdi
0x180118755  push    r14
0x180118757  lea     rbp, [rsp-37h]
0x18011875c  sub     rsp, 100h
0x180118763  mov     rax, cs:__security_cookie
0x18011876a  xor     rax, rsp
0x18011876d  mov     [rbp+57h+var_28], rax
0x180118771  mov     rdi, r8
0x180118774  mov     r14d, edx
0x180118777  lea     eax, [rdx-1]
0x18011877a  xor     esi, esi
0x18011877c  test    eax, 0FFFFFFFDh
0x180118781  jz      short loc_1801187BD
0x180118783  movaps  xmm0, xmmword ptr [r9]
0x180118787  movdqa  [rbp+57h+var_50], xmm0
0x18011878c  mov     [rsp+120h+var_E0], rsi
0x180118791  mov     [rsp+120h+var_E8], rsi
0x180118796  mov     [rsp+120h+var_F0], rsi
0x18011879b  mov     [rsp+120h+var_F8], rsi
0x1801187a0  mov     dword ptr [rsp+120h+ppv], esi
0x1801187a4  lea     r9, [rbp+57h+var_50]
0x1801187a8  mov     rcx, [rcx+8]
0x1801187ac  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x1801187b1  test    eax, eax
0x1801187b3  cmovs   esi, eax
0x1801187b6  mov     eax, esi
0x1801187b8  jmp     loc_180118D10
0x1801187bd  mov     qword ptr [rbp+57h+var_50], rsi
0x1801187c1  mov     rbx, [rcx]
0x1801187c4  lea     rcx, [rbp+57h+var_50]
0x1801187c8  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1801187cd  lea     rcx, [rbx+28h]
0x1801187d1  lea     rdx, [rbp+57h+var_50]
0x1801187d5  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x1801187da  mov     [rbp+57h+pv], rsi
0x1801187de  lea     rax, [rbp+57h+pv]
0x1801187e2  mov     [rbp+57h+var_40], rax
0x1801187e6  mov     [rbp+57h+var_38], rsi
0x1801187ea  mov     byte ptr [rbp+57h+var_30], 1
0x1801187ee  lea     rdx, [rbp+57h+var_38]; struct KSDATAFORMAT_WAVEFORMATEX **
0x1801187f2  mov     rcx, rdi; Src
0x1801187f5  call    ?CreateKSFormatFromWFXFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAUKSDATAFORMAT_WAVEFORMATEX@@@Z; CreateKSFormatFromWFXFormat(tWAVEFORMATEX const *,KSDATAFORMAT_WAVEFORMATEX * *)
0x1801187fa  mov     ebx, eax
0x1801187fc  lea     rcx, [rbp+57h+var_40]
0x180118800  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180118805  test    ebx, ebx
0x180118807  jns     short loc_180118823
0x180118809  mov     rcx, [rbp+5Fh]; this
0x18011880d  mov     r9d, ebx; char *
0x180118810  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118817  mov     edx, 1B6h; void *
0x18011881c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118821  jmp     short loc_18011886A
0x180118823  mov     [rbp+57h+var_C8], rsi
0x180118827  mov     rcx, qword ptr [rbp+57h+var_50]
0x18011882b  mov     rax, [rcx]
0x18011882e  mov     [rbp+57h+var_C8], rsi
0x180118832  lea     r8, [rbp+57h+var_C8]
0x180118836  xor     edx, edx
0x180118838  mov     rax, [rax+20h]
0x18011883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118841  mov     ebx, eax
0x180118843  test    eax, eax
0x180118845  jns     short loc_180118886
0x180118847  mov     rcx, [rbp+5Fh]; this
0x18011884b  mov     r9d, eax; char *
0x18011884e  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118855  mov     edx, 1B9h; void *
0x18011885a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011885f  nop
0x180118860  lea     rcx, [rbp+57h+var_C8]
0x180118864  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118869  nop
0x18011886a  mov     rcx, [rbp+57h+pv]; pv
0x18011886e  mov     [rbp+57h+pv], rsi
0x180118872  test    rcx, rcx
0x180118875  jz      loc_180118C96
0x18011887b  call    cs:__imp_CoTaskMemFree
0x180118881  jmp     loc_180118C96
0x180118886  xorps   xmm0, xmm0
0x180118889  xor     eax, eax
0x18011888b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18011888f  mov     [rbp+57h+var_68], rax
0x180118893  mov     rcx, [rbp+57h+var_C8]
0x180118897  mov     rax, [rcx]
0x18011889a  mov     dword ptr [rbp+57h+var_40], 233164C8h
0x1801188a1  mov     dword ptr [rbp+57h+var_40+4], 4C7D1B2Ch
0x1801188a8  mov     dword ptr [rbp+57h+var_38], 71B668BCh
0x1801188af  mov     dword ptr [rbp+57h+var_38+4], 67257A68h
0x1801188b6  mov     [rbp+57h+var_30], 1
0x1801188bd  lea     r8, [rbp+57h+pvar]
0x1801188c1  lea     rdx, [rbp+57h+var_40]
0x1801188c5  mov     rax, [rax+28h]
0x1801188c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801188ce  mov     ebx, eax
0x1801188d0  test    eax, eax
0x1801188d2  jns     short loc_1801188FC
0x1801188d4  mov     rcx, [rbp+5Fh]; this
0x1801188d8  mov     r9d, eax; char *
0x1801188db  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801188e2  mov     edx, 1BCh; void *
0x1801188e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801188ec  nop
0x1801188ed  lea     rcx, [rbp+57h+pvar]; pvar
0x1801188f1  call    cs:__imp_PropVariantClear
0x1801188f7  jmp     loc_180118860
0x1801188fc  xorps   xmm0, xmm0
0x1801188ff  xor     eax, eax
0x180118901  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180118905  mov     [rbp+57h+var_80], rax
0x180118909  mov     rcx, [rbp+57h+var_C8]
0x18011890d  lea     r8, [rbp+57h+var_90]
0x180118911  mov     rax, [rcx]
0x180118914  mov     rax, [rax+28h]
0x180118918  cmp     r14d, 3
0x18011891c  jnz     short loc_180118955
0x18011891e  lea     rdx, PKEY_Endpoint_KeywordDetector_ConnectorId
0x180118925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011892a  mov     ebx, eax
0x18011892c  test    eax, eax
0x18011892e  jns     short loc_18011896E
0x180118930  mov     edx, 1C1h; void *
0x180118935  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011893c  mov     r9d, eax; char *
0x18011893f  mov     rcx, [rbp+5Fh]; this
0x180118943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118948  nop
0x180118949  lea     rcx, [rbp+57h+var_90]; pvar
0x18011894d  call    cs:__imp_PropVariantClear
0x180118953  jmp     short loc_1801188ED
0x180118955  lea     rdx, PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId
0x18011895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118961  mov     ebx, eax
0x180118963  test    eax, eax
0x180118965  jns     short loc_18011896E
0x180118967  mov     edx, 1C5h
0x18011896c  jmp     short loc_180118935
0x18011896e  mov     [rbp+57h+var_B8], rsi
0x180118972  lea     rax, [rbp+57h+var_B8]
0x180118976  mov     [rbp+57h+var_40], rax
0x18011897a  mov     [rbp+57h+var_38], rsi
0x18011897e  mov     byte ptr [rbp+57h+var_30], 1
0x180118982  lea     rax, [rbp+57h+var_38]
0x180118986  mov     [rsp+120h+ppv], rax; int
0x18011898b  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180118992  xor     edx, edx; pUnkOuter
0x180118994  lea     r8d, [rdx+17h]; dwClsContext
0x180118998  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x18011899f  call    cs:__imp_CoCreateInstance
0x1801189a5  mov     ebx, eax
0x1801189a7  lea     rcx, [rbp+57h+var_40]
0x1801189ab  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIMMDeviceEnumerator@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>(void)
0x1801189b0  test    ebx, ebx
0x1801189b2  jns     short loc_1801189DB
0x1801189b4  mov     rcx, [rbp+5Fh]; this
0x1801189b8  mov     r9d, ebx; char *
0x1801189bb  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801189c2  mov     edx, 1C9h; void *
0x1801189c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801189cc  nop
0x1801189cd  lea     rcx, [rbp+57h+var_B8]
0x1801189d1  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801189d6  jmp     loc_180118949
0x1801189db  mov     [rbp+57h+var_C0], rsi
0x1801189df  mov     rdi, [rbp+57h+var_B8]
0x1801189e3  mov     rax, [rdi]
0x1801189e6  mov     rbx, [rax+28h]
0x1801189ea  lea     rcx, [rbp+57h+var_C0]
0x1801189ee  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1801189f3  lea     r8, [rbp+57h+var_C0]
0x1801189f7  mov     rdx, [rbp+57h+pvar+8]
0x1801189fb  mov     rcx, rdi
0x1801189fe  mov     rax, rbx
0x180118a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a06  mov     ebx, eax
0x180118a08  test    eax, eax
0x180118a0a  jns     short loc_180118A30
0x180118a0c  mov     rcx, [rbp+5Fh]; this
0x180118a10  mov     r9d, eax; char *
0x180118a13  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118a1a  mov     edx, 1CCh; void *
0x180118a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118a24  nop
0x180118a25  lea     rcx, [rbp+57h+var_C0]
0x180118a29  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118a2e  jmp     short loc_1801189CD
0x180118a30  mov     [rbp+57h+var_A8], rsi
0x180118a34  mov     rcx, [rbp+57h+var_C0]
0x180118a38  mov     rax, [rcx]
0x180118a3b  lea     rdx, [rbp+57h+var_A8]
0x180118a3f  mov     [rbp+57h+var_40], rdx
0x180118a43  mov     [rbp+57h+var_38], rsi
0x180118a47  mov     byte ptr [rbp+57h+var_30], 1
0x180118a4b  lea     rdx, [rbp+57h+var_38]
0x180118a4f  mov     [rsp+120h+ppv], rdx; int
0x180118a54  xor     r9d, r9d
0x180118a57  lea     r8d, [r9+17h]
0x180118a5b  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180118a62  mov     rax, [rax+18h]
0x180118a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a6b  mov     ebx, eax
0x180118a6d  lea     rcx, [rbp+57h+var_40]
0x180118a71  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIDeviceTopology@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(void)
0x180118a76  test    ebx, ebx
0x180118a78  jns     short loc_180118A9E
0x180118a7a  mov     rcx, [rbp+5Fh]; this
0x180118a7e  mov     r9d, ebx; char *
0x180118a81  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118a88  mov     edx, 1CFh; void *
0x180118a8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118a92  nop
0x180118a93  lea     rcx, [rbp+57h+var_A8]
0x180118a97  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118a9c  jmp     short loc_180118A25
0x180118a9e  mov     [rbp+57h+var_B0], rsi
0x180118aa2  mov     rcx, [rbp+57h+var_A8]
0x180118aa6  mov     rax, [rcx]
0x180118aa9  mov     [rbp+57h+var_B0], rsi
0x180118aad  lea     r8, [rbp+57h+var_B0]
0x180118ab1  mov     edx, dword ptr [rbp+57h+var_90+8]
0x180118ab4  mov     rax, [rax+38h]
0x180118ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118abd  mov     ebx, eax
0x180118abf  test    eax, eax
0x180118ac1  jns     short loc_180118AE7
0x180118ac3  mov     r9d, eax; char *
0x180118ac6  mov     edx, 1D2h; void *
0x180118acb  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118ad2  mov     rcx, [rbp+5Fh]; this
0x180118ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118adb  nop
0x180118adc  lea     rcx, [rbp+57h+var_B0]
0x180118ae0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118ae5  jmp     short loc_180118A93
0x180118ae7  mov     rcx, [rbp+57h+var_B0]
0x180118aeb  test    rcx, rcx
0x180118aee  jnz     short loc_180118AFF
0x180118af0  mov     ebx, 80070490h
0x180118af5  mov     r9d, ebx
0x180118af8  mov     edx, 1D3h
0x180118afd  jmp     short loc_180118ACB
0x180118aff  cmp     r14d, 1
0x180118b03  jnz     loc_180118B93
0x180118b09  mov     [rbp+57h+var_A0], rsi
0x180118b0d  mov     rax, [rcx]
0x180118b10  lea     r8, [rbp+57h+var_A0]
0x180118b14  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x180118b1b  mov     rax, [rax]
0x180118b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b23  mov     ebx, eax
0x180118b25  test    eax, eax
0x180118b27  jns     short loc_180118B4D
0x180118b29  mov     edx, 1D8h; void *
0x180118b2e  mov     r9d, eax; char *
0x180118b31  mov     rcx, [rbp+5Fh]; this
0x180118b35  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118b41  nop
0x180118b42  lea     rcx, [rbp+57h+var_A0]
0x180118b46  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118b4b  jmp     short loc_180118ADC
0x180118b4d  mov     [rbp+57h+var_60], esi
0x180118b50  mov     rcx, [rbp+57h+var_A0]
0x180118b54  mov     rax, [rcx]
0x180118b57  lea     rdx, [rbp+57h+var_60]
0x180118b5b  mov     rax, [rax+18h]
0x180118b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118b64  mov     ebx, eax
0x180118b66  test    eax, eax
0x180118b68  jns     short loc_180118B71
0x180118b6a  mov     edx, 1DCh
0x180118b6f  jmp     short loc_180118B2E
0x180118b71  cmp     [rbp+57h+var_60], 3
0x180118b75  jz      short loc_180118B86
0x180118b77  mov     ebx, 8000FFFFh
0x180118b7c  mov     r9d, ebx
0x180118b7f  mov     edx, 1DDh
0x180118b84  jmp     short loc_180118B31
0x180118b86  lea     rcx, [rbp+57h+var_A0]
0x180118b8a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118b8f  mov     rcx, [rbp+57h+var_B0]
0x180118b93  mov     [rbp+57h+var_98], rsi
0x180118b97  mov     rax, [rcx]
0x180118b9a  lea     r8, [rbp+57h+var_98]
0x180118b9e  mov     [rbp+57h+var_40], r8
0x180118ba2  mov     [rbp+57h+var_38], rsi
0x180118ba6  mov     byte ptr [rbp+57h+var_30], 1
0x180118baa  lea     r9, [rbp+57h+var_38]
0x180118bae  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x180118bb5  mov     edx, 1
0x180118bba  mov     rax, [rax+68h]
0x180118bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118bc3  mov     ebx, eax
0x180118bc5  lea     rcx, [rbp+57h+var_40]
0x180118bc9  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIDeviceTopology@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(void)
0x180118bce  test    ebx, ebx
0x180118bd0  jns     short loc_180118BF9
  ... truncated ...
```
