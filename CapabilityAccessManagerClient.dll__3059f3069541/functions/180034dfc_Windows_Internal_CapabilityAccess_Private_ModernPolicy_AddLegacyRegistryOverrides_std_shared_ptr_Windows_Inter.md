# Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>)

- ea: `0x180034dfc`
- end: `0x180035301`
- name: `?AddLegacyRegistryOverrides@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YAXV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@Z`
- size: `1285`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003484c`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x18001b444`
- `0x18001c330`
- `0x1800207a4`
- `0x180021204`
- `0x180021300`
- `0x180021550`
- `0x1800236ac`
- `0x18002392c`
- `0x180023b38`
- `0x180025080`
- `0x1800286e0`
- `0x180028ce8`
- `0x18002a1a8`
- `0x18002cb24`
- `0x18002f06c`
- `0x18002f4c8`
- `0x180034dfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180035222`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034f44`

## string_xrefs

- `0x180034e68`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180035181`: `AlwaysBlockAccess`
- `0x180035121`: `BlockAccess`
- `0x180035061`: `TerminateAppOnAccessChange`
- `0x180035031`: `AppLaunchAccessCheckRequired`
- `0x180034e57`: `onecore\base\devices\cam\policy\registryoverrides.cpp`
- `0x1800352ef`: `onecore\base\devices\cam\policy\registryoverrides.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::AddLegacyRegistryOverrides(_QWORD *a1)
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
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // r14
  __int64 i; // r15
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  int v35; // eax
  __int64 v36; // rbx
  std::_Ref_count_base *v37; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY v39; // [rsp+30h] [rbp-D0h] BYREF
  void **v40; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v41; // [rsp+40h] [rbp-C0h]
  __int128 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h]
  _QWORD *v46; // [rsp+80h] [rbp-80h]
  char v47; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v48[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v49[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v50[16]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v51; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-28h]
  _BYTE Src[16]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v54; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v55; // [rsp+F8h] [rbp-8h]
  _BYTE v56[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v57; // [rsp+110h] [rbp+10h]
  _DWORD v58[8]; // [rsp+120h] [rbp+20h] BYREF
  void **v59; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v46 = a1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x32,
    (unsigned int)"onecore\\base\\devices\\cam\\policy\\registryoverrides.cpp",
    (const char *)0x80070057LL,
    *(_QWORD *)(*a1 + 24LL) == 0,
    (bool)"Policy has not provided a capability definition to parse Edition policy",
    (const char *)v39);
  std::wstring::wstring((__int64)Src, (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager");
  v4 = v54;
  if ( v54 >= v55 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v54;
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v4, v2, v3);
    *(_DWORD *)(v5 + 2 * v6) = 92;
  }
  std::wstring::_Append<unsigned short>(Src, L"Capabilities", 12);
  v9 = v54;
  if ( v54 >= v55 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
  }
  else
  {
    ++v54;
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v9, v7, v8);
    *(_DWORD *)(v10 + 2 * v11) = 92;
  }
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(*a1 + 8LL, v11, *a1, v12);
  std::wstring::_Append<unsigned short>(Src, v13, *(_QWORD *)(v14 + 24));
  v39 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v39,
    0);
  v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src, v15, v16, v17);
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0x20119u, &v39);
  if ( v19 != 2 )
  {
    if ( v19 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\devices\\cam\\policy\\registryoverrides.cpp",
        (const char *)v19,
        phkResult);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v44, v39, L"Apps");
    v20 = v44;
    for ( i = v45; v20 != i; v20 += 32 )
    {
      if ( !std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(
              *a1 + 168LL,
              v20) )
      {
        std::wstring::wstring((__int64)v56, v20, v22, v23);
        std::wstring::wstring((__int64)v50, (__int64)L"Apps");
        v26 = v51;
        if ( v51 >= v52 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v50);
        }
        else
        {
          ++v51;
          v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50, v26, v24, v25);
          *(_DWORD *)(v27 + 2 * v28) = 92;
        }
        v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56, v28, v29, v30);
        std::wstring::_Append<unsigned short>(v50, v31, v57);
        v40 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v41 = 0;
        v42 = 0;
        v43 = 0;
        std::wstring::wstring((__int64)v49, (__int64)L"AppLaunchAccessCheckRequired");
        LODWORD(v41) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"TerminateAppOnAccessChange");
        DWORD1(v41) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"UserConsentRequired");
        DWORD2(v41) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"UserConsentPromptRequired");
        HIDWORD(v41) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"UserAppConsentRequired");
        LODWORD(v42) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"BlockAccess");
        DWORD1(v42) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"InitUserAppConsentDenied");
        DWORD2(v42) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"AlwaysBlockAccess");
        HIDWORD(v42) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"GlobalPrompts");
        LODWORD(v43) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::wstring((__int64)v49, (__int64)L"RequireWindowsCert");
        HIDWORD(v43) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v39, v50, v49);
        std::wstring::_Tidy_deallocate(v49);
        v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56, v32, v33, v34);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v47,
          v35,
          v35 + 2 * v57,
          v35,
          _o_towlower);
        v36 = *a1;
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          (__int64)v58,
          (__int64)v56,
          &v40);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          (_QWORD *)(v36 + 168),
          (__int64)v48,
          v58);
        v59 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(v50);
        std::wstring::_Tidy_deallocate(v56);
      }
    }
    std::vector<std::wstring>::_Tidy(&v44);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v39);
  std::wstring::_Tidy_deallocate(Src);
  v37 = (std::_Ref_count_base *)a1[1];
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
}

```

## disassembly

```asm
0x180034dfc  mov     [rsp-8+arg_8], rbx
0x180034e01  mov     [rsp-8+arg_10], rsi
0x180034e06  push    rbp
0x180034e07  push    rdi
0x180034e08  push    r13
0x180034e0a  push    r14
0x180034e0c  push    r15
0x180034e0e  lea     rbp, [rsp-80h]
0x180034e13  sub     rsp, 180h
0x180034e1a  mov     rax, cs:__security_cookie
0x180034e21  xor     rax, rsp
0x180034e24  mov     [rbp+0A0h+var_30], rax
0x180034e28  mov     rsi, rcx
0x180034e2b  mov     [rbp+0A0h+var_120], rcx
0x180034e2f  mov     rax, [rcx]
0x180034e32  cmp     qword ptr [rax+18h], 0
0x180034e37  setz    al
0x180034e3a  mov     rcx, [rbp+0A8h]; this
0x180034e41  lea     rdx, aPolicyHasNotPr; "Policy has not provided a capability de"...
0x180034e48  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x180034e4d  mov     byte ptr [rsp+1A0h+phkResult], al; char
0x180034e51  mov     r9d, 80070057h; char *
0x180034e57  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\policy\\re"...
0x180034e5e  mov     edx, 32h ; '2'; void *
0x180034e63  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180034e68  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034e6f  lea     rcx, [rbp+0A0h+Src]
0x180034e73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034e78  nop
0x180034e79  mov     rdx, [rbp+0A0h+var_B0]
0x180034e7d  lea     rcx, [rbp+0A0h+Src]; Src
0x180034e81  cmp     rdx, [rbp+0A0h+var_A8]
0x180034e85  jnb     short loc_180034E9E
0x180034e87  lea     rax, [rdx+1]
0x180034e8b  mov     [rbp+0A0h+var_B0], rax
0x180034e8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034e94  mov     edi, 5Ch ; '\'
0x180034e99  mov     [rax+rdx*2], edi
0x180034e9c  jmp     short loc_180034EAB
0x180034e9e  mov     edi, 5Ch ; '\'
0x180034ea3  mov     r9d, edi
0x180034ea6  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180034eab  mov     r8d, 0Ch
0x180034eb1  lea     rdx, aCapabilities; "Capabilities"
0x180034eb8  lea     rcx, [rbp+0A0h+Src]
0x180034ebc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180034ec1  mov     rdx, [rbp+0A0h+var_B0]
0x180034ec5  lea     rcx, [rbp+0A0h+Src]; Src
0x180034ec9  cmp     rdx, [rbp+0A0h+var_A8]
0x180034ecd  jnb     short loc_180034EE5
0x180034ecf  lea     rax, [rdx+1]
0x180034ed3  mov     [rbp+0A0h+var_B0], rax
0x180034ed7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034edc  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180034ee3  jmp     short loc_180034EED
0x180034ee5  mov     r9d, edi
0x180034ee8  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180034eed  mov     r8, [rsi]
0x180034ef0  lea     rcx, [r8+8]
0x180034ef4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034ef9  mov     r8, [r8+18h]
0x180034efd  mov     rdx, rax
0x180034f00  lea     rcx, [rbp+0A0h+Src]
0x180034f04  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180034f09  mov     [rsp+1A0h+var_170], 0
0x180034f12  xor     edx, edx
0x180034f14  lea     rcx, [rsp+1A0h+var_170]
0x180034f19  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180034f1e  lea     rcx, [rbp+0A0h+Src]
0x180034f22  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034f27  mov     rdx, rax; lpSubKey
0x180034f2a  lea     rax, [rsp+1A0h+var_170]
0x180034f2f  mov     [rsp+1A0h+phkResult], rax; unsigned int
0x180034f34  mov     r9d, 20119h; samDesired
0x180034f3a  xor     r8d, r8d; ulOptions
0x180034f3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034f44  call    cs:__imp_RegOpenKeyExW
0x180034f4a  cmp     eax, 2
0x180034f4d  jz      loc_1800352A1
0x180034f53  mov     rcx, [rbp+0A8h]; this
0x180034f5a  test    eax, eax
0x180034f5c  jnz     loc_1800352EC
0x180034f62  lea     r8, aApps; "Apps"
0x180034f69  mov     rdx, [rsp+1A0h+var_170]
0x180034f6e  lea     rcx, [rsp+1A0h+var_138]
0x180034f73  call    ?RegGetKeyArray@Private@CapabilityAccess@Internal@Windows@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@PEBG@Z; Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(HKEY__ *,ushort const *)
0x180034f78  nop
0x180034f79  mov     r14, [rsp+1A0h+var_138]
0x180034f7e  mov     r15, [rsp+1A0h+var_130]
0x180034f83  cmp     r14, r15
0x180034f86  jz      loc_180035296
0x180034f8c  lea     r13, ??_7CapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@6B@; const Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable'
0x180034f93  mov     rcx, [rsi]
0x180034f96  add     rcx, 0A8h
0x180034f9d  mov     rdx, r14
0x180034fa0  call    ?count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(std::wstring const &)
0x180034fa5  test    rax, rax
0x180034fa8  jnz     loc_180035289
0x180034fae  mov     rdx, r14
0x180034fb1  lea     rcx, [rbp+0A0h+var_A0]
0x180034fb5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034fba  nop
0x180034fbb  lea     rdx, aApps; "Apps"
0x180034fc2  lea     rcx, [rbp+0A0h+var_E0]
0x180034fc6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180034fcb  nop
0x180034fcc  mov     rdx, [rbp+0A0h+var_D0]
0x180034fd0  lea     rcx, [rbp+0A0h+var_E0]; Src
0x180034fd4  cmp     rdx, [rbp+0A0h+var_C8]
0x180034fd8  jnb     short loc_180034FF0
0x180034fda  lea     rax, [rdx+1]
0x180034fde  mov     [rbp+0A0h+var_D0], rax
0x180034fe2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034fe7  mov     dword ptr [rax+rdx*2], 5Ch ; '\'
0x180034fee  jmp     short loc_180034FF8
0x180034ff0  mov     r9d, edi
0x180034ff3  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180034ff8  lea     rcx, [rbp+0A0h+var_A0]
0x180034ffc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035001  mov     rdx, rax
0x180035004  mov     r8, [rbp+0A0h+var_90]
0x180035008  lea     rcx, [rbp+0A0h+var_E0]
0x18003500c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180035011  mov     [rsp+1A0h+var_168], r13
0x180035016  xorps   xmm0, xmm0
0x180035019  movdqu  [rsp+1A0h+var_160], xmm0
0x18003501f  xorps   xmm1, xmm1
0x180035022  movdqu  [rsp+1A0h+var_150], xmm1
0x180035028  mov     [rsp+1A0h+var_140], 0
0x180035031  lea     rdx, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x180035038  lea     rcx, [rbp+0A0h+var_100]
0x18003503c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035041  nop
0x180035042  lea     r8, [rbp+0A0h+var_100]
0x180035046  lea     rdx, [rbp+0A0h+var_E0]
0x18003504a  lea     rcx, [rsp+1A0h+var_170]
0x18003504f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035054  mov     dword ptr [rsp+1A0h+var_160], eax
0x180035058  lea     rcx, [rbp+0A0h+var_100]
0x18003505c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035061  lea     rdx, aTerminateappon; "TerminateAppOnAccessChange"
0x180035068  lea     rcx, [rbp+0A0h+var_100]
0x18003506c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035071  nop
0x180035072  lea     r8, [rbp+0A0h+var_100]
0x180035076  lea     rdx, [rbp+0A0h+var_E0]
0x18003507a  lea     rcx, [rsp+1A0h+var_170]
0x18003507f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035084  mov     dword ptr [rsp+1A0h+var_160+4], eax
0x180035088  lea     rcx, [rbp+0A0h+var_100]
0x18003508c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035091  lea     rdx, aUserconsentreq; "UserConsentRequired"
0x180035098  lea     rcx, [rbp+0A0h+var_100]
0x18003509c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800350a1  nop
0x1800350a2  lea     r8, [rbp+0A0h+var_100]
0x1800350a6  lea     rdx, [rbp+0A0h+var_E0]
0x1800350aa  lea     rcx, [rsp+1A0h+var_170]
0x1800350af  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x1800350b4  mov     dword ptr [rsp+1A0h+var_160+8], eax
0x1800350b8  lea     rcx, [rbp+0A0h+var_100]
0x1800350bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800350c1  lea     rdx, aUserconsentpro; "UserConsentPromptRequired"
0x1800350c8  lea     rcx, [rbp+0A0h+var_100]
0x1800350cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800350d1  nop
0x1800350d2  lea     r8, [rbp+0A0h+var_100]
0x1800350d6  lea     rdx, [rbp+0A0h+var_E0]
0x1800350da  lea     rcx, [rsp+1A0h+var_170]
0x1800350df  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x1800350e4  mov     dword ptr [rsp+1A0h+var_160+0Ch], eax
0x1800350e8  lea     rcx, [rbp+0A0h+var_100]
0x1800350ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800350f1  lea     rdx, aUserappconsent; "UserAppConsentRequired"
0x1800350f8  lea     rcx, [rbp+0A0h+var_100]
0x1800350fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035101  nop
0x180035102  lea     r8, [rbp+0A0h+var_100]
0x180035106  lea     rdx, [rbp+0A0h+var_E0]
0x18003510a  lea     rcx, [rsp+1A0h+var_170]
0x18003510f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035114  mov     dword ptr [rsp+1A0h+var_150], eax
0x180035118  lea     rcx, [rbp+0A0h+var_100]
0x18003511c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035121  lea     rdx, aBlockaccess; "BlockAccess"
0x180035128  lea     rcx, [rbp+0A0h+var_100]
0x18003512c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035131  nop
0x180035132  lea     r8, [rbp+0A0h+var_100]
0x180035136  lea     rdx, [rbp+0A0h+var_E0]
0x18003513a  lea     rcx, [rsp+1A0h+var_170]
0x18003513f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035144  mov     dword ptr [rsp+1A0h+var_150+4], eax
0x180035148  lea     rcx, [rbp+0A0h+var_100]
0x18003514c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035151  lea     rdx, aInituserappcon; "InitUserAppConsentDenied"
0x180035158  lea     rcx, [rbp+0A0h+var_100]
0x18003515c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035161  nop
0x180035162  lea     r8, [rbp+0A0h+var_100]
0x180035166  lea     rdx, [rbp+0A0h+var_E0]
0x18003516a  lea     rcx, [rsp+1A0h+var_170]
0x18003516f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035174  mov     dword ptr [rsp+1A0h+var_150+8], eax
0x180035178  lea     rcx, [rbp+0A0h+var_100]
0x18003517c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035181  lea     rdx, aAlwaysblockacc; "AlwaysBlockAccess"
0x180035188  lea     rcx, [rbp+0A0h+var_100]
0x18003518c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180035191  nop
0x180035192  lea     r8, [rbp+0A0h+var_100]
0x180035196  lea     rdx, [rbp+0A0h+var_E0]
0x18003519a  lea     rcx, [rsp+1A0h+var_170]
0x18003519f  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x1800351a4  mov     dword ptr [rsp+1A0h+var_150+0Ch], eax
0x1800351a8  lea     rcx, [rbp+0A0h+var_100]
0x1800351ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800351b1  lea     rdx, aGlobalprompts; "GlobalPrompts"
0x1800351b8  lea     rcx, [rbp+0A0h+var_100]
0x1800351bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800351c1  nop
0x1800351c2  lea     r8, [rbp+0A0h+var_100]
0x1800351c6  lea     rdx, [rbp+0A0h+var_E0]
0x1800351ca  lea     rcx, [rsp+1A0h+var_170]
0x1800351cf  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x1800351d4  mov     dword ptr [rsp+1A0h+var_140], eax
0x1800351d8  lea     rcx, [rbp+0A0h+var_100]
0x1800351dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800351e1  lea     rdx, aRequirewindows; "RequireWindowsCert"
0x1800351e8  lea     rcx, [rbp+0A0h+var_100]
0x1800351ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800351f1  nop
0x1800351f2  lea     r8, [rbp+0A0h+var_100]
0x1800351f6  lea     rdx, [rbp+0A0h+var_E0]
0x1800351fa  lea     rcx, [rsp+1A0h+var_170]
0x1800351ff  call    ?ReadAppPolicyValue@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppPolicyBoolValue@2345@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,std::wstring const &)
0x180035204  mov     dword ptr [rsp+1A0h+var_140+4], eax
0x180035208  lea     rcx, [rbp+0A0h+var_100]
0x18003520c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035211  lea     rcx, [rbp+0A0h+var_A0]
0x180035215  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003521a  mov     rcx, [rbp+0A0h+var_90]
0x18003521e  lea     r8, [rax+rcx*2]
0x180035222  mov     rcx, cs:__imp__o_towlower
0x180035229  mov     [rsp+1A0h+phkResult], rcx
0x18003522e  mov     r9, rax
0x180035231  mov     rdx, rax
0x180035234  lea     rcx, [rbp+0A0h+var_118]
0x180035238  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18003523d  mov     rbx, [rsi]
0x180035240  lea     r8, [rsp+1A0h+var_168]
0x180035245  lea     rdx, [rbp+0A0h+var_A0]
0x180035249  lea     rcx, [rbp+0A0h+var_80]
0x18003524d  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAVCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@Z; std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(std::wstring &,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy &)
0x180035252  nop
0x180035253  lea     r8, [rbp+0A0h+var_80]
0x180035257  lea     rdx, [rbp+0A0h+var_110]
0x18003525b  lea     rcx, [rbx+0A8h]
0x180035262  call    ??$emplace@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCapabilityAppPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy> &&)
0x180035267  nop
0x180035268  mov     [rbp+0A0h+var_60], r13
0x18003526c  lea     rcx, [rbp+0A0h+var_80]
0x180035270  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035275  nop
0x180035276  lea     rcx, [rbp+0A0h+var_E0]
0x18003527a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003527f  nop
0x180035280  lea     rcx, [rbp+0A0h+var_A0]
0x180035284  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035289  add     r14, 20h ; ' '
0x18003528d  cmp     r14, r15
0x180035290  jnz     loc_180034F93
0x180035296  lea     rcx, [rsp+1A0h+var_138]
0x18003529b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800352a0  nop
0x1800352a1  lea     rcx, [rsp+1A0h+var_170]
0x1800352a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800352ab  nop
0x1800352ac  lea     rcx, [rbp+0A0h+Src]
0x1800352b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800352b5  nop
0x1800352b6  mov     rcx, [rsi+8]; this
0x1800352ba  test    rcx, rcx
0x1800352bd  jz      short loc_1800352C4
0x1800352bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800352c4  mov     rcx, [rbp+0A0h+var_30]
0x1800352c8  xor     rcx, rsp; StackCookie
0x1800352cb  call    __security_check_cookie
0x1800352d0  lea     r11, [rsp+1A0h+var_20]
0x1800352d8  mov     rbx, [r11+38h]
0x1800352dc  mov     rsi, [r11+40h]
0x1800352e0  mov     rsp, r11
0x1800352e3  pop     r15
0x1800352e5  pop     r14
0x1800352e7  pop     r13
0x1800352e9  pop     rdi
0x1800352ea  pop     rbp
0x1800352eb  retn
0x1800352ec  mov     r9d, eax; char *
0x1800352ef  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\policy\\re"...
  ... truncated ...
```
