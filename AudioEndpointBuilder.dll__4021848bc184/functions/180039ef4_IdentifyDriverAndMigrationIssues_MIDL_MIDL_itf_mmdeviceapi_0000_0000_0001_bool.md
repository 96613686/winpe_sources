# IdentifyDriverAndMigrationIssues(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,bool &)

- ea: `0x180039ef4`
- end: `0x18003a6c1`
- name: `?IdentifyDriverAndMigrationIssues@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@AEA_N@Z`
- size: `1997`
- prototype: `__int64 __fastcall(enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039d90`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180012e80`
- `0x180023fbc`
- `0x180039ef4`
- `0x180059e10`
- `0x18005a2ac`
- `0x18005a948`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a29b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a330`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a5dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a671`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a29b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a330`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a5dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a671`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a31b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a65c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a31b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a5c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a65c`

## string_xrefs

- `0x180039fc9`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a027`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a2b7`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a301`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a5f8`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a642`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a345`: `Completed processing current OS devices\n`
- `0x18003a681`: `Completed processing previous OS devices\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall IdentifyDriverAndMigrationIssues(unsigned int a1, bool *a2)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(__int64, const WCHAR *, struct IMMDeviceEnumerator **); // rdi
  HRESULT (__stdcall *v9)(IUnknown *, const IID *const, void **); // rbx
  int v10; // eax
  __int64 v11; // rdx
  unsigned int i; // esi
  __int64 v13; // rax
  int v14; // eax
  struct IMMDevice *v15; // rdi
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  struct IMMDevice *v17; // rbx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rdi
  __int64 v19; // rcx
  int MatchingEndpoint; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  struct IMMDeviceEnumerator *v24; // rdi
  HRESULT (__stdcall *EnumAudioEndpoints)(IMMDeviceEnumerator *, EDataFlow, DWORD, IMMDeviceCollection **); // rbx
  unsigned int j; // esi
  __int64 v27; // rax
  int v28; // eax
  struct IMMDevice *v29; // rdi
  HRESULT (__stdcall *v30)(IMMDevice *, LPWSTR *); // rbx
  struct IMMDevice *v31; // rbx
  HRESULT (__stdcall *v32)(IMMDevice *, DWORD, IPropertyStore **); // rdi
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // r9d
  unsigned int v36; // r8d
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  int v41; // [rsp+20h] [rbp-79h]
  __int64 *v42; // [rsp+30h] [rbp-69h] BYREF
  struct IMMDevice *v43; // [rsp+38h] [rbp-61h] BYREF
  struct IMMDevice *v44; // [rsp+40h] [rbp-59h] BYREF
  struct IMMDevice *v45; // [rsp+48h] [rbp-51h] BYREF
  __int64 v46; // [rsp+50h] [rbp-49h] BYREF
  __int64 v47; // [rsp+58h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v49; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-2Dh] BYREF
  struct IMMDeviceEnumerator *v51; // [rsp+70h] [rbp-29h] BYREF
  struct IMMDevice *v52; // [rsp+78h] [rbp-21h] BYREF
  __int64 v53; // [rsp+80h] [rbp-19h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v55; // [rsp+98h] [rbp-1h]
  PROPVARIANT v56[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v57; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  unsigned int v59; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v60; // [rsp+110h] [rbp+77h] BYREF
  unsigned int v61; // [rsp+118h] [rbp+7Fh] BYREF

  v51 = 0;
  v53 = 0;
  AudMigLibSetupLog(L"Identifying driver and migration issues for %s\r\n", off_18006AD60[a1]);
  QueryInterface = g_DeviceEnumerator->lpVtbl->QueryInterface;
  v53 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         g_DeviceEnumerator,
         &GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0,
         &v53);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1741;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)v5,
      v41);
    goto LABEL_88;
  }
  v8 = *(__int64 (__fastcall **)(__int64, const WCHAR *, struct IMMDeviceEnumerator **))(*(_QWORD *)v53 + 112LL);
  v51 = 0;
  v5 = v8(v53, L"Software\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\Audio\\PreviousOs", &v51);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1742;
    goto LABEL_5;
  }
  v42 = 0;
  v59 = 0;
  v9 = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v42);
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, __int64, __int64 **))v9)(g_DeviceEnumerator, a1, 9, &v42);
  v6 = v10;
  if ( v10 < 0 )
  {
    v11 = 1753;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)v10,
      v41);
    goto LABEL_9;
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v42 + 24))(v42, &v59);
  v6 = v10;
  if ( v10 < 0 )
  {
    v11 = 1754;
    goto LABEL_8;
  }
  AudMigLibSetupLog(L"Processing %d current active or unplugged devices\r\n", v59);
  for ( i = 0; i < v59; ++i )
  {
    v44 = 0;
    *(_OWORD *)pvar = 0;
    v55 = 0;
    v46 = 0;
    pv = 0;
    v60 = 0;
    v13 = *v42;
    v44 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMMDevice **))(v13 + 32))(v42, i, &v44);
    v6 = v14;
    if ( v14 < 0 )
    {
      v22 = 1764;
      goto LABEL_43;
    }
    AEBTelemetry::LogMigrationDeviceInformation(L"CurrentOs", v44);
    v15 = v44;
    GetId = v44->lpVtbl->GetId;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    v14 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(v15, &pv);
    v6 = v14;
    if ( v14 < 0 )
    {
      v22 = 1766;
      goto LABEL_43;
    }
    AudMigLibSetupLog(L"Processing current os device %s\r\n", pv);
    v14 = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned int *))v44->lpVtbl->GetState)(v44, &v60);
    v6 = v14;
    if ( v14 < 0 )
    {
      v22 = 1769;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
        (const char *)(unsigned int)v14,
        v41);
      goto LABEL_44;
    }
    v17 = v44;
    OpenPropertyStore = v44->lpVtbl->OpenPropertyStore;
    v19 = v46;
    v46 = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v14 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(v17, 0, &v46);
    v6 = v14;
    if ( v14 < 0 )
    {
      v22 = 1770;
      goto LABEL_43;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v46 + 40LL))(
            v46,
            PKEY_AudioEndpoint_PersistentId,
            pvar);
    v6 = v14;
    if ( v14 < 0 )
    {
      v22 = 1771;
      goto LABEL_43;
    }
    if ( LOWORD(pvar[0]) == 31 )
    {
      v43 = 0;
      MatchingEndpoint = FindMatchingEndpoint(v51, (unsigned __int16 *)pvar[1], &v43);
      v6 = MatchingEndpoint;
      if ( MatchingEndpoint < 0 )
      {
        v21 = 1776;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
          (const char *)(unsigned int)MatchingEndpoint,
          v41);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v43);
LABEL_44:
        if ( pv )
          CoTaskMemFree(pv);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
        PropVariantClear(pvar);
        v23 = (__int64 *)&v44;
        goto LABEL_47;
      }
      if ( v43 )
      {
        v61 = 0;
        MatchingEndpoint = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned int *))v43->lpVtbl->GetState)(
                             v43,
                             &v61);
        v6 = MatchingEndpoint;
        if ( MatchingEndpoint < 0 )
        {
          v21 = 1780;
          goto LABEL_36;
        }
        if ( v60 == v61 )
        {
          AudMigLibSetupLog(L"Device is as expected\r\n", v59);
        }
        else
        {
          AudMigLibSetupLog(
            L"Migration match %s found, however endpoint state changed previously 0x%08x now 0x%08x\r\n",
            pvar[1]);
          AEBTelemetry::LogMigrationIssue(L"DeviceStateChanged", v44, v60, v61);
        }
      }
      else
      {
        AudMigLibSetupLog(L"Migration match not found for device %s\r\n", pvar[1]);
        AEBTelemetry::LogMigrationIssue(L"NoMigrationData", v44, 0, 0);
        if ( v60 == 1 )
          *a2 = 1;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v43);
    }
    else
    {
      AudMigLibSetupLog(L"Current device has invalid persistent id\r\n");
    }
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v44);
  }
  AudMigLibSetupLog(L"Completed processing current OS devices\r\n");
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v42);
  v24 = v51;
  EnumAudioEndpoints = v51->lpVtbl->EnumAudioEndpoints;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v42);
  v10 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, _QWORD, __int64, __int64 **))EnumAudioEndpoints)(
          v24,
          a1,
          9,
          &v42);
  v6 = v10;
  if ( v10 < 0 )
  {
    v11 = 1813;
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v42 + 24))(v42, &v59);
  v6 = v10;
  if ( v10 < 0 )
  {
    v11 = 1814;
    goto LABEL_8;
  }
  AudMigLibSetupLog(L"Processing %d previous os active or unplugged devices\r\n", v59);
  for ( j = 0; ; ++j )
  {
    if ( j >= v59 )
    {
      AudMigLibSetupLog(L"Completed processing previous OS devices\r\n");
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v42);
      v6 = 0;
      goto LABEL_88;
    }
    v45 = 0;
    *(_OWORD *)v56 = 0;
    v57 = 0;
    v47 = 0;
    v43 = 0;
    v49 = 0;
    v27 = *v42;
    v45 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMMDevice **))(v27 + 32))(v42, j, &v45);
    v6 = v28;
    if ( v28 < 0 )
    {
      v39 = 1824;
      goto LABEL_83;
    }
    AEBTelemetry::LogMigrationDeviceInformation(L"PreviousOs", v45);
    v29 = v45;
    v30 = v45->lpVtbl->GetId;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v43,
      0);
    v28 = ((__int64 (__fastcall *)(struct IMMDevice *, struct IMMDevice **))v30)(v29, &v43);
    v6 = v28;
    if ( v28 < 0 )
    {
      v39 = 1826;
      goto LABEL_83;
    }
    AudMigLibSetupLog(L"Processing previous os device %s\r\n", v43);
    v28 = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned int *))v45->lpVtbl->GetState)(v45, &v49);
    v6 = v28;
    if ( v28 < 0 )
    {
      v39 = 1829;
      goto LABEL_83;
    }
    v31 = v45;
    v32 = v45->lpVtbl->OpenPropertyStore;
    v33 = v47;
    v47 = 0;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v28 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))v32)(v31, 0, &v47);
    v6 = v28;
    if ( v28 < 0 )
      break;
    v28 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v47 + 40LL))(
            v47,
            PKEY_AudioEndpoint_PersistentId,
            v56);
    v6 = v28;
    if ( v28 < 0 )
    {
      v39 = 1831;
      goto LABEL_83;
    }
    if ( LOWORD(v56[0]) == 31 )
    {
      v52 = 0;
      v34 = FindMatchingEndpoint((struct IMMDeviceEnumerator *)g_DeviceEnumerator, (unsigned __int16 *)v56[1], &v52);
      v6 = v34;
      if ( v34 < 0 )
      {
        v38 = 1836;
        goto LABEL_76;
      }
      if ( v52 )
      {
        v50 = 0;
        v34 = ((__int64 (__fastcall *)(struct IMMDevice *, unsigned int *))v52->lpVtbl->GetState)(v52, &v50);
        v6 = v34;
        if ( v34 < 0 )
        {
          v38 = 1840;
LABEL_76:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
            (const char *)(unsigned int)v34,
            v41);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
          goto LABEL_84;
        }
        if ( v49 != v50 )
        {
          AudMigLibSetupLog(
            L"Migration match %s found, however endpoint state changed previously 0x%08x now 0x%08x\r\n",
            v56[1]);
          v35 = v49;
          v36 = v50;
          v37 = L"DeviceStateChanged";
          goto LABEL_69;
        }
        AudMigLibSetupLog(L"Device is as expected\r\n", v59);
      }
      else
      {
        AudMigLibSetupLog(L"Migration match not found for device seen on prior os %s\r\n", v56[1]);
        v35 = 0;
        v36 = 0;
        v37 = L"MissingAfterUpgrade";
LABEL_69:
        AEBTelemetry::LogMigrationIssue(v37, v45, v36, v35);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v52);
      goto LABEL_72;
    }
    AudMigLibSetupLog(L"Previous OS device has invalid persistent id\r\n");
LABEL_72:
    if ( v43 )
      CoTaskMemFree(v43);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
    PropVariantClear(v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v45);
  }
  v39 = 1830;
LABEL_83:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v39,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
    (const char *)(unsigned int)v28,
    v41);
LABEL_84:
  if ( v43 )
    CoTaskMemFree(v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  PropVariantClear(v56);
  v23 = (__int64 *)&v45;
LABEL_47:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v23);
LABEL_9:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v42);
LABEL_88:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v51);
  return v6;
}

```

## disassembly

```asm
0x180039ef4  push    rbp
0x180039ef6  push    rbx
0x180039ef7  push    rsi
0x180039ef8  push    rdi
0x180039ef9  push    r12
0x180039efb  push    r14
0x180039efd  push    r15
0x180039eff  lea     rbp, [rsp-27h]
0x180039f04  sub     rsp, 0C0h
0x180039f0b  mov     r15, rdx
0x180039f0e  movsxd  r14, ecx
0x180039f11  xor     r12d, r12d
0x180039f14  mov     [rbp+57h+var_80], r12
0x180039f18  mov     [rbp+57h+var_70], r12
0x180039f1c  lea     rax, off_18006AD60; "Render"
0x180039f23  mov     rdx, [rax+r14*8]
0x180039f27  lea     rcx, aIdentifyingDri; "Identifying driver and migration issues"...
0x180039f2e  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180039f33  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039f3a  mov     rax, [r9]
0x180039f3d  mov     rbx, [rax]
0x180039f40  mov     rcx, [rbp+57h+var_70]
0x180039f44  mov     [rbp+57h+var_70], r12
0x180039f48  test    rcx, rcx
0x180039f4b  jz      short loc_180039F60
0x180039f4d  mov     rax, [rcx]
0x180039f50  mov     rax, [rax+10h]
0x180039f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f59  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039f60  lea     r8, [rbp+57h+var_70]
0x180039f64  lea     rdx, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0
0x180039f6b  mov     rcx, r9
0x180039f6e  mov     rax, rbx
0x180039f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f76  mov     ebx, eax
0x180039f78  test    eax, eax
0x180039f7a  jns     short loc_180039F83
0x180039f7c  mov     edx, 6CDh
0x180039f81  jmp     short loc_180039FC9
0x180039f83  mov     rbx, [rbp+57h+var_70]
0x180039f87  mov     rax, [rbx]
0x180039f8a  mov     rdi, [rax+70h]
0x180039f8e  mov     rcx, [rbp+57h+var_80]
0x180039f92  mov     [rbp+57h+var_80], r12
0x180039f96  test    rcx, rcx
0x180039f99  jz      short loc_180039FA8
0x180039f9b  mov     rdx, [rcx]
0x180039f9e  mov     rax, [rdx+10h]
0x180039fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fa7  nop
0x180039fa8  lea     r8, [rbp+57h+var_80]
0x180039fac  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039fb3  mov     rcx, rbx
0x180039fb6  mov     rax, rdi
0x180039fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fbe  mov     ebx, eax
0x180039fc0  test    eax, eax
0x180039fc2  jns     short loc_180039FE1
0x180039fc4  mov     edx, 6CEh; void *
0x180039fc9  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x180039fd0  mov     r9d, eax; char *
0x180039fd3  mov     rcx, [rbp+5Fh]; this
0x180039fd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fdc  jmp     loc_18003A69A
0x180039fe1  mov     [rbp+57h+var_C0], r12
0x180039fe5  mov     [rbp+57h+arg_0], r12d
0x180039fe9  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039ff0  mov     rcx, [rax]
0x180039ff3  mov     rbx, [rcx+18h]
0x180039ff7  lea     rcx, [rbp+57h+var_C0]
0x180039ffb  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x18003a000  lea     r9, [rbp+57h+var_C0]
0x18003a004  mov     r8d, 9
0x18003a00a  mov     edx, r14d
0x18003a00d  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18003a014  mov     rax, rbx
0x18003a017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a01c  mov     ebx, eax
0x18003a01e  test    eax, eax
0x18003a020  jns     short loc_18003A049
0x18003a022  mov     edx, 6D9h; void *
0x18003a027  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18003a02e  mov     r9d, eax; char *
0x18003a031  mov     rcx, [rbp+5Fh]; this
0x18003a035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a03a  nop
0x18003a03b  lea     rcx, [rbp+57h+var_C0]
0x18003a03f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a044  jmp     loc_18003A69A
0x18003a049  mov     rcx, [rbp+57h+var_C0]
0x18003a04d  mov     rax, [rcx]
0x18003a050  lea     rdx, [rbp+57h+arg_0]
0x18003a054  mov     rax, [rax+18h]
0x18003a058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a05d  mov     ebx, eax
0x18003a05f  test    eax, eax
0x18003a061  jns     short loc_18003A06A
0x18003a063  mov     edx, 6DAh
0x18003a068  jmp     short loc_18003A027
0x18003a06a  mov     edx, [rbp+57h+arg_0]
0x18003a06d  lea     rcx, aProcessingDCur; "Processing %d current active or unplugg"...
0x18003a074  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a079  mov     esi, r12d
0x18003a07c  cmp     esi, [rbp+57h+arg_0]
0x18003a07f  jnb     loc_18003A345
0x18003a085  mov     [rbp+57h+var_B0], r12
0x18003a089  xorps   xmm0, xmm0
0x18003a08c  xor     eax, eax
0x18003a08e  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003a092  mov     [rbp+57h+var_58], rax
0x18003a096  mov     [rbp+57h+var_A0], r12
0x18003a09a  mov     [rbp+57h+pv], r12
0x18003a09e  mov     [rbp+57h+arg_10], r12d
0x18003a0a2  mov     rcx, [rbp+57h+var_C0]
0x18003a0a6  mov     rax, [rcx]
0x18003a0a9  mov     [rbp+57h+var_B0], r12
0x18003a0ad  lea     r8, [rbp+57h+var_B0]
0x18003a0b1  mov     edx, esi
0x18003a0b3  mov     rax, [rax+20h]
0x18003a0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0bc  mov     ebx, eax
0x18003a0be  test    eax, eax
0x18003a0c0  js      loc_18003A2F9
0x18003a0c6  mov     rdx, [rbp+57h+var_B0]; struct IMMDevice *
0x18003a0ca  lea     rcx, aCurrentos; "CurrentOs"
0x18003a0d1  call    ?LogMigrationDeviceInformation@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@@Z; AEBTelemetry::LogMigrationDeviceInformation(ushort const *,IMMDevice *)
0x18003a0d6  mov     rdi, [rbp+57h+var_B0]
0x18003a0da  mov     rax, [rdi]
0x18003a0dd  mov     rbx, [rax+28h]
0x18003a0e1  xor     edx, edx
0x18003a0e3  lea     rcx, [rbp+57h+pv]
0x18003a0e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a0ec  lea     rdx, [rbp+57h+pv]
0x18003a0f0  mov     rcx, rdi
0x18003a0f3  mov     rax, rbx
0x18003a0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0fb  mov     ebx, eax
0x18003a0fd  test    eax, eax
0x18003a0ff  js      loc_18003A2F2
0x18003a105  mov     rdx, [rbp+57h+pv]
0x18003a109  lea     rcx, aProcessingCurr; "Processing current os device %s\r\n"
0x18003a110  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a115  mov     rcx, [rbp+57h+var_B0]
0x18003a119  mov     rax, [rcx]
0x18003a11c  lea     rdx, [rbp+57h+arg_10]
0x18003a120  mov     rax, [rax+30h]
0x18003a124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a129  mov     ebx, eax
0x18003a12b  test    eax, eax
0x18003a12d  js      loc_18003A2EB
0x18003a133  mov     rbx, [rbp+57h+var_B0]
0x18003a137  mov     rax, [rbx]
0x18003a13a  mov     rdi, [rax+20h]
0x18003a13e  mov     rcx, [rbp+57h+var_A0]
0x18003a142  mov     [rbp+57h+var_A0], r12
0x18003a146  test    rcx, rcx
0x18003a149  jz      short loc_18003A158
0x18003a14b  mov     rdx, [rcx]
0x18003a14e  mov     rax, [rdx+10h]
0x18003a152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a157  nop
0x18003a158  lea     r8, [rbp+57h+var_A0]
0x18003a15c  xor     edx, edx
0x18003a15e  mov     rcx, rbx
0x18003a161  mov     rax, rdi
0x18003a164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a169  mov     ebx, eax
0x18003a16b  test    eax, eax
0x18003a16d  js      loc_18003A2E4
0x18003a173  mov     rcx, [rbp+57h+var_A0]
0x18003a177  mov     rax, [rcx]
0x18003a17a  lea     r8, [rbp+57h+pvar]
0x18003a17e  lea     rdx, PKEY_AudioEndpoint_PersistentId
0x18003a185  mov     rax, [rax+28h]
0x18003a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a18e  mov     ebx, eax
0x18003a190  test    eax, eax
0x18003a192  js      loc_18003A2DD
0x18003a198  mov     eax, 1Fh
0x18003a19d  cmp     ax, word ptr [rbp+57h+pvar]
0x18003a1a1  jnz     loc_18003A270
0x18003a1a7  mov     [rbp+57h+var_B8], r12
0x18003a1ab  lea     r8, [rbp+57h+var_B8]; struct IMMDevice **
0x18003a1af  mov     rdx, [rbp+57h+pvar+8]; unsigned __int16 *
0x18003a1b3  mov     rcx, [rbp+57h+var_80]; struct IMMDeviceEnumerator *
0x18003a1b7  call    ?FindMatchingEndpoint@@YAJPEAUIMMDeviceEnumerator@@PEAGPEAPEAUIMMDevice@@@Z; FindMatchingEndpoint(IMMDeviceEnumerator *,ushort *,IMMDevice * *)
0x18003a1bc  mov     ebx, eax
0x18003a1be  test    eax, eax
0x18003a1c0  js      loc_18003A2D6
0x18003a1c6  mov     rcx, [rbp+57h+var_B8]
0x18003a1ca  test    rcx, rcx
0x18003a1cd  jz      short loc_18003A235
0x18003a1cf  mov     [rbp+57h+arg_18], r12d
0x18003a1d3  mov     rax, [rcx]
0x18003a1d6  lea     rdx, [rbp+57h+arg_18]
0x18003a1da  mov     rax, [rax+30h]
0x18003a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1e3  mov     ebx, eax
0x18003a1e5  test    eax, eax
0x18003a1e7  js      loc_18003A2B2
0x18003a1ed  mov     r9d, [rbp+57h+arg_10]
0x18003a1f1  mov     r8d, [rbp+57h+arg_18]
0x18003a1f5  cmp     r9d, r8d
0x18003a1f8  jz      short loc_18003A224
0x18003a1fa  mov     rdx, [rbp+57h+pvar+8]
0x18003a1fe  lea     rcx, aMigrationMatch; "Migration match %s found, however endpo"...
0x18003a205  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a20a  mov     r9d, [rbp+57h+arg_18]; unsigned int
0x18003a20e  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x18003a212  mov     rdx, [rbp+57h+var_B0]; struct IMMDevice *
0x18003a216  lea     rcx, aDevicestatecha; "DeviceStateChanged"
0x18003a21d  call    ?LogMigrationIssue@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@KK@Z; AEBTelemetry::LogMigrationIssue(ushort const *,IMMDevice *,ulong,ulong)
0x18003a222  jmp     short loc_18003A265
0x18003a224  mov     edx, [rbp+57h+arg_0]
0x18003a227  lea     rcx, aDeviceIsAsExpe; "Device is as expected\r\n"
0x18003a22e  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a233  jmp     short loc_18003A265
0x18003a235  mov     rdx, [rbp+57h+pvar+8]
0x18003a239  lea     rcx, aMigrationMatch_0; "Migration match not found for device %s"...
0x18003a240  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a245  xor     r9d, r9d; unsigned int
0x18003a248  xor     r8d, r8d; unsigned int
0x18003a24b  mov     rdx, [rbp+57h+var_B0]; struct IMMDevice *
0x18003a24f  lea     rcx, aNomigrationdat; "NoMigrationData"
0x18003a256  call    ?LogMigrationIssue@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@KK@Z; AEBTelemetry::LogMigrationIssue(ushort const *,IMMDevice *,ulong,ulong)
0x18003a25b  cmp     [rbp+57h+arg_10], 1
0x18003a25f  jnz     short loc_18003A265
0x18003a261  mov     byte ptr [r15], 1
0x18003a265  lea     rcx, [rbp+57h+var_B8]
0x18003a269  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a26e  jmp     short loc_18003A27D
0x18003a270  lea     rcx, aCurrentDeviceH; "Current device has invalid persistent i"...
0x18003a277  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a27c  nop
0x18003a27d  mov     rcx, [rbp+57h+pv]; pv
0x18003a281  test    rcx, rcx
0x18003a284  jz      short loc_18003A28D
0x18003a286  call    cs:__imp_CoTaskMemFree
0x18003a28c  nop
0x18003a28d  lea     rcx, [rbp+57h+var_A0]
0x18003a291  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a296  nop
0x18003a297  lea     rcx, [rbp+57h+pvar]; pvar
0x18003a29b  call    cs:__imp_PropVariantClear
0x18003a2a1  nop
0x18003a2a2  lea     rcx, [rbp+57h+var_B0]
0x18003a2a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a2ab  inc     esi
0x18003a2ad  jmp     loc_18003A07C
0x18003a2b2  mov     edx, 6F4h; void *
0x18003a2b7  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18003a2be  mov     r9d, eax; char *
0x18003a2c1  mov     rcx, [rbp+5Fh]; this
0x18003a2c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a2ca  nop
0x18003a2cb  lea     rcx, [rbp+57h+var_B8]
0x18003a2cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a2d4  jmp     short loc_18003A312
0x18003a2d6  mov     edx, 6F0h
0x18003a2db  jmp     short loc_18003A2B7
0x18003a2dd  mov     edx, 6EBh
0x18003a2e2  jmp     short loc_18003A2FE
0x18003a2e4  mov     edx, 6EAh
0x18003a2e9  jmp     short loc_18003A2FE
0x18003a2eb  mov     edx, 6E9h
0x18003a2f0  jmp     short loc_18003A2FE
0x18003a2f2  mov     edx, 6E6h
0x18003a2f7  jmp     short loc_18003A2FE
0x18003a2f9  mov     edx, 6E4h; void *
0x18003a2fe  mov     r9d, eax; char *
0x18003a301  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18003a308  mov     rcx, [rbp+5Fh]; this
0x18003a30c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a311  nop
0x18003a312  mov     rcx, [rbp+57h+pv]; pv
0x18003a316  test    rcx, rcx
0x18003a319  jz      short loc_18003A322
0x18003a31b  call    cs:__imp_CoTaskMemFree
0x18003a321  nop
0x18003a322  lea     rcx, [rbp+57h+var_A0]
0x18003a326  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a32b  nop
0x18003a32c  lea     rcx, [rbp+57h+pvar]; pvar
0x18003a330  call    cs:__imp_PropVariantClear
0x18003a336  nop
0x18003a337  lea     rcx, [rbp+57h+var_B0]
0x18003a33b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a340  jmp     loc_18003A03B
0x18003a345  lea     rcx, aCompletedProce; "Completed processing current OS devices"...
0x18003a34c  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a351  lea     rcx, [rbp+57h+var_C0]
0x18003a355  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x18003a35a  mov     rdi, [rbp+57h+var_80]
0x18003a35e  mov     rax, [rdi]
0x18003a361  mov     rbx, [rax+18h]
0x18003a365  lea     rcx, [rbp+57h+var_C0]
0x18003a369  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x18003a36e  lea     r9, [rbp+57h+var_C0]
0x18003a372  mov     r8d, 9
0x18003a378  mov     edx, r14d
  ... truncated ...
```
