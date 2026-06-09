# winrt::UXFrame::implementation::SystemXamlApplication::EnableSystemResourceManagerForCurrentProcess(void)

- ea: `0x1800303b8`
- end: `0x1800304f3`
- name: `?EnableSystemResourceManagerForCurrentProcess@SystemXamlApplication@implementation@UXFrame@winrt@@AEAAXXZ`
- size: `315`
- prototype: `void __fastcall(winrt::UXFrame::implementation::SystemXamlApplication *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f800`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x1800046c8`
- `0x18000e1c8`
- `0x180017024`
- `0x18001c864`
- `0x18002e224`
- `0x18002e3d4`
- `0x18002e9c4`
- `0x18002ed64`
- `0x1800303b8`
- `0x18005a010`

## string_xrefs

- `0x180030440`: `pcshell\shell\uxframe\dll\SystemXamlApplication.cpp`
- `0x180030494`: `pcshell\shell\uxframe\dll\SystemXamlApplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall winrt::UXFrame::implementation::SystemXamlApplication::EnableSystemResourceManagerForCurrentProcess(
        winrt::UXFrame::implementation::SystemXamlApplication *this)
{
  struct IUnknown *v1; // rdx
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, void **); // rbx
  void **v4; // rax
  int v5; // eax
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h] BYREF
  void *v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v11 = 0;
  _InterlockedIncrement64(&qword_180073358);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Resources::Core::ResourceManager,Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal> )
  {
    _lambda_c88db0dbc366a6ea415c26622dd26c45_::operator()<winrt::com_ptr<Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal> const &>(
      this,
      &v8);
    _InterlockedDecrement64(&qword_180073358);
  }
  else
  {
    _InterlockedDecrement64(&qword_180073358);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Resources::Core::ResourceManager,Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal>::call<_lambda_c88db0dbc366a6ea415c26622dd26c45_ &>(
      this,
      &v8);
  }
  v2 = v8;
  v3 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v8 + 56LL);
  v4 = winrt::put_abi((winrt *)&v11, v1);
  v5 = v3(v2, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlApplication.cpp",
      (const char *)(unsigned int)v5,
      v8);
  winrt::impl::as<Windows::ApplicationModel::Resources::Core::Internal::ISystemResourceManagerExtensions2,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v9,
    v11);
  v10 = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(&v10);
  v6 = v9;
  v7 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v9 + 48LL))(v9, v10);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlApplication.cpp",
      (const char *)(unsigned int)v7,
      v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
  if ( v6 )
    winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v9);
  if ( v2 )
    winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v8);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v11);
}

```

## disassembly

```asm
0x1800303b8  mov     [rsp-8+arg_0], rbx
0x1800303bd  mov     [rsp-8+arg_8], rdi
0x1800303c2  push    rbp
0x1800303c3  mov     rbp, rsp
0x1800303c6  sub     rsp, 50h
0x1800303ca  mov     rax, cs:__security_cookie
0x1800303d1  xor     rax, rsp
0x1800303d4  mov     [rbp+var_10], rax
0x1800303d8  mov     [rbp+var_18], 0
0x1800303e0  lock inc cs:qword_180073358
0x1800303e8  lea     rdx, [rbp+var_30]
0x1800303ec  cmp     cs:??$factory_cache_entry_v@UResourceManager@Core@Resources@ApplicationModel@Windows@winrt@@UIResourceManagerStaticInternal@Internal@2345@@impl@winrt@@3U?$factory_cache_entry@UResourceManager@Core@Resources@ApplicationModel@Windows@winrt@@UIResourceManagerStaticInternal@Internal@2345@@12@A, 0; factory_cache_entry<winrt::Windows::ApplicationModel::Resources::Core::ResourceManager,Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Resources::Core::ResourceManager,Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Resources::Core::ResourceManager,Windows::ApplicationModel::Resources::Core::Internal::IResourceManagerStaticInternal>
0x1800303f4  jz      short loc_180030405
0x1800303f6  call    ??$?RAEBU?$com_ptr@UIResourceManagerStaticInternal@Internal@Core@Resources@ApplicationModel@Windows@@@winrt@@@_lambda_c88db0dbc366a6ea415c26622dd26c45_@@QEBA?A_PAEBU?$com_ptr@UIResourceManagerStaticInternal@Internal@Core@Resources@ApplicationModel@Windows@@@winrt@@@Z
0x1800303fb  lock dec cs:qword_180073358
0x180030403  jmp     short loc_180030413
0x180030405  lock dec cs:qword_180073358
0x18003040d  call    ??$call@AEAV_lambda_c88db0dbc366a6ea415c26622dd26c45_@@@?$factory_cache_entry@UResourceManager@Core@Resources@ApplicationModel@Windows@winrt@@UIResourceManagerStaticInternal@Internal@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c88db0dbc366a6ea415c26622dd26c45_@@@Z
0x180030412  nop
0x180030413  mov     rdi, [rbp+var_30]
0x180030417  mov     rax, [rdi]
0x18003041a  mov     rbx, [rax+38h]
0x18003041e  lea     rcx, [rbp+var_18]; this
0x180030422  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180030427  mov     rdx, rax
0x18003042a  mov     rcx, rdi
0x18003042d  mov     rax, rbx
0x180030430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030435  mov     rcx, [rbp+8]; this
0x180030439  test    eax, eax
0x18003043b  jns     short loc_180030452
0x18003043d  mov     r9d, eax; char *
0x180030440  lea     r8, aPcshellShellUx_9; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x180030447  mov     edx, 37h ; '7'; void *
0x18003044c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030452  mov     rdx, [rbp+var_18]
0x180030456  lea     rcx, [rbp+var_28]
0x18003045a  call    ??$as@UISystemResourceManagerExtensions2@Internal@Core@Resources@ApplicationModel@Windows@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UISystemResourceManagerExtensions2@Internal@Core@Resources@ApplicationModel@Windows@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<Windows::ApplicationModel::Resources::Core::Internal::ISystemResourceManagerExtensions2,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18003045f  nop
0x180030460  mov     [rbp+var_20], 0
0x180030468  lea     rcx, [rbp+var_20]
0x18003046c  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180030471  nop
0x180030472  mov     rbx, [rbp+var_28]
0x180030476  mov     rax, [rbx]
0x180030479  mov     rdx, [rbp+var_20]
0x18003047d  mov     rcx, rbx
0x180030480  mov     rax, [rax+30h]
0x180030484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030489  mov     rcx, [rbp+8]; this
0x18003048d  test    eax, eax
0x18003048f  jns     short loc_1800304A6
0x180030491  mov     r9d, eax; char *
0x180030494  lea     r8, aPcshellShellUx_9; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x18003049b  mov     edx, 3Dh ; '='; void *
0x1800304a0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800304a6  lea     rcx, [rbp+var_20]
0x1800304aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800304af  nop
0x1800304b0  test    rbx, rbx
0x1800304b3  jz      short loc_1800304BF
0x1800304b5  lea     rcx, [rbp+var_28]
0x1800304b9  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x1800304be  nop
0x1800304bf  test    rdi, rdi
0x1800304c2  jz      short loc_1800304CE
0x1800304c4  lea     rcx, [rbp+var_30]
0x1800304c8  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x1800304cd  nop
0x1800304ce  lea     rcx, [rbp+var_18]; this
0x1800304d2  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800304d7  mov     rcx, [rbp+var_10]
0x1800304db  xor     rcx, rsp; StackCookie
0x1800304de  call    __security_check_cookie
0x1800304e3  mov     rbx, [rsp+50h+arg_0]
0x1800304e8  mov     rdi, [rsp+50h+arg_8]
0x1800304ed  add     rsp, 50h
0x1800304f1  pop     rbp
0x1800304f2  retn
```
