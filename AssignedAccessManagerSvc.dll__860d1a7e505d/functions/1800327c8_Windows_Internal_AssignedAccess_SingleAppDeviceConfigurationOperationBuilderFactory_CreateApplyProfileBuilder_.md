# Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateApplyProfileBuilder(void)

- ea: `0x1800327c8`
- end: `0x180032c58`
- name: `?CreateApplyProfileBuilder@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBAPEAUIProfileOperationBuilder@234@XZ`
- size: `1168`
- prototype: `struct Windows::Internal::AssignedAccess::IProfileOperationBuilder *__fastcall(Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032f70`

## callees

- `0x180006640`
- `0x18000cfe4`
- `0x180010c98`
- `0x180014a5c`
- `0x180020050`
- `0x180022930`
- `0x180027190`
- `0x18002cf18`
- `0x18002e19c`
- `0x180030498`
- `0x1800308ec`
- `0x1800309e4`
- `0x180030b08`
- `0x180030bf8`
- `0x180030e14`
- `0x1800312d0`
- `0x180031b48`
- `0x1800327c8`
- `0x180033090`
- `0x1800340ec`
- `0x18003429c`
- `0x18005080c`
- `0x180096010`

## string_xrefs

- `0x18003280d`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x18003283f`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x18003286f`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800328c6`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800328f2`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800329a9`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800329d5`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032a1c`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032a45`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032a92`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032ad9`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032b05`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032b6d`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032b99`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032be7`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180032c10`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct Windows::Internal::AssignedAccess::IProfileOperationBuilder *__fastcall Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateApplyProfileBuilder(
        Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory *this)
{
  int v2; // eax
  int v3; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v4; // rbx
  Windows::Internal::AssignedAccess::CompositeOperation *v5; // rdi
  int v6; // eax
  int v7; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v8; // r14
  int v9; // eax
  __int64 v10; // rax
  int v11; // ebx
  int v12; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v18; // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v27; // [rsp+20h] [rbp-69h] BYREF
  struct Windows::Internal::AssignedAccess::IProfileOperation *v28; // [rsp+28h] [rbp-61h] BYREF
  int v29; // [rsp+30h] [rbp-59h] BYREF
  Windows::Internal::AssignedAccess::CompositeOperation *v30; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v31[32]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v32[32]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v33[32]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v29 = 0;
  v30 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(&v30);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v2,
      v27);
  LOBYTE(v27) = 0;
  v28 = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DeviceRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
         &v28,
         &v27);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v3,
      v27);
  v4 = v28;
  v5 = v30;
  v6 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v30, v28);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v6,
      v27);
  if ( Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(this) )
  {
    LOBYTE(v27) = 0;
    v28 = 0;
    if ( v4 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v4 + 16LL))(v4);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::SingleAppClassicRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
           &v28,
           &v27);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v7,
        v27);
    v8 = v28;
    v9 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13F,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v9,
        v27);
    if ( (unsigned __int8)Windows::Internal::AssignedAccess::UserInfoHelper::IsLocalUser((char *)this + 24) )
    {
      v10 = std::wstring::wstring(v33, (char *)this + 24);
      v11 = 1;
    }
    else
    {
      v10 = std::wstring::wstring(v32, L"S-1-5-32-545");
      v11 = 2;
    }
    v29 = v11;
    std::wstring::wstring(v31, v10);
    if ( (v11 & 2) != 0 )
    {
      LOBYTE(v11) = v11 & 0xFD;
      std::wstring::_Tidy_deallocate(v32);
    }
    if ( (v11 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v33);
    LOBYTE(v27) = 0;
    v28 = 0;
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v8 + 16LL))(v8);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingLocalPolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &>(
            &v28,
            &v27,
            (char *)this + 16,
            v31);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v12,
        v27);
    v13 = v28;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x142,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v14,
        v27);
    LOBYTE(v27) = 0;
    v28 = 0;
    if ( v13 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v13 + 16LL))(v13);
    v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingMachinePolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
            &v28,
            &v27);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v15,
        v27);
    v16 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v16,
        v27);
    v17 = Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateMDMApplyOperationBuilder(
            &v29,
            *((unsigned int *)this + 4));
    wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy>::operator=(
      &v28,
      v17);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v29);
    v18 = v28;
    v19 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v19,
        v27);
    LOBYTE(v27) = 0;
    v28 = 0;
    if ( v18 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v18 + 16LL))(v18);
    v20 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
            &v28,
            &v27);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v20,
        v27);
    v4 = v28;
    v21 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v21,
        v27);
    std::wstring::_Tidy_deallocate(v31);
  }
  if ( Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(this)
    || Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppWithBreakoutSequenceConfigured(this) )
  {
    LOBYTE(v27) = 0;
    v28 = 0;
    if ( v4 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v4 + 16LL))(v4);
    v22 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::KeyboardFilteringOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
            &v28,
            &v27);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v22,
        v27);
    v4 = v28;
    v23 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v23,
        v27);
  }
  v29 = 1;
  v28 = 0;
  if ( v4 )
    (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v4 + 16LL))(v4);
  v24 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AppSettingsOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,enum Windows::Internal::AssignedAccess::ApplyOption,std::wstring const &>(
          &v28,
          &v29,
          (char *)this + 24);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v24,
      v27);
  v25 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v28);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v25,
      v27);
  v30 = 0;
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v28);
  wil::com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>(&v30);
  return v5;
}

```

## disassembly

```asm
0x1800327c8  push    rbp
0x1800327ca  push    rbx
0x1800327cb  push    rsi
0x1800327cc  push    rdi
0x1800327cd  push    r14
0x1800327cf  push    r15
0x1800327d1  lea     rbp, [rsp-2Fh]
0x1800327d6  sub     rsp, 0B8h
0x1800327dd  mov     rax, cs:__security_cookie
0x1800327e4  xor     rax, rsp
0x1800327e7  mov     [rbp+57h+var_40], rax
0x1800327eb  mov     rsi, rcx
0x1800327ee  xor     r15d, r15d
0x1800327f1  mov     [rbp+57h+var_B0], r15d
0x1800327f5  mov     [rbp+57h+var_A8], r15
0x1800327f9  lea     rcx, [rbp+57h+var_A8]
0x1800327fd  call    ??$MakeAndInitialize@VCompositeOperationBuilder@AssignedAccess@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompositeOperationBuilder@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(Windows::Internal::AssignedAccess::CompositeOperationBuilder * *)
0x180032802  mov     rcx, [rbp+5Fh]; this
0x180032806  test    eax, eax
0x180032808  jns     short loc_18003281F
0x18003280a  mov     r9d, eax; char *
0x18003280d  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032814  mov     edx, 135h; void *
0x180032819  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003281f  mov     byte ptr [rbp+57h+var_C0], r15b
0x180032823  mov     [rbp+57h+var_B8], r15
0x180032827  lea     rdx, [rbp+57h+var_C0]
0x18003282b  lea     rcx, [rbp+57h+var_B8]
0x18003282f  call    ??$MakeAndInitialize@VDeviceRegistryKeyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DeviceRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180032834  mov     rcx, [rbp+5Fh]; this
0x180032838  test    eax, eax
0x18003283a  jns     short loc_180032851
0x18003283c  mov     r9d, eax; char *
0x18003283f  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032846  mov     edx, 139h; void *
0x18003284b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032851  mov     rbx, [rbp+57h+var_B8]
0x180032855  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032858  mov     rdi, [rbp+57h+var_A8]
0x18003285c  mov     rcx, rdi; this
0x18003285f  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032864  mov     rcx, [rbp+5Fh]; this
0x180032868  test    eax, eax
0x18003286a  jns     short loc_180032881
0x18003286c  mov     r9d, eax; char *
0x18003286f  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032876  mov     edx, 13Ah; void *
0x18003287b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032881  mov     rcx, rsi; this
0x180032884  call    ?IsSingleAppClassicAppConfigured@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBA_NXZ; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(void)
0x180032889  test    al, al
0x18003288b  jz      loc_180032B20
0x180032891  mov     byte ptr [rbp+57h+var_C0], r15b
0x180032895  mov     [rbp+57h+var_B8], r15
0x180032899  test    rbx, rbx
0x18003289c  jz      short loc_1800328AE
0x18003289e  mov     rax, [rbx]
0x1800328a1  mov     rcx, rbx
0x1800328a4  mov     rax, [rax+10h]
0x1800328a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328ad  nop
0x1800328ae  lea     rdx, [rbp+57h+var_C0]
0x1800328b2  lea     rcx, [rbp+57h+var_B8]
0x1800328b6  call    ??$MakeAndInitialize@VSingleAppClassicRegistryKeyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::SingleAppClassicRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x1800328bb  mov     rcx, [rbp+5Fh]; this
0x1800328bf  test    eax, eax
0x1800328c1  jns     short loc_1800328D8
0x1800328c3  mov     r9d, eax; char *
0x1800328c6  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800328cd  mov     edx, 13Eh; void *
0x1800328d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800328d8  mov     r14, [rbp+57h+var_B8]
0x1800328dc  mov     rdx, r14; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800328df  mov     rcx, rdi; this
0x1800328e2  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x1800328e7  mov     rcx, [rbp+5Fh]; this
0x1800328eb  test    eax, eax
0x1800328ed  jns     short loc_180032904
0x1800328ef  mov     r9d, eax; char *
0x1800328f2  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800328f9  mov     edx, 13Fh; void *
0x1800328fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032904  lea     rcx, [rsi+18h]
0x180032908  call    ?IsLocalUser@UserInfoHelper@AssignedAccess@Internal@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::IsLocalUser(std::wstring const &)
0x18003290d  test    al, al
0x18003290f  jz      short loc_180032926
0x180032911  lea     rdx, [rsi+18h]
0x180032915  lea     rcx, [rbp+57h+var_60]
0x180032919  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003291e  nop
0x18003291f  mov     ebx, 1
0x180032924  jmp     short loc_18003293C
0x180032926  lea     rdx, aS1532545; "S-1-5-32-545"
0x18003292d  lea     rcx, [rbp+57h+var_80]
0x180032931  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180032936  nop
0x180032937  mov     ebx, 2
0x18003293c  mov     [rbp+57h+var_B0], ebx
0x18003293f  mov     rdx, rax
0x180032942  lea     rcx, [rbp+57h+var_A0]
0x180032946  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003294b  nop
0x18003294c  test    bl, 2
0x18003294f  jz      short loc_18003295E
0x180032951  and     ebx, 0FFFFFFFDh
0x180032954  lea     rcx, [rbp+57h+var_80]
0x180032958  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003295d  nop
0x18003295e  test    bl, 1
0x180032961  jz      short loc_18003296C
0x180032963  lea     rcx, [rbp+57h+var_60]
0x180032967  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003296c  mov     byte ptr [rbp+57h+var_C0], r15b
0x180032970  mov     [rbp+57h+var_B8], r15
0x180032974  test    r14, r14
0x180032977  jz      short loc_180032989
0x180032979  mov     rax, [r14]
0x18003297c  mov     rcx, r14
0x18003297f  mov     rax, [rax+10h]
0x180032983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032988  nop
0x180032989  lea     r9, [rbp+57h+var_A0]
0x18003298d  lea     r8, [rsi+10h]
0x180032991  lea     rdx, [rbp+57h+var_C0]
0x180032995  lea     rcx, [rbp+57h+var_B8]
0x180032999  call    ??$MakeAndInitialize@VDialogBlockingLocalPolicyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_NAEBW4DefinitionVersion@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_NAEBW4DefinitionVersion@456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingLocalPolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &)
0x18003299e  mov     rcx, [rbp+5Fh]; this
0x1800329a2  test    eax, eax
0x1800329a4  jns     short loc_1800329BB
0x1800329a6  mov     r9d, eax; char *
0x1800329a9  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800329b0  mov     edx, 141h; void *
0x1800329b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800329bb  mov     rbx, [rbp+57h+var_B8]
0x1800329bf  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800329c2  mov     rcx, rdi; this
0x1800329c5  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x1800329ca  mov     rcx, [rbp+5Fh]; this
0x1800329ce  test    eax, eax
0x1800329d0  jns     short loc_1800329E7
0x1800329d2  mov     r9d, eax; char *
0x1800329d5  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800329dc  mov     edx, 142h; void *
0x1800329e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800329e7  mov     byte ptr [rbp+57h+var_C0], r15b
0x1800329eb  mov     [rbp+57h+var_B8], r15
0x1800329ef  test    rbx, rbx
0x1800329f2  jz      short loc_180032A04
0x1800329f4  mov     rax, [rbx]
0x1800329f7  mov     rcx, rbx
0x1800329fa  mov     rax, [rax+10h]
0x1800329fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a03  nop
0x180032a04  lea     rdx, [rbp+57h+var_C0]
0x180032a08  lea     rcx, [rbp+57h+var_B8]
0x180032a0c  call    ??$MakeAndInitialize@VDialogBlockingMachinePolicyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingMachinePolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180032a11  mov     rcx, [rbp+5Fh]; this
0x180032a15  test    eax, eax
0x180032a17  jns     short loc_180032A2E
0x180032a19  mov     r9d, eax; char *
0x180032a1c  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032a23  mov     edx, 143h; void *
0x180032a28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032a2e  mov     rdx, [rbp+57h+var_B8]; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032a32  mov     rcx, rdi; this
0x180032a35  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032a3a  mov     rcx, [rbp+5Fh]; this
0x180032a3e  test    eax, eax
0x180032a40  jns     short loc_180032A57
0x180032a42  mov     r9d, eax; char *
0x180032a45  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032a4c  mov     edx, 144h; void *
0x180032a51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032a57  mov     edx, [rsi+10h]
0x180032a5a  lea     rcx, [rbp+57h+var_B0]
0x180032a5e  call    ?CreateMDMApplyOperationBuilder@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@CA?AV?$com_ptr_t@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@W4DefinitionVersion@234@@Z; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateMDMApplyOperationBuilder(Windows::Internal::AssignedAccess::DefinitionVersion)
0x180032a63  mov     rdx, rax
0x180032a66  lea     rcx, [rbp+57h+var_B8]
0x180032a6a  call    ??4?$com_ptr_t@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy> &&)
0x180032a6f  lea     rcx, [rbp+57h+var_B0]
0x180032a73  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180032a78  mov     rbx, [rbp+57h+var_B8]
0x180032a7c  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032a7f  mov     rcx, rdi; this
0x180032a82  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032a87  mov     rcx, [rbp+5Fh]; this
0x180032a8b  test    eax, eax
0x180032a8d  jns     short loc_180032AA4
0x180032a8f  mov     r9d, eax; char *
0x180032a92  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032a99  mov     edx, 146h; void *
0x180032a9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032aa4  mov     byte ptr [rbp+57h+var_C0], r15b
0x180032aa8  mov     [rbp+57h+var_B8], r15
0x180032aac  test    rbx, rbx
0x180032aaf  jz      short loc_180032AC1
0x180032ab1  mov     rax, [rbx]
0x180032ab4  mov     rcx, rbx
0x180032ab7  mov     rax, [rax+10h]
0x180032abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ac0  nop
0x180032ac1  lea     rdx, [rbp+57h+var_C0]
0x180032ac5  lea     rcx, [rbp+57h+var_B8]
0x180032ac9  call    ??$MakeAndInitialize@VDialogBlockingOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180032ace  mov     rcx, [rbp+5Fh]; this
0x180032ad2  test    eax, eax
0x180032ad4  jns     short loc_180032AEB
0x180032ad6  mov     r9d, eax; char *
0x180032ad9  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032ae0  mov     edx, 147h; void *
0x180032ae5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032aeb  mov     rbx, [rbp+57h+var_B8]
0x180032aef  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032af2  mov     rcx, rdi; this
0x180032af5  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032afa  mov     rcx, [rbp+5Fh]; this
0x180032afe  test    eax, eax
0x180032b00  jns     short loc_180032B17
0x180032b02  mov     r9d, eax; char *
0x180032b05  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032b0c  mov     edx, 148h; void *
0x180032b11  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032b17  lea     rcx, [rbp+57h+var_A0]
0x180032b1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032b20  mov     rcx, rsi; this
0x180032b23  call    ?IsSingleAppClassicAppConfigured@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBA_NXZ; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(void)
0x180032b28  test    al, al
0x180032b2a  jnz     short loc_180032B38
0x180032b2c  mov     rcx, rsi; this
0x180032b2f  call    ?IsSingleAppWithBreakoutSequenceConfigured@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBA_NXZ; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppWithBreakoutSequenceConfigured(void)
0x180032b34  test    al, al
0x180032b36  jz      short loc_180032BAB
0x180032b38  mov     byte ptr [rbp+57h+var_C0], r15b
0x180032b3c  mov     [rbp+57h+var_B8], r15
0x180032b40  test    rbx, rbx
0x180032b43  jz      short loc_180032B55
0x180032b45  mov     rax, [rbx]
0x180032b48  mov     rcx, rbx
0x180032b4b  mov     rax, [rax+10h]
0x180032b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b54  nop
0x180032b55  lea     rdx, [rbp+57h+var_C0]
0x180032b59  lea     rcx, [rbp+57h+var_B8]
0x180032b5d  call    ??$MakeAndInitialize@VKeyboardFilteringOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::KeyboardFilteringOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180032b62  mov     rcx, [rbp+5Fh]; this
0x180032b66  test    eax, eax
0x180032b68  jns     short loc_180032B7F
0x180032b6a  mov     r9d, eax; char *
0x180032b6d  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032b74  mov     edx, 14Dh; void *
0x180032b79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032b7f  mov     rbx, [rbp+57h+var_B8]
0x180032b83  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032b86  mov     rcx, rdi; this
0x180032b89  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032b8e  mov     rcx, [rbp+5Fh]; this
0x180032b92  test    eax, eax
0x180032b94  jns     short loc_180032BAB
0x180032b96  mov     r9d, eax; char *
0x180032b99  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032ba0  mov     edx, 14Eh; void *
0x180032ba5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032bab  mov     [rbp+57h+var_B0], 1
0x180032bb2  mov     [rbp+57h+var_B8], r15
0x180032bb6  test    rbx, rbx
0x180032bb9  jz      short loc_180032BCB
0x180032bbb  mov     rax, [rbx]
0x180032bbe  mov     rcx, rbx
0x180032bc1  mov     rax, [rax+10h]
0x180032bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bca  nop
0x180032bcb  lea     r8, [rsi+18h]
0x180032bcf  lea     rdx, [rbp+57h+var_B0]
0x180032bd3  lea     rcx, [rbp+57h+var_B8]
0x180032bd7  call    ??$MakeAndInitialize@VAppSettingsOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@W4ApplyOption@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEAW4ApplyOption@456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AppSettingsOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,Windows::Internal::AssignedAccess::ApplyOption,std::wstring const &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,Windows::Internal::AssignedAccess::ApplyOption &&,std::wstring const &)
0x180032bdc  mov     rcx, [rbp+5Fh]; this
0x180032be0  test    eax, eax
0x180032be2  jns     short loc_180032BF9
0x180032be4  mov     r9d, eax; char *
0x180032be7  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032bee  mov     edx, 151h; void *
0x180032bf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032bf9  mov     rdx, [rbp+57h+var_B8]; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180032bfd  mov     rcx, rdi; this
0x180032c00  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180032c05  mov     rcx, [rbp+5Fh]; this
0x180032c09  test    eax, eax
0x180032c0b  jns     short loc_180032C22
0x180032c0d  mov     r9d, eax; char *
0x180032c10  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180032c17  mov     edx, 152h; void *
0x180032c1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032c22  mov     [rbp+57h+var_A8], r15
0x180032c26  lea     rcx, [rbp+57h+var_B8]
0x180032c2a  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180032c2f  nop
0x180032c30  lea     rcx, [rbp+57h+var_A8]
0x180032c34  call    ??1?$com_ptr_t@VRegistryKeyOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>(void)
0x180032c39  mov     rax, rdi
0x180032c3c  mov     rcx, [rbp+57h+var_40]
  ... truncated ...
```
