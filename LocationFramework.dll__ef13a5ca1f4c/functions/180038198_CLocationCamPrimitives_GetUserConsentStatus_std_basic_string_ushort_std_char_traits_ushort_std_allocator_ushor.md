# CLocationCamPrimitives::GetUserConsentStatus(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x180038198`
- end: `0x1800385d4`
- name: `?GetUserConsentStatus@CLocationCamPrimitives@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `1084`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d690`

## callees

- `0x180012310`
- `0x180038198`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800bd60c`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003826f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800382f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800385c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003826f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800382f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800385c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800381e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800381e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038282`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038307`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038211`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038211`

## string_xrefs

- `0x180038463`: `GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager).Get(), &consentManagerStatics)`
- `0x1800383e1`: `consentManager->GetUserGlobalConsent(StringReference(userSidString.c_str()).Get(), &consent)`
- `0x18003854f`: `consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)`
- `0x1800381e1`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationCamPrimitives::GetUserConsentStatus(const WCHAR *sourceString, bool *a2)
{
  PCWSTR v3; // rdi
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // r12
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // r13
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rsi
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64 *); // r15
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  wil::details *v31; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  __int64 v35; // [rsp+58h] [rbp-28h] BYREF
  __int64 v36; // [rsp+60h] [rbp-20h] BYREF
  int v37; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+B8h] [rbp+38h]

  v3 = sourceString;
  if ( !*((_QWORD *)sourceString + 2) )
    return 2147549183LL;
  v34 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
         0x45u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v34);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v31) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetUserConsentStatus",
      "GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentM"
      "anager).Get(), &consentManagerStatics)",
      v31,
      (int)string);
    v24 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v6;
  }
  v35 = 0;
  v7 = v34;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v34 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( c_szCapabilityLocation[v10] );
  if ( v10 > 0xFFFFFFFF )
  {
    LODWORD(v10) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_szCapabilityLocation, v10, &hstringHeader, &string);
  v11 = v8(v7, string, &v35);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v36 = 0;
    v13 = v35;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v35 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(v3) )
      v3 = *(PCWSTR *)v3;
    do
      ++v9;
    while ( v3[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(v3, v9, &hstringHeader, &string);
    v15 = v14(v13, string, &v36);
    v6 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v31) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
        "CLocationCamPrimitives::GetUserConsentStatus",
        "consentManager->GetUserGlobalConsent(StringReference(userSidString.c_str()).Get(), &consent)",
        v31,
        (int)string);
      v21 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    else
    {
      if ( !v36 )
      {
        *a2 = 1;
        v25 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        goto LABEL_22;
      }
      v37 = 2;
      v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 88LL))(v36, &v37);
      v6 = v16;
      if ( v16 >= 0 )
      {
        *a2 = v37 == 1;
        v17 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v18 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
LABEL_22:
        v19 = v34;
        if ( v34 )
        {
          v34 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        return 0;
      }
      LODWORD(v31) = v16;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
        "CLocationCamPrimitives::GetUserConsentStatus",
        "consent->get_Value(&consentValue)",
        v31,
        (int)string);
      v26 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v27 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    return v6;
  }
  LODWORD(v31) = v11;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x6E,
    (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
    "CLocationCamPrimitives::GetUserConsentStatus",
    "consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)",
    v31,
    (int)string);
  v29 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return v12;
}

```

## disassembly

```asm
0x180038198  mov     [rsp-38h+arg_10], rbx
0x18003819d  push    rbp
0x18003819e  push    rsi
0x18003819f  push    rdi
0x1800381a0  push    r12
0x1800381a2  push    r13
0x1800381a4  push    r14
0x1800381a6  push    r15
0x1800381a8  mov     rbp, rsp
0x1800381ab  sub     rsp, 80h
0x1800381b2  mov     rax, cs:__security_cookie
0x1800381b9  xor     rax, rsp
0x1800381bc  mov     [rbp+var_10], rax
0x1800381c0  mov     r14, rdx
0x1800381c3  mov     rdi, rcx
0x1800381c6  xor     esi, esi
0x1800381c8  cmp     [rcx+10h], rsi
0x1800381cc  jz      loc_1800385AF
0x1800381d2  mov     [rbp+var_30], rsi
0x1800381d6  lea     r9, [rbp+string]; string
0x1800381da  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800381de  lea     edx, [rsi+45h]; length
0x1800381e1  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x1800381e8  call    cs:__imp_WindowsCreateStringReference
0x1800381ee  test    eax, eax
0x1800381f0  js      loc_1800385B9
0x1800381f6  mov     rbx, [rbp+string]
0x1800381fa  lea     rcx, [rbp+var_30]
0x1800381fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038203  lea     r8, [rbp+var_30]
0x180038207  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x18003820e  mov     rcx, rbx
0x180038211  call    cs:__imp_RoGetActivationFactory
0x180038217  mov     ebx, eax
0x180038219  test    eax, eax
0x18003821b  js      loc_18003845B
0x180038221  mov     [rbp+var_28], rsi
0x180038225  mov     r12, [rbp+var_30]
0x180038229  mov     rax, [r12]
0x18003822d  mov     r13, [rax+30h]
0x180038231  lea     rcx, [rbp+var_28]
0x180038235  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003823a  mov     r15, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180038241  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038245  mov     rsi, rbx
0x180038248  xor     eax, eax
0x18003824a  inc     rsi
0x18003824d  cmp     [r15+rsi*2], ax
0x180038252  jnz     short loc_18003824A
0x180038254  mov     eax, 0FFFFFFFFh
0x180038259  cmp     rsi, rax
0x18003825c  jbe     short loc_180038275
0x18003825e  mov     esi, eax
0x180038260  xor     r9d, r9d; lpArguments
0x180038263  xor     r8d, r8d; nNumberOfArguments
0x180038266  lea     edx, [r9+1]; dwExceptionFlags
0x18003826a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003826f  call    cs:__imp_RaiseException
0x180038275  lea     r9, [rbp+string]; string
0x180038279  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003827d  mov     edx, esi; length
0x18003827f  mov     rcx, r15; sourceString
0x180038282  call    cs:__imp_WindowsCreateStringReference
0x180038288  lea     r8, [rbp+var_28]
0x18003828c  mov     rdx, [rbp+string]
0x180038290  mov     rcx, r12
0x180038293  mov     rax, r13
0x180038296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003829b  mov     esi, eax
0x18003829d  xor     r12d, r12d
0x1800382a0  test    eax, eax
0x1800382a2  js      loc_180038547
0x1800382a8  mov     [rbp+var_20], r12
0x1800382ac  mov     rsi, [rbp+var_28]
0x1800382b0  mov     rax, [rsi]
0x1800382b3  mov     r15, [rax+38h]
0x1800382b7  lea     rcx, [rbp+var_20]
0x1800382bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800382c0  mov     rcx, rdi
0x1800382c3  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x1800382c8  test    al, al
0x1800382ca  jz      short loc_1800382CF
0x1800382cc  mov     rdi, [rdi]
0x1800382cf  inc     rbx
0x1800382d2  cmp     [rdi+rbx*2], r12w
0x1800382d7  jnz     short loc_1800382CF
0x1800382d9  mov     eax, 0FFFFFFFFh
0x1800382de  cmp     rbx, rax
0x1800382e1  jbe     short loc_1800382FA
0x1800382e3  mov     ebx, eax
0x1800382e5  xor     r9d, r9d; lpArguments
0x1800382e8  xor     r8d, r8d; nNumberOfArguments
0x1800382eb  lea     edx, [r9+1]; dwExceptionFlags
0x1800382ef  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800382f4  call    cs:__imp_RaiseException
0x1800382fa  lea     r9, [rbp+string]; string
0x1800382fe  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180038302  mov     edx, ebx; length
0x180038304  mov     rcx, rdi; sourceString
0x180038307  call    cs:__imp_WindowsCreateStringReference
0x18003830d  lea     r8, [rbp+var_20]
0x180038311  mov     rdx, [rbp+string]
0x180038315  mov     rcx, rsi
0x180038318  mov     rax, r15
0x18003831b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038320  mov     ebx, eax
0x180038322  test    eax, eax
0x180038324  js      loc_1800383D9
0x18003832a  mov     rcx, [rbp+var_20]
0x18003832e  test    rcx, rcx
0x180038331  jz      loc_1800384A4
0x180038337  mov     [rbp+var_18], 2
0x18003833e  mov     rax, [rcx]
0x180038341  lea     rdx, [rbp+var_18]
0x180038345  mov     rax, [rax+58h]
0x180038349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003834e  mov     ebx, eax
0x180038350  test    eax, eax
0x180038352  js      loc_1800384C7
0x180038358  cmp     [rbp+var_18], 1
0x18003835c  setz    al
0x18003835f  mov     [r14], al
0x180038362  mov     rcx, [rbp+var_20]
0x180038366  test    rcx, rcx
0x180038369  jz      short loc_18003837C
0x18003836b  mov     [rbp+var_20], r12
0x18003836f  mov     rax, [rcx]
0x180038372  mov     rax, [rax+10h]
0x180038376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003837b  nop
0x18003837c  mov     rcx, [rbp+var_28]
0x180038380  test    rcx, rcx
0x180038383  jz      short loc_180038396
0x180038385  mov     [rbp+var_28], r12
0x180038389  mov     rax, [rcx]
0x18003838c  mov     rax, [rax+10h]
0x180038390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038395  nop
0x180038396  mov     rcx, [rbp+var_30]
0x18003839a  test    rcx, rcx
0x18003839d  jz      short loc_1800383B0
0x18003839f  mov     [rbp+var_30], r12
0x1800383a3  mov     rax, [rcx]
0x1800383a6  mov     rax, [rax+10h]
0x1800383aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383af  nop
0x1800383b0  xor     eax, eax
0x1800383b2  mov     rcx, [rbp+var_10]
0x1800383b6  xor     rcx, rsp; StackCookie
0x1800383b9  call    __security_check_cookie
0x1800383be  mov     rbx, [rsp+80h+arg_10]
0x1800383c6  add     rsp, 80h
0x1800383cd  pop     r15
0x1800383cf  pop     r14
0x1800383d1  pop     r13
0x1800383d3  pop     r12
0x1800383d5  pop     rdi
0x1800383d6  pop     rsi
0x1800383d7  pop     rbp
0x1800383d8  retn
0x1800383d9  mov     rcx, [rbp+38h]; this
0x1800383dd  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x1800383e1  lea     rax, aConsentmanager_2; "consentManager->GetUserGlobalConsent(St"...
0x1800383e8  mov     [rsp+80h+var_60], rax; char *
0x1800383ed  lea     r9, aClocationcampr_0; "CLocationCamPrimitives::GetUserConsentS"...
0x1800383f4  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800383fb  mov     edx, 71h ; 'q'; void *
0x180038400  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038405  nop
0x180038406  mov     rcx, [rbp+var_20]
0x18003840a  test    rcx, rcx
0x18003840d  jz      short loc_180038420
0x18003840f  mov     [rbp+var_20], r12
0x180038413  mov     rax, [rcx]
0x180038416  mov     rax, [rax+10h]
0x18003841a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003841f  nop
0x180038420  mov     rcx, [rbp+var_28]
0x180038424  test    rcx, rcx
0x180038427  jz      short loc_18003843A
0x180038429  mov     [rbp+var_28], r12
0x18003842d  mov     rax, [rcx]
0x180038430  mov     rax, [rax+10h]
0x180038434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038439  nop
0x18003843a  mov     rcx, [rbp+var_30]
0x18003843e  test    rcx, rcx
0x180038441  jz      short loc_180038454
0x180038443  mov     [rbp+var_30], r12
0x180038447  mov     rax, [rcx]
0x18003844a  mov     rax, [rax+10h]
0x18003844e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038453  nop
0x180038454  mov     eax, ebx
0x180038456  jmp     loc_1800383B2
0x18003845b  mov     rcx, [rbp+38h]; this
0x18003845f  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x180038463  lea     rax, aGetactivationf; "GetActivationFactory( StringReference(R"...
0x18003846a  mov     [rsp+80h+var_60], rax; char *
0x18003846f  lea     r9, aClocationcampr_0; "CLocationCamPrimitives::GetUserConsentS"...
0x180038476  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x18003847d  mov     edx, 6Bh ; 'k'; void *
0x180038482  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038487  nop
0x180038488  mov     rcx, [rbp+var_30]
0x18003848c  test    rcx, rcx
0x18003848f  jz      short loc_1800384A2
0x180038491  mov     [rbp+var_30], rsi
0x180038495  mov     rax, [rcx]
0x180038498  mov     rax, [rax+10h]
0x18003849c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384a1  nop
0x1800384a2  jmp     short loc_180038454
0x1800384a4  mov     byte ptr [r14], 1
0x1800384a8  mov     rcx, [rbp+var_28]
0x1800384ac  test    rcx, rcx
0x1800384af  jz      short loc_1800384C2
0x1800384b1  mov     [rbp+var_28], r12
0x1800384b5  mov     rax, [rcx]
0x1800384b8  mov     rax, [rax+10h]
0x1800384bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384c1  nop
0x1800384c2  jmp     loc_180038396
0x1800384c7  mov     rcx, [rbp+38h]; this
0x1800384cb  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x1800384cf  lea     rax, aConsentGetValu; "consent->get_Value(&consentValue)"
0x1800384d6  mov     [rsp+80h+var_60], rax; char *
0x1800384db  lea     r9, aClocationcampr_0; "CLocationCamPrimitives::GetUserConsentS"...
0x1800384e2  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800384e9  mov     edx, 7Ch ; '|'; void *
0x1800384ee  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800384f3  nop
0x1800384f4  mov     rcx, [rbp+var_20]
0x1800384f8  test    rcx, rcx
0x1800384fb  jz      short loc_18003850E
0x1800384fd  mov     [rbp+var_20], r12
0x180038501  mov     rax, [rcx]
0x180038504  mov     rax, [rax+10h]
0x180038508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003850d  nop
0x18003850e  mov     rcx, [rbp+var_28]
0x180038512  test    rcx, rcx
0x180038515  jz      short loc_180038528
0x180038517  mov     [rbp+var_28], r12
0x18003851b  mov     rax, [rcx]
0x18003851e  mov     rax, [rax+10h]
0x180038522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038527  nop
0x180038528  mov     rcx, [rbp+var_30]
0x18003852c  test    rcx, rcx
0x18003852f  jz      short loc_180038542
0x180038531  mov     [rbp+var_30], r12
0x180038535  mov     rax, [rcx]
0x180038538  mov     rax, [rax+10h]
0x18003853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038541  nop
0x180038542  jmp     loc_180038454
0x180038547  mov     rcx, [rbp+38h]; this
0x18003854b  mov     dword ptr [rsp+80h+var_58], esi; wil::details *
0x18003854f  lea     rax, aConsentmanager_0; "consentManagerStatics->Create(GetLocati"...
0x180038556  mov     [rsp+80h+var_60], rax; char *
0x18003855b  lea     r9, aClocationcampr_0; "CLocationCamPrimitives::GetUserConsentS"...
0x180038562  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038569  mov     edx, 6Eh ; 'n'; void *
0x18003856e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038573  nop
0x180038574  mov     rcx, [rbp+var_28]
0x180038578  test    rcx, rcx
0x18003857b  jz      short loc_18003858E
0x18003857d  mov     [rbp+var_28], r12
0x180038581  mov     rax, [rcx]
0x180038584  mov     rax, [rax+10h]
0x180038588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003858d  nop
0x18003858e  mov     rcx, [rbp+var_30]
0x180038592  test    rcx, rcx
0x180038595  jz      short loc_1800385A8
0x180038597  mov     [rbp+var_30], r12
0x18003859b  mov     rax, [rcx]
0x18003859e  mov     rax, [rax+10h]
0x1800385a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385a7  nop
0x1800385a8  mov     eax, esi
0x1800385aa  jmp     loc_1800383B2
0x1800385af  mov     eax, 8000FFFFh
0x1800385b4  jmp     loc_1800383B2
0x1800385b9  xor     r9d, r9d; lpArguments
0x1800385bc  xor     r8d, r8d; nNumberOfArguments
0x1800385bf  lea     edx, [r9+1]; dwExceptionFlags
0x1800385c3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800385c8  call    cs:__imp_RaiseException
0x1800385ce  jmp     loc_1800381F6
```
