# Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::GetPackageId(IAppxManifestPackageId * *)

- ea: `0x1800104a0`
- end: `0x180010f2c`
- name: `?GetPackageId@BundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@UEAAJPEAPEAUIAppxManifestPackageId@@@Z`
- size: `2700`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *__hidden this, struct IAppxManifestPackageId **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005db0`
- `0x180005eb8`
- `0x18000fab0`
- `0x1800104a0`
- `0x180010f40`
- `0x180011710`
- `0x1800133fc`
- `0x180071f50`
- `0x1800992d0`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010602`
- `OLEAUT32!__imp_SysFreeString` at `0x18001085f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001091e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010936`
- `OLEAUT32!__imp_SysFreeString` at `0x180010946`
- `OLEAUT32!__imp_SysFreeString` at `0x180010b4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d85`
- `OLEAUT32!__imp_SysFreeString` at `0x180010602`
- `OLEAUT32!__imp_SysFreeString` at `0x18001085f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800108d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001091e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010936`
- `OLEAUT32!__imp_SysFreeString` at `0x180010946`
- `OLEAUT32!__imp_SysFreeString` at `0x180010b4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010d85`
- `OLEAUT32!__imp_SysStringLen` at `0x180010582`
- `OLEAUT32!__imp_SysStringLen` at `0x18001061a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001080e`
- `OLEAUT32!__imp_SysStringLen` at `0x180010c68`
- `OLEAUT32!__imp_SysStringLen` at `0x180010582`
- `OLEAUT32!__imp_SysStringLen` at `0x18001061a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001080e`
- `OLEAUT32!__imp_SysStringLen` at `0x180010c68`

## string_xrefs

- `0x180010ec2`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180010edc`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180010ef6`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001086f`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x1800108b6`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x180010d6d`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x180010ddf`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`
- `0x180010f13`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestpackageinfo.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::GetPackageId(
        const unsigned __int16 **this,
        struct IAppxManifestPackageId **a2,
        __int64 a3,
        struct Common::AutoBStr *a4)
{
  Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *v4; // r15
  int v5; // eax
  int v6; // ebx
  OLECHAR *v7; // rdi
  __int64 v8; // rcx
  BSTR v9; // rdx
  int v10; // eax
  unsigned int v11; // esi
  int v12; // eax
  __int64 v13; // rdx
  BSTR v14; // rcx
  BSTR v15; // rcx
  UINT v16; // eax
  struct Common::AutoBStr *v17; // r9
  BSTR v18; // rcx
  unsigned int v19; // edi
  BSTR v20; // rdx
  OLECHAR *v21; // r8
  int v22; // ebx
  unsigned int v23; // r11d
  unsigned __int16 v24; // r10
  unsigned int v25; // r11d
  int v26; // eax
  OLECHAR *v27; // rdi
  __int64 v28; // rcx
  BSTR v29; // rdx
  int v30; // eax
  int v31; // eax
  BSTR v32; // rcx
  __int64 v33; // rdx
  BSTR v34; // rcx
  int v35; // ebx
  __int64 v36; // r12
  const unsigned __int16 *v37; // r14
  const unsigned __int16 *v38; // rsi
  const unsigned __int16 *v39; // r13
  _OWORD *v40; // rax
  __int64 v41; // rdi
  Common::StringBuffer *v42; // rcx
  __int64 v43; // r9
  const unsigned __int16 *v44; // rax
  unsigned int v45; // r8d
  __int64 v46; // rcx
  const unsigned __int16 *v47; // rax
  __int64 v48; // rcx
  const unsigned __int16 *v49; // rax
  BSTR v51; // rcx
  struct Common::AutoBStr *i; // r9
  char *v53; // rax
  char *v54; // r8
  int v55; // ecx
  int v56; // edx
  int v57; // eax
  OLECHAR *v58; // rsi
  __int64 v59; // rcx
  int v60; // eax
  int v61; // eax
  BSTR v62; // rcx
  __int64 v63; // rdx
  int j; // eax
  const struct Appx::Packaging::Manifest::Attribute::PackageArchitectureTable near *v65; // rcx
  int v66; // edx
  int v67; // r8d
  BSTR v68; // [rsp+20h] [rbp-50h] BYREF
  int v69; // [rsp+28h] [rbp-48h] BYREF
  const unsigned __int16 *v70; // [rsp+30h] [rbp-40h]
  int v71; // [rsp+38h] [rbp-38h]
  const wchar_t *v72; // [rsp+40h] [rbp-30h]
  int v73; // [rsp+48h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  BSTR bstrString; // [rsp+A0h] [rbp+30h] BYREF
  BSTR pbstr; // [rsp+A8h] [rbp+38h] BYREF

  v4 = (Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *)this;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)0x80004003LL,
      (int)v68);
    return 2147500035LL;
  }
  if ( this[9] )
    goto LABEL_62;
  pbstr = 0;
  v70 = L"Version";
  v72 = L"']";
  bstrString = 0;
  v69 = 5;
  v71 = 7;
  v73 = 0;
  v5 = Appx::Packaging::BuildXPath(
         (Appx::Packaging *)&v69,
         (const struct Appx::Packaging::XPathComponent *)1,
         &bstrString,
         a4);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v5,
      (int)v68);
    SysFreeString(bstrString);
    goto LABEL_52;
  }
  v7 = bstrString;
  v8 = *((_QWORD *)v4 + 5);
  v9 = bstrString;
  bstrString = 0;
  pbstr = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR *))(*(_QWORD *)v8 + 296LL))(v8, v9, &bstrString);
  v6 = v10;
  v11 = -2147418113;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v10,
      (int)v68);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
    goto LABEL_16;
  }
  if ( !bstrString )
  {
    v13 = 79;
    goto LABEL_13;
  }
  v12 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 208LL))(bstrString, &pbstr);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)(unsigned int)v12,
      (int)v68);
  }
  else if ( !SysStringLen(pbstr) )
  {
    v13 = 84;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
      (const char *)0x8000FFFFLL,
      (int)v68);
    v15 = bstrString;
    if ( bstrString )
    {
      bstrString = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v6 = -2147418113;
    goto LABEL_16;
  }
  v14 = bstrString;
  if ( bstrString )
  {
    bstrString = 0;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
  }
LABEL_16:
  SysFreeString(v7);
  if ( v6 < 0 )
  {
LABEL_52:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
      (const char *)(unsigned int)v6,
      (int)v68);
LABEL_56:
    SysFreeString(pbstr);
    return (unsigned int)v6;
  }
  v16 = SysStringLen(pbstr);
  v18 = pbstr;
  if ( !pbstr )
  {
    *((_QWORD *)v4 + 9) = 0;
LABEL_43:
    v68 = 0;
    v70 = L"Architecture";
    bstrString = 0;
    v69 = 5;
    v71 = 12;
    v72 = L"']";
    v73 = 0;
    v26 = Appx::Packaging::BuildXPath(
            (Appx::Packaging *)&v69,
            (const struct Appx::Packaging::XPathComponent *)1,
            &bstrString,
            v17);
    v6 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v26,
        (int)v68);
      SysFreeString(bstrString);
      goto LABEL_112;
    }
    v27 = bstrString;
    v28 = *((_QWORD *)v4 + 5);
    v29 = bstrString;
    bstrString = 0;
    v68 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR *))(*(_QWORD *)v28 + 296LL))(v28, v29, &bstrString);
    v6 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v30,
        (int)v68);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
      goto LABEL_93;
    }
    if ( !bstrString )
    {
      v6 = 0;
      goto LABEL_93;
    }
    v31 = (*(__int64 (__fastcall **)(BSTR, BSTR *))(*(_QWORD *)bstrString + 208LL))(bstrString, &v68);
    v6 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
        (const char *)(unsigned int)v31,
        (int)v68);
    }
    else if ( !SysStringLen(v68) )
    {
      v32 = bstrString;
      if ( bstrString )
      {
        bstrString = 0;
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v6 = 0;
      goto LABEL_93;
    }
    v51 = bstrString;
    if ( bstrString )
    {
      bstrString = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v51 + 16LL))(v51);
    }
LABEL_93:
    SysFreeString(v27);
    if ( v6 >= 0 )
    {
      if ( v68 )
      {
        for ( i = 0; (unsigned int)i < 5; i = (struct Common::AutoBStr *)(unsigned int)((_DWORD)i + 1) )
        {
          v53 = (char *)*((_QWORD *)&Appx::Packaging::Manifest::Attribute::PackageArchitectureValues_V1
                        + 2 * (unsigned int)i);
          v54 = (char *)((char *)v68 - v53);
          do
          {
            v55 = *(unsigned __int16 *)&v54[(_QWORD)v53];
            v56 = *(unsigned __int16 *)v53 - v55;
            if ( v56 )
              break;
            v53 += 2;
          }
          while ( v55 );
          if ( !v56 )
          {
            *((_DWORD *)v4 + 20) = dword_18010A628[4 * (unsigned int)i];
            goto LABEL_103;
          }
        }
        for ( j = 0; !j; j = 1 )
        {
          i = 0;
          v65 = Appx::Packaging::Manifest::Attribute::PackageArchitectureValues_V2;
          do
          {
            v66 = *(unsigned __int16 *)((char *)v65
                                      + (char *)v68
                                      - (char *)Appx::Packaging::Manifest::Attribute::PackageArchitectureValues_V2);
            v67 = *(unsigned __int16 *)v65 - v66;
            if ( v67 )
              break;
            v65 = (const struct Appx::Packaging::Manifest::Attribute::PackageArchitectureTable near *)((char *)v65 + 2);
          }
          while ( v66 );
          if ( !v67 )
          {
            *((_DWORD *)v4 + 20) = 14;
            goto LABEL_103;
          }
        }
        *((_DWORD *)v4 + 20) = 0xFFFF;
      }
      else
      {
        *((_DWORD *)v4 + 20) = 11;
      }
LABEL_103:
      bstrString = 0;
      v70 = L"ResourceId";
      v69 = 5;
      v71 = 10;
      v72 = L"']";
      v73 = 0;
      v57 = Appx::Packaging::BuildXPath(
              (Appx::Packaging *)&v69,
              (const struct Appx::Packaging::XPathComponent *)1,
              &bstrString,
              i);
      v6 = v57;
      if ( v57 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x104,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v57,
          (int)v68);
        SysFreeString(bstrString);
LABEL_54:
        v33 = 105;
LABEL_55:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
          (const char *)(unsigned int)v6,
          (int)v68);
        SysFreeString(v68);
        goto LABEL_56;
      }
      v58 = bstrString;
      *((_QWORD *)v4 + 11) = 0;
      v59 = *((_QWORD *)v4 + 5);
      bstrString = 0;
      v60 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR *))(*(_QWORD *)v59 + 296LL))(v59, v58, &bstrString);
      v6 = v60;
      if ( v60 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v60,
          (int)v68);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
        goto LABEL_60;
      }
      if ( !bstrString )
      {
        v6 = 0;
        goto LABEL_60;
      }
      v61 = (*(__int64 (__fastcall **)(BSTR, __int64))(*(_QWORD *)bstrString + 208LL))(bstrString, (__int64)v4 + 88);
      v6 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\valuehelper.cpp",
          (const char *)(unsigned int)v61,
          (int)v68);
      }
      else if ( !SysStringLen(*((BSTR *)v4 + 11)) )
      {
        v62 = bstrString;
        if ( bstrString )
        {
          bstrString = 0;
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v62 + 16LL))(v62);
        }
        v6 = 0;
        goto LABEL_60;
      }
      v34 = bstrString;
      if ( bstrString )
      {
        bstrString = 0;
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v34 + 16LL))(v34);
      }
LABEL_60:
      SysFreeString(v58);
      if ( v6 >= 0 )
      {
        SysFreeString(v68);
        SysFreeString(pbstr);
        this = (const unsigned __int16 **)v4;
LABEL_62:
        v35 = *((_DWORD *)v4 + 20);
        v36 = *((_QWORD *)v4 + 9);
        v37 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v38 = (const unsigned __int16 *)*((_QWORD *)v4 + 13);
        v39 = this[11];
        v40 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v40 )
        {
          *v40 = 0;
          v40[1] = 0;
          v40[2] = 0;
          v40[3] = 0;
          v40[4] = 0;
          v40[5] = 0;
          v40[6] = 0;
          *((_QWORD *)v40 + 14) = 0;
          v41 = Appx::Packaging::Manifest::BundlePayloadPackageId::BundlePayloadPackageId((Appx::Packaging::Manifest::BundlePayloadPackageId *)v40);
        }
        else
        {
          v41 = 0;
        }
        v42 = (Common::StringBuffer *)(v41 + 32);
        if ( v38 )
        {
          v43 = 1073741822;
          v44 = v38;
          do
          {
            if ( !*v44 )
              break;
            ++v44;
            --v43;
          }
          while ( v43 );
          if ( v43 )
            Common::StringBuffer::SetValue(v42, v38, 1073741822 - v43);
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)0x80070057LL,
              (int)v68);
          v45 = -2147024809;
        }
        else
        {
          Common::StringBuffer::Clear(v42);
        }
        if ( v37 )
        {
          v46 = 1073741822;
          v47 = v37;
          do
          {
            if ( !*v47 )
              break;
            ++v47;
            --v46;
          }
          while ( v46 );
          if ( v46 )
            Common::StringBuffer::SetValue((Common::StringBuffer *)(v41 + 56), v37, 1073741822 - v46);
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)v45,
              (int)v68);
        }
        else
        {
          Common::StringBuffer::Clear((Common::StringBuffer *)(v41 + 56));
        }
        *(_QWORD *)(v41 + 80) = v36;
        *(_DWORD *)(v41 + 88) = v35;
        if ( v39 )
        {
          v48 = 1073741822;
          v49 = v39;
          do
          {
            if ( !*v49 )
              break;
            ++v49;
            --v48;
          }
          while ( v48 );
          if ( v48 )
            Common::StringBuffer::SetValue((Common::StringBuffer *)(v41 + 96), v39, 1073741822 - v48);
          else
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)0x80070057LL,
              (int)v68);
        }
        else
        {
          Common::StringBuffer::Clear((Common::StringBuffer *)(v41 + 96));
        }
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IAppxManifestPackageId **))v41)(
               v41,
               &GUID_283ce2d7_7153_4a91_9649_7a0f7240945f,
               a2);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        if ( v6 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
            (const char *)(unsigned int)v6,
            (int)v68);
        return (unsigned int)v6;
      }
      goto LABEL_54;
    }
LABEL_112:
    v33 = 102;
    goto LABEL_55;
  }
  if ( v16 )
  {
    v19 = 0;
    bstrString = 0;
    v20 = pbstr;
    v21 = &pbstr[v16];
    while ( 1 )
    {
      if ( v20 == v21 )
        goto LABEL_24;
      if ( v20 > v21 )
      {
        if ( v19 == 4 && v20 == v21 + 1 )
        {
          *((_QWORD *)v4 + 9) = bstrString;
          goto LABEL_43;
        }
        v63 = 94;
        goto LABEL_119;
      }
      if ( *v20 == 46 )
      {
LABEL_24:
        if ( ++v19 > 4 )
        {
          v63 = 83;
          goto LABEL_119;
        }
        if ( !v18 )
        {
          v11 = -2147467261;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\corevaluehelper.cpp",
            (const char *)0x80004003LL,
            (int)v68);
          goto LABEL_42;
        }
        v17 = (struct Common::AutoBStr *)&v18[(unsigned int)(v20 - v18)];
        if ( v18 == (BSTR)v17 )
          goto LABEL_41;
        if ( *v18 == 45 )
        {
          ++v18;
          v22 = 1;
          if ( v18 == (BSTR)v17 )
            goto LABEL_41;
        }
        else
        {
          v22 = 0;
        }
        v23 = 0;
        while ( v18 < (BSTR)v17 )
        {
          v24 = *v18 - 48;
          if ( v24 > 9u )
            goto LABEL_41;
          if ( v23 > 0x19999999 )
            goto LABEL_41;
          v25 = 10 * v23;
          if ( v25 > ~v24 )
            goto LABEL_41;
          v23 = v24 + v25;
          ++v18;
        }
        if ( v22 && v23 )
        {
LABEL_41:
          v11 = -2147024885;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x21,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\corevaluehelper.cpp",
            (const char *)0x8007000BLL,
            (int)v68);
LABEL_42:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x55,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\corevaluehelper.cpp",
            (const char *)v11,
            (int)v68);
          goto LABEL_120;
        }
        if ( v23 > 0xFFFF )
        {
          v11 = -2147024362;
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\corevaluehelper.cpp",
            (const char *)0x80070216LL,
            (int)v68);
          goto LABEL_42;
        }
        v18 = v20 + 1;
        *((_WORD *)&pbstr - v19) = v23;
      }
      ++v20;
    }
  }
  v63 = 58;
LABEL_119:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v63,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\corevaluehelper.cpp",
    (const char *)0x8000FFFFLL,
    (int)v68);
LABEL_120:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestpackageinfo.cpp",
    (const char *)v11,
    (int)v68);
  SysFreeString(pbstr);
  return v11;
}

```

## disassembly

```asm
0x1800104a0  mov     rax, rsp
0x1800104a3  mov     [rax+10h], rdx
0x1800104a7  push    rbp
0x1800104a8  push    rsi
0x1800104a9  push    r15
0x1800104ab  mov     rbp, rsp
0x1800104ae  sub     rsp, 70h
0x1800104b2  mov     r15, rcx
0x1800104b5  test    rdx, rdx
0x1800104b8  jz      loc_180010DDB
0x1800104be  mov     [rax+8], rbx
0x1800104c2  mov     [rax-20h], rdi
0x1800104c6  mov     [rax-28h], r12
0x1800104ca  mov     [rax-38h], r14
0x1800104ce  xor     r14d, r14d
0x1800104d1  cmp     [rcx+48h], r14
0x1800104d5  jnz     loc_180010955
0x1800104db  lea     rax, ?Version@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Version"
0x1800104e2  mov     [rbp+pbstr], r14
0x1800104e6  lea     r12, asc_1801177B4; "']"
0x1800104ed  mov     [rbp+var_40], rax
0x1800104f1  lea     r8, [rbp+bstrString]; unsigned int
0x1800104f5  mov     [rbp+var_30], r12
0x1800104f9  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x1800104fe  mov     [rbp+bstrString], r14
0x180010502  lea     rcx, [rbp+var_48]; this
0x180010506  mov     [rbp+var_48], 5
0x18001050d  mov     [rbp+var_38], 7
0x180010514  mov     [rbp+var_28], r14d
0x180010518  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001051d  mov     ebx, eax
0x18001051f  test    eax, eax
0x180010521  js      loc_180010843
0x180010527  mov     rdi, [rbp+bstrString]
0x18001052b  lea     r8, [rbp+bstrString]
0x18001052f  mov     rcx, [r15+28h]
0x180010533  mov     rdx, rdi
0x180010536  mov     [rbp+bstrString], r14
0x18001053a  mov     [rbp+pbstr], r14
0x18001053e  mov     rax, [rcx]
0x180010541  mov     rax, [rax+128h]
0x180010548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001054d  mov     ebx, eax
0x18001054f  mov     esi, 8000FFFFh
0x180010554  test    eax, eax
0x180010556  js      loc_180010CCF
0x18001055c  mov     rcx, [rbp+bstrString]
0x180010560  test    rcx, rcx
0x180010563  jz      short loc_1800105CC
0x180010565  mov     rax, [rcx]
0x180010568  lea     rdx, [rbp+pbstr]
0x18001056c  mov     rax, [rax+0D0h]
0x180010573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010578  mov     ebx, eax
0x18001057a  test    eax, eax
0x18001057c  js      short loc_180010599
0x18001057e  mov     rcx, [rbp+pbstr]; pbstr
0x180010582  call    cs:__imp_SysStringLen
0x180010589  nop     dword ptr [rax+rax+00h]
0x18001058e  test    eax, eax
0x180010590  jnz     short loc_1800105B1
0x180010592  mov     edx, 54h ; 'T'
0x180010597  jmp     short loc_1800105D1
0x180010599  mov     rcx, [rbp+18h]; this
0x18001059d  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800105a4  mov     r9d, eax; char *
0x1800105a7  mov     edx, 51h ; 'Q'; void *
0x1800105ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800105b1  mov     rcx, [rbp+bstrString]
0x1800105b5  test    rcx, rcx
0x1800105b8  jz      short loc_1800105FF
0x1800105ba  mov     [rbp+bstrString], r14
0x1800105be  mov     rax, [rcx]
0x1800105c1  mov     rax, [rax+10h]
0x1800105c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ca  jmp     short loc_1800105FF
0x1800105cc  mov     edx, 4Fh ; 'O'; void *
0x1800105d1  mov     rcx, [rbp+18h]; this
0x1800105d5  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800105dc  mov     r9d, esi; char *
0x1800105df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105e4  mov     rcx, [rbp+bstrString]
0x1800105e8  test    rcx, rcx
0x1800105eb  jz      short loc_1800105FD
0x1800105ed  mov     [rbp+bstrString], r14
0x1800105f1  mov     rax, [rcx]
0x1800105f4  mov     rax, [rax+10h]
0x1800105f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fd  mov     ebx, esi
0x1800105ff  mov     rcx, rdi; bstrString
0x180010602  call    cs:__imp_SysFreeString
0x180010609  nop     dword ptr [rax+rax+00h]
0x18001060e  test    ebx, ebx
0x180010610  js      loc_18001086B
0x180010616  mov     rcx, [rbp+pbstr]; pbstr
0x18001061a  call    cs:__imp_SysStringLen
0x180010621  nop     dword ptr [rax+rax+00h]
0x180010626  mov     rcx, [rbp+pbstr]
0x18001062a  test    rcx, rcx
0x18001062d  jz      loc_180010DD2
0x180010633  test    eax, eax
0x180010635  jz      loc_180010DCB
0x18001063b  mov     eax, eax
0x18001063d  mov     edi, r14d
0x180010640  mov     [rbp+bstrString], r14
0x180010644  mov     rdx, rcx
0x180010647  lea     r8, [rcx+rax*2]
0x18001064b  nop     dword ptr [rax+rax+00h]
0x180010650  cmp     rdx, r8
0x180010653  jz      short loc_180010667
0x180010655  ja      loc_18001070E
0x18001065b  cmp     word ptr [rdx], 2Eh ; '.'
0x18001065f  jz      short loc_180010667
0x180010661  add     rdx, 2
0x180010665  jmp     short loc_180010650
0x180010667  inc     edi
0x180010669  cmp     edi, 4
0x18001066c  ja      loc_180010E51
0x180010672  test    rcx, rcx
0x180010675  jz      loc_180010E2F
0x18001067b  mov     rax, rdx
0x18001067e  sub     rax, rcx
0x180010681  sar     rax, 1
0x180010684  mov     eax, eax
0x180010686  lea     r9, [rcx+rax*2]
0x18001068a  cmp     rcx, r9
0x18001068d  jz      loc_18001072E
0x180010693  cmp     word ptr [rcx], 2Dh ; '-'
0x180010697  jz      loc_180010B04
0x18001069d  mov     ebx, r14d
0x1800106a0  mov     r11d, r14d
0x1800106a3  cmp     rcx, r9
0x1800106a6  jnb     short loc_1800106E0
0x1800106a8  movzx   r10d, word ptr [rcx]
0x1800106ac  sub     r10w, 30h ; '0'
0x1800106b1  cmp     r10w, 9
0x1800106b6  ja      short loc_18001072E
0x1800106b8  cmp     r11d, 19999999h
0x1800106bf  ja      short loc_18001072E
0x1800106c1  lea     eax, [r11+r11*4]
0x1800106c5  movzx   r10d, r10w
0x1800106c9  lea     r11d, [rax+rax]
0x1800106cd  mov     eax, r10d
0x1800106d0  not     eax
0x1800106d2  cmp     r11d, eax
0x1800106d5  ja      short loc_18001072E
0x1800106d7  add     r11d, r10d
0x1800106da  add     rcx, 2
0x1800106de  jmp     short loc_1800106A3
0x1800106e0  test    ebx, ebx
0x1800106e2  jnz     loc_180010DFF
0x1800106e8  cmp     r11d, 0FFFFh
0x1800106ef  ja      loc_180010E0D
0x1800106f5  mov     ecx, edi
0x1800106f7  lea     rax, [rbp+pbstr]
0x1800106fb  add     rcx, rcx
0x1800106fe  sub     rax, rcx
0x180010701  lea     rcx, [rdx+2]
0x180010705  mov     [rax], r11w
0x180010709  jmp     loc_180010661
0x18001070e  cmp     edi, 4
0x180010711  jnz     loc_180010D51
0x180010717  lea     rax, [r8+2]
0x18001071b  cmp     rdx, rax
0x18001071e  jnz     loc_180010D51
0x180010724  mov     rax, [rbp+bstrString]
0x180010728  mov     [r15+48h], rax
0x18001072c  jmp     short loc_18001076B
0x18001072e  mov     rcx, [rbp+18h]; this
0x180010732  lea     r8, aOnecorePrintsc_157; "onecore\\printscan\\appxpackaging\\lib"...
0x180010739  mov     esi, 8007000Bh
0x18001073e  mov     edx, 21h ; '!'; void *
0x180010743  mov     r9d, esi; char *
0x180010746  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001074b  mov     rcx, [rbp+18h]; this
0x18001074f  lea     r8, aOnecorePrintsc_157; "onecore\\printscan\\appxpackaging\\lib"...
0x180010756  mov     r9d, esi; char *
0x180010759  mov     edx, 55h ; 'U'; void *
0x18001075e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010763  test    esi, esi
0x180010765  js      loc_180010D69
0x18001076b  lea     rax, ?Architecture@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "Architecture"
0x180010772  mov     [rbp+var_50], r14
0x180010776  lea     r8, [rbp+bstrString]; unsigned int
0x18001077a  mov     [rbp+var_40], rax
0x18001077e  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180010783  mov     [rbp+bstrString], r14
0x180010787  lea     rcx, [rbp+var_48]; this
0x18001078b  mov     [rbp+var_48], 5
0x180010792  mov     [rbp+var_38], 0Ch
0x180010799  mov     [rbp+var_30], r12
0x18001079d  mov     [rbp+var_28], r14d
0x1800107a1  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x1800107a6  mov     ebx, eax
0x1800107a8  test    eax, eax
0x1800107aa  js      loc_180010C9D
0x1800107b0  mov     rdi, [rbp+bstrString]
0x1800107b4  lea     r8, [rbp+bstrString]
0x1800107b8  mov     rcx, [r15+28h]
0x1800107bc  mov     rdx, rdi
0x1800107bf  mov     [rbp+bstrString], r14
0x1800107c3  mov     [rbp+var_50], r14
0x1800107c7  mov     rax, [rcx]
0x1800107ca  mov     rax, [rax+128h]
0x1800107d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107d6  mov     ebx, eax
0x1800107d8  test    eax, eax
0x1800107da  js      loc_180010D05
0x1800107e0  mov     rcx, [rbp+bstrString]
0x1800107e4  test    rcx, rcx
0x1800107e7  jz      loc_180010CF5
0x1800107ed  mov     rax, [rcx]
0x1800107f0  lea     rdx, [rbp+var_50]
0x1800107f4  mov     rax, [rax+0D0h]
0x1800107fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010800  mov     ebx, eax
0x180010802  test    eax, eax
0x180010804  js      loc_180010B1B
0x18001080a  mov     rcx, [rbp+var_50]; pbstr
0x18001080e  call    cs:__imp_SysStringLen
0x180010815  nop     dword ptr [rax+rax+00h]
0x18001081a  test    eax, eax
0x18001081c  jnz     loc_180010B33
0x180010822  mov     rcx, [rbp+bstrString]
0x180010826  test    rcx, rcx
0x180010829  jz      short loc_18001083B
0x18001082b  mov     [rbp+bstrString], r14
0x18001082f  mov     rax, [rcx]
0x180010832  mov     rax, [rax+10h]
0x180010836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083b  mov     ebx, r14d
0x18001083e  jmp     loc_180010B4C
0x180010843  mov     rcx, [rbp+18h]; this
0x180010847  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x18001084e  mov     r9d, eax; char *
0x180010851  mov     edx, 104h; void *
0x180010856  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001085b  mov     rcx, [rbp+bstrString]; bstrString
0x18001085f  call    cs:__imp_SysFreeString
0x180010866  nop     dword ptr [rax+rax+00h]
0x18001086b  mov     rcx, [rbp+18h]; this
0x18001086f  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x180010876  mov     r9d, ebx; char *
0x180010879  mov     edx, 62h ; 'b'; void *
0x18001087e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010883  jmp     short loc_1800108D5
0x180010885  mov     rcx, [rbp+18h]; this
0x180010889  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x180010890  mov     r9d, eax; char *
0x180010893  mov     edx, 104h; void *
0x180010898  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001089d  mov     rcx, [rbp+bstrString]; bstrString
0x1800108a1  call    cs:__imp_SysFreeString
0x1800108a8  nop     dword ptr [rax+rax+00h]
0x1800108ad  mov     edx, 69h ; 'i'; void *
0x1800108b2  mov     rcx, [rbp+18h]; this
0x1800108b6  lea     r8, aOnecorePrintsc_96; "onecore\\printscan\\appxpackaging\\mani"...
0x1800108bd  mov     r9d, ebx; char *
0x1800108c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800108c5  mov     rcx, [rbp+var_50]; bstrString
0x1800108c9  call    cs:__imp_SysFreeString
0x1800108d0  nop     dword ptr [rax+rax+00h]
0x1800108d5  mov     rcx, [rbp+pbstr]; bstrString
0x1800108d9  call    cs:__imp_SysFreeString
0x1800108e0  nop     dword ptr [rax+rax+00h]
0x1800108e5  jmp     loc_180010AE1
0x1800108ea  mov     rcx, [rbp+18h]; this
0x1800108ee  lea     r8, aOnecorePrintsc_100; "onecore\\printscan\\appxpackaging\\lib"...
0x1800108f5  mov     r9d, eax; char *
0x1800108f8  mov     edx, 51h ; 'Q'; void *
0x1800108fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010902  mov     rcx, [rbp+bstrString]
0x180010906  test    rcx, rcx
0x180010909  jz      short loc_18001091B
0x18001090b  mov     [rbp+bstrString], r14
0x18001090f  mov     rax, [rcx]
0x180010912  mov     rax, [rax+10h]
0x180010916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001091b  mov     rcx, rsi; bstrString
0x18001091e  call    cs:__imp_SysFreeString
0x180010925  nop     dword ptr [rax+rax+00h]
0x18001092a  test    ebx, ebx
0x18001092c  js      loc_1800108AD
0x180010932  mov     rcx, [rbp+var_50]; bstrString
0x180010936  call    cs:__imp_SysFreeString
0x18001093d  nop     dword ptr [rax+rax+00h]
0x180010942  mov     rcx, [rbp+pbstr]; bstrString
0x180010946  call    cs:__imp_SysFreeString
0x18001094d  nop     dword ptr [rax+rax+00h]
0x180010952  mov     rcx, r15
0x180010955  mov     ebx, [r15+50h]
0x180010959  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010960  mov     r12, [r15+48h]
0x180010964  mov     eax, 58h ; 'X'
0x180010969  mov     r14, [r15+70h]
0x18001096d  mov     rsi, [r15+68h]
0x180010971  mov     [rsp+70h+var_18], r13
0x180010976  mov     r13, [rax+rcx]
0x18001097a  mov     ecx, 78h ; 'x'; unsigned __int64
0x18001097f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
  ... truncated ...
```
