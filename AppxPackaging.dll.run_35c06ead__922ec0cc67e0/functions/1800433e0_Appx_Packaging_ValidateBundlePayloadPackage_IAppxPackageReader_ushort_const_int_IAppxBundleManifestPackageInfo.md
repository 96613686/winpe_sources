# Appx::Packaging::ValidateBundlePayloadPackage(IAppxPackageReader *,ushort const *,int,IAppxBundleManifestPackageInfo *,IUri *,Appx::Packaging::ManifestComparisonHelper *)

- ea: `0x1800433e0`
- end: `0x180043ebf`
- name: `?ValidateBundlePayloadPackage@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEBGHPEAUIAppxBundleManifestPackageInfo@@PEAUIUri@@PEAVManifestComparisonHelper@12@@Z`
- size: `2783`
- prototype: `__int64 __fastcall(struct IAppxPackageReader *this, struct IAppxPackageReader *, const unsigned __int16 *, __int64 *, struct IUri *, struct IUri *)`
- caller_count: `4`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023590`
- `0x1800932b0`
- `0x1800cc9f0`
- `0x1800cd1b0`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18003d318`
- `0x1800433e0`
- `0x180043ec8`
- `0x180043f00`
- `0x18004400c`
- `0x1800441f8`
- `0x18004444c`
- `0x1800446d0`
- `0x18004470c`
- `0x1800447a8`
- `0x180044a38`
- `0x18006c2c0`
- `0x180071f50`
- `0x1800968c4`
- `0x180096b04`
- `0x1800cb3f8`
- `0x1800cdcb0`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800437cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800437cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ca0`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::ValidateBundlePayloadPackage(
        struct IAppxPackageReader *this,
        struct IAppxPackageReader *a2,
        const unsigned __int16 *a3,
        __int64 *a4,
        struct IUri *a5,
        struct IUri *a6)
{
  struct IAppxPackageReader v6; // rax
  int v9; // r12d
  HRESULT (__stdcall *GetManifest)(IAppxPackageReader *, IAppxManifestReader **); // rbx
  int v12; // eax
  int PayloadPackageType; // ebx
  struct IAppxManifestReader *v14; // rdi
  HRESULT (__stdcall *GetPackageId)(IAppxManifestReader *, IAppxManifestPackageId **); // rbx
  int v16; // eax
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rax
  __int64 (__fastcall *v20)(__int64 *, __int64 *); // rbx
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  struct IAppxManifestReader *v24; // rbx
  HRESULT (__stdcall *QueryInterface)(IAppxManifestReader *, const IID *const, void **); // rdi
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 **); // rbx
  int v29; // eax
  __int64 v30; // r13
  unsigned __int64 v31; // r14
  __int64 v32; // rax
  int v33; // eax
  __int64 *v34; // rdi
  __int64 (__fastcall *v35)(__int64 *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *); // rbx
  int v36; // eax
  struct Appx::Packaging::ManifestQualifiedResourceFields **v37; // r8
  int QualifiedResourceFields; // eax
  __int64 v39; // r14
  int v40; // eax
  Appx::Packaging *v41; // rcx
  __int64 v42; // rax
  __int64 (__fastcall *v43)(__int64 *, Appx::Packaging **); // rbx
  int v44; // eax
  int v45; // eax
  struct IAppxManifestQualifiedResourceVtbl *v46; // rcx
  char v47; // r12
  Appx::Packaging *v48; // rdi
  __int64 (__fastcall *v49)(Appx::Packaging *, IAppxManifestQualifiedResource *); // rbx
  int v50; // eax
  struct Appx::Packaging::ManifestQualifiedResourceFields **v51; // r8
  int v52; // eax
  struct IAppxManifestQualifiedResourceVtbl *v53; // rdi
  unsigned __int64 i; // rbx
  __int64 v55; // r15
  unsigned int AddRef; // eax
  int AddRef_high; // eax
  int v58; // eax
  struct IAppxManifestQualifiedResourceVtbl *v59; // rcx
  Appx::Packaging *v60; // rcx
  __int64 *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  struct IAppxManifestReader *v65; // rcx
  __int64 v66; // rdx
  struct IAppxManifestQualifiedResourceVtbl *v67; // rcx
  int v69; // eax
  int v70; // eax
  unsigned __int64 v71; // r9
  __int64 v72; // rdx
  Appx::Packaging *v73; // rcx
  __int64 *v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rdx
  struct IAppxManifestQualifiedResourceVtbl *lpVtbl; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-89h]
  int bIgnoreCasea; // [rsp+20h] [rbp-89h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-89h]
  int bIgnoreCasec; // [rsp+20h] [rbp-89h]
  struct IAppxManifestReader *v86; // [rsp+30h] [rbp-79h] BYREF
  __int64 v87; // [rsp+38h] [rbp-71h] BYREF
  __int64 v88; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v89; // [rsp+48h] [rbp-61h] BYREF
  __int64 v90; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *v92; // [rsp+60h] [rbp-49h] BYREF
  Appx::Packaging *v93; // [rsp+68h] [rbp-41h] BYREF
  IAppxManifestQualifiedResource v94; // [rsp+70h] [rbp-39h] BYREF
  enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE v95[2]; // [rsp+78h] [rbp-31h] BYREF
  int v96; // [rsp+80h] [rbp-29h] BYREF
  int v97; // [rsp+84h] [rbp-25h] BYREF
  _QWORD v98[2]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v99; // [rsp+98h] [rbp-11h]
  char v100; // [rsp+A0h] [rbp-9h]
  struct IAppxManifestQualifiedResource v101; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]
  int v103; // [rsp+100h] [rbp+57h] BYREF

  v6.lpVtbl = this->lpVtbl;
  v86 = 0;
  v9 = (int)a3;
  GetManifest = v6.lpVtbl->GetManifest;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v86);
  v12 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, struct IAppxManifestReader **))GetManifest)(this, &v86);
  PayloadPackageType = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x28F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
LABEL_96:
    v65 = v86;
    if ( !v86 )
      return (unsigned int)PayloadPackageType;
    v86 = 0;
    goto LABEL_61;
  }
  v14 = v86;
  v88 = 0;
  GetPackageId = v86->lpVtbl->GetPackageId;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v88);
  v16 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 *))GetPackageId)(v14, &v88);
  PayloadPackageType = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x291,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v16,
      bIgnoreCase);
    goto LABEL_70;
  }
  v92 = 0;
  PayloadPackageType = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v88 + 72LL))(v88, &v92);
  if ( PayloadPackageType < 0 )
  {
    v72 = 659;
    goto LABEL_103;
  }
  PayloadPackageType = Appx::Packaging::BundleValidationHelper::ValidateOSVersion(v86, (const unsigned __int16 *)a2);
  if ( PayloadPackageType < 0 )
  {
    v72 = 662;
LABEL_103:
    v71 = (unsigned int)PayloadPackageType;
    goto LABEL_104;
  }
  PayloadPackageType = Appx::Packaging::BundleValidationHelper::PackageMatchesHashMethod(
                         this,
                         (const unsigned __int16 *)a2,
                         a5);
  if ( PayloadPackageType < 0 )
  {
    v72 = 665;
    goto LABEL_103;
  }
  v95[0] = APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE_APPLICATION;
  PayloadPackageType = Appx::Packaging::BundleValidationHelper::GetPayloadPackageType(
                         v86,
                         (const unsigned __int16 *)a2,
                         v95);
  if ( PayloadPackageType < 0 )
  {
    v80 = 670;
    goto LABEL_109;
  }
  v17 = *a4;
  v97 = 0;
  PayloadPackageType = (*(__int64 (__fastcall **)(__int64 *, int *))(v17 + 24))(a4, &v97);
  if ( PayloadPackageType < 0 )
  {
    v80 = 672;
LABEL_109:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v80,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)PayloadPackageType,
      bIgnoreCase);
    CoTaskMemFree(v92);
    v81 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    goto LABEL_96;
  }
  if ( v95[0] != v97 )
  {
    PayloadPackageType = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dzz_EventWriteTransfer(
        v18,
        (unsigned int)&EVENT_BUNDLE_VALIDATION_MISMATCHED_TYPE,
        -2146958844,
        (_DWORD)a2,
        (__int64)v92);
    AppxPackagingLog(
      &EVENT_BUNDLE_VALIDATION_MISMATCHED_TYPE,
      0xB0000189,
      -2146958844,
      (const unsigned __int16 *)a2,
      v92);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)0x80080204LL,
      bIgnoreCaseb);
    goto LABEL_69;
  }
  if ( v95[0] == APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE_APPLICATION )
  {
    v69 = Appx::Packaging::BundleValidationHelper::ValidateApplicationElement(v86, (const unsigned __int16 *)a2);
    PayloadPackageType = v69;
    if ( v69 < 0 )
    {
      v71 = (unsigned int)v69;
      v72 = 682;
    }
    else
    {
      v70 = Appx::Packaging::ManifestComparisonPackageSet::AddManifest(
              (char *)&a6[11] + (-(__int64)(v9 != 0) & 0xFFFFFFFFFFFFFFB8uLL),
              &v86,
              a2);
      PayloadPackageType = v70;
      if ( v70 >= 0 )
        goto LABEL_10;
      v71 = (unsigned int)v70;
      v72 = 685;
    }
LABEL_104:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v72,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)v71,
      bIgnoreCase);
    goto LABEL_69;
  }
LABEL_10:
  v19 = *a4;
  v87 = 0;
  v20 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 32);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v87);
  v21 = v20(a4, &v87);
  PayloadPackageType = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCase);
LABEL_84:
    v76 = v87;
    if ( v87 )
    {
      v87 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    CoTaskMemFree(v92);
    v77 = v88;
    if ( v88 )
    {
      v88 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v65 = v86;
    if ( !v86 )
      return (unsigned int)PayloadPackageType;
    v86 = 0;
LABEL_61:
    ((void (__fastcall *)(struct IAppxManifestReader *))v65->lpVtbl->Release)(v65);
    return (unsigned int)PayloadPackageType;
  }
  pv = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v87 + 72LL))(v87, &pv);
  PayloadPackageType = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v22,
      bIgnoreCase);
    goto LABEL_68;
  }
  if ( !Common::String::CaseInsensitiveEquals(v92, (const unsigned __int16 *)pv) )
  {
    PayloadPackageType = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dzzz_EventWriteTransfer(
        v23,
        (unsigned int)&EVENT_BUNDLE_VALIDATION_MISMATCHED_IDENTITY,
        -2146958844,
        (_DWORD)a2,
        (__int64)v92,
        (__int64)pv);
    AppxPackagingLog(
      &EVENT_BUNDLE_VALIDATION_MISMATCHED_IDENTITY,
      0xB000018A,
      -2146958844,
      (const unsigned __int16 *)a2,
      v92,
      (const unsigned __int16 *)pv);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)0x80080204LL,
      bIgnoreCasec);
    goto LABEL_68;
  }
  v24 = v86;
  v90 = 0;
  QueryInterface = v86->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v90);
  v26 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, GUID *, __int64 *))QueryInterface)(
          v24,
          &GUID_d06f67bc_b31d_4eba_a8af_638e73e77b4d,
          &v90);
  PayloadPackageType = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v26,
      bIgnoreCase);
LABEL_81:
    v75 = v90;
    if ( v90 )
    {
      v90 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    CoTaskMemFree(pv);
    goto LABEL_84;
  }
  v27 = v90;
  v89 = 0;
  v28 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v90 + 96LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v89);
  v29 = v28(v27, &v89);
  PayloadPackageType = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v29,
      bIgnoreCase);
    goto LABEL_67;
  }
  v103 = 0;
  v30 = 0;
  v98[0] = 0;
  v31 = 0;
  v98[1] = 0;
  v32 = *v89;
  v99 = 0;
  v100 = 1;
  v33 = (*(__int64 (__fastcall **)(__int64 *, int *))(v32 + 32))(v89, &v103);
  PayloadPackageType = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v33,
      bIgnoreCase);
    goto LABEL_66;
  }
  while ( v103 )
  {
    v34 = v89;
    *(_QWORD *)v95 = 0;
    v35 = *(__int64 (__fastcall **)(__int64 *, enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *))(*v89 + 24);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v95);
    v36 = v35(v34, v95);
    PayloadPackageType = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
        (const char *)(unsigned int)v36,
        bIgnoreCase);
      v73 = *(Appx::Packaging **)v95;
      if ( *(_QWORD *)v95 )
      {
        *(_QWORD *)v95 = 0;
        goto LABEL_78;
      }
      goto LABEL_79;
    }
    v94.lpVtbl = 0;
    QualifiedResourceFields = Appx::Packaging::GetQualifiedResourceFields(*(Appx::Packaging **)v95, &v94, v37);
    PayloadPackageType = QualifiedResourceFields;
    if ( QualifiedResourceFields < 0 )
    {
      v78 = 718;
LABEL_99:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v78,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
        (const char *)(unsigned int)QualifiedResourceFields,
        bIgnoreCase);
      lpVtbl = v94.lpVtbl;
      goto LABEL_100;
    }
    QualifiedResourceFields = Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(
                                v98,
                                v31 + 1);
    PayloadPackageType = QualifiedResourceFields;
    if ( QualifiedResourceFields < 0 )
    {
      v78 = 719;
      goto LABEL_99;
    }
    v39 = v99;
    v30 = v98[0];
    *(IAppxManifestQualifiedResource *)(v98[0] + 8 * v99) = v94;
    v31 = v39 + 1;
    v99 = v31;
    v40 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v89 + 40))(v89, &v103);
    PayloadPackageType = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCase);
      lpVtbl = 0;
LABEL_100:
      Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(lpVtbl);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v95);
LABEL_66:
      Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::~Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>(v98);
LABEL_67:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v89);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v90);
LABEL_68:
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v87);
LABEL_69:
      CoTaskMemFree(v92);
LABEL_70:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v88);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v86);
      return (unsigned int)PayloadPackageType;
    }
    Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(0);
    v41 = *(Appx::Packaging **)v95;
    if ( *(_QWORD *)v95 )
    {
      *(_QWORD *)v95 = 0;
      (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v41 + 16LL))(v41);
    }
  }
  v42 = *a4;
  v93 = 0;
  v43 = *(__int64 (__fastcall **)(__int64 *, Appx::Packaging **))(v42 + 64);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v93);
  v44 = v43(a4, &v93);
  PayloadPackageType = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v44,
      bIgnoreCase);
    v73 = v93;
    if ( v93 )
    {
      v93 = 0;
LABEL_78:
      (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v73 + 16LL))(v73);
    }
LABEL_79:
    Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::~Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>(v98);
    v74 = v89;
    if ( v89 )
    {
      v89 = 0;
      (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
    }
    goto LABEL_81;
  }
  v96 = 0;
  v45 = (*(__int64 (__fastcall **)(Appx::Packaging *, int *))(*(_QWORD *)v93 + 32LL))(v93, &v96);
  PayloadPackageType = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)(unsigned int)v45,
      bIgnoreCase);
LABEL_65:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v93);
    goto LABEL_66;
  }
  v47 = 1;
LABEL_26:
  if ( v47 && v96 )
  {
    v48 = v93;
    v94.lpVtbl = 0;
    v49 = *(__int64 (__fastcall **)(Appx::Packaging *, IAppxManifestQualifiedResource *))(*(_QWORD *)v93 + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v94);
    v50 = v49(v48, &v94);
    PayloadPackageType = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
        (const char *)(unsigned int)v50,
        bIgnoreCase);
      v59 = v94.lpVtbl;
      if ( v94.lpVtbl )
      {
        v94.lpVtbl = 0;
        (*((void (__fastcall **)(struct IAppxManifestQualifiedResourceVtbl *))v59->QueryInterface + 2))(v59);
      }
      goto LABEL_49;
    }
    v101.lpVtbl = 0;
    v52 = Appx::Packaging::GetQualifiedResourceFields((Appx::Packaging *)v94.lpVtbl, &v101, v51);
    PayloadPackageType = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E8,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
        (const char *)(unsigned int)v52,
        bIgnoreCase);
      v67 = v101.lpVtbl;
LABEL_64:
      Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(v67);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v94);
      goto LABEL_65;
    }
    v53 = v101.lpVtbl;
    for ( i = 0; ; ++i )
    {
      if ( i >= v31 )
        goto LABEL_40;
      v55 = *(_QWORD *)(v30 + 8 * i);
      if ( v53->QueryInterface )
      {
        if ( !*(_QWORD *)v55 || CompareStringOrdinal((LPCWCH)v53->QueryInterface, -1, *(LPCWCH *)v55, -1, 1) != 2 )
          continue;
      }
      else if ( *(_QWORD *)v55 )
      {
        continue;
      }
      AddRef = (unsigned int)v53->AddRef;
      if ( AddRef <= *(_DWORD *)(v55 + 8) && AddRef >= *(_DWORD *)(v55 + 8) )
      {
        AddRef_high = HIDWORD(v53->AddRef);
        if ( AddRef_high <= *(_DWORD *)(v55 + 12) && AddRef_high >= *(_DWORD *)(v55 + 12) )
        {
          if ( i == 0x40000000 )
          {
LABEL_40:
            v47 = 0;
            goto LABEL_41;
          }
          v58 = Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::DeleteAt(
                  v98,
                  i);
          PayloadPackageType = v58;
          if ( v58 < 0 )
          {
            v66 = 753;
            goto LABEL_63;
          }
          v31 = v99;
          v30 = v98[0];
LABEL_41:
          v58 = (*(__int64 (__fastcall **)(Appx::Packaging *, int *))(*(_QWORD *)v93 + 40LL))(v93, &v96);
          PayloadPackageType = v58;
          if ( v58 < 0 )
          {
            v66 = 756;
LABEL_63:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v66,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
              (const char *)(unsigned int)v58,
              bIgnoreCase);
            v67 = v53;
            goto LABEL_64;
          }
          Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(v53);
          v46 = v94.lpVtbl;
          if ( v94.lpVtbl )
          {
            v94.lpVtbl = 0;
            (*((void (__fastcall **)(struct IAppxManifestQualifiedResourceVtbl *))v46->QueryInterface + 2))(v46);
          }
          goto LABEL_26;
        }
      }
    }
  }
  if ( v31 || !v47 )
  {
    PayloadPackageType = -2146958844;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
      McTemplateU0dzz_EventWriteTransfer(
        (_DWORD)v46,
        (unsigned int)&EVENT_BUNDLE_VALIDATION_MISMATCHED_RESOURCES,
        -2146958844,
        (_DWORD)a2,
        (__int64)v92);
    AppxPackagingLog(
      &EVENT_BUNDLE_VALIDATION_MISMATCHED_RESOURCES,
      0xB000018B,
      -2146958844,
      (const unsigned __int16 *)a2,
      v92);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
      (const char *)0x80080204LL,
      bIgnoreCasea);
    goto LABEL_65;
  }
LABEL_49:
  v60 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v60 + 16LL))(v60);
  }
  Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::~Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>(v98);
  v61 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
  }
  v62 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  }
  CoTaskMemFree(pv);
  v63 = v87;
  if ( v87 )
  {
    v87 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
  }
  CoTaskMemFree(v92);
  v64 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  v65 = v86;
  if ( v86 )
  {
    v86 = 0;
    goto LABEL_61;
  }
  return (unsigned int)PayloadPackageType;
}

```

## disassembly

```asm
0x1800433e0  push    rbp
0x1800433e2  push    rbx
0x1800433e3  push    rsi
0x1800433e4  push    rdi
0x1800433e5  push    r12
0x1800433e7  push    r13
0x1800433e9  push    r14
0x1800433eb  push    r15
0x1800433ed  lea     rbp, [rsp-0Fh]
0x1800433f2  sub     rsp, 0B8h
0x1800433f9  mov     rax, [rcx]
0x1800433fc  mov     r14, rcx
0x1800433ff  xor     r13d, r13d
0x180043402  lea     rcx, [rbp+47h+var_C0]
0x180043406  mov     r15, r9
0x180043409  mov     [rbp+47h+var_C0], r13
0x18004340d  mov     r12d, r8d
0x180043410  mov     rsi, rdx
0x180043413  mov     rbx, [rax+38h]
0x180043417  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18004341c  lea     rdx, [rbp+47h+var_C0]
0x180043420  mov     rcx, r14
0x180043423  mov     rax, rbx
0x180043426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004342b  mov     ebx, eax
0x18004342d  test    eax, eax
0x18004342f  js      loc_180043BC3
0x180043435  mov     rdi, [rbp+47h+var_C0]
0x180043439  lea     rcx, [rbp+47h+var_B0]
0x18004343d  mov     [rbp+47h+var_B0], r13
0x180043441  mov     rax, [rdi]
0x180043444  mov     rbx, [rax+18h]
0x180043448  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18004344d  lea     rdx, [rbp+47h+var_B0]
0x180043451  mov     rcx, rdi
0x180043454  mov     rax, rbx
0x180043457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004345c  mov     ebx, eax
0x18004345e  test    eax, eax
0x180043460  js      loc_180043C59
0x180043466  mov     rcx, [rbp+47h+var_B0]
0x18004346a  lea     rdx, [rbp+47h+var_90]
0x18004346e  mov     [rbp+47h+var_90], r13
0x180043472  mov     rax, [rcx]
0x180043475  mov     rax, [rax+48h]
0x180043479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004347e  mov     ebx, eax
0x180043480  test    eax, eax
0x180043482  js      loc_180043C76
0x180043488  mov     rcx, [rbp+47h+var_C0]; struct IAppxManifestReader *
0x18004348c  mov     rdx, rsi; unsigned __int16 *
0x18004348f  call    ?ValidateOSVersion@BundleValidationHelper@Packaging@Appx@@SAJPEAUIAppxManifestReader@@PEBG@Z; Appx::Packaging::BundleValidationHelper::ValidateOSVersion(IAppxManifestReader *,ushort const *)
0x180043494  mov     ebx, eax
0x180043496  test    eax, eax
0x180043498  js      loc_180043C3C
0x18004349e  mov     r8, [rbp+47h+arg_20]; struct IUri *
0x1800434a2  mov     rdx, rsi; unsigned __int16 *
0x1800434a5  mov     rcx, r14; struct IAppxPackageReader *
0x1800434a8  call    ?PackageMatchesHashMethod@BundleValidationHelper@Packaging@Appx@@SAJPEAUIAppxPackageReader@@PEBGPEAUIUri@@@Z; Appx::Packaging::BundleValidationHelper::PackageMatchesHashMethod(IAppxPackageReader *,ushort const *,IUri *)
0x1800434ad  mov     ebx, eax
0x1800434af  test    eax, eax
0x1800434b1  js      loc_180043C7D
0x1800434b7  mov     rcx, [rbp+47h+var_C0]; struct IAppxManifestReader *
0x1800434bb  lea     r8, [rbp+47h+var_78]; enum APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *
0x1800434bf  mov     rdx, rsi; unsigned __int16 *
0x1800434c2  mov     [rbp+47h+var_78], r13d
0x1800434c6  call    ?GetPayloadPackageType@BundleValidationHelper@Packaging@Appx@@SAJPEAUIAppxManifestReader@@PEBGPEAW4APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE@@@Z; Appx::Packaging::BundleValidationHelper::GetPayloadPackageType(IAppxManifestReader *,ushort const *,APPX_BUNDLE_PAYLOAD_PACKAGE_TYPE *)
0x1800434cb  mov     ebx, eax
0x1800434cd  test    eax, eax
0x1800434cf  js      loc_180043C84
0x1800434d5  mov     rax, [r15]
0x1800434d8  lea     rdx, [rbp+47h+var_6C]
0x1800434dc  mov     rcx, r15
0x1800434df  mov     [rbp+47h+var_6C], r13d
0x1800434e3  mov     rax, [rax+18h]
0x1800434e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434ec  mov     ebx, eax
0x1800434ee  test    eax, eax
0x1800434f0  js      loc_180043CCE
0x1800434f6  mov     eax, [rbp+47h+var_78]
0x1800434f9  cmp     eax, [rbp+47h+var_6C]
0x1800434fc  jnz     loc_180043DC8
0x180043502  test    eax, eax
0x180043504  jz      loc_180043A0C
0x18004350a  xor     r12d, r12d
0x18004350d  mov     rax, [r15]
0x180043510  lea     rcx, [rbp+47h+var_B8]
0x180043514  mov     [rbp+47h+var_B8], r12
0x180043518  mov     rbx, [rax+20h]
0x18004351c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180043521  lea     rdx, [rbp+47h+var_B8]
0x180043525  mov     rcx, r15
0x180043528  mov     rax, rbx
0x18004352b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043530  mov     ebx, eax
0x180043532  test    eax, eax
0x180043534  js      loc_180043CD5
0x18004353a  mov     rcx, [rbp+47h+var_B8]
0x18004353e  lea     rdx, [rbp+47h+pv]
0x180043542  mov     [rbp+47h+pv], r12
0x180043546  mov     rax, [rcx]
0x180043549  mov     rax, [rax+48h]
0x18004354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043552  mov     ebx, eax
0x180043554  test    eax, eax
0x180043556  js      loc_180043CF2
0x18004355c  mov     rdx, [rbp+47h+pv]; unsigned __int16 *
0x180043560  mov     rcx, [rbp+47h+var_90]; unsigned __int16 *
0x180043564  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x180043569  test    eax, eax
0x18004356b  jz      loc_180043E2E
0x180043571  mov     rbx, [rbp+47h+var_C0]
0x180043575  lea     rcx, [rbp+47h+var_A0]
0x180043579  mov     [rbp+47h+var_A0], r12
0x18004357d  mov     rax, [rbx]
0x180043580  mov     rdi, [rax]
0x180043583  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180043588  lea     r8, [rbp+47h+var_A0]
0x18004358c  mov     rcx, rbx
0x18004358f  lea     rdx, _GUID_d06f67bc_b31d_4eba_a8af_638e73e77b4d
0x180043596  mov     rax, rdi
0x180043599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004359e  mov     ebx, eax
0x1800435a0  test    eax, eax
0x1800435a2  js      loc_180043D0F
0x1800435a8  mov     rdi, [rbp+47h+var_A0]
0x1800435ac  lea     rcx, [rbp+47h+var_A8]
0x1800435b0  mov     [rbp+47h+var_A8], r12
0x1800435b4  mov     rax, [rdi]
0x1800435b7  mov     rbx, [rax+60h]
0x1800435bb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800435c0  lea     rdx, [rbp+47h+var_A8]
0x1800435c4  mov     rcx, rdi
0x1800435c7  mov     rax, rbx
0x1800435ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435cf  mov     ebx, eax
0x1800435d1  test    eax, eax
0x1800435d3  js      loc_180043D2C
0x1800435d9  mov     rcx, [rbp+47h+var_A8]
0x1800435dd  lea     rdx, [rbp+47h+arg_0]
0x1800435e1  mov     [rbp+47h+arg_0], r12d
0x1800435e5  mov     r13, r12
0x1800435e8  mov     [rbp+47h+var_68], r12
0x1800435ec  mov     r14, r12
0x1800435ef  mov     [rbp+47h+var_60], r12
0x1800435f3  mov     rax, [rcx]
0x1800435f6  mov     [rbp+47h+var_58], r12
0x1800435fa  mov     [rbp+47h+var_50], 1
0x1800435fe  mov     rax, [rax+20h]
0x180043602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043607  mov     ebx, eax
0x180043609  test    eax, eax
0x18004360b  js      loc_180043D49
0x180043611  cmp     [rbp+47h+arg_0], r12d
0x180043615  jz      loc_1800436DD
0x18004361b  mov     rdi, [rbp+47h+var_A8]
0x18004361f  lea     rcx, [rbp+47h+var_78]
0x180043623  mov     qword ptr [rbp+47h+var_78], r12
0x180043627  mov     rax, [rdi]
0x18004362a  mov     rbx, [rax+18h]
0x18004362e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180043633  lea     rdx, [rbp+47h+var_78]
0x180043637  mov     rcx, rdi
0x18004363a  mov     rax, rbx
0x18004363d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043642  mov     ebx, eax
0x180043644  test    eax, eax
0x180043646  js      loc_180043A7B
0x18004364c  mov     rcx, qword ptr [rbp+47h+var_78]; this
0x180043650  lea     rdx, [rbp+47h+var_80]; struct IAppxManifestQualifiedResource *
0x180043654  mov     [rbp+47h+var_80.lpVtbl], r12
0x180043658  call    ?GetQualifiedResourceFields@Packaging@Appx@@YAJPEAUIAppxManifestQualifiedResource@@PEAPEAUManifestQualifiedResourceFields@12@@Z; Appx::Packaging::GetQualifiedResourceFields(IAppxManifestQualifiedResource *,Appx::Packaging::ManifestQualifiedResourceFields * *)
0x18004365d  mov     ebx, eax
0x18004365f  test    eax, eax
0x180043661  js      loc_180043BF1
0x180043667  lea     rdx, [r14+1]
0x18004366b  lea     rcx, [rbp+47h+var_68]
0x18004366f  call    ?EnsureCapacity@?$Array@UManifestQualifiedResourceFields@Packaging@Appx@@V?$ContainerOperations@UManifestQualifiedResourceFields@Packaging@Appx@@U123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@UManifestQualifiedResourceFields@Packaging@Appx@@@5@V?$ArrayOperations@UManifestQualifiedResourceFields@Packaging@Appx@@VNoKey@Common@@@5@@Common@@QEAAJ_K@Z; Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(unsigned __int64)
0x180043674  mov     ebx, eax
0x180043676  test    eax, eax
0x180043678  js      loc_180043EA6
0x18004367e  mov     r14, [rbp+47h+var_58]
0x180043682  lea     rdx, [rbp+47h+arg_0]
0x180043686  mov     rax, [rbp+47h+var_80.lpVtbl]
0x18004368a  mov     r13, [rbp+47h+var_68]
0x18004368e  mov     [r13+r14*8+0], rax
0x180043693  inc     r14
0x180043696  mov     rcx, [rbp+47h+var_A8]
0x18004369a  mov     [rbp+47h+var_58], r14
0x18004369e  mov     rax, [rcx]
0x1800436a1  mov     rax, [rax+28h]
0x1800436a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436aa  mov     ebx, eax
0x1800436ac  test    eax, eax
0x1800436ae  js      loc_180043C20
0x1800436b4  xor     ecx, ecx; void *
0x1800436b6  call    ??$AutoPtrDeallocate@UManifestQualifiedResourceFields@Packaging@Appx@@@Common@@YAXPEAUManifestQualifiedResourceFields@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(Appx::Packaging::ManifestQualifiedResourceFields *)
0x1800436bb  mov     rcx, qword ptr [rbp+47h+var_78]
0x1800436bf  test    rcx, rcx
0x1800436c2  jz      loc_180043611
0x1800436c8  mov     qword ptr [rbp+47h+var_78], r12
0x1800436cc  mov     rax, [rcx]
0x1800436cf  mov     rax, [rax+10h]
0x1800436d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436d8  jmp     loc_180043611
0x1800436dd  mov     rax, [r15]
0x1800436e0  lea     rcx, [rbp+47h+var_88]
0x1800436e4  mov     [rbp+47h+var_88], r12
0x1800436e8  mov     rbx, [rax+40h]
0x1800436ec  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800436f1  lea     rdx, [rbp+47h+var_88]
0x1800436f5  mov     rcx, r15
0x1800436f8  mov     rax, rbx
0x1800436fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043700  mov     ebx, eax
0x180043702  test    eax, eax
0x180043704  js      loc_180043D70
0x18004370a  mov     rcx, [rbp+47h+var_88]
0x18004370e  lea     rdx, [rbp+47h+var_70]
0x180043712  mov     [rbp+47h+var_70], r12d
0x180043716  mov     rax, [rcx]
0x180043719  mov     rax, [rax+20h]
0x18004371d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043722  mov     ebx, eax
0x180043724  test    eax, eax
0x180043726  js      loc_180043D9E
0x18004372c  mov     r12b, 1
0x18004372f  xor     r15d, r15d
0x180043732  test    r12b, r12b
0x180043735  jz      loc_180043B4F
0x18004373b  cmp     [rbp+47h+var_70], r15d
0x18004373f  jz      loc_180043B4F
0x180043745  mov     rdi, [rbp+47h+var_88]
0x180043749  lea     rcx, [rbp+47h+var_80]
0x18004374d  mov     [rbp+47h+var_80.lpVtbl], r15
0x180043751  mov     rax, [rdi]
0x180043754  mov     rbx, [rax+18h]
0x180043758  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18004375d  lea     rdx, [rbp+47h+var_80]
0x180043761  mov     rcx, rdi
0x180043764  mov     rax, rbx
0x180043767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004376c  mov     ebx, eax
0x18004376e  test    eax, eax
0x180043770  js      loc_180043874
0x180043776  mov     rcx, [rbp+47h+var_80.lpVtbl]; this
0x18004377a  lea     rdx, [rbp+47h+var_48]; struct IAppxManifestQualifiedResource *
0x18004377e  mov     [rbp+47h+var_48.lpVtbl], r15
0x180043782  call    ?GetQualifiedResourceFields@Packaging@Appx@@YAJPEAUIAppxManifestQualifiedResource@@PEAPEAUManifestQualifiedResourceFields@12@@Z; Appx::Packaging::GetQualifiedResourceFields(IAppxManifestQualifiedResource *,Appx::Packaging::ManifestQualifiedResourceFields * *)
0x180043787  mov     ebx, eax
0x180043789  test    eax, eax
0x18004378b  js      loc_180043A5A
0x180043791  mov     rdi, [rbp+47h+var_48.lpVtbl]
0x180043795  mov     rbx, r15
0x180043798  cmp     rbx, r14
0x18004379b  jnb     short loc_1800437FB
0x18004379d  mov     rcx, [rdi]; lpString1
0x1800437a0  mov     r15, [r13+rbx*8+0]
0x1800437a5  test    rcx, rcx
0x1800437a8  jz      loc_180043EB0
0x1800437ae  cmp     qword ptr [r15], 0
0x1800437b2  jz      loc_180043849
0x1800437b8  mov     r8, [r15]; lpString2
0x1800437bb  or      eax, 0FFFFFFFFh
0x1800437be  mov     r9d, eax; cchCount2
0x1800437c1  mov     [rsp+0F0h+bIgnoreCase], 1; int
0x1800437c9  mov     edx, eax; cchCount1
0x1800437cb  call    cs:__imp_CompareStringOrdinal
0x1800437d2  nop     dword ptr [rax+rax+00h]
0x1800437d7  cmp     eax, 2
0x1800437da  jnz     short loc_180043849
0x1800437dc  mov     eax, [rdi+8]
0x1800437df  cmp     eax, [r15+8]
0x1800437e3  ja      short loc_180043849
0x1800437e5  jb      short loc_180043849
0x1800437e7  mov     eax, [rdi+0Ch]
0x1800437ea  cmp     eax, [r15+0Ch]
0x1800437ee  jg      short loc_180043849
0x1800437f0  jl      short loc_180043849
0x1800437f2  cmp     rbx, 40000000h
0x1800437f9  jnz     short loc_180043851
0x1800437fb  xor     r15d, r15d
0x1800437fe  mov     r12b, r15b
0x180043801  mov     rcx, [rbp+47h+var_88]
0x180043805  lea     rdx, [rbp+47h+var_70]
0x180043809  mov     rax, [rcx]
0x18004380c  mov     rax, [rax+28h]
0x180043810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043815  mov     ebx, eax
0x180043817  test    eax, eax
0x180043819  js      loc_18004396D
0x18004381f  mov     rcx, rdi; void *
0x180043822  call    ??$AutoPtrDeallocate@UManifestQualifiedResourceFields@Packaging@Appx@@@Common@@YAXPEAUManifestQualifiedResourceFields@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ManifestQualifiedResourceFields>(Appx::Packaging::ManifestQualifiedResourceFields *)
0x180043827  mov     rcx, [rbp+47h+var_80.lpVtbl]
0x18004382b  test    rcx, rcx
0x18004382e  jz      loc_180043732
0x180043834  mov     [rbp+47h+var_80.lpVtbl], r15
0x180043838  mov     rax, [rcx]
0x18004383b  mov     rax, [rax+10h]
0x18004383f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
