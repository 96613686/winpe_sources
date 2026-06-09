# ConnectorSupportsFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID)

- ea: `0x180118500`
- end: `0x180118ada`
- name: `?ConnectorSupportsFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@@Z`
- size: `1498`
- prototype: `int(struct EndpointCharacteristicsDescriptor *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct tWAVEFORMATEX *, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fa40`
- `0x180118ae0`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x180029d8c`
- `0x1800423cc`
- `0x180045068`
- `0x1800623ec`
- `0x1800639f4`
- `0x1800cf8c0`
- `0x180118414`
- `0x180118500`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a12`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a12`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180118a90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011874f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18011874f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011862b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118aae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011862b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118aae`

## string_xrefs

- `0x1801185c0`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801185fe`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011868b`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801186e5`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011876b`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801187c3`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180118831`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011887b`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1801188e5`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18011898a`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

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
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, PROPVARIANT, __int64 **); // rbx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 *v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rax
  unsigned __int64 v32; // r9
  __int64 v33; // rdx
  int v34; // eax
  void *v35; // rcx
  void *v36; // rcx
  int ppv; // [rsp+20h] [rbp-A9h]
  int ppva; // [rsp+20h] [rbp-A9h]
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  __int64 *v40; // [rsp+58h] [rbp-71h] BYREF
  __int64 *v41; // [rsp+60h] [rbp-69h] BYREF
  __int64 v42; // [rsp+68h] [rbp-61h] BYREF
  __int64 *v43; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v44; // [rsp+78h] [rbp-51h] BYREF
  __int64 v45; // [rsp+80h] [rbp-49h] BYREF
  __int64 v46; // [rsp+88h] [rbp-41h] BYREF
  PROPVARIANT v47[2]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-29h]
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-11h]
  int v51; // [rsp+C0h] [rbp-9h] BYREF
  _DWORD v52[3]; // [rsp+C4h] [rbp-5h] BYREF
  __int128 v53; // [rsp+D0h] [rbp+7h] BYREF
  __int64 p_pv; // [rsp+E0h] [rbp+17h] BYREF
  struct KSDATAFORMAT_WAVEFORMATEX *v55; // [rsp+E8h] [rbp+1Fh] BYREF
  int v56; // [rsp+F0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v5 = a2;
  v6 = 0;
  if ( (((_DWORD)a2 - 1) & 0xFFFFFFFD) != 0 )
  {
    v53 = (__int128)*a4;
    SharedModeEnginePeriodicity = EffectPack::GetSharedModeEnginePeriodicity(*((_QWORD *)a1 + 1), a2, a3, &v53);
    if ( SharedModeEnginePeriodicity < 0 )
      return (unsigned int)SharedModeEnginePeriodicity;
    return v6;
  }
  *(_QWORD *)&v53 = 0;
  v9 = *(_QWORD *)a1;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v53);
  wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(v9 + 40, &v53);
  pv = 0;
  p_pv = (__int64)&pv;
  v55 = 0;
  LOBYTE(v56) = 1;
  Instance = CreateKSFormatFromWFXFormat(a3, &v55);
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
  v40 = 0;
  v11 = *(_QWORD *)v53;
  v40 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v11 + 32))(v53, 0, &v40);
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
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
LABEL_10:
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
LABEL_56:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v53);
    return (unsigned int)Instance;
  }
  *(_OWORD *)pvar = 0;
  v50 = 0;
  v14 = *v40;
  p_pv = 0x4C7D1B2C233164C8LL;
  v55 = (struct KSDATAFORMAT_WAVEFORMATEX *)0x67257A6871B668BCLL;
  v56 = 1;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, PROPVARIANT *))(v14 + 40))(v40, &p_pv, pvar);
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
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v16 = *(__int64 (__fastcall **)(__int64 *, const struct _tagpropertykey *, PROPVARIANT *))(*v40 + 40);
  if ( v5 == 3 )
  {
    v17 = v16(v40, &PKEY_Endpoint_KeywordDetector_ConnectorId, v47);
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
      PropVariantClear(v47);
      goto LABEL_14;
    }
  }
  else
  {
    v17 = v16(v40, &PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId, v47);
    Instance = v17;
    if ( v17 < 0 )
    {
      v18 = 453;
      goto LABEL_18;
    }
  }
  v42 = 0;
  p_pv = (__int64)&v42;
  v55 = 0;
  LOBYTE(v56) = 1;
  Instance = CoCreateInstance(
               &CLSID_MMDeviceEnumerator,
               0,
               0x17u,
               &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
               (LPVOID *)&v55);
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
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
    goto LABEL_19;
  }
  v41 = 0;
  v19 = v42;
  v20 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, __int64 **))(*(_QWORD *)v42 + 40LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v41);
  v21 = v20(v19, pvar[1], &v41);
  Instance = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)(unsigned int)v21,
      ppva);
LABEL_27:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    goto LABEL_24;
  }
  v44 = 0;
  v22 = *v41;
  p_pv = (__int64)&v44;
  v55 = 0;
  LOBYTE(v56) = 1;
  Instance = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v22 + 24))(
               v41,
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
      (int)&v55);
LABEL_30:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    goto LABEL_27;
  }
  v43 = 0;
  v23 = *v44;
  v43 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v23 + 56))(v44, LODWORD(v47[1]), &v43);
  Instance = v24;
  if ( v24 < 0 )
  {
    v25 = (unsigned int)v24;
    v26 = 466;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)v25,
      (int)&v55);
LABEL_34:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
    goto LABEL_30;
  }
  v27 = v43;
  if ( !v43 )
  {
    Instance = -2147023728;
    v25 = 2147943568LL;
    v26 = 467;
    goto LABEL_33;
  }
  if ( v5 == 1 )
  {
    v45 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v43)(
            v43,
            &GUID_9c2c4058_23f5_41de_877a_df3af236a09e,
            &v45);
    Instance = v28;
    if ( v28 < 0 )
    {
      v29 = 472;
LABEL_40:
      v30 = (unsigned int)v28;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)v30,
        (int)&v55);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
      goto LABEL_34;
    }
    v51 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 24LL))(v45, &v51);
    Instance = v28;
    if ( v28 < 0 )
    {
      v29 = 476;
      goto LABEL_40;
    }
    if ( v51 != 3 )
    {
      Instance = -2147418113;
      v30 = 2147549183LL;
      v29 = 477;
      goto LABEL_41;
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v45);
    v27 = v43;
  }
  v46 = 0;
  v31 = *v27;
  p_pv = (__int64)&v46;
  v55 = 0;
  LOBYTE(v56) = 1;
  Instance = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, struct KSDATAFORMAT_WAVEFORMATEX **))(v31 + 104))(
               v27,
               1,
               &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
               &v55);
  wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(&p_pv);
  if ( Instance < 0 )
  {
    v32 = (unsigned int)Instance;
    v33 = 481;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
      (const char *)v32,
      (int)&v55);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
    goto LABEL_34;
  }
  v52[0] = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _DWORD *))(*(_QWORD *)v46 + 24LL))(
          v46,
          pv,
          *(unsigned int *)pv,
          v52);
  Instance = v34;
  if ( v34 < 0 )
  {
    v32 = (unsigned int)v34;
    v33 = 484;
    goto LABEL_49;
  }
  if ( !v52[0] )
  {
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
    PropVariantClear(v47);
    PropVariantClear(pvar);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
    v35 = pv;
    pv = 0;
    if ( v35 )
      CoTaskMemFree(v35);
    Instance = -2004287480;
    goto LABEL_56;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v46);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
  PropVariantClear(v47);
  PropVariantClear(pvar);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v40);
  v36 = pv;
  pv = 0;
  if ( v36 )
    CoTaskMemFree(v36);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v53);
  return 0;
}

```

## disassembly

```asm
0x180118500  push    rbp
0x180118502  push    rbx
0x180118503  push    rsi
0x180118504  push    rdi
0x180118505  push    r14
0x180118507  lea     rbp, [rsp-37h]
0x18011850c  sub     rsp, 100h
0x180118513  mov     rax, cs:__security_cookie
0x18011851a  xor     rax, rsp
0x18011851d  mov     [rbp+57h+var_28], rax
0x180118521  mov     rdi, r8
0x180118524  mov     r14d, edx
0x180118527  lea     eax, [rdx-1]
0x18011852a  xor     esi, esi
0x18011852c  test    eax, 0FFFFFFFDh
0x180118531  jz      short loc_18011856D
0x180118533  movaps  xmm0, xmmword ptr [r9]
0x180118537  movdqa  [rbp+57h+var_50], xmm0
0x18011853c  mov     [rsp+120h+var_E0], rsi
0x180118541  mov     [rsp+120h+var_E8], rsi
0x180118546  mov     [rsp+120h+var_F0], rsi
0x18011854b  mov     [rsp+120h+var_F8], rsi
0x180118550  mov     dword ptr [rsp+120h+ppv], esi
0x180118554  lea     r9, [rbp+57h+var_50]
0x180118558  mov     rcx, [rcx+8]
0x18011855c  call    ?GetSharedModeEnginePeriodicity@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@U_GUID@@W4PeriodicityType@@PEAI444@Z; EffectPack::GetSharedModeEnginePeriodicity(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,_GUID,PeriodicityType,uint *,uint *,uint *,uint *)
0x180118561  test    eax, eax
0x180118563  cmovs   esi, eax
0x180118566  mov     eax, esi
0x180118568  jmp     loc_180118AC0
0x18011856d  mov     qword ptr [rbp+57h+var_50], rsi
0x180118571  mov     rbx, [rcx]
0x180118574  lea     rcx, [rbp+57h+var_50]
0x180118578  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18011857d  lea     rcx, [rbx+28h]
0x180118581  lea     rdx, [rbp+57h+var_50]
0x180118585  call    ??$copy_to@VCAudioSession@@@?$com_ptr_t@VCAudioSession@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAVCAudioSession@@@Z; wil::com_ptr_t<CAudioSession,wil::err_returncode_policy>::copy_to<CAudioSession>(CAudioSession * *)
0x18011858a  mov     [rbp+57h+pv], rsi
0x18011858e  lea     rax, [rbp+57h+pv]
0x180118592  mov     [rbp+57h+var_40], rax
0x180118596  mov     [rbp+57h+var_38], rsi
0x18011859a  mov     byte ptr [rbp+57h+var_30], 1
0x18011859e  lea     rdx, [rbp+57h+var_38]; struct KSDATAFORMAT_WAVEFORMATEX **
0x1801185a2  mov     rcx, rdi; Src
0x1801185a5  call    ?CreateKSFormatFromWFXFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAUKSDATAFORMAT_WAVEFORMATEX@@@Z; CreateKSFormatFromWFXFormat(tWAVEFORMATEX const *,KSDATAFORMAT_WAVEFORMATEX * *)
0x1801185aa  mov     ebx, eax
0x1801185ac  lea     rcx, [rbp+57h+var_40]
0x1801185b0  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801185b5  test    ebx, ebx
0x1801185b7  jns     short loc_1801185D3
0x1801185b9  mov     rcx, [rbp+5Fh]; this
0x1801185bd  mov     r9d, ebx; char *
0x1801185c0  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801185c7  mov     edx, 1B6h; void *
0x1801185cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801185d1  jmp     short loc_18011861A
0x1801185d3  mov     [rbp+57h+var_C8], rsi
0x1801185d7  mov     rcx, qword ptr [rbp+57h+var_50]
0x1801185db  mov     rax, [rcx]
0x1801185de  mov     [rbp+57h+var_C8], rsi
0x1801185e2  lea     r8, [rbp+57h+var_C8]
0x1801185e6  xor     edx, edx
0x1801185e8  mov     rax, [rax+20h]
0x1801185ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801185f1  mov     ebx, eax
0x1801185f3  test    eax, eax
0x1801185f5  jns     short loc_180118636
0x1801185f7  mov     rcx, [rbp+5Fh]; this
0x1801185fb  mov     r9d, eax; char *
0x1801185fe  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118605  mov     edx, 1B9h; void *
0x18011860a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011860f  nop
0x180118610  lea     rcx, [rbp+57h+var_C8]
0x180118614  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118619  nop
0x18011861a  mov     rcx, [rbp+57h+pv]; pv
0x18011861e  mov     [rbp+57h+pv], rsi
0x180118622  test    rcx, rcx
0x180118625  jz      loc_180118A46
0x18011862b  call    cs:__imp_CoTaskMemFree
0x180118631  jmp     loc_180118A46
0x180118636  xorps   xmm0, xmm0
0x180118639  xor     eax, eax
0x18011863b  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18011863f  mov     [rbp+57h+var_68], rax
0x180118643  mov     rcx, [rbp+57h+var_C8]
0x180118647  mov     rax, [rcx]
0x18011864a  mov     dword ptr [rbp+57h+var_40], 233164C8h
0x180118651  mov     dword ptr [rbp+57h+var_40+4], 4C7D1B2Ch
0x180118658  mov     dword ptr [rbp+57h+var_38], 71B668BCh
0x18011865f  mov     dword ptr [rbp+57h+var_38+4], 67257A68h
0x180118666  mov     [rbp+57h+var_30], 1
0x18011866d  lea     r8, [rbp+57h+pvar]
0x180118671  lea     rdx, [rbp+57h+var_40]
0x180118675  mov     rax, [rax+28h]
0x180118679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011867e  mov     ebx, eax
0x180118680  test    eax, eax
0x180118682  jns     short loc_1801186AC
0x180118684  mov     rcx, [rbp+5Fh]; this
0x180118688  mov     r9d, eax; char *
0x18011868b  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118692  mov     edx, 1BCh; void *
0x180118697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011869c  nop
0x18011869d  lea     rcx, [rbp+57h+pvar]; pvar
0x1801186a1  call    cs:__imp_PropVariantClear
0x1801186a7  jmp     loc_180118610
0x1801186ac  xorps   xmm0, xmm0
0x1801186af  xor     eax, eax
0x1801186b1  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1801186b5  mov     [rbp+57h+var_80], rax
0x1801186b9  mov     rcx, [rbp+57h+var_C8]
0x1801186bd  lea     r8, [rbp+57h+var_90]
0x1801186c1  mov     rax, [rcx]
0x1801186c4  mov     rax, [rax+28h]
0x1801186c8  cmp     r14d, 3
0x1801186cc  jnz     short loc_180118705
0x1801186ce  lea     rdx, PKEY_Endpoint_KeywordDetector_ConnectorId
0x1801186d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801186da  mov     ebx, eax
0x1801186dc  test    eax, eax
0x1801186de  jns     short loc_18011871E
0x1801186e0  mov     edx, 1C1h; void *
0x1801186e5  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801186ec  mov     r9d, eax; char *
0x1801186ef  mov     rcx, [rbp+5Fh]; this
0x1801186f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801186f8  nop
0x1801186f9  lea     rcx, [rbp+57h+var_90]; pvar
0x1801186fd  call    cs:__imp_PropVariantClear
0x180118703  jmp     short loc_18011869D
0x180118705  lea     rdx, PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId
0x18011870c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118711  mov     ebx, eax
0x180118713  test    eax, eax
0x180118715  jns     short loc_18011871E
0x180118717  mov     edx, 1C5h
0x18011871c  jmp     short loc_1801186E5
0x18011871e  mov     [rbp+57h+var_B8], rsi
0x180118722  lea     rax, [rbp+57h+var_B8]
0x180118726  mov     [rbp+57h+var_40], rax
0x18011872a  mov     [rbp+57h+var_38], rsi
0x18011872e  mov     byte ptr [rbp+57h+var_30], 1
0x180118732  lea     rax, [rbp+57h+var_38]
0x180118736  mov     [rsp+120h+ppv], rax; int
0x18011873b  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180118742  xor     edx, edx; pUnkOuter
0x180118744  lea     r8d, [rdx+17h]; dwClsContext
0x180118748  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x18011874f  call    cs:__imp_CoCreateInstance
0x180118755  mov     ebx, eax
0x180118757  lea     rcx, [rbp+57h+var_40]
0x18011875b  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIMMDeviceEnumerator@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IMMDeviceEnumerator,wil::err_returncode_policy>>(void)
0x180118760  test    ebx, ebx
0x180118762  jns     short loc_18011878B
0x180118764  mov     rcx, [rbp+5Fh]; this
0x180118768  mov     r9d, ebx; char *
0x18011876b  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118772  mov     edx, 1C9h; void *
0x180118777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011877c  nop
0x18011877d  lea     rcx, [rbp+57h+var_B8]
0x180118781  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118786  jmp     loc_1801186F9
0x18011878b  mov     [rbp+57h+var_C0], rsi
0x18011878f  mov     rdi, [rbp+57h+var_B8]
0x180118793  mov     rax, [rdi]
0x180118796  mov     rbx, [rax+28h]
0x18011879a  lea     rcx, [rbp+57h+var_C0]
0x18011879e  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1801187a3  lea     r8, [rbp+57h+var_C0]
0x1801187a7  mov     rdx, [rbp+57h+pvar+8]
0x1801187ab  mov     rcx, rdi
0x1801187ae  mov     rax, rbx
0x1801187b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801187b6  mov     ebx, eax
0x1801187b8  test    eax, eax
0x1801187ba  jns     short loc_1801187E0
0x1801187bc  mov     rcx, [rbp+5Fh]; this
0x1801187c0  mov     r9d, eax; char *
0x1801187c3  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801187ca  mov     edx, 1CCh; void *
0x1801187cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801187d4  nop
0x1801187d5  lea     rcx, [rbp+57h+var_C0]
0x1801187d9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801187de  jmp     short loc_18011877D
0x1801187e0  mov     [rbp+57h+var_A8], rsi
0x1801187e4  mov     rcx, [rbp+57h+var_C0]
0x1801187e8  mov     rax, [rcx]
0x1801187eb  lea     rdx, [rbp+57h+var_A8]
0x1801187ef  mov     [rbp+57h+var_40], rdx
0x1801187f3  mov     [rbp+57h+var_38], rsi
0x1801187f7  mov     byte ptr [rbp+57h+var_30], 1
0x1801187fb  lea     rdx, [rbp+57h+var_38]
0x1801187ff  mov     [rsp+120h+ppv], rdx; int
0x180118804  xor     r9d, r9d
0x180118807  lea     r8d, [r9+17h]
0x18011880b  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180118812  mov     rax, [rax+18h]
0x180118816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011881b  mov     ebx, eax
0x18011881d  lea     rcx, [rbp+57h+var_40]
0x180118821  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIDeviceTopology@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(void)
0x180118826  test    ebx, ebx
0x180118828  jns     short loc_18011884E
0x18011882a  mov     rcx, [rbp+5Fh]; this
0x18011882e  mov     r9d, ebx; char *
0x180118831  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118838  mov     edx, 1CFh; void *
0x18011883d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118842  nop
0x180118843  lea     rcx, [rbp+57h+var_A8]
0x180118847  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18011884c  jmp     short loc_1801187D5
0x18011884e  mov     [rbp+57h+var_B0], rsi
0x180118852  mov     rcx, [rbp+57h+var_A8]
0x180118856  mov     rax, [rcx]
0x180118859  mov     [rbp+57h+var_B0], rsi
0x18011885d  lea     r8, [rbp+57h+var_B0]
0x180118861  mov     edx, dword ptr [rbp+57h+var_90+8]
0x180118864  mov     rax, [rax+38h]
0x180118868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011886d  mov     ebx, eax
0x18011886f  test    eax, eax
0x180118871  jns     short loc_180118897
0x180118873  mov     r9d, eax; char *
0x180118876  mov     edx, 1D2h; void *
0x18011887b  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180118882  mov     rcx, [rbp+5Fh]; this
0x180118886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011888b  nop
0x18011888c  lea     rcx, [rbp+57h+var_B0]
0x180118890  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180118895  jmp     short loc_180118843
0x180118897  mov     rcx, [rbp+57h+var_B0]
0x18011889b  test    rcx, rcx
0x18011889e  jnz     short loc_1801188AF
0x1801188a0  mov     ebx, 80070490h
0x1801188a5  mov     r9d, ebx
0x1801188a8  mov     edx, 1D3h
0x1801188ad  jmp     short loc_18011887B
0x1801188af  cmp     r14d, 1
0x1801188b3  jnz     loc_180118943
0x1801188b9  mov     [rbp+57h+var_A0], rsi
0x1801188bd  mov     rax, [rcx]
0x1801188c0  lea     r8, [rbp+57h+var_A0]
0x1801188c4  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x1801188cb  mov     rax, [rax]
0x1801188ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801188d3  mov     ebx, eax
0x1801188d5  test    eax, eax
0x1801188d7  jns     short loc_1801188FD
0x1801188d9  mov     edx, 1D8h; void *
0x1801188de  mov     r9d, eax; char *
0x1801188e1  mov     rcx, [rbp+5Fh]; this
0x1801188e5  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801188ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801188f1  nop
0x1801188f2  lea     rcx, [rbp+57h+var_A0]
0x1801188f6  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801188fb  jmp     short loc_18011888C
0x1801188fd  mov     [rbp+57h+var_60], esi
0x180118900  mov     rcx, [rbp+57h+var_A0]
0x180118904  mov     rax, [rcx]
0x180118907  lea     rdx, [rbp+57h+var_60]
0x18011890b  mov     rax, [rax+18h]
0x18011890f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118914  mov     ebx, eax
0x180118916  test    eax, eax
0x180118918  jns     short loc_180118921
0x18011891a  mov     edx, 1DCh
0x18011891f  jmp     short loc_1801188DE
0x180118921  cmp     [rbp+57h+var_60], 3
0x180118925  jz      short loc_180118936
0x180118927  mov     ebx, 8000FFFFh
0x18011892c  mov     r9d, ebx
0x18011892f  mov     edx, 1DDh
0x180118934  jmp     short loc_1801188E1
0x180118936  lea     rcx, [rbp+57h+var_A0]
0x18011893a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18011893f  mov     rcx, [rbp+57h+var_B0]
0x180118943  mov     [rbp+57h+var_98], rsi
0x180118947  mov     rax, [rcx]
0x18011894a  lea     r8, [rbp+57h+var_98]
0x18011894e  mov     [rbp+57h+var_40], r8
0x180118952  mov     [rbp+57h+var_38], rsi
0x180118956  mov     byte ptr [rbp+57h+var_30], 1
0x18011895a  lea     r9, [rbp+57h+var_38]
0x18011895e  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x180118965  mov     edx, 1
0x18011896a  mov     rax, [rax+68h]
0x18011896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118973  mov     ebx, eax
0x180118975  lea     rcx, [rbp+57h+var_40]
0x180118979  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIDeviceTopology@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IDeviceTopology,wil::err_returncode_policy>>(void)
0x18011897e  test    ebx, ebx
0x180118980  jns     short loc_1801189A9
  ... truncated ...
```
