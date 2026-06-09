# Appx::Packaging::Manifest::AppxManifestReaderWithoutValidationImpl::RuntimeClassInitialize(IStream *)

- ea: `0x180058b00`
- end: `0x1800590df`
- name: `?RuntimeClassInitialize@AppxManifestReaderWithoutValidationImpl@Manifest@Packaging@Appx@@QEAAJPEAUIStream@@@Z`
- size: `1503`
- prototype: `int(Appx::Packaging::Manifest::AppxManifestReaderWithoutValidationImpl *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800589dc`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x1800133fc`
- `0x1800163fc`
- `0x180017a40`
- `0x180017b04`
- `0x180023d10`
- `0x180026b54`
- `0x180028dd0`
- `0x18002e7e0`
- `0x180030958`
- `0x180058b00`
- `0x18005bc7c`
- `0x18006bee8`
- `0x180071f50`
- `0x18008e548`
- `0x1800992a0`
- `0x1800992d0`
- `0x1800e1804`
- `0x1800e51ac`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180058cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180058f93`
- `OLEAUT32!__imp_SysFreeString` at `0x18005901e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800590a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180058cb3`
- `OLEAUT32!__imp_SysFreeString` at `0x180058f93`
- `OLEAUT32!__imp_SysFreeString` at `0x18005901e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800590a4`

## string_xrefs

- `0x180058b6c`: `http://schemas.microsoft.com/appx/manifest/foundation/windows10`
- `0x180058d2c`: `http://schemas.microsoft.com/appx/manifest/foundation/windows10`
- `0x180058b56`: `http://schemas.microsoft.com/appx/2010/manifest`
- `0x180058d16`: `http://schemas.microsoft.com/appx/2010/manifest`
- `0x180058bbd`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058c11`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058ca2`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058d93`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058e03`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058eda`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058f29`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058f83`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x18005900e`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180059088`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreaderwithoutvalidation.cpp`
- `0x180058d58`: `http://schemas.microsoft.com/appx/manifest/trustedlaunch/windows10`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderWithoutValidationImpl::RuntimeClassInitialize(
        Appx::Packaging::Manifest::AppxManifestReaderWithoutValidationImpl *this,
        struct IStream *a2)
{
  int v4; // eax
  int RequiredUniqueNodeValue; // edi
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rbx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  int *v12; // r9
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v20; // rdx
  struct IXMLDOMNode *v21; // rdi
  Appx::Packaging::Manifest::PackageIdHelper *v22; // rax
  Appx::Packaging::Manifest::PackageIdHelper *v23; // rsi
  int PackageNameInternal; // eax
  unsigned int v25; // edx
  int v26; // eax
  __int64 v27; // r8
  int *v28; // r9
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // r8
  int *v33; // r9
  unsigned __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // eax
  int v37; // eax
  int v38; // [rsp+20h] [rbp-99h]
  BSTR bstrString; // [rsp+30h] [rbp-89h] BYREF
  struct IXMLDOMNode *v40; // [rsp+38h] [rbp-81h] BYREF
  BSTR v41; // [rsp+40h] [rbp-79h] BYREF
  struct IXMLDOMDocument *v42; // [rsp+48h] [rbp-71h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-69h] BYREF
  int v44[2]; // [rsp+58h] [rbp-61h] BYREF
  BSTR v45; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v46[7]; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v47[8]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v42 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl'::`2'::impl) )
  {
    v47[0] = L"m";
    v47[1] = L"http://schemas.microsoft.com/appx/2010/manifest";
    v47[2] = L"win10foundation";
    v47[3] = L"http://schemas.microsoft.com/appx/manifest/foundation/windows10";
    v47[4] = L"uap6";
    v47[5] = &Appx::Packaging::Manifest::RS4UapNamespace;
    v47[6] = L"trustedlaunch";
    v47[7] = L"http://schemas.microsoft.com/appx/manifest/trustedlaunch/windows10";
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
    v17 = Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(
            a2,
            (struct XmlNamespaceAlias *)v47,
            4u,
            0,
            &v42,
            0);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)v17,
        v38);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      return v18;
    }
    bstrString = (BSTR)v42;
    v45 = 0;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&bstrString);
    RequiredUniqueNodeValue = Appx::Packaging::GetRequiredUniqueNodeValue(
                                &bstrString,
                                L"m:Package/m:Identity/@Publisher | win10foundation:Package/win10foundation:Identity/@Publisher",
                                &v45);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
    v7 = v45;
    if ( RequiredUniqueNodeValue < 0 )
    {
      v9 = (unsigned int)RequiredUniqueNodeValue;
      v10 = 68;
      goto LABEL_20;
    }
    v40 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
    bstrString = (BSTR)v42;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&bstrString);
    RequiredUniqueNodeValue = Appx::Packaging::TryGetNode(
                                &bstrString,
                                L"m:Package/m:Identity | win10foundation:Package/win10foundation:Identity",
                                &v40);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
    if ( RequiredUniqueNodeValue < 0 )
    {
      v20 = 72;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)RequiredUniqueNodeValue,
        v38);
      goto LABEL_48;
    }
    v21 = v40;
    if ( !v40 )
    {
      RequiredUniqueNodeValue = -2146958844;
      v20 = 73;
      goto LABEL_47;
    }
    v22 = (Appx::Packaging::Manifest::PackageIdHelper *)operator new(
                                                          0x20u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    if ( !v22
      || (v23 = (Appx::Packaging::Manifest::PackageIdHelper *)Appx::Packaging::Manifest::PackageIdHelper::PackageIdHelper(
                                                                v22,
                                                                v21)) == 0 )
    {
      RequiredUniqueNodeValue = -2147024882;
      v20 = 76;
      goto LABEL_47;
    }
    bstrString = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &bstrString,
      0);
    PackageNameInternal = Appx::Packaging::Manifest::PackageIdHelper::GetPackageNameInternal(v23, 0, &bstrString);
    RequiredUniqueNodeValue = PackageNameInternal;
    if ( PackageNameInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)PackageNameInternal,
        v38);
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
      Appx::Packaging::Manifest::PackageIdHelper::`scalar deleting destructor'(v23, v25);
LABEL_48:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      goto LABEL_49;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 16);
    v26 = Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(
            v7,
            bstrString,
            (struct IAppxManifestPackageId **)this + 2);
    RequiredUniqueNodeValue = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)v26,
        v38);
      goto LABEL_29;
    }
    v45 = (BSTR)v42;
    pbstr = 0;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v45);
    RequiredUniqueNodeValue = Appx::Packaging::GetNodeValue(
                                &v45,
                                L"win10foundation:Package/win10foundation:Properties/uap6:AllowExecution",
                                v27,
                                &pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    if ( RequiredUniqueNodeValue < 0 )
    {
      v29 = (unsigned int)RequiredUniqueNodeValue;
      v30 = 85;
LABEL_34:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)v29,
        v38);
LABEL_35:
      SysFreeString(pbstr);
      goto LABEL_29;
    }
    LODWORD(v45) = 0;
    v31 = Appx::Packaging::ConvertToBool((Appx::Packaging *)pbstr, (unsigned __int16 *)1, (int)&v45, v28);
    RequiredUniqueNodeValue = v31;
    if ( v31 < 0 )
    {
      v29 = (unsigned int)v31;
      v30 = 87;
      goto LABEL_34;
    }
    *(_QWORD *)v44 = v42;
    v41 = 0;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(v44);
    RequiredUniqueNodeValue = Appx::Packaging::GetNodeValue(
                                v44,
                                L"win10foundation:Package/win10foundation:Properties/trustedlaunch:TrustedLaunch",
                                v32,
                                &v41);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v44);
    if ( RequiredUniqueNodeValue >= 0 )
    {
      v44[0] = 0;
      v36 = Appx::Packaging::ConvertToBool((Appx::Packaging *)v41, 0, (int)v44, v33);
      RequiredUniqueNodeValue = v36;
      if ( v36 >= 0 )
      {
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 24);
        v37 = Appx::Packaging::Manifest::AppxManifestPropertiesWithoutValidationImpl::Create(
                (int)v45,
                v44[0],
                (struct IAppxManifestProperties **)this + 3);
        RequiredUniqueNodeValue = v37;
        if ( v37 >= 0 )
          goto LABEL_41;
        v34 = (unsigned int)v37;
        v35 = 95;
      }
      else
      {
        v34 = (unsigned int)v36;
        v35 = 93;
      }
    }
    else
    {
      v34 = (unsigned int)RequiredUniqueNodeValue;
      v35 = 91;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
      (const char *)v34,
      v38);
LABEL_41:
    SysFreeString(v41);
    goto LABEL_35;
  }
  v46[0] = L"m";
  v46[1] = L"http://schemas.microsoft.com/appx/2010/manifest";
  v46[2] = L"win10foundation";
  v46[3] = L"http://schemas.microsoft.com/appx/manifest/foundation/windows10";
  v46[4] = L"uap6";
  v46[5] = &Appx::Packaging::Manifest::RS4UapNamespace;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  v4 = Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(
         a2,
         (struct XmlNamespaceAlias *)v46,
         3u,
         0,
         &v42,
         0);
  RequiredUniqueNodeValue = v4;
  if ( v4 >= 0 )
  {
    v41 = (BSTR)v42;
    pbstr = 0;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v41);
    RequiredUniqueNodeValue = Appx::Packaging::GetRequiredUniqueNodeValue(
                                &v41,
                                L"m:Package/m:Identity/@Publisher | win10foundation:Package/win10foundation:Identity/@Publisher",
                                &pbstr);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
    if ( RequiredUniqueNodeValue < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)RequiredUniqueNodeValue,
        v38);
      v6 = pbstr;
LABEL_50:
      SysFreeString(v6);
      goto LABEL_51;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 16);
    v7 = pbstr;
    v8 = Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(
           pbstr,
           0,
           (struct IAppxManifestPackageId **)this + 2);
    RequiredUniqueNodeValue = v8;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v10 = 110;
LABEL_20:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
        (const char *)v9,
        v38);
      goto LABEL_49;
    }
    v41 = (BSTR)v42;
    bstrString = 0;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v41);
    RequiredUniqueNodeValue = Appx::Packaging::GetNodeValue(
                                &v41,
                                L"win10foundation:Package/win10foundation:Properties/uap6:AllowExecution",
                                v11,
                                &bstrString);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
    if ( RequiredUniqueNodeValue >= 0 )
    {
      v44[0] = 0;
      v15 = Appx::Packaging::ConvertToBool((Appx::Packaging *)bstrString, (unsigned __int16 *)1, (int)v44, v12);
      RequiredUniqueNodeValue = v15;
      if ( v15 >= 0 )
      {
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 24);
        v16 = Appx::Packaging::Manifest::AppxManifestPropertiesWithoutValidationImpl::Create(
                v44[0],
                0,
                (struct IAppxManifestProperties **)this + 3);
        RequiredUniqueNodeValue = v16;
        if ( v16 >= 0 )
          goto LABEL_11;
        v13 = (unsigned int)v16;
        v14 = 117;
      }
      else
      {
        v13 = (unsigned int)v15;
        v14 = 116;
      }
    }
    else
    {
      v13 = (unsigned int)RequiredUniqueNodeValue;
      v14 = 114;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
      (const char *)v13,
      v38);
LABEL_11:
    SysFreeString(bstrString);
LABEL_49:
    v6 = v7;
    goto LABEL_50;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreaderwithoutvalidation.cpp",
    (const char *)(unsigned int)v4,
    v38);
LABEL_51:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  return (unsigned int)RequiredUniqueNodeValue;
}

```

## disassembly

```asm
0x180058b00  mov     [rsp-8+arg_10], rbx
0x180058b05  push    rbp
0x180058b06  push    rsi
0x180058b07  push    rdi
0x180058b08  push    r14
0x180058b0a  push    r15
0x180058b0c  lea     rbp, [rsp-37h]
0x180058b11  sub     rsp, 0F0h
0x180058b18  mov     rax, cs:__security_cookie
0x180058b1f  xor     rax, rsp
0x180058b22  mov     [rbp+57h+var_30], rax
0x180058b26  xor     r15d, r15d
0x180058b29  mov     rbx, rdx
0x180058b2c  mov     [rbp+57h+var_C8], r15
0x180058b30  mov     r14, rcx
0x180058b33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TrustedLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch> `wil::Feature<__WilFeatureTraits_Feature_TrustedLaunch>::GetImpl(void)'::`2'::impl
0x180058b3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TrustedLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TrustedLaunch>::__private_IsEnabled(void)
0x180058b3f  test    al, al
0x180058b41  lea     rcx, [rbp+57h+var_C8]
0x180058b45  lea     rax, ?NamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "m"
0x180058b4c  jnz     loc_180058D12
0x180058b52  mov     [rbp+57h+var_A8], rax
0x180058b56  lea     rax, ?Namespace@Manifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2010/"...
0x180058b5d  mov     [rbp+57h+var_A0], rax
0x180058b61  lea     rax, ?Windows10FoundationNamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "win10foundation"
0x180058b68  mov     [rbp+57h+var_98], rax
0x180058b6c  lea     rax, ?Windows10FoundationNamespace@Manifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/manif"...
0x180058b73  mov     [rbp+57h+var_90], rax
0x180058b77  lea     rax, ?RS4UapNamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "uap6"
0x180058b7e  mov     [rbp+57h+var_88], rax
0x180058b82  lea     rax, ?RS4UapNamespace@Manifest@Packaging@Appx@@3QBGB; ushort const near * const Appx::Packaging::Manifest::RS4UapNamespace
0x180058b89  mov     [rbp+57h+var_80], rax
0x180058b8d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058b92  lea     rax, [rbp+57h+var_C8]
0x180058b96  mov     [rsp+110h+var_E8], r15; struct IXMLDOMDocument **
0x180058b9b  xor     r9d, r9d; unsigned __int16 **
0x180058b9e  mov     [rsp+110h+var_F0], rax; int
0x180058ba3  lea     r8d, [r15+3]; unsigned int
0x180058ba7  mov     rcx, rbx; this
0x180058baa  lea     rdx, [rbp+57h+var_A8]; struct XmlNamespaceAlias *
0x180058bae  call    ?LoadXmlWithoutValidation@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUXmlNamespaceAlias@@KPEAPEAGPEAPEAUIXMLDOMDocument@@3@Z; Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(IStream *,XmlNamespaceAlias *,ulong,ushort * *,IXMLDOMDocument * *,IXMLDOMDocument * *)
0x180058bb3  mov     edi, eax
0x180058bb5  test    eax, eax
0x180058bb7  jns     short loc_180058BD5
0x180058bb9  mov     rcx, [rbp+5Fh]; this
0x180058bbd  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058bc4  mov     r9d, eax; char *
0x180058bc7  lea     edx, [r15+69h]; void *
0x180058bcb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058bd0  jmp     loc_1800590B0
0x180058bd5  mov     rax, [rbp+57h+var_C8]
0x180058bd9  lea     rcx, [rbp+57h+var_D0]
0x180058bdd  mov     [rbp+57h+var_D0], rax
0x180058be1  mov     [rbp+57h+pbstr], r15
0x180058be5  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058bea  lea     r8, [rbp+57h+pbstr]
0x180058bee  lea     rdx, aMPackageMIdent; "m:Package/m:Identity/@Publisher | win10"...
0x180058bf5  lea     rcx, [rbp+57h+var_D0]
0x180058bf9  call    ?GetRequiredUniqueNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAG@Z; Appx::Packaging::GetRequiredUniqueNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,ushort * *)
0x180058bfe  lea     rcx, [rbp+57h+var_D0]
0x180058c02  mov     edi, eax
0x180058c04  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058c09  test    edi, edi
0x180058c0b  jns     short loc_180058C2E
0x180058c0d  mov     rcx, [rbp+5Fh]; this
0x180058c11  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058c18  mov     r9d, edi; char *
0x180058c1b  mov     edx, 6Dh ; 'm'; void *
0x180058c20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058c25  mov     rcx, [rbp+57h+pbstr]
0x180058c29  jmp     loc_1800590A4
0x180058c2e  lea     rcx, [r14+10h]
0x180058c32  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058c37  mov     rbx, [rbp+57h+pbstr]
0x180058c3b  lea     r8, [r14+10h]; struct IAppxManifestPackageId **
0x180058c3f  mov     rcx, rbx; pbstr
0x180058c42  xor     edx, edx; unsigned __int16 *
0x180058c44  call    ?Create@AppxManifestPackageIdWithoutValidationImpl@Manifest@Packaging@Appx@@SAJPEAGPEBGPEAPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(ushort *,ushort const *,IAppxManifestPackageId * *)
0x180058c49  mov     edi, eax
0x180058c4b  test    eax, eax
0x180058c4d  jns     short loc_180058C5C
0x180058c4f  mov     r9d, eax
0x180058c52  mov     edx, 6Eh ; 'n'
0x180058c57  jmp     loc_180058DFF
0x180058c5c  mov     rax, [rbp+57h+var_C8]
0x180058c60  lea     rcx, [rbp+57h+var_D0]
0x180058c64  mov     [rbp+57h+var_D0], rax
0x180058c68  mov     [rsp+110h+bstrString], r15
0x180058c6d  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058c72  lea     r9, [rsp+110h+bstrString]
0x180058c77  lea     rdx, aWin10foundatio; "win10foundation:Package/win10foundation"...
0x180058c7e  lea     rcx, [rbp+57h+var_D0]
0x180058c82  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *,IXMLDOMNode * *)
0x180058c87  lea     rcx, [rbp+57h+var_D0]
0x180058c8b  mov     edi, eax
0x180058c8d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058c92  test    edi, edi
0x180058c94  jns     short loc_180058CC4
0x180058c96  mov     r9d, edi; char *
0x180058c99  mov     edx, 72h ; 'r'; void *
0x180058c9e  mov     rcx, [rbp+5Fh]; this
0x180058ca2  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058ca9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058cae  mov     rcx, [rsp+110h+bstrString]; bstrString
0x180058cb3  call    cs:__imp_SysFreeString
0x180058cba  nop     dword ptr [rax+rax+00h]
0x180058cbf  jmp     loc_1800590A1
0x180058cc4  mov     rcx, [rsp+110h+bstrString]; this
0x180058cc9  lea     r8, [rbp+57h+var_B8]; int
0x180058ccd  mov     edx, 1; unsigned __int16 *
0x180058cd2  mov     [rbp+57h+var_B8], r15d
0x180058cd6  call    ?ConvertToBool@Packaging@Appx@@YAJPEAGHPEAH@Z; Appx::Packaging::ConvertToBool(ushort *,int,int *)
0x180058cdb  mov     edi, eax
0x180058cdd  test    eax, eax
0x180058cdf  jns     short loc_180058CEB
0x180058ce1  mov     r9d, eax
0x180058ce4  mov     edx, 74h ; 't'
0x180058ce9  jmp     short loc_180058C9E
0x180058ceb  lea     rcx, [r14+18h]
0x180058cef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058cf4  mov     ecx, [rbp+57h+var_B8]; int
0x180058cf7  lea     r8, [r14+18h]; struct IAppxManifestProperties **
0x180058cfb  xor     edx, edx; int
0x180058cfd  call    ?Create@AppxManifestPropertiesWithoutValidationImpl@Manifest@Packaging@Appx@@SAJHHPEAPEAUIAppxManifestProperties@@@Z; Appx::Packaging::Manifest::AppxManifestPropertiesWithoutValidationImpl::Create(int,int,IAppxManifestProperties * *)
0x180058d02  mov     edi, eax
0x180058d04  test    eax, eax
0x180058d06  jns     short loc_180058CAE
0x180058d08  mov     r9d, eax
0x180058d0b  mov     edx, 75h ; 'u'
0x180058d10  jmp     short loc_180058C9E
0x180058d12  mov     [rbp+57h+var_70], rax
0x180058d16  lea     rax, ?Namespace@Manifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2010/"...
0x180058d1d  mov     [rbp+57h+var_68], rax
0x180058d21  lea     rax, ?Windows10FoundationNamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "win10foundation"
0x180058d28  mov     [rbp+57h+var_60], rax
0x180058d2c  lea     rax, ?Windows10FoundationNamespace@Manifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/manif"...
0x180058d33  mov     [rbp+57h+var_58], rax
0x180058d37  lea     rax, ?RS4UapNamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "uap6"
0x180058d3e  mov     [rbp+57h+var_50], rax
0x180058d42  lea     rax, ?RS4UapNamespace@Manifest@Packaging@Appx@@3QBGB; ushort const near * const Appx::Packaging::Manifest::RS4UapNamespace
0x180058d49  mov     [rbp+57h+var_48], rax
0x180058d4d  lea     rax, ?GermaniumTrustedLaunchNamespaceAlias@Manifest@Packaging@Appx@@3QBGB; "trustedlaunch"
0x180058d54  mov     [rbp+57h+var_40], rax
0x180058d58  lea     rax, ?GermaniumTrustedLaunchNamespace@Manifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/manif"...
0x180058d5f  mov     [rbp+57h+var_38], rax
0x180058d63  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058d68  xor     r9d, r9d; unsigned __int16 **
0x180058d6b  mov     [rsp+110h+var_E8], r15; struct IXMLDOMDocument **
0x180058d70  lea     rax, [rbp+57h+var_C8]
0x180058d74  mov     rcx, rbx; this
0x180058d77  lea     rdx, [rbp+57h+var_70]; struct XmlNamespaceAlias *
0x180058d7b  mov     [rsp+110h+var_F0], rax; int
0x180058d80  lea     r8d, [r9+4]; unsigned int
0x180058d84  call    ?LoadXmlWithoutValidation@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUXmlNamespaceAlias@@KPEAPEAGPEAPEAUIXMLDOMDocument@@3@Z; Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(IStream *,XmlNamespaceAlias *,ulong,ushort * *,IXMLDOMDocument * *,IXMLDOMDocument * *)
0x180058d89  mov     ebx, eax
0x180058d8b  test    eax, eax
0x180058d8d  jns     short loc_180058DB7
0x180058d8f  mov     rcx, [rbp+5Fh]; this
0x180058d93  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058d9a  mov     r9d, eax; char *
0x180058d9d  mov     edx, 40h ; '@'; void *
0x180058da2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058da7  lea     rcx, [rbp+57h+var_C8]
0x180058dab  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058db0  mov     eax, ebx
0x180058db2  jmp     loc_1800590BB
0x180058db7  mov     rax, [rbp+57h+var_C8]
0x180058dbb  lea     rcx, [rsp+110h+bstrString]
0x180058dc0  mov     [rsp+110h+bstrString], rax
0x180058dc5  mov     [rbp+57h+var_B0], r15
0x180058dc9  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058dce  lea     r8, [rbp+57h+var_B0]
0x180058dd2  lea     rdx, aMPackageMIdent; "m:Package/m:Identity/@Publisher | win10"...
0x180058dd9  lea     rcx, [rsp+110h+bstrString]
0x180058dde  call    ?GetRequiredUniqueNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAG@Z; Appx::Packaging::GetRequiredUniqueNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,ushort * *)
0x180058de3  lea     rcx, [rsp+110h+bstrString]
0x180058de8  mov     edi, eax
0x180058dea  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058def  mov     rbx, [rbp+57h+var_B0]
0x180058df3  test    edi, edi
0x180058df5  jns     short loc_180058E14
0x180058df7  mov     r9d, edi; char *
0x180058dfa  mov     edx, 44h ; 'D'; void *
0x180058dff  mov     rcx, [rbp+5Fh]; this
0x180058e03  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058e0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058e0f  jmp     loc_1800590A1
0x180058e14  lea     rcx, [rsp+110h+var_D8]
0x180058e19  mov     [rsp+110h+var_D8], r15
0x180058e1e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058e23  mov     rax, [rbp+57h+var_C8]
0x180058e27  lea     rcx, [rsp+110h+bstrString]
0x180058e2c  mov     [rsp+110h+bstrString], rax
0x180058e31  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058e36  lea     r8, [rsp+110h+var_D8]
0x180058e3b  lea     rdx, aMPackageMIdent_0; "m:Package/m:Identity | win10foundation:"...
0x180058e42  lea     rcx, [rsp+110h+bstrString]
0x180058e47  call    ?TryGetNode@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::TryGetNode(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,IXMLDOMNode * *)
0x180058e4c  lea     rcx, [rsp+110h+bstrString]
0x180058e51  mov     edi, eax
0x180058e53  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058e58  test    edi, edi
0x180058e5a  jns     short loc_180058E66
0x180058e5c  mov     edx, 48h ; 'H'
0x180058e61  jmp     loc_180059084
0x180058e66  mov     rdi, [rsp+110h+var_D8]
0x180058e6b  test    rdi, rdi
0x180058e6e  jnz     short loc_180058E7F
0x180058e70  mov     edi, 80080204h
0x180058e75  mov     edx, 49h ; 'I'
0x180058e7a  jmp     loc_180059084
0x180058e7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180058e86  mov     ecx, 20h ; ' '; unsigned __int64
0x180058e8b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180058e90  test    rax, rax
0x180058e93  jz      loc_18005907A
0x180058e99  mov     rdx, rdi; struct IXMLDOMNode *
0x180058e9c  mov     rcx, rax; this
0x180058e9f  call    ??0PackageIdHelper@Manifest@Packaging@Appx@@QEAA@PEAUIXMLDOMNode@@@Z; Appx::Packaging::Manifest::PackageIdHelper::PackageIdHelper(IXMLDOMNode *)
0x180058ea4  mov     rsi, rax
0x180058ea7  test    rax, rax
0x180058eaa  jz      loc_18005907A
0x180058eb0  xor     edx, edx
0x180058eb2  mov     [rsp+110h+bstrString], r15
0x180058eb7  lea     rcx, [rsp+110h+bstrString]
0x180058ebc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058ec1  lea     r8, [rsp+110h+bstrString]
0x180058ec6  xor     edx, edx
0x180058ec8  mov     rcx, rsi
0x180058ecb  call    ?GetPackageNameInternal@PackageIdHelper@Manifest@Packaging@Appx@@AEAAJW4PackageNameType@1234@PEAPEAG@Z; Appx::Packaging::Manifest::PackageIdHelper::GetPackageNameInternal(Appx::Packaging::Manifest::PackageIdHelper::PackageNameType,ushort * *)
0x180058ed0  mov     edi, eax
0x180058ed2  test    eax, eax
0x180058ed4  jns     short loc_180058F05
0x180058ed6  mov     rcx, [rbp+5Fh]; this
0x180058eda  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058ee1  mov     r9d, eax; char *
0x180058ee4  mov     edx, 4Fh ; 'O'; void *
0x180058ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058eee  lea     rcx, [rsp+110h+bstrString]
0x180058ef3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058ef8  mov     rcx, rsi; this
0x180058efb  call    ??_GPackageIdHelper@Manifest@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Manifest::PackageIdHelper::`scalar deleting destructor'(uint)
0x180058f00  jmp     loc_180059097
0x180058f05  lea     rcx, [r14+10h]
0x180058f09  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058f0e  mov     rdx, [rsp+110h+bstrString]; unsigned __int16 *
0x180058f13  lea     r8, [r14+10h]; struct IAppxManifestPackageId **
0x180058f17  mov     rcx, rbx; pbstr
0x180058f1a  call    ?Create@AppxManifestPackageIdWithoutValidationImpl@Manifest@Packaging@Appx@@SAJPEAGPEBGPEAPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(ushort *,ushort const *,IAppxManifestPackageId * *)
0x180058f1f  mov     edi, eax
0x180058f21  test    eax, eax
0x180058f23  jns     short loc_180058F3F
0x180058f25  mov     rcx, [rbp+5Fh]; this
0x180058f29  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058f30  mov     r9d, eax; char *
0x180058f33  mov     edx, 51h ; 'Q'; void *
0x180058f38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058f3d  jmp     short loc_180058EEE
0x180058f3f  mov     rax, [rbp+57h+var_C8]
0x180058f43  lea     rcx, [rbp+57h+var_B0]
0x180058f47  mov     [rbp+57h+var_B0], rax
0x180058f4b  mov     [rbp+57h+pbstr], r15
0x180058f4f  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058f54  lea     r9, [rbp+57h+pbstr]
0x180058f58  lea     rdx, aWin10foundatio; "win10foundation:Package/win10foundation"...
0x180058f5f  lea     rcx, [rbp+57h+var_B0]
0x180058f63  call    ?GetNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAGPEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::GetNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,ushort * *,IXMLDOMNode * *)
0x180058f68  lea     rcx, [rbp+57h+var_B0]
0x180058f6c  mov     edi, eax
0x180058f6e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180058f73  test    edi, edi
0x180058f75  jns     short loc_180058FA4
0x180058f77  mov     r9d, edi; char *
0x180058f7a  mov     edx, 55h ; 'U'; void *
0x180058f7f  mov     rcx, [rbp+5Fh]; this
0x180058f83  lea     r8, aOnecorePrintsc_14; "onecore\\printscan\\appxpackaging\\mani"...
0x180058f8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058f8f  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180058f93  call    cs:__imp_SysFreeString
0x180058f9a  nop     dword ptr [rax+rax+00h]
0x180058f9f  jmp     loc_180058EEE
0x180058fa4  mov     rcx, [rbp+57h+pbstr]; this
0x180058fa8  lea     r8, [rbp+57h+var_B0]; int
0x180058fac  mov     edx, 1; unsigned __int16 *
0x180058fb1  mov     dword ptr [rbp+57h+var_B0], r15d
0x180058fb5  call    ?ConvertToBool@Packaging@Appx@@YAJPEAGHPEAH@Z; Appx::Packaging::ConvertToBool(ushort *,int,int *)
0x180058fba  mov     edi, eax
0x180058fbc  test    eax, eax
0x180058fbe  jns     short loc_180058FCA
0x180058fc0  mov     r9d, eax
0x180058fc3  mov     edx, 57h ; 'W'
0x180058fc8  jmp     short loc_180058F7F
0x180058fca  mov     rax, [rbp+57h+var_C8]
0x180058fce  lea     rcx, [rbp+57h+var_B8]
0x180058fd2  mov     qword ptr [rbp+57h+var_B8], rax
0x180058fd6  mov     [rbp+57h+var_D0], r15
0x180058fda  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x180058fdf  lea     r9, [rbp+57h+var_D0]
0x180058fe3  lea     rdx, aWin10foundatio_0; "win10foundation:Package/win10foundation"...
0x180058fea  lea     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
