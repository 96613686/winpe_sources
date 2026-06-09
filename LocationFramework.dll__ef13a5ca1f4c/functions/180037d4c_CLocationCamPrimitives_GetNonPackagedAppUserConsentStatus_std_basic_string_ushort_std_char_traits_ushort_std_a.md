# CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x180037d4c`
- end: `0x180038191`
- name: `?GetNonPackagedAppUserConsentStatus@CLocationCamPrimitives@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `1093`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d690`
- `0x1800d2810`

## callees

- `0x180012310`
- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020c64`
- `0x180037d4c`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037e27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037ed8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037f28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800380f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037e27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037ed8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180037f28`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800380f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037e3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037e3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180037f3b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180037dca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180037dca`

## string_xrefs

- `0x180038020`: `GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager).Get(), &consentManagerStatics)`
- `0x18003810c`: `consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)`
- `0x180037d9a`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x18003813a`: `consentManager->GetUserAppConsent( StringReference(userSidString.c_str()).Get(), StringReference(std::wstring(L"NonPackaged").c_str()).Get(), &consent)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus(__int64 a1, bool *a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // r15
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // r13
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rbx
  __int64 v11; // r15
  __int64 (__fastcall *v12)(__int64, HSTRING, HSTRING, __int64 *); // r13
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  const WCHAR *v16; // r14
  unsigned __int64 v17; // rbx
  HSTRING v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rax
  const WCHAR *v21; // rbx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  wil::details *v31; // [rsp+28h] [rbp-71h]
  HSTRING hstringHeader[4]; // [rsp+30h] [rbp-69h] BYREF
  HSTRING string; // [rsp+50h] [rbp-49h] BYREF
  HSTRING_HEADER v34; // [rsp+58h] [rbp-41h] BYREF
  HSTRING v35; // [rsp+70h] [rbp-29h] BYREF
  HSTRING_HEADER v36; // [rsp+78h] [rbp-21h] BYREF
  __int64 v37; // [rsp+90h] [rbp-9h] BYREF
  __int64 v38; // [rsp+98h] [rbp-1h] BYREF
  __int64 v39; // [rsp+A0h] [rbp+7h] BYREF
  int v40; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a2 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
    return 2147549183LL;
  v37 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
         0x45u,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = hstringHeader[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v37);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v31) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus",
      "GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentM"
      "anager).Get(), &consentManagerStatics)",
      v31,
      (int)hstringHeader[0]);
    v27 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return (unsigned int)v6;
  }
  v39 = 0;
  v7 = v37;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v37 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
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
  WindowsCreateStringReference(c_szCapabilityLocation, v10, (HSTRING_HEADER *)&hstringHeader[1], hstringHeader);
  v6 = v8(v7, hstringHeader[0], &v39);
  if ( v6 < 0 )
  {
    LODWORD(v31) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus",
      "consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)",
      v31,
      (int)hstringHeader[0]);
LABEL_42:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    return (unsigned int)v6;
  }
  v38 = 0;
  v11 = v39;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v39 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  memset(hstringHeader, 0, sizeof(hstringHeader));
  v13 = std::_WChar_traits<unsigned short>::length(L"NonPackaged");
  std::wstring::_Construct<1,unsigned short const *>(hstringHeader, v14, v13);
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(hstringHeader, v15);
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    LODWORD(v17) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v16, v17, &v34, &string);
  v18 = string;
  v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v19);
  v21 = (const WCHAR *)v20;
  do
    ++v9;
  while ( *(_WORD *)(v20 + 2 * v9) );
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(v9) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v21, v9, &v36, &v35);
  v6 = v12(v11, v35, v18, &v38);
  std::wstring::_Tidy_deallocate(hstringHeader);
  if ( v6 < 0 )
  {
    LODWORD(v31) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus",
      "consentManager->GetUserAppConsent( StringReference(userSidString.c_str()).Get(), StringReference(std::wstring(L\"N"
      "onPackaged\").c_str()).Get(), &consent)",
      v31,
      (int)hstringHeader[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    goto LABEL_42;
  }
  if ( !v38 )
  {
    *a2 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v6 = 0;
    goto LABEL_42;
  }
  v40 = 2;
  v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 88LL))(v38, &v40);
  v6 = v22;
  if ( v22 < 0 )
  {
    LODWORD(v31) = v22;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xF2,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetNonPackagedAppUserConsentStatus",
      "consent->get_Value(&consentValue)",
      v31,
      (int)hstringHeader[0]);
    v28 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return (unsigned int)v6;
  }
  *a2 = v40 == 1;
  v23 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180037d4c  mov     [rsp-8+arg_10], rbx
0x180037d51  push    rbp
0x180037d52  push    rsi
0x180037d53  push    rdi
0x180037d54  push    r12
0x180037d56  push    r13
0x180037d58  push    r14
0x180037d5a  push    r15
0x180037d5c  lea     rbp, [rsp-27h]
0x180037d61  sub     rsp, 0C0h
0x180037d68  mov     rax, cs:__security_cookie
0x180037d6f  xor     rax, rsp
0x180037d72  mov     [rbp+57h+var_40], rax
0x180037d76  mov     rsi, rdx
0x180037d79  mov     r12, rcx
0x180037d7c  xor     edi, edi
0x180037d7e  mov     [rdx], dil
0x180037d81  cmp     [rcx+10h], rdi
0x180037d85  jz      loc_180038063
0x180037d8b  mov     [rbp+57h+var_60], rdi
0x180037d8f  lea     r9, [rbp+57h+hstringHeader]; string
0x180037d93  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180037d97  lea     edx, [rdi+45h]; length
0x180037d9a  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180037da1  call    cs:__imp_WindowsCreateStringReference
0x180037da7  test    eax, eax
0x180037da9  js      loc_1800380EA
0x180037daf  mov     rbx, qword ptr [rbp+57h+hstringHeader]
0x180037db3  lea     rcx, [rbp+57h+var_60]
0x180037db7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037dbc  lea     r8, [rbp+57h+var_60]
0x180037dc0  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x180037dc7  mov     rcx, rbx
0x180037dca  call    cs:__imp_RoGetActivationFactory
0x180037dd0  mov     ebx, eax
0x180037dd2  test    eax, eax
0x180037dd4  js      loc_180038018
0x180037dda  mov     [rbp+57h+var_50], rdi
0x180037dde  mov     r15, [rbp+57h+var_60]
0x180037de2  mov     rax, [r15]
0x180037de5  mov     r13, [rax+30h]
0x180037de9  lea     rcx, [rbp+57h+var_50]
0x180037ded  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037df2  mov     r14, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180037df9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180037dfd  mov     rbx, rdi
0x180037e00  xor     eax, eax
0x180037e02  inc     rbx
0x180037e05  cmp     [r14+rbx*2], ax
0x180037e0a  jnz     short loc_180037E02
0x180037e0c  mov     eax, 0FFFFFFFFh
0x180037e11  cmp     rbx, rax
0x180037e14  jbe     short loc_180037E2D
0x180037e16  mov     ebx, eax
0x180037e18  xor     r9d, r9d; lpArguments
0x180037e1b  xor     r8d, r8d; nNumberOfArguments
0x180037e1e  lea     edx, [r9+1]; dwExceptionFlags
0x180037e22  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037e27  call    cs:__imp_RaiseException
0x180037e2d  lea     r9, [rbp+57h+hstringHeader]; string
0x180037e31  lea     r8, [rbp+57h+hstringHeader+8]; hstringHeader
0x180037e35  mov     edx, ebx; length
0x180037e37  mov     rcx, r14; sourceString
0x180037e3a  call    cs:__imp_WindowsCreateStringReference
0x180037e40  lea     r8, [rbp+57h+var_50]
0x180037e44  mov     rdx, qword ptr [rbp+57h+hstringHeader]
0x180037e48  mov     rcx, r15
0x180037e4b  mov     rax, r13
0x180037e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e53  mov     ebx, eax
0x180037e55  xor     eax, eax
0x180037e57  test    ebx, ebx
0x180037e59  js      loc_180038104
0x180037e5f  mov     [rbp+57h+var_58], rax
0x180037e63  mov     r15, [rbp+57h+var_50]
0x180037e67  mov     rax, [r15]
0x180037e6a  mov     r13, [rax+58h]
0x180037e6e  lea     rcx, [rbp+57h+var_58]
0x180037e72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180037e77  xorps   xmm0, xmm0
0x180037e7a  movups  xmmword ptr [rbp+57h+hstringHeader], xmm0
0x180037e7e  xorps   xmm1, xmm1
0x180037e81  movdqu  xmmword ptr [rbp+57h+hstringHeader+10h], xmm1
0x180037e86  lea     rcx, aNonpackaged; "NonPackaged"
0x180037e8d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180037e92  mov     r8, rax
0x180037e95  mov     rdx, rcx
0x180037e98  lea     rcx, [rbp+57h+hstringHeader]
0x180037e9c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037ea1  nop
0x180037ea2  lea     rcx, [rbp+57h+hstringHeader]
0x180037ea6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037eab  mov     r14, rax
0x180037eae  mov     rbx, rdi
0x180037eb1  xor     eax, eax
0x180037eb3  inc     rbx
0x180037eb6  cmp     [r14+rbx*2], ax
0x180037ebb  jnz     short loc_180037EB3
0x180037ebd  mov     eax, 0FFFFFFFFh
0x180037ec2  cmp     rbx, rax
0x180037ec5  jbe     short loc_180037EDE
0x180037ec7  mov     ebx, eax
0x180037ec9  xor     r9d, r9d; lpArguments
0x180037ecc  xor     r8d, r8d; nNumberOfArguments
0x180037ecf  lea     edx, [r9+1]; dwExceptionFlags
0x180037ed3  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037ed8  call    cs:__imp_RaiseException
0x180037ede  lea     r9, [rbp+57h+string]; string
0x180037ee2  lea     r8, [rbp+57h+var_98]; hstringHeader
0x180037ee6  mov     edx, ebx; length
0x180037ee8  mov     rcx, r14; sourceString
0x180037eeb  call    cs:__imp_WindowsCreateStringReference
0x180037ef1  mov     r14, [rbp+57h+string]
0x180037ef5  mov     rcx, r12
0x180037ef8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037efd  mov     rbx, rax
0x180037f00  xor     r12d, r12d
0x180037f03  inc     rdi
0x180037f06  cmp     [rax+rdi*2], r12w
0x180037f0b  jnz     short loc_180037F03
0x180037f0d  mov     eax, 0FFFFFFFFh
0x180037f12  cmp     rdi, rax
0x180037f15  jbe     short loc_180037F2E
0x180037f17  mov     edi, eax
0x180037f19  xor     r9d, r9d; lpArguments
0x180037f1c  xor     r8d, r8d; nNumberOfArguments
0x180037f1f  lea     edx, [r9+1]; dwExceptionFlags
0x180037f23  mov     ecx, 0C000000Dh; dwExceptionCode
0x180037f28  call    cs:__imp_RaiseException
0x180037f2e  lea     r9, [rbp+57h+var_80]; string
0x180037f32  lea     r8, [rbp+57h+var_78]; hstringHeader
0x180037f36  mov     edx, edi; length
0x180037f38  mov     rcx, rbx; sourceString
0x180037f3b  call    cs:__imp_WindowsCreateStringReference
0x180037f41  lea     r9, [rbp+57h+var_58]
0x180037f45  mov     r8, r14
0x180037f48  mov     rdx, [rbp+57h+var_80]
0x180037f4c  mov     rcx, r15
0x180037f4f  mov     rax, r13
0x180037f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f57  mov     ebx, eax
0x180037f59  lea     rcx, [rbp+57h+hstringHeader]
0x180037f5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037f62  test    ebx, ebx
0x180037f64  js      loc_180038132
0x180037f6a  mov     rcx, [rbp+57h+var_58]
0x180037f6e  test    rcx, rcx
0x180037f71  jz      loc_18003816A
0x180037f77  mov     [rbp+57h+var_48], 2
0x180037f7e  mov     rax, [rcx]
0x180037f81  lea     rdx, [rbp+57h+var_48]
0x180037f85  mov     rax, [rax+58h]
0x180037f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f8e  mov     ebx, eax
0x180037f90  test    eax, eax
0x180037f92  js      loc_18003806A
0x180037f98  cmp     [rbp+57h+var_48], 1
0x180037f9c  setz    al
0x180037f9f  mov     [rsi], al
0x180037fa1  mov     rcx, [rbp+57h+var_58]
0x180037fa5  test    rcx, rcx
0x180037fa8  jz      short loc_180037FBB
0x180037faa  mov     [rbp+57h+var_58], r12
0x180037fae  mov     rax, [rcx]
0x180037fb1  mov     rax, [rax+10h]
0x180037fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fba  nop
0x180037fbb  mov     rcx, [rbp+57h+var_50]
0x180037fbf  test    rcx, rcx
0x180037fc2  jz      short loc_180037FD5
0x180037fc4  mov     [rbp+57h+var_50], r12
0x180037fc8  mov     rax, [rcx]
0x180037fcb  mov     rax, [rax+10h]
0x180037fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fd4  nop
0x180037fd5  mov     rcx, [rbp+57h+var_60]
0x180037fd9  test    rcx, rcx
0x180037fdc  jz      short loc_180037FEF
0x180037fde  mov     [rbp+57h+var_60], r12
0x180037fe2  mov     rax, [rcx]
0x180037fe5  mov     rax, [rax+10h]
0x180037fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fee  nop
0x180037fef  xor     eax, eax
0x180037ff1  mov     rcx, [rbp+57h+var_40]
0x180037ff5  xor     rcx, rsp; StackCookie
0x180037ff8  call    __security_check_cookie
0x180037ffd  mov     rbx, [rsp+0F0h+arg_10]
0x180038005  add     rsp, 0C0h
0x18003800c  pop     r15
0x18003800e  pop     r14
0x180038010  pop     r13
0x180038012  pop     r12
0x180038014  pop     rdi
0x180038015  pop     rsi
0x180038016  pop     rbp
0x180038017  retn
0x180038018  mov     rcx, [rbp+5Fh]; this
0x18003801c  mov     dword ptr [rsp+0F0h+var_C8], ebx; wil::details *
0x180038020  lea     rax, aGetactivationf; "GetActivationFactory( StringReference(R"...
0x180038027  mov     [rsp+0F0h+var_D0], rax; char *
0x18003802c  lea     r9, aClocationcampr_2; "CLocationCamPrimitives::GetNonPackagedA"...
0x180038033  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x18003803a  mov     edx, 0DFh; void *
0x18003803f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038044  nop
0x180038045  mov     rcx, [rbp+57h+var_60]
0x180038049  test    rcx, rcx
0x18003804c  jz      short loc_18003805F
0x18003804e  mov     [rbp+57h+var_60], rdi
0x180038052  mov     rax, [rcx]
0x180038055  mov     rax, [rax+10h]
0x180038059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003805e  nop
0x18003805f  mov     eax, ebx
0x180038061  jmp     short loc_180037FF1
0x180038063  mov     eax, 8000FFFFh
0x180038068  jmp     short loc_180037FF1
0x18003806a  mov     rcx, [rbp+5Fh]; this
0x18003806e  mov     dword ptr [rsp+0F0h+var_C8], ebx; wil::details *
0x180038072  lea     rax, aConsentGetValu; "consent->get_Value(&consentValue)"
0x180038079  mov     [rsp+0F0h+var_D0], rax; char *
0x18003807e  lea     r9, aClocationcampr_2; "CLocationCamPrimitives::GetNonPackagedA"...
0x180038085  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x18003808c  mov     edx, 0F2h; void *
0x180038091  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038096  nop
0x180038097  mov     rcx, [rbp+57h+var_58]
0x18003809b  test    rcx, rcx
0x18003809e  jz      short loc_1800380B1
0x1800380a0  mov     [rbp+57h+var_58], r12
0x1800380a4  mov     rax, [rcx]
0x1800380a7  mov     rax, [rax+10h]
0x1800380ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380b0  nop
0x1800380b1  mov     rcx, [rbp+57h+var_50]
0x1800380b5  test    rcx, rcx
0x1800380b8  jz      short loc_1800380CB
0x1800380ba  mov     [rbp+57h+var_50], r12
0x1800380be  mov     rax, [rcx]
0x1800380c1  mov     rax, [rax+10h]
0x1800380c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380ca  nop
0x1800380cb  mov     rcx, [rbp+57h+var_60]
0x1800380cf  test    rcx, rcx
0x1800380d2  jz      short loc_1800380E5
0x1800380d4  mov     [rbp+57h+var_60], r12
0x1800380d8  mov     rax, [rcx]
0x1800380db  mov     rax, [rax+10h]
0x1800380df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380e4  nop
0x1800380e5  jmp     loc_18003805F
0x1800380ea  xor     r9d, r9d; lpArguments
0x1800380ed  xor     r8d, r8d; nNumberOfArguments
0x1800380f0  lea     edx, [r9+1]; dwExceptionFlags
0x1800380f4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800380f9  call    cs:__imp_RaiseException
0x1800380ff  jmp     loc_180037DAF
0x180038104  mov     rcx, [rbp+5Fh]; this
0x180038108  mov     dword ptr [rsp+0F0h+var_C8], ebx; wil::details *
0x18003810c  lea     rax, aConsentmanager_0; "consentManagerStatics->Create(GetLocati"...
0x180038113  mov     [rsp+0F0h+var_D0], rax; char *
0x180038118  lea     r9, aClocationcampr_2; "CLocationCamPrimitives::GetNonPackagedA"...
0x18003811f  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038126  mov     edx, 0E2h; void *
0x18003812b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038130  jmp     short loc_180038179
0x180038132  mov     rcx, [rbp+5Fh]; this
0x180038136  mov     dword ptr [rsp+0F0h+var_C8], ebx; wil::details *
0x18003813a  lea     rax, aConsentmanager; "consentManager->GetUserAppConsent( Stri"...
0x180038141  mov     [rsp+0F0h+var_D0], rax; char *
0x180038146  lea     r9, aClocationcampr_2; "CLocationCamPrimitives::GetNonPackagedA"...
0x18003814d  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038154  mov     edx, 0E6h; void *
0x180038159  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003815e  nop
0x18003815f  lea     rcx, [rbp+57h+var_58]
0x180038163  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038168  jmp     short loc_180038179
0x18003816a  mov     byte ptr [rsi], 1
0x18003816d  lea     rcx, [rbp+57h+var_58]
0x180038171  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038176  mov     ebx, r12d
0x180038179  lea     rcx, [rbp+57h+var_50]
0x18003817d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038182  nop
0x180038183  lea     rcx, [rbp+57h+var_60]
0x180038187  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003818c  jmp     loc_18003805F
```
