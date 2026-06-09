# Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::GetCurrent(IAppxBundleManifestPackageInfo * *)

- ea: `0x18000eaf0`
- end: `0x18000f245`
- name: `?GetCurrent@?$AppxManifestObjectEnumerator@UIAppxBundleManifestPackageInfoEnumerator@@UIAppxBundleManifestPackageInfo@@VBundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@$01@Manifest@Packaging@Appx@@UEAAJPEAPEAUIAppxBundleManifestPackageInfo@@@Z`
- size: `1877`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x18000eaf0`
- `0x18000f24c`
- `0x180010f40`
- `0x1800133fc`
- `0x180071f50`
- `0x1800992d0`
- `0x18009d729`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000edfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ec6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000edfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f0cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f0cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecf1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f02d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f055`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecf1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef9a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f02d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f055`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ef3c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ef3c`

## string_xrefs

- `0x18000f124`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18000f196`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18000f1b3`: `onecore\printscan\AppxPackaging\Manifest\src\AppxManifestEnumerator.hpp`
- `0x18000ed7e`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000eda3`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000f042`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000f14f`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000f1db`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000f1fe`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x18000edd0`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x18000ee68`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestObjectEnumerator<IAppxBundleManifestPackageInfoEnumerator,IAppxBundleManifestPackageInfo,Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl,2>::GetCurrent(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // rdi
  _WORD *v7; // rsi
  _WORD *v8; // r13
  void *v9; // rax
  void *v10; // r15
  struct Microsoft::WRL::Details::ModuleBase *v11; // rcx
  __int64 v12; // rcx
  _WORD *v13; // rax
  __int64 v14; // rcx
  int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  int v19; // ebx
  OLECHAR *v20; // rcx
  __int64 v21; // rcx
  __int64 v23; // rdx
  int v24; // eax
  struct Common::AutoBStr *v25; // r9
  __int64 v26; // rcx
  _WORD *v27; // rax
  __int64 v28; // r12
  __int64 v29; // rbx
  __int64 v30; // rdx
  int v31; // eax
  OLECHAR *v32; // rdi
  __int64 v33; // rcx
  BSTR v34; // rdx
  int v35; // eax
  int v36; // eax
  BSTR v37; // rcx
  BSTR v38; // rcx
  unsigned int i; // r9d
  char *v40; // rax
  char *v41; // r8
  int v42; // ecx
  int v43; // edx
  __int64 v44; // rdx
  char *v45; // rax
  char *v46; // rdi
  char *v47; // rax
  char *v48; // rdi
  __int64 v49; // rdx
  __int64 v50; // [rsp+20h] [rbp-50h] BYREF
  int v51; // [rsp+28h] [rbp-48h] BYREF
  const unsigned __int16 *v52; // [rsp+30h] [rbp-40h]
  int v53; // [rsp+38h] [rbp-38h]
  const wchar_t *v54; // [rsp+40h] [rbp-30h]
  int v55; // [rsp+48h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  BSTR v58; // [rsp+A0h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x80004003LL,
      v50);
    return 2147500035LL;
  }
  v4 = *(unsigned int *)(a1 + 28);
  v50 = 0;
  if ( (unsigned int)v4 >= *(_DWORD *)(a1 + 24) )
  {
    v5 = -2147483637;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)0x8000000BLL,
      v50);
    goto LABEL_84;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a1 + 16) + 56LL))(
         *(_QWORD *)(a1 + 16),
         v4,
         &v50);
  if ( v5 < 0 )
  {
LABEL_84:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\printscan\\AppxPackaging\\Manifest\\src\\AppxManifestEnumerator.hpp",
      (const char *)(unsigned int)v5,
      v50);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    return (unsigned int)v5;
  }
  v6 = v50;
  if ( !v50 )
  {
    v15 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      0);
    goto LABEL_22;
  }
  v7 = *(_WORD **)(a1 + 32);
  if ( !v7 )
  {
    v15 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      v50);
    goto LABEL_22;
  }
  v8 = *(_WORD **)(a1 + 40);
  if ( !v8 )
  {
    v15 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      v50);
    goto LABEL_22;
  }
  *a2 = 0;
  v9 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v15 = -2147024882;
    goto LABEL_29;
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>(v9);
  *((_QWORD *)v10 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'};
  *(_QWORD *)v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo'};
  v11 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_QWORD *)v10 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo3'};
  *((_QWORD *)v10 + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'};
  if ( v11 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v11 + 8LL))(v11);
  *(_QWORD *)v10 = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo'};
  *((_QWORD *)v10 + 1) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'};
  *((_QWORD *)v10 + 2) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo3'};
  *((_QWORD *)v10 + 3) = &Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'};
  *((_QWORD *)v10 + 5) = 0;
  *((_DWORD *)v10 + 12) = 0;
  *((_QWORD *)v10 + 7) = 0;
  *((_QWORD *)v10 + 8) = 0;
  *((_QWORD *)v10 + 9) = 0;
  *((_DWORD *)v10 + 20) = 0;
  *((_QWORD *)v10 + 11) = 0;
  *((_QWORD *)v10 + 12) = 0;
  *((_QWORD *)v10 + 13) = 0;
  *((_QWORD *)v10 + 14) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v12 = *((_QWORD *)v10 + 5);
  *((_QWORD *)v10 + 5) = v6;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  CoTaskMemFree(*((LPVOID *)v10 + 13));
  *((_QWORD *)v10 + 13) = 0;
  v13 = v7;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v15 = -2147024809;
  if ( !v14 )
    goto LABEL_26;
  v15 = -2147024882;
  v16 = (unsigned int)(0x7FFFFFFF - v14);
  if ( (unsigned int)v16 > 0x3FFFFFFF )
  {
    v24 = -2147024809;
  }
  else
  {
    v17 = 2 * v16;
    if ( (unsigned __int64)(2 * v16) > 0xFFFFFFFF )
    {
      v18 = 27;
LABEL_32:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        v50);
LABEL_33:
      *((_QWORD *)v10 + 13) = 0;
      v24 = -2147024882;
      goto LABEL_34;
    }
    if ( (int)v17 + 2 < (unsigned int)v17 )
    {
      v18 = 29;
      goto LABEL_32;
    }
    v45 = (char *)CoTaskMemAlloc((unsigned int)(v17 + 2));
    v46 = v45;
    if ( !v45 )
      goto LABEL_33;
    memcpy_0(v45, v7, (unsigned int)v17);
    *(_WORD *)&v46[v17] = 0;
    v24 = 0;
    *((_QWORD *)v10 + 13) = v46;
  }
LABEL_34:
  if ( v24 < 0 )
  {
    v15 = v24;
LABEL_26:
    v23 = 70;
LABEL_27:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v15,
      v50);
LABEL_28:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
    goto LABEL_29;
  }
  CoTaskMemFree(*((LPVOID *)v10 + 14));
  v26 = 0x7FFFFFFF;
  *((_QWORD *)v10 + 14) = 0;
  v27 = v8;
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  if ( !v26 )
  {
    v15 = -2147024809;
    goto LABEL_90;
  }
  v28 = (unsigned int)(0x7FFFFFFF - v26);
  if ( (unsigned int)v28 > 0x3FFFFFFF )
  {
    v15 = -2147024809;
  }
  else
  {
    v29 = 2 * v28;
    if ( (unsigned __int64)(2 * v28) > 0xFFFFFFFF )
    {
      v30 = 27;
      goto LABEL_43;
    }
    if ( (int)v29 + 2 < (unsigned int)v29 )
    {
      v30 = 29;
LABEL_43:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        v50);
LABEL_44:
      *((_QWORD *)v10 + 14) = 0;
      goto LABEL_45;
    }
    v47 = (char *)CoTaskMemAlloc((unsigned int)(v29 + 2));
    v48 = v47;
    if ( !v47 )
      goto LABEL_44;
    memcpy_0(v47, v8, (unsigned int)v29);
    *(_WORD *)&v48[v29] = 0;
    v15 = 0;
    *((_QWORD *)v10 + 14) = v48;
  }
LABEL_45:
  if ( v15 < 0 )
  {
LABEL_90:
    v23 = 71;
    goto LABEL_27;
  }
  v51 = 5;
  bstrString = 0;
  v52 = L"Type";
  v58 = 0;
  v19 = 1;
  v54 = L"']";
  v53 = 4;
  v55 = 0;
  v31 = Appx::Packaging::BuildXPath(
          (Appx::Packaging *)&v51,
          (const struct Appx::Packaging::XPathComponent *)1,
          (unsigned int)&v58,
          v25);
  v15 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v31,
      v50);
    SysFreeString(v58);
    goto LABEL_68;
  }
  v32 = v58;
  v33 = *((_QWORD *)v10 + 5);
  v34 = v58;
  v58 = 0;
  bstrString = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR *))(*(_QWORD *)v33 + 296LL))(v33, v34, &v58);
  v15 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v35,
      v50);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
    goto LABEL_57;
  }
  if ( !v58 )
  {
    v15 = 0;
    goto LABEL_57;
  }
  v36 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)v58 + 208LL))(v58, &bstrString);
  v15 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v36,
      v50);
  }
  else if ( !SysStringLen(bstrString) )
  {
    v37 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v15 = 0;
    goto LABEL_57;
  }
  v38 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v38 + 16LL))(v38);
  }
LABEL_57:
  SysFreeString(v32);
  if ( v15 < 0 )
  {
LABEL_68:
    v44 = 74;
LABEL_69:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v15,
      v50);
    SysFreeString(bstrString);
    goto LABEL_28;
  }
  if ( v10 == (void *)-48LL )
  {
    v15 = -2147467261;
    v49 = 373;
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v49,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v15,
      v50);
    v44 = 75;
    goto LABEL_69;
  }
  if ( bstrString )
  {
    for ( i = 0; i < 2; ++i )
    {
      v40 = (char *)*((_QWORD *)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 2 * i);
      v41 = (char *)((char *)bstrString - v40);
      do
      {
        v42 = *(unsigned __int16 *)&v41[(_QWORD)v40];
        v43 = *(unsigned __int16 *)v40 - v42;
        if ( v43 )
          break;
        v40 += 2;
      }
      while ( v42 );
      if ( !v43 )
      {
        v19 = *((_DWORD *)&Appx::Packaging::BundleManifest::Attribute::PackageTypeValues + 4 * i + 2);
        goto LABEL_20;
      }
    }
    v15 = -2147024809;
    v49 = 391;
    goto LABEL_82;
  }
LABEL_20:
  v20 = bstrString;
  *((_DWORD *)v10 + 12) = v19;
  SysFreeString(v20);
  v15 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v10)(v10, &GUID_54cd06c1_268f_40bb_8ed2_757a9ebaec8d, a2);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v15 < 0 )
  {
LABEL_29:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v15,
      v50);
    goto LABEL_22;
  }
  v15 = 0;
LABEL_22:
  v21 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000eaf0  mov     [rsp-18h+arg_8], rdx
0x18000eaf5  push    rbp
0x18000eaf6  push    rbx
0x18000eaf7  push    r14
0x18000eaf9  mov     rbp, rsp
0x18000eafc  sub     rsp, 70h
0x18000eb00  mov     r14, rdx
0x18000eb03  mov     rbx, rcx
0x18000eb06  test    rdx, rdx
0x18000eb09  jz      loc_18000F120
0x18000eb0f  mov     edx, [rcx+1Ch]
0x18000eb12  mov     [rsp+70h+var_8], rdi
0x18000eb17  mov     [rsp+70h+var_10], r12
0x18000eb1c  xor     r12d, r12d
0x18000eb1f  mov     [rbp+var_50], r12
0x18000eb23  cmp     edx, [rcx+18h]
0x18000eb26  jnb     loc_18000F192
0x18000eb2c  mov     rcx, [rcx+10h]
0x18000eb30  lea     r8, [rbp+var_50]
0x18000eb34  mov     rax, [rcx]
0x18000eb37  mov     rax, [rax+38h]
0x18000eb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb40  mov     edi, eax
0x18000eb42  test    eax, eax
0x18000eb44  js      loc_18000F1AF
0x18000eb4a  mov     rdi, [rbp+var_50]
0x18000eb4e  test    rdi, rdi
0x18000eb51  jz      loc_18000F1D7
0x18000eb57  mov     [rsp+70h+arg_0], rsi
0x18000eb5f  mov     rsi, [rbx+20h]
0x18000eb63  test    rsi, rsi
0x18000eb66  jz      loc_18000F1FA
0x18000eb6c  mov     [rsp+70h+var_18], r13
0x18000eb71  mov     r13, [rbx+28h]
0x18000eb75  test    r13, r13
0x18000eb78  jz      loc_18000F14B
0x18000eb7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb85  mov     [rsp+70h+var_20], r15
0x18000eb8a  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000eb8f  mov     [r14], r12
0x18000eb92  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000eb97  mov     r15, rax
0x18000eb9a  test    rax, rax
0x18000eb9d  jz      loc_18000F21D
0x18000eba3  mov     rcx, rax
0x18000eba6  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAppxBundleWriter@@UIAppxBundleWriter2@@UIAppxBundleWriter3@@UIAppxBundleWriter4@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAppxBundleWriter,IAppxBundleWriter2,IAppxBundleWriter3,IAppxBundleWriter4>(void)
0x18000ebab  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'}
0x18000ebb2  mov     [r15+8], rax
0x18000ebb6  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6BIAppxBundleManifestPackageInfo@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo'}
0x18000ebbd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6BIAppxBundleManifestPackageInfo3@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `IAppxBundleManifestPackageInfo3'}
0x18000ebc4  mov     [r15], rcx
0x18000ebc7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ebce  mov     [r15+10h], rax
0x18000ebd2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAppxBundleManifestPackageInfo@@UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo4@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAppxBundleManifestPackageInfo,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'}
0x18000ebd9  mov     [r15+18h], rax
0x18000ebdd  test    rcx, rcx
0x18000ebe0  jz      short loc_18000EBEE
0x18000ebe2  mov     rax, [rcx]
0x18000ebe5  mov     rax, [rax+8]
0x18000ebe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebee  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6BIAppxBundleManifestPackageInfo@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo'}
0x18000ebf5  mov     rcx, rdi
0x18000ebf8  mov     [r15], rax
0x18000ebfb  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo2@@UIAppxBundleManifestPackageInfo3@@UIAppxBundleManifestPackageInfo4@@@Details@WRL@Microsoft@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo2,IAppxBundleManifestPackageInfo3,IAppxBundleManifestPackageInfo4>'}
0x18000ec02  mov     [r15+8], rax
0x18000ec06  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6BIAppxBundleManifestPackageInfo3@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `IAppxBundleManifestPackageInfo3'}
0x18000ec0d  mov     [r15+10h], rax
0x18000ec11  lea     rax, ??_7BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIAppxBundleManifestPackageInfo4@@@Details@WRL@Microsoft@@@; const Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IAppxBundleManifestPackageInfo4>'}
0x18000ec18  mov     [r15+18h], rax
0x18000ec1c  mov     [r15+28h], r12
0x18000ec20  mov     [r15+30h], r12d
0x18000ec24  mov     [r15+38h], r12
0x18000ec28  mov     [r15+40h], r12
0x18000ec2c  mov     [r15+48h], r12
0x18000ec30  mov     [r15+50h], r12d
0x18000ec34  mov     [r15+58h], r12
0x18000ec38  mov     [r15+60h], r12
0x18000ec3c  mov     [r15+68h], r12
0x18000ec40  mov     [r15+70h], r12
0x18000ec44  mov     rax, [rdi]
0x18000ec47  mov     rax, [rax+8]
0x18000ec4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec50  mov     rcx, [r15+28h]
0x18000ec54  mov     [r15+28h], rdi
0x18000ec58  test    rcx, rcx
0x18000ec5b  jz      short loc_18000EC69
0x18000ec5d  mov     rax, [rcx]
0x18000ec60  mov     rax, [rax+10h]
0x18000ec64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec69  mov     rcx, [r15+68h]; pv
0x18000ec6d  call    cs:__imp_CoTaskMemFree
0x18000ec74  nop     dword ptr [rax+rax+00h]
0x18000ec79  mov     [r15+68h], r12
0x18000ec7d  mov     rax, rsi
0x18000ec80  mov     r12d, 7FFFFFFFh
0x18000ec86  mov     ecx, r12d
0x18000ec89  nop     dword ptr [rax+00000000h]
0x18000ec90  cmp     word ptr [rax], 0
0x18000ec94  jz      short loc_18000ECA0
0x18000ec96  add     rax, 2
0x18000ec9a  sub     rcx, 1
0x18000ec9e  jnz     short loc_18000EC90
0x18000eca0  xor     eax, eax
0x18000eca2  mov     r14d, 80070057h
0x18000eca8  test    rcx, rcx
0x18000ecab  cmovnz  r14d, eax
0x18000ecaf  jz      loc_18000ED75
0x18000ecb5  mov     eax, r12d
0x18000ecb8  mov     r14d, 8007000Eh
0x18000ecbe  sub     eax, ecx
0x18000ecc0  mov     ecx, 0FFFFFFFFh
0x18000ecc5  cmp     eax, 3FFFFFFFh
0x18000ecca  ja      loc_18000F10B
0x18000ecd0  lea     rbx, [rax+rax]
0x18000ecd4  cmp     rbx, rcx
0x18000ecd7  jbe     loc_18000EDBC
0x18000ecdd  mov     edx, 1Bh
0x18000ece2  jmp     loc_18000EDCC
0x18000ece7  mov     ebx, [rdi+rbx*8+8]
0x18000eceb  mov     rcx, r10; bstrString
0x18000ecee  mov     [r11], ebx
0x18000ecf1  call    cs:__imp_SysFreeString
0x18000ecf8  nop     dword ptr [rax+rax+00h]
0x18000ecfd  mov     rax, [r15]
0x18000ed00  lea     rdx, _GUID_54cd06c1_268f_40bb_8ed2_757a9ebaec8d
0x18000ed07  mov     r8, [rbp+arg_8]
0x18000ed0b  mov     rcx, r15
0x18000ed0e  mov     rax, [rax]
0x18000ed11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed16  mov     r14d, eax
0x18000ed19  mov     rcx, r15
0x18000ed1c  mov     rax, [r15]
0x18000ed1f  mov     rax, [rax+10h]
0x18000ed23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed28  test    r14d, r14d
0x18000ed2b  js      short loc_18000ED9F
0x18000ed2d  mov     r14d, r12d
0x18000ed30  mov     r15, [rsp+70h+var_20]
0x18000ed35  mov     r13, [rsp+70h+var_18]
0x18000ed3a  mov     rsi, [rsp+70h+arg_0]
0x18000ed42  mov     rcx, [rbp+var_50]
0x18000ed46  test    rcx, rcx
0x18000ed49  jz      short loc_18000ED5B
0x18000ed4b  mov     [rbp+var_50], r12
0x18000ed4f  mov     rdx, [rcx]
0x18000ed52  mov     rax, [rdx+10h]
0x18000ed56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed5b  mov     eax, r14d
0x18000ed5e  mov     rdi, [rsp+70h+var_8]
0x18000ed63  mov     r12, [rsp+70h+var_10]
0x18000ed68  add     rsp, 70h
0x18000ed6c  pop     r14
0x18000ed6e  pop     rbx
0x18000ed6f  pop     rbp
0x18000ed70  retn
0x18000ed72  mov     r14d, eax
0x18000ed75  mov     edx, 46h ; 'F'; void *
0x18000ed7a  mov     rcx, [rbp+18h]; this
0x18000ed7e  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x18000ed85  mov     r9d, r14d; char *
0x18000ed88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ed8d  xor     r12d, r12d
0x18000ed90  mov     rax, [r15]
0x18000ed93  mov     rcx, r15
0x18000ed96  mov     rax, [rax+10h]
0x18000ed9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9f  mov     rcx, [rbp+18h]; this
0x18000eda3  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x18000edaa  mov     r9d, r14d; char *
0x18000edad  mov     edx, 35h ; '5'; void *
0x18000edb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000edb7  jmp     loc_18000ED30
0x18000edbc  lea     eax, [rbx+2]
0x18000edbf  cmp     eax, ebx
0x18000edc1  jnb     loc_18000F090
0x18000edc7  mov     edx, 1Dh; void *
0x18000edcc  mov     rcx, [rbp+18h]; this
0x18000edd0  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18000edd7  mov     r9d, 80070216h; char *
0x18000eddd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ede2  mov     qword ptr [r15+68h], 0
0x18000edea  mov     eax, r14d
0x18000eded  xor     esi, esi
0x18000edef  test    eax, eax
0x18000edf1  js      loc_18000ED72
0x18000edf7  mov     rcx, [r15+70h]; pv
0x18000edfb  call    cs:__imp_CoTaskMemFree
0x18000ee02  nop     dword ptr [rax+rax+00h]
0x18000ee07  mov     rcx, r12
0x18000ee0a  mov     [r15+70h], rsi
0x18000ee0e  mov     rax, r13
0x18000ee11  cmp     word ptr [rax], 0
0x18000ee15  jz      short loc_18000EE21
0x18000ee17  add     rax, 2
0x18000ee1b  sub     rcx, 1
0x18000ee1f  jnz     short loc_18000EE11
0x18000ee21  test    rcx, rcx
0x18000ee24  mov     edx, 80070057h
0x18000ee29  cmovnz  edx, esi
0x18000ee2c  jz      loc_18000F238
0x18000ee32  sub     r12d, ecx
0x18000ee35  cmp     r12d, 3FFFFFFFh
0x18000ee3c  ja      loc_18000F115
0x18000ee42  lea     rbx, [r12+r12]
0x18000ee46  mov     eax, 0FFFFFFFFh
0x18000ee4b  cmp     rbx, rax
0x18000ee4e  ja      loc_18000F101
0x18000ee54  lea     eax, [rbx+2]
0x18000ee57  cmp     eax, ebx
0x18000ee59  jnb     loc_18000F0C9
0x18000ee5f  mov     edx, 1Dh; void *
0x18000ee64  mov     rcx, [rbp+18h]; this
0x18000ee68  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18000ee6f  mov     r9d, 80070216h; char *
0x18000ee75  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ee7a  mov     [r15+70h], rsi
0x18000ee7e  test    r14d, r14d
0x18000ee81  js      loc_18000F23B
0x18000ee87  xor     r12d, r12d
0x18000ee8a  mov     [rbp+var_48], 5
0x18000ee91  lea     rax, ?PackageType@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Type"
0x18000ee98  mov     [rbp+bstrString], r12
0x18000ee9c  mov     [rbp+var_40], rax
0x18000eea0  lea     r8, [rbp+arg_10]; unsigned int
0x18000eea4  lea     rax, asc_1801177B4; "']"
0x18000eeab  mov     [rbp+arg_10], r12
0x18000eeaf  mov     ebx, 1
0x18000eeb4  mov     [rbp+var_30], rax
0x18000eeb8  mov     edx, ebx; struct Appx::Packaging::XPathComponent *
0x18000eeba  mov     [rbp+var_38], 4
0x18000eec1  lea     rcx, [rbp+var_48]; this
0x18000eec5  mov     [rbp+var_28], r12d
0x18000eec9  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18000eece  mov     r14d, eax
0x18000eed1  test    eax, eax
0x18000eed3  js      loc_18000F011
0x18000eed9  mov     rdi, [rbp+arg_10]
0x18000eedd  lea     r8, [rbp+arg_10]
0x18000eee1  mov     rcx, [r15+28h]
0x18000eee5  mov     rdx, rdi
0x18000eee8  mov     [rbp+arg_10], r12
0x18000eeec  mov     [rbp+bstrString], r12
0x18000eef0  mov     rax, [rcx]
0x18000eef3  mov     rax, [rax+128h]
0x18000eefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeff  lea     rsi, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18000ef06  mov     r14d, eax
0x18000ef09  test    eax, eax
0x18000ef0b  js      loc_18000F06E
0x18000ef11  mov     rcx, [rbp+arg_10]
0x18000ef15  test    rcx, rcx
0x18000ef18  jz      loc_18000F066
0x18000ef1e  mov     rax, [rcx]
0x18000ef21  lea     rdx, [rbp+bstrString]
0x18000ef25  mov     rax, [rax+0D0h]
0x18000ef2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef31  mov     r14d, eax
0x18000ef34  test    eax, eax
0x18000ef36  js      short loc_18000EF6A
0x18000ef38  mov     rcx, [rbp+bstrString]; pbstr
0x18000ef3c  call    cs:__imp_SysStringLen
0x18000ef43  nop     dword ptr [rax+rax+00h]
0x18000ef48  test    eax, eax
0x18000ef4a  jnz     short loc_18000EF7E
0x18000ef4c  mov     rcx, [rbp+arg_10]
0x18000ef50  test    rcx, rcx
0x18000ef53  jz      short loc_18000EF65
0x18000ef55  mov     [rbp+arg_10], r12
0x18000ef59  mov     rax, [rcx]
0x18000ef5c  mov     rax, [rax+10h]
0x18000ef60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef65  mov     r14d, r12d
0x18000ef68  jmp     short loc_18000EF97
0x18000ef6a  mov     rcx, [rbp+18h]; this
0x18000ef6e  mov     r9d, eax; char *
0x18000ef71  mov     r8, rsi; unsigned int
0x18000ef74  mov     edx, 51h ; 'Q'; void *
0x18000ef79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ef7e  mov     rcx, [rbp+arg_10]
0x18000ef82  test    rcx, rcx
0x18000ef85  jz      short loc_18000EF97
0x18000ef87  mov     [rbp+arg_10], r12
0x18000ef8b  mov     rax, [rcx]
0x18000ef8e  mov     rax, [rax+10h]
0x18000ef92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef97  mov     rcx, rdi; bstrString
0x18000ef9a  call    cs:__imp_SysFreeString
0x18000efa1  nop     dword ptr [rax+rax+00h]
0x18000efa6  test    r14d, r14d
0x18000efa9  js      loc_18000F039
0x18000efaf  lea     r11, [r15+30h]
0x18000efb3  test    r11, r11
0x18000efb6  jz      loc_18000F16E
0x18000efbc  mov     r10, [rbp+bstrString]
0x18000efc0  test    r10, r10
0x18000efc3  jz      loc_18000ECEB
0x18000efc9  mov     r9d, r12d
0x18000efcc  lea     rdi, ?PackageTypeValues@Attribute@BundleManifest@Packaging@Appx@@3QBUPackageTypeTable@1234@B; Appx::Packaging::BundleManifest::Attribute::PackageTypeTable const near * const Appx::Packaging::BundleManifest::Attribute::PackageTypeValues
0x18000efd3  cmp     r9d, 2
0x18000efd7  jnb     loc_18000F228
  ... truncated ...
```
