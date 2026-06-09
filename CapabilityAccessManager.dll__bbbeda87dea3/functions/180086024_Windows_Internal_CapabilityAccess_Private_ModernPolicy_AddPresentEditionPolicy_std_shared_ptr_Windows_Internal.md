# Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)

- ea: `0x180086024`
- end: `0x180086805`
- name: `?AddPresentEditionPolicy@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z`
- size: `2017`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180085568`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x180020fcc`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x18002f93c`
- `0x18002f978`
- `0x18003afa0`
- `0x18003ce34`
- `0x1800473fc`
- `0x180048444`
- `0x180051874`
- `0x18005829c`
- `0x180058ac4`
- `0x180058c8c`
- `0x180058dfc`
- `0x180072d00`
- `0x180086024`
- `0x18008680c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086196`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180086196`

## string_xrefs

- `0x18008607f`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x18008647f`: `ForegroundRequiredForAccess`
- `0x18008642c`: `FallbackTokenCapabilities`
- `0x180086228`: `AlwaysAttemptPrompts`
- `0x18008624f`: `AlwaysBlockAccess`
- `0x1800862e9`: `BlockAccess`
- `0x1800866a6`: `TerminateAppOnAccessChange`
- `0x18008629d`: `AppLaunchAccessCheckRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  unsigned int Uint32Value; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 StringValue; // rax
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 KeyArray; // rax
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  std::_Ref_count_base *v42; // rcx
  bool *phkResult; // [rsp+20h] [rbp-79h]
  bool *phkResulta; // [rsp+20h] [rbp-79h]
  bool *phkResultb; // [rsp+20h] [rbp-79h]
  bool *phkResultc; // [rsp+20h] [rbp-79h]
  bool *phkResultd; // [rsp+20h] [rbp-79h]
  bool *phkResulte; // [rsp+20h] [rbp-79h]
  bool *phkResultf; // [rsp+20h] [rbp-79h]
  bool *phkResultg; // [rsp+20h] [rbp-79h]
  bool *phkResulth; // [rsp+20h] [rbp-79h]
  bool *phkResulti; // [rsp+20h] [rbp-79h]
  bool *phkResultj; // [rsp+20h] [rbp-79h]
  bool *phkResultk; // [rsp+20h] [rbp-79h]
  bool *phkResultl; // [rsp+20h] [rbp-79h]
  bool *phkResultm; // [rsp+20h] [rbp-79h]
  bool *phkResultn; // [rsp+20h] [rbp-79h]
  bool *phkResulto; // [rsp+20h] [rbp-79h]
  bool *phkResultp; // [rsp+20h] [rbp-79h]
  bool *phkResultq; // [rsp+20h] [rbp-79h]
  bool *phkResultr; // [rsp+20h] [rbp-79h]
  bool *phkResults; // [rsp+20h] [rbp-79h]
  bool *phkResultt; // [rsp+20h] [rbp-79h]
  bool *phkResultu; // [rsp+20h] [rbp-79h]
  bool *phkResultv; // [rsp+20h] [rbp-79h]
  bool *phkResultw; // [rsp+20h] [rbp-79h]
  bool *phkResultx; // [rsp+20h] [rbp-79h]
  bool *phkResulty; // [rsp+20h] [rbp-79h]
  const char *v69; // [rsp+30h] [rbp-69h] BYREF
  HKEY v70; // [rsp+38h] [rbp-61h] BYREF
  __int128 v71; // [rsp+40h] [rbp-59h] BYREF
  __int64 v72; // [rsp+50h] [rbp-49h]
  _QWORD *v73; // [rsp+58h] [rbp-41h]
  _BYTE Src[16]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v75; // [rsp+70h] [rbp-29h]
  unsigned __int64 v76; // [rsp+78h] [rbp-21h]
  __int128 v77; // [rsp+80h] [rbp-19h] BYREF
  __int64 v78; // [rsp+90h] [rbp-9h]
  __int64 v79; // [rsp+98h] [rbp-1h]
  _BYTE v80[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v73 = a1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\edition.cpp",
    (const char *)0x80070057LL,
    *(_QWORD *)(*a1 + 24LL) == 0,
    (bool)"Policy has not provided a capability definition to parse Edition policy",
    v69);
  std::wstring::wstring(Src, L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  if ( v75 >= v76 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v75;
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_DWORD *)(v2 + 2 * v3) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Capabilities");
  if ( v75 >= v76 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v75;
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_DWORD *)(v4 + 2 * v5) = 92;
  }
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 8LL);
  std::wstring::_Append<unsigned short>(Src, v6);
  if ( v75 >= v76 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v75;
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_DWORD *)(v7 + 2 * v8) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Edition");
  v70 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v70,
    0);
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20119u, &v70);
  if ( v10 != 2 )
  {
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\edition.cpp",
        (const char *)v10,
        (unsigned int)phkResult);
    LOBYTE(v69) = 0;
    v77 = 0;
    v78 = 0;
    v79 = 7;
    LOWORD(v77) = 0;
    v71 = 0;
    v72 = 0;
    Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                    (Windows::Internal::CapabilityAccess::Private *)v70,
                    0,
                    L"AllUsersConsentRequiredForMua",
                    (const unsigned __int16 *)&v69,
                    phkResult);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 41LL) = Uint32Value == 1;
    v12 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AlwaysAllowBeforeOOBE",
            (const unsigned __int16 *)&v69,
            phkResulta);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 42LL) = v12 == 1;
    v13 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AlwaysAttemptPrompts",
            (const unsigned __int16 *)&v69,
            phkResultb);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 44LL) = v13 == 1;
    v14 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AlwaysBlockAccess",
            (const unsigned __int16 *)&v69,
            phkResultc);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 45LL) = v14 == 1;
    v15 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AlwaysBlockNonPackaged",
            (const unsigned __int16 *)&v69,
            phkResultd);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 46LL) = v15 == 1;
    v16 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AppLaunchAccessCheckRequired",
            (const unsigned __int16 *)&v69,
            phkResulte);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 47LL) = v16 == 1;
    v17 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"AuditBehaviorDefault",
            (const unsigned __int16 *)&v69,
            phkResultf);
    if ( (_BYTE)v69 )
      *(_DWORD *)(*a1 + 136LL) = v17;
    v18 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"BlockAccess",
            (const unsigned __int16 *)&v69,
            phkResultg);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 48LL) = v18 == 1;
    StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
                    v80,
                    v70,
                    0,
                    L"CapabilityForConsent",
                    &v69);
    std::wstring::operator=(&v77, StringValue);
    std::wstring::_Tidy_deallocate(v80);
    if ( (_BYTE)v69 )
    {
      std::wstring::operator=(*a1 + 72LL, &v77);
      v78 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v77) = 0;
    }
    v20 = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(v80, v70, 0, L"CapabilityForPrompt", &v69);
    std::wstring::operator=(&v77, v20);
    std::wstring::_Tidy_deallocate(v80);
    if ( (_BYTE)v69 )
    {
      std::wstring::operator=(*a1 + 104LL, &v77);
      v78 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v77) = 0;
    }
    v21 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"CollapseRecentActivity",
            (const unsigned __int16 *)&v69,
            phkResulth);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 49LL) = v21 == 1;
    v22 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"ExtendUXLifetime",
            (const unsigned __int16 *)&v69,
            phkResulti);
    if ( (_BYTE)v69
      || (v22 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                  (Windows::Internal::CapabilityAccess::Private *)v70,
                  0,
                  L"MinimumSessionDuration",
                  (const unsigned __int16 *)&v69,
                  phkResultj),
          (_BYTE)v69) )
    {
      *(_BYTE *)(*a1 + 56LL) = v22 == 1;
    }
    KeyArray = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v80, v70, L"FallbackTokenCapabilities");
    std::vector<std::wstring>::operator=(&v71, KeyArray);
    std::vector<std::wstring>::_Tidy(v80);
    if ( (_QWORD)v71 != *((_QWORD *)&v71 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 384LL, &v71);
      std::vector<std::wstring>::clear(&v71);
    }
    v24 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"ForegroundRequiredForAccess",
            (const unsigned __int16 *)&v69,
            phkResultj);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 50LL) = v24 == 1;
    v25 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"GlobalPrompts",
            (const unsigned __int16 *)&v69,
            phkResultk);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 51LL) = v25 == 1;
    v26 = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v80, v70, L"IncludedCapabilities");
    std::vector<std::wstring>::operator=(&v71, v26);
    std::vector<std::wstring>::_Tidy(v80);
    if ( (_QWORD)v71 != *((_QWORD *)&v71 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 408LL, &v71);
      std::vector<std::wstring>::clear(&v71);
    }
    v27 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"InitAllAppsDeniedOrPrompt",
            (const unsigned __int16 *)&v69,
            phkResultl);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 52LL) = v27 == 1;
    v28 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"InitSystemGlobalConsentDenied",
            (const unsigned __int16 *)&v69,
            phkResultm);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 53LL) = v28 == 1;
    v29 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"InitUserAppConsentDenied",
            (const unsigned __int16 *)&v69,
            phkResultn);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 54LL) = v29 == 1;
    v30 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"InitUserGlobalConsentDenied",
            (const unsigned __int16 *)&v69,
            phkResulto);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 55LL) = v30 == 1;
    v31 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"RecordUsageData",
            (const unsigned __int16 *)&v69,
            phkResultp);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 58LL) = v31 == 1;
    v32 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"RequireActiveSessionForInteractiveUsers",
            (const unsigned __int16 *)&v69,
            phkResultq);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 140LL) = v32 == 1;
    v33 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"RequireExplicitDeclaration",
            (const unsigned __int16 *)&v69,
            phkResultr);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 59LL) = v33 == 1;
    v34 = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v80, v70, L"RequiredCapabilities");
    std::vector<std::wstring>::operator=(&v71, v34);
    std::vector<std::wstring>::_Tidy(v80);
    if ( (_QWORD)v71 != *((_QWORD *)&v71 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 432LL, &v71);
      std::vector<std::wstring>::clear(&v71);
    }
    v35 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"RequireWindowsCert",
            (const unsigned __int16 *)&v69,
            phkResults);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 60LL) = v35 == 1;
    v36 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"TerminateAppOnAccessChange",
            (const unsigned __int16 *)&v69,
            phkResultt);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 62LL) = v36 == 1;
    v37 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"UserConsentPromptRequired",
            (const unsigned __int16 *)&v69,
            phkResultu);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 64LL) = v37 == 1;
    v38 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v70,
            0,
            L"UserConsentRequired",
            (const unsigned __int16 *)&v69,
            phkResultv);
    if ( (_BYTE)v69 )
      *(_BYTE *)(*a1 + 65LL) = v38 == 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      v39 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v70,
              0,
              L"RequireDeveloperMode",
              (const unsigned __int16 *)&v69,
              phkResultw);
      if ( (_BYTE)v69 )
        *(_BYTE *)(*a1 + 513LL) = v39 == 1;
      v40 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v70,
              0,
              L"RequireExplicitDeclaration",
              (const unsigned __int16 *)&v69,
              phkResultx);
      if ( (_BYTE)v69 )
        *(_BYTE *)(*a1 + 59LL) = v40 == 1;
      v41 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v70,
              0,
              L"SkipCapabilityCheck",
              (const unsigned __int16 *)&v69,
              phkResulty);
      if ( (_BYTE)v69 )
        *(_BYTE *)(*a1 + 512LL) = v41 == 1;
    }
    std::vector<std::wstring>::_Tidy(&v71);
    std::wstring::_Tidy_deallocate(&v77);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v70);
  std::wstring::_Tidy_deallocate(Src);
  v42 = (std::_Ref_count_base *)a1[1];
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
}

```

## disassembly

```asm
0x180086024  push    rbp
0x180086026  push    rbx
0x180086027  push    rsi
0x180086028  push    rdi
0x180086029  lea     rbp, [rsp-3Fh]
0x18008602e  sub     rsp, 0D8h
0x180086035  mov     rax, cs:__security_cookie
0x18008603c  xor     rax, rsp
0x18008603f  mov     [rbp+57h+var_30], rax
0x180086043  mov     rbx, rcx
0x180086046  mov     [rbp+57h+var_98], rcx
0x18008604a  mov     rax, [rcx]
0x18008604d  xor     esi, esi
0x18008604f  cmp     [rax+18h], rsi
0x180086053  setz    al
0x180086056  mov     rcx, [rbp+5Fh]; this
0x18008605a  lea     rdx, aPolicyHasNotPr; "Policy has not provided a capability de"...
0x180086061  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x180086066  mov     byte ptr [rsp+0F0h+phkResult], al; char
0x18008606a  mov     r9d, 80070057h; char *
0x180086070  lea     r8, aOnecoreBaseDev_30; "onecore\\base\\devices\\cam\\policy\\ed"...
0x180086077  lea     edx, [rsi+1Ah]; void *
0x18008607a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18008607f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180086086  lea     rcx, [rbp+57h+Src]
0x18008608a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008608f  nop
0x180086090  mov     rdx, [rbp+57h+var_80]
0x180086094  lea     rcx, [rbp+57h+Src]; Src
0x180086098  cmp     rdx, [rbp+57h+var_78]
0x18008609c  jnb     short loc_1800860B3
0x18008609e  lea     rax, [rdx+1]
0x1800860a2  mov     [rbp+57h+var_80], rax
0x1800860a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800860ab  lea     edi, [rsi+5Ch]
0x1800860ae  mov     [rax+rdx*2], edi
0x1800860b1  jmp     short loc_1800860C0
0x1800860b3  mov     edi, 5Ch ; '\'
0x1800860b8  mov     r9d, edi
0x1800860bb  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800860c0  mov     r8d, 0Ch
0x1800860c6  lea     rdx, aCapabilities; "Capabilities"
0x1800860cd  lea     rcx, [rbp+57h+Src]
0x1800860d1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800860d6  mov     rdx, [rbp+57h+var_80]
0x1800860da  lea     rcx, [rbp+57h+Src]; Src
0x1800860de  cmp     rdx, [rbp+57h+var_78]
0x1800860e2  jnb     short loc_1800860FA
0x1800860e4  lea     rax, [rdx+1]
0x1800860e8  mov     [rbp+57h+var_80], rax
0x1800860ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800860f1  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x1800860f8  jmp     short loc_180086102
0x1800860fa  mov     r9d, edi
0x1800860fd  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180086102  mov     r8, [rbx]
0x180086105  lea     rcx, [r8+8]
0x180086109  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008610e  mov     r8, [r8+18h]
0x180086112  mov     rdx, rax
0x180086115  lea     rcx, [rbp+57h+Src]
0x180086119  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18008611e  mov     rdx, [rbp+57h+var_80]
0x180086122  lea     rcx, [rbp+57h+Src]; Src
0x180086126  cmp     rdx, [rbp+57h+var_78]
0x18008612a  jnb     short loc_180086142
0x18008612c  lea     rax, [rdx+1]
0x180086130  mov     [rbp+57h+var_80], rax
0x180086134  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180086139  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180086140  jmp     short loc_18008614A
0x180086142  mov     r9d, edi
0x180086145  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18008614a  mov     edi, 7
0x18008614f  mov     r8d, edi
0x180086152  lea     rdx, aEdition; "Edition"
0x180086159  lea     rcx, [rbp+57h+Src]
0x18008615d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180086162  mov     [rbp+57h+var_B8], rsi
0x180086166  xor     edx, edx
0x180086168  lea     rcx, [rbp+57h+var_B8]
0x18008616c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180086171  lea     rcx, [rbp+57h+Src]
0x180086175  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008617a  mov     rdx, rax; lpSubKey
0x18008617d  lea     rax, [rbp+57h+var_B8]
0x180086181  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x180086186  mov     r9d, 20119h; samDesired
0x18008618c  xor     r8d, r8d; ulOptions
0x18008618f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180086196  call    cs:__imp_RegOpenKeyExW
0x18008619c  cmp     eax, 2
0x18008619f  jz      loc_1800867B6
0x1800861a5  mov     rcx, [rbp+5Fh]; this
0x1800861a9  test    eax, eax
0x1800861ab  jnz     loc_1800867F0
0x1800861b1  mov     byte ptr [rbp+57h+var_C0], sil
0x1800861b5  xorps   xmm0, xmm0
0x1800861b8  movups  [rbp+57h+var_70], xmm0
0x1800861bc  mov     [rbp+57h+var_60], rsi
0x1800861c0  mov     [rbp+57h+var_58], rdi
0x1800861c4  mov     word ptr [rbp+57h+var_70], si
0x1800861c8  movdqu  [rbp+57h+var_B0], xmm0
0x1800861cd  mov     [rbp+57h+var_A0], rsi
0x1800861d1  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800861d5  lea     r8, aAllusersconsen; "AllUsersConsentRequiredForMua"
0x1800861dc  xor     edx, edx; HKEY
0x1800861de  mov     rcx, [rbp+57h+var_B8]; this
0x1800861e2  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800861e7  mov     edi, 1
0x1800861ec  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800861f0  jz      short loc_1800861FD
0x1800861f2  cmp     eax, edi
0x1800861f4  setz    cl
0x1800861f7  mov     rax, [rbx]
0x1800861fa  mov     [rax+29h], cl
0x1800861fd  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180086201  lea     r8, aAlwaysallowbef; "AlwaysAllowBeforeOOBE"
0x180086208  xor     edx, edx; HKEY
0x18008620a  mov     rcx, [rbp+57h+var_B8]; this
0x18008620e  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180086213  cmp     byte ptr [rbp+57h+var_C0], sil
0x180086217  jz      short loc_180086224
0x180086219  cmp     eax, edi
0x18008621b  setz    cl
0x18008621e  mov     rax, [rbx]
0x180086221  mov     [rax+2Ah], cl
0x180086224  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180086228  lea     r8, aAlwaysattemptp; "AlwaysAttemptPrompts"
0x18008622f  xor     edx, edx; HKEY
0x180086231  mov     rcx, [rbp+57h+var_B8]; this
0x180086235  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18008623a  cmp     byte ptr [rbp+57h+var_C0], sil
0x18008623e  jz      short loc_18008624B
0x180086240  cmp     eax, edi
0x180086242  setz    cl
0x180086245  mov     rax, [rbx]
0x180086248  mov     [rax+2Ch], cl
0x18008624b  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18008624f  lea     r8, aAlwaysblockacc; "AlwaysBlockAccess"
0x180086256  xor     edx, edx; HKEY
0x180086258  mov     rcx, [rbp+57h+var_B8]; this
0x18008625c  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180086261  cmp     byte ptr [rbp+57h+var_C0], sil
0x180086265  jz      short loc_180086272
0x180086267  cmp     eax, edi
0x180086269  setz    cl
0x18008626c  mov     rax, [rbx]
0x18008626f  mov     [rax+2Dh], cl
0x180086272  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180086276  lea     r8, aAlwaysblocknon; "AlwaysBlockNonPackaged"
0x18008627d  xor     edx, edx; HKEY
0x18008627f  mov     rcx, [rbp+57h+var_B8]; this
0x180086283  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180086288  cmp     byte ptr [rbp+57h+var_C0], sil
0x18008628c  jz      short loc_180086299
0x18008628e  cmp     eax, edi
0x180086290  setz    cl
0x180086293  mov     rax, [rbx]
0x180086296  mov     [rax+2Eh], cl
0x180086299  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18008629d  lea     r8, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x1800862a4  xor     edx, edx; HKEY
0x1800862a6  mov     rcx, [rbp+57h+var_B8]; this
0x1800862aa  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800862af  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800862b3  jz      short loc_1800862C0
0x1800862b5  cmp     eax, edi
0x1800862b7  setz    cl
0x1800862ba  mov     rax, [rbx]
0x1800862bd  mov     [rax+2Fh], cl
0x1800862c0  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800862c4  lea     r8, aAuditbehaviord; "AuditBehaviorDefault"
0x1800862cb  xor     edx, edx; HKEY
0x1800862cd  mov     rcx, [rbp+57h+var_B8]; this
0x1800862d1  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800862d6  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800862da  jz      short loc_1800862E5
0x1800862dc  mov     rcx, [rbx]
0x1800862df  mov     [rcx+88h], eax
0x1800862e5  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800862e9  lea     r8, aBlockaccess; "BlockAccess"
0x1800862f0  xor     edx, edx; HKEY
0x1800862f2  mov     rcx, [rbp+57h+var_B8]; this
0x1800862f6  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800862fb  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800862ff  jz      short loc_18008630C
0x180086301  cmp     eax, edi
0x180086303  setz    cl
0x180086306  mov     rax, [rbx]
0x180086309  mov     [rax+30h], cl
0x18008630c  lea     rax, [rbp+57h+var_C0]
0x180086310  mov     [rsp+0F0h+phkResult], rax
0x180086315  lea     r9, aCapabilityforc; "CapabilityForConsent"
0x18008631c  xor     r8d, r8d
0x18008631f  mov     rdx, [rbp+57h+var_B8]
0x180086323  lea     rcx, [rbp+57h+var_50]
0x180086327  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x18008632c  mov     rdx, rax
0x18008632f  lea     rcx, [rbp+57h+var_70]
0x180086333  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180086338  lea     rcx, [rbp+57h+var_50]
0x18008633c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180086341  cmp     byte ptr [rbp+57h+var_C0], sil
0x180086345  jz      short loc_180086367
0x180086347  mov     rcx, [rbx]
0x18008634a  add     rcx, 48h ; 'H'
0x18008634e  lea     rdx, [rbp+57h+var_70]
0x180086352  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180086357  mov     [rbp+57h+var_60], rsi
0x18008635b  lea     rcx, [rbp+57h+var_70]
0x18008635f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180086364  mov     [rax], si
0x180086367  lea     rax, [rbp+57h+var_C0]
0x18008636b  mov     [rsp+0F0h+phkResult], rax; bool *
0x180086370  lea     r9, aCapabilityforp_0; "CapabilityForPrompt"
0x180086377  xor     r8d, r8d
0x18008637a  mov     rdx, [rbp+57h+var_B8]
0x18008637e  lea     rcx, [rbp+57h+var_50]
0x180086382  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x180086387  mov     rdx, rax
0x18008638a  lea     rcx, [rbp+57h+var_70]
0x18008638e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180086393  lea     rcx, [rbp+57h+var_50]
0x180086397  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008639c  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800863a0  jz      short loc_1800863C2
0x1800863a2  mov     rcx, [rbx]
0x1800863a5  add     rcx, 68h ; 'h'
0x1800863a9  lea     rdx, [rbp+57h+var_70]
0x1800863ad  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800863b2  mov     [rbp+57h+var_60], rsi
0x1800863b6  lea     rcx, [rbp+57h+var_70]
0x1800863ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800863bf  mov     [rax], si
0x1800863c2  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800863c6  lea     r8, aCollapserecent; "CollapseRecentActivity"
0x1800863cd  xor     edx, edx; HKEY
0x1800863cf  mov     rcx, [rbp+57h+var_B8]; this
0x1800863d3  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800863d8  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800863dc  jz      short loc_1800863E9
0x1800863de  cmp     eax, edi
0x1800863e0  setz    cl
0x1800863e3  mov     rax, [rbx]
0x1800863e6  mov     [rax+31h], cl
0x1800863e9  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800863ed  lea     r8, aExtenduxlifeti; "ExtendUXLifetime"
0x1800863f4  xor     edx, edx; HKEY
0x1800863f6  mov     rcx, [rbp+57h+var_B8]; this
0x1800863fa  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800863ff  cmp     byte ptr [rbp+57h+var_C0], sil
0x180086403  jnz     short loc_180086421
0x180086405  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180086409  lea     r8, aMinimumsession; "MinimumSessionDuration"
0x180086410  xor     edx, edx; HKEY
0x180086412  mov     rcx, [rbp+57h+var_B8]; this
0x180086416  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18008641b  cmp     byte ptr [rbp+57h+var_C0], sil
0x18008641f  jz      short loc_18008642C
0x180086421  cmp     eax, edi
0x180086423  mov     rax, [rbx]
0x180086426  setz    cl
0x180086429  mov     [rax+38h], cl
0x18008642c  lea     r8, aFallbacktokenc; "FallbackTokenCapabilities"
0x180086433  mov     rdx, [rbp+57h+var_B8]
0x180086437  lea     rcx, [rbp+57h+var_50]
0x18008643b  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x180086440  mov     rdx, rax
0x180086443  lea     rcx, [rbp+57h+var_B0]
0x180086447  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x18008644c  lea     rcx, [rbp+57h+var_50]
0x180086450  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180086455  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x180086459  cmp     qword ptr [rbp+57h+var_B0], rax
0x18008645d  jz      short loc_18008647B
0x18008645f  mov     rcx, [rbx]
0x180086462  add     rcx, 180h
0x180086469  lea     rdx, [rbp+57h+var_B0]
0x18008646d  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x180086472  lea     rcx, [rbp+57h+var_B0]
0x180086476  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18008647b  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18008647f  lea     r8, aForegroundrequ; "ForegroundRequiredForAccess"
0x180086486  xor     edx, edx; HKEY
0x180086488  mov     rcx, [rbp+57h+var_B8]; this
0x18008648c  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180086491  cmp     byte ptr [rbp+57h+var_C0], sil
0x180086495  jz      short loc_1800864A2
0x180086497  cmp     eax, edi
0x180086499  setz    cl
0x18008649c  mov     rax, [rbx]
0x18008649f  mov     [rax+32h], cl
0x1800864a2  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800864a6  lea     r8, aGlobalprompts; "GlobalPrompts"
0x1800864ad  xor     edx, edx; HKEY
0x1800864af  mov     rcx, [rbp+57h+var_B8]; this
0x1800864b3  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800864b8  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800864bc  jz      short loc_1800864C9
  ... truncated ...
```
