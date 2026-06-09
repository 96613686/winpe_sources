# Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)

- ea: `0x180085b18`
- end: `0x18008601d`
- name: `?AddLegacyRegistryOverrides@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z`
- size: `1285`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180085568`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x180020fcc`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002e304`
- `0x18002f280`
- `0x18003afa0`
- `0x18003ce34`
- `0x1800473fc`
- `0x180051874`
- `0x180052674`
- `0x180052a78`
- `0x180055158`
- `0x1800583e0`
- `0x180058ac4`
- `0x180085b18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180085f3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085c60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085c60`

## string_xrefs

- `0x180085b84`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180085e9d`: `AlwaysBlockAccess`
- `0x180085e3d`: `BlockAccess`
- `0x180085d7d`: `TerminateAppOnAccessChange`
- `0x180085d4d`: `AppLaunchAccessCheckRequired`
- `0x180085b73`: `onecore\base\devices\cam\policy\registryoverrides.cpp`
- `0x18008600b`: `onecore\base\devices\cam\policy\registryoverrides.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r14
  __int64 i; // r15
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  std::_Ref_count_base *v16; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY v18; // [rsp+30h] [rbp-D0h] BYREF
  void **v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  _QWORD *v25; // [rsp+80h] [rbp-80h]
  char v26; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v27[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v30; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v31; // [rsp+D8h] [rbp-28h]
  _BYTE Src[16]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v33; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v34; // [rsp+F8h] [rbp-8h]
  _BYTE v35[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v36; // [rsp+110h] [rbp+10h]
  _BYTE v37[32]; // [rsp+120h] [rbp+20h] BYREF
  void **v38; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v25 = a1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x32,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\registryoverrides.cpp",
    (const char *)0x80070057LL,
    *(_QWORD *)(*a1 + 24LL) == 0,
    (bool)"Policy has not provided a capability definition to parse Edition policy",
    (const char *)v18);
  std::wstring::wstring(Src, L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  if ( v33 >= v34 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v33;
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_DWORD *)(v2 + 2 * v3) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Capabilities");
  if ( v33 >= v34 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v33;
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    *(_DWORD *)(v4 + 2 * v5) = 92;
  }
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 8LL);
  std::wstring::_Append<unsigned short>(Src, v6);
  v18 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20119u, &v18);
  if ( v8 != 2 )
  {
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\registryoverrides.cpp",
        (const char *)v8,
        phkResult);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v23, v18, L"Apps");
    v9 = v23;
    for ( i = v24; v9 != i; v9 += 32 )
    {
      if ( !std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(
              *a1 + 168LL,
              v9) )
      {
        std::wstring::wstring(v35, v9);
        std::wstring::wstring(v29, L"Apps");
        if ( v30 >= v31 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v29);
        }
        else
        {
          ++v30;
          v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
          *(_DWORD *)(v11 + 2 * v12) = 92;
        }
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        std::wstring::_Append<unsigned short>(v29, v13);
        v19 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v20 = 0;
        v21 = 0;
        v22 = 0;
        std::wstring::wstring(v28, L"AppLaunchAccessCheckRequired");
        LODWORD(v20) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"TerminateAppOnAccessChange");
        DWORD1(v20) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"UserConsentRequired");
        DWORD2(v20) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"UserConsentPromptRequired");
        HIDWORD(v20) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"UserAppConsentRequired");
        LODWORD(v21) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"BlockAccess");
        DWORD1(v21) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"InitUserAppConsentDenied");
        DWORD2(v21) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"AlwaysBlockAccess");
        HIDWORD(v21) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"GlobalPrompts");
        LODWORD(v22) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        std::wstring::wstring(v28, L"RequireWindowsCert");
        HIDWORD(v22) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v18, v29, v28);
        std::wstring::_Tidy_deallocate(v28);
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v26,
          v14,
          v14 + 2 * v36,
          v14,
          *(__int64 *)&_o_towlower);
        v15 = *a1;
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          v37,
          v35,
          &v19);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          v15 + 168,
          v27,
          v37);
        v38 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(v37);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v35);
      }
    }
    std::vector<std::wstring>::_Tidy(&v23);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  std::wstring::_Tidy_deallocate(Src);
  v16 = (std::_Ref_count_base *)a1[1];
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
}

```

## disassembly

```asm
0x180085b18  mov     [rsp-8+arg_8], rbx
0x180085b1d  mov     [rsp-8+arg_10], rsi
0x180085b22  push    rbp
0x180085b23  push    rdi
0x180085b24  push    r13
0x180085b26  push    r14
0x180085b28  push    r15
0x180085b2a  lea     rbp, [rsp-80h]
0x180085b2f  sub     rsp, 180h
0x180085b36  mov     rax, cs:__security_cookie
0x180085b3d  xor     rax, rsp
0x180085b40  mov     [rbp+0A0h+var_30], rax
0x180085b44  mov     rsi, rcx
0x180085b47  mov     [rbp+0A0h+var_120], rcx
0x180085b4b  mov     rax, [rcx]
0x180085b4e  cmp     qword ptr [rax+18h], 0
0x180085b53  setz    al
0x180085b56  mov     rcx, [rbp+0A8h]; this
0x180085b5d  lea     rdx, aPolicyHasNotPr; "Policy has not provided a capability de"...
0x180085b64  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x180085b69  mov     byte ptr [rsp+1A0h+phkResult], al; char
0x180085b6d  mov     r9d, 80070057h; char *
0x180085b73  lea     r8, aOnecoreBaseDev_12; "onecore\\base\\devices\\cam\\policy\\re"...
0x180085b7a  mov     edx, 32h ; '2'; void *
0x180085b7f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180085b84  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180085b8b  lea     rcx, [rbp+0A0h+Src]
0x180085b8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085b94  nop
0x180085b95  mov     rdx, [rbp+0A0h+var_B0]
0x180085b99  lea     rcx, [rbp+0A0h+Src]; Src
0x180085b9d  cmp     rdx, [rbp+0A0h+var_A8]
0x180085ba1  jnb     short loc_180085BBA
0x180085ba3  lea     rax, [rdx+1]
0x180085ba7  mov     [rbp+0A0h+var_B0], rax
0x180085bab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085bb0  mov     edi, 5Ch ; '\'
0x180085bb5  mov     [rax+rdx*2], edi
0x180085bb8  jmp     short loc_180085BC7
0x180085bba  mov     edi, 5Ch ; '\'
0x180085bbf  mov     r9d, edi
0x180085bc2  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180085bc7  mov     r8d, 0Ch
0x180085bcd  lea     rdx, aCapabilities; "Capabilities"
0x180085bd4  lea     rcx, [rbp+0A0h+Src]
0x180085bd8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180085bdd  mov     rdx, [rbp+0A0h+var_B0]
0x180085be1  lea     rcx, [rbp+0A0h+Src]; Src
0x180085be5  cmp     rdx, [rbp+0A0h+var_A8]
0x180085be9  jnb     short loc_180085C01
0x180085beb  lea     rax, [rdx+1]
0x180085bef  mov     [rbp+0A0h+var_B0], rax
0x180085bf3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085bf8  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180085bff  jmp     short loc_180085C09
0x180085c01  mov     r9d, edi
0x180085c04  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180085c09  mov     r8, [rsi]
0x180085c0c  lea     rcx, [r8+8]
0x180085c10  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085c15  mov     r8, [r8+18h]
0x180085c19  mov     rdx, rax
0x180085c1c  lea     rcx, [rbp+0A0h+Src]
0x180085c20  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180085c25  mov     [rsp+1A0h+var_170], 0
0x180085c2e  xor     edx, edx
0x180085c30  lea     rcx, [rsp+1A0h+var_170]
0x180085c35  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180085c3a  lea     rcx, [rbp+0A0h+Src]
0x180085c3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085c43  mov     rdx, rax; lpSubKey
0x180085c46  lea     rax, [rsp+1A0h+var_170]
0x180085c4b  mov     [rsp+1A0h+phkResult], rax; unsigned int
0x180085c50  mov     r9d, 20119h; samDesired
0x180085c56  xor     r8d, r8d; ulOptions
0x180085c59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085c60  call    cs:__imp_RegOpenKeyExW
0x180085c66  cmp     eax, 2
0x180085c69  jz      loc_180085FBD
0x180085c6f  mov     rcx, [rbp+0A8h]; this
0x180085c76  test    eax, eax
0x180085c78  jnz     loc_180086008
0x180085c7e  lea     r8, aApps; "Apps"
0x180085c85  mov     rdx, [rsp+1A0h+var_170]
0x180085c8a  lea     rcx, [rsp+1A0h+var_138]
0x180085c8f  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x180085c94  nop
0x180085c95  mov     r14, [rsp+1A0h+var_138]
0x180085c9a  mov     r15, [rsp+1A0h+var_130]
0x180085c9f  cmp     r14, r15
0x180085ca2  jz      loc_180085FB2
0x180085ca8  lea     r13, ??_7CapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@6B@; const Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable'
0x180085caf  mov     rcx, [rsi]
0x180085cb2  add     rcx, 0A8h
0x180085cb9  mov     rdx, r14
0x180085cbc  call    ?count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(std::wstring const &)
0x180085cc1  test    rax, rax
0x180085cc4  jnz     loc_180085FA5
0x180085cca  mov     rdx, r14
0x180085ccd  lea     rcx, [rbp+0A0h+var_A0]
0x180085cd1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180085cd6  nop
0x180085cd7  lea     rdx, aApps; "Apps"
0x180085cde  lea     rcx, [rbp+0A0h+var_E0]
0x180085ce2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085ce7  nop
0x180085ce8  mov     rdx, [rbp+0A0h+var_D0]
0x180085cec  lea     rcx, [rbp+0A0h+var_E0]; Src
0x180085cf0  cmp     rdx, [rbp+0A0h+var_C8]
0x180085cf4  jnb     short loc_180085D0C
0x180085cf6  lea     rax, [rdx+1]
0x180085cfa  mov     [rbp+0A0h+var_D0], rax
0x180085cfe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085d03  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180085d0a  jmp     short loc_180085D14
0x180085d0c  mov     r9d, edi
0x180085d0f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180085d14  lea     rcx, [rbp+0A0h+var_A0]
0x180085d18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085d1d  mov     rdx, rax
0x180085d20  mov     r8, [rbp+0A0h+var_90]
0x180085d24  lea     rcx, [rbp+0A0h+var_E0]
0x180085d28  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180085d2d  mov     [rsp+1A0h+var_168], r13
0x180085d32  xorps   xmm0, xmm0
0x180085d35  movdqu  [rsp+1A0h+var_160], xmm0
0x180085d3b  xorps   xmm1, xmm1
0x180085d3e  movdqu  [rsp+1A0h+var_150], xmm1
0x180085d44  mov     [rsp+1A0h+var_140], 0
0x180085d4d  lea     rdx, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x180085d54  lea     rcx, [rbp+0A0h+var_100]
0x180085d58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085d5d  nop
0x180085d5e  lea     r8, [rbp+0A0h+var_100]
0x180085d62  lea     rdx, [rbp+0A0h+var_E0]
0x180085d66  lea     rcx, [rsp+1A0h+var_170]
0x180085d6b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085d70  mov     dword ptr [rsp+1A0h+var_160], eax
0x180085d74  lea     rcx, [rbp+0A0h+var_100]
0x180085d78  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085d7d  lea     rdx, aTerminateappon; "TerminateAppOnAccessChange"
0x180085d84  lea     rcx, [rbp+0A0h+var_100]
0x180085d88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085d8d  nop
0x180085d8e  lea     r8, [rbp+0A0h+var_100]
0x180085d92  lea     rdx, [rbp+0A0h+var_E0]
0x180085d96  lea     rcx, [rsp+1A0h+var_170]
0x180085d9b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085da0  mov     dword ptr [rsp+1A0h+var_160+4], eax
0x180085da4  lea     rcx, [rbp+0A0h+var_100]
0x180085da8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085dad  lea     rdx, aUserconsentreq; "UserConsentRequired"
0x180085db4  lea     rcx, [rbp+0A0h+var_100]
0x180085db8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085dbd  nop
0x180085dbe  lea     r8, [rbp+0A0h+var_100]
0x180085dc2  lea     rdx, [rbp+0A0h+var_E0]
0x180085dc6  lea     rcx, [rsp+1A0h+var_170]
0x180085dcb  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085dd0  mov     dword ptr [rsp+1A0h+var_160+8], eax
0x180085dd4  lea     rcx, [rbp+0A0h+var_100]
0x180085dd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085ddd  lea     rdx, aUserconsentpro; "UserConsentPromptRequired"
0x180085de4  lea     rcx, [rbp+0A0h+var_100]
0x180085de8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085ded  nop
0x180085dee  lea     r8, [rbp+0A0h+var_100]
0x180085df2  lea     rdx, [rbp+0A0h+var_E0]
0x180085df6  lea     rcx, [rsp+1A0h+var_170]
0x180085dfb  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085e00  mov     dword ptr [rsp+1A0h+var_160+0Ch], eax
0x180085e04  lea     rcx, [rbp+0A0h+var_100]
0x180085e08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085e0d  lea     rdx, aUserappconsent; "UserAppConsentRequired"
0x180085e14  lea     rcx, [rbp+0A0h+var_100]
0x180085e18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085e1d  nop
0x180085e1e  lea     r8, [rbp+0A0h+var_100]
0x180085e22  lea     rdx, [rbp+0A0h+var_E0]
0x180085e26  lea     rcx, [rsp+1A0h+var_170]
0x180085e2b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085e30  mov     dword ptr [rsp+1A0h+var_150], eax
0x180085e34  lea     rcx, [rbp+0A0h+var_100]
0x180085e38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085e3d  lea     rdx, aBlockaccess; "BlockAccess"
0x180085e44  lea     rcx, [rbp+0A0h+var_100]
0x180085e48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085e4d  nop
0x180085e4e  lea     r8, [rbp+0A0h+var_100]
0x180085e52  lea     rdx, [rbp+0A0h+var_E0]
0x180085e56  lea     rcx, [rsp+1A0h+var_170]
0x180085e5b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085e60  mov     dword ptr [rsp+1A0h+var_150+4], eax
0x180085e64  lea     rcx, [rbp+0A0h+var_100]
0x180085e68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085e6d  lea     rdx, aInituserappcon; "InitUserAppConsentDenied"
0x180085e74  lea     rcx, [rbp+0A0h+var_100]
0x180085e78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085e7d  nop
0x180085e7e  lea     r8, [rbp+0A0h+var_100]
0x180085e82  lea     rdx, [rbp+0A0h+var_E0]
0x180085e86  lea     rcx, [rsp+1A0h+var_170]
0x180085e8b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085e90  mov     dword ptr [rsp+1A0h+var_150+8], eax
0x180085e94  lea     rcx, [rbp+0A0h+var_100]
0x180085e98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085e9d  lea     rdx, aAlwaysblockacc; "AlwaysBlockAccess"
0x180085ea4  lea     rcx, [rbp+0A0h+var_100]
0x180085ea8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085ead  nop
0x180085eae  lea     r8, [rbp+0A0h+var_100]
0x180085eb2  lea     rdx, [rbp+0A0h+var_E0]
0x180085eb6  lea     rcx, [rsp+1A0h+var_170]
0x180085ebb  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085ec0  mov     dword ptr [rsp+1A0h+var_150+0Ch], eax
0x180085ec4  lea     rcx, [rbp+0A0h+var_100]
0x180085ec8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085ecd  lea     rdx, aGlobalprompts; "GlobalPrompts"
0x180085ed4  lea     rcx, [rbp+0A0h+var_100]
0x180085ed8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085edd  nop
0x180085ede  lea     r8, [rbp+0A0h+var_100]
0x180085ee2  lea     rdx, [rbp+0A0h+var_E0]
0x180085ee6  lea     rcx, [rsp+1A0h+var_170]
0x180085eeb  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085ef0  mov     dword ptr [rsp+1A0h+var_140], eax
0x180085ef4  lea     rcx, [rbp+0A0h+var_100]
0x180085ef8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085efd  lea     rdx, aRequirewindows; "RequireWindowsCert"
0x180085f04  lea     rcx, [rbp+0A0h+var_100]
0x180085f08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180085f0d  nop
0x180085f0e  lea     r8, [rbp+0A0h+var_100]
0x180085f12  lea     rdx, [rbp+0A0h+var_E0]
0x180085f16  lea     rcx, [rsp+1A0h+var_170]
0x180085f1b  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180085f20  mov     dword ptr [rsp+1A0h+var_140+4], eax
0x180085f24  lea     rcx, [rbp+0A0h+var_100]
0x180085f28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085f2d  lea     rcx, [rbp+0A0h+var_A0]
0x180085f31  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085f36  mov     rcx, [rbp+0A0h+var_90]
0x180085f3a  lea     r8, [rax+rcx*2]
0x180085f3e  mov     rcx, cs:__imp__o_towlower
0x180085f45  mov     [rsp+1A0h+phkResult], rcx
0x180085f4a  mov     r9, rax
0x180085f4d  mov     rdx, rax
0x180085f50  lea     rcx, [rbp+0A0h+var_118]
0x180085f54  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x180085f59  mov     rbx, [rsi]
0x180085f5c  lea     r8, [rsp+1A0h+var_168]
0x180085f61  lea     rdx, [rbp+0A0h+var_A0]
0x180085f65  lea     rcx, [rbp+0A0h+var_80]
0x180085f69  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(std::wstring &,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy &)
0x180085f6e  nop
0x180085f6f  lea     r8, [rbp+0A0h+var_80]
0x180085f73  lea     rdx, [rbp+0A0h+var_110]
0x180085f77  lea     rcx, [rbx+0A8h]
0x180085f7e  call    ??$emplace@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy> &&)
0x180085f83  nop
0x180085f84  mov     [rbp+0A0h+var_60], r13
0x180085f88  lea     rcx, [rbp+0A0h+var_80]
0x180085f8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085f91  nop
0x180085f92  lea     rcx, [rbp+0A0h+var_E0]
0x180085f96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085f9b  nop
0x180085f9c  lea     rcx, [rbp+0A0h+var_A0]
0x180085fa0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085fa5  add     r14, 20h ; ' '
0x180085fa9  cmp     r14, r15
0x180085fac  jnz     loc_180085CAF
0x180085fb2  lea     rcx, [rsp+1A0h+var_138]
0x180085fb7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180085fbc  nop
0x180085fbd  lea     rcx, [rsp+1A0h+var_170]
0x180085fc2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180085fc7  nop
0x180085fc8  lea     rcx, [rbp+0A0h+Src]
0x180085fcc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085fd1  nop
0x180085fd2  mov     rcx, [rsi+8]; this
0x180085fd6  test    rcx, rcx
0x180085fd9  jz      short loc_180085FE0
0x180085fdb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180085fe0  mov     rcx, [rbp+0A0h+var_30]
0x180085fe4  xor     rcx, rsp; StackCookie
0x180085fe7  call    __security_check_cookie
0x180085fec  lea     r11, [rsp+1A0h+var_20]
0x180085ff4  mov     rbx, [r11+38h]
0x180085ff8  mov     rsi, [r11+40h]
0x180085ffc  mov     rsp, r11
0x180085fff  pop     r15
0x180086001  pop     r14
0x180086003  pop     r13
0x180086005  pop     rdi
0x180086006  pop     rbp
0x180086007  retn
0x180086008  mov     r9d, eax; char *
0x18008600b  lea     r8, aOnecoreBaseDev_12; "onecore\\base\\devices\\cam\\policy\\re"...
  ... truncated ...
```
