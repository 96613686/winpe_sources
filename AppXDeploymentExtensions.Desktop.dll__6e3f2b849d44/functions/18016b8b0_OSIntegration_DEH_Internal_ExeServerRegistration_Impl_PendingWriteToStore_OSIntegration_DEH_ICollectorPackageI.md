# OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore(OSIntegration::DEH::ICollectorPackageInformation const *,IActivationCatalogContext *)

- ea: `0x18016b8b0`
- end: `0x18016bb80`
- name: `?PendingWriteToStore@ExeServerRegistration_Impl@Internal@DEH@OSIntegration@@UEAAJPEBUICollectorPackageInformation@34@PEAUIActivationCatalogContext@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *, struct IActivationCatalogContext *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006970`
- `0x180047fe4`
- `0x1800502a4`
- `0x18006a4c8`
- `0x1800aed10`
- `0x1800eb890`
- `0x180142a98`
- `0x1801480f0`
- `0x18016b8b0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016b941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016b95b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18016b95b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016bb3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016baf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016bb3f`

## string_xrefs

- `0x18016bad1`: `incomingPackage->GetMainPackageFamilyMoniker(executionPackageFamily)`
- `0x18016b983`: `CalculateServerPermissions(strPackageSid)`
- `0x18016ba99`: `registrationStoreContext->CreateServerEntry( packageMoniker.Get(), _serverName.Get(), _properties)`
- `0x18016b99e`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18016ba4b`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18016bae3`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore(
        OSIntegration::DEH::Internal::ExeServerRegistration_Impl *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2,
        struct IActivationCatalogContext *a3)
{
  const unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // rax
  char v8; // r13
  const WCHAR *StringRawBuffer; // rax
  int v10; // ebx
  const char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, char *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  const char *v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  const char *v23; // rax
  HSTRING *v24; // rax
  int v25; // eax
  char *v27; // [rsp+28h] [rbp-61h]
  UINT32 length[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v29; // [rsp+38h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-41h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string[4]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v34[4]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(const struct OSIntegration::DEH::ICollectorPackageInformation *))a2)(a2);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v34, v6);
  v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 32LL))(a2);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v7);
  v8 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 40LL))(a2);
  v31 = 0;
  length[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string[0], length);
  WindowsCreateStringReference(StringRawBuffer, length[0], &hstringHeader, &v31);
  v10 = (*(__int64 (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *, HSTRING *))(*(_QWORD *)this + 328LL))(
          this,
          &v31);
  if ( v10 >= 0 )
  {
    v13 = *((_QWORD *)this + 28);
    v14 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 72LL);
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease((char *)this + 216);
    v10 = v14(v13, (char *)this + 216);
    if ( v10 < 0 )
    {
      v11 = "_attributes->GetView(&(_properties.CustomAttributes.MapView))";
      v12 = 776;
      goto LABEL_3;
    }
    v29 = 0;
    v15 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>::As<Windows::Foundation::Collections::IIterable<HSTRING__ *>>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 31,
            (__int64)&v29);
    v10 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v27) = v15;
      v16 = 779;
      v17 = "_classNames.As(&classNamesIterable)";
LABEL_10:
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
        "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
        v17,
        v27,
        length[0]);
LABEL_21:
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v29);
      return (unsigned int)v10;
    }
    v18 = MultiString::InitializeFromStringArray((HSTRING *)this + 19, v29);
    v10 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v27) = v18;
      v16 = 782;
      v17 = "_properties.ActivatableClasses.InitializeFromStringArray(classNamesIterable.Get())";
      goto LABEL_10;
    }
    v19 = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, _QWORD, _QWORD, char *))(*(_QWORD *)a3 + 256LL))(
            a3,
            v34[0],
            *((_QWORD *)this + 29),
            (char *)this + 40);
    v10 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v27) = v19;
      v16 = 786;
      v17 = "registrationStoreContext->CreateServerEntry( packageMoniker.Get(), _serverName.Get(), _properties)";
      goto LABEL_10;
    }
    if ( v8 )
    {
      v20 = *(_QWORD *)a2;
      *(_QWORD *)length = 0;
      v21 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *, UINT32 *))(v20 + 64))(
              a2,
              length);
      v10 = v21;
      if ( v21 < 0 )
      {
        LODWORD(v27) = v21;
        v22 = 793;
        v23 = "incomingPackage->GetMainPackageFamilyMoniker(executionPackageFamily)";
LABEL_16:
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
          "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
          v23,
          v27,
          length[0]);
        WindowsDeleteString(*(HSTRING *)length);
        *(_QWORD *)length = 0;
        goto LABEL_21;
      }
      v24 = (HSTRING *)OpaqueString::OpaqueString(&newString, (const struct OpaqueString *)length);
      v25 = SetRegistrationProperty<OpaqueString,OpaqueString>((__int64)this + 112, v24);
      v10 = v25;
      if ( v25 < 0 )
      {
        LODWORD(v27) = v25;
        v22 = 795;
        v23 = "SetRegistrationProperty( _properties.ExecutionPackageFamily, executionPackageFamily)";
        goto LABEL_16;
      }
      WindowsDeleteString(*(HSTRING *)length);
    }
    v10 = 0;
    goto LABEL_21;
  }
  v11 = "CalculateServerPermissions(strPackageSid)";
  v12 = 774;
LABEL_3:
  LODWORD(v27) = v10;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
    "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
    v11,
    v27,
    length[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18016b8b0  mov     [rsp-8+arg_18], rbx
0x18016b8b5  push    rbp
0x18016b8b6  push    rsi
0x18016b8b7  push    rdi
0x18016b8b8  push    r12
0x18016b8ba  push    r13
0x18016b8bc  push    r14
0x18016b8be  push    r15
0x18016b8c0  lea     rbp, [rsp-27h]
0x18016b8c5  sub     rsp, 0B0h
0x18016b8cc  mov     rax, cs:__security_cookie
0x18016b8d3  xor     rax, rsp
0x18016b8d6  mov     [rbp+57h+var_38], rax
0x18016b8da  mov     rax, [rdx]
0x18016b8dd  mov     r14, rcx
0x18016b8e0  mov     rcx, rdx
0x18016b8e3  mov     r12, r8
0x18016b8e6  mov     r15, rdx
0x18016b8e9  mov     rax, [rax]
0x18016b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b8f1  mov     rdx, rax; unsigned __int16 *
0x18016b8f4  lea     rcx, [rbp+57h+var_58]; this
0x18016b8f8  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18016b8fd  mov     rax, [r15]
0x18016b900  mov     rcx, r15
0x18016b903  mov     rax, [rax+20h]
0x18016b907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b90c  mov     rdx, rax; unsigned __int16 *
0x18016b90f  lea     rcx, [rbp+57h+string]; this
0x18016b913  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18016b918  mov     rax, [r15]
0x18016b91b  mov     rcx, r15
0x18016b91e  mov     rax, [rax+28h]
0x18016b922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b927  mov     rcx, [rbp+57h+string]; string
0x18016b92b  lea     rdx, [rbp+57h+length]; length
0x18016b92f  mov     r13b, al
0x18016b932  mov     [rbp+57h+var_98], 0
0x18016b93a  mov     [rbp+57h+length], 0
0x18016b941  call    cs:__imp_WindowsGetStringRawBuffer
0x18016b948  nop     dword ptr [rax+rax+00h]
0x18016b94d  mov     edx, [rbp+57h+length]; length
0x18016b950  lea     r9, [rbp+57h+var_98]; string
0x18016b954  mov     rcx, rax; sourceString
0x18016b957  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18016b95b  call    cs:__imp_WindowsCreateStringReference
0x18016b962  nop     dword ptr [rax+rax+00h]
0x18016b967  mov     rcx, [r14]
0x18016b96a  lea     rdx, [rbp+57h+var_98]
0x18016b96e  mov     rax, [rcx+148h]
0x18016b975  mov     rcx, r14
0x18016b978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b97d  mov     ebx, eax
0x18016b97f  test    eax, eax
0x18016b981  jns     short loc_18016B9B4
0x18016b983  lea     rax, aCalculateserve; "CalculateServerPermissions(strPackageSi"...
0x18016b98a  mov     edx, 306h; void *
0x18016b98f  mov     rcx, [rbp+5Fh]; this
0x18016b993  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016b99a  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x18016b99e  lea     r9, aOsintegrationD_187; "OSIntegration::DEH::Internal::ExeServer"...
0x18016b9a5  mov     [rsp+0E0h+var_C0], rax; char *
0x18016b9aa  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016b9af  jmp     loc_18016BB56
0x18016b9b4  mov     rsi, [r14+0E0h]
0x18016b9bb  lea     rbx, [r14+0D8h]
0x18016b9c2  mov     rcx, rbx
0x18016b9c5  mov     rax, [rsi]
0x18016b9c8  mov     rdi, [rax+48h]
0x18016b9cc  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18016b9d1  mov     rdx, rbx
0x18016b9d4  mov     rcx, rsi
0x18016b9d7  mov     rax, rdi
0x18016b9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b9df  xor     edi, edi
0x18016b9e1  mov     ebx, eax
0x18016b9e3  test    eax, eax
0x18016b9e5  jns     short loc_18016B9F5
0x18016b9e7  lea     rax, aAttributesGetv_0; "_attributes->GetView(&(_properties.Cust"...
0x18016b9ee  mov     edx, 308h
0x18016b9f3  jmp     short loc_18016B98F
0x18016b9f5  lea     rcx, [r14+0F8h]
0x18016b9fc  mov     [rbp+57h+var_A8], rdi
0x18016ba00  lea     rdx, [rbp+57h+var_A8]
0x18016ba04  call    ??$As@U?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@?$ComPtr@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>::As<Windows::Foundation::Collections::IIterable<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<HSTRING__ *>>>)
0x18016ba09  mov     ebx, eax
0x18016ba0b  test    eax, eax
0x18016ba0d  jns     short loc_18016BA21
0x18016ba0f  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18016ba13  mov     edx, 30Bh
0x18016ba18  lea     rax, aClassnamesAsCl; "_classNames.As(&classNamesIterable)"
0x18016ba1f  jmp     short loc_18016BA47
0x18016ba21  mov     rdx, [rbp+57h+var_A8]
0x18016ba25  lea     rcx, [r14+98h]; string
0x18016ba2c  call    ?InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; MultiString::InitializeFromStringArray(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)
0x18016ba31  mov     ebx, eax
0x18016ba33  test    eax, eax
0x18016ba35  jns     short loc_18016BA68
0x18016ba37  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18016ba3b  mov     edx, 30Eh; void *
0x18016ba40  lea     rax, aPropertiesActi; "_properties.ActivatableClasses.Initiali"...
0x18016ba47  mov     rcx, [rbp+5Fh]; this
0x18016ba4b  lea     r9, aOsintegrationD_187; "OSIntegration::DEH::Internal::ExeServer"...
0x18016ba52  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016ba59  mov     [rsp+0E0h+var_C0], rax; char *
0x18016ba5e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016ba63  jmp     loc_18016BB4D
0x18016ba68  mov     rax, [r12]
0x18016ba6c  lea     r9, [r14+28h]
0x18016ba70  mov     r8, [r14+0E8h]
0x18016ba77  mov     rcx, r12
0x18016ba7a  mov     rdx, [rbp+57h+var_58]
0x18016ba7e  mov     rax, [rax+100h]
0x18016ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ba8a  mov     ebx, eax
0x18016ba8c  test    eax, eax
0x18016ba8e  jns     short loc_18016BAA2
0x18016ba90  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18016ba94  mov     edx, 312h
0x18016ba99  lea     rax, aRegistrationst_15; "registrationStoreContext->CreateServerE"...
0x18016baa0  jmp     short loc_18016BA47
0x18016baa2  test    r13b, r13b
0x18016baa5  jz      loc_18016BB4B
0x18016baab  mov     rax, [r15]
0x18016baae  lea     rdx, [rbp+57h+length]
0x18016bab2  mov     rcx, r15
0x18016bab5  mov     qword ptr [rbp+57h+length], rdi
0x18016bab9  mov     rax, [rax+40h]
0x18016babd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016bac2  mov     ebx, eax
0x18016bac4  test    eax, eax
0x18016bac6  jns     short loc_18016BB0A
0x18016bac8  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18016bacc  mov     edx, 319h; void *
0x18016bad1  lea     rax, aIncomingpackag; "incomingPackage->GetMainPackageFamilyMo"...
0x18016bad8  mov     rcx, [rbp+5Fh]; this
0x18016badc  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18016bae3  lea     r9, aOsintegrationD_187; "OSIntegration::DEH::Internal::ExeServer"...
0x18016baea  mov     [rsp+0E0h+var_C0], rax; char *
0x18016baef  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18016baf4  mov     rcx, qword ptr [rbp+57h+length]; string
0x18016baf8  call    cs:__imp_WindowsDeleteString
0x18016baff  nop     dword ptr [rax+rax+00h]
0x18016bb04  mov     qword ptr [rbp+57h+length], rdi
0x18016bb08  jmp     short loc_18016BB4D
0x18016bb0a  lea     rdx, [rbp+57h+length]; struct OpaqueString *
0x18016bb0e  lea     rcx, [rbp+57h+newString]; newString
0x18016bb12  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x18016bb17  mov     rdx, rax
0x18016bb1a  lea     rcx, [r14+70h]
0x18016bb1e  call    ??$SetRegistrationProperty@VOpaqueString@@V1@@@YAJAEAU?$Optional@VOpaqueString@@@@VOpaqueString@@@Z; SetRegistrationProperty<OpaqueString,OpaqueString>(Optional<OpaqueString> &,OpaqueString)
0x18016bb23  mov     ebx, eax
0x18016bb25  test    eax, eax
0x18016bb27  jns     short loc_18016BB3B
0x18016bb29  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18016bb2d  mov     edx, 31Bh
0x18016bb32  lea     rax, aSetregistratio_22; "SetRegistrationProperty( _properties.Ex"...
0x18016bb39  jmp     short loc_18016BAD8
0x18016bb3b  mov     rcx, qword ptr [rbp+57h+length]; string
0x18016bb3f  call    cs:__imp_WindowsDeleteString
0x18016bb46  nop     dword ptr [rax+rax+00h]
0x18016bb4b  mov     ebx, edi
0x18016bb4d  lea     rcx, [rbp+57h+var_A8]
0x18016bb51  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18016bb56  mov     eax, ebx
0x18016bb58  mov     rcx, [rbp+57h+var_38]
0x18016bb5c  xor     rcx, rsp; StackCookie
0x18016bb5f  call    __security_check_cookie
0x18016bb64  mov     rbx, [rsp+0E0h+arg_18]
0x18016bb6c  add     rsp, 0B0h
0x18016bb73  pop     r15
0x18016bb75  pop     r14
0x18016bb77  pop     r13
0x18016bb79  pop     r12
0x18016bb7b  pop     rdi
0x18016bb7c  pop     rsi
0x18016bb7d  pop     rbp
0x18016bb7e  retn
```
