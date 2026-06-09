# CloudExperienceHostLauncher::Launch(ushort const *)

- ea: `0x180013760`
- end: `0x180013b2c`
- name: `?Launch@CloudExperienceHostLauncher@@EEAAJPEBG@Z`
- size: `972`
- prototype: `int(CloudExperienceHostLauncher *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032b0`
- `0x1800056c8`
- `0x180007134`
- `0x18000e2bc`
- `0x18000ee5c`
- `0x1800111f8`
- `0x18001136c`
- `0x1800113cc`
- `0x180012328`
- `0x180013688`
- `0x180013760`
- `0x1800169b0`
- `0x180016b90`
- `0x1800396b8`
- `0x180039bb0`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800139fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800139fa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013875`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013875`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800137c3`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800137c3`

## string_xrefs

- `0x18001388c`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x18001391b`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x1800139a1`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013ada`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013aef`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013b04`: `shell\oobe\user\dll\oobelauncher.cpp`
- `0x180013b19`: `shell\oobe\user\dll\oobelauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CloudExperienceHostLauncher::Launch(CloudExperienceHostLauncher *this, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // eax
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 **); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // eax
  int v18; // eax
  HSTRING string; // [rsp+20h] [rbp-98h] BYREF
  __int64 *v20; // [rsp+28h] [rbp-90h] BYREF
  __int64 v21; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int16 *v23[3]; // [rsp+40h] [rbp-78h] BYREF
  PARSEDURLW ppu; // [rsp+58h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-38h] BYREF
  __int64 v26; // [rsp+98h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  __0__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_PEBG_Z(
    v22,
    L"Local\\Windows.User.FullScreenCloudExperienceHost");
  if ( GetLastError() == 183 )
  {
LABEL_19:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    return 0;
  }
  *(_QWORD *)&ppu.cbSize = 40;
  memset(&ppu.pszProtocol, 0, 32);
  v3 = ParseURLW(a2, &ppu);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
  memset(v23, 0, sizeof(v23));
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v23,
         L"ms-cxh:%ls",
         ppu.pszSuffix);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher>::GetImpl'::`2'::impl) )
  {
LABEL_17:
    v18 = LaunchCloudExperienceHostForNthUserScenario(v23[0]);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
        (const char *)(unsigned int)v18,
        (int)string);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
    goto LABEL_19;
  }
  v21 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"CloudExperienceHostAPI.Redirection.RedirectionManager",
    0x36u,
    0x35u);
  ActivationFactory = RoGetActivationFactory(v26, &GUID_dcaebdd1_c09b_5f76_9aae_b70b9809cbaf, &v21);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    return v6;
  }
  v20 = 0;
  v8 = v21;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v21 + 48LL);
  v20 = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v23);
  v11 = v9(v8, *(_QWORD *)(v10 + 24), &v20);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    return v12;
  }
  string = 0;
  if ( !v20 )
    goto LABEL_16;
  v13 = *v20;
  string = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v13 + 72))(v20, &string);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v14,
      (int)string);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    return v15;
  }
  if ( !string || WindowsIsStringEmpty(string) )
  {
LABEL_16:
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
    goto LABEL_17;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v17 = LaunchShellHostForNthUserScenario(v23[0], StringRawBuffer);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"shell\\oobe\\user\\dll\\oobelauncher.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v21);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return 0;
}

```

## disassembly

```asm
0x180013760  mov     [rsp+arg_0], rbx
0x180013765  push    rdi
0x180013766  sub     rsp, 0B0h
0x18001376d  mov     rax, cs:__security_cookie
0x180013774  xor     rax, rsp
0x180013777  mov     [rsp+0B8h+var_18], rax
0x18001377f  mov     rbx, rdx
0x180013782  lea     rdx, aLocalWindowsUs; "Local\\Windows.User.FullScreenCloudExpe"...
0x180013789  lea     rcx, [rsp+0B8h+var_80]
0x18001378e  call    ??0?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@PEBG@Z
0x180013793  nop
0x180013794  call    cs:__imp_GetLastError
0x18001379a  cmp     eax, 0B7h
0x18001379f  jz      loc_180013AA9
0x1800137a5  mov     qword ptr [rsp+0B8h+ppu.cbSize], 28h ; '('
0x1800137ae  xorps   xmm0, xmm0
0x1800137b1  movups  xmmword ptr [rsp+0B8h+ppu.pszProtocol], xmm0
0x1800137b6  movups  xmmword ptr [rsp+0B8h+ppu.pszSuffix], xmm0
0x1800137bb  lea     rdx, [rsp+0B8h+ppu]; ppu
0x1800137c0  mov     rcx, rbx; pcszURL
0x1800137c3  call    cs:__imp_ParseURLW
0x1800137c9  mov     rcx, [rsp+0B8h]; this
0x1800137d1  test    eax, eax
0x1800137d3  js      loc_180013AD7
0x1800137d9  mov     [rsp+0B8h+var_78], 0
0x1800137e2  mov     [rsp+0B8h+var_70], 0
0x1800137eb  mov     [rsp+0B8h+var_68], 0
0x1800137f4  mov     r8, [rsp+0B8h+ppu.pszSuffix]
0x1800137f9  lea     rdx, aMsCxhLs; "ms-cxh:%ls"
0x180013800  lea     rcx, [rsp+0B8h+var_78]
0x180013805  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001380a  mov     rcx, [rsp+0B8h]; this
0x180013812  test    eax, eax
0x180013814  js      loc_180013AEC
0x18001381a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher> `wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher>::GetImpl(void)'::`2'::impl
0x180013821  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHostLauncher>::__private_IsEnabled(void)
0x180013826  test    al, al
0x180013828  jz      loc_180013A88
0x18001382e  mov     [rsp+0B8h+var_88], 0
0x180013837  mov     [rsp+0B8h+var_20], 0
0x180013843  mov     r9d, 35h ; '5'; unsigned int
0x180013849  lea     r8d, [r9+1]; unsigned int
0x18001384d  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_Redirection_RedirectionManager@@3QBGB; "CloudExperienceHostAPI.Redirection.Redi"...
0x180013854  lea     rcx, [rsp+0B8h+hstringHeader]; hstringHeader
0x18001385c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180013861  lea     r8, [rsp+0B8h+var_88]
0x180013866  lea     rdx, _GUID_dcaebdd1_c09b_5f76_9aae_b70b9809cbaf
0x18001386d  mov     rcx, [rsp+0B8h+var_20]
0x180013875  call    cs:__imp_RoGetActivationFactory
0x18001387b  mov     ebx, eax
0x18001387d  test    eax, eax
0x18001387f  jns     short loc_1800138C5
0x180013881  mov     rcx, [rsp+0B8h]; this
0x180013889  mov     r9d, eax; char *
0x18001388c  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013893  mov     edx, 5Ch ; '\'; void *
0x180013898  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001389d  nop
0x18001389e  lea     rcx, [rsp+0B8h+var_88]
0x1800138a3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800138a8  nop
0x1800138a9  lea     rcx, [rsp+0B8h+var_78]
0x1800138ae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800138b3  nop
0x1800138b4  lea     rcx, [rsp+0B8h+var_80]
0x1800138b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800138be  mov     eax, ebx
0x1800138c0  jmp     loc_180013AB6
0x1800138c5  mov     [rsp+0B8h+var_90], 0
0x1800138ce  mov     rdi, [rsp+0B8h+var_88]
0x1800138d3  mov     rax, [rdi]
0x1800138d6  mov     rbx, [rax+30h]
0x1800138da  mov     [rsp+0B8h+var_90], 0
0x1800138e3  lea     rdx, [rsp+0B8h+var_78]
0x1800138e8  lea     rcx, [rsp+0B8h+hstringHeader]
0x1800138f0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800138f5  nop
0x1800138f6  lea     r8, [rsp+0B8h+var_90]
0x1800138fb  mov     rdx, [rax+18h]
0x1800138ff  mov     rcx, rdi
0x180013902  mov     rax, rbx
0x180013905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001390a  mov     ebx, eax
0x18001390c  test    eax, eax
0x18001390e  jns     short loc_18001395F
0x180013910  mov     rcx, [rsp+0B8h]; this
0x180013918  mov     r9d, eax; char *
0x18001391b  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013922  mov     edx, 5Eh ; '^'; void *
0x180013927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001392c  nop
0x18001392d  lea     rcx, [rsp+0B8h+var_90]
0x180013932  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013937  nop
0x180013938  lea     rcx, [rsp+0B8h+var_88]
0x18001393d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013942  nop
0x180013943  lea     rcx, [rsp+0B8h+var_78]
0x180013948  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001394d  nop
0x18001394e  lea     rcx, [rsp+0B8h+var_80]
0x180013953  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013958  mov     eax, ebx
0x18001395a  jmp     loc_180013AB6
0x18001395f  mov     [rsp+0B8h+string], 0; int
0x180013968  mov     rcx, [rsp+0B8h+var_90]
0x18001396d  test    rcx, rcx
0x180013970  jz      loc_180013A68
0x180013976  mov     rax, [rcx]
0x180013979  mov     [rsp+0B8h+string], 0; int
0x180013982  lea     rdx, [rsp+0B8h+string]
0x180013987  mov     rax, [rax+48h]
0x18001398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013990  mov     ebx, eax
0x180013992  test    eax, eax
0x180013994  jns     short loc_1800139F0
0x180013996  mov     rcx, [rsp+0B8h]; this
0x18001399e  mov     r9d, eax; char *
0x1800139a1  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x1800139a8  mov     edx, 63h ; 'c'; void *
0x1800139ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800139b2  nop
0x1800139b3  lea     rcx, [rsp+0B8h+string]; this
0x1800139b8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800139bd  nop
0x1800139be  lea     rcx, [rsp+0B8h+var_90]
0x1800139c3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800139c8  nop
0x1800139c9  lea     rcx, [rsp+0B8h+var_88]
0x1800139ce  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800139d3  nop
0x1800139d4  lea     rcx, [rsp+0B8h+var_78]
0x1800139d9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800139de  nop
0x1800139df  lea     rcx, [rsp+0B8h+var_80]
0x1800139e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800139e9  mov     eax, ebx
0x1800139eb  jmp     loc_180013AB6
0x1800139f0  mov     rcx, [rsp+0B8h+string]; string
0x1800139f5  test    rcx, rcx
0x1800139f8  jz      short loc_180013A68
0x1800139fa  call    cs:__imp_WindowsIsStringEmpty
0x180013a00  test    eax, eax
0x180013a02  jnz     short loc_180013A68
0x180013a04  xor     edx, edx; length
0x180013a06  mov     rcx, [rsp+0B8h+string]; string
0x180013a0b  call    cs:__imp_WindowsGetStringRawBuffer
0x180013a11  mov     rdx, rax; unsigned __int16 *
0x180013a14  mov     rcx, [rsp+0B8h+var_78]; unsigned __int16 *
0x180013a19  call    ?LaunchShellHostForNthUserScenario@@YAJPEBG0@Z; LaunchShellHostForNthUserScenario(ushort const *,ushort const *)
0x180013a1e  mov     rcx, [rsp+0B8h]; this
0x180013a26  test    eax, eax
0x180013a28  js      loc_180013B01
0x180013a2e  lea     rcx, [rsp+0B8h+string]; this
0x180013a33  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180013a38  nop
0x180013a39  lea     rcx, [rsp+0B8h+var_90]
0x180013a3e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013a43  nop
0x180013a44  lea     rcx, [rsp+0B8h+var_88]
0x180013a49  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013a4e  nop
0x180013a4f  lea     rcx, [rsp+0B8h+var_78]
0x180013a54  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013a59  nop
0x180013a5a  lea     rcx, [rsp+0B8h+var_80]
0x180013a5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013a64  xor     eax, eax
0x180013a66  jmp     short loc_180013AB6
0x180013a68  lea     rcx, [rsp+0B8h+string]; this
0x180013a6d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180013a72  nop
0x180013a73  lea     rcx, [rsp+0B8h+var_90]
0x180013a78  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013a7d  nop
0x180013a7e  lea     rcx, [rsp+0B8h+var_88]
0x180013a83  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180013a88  mov     rcx, [rsp+0B8h+var_78]; unsigned __int16 *
0x180013a8d  call    ?LaunchCloudExperienceHostForNthUserScenario@@YAJPEBG@Z; LaunchCloudExperienceHostForNthUserScenario(ushort const *)
0x180013a92  mov     rcx, [rsp+0B8h]; this
0x180013a9a  test    eax, eax
0x180013a9c  js      short loc_180013B16
0x180013a9e  lea     rcx, [rsp+0B8h+var_78]
0x180013aa3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013aa8  nop
0x180013aa9  lea     rcx, [rsp+0B8h+var_80]
0x180013aae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013ab3  nop
0x180013ab4  xor     eax, eax
0x180013ab6  mov     rcx, [rsp+0B8h+var_18]
0x180013abe  xor     rcx, rsp; StackCookie
0x180013ac1  call    __security_check_cookie
0x180013ac6  mov     rbx, [rsp+0B8h+arg_0]
0x180013ace  add     rsp, 0B0h
0x180013ad5  pop     rdi
0x180013ad6  retn
0x180013ad7  mov     r9d, eax; char *
0x180013ada  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013ae1  mov     edx, 54h ; 'T'; void *
0x180013ae6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013aec  mov     r9d, eax; char *
0x180013aef  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013af6  mov     edx, 56h ; 'V'; void *
0x180013afb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013b01  mov     r9d, eax; char *
0x180013b04  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013b0b  mov     edx, 67h ; 'g'; void *
0x180013b10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013b16  mov     r9d, eax; char *
0x180013b19  lea     r8, aShellOobeUserD_6; "shell\\oobe\\user\\dll\\oobelauncher.cp"...
0x180013b20  mov     edx, 6Dh ; 'm'; void *
0x180013b25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
