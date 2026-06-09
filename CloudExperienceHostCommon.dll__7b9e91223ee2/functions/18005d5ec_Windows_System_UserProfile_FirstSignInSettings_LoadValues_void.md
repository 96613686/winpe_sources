# Windows::System::UserProfile::FirstSignInSettings::LoadValues(void)

- ea: `0x18005d5ec`
- end: `0x18005d817`
- name: `?LoadValues@FirstSignInSettings@UserProfile@System@Windows@@AEAAXXZ`
- size: `555`
- prototype: `void __fastcall(Windows::System::UserProfile::FirstSignInSettings *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005f4a8`

## callees

- `0x180003a70`
- `0x18000fa5c`
- `0x180010c8c`
- `0x1800128a4`
- `0x18001475c`
- `0x18001a540`
- `0x180059ecc`
- `0x18005c930`
- `0x18005d510`
- `0x18005d5ec`
- `0x18005dc30`
- `0x18005e170`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d6b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d6ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d755`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d6b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d6ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d755`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005d674`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005d674`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::System::UserProfile::FirstSignInSettings::LoadValues(
        Windows::System::UserProfile::FirstSignInSettings *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rbx
  int ActivationFactory; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  int View; // eax
  int phkResult; // [rsp+20h] [rbp-29h]
  int phkResulta; // [rsp+20h] [rbp-29h]
  __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  HKEY v16; // [rsp+38h] [rbp-11h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-9h] BYREF
  HKEY v18; // [rsp+48h] [rbp-1h] BYREF
  HKEY v19; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v21; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v2 = (_QWORD *)((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease((char *)this + 80);
  v5 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
         v4,
         v3,
         v2);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\firstsigninsettings.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
  v15 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.PropertyValue",
    0x21u,
    0x20u);
  v6 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v15);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\firstsigninsettings.cpp",
      (const char *)(unsigned int)ActivationFactory,
      phkResult);
  v19 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\AppSettings",
          0,
          0x101u,
          &v19) )
    Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(v8, *v2, v15, v19);
  v18 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\AppSettings",
          0,
          0x101u,
          &v18) )
    Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(v9, *v2, v15, v18);
  lpSubKey = 0;
  v16 = 0;
  if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &lpSubKey,
              L"%ws\\%ws",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent",
              L"FirstSignInSettings") >= 0
    && !RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x101u, &v16) )
  {
    Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(v10, *v2, v15, v16);
  }
  v11 = *v2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
  View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
           v11,
           (char *)this + 88);
  if ( View < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\firstsigninsettings.cpp",
      (const char *)(unsigned int)View,
      phkResulta);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
}

```

## disassembly

```asm
0x18005d5ec  push    rbp
0x18005d5ee  push    rbx
0x18005d5ef  push    rsi
0x18005d5f0  push    rdi
0x18005d5f1  lea     rbp, [rsp-3Fh]
0x18005d5f6  sub     rsp, 88h
0x18005d5fd  mov     rax, cs:__security_cookie
0x18005d604  xor     rax, rsp
0x18005d607  mov     [rbp+57h+var_28], rax
0x18005d60b  mov     rsi, rcx
0x18005d60e  lea     rdi, [rcx+50h]
0x18005d612  mov     rcx, rdi
0x18005d615  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x18005d61a  mov     r8, rdi
0x18005d61d  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>> * *)
0x18005d622  mov     rcx, [rbp+5Fh]; this
0x18005d626  test    eax, eax
0x18005d628  js      loc_18005D7ED
0x18005d62e  mov     [rbp+57h+var_70], 0
0x18005d636  mov     [rbp+57h+var_30], 0
0x18005d63e  mov     r9d, 20h ; ' '; unsigned int
0x18005d644  lea     r8d, [r9+1]; unsigned int
0x18005d648  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005d64f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005d653  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005d658  nop
0x18005d659  mov     rbx, [rbp+57h+var_30]
0x18005d65d  lea     rcx, [rbp+57h+var_70]
0x18005d661  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d666  lea     r8, [rbp+57h+var_70]
0x18005d66a  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18005d671  mov     rcx, rbx
0x18005d674  call    cs:__imp_RoGetActivationFactory
0x18005d67a  mov     rcx, [rbp+5Fh]; this
0x18005d67e  test    eax, eax
0x18005d680  js      loc_18005D802
0x18005d686  mov     [rbp+57h+var_50], 0
0x18005d68e  lea     rax, [rbp+57h+var_50]
0x18005d692  mov     qword ptr [rsp+0A0h+phkResult], rax; phkResult
0x18005d697  mov     ebx, 101h
0x18005d69c  mov     r9d, ebx; samDesired
0x18005d69f  xor     r8d, r8d; ulOptions
0x18005d6a2  lea     rdx, ?c_FirstSignInSettingsRegPath@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d6a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005d6b0  call    cs:__imp_RegOpenKeyExW
0x18005d6b6  test    eax, eax
0x18005d6b8  jnz     short loc_18005D6CA
0x18005d6ba  mov     r9, [rbp+57h+var_50]
0x18005d6be  mov     r8, [rbp+57h+var_70]
0x18005d6c2  mov     rdx, [rdi]
0x18005d6c5  call    ?ProcessRegkey@FirstSignInSettings@UserProfile@System@Windows@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUIPropertyValueStatics@74@PEAUHKEY__@@@Z; Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::IPropertyValueStatics *,HKEY__ *)
0x18005d6ca  mov     [rbp+57h+var_58], 0
0x18005d6d2  lea     rax, [rbp+57h+var_58]
0x18005d6d6  mov     qword ptr [rsp+0A0h+phkResult], rax; phkResult
0x18005d6db  mov     r9d, ebx; samDesired
0x18005d6de  xor     r8d, r8d; ulOptions
0x18005d6e1  lea     rdx, ?c_FirstSignInSettingsRegPath@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d6e8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005d6ef  call    cs:__imp_RegOpenKeyExW
0x18005d6f5  test    eax, eax
0x18005d6f7  jnz     short loc_18005D709
0x18005d6f9  mov     r9, [rbp+57h+var_58]
0x18005d6fd  mov     r8, [rbp+57h+var_70]
0x18005d701  mov     rdx, [rdi]
0x18005d704  call    ?ProcessRegkey@FirstSignInSettings@UserProfile@System@Windows@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUIPropertyValueStatics@74@PEAUHKEY__@@@Z; Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::IPropertyValueStatics *,HKEY__ *)
0x18005d709  mov     [rbp+57h+lpSubKey], 0
0x18005d711  mov     [rbp+57h+var_68], 0
0x18005d719  lea     r9, aFirstsigninset_1; "FirstSignInSettings"
0x18005d720  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005d727  lea     rdx, aWsWs; "%ws\\%ws"
0x18005d72e  lea     rcx, [rbp+57h+lpSubKey]
0x18005d732  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005d737  test    eax, eax
0x18005d739  js      short loc_18005D76F
0x18005d73b  lea     rax, [rbp+57h+var_68]
0x18005d73f  mov     qword ptr [rsp+0A0h+phkResult], rax; int
0x18005d744  mov     r9d, ebx; samDesired
0x18005d747  xor     r8d, r8d; ulOptions
0x18005d74a  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18005d74e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005d755  call    cs:__imp_RegOpenKeyExW
0x18005d75b  test    eax, eax
0x18005d75d  jnz     short loc_18005D76F
0x18005d75f  mov     r9, [rbp+57h+var_68]
0x18005d763  mov     r8, [rbp+57h+var_70]
0x18005d767  mov     rdx, [rdi]
0x18005d76a  call    ?ProcessRegkey@FirstSignInSettings@UserProfile@System@Windows@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUIPropertyValueStatics@74@PEAUHKEY__@@@Z; Windows::System::UserProfile::FirstSignInSettings::ProcessRegkey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::IPropertyValueStatics *,HKEY__ *)
0x18005d76f  mov     rdi, [rdi]
0x18005d772  lea     rcx, [rsi+58h]
0x18005d776  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d77b  lea     rdx, [rsi+58h]
0x18005d77f  mov     rcx, rdi
0x18005d782  call    ?GetView@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> * *)
0x18005d787  mov     rcx, [rbp+5Fh]; this
0x18005d78b  test    eax, eax
0x18005d78d  js      short loc_18005D7D8
0x18005d78f  lea     rcx, [rbp+57h+var_68]
0x18005d793  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005d798  nop
0x18005d799  lea     rcx, [rbp+57h+lpSubKey]
0x18005d79d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005d7a2  nop
0x18005d7a3  lea     rcx, [rbp+57h+var_58]
0x18005d7a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005d7ac  nop
0x18005d7ad  lea     rcx, [rbp+57h+var_50]
0x18005d7b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005d7b6  nop
0x18005d7b7  lea     rcx, [rbp+57h+var_70]
0x18005d7bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005d7c0  mov     rcx, [rbp+57h+var_28]
0x18005d7c4  xor     rcx, rsp; StackCookie
0x18005d7c7  call    __security_check_cookie
0x18005d7cc  add     rsp, 88h
0x18005d7d3  pop     rdi
0x18005d7d4  pop     rsi
0x18005d7d5  pop     rbx
0x18005d7d6  pop     rbp
0x18005d7d7  retn
0x18005d7d8  mov     r9d, eax; char *
0x18005d7db  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudexperiencehost"...
0x18005d7e2  mov     edx, 6Eh ; 'n'; void *
0x18005d7e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d7ed  mov     r9d, eax; char *
0x18005d7f0  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudexperiencehost"...
0x18005d7f7  mov     edx, 4Fh ; 'O'; void *
0x18005d7fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005d802  mov     r9d, eax; char *
0x18005d805  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\cloudexperiencehost"...
0x18005d80c  mov     edx, 52h ; 'R'; void *
0x18005d811  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
