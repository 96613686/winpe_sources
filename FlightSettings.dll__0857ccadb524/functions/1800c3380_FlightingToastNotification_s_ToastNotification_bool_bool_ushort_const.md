# FlightingToastNotification::s_ToastNotification(bool,bool,ushort const *)

- ea: `0x1800c3380`
- end: `0x1800c3626`
- name: `?s_ToastNotification@FlightingToastNotification@@KAJ_N0PEBG@Z`
- size: `678`
- prototype: `__int64 __fastcall(bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ac430`

## callees

- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18002299c`
- `0x180085e88`
- `0x18008a2fc`
- `0x18008aaf0`
- `0x1800960cc`
- `0x1800c3380`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c3400`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x1800c3400`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c3427`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c3493`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c3427`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c3493`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c33b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c33b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c3610`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c3610`

## string_xrefs

- `0x1800c33dc`: `onecore\base\flighting\flightsettings\broker\lib\flightingtoastnotification.cpp`
- `0x1800c3452`: `onecore\base\flighting\flightsettings\broker\lib\flightingtoastnotification.cpp`
- `0x1800c35dc`: `onecore\base\flighting\flightsettings\broker\lib\flightingtoastnotification.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FlightingToastNotification::s_ToastNotification(__int64 a1, bool a2, const unsigned __int16 *a3)
{
  int v3; // ebx
  HRESULT active; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-79h]
  __int64 v10; // [rsp+90h] [rbp-9h] BYREF
  LPVOID v11; // [rsp+98h] [rbp-1h] BYREF
  HKEY v12; // [rsp+A0h] [rbp+7h] BYREF
  int v13; // [rsp+A8h] [rbp+Fh]
  unsigned __int16 *v14; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+1Fh]
  __int64 v16; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  bool v18; // [rsp+108h] [rbp+6Fh] BYREF
  int v19; // [rsp+118h] [rbp+7Fh]

  v18 = a2;
  v19 = 0;
  v3 = 0;
  v11 = 0;
  v10 = 0;
  active = CoInitializeEx(0, 0);
  if ( active >= 0 )
  {
    v3 = 1;
    active = 0;
  }
  if ( active < 0 )
  {
    v5 = 103;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightingtoastnotification.cpp",
      (const char *)(unsigned int)active,
      ppv);
    goto LABEL_23;
  }
  v18 = 0;
  FlightSettingsAPICommon::IsLocalSystem(&v18);
  if ( !v18 && !(unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    active = CoCreateInstance(
               &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
               0,
               4u,
               &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
               &v11);
    if ( active < 0 )
    {
      v5 = 136;
      goto LABEL_5;
    }
    goto LABEL_16;
  }
  v18 = 0;
  active = ImpersonationHelper::ImpersonateActiveUser((struct UstCommon::CImpersonator *)&v18);
  if ( active < 0 )
  {
    v6 = 120;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightingtoastnotification.cpp",
      (const char *)(unsigned int)active,
      ppv);
    UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v18);
    goto LABEL_23;
  }
  active = CoCreateInstance(
             &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
             0,
             0x100004u,
             &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
             &v11);
  if ( active < 0 )
  {
    v6 = 127;
    goto LABEL_12;
  }
  UstCommon::CImpersonator::~CImpersonator((UstCommon::CImpersonator *)&v18);
LABEL_16:
  active = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, &v10);
  if ( active < 0 )
  {
    v5 = 140;
    goto LABEL_5;
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
  v15 = -1;
  v16 = -1;
  v12 = HKEY_LOCAL_MACHINE;
  if ( (int)FSRegUtils::GetRegString(&v12, L"Software\\Microsoft\\SystemSettings", L"SystemSettingsAUMID", &v14, 0) < 0 )
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
      &v14,
      L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
      -1);
  (*(void (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD, _QWORD, const BYTE *))(*(_QWORD *)v10 + 80LL))(
    v10,
    L"NonImmersivePackage",
    v14,
    0,
    0,
    L"FlightSettings");
  v12 = 0;
  v13 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v10 + 64LL))(
         v10,
         L"NonImmersivePackage",
         v14,
         0);
  active = v7;
  if ( v7 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\flightingtoastnotification.cpp",
      (const char *)(unsigned int)v7,
      1);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
LABEL_23:
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v10);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v11);
  if ( v3 )
    CoUninitialize();
  return (unsigned int)active;
}

```

## disassembly

```asm
0x1800c3380  mov     [rsp-8+arg_8], dl
0x1800c3384  mov     byte ptr [rsp-8+arg_0], cl
0x1800c3388  push    rbp
0x1800c3389  push    rbx
0x1800c338a  push    rsi
0x1800c338b  push    rdi
0x1800c338c  push    r14
0x1800c338e  lea     rbp, [rsp-37h]
0x1800c3393  sub     rsp, 0D0h
0x1800c339a  mov     rsi, r8
0x1800c339d  xor     r14d, r14d
0x1800c33a0  mov     [rbp+57h+arg_18], r14d
0x1800c33a4  mov     ebx, r14d
0x1800c33a7  mov     [rbp+57h+arg_0], ebx
0x1800c33aa  mov     [rbp+57h+var_58], r14
0x1800c33ae  mov     [rbp+57h+var_60], r14
0x1800c33b2  xor     edx, edx; dwCoInit
0x1800c33b4  xor     ecx, ecx; pvReserved
0x1800c33b6  call    cs:__imp_CoInitializeEx
0x1800c33bc  mov     edi, eax
0x1800c33be  test    eax, eax
0x1800c33c0  js      short loc_1800C33CC
0x1800c33c2  lea     ebx, [r14+1]
0x1800c33c6  mov     [rbp+57h+arg_0], ebx
0x1800c33c9  mov     edi, r14d
0x1800c33cc  test    edi, edi
0x1800c33ce  jns     short loc_1800C33ED
0x1800c33d0  mov     edx, 67h ; 'g'; void *
0x1800c33d5  mov     rcx, [rbp+5Fh]; this
0x1800c33d9  mov     r9d, edi; char *
0x1800c33dc  lea     r8, aOnecoreBaseFli_71; "onecore\\base\\flighting\\flightsetting"...
0x1800c33e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c33e8  jmp     loc_1800C35F8
0x1800c33ed  mov     [rbp+57h+arg_8], r14b
0x1800c33f1  lea     rcx, [rbp+57h+arg_8]; bool *
0x1800c33f5  call    ?IsLocalSystem@FlightSettingsAPICommon@@SAJPEA_N@Z; FlightSettingsAPICommon::IsLocalSystem(bool *)
0x1800c33fa  cmp     [rbp+57h+arg_8], r14b
0x1800c33fe  jnz     short loc_1800C343A
0x1800c3400  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x1800c3406  test    al, al
0x1800c3408  jnz     short loc_1800C343A
0x1800c340a  lea     rax, [rbp+57h+var_58]
0x1800c340e  mov     [rsp+0F0h+ppv], rax; ppv
0x1800c3413  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800c341a  xor     edx, edx; pUnkOuter
0x1800c341c  lea     r8d, [rdx+4]; dwClsContext
0x1800c3420  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x1800c3427  call    cs:__imp_CoCreateInstance
0x1800c342d  mov     edi, eax
0x1800c342f  test    eax, eax
0x1800c3431  jns     short loc_1800C34AF
0x1800c3433  mov     edx, 88h
0x1800c3438  jmp     short loc_1800C33D5
0x1800c343a  mov     [rbp+57h+arg_8], r14b
0x1800c343e  lea     rcx, [rbp+57h+arg_8]; this
0x1800c3442  call    ?ImpersonateActiveUser@ImpersonationHelper@@SAJPEAVCImpersonator@UstCommon@@@Z; ImpersonationHelper::ImpersonateActiveUser(UstCommon::CImpersonator *)
0x1800c3447  mov     edi, eax
0x1800c3449  test    eax, eax
0x1800c344b  jns     short loc_1800C3474
0x1800c344d  mov     edx, 78h ; 'x'; void *
0x1800c3452  lea     r8, aOnecoreBaseFli_71; "onecore\\base\\flighting\\flightsetting"...
0x1800c3459  mov     r9d, edi; char *
0x1800c345c  mov     rcx, [rbp+5Fh]; this
0x1800c3460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3465  nop
0x1800c3466  lea     rcx, [rbp+57h+arg_8]; this
0x1800c346a  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x1800c346f  jmp     loc_1800C35F8
0x1800c3474  lea     rax, [rbp+57h+var_58]
0x1800c3478  mov     [rsp+0F0h+ppv], rax; ppv
0x1800c347d  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1800c3484  xor     edx, edx; pUnkOuter
0x1800c3486  mov     r8d, 100004h; dwClsContext
0x1800c348c  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x1800c3493  call    cs:__imp_CoCreateInstance
0x1800c3499  mov     edi, eax
0x1800c349b  test    eax, eax
0x1800c349d  jns     short loc_1800C34A6
0x1800c349f  mov     edx, 7Fh
0x1800c34a4  jmp     short loc_1800C3452
0x1800c34a6  lea     rcx, [rbp+57h+arg_8]; this
0x1800c34aa  call    ??1CImpersonator@UstCommon@@QEAA@XZ; UstCommon::CImpersonator::~CImpersonator(void)
0x1800c34af  mov     rcx, [rbp+57h+var_58]
0x1800c34b3  mov     rax, [rcx]
0x1800c34b6  lea     rdx, [rbp+57h+var_60]
0x1800c34ba  mov     rax, [rax+18h]
0x1800c34be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c34c3  mov     edi, eax
0x1800c34c5  test    eax, eax
0x1800c34c7  jns     short loc_1800C34D3
0x1800c34c9  mov     edx, 8Ch
0x1800c34ce  jmp     loc_1800C33D5
0x1800c34d3  mov     [rbp+57h+var_40], r14
0x1800c34d7  mov     [rbp+57h+var_38], r14
0x1800c34db  mov     [rbp+57h+var_30], r14
0x1800c34df  lea     rcx, [rbp+57h+var_40]
0x1800c34e3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c34e8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c34ec  mov     [rbp+57h+var_38], rdi
0x1800c34f0  mov     [rbp+57h+var_30], rdi
0x1800c34f4  mov     [rbp+57h+var_50], 0FFFFFFFF80000002h
0x1800c34fc  mov     [rsp+0F0h+ppv], r14; unsigned __int16 *
0x1800c3501  lea     r9, [rbp+57h+var_40]; unsigned __int16 **
0x1800c3505  lea     r8, aSystemsettings_2; "SystemSettingsAUMID"
0x1800c350c  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\SystemSettings"
0x1800c3513  lea     rcx, [rbp+57h+var_50]; HKEY *
0x1800c3517  call    ?GetRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@PEBG1PEAPEAG1@Z; FSRegUtils::GetRegString(HKEY__ * const &,ushort const *,ushort const *,ushort * *,ushort const *)
0x1800c351c  test    eax, eax
0x1800c351e  jns     short loc_1800C3533
0x1800c3520  mov     r8, rdi
0x1800c3523  lea     rdx, ?c_szPCSettingsAppID@@3QBGB; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1800c352a  lea     rcx, [rbp+57h+var_40]
0x1800c352e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800c3533  mov     rcx, [rbp+57h+var_60]
0x1800c3537  mov     rax, [rcx]
0x1800c353a  lea     rdi, pbData; "FlightSettings"
0x1800c3541  mov     [rsp+0F0h+var_C8], rdi
0x1800c3546  mov     [rsp+0F0h+ppv], r14
0x1800c354b  xor     r9d, r9d
0x1800c354e  mov     r8, [rbp+57h+var_40]
0x1800c3552  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x1800c3559  mov     rax, [rax+50h]
0x1800c355d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3562  mov     rcx, [rbp+57h+var_60]
0x1800c3566  mov     [rbp+57h+var_50], r14
0x1800c356a  mov     [rbp+57h+var_48], r14d
0x1800c356e  mov     rax, [rcx]
0x1800c3571  lea     rdx, [rbp+57h+arg_18]
0x1800c3575  mov     [rsp+0F0h+var_78], rdx
0x1800c357a  mov     [rsp+0F0h+var_80], r14d
0x1800c357f  mov     [rsp+0F0h+var_88], r14
0x1800c3584  mov     [rsp+0F0h+var_90], r14
0x1800c3589  mov     [rsp+0F0h+var_98], r14
0x1800c358e  mov     [rsp+0F0h+var_A0], r14d
0x1800c3593  mov     [rsp+0F0h+var_A8], r14d
0x1800c3598  lea     r8, [rbp+57h+var_50]
0x1800c359c  mov     [rsp+0F0h+var_B0], r8
0x1800c35a1  mov     [rsp+0F0h+var_B8], rdi
0x1800c35a6  mov     [rsp+0F0h+var_C0], rdi
0x1800c35ab  mov     [rsp+0F0h+var_C8], rsi
0x1800c35b0  mov     dword ptr [rsp+0F0h+ppv], 1; int
0x1800c35b8  xor     r9d, r9d
0x1800c35bb  mov     r8, [rbp+57h+var_40]
0x1800c35bf  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x1800c35c6  mov     rax, [rax+40h]
0x1800c35ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c35cf  mov     edi, eax
0x1800c35d1  test    eax, eax
0x1800c35d3  jns     short loc_1800C35EE
0x1800c35d5  mov     rcx, [rbp+5Fh]; this
0x1800c35d9  mov     r9d, eax; char *
0x1800c35dc  lea     r8, aOnecoreBaseFli_71; "onecore\\base\\flighting\\flightsetting"...
0x1800c35e3  mov     edx, 0BEh; void *
0x1800c35e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c35ed  nop
0x1800c35ee  lea     rcx, [rbp+57h+var_40]
0x1800c35f2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c35f7  nop
0x1800c35f8  lea     rcx, [rbp+57h+var_60]
0x1800c35fc  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800c3601  nop
0x1800c3602  lea     rcx, [rbp+57h+var_58]
0x1800c3606  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800c360b  nop
0x1800c360c  test    ebx, ebx
0x1800c360e  jz      short loc_1800C3616
0x1800c3610  call    cs:__imp_CoUninitialize
0x1800c3616  mov     eax, edi
0x1800c3618  add     rsp, 0D0h
0x1800c361f  pop     r14
0x1800c3621  pop     rdi
0x1800c3622  pop     rsi
0x1800c3623  pop     rbx
0x1800c3624  pop     rbp
0x1800c3625  retn
```
