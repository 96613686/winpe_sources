# WlanSyncTaskWlanToCDS::SyncNlmChanges(WiFiCloudStoreTelemetry::WlanTriggeredSync &,bool)

- ea: `0x1800144c0`
- end: `0x180014d69`
- name: `?SyncNlmChanges@WlanSyncTaskWlanToCDS@@CAXAEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@_N@Z`
- size: `2217`
- prototype: `void __fastcall(struct WiFiCloudStoreTelemetry::WlanTriggeredSync *, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001314c`

## callees

- `0x180006afc`
- `0x180006b88`
- `0x180006d7c`
- `0x180007190`
- `0x180007f90`
- `0x180010c8c`
- `0x1800115a0`
- `0x180011690`
- `0x1800144c0`
- `0x180015624`
- `0x180016398`
- `0x1800163e8`
- `0x180016478`
- `0x180016794`
- `0x1800167e8`
- `0x1800168c4`
- `0x1800169bc`
- `0x1800169e0`
- `0x1800208d8`
- `0x180025308`
- `0x180027514`
- `0x1800290cc`
- `0x18002a030`
- `0x18002aad0`
- `0x18002e2d0`
- `0x180032e48`
- `0x1800332cc`
- `0x1800333ec`
- `0x180033748`
- `0x180034008`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800145af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800145af`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800149cd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800149cd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001462b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001462b`
- `OLEAUT32!__imp_VariantInit` at `0x180014715`
- `OLEAUT32!__imp_VariantInit` at `0x180014715`
- `OLEAUT32!__imp_VariantClear` at `0x180014bb2`
- `OLEAUT32!__imp_VariantClear` at `0x180014bb2`

## string_xrefs

- `0x1800145c4`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x18001463b`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x18001469c`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800146fc`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180014751`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800147a8`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180014824`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x18001488f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800148fc`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800149e2`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x180014a1a`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall WlanSyncTaskWlanToCDS::SyncNlmChanges(struct WiFiCloudStoreTelemetry::WlanTriggeredSync *a1, char a2)
{
  char v2; // di
  struct WiFiCloudStoreTelemetry::WlanTriggeredSync *v3; // r15
  int v4; // r12d
  int v5; // r13d
  HRESULT v6; // eax
  GUID *v7; // r14
  GUID *v8; // rax
  int v9; // eax
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, GUID *, IUnknown **); // rbx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  char *v16; // r8
  char *v17; // rdx
  IUnknown *v18; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 **, int *); // rbx
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  _QWORD *v26; // rdx
  HRESULT v27; // eax
  int v28; // eax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  void *v31; // rcx
  _QWORD *v32; // rax
  void *v33; // rcx
  __int64 v34; // rdx
  const char *v35; // r9
  LPVOID v36; // rcx
  GUID **p_rguid; // rcx
  int ppv; // [rsp+20h] [rbp-238h]
  char v39; // [rsp+40h] [rbp-218h] BYREF
  _BYTE v40[7]; // [rsp+41h] [rbp-217h] BYREF
  char v41[8]; // [rsp+48h] [rbp-210h] BYREF
  char v42; // [rsp+50h] [rbp-208h]
  unsigned int v43; // [rsp+54h] [rbp-204h] BYREF
  IUnknown *pProxy; // [rsp+58h] [rbp-200h] BYREF
  unsigned int v45; // [rsp+60h] [rbp-1F8h] BYREF
  int v46; // [rsp+64h] [rbp-1F4h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1F0h] BYREF
  _QWORD *v48; // [rsp+70h] [rbp-1E8h] BYREF
  LPVOID v49; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 *v50; // [rsp+80h] [rbp-1D8h] BYREF
  __int64 v51; // [rsp+88h] [rbp-1D0h] BYREF
  int v52; // [rsp+90h] [rbp-1C8h] BYREF
  __int64 v53; // [rsp+98h] [rbp-1C0h] BYREF
  _QWORD *v54; // [rsp+A0h] [rbp-1B8h] BYREF
  void *v55; // [rsp+A8h] [rbp-1B0h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-1A8h]
  GUID *v57; // [rsp+C0h] [rbp-198h]
  GUID *v58; // [rsp+C8h] [rbp-190h]
  GUID *rguid; // [rsp+D0h] [rbp-188h] BYREF
  GUID *v60; // [rsp+D8h] [rbp-180h]
  __int64 v61; // [rsp+E0h] [rbp-178h]
  struct WiFiCloudStoreTelemetry::WlanTriggeredSync *v62; // [rsp+E8h] [rbp-170h]
  LPVOID *p_pv; // [rsp+F0h] [rbp-168h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-160h] BYREF
  char v65; // [rsp+100h] [rbp-158h]
  VARIANTARG pvarg; // [rsp+108h] [rbp-150h] BYREF
  unsigned int v67[4]; // [rsp+120h] [rbp-138h] BYREF
  __int64 v68; // [rsp+130h] [rbp-128h] BYREF
  char v69; // [rsp+138h] [rbp-120h]
  char v70[8]; // [rsp+148h] [rbp-110h] BYREF
  std::_Ref_count_base *v71; // [rsp+150h] [rbp-108h]
  std::_Ref_count_base *v72; // [rsp+168h] [rbp-F0h]
  _QWORD v73[3]; // [rsp+170h] [rbp-E8h] BYREF
  unsigned __int64 v74; // [rsp+188h] [rbp-D0h]
  _BYTE v75[64]; // [rsp+190h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+1D0h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v2 = a2;
  v42 = a2;
  v3 = a1;
  v62 = a1;
  v41[0] = a2;
  WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginProcessingNlmRegistry(a1);
  Windows::Internal::WiFiCloudStore::GetNlmSyncChangesFromRegistry(&rguid);
  v43 = -858993459 * (((char *)v60 - (char *)rguid) >> 2);
  WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginSyncingNlmChanges<unsigned int,bool &>(v3, &v43, v41);
  std::vector<bond::blob>::vector<bond::blob>(&v55);
  v4 = 0;
  v46 = 0;
  v5 = 0;
  LODWORD(v48) = 0;
  if ( !v2 )
    goto LABEL_67;
  wil::cloud_store::cloud_store(v70);
  v49 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  v6 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v49);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v7 = rguid;
  v8 = v60;
  v57 = v60;
  while ( 1 )
  {
    v58 = v7;
    if ( v7 == v8 )
      break;
    memset_0(sz, 0, 0x4Eu);
    v9 = StringFromGUID2(v7, sz, 39);
    try
    {
      if ( !v9 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x106,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)0x8007007ALL,
          ppv);
      wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
        v3,
        sz);
      pProxy = 0;
      v10 = v49;
      v11 = *(__int64 (__fastcall **)(LPVOID, GUID *, IUnknown **))(*(_QWORD *)v49 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
      v12 = v11(v10, v7, &pProxy);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)v12,
          ppv);
      if ( v7[1].Data1 == 2 )
      {
        v4 += WlanSyncTaskCommon::UploadSignaturesToCloudForNetwork(
                (struct wil::cloud_store *)v70,
                (struct INetworkPrivate *)pProxy);
        v46 = v4;
LABEL_56:
        v34 = v56;
        if ( (_QWORD)v56 == *((_QWORD *)&v56 + 1) )
        {
          std::vector<Windows::Internal::WiFiCloudStore::NlmSyncStruct>::_Emplace_reallocate<Windows::Internal::WiFiCloudStore::NlmSyncStruct const &>(
            &v55,
            v56,
            v7);
        }
        else
        {
          *(GUID *)v56 = *v7;
          *(_DWORD *)(v34 + 16) = v7[1].Data1;
          *(_QWORD *)&v56 = v56 + 20;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
        v2 = v42;
        goto LABEL_77;
      }
      v53 = 0;
      v13 = Microsoft::WRL::ComPtr<INetworkPrivate>::As<IPropertyBag>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&pProxy,
              (__int64)&v53);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)v13,
          ppv);
      VariantInit(&pvarg);
      v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v53 + 24LL))(
              v53,
              L"NA_NetworkClass",
              &pvarg,
              0);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
          (const char *)(unsigned int)v14,
          ppv);
      if ( pvarg.vt == 23 && pvarg.lVal == 2 )
      {
        v45 = 0;
        v15 = ((__int64 (__fastcall *)(IUnknown *, unsigned int *))pProxy->lpVtbl[4].AddRef)(pProxy, &v45);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x11D,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
            (const char *)(unsigned int)v15,
            ppv);
        if ( v45 > 1 )
        {
          v39 = 1;
          v40[0] = 1;
          v16 = &v39;
          v17 = v40;
          goto LABEL_54;
        }
        v51 = 0;
        v18 = pProxy;
        AddRef = pProxy->lpVtbl[5].AddRef;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        v20 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64 *))AddRef)(v18, 3, &v51);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x122,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
            (const char *)(unsigned int)v20,
            ppv);
        v50 = 0;
        v52 = 0;
        while ( 1 )
        {
          v21 = v51;
          v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **, int *))(*(_QWORD *)v51 + 24LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
          v23 = v22(v21, 1, &v50, &v52);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x126,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              (const char *)(unsigned int)v23,
              ppv);
          if ( v23 )
          {
            WiFiCloudStoreTelemetry::NoSignatureFoundInCloudForNetwork<_GUID const &>(v7);
            goto LABEL_52;
          }
          pv = 0;
          v43 = 0;
          v24 = *v50;
          p_pv = &pv;
          v64 = 0;
          v65 = 1;
          v25 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, __int64 *))(v24 + 24))(v50, &v43, &v64);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x12A,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              (const char *)(unsigned int)v25,
              ppv);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
          NetworkSignatureToCDSReferenceId(v73, pv, v43);
          v26 = v73;
          if ( v74 > 7 )
            v26 = (_QWORD *)v73[0];
          wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(
            (__int64)v75,
            (__int64)v26,
            (__int64)c_wiFiCloudStoreDataReferenceDefaultCollectionName);
          wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>((__int64)v70, (__int64)v67, (__int64)v75, 0);
          if ( !v69 )
            break;
          v32 = v73;
          if ( v74 > 7 )
            v32 = (_QWORD *)v73[0];
          v54 = v32;
          WiFiCloudStoreTelemetry::SignatureNotFoundInCloud<_GUID const &,unsigned short const *>(v7, &v54);
          wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v68);
          Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>((__int64)v75);
          std::wstring::~wstring((__int64)v73);
          v33 = pv;
          pv = 0;
          if ( v33 )
            CoTaskMemFree(v33);
        }
        if ( *(_QWORD *)v67 == v45 )
        {
          v30 = v73;
          if ( v74 > 7 )
            v30 = (_QWORD *)v73[0];
          v54 = v30;
          WiFiCloudStoreTelemetry::NlmCategoryUpToDate<_GUID const &,unsigned short const *,unsigned __int64 &>(
            v7,
            &v54,
            v67);
        }
        else
        {
          v27 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x146,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              (const char *)(unsigned int)v27,
              ppv);
          v28 = ((__int64 (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl[4].Release)(pProxy, v67[0]);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x148,
              (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
              (const char *)(unsigned int)v28,
              ppv);
          v29 = v73;
          if ( v74 > 7 )
            v29 = (_QWORD *)v73[0];
          v48 = v29;
          WiFiCloudStoreTelemetry::AppliedNlmCategory<_GUID const &,unsigned short const *,unsigned __int64 &>(
            v7,
            &v48,
            v67);
          LODWORD(v48) = ++v5;
        }
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v68);
        Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>((__int64)v75);
        std::wstring::~wstring((__int64)v73);
        v31 = pv;
        pv = 0;
        if ( v31 )
          CoTaskMemFree(v31);
LABEL_52:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      }
      else
      {
        v40[0] = 0;
        v39 = 0;
        v16 = v40;
        v17 = &v39;
LABEL_54:
        WiFiCloudStoreTelemetry::NlmSkippingNetwork<_GUID const &,bool,bool>(v7, v17, v16);
      }
      VariantClear(&pvarg);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
      goto LABEL_56;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
        v35);
      v4 = v46;
      v5 = (int)v48;
      v7 = v58;
      v3 = v62;
      v2 = v41[0];
      v42 = v41[0];
    }
LABEL_77:
    v8 = v57;
    v7 = (GUID *)((char *)v7 + 20);
  }
  v36 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( v72 )
    std::_Ref_count_base::_Decref(v72);
  if ( v71 )
    std::_Ref_count_base::_Decref(v71);
LABEL_67:
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
    v3,
    0);
  WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginNlmCleanup<unsigned int &,unsigned int &>(v3, &v46, &v48);
  p_rguid = (GUID **)&v55;
  if ( !v2 )
    p_rguid = &rguid;
  Windows::Internal::WiFiCloudStore::DeleteProcessedNlmSyncChangesFromRegistry(p_rguid);
  if ( v55 )
  {
    std::_Deallocate<16>(v55, 4 * ((__int64)(*((_QWORD *)&v56 + 1) - (_QWORD)v55) >> 2));
    v55 = 0;
    v56 = 0;
  }
  if ( rguid )
    std::_Deallocate<16>(rguid, 4 * ((v61 - (__int64)rguid) >> 2));
}

```

## disassembly

```asm
0x1800144c0  mov     [rsp+arg_10], rbx
0x1800144c5  mov     [rsp+arg_18], rsi
0x1800144ca  push    rdi
0x1800144cb  push    r12
0x1800144cd  push    r13
0x1800144cf  push    r14
0x1800144d1  push    r15
0x1800144d3  sub     rsp, 230h
0x1800144da  mov     rax, cs:__security_cookie
0x1800144e1  xor     rax, rsp
0x1800144e4  mov     [rsp+258h+var_38], rax
0x1800144ec  mov     dil, dl
0x1800144ef  mov     [rsp+258h+var_208], dl
0x1800144f3  mov     r15, rcx
0x1800144f6  mov     [rsp+258h+var_170], rcx
0x1800144fe  mov     [rsp+258h+var_210], dl
0x180014502  call    ?BeginProcessingNlmRegistry@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXXZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginProcessingNlmRegistry(void)
0x180014507  lea     rcx, [rsp+258h+rguid]
0x18001450f  call    ?GetNlmSyncChangesFromRegistry@WiFiCloudStore@Internal@Windows@@YA?AV?$vector@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@V?$allocator@UNlmSyncStruct@WiFiCloudStore@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::WiFiCloudStore::GetNlmSyncChangesFromRegistry(void)
0x180014514  nop
0x180014515  mov     rax, [rsp+258h+var_180]
0x18001451d  sub     rax, [rsp+258h+rguid]
0x180014525  sar     rax, 2
0x180014529  mov     rbx, 0CCCCCCCCCCCCCCCDh
0x180014533  imul    rax, rbx
0x180014537  mov     [rsp+258h+var_204], eax
0x18001453b  lea     r8, [rsp+258h+var_210]
0x180014540  lea     rdx, [rsp+258h+var_204]
0x180014545  mov     rcx, r15
0x180014548  call    ??$BeginSyncingNlmChanges@IAEA_N@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAIAEA_N@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::BeginSyncingNlmChanges<uint,bool &>(uint &&,bool &)
0x18001454d  lea     rcx, [rsp+258h+var_1B0]
0x180014555  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18001455a  nop
0x18001455b  xor     esi, esi
0x18001455d  mov     r12d, esi
0x180014560  mov     [rsp+258h+var_1F4], esi
0x180014564  mov     r13d, esi
0x180014567  mov     dword ptr [rsp+258h+var_1E8], esi
0x18001456b  test    dil, dil
0x18001456e  jz      loc_180014C95
0x180014574  lea     rcx, [rsp+258h+var_110]
0x18001457c  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180014581  nop
0x180014582  mov     [rsp+258h+var_1E0], rsi
0x180014587  lea     rcx, [rsp+258h+var_1E0]
0x18001458c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014591  lea     rax, [rsp+258h+var_1E0]
0x180014596  mov     [rsp+258h+ppv], rax; int
0x18001459b  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x1800145a2  xor     edx, edx; pUnkOuter
0x1800145a4  lea     r8d, [rsi+4]; dwClsContext
0x1800145a8  lea     rcx, CLSID_CNetworkListManager; rclsid
0x1800145af  call    cs:__imp_CoCreateInstance
0x1800145b5  mov     rcx, [rsp+258h]; this
0x1800145bd  test    eax, eax
0x1800145bf  jns     short loc_1800145D6
0x1800145c1  mov     r9d, eax; char *
0x1800145c4  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800145cb  mov     edx, 0FCh; void *
0x1800145d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800145d6  mov     r14, [rsp+258h+rguid]
0x1800145de  mov     rax, [rsp+258h+var_180]
0x1800145e6  mov     [rsp+258h+var_198], rax
0x1800145ee  mov     [rsp+258h+var_190], r14
0x1800145f6  cmp     r14, rax
0x1800145f9  jz      loc_180014C55
0x1800145ff  xor     edx, edx; Val
0x180014601  lea     r8d, [rdx+4Eh]; Size
0x180014605  lea     rcx, [rsp+258h+sz]; void *
0x18001460d  call    memset_0
0x180014612  mov     rbx, [rsp+258h]
0x18001461a  mov     r8d, 27h ; '''; cchMax
0x180014620  lea     rdx, [rsp+258h+sz]; lpsz
0x180014628  mov     rcx, r14; rguid
0x18001462b  call    cs:__imp_StringFromGUID2
0x180014631  test    eax, eax
0x180014633  jnz     short loc_18001464F
0x180014635  mov     r9d, 8007007Ah; char *
0x18001463b  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014642  mov     edx, 106h; void *
0x180014647  mov     rcx, rbx; this
0x18001464a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001464f  lea     rdx, [rsp+258h+sz]
0x180014657  mov     rcx, r15
0x18001465a  call    ?SetMessage@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXPEBG@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(ushort const *)
0x18001465f  mov     [rsp+258h+pProxy], rsi
0x180014664  mov     rdi, [rsp+258h+var_1E0]
0x180014669  mov     rax, [rdi]
0x18001466c  mov     rbx, [rax+30h]
0x180014670  lea     rcx, [rsp+258h+pProxy]
0x180014675  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001467a  lea     r8, [rsp+258h+pProxy]
0x18001467f  mov     rdx, r14
0x180014682  mov     rcx, rdi
0x180014685  mov     rax, rbx
0x180014688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001468d  mov     rcx, [rsp+258h]; this
0x180014695  test    eax, eax
0x180014697  jns     short loc_1800146AD
0x180014699  mov     r9d, eax; char *
0x18001469c  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800146a3  mov     edx, 10Ah; void *
0x1800146a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800146ad  cmp     dword ptr [r14+10h], 2
0x1800146b2  jnz     short loc_1800146D3
0x1800146b4  mov     rdx, [rsp+258h+pProxy]; struct INetworkPrivate *
0x1800146b9  lea     rcx, [rsp+258h+var_110]; struct wil::cloud_store *
0x1800146c1  call    ?UploadSignaturesToCloudForNetwork@WlanSyncTaskCommon@@SAIAEAVcloud_store@wil@@PEAUINetworkPrivate@@@Z; WlanSyncTaskCommon::UploadSignaturesToCloudForNetwork(wil::cloud_store &,INetworkPrivate *)
0x1800146c6  add     r12d, eax
0x1800146c9  mov     [rsp+258h+var_1F4], r12d
0x1800146ce  jmp     loc_180014BC6
0x1800146d3  mov     [rsp+258h+var_1C0], rsi
0x1800146db  lea     rdx, [rsp+258h+var_1C0]
0x1800146e3  lea     rcx, [rsp+258h+pProxy]
0x1800146e8  call    ??$As@UIPropertyBag@@@?$ComPtr@UINetworkPrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<INetworkPrivate>::As<IPropertyBag>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPropertyBag>>)
0x1800146ed  mov     rcx, [rsp+258h]; this
0x1800146f5  test    eax, eax
0x1800146f7  jns     short loc_18001470D
0x1800146f9  mov     r9d, eax; char *
0x1800146fc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014703  mov     edx, 117h; void *
0x180014708  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001470d  lea     rcx, [rsp+258h+pvarg]; pvarg
0x180014715  call    cs:__imp_VariantInit
0x18001471b  nop
0x18001471c  mov     rcx, [rsp+258h+var_1C0]
0x180014724  mov     rax, [rcx]
0x180014727  xor     r9d, r9d
0x18001472a  lea     r8, [rsp+258h+pvarg]
0x180014732  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x180014739  mov     rax, [rax+18h]
0x18001473d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014742  mov     rcx, [rsp+258h]; this
0x18001474a  test    eax, eax
0x18001474c  jns     short loc_180014762
0x18001474e  mov     r9d, eax; char *
0x180014751  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014758  mov     edx, 119h; void *
0x18001475d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014762  cmp     word ptr [rsp+258h+pvarg], 17h
0x18001476b  jnz     loc_180014B8D
0x180014771  cmp     dword ptr [rsp+258h+pvarg+8], 2
0x180014779  jnz     loc_180014B8D
0x18001477f  mov     [rsp+258h+var_1F8], esi
0x180014783  mov     rcx, [rsp+258h+pProxy]
0x180014788  mov     rax, [rcx]
0x18001478b  lea     rdx, [rsp+258h+var_1F8]
0x180014790  mov     rax, [rax+68h]
0x180014794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014799  mov     rcx, [rsp+258h]; this
0x1800147a1  test    eax, eax
0x1800147a3  jns     short loc_1800147B9
0x1800147a5  mov     r9d, eax; char *
0x1800147a8  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800147af  mov     edx, 11Dh; void *
0x1800147b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800147b9  cmp     [rsp+258h+var_1F8], 1
0x1800147be  jbe     short loc_1800147D9
0x1800147c0  mov     [rsp+258h+var_218], 1
0x1800147c5  mov     [rsp+258h+var_217], 1
0x1800147ca  lea     r8, [rsp+258h+var_218]
0x1800147cf  lea     rdx, [rsp+258h+var_217]
0x1800147d4  jmp     loc_180014BA1
0x1800147d9  mov     [rsp+258h+var_1D0], rsi
0x1800147e1  mov     rdi, [rsp+258h+pProxy]
0x1800147e6  mov     rax, [rdi]
0x1800147e9  mov     rbx, [rax+80h]
0x1800147f0  lea     rcx, [rsp+258h+var_1D0]
0x1800147f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147fd  lea     r8, [rsp+258h+var_1D0]
0x180014805  mov     edx, 3
0x18001480a  mov     rcx, rdi
0x18001480d  mov     rax, rbx
0x180014810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014815  mov     rcx, [rsp+258h]; this
0x18001481d  test    eax, eax
0x18001481f  jns     short loc_180014835
0x180014821  mov     r9d, eax; char *
0x180014824  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18001482b  mov     edx, 122h; void *
0x180014830  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014835  mov     [rsp+258h+var_1D8], rsi
0x18001483d  mov     [rsp+258h+var_1C8], esi
0x180014844  mov     rdi, [rsp+258h+var_1D0]
0x18001484c  mov     rax, [rdi]
0x18001484f  mov     rbx, [rax+18h]
0x180014853  lea     rcx, [rsp+258h+var_1D8]
0x18001485b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014860  lea     r9, [rsp+258h+var_1C8]
0x180014868  lea     r8, [rsp+258h+var_1D8]
0x180014870  mov     edx, 1
0x180014875  mov     rcx, rdi
0x180014878  mov     rax, rbx
0x18001487b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014880  mov     rcx, [rsp+258h]; this
0x180014888  test    eax, eax
0x18001488a  jns     short loc_1800148A0
0x18001488c  mov     r9d, eax; char *
0x18001488f  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014896  mov     edx, 126h; void *
0x18001489b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800148a0  jnz     loc_180014B67
0x1800148a6  mov     [rsp+258h+pv], rsi
0x1800148ab  mov     [rsp+258h+var_204], esi
0x1800148af  mov     rcx, [rsp+258h+var_1D8]
0x1800148b7  mov     rax, [rcx]
0x1800148ba  lea     rdx, [rsp+258h+pv]
0x1800148bf  mov     [rsp+258h+var_168], rdx
0x1800148c7  mov     [rsp+258h+var_160], rsi
0x1800148cf  mov     [rsp+258h+var_158], 1
0x1800148d7  lea     r8, [rsp+258h+var_160]
0x1800148df  lea     rdx, [rsp+258h+var_204]
0x1800148e4  mov     rax, [rax+18h]
0x1800148e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148ed  mov     rcx, [rsp+258h]; this
0x1800148f5  test    eax, eax
0x1800148f7  jns     short loc_18001490E
0x1800148f9  mov     r9d, eax; char *
0x1800148fc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014903  mov     edx, 12Ah; void *
0x180014908  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001490e  lea     rcx, [rsp+258h+var_168]
0x180014916  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001491b  mov     r8d, [rsp+258h+var_204]
0x180014920  mov     rdx, [rsp+258h+pv]
0x180014925  lea     rcx, [rsp+258h+var_E8]
0x18001492d  call    ?NetworkSignatureToCDSReferenceId@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBEK@Z; NetworkSignatureToCDSReferenceId(uchar const * const,ulong)
0x180014932  nop
0x180014933  lea     rdx, [rsp+258h+var_E8]
0x18001493b  cmp     [rsp+258h+var_D0], 7
0x180014944  cmova   rdx, [rsp+258h+var_E8]
0x18001494d  mov     r8, cs:?c_wiFiCloudStoreDataReferenceDefaultCollectionName@@3PEBGEB; ushort const * const c_wiFiCloudStoreDataReferenceDefaultCollectionName
0x180014954  lea     rcx, [rsp+258h+var_C8]
0x18001495c  call    ??$make_cloud_store_data_reference@UNlmSignature@Nlm@Data@Windows@@@wil@@YA?AU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(ushort const *,ushort const *)
0x180014961  nop
0x180014962  xor     r9d, r9d
0x180014965  lea     r8, [rsp+258h+var_C8]
0x18001496d  lea     rdx, [rsp+258h+var_138]
0x180014975  lea     rcx, [rsp+258h+var_110]
0x18001497d  call    ??$load@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@1@AEBU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Nlm::NlmSignature>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> const &,wil::cloud_store_load_options,char const *)
0x180014982  nop
0x180014983  cmp     [rsp+258h+var_120], sil
0x18001498b  jnz     loc_180014AEC
0x180014991  movsxd  rax, [rsp+258h+var_1F8]
0x180014996  cmp     qword ptr [rsp+258h+var_138], rax
0x18001499e  jz      loc_180014A69
0x1800149a4  mov     [rsp+258h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800149ac  mov     [rsp+258h+pAuthInfo], rsi; pAuthInfo
0x1800149b1  mov     [rsp+258h+dwImpLevel], 3; dwImpLevel
0x1800149b9  mov     dword ptr [rsp+258h+ppv], esi; int
0x1800149bd  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800149c1  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800149c5  or      edx, r8d; dwAuthnSvc
0x1800149c8  mov     rcx, [rsp+258h+pProxy]; pProxy
0x1800149cd  call    cs:__imp_CoSetProxyBlanket
0x1800149d3  mov     rcx, [rsp+258h]; this
0x1800149db  test    eax, eax
0x1800149dd  jns     short loc_1800149F3
0x1800149df  mov     r9d, eax; char *
0x1800149e2  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800149e9  mov     edx, 146h; void *
0x1800149ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800149f3  mov     rcx, [rsp+258h+pProxy]
0x1800149f8  mov     rax, [rcx]
0x1800149fb  mov     edx, [rsp+258h+var_138]
0x180014a02  mov     rax, [rax+70h]
0x180014a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0b  mov     rcx, [rsp+258h]; this
0x180014a13  test    eax, eax
0x180014a15  jns     short loc_180014A2B
0x180014a17  mov     r9d, eax; char *
0x180014a1a  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180014a21  mov     edx, 148h; void *
0x180014a26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014a2b  lea     rax, [rsp+258h+var_E8]
0x180014a33  cmp     [rsp+258h+var_D0], 7
0x180014a3c  cmova   rax, [rsp+258h+var_E8]
0x180014a45  mov     [rsp+258h+var_1E8], rax
0x180014a4a  lea     r8, [rsp+258h+var_138]
0x180014a52  lea     rdx, [rsp+258h+var_1E8]
0x180014a57  mov     rcx, r14
0x180014a5a  call    ??$AppliedNlmCategory@AEBU_GUID@@PEBGAEA_K@WiFiCloudStoreTelemetry@@SAXAEBU_GUID@@$$QEAPEBGAEA_K@Z; WiFiCloudStoreTelemetry::AppliedNlmCategory<_GUID const &,ushort const *,unsigned __int64 &>(_GUID const &,ushort const * &&,unsigned __int64 &)
0x180014a5f  inc     r13d
0x180014a62  mov     dword ptr [rsp+258h+var_1E8], r13d
0x180014a67  jmp     short loc_180014AA4
0x180014a69  lea     rax, [rsp+258h+var_E8]
0x180014a71  cmp     [rsp+258h+var_D0], 7
0x180014a7a  cmova   rax, [rsp+258h+var_E8]
0x180014a83  mov     [rsp+258h+var_1B8], rax
0x180014a8b  lea     r8, [rsp+258h+var_138]
0x180014a93  lea     rdx, [rsp+258h+var_1B8]
0x180014a9b  mov     rcx, r14
0x180014a9e  call    ??$NlmCategoryUpToDate@AEBU_GUID@@PEBGAEA_K@WiFiCloudStoreTelemetry@@SAXAEBU_GUID@@$$QEAPEBGAEA_K@Z; WiFiCloudStoreTelemetry::NlmCategoryUpToDate<_GUID const &,ushort const *,unsigned __int64 &>(_GUID const &,ushort const * &&,unsigned __int64 &)
0x180014aa3  nop
0x180014aa4  lea     rcx, [rsp+258h+var_128]
0x180014aac  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180014ab1  nop
0x180014ab2  lea     rcx, [rsp+258h+var_C8]
0x180014aba  call    ??1?$ItemReference@UWiFiProfileCost@WiFi@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::WiFi::WiFiProfileCost>::~ItemReference<Windows::Data::WiFi::WiFiProfileCost>(void)
0x180014abf  nop
  ... truncated ...
```
