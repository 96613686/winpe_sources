# Windows::Internal::Storage::Cloud::Common::GetWebAccountType(Windows::Security::Credentials::IWebAccount *)

- ea: `0x1800fce6c`
- end: `0x1800fcff5`
- name: `?GetWebAccountType@Common@Cloud@Storage@Internal@Windows@@YA?AW4UserAccountType@12345@PEAUIWebAccount@Credentials@Security@5@@Z`
- size: `393`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e1d4c`
- `0x1800e1f70`
- `0x1801c1e6c`

## callees

- `0x18000dfe4`
- `0x18000e8d0`
- `0x180016cf4`
- `0x18003f11c`
- `0x180065614`
- `0x1800d9764`
- `0x1800fce6c`
- `0x1800fcffc`
- `0x180128e9c`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcf76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcf9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcf76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fcf9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcf54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcf54`

## string_xrefs

- `0x1800fced7`: `onecoreuap\shell\cloudstore\common\src\webaccountutils.cpp`
- `0x1800fcf33`: `onecoreuap\shell\cloudstore\common\src\webaccountutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::Storage::Cloud::Common::GetWebAccountType(__int64 *a1)
{
  __int64 v3; // rax
  int v4; // eax
  __int64 v5; // rax
  int v6; // eax
  const WCHAR *StringRawBuffer; // rdi
  unsigned int v8; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  HSTRING *p_string; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+70h] [rbp+20h] BYREF
  __int64 v15; // [rsp+78h] [rbp+28h] BYREF
  __int64 *v16; // [rsp+80h] [rbp+30h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssets>::GetImpl'::`2'::impl) )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl'::`2'::impl);
  if ( !a1 )
    return 1;
  v15 = 0;
  v3 = *a1;
  p_string = (HSTRING *)&v15;
  v11 = 0;
  v12 = 1;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v3 + 48))(a1, &v11);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\webaccountutils.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
  wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_string);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccountProvider2>(
    &v15,
    &v16);
  string = 0;
  v5 = *v16;
  p_string = &string;
  v11 = 0;
  v12 = 1;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v5 + 56))(v16, &v11);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\webaccountutils.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v8 = 2;
  if ( CompareStringOrdinal(StringRawBuffer, -1, (LPCWCH)"c\x00o\x00n\x00s\x00u\x00m\x00e\x00r\x00s", -1, 1) == 2 )
    goto LABEL_12;
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"organizations", -1, 1) == 2 )
  {
    v8 = 3;
LABEL_12:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v16);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v15);
    return v8;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v16);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v15);
  return 0;
}

```

## disassembly

```asm
0x1800fce6c  push    rbp
0x1800fce6e  push    rbx
0x1800fce6f  push    rdi
0x1800fce70  mov     rbp, rsp
0x1800fce73  sub     rsp, 50h
0x1800fce77  mov     rbx, rcx
0x1800fce7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AadAssets@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssets@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets> `wil::Feature<__WilFeatureTraits_Feature_AadAssets>::GetImpl(void)'::`2'::impl
0x1800fce81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssets@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssets>::__private_IsEnabled(void)
0x1800fce86  xor     edi, edi
0x1800fce88  test    al, al
0x1800fce8a  jnz     short loc_1800FCE98
0x1800fce8c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AadAssetsRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore> `wil::Feature<__WilFeatureTraits_Feature_AadAssetsRestore>::GetImpl(void)'::`2'::impl
0x1800fce93  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AadAssetsRestore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AadAssetsRestore>::__private_IsEnabled(void)
0x1800fce98  test    rbx, rbx
0x1800fce9b  jnz     short loc_1800FCEA5
0x1800fce9d  lea     eax, [rbx+1]
0x1800fcea0  jmp     loc_1800FCFED
0x1800fcea5  mov     [rbp+arg_8], rdi
0x1800fcea9  mov     rax, [rbx]
0x1800fceac  lea     rcx, [rbp+arg_8]
0x1800fceb0  mov     [rbp+var_20], rcx
0x1800fceb4  mov     [rbp+var_18], rdi
0x1800fceb8  mov     [rbp+var_10], 1
0x1800fcebc  lea     rdx, [rbp+var_18]
0x1800fcec0  mov     rcx, rbx
0x1800fcec3  mov     rax, [rax+30h]
0x1800fcec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcecc  mov     rcx, [rbp+18h]; this
0x1800fced0  test    eax, eax
0x1800fced2  jns     short loc_1800FCEE9
0x1800fced4  mov     r9d, eax; char *
0x1800fced7  lea     r8, aOnecoreuapShel_93; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800fcede  mov     edx, 44h ; 'D'; void *
0x1800fcee3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fcee9  lea     rcx, [rbp+var_20]
0x1800fceed  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800fcef2  lea     rdx, [rbp+arg_10]
0x1800fcef6  lea     rcx, [rbp+arg_8]
0x1800fcefa  call    ??$query@UIWebAccountProvider2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccountProvider@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccountProvider2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccountProvider2>(void)
0x1800fceff  nop
0x1800fcf00  mov     [rbp+string], rdi
0x1800fcf04  mov     rcx, [rbp+arg_10]
0x1800fcf08  mov     rax, [rcx]
0x1800fcf0b  lea     rdx, [rbp+string]
0x1800fcf0f  mov     [rbp+var_20], rdx
0x1800fcf13  mov     [rbp+var_18], rdi
0x1800fcf17  mov     [rbp+var_10], 1
0x1800fcf1b  lea     rdx, [rbp+var_18]
0x1800fcf1f  mov     rax, [rax+38h]
0x1800fcf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fcf28  mov     rcx, [rbp+18h]; this
0x1800fcf2c  test    eax, eax
0x1800fcf2e  jns     short loc_1800FCF45
0x1800fcf30  mov     r9d, eax; char *
0x1800fcf33  lea     r8, aOnecoreuapShel_93; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800fcf3a  mov     edx, 49h ; 'I'; void *
0x1800fcf3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fcf45  lea     rcx, [rbp+var_20]
0x1800fcf49  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800fcf4e  xor     edx, edx; length
0x1800fcf50  mov     rcx, [rbp+string]; string
0x1800fcf54  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fcf5a  mov     rdi, rax
0x1800fcf5d  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800fcf65  or      r9d, 0FFFFFFFFh; cchCount2
0x1800fcf69  lea     r8, aAbcdefghijklmn_0+40h; "c\x00o\x00n\x00s\x00u\x00m\x00e\x00r"...
0x1800fcf70  or      edx, r9d; cchCount1
0x1800fcf73  mov     rcx, rax; lpString1
0x1800fcf76  call    cs:__imp_CompareStringOrdinal
0x1800fcf7c  mov     ebx, 2
0x1800fcf81  cmp     eax, ebx
0x1800fcf83  jz      short loc_1800FCFAD
0x1800fcf85  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800fcf8d  or      r9d, 0FFFFFFFFh; cchCount2
0x1800fcf91  lea     r8, aOrganizations; "organizations"
0x1800fcf98  or      edx, r9d; cchCount1
0x1800fcf9b  mov     rcx, rdi; lpString1
0x1800fcf9e  call    cs:__imp_CompareStringOrdinal
0x1800fcfa4  cmp     eax, ebx
0x1800fcfa6  jnz     short loc_1800FCFCE
0x1800fcfa8  mov     ebx, 3
0x1800fcfad  lea     rcx, [rbp+string]
0x1800fcfb1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800fcfb6  nop
0x1800fcfb7  lea     rcx, [rbp+arg_10]
0x1800fcfbb  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800fcfc0  nop
0x1800fcfc1  lea     rcx, [rbp+arg_8]
0x1800fcfc5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800fcfca  mov     eax, ebx
0x1800fcfcc  jmp     short loc_1800FCFED
0x1800fcfce  lea     rcx, [rbp+string]
0x1800fcfd2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800fcfd7  nop
0x1800fcfd8  lea     rcx, [rbp+arg_10]
0x1800fcfdc  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800fcfe1  nop
0x1800fcfe2  lea     rcx, [rbp+arg_8]
0x1800fcfe6  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800fcfeb  xor     eax, eax
0x1800fcfed  add     rsp, 50h
0x1800fcff1  pop     rdi
0x1800fcff2  pop     rbx
0x1800fcff3  pop     rbp
0x1800fcff4  retn
```
