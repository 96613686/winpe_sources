# OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x18006abf0`
- end: `0x18006b235`
- name: `?SetIsAdditiveMode@PackagedComCatalogCollector@DEH@OSIntegration@@UEAAJPEBUICollectorPackageInformation@23@@Z`
- size: `1605`
- prototype: `__int64 __fastcall(OSIntegration::DEH::PackagedComCatalogCollector *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180059424`
- `0x18006a4c8`
- `0x18006abf0`
- `0x18006b23c`
- `0x18006b4b4`
- `0x180097240`
- `0x1800a2dd0`
- `0x1800aed10`
- `0x1800db594`
- `0x180145384`
- `0x18014ae30`
- `0x18014bf08`
- `0x180155fc8`
- `0x1801ac010`

## import_xrefs

- `combase!__imp_RoGetRegistrationStoreContext` at `0x18006ace2`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18006ace2`

## string_xrefs

- `0x18006ac57`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006ad12`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006ad5f`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006aded`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006afb6`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006b00c`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006b066`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006b133`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006b1da`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18006ac50`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006ad0b`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006ad66`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006ade6`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006afaf`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006b005`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006b05f`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006b12c`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006b1d3`: `OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode`
- `0x18006afa3`: `_classes->Insert(clsid, classProperties.Get(), &replaced)`
- `0x18006adda`: `hrReadEntry`
- `0x18006ad53`: `registrationStoreContext.query_to(&packagedComContext)`
- `0x18006b1c7`: `packagedComContext->TryGetComClassIdForPackageByIndex(classesHandle, classIndex, &hasEntryAtIndex, &clsid)`
- `0x18006ae42`: `packagedComContext->GetComClassEntriesForPackage(packageMoniker.Get(), &classesHandle)`
- `0x18006b053`: `packagedComContext->ReadComClassEntry(packageMoniker.Get(), clsid, properties)`
- `0x18006b0ef`: `registryCompatibilityCollector.query_to(&registryCompatibilityCollectorTestHooks)`
- `0x18006b11b`: `registryCompatibilityCollectorTestHooks->SetIsAdditiveMode(incomingPackage)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode(
        OSIntegration::DEH::PackagedComCatalogCollector *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  OSIntegration::DEH::PackagedComCatalogCollector *v4; // rcx
  const char *v5; // rax
  __int64 v6; // rdx
  int HasAnyClasses; // ebx
  int RegistrationStoreContext; // eax
  int v10; // eax
  const char *v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rbx
  unsigned int i; // ebx
  int v17; // eax
  unsigned int v18; // esi
  int v19; // eax
  int v20; // esi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  const char *v28; // rax
  __int64 v29; // rdx
  int v30; // eax
  char *v31; // [rsp+28h] [rbp-D8h]
  int v32; // [rsp+30h] [rbp-D0h]
  bool v33; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v34[7]; // [rsp+41h] [rbp-BFh] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int128 v40; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v41[2]; // [rsp+80h] [rbp-80h] BYREF
  char v42; // [rsp+90h] [rbp-70h]
  __int128 v43; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[24]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-38h]
  _BYTE v46[576]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+348h] [rbp+248h]

  v4 = (OSIntegration::DEH::PackagedComCatalogCollector *)((char *)this - 24);
  if ( *((_DWORD *)v4 + 12) )
  {
    v5 = "_serverCount > 0";
    v6 = 5414;
LABEL_3:
    HasAnyClasses = -2147483635;
LABEL_4:
    LODWORD(v31) = HasAnyClasses;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
      v5,
      v31,
      v32);
    return (unsigned int)HasAnyClasses;
  }
  v33 = 0;
  HasAnyClasses = OSIntegration::DEH::PackagedComCatalogCollector::GetHasAnyClasses(v4, &v33);
  if ( HasAnyClasses < 0 )
  {
    v5 = "GetHasAnyClasses(&hasAnyClasses)";
    v6 = 5419;
    goto LABEL_4;
  }
  if ( v33 )
  {
    v5 = "hasAnyClasses";
    v6 = 5420;
    goto LABEL_3;
  }
  *(_QWORD *)&v40 = (**(__int64 (__fastcall ***)(const struct OSIntegration::DEH::ICollectorPackageInformation *))a2)(a2);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v44, &v40);
  v37 = 0;
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_82e99b35_ccbd_4e12_b426_ba25a40986c8, &v37);
  HasAnyClasses = RegistrationStoreContext;
  if ( RegistrationStoreContext < 0 )
  {
    LODWORD(v31) = RegistrationStoreContext;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1532,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
      "RoGetRegistrationStoreContext(Windows::Foundation::RegistrationScope_PerUser, nullptr, 0, IID_PPV_ARGS(&registrati"
      "onStoreContext))",
      v31,
      v32);
LABEL_48:
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v37);
    return (unsigned int)HasAnyClasses;
  }
  v35 = 0;
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
          v37,
          &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada,
          &v35);
  HasAnyClasses = v10;
  if ( v10 < 0 )
  {
    LODWORD(v31) = v10;
    v11 = "registrationStoreContext.query_to(&packagedComContext)";
    v12 = 5429;
    goto LABEL_14;
  }
  while ( 1 )
  {
    ComServerRegistrationEntryProperties::ComServerRegistrationEntryProperties((ComServerRegistrationEntryProperties *)v46);
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)v35 + 80LL))(
            v35,
            v45,
            *((unsigned int *)this + 6),
            v46,
            0,
            0);
    HasAnyClasses = v13;
    if ( v13 == -2147024894 )
      break;
    if ( v13 < 0 )
    {
      LODWORD(v31) = v13;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1540,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        "hrReadEntry",
        v31,
        v32);
      ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties((ComServerRegistrationEntryProperties *)v46);
      goto LABEL_47;
    }
    ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties((ComServerRegistrationEntryProperties *)v46);
    ++*((_DWORD *)this + 6);
  }
  ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties((ComServerRegistrationEntryProperties *)v46);
  v39 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v35 + 144LL))(v35, v45, &v39);
  HasAnyClasses = v14;
  if ( v14 < 0 )
  {
    LODWORD(v31) = v14;
    v11 = "packagedComContext->GetComClassEntriesForPackage(packageMoniker.Get(), &classesHandle)";
    v12 = 5448;
LABEL_14:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
      v11,
      v31,
      v32);
LABEL_47:
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v35);
    goto LABEL_48;
  }
  v15 = v37;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
  *((_QWORD *)&v43 + 1) = &v39;
  *(_QWORD *)&v43 = 0;
  v41[0] = v15;
  v41[1] = &v39;
  v42 = 1;
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v43);
  for ( i = 0; ; ++i )
  {
    v33 = 0;
    v43 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, bool *, __int128 *))(*(_QWORD *)v35 + 152LL))(
            v35,
            v39,
            i,
            &v33,
            &v43);
    v18 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v31) = v17;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1555,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        "packagedComContext->TryGetComClassIdForPackageByIndex(classesHandle, classIndex, &hasEntryAtIndex, &clsid)",
        v31,
        v32);
      wil::details::lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>::~lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>(v41);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v35);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v37);
      return v18;
    }
    if ( !v33 )
      break;
    ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v46);
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)v35 + 72LL))(
            v35,
            v45,
            &v43,
            v46,
            0,
            0);
    v20 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v31) = v19;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1562,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        "packagedComContext->ReadComClassEntry(packageMoniker.Get(), clsid, properties)",
        v31,
        v32);
LABEL_39:
      ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v46);
      wil::details::lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>::~lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>(v41);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v35);
      HasAnyClasses = v20;
      goto LABEL_48;
    }
    Microsoft::WRL::Details::Make<OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties,_GUID &,ComClassRegistrationEntryProperties>(
      &v36,
      &v43,
      v46);
    if ( !v36 )
    {
      HasAnyClasses = -2147024882;
      LODWORD(v31) = -2147024882;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1565,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        "classProperties",
        v31,
        v32);
      v25 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v46);
      goto LABEL_46;
    }
    v34[0] = 0;
    v21 = *((_QWORD *)this + 5);
    v40 = v43;
    v22 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _BYTE *))(*(_QWORD *)v21 + 80LL))(
            v21,
            &v40,
            v36,
            v34);
    v20 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v31) = v22;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1568,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        "_classes->Insert(clsid, classProperties.Get(), &replaced)",
        v31,
        v32);
      v24 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      goto LABEL_39;
    }
    v23 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v46);
  }
  v26 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 72LL))(a2);
  wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(
    &v40,
    *(_QWORD *)(v26 + 72));
  if ( (_QWORD)v40 )
  {
    v38 = 0;
    v27 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v40)(
            v40,
            &GUID_ad2079f6_143d_485e_b9f2_8037a4e0128b,
            &v38);
    HasAnyClasses = v27;
    if ( v27 < 0 )
    {
      LODWORD(v31) = v27;
      v28 = "registryCompatibilityCollector.query_to(&registryCompatibilityCollectorTestHooks)";
      v29 = 5491;
LABEL_45:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::SetIsAdditiveMode",
        v28,
        v31,
        v32);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v38);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v40);
LABEL_46:
      wil::details::lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>::~lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>(v41);
      goto LABEL_47;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)v38 + 48LL))(
            v38,
            a2);
    HasAnyClasses = v30;
    if ( v30 < 0 )
    {
      LODWORD(v31) = v30;
      v28 = "registryCompatibilityCollectorTestHooks->SetIsAdditiveMode(incomingPackage)";
      v29 = 5493;
      goto LABEL_45;
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v38);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v40);
  wil::details::lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>::~lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>(v41);
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v35);
  wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v37);
  return 0;
}

```

## disassembly

```asm
0x18006abf0  mov     [rsp-8+arg_10], rbx
0x18006abf5  push    rbp
0x18006abf6  push    rsi
0x18006abf7  push    rdi
0x18006abf8  push    r14
0x18006abfa  push    r15
0x18006abfc  lea     rbp, [rsp-220h]
0x18006ac04  sub     rsp, 320h
0x18006ac0b  mov     rax, cs:__security_cookie
0x18006ac12  xor     rax, rsp
0x18006ac15  mov     [rbp+240h+var_30], rax
0x18006ac1c  mov     r14, rdx
0x18006ac1f  mov     rdi, rcx
0x18006ac22  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18006ac26  xor     r15d, r15d
0x18006ac29  cmp     [rcx+30h], r15d
0x18006ac2d  jbe     short loc_18006AC6A
0x18006ac2f  lea     rax, aServercount0; "_serverCount > 0"
0x18006ac36  mov     edx, 1526h; void *
0x18006ac3b  mov     ebx, 8000000Dh
0x18006ac40  mov     dword ptr [rsp+340h+var_318], ebx; char *
0x18006ac44  mov     rcx, [rbp+248h]; this
0x18006ac4b  mov     [rsp+340h+var_320], rax; char *
0x18006ac50  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006ac57  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006ac5e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006ac63  mov     eax, ebx
0x18006ac65  jmp     loc_18006B20E
0x18006ac6a  mov     [rsp+340h+var_300], r15b
0x18006ac6f  lea     rdx, [rsp+340h+var_300]; bool *
0x18006ac74  call    ?GetHasAnyClasses@PackagedComCatalogCollector@DEH@OSIntegration@@AEBAJPEA_N@Z; OSIntegration::DEH::PackagedComCatalogCollector::GetHasAnyClasses(bool *)
0x18006ac79  mov     ebx, eax
0x18006ac7b  test    eax, eax
0x18006ac7d  jns     short loc_18006AC8D
0x18006ac7f  lea     rax, aGethasanyclass; "GetHasAnyClasses(&hasAnyClasses)"
0x18006ac86  mov     edx, 152Bh
0x18006ac8b  jmp     short loc_18006AC40
0x18006ac8d  cmp     [rsp+340h+var_300], r15b
0x18006ac92  jz      short loc_18006ACA2
0x18006ac94  lea     rax, aHasanyclasses; "hasAnyClasses"
0x18006ac9b  mov     edx, 152Ch
0x18006aca0  jmp     short loc_18006AC3B
0x18006aca2  mov     rax, [r14]
0x18006aca5  mov     rcx, r14
0x18006aca8  mov     rax, [rax]
0x18006acab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acb0  mov     qword ptr [rsp+340h+var_2D0], rax
0x18006acb5  lea     rdx, [rsp+340h+var_2D0]
0x18006acba  lea     rcx, [rbp+240h+var_290]
0x18006acbe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006acc3  nop
0x18006acc4  mov     [rsp+340h+var_2E8], r15
0x18006acc9  lea     rax, [rsp+340h+var_2E8]
0x18006acce  mov     [rsp+340h+var_320], rax
0x18006acd3  lea     r9, _GUID_82e99b35_ccbd_4e12_b426_ba25a40986c8
0x18006acda  xor     r8d, r8d
0x18006acdd  xor     edx, edx
0x18006acdf  lea     ecx, [rdx+1]
0x18006ace2  call    cs:__imp_RoGetRegistrationStoreContext
0x18006ace9  nop     dword ptr [rax+rax+00h]
0x18006acee  mov     ebx, eax
0x18006acf0  test    eax, eax
0x18006acf2  jns     short loc_18006AD28
0x18006acf4  mov     rcx, [rbp+248h]; this
0x18006acfb  mov     dword ptr [rsp+340h+var_318], eax; char *
0x18006acff  lea     rax, aRogetregistrat; "RoGetRegistrationStoreContext(Windows::"...
0x18006ad06  mov     [rsp+340h+var_320], rax; char *
0x18006ad0b  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006ad12  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006ad19  mov     edx, 1532h; void *
0x18006ad1e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006ad23  jmp     loc_18006B172
0x18006ad28  mov     [rsp+340h+var_2F8], r15
0x18006ad2d  mov     rcx, [rsp+340h+var_2E8]
0x18006ad32  mov     rax, [rcx]
0x18006ad35  lea     r8, [rsp+340h+var_2F8]
0x18006ad3a  lea     rdx, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x18006ad41  mov     rax, [rax]
0x18006ad44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad49  mov     ebx, eax
0x18006ad4b  test    eax, eax
0x18006ad4d  jns     short loc_18006AD83
0x18006ad4f  mov     dword ptr [rsp+340h+var_318], eax; char *
0x18006ad53  lea     rax, aRegistrationst_20; "registrationStoreContext.query_to(&pack"...
0x18006ad5a  mov     edx, 1535h; void *
0x18006ad5f  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006ad66  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006ad6d  mov     [rsp+340h+var_320], rax; char *
0x18006ad72  mov     rcx, [rbp+248h]; this
0x18006ad79  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006ad7e  jmp     loc_18006B167
0x18006ad83  lea     rcx, [rbp+240h+var_270]; this
0x18006ad87  call    ??0ComServerRegistrationEntryProperties@@QEAA@XZ; ComServerRegistrationEntryProperties::ComServerRegistrationEntryProperties(void)
0x18006ad8c  nop
0x18006ad8d  mov     rcx, [rsp+340h+var_2F8]
0x18006ad92  mov     rax, [rcx]
0x18006ad95  mov     [rsp+340h+var_318], r15
0x18006ad9a  mov     [rsp+340h+var_320], r15
0x18006ad9f  lea     r9, [rbp+240h+var_270]
0x18006ada3  mov     r8d, [rdi+18h]
0x18006ada7  mov     rdx, [rbp+240h+var_278]
0x18006adab  mov     rax, [rax+50h]
0x18006adaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adb4  mov     ebx, eax
0x18006adb6  cmp     eax, 80070002h
0x18006adbb  jz      short loc_18006AE0D
0x18006adbd  test    eax, eax
0x18006adbf  js      short loc_18006ADCF
0x18006adc1  lea     rcx, [rbp+240h+var_270]; this
0x18006adc5  call    ??1ComServerRegistrationEntryProperties@@QEAA@XZ; ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)
0x18006adca  inc     dword ptr [rdi+18h]
0x18006adcd  jmp     short loc_18006AD83
0x18006adcf  mov     rcx, [rbp+248h]; this
0x18006add6  mov     dword ptr [rsp+340h+var_318], ebx; char *
0x18006adda  lea     rax, aHrreadentry; "hrReadEntry"
0x18006ade1  mov     [rsp+340h+var_320], rax; char *
0x18006ade6  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006aded  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006adf4  mov     edx, 1540h; void *
0x18006adf9  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006adfe  nop
0x18006adff  lea     rcx, [rbp+240h+var_270]; this
0x18006ae03  call    ??1ComServerRegistrationEntryProperties@@QEAA@XZ; ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)
0x18006ae08  jmp     loc_18006B167
0x18006ae0d  lea     rcx, [rbp+240h+var_270]; this
0x18006ae11  call    ??1ComServerRegistrationEntryProperties@@QEAA@XZ; ComServerRegistrationEntryProperties::~ComServerRegistrationEntryProperties(void)
0x18006ae16  mov     [rsp+340h+var_2D8], r15
0x18006ae1b  mov     rcx, [rsp+340h+var_2F8]
0x18006ae20  mov     rax, [rcx]
0x18006ae23  lea     r8, [rsp+340h+var_2D8]
0x18006ae28  mov     rdx, [rbp+240h+var_278]
0x18006ae2c  mov     rax, [rax+90h]
0x18006ae33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae38  mov     ebx, eax
0x18006ae3a  test    eax, eax
0x18006ae3c  jns     short loc_18006AE53
0x18006ae3e  mov     dword ptr [rsp+340h+var_318], eax
0x18006ae42  lea     rax, aPackagedcomcon_0; "packagedComContext->GetComClassEntriesF"...
0x18006ae49  mov     edx, 1548h
0x18006ae4e  jmp     loc_18006AD5F
0x18006ae53  mov     rbx, [rsp+340h+var_2E8]
0x18006ae58  test    rbx, rbx
0x18006ae5b  jz      short loc_18006AE6D
0x18006ae5d  mov     rax, [rbx]
0x18006ae60  mov     rcx, rbx
0x18006ae63  mov     rax, [rax+8]
0x18006ae67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae6c  nop
0x18006ae6d  lea     rax, [rsp+340h+var_2D8]
0x18006ae72  mov     qword ptr [rbp+240h+var_2A0+8], rax
0x18006ae76  mov     qword ptr [rbp+240h+var_2A0], r15
0x18006ae7a  mov     [rbp+240h+var_2C0], rbx
0x18006ae7e  lea     rax, [rsp+340h+var_2D8]
0x18006ae83  mov     [rbp+240h+var_2B8], rax
0x18006ae87  mov     [rbp+240h+var_2B0], 1
0x18006ae8b  lea     rcx, [rbp+240h+var_2A0]
0x18006ae8f  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18006ae94  mov     ebx, r15d
0x18006ae97  mov     [rsp+340h+var_300], r15b
0x18006ae9c  xorps   xmm0, xmm0
0x18006ae9f  movups  [rbp+240h+var_2A0], xmm0
0x18006aea3  mov     rcx, [rsp+340h+var_2F8]
0x18006aea8  mov     rax, [rcx]
0x18006aeab  lea     rdx, [rbp+240h+var_2A0]
0x18006aeaf  mov     [rsp+340h+var_320], rdx
0x18006aeb4  lea     r9, [rsp+340h+var_300]
0x18006aeb9  mov     r8d, ebx
0x18006aebc  mov     rdx, [rsp+340h+var_2D8]
0x18006aec1  mov     rax, [rax+98h]
0x18006aec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aecd  mov     esi, eax
0x18006aecf  test    eax, eax
0x18006aed1  js      loc_18006B1BC
0x18006aed7  cmp     [rsp+340h+var_300], r15b
0x18006aedc  jz      loc_18006B09D
0x18006aee2  lea     rcx, [rbp+240h+var_270]; this
0x18006aee6  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x18006aeeb  nop
0x18006aeec  mov     rcx, [rsp+340h+var_2F8]
0x18006aef1  mov     rax, [rcx]
0x18006aef4  mov     [rsp+340h+var_318], r15
0x18006aef9  mov     [rsp+340h+var_320], r15
0x18006aefe  lea     r9, [rbp+240h+var_270]
0x18006af02  lea     r8, [rbp+240h+var_2A0]
0x18006af06  mov     rdx, [rbp+240h+var_278]
0x18006af0a  mov     rax, [rax+48h]
0x18006af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af13  mov     esi, eax
0x18006af15  test    eax, eax
0x18006af17  js      loc_18006B048
0x18006af1d  lea     r8, [rbp+240h+var_270]
0x18006af21  lea     rdx, [rbp+240h+var_2A0]
0x18006af25  lea     rcx, [rsp+340h+var_2F0]
0x18006af2a  call    ??$Make@VComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAU_GUID@@UComClassRegistrationEntryProperties@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@12@AEAU_GUID@@$$QEAUComClassRegistrationEntryProperties@@@Z; Microsoft::WRL::Details::Make<OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties,_GUID &,ComClassRegistrationEntryProperties>(_GUID &,ComClassRegistrationEntryProperties &&)
0x18006af2f  mov     r8, [rsp+340h+var_2F0]
0x18006af34  test    r8, r8
0x18006af37  jz      loc_18006AFE9
0x18006af3d  mov     [rsp+340h+var_2FF], r15b
0x18006af42  mov     rcx, [rdi+28h]
0x18006af46  movaps  xmm0, [rbp+240h+var_2A0]
0x18006af4a  movdqa  [rsp+340h+var_2D0], xmm0
0x18006af50  mov     rax, [rcx]
0x18006af53  lea     r9, [rsp+340h+var_2FF]
0x18006af58  lea     rdx, [rsp+340h+var_2D0]
0x18006af5d  mov     rax, [rax+50h]
0x18006af61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af66  mov     esi, eax
0x18006af68  test    eax, eax
0x18006af6a  js      short loc_18006AF98
0x18006af6c  mov     rcx, [rsp+340h+var_2F0]
0x18006af71  test    rcx, rcx
0x18006af74  jz      short loc_18006AF88
0x18006af76  mov     [rsp+340h+var_2F0], r15
0x18006af7b  mov     rax, [rcx]
0x18006af7e  mov     rax, [rax+10h]
0x18006af82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af87  nop
0x18006af88  lea     rcx, [rbp+240h+var_270]; this
0x18006af8c  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18006af91  inc     ebx
0x18006af93  jmp     loc_18006AE97
0x18006af98  mov     rcx, [rbp+248h]; this
0x18006af9f  mov     dword ptr [rsp+340h+var_318], esi; char *
0x18006afa3  lea     rax, aClassesInsertC; "_classes->Insert(clsid, classProperties"...
0x18006afaa  mov     [rsp+340h+var_320], rax; char *
0x18006afaf  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006afb6  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006afbd  mov     edx, 1568h; void *
0x18006afc2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006afc7  nop
0x18006afc8  mov     rcx, [rsp+340h+var_2F0]
0x18006afcd  test    rcx, rcx
0x18006afd0  jz      short loc_18006AFE4
0x18006afd2  mov     [rsp+340h+var_2F0], r15
0x18006afd7  mov     rax, [rcx]
0x18006afda  mov     rax, [rax+10h]
0x18006afde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afe3  nop
0x18006afe4  jmp     loc_18006B078
0x18006afe9  mov     rcx, [rbp+248h]; this
0x18006aff0  mov     ebx, 8007000Eh
0x18006aff5  mov     dword ptr [rsp+340h+var_318], ebx; char *
0x18006aff9  lea     rax, aClasspropertie; "classProperties"
0x18006b000  mov     [rsp+340h+var_320], rax; char *
0x18006b005  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006b00c  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006b013  mov     edx, 1565h; void *
0x18006b018  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006b01d  nop
0x18006b01e  mov     rcx, [rsp+340h+var_2F0]
0x18006b023  test    rcx, rcx
0x18006b026  jz      short loc_18006B03A
0x18006b028  mov     [rsp+340h+var_2F0], r15
0x18006b02d  mov     rax, [rcx]
0x18006b030  mov     rax, [rax+10h]
0x18006b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b039  nop
0x18006b03a  lea     rcx, [rbp+240h+var_270]; this
0x18006b03e  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18006b043  jmp     loc_18006B15D
0x18006b048  mov     rcx, [rbp+248h]; this
0x18006b04f  mov     dword ptr [rsp+340h+var_318], esi; char *
0x18006b053  lea     rax, aPackagedcomcon; "packagedComContext->ReadComClassEntry(p"...
0x18006b05a  mov     [rsp+340h+var_320], rax; char *
0x18006b05f  lea     r9, aOsintegrationD_325; "OSIntegration::DEH::PackagedComCatalogC"...
0x18006b066  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006b06d  mov     edx, 1562h; void *
0x18006b072  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18006b077  nop
0x18006b078  lea     rcx, [rbp+240h+var_270]; this
0x18006b07c  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18006b081  nop
0x18006b082  lea     rcx, [rbp+240h+var_2C0]
0x18006b086  call    ??1?$lambda_call@V_lambda_8ce200d1f4a832bb238a4f943de436cf_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>::~lambda_call<_lambda_8ce200d1f4a832bb238a4f943de436cf_>(void)
0x18006b08b  nop
0x18006b08c  lea     rcx, [rsp+340h+var_2F8]
0x18006b091  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18006b096  mov     ebx, esi
0x18006b098  jmp     loc_18006B172
0x18006b09d  mov     rax, [r14]
0x18006b0a0  mov     rcx, r14
0x18006b0a3  mov     rax, [rax+48h]
0x18006b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0ac  mov     rdx, [rax+48h]
0x18006b0b0  lea     rcx, [rsp+340h+var_2D0]
0x18006b0b5  call    ??0?$com_ptr_t@UIXMLDOMElement@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIXMLDOMElement@@@Z; wil::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>::com_ptr_t<IXMLDOMElement,wil::err_exception_policy>(IXMLDOMElement *)
0x18006b0ba  nop
0x18006b0bb  mov     rcx, qword ptr [rsp+340h+var_2D0]
0x18006b0c0  test    rcx, rcx
0x18006b0c3  jz      loc_18006B18D
0x18006b0c9  mov     [rsp+340h+var_2E0], r15
0x18006b0ce  mov     rax, [rcx]
0x18006b0d1  lea     r8, [rsp+340h+var_2E0]
0x18006b0d6  lea     rdx, _GUID_ad2079f6_143d_485e_b9f2_8037a4e0128b
0x18006b0dd  mov     rax, [rax]
0x18006b0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0e5  mov     ebx, eax
0x18006b0e7  test    eax, eax
0x18006b0e9  jns     short loc_18006B0FD
0x18006b0eb  mov     dword ptr [rsp+340h+var_318], eax
  ... truncated ...
```
