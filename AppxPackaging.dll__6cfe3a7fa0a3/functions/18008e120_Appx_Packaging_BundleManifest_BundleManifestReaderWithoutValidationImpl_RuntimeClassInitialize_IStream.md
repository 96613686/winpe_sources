# Appx::Packaging::BundleManifest::BundleManifestReaderWithoutValidationImpl::RuntimeClassInitialize(IStream *)

- ea: `0x18008e120`
- end: `0x18008e53f`
- name: `?RuntimeClassInitialize@BundleManifestReaderWithoutValidationImpl@BundleManifest@Packaging@Appx@@QEAAJPEAUIStream@@@Z`
- size: `1055`
- prototype: `int(Appx::Packaging::BundleManifest::BundleManifestReaderWithoutValidationImpl *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180095854`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180011cd0`
- `0x1800133fc`
- `0x180019950`
- `0x180023d10`
- `0x180035ba8`
- `0x18005bc7c`
- `0x180071f50`
- `0x18008e120`
- `0x18008e548`
- `0x1800992a0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlIsGenericTableEmptyAvl` at `0x18008e4cd`
- `ntdll!RtlIsGenericTableEmptyAvl` at `0x18008e4cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e269`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e2b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e3f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e403`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e43c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e48b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e507`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e269`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e2b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e3f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e403`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e43c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e48b`
- `OLEAUT32!__imp_SysFreeString` at `0x18008e507`

## string_xrefs

- `0x18008e15e`: `http://schemas.microsoft.com/appx/2013/bundle`
- `0x18008e1bc`: `http://schemas.microsoft.com/appx/2019/bundle`
- `0x18008e1a6`: `http://schemas.microsoft.com/appx/2018/bundle`
- `0x18008e190`: `http://schemas.microsoft.com/appx/2017/bundle`
- `0x18008e17a`: `http://schemas.microsoft.com/appx/2016/bundle`
- `0x18008e1f7`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e251`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e29e`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e328`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e42c`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e473`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e49d`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`
- `0x18008e4e1`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreaderwithoutvalidation.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestReaderWithoutValidationImpl::RuntimeClassInitialize(
        Appx::Packaging::BundleManifest::BundleManifestReaderWithoutValidationImpl *this,
        struct IStream *a2)
{
  struct IXMLDOMDocument **v3; // rsi
  int XmlWithoutValidation; // eax
  unsigned int RequiredUniqueNodeValue; // ebx
  OLECHAR *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int NodesList; // r14d
  BSTR v12; // rsi
  int i; // r15d
  __int64 (__fastcall *v14)(BSTR, __int64 *); // rdi
  int v15; // eax
  int v16; // eax
  OLECHAR *v17; // rdi
  int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-69h]
  BSTR bstrString; // [rsp+30h] [rbp-59h] BYREF
  BSTR v23; // [rsp+38h] [rbp-51h] BYREF
  __int64 v24; // [rsp+40h] [rbp-49h] BYREF
  int v25; // [rsp+48h] [rbp-41h] BYREF
  BSTR v26[2]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v27[10]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v27[0] = L"b";
  v3 = (struct IXMLDOMDocument **)((char *)this + 24);
  v27[1] = L"http://schemas.microsoft.com/appx/2013/bundle";
  v27[2] = L"b2";
  v27[3] = L"http://schemas.microsoft.com/appx/2016/bundle";
  v27[4] = L"b3";
  v27[5] = L"http://schemas.microsoft.com/appx/2017/bundle";
  v27[6] = L"b4";
  v27[7] = L"http://schemas.microsoft.com/appx/2018/bundle";
  v27[8] = L"b5";
  v27[9] = L"http://schemas.microsoft.com/appx/2019/bundle";
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 24);
  XmlWithoutValidation = Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(
                           a2,
                           (struct XmlNamespaceAlias *)v27,
                           5u,
                           0,
                           v3,
                           0);
  RequiredUniqueNodeValue = XmlWithoutValidation;
  if ( XmlWithoutValidation < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
      (const char *)(unsigned int)XmlWithoutValidation,
      v21);
    return RequiredUniqueNodeValue;
  }
  v23 = (BSTR)*v3;
  bstrString = 0;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v23);
  RequiredUniqueNodeValue = Appx::Packaging::GetRequiredUniqueNodeValue(
                              &v23,
                              L"b:Bundle/b:Identity/@Publisher | b2:Bundle/b2:Identity/@Publisher | b3:Bundle/b3:Identity/"
                               "@Publisher | b4:Bundle/b4:Identity/@Publisher",
                              &bstrString);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v23);
  if ( (RequiredUniqueNodeValue & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
      (const char *)RequiredUniqueNodeValue,
      v21);
    SysFreeString(bstrString);
    return RequiredUniqueNodeValue;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)this + 32);
  v8 = bstrString;
  v9 = Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(
         bstrString,
         0,
         (struct IAppxManifestPackageId **)this + 4);
  v10 = v9;
  if ( v9 >= 0 )
  {
    bstrString = 0;
    v25 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
    v23 = (BSTR)*v3;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v23);
    NodesList = Appx::Packaging::GetNodesList(
                  &v23,
                  L"b:Bundle/b:Packages/b:Package | b2:Bundle/b2:Packages/b2:Package | b3:Bundle/b3:Packages/b3:Package | "
                   "b4:Bundle/b4:Packages/b4:Package | b:Bundle/b:Packages/b5:Package | b2:Bundle/b2:Packages/b5:Package "
                   "| b3:Bundle/b3:Packages/b5:Package | b4:Bundle/b4:Packages/b5:Package",
                  2148008452LL,
                  &bstrString);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v23);
    if ( NodesList >= 0 )
    {
      v12 = bstrString;
      for ( i = 0; i < v25; ++i )
      {
        v24 = 0;
        v14 = *(__int64 (__fastcall **)(BSTR, __int64 *))(*(_QWORD *)v12 + 72LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
        v15 = v14(v12, &v24);
        v10 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x6F,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
            (const char *)(unsigned int)v15,
            (int)&v25);
          goto LABEL_23;
        }
        v26[0] = 0;
        v16 = Appx::Packaging::BuildXPath(4, L"FileName", v26);
        v10 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x73,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
            (const char *)(unsigned int)v16,
            (int)&v25);
          SysFreeString(v26[0]);
LABEL_23:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
          goto LABEL_8;
        }
        v17 = v26[0];
        v23 = 0;
        NodesList = Appx::Packaging::GetRequiredUniqueNodeValue(&v24, v26[0], &v23);
        if ( NodesList < 0 )
        {
          v19 = (unsigned int)NodesList;
          v20 = 117;
          goto LABEL_19;
        }
        v18 = Common::GenericMap<unsigned short *,unsigned short *>::Insert((char *)this + 40, v23, v24);
        NodesList = v18;
        if ( v18 < 0 )
        {
          v19 = (unsigned int)v18;
          v20 = 119;
LABEL_19:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
            (const char *)v19,
            (int)&v25);
          SysFreeString(v23);
          SysFreeString(v17);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
          goto LABEL_26;
        }
        v24 = 0;
        SysFreeString(0);
        SysFreeString(v17);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v24);
      }
      if ( RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)((char *)this + 40)) )
      {
        NodesList = -2146958844;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
          (const char *)0x80080204LL,
          (int)&v25);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
        (const char *)(unsigned int)NodesList,
        (int)&v25);
    }
LABEL_26:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&bstrString);
    SysFreeString(v8);
    return (unsigned int)NodesList;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreaderwithoutvalidation.cpp",
      (const char *)(unsigned int)v9,
      v21);
LABEL_8:
    SysFreeString(v8);
    return v10;
  }
}

```

## disassembly

```asm
0x18008e120  mov     [rsp-8+arg_10], rbx
0x18008e125  mov     [rsp-8+arg_18], rsi
0x18008e12a  push    rbp
0x18008e12b  push    rdi
0x18008e12c  push    r12
0x18008e12e  push    r14
0x18008e130  push    r15
0x18008e132  lea     rbp, [rsp-37h]
0x18008e137  sub     rsp, 0C0h
0x18008e13e  mov     rax, cs:__security_cookie
0x18008e145  xor     rax, rsp
0x18008e148  mov     [rbp+57h+var_30], rax
0x18008e14c  lea     rax, ?NamespaceAlias@BundleManifest@Packaging@Appx@@3QBGB; "b"
0x18008e153  mov     r12, rcx
0x18008e156  mov     [rbp+57h+var_80], rax
0x18008e15a  lea     rsi, [rcx+18h]
0x18008e15e  lea     rax, ?Namespace@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2013/"...
0x18008e165  mov     rcx, rsi
0x18008e168  mov     [rbp+57h+var_78], rax
0x18008e16c  mov     rbx, rdx
0x18008e16f  lea     rax, ?Namespace2016Alias@BundleManifest@Packaging@Appx@@3QBGB; "b2"
0x18008e176  mov     [rbp+57h+var_70], rax
0x18008e17a  lea     rax, ?Namespace2016@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2016/"...
0x18008e181  mov     [rbp+57h+var_68], rax
0x18008e185  lea     rax, ?Namespace2017Alias@BundleManifest@Packaging@Appx@@3QBGB; "b3"
0x18008e18c  mov     [rbp+57h+var_60], rax
0x18008e190  lea     rax, ?Namespace2017@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2017/"...
0x18008e197  mov     [rbp+57h+var_58], rax
0x18008e19b  lea     rax, ?Namespace2018Alias@BundleManifest@Packaging@Appx@@3QBGB; "b4"
0x18008e1a2  mov     [rbp+57h+var_50], rax
0x18008e1a6  lea     rax, ?Namespace2018@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2018/"...
0x18008e1ad  mov     [rbp+57h+var_48], rax
0x18008e1b1  lea     rax, ?Namespace2019Alias@BundleManifest@Packaging@Appx@@3QBGB; "b5"
0x18008e1b8  mov     [rbp+57h+var_40], rax
0x18008e1bc  lea     rax, ?Namespace2019@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2019/"...
0x18008e1c3  mov     [rbp+57h+var_38], rax
0x18008e1c7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e1cc  xor     r9d, r9d; unsigned __int16 **
0x18008e1cf  mov     [rsp+0E0h+var_B8], 0; struct IXMLDOMDocument **
0x18008e1d8  lea     rdx, [rbp+57h+var_80]; struct XmlNamespaceAlias *
0x18008e1dc  mov     [rsp+0E0h+var_C0], rsi; int
0x18008e1e1  mov     rcx, rbx; this
0x18008e1e4  lea     r8d, [r9+5]; unsigned int
0x18008e1e8  call    ?LoadXmlWithoutValidation@XmlValidationHelper@Packaging@Appx@@SAJPEAUIStream@@PEAUXmlNamespaceAlias@@KPEAPEAGPEAPEAUIXMLDOMDocument@@3@Z; Appx::Packaging::XmlValidationHelper::LoadXmlWithoutValidation(IStream *,XmlNamespaceAlias *,ulong,ushort * *,IXMLDOMDocument * *,IXMLDOMDocument * *)
0x18008e1ed  mov     ebx, eax
0x18008e1ef  test    eax, eax
0x18008e1f1  jns     short loc_18008E212
0x18008e1f3  mov     rcx, [rbp+5Fh]; this
0x18008e1f7  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e1fe  mov     r9d, eax; char *
0x18008e201  mov     edx, 60h ; '`'; void *
0x18008e206  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e20b  mov     eax, ebx
0x18008e20d  jmp     loc_18008E516
0x18008e212  mov     rax, [rsi]
0x18008e215  lea     rcx, [rbp+57h+var_A8]
0x18008e219  mov     [rbp+57h+var_A8], rax
0x18008e21d  mov     [rbp+57h+bstrString], 0
0x18008e225  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x18008e22a  lea     r8, [rbp+57h+bstrString]
0x18008e22e  lea     rdx, aBBundleBIdenti; "b:Bundle/b:Identity/@Publisher | b2:Bun"...
0x18008e235  lea     rcx, [rbp+57h+var_A8]
0x18008e239  call    ?GetRequiredUniqueNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAG@Z; Appx::Packaging::GetRequiredUniqueNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,ushort * *)
0x18008e23e  lea     rcx, [rbp+57h+var_A8]
0x18008e242  mov     ebx, eax
0x18008e244  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e249  test    ebx, ebx
0x18008e24b  jns     short loc_18008E277
0x18008e24d  mov     rcx, [rbp+5Fh]; this
0x18008e251  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e258  mov     r9d, ebx; char *
0x18008e25b  mov     edx, 63h ; 'c'; void *
0x18008e260  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e265  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18008e269  call    cs:__imp_SysFreeString
0x18008e270  nop     dword ptr [rax+rax+00h]
0x18008e275  jmp     short loc_18008E20B
0x18008e277  lea     rcx, [r12+20h]
0x18008e27c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e281  mov     rbx, [rbp+57h+bstrString]
0x18008e285  lea     r8, [r12+20h]; struct IAppxManifestPackageId **
0x18008e28a  mov     rcx, rbx; pbstr
0x18008e28d  xor     edx, edx; unsigned __int16 *
0x18008e28f  call    ?Create@AppxManifestPackageIdWithoutValidationImpl@Manifest@Packaging@Appx@@SAJPEAGPEBGPEAPEAUIAppxManifestPackageId@@@Z; Appx::Packaging::Manifest::AppxManifestPackageIdWithoutValidationImpl::Create(ushort *,ushort const *,IAppxManifestPackageId * *)
0x18008e294  mov     edi, eax
0x18008e296  test    eax, eax
0x18008e298  jns     short loc_18008E2C8
0x18008e29a  mov     rcx, [rbp+5Fh]; this
0x18008e29e  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e2a5  mov     r9d, eax; char *
0x18008e2a8  mov     edx, 64h ; 'd'; void *
0x18008e2ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e2b2  mov     rcx, rbx; bstrString
0x18008e2b5  call    cs:__imp_SysFreeString
0x18008e2bc  nop     dword ptr [rax+rax+00h]
0x18008e2c1  mov     eax, edi
0x18008e2c3  jmp     loc_18008E516
0x18008e2c8  lea     rcx, [rbp+57h+bstrString]
0x18008e2cc  mov     [rbp+57h+bstrString], 0
0x18008e2d4  mov     [rbp+57h+var_98], 0
0x18008e2db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e2e0  mov     rax, [rsi]
0x18008e2e3  lea     rcx, [rbp+57h+var_A8]
0x18008e2e7  mov     [rbp+57h+var_A8], rax
0x18008e2eb  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x18008e2f0  lea     rax, [rbp+57h+var_98]
0x18008e2f4  mov     r8d, 80080204h
0x18008e2fa  lea     r9, [rbp+57h+bstrString]
0x18008e2fe  mov     [rsp+0E0h+var_C0], rax; int
0x18008e303  lea     rdx, aBBundleBPackag; "b:Bundle/b:Packages/b:Package | b2:Bund"...
0x18008e30a  lea     rcx, [rbp+57h+var_A8]
0x18008e30e  call    ?GetNodesList@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::GetNodesList(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,long,IXMLDOMNodeList * *,long *)
0x18008e313  lea     rcx, [rbp+57h+var_A8]
0x18008e317  mov     r14d, eax
0x18008e31a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e31f  test    r14d, r14d
0x18008e322  jns     short loc_18008E341
0x18008e324  mov     rcx, [rbp+5Fh]; this
0x18008e328  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e32f  mov     r9d, r14d; char *
0x18008e332  mov     edx, 6Ah ; 'j'; void *
0x18008e337  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e33c  jmp     loc_18008E4FB
0x18008e341  mov     rsi, [rbp+57h+bstrString]
0x18008e345  xor     r15d, r15d
0x18008e348  cmp     r15d, [rbp+57h+var_98]
0x18008e34c  jge     loc_18008E4C8
0x18008e352  mov     [rbp+57h+var_A0], 0
0x18008e35a  lea     rcx, [rbp+57h+var_A0]
0x18008e35e  mov     rax, [rsi]
0x18008e361  mov     rdi, [rax+48h]
0x18008e365  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e36a  lea     rdx, [rbp+57h+var_A0]
0x18008e36e  mov     rcx, rsi
0x18008e371  mov     rax, rdi
0x18008e374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e379  mov     edi, eax
0x18008e37b  test    eax, eax
0x18008e37d  js      loc_18008E499
0x18008e383  lea     r8, [rbp+57h+var_90]
0x18008e387  mov     [rbp+57h+var_90], 0
0x18008e38f  lea     rdx, ?FileName@AttributeNameWithoutPrefix@BundleManifest@Packaging@Appx@@3QBGB; "FileName"
0x18008e396  mov     ecx, 4
0x18008e39b  call    ?BuildXPath@Packaging@Appx@@YAJW4XPathComponentType@12@PEBGAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponentType,ushort const *,Common::AutoBStr &)
0x18008e3a0  mov     edi, eax
0x18008e3a2  test    eax, eax
0x18008e3a4  js      loc_18008E46F
0x18008e3aa  mov     rdi, [rbp+57h+var_90]
0x18008e3ae  lea     r8, [rbp+57h+var_A8]
0x18008e3b2  mov     rdx, rdi
0x18008e3b5  mov     [rbp+57h+var_A8], 0
0x18008e3bd  lea     rcx, [rbp+57h+var_A0]
0x18008e3c1  call    ?GetRequiredUniqueNodeValue@Packaging@Appx@@YAJAEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBGPEAPEAG@Z; Appx::Packaging::GetRequiredUniqueNodeValue(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *,ushort * *)
0x18008e3c6  mov     r14d, eax
0x18008e3c9  test    eax, eax
0x18008e3cb  js      loc_18008E465
0x18008e3d1  mov     r8, [rbp+57h+var_A0]
0x18008e3d5  lea     rcx, [r12+28h]
0x18008e3da  mov     rdx, [rbp+57h+var_A8]
0x18008e3de  call    ?Insert@?$GenericMap@PEAGPEAG@Common@@QEAAJPEAG0@Z; Common::GenericMap<ushort *,ushort *>::Insert(ushort *,ushort *)
0x18008e3e3  mov     r14d, eax
0x18008e3e6  test    eax, eax
0x18008e3e8  js      short loc_18008E420
0x18008e3ea  xor     ecx, ecx; bstrString
0x18008e3ec  mov     [rbp+57h+var_A0], 0
0x18008e3f4  call    cs:__imp_SysFreeString
0x18008e3fb  nop     dword ptr [rax+rax+00h]
0x18008e400  mov     rcx, rdi; bstrString
0x18008e403  call    cs:__imp_SysFreeString
0x18008e40a  nop     dword ptr [rax+rax+00h]
0x18008e40f  lea     rcx, [rbp+57h+var_A0]
0x18008e413  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e418  inc     r15d
0x18008e41b  jmp     loc_18008E348
0x18008e420  mov     r9d, eax; char *
0x18008e423  mov     edx, 77h ; 'w'; void *
0x18008e428  mov     rcx, [rbp+5Fh]; this
0x18008e42c  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e433  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e438  mov     rcx, [rbp+57h+var_A8]; bstrString
0x18008e43c  call    cs:__imp_SysFreeString
0x18008e443  nop     dword ptr [rax+rax+00h]
0x18008e448  mov     rcx, rdi; bstrString
0x18008e44b  call    cs:__imp_SysFreeString
0x18008e452  nop     dword ptr [rax+rax+00h]
0x18008e457  lea     rcx, [rbp+57h+var_A0]
0x18008e45b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e460  jmp     loc_18008E4FB
0x18008e465  mov     r9d, r14d
0x18008e468  mov     edx, 75h ; 'u'
0x18008e46d  jmp     short loc_18008E428
0x18008e46f  mov     rcx, [rbp+5Fh]; this
0x18008e473  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e47a  mov     r9d, edi; char *
0x18008e47d  mov     edx, 73h ; 's'; void *
0x18008e482  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e487  mov     rcx, [rbp+57h+var_90]; bstrString
0x18008e48b  call    cs:__imp_SysFreeString
0x18008e492  nop     dword ptr [rax+rax+00h]
0x18008e497  jmp     short loc_18008E4B1
0x18008e499  mov     rcx, [rbp+5Fh]; this
0x18008e49d  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e4a4  mov     r9d, edi; char *
0x18008e4a7  mov     edx, 6Fh ; 'o'; void *
0x18008e4ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e4b1  lea     rcx, [rbp+57h+var_A0]
0x18008e4b5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e4ba  lea     rcx, [rbp+57h+bstrString]
0x18008e4be  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e4c3  jmp     loc_18008E2B2
0x18008e4c8  lea     rcx, [r12+28h]; Table
0x18008e4cd  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x18008e4d4  nop     dword ptr [rax+rax+00h]
0x18008e4d9  test    al, al
0x18008e4db  jz      short loc_18008E4FB
0x18008e4dd  mov     rcx, [rbp+5Fh]; this
0x18008e4e1  lea     r8, aOnecorePrintsc_163; "onecore\\printscan\\appxpackaging\\mani"...
0x18008e4e8  mov     r14d, 80080204h
0x18008e4ee  mov     edx, 7Bh ; '{'; void *
0x18008e4f3  mov     r9d, r14d; char *
0x18008e4f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e4fb  lea     rcx, [rbp+57h+bstrString]
0x18008e4ff  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e504  mov     rcx, rbx; bstrString
0x18008e507  call    cs:__imp_SysFreeString
0x18008e50e  nop     dword ptr [rax+rax+00h]
0x18008e513  mov     eax, r14d
0x18008e516  mov     rcx, [rbp+57h+var_30]
0x18008e51a  xor     rcx, rsp; StackCookie
0x18008e51d  call    __security_check_cookie
0x18008e522  lea     r11, [rsp+0E0h+var_20]
0x18008e52a  mov     rbx, [r11+40h]
0x18008e52e  mov     rsi, [r11+48h]
0x18008e532  mov     rsp, r11
0x18008e535  pop     r15
0x18008e537  pop     r14
0x18008e539  pop     r12
0x18008e53b  pop     rdi
0x18008e53c  pop     rbp
0x18008e53d  retn
```
