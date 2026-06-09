# CLocationCamPrimitives::GetGlobalConsentStatus(bool &)

- ea: `0x180038664`
- end: `0x180038a33`
- name: `?GetGlobalConsentStatus@CLocationCamPrimitives@@SAJAEA_N@Z`
- size: `975`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180038620`
- `0x18005bfcc`
- `0x180097ab0`
- `0x1800d27a8`
- `0x1800d3860`

## callees

- `0x180012310`
- `0x180038664`
- `0x18009c310`
- `0x1800a98c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038730`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038a03`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038730`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038a03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800386af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800386af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180038743`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800386d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800386d8`

## string_xrefs

- `0x18003884e`: `GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager).Get(), &consentManagerStatics)`
- `0x180038899`: `consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)`
- `0x1800386a8`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLocationCamPrimitives::GetGlobalConsentStatus(bool *a1)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // r14
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // r15
  unsigned __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  wil::details *v26; // [rsp+28h] [rbp-58h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+60h] [rbp-20h] BYREF
  int v32; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+28h]

  *a1 = 0;
  v29 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
         0x45u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v29);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    LODWORD(v26) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
      "CLocationCamPrimitives::GetGlobalConsentStatus",
      "GetActivationFactory( StringReference(RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentM"
      "anager).Get(), &consentManagerStatics)",
      v26,
      (int)string);
    v17 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  else
  {
    v30 = 0;
    v5 = v29;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v7 = -1;
    do
      ++v7;
    while ( c_szCapabilityLocation[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      LODWORD(v7) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(c_szCapabilityLocation, v7, &hstringHeader, &string);
    v8 = v6(v5, string, &v30);
    v4 = v8;
    if ( v8 < 0 )
    {
      LODWORD(v26) = v8;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
        "CLocationCamPrimitives::GetGlobalConsentStatus",
        "consentManagerStatics->Create(GetLocationCapabilityName().Get(), &consentManager)",
        v26,
        (int)string);
      v18 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    else
    {
      v31 = 0;
      v9 = v30;
      v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v11 = v10(v9, &v31);
      v4 = v11;
      if ( v11 < 0 )
      {
        LODWORD(v26) = v11;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
          "CLocationCamPrimitives::GetGlobalConsentStatus",
          "consentManager->GetSystemGlobalConsent(&consent)",
          v26,
          (int)string);
        v23 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v25 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
      }
      else
      {
        if ( !v31 )
        {
          *a1 = 1;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
          return 0;
        }
        v32 = 2;
        v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 88LL))(v31, &v32);
        v4 = v12;
        if ( v12 >= 0 )
        {
          *a1 = v32 == 1;
          v13 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v14 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          v15 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          return 0;
        }
        LODWORD(v26) = v12;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationcamprimitives.cpp",
          "CLocationCamPrimitives::GetGlobalConsentStatus",
          "consent->get_Value(&consentValue)",
          v26,
          (int)string);
        v20 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180038664  mov     [rsp-28h+arg_8], rbx
0x180038669  mov     [rsp-28h+arg_10], rsi
0x18003866e  push    rbp
0x18003866f  push    rdi
0x180038670  push    r12
0x180038672  push    r14
0x180038674  push    r15
0x180038676  mov     rbp, rsp
0x180038679  sub     rsp, 80h
0x180038680  mov     rax, cs:__security_cookie
0x180038687  xor     rax, rsp
0x18003868a  mov     [rbp+var_10], rax
0x18003868e  mov     rsi, rcx
0x180038691  xor     r12d, r12d
0x180038694  mov     [rcx], r12b
0x180038697  mov     [rbp+var_30], r12
0x18003869b  lea     r9, [rbp+string]; string
0x18003869f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800386a3  lea     edx, [r12+45h]; length
0x1800386a8  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x1800386af  call    cs:__imp_WindowsCreateStringReference
0x1800386b5  test    eax, eax
0x1800386b7  js      loc_1800389F4
0x1800386bd  mov     rbx, [rbp+string]
0x1800386c1  lea     rcx, [rbp+var_30]
0x1800386c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800386ca  lea     r8, [rbp+var_30]
0x1800386ce  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x1800386d5  mov     rcx, rbx
0x1800386d8  call    cs:__imp_RoGetActivationFactory
0x1800386de  mov     ebx, eax
0x1800386e0  test    eax, eax
0x1800386e2  js      loc_180038846
0x1800386e8  mov     [rbp+var_28], r12
0x1800386ec  mov     r14, [rbp+var_30]
0x1800386f0  mov     rax, [r14]
0x1800386f3  mov     r15, [rax+30h]
0x1800386f7  lea     rcx, [rbp+var_28]
0x1800386fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038700  mov     rdi, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180038707  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003870b  inc     rbx
0x18003870e  cmp     [rdi+rbx*2], r12w
0x180038713  jnz     short loc_18003870B
0x180038715  mov     eax, 0FFFFFFFFh
0x18003871a  cmp     rbx, rax
0x18003871d  jbe     short loc_180038736
0x18003871f  mov     ebx, eax
0x180038721  xor     r9d, r9d; lpArguments
0x180038724  xor     r8d, r8d; nNumberOfArguments
0x180038727  lea     edx, [r9+1]; dwExceptionFlags
0x18003872b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180038730  call    cs:__imp_RaiseException
0x180038736  lea     r9, [rbp+string]; string
0x18003873a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003873e  mov     edx, ebx; length
0x180038740  mov     rcx, rdi; sourceString
0x180038743  call    cs:__imp_WindowsCreateStringReference
0x180038749  lea     r8, [rbp+var_28]
0x18003874d  mov     rdx, [rbp+string]
0x180038751  mov     rcx, r14
0x180038754  mov     rax, r15
0x180038757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003875c  mov     ebx, eax
0x18003875e  test    eax, eax
0x180038760  js      loc_180038891
0x180038766  mov     [rbp+var_20], r12
0x18003876a  mov     rdi, [rbp+var_28]
0x18003876e  mov     rax, [rdi]
0x180038771  mov     rbx, [rax+30h]
0x180038775  lea     rcx, [rbp+var_20]
0x180038779  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003877e  lea     rdx, [rbp+var_20]
0x180038782  mov     rcx, rdi
0x180038785  mov     rax, rbx
0x180038788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003878d  mov     ebx, eax
0x18003878f  test    eax, eax
0x180038791  js      loc_180038974
0x180038797  mov     rcx, [rbp+var_20]
0x18003879b  test    rcx, rcx
0x18003879e  jz      loc_180038A0E
0x1800387a4  mov     [rbp+var_18], 2
0x1800387ab  mov     rax, [rcx]
0x1800387ae  lea     rdx, [rbp+var_18]
0x1800387b2  mov     rax, [rax+58h]
0x1800387b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387bb  mov     ebx, eax
0x1800387bd  test    eax, eax
0x1800387bf  js      loc_1800388F4
0x1800387c5  cmp     [rbp+var_18], 1
0x1800387c9  setz    al
0x1800387cc  mov     [rsi], al
0x1800387ce  mov     rcx, [rbp+var_20]
0x1800387d2  test    rcx, rcx
0x1800387d5  jz      short loc_1800387E8
0x1800387d7  mov     [rbp+var_20], r12
0x1800387db  mov     rax, [rcx]
0x1800387de  mov     rax, [rax+10h]
0x1800387e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387e7  nop
0x1800387e8  mov     rcx, [rbp+var_28]
0x1800387ec  test    rcx, rcx
0x1800387ef  jz      short loc_180038802
0x1800387f1  mov     [rbp+var_28], r12
0x1800387f5  mov     rax, [rcx]
0x1800387f8  mov     rax, [rax+10h]
0x1800387fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038801  nop
0x180038802  mov     rcx, [rbp+var_30]
0x180038806  test    rcx, rcx
0x180038809  jz      short loc_18003881C
0x18003880b  mov     [rbp+var_30], r12
0x18003880f  mov     rax, [rcx]
0x180038812  mov     rax, [rax+10h]
0x180038816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003881b  nop
0x18003881c  xor     eax, eax
0x18003881e  mov     rcx, [rbp+var_10]
0x180038822  xor     rcx, rsp; StackCookie
0x180038825  call    __security_check_cookie
0x18003882a  lea     r11, [rsp+80h+var_s0]
0x180038832  mov     rbx, [r11+38h]
0x180038836  mov     rsi, [r11+40h]
0x18003883a  mov     rsp, r11
0x18003883d  pop     r15
0x18003883f  pop     r14
0x180038841  pop     r12
0x180038843  pop     rdi
0x180038844  pop     rbp
0x180038845  retn
0x180038846  mov     rcx, [rbp+28h]; this
0x18003884a  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x18003884e  lea     rax, aGetactivationf; "GetActivationFactory( StringReference(R"...
0x180038855  mov     [rsp+80h+var_60], rax; char *
0x18003885a  lea     r9, aClocationcampr_3; "CLocationCamPrimitives::GetGlobalConsen"...
0x180038861  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038868  mov     edx, 4Dh ; 'M'; void *
0x18003886d  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038872  nop
0x180038873  mov     rcx, [rbp+var_30]
0x180038877  test    rcx, rcx
0x18003887a  jz      short loc_18003888D
0x18003887c  mov     [rbp+var_30], r12
0x180038880  mov     rax, [rcx]
0x180038883  mov     rax, [rax+10h]
0x180038887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003888c  nop
0x18003888d  mov     eax, ebx
0x18003888f  jmp     short loc_18003881E
0x180038891  mov     rcx, [rbp+28h]; this
0x180038895  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x180038899  lea     rax, aConsentmanager_0; "consentManagerStatics->Create(GetLocati"...
0x1800388a0  mov     [rsp+80h+var_60], rax; char *
0x1800388a5  lea     r9, aClocationcampr_3; "CLocationCamPrimitives::GetGlobalConsen"...
0x1800388ac  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800388b3  mov     edx, 50h ; 'P'; void *
0x1800388b8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800388bd  nop
0x1800388be  mov     rcx, [rbp+var_28]
0x1800388c2  test    rcx, rcx
0x1800388c5  jz      short loc_1800388D8
0x1800388c7  mov     [rbp+var_28], r12
0x1800388cb  mov     rax, [rcx]
0x1800388ce  mov     rax, [rax+10h]
0x1800388d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388d7  nop
0x1800388d8  mov     rcx, [rbp+var_30]
0x1800388dc  test    rcx, rcx
0x1800388df  jz      short loc_1800388F2
0x1800388e1  mov     [rbp+var_30], r12
0x1800388e5  mov     rax, [rcx]
0x1800388e8  mov     rax, [rax+10h]
0x1800388ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388f1  nop
0x1800388f2  jmp     short loc_18003888D
0x1800388f4  mov     rcx, [rbp+28h]; this
0x1800388f8  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x1800388fc  lea     rax, aConsentGetValu; "consent->get_Value(&consentValue)"
0x180038903  mov     [rsp+80h+var_60], rax; char *
0x180038908  lea     r9, aClocationcampr_3; "CLocationCamPrimitives::GetGlobalConsen"...
0x18003890f  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038916  mov     edx, 5Fh ; '_'; void *
0x18003891b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180038920  nop
0x180038921  mov     rcx, [rbp+var_20]
0x180038925  test    rcx, rcx
0x180038928  jz      short loc_18003893B
0x18003892a  mov     [rbp+var_20], r12
0x18003892e  mov     rax, [rcx]
0x180038931  mov     rax, [rax+10h]
0x180038935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003893a  nop
0x18003893b  mov     rcx, [rbp+var_28]
0x18003893f  test    rcx, rcx
0x180038942  jz      short loc_180038955
0x180038944  mov     [rbp+var_28], r12
0x180038948  mov     rax, [rcx]
0x18003894b  mov     rax, [rax+10h]
0x18003894f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038954  nop
0x180038955  mov     rcx, [rbp+var_30]
0x180038959  test    rcx, rcx
0x18003895c  jz      short loc_18003896F
0x18003895e  mov     [rbp+var_30], r12
0x180038962  mov     rax, [rcx]
0x180038965  mov     rax, [rax+10h]
0x180038969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003896e  nop
0x18003896f  jmp     loc_18003888D
0x180038974  mov     rcx, [rbp+28h]; this
0x180038978  mov     dword ptr [rsp+80h+var_58], ebx; wil::details *
0x18003897c  lea     rax, aConsentmanager_4; "consentManager->GetSystemGlobalConsent("...
0x180038983  mov     [rsp+80h+var_60], rax; char *
0x180038988  lea     r9, aClocationcampr_3; "CLocationCamPrimitives::GetGlobalConsen"...
0x18003898f  lea     r8, aOnecoreuapDriv_29; "onecoreuap\\drivers\\mobilepc\\location"...
0x180038996  mov     edx, 53h ; 'S'; void *
0x18003899b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800389a0  nop
0x1800389a1  mov     rcx, [rbp+var_20]
0x1800389a5  test    rcx, rcx
0x1800389a8  jz      short loc_1800389BB
0x1800389aa  mov     [rbp+var_20], r12
0x1800389ae  mov     rax, [rcx]
0x1800389b1  mov     rax, [rax+10h]
0x1800389b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389ba  nop
0x1800389bb  mov     rcx, [rbp+var_28]
0x1800389bf  test    rcx, rcx
0x1800389c2  jz      short loc_1800389D5
0x1800389c4  mov     [rbp+var_28], r12
0x1800389c8  mov     rax, [rcx]
0x1800389cb  mov     rax, [rax+10h]
0x1800389cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389d4  nop
0x1800389d5  mov     rcx, [rbp+var_30]
0x1800389d9  test    rcx, rcx
0x1800389dc  jz      short loc_1800389EF
0x1800389de  mov     [rbp+var_30], r12
0x1800389e2  mov     rax, [rcx]
0x1800389e5  mov     rax, [rax+10h]
0x1800389e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389ee  nop
0x1800389ef  jmp     loc_18003888D
0x1800389f4  xor     r9d, r9d; lpArguments
0x1800389f7  xor     r8d, r8d; nNumberOfArguments
0x1800389fa  lea     edx, [r9+1]; dwExceptionFlags
0x1800389fe  mov     ecx, 0C000000Dh; dwExceptionCode
0x180038a03  call    cs:__imp_RaiseException
0x180038a09  jmp     loc_1800386BD
0x180038a0e  mov     byte ptr [rsi], 1
0x180038a11  lea     rcx, [rbp+var_20]
0x180038a15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038a1a  nop
0x180038a1b  lea     rcx, [rbp+var_28]
0x180038a1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038a24  nop
0x180038a25  lea     rcx, [rbp+var_30]
0x180038a29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038a2e  jmp     loc_18003881C
```
