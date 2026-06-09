# Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)

- ea: `0x180035308`
- end: `0x180035ae9`
- name: `?AddPresentEditionPolicy@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z`
- size: `2017`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003484c`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x180014754`
- `0x18001b444`
- `0x18001c330`
- `0x1800207a4`
- `0x180021550`
- `0x180021638`
- `0x1800236ac`
- `0x18002392c`
- `0x180023b38`
- `0x180024358`
- `0x180025080`
- `0x180028414`
- `0x18002f06c`
- `0x18002f4c8`
- `0x18002f690`
- `0x18002f800`
- `0x18002fa94`
- `0x180035308`
- `0x180035af0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003547a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003547a`

## string_xrefs

- `0x180035363`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180035763`: `ForegroundRequiredForAccess`
- `0x180035710`: `FallbackTokenCapabilities`
- `0x18003550c`: `AlwaysAttemptPrompts`
- `0x180035533`: `AlwaysBlockAccess`
- `0x1800355cd`: `BlockAccess`
- `0x18003598a`: `TerminateAppOnAccessChange`
- `0x180035581`: `AppLaunchAccessCheckRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddPresentEditionPolicy(_QWORD *a1)
{
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  const WCHAR *v23; // rax
  unsigned int v24; // eax
  unsigned int Uint32Value; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 StringValue; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned int v41; // eax
  unsigned int v42; // eax
  __int64 KeyArray; // rax
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v46; // rax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  __int64 v54; // rax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  std::_Ref_count_base *v62; // rcx
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
  const char *v89; // [rsp+30h] [rbp-69h] BYREF
  HKEY v90; // [rsp+38h] [rbp-61h] BYREF
  __int128 v91; // [rsp+40h] [rbp-59h] BYREF
  __int64 v92; // [rsp+50h] [rbp-49h]
  _QWORD *v93; // [rsp+58h] [rbp-41h]
  _BYTE Src[16]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v95; // [rsp+70h] [rbp-29h]
  unsigned __int64 v96; // [rsp+78h] [rbp-21h]
  __int128 v97; // [rsp+80h] [rbp-19h] BYREF
  __int64 v98; // [rsp+90h] [rbp-9h]
  __int64 v99; // [rsp+98h] [rbp-1h]
  _BYTE v100[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v93 = a1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1A,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\edition.cpp",
    (const char *)0x80070057LL,
    *(_QWORD *)(*a1 + 24LL) == 0,
    (bool)"Policy has not provided a capability definition to parse Edition policy",
    v89);
  std::wstring::wstring((__int64)Src, (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  v4 = v95;
  if ( v95 >= v96 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v95;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v4, v2, v3);
    *(_DWORD *)(v5 + 2 * v6) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Capabilities", 12);
  v9 = v95;
  if ( v95 >= v96 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v95;
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v9, v7, v8);
    *(_DWORD *)(v10 + 2 * v11) = 92;
  }
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 8LL, v11, *a1, v12);
  std::wstring::_Append<unsigned short>(Src, v13, *(_QWORD *)(v14 + 24));
  v17 = v95;
  if ( v95 >= v96 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v95;
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v17, v15, v16);
    *(_DWORD *)(v18 + 2 * v19) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Edition", 7);
  v90 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v90,
    0);
  v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v20, v21, v22);
  v24 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v23, 0, 0x20119u, &v90);
  if ( v24 != 2 )
  {
    if ( v24 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\edition.cpp",
        (const char *)v24,
        (unsigned int)phkResult);
    LOBYTE(v89) = 0;
    v97 = 0;
    v98 = 0;
    v99 = 7;
    LOWORD(v97) = 0;
    v91 = 0;
    v92 = 0;
    Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                    (Windows::Internal::CapabilityAccess::Private *)v90,
                    0,
                    L"AllUsersConsentRequiredForMua",
                    (const unsigned __int16 *)&v89,
                    phkResult);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 41LL) = Uint32Value == 1;
    v26 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AlwaysAllowBeforeOOBE",
            (const unsigned __int16 *)&v89,
            phkResulta);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 42LL) = v26 == 1;
    v27 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AlwaysAttemptPrompts",
            (const unsigned __int16 *)&v89,
            phkResultb);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 44LL) = v27 == 1;
    v28 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AlwaysBlockAccess",
            (const unsigned __int16 *)&v89,
            phkResultc);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 45LL) = v28 == 1;
    v29 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AlwaysBlockNonPackaged",
            (const unsigned __int16 *)&v89,
            phkResultd);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 46LL) = v29 == 1;
    v30 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AppLaunchAccessCheckRequired",
            (const unsigned __int16 *)&v89,
            phkResulte);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 47LL) = v30 == 1;
    v31 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"AuditBehaviorDefault",
            (const unsigned __int16 *)&v89,
            phkResultf);
    if ( (_BYTE)v89 )
      *(_DWORD *)(*a1 + 136LL) = v31;
    v32 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"BlockAccess",
            (const unsigned __int16 *)&v89,
            phkResultg);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 48LL) = v32 == 1;
    StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
                    v100,
                    v90,
                    0,
                    L"CapabilityForConsent",
                    &v89);
    std::wstring::operator=(&v97, StringValue);
    std::wstring::_Tidy_deallocate(v100);
    if ( (_BYTE)v89 )
    {
      std::wstring::operator=(*a1 + 72LL, &v97);
      v98 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v97, v34, v35, v36) = 0;
    }
    v37 = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(v100, v90, 0, L"CapabilityForPrompt", &v89);
    std::wstring::operator=(&v97, v37);
    std::wstring::_Tidy_deallocate(v100);
    if ( (_BYTE)v89 )
    {
      std::wstring::operator=(*a1 + 104LL, &v97);
      v98 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v97, v38, v39, v40) = 0;
    }
    v41 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"CollapseRecentActivity",
            (const unsigned __int16 *)&v89,
            phkResulth);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 49LL) = v41 == 1;
    v42 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"ExtendUXLifetime",
            (const unsigned __int16 *)&v89,
            phkResulti);
    if ( (_BYTE)v89
      || (v42 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                  (Windows::Internal::CapabilityAccess::Private *)v90,
                  0,
                  L"MinimumSessionDuration",
                  (const unsigned __int16 *)&v89,
                  phkResultj),
          (_BYTE)v89) )
    {
      *(_BYTE *)(*a1 + 56LL) = v42 == 1;
    }
    KeyArray = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v100, v90, L"FallbackTokenCapabilities");
    std::vector<std::wstring>::operator=(&v91, KeyArray);
    std::vector<std::wstring>::_Tidy(v100);
    if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 384LL, &v91);
      std::vector<std::wstring>::clear(&v91);
    }
    v44 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"ForegroundRequiredForAccess",
            (const unsigned __int16 *)&v89,
            phkResultj);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 50LL) = v44 == 1;
    v45 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"GlobalPrompts",
            (const unsigned __int16 *)&v89,
            phkResultk);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 51LL) = v45 == 1;
    v46 = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v100, v90, L"IncludedCapabilities");
    std::vector<std::wstring>::operator=(&v91, v46);
    std::vector<std::wstring>::_Tidy(v100);
    if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 408LL, &v91);
      std::vector<std::wstring>::clear(&v91);
    }
    v47 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"InitAllAppsDeniedOrPrompt",
            (const unsigned __int16 *)&v89,
            phkResultl);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 52LL) = v47 == 1;
    v48 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"InitSystemGlobalConsentDenied",
            (const unsigned __int16 *)&v89,
            phkResultm);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 53LL) = v48 == 1;
    v49 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"InitUserAppConsentDenied",
            (const unsigned __int16 *)&v89,
            phkResultn);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 54LL) = v49 == 1;
    v50 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"InitUserGlobalConsentDenied",
            (const unsigned __int16 *)&v89,
            phkResulto);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 55LL) = v50 == 1;
    v51 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"RecordUsageData",
            (const unsigned __int16 *)&v89,
            phkResultp);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 58LL) = v51 == 1;
    v52 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"RequireActiveSessionForInteractiveUsers",
            (const unsigned __int16 *)&v89,
            phkResultq);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 140LL) = v52 == 1;
    v53 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"RequireExplicitDeclaration",
            (const unsigned __int16 *)&v89,
            phkResultr);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 59LL) = v53 == 1;
    v54 = Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v100, v90, L"RequiredCapabilities");
    std::vector<std::wstring>::operator=(&v91, v54);
    std::vector<std::wstring>::_Tidy(v100);
    if ( (_QWORD)v91 != *((_QWORD *)&v91 + 1) )
    {
      std::vector<std::wstring>::operator=(*a1 + 432LL, &v91);
      std::vector<std::wstring>::clear(&v91);
    }
    v55 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"RequireWindowsCert",
            (const unsigned __int16 *)&v89,
            phkResults);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 60LL) = v55 == 1;
    v56 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"TerminateAppOnAccessChange",
            (const unsigned __int16 *)&v89,
            phkResultt);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 62LL) = v56 == 1;
    v57 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"UserConsentPromptRequired",
            (const unsigned __int16 *)&v89,
            phkResultu);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 64LL) = v57 == 1;
    v58 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)v90,
            0,
            L"UserConsentRequired",
            (const unsigned __int16 *)&v89,
            phkResultv);
    if ( (_BYTE)v89 )
      *(_BYTE *)(*a1 + 65LL) = v58 == 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      v59 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v90,
              0,
              L"RequireDeveloperMode",
              (const unsigned __int16 *)&v89,
              phkResultw);
      if ( (_BYTE)v89 )
        *(_BYTE *)(*a1 + 513LL) = v59 == 1;
      v60 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v90,
              0,
              L"RequireExplicitDeclaration",
              (const unsigned __int16 *)&v89,
              phkResultx);
      if ( (_BYTE)v89 )
        *(_BYTE *)(*a1 + 59LL) = v60 == 1;
      v61 = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
              (Windows::Internal::CapabilityAccess::Private *)v90,
              0,
              L"SkipCapabilityCheck",
              (const unsigned __int16 *)&v89,
              phkResulty);
      if ( (_BYTE)v89 )
        *(_BYTE *)(*a1 + 512LL) = v61 == 1;
    }
    std::vector<std::wstring>::_Tidy(&v91);
    std::wstring::_Tidy_deallocate(&v97);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v90);
  std::wstring::_Tidy_deallocate(Src);
  v62 = (std::_Ref_count_base *)a1[1];
  if ( v62 )
    std::_Ref_count_base::_Decref(v62);
}

```

## disassembly

```asm
0x180035308  push    rbp
0x18003530a  push    rbx
0x18003530b  push    rsi
0x18003530c  push    rdi
0x18003530d  lea     rbp, [rsp-3Fh]
0x180035312  sub     rsp, 0D8h
0x180035319  mov     rax, cs:__security_cookie
0x180035320  xor     rax, rsp
0x180035323  mov     [rbp+57h+var_30], rax
0x180035327  mov     rbx, rcx
0x18003532a  mov     [rbp+57h+var_98], rcx
0x18003532e  mov     rax, [rcx]
0x180035331  xor     esi, esi
0x180035333  cmp     [rax+18h], rsi
0x180035337  setz    al
0x18003533a  mov     rcx, [rbp+5Fh]; this
0x18003533e  lea     rdx, aPolicyHasNotPr; "Policy has not provided a capability de"...
0x180035345  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x18003534a  mov     byte ptr [rsp+0F0h+phkResult], al; char
0x18003534e  mov     r9d, 80070057h; char *
0x180035354  lea     r8, aOnecoreBaseDev_5; "onecore\\base\\devices\\cam\\policy\\ed"...
0x18003535b  lea     edx, [rsi+1Ah]; void *
0x18003535e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180035363  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003536a  lea     rcx, [rbp+57h+Src]
0x18003536e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035373  nop
0x180035374  mov     rdx, [rbp+57h+var_80]
0x180035378  lea     rcx, [rbp+57h+Src]; Src
0x18003537c  cmp     rdx, [rbp+57h+var_78]
0x180035380  jnb     short loc_180035397
0x180035382  lea     rax, [rdx+1]
0x180035386  mov     [rbp+57h+var_80], rax
0x18003538a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003538f  lea     edi, [rsi+5Ch]
0x180035392  mov     [rax+rdx*2], edi
0x180035395  jmp     short loc_1800353A4
0x180035397  mov     edi, 5Ch ; '\'
0x18003539c  mov     r9d, edi
0x18003539f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800353a4  mov     r8d, 0Ch
0x1800353aa  lea     rdx, aCapabilities; "Capabilities"
0x1800353b1  lea     rcx, [rbp+57h+Src]
0x1800353b5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800353ba  mov     rdx, [rbp+57h+var_80]
0x1800353be  lea     rcx, [rbp+57h+Src]; Src
0x1800353c2  cmp     rdx, [rbp+57h+var_78]
0x1800353c6  jnb     short loc_1800353DE
0x1800353c8  lea     rax, [rdx+1]
0x1800353cc  mov     [rbp+57h+var_80], rax
0x1800353d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800353d5  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x1800353dc  jmp     short loc_1800353E6
0x1800353de  mov     r9d, edi
0x1800353e1  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800353e6  mov     r8, [rbx]
0x1800353e9  lea     rcx, [r8+8]
0x1800353ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800353f2  mov     r8, [r8+18h]
0x1800353f6  mov     rdx, rax
0x1800353f9  lea     rcx, [rbp+57h+Src]
0x1800353fd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180035402  mov     rdx, [rbp+57h+var_80]
0x180035406  lea     rcx, [rbp+57h+Src]; Src
0x18003540a  cmp     rdx, [rbp+57h+var_78]
0x18003540e  jnb     short loc_180035426
0x180035410  lea     rax, [rdx+1]
0x180035414  mov     [rbp+57h+var_80], rax
0x180035418  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003541d  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180035424  jmp     short loc_18003542E
0x180035426  mov     r9d, edi
0x180035429  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18003542e  mov     edi, 7
0x180035433  mov     r8d, edi
0x180035436  lea     rdx, aEdition; "Edition"
0x18003543d  lea     rcx, [rbp+57h+Src]
0x180035441  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180035446  mov     [rbp+57h+var_B8], rsi
0x18003544a  xor     edx, edx
0x18003544c  lea     rcx, [rbp+57h+var_B8]
0x180035450  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180035455  lea     rcx, [rbp+57h+Src]
0x180035459  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003545e  mov     rdx, rax; lpSubKey
0x180035461  lea     rax, [rbp+57h+var_B8]
0x180035465  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18003546a  mov     r9d, 20119h; samDesired
0x180035470  xor     r8d, r8d; ulOptions
0x180035473  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003547a  call    cs:__imp_RegOpenKeyExW
0x180035480  cmp     eax, 2
0x180035483  jz      loc_180035A9A
0x180035489  mov     rcx, [rbp+5Fh]; this
0x18003548d  test    eax, eax
0x18003548f  jnz     loc_180035AD4
0x180035495  mov     byte ptr [rbp+57h+var_C0], sil
0x180035499  xorps   xmm0, xmm0
0x18003549c  movups  [rbp+57h+var_70], xmm0
0x1800354a0  mov     [rbp+57h+var_60], rsi
0x1800354a4  mov     [rbp+57h+var_58], rdi
0x1800354a8  mov     word ptr [rbp+57h+var_70], si
0x1800354ac  movdqu  [rbp+57h+var_B0], xmm0
0x1800354b1  mov     [rbp+57h+var_A0], rsi
0x1800354b5  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800354b9  lea     r8, aAllusersconsen; "AllUsersConsentRequiredForMua"
0x1800354c0  xor     edx, edx; HKEY
0x1800354c2  mov     rcx, [rbp+57h+var_B8]; this
0x1800354c6  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800354cb  mov     edi, 1
0x1800354d0  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800354d4  jz      short loc_1800354E1
0x1800354d6  cmp     eax, edi
0x1800354d8  setz    cl
0x1800354db  mov     rax, [rbx]
0x1800354de  mov     [rax+29h], cl
0x1800354e1  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800354e5  lea     r8, aAlwaysallowbef; "AlwaysAllowBeforeOOBE"
0x1800354ec  xor     edx, edx; HKEY
0x1800354ee  mov     rcx, [rbp+57h+var_B8]; this
0x1800354f2  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800354f7  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800354fb  jz      short loc_180035508
0x1800354fd  cmp     eax, edi
0x1800354ff  setz    cl
0x180035502  mov     rax, [rbx]
0x180035505  mov     [rax+2Ah], cl
0x180035508  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18003550c  lea     r8, aAlwaysattemptp; "AlwaysAttemptPrompts"
0x180035513  xor     edx, edx; HKEY
0x180035515  mov     rcx, [rbp+57h+var_B8]; this
0x180035519  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18003551e  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035522  jz      short loc_18003552F
0x180035524  cmp     eax, edi
0x180035526  setz    cl
0x180035529  mov     rax, [rbx]
0x18003552c  mov     [rax+2Ch], cl
0x18003552f  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180035533  lea     r8, aAlwaysblockacc; "AlwaysBlockAccess"
0x18003553a  xor     edx, edx; HKEY
0x18003553c  mov     rcx, [rbp+57h+var_B8]; this
0x180035540  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180035545  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035549  jz      short loc_180035556
0x18003554b  cmp     eax, edi
0x18003554d  setz    cl
0x180035550  mov     rax, [rbx]
0x180035553  mov     [rax+2Dh], cl
0x180035556  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18003555a  lea     r8, aAlwaysblocknon; "AlwaysBlockNonPackaged"
0x180035561  xor     edx, edx; HKEY
0x180035563  mov     rcx, [rbp+57h+var_B8]; this
0x180035567  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18003556c  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035570  jz      short loc_18003557D
0x180035572  cmp     eax, edi
0x180035574  setz    cl
0x180035577  mov     rax, [rbx]
0x18003557a  mov     [rax+2Eh], cl
0x18003557d  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180035581  lea     r8, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x180035588  xor     edx, edx; HKEY
0x18003558a  mov     rcx, [rbp+57h+var_B8]; this
0x18003558e  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180035593  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035597  jz      short loc_1800355A4
0x180035599  cmp     eax, edi
0x18003559b  setz    cl
0x18003559e  mov     rax, [rbx]
0x1800355a1  mov     [rax+2Fh], cl
0x1800355a4  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800355a8  lea     r8, aAuditbehaviord; "AuditBehaviorDefault"
0x1800355af  xor     edx, edx; HKEY
0x1800355b1  mov     rcx, [rbp+57h+var_B8]; this
0x1800355b5  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800355ba  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800355be  jz      short loc_1800355C9
0x1800355c0  mov     rcx, [rbx]
0x1800355c3  mov     [rcx+88h], eax
0x1800355c9  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800355cd  lea     r8, aBlockaccess; "BlockAccess"
0x1800355d4  xor     edx, edx; HKEY
0x1800355d6  mov     rcx, [rbp+57h+var_B8]; this
0x1800355da  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800355df  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800355e3  jz      short loc_1800355F0
0x1800355e5  cmp     eax, edi
0x1800355e7  setz    cl
0x1800355ea  mov     rax, [rbx]
0x1800355ed  mov     [rax+30h], cl
0x1800355f0  lea     rax, [rbp+57h+var_C0]
0x1800355f4  mov     [rsp+0F0h+phkResult], rax
0x1800355f9  lea     r9, aCapabilityforc; "CapabilityForConsent"
0x180035600  xor     r8d, r8d
0x180035603  mov     rdx, [rbp+57h+var_B8]
0x180035607  lea     rcx, [rbp+57h+var_50]
0x18003560b  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x180035610  mov     rdx, rax
0x180035613  lea     rcx, [rbp+57h+var_70]
0x180035617  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003561c  lea     rcx, [rbp+57h+var_50]
0x180035620  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035625  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035629  jz      short loc_18003564B
0x18003562b  mov     rcx, [rbx]
0x18003562e  add     rcx, 48h ; 'H'
0x180035632  lea     rdx, [rbp+57h+var_70]
0x180035636  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003563b  mov     [rbp+57h+var_60], rsi
0x18003563f  lea     rcx, [rbp+57h+var_70]
0x180035643  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035648  mov     [rax], si
0x18003564b  lea     rax, [rbp+57h+var_C0]
0x18003564f  mov     [rsp+0F0h+phkResult], rax; bool *
0x180035654  lea     r9, aCapabilityforp_0; "CapabilityForPrompt"
0x18003565b  xor     r8d, r8d
0x18003565e  mov     rdx, [rbp+57h+var_B8]
0x180035662  lea     rcx, [rbp+57h+var_50]
0x180035666  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x18003566b  mov     rdx, rax
0x18003566e  lea     rcx, [rbp+57h+var_70]
0x180035672  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180035677  lea     rcx, [rbp+57h+var_50]
0x18003567b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035680  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035684  jz      short loc_1800356A6
0x180035686  mov     rcx, [rbx]
0x180035689  add     rcx, 68h ; 'h'
0x18003568d  lea     rdx, [rbp+57h+var_70]
0x180035691  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180035696  mov     [rbp+57h+var_60], rsi
0x18003569a  lea     rcx, [rbp+57h+var_70]
0x18003569e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800356a3  mov     [rax], si
0x1800356a6  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800356aa  lea     r8, aCollapserecent; "CollapseRecentActivity"
0x1800356b1  xor     edx, edx; HKEY
0x1800356b3  mov     rcx, [rbp+57h+var_B8]; this
0x1800356b7  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800356bc  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800356c0  jz      short loc_1800356CD
0x1800356c2  cmp     eax, edi
0x1800356c4  setz    cl
0x1800356c7  mov     rax, [rbx]
0x1800356ca  mov     [rax+31h], cl
0x1800356cd  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800356d1  lea     r8, aExtenduxlifeti; "ExtendUXLifetime"
0x1800356d8  xor     edx, edx; HKEY
0x1800356da  mov     rcx, [rbp+57h+var_B8]; this
0x1800356de  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800356e3  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800356e7  jnz     short loc_180035705
0x1800356e9  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x1800356ed  lea     r8, aMinimumsession; "MinimumSessionDuration"
0x1800356f4  xor     edx, edx; HKEY
0x1800356f6  mov     rcx, [rbp+57h+var_B8]; this
0x1800356fa  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800356ff  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035703  jz      short loc_180035710
0x180035705  cmp     eax, edi
0x180035707  mov     rax, [rbx]
0x18003570a  setz    cl
0x18003570d  mov     [rax+38h], cl
0x180035710  lea     r8, aFallbacktokenc; "FallbackTokenCapabilities"
0x180035717  mov     rdx, [rbp+57h+var_B8]
0x18003571b  lea     rcx, [rbp+57h+var_50]
0x18003571f  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x180035724  mov     rdx, rax
0x180035727  lea     rcx, [rbp+57h+var_B0]
0x18003572b  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x180035730  lea     rcx, [rbp+57h+var_50]
0x180035734  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180035739  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x18003573d  cmp     qword ptr [rbp+57h+var_B0], rax
0x180035741  jz      short loc_18003575F
0x180035743  mov     rcx, [rbx]
0x180035746  add     rcx, 180h
0x18003574d  lea     rdx, [rbp+57h+var_B0]
0x180035751  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> const &)
0x180035756  lea     rcx, [rbp+57h+var_B0]
0x18003575a  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18003575f  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x180035763  lea     r8, aForegroundrequ; "ForegroundRequiredForAccess"
0x18003576a  xor     edx, edx; HKEY
0x18003576c  mov     rcx, [rbp+57h+var_B8]; this
0x180035770  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180035775  cmp     byte ptr [rbp+57h+var_C0], sil
0x180035779  jz      short loc_180035786
0x18003577b  cmp     eax, edi
0x18003577d  setz    cl
0x180035780  mov     rax, [rbx]
0x180035783  mov     [rax+32h], cl
0x180035786  lea     r9, [rbp+57h+var_C0]; unsigned __int16 *
0x18003578a  lea     r8, aGlobalprompts; "GlobalPrompts"
0x180035791  xor     edx, edx; HKEY
0x180035793  mov     rcx, [rbp+57h+var_B8]; this
0x180035797  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18003579c  cmp     byte ptr [rbp+57h+var_C0], sil
0x1800357a0  jz      short loc_1800357AD
  ... truncated ...
```
