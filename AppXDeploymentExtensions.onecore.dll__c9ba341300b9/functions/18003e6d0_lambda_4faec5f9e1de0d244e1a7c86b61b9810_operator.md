# _lambda_4faec5f9e1de0d244e1a7c86b61b9810_::operator()

- ea: `0x18003e6d0`
- end: `0x18003e9c2`
- name: `_lambda_4faec5f9e1de0d244e1a7c86b61b9810_::operator()`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003df60`

## callees

- `0x18000b3bc`
- `0x18003aec8`
- `0x18003e6d0`
- `0x18003e9d0`
- `0x18003f0bc`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800f0260`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e861`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003e861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003e874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e824`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003e7bc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003e7bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e995`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e995`
- `RPCRT4!UuidFromStringW` at `0x18003e775`
- `RPCRT4!UuidFromStringW` at `0x18003e775`

## string_xrefs

- `0x18003e8fc`: `InterfaceRegistration::Create(strValidatedIid, interfaceName, strValidatedCLSID, _sourcePackage->GetCollectors(), &itf)`
- `0x18003e7c8`: `StringFromCLSID(iid, &tempIid)`
- `0x18003e95f`: `strValidatedIid.Initialize(tempIid.get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_4faec5f9e1de0d244e1a7c86b61b9810_::operator()(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  int v4; // eax
  HRESULT v5; // ebx
  UUID *v6; // rbx
  unsigned __int16 *StringRawBuffer; // rax
  RPC_STATUS v8; // eax
  const char *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rdx
  HSTRING *v14; // r14
  HSTRING v15; // rcx
  const WCHAR *v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  struct OSIntegration::DEH::InterfaceRegistration *v20; // rcx
  char *v21; // [rsp+28h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-38h] BYREF
  struct OSIntegration::DEH::InterfaceRegistration *v24; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v25; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+98h] [rbp+28h]

  v2 = *(_QWORD *)(a1 + 24);
  string = **(HSTRING **)(a1 + 16);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&string);
  v4 = OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(v3, *(_QWORD *)(a1 + 8), &string, v2);
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v21) = v4;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub::<lambda_4faec5f9e1de0d244e1a7c86b61b9810>::operator ()",
      "RetrieveAttribute(iidQuery, node, strIid)",
      v21,
      (int)string);
    return (unsigned int)v5;
  }
  v6 = *(UUID **)(a1 + 32);
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(**(HSTRING **)(a1 + 24), 0);
  v8 = UuidFromStringW(StringRawBuffer, v6);
  if ( v8 )
  {
    LODWORD(v21) = v8;
    return wil::details::in1diag5::Return_Win32(
             retaddr,
             (void *)0x23C,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
             "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub::<lambda_4faec5f9e1de0d244e1a7c86b61b9"
             "810>::operator ()",
             "UuidFromString(const_cast<RPC_WSTR>(strIid.GetRawBuffer(nullptr)), &iid)",
             v21,
             (unsigned int)string);
  }
  lpsz = 0;
  v5 = StringFromCLSID(*(const IID *const *)(a1 + 32), &lpsz);
  if ( v5 < 0 )
  {
    v10 = "StringFromCLSID(iid, &tempIid)";
    v11 = 575;
LABEL_30:
    LODWORD(v21) = v5;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub::<lambda_4faec5f9e1de0d244e1a7c86b61b9810>::operator ()",
      v10,
      v21,
      (int)string);
LABEL_31:
    if ( lpsz )
      CoTaskMemFree(lpsz);
    return (unsigned int)v5;
  }
  if ( !lpsz )
  {
    v5 = -2147467261;
LABEL_29:
    v10 = "strValidatedIid.Initialize(tempIid.get())";
    v11 = 576;
    goto LABEL_30;
  }
  string = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( lpsz[v13] );
  if ( v13 > 0xFFFFFFFF )
  {
    v5 = -2147024362;
  }
  else
  {
    v14 = *(HSTRING **)(a1 + 40);
    v5 = WindowsCreateString(lpsz, v13, &string);
    if ( v5 >= 0 )
    {
      v15 = *v14;
      *v14 = string;
      WindowsDeleteString(v15);
    }
  }
  if ( v5 < 0 )
    goto LABEL_29;
  v16 = off_1802E0600;
  do
    ++v12;
  while ( off_1802E0600[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    LODWORD(v12) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v16, v12, &hstringHeader, &v25);
  v17 = *(_QWORD *)(a1 + 48);
  string = **(HSTRING **)(a1 + 16);
  Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(&string);
  v5 = OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(v18, &v25, &string, v17);
  if ( v5 < 0 )
  {
    v10 = "RetrieveAttribute(interfaceNameQuery, node, interfaceName)";
    v11 = 579;
    goto LABEL_30;
  }
  v24 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  v19 = OSIntegration::DEH::InterfaceRegistration::Create(
          *(const struct Windows::Internal::String **)(a1 + 40),
          *(const struct Windows::Internal::String **)(a1 + 48),
          *(const struct Windows::Internal::String **)(a1 + 56),
          *(struct OSIntegration::DEH::Collectors **)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 808LL),
          &v24);
  v5 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v21) = v19;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\activationdeh\\activatableclasshelper.cpp",
      "OSIntegration::DEH::Internal::ActivatableClassHelper::ParseProxyStub::<lambda_4faec5f9e1de0d244e1a7c86b61b9810>::operator ()",
      "InterfaceRegistration::Create(strValidatedIid, interfaceName, strValidatedCLSID, _sourcePackage->GetCollectors(), &itf)",
      v21,
      (int)string);
    v20 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct OSIntegration::DEH::InterfaceRegistration *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_31;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return 0;
}

```

## disassembly

```asm
0x18003e6d0  mov     [rsp-28h+arg_8], rbx
0x18003e6d5  mov     [rsp-28h+arg_10], rsi
0x18003e6da  push    rbp
0x18003e6db  push    rdi
0x18003e6dc  push    r12
0x18003e6de  push    r14
0x18003e6e0  push    r15
0x18003e6e2  mov     rbp, rsp
0x18003e6e5  sub     rsp, 70h
0x18003e6e9  mov     rax, cs:__security_cookie
0x18003e6f0  xor     rax, rsp
0x18003e6f3  mov     [rbp+var_8], rax
0x18003e6f7  mov     rdi, rcx
0x18003e6fa  mov     rbx, [rcx+18h]
0x18003e6fe  mov     rax, [rcx+10h]
0x18003e702  mov     rcx, [rax]
0x18003e705  mov     [rbp+string], rcx
0x18003e709  lea     rcx, [rbp+string]
0x18003e70d  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003e712  mov     r9, rbx
0x18003e715  lea     r8, [rbp+string]
0x18003e719  mov     rdx, [rdi+8]
0x18003e71d  call    ?RetrieveAttribute@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEBVString@2Windows@@V?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEAV526@@Z; OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(Windows::Internal::String const &,Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String &)
0x18003e722  mov     ebx, eax
0x18003e724  xor     r15d, r15d
0x18003e727  test    eax, eax
0x18003e729  jns     short loc_18003E75C
0x18003e72b  mov     rcx, [rbp+28h]; this
0x18003e72f  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18003e733  lea     rax, aRetrieveattrib_3; "RetrieveAttribute(iidQuery, node, strIi"...
0x18003e73a  mov     [rsp+70h+var_50], rax; char *
0x18003e73f  lea     r9, aOsintegrationD_224; "OSIntegration::DEH::Internal::Activatab"...
0x18003e746  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e74d  mov     edx, 239h; void *
0x18003e752  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e757  jmp     loc_18003E99B
0x18003e75c  mov     rbx, [rdi+20h]
0x18003e760  mov     rcx, [rdi+18h]
0x18003e764  xor     edx, edx; length
0x18003e766  mov     rcx, [rcx]; string
0x18003e769  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e76f  mov     rdx, rbx; Uuid
0x18003e772  mov     rcx, rax; StringUuid
0x18003e775  call    cs:__imp_UuidFromStringW
0x18003e77b  test    eax, eax
0x18003e77d  jz      short loc_18003E7B0
0x18003e77f  mov     rcx, [rbp+28h]; this
0x18003e783  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18003e787  lea     rax, aUuidfromstring; "UuidFromString(const_cast<RPC_WSTR>(str"...
0x18003e78e  mov     [rsp+70h+var_50], rax; char *
0x18003e793  lea     r9, aOsintegrationD_224; "OSIntegration::DEH::Internal::Activatab"...
0x18003e79a  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e7a1  mov     edx, 23Ch; void *
0x18003e7a6  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x18003e7ab  jmp     loc_18003E99D
0x18003e7b0  mov     [rbp+lpsz], r15
0x18003e7b4  lea     rdx, [rbp+lpsz]; lplpsz
0x18003e7b8  mov     rcx, [rdi+20h]; rclsid
0x18003e7bc  call    cs:__imp_StringFromCLSID
0x18003e7c2  mov     ebx, eax
0x18003e7c4  test    eax, eax
0x18003e7c6  jns     short loc_18003E7D9
0x18003e7c8  lea     rax, aStringfromclsi_0; "StringFromCLSID(iid, &tempIid)"
0x18003e7cf  mov     edx, 23Fh
0x18003e7d4  jmp     loc_18003E96B
0x18003e7d9  mov     rcx, [rbp+lpsz]; sourceString
0x18003e7dd  test    rcx, rcx
0x18003e7e0  jz      loc_18003E95A
0x18003e7e6  mov     [rbp+string], r15
0x18003e7ea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003e7ee  mov     rdx, rsi
0x18003e7f1  inc     rdx; length
0x18003e7f4  cmp     [rcx+rdx*2], r15w
0x18003e7f9  jnz     short loc_18003E7F1
0x18003e7fb  mov     r12d, 0FFFFFFFFh
0x18003e801  cmp     rdx, r12
0x18003e804  ja      short loc_18003E82C
0x18003e806  mov     r14, [rdi+28h]
0x18003e80a  lea     r8, [rbp+string]; string
0x18003e80e  call    cs:__imp_WindowsCreateString
0x18003e814  mov     ebx, eax
0x18003e816  test    eax, eax
0x18003e818  js      short loc_18003E831
0x18003e81a  mov     rcx, [r14]; string
0x18003e81d  mov     rax, [rbp+string]
0x18003e821  mov     [r14], rax
0x18003e824  call    cs:__imp_WindowsDeleteString
0x18003e82a  jmp     short loc_18003E831
0x18003e82c  mov     ebx, 80070216h
0x18003e831  test    ebx, ebx
0x18003e833  js      loc_18003E95F
0x18003e839  mov     rbx, cs:off_1802E0600
0x18003e840  inc     rsi
0x18003e843  cmp     [rbx+rsi*2], r15w
0x18003e848  jnz     short loc_18003E840
0x18003e84a  cmp     rsi, r12
0x18003e84d  jbe     short loc_18003E867
0x18003e84f  mov     esi, r12d
0x18003e852  xor     r9d, r9d; lpArguments
0x18003e855  xor     r8d, r8d; nNumberOfArguments
0x18003e858  lea     edx, [r9+1]; dwExceptionFlags
0x18003e85c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003e861  call    cs:__imp_RaiseException
0x18003e867  lea     r9, [rbp+var_28]; string
0x18003e86b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003e86f  mov     edx, esi; length
0x18003e871  mov     rcx, rbx; sourceString
0x18003e874  call    cs:__imp_WindowsCreateStringReference
0x18003e87a  mov     rbx, [rdi+30h]
0x18003e87e  mov     rax, [rdi+10h]
0x18003e882  mov     rcx, [rax]
0x18003e885  mov     [rbp+string], rcx
0x18003e889  lea     rcx, [rbp+string]
0x18003e88d  call    ?InternalAddRef@?$ComPtr@VExtensionCatalogCollector@DEH@OSIntegration@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::ExtensionCatalogCollector>::InternalAddRef(void)
0x18003e892  mov     r9, rbx
0x18003e895  lea     r8, [rbp+string]
0x18003e899  lea     rdx, [rbp+var_28]
0x18003e89d  call    ?RetrieveAttribute@ActivatableClassHelper@Internal@DEH@OSIntegration@@AEAAJAEBVString@2Windows@@V?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@AEAV526@@Z; OSIntegration::DEH::Internal::ActivatableClassHelper::RetrieveAttribute(Windows::Internal::String const &,Microsoft::WRL::ComPtr<IXMLDOMNode>,Windows::Internal::String &)
0x18003e8a2  mov     ebx, eax
0x18003e8a4  test    eax, eax
0x18003e8a6  jns     short loc_18003E8B9
0x18003e8a8  lea     rax, aRetrieveattrib_0; "RetrieveAttribute(interfaceNameQuery, n"...
0x18003e8af  mov     edx, 243h
0x18003e8b4  jmp     loc_18003E96B
0x18003e8b9  mov     [rbp+var_30], r15
0x18003e8bd  lea     rcx, [rbp+var_30]
0x18003e8c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e8c6  mov     rax, [rdi]
0x18003e8c9  mov     r9, [rax+20h]
0x18003e8cd  lea     rax, [rbp+var_30]
0x18003e8d1  mov     [rsp+70h+var_50], rax; struct OSIntegration::DEH::InterfaceRegistration **
0x18003e8d6  mov     r9, [r9+328h]; struct OSIntegration::DEH::Collectors *
0x18003e8dd  mov     r8, [rdi+38h]; struct Windows::Internal::String *
0x18003e8e1  mov     rdx, [rdi+30h]; struct Windows::Internal::String *
0x18003e8e5  mov     rcx, [rdi+28h]; struct Windows::Internal::String *
0x18003e8e9  call    ?Create@InterfaceRegistration@DEH@OSIntegration@@SAJAEBVString@Internal@Windows@@00PEAVCollectors@23@PEAPEAU123@@Z; OSIntegration::DEH::InterfaceRegistration::Create(Windows::Internal::String const &,Windows::Internal::String const &,Windows::Internal::String const &,OSIntegration::DEH::Collectors *,OSIntegration::DEH::InterfaceRegistration * *)
0x18003e8ee  mov     ebx, eax
0x18003e8f0  test    eax, eax
0x18003e8f2  jns     short loc_18003E93D
0x18003e8f4  mov     rcx, [rbp+28h]; this
0x18003e8f8  mov     dword ptr [rsp+70h+var_48], eax; char *
0x18003e8fc  lea     rax, aInterfaceregis_3; "InterfaceRegistration::Create(strValida"...
0x18003e903  mov     [rsp+70h+var_50], rax; char *
0x18003e908  lea     r9, aOsintegrationD_224; "OSIntegration::DEH::Internal::Activatab"...
0x18003e90f  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e916  mov     edx, 246h; void *
0x18003e91b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e920  nop
0x18003e921  mov     rcx, [rbp+var_30]
0x18003e925  test    rcx, rcx
0x18003e928  jz      short loc_18003E93B
0x18003e92a  mov     [rbp+var_30], r15
0x18003e92e  mov     rax, [rcx]
0x18003e931  mov     rax, [rax+10h]
0x18003e935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e93a  nop
0x18003e93b  jmp     short loc_18003E98C
0x18003e93d  lea     rcx, [rbp+var_30]
0x18003e941  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003e946  nop
0x18003e947  mov     rcx, [rbp+lpsz]; pv
0x18003e94b  test    rcx, rcx
0x18003e94e  jz      short loc_18003E956
0x18003e950  call    cs:__imp_CoTaskMemFree
0x18003e956  xor     eax, eax
0x18003e958  jmp     short loc_18003E99D
0x18003e95a  mov     ebx, 80004003h
0x18003e95f  lea     rax, aStrvalidatedii; "strValidatedIid.Initialize(tempIid.get("...
0x18003e966  mov     edx, 240h; void *
0x18003e96b  mov     dword ptr [rsp+70h+var_48], ebx; char *
0x18003e96f  mov     [rsp+70h+var_50], rax; char *
0x18003e974  lea     r9, aOsintegrationD_224; "OSIntegration::DEH::Internal::Activatab"...
0x18003e97b  lea     r8, aOnecoreAdminAp_130; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003e982  mov     rcx, [rbp+28h]; this
0x18003e986  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003e98b  nop
0x18003e98c  mov     rcx, [rbp+lpsz]; pv
0x18003e990  test    rcx, rcx
0x18003e993  jz      short loc_18003E99B
0x18003e995  call    cs:__imp_CoTaskMemFree
0x18003e99b  mov     eax, ebx
0x18003e99d  mov     rcx, [rbp+var_8]
0x18003e9a1  xor     rcx, rsp; StackCookie
0x18003e9a4  call    __security_check_cookie
0x18003e9a9  lea     r11, [rsp+70h+var_s0]
0x18003e9ae  mov     rbx, [r11+38h]
0x18003e9b2  mov     rsi, [r11+40h]
0x18003e9b6  mov     rsp, r11
0x18003e9b9  pop     r15
0x18003e9bb  pop     r14
0x18003e9bd  pop     r12
0x18003e9bf  pop     rdi
0x18003e9c0  pop     rbp
0x18003e9c1  retn
```
