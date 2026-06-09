# Appx::Packaging::Production::BundleManifestWriterHelper::AddExternalPackageReferenceFromManifest(ushort const *,IAppxManifestReader *,bool,bool)

- ea: `0x180075c34`
- end: `0x1800764c4`
- name: `?AddExternalPackageReferenceFromManifest@BundleManifestWriterHelper@Production@Packaging@Appx@@QEAAJPEBGPEAUIAppxManifestReader@@_N2@Z`
- size: `2192`
- prototype: `int(Appx::Packaging::Production::BundleManifestWriterHelper *__hidden this, const unsigned __int16 *, struct IAppxManifestReader *, bool, bool)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f292c`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x18000fb60`
- `0x1800133fc`
- `0x180028dd0`
- `0x180028e00`
- `0x18004400c`
- `0x1800446d0`
- `0x1800447a8`
- `0x180044a14`
- `0x1800562a4`
- `0x18006bee8`
- `0x180074678`
- `0x180075c34`
- `0x180076fd4`
- `0x1800efe5c`
- `0x1800f2620`
- `0x1800f26bc`
- `0x1800f2728`
- `0x1800f2900`
- `0x1800f314c`
- `0x1800f4208`
- `0x180106010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x180076065`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180076065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075f27`

## string_xrefs

- `0x180075c74`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075cbe`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075d10`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075d9d`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075e29`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075e7a`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075ed2`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075f9d`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075fda`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180076034`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x1800760d6`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x1800761af`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180076319`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x1800763ea`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::BundleManifestWriterHelper::AddExternalPackageReferenceFromManifest(
        Appx::Packaging::Production::BundleManifestWriterHelper *this,
        unsigned __int16 *a2,
        struct IAppxManifestReader *a3,
        unsigned __int8 a4,
        bool a5)
{
  const unsigned __int16 *v6; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // eax
  unsigned int v22; // edi
  int v23; // eax
  const unsigned __int16 *v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  struct IAppxManifestReaderVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetPackageId)(IAppxManifestReader *, IAppxManifestPackageId **); // rbx
  int v29; // eax
  int v30; // eax
  struct IAppxManifestPackageId *v31; // rdi
  HRESULT (__stdcall *GetPackageFamilyName)(IAppxManifestPackageId *, LPWSTR *); // rbx
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  PVOID v36; // rax
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *v37; // r15
  struct IAppxManifestPackageId *v38; // rdi
  HRESULT (__stdcall *GetName)(IAppxManifestPackageId *, LPWSTR *); // rbx
  int v40; // eax
  __int64 v41; // rdx
  unsigned int v42; // edx
  struct IAppxManifestPackageId *v43; // rsi
  HRESULT (__stdcall *GetPublisher)(IAppxManifestPackageId *, LPWSTR *); // rdi
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *v45; // r14
  int PayloadPackageType; // eax
  __int64 v47; // rdx
  unsigned __int64 v48; // r9
  struct IAppxManifestPackageId *v49; // rsi
  HRESULT (__stdcall *GetResourceId)(IAppxManifestPackageId *, LPWSTR *); // rdi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r9
  __int64 (__fastcall ***v54)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v55)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v56; // r8
  const char *v57; // r9
  __int64 (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v59)(_QWORD, GUID *, __int64 *); // rdi
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(__int64, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *); // rdi
  int v65; // [rsp+28h] [rbp-61h]
  __int64 v66; // [rsp+38h] [rbp-51h] BYREF
  __int64 v67; // [rsp+40h] [rbp-49h] BYREF
  struct IAppxManifestPackageId *v68; // [rsp+48h] [rbp-41h] BYREF
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *v69; // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall ***v71)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-29h] BYREF
  int v72; // [rsp+68h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-19h] BYREF
  __int64 v74; // [rsp+78h] [rbp-11h] BYREF
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *Buffer[2]; // [rsp+80h] [rbp-9h] BYREF
  PCNZWCH lpString2; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v77[8]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+57h]

  v6 = a2;
  v8 = Appx::Packaging::Production::BundleManifestWriterHelper::ValidatePayloadPackageExtension(this, a2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v77[0] = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v77);
    v10 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, GUID *, _QWORD *))a3->lpVtbl->QueryInterface)(
            a3,
            &GUID_8d7ae132_a690_4c00_b75a_6aae1feaac80,
            v77);
    v9 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)(unsigned int)v10,
        v65);
LABEL_100:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v77);
      return v9;
    }
    v11 = v77[0];
    v66 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v77[0] + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
    v13 = v12(v11, &v66);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 450;
LABEL_7:
      v15 = (unsigned int)v13;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)v15,
        v65);
LABEL_9:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      goto LABEL_100;
    }
    v72 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v66 + 32LL))(v66, &v72);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 452;
      goto LABEL_7;
    }
    if ( !v72 )
    {
      v9 = -2146958844;
      v14 = 456;
      v15 = 2148008452LL;
      goto LABEL_8;
    }
    v16 = v66;
    v67 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    v18 = v17(v16, &v67);
    v9 = v18;
    if ( v18 < 0 )
    {
      v19 = 458;
LABEL_16:
      v20 = (unsigned int)v18;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)v20,
        v65);
LABEL_18:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      goto LABEL_9;
    }
    if ( !*((_QWORD *)this + 116) )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v67 + 24LL))(v67, (char *)this + 928);
      v9 = v18;
      if ( v18 < 0 )
      {
        v19 = 462;
        goto LABEL_16;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v67 + 32LL))(v67, (char *)this + 936);
      v9 = v18;
      if ( v18 < 0 )
      {
        v19 = 463;
        goto LABEL_16;
      }
LABEL_35:
      v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v66 + 40LL))(v66, &v72);
      v9 = v18;
      if ( v18 < 0 )
      {
        v19 = 483;
        goto LABEL_16;
      }
      if ( v72 )
      {
        v9 = -2146958844;
        v19 = 484;
        v20 = 2148008452LL;
        goto LABEL_17;
      }
      lpVtbl = a3->lpVtbl;
      v70 = 0;
      GetPackageId = lpVtbl->GetPackageId;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
      v29 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))GetPackageId)(
              a3,
              &v70);
      v9 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E8,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
          (const char *)(unsigned int)v29,
          v65);
LABEL_41:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
        goto LABEL_18;
      }
      v68 = 0;
      v30 = Microsoft::WRL::ComPtr<IAppxManifestPackageId>::As<IAppxManifestPackageId2>(&v70, (__int64)&v68);
      v9 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EB,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
          (const char *)(unsigned int)v30,
          v65);
LABEL_44:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
        goto LABEL_41;
      }
      v31 = v68;
      v69 = 0;
      GetPackageFamilyName = v68->lpVtbl->GetPackageFamilyName;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v69,
        0);
      v33 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE **))GetPackageFamilyName)(
              v31,
              &v69);
      v9 = v33;
      if ( v33 < 0 )
      {
        v34 = (unsigned int)v33;
        v35 = 494;
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
          (const char *)v34,
          v65);
LABEL_48:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v69);
        goto LABEL_44;
      }
      Buffer[0] = v69;
      Buffer[1] = 0;
      v36 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 992), Buffer);
      if ( !v36 || (v37 = (enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *)*((_QWORD *)v36 + 1)) == 0 )
      {
        wil::make_unique_nothrow<Appx::Packaging::BundleManifest::OptionalBundleInfo,>(Buffer);
        v37 = Buffer[0];
        if ( !Buffer[0] )
        {
          v9 = -2147024882;
          v35 = 500;
          v34 = 2147942414LL;
          goto LABEL_47;
        }
        v38 = v68;
        GetName = v68->lpVtbl->GetName;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          Buffer[0],
          0);
        v40 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))GetName)(
                v38,
                v37);
        v9 = v40;
        if ( v40 < 0 )
        {
          v41 = 502;
          goto LABEL_55;
        }
        v43 = v68;
        GetPublisher = v68->lpVtbl->GetPublisher;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          v37 + 2,
          0);
        v40 = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))GetPublisher)(
                v43,
                v37 + 2);
        v9 = v40;
        if ( v40 < 0 )
        {
          v41 = 503;
          goto LABEL_55;
        }
        *((_QWORD *)v37 + 2) = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          v37 + 6,
          0);
        v40 = Common::GenericMap<unsigned short const *,unsigned short const *>::Insert((char *)this + 992, v69, v37);
        v9 = v40;
        if ( v40 < 0 )
        {
          v41 = 507;
LABEL_55:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v41,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
            (const char *)(unsigned int)v40,
            v65);
          if ( v37 )
            Appx::Packaging::BundleManifest::OptionalBundleInfo::`scalar deleting destructor'(
              (Appx::Packaging::BundleManifest::OptionalBundleInfo *)v37,
              v42);
          goto LABEL_48;
        }
        v6 = a2;
        v69 = 0;
      }
      wil::make_unique_nothrow<Appx::Packaging::BundleManifest::PackageInfo,>(Buffer);
      v45 = Buffer[0];
      if ( !Buffer[0] )
      {
        v9 = -2147024882;
        v35 = 514;
        v34 = 2147942414LL;
        goto LABEL_47;
      }
      PayloadPackageType = Appx::Packaging::BundleValidationHelper::GetPayloadPackageType(a3, v6, Buffer[0]);
      v9 = PayloadPackageType;
      if ( PayloadPackageType < 0 )
      {
        v47 = 516;
LABEL_66:
        v48 = (unsigned int)PayloadPackageType;
LABEL_67:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v47,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
          (const char *)v48,
          v65);
        goto LABEL_68;
      }
      PayloadPackageType = Appx::Packaging::BundleValidationHelper::AddPackage(
                             (Appx::Packaging::BundleValidationHelper *)(v37 + 16),
                             *v45,
                             v68,
                             a5,
                             v6);
      v9 = PayloadPackageType;
      if ( PayloadPackageType < 0 )
      {
        v47 = 517;
        goto LABEL_66;
      }
      if ( *v45 == APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE_APPLICATION )
      {
        PayloadPackageType = Appx::Packaging::BundleValidationHelper::ValidateApplicationElement(a3, v6);
        v9 = PayloadPackageType;
        if ( PayloadPackageType < 0 )
        {
          v47 = 520;
          goto LABEL_66;
        }
        Buffer[0] = (enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *)a3;
        Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(Buffer);
        v9 = Appx::Packaging::ManifestComparisonHelper::AddManifest(v37 + 244, Buffer, a5, v6);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(Buffer);
        if ( (v9 & 0x80000000) != 0 )
        {
          v48 = v9;
          v47 = 521;
          goto LABEL_67;
        }
      }
      PayloadPackageType = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))v68->lpVtbl[1].QueryInterface)(
                             v68,
                             v45 + 4);
      v9 = PayloadPackageType;
      if ( PayloadPackageType < 0 )
      {
        v47 = 524;
        goto LABEL_66;
      }
      PayloadPackageType = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))v68->lpVtbl->GetVersion)(
                             v68,
                             v45 + 2);
      v9 = PayloadPackageType;
      if ( PayloadPackageType < 0 )
      {
        v47 = 525;
        goto LABEL_66;
      }
      v49 = v68;
      GetResourceId = v68->lpVtbl->GetResourceId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v45 + 6,
        0);
      PayloadPackageType = ((__int64 (__fastcall *)(struct IAppxManifestPackageId *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))GetResourceId)(
                             v49,
                             v45 + 6);
      v9 = PayloadPackageType;
      if ( PayloadPackageType < 0 )
      {
        v47 = 526;
        goto LABEL_66;
      }
      v71 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
      v51 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, GUID *, _QWORD))a3->lpVtbl->QueryInterface)(
              a3,
              &GUID_d06f67bc_b31d_4eba_a8af_638e73e77b4d,
              &v71);
      v9 = v51;
      if ( v51 >= 0 )
      {
        *((_DWORD *)v45 + 16) = a4;
        v54 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v71;
        v55 = (*v71)[12];
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v45 + 14);
        v51 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))v55)(
                v54,
                v45 + 14);
        v9 = v51;
        if ( v51 >= 0 )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            Buffer,
            (char *)a2,
            v56,
            v57);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            v45 + 8,
            Buffer);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Buffer);
          if ( *((_QWORD *)v45 + 4) )
          {
            *((_QWORD *)v45 + 6) = 0;
            *((_QWORD *)v45 + 5) = 0;
            v58 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v71;
            v74 = 0;
            v59 = **v71;
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
            v60 = v59(v58, &GUID_c43825ab_69b7_400a_9709_cc37f5a72d24, &v74);
            v9 = v60;
            if ( v60 >= 0 )
            {
              v62 = v74;
              v63 = *(__int64 (__fastcall **)(__int64, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))(*(_QWORD *)v74 + 112LL);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v45 + 18);
              v60 = v63(v62, v45 + 18);
              v9 = v60;
              if ( v60 >= 0 )
              {
                *((_DWORD *)v45 + 20) = a5;
                v60 = Appx::Packaging::Production::BundleManifestWriterHelper::AddPackageInfoToArray(this, v37 + 8, v45);
                v9 = v60;
                if ( v60 >= 0 )
                {
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v69);
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
                  v9 = 0;
                  goto LABEL_100;
                }
                v61 = 543;
              }
              else
              {
                v61 = 540;
              }
            }
            else
            {
              v61 = 539;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v61,
              (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
              (const char *)(unsigned int)v60,
              v65);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
            goto LABEL_87;
          }
          v9 = -2147024882;
          v52 = 533;
          v53 = 2147942414LL;
LABEL_86:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
            (const char *)v53,
            v65);
LABEL_87:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
LABEL_68:
          if ( v45 )
            Appx::Packaging::BundleManifest::PackageInfo::`scalar deleting destructor'(
              (Appx::Packaging::BundleManifest::PackageInfo *)v45,
              1u);
          goto LABEL_48;
        }
        v52 = 531;
      }
      else
      {
        v52 = 529;
      }
      v53 = (unsigned int)v51;
      goto LABEL_86;
    }
    pv = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v67 + 24LL))(v67, &pv);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)(unsigned int)v21,
        v65);
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      v9 = v22;
      goto LABEL_100;
    }
    if ( Common::String::CaseInsensitiveEquals(*((const unsigned __int16 **)this + 116), (const unsigned __int16 *)pv) )
    {
      lpString2 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v67 + 32LL))(v67, &lpString2);
      v9 = v23;
      if ( v23 >= 0 )
      {
        if ( Appx::Packaging::IsPublisherNameEqual(*((PCNZWCH *)this + 117), lpString2, v24) )
        {
          CoTaskMemFree((LPVOID)lpString2);
          CoTaskMemFree(pv);
          goto LABEL_35;
        }
        v9 = -2146958844;
        v26 = 478;
        v25 = 2148008452LL;
      }
      else
      {
        v25 = (unsigned int)v23;
        v26 = 475;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)v25,
        v65);
      CoTaskMemFree((LPVOID)lpString2);
    }
    else
    {
      v9 = -2146958844;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)0x80080204LL,
        v65);
    }
    CoTaskMemFree(pv);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BD,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
    (const char *)(unsigned int)v8,
    v65);
  return v9;
}

```

## disassembly

```asm
0x180075c34  mov     rax, rsp
0x180075c37  mov     [rax+8], rbx
0x180075c3b  mov     [rax+20h], r9b
0x180075c3f  mov     [rax+10h], rdx
0x180075c43  push    rbp
0x180075c44  push    rsi
0x180075c45  push    rdi
0x180075c46  push    r12
0x180075c48  push    r13
0x180075c4a  push    r14
0x180075c4c  push    r15
0x180075c4e  lea     rbp, [rax-57h]
0x180075c52  sub     rsp, 0A0h
0x180075c59  mov     r12, r8
0x180075c5c  mov     rsi, rdx
0x180075c5f  mov     r13, rcx
0x180075c62  call    ?ValidatePayloadPackageExtension@BundleManifestWriterHelper@Production@Packaging@Appx@@AEAAJPEBG@Z; Appx::Packaging::Production::BundleManifestWriterHelper::ValidatePayloadPackageExtension(ushort const *)
0x180075c67  xor     r15d, r15d
0x180075c6a  mov     ebx, eax
0x180075c6c  test    eax, eax
0x180075c6e  jns     short loc_180075C8D
0x180075c70  mov     rcx, [rbp+57h]; this
0x180075c74  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075c7b  mov     r9d, eax; char *
0x180075c7e  mov     edx, 1BDh; void *
0x180075c83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075c88  jmp     loc_1800764A6
0x180075c8d  lea     rcx, [rbp+4Fh+var_40]
0x180075c91  mov     [rbp+4Fh+var_40], r15
0x180075c95  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075c9a  mov     rax, [r12]
0x180075c9e  lea     r8, [rbp+4Fh+var_40]
0x180075ca2  lea     rdx, _GUID_8d7ae132_a690_4c00_b75a_6aae1feaac80
0x180075ca9  mov     rcx, r12
0x180075cac  mov     rax, [rax]
0x180075caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cb4  mov     ebx, eax
0x180075cb6  test    eax, eax
0x180075cb8  jns     short loc_180075CD7
0x180075cba  mov     rcx, [rbp+57h]; this
0x180075cbe  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075cc5  mov     r9d, eax; char *
0x180075cc8  mov     edx, 1C0h; void *
0x180075ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075cd2  jmp     loc_18007649D
0x180075cd7  mov     rdi, [rbp+4Fh+var_40]
0x180075cdb  lea     rcx, [rbp+4Fh+var_A0]
0x180075cdf  mov     [rbp+4Fh+var_A0], r15
0x180075ce3  mov     rax, [rdi]
0x180075ce6  mov     rbx, [rax+18h]
0x180075cea  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075cef  lea     rdx, [rbp+4Fh+var_A0]
0x180075cf3  mov     rcx, rdi
0x180075cf6  mov     rax, rbx
0x180075cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cfe  mov     ebx, eax
0x180075d00  test    eax, eax
0x180075d02  jns     short loc_180075D2A
0x180075d04  mov     edx, 1C2h; void *
0x180075d09  mov     r9d, eax; char *
0x180075d0c  mov     rcx, [rbp+57h]; this
0x180075d10  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075d17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075d1c  lea     rcx, [rbp+4Fh+var_A0]
0x180075d20  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075d25  jmp     loc_18007649D
0x180075d2a  mov     rcx, [rbp+4Fh+var_A0]
0x180075d2e  lea     rdx, [rbp+4Fh+var_70]
0x180075d32  mov     [rbp+4Fh+var_70], r15d
0x180075d36  mov     rax, [rcx]
0x180075d39  mov     rax, [rax+20h]
0x180075d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d42  mov     ebx, eax
0x180075d44  test    eax, eax
0x180075d46  jns     short loc_180075D4F
0x180075d48  mov     edx, 1C4h
0x180075d4d  jmp     short loc_180075D09
0x180075d4f  cmp     [rbp+4Fh+var_70], r15d
0x180075d53  jnz     short loc_180075D64
0x180075d55  mov     ebx, 80080204h
0x180075d5a  mov     edx, 1C8h
0x180075d5f  mov     r9d, ebx
0x180075d62  jmp     short loc_180075D0C
0x180075d64  mov     rdi, [rbp+4Fh+var_A0]
0x180075d68  lea     rcx, [rbp+4Fh+var_98]
0x180075d6c  mov     [rbp+4Fh+var_98], r15
0x180075d70  mov     rax, [rdi]
0x180075d73  mov     rbx, [rax+18h]
0x180075d77  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075d7c  lea     rdx, [rbp+4Fh+var_98]
0x180075d80  mov     rcx, rdi
0x180075d83  mov     rax, rbx
0x180075d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d8b  mov     ebx, eax
0x180075d8d  test    eax, eax
0x180075d8f  jns     short loc_180075DB7
0x180075d91  mov     edx, 1CAh; void *
0x180075d96  mov     r9d, eax; char *
0x180075d99  mov     rcx, [rbp+57h]; this
0x180075d9d  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075da4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075da9  lea     rcx, [rbp+4Fh+var_98]
0x180075dad  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075db2  jmp     loc_180075D1C
0x180075db7  mov     rcx, [rbp+4Fh+var_98]
0x180075dbb  lea     rbx, [r13+3A0h]
0x180075dc2  cmp     [rbx], r15
0x180075dc5  jnz     short loc_180075E0B
0x180075dc7  mov     rax, [rcx]
0x180075dca  mov     rdx, rbx
0x180075dcd  mov     rax, [rax+18h]
0x180075dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dd6  mov     ebx, eax
0x180075dd8  test    eax, eax
0x180075dda  jns     short loc_180075DE3
0x180075ddc  mov     edx, 1CEh
0x180075de1  jmp     short loc_180075D96
0x180075de3  mov     rcx, [rbp+4Fh+var_98]
0x180075de7  lea     rdx, [r13+3A8h]
0x180075dee  mov     rax, [rcx]
0x180075df1  mov     rax, [rax+20h]
0x180075df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dfa  mov     ebx, eax
0x180075dfc  test    eax, eax
0x180075dfe  jns     loc_180075F33
0x180075e04  mov     edx, 1CFh
0x180075e09  jmp     short loc_180075D96
0x180075e0b  mov     [rbp+4Fh+pv], r15
0x180075e0f  lea     rdx, [rbp+4Fh+pv]
0x180075e13  mov     rax, [rcx]
0x180075e16  mov     rax, [rax+18h]
0x180075e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e1f  mov     edi, eax
0x180075e21  test    eax, eax
0x180075e23  jns     short loc_180075E66
0x180075e25  mov     rcx, [rbp+57h]; this
0x180075e29  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075e30  mov     r9d, eax; char *
0x180075e33  mov     edx, 1D4h; void *
0x180075e38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075e3d  mov     rcx, [rbp+4Fh+pv]; pv
0x180075e41  call    cs:__imp_CoTaskMemFree
0x180075e48  nop     dword ptr [rax+rax+00h]
0x180075e4d  lea     rcx, [rbp+4Fh+var_98]
0x180075e51  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075e56  lea     rcx, [rbp+4Fh+var_A0]
0x180075e5a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075e5f  mov     ebx, edi
0x180075e61  jmp     loc_18007649D
0x180075e66  mov     rdx, [rbp+4Fh+pv]; unsigned __int16 *
0x180075e6a  mov     rcx, [rbx]; unsigned __int16 *
0x180075e6d  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x180075e72  test    eax, eax
0x180075e74  jnz     short loc_180075EA8
0x180075e76  mov     rcx, [rbp+57h]; this
0x180075e7a  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075e81  mov     ebx, 80080204h
0x180075e86  mov     edx, 1D7h; void *
0x180075e8b  mov     r9d, ebx; char *
0x180075e8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075e93  mov     rcx, [rbp+4Fh+pv]; pv
0x180075e97  call    cs:__imp_CoTaskMemFree
0x180075e9e  nop     dword ptr [rax+rax+00h]
0x180075ea3  jmp     loc_180075DA9
0x180075ea8  mov     rcx, [rbp+4Fh+var_98]
0x180075eac  lea     rdx, [rbp+4Fh+lpString2]
0x180075eb0  mov     [rbp+4Fh+lpString2], r15
0x180075eb4  mov     rax, [rcx]
0x180075eb7  mov     rax, [rax+20h]
0x180075ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ec0  mov     ebx, eax
0x180075ec2  test    eax, eax
0x180075ec4  jns     short loc_180075EF0
0x180075ec6  mov     r9d, eax; char *
0x180075ec9  mov     edx, 1DBh; void *
0x180075ece  mov     rcx, [rbp+57h]; this
0x180075ed2  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075ed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075ede  mov     rcx, [rbp+4Fh+lpString2]; pv
0x180075ee2  call    cs:__imp_CoTaskMemFree
0x180075ee9  nop     dword ptr [rax+rax+00h]
0x180075eee  jmp     short loc_180075E93
0x180075ef0  mov     rdx, [rbp+4Fh+lpString2]; lpString2
0x180075ef4  mov     rcx, [r13+3A8h]; lpString1
0x180075efb  call    ?IsPublisherNameEqual@Packaging@Appx@@YA_NPEBG0@Z; Appx::Packaging::IsPublisherNameEqual(ushort const *,ushort const *)
0x180075f00  test    al, al
0x180075f02  jnz     short loc_180075F13
0x180075f04  mov     ebx, 80080204h
0x180075f09  mov     edx, 1DEh
0x180075f0e  mov     r9d, ebx
0x180075f11  jmp     short loc_180075ECE
0x180075f13  mov     rcx, [rbp+4Fh+lpString2]; pv
0x180075f17  call    cs:__imp_CoTaskMemFree
0x180075f1e  nop     dword ptr [rax+rax+00h]
0x180075f23  mov     rcx, [rbp+4Fh+pv]; pv
0x180075f27  call    cs:__imp_CoTaskMemFree
0x180075f2e  nop     dword ptr [rax+rax+00h]
0x180075f33  mov     rcx, [rbp+4Fh+var_A0]
0x180075f37  lea     rdx, [rbp+4Fh+var_70]
0x180075f3b  mov     rax, [rcx]
0x180075f3e  mov     rax, [rax+28h]
0x180075f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f47  mov     ebx, eax
0x180075f49  test    eax, eax
0x180075f4b  jns     short loc_180075F57
0x180075f4d  mov     edx, 1E3h
0x180075f52  jmp     loc_180075D96
0x180075f57  cmp     [rbp+4Fh+var_70], r15d
0x180075f5b  jz      short loc_180075F6F
0x180075f5d  mov     ebx, 80080204h
0x180075f62  mov     edx, 1E4h
0x180075f67  mov     r9d, ebx
0x180075f6a  jmp     loc_180075D99
0x180075f6f  mov     rax, [r12]
0x180075f73  lea     rcx, [rbp+4Fh+var_80]
0x180075f77  mov     [rbp+4Fh+var_80], r15
0x180075f7b  mov     rbx, [rax+18h]
0x180075f7f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075f84  lea     rdx, [rbp+4Fh+var_80]
0x180075f88  mov     rcx, r12
0x180075f8b  mov     rax, rbx
0x180075f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f93  mov     ebx, eax
0x180075f95  test    eax, eax
0x180075f97  jns     short loc_180075FBF
0x180075f99  mov     rcx, [rbp+57h]; this
0x180075f9d  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075fa4  mov     r9d, eax; char *
0x180075fa7  mov     edx, 1E8h; void *
0x180075fac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075fb1  lea     rcx, [rbp+4Fh+var_80]
0x180075fb5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075fba  jmp     loc_180075DA9
0x180075fbf  lea     rdx, [rbp+4Fh+var_90]
0x180075fc3  mov     [rbp+4Fh+var_90], r15
0x180075fc7  lea     rcx, [rbp+4Fh+var_80]
0x180075fcb  call    ??$As@UIAppxManifestPackageId2@@@?$ComPtr@UIAppxManifestPackageId@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxManifestPackageId2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAppxManifestPackageId>::As<IAppxManifestPackageId2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxManifestPackageId2>>)
0x180075fd0  mov     ebx, eax
0x180075fd2  test    eax, eax
0x180075fd4  jns     short loc_180075FF9
0x180075fd6  mov     rcx, [rbp+57h]; this
0x180075fda  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075fe1  mov     r9d, eax; char *
0x180075fe4  mov     edx, 1EBh; void *
0x180075fe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075fee  lea     rcx, [rbp+4Fh+var_90]
0x180075ff2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075ff7  jmp     short loc_180075FB1
0x180075ff9  mov     rdi, [rbp+4Fh+var_90]
0x180075ffd  lea     rcx, [rbp+4Fh+var_88]
0x180076001  mov     [rbp+4Fh+var_88], r15
0x180076005  xor     edx, edx
0x180076007  mov     rax, [rdi]
0x18007600a  mov     rbx, [rax+50h]
0x18007600e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180076013  lea     rdx, [rbp+4Fh+var_88]
0x180076017  mov     rcx, rdi
0x18007601a  mov     rax, rbx
0x18007601d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076022  mov     ebx, eax
0x180076024  test    eax, eax
0x180076026  jns     short loc_18007604B
0x180076028  mov     r9d, eax; char *
0x18007602b  mov     edx, 1EEh; void *
0x180076030  mov     rcx, [rbp+57h]; this
0x180076034  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x18007603b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076040  lea     rcx, [rbp+4Fh+var_88]
0x180076044  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180076049  jmp     short loc_180075FEE
0x18007604b  mov     rax, [rbp+4Fh+var_88]
0x18007604f  lea     r14, [r13+3E0h]
0x180076056  mov     rcx, r14; Table
0x180076059  mov     [rbp+4Fh+Buffer], rax
0x18007605d  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x180076061  mov     [rbp+4Fh+var_50], r15
0x180076065  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18007606c  nop     dword ptr [rax+rax+00h]
0x180076071  test    rax, rax
0x180076074  jz      short loc_180076083
0x180076076  mov     r15, [rax+8]
0x18007607a  test    r15, r15
0x18007607d  jnz     loc_18007616B
0x180076083  lea     rcx, [rbp+4Fh+Buffer]
0x180076087  call    ??$make_unique_nothrow@UOptionalBundleInfo@BundleManifest@Packaging@Appx@@$$V@wil@@YA?AV?$unique_ptr@UOptionalBundleInfo@BundleManifest@Packaging@Appx@@U?$default_delete@UOptionalBundleInfo@BundleManifest@Packaging@Appx@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Appx::Packaging::BundleManifest::OptionalBundleInfo,>(void)
0x18007608c  mov     r15, [rbp+4Fh+Buffer]
0x180076090  test    r15, r15
0x180076093  jnz     short loc_1800760A4
0x180076095  mov     ebx, 8007000Eh
0x18007609a  mov     edx, 1F4h
0x18007609f  mov     r9d, ebx
0x1800760a2  jmp     short loc_180076030
0x1800760a4  mov     rdi, [rbp+4Fh+var_90]
0x1800760a8  xor     edx, edx
0x1800760aa  mov     rcx, r15
0x1800760ad  mov     rax, [rdi]
0x1800760b0  mov     rbx, [rax+18h]
0x1800760b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800760b9  mov     rdx, r15
0x1800760bc  mov     rcx, rdi
  ... truncated ...
```
