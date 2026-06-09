# Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateUnapplyProfileBuilder(void)

- ea: `0x180033958`
- end: `0x180033d14`
- name: `?CreateUnapplyProfileBuilder@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBAPEAUIProfileOperationBuilder@234@XZ`
- size: `956`
- prototype: `struct Windows::Internal::AssignedAccess::IProfileOperationBuilder *__fastcall(Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory *__hidden this)`
- caller_count: `1`
- callee_count: `20`
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
- `0x1800312d0`
- `0x180031b48`
- `0x180033138`
- `0x180033958`
- `0x1800340ec`
- `0x18005080c`
- `0x180096010`

## string_xrefs

- `0x1800339a6`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x1800339dc`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033a0c`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033a67`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033a93`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033b4e`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033b7a`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033bc5`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033bee`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033c3c`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033c97`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`
- `0x180033cc0`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\configurationoperationbuilderfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct Windows::Internal::AssignedAccess::IProfileOperationBuilder *__fastcall Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateUnapplyProfileBuilder(
        Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory *this)
{
  int v2; // eax
  int v3; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v4; // rbx
  Windows::Internal::AssignedAccess::CompositeOperation *v5; // rdi
  int v6; // eax
  int v7; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  int v11; // ebx
  int v12; // eax
  struct Windows::Internal::AssignedAccess::IProfileOperation *v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v22; // [rsp+20h] [rbp-49h] BYREF
  struct Windows::Internal::AssignedAccess::IProfileOperation *v23; // [rsp+28h] [rbp-41h] BYREF
  int v24; // [rsp+30h] [rbp-39h] BYREF
  Windows::Internal::AssignedAccess::CompositeOperation *v25; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v26[32]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v24 = 0;
  v25 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(&v25);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v2,
      v22);
  LOBYTE(v22) = 1;
  v23 = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DeviceRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
         &v23,
         &v22);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v3,
      v22);
  v4 = v23;
  v5 = v25;
  v6 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v25, v23);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v6,
      v22);
  if ( Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(this) )
  {
    LOBYTE(v22) = 1;
    v23 = 0;
    if ( v4 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v4 + 16LL))(v4);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::SingleAppClassicRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
           &v23,
           &v22);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v7,
        v22);
    v8 = v23;
    v9 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v23);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v9,
        v22);
    if ( (unsigned __int8)Windows::Internal::AssignedAccess::UserInfoHelper::IsLocalUser((char *)this + 24) )
    {
      v10 = std::wstring::wstring(v28, (char *)this + 24);
      v11 = 1;
    }
    else
    {
      v10 = std::wstring::wstring(v27, L"S-1-5-32-545");
      v11 = 2;
    }
    v24 = v11;
    std::wstring::wstring(v26, v10);
    if ( (v11 & 2) != 0 )
    {
      LOBYTE(v11) = v11 & 0xFD;
      std::wstring::_Tidy_deallocate(v27);
    }
    if ( (v11 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v28);
    LOBYTE(v22) = 1;
    v23 = 0;
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v8 + 16LL))(v8);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingLocalPolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,enum Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &>(
            &v23,
            &v22,
            (char *)this + 16,
            v26);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v12,
        v22);
    v13 = v23;
    v14 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v23);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v14,
        v22);
    LOBYTE(v22) = 1;
    v23 = 0;
    if ( v13 )
      (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v13 + 16LL))(v13);
    v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingMachinePolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(
            &v23,
            &v22);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v15,
        v22);
    v16 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v23);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v16,
        v22);
    v17 = Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateMDMUnapplyOperationBuilder(
            &v24,
            *((unsigned int *)this + 4));
    wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy>::operator=(
      &v23,
      v17);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v24);
    v4 = v23;
    v18 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v23);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
        (const char *)(unsigned int)v18,
        v22);
    std::wstring::_Tidy_deallocate(v26);
  }
  v24 = 2;
  v23 = 0;
  if ( v4 )
    (*(void (__fastcall **)(struct Windows::Internal::AssignedAccess::IProfileOperation *))(*(_QWORD *)v4 + 16LL))(v4);
  v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AppSettingsOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,enum Windows::Internal::AssignedAccess::ApplyOption,std::wstring const &>(
          &v23,
          &v24,
          (char *)this + 24);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v19,
      v22);
  v20 = Windows::Internal::AssignedAccess::CompositeOperation::Add(v5, v23);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\configurationoperationbuilderfactory.cpp",
      (const char *)(unsigned int)v20,
      v22);
  v25 = 0;
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v23);
  wil::com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>(&v25);
  return v5;
}

```

## disassembly

```asm
0x180033958  mov     [rsp-8+arg_8], rbx
0x18003395d  mov     [rsp-8+arg_10], rsi
0x180033962  push    rbp
0x180033963  push    rdi
0x180033964  push    r14
0x180033966  lea     rbp, [rsp-47h]
0x18003396b  sub     rsp, 0B0h
0x180033972  mov     rax, cs:__security_cookie
0x180033979  xor     rax, rsp
0x18003397c  mov     [rbp+57h+var_20], rax
0x180033980  mov     r14, rcx
0x180033983  mov     [rbp+57h+var_90], 0
0x18003398a  mov     [rbp+57h+var_88], 0
0x180033992  lea     rcx, [rbp+57h+var_88]
0x180033996  call    ??$MakeAndInitialize@VCompositeOperationBuilder@AssignedAccess@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompositeOperationBuilder@AssignedAccess@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::CompositeOperationBuilder,Windows::Internal::AssignedAccess::CompositeOperationBuilder,>(Windows::Internal::AssignedAccess::CompositeOperationBuilder * *)
0x18003399b  mov     rcx, [rbp+5Fh]; this
0x18003399f  test    eax, eax
0x1800339a1  jns     short loc_1800339B8
0x1800339a3  mov     r9d, eax; char *
0x1800339a6  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800339ad  mov     edx, 159h; void *
0x1800339b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800339b8  mov     byte ptr [rbp+57h+var_A0], 1
0x1800339bc  mov     [rbp+57h+var_98], 0
0x1800339c4  lea     rdx, [rbp+57h+var_A0]
0x1800339c8  lea     rcx, [rbp+57h+var_98]
0x1800339cc  call    ??$MakeAndInitialize@VDeviceRegistryKeyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DeviceRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x1800339d1  mov     rcx, [rbp+5Fh]; this
0x1800339d5  test    eax, eax
0x1800339d7  jns     short loc_1800339EE
0x1800339d9  mov     r9d, eax; char *
0x1800339dc  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800339e3  mov     edx, 15Dh; void *
0x1800339e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800339ee  mov     rbx, [rbp+57h+var_98]
0x1800339f2  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x1800339f5  mov     rdi, [rbp+57h+var_88]
0x1800339f9  mov     rcx, rdi; this
0x1800339fc  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033a01  mov     rcx, [rbp+5Fh]; this
0x180033a05  test    eax, eax
0x180033a07  jns     short loc_180033A1E
0x180033a09  mov     r9d, eax; char *
0x180033a0c  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033a13  mov     edx, 15Eh; void *
0x180033a18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033a1e  mov     rcx, r14; this
0x180033a21  call    ?IsSingleAppClassicAppConfigured@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@AEBA_NXZ; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::IsSingleAppClassicAppConfigured(void)
0x180033a26  test    al, al
0x180033a28  jz      loc_180033C57
0x180033a2e  mov     byte ptr [rbp+57h+var_A0], 1
0x180033a32  mov     [rbp+57h+var_98], 0
0x180033a3a  test    rbx, rbx
0x180033a3d  jz      short loc_180033A4F
0x180033a3f  mov     rax, [rbx]
0x180033a42  mov     rcx, rbx
0x180033a45  mov     rax, [rax+10h]
0x180033a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a4e  nop
0x180033a4f  lea     rdx, [rbp+57h+var_A0]
0x180033a53  lea     rcx, [rbp+57h+var_98]
0x180033a57  call    ??$MakeAndInitialize@VSingleAppClassicRegistryKeyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::SingleAppClassicRegistryKeyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180033a5c  mov     rcx, [rbp+5Fh]; this
0x180033a60  test    eax, eax
0x180033a62  jns     short loc_180033A79
0x180033a64  mov     r9d, eax; char *
0x180033a67  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033a6e  mov     edx, 162h; void *
0x180033a73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033a79  mov     rsi, [rbp+57h+var_98]
0x180033a7d  mov     rdx, rsi; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033a80  mov     rcx, rdi; this
0x180033a83  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033a88  mov     rcx, [rbp+5Fh]; this
0x180033a8c  test    eax, eax
0x180033a8e  jns     short loc_180033AA5
0x180033a90  mov     r9d, eax; char *
0x180033a93  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033a9a  mov     edx, 163h; void *
0x180033a9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033aa5  lea     rcx, [r14+18h]
0x180033aa9  call    ?IsLocalUser@UserInfoHelper@AssignedAccess@Internal@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::IsLocalUser(std::wstring const &)
0x180033aae  test    al, al
0x180033ab0  jz      short loc_180033AC7
0x180033ab2  lea     rdx, [r14+18h]
0x180033ab6  lea     rcx, [rbp+57h+var_40]
0x180033aba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033abf  nop
0x180033ac0  mov     ebx, 1
0x180033ac5  jmp     short loc_180033ADD
0x180033ac7  lea     rdx, aS1532545; "S-1-5-32-545"
0x180033ace  lea     rcx, [rbp+57h+var_60]
0x180033ad2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033ad7  nop
0x180033ad8  mov     ebx, 2
0x180033add  mov     [rbp+57h+var_90], ebx
0x180033ae0  mov     rdx, rax
0x180033ae3  lea     rcx, [rbp+57h+var_80]
0x180033ae7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033aec  nop
0x180033aed  test    bl, 2
0x180033af0  jz      short loc_180033AFF
0x180033af2  and     ebx, 0FFFFFFFDh
0x180033af5  lea     rcx, [rbp+57h+var_60]
0x180033af9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033afe  nop
0x180033aff  test    bl, 1
0x180033b02  jz      short loc_180033B0D
0x180033b04  lea     rcx, [rbp+57h+var_40]
0x180033b08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033b0d  mov     byte ptr [rbp+57h+var_A0], 1
0x180033b11  mov     [rbp+57h+var_98], 0
0x180033b19  test    rsi, rsi
0x180033b1c  jz      short loc_180033B2E
0x180033b1e  mov     rax, [rsi]
0x180033b21  mov     rcx, rsi
0x180033b24  mov     rax, [rax+10h]
0x180033b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b2d  nop
0x180033b2e  lea     r9, [rbp+57h+var_80]
0x180033b32  lea     r8, [r14+10h]
0x180033b36  lea     rdx, [rbp+57h+var_A0]
0x180033b3a  lea     rcx, [rbp+57h+var_98]
0x180033b3e  call    ??$MakeAndInitialize@VDialogBlockingLocalPolicyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_NAEBW4DefinitionVersion@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_NAEBW4DefinitionVersion@456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingLocalPolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&,Windows::Internal::AssignedAccess::DefinitionVersion const &,std::wstring const &)
0x180033b43  mov     rcx, [rbp+5Fh]; this
0x180033b47  test    eax, eax
0x180033b49  jns     short loc_180033B60
0x180033b4b  mov     r9d, eax; char *
0x180033b4e  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033b55  mov     edx, 165h; void *
0x180033b5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033b60  mov     rbx, [rbp+57h+var_98]
0x180033b64  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033b67  mov     rcx, rdi; this
0x180033b6a  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033b6f  mov     rcx, [rbp+5Fh]; this
0x180033b73  test    eax, eax
0x180033b75  jns     short loc_180033B8C
0x180033b77  mov     r9d, eax; char *
0x180033b7a  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033b81  mov     edx, 166h; void *
0x180033b86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033b8c  mov     byte ptr [rbp+57h+var_A0], 1
0x180033b90  mov     [rbp+57h+var_98], 0
0x180033b98  test    rbx, rbx
0x180033b9b  jz      short loc_180033BAD
0x180033b9d  mov     rax, [rbx]
0x180033ba0  mov     rcx, rbx
0x180033ba3  mov     rax, [rax+10h]
0x180033ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bac  nop
0x180033bad  lea     rdx, [rbp+57h+var_A0]
0x180033bb1  lea     rcx, [rbp+57h+var_98]
0x180033bb5  call    ??$MakeAndInitialize@VDialogBlockingMachinePolicyOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@_N@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::DialogBlockingMachinePolicyOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,bool>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,bool &&)
0x180033bba  mov     rcx, [rbp+5Fh]; this
0x180033bbe  test    eax, eax
0x180033bc0  jns     short loc_180033BD7
0x180033bc2  mov     r9d, eax; char *
0x180033bc5  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033bcc  mov     edx, 167h; void *
0x180033bd1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033bd7  mov     rdx, [rbp+57h+var_98]; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033bdb  mov     rcx, rdi; this
0x180033bde  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033be3  mov     rcx, [rbp+5Fh]; this
0x180033be7  test    eax, eax
0x180033be9  jns     short loc_180033C00
0x180033beb  mov     r9d, eax; char *
0x180033bee  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033bf5  mov     edx, 168h; void *
0x180033bfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033c00  mov     edx, [r14+10h]
0x180033c04  lea     rcx, [rbp+57h+var_90]
0x180033c08  call    ?CreateMDMUnapplyOperationBuilder@SingleAppDeviceConfigurationOperationBuilderFactory@AssignedAccess@Internal@Windows@@CA?AV?$com_ptr_t@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@W4DefinitionVersion@234@@Z; Windows::Internal::AssignedAccess::SingleAppDeviceConfigurationOperationBuilderFactory::CreateMDMUnapplyOperationBuilder(Windows::Internal::AssignedAccess::DefinitionVersion)
0x180033c0d  mov     rdx, rax
0x180033c10  lea     rcx, [rbp+57h+var_98]
0x180033c14  call    ??4?$com_ptr_t@UIProfileOperationBuilder@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperationBuilder,wil::err_exception_policy> &&)
0x180033c19  lea     rcx, [rbp+57h+var_90]
0x180033c1d  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180033c22  mov     rbx, [rbp+57h+var_98]
0x180033c26  mov     rdx, rbx; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033c29  mov     rcx, rdi; this
0x180033c2c  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033c31  mov     rcx, [rbp+5Fh]; this
0x180033c35  test    eax, eax
0x180033c37  jns     short loc_180033C4E
0x180033c39  mov     r9d, eax; char *
0x180033c3c  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033c43  mov     edx, 16Ah; void *
0x180033c48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033c4e  lea     rcx, [rbp+57h+var_80]
0x180033c52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033c57  mov     [rbp+57h+var_90], 2
0x180033c5e  mov     [rbp+57h+var_98], 0
0x180033c66  test    rbx, rbx
0x180033c69  jz      short loc_180033C7B
0x180033c6b  mov     rax, [rbx]
0x180033c6e  mov     rcx, rbx
0x180033c71  mov     rax, [rax+10h]
0x180033c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c7a  nop
0x180033c7b  lea     r8, [r14+18h]
0x180033c7f  lea     rdx, [rbp+57h+var_90]
0x180033c83  lea     rcx, [rbp+57h+var_98]
0x180033c87  call    ??$MakeAndInitialize@VAppSettingsOperationBuilder@AssignedAccess@Internal@Windows@@UIProfileOperationBuilder@234@W4ApplyOption@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIProfileOperationBuilder@AssignedAccess@Internal@Windows@@$$QEAW4ApplyOption@456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::AppSettingsOperationBuilder,Windows::Internal::AssignedAccess::IProfileOperationBuilder,Windows::Internal::AssignedAccess::ApplyOption,std::wstring const &>(Windows::Internal::AssignedAccess::IProfileOperationBuilder * *,Windows::Internal::AssignedAccess::ApplyOption &&,std::wstring const &)
0x180033c8c  mov     rcx, [rbp+5Fh]; this
0x180033c90  test    eax, eax
0x180033c92  jns     short loc_180033CA9
0x180033c94  mov     r9d, eax; char *
0x180033c97  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033c9e  mov     edx, 16Dh; void *
0x180033ca3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033ca9  mov     rdx, [rbp+57h+var_98]; struct Windows::Internal::AssignedAccess::IProfileOperation *
0x180033cad  mov     rcx, rdi; this
0x180033cb0  call    ?Add@CompositeOperation@AssignedAccess@Internal@Windows@@QEAAJPEAUIProfileOperation@234@@Z; Windows::Internal::AssignedAccess::CompositeOperation::Add(Windows::Internal::AssignedAccess::IProfileOperation *)
0x180033cb5  mov     rcx, [rbp+5Fh]; this
0x180033cb9  test    eax, eax
0x180033cbb  jns     short loc_180033CD2
0x180033cbd  mov     r9d, eax; char *
0x180033cc0  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180033cc7  mov     edx, 16Eh; void *
0x180033ccc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033cd2  mov     [rbp+57h+var_88], 0
0x180033cda  lea     rcx, [rbp+57h+var_98]
0x180033cde  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180033ce3  nop
0x180033ce4  lea     rcx, [rbp+57h+var_88]
0x180033ce8  call    ??1?$com_ptr_t@VRegistryKeyOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::AssignedAccess::RegistryKeyOperation,wil::err_exception_policy>(void)
0x180033ced  mov     rax, rdi
0x180033cf0  mov     rcx, [rbp+57h+var_20]
0x180033cf4  xor     rcx, rsp; StackCookie
0x180033cf7  call    __security_check_cookie
0x180033cfc  lea     r11, [rsp+0C0h+var_10]
0x180033d04  mov     rbx, [r11+28h]
0x180033d08  mov     rsi, [r11+30h]
0x180033d0c  mov     rsp, r11
0x180033d0f  pop     r14
0x180033d11  pop     rdi
0x180033d12  pop     rbp
0x180033d13  retn
```
