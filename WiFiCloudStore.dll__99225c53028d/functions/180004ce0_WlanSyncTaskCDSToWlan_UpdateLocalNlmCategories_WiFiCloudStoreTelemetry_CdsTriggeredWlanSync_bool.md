# WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories(WiFiCloudStoreTelemetry::CdsTriggeredWlanSync &,bool)

- ea: `0x180004ce0`
- end: `0x1800056c1`
- name: `?UpdateLocalNlmCategories@WlanSyncTaskCDSToWlan@@AEBAXAEAVCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@_N@Z`
- size: `2529`
- prototype: `void(WlanSyncTaskCDSToWlan *__hidden this, struct WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180012594`

## callees

- `0x180004ce0`
- `0x1800056c8`
- `0x180005700`
- `0x180005880`
- `0x180006460`
- `0x180006b88`
- `0x1800115a0`
- `0x180011690`
- `0x18001adbc`
- `0x18001dfd8`
- `0x1800202e8`
- `0x18002079c`
- `0x180020eec`
- `0x180025308`
- `0x180026bc8`
- `0x18002a030`
- `0x18002a400`
- `0x18002e2d0`
- `0x18002f214`
- `0x18003a3b0`
- `0x18003bb30`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d8a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004d8a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800054c0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800054c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800051d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800051d4`
- `OLEAUT32!__imp_VariantClear` at `0x18000527d`
- `OLEAUT32!__imp_VariantClear` at `0x18000527d`

## string_xrefs

- `0x180005538`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x1800055aa`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x1800055bf`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x1800055dc`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x1800055f1`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180005605`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180005632`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180005646`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
void __fastcall WlanSyncTaskCDSToWlan::UpdateLocalNlmCategories(
        WlanSyncTaskCDSToWlan *this,
        struct WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *a2,
        char a3)
{
  int v4; // esi
  HRESULT v5; // eax
  __int64 v6; // r8
  void **v7; // r15
  void **v8; // r12
  void **v9; // rdx
  __int128 *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // esi
  wil::details_abi *v15; // rcx
  bool v16; // dl
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  struct wil::details::IFunctorHost *v18; // r8
  unsigned int v19; // esi
  int v20; // esi
  LPVOID v21; // rdi
  int (__fastcall *v22)(LPVOID, _QWORD, void *, __int64 *); // rbx
  int v23; // eax
  LPVOID v24; // rdi
  __int64 (__fastcall *v25)(LPVOID, __int128 *, IUnknown **); // rbx
  int v26; // eax
  IUnknown *v27; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  IUnknown *v33; // rcx
  __int64 v34; // rcx
  void *v35; // rcx
  __int64 v36; // rcx
  void *v37; // rcx
  char *v38; // r8
  char *v39; // rdx
  LPVOID v40; // rcx
  HRESULT v41; // eax
  int v42; // eax
  void *v43; // rax
  int ppv; // [rsp+20h] [rbp-228h]
  char v45; // [rsp+40h] [rbp-208h] BYREF
  _BYTE v46[7]; // [rsp+41h] [rbp-207h] BYREF
  char v47[8]; // [rsp+48h] [rbp-200h] BYREF
  unsigned int v48; // [rsp+50h] [rbp-1F8h]
  void *v49; // [rsp+58h] [rbp-1F0h] BYREF
  void *v50; // [rsp+60h] [rbp-1E8h] BYREF
  IUnknown *pProxy; // [rsp+68h] [rbp-1E0h] BYREF
  int v52; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v53; // [rsp+78h] [rbp-1D0h] BYREF
  LPVOID v54; // [rsp+80h] [rbp-1C8h] BYREF
  _QWORD v55[2]; // [rsp+88h] [rbp-1C0h] BYREF
  struct WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *v56; // [rsp+98h] [rbp-1B0h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-1A8h] BYREF
  __int128 v58; // [rsp+B8h] [rbp-190h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-180h]
  __int64 v60; // [rsp+D0h] [rbp-178h]
  __int64 v61; // [rsp+D8h] [rbp-170h]
  void **v62; // [rsp+E0h] [rbp-168h] BYREF
  struct wil::details_abi::ThreadLocalData *v63; // [rsp+E8h] [rbp-160h]
  __int64 v64; // [rsp+F0h] [rbp-158h]
  _QWORD *v65; // [rsp+F8h] [rbp-150h]
  int v66; // [rsp+100h] [rbp-148h]
  void **v67; // [rsp+108h] [rbp-140h]
  struct WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *v68; // [rsp+110h] [rbp-138h]
  void **v69; // [rsp+118h] [rbp-130h] BYREF
  void **v70; // [rsp+120h] [rbp-128h]
  _QWORD v71[3]; // [rsp+130h] [rbp-118h] BYREF
  __int16 v72; // [rsp+148h] [rbp-100h]
  char v73[8]; // [rsp+150h] [rbp-F8h] BYREF
  std::_Ref_count_base *v74; // [rsp+158h] [rbp-F0h]
  std::_Ref_count_base *v75; // [rsp+170h] [rbp-D8h]
  void *v76[2]; // [rsp+178h] [rbp-D0h] BYREF
  __int64 v77; // [rsp+188h] [rbp-C0h]
  unsigned __int64 v78; // [rsp+190h] [rbp-B8h]
  __int128 v79; // [rsp+198h] [rbp-B0h] BYREF
  char *v80; // [rsp+1A8h] [rbp-A0h]
  void **v81; // [rsp+1B0h] [rbp-98h]
  void **v82; // [rsp+1B8h] [rbp-90h]
  __int128 v83; // [rsp+1C0h] [rbp-88h] BYREF
  __int128 v84; // [rsp+1D0h] [rbp-78h]
  _QWORD v85[3]; // [rsp+1E0h] [rbp-68h] BYREF
  __int128 v86; // [rsp+1F8h] [rbp-50h] BYREF
  __int128 v87; // [rsp+208h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v56 = a2;
  v68 = a2;
  v47[0] = a3;
  v4 = 0;
  v48 = 0;
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginProcessingNlmUpdates(a2);
  wil::cloud_store::cloud_store(v73);
  v52 = 0;
  if ( !a3 )
    goto LABEL_56;
  v54 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v54);
  v5 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v54);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33D,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  wil::cloud_store::get_collection_items<Windows::Data::Nlm::NlmSignature>((__int64)v73, (__int64)&v69, v6);
  v7 = v69;
  v8 = v70;
  v67 = v70;
  while ( 1 )
  {
    v55[1] = v7;
    if ( v7 == v8 )
      break;
    *(_OWORD *)v76 = 0;
    v77 = 0;
    v78 = 0;
    std::string::_Construct<1,char const *>(v76, &dword_180043B4C, 0);
    v50 = v7;
    LODWORD(v49) = 0;
    v80 = v73;
    v81 = &v49;
    v82 = &v50;
    v83 = 0;
    v84 = 0;
    v9 = v76;
    if ( v78 > 0xF )
      v9 = (void **)v76[0];
    std::string::_Construct<2,char const *>(&v83, v9, v77);
    v71[0] = retaddr;
    v71[1] = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
    v71[2] = "Load";
    v72 = 1300;
    v85[0] = v80;
    v85[1] = v81;
    v85[2] = v82;
    v86 = 0;
    v87 = 0;
    v10 = &v83;
    if ( *((_QWORD *)&v84 + 1) > 0xFu )
      v10 = (__int128 *)v83;
    std::string::_Construct<2,char const *>(&v86, v10, v84);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl'::`2'::impl,
      v11,
      v12,
      v13);
    v60 = 1;
    v61 = 1;
    v58 = 0u;
    v59 = 0;
    v14 = v4 | 0x20;
    v48 = v14;
    *(_QWORD *)&pvarg.vt = &wil::details::functor_wrapper_other<_lambda_cc1b274828db2bc48063dbe1061c0642_ &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>::`vftable';
    pvarg.llVal = (LONGLONG)v85;
    pvarg.pRecInfo = (IRecordInfo *)&v58;
    v62 = &wil::details::FeatureFunctorHost::`vftable';
    LOBYTE(v15) = 1;
    ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v15, v16);
    v63 = ThreadLocalDataCache;
    v64 = 0;
    if ( ThreadLocalDataCache )
    {
      HIDWORD(v64) = *((_DWORD *)ThreadLocalDataCache + 4);
      LODWORD(v64) = **((_DWORD **)ThreadLocalDataCache + 1);
      *((_DWORD *)v63 + 4) = v64;
    }
    v65 = v71;
    v66 = 6201249;
    wil::details::RunFunctor((wil::details *)&pvarg, (struct wil::details::IFunctor *)&v62, v18);
    if ( v63 )
      *((_DWORD *)v63 + 4) = HIDWORD(v64);
    v19 = v14 & 0xFFFFFFC3 | 0x1C;
    v48 = v19;
    if ( *((_QWORD *)&v87 + 1) > 0xFu )
      std::_Deallocate<16>((void *)v86, *((_QWORD *)&v87 + 1) + 1LL);
    v20 = v19 | 2;
    v48 = v20;
    if ( *((_QWORD *)&v84 + 1) > 0xFu )
      std::_Deallocate<16>((void *)v83, *((_QWORD *)&v84 + 1) + 1LL);
    v4 = v20 | 1;
    v48 = v4;
    if ( v78 > 0xF )
      std::_Deallocate<16>(v76[0], v78 + 1);
    if ( (_BYTE)v60 )
      goto LABEL_40;
    CDSReferenceIdToNetworkSignature(v76, v7);
    v53 = 0;
    v21 = v54;
    v22 = *(int (__fastcall **)(LPVOID, _QWORD, void *, __int64 *))(*(_QWORD *)v54 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    if ( v22(v21, (unsigned int)(LODWORD(v76[1]) - LODWORD(v76[0])), v76[0], &v53) >= 0 )
    {
      v79 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v53 + 32LL))(v53, &v79);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
          (const char *)(unsigned int)v23,
          ppv);
      pProxy = 0;
      v24 = v54;
      v25 = *(__int64 (__fastcall **)(LPVOID, __int128 *, IUnknown **))(*(_QWORD *)v54 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
      v26 = v25(v24, &v79, &pProxy);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x357,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
          (const char *)(unsigned int)v26,
          ppv);
      v55[0] = 0;
      v27 = pProxy;
      QueryInterface = pProxy->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v55);
      v29 = ((__int64 (__fastcall *)(IUnknown *, GUID *, _QWORD *))QueryInterface)(
              v27,
              &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
              v55);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35A,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
          (const char *)(unsigned int)v29,
          ppv);
      VariantInit(&pvarg);
      v30 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v55[0] + 24LL))(
              v55[0],
              L"NA_NetworkClass",
              &pvarg,
              0);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35C,
          (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
          (const char *)(unsigned int)v30,
          ppv);
      if ( pvarg.lVal == 2 && pvarg.vt == 23 )
      {
        LODWORD(v49) = 0;
        v31 = ((__int64 (__fastcall *)(IUnknown *, void **))pProxy->lpVtbl[4].AddRef)(pProxy, &v49);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x360,
            (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
            (const char *)(unsigned int)v31,
            ppv);
        if ( (unsigned int)v49 <= 1 )
        {
          if ( (_QWORD)v58 != (int)v49 )
          {
            v41 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
            if ( v41 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x370,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)(unsigned int)v41,
                ppv);
            v42 = ((__int64 (__fastcall *)(IUnknown *, _QWORD))pProxy->lpVtbl[4].Release)(pProxy, (unsigned int)v58);
            if ( v42 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x371,
                (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
                (const char *)(unsigned int)v42,
                ppv);
            if ( (unsigned __int64)v7[3] <= 7 )
              v43 = v7;
            else
              v43 = *v7;
            v50 = v43;
            WiFiCloudStoreTelemetry::AppliedNlmCategory<_GUID &,unsigned short const *,unsigned __int64 &>(
              &v79,
              &v50,
              &v58);
            ++v52;
          }
          goto LABEL_30;
        }
        v45 = 1;
        v46[0] = 1;
        v38 = &v45;
        v39 = v46;
      }
      else
      {
        v46[0] = 0;
        v45 = 0;
        v38 = v46;
        v39 = &v45;
      }
      WiFiCloudStoreTelemetry::NlmSkippingNetwork<_GUID &,bool,bool>(&v79, v39, v38);
LABEL_30:
      VariantClear(&pvarg);
      v32 = v55[0];
      if ( v55[0] )
      {
        v55[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v33->lpVtbl->Release)(v33);
      }
      v34 = v53;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = v76[0];
      if ( v76[0] )
      {
        v50 = (void *)(v77 - (unsigned __int64)v76[0]);
        v49 = v76[0];
        if ( v77 - (unsigned __int64)v76[0] >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v49, (unsigned __int64 *)&v50);
          v35 = v49;
        }
        operator delete(v35);
      }
LABEL_40:
      if ( v59 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      goto LABEL_42;
    }
    v36 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v76[0];
    if ( v76[0] )
    {
      v49 = (void *)(v77 - (unsigned __int64)v76[0]);
      v50 = v76[0];
      if ( v77 - (unsigned __int64)v76[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v50, (unsigned __int64 *)&v49);
        v37 = v50;
      }
      operator delete(v37);
      *(_OWORD *)v76 = 0;
      v77 = 0;
    }
    if ( v59 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
LABEL_42:
    v7 += 8;
  }
  std::vector<Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature>>::_Tidy(&v69);
  v40 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
  }
LABEL_56:
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::NlmUpdatesComplete<unsigned int &,bool const &>(
    (__int64)v56,
    &v52,
    v47);
  if ( v75 )
    std::_Ref_count_base::_Decref(v75);
  if ( v74 )
    std::_Ref_count_base::_Decref(v74);
}

```

## disassembly

```asm
0x180004ce0  mov     [rsp+arg_0], rbx
0x180004ce5  mov     [rsp+arg_18], rsi
0x180004cea  push    rdi
0x180004ceb  push    r12
0x180004ced  push    r13
0x180004cef  push    r14
0x180004cf1  push    r15
0x180004cf3  sub     rsp, 220h
0x180004cfa  mov     rax, cs:__security_cookie
0x180004d01  xor     rax, rsp
0x180004d04  mov     [rsp+248h+var_30], rax
0x180004d0c  movzx   ebx, r8b
0x180004d10  mov     [rsp+248h+var_1B0], rdx
0x180004d18  mov     [rsp+248h+var_138], rdx
0x180004d20  mov     [rsp+248h+var_200], bl
0x180004d24  xor     r14d, r14d
0x180004d27  mov     esi, r14d
0x180004d2a  mov     [rsp+248h+var_1F8], r14d
0x180004d2f  mov     rcx, rdx; this
0x180004d32  call    ?BeginProcessingNlmUpdates@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAXXZ; WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::BeginProcessingNlmUpdates(void)
0x180004d37  lea     rcx, [rsp+248h+var_F8]
0x180004d3f  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x180004d44  nop
0x180004d45  mov     [rsp+248h+var_1D8], r14d
0x180004d4a  test    bl, bl
0x180004d4c  jz      loc_18000542A
0x180004d52  mov     [rsp+248h+var_1C8], r14
0x180004d5a  lea     rcx, [rsp+248h+var_1C8]
0x180004d62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004d67  lea     rax, [rsp+248h+var_1C8]
0x180004d6f  mov     [rsp+248h+ppv], rax; int
0x180004d74  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180004d7b  xor     edx, edx; pUnkOuter
0x180004d7d  mov     r8d, 4; dwClsContext
0x180004d83  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180004d8a  call    cs:__imp_CoCreateInstance
0x180004d90  mov     rcx, [rsp+248h]; this
0x180004d98  test    eax, eax
0x180004d9a  js      loc_180005535
0x180004da0  lea     rdx, [rsp+248h+var_130]
0x180004da8  lea     rcx, [rsp+248h+var_F8]
0x180004db0  call    ??$get_collection_items@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@QEAA?AV?$vector@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@V?$allocator@U?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@std@@@std@@PEBGW4cloud_store_load_options@1@W4cloud_store_collection_options@1@PEBD@Z; wil::cloud_store::get_collection_items<Windows::Data::Nlm::NlmSignature>(ushort const *,wil::cloud_store_load_options,wil::cloud_store_collection_options,char const *)
0x180004db5  nop
0x180004db6  mov     r15, [rsp+248h+var_130]
0x180004dbe  mov     r12, [rsp+248h+var_128]
0x180004dc6  mov     [rsp+248h+var_140], r12
0x180004dce  lea     rdi, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180004dd5  lea     r13, ??_7?$functor_wrapper_other@AEAV_lambda_cc1b274828db2bc48063dbe1061c0642_@@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@details@wil@@6B@; const wil::details::functor_wrapper_other<_lambda_cc1b274828db2bc48063dbe1061c0642_ &,wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>::`vftable'
0x180004ddc  lea     rbx, ??_7FeatureFunctorHost@details@wil@@6B@; const wil::details::FeatureFunctorHost::`vftable'
0x180004de3  mov     [rsp+248h+var_1B8], r15
0x180004deb  cmp     r15, r12
0x180004dee  jz      loc_1800053FA
0x180004df4  xorps   xmm0, xmm0
0x180004df7  movups  xmmword ptr [rsp+248h+var_D0], xmm0
0x180004dff  mov     [rsp+248h+var_C0], r14
0x180004e07  mov     [rsp+248h+var_B8], r14
0x180004e0f  xor     r8d, r8d
0x180004e12  lea     rdx, dword_180043B4C
0x180004e19  lea     rcx, [rsp+248h+var_D0]
0x180004e21  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004e26  nop
0x180004e27  mov     [rsp+248h+var_1E8], r15
0x180004e2c  mov     dword ptr [rsp+248h+var_1F0], r14d
0x180004e31  lea     rax, [rsp+248h+var_F8]
0x180004e39  mov     [rsp+248h+var_A0], rax
0x180004e41  lea     rax, [rsp+248h+var_1F0]
0x180004e46  mov     [rsp+248h+var_98], rax
0x180004e4e  lea     rax, [rsp+248h+var_1E8]
0x180004e53  mov     [rsp+248h+var_90], rax
0x180004e5b  xorps   xmm0, xmm0
0x180004e5e  movups  [rsp+248h+var_88], xmm0
0x180004e66  xorps   xmm1, xmm1
0x180004e69  movdqu  [rsp+248h+var_78], xmm1
0x180004e72  lea     rdx, [rsp+248h+var_D0]
0x180004e7a  cmp     [rsp+248h+var_B8], 0Fh
0x180004e83  cmova   rdx, [rsp+248h+var_D0]
0x180004e8c  mov     r8, [rsp+248h+var_C0]
0x180004e94  lea     rcx, [rsp+248h+var_88]
0x180004e9c  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180004ea1  nop
0x180004ea2  mov     rax, [rsp+248h]
0x180004eaa  mov     [rsp+248h+var_118], rax
0x180004eb2  mov     [rsp+248h+var_110], rdi
0x180004eba  lea     rax, aLoad; "Load"
0x180004ec1  mov     [rsp+248h+var_108], rax
0x180004ec9  mov     eax, 514h
0x180004ece  mov     [rsp+248h+var_100], ax
0x180004ed6  mov     rax, [rsp+248h+var_A0]
0x180004ede  mov     [rsp+248h+var_68], rax
0x180004ee6  mov     rax, [rsp+248h+var_98]
0x180004eee  mov     [rsp+248h+var_60], rax
0x180004ef6  mov     rax, [rsp+248h+var_90]
0x180004efe  mov     [rsp+248h+var_58], rax
0x180004f06  xorps   xmm0, xmm0
0x180004f09  movups  [rsp+248h+var_50], xmm0
0x180004f11  xorps   xmm1, xmm1
0x180004f14  movdqu  [rsp+248h+var_40], xmm1
0x180004f1d  lea     rdx, [rsp+248h+var_88]
0x180004f25  cmp     qword ptr [rsp+248h+var_78+8], 0Fh
0x180004f2e  cmova   rdx, qword ptr [rsp+248h+var_88]
0x180004f37  mov     r8, qword ptr [rsp+248h+var_78]
0x180004f3f  lea     rcx, [rsp+248h+var_50]
0x180004f47  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x180004f4c  nop
0x180004f4d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudStore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore> `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl(void)'::`2'::impl
0x180004f54  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180004f59  nop
0x180004f5a  xorps   xmm0, xmm0
0x180004f5d  xor     eax, eax
0x180004f5f  movups  [rsp+248h+var_190], xmm0
0x180004f67  movups  [rsp+248h+var_180], xmm0
0x180004f6f  mov     [rsp+248h+var_170], rax
0x180004f77  mov     qword ptr [rsp+248h+var_190], r14
0x180004f7f  mov     qword ptr [rsp+248h+var_180], r14
0x180004f87  mov     word ptr [rsp+248h+var_180+8], 1
0x180004f91  mov     byte ptr [rsp+248h+var_170], 1
0x180004f99  or      esi, 20h
0x180004f9c  mov     [rsp+248h+var_1F8], esi
0x180004fa0  mov     qword ptr [rsp+248h+pvarg], r13
0x180004fa8  lea     rax, [rsp+248h+var_68]
0x180004fb0  mov     qword ptr [rsp+248h+pvarg+8], rax
0x180004fb8  lea     rax, [rsp+248h+var_190]
0x180004fc0  mov     qword ptr [rsp+248h+pvarg+10h], rax
0x180004fc8  mov     [rsp+248h+var_168], rbx
0x180004fd0  mov     cl, 1; this
0x180004fd2  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004fd7  mov     [rsp+248h+var_160], rax
0x180004fdf  mov     [rsp+248h+var_158], 0
0x180004feb  test    rax, rax
0x180004fee  jz      short loc_180005012
0x180004ff0  mov     ecx, [rax+10h]
0x180004ff3  mov     dword ptr [rsp+248h+var_158+4], ecx
0x180004ffa  mov     rcx, [rax+8]
0x180004ffe  mov     eax, [rcx]
0x180005000  mov     dword ptr [rsp+248h+var_158], eax
0x180005007  mov     rcx, [rsp+248h+var_160]
0x18000500f  mov     [rcx+10h], eax
0x180005012  lea     rax, [rsp+248h+var_118]
0x18000501a  mov     [rsp+248h+var_150], rax
0x180005022  mov     [rsp+248h+var_148], 5E9FA1h
0x18000502d  lea     rdx, [rsp+248h+var_168]; struct wil::details::IFunctor *
0x180005035  lea     rcx, [rsp+248h+pvarg]; this
0x18000503d  call    ?RunFunctor@details@wil@@YAJAEAUIFunctor@12@AEAUIFunctorHost@12@@Z; wil::details::RunFunctor(wil::details::IFunctor &,wil::details::IFunctorHost &)
0x180005042  nop
0x180005043  mov     rcx, [rsp+248h+var_160]
0x18000504b  test    rcx, rcx
0x18000504e  jz      short loc_18000505A
0x180005050  mov     eax, dword ptr [rsp+248h+var_158+4]
0x180005057  mov     [rcx+10h], eax
0x18000505a  and     esi, 0FFFFFFDFh
0x18000505d  or      esi, 1Ch
0x180005060  mov     [rsp+248h+var_1F8], esi
0x180005064  mov     rdx, qword ptr [rsp+248h+var_40+8]
0x18000506c  cmp     rdx, 0Fh
0x180005070  ja      loc_18000554A
0x180005076  or      esi, 2
0x180005079  mov     [rsp+248h+var_1F8], esi
0x18000507d  mov     rdx, qword ptr [rsp+248h+var_78+8]
0x180005085  cmp     rdx, 0Fh
0x180005089  ja      loc_18000555F
0x18000508f  or      esi, 1
0x180005092  mov     [rsp+248h+var_1F8], esi
0x180005096  mov     rdx, [rsp+248h+var_B8]
0x18000509e  cmp     rdx, 0Fh
0x1800050a2  ja      loc_180005574
0x1800050a8  cmp     byte ptr [rsp+248h+var_180+8], 0
0x1800050b0  jnz     loc_180005320
0x1800050b6  mov     rdx, r15
0x1800050b9  lea     rcx, [rsp+248h+var_D0]
0x1800050c1  call    ?CDSReferenceIdToNetworkSignature@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; CDSReferenceIdToNetworkSignature(std::wstring const &)
0x1800050c6  nop
0x1800050c7  mov     [rsp+248h+var_1D0], r14
0x1800050cc  mov     rdi, [rsp+248h+var_1C8]
0x1800050d4  mov     rax, [rdi]
0x1800050d7  mov     rbx, [rax+48h]
0x1800050db  lea     rcx, [rsp+248h+var_1D0]
0x1800050e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800050e5  mov     r8, [rsp+248h+var_D0]
0x1800050ed  mov     edx, dword ptr [rsp+248h+var_D0+8]
0x1800050f4  sub     edx, r8d
0x1800050f7  lea     r9, [rsp+248h+var_1D0]
0x1800050fc  mov     rcx, rdi
0x1800050ff  mov     rax, rbx
0x180005102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005107  test    eax, eax
0x180005109  js      loc_180005343
0x18000510f  xorps   xmm0, xmm0
0x180005112  movups  [rsp+248h+var_B0], xmm0
0x18000511a  mov     rcx, [rsp+248h+var_1D0]
0x18000511f  mov     rax, [rcx]
0x180005122  lea     rdx, [rsp+248h+var_B0]
0x18000512a  mov     rax, [rax+20h]
0x18000512e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005133  mov     rcx, [rsp+248h]; this
0x18000513b  test    eax, eax
0x18000513d  js      loc_1800055A7
0x180005143  mov     [rsp+248h+pProxy], r14
0x180005148  mov     rdi, [rsp+248h+var_1C8]
0x180005150  mov     rax, [rdi]
0x180005153  mov     rbx, [rax+30h]
0x180005157  lea     rcx, [rsp+248h+pProxy]
0x18000515c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005161  lea     r8, [rsp+248h+pProxy]
0x180005166  lea     rdx, [rsp+248h+var_B0]
0x18000516e  mov     rcx, rdi
0x180005171  mov     rax, rbx
0x180005174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005179  mov     rcx, [rsp+248h]; this
0x180005181  test    eax, eax
0x180005183  js      loc_1800055BC
0x180005189  mov     [rsp+248h+var_1C0], r14
0x180005191  mov     rbx, [rsp+248h+pProxy]
0x180005196  mov     rax, [rbx]
0x180005199  mov     rdi, [rax]
0x18000519c  lea     rcx, [rsp+248h+var_1C0]
0x1800051a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800051a9  lea     r8, [rsp+248h+var_1C0]
0x1800051b1  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800051b8  mov     rcx, rbx
0x1800051bb  mov     rax, rdi
0x1800051be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c3  nop
0x1800051c4  test    eax, eax
0x1800051c6  js      loc_1800055D1
0x1800051cc  lea     rcx, [rsp+248h+pvarg]; pvarg
0x1800051d4  call    cs:__imp_VariantInit
0x1800051da  nop
0x1800051db  mov     rcx, [rsp+248h+var_1C0]
0x1800051e3  mov     rax, [rcx]
0x1800051e6  xor     r9d, r9d
0x1800051e9  lea     r8, [rsp+248h+pvarg]
0x1800051f1  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800051f8  mov     rax, [rax+18h]
0x1800051fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005201  mov     rcx, [rsp+248h]; this
0x180005209  test    eax, eax
0x18000520b  js      loc_1800055EE
0x180005211  cmp     dword ptr [rsp+248h+pvarg+8], 2
0x180005219  jnz     loc_1800053D4
0x18000521f  cmp     word ptr [rsp+248h+pvarg], 17h
0x180005228  jnz     loc_1800053D4
0x18000522e  mov     dword ptr [rsp+248h+var_1F0], r14d
0x180005233  mov     rcx, [rsp+248h+pProxy]
0x180005238  mov     rax, [rcx]
0x18000523b  lea     rdx, [rsp+248h+var_1F0]
0x180005240  mov     rax, [rax+68h]
0x180005244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005249  mov     rcx, [rsp+248h]; this
0x180005251  test    eax, eax
0x180005253  js      loc_180005602
0x180005259  movsxd  rax, dword ptr [rsp+248h+var_1F0]
0x18000525e  cmp     eax, 1
0x180005261  ja      loc_180005616
0x180005267  cmp     qword ptr [rsp+248h+var_190], rax
0x18000526f  jnz     loc_180005492
0x180005275  lea     rcx, [rsp+248h+pvarg]; pvarg
0x18000527d  call    cs:__imp_VariantClear
0x180005283  nop
0x180005284  mov     rcx, [rsp+248h+var_1C0]
0x18000528c  test    rcx, rcx
0x18000528f  jz      short loc_1800052A6
0x180005291  mov     [rsp+248h+var_1C0], r14
0x180005299  mov     rax, [rcx]
0x18000529c  mov     rax, [rax+10h]
0x1800052a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a5  nop
0x1800052a6  mov     rcx, [rsp+248h+pProxy]
0x1800052ab  test    rcx, rcx
0x1800052ae  jz      short loc_1800052C2
0x1800052b0  mov     [rsp+248h+pProxy], r14
0x1800052b5  mov     rax, [rcx]
0x1800052b8  mov     rax, [rax+10h]
0x1800052bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c1  nop
0x1800052c2  mov     rcx, [rsp+248h+var_1D0]
0x1800052c7  test    rcx, rcx
0x1800052ca  jz      short loc_1800052DE
0x1800052cc  mov     [rsp+248h+var_1D0], r14
0x1800052d1  mov     rax, [rcx]
0x1800052d4  mov     rax, [rax+10h]
0x1800052d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052dd  nop
0x1800052de  mov     rcx, [rsp+248h+var_D0]; void *
0x1800052e6  test    rcx, rcx
0x1800052e9  jz      short loc_180005312
0x1800052eb  mov     rdx, [rsp+248h+var_C0]
0x1800052f3  sub     rdx, rcx; unsigned __int64
0x1800052f6  mov     [rsp+248h+var_1E8], rdx
0x1800052fb  mov     [rsp+248h+var_1F0], rcx
0x180005300  cmp     rdx, 1000h
0x180005307  jnb     loc_180005658
0x18000530d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005312  lea     rdi, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180005319  lea     rbx, ??_7FeatureFunctorHost@details@wil@@6B@; const wil::details::FeatureFunctorHost::`vftable'
0x180005320  mov     rcx, qword ptr [rsp+248h+var_180]
0x180005328  test    rcx, rcx
0x18000532b  jz      short loc_18000533A
0x18000532d  mov     rax, [rcx]
0x180005330  mov     rax, [rax+10h]
0x180005334  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
