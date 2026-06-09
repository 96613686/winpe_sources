# SystemSettings::PenSettings::IsSearchAumId(ushort const *)

- ea: `0x180054424`
- end: `0x180054603`
- name: `?IsSearchAumId@PenSettings@SystemSettings@@YA_NPEBG@Z`
- size: `479`
- prototype: `bool __fastcall(PCNZWCH lpString1, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054048`

## callees

- `0x1800111f0`
- `0x180031788`
- `0x1800318e0`
- `0x180051110`
- `0x1800532cc`
- `0x180053398`
- `0x180054424`
- `0x18005493c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800544b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054546`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800545d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800544b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180054546`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800545d3`

## string_xrefs

- `0x1800544e0`: `com.microsoft.windows.app.search`
- `0x180054455`: `com.microsoft.windows.app.searchMI`
- `0x18005456d`: `com.microsoft.windows.app.searchbox`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall SystemSettings::PenSettings::IsSearchAumId(PCNZWCH lpString1, const unsigned __int16 *a2)
{
  char v3; // di
  winrt::hstring *v4; // rax
  const WCHAR *lpString2; // rax
  int v6; // ebx
  winrt::hstring *v7; // rax
  const WCHAR *v8; // rax
  int v9; // ebx
  winrt::hstring *v10; // rax
  const WCHAR *v11; // rax
  int v12; // ebx
  _BYTE v14[8]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v15[5]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+40h] BYREF
  char v17; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_53852258>::GetImpl'::`2'::impl,
                          a2) )
  {
    v15[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v17, L"com.microsoft.windows.app.searchMI");
    winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(
      (const struct winrt::param::hstring *)&v16,
      (const enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *)v15);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
    if ( v16 )
    {
      v4 = (winrt::hstring *)winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(
                               &v16,
                               v14);
      lpString2 = winrt::hstring::c_str(v4);
      v6 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v14);
      if ( v6 == 2 )
        goto LABEL_10;
    }
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v16);
  }
  v15[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v17, L"com.microsoft.windows.app.search");
  winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(
    (const struct winrt::param::hstring *)&v16,
    (const enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *)v15);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
  if ( !v16
    || (v7 = (winrt::hstring *)winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(
                                 &v16,
                                 v14),
        v8 = winrt::hstring::c_str(v7),
        v9 = CompareStringW(0x7Fu, 1u, lpString1, -1, v8, -1),
        winrt::handle_type<winrt::impl::hstring_traits>::close(v14),
        v9 != 2) )
  {
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v16);
    v15[0] = *(_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v17, L"com.microsoft.windows.app.searchbox");
    winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(
      (const struct winrt::param::hstring *)&v16,
      (const enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *)v15);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
    if ( !v16
      || (v10 = (winrt::hstring *)winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(
                                    &v16,
                                    v14),
          v11 = winrt::hstring::c_str(v10),
          v12 = CompareStringW(0x7Fu, 1u, lpString1, -1, v11, -1),
          winrt::handle_type<winrt::impl::hstring_traits>::close(v14),
          v12 != 2) )
    {
      v3 = 0;
    }
  }
LABEL_10:
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v16);
  return v3;
}

```

## disassembly

```asm
0x180054424  push    rbp
0x180054426  push    rbx
0x180054427  push    rsi
0x180054428  push    rdi
0x180054429  push    r15
0x18005442b  mov     rbp, rsp
0x18005442e  sub     rsp, 60h
0x180054432  mov     rsi, rcx
0x180054435  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53852258@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53852258@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258> `wil::Feature<__WilFeatureTraits_Feature_53852258>::GetImpl(void)'::`2'::impl
0x18005443c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53852258@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258>::__private_IsEnabled(void)
0x180054441  mov     edi, 1
0x180054446  or      r15d, 0FFFFFFFFh
0x18005444a  test    al, al
0x18005444c  jz      loc_1800544DD
0x180054452  mov     [rbp+arg_8], edi
0x180054455  lea     rdx, aComMicrosoftWi_1; "com.microsoft.windows.app.searchMI"
0x18005445c  lea     rcx, [rbp+arg_18]; this
0x180054460  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180054465  nop
0x180054466  mov     rax, [rax]
0x180054469  mov     [rbp+var_28], rax
0x18005446d  lea     r8, [rbp+arg_8]
0x180054471  lea     rdx, [rbp+var_28]; enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *
0x180054475  lea     rcx, [rbp+arg_10]; struct winrt::param::hstring *
0x180054479  call    ?Find@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@AEBW4AppExtensionOptions@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(winrt::param::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions const &)
0x18005447e  nop
0x18005447f  lea     rcx, [rbp+arg_18]
0x180054483  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180054488  cmp     [rbp+arg_10], 0
0x18005448d  jz      short loc_1800544D4
0x18005448f  lea     rdx, [rbp+var_30]
0x180054493  lea     rcx, [rbp+arg_10]
0x180054497  call    ?ApplicationUserModelId@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension@UIAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(void)
0x18005449c  mov     rcx, rax; this
0x18005449f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800544a4  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x1800544a9  mov     [rsp+60h+lpString2], rax; lpString2
0x1800544ae  mov     r9d, r15d; cchCount1
0x1800544b1  mov     r8, rsi; lpString1
0x1800544b4  mov     edx, edi; dwCmpFlags
0x1800544b6  lea     ecx, [rdi+7Eh]; Locale
0x1800544b9  call    cs:__imp_CompareStringW
0x1800544bf  mov     ebx, eax
0x1800544c1  lea     rcx, [rbp+var_30]
0x1800544c5  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800544ca  cmp     ebx, 2
0x1800544cd  jnz     short loc_1800544D4
0x1800544cf  jmp     loc_1800545EC
0x1800544d4  lea     rcx, [rbp+arg_10]; this
0x1800544d8  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800544dd  mov     [rbp+arg_8], edi
0x1800544e0  lea     rdx, aComMicrosoftWi_2; "com.microsoft.windows.app.search"
0x1800544e7  lea     rcx, [rbp+arg_18]; this
0x1800544eb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800544f0  nop
0x1800544f1  mov     rax, [rax]
0x1800544f4  mov     [rbp+var_28], rax
0x1800544f8  lea     r8, [rbp+arg_8]
0x1800544fc  lea     rdx, [rbp+var_28]; enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *
0x180054500  lea     rcx, [rbp+arg_10]; struct winrt::param::hstring *
0x180054504  call    ?Find@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@AEBW4AppExtensionOptions@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(winrt::param::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions const &)
0x180054509  nop
0x18005450a  lea     rcx, [rbp+arg_18]
0x18005450e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180054513  cmp     [rbp+arg_10], 0
0x180054518  jz      short loc_180054561
0x18005451a  lea     rdx, [rbp+var_30]
0x18005451e  lea     rcx, [rbp+arg_10]
0x180054522  call    ?ApplicationUserModelId@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension@UIAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(void)
0x180054527  mov     rcx, rax; this
0x18005452a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18005452f  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x180054534  mov     [rsp+60h+lpString2], rax; lpString2
0x180054539  mov     r9d, r15d; cchCount1
0x18005453c  mov     r8, rsi; lpString1
0x18005453f  mov     edx, edi; dwCmpFlags
0x180054541  mov     ecx, 7Fh; Locale
0x180054546  call    cs:__imp_CompareStringW
0x18005454c  mov     ebx, eax
0x18005454e  lea     rcx, [rbp+var_30]
0x180054552  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180054557  cmp     ebx, 2
0x18005455a  jnz     short loc_180054561
0x18005455c  jmp     loc_1800545EC
0x180054561  lea     rcx, [rbp+arg_10]; this
0x180054565  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18005456a  mov     [rbp+arg_8], edi
0x18005456d  lea     rdx, aComMicrosoftWi_0; "com.microsoft.windows.app.searchbox"
0x180054574  lea     rcx, [rbp+arg_18]; this
0x180054578  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18005457d  nop
0x18005457e  mov     rax, [rax]
0x180054581  mov     [rbp+var_28], rax
0x180054585  lea     r8, [rbp+arg_8]
0x180054589  lea     rdx, [rbp+var_28]; enum winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions *
0x18005458d  lea     rcx, [rbp+arg_10]; struct winrt::param::hstring *
0x180054591  call    ?Find@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@AEBW4AppExtensionOptions@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::Find(winrt::param::hstring const &,winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtensionOptions const &)
0x180054596  nop
0x180054597  lea     rcx, [rbp+arg_18]
0x18005459b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800545a0  cmp     [rbp+arg_10], 0
0x1800545a5  jz      short loc_1800545E9
0x1800545a7  lea     rdx, [rbp+var_30]
0x1800545ab  lea     rcx, [rbp+arg_10]
0x1800545af  call    ?ApplicationUserModelId@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension@UIAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IAppExtension<winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtension>::ApplicationUserModelId(void)
0x1800545b4  mov     rcx, rax; this
0x1800545b7  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800545bc  mov     [rsp+60h+cchCount2], r15d; cchCount2
0x1800545c1  mov     [rsp+60h+lpString2], rax; lpString2
0x1800545c6  mov     r9d, r15d; cchCount1
0x1800545c9  mov     r8, rsi; lpString1
0x1800545cc  mov     edx, edi; dwCmpFlags
0x1800545ce  mov     ecx, 7Fh; Locale
0x1800545d3  call    cs:__imp_CompareStringW
0x1800545d9  mov     ebx, eax
0x1800545db  lea     rcx, [rbp+var_30]
0x1800545df  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800545e4  cmp     ebx, 2
0x1800545e7  jz      short loc_1800545EC
0x1800545e9  xor     dil, dil
0x1800545ec  lea     rcx, [rbp+arg_10]; this
0x1800545f0  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800545f5  mov     al, dil
0x1800545f8  add     rsp, 60h
0x1800545fc  pop     r15
0x1800545fe  pop     rdi
0x1800545ff  pop     rsi
0x180054600  pop     rbx
0x180054601  pop     rbp
0x180054602  retn
```
