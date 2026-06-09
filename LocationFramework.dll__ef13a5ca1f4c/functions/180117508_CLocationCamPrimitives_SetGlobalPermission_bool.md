# CLocationCamPrimitives::SetGlobalPermission(bool)

- ea: `0x180117508`
- end: `0x180117863`
- name: `?SetGlobalPermission@CLocationCamPrimitives@@SAJ_N@Z`
- size: `859`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c36f0`

## callees

- `0x180012310`
- `0x180018228`
- `0x1800191cc`
- `0x18001e170`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x18001fbac`
- `0x180020994`
- `0x180020c64`
- `0x1800385dc`
- `0x18004bb74`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x180117508`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801176c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180117782`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801176c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180117782`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180117552`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180117552`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180117617`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180117617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801176d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180117797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801176d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180117797`

## string_xrefs

- `0x18011764a`: `GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager).Get(), &consentManagerStatics)`
- `0x180117702`: `consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)`
- `0x1801177b7`: `consentManager->put_CallingUser(StringReference(userSidString.c_str()).Get())`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationCamPrimitives::SetGlobalPermission(unsigned __int8 a1)
{
  int v1; // r12d
  HRESULT v2; // eax
  const unsigned __int16 *v3; // rdx
  bool v4; // bl
  __int64 v5; // rax
  HSTRING *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, PVOID, __int64 *); // r15
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // rdx
  int v15; // edi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, PVOID); // r14
  __int64 v18; // rax
  const WCHAR *v19; // rdi
  int v20; // eax
  const char *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  wil::details *v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+30h] [rbp-D0h]
  HSTRING string[4]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  _BYTE v35[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v36[120]; // [rsp+B8h] [rbp-48h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+188h] [rbp+88h]

  v1 = a1;
  v32 = 0;
  v33 = 0;
  v34 = 7;
  LOWORD(v32) = 0;
  v2 = CoImpersonateClient();
  v4 = v2 >= 0;
  LOBYTE(v26) = v2 >= 0;
  if ( v2 == -2147417833 )
    v2 = 1;
  if ( v2 >= 0 )
  {
    hstringHeader.Reserved.Reserved1 = &ATL::CAccessToken::`vftable';
    *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    v31 = 0;
    ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&hstringHeader, 8u);
    memset_0(v35, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v35);
    if ( ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&hstringHeader, (__int64)v35) )
    {
      v5 = LocationCallerInfoHelper::SidToString(string, v36);
      std::wstring::operator=(&v32, v5);
      std::wstring::_Tidy_deallocate(string);
    }
    ATL::CSid::~CSid((ATL::CSid *)v35);
    hstringHeader.Reserved.Reserved1 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&hstringHeader);
  }
  if ( v4 )
    CoRevertToSelf();
  v29 = 0;
  v6 = Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[70])v3);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManagerStatics>>(
         *v6,
         &v29);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v28 = 0;
    v9 = v29;
    v10 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( c_szCapabilityLocation[v12] );
    if ( v12 > 0xFFFFFFFF )
    {
      LODWORD(v12) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(
      c_szCapabilityLocation,
      v12,
      (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
      (HSTRING *)&hstringHeader);
    v13 = v10(v9, hstringHeader.Reserved.Reserved1, &v28);
    v15 = v13;
    if ( v13 >= 0 )
    {
      if ( !v33 )
        goto LABEL_25;
      v16 = v28;
      v17 = *(__int64 (__fastcall **)(__int64, PVOID))(*(_QWORD *)v28 + 224LL);
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v32, v14);
      v19 = (const WCHAR *)v18;
      do
        ++v11;
      while ( *(_WORD *)(v18 + 2 * v11) );
      if ( v11 > 0xFFFFFFFF )
      {
        LODWORD(v11) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(
        v19,
        v11,
        (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
        (HSTRING *)&hstringHeader);
      v20 = v17(v16, hstringHeader.Reserved.Reserved1);
      v8 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v25) = v20;
        v21 = "consentManager->put_CallingUser(StringReference(userSidString.c_str()).Get())";
        v22 = 62;
      }
      else
      {
LABEL_25:
        v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 112LL))(v28, (v1 ^ 1u) + 1);
        v8 = v23;
        if ( v23 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
          v8 = 0;
          goto LABEL_28;
        }
        LODWORD(v25) = v23;
        v21 = "consentManager->SetSystemGlobalConsent(consentValue)";
        v22 = 66;
      }
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
        "CLocationCamPrimitives::SetGlobalPermission",
        v21,
        v25,
        v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    }
    else
    {
      LODWORD(v25) = v13;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
        "CLocationCamPrimitives::SetGlobalPermission",
        "consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)",
        v25,
        v26);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      v8 = v15;
    }
  }
  else
  {
    LODWORD(v25) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::SetGlobalPermission",
      "GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentM"
      "anager).Get(), &consentManagerStatics)",
      v25,
      v26);
  }
LABEL_28:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  std::wstring::_Tidy_deallocate(&v32);
  return v8;
}

```

## disassembly

```asm
0x180117508  push    rbp
0x18011750a  push    rbx
0x18011750b  push    rsi
0x18011750c  push    rdi
0x18011750d  push    r12
0x18011750f  push    r13
0x180117511  push    r14
0x180117513  push    r15
0x180117515  lea     rbp, [rsp-48h]
0x18011751a  sub     rsp, 148h
0x180117521  mov     rax, cs:__security_cookie
0x180117528  xor     rax, rsp
0x18011752b  mov     [rbp+80h+var_50], rax
0x18011752f  movzx   r12d, cl
0x180117533  xorps   xmm0, xmm0
0x180117536  movups  [rbp+80h+var_F8], xmm0
0x18011753a  xor     r13d, r13d
0x18011753d  mov     [rbp+80h+var_E8], r13
0x180117541  mov     [rbp+80h+var_E0], 7
0x180117549  mov     word ptr [rbp+80h+var_F8], r13w
0x18011754e  movzx   ebx, r13b
0x180117552  call    cs:__imp_CoImpersonateClient
0x180117558  mov     [rsp+180h+var_14C], eax
0x18011755c  lea     ecx, [r13+1]
0x180117560  test    eax, eax
0x180117562  cmovns  ebx, ecx
0x180117565  mov     byte ptr [rsp+180h+var_150], bl; int
0x180117569  cmp     eax, 80010117h
0x18011756e  cmovz   eax, ecx
0x180117571  test    eax, eax
0x180117573  js      loc_180117613
0x180117579  xorps   xmm0, xmm0
0x18011757c  movups  xmmword ptr [rsp+180h+hstringHeader.Reserved], xmm0
0x180117581  movups  xmmword ptr [rsp+180h+hstringHeader.Reserved+10h], xmm0
0x180117586  lea     rdi, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18011758d  mov     qword ptr [rsp+180h+hstringHeader.Reserved], rdi
0x180117592  movdqu  xmmword ptr [rsp+180h+hstringHeader.Reserved+8], xmm0
0x180117598  mov     [rbp+80h+var_100], r13
0x18011759c  lea     edx, [rcx+7]; unsigned int
0x18011759f  lea     rcx, [rsp+180h+hstringHeader]; this
0x1801175a4  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x1801175a9  xor     edx, edx; Val
0x1801175ab  lea     r8d, [r13+78h]; Size
0x1801175af  lea     rcx, [rbp+80h+var_D0]; void *
0x1801175b3  call    memset_0
0x1801175b8  lea     rcx, [rbp+80h+var_D0]; this
0x1801175bc  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1801175c1  nop
0x1801175c2  lea     rdx, [rbp+80h+var_D0]
0x1801175c6  lea     rcx, [rsp+180h+hstringHeader]
0x1801175cb  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x1801175d0  test    al, al
0x1801175d2  jz      short loc_1801175F9
0x1801175d4  lea     rdx, [rbp+80h+var_C8]
0x1801175d8  lea     rcx, [rsp+180h+string]
0x1801175dd  call    ?SidToString@LocationCallerInfoHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@@Z; LocationCallerInfoHelper::SidToString(_SID const *)
0x1801175e2  mov     rdx, rax
0x1801175e5  lea     rcx, [rbp+80h+var_F8]
0x1801175e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801175ee  lea     rcx, [rsp+180h+string]
0x1801175f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801175f8  nop
0x1801175f9  lea     rcx, [rbp+80h+var_D0]; this
0x1801175fd  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180117602  nop
0x180117603  mov     qword ptr [rsp+180h+hstringHeader.Reserved], rdi
0x180117608  lea     rcx, [rsp+180h+hstringHeader]; this
0x18011760d  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180117612  nop
0x180117613  test    bl, bl
0x180117615  jz      short loc_18011761D
0x180117617  call    cs:__imp_CoRevertToSelf
0x18011761d  mov     [rsp+180h+var_120], r13
0x180117622  lea     rcx, [rsp+180h+string]; string
0x180117627  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x18011762c  lea     rdx, [rsp+180h+var_120]
0x180117631  mov     rcx, [rax]
0x180117634  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityConsentManagerStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityConsentManagerStatics@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityConsentManagerStatics>>)
0x180117639  mov     ebx, eax
0x18011763b  test    eax, eax
0x18011763d  jns     short loc_180117673
0x18011763f  mov     rcx, [rbp+88h]; this
0x180117646  mov     dword ptr [rsp+180h+var_158], eax; wil::details *
0x18011764a  lea     rax, aGetactivationf; "GetActivationFactory( StringReference(R"...
0x180117651  mov     [rsp+180h+var_160], rax; char *
0x180117656  lea     r9, aClocationcampr_1; "CLocationCamPrimitives::SetGlobalPermis"...
0x18011765d  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180117664  mov     edx, 30h ; '0'; void *
0x180117669  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011766e  jmp     loc_18011782D
0x180117673  mov     [rsp+180h+var_128], r13
0x180117678  mov     r14, [rsp+180h+var_120]
0x18011767d  mov     rax, [r14]
0x180117680  mov     r15, [rax+30h]
0x180117684  lea     rcx, [rsp+180h+var_128]
0x180117689  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18011768e  mov     rsi, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180117695  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180117699  mov     rdi, rbx
0x18011769c  inc     rdi
0x18011769f  cmp     [rsi+rdi*2], r13w
0x1801176a4  jnz     short loc_18011769C
0x1801176a6  mov     eax, 0FFFFFFFFh
0x1801176ab  cmp     rdi, rax
0x1801176ae  jbe     short loc_1801176C7
0x1801176b0  mov     edi, eax
0x1801176b2  xor     r9d, r9d; lpArguments
0x1801176b5  xor     r8d, r8d; nNumberOfArguments
0x1801176b8  lea     edx, [r9+1]; dwExceptionFlags
0x1801176bc  mov     ecx, 0C000000Dh; dwExceptionCode
0x1801176c1  call    cs:__imp_RaiseException
0x1801176c7  lea     r9, [rsp+180h+hstringHeader]; string
0x1801176cc  lea     r8, [rsp+180h+hstringHeader.Reserved+8]; hstringHeader
0x1801176d1  mov     edx, edi; length
0x1801176d3  mov     rcx, rsi; sourceString
0x1801176d6  call    cs:__imp_WindowsCreateStringReference
0x1801176dc  lea     r8, [rsp+180h+var_128]
0x1801176e1  mov     rdx, qword ptr [rsp+180h+hstringHeader.Reserved]
0x1801176e6  mov     rcx, r14
0x1801176e9  mov     rax, r15
0x1801176ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801176f1  mov     edi, eax
0x1801176f3  test    eax, eax
0x1801176f5  jns     short loc_180117738
0x1801176f7  mov     rcx, [rbp+88h]; this
0x1801176fe  mov     dword ptr [rsp+180h+var_158], eax; wil::details *
0x180117702  lea     rax, aConsentmanager_0; "consentManagerStatics->Create(GetLocati"...
0x180117709  mov     [rsp+180h+var_160], rax; char *
0x18011770e  lea     r9, aClocationcampr_1; "CLocationCamPrimitives::SetGlobalPermis"...
0x180117715  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x18011771c  mov     edx, 33h ; '3'; void *
0x180117721  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180117726  nop
0x180117727  lea     rcx, [rsp+180h+var_128]
0x18011772c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117731  mov     ebx, edi
0x180117733  jmp     loc_18011782D
0x180117738  cmp     [rbp+80h+var_E8], r13
0x18011773c  jz      loc_1801177EF
0x180117742  mov     rsi, [rsp+180h+var_128]
0x180117747  mov     rax, [rsi]
0x18011774a  mov     r14, [rax+0E0h]
0x180117751  lea     rcx, [rbp+80h+var_F8]
0x180117755  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011775a  mov     rdi, rax
0x18011775d  inc     rbx
0x180117760  cmp     [rax+rbx*2], r13w
0x180117765  jnz     short loc_18011775D
0x180117767  mov     eax, 0FFFFFFFFh
0x18011776c  cmp     rbx, rax
0x18011776f  jbe     short loc_180117788
0x180117771  mov     ebx, eax
0x180117773  xor     r9d, r9d; lpArguments
0x180117776  xor     r8d, r8d; nNumberOfArguments
0x180117779  lea     edx, [r9+1]; dwExceptionFlags
0x18011777d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180117782  call    cs:__imp_RaiseException
0x180117788  lea     r9, [rsp+180h+hstringHeader]; string
0x18011778d  lea     r8, [rsp+180h+hstringHeader.Reserved+8]; hstringHeader
0x180117792  mov     edx, ebx; length
0x180117794  mov     rcx, rdi; sourceString
0x180117797  call    cs:__imp_WindowsCreateStringReference
0x18011779d  mov     rdx, qword ptr [rsp+180h+hstringHeader.Reserved]
0x1801177a2  mov     rcx, rsi
0x1801177a5  mov     rax, r14
0x1801177a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801177ad  mov     ebx, eax
0x1801177af  test    eax, eax
0x1801177b1  jns     short loc_1801177EF
0x1801177b3  mov     dword ptr [rsp+180h+var_158], eax; wil::details *
0x1801177b7  lea     rax, aConsentmanager_3; "consentManager->put_CallingUser(StringR"...
0x1801177be  mov     edx, 3Eh ; '>'; void *
0x1801177c3  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x1801177ca  lea     r9, aClocationcampr_1; "CLocationCamPrimitives::SetGlobalPermis"...
0x1801177d1  mov     [rsp+180h+var_160], rax; char *
0x1801177d6  mov     rcx, [rbp+88h]; this
0x1801177dd  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801177e2  nop
0x1801177e3  lea     rcx, [rsp+180h+var_128]
0x1801177e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801177ed  jmp     short loc_18011782D
0x1801177ef  mov     rcx, [rsp+180h+var_128]
0x1801177f4  mov     rax, [rcx]
0x1801177f7  mov     edx, r12d
0x1801177fa  xor     edx, 1
0x1801177fd  inc     edx
0x1801177ff  mov     rax, [rax+70h]
0x180117803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117808  mov     ebx, eax
0x18011780a  test    eax, eax
0x18011780c  jns     short loc_180117820
0x18011780e  mov     dword ptr [rsp+180h+var_158], eax
0x180117812  lea     rax, aConsentmanager_1; "consentManager->SetSystemGlobalConsent("...
0x180117819  mov     edx, 42h ; 'B'
0x18011781e  jmp     short loc_1801177C3
0x180117820  lea     rcx, [rsp+180h+var_128]
0x180117825  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18011782a  mov     ebx, r13d
0x18011782d  lea     rcx, [rsp+180h+var_120]
0x180117832  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180117837  nop
0x180117838  lea     rcx, [rbp+80h+var_F8]
0x18011783c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180117841  mov     eax, ebx
0x180117843  mov     rcx, [rbp+80h+var_50]
0x180117847  xor     rcx, rsp; StackCookie
0x18011784a  call    __security_check_cookie
0x18011784f  add     rsp, 148h
0x180117856  pop     r15
0x180117858  pop     r14
0x18011785a  pop     r13
0x18011785c  pop     r12
0x18011785e  pop     rdi
0x18011785f  pop     rsi
0x180117860  pop     rbx
0x180117861  pop     rbp
0x180117862  retn
```
