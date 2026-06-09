# Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::Create(IXMLDOMNode *,ushort const *,ushort const *,IAppxBundleManifestPackageInfo * *)

- ea: `0x18000e420`
- end: `0x18000eae1`
- name: `?Create@BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAUIAppxBundleManifestPackageInfo@@@Z`
- size: `1729`
- prototype: `static int(struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, struct IAppxBundleManifestPackageInfo **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180057560`

## callees

- `0x180005eb8`
- `0x18000e420`
- `0x18000f24c`
- `0x180010f40`
- `0x1800133fc`
- `0x180071f50`
- `0x1800992d0`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e55d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e992`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e6b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e88e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e92d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e955`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e6b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e88e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e92d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e955`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e830`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e830`

## string_xrefs

- `0x18000e66e`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000e690`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000e942`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000e9f9`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000ea4b`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000ea71`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000ea97`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000e5de`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x18000e75d`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::Create(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IAppxBundleManifestPackageInfo **a4)
{
  void *v7; // rax
  void *v8; // r15
  struct Microsoft::WRL::Details::ModuleBase *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  int v17; // eax
  struct Common::AutoBStr *v18; // r9
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rax
  __int64 v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v26; // ebx
  OLECHAR *v27; // rcx
  char *v28; // rax
  char *v29; // rdi
  int v30; // eax
  OLECHAR *v31; // rdi
  __int64 v32; // rcx
  int v33; // eax
  int v34; // eax
  BSTR v35; // rcx
  BSTR v36; // rcx
  unsigned int i; // r9d
  char *v38; // rax
  char *v39; // r8
  int v40; // ecx
  int v41; // edx
  __int64 v42; // rdx
  char *v43; // rax
  char *v44; // rdi
  __int64 v45; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-40h] BYREF
  int v47; // [rsp+28h] [rbp-38h] BYREF
  const unsigned __int16 *v48; // [rsp+30h] [rbp-30h]
  int v49; // [rsp+38h] [rbp-28h]
  const wchar_t *v50; // [rsp+40h] [rbp-20h]
  int v51; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  BSTR v53; // [rsp+90h] [rbp+30h] BYREF
  struct IAppxBundleManifestPackageInfo **v54; // [rsp+A8h] [rbp+48h]

  v54 = a4;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      (int)bstrString);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      (int)bstrString);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      (int)bstrString);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      (int)bstrString);
    return 2147500035LL;
  }
  *a4 = 0;
  v7 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    v13 = -2147024882;
    goto LABEL_32;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>(v7);
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'};
  *(_QWORD *)v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo'};
  v9 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_QWORD *)v8 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo3'};
  *((_QWORD *)v8 + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'};
  if ( v9 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v9 + 8LL))(v9);
  *(_QWORD *)v8 = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo'};
  *((_QWORD *)v8 + 1) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'};
  *((_QWORD *)v8 + 2) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo3'};
  *((_QWORD *)v8 + 3) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'};
  *((_QWORD *)v8 + 5) = 0;
  *((_DWORD *)v8 + 12) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_QWORD *)v8 + 8) = 0;
  *((_QWORD *)v8 + 9) = 0;
  *((_DWORD *)v8 + 20) = 0;
  *((_QWORD *)v8 + 11) = 0;
  *((_QWORD *)v8 + 12) = 0;
  *((_QWORD *)v8 + 13) = 0;
  *((_QWORD *)v8 + 14) = 0;
  ((void (__fastcall *)(struct IXMLDOMNode *))a1->lpVtbl->AddRef)(a1);
  v10 = *((_QWORD *)v8 + 5);
  *((_QWORD *)v8 + 5) = a1;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  CoTaskMemFree(*((LPVOID *)v8 + 13));
  *((_QWORD *)v8 + 13) = 0;
  v11 = 0x7FFFFFFF;
  v12 = a2;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = -2147024809;
  if ( !v11 )
    goto LABEL_29;
  v13 = -2147024882;
  v14 = (unsigned int)(0x7FFFFFFF - v11);
  if ( (unsigned int)v14 > 0x3FFFFFFF )
  {
    v17 = -2147024809;
  }
  else
  {
    v15 = 2 * v14;
    if ( (unsigned __int64)(2 * v14) > 0xFFFFFFFF )
    {
      v16 = 27;
      goto LABEL_18;
    }
    if ( (int)v15 + 2 < (unsigned int)v15 )
    {
      v16 = 29;
LABEL_18:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        (int)bstrString);
LABEL_19:
      *((_QWORD *)v8 + 13) = 0;
      v17 = -2147024882;
      goto LABEL_20;
    }
    v28 = (char *)CoTaskMemAlloc((unsigned int)(v15 + 2));
    v29 = v28;
    if ( !v28 )
      goto LABEL_19;
    memcpy_0(v28, a2, (unsigned int)v15);
    v17 = 0;
    *(_WORD *)&v29[v15] = 0;
    *((_QWORD *)v8 + 13) = v29;
  }
LABEL_20:
  if ( v17 < 0 )
  {
    v13 = v17;
LABEL_29:
    v24 = 70;
LABEL_30:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v13,
      (int)bstrString);
LABEL_31:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_32:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v13,
      (int)bstrString);
    return (unsigned int)v13;
  }
  CoTaskMemFree(*((LPVOID *)v8 + 14));
  v19 = 0x7FFFFFFF;
  *((_QWORD *)v8 + 14) = 0;
  v20 = a3;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  if ( !v19 )
  {
    v13 = -2147024809;
    goto LABEL_85;
  }
  v21 = (unsigned int)(0x7FFFFFFF - v19);
  if ( (unsigned int)v21 > 0x3FFFFFFF )
  {
    v13 = -2147024809;
  }
  else
  {
    v22 = 2 * v21;
    if ( (unsigned __int64)(2 * v21) > 0xFFFFFFFF )
    {
      v23 = 27;
LABEL_40:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        (int)bstrString);
LABEL_41:
      *((_QWORD *)v8 + 14) = 0;
      goto LABEL_42;
    }
    if ( (int)v22 + 2 < (unsigned int)v22 )
    {
      v23 = 29;
      goto LABEL_40;
    }
    v43 = (char *)CoTaskMemAlloc((unsigned int)(v22 + 2));
    v44 = v43;
    if ( !v43 )
      goto LABEL_41;
    memcpy_0(v43, a3, (unsigned int)v22);
    *(_WORD *)&v44[v22] = 0;
    *((_QWORD *)v8 + 14) = v44;
    v13 = 0;
  }
LABEL_42:
  if ( v13 < 0 )
  {
LABEL_85:
    v24 = 71;
    goto LABEL_30;
  }
  bstrString = 0;
  v48 = L"Type";
  v53 = 0;
  v26 = 1;
  v50 = L"']";
  v47 = 5;
  v49 = 4;
  v51 = 0;
  v30 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&v47,
          (const struct Appx::Packaging::XPathComponent *)1,
          &v53,
          v18);
  v13 = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v30,
      (int)bstrString);
    SysFreeString(v53);
    goto LABEL_65;
  }
  v31 = v53;
  v32 = *((_QWORD *)v8 + 5);
  v53 = 0;
  bstrString = 0;
  v33 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR *))(*(_QWORD *)v32 + 296LL))(v32, v31, &v53);
  v13 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v33,
      (int)bstrString);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
    goto LABEL_54;
  }
  if ( !v53 )
  {
    v13 = 0;
    goto LABEL_54;
  }
  v34 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v53 + 208LL))(v53, &bstrString);
  v13 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v34,
      (int)bstrString);
  }
  else if ( !SysStringLen(bstrString) )
  {
    v35 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v13 = 0;
    goto LABEL_54;
  }
  v36 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v36 + 16LL))(v36);
  }
LABEL_54:
  SysFreeString(v31);
  if ( v13 < 0 )
  {
LABEL_65:
    v42 = 74;
LABEL_66:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v13,
      (int)bstrString);
    SysFreeString(bstrString);
    goto LABEL_31;
  }
  if ( v8 == (void *)-48LL )
  {
    v13 = -2147467261;
    v45 = 373;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v13,
      (int)bstrString);
    v42 = 75;
    goto LABEL_66;
  }
  if ( bstrString )
  {
    for ( i = 0; i < 2; ++i )
    {
      v38 = (char *)*((_QWORD *)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 2 * i);
      v39 = (char *)((char *)bstrString - v38);
      do
      {
        v40 = *(unsigned __int16 *)&v39[(_QWORD)v38];
        v41 = *(unsigned __int16 *)v38 - v40;
        if ( v41 )
          break;
        v38 += 2;
      }
      while ( v40 );
      if ( !v41 )
      {
        v26 = *((_DWORD *)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 4 * i + 2);
        goto LABEL_34;
      }
    }
    v13 = -2147024809;
    v45 = 391;
    goto LABEL_78;
  }
LABEL_34:
  v27 = bstrString;
  *((_DWORD *)v8 + 12) = v26;
  SysFreeString(v27);
  v13 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IAppxBundleManifestPackageInfo **))v8)(
          v8,
          &GUID_54cd06c1_268f_40bb_8ed2_757a9ebaec8d,
          v54);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v13 < 0 )
    goto LABEL_32;
  return 0;
}

```

## disassembly

```asm
0x18000e420  mov     r11, rsp
0x18000e423  mov     [r11+20h], r9
0x18000e427  push    rbp
0x18000e428  push    rbx
0x18000e429  push    rsi
0x18000e42a  push    r13
0x18000e42c  push    r14
0x18000e42e  mov     rbp, rsp
0x18000e431  sub     rsp, 60h
0x18000e435  mov     rax, r9
0x18000e438  mov     r13, r8
0x18000e43b  mov     rsi, rdx
0x18000e43e  mov     rbx, rcx
0x18000e441  test    rcx, rcx
0x18000e444  jz      loc_18000EA47
0x18000e44a  test    rdx, rdx
0x18000e44d  jz      loc_18000EA6D
0x18000e453  test    r8, r8
0x18000e456  jz      loc_18000E9F5
0x18000e45c  test    rax, rax
0x18000e45f  jz      loc_18000EA93
0x18000e465  mov     [r11+10h], rdi
0x18000e469  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e470  mov     [r11-30h], r12
0x18000e474  xor     edi, edi
0x18000e476  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000e47b  mov     [r9], rdi
0x18000e47e  mov     [r11-38h], r15
0x18000e482  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e487  mov     r15, rax
0x18000e48a  test    rax, rax
0x18000e48d  jz      loc_18000EAB9
0x18000e493  mov     rcx, rax
0x18000e496  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAppxBundleWriter@@UIAppxBundleWriter2@@UIAppxBundleWriter3@@UIAppxBundleWriter4@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>(void)
0x18000e49b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'}
0x18000e4a2  mov     [r15+8], rax
0x18000e4a6  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6BIAppxBundleManifestPackageInfo@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo'}
0x18000e4ad  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6BIAppxBundleManifestPackageInfo3@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo3'}
0x18000e4b4  mov     [r15], rcx
0x18000e4b7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e4be  mov     [r15+10h], rax
0x18000e4c2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo4@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'}
0x18000e4c9  mov     [r15+18h], rax
0x18000e4cd  test    rcx, rcx
0x18000e4d0  jz      short loc_18000E4DE
0x18000e4d2  mov     rax, [rcx]
0x18000e4d5  mov     rax, [rax+8]
0x18000e4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4de  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6BIAppxBundleManifestPackageInfo@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo'}
0x18000e4e5  mov     rcx, rbx
0x18000e4e8  mov     [r15], rax
0x18000e4eb  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@Details@WRL@Microsoft@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'}
0x18000e4f2  mov     [r15+8], rax
0x18000e4f6  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6BIAppxBundleManifestPackageInfo3@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo3'}
0x18000e4fd  mov     [r15+10h], rax
0x18000e501  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo4@@@Details@WRL@Microsoft@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'}
0x18000e508  mov     [r15+18h], rax
0x18000e50c  mov     [r15+28h], rdi
0x18000e510  mov     [r15+30h], edi
0x18000e514  mov     [r15+38h], rdi
0x18000e518  mov     [r15+40h], rdi
0x18000e51c  mov     [r15+48h], rdi
0x18000e520  mov     [r15+50h], edi
0x18000e524  mov     [r15+58h], rdi
0x18000e528  mov     [r15+60h], rdi
0x18000e52c  mov     [r15+68h], rdi
0x18000e530  mov     [r15+70h], rdi
0x18000e534  mov     rax, [rbx]
0x18000e537  mov     rax, [rax+8]
0x18000e53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e540  mov     rcx, [r15+28h]
0x18000e544  mov     [r15+28h], rbx
0x18000e548  test    rcx, rcx
0x18000e54b  jz      short loc_18000E559
0x18000e54d  mov     rax, [rcx]
0x18000e550  mov     rax, [rax+10h]
0x18000e554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e559  mov     rcx, [r15+68h]; pv
0x18000e55d  call    cs:__imp_CoTaskMemFree
0x18000e564  nop     dword ptr [rax+rax+00h]
0x18000e569  mov     r12d, 7FFFFFFFh
0x18000e56f  mov     [r15+68h], rdi
0x18000e573  mov     ecx, r12d
0x18000e576  mov     rax, rsi
0x18000e579  nop     dword ptr [rax+00000000h]
0x18000e580  cmp     [rax], di
0x18000e583  jz      short loc_18000E58F
0x18000e585  add     rax, 2
0x18000e589  sub     rcx, 1
0x18000e58d  jnz     short loc_18000E580
0x18000e58f  test    rcx, rcx
0x18000e592  mov     r14d, 80070057h
0x18000e598  cmovnz  r14d, edi
0x18000e59c  jz      loc_18000E665
0x18000e5a2  mov     eax, r12d
0x18000e5a5  mov     r14d, 8007000Eh
0x18000e5ab  sub     eax, ecx
0x18000e5ad  mov     ecx, 0FFFFFFFFh
0x18000e5b2  cmp     eax, 3FFFFFFFh
0x18000e5b7  ja      loc_18000E9D2
0x18000e5bd  lea     rbx, [rax+rax]
0x18000e5c1  cmp     rbx, rcx
0x18000e5c4  ja      loc_18000E9C8
0x18000e5ca  lea     eax, [rbx+2]
0x18000e5cd  cmp     eax, ebx
0x18000e5cf  jnb     loc_18000E710
0x18000e5d5  mov     edx, 1Dh; void *
0x18000e5da  mov     rcx, [rbp+28h]; this
0x18000e5de  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18000e5e5  mov     r9d, 80070216h; char *
0x18000e5eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e5f0  mov     [r15+68h], rdi
0x18000e5f4  mov     eax, r14d
0x18000e5f7  test    eax, eax
0x18000e5f9  js      short loc_18000E662
0x18000e5fb  mov     rcx, [r15+70h]; pv
0x18000e5ff  call    cs:__imp_CoTaskMemFree
0x18000e606  nop     dword ptr [rax+rax+00h]
0x18000e60b  mov     rcx, r12
0x18000e60e  mov     [r15+70h], rdi
0x18000e612  mov     rax, r13
0x18000e615  cmp     word ptr [rax], 0
0x18000e619  jz      short loc_18000E625
0x18000e61b  add     rax, 2
0x18000e61f  sub     rcx, 1
0x18000e623  jnz     short loc_18000E615
0x18000e625  test    rcx, rcx
0x18000e628  mov     edx, 80070057h
0x18000e62d  cmovnz  edx, edi
0x18000e630  jz      loc_18000EAD4
0x18000e636  sub     r12d, ecx
0x18000e639  cmp     r12d, 3FFFFFFFh
0x18000e640  ja      loc_18000E9DC
0x18000e646  lea     rbx, [r12+r12]
0x18000e64a  mov     eax, 0FFFFFFFFh
0x18000e64f  cmp     rbx, rax
0x18000e652  jbe     loc_18000E749
0x18000e658  mov     edx, 1Bh
0x18000e65d  jmp     loc_18000E759
0x18000e662  mov     r14d, eax
0x18000e665  mov     edx, 46h ; 'F'; void *
0x18000e66a  mov     rcx, [rbp+28h]; this
0x18000e66e  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x18000e675  mov     r9d, r14d; char *
0x18000e678  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e67d  mov     rcx, [r15]
0x18000e680  mov     rax, [rcx+10h]
0x18000e684  mov     rcx, r15
0x18000e687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e68c  mov     rcx, [rbp+28h]; this
0x18000e690  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x18000e697  mov     r9d, r14d; char *
0x18000e69a  mov     edx, 35h ; '5'; void *
0x18000e69f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e6a4  mov     eax, r14d
0x18000e6a7  jmp     short loc_18000E6F1
0x18000e6a9  mov     ebx, [rdi+rbx*8+8]
0x18000e6ad  mov     rcx, r10; bstrString
0x18000e6b0  mov     [r11], ebx
0x18000e6b3  call    cs:__imp_SysFreeString
0x18000e6ba  nop     dword ptr [rax+rax+00h]
0x18000e6bf  mov     rax, [r15]
0x18000e6c2  lea     rdx, _GUID_54cd06c1_268f_40bb_8ed2_757a9ebaec8d
0x18000e6c9  mov     r8, [rbp+arg_18]
0x18000e6cd  mov     rcx, r15
0x18000e6d0  mov     rax, [rax]
0x18000e6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d8  mov     r14d, eax
0x18000e6db  mov     rcx, r15
0x18000e6de  mov     rax, [r15]
0x18000e6e1  mov     rax, [rax+10h]
0x18000e6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ea  test    r14d, r14d
0x18000e6ed  js      short loc_18000E68C
0x18000e6ef  xor     eax, eax
0x18000e6f1  mov     r12, [rsp+60h+var_8]
0x18000e6f6  mov     rdi, [rsp+60h+arg_8]
0x18000e6fe  mov     r15, [rsp+60h+var_10]
0x18000e703  add     rsp, 60h
0x18000e707  pop     r14
0x18000e709  pop     r13
0x18000e70b  pop     rsi
0x18000e70c  pop     rbx
0x18000e70d  pop     rbp
0x18000e70e  retn
0x18000e710  mov     ecx, eax; cb
0x18000e712  call    cs:__imp_CoTaskMemAlloc
0x18000e719  nop     dword ptr [rax+rax+00h]
0x18000e71e  mov     rdi, rax
0x18000e721  test    rax, rax
0x18000e724  jz      loc_18000E9E7
0x18000e72a  mov     r8d, ebx; Size
0x18000e72d  mov     rdx, rsi; Src
0x18000e730  mov     rcx, rax; void *
0x18000e733  call    memcpy_0
0x18000e738  xor     eax, eax
0x18000e73a  mov     [rbx+rdi], ax
0x18000e73e  mov     [r15+68h], rdi
0x18000e742  xor     edi, edi
0x18000e744  jmp     loc_18000E5F7
0x18000e749  lea     eax, [rbx+2]
0x18000e74c  cmp     eax, ebx
0x18000e74e  jnb     loc_18000E990
0x18000e754  mov     edx, 1Dh; void *
0x18000e759  mov     rcx, [rbp+28h]; this
0x18000e75d  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18000e764  mov     r9d, 80070216h; char *
0x18000e76a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e76f  mov     [r15+70h], rdi
0x18000e773  test    r14d, r14d
0x18000e776  js      loc_18000EAD7
0x18000e77c  lea     rax, ?PackageType@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Type"
0x18000e783  mov     [rbp+bstrString], rdi
0x18000e787  mov     [rbp+var_30], rax
0x18000e78b  lea     r8, [rbp+arg_0]; unsigned int
0x18000e78f  lea     rax, asc_1801177B4; "']"
0x18000e796  mov     [rbp+arg_0], rdi
0x18000e79a  mov     ebx, 1
0x18000e79f  mov     [rbp+var_20], rax
0x18000e7a3  mov     edx, ebx; struct Appx::Packaging::XPathComponent *
0x18000e7a5  mov     [rbp+var_38], 5
0x18000e7ac  lea     rcx, [rbp+var_38]; this
0x18000e7b0  mov     [rbp+var_28], 4
0x18000e7b7  mov     [rbp+var_18], edi
0x18000e7ba  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18000e7bf  mov     r14d, eax
0x18000e7c2  test    eax, eax
0x18000e7c4  js      loc_18000E911
0x18000e7ca  mov     rdi, [rbp+arg_0]
0x18000e7ce  lea     r8, [rbp+arg_0]
0x18000e7d2  mov     rcx, [r15+28h]
0x18000e7d6  xor     r12d, r12d
0x18000e7d9  mov     [rbp+arg_0], r12
0x18000e7dd  mov     rdx, rdi
0x18000e7e0  mov     [rbp+bstrString], r12
0x18000e7e4  mov     rax, [rcx]
0x18000e7e7  mov     rax, [rax+128h]
0x18000e7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f3  lea     rsi, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18000e7fa  mov     r14d, eax
0x18000e7fd  test    eax, eax
0x18000e7ff  js      loc_18000E96E
0x18000e805  mov     rcx, [rbp+arg_0]
0x18000e809  test    rcx, rcx
0x18000e80c  jz      loc_18000E966
0x18000e812  mov     rax, [rcx]
0x18000e815  lea     rdx, [rbp+bstrString]
0x18000e819  mov     rax, [rax+0D0h]
0x18000e820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e825  mov     r14d, eax
0x18000e828  test    eax, eax
0x18000e82a  js      short loc_18000E85E
0x18000e82c  mov     rcx, [rbp+bstrString]; pbstr
0x18000e830  call    cs:__imp_SysStringLen
0x18000e837  nop     dword ptr [rax+rax+00h]
0x18000e83c  test    eax, eax
0x18000e83e  jnz     short loc_18000E872
0x18000e840  mov     rcx, [rbp+arg_0]
0x18000e844  test    rcx, rcx
0x18000e847  jz      short loc_18000E859
0x18000e849  mov     [rbp+arg_0], r12
0x18000e84d  mov     rax, [rcx]
0x18000e850  mov     rax, [rax+10h]
0x18000e854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e859  mov     r14d, r12d
0x18000e85c  jmp     short loc_18000E88B
0x18000e85e  mov     rcx, [rbp+28h]; this
0x18000e862  mov     r9d, eax; char *
0x18000e865  mov     r8, rsi; unsigned int
0x18000e868  mov     edx, 51h ; 'Q'; void *
0x18000e86d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e872  mov     rcx, [rbp+arg_0]
0x18000e876  test    rcx, rcx
0x18000e879  jz      short loc_18000E88B
0x18000e87b  mov     [rbp+arg_0], r12
0x18000e87f  mov     rax, [rcx]
0x18000e882  mov     rax, [rax+10h]
0x18000e886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88b  mov     rcx, rdi; bstrString
0x18000e88e  call    cs:__imp_SysFreeString
0x18000e895  nop     dword ptr [rax+rax+00h]
0x18000e89a  test    r14d, r14d
0x18000e89d  js      loc_18000E939
0x18000e8a3  lea     r11, [r15+30h]
0x18000e8a7  test    r11, r11
0x18000e8aa  jz      loc_18000EA23
0x18000e8b0  mov     r10, [rbp+bstrString]
0x18000e8b4  test    r10, r10
0x18000e8b7  jz      loc_18000E6AD
0x18000e8bd  mov     r9d, r12d
0x18000e8c0  lea     rdi, ?PackageTypeValues@Attribute@BundleManifest@Packaging@Appx@@3QBUPackageTypeTable@1234@B; Appx::Packaging::BundleManifest::Attribute::PackageTypeTable const near * const Appx::Packaging::BundleManifest::Attribute::PackageTypeValues
0x18000e8c7  nop     word ptr [rax+rax+00000000h]
0x18000e8d0  cmp     r9d, 2
0x18000e8d4  jnb     loc_18000EAC4
0x18000e8da  mov     ebx, r9d
0x18000e8dd  mov     r8, r10
0x18000e8e0  add     rbx, rbx
0x18000e8e3  mov     rax, [rdi+rbx*8]
0x18000e8e7  sub     r8, rax
0x18000e8ea  nop     word ptr [rax+rax+00h]
  ... truncated ...
```
