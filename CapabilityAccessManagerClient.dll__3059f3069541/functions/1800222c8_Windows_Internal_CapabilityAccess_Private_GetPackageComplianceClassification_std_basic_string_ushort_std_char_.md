# Windows::Internal::CapabilityAccess::Private::GetPackageComplianceClassification(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800222c8`
- end: `0x180022458`
- name: `?GetPackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@YA?AW4PackageComplianceClassification@1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `400`
- prototype: `__int64 __fastcall(Windows::Internal::CapabilityAccess::Private *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002b8c0`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x18001b444`
- `0x180020fb0`
- `0x1800222c8`
- `0x180023074`
- `0x180023224`
- `0x180023c34`
- `0x18002e5e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180022327`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800223ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180022327`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800223ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageComplianceClassification(
        Windows::Internal::CapabilityAccess::Private *a1,
        __int64 a2)
{
  unsigned __int64 *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const struct ShellLists::SystemCategorizationOverrideEntry near *const *v9; // rbx
  __int64 v10; // rax
  const struct ShellLists::SystemCategorizationOverrideEntry near *const *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  _BYTE v28[16]; // [rsp+30h] [rbp-50h] BYREF
  int v29[4]; // [rsp+40h] [rbp-40h]
  _BYTE v30[16]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+60h] [rbp-20h]

  v4 = (unsigned __int64 *)((char *)a1 + 16);
  if ( Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(a1) )
  {
    LOBYTE(v5) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57933778>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_57933778>::GetImpl'::`2'::impl,
      v5);
    v9 = (const struct ShellLists::SystemCategorizationOverrideEntry near *const *)&off_180048CC0;
    while ( 1 )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v6, v7, v8);
      if ( !(unsigned int)_o__wcsnicmp(v10, *v9, *v4) )
        return 3 - (unsigned int)(*((_BYTE *)v9 + 8) != 0);
      v9 += 2;
      if ( v9 == &ShellLists::s_packagedAppSystemCategorizationOverrides )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    v11 = &ShellLists::s_packagedAppSystemCategorizationOverrides;
    while ( 1 )
    {
      std::wstring::wstring((__int64)v28, (__int64)*v11);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28, v12, v13, v14);
      v18 = std::_Traits_find_first_of<std::char_traits<unsigned short>>(v15, v29[0], v16, v17, 1u);
      std::wstring::substr(v28, v30, 0, v18);
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v19, v31, v20);
      if ( v22 <= *v4 )
        v22 = *v4;
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v21, v22, v23);
      if ( !(unsigned int)_o__wcsnicmp(v24, v25, v26) )
        break;
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v28);
      v11 += 2;
      if ( v11 == (const struct ShellLists::SystemCategorizationOverrideEntry near *const *)&c_szCapabilityLocation )
      {
        if ( *(_QWORD *)(a2 + 16) )
          return Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetPackageFamilyPackageComplianceClassification(
                   a1,
                   a2);
        else
          return 1;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v28);
      return 2;
    }
    else
    {
      std::wstring::_Tidy_deallocate(v30);
      std::wstring::_Tidy_deallocate(v28);
      return 3;
    }
  }
}

```

## disassembly

```asm
0x1800222c8  mov     [rsp-18h+arg_10], rbx
0x1800222cd  mov     [rsp-18h+arg_18], rsi
0x1800222d2  push    rbp
0x1800222d3  push    rdi
0x1800222d4  push    r14
0x1800222d6  mov     rbp, rsp
0x1800222d9  sub     rsp, 80h
0x1800222e0  mov     rax, cs:__security_cookie
0x1800222e7  xor     rax, rsp
0x1800222ea  mov     [rbp+var_10], rax
0x1800222ee  mov     r14, rdx
0x1800222f1  mov     rsi, rcx
0x1800222f4  lea     rdi, [rcx+10h]
0x1800222f8  call    ?IsCTARegionActive@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsCTARegionActive(void)
0x1800222fd  test    al, al
0x1800222ff  jz      short loc_180022345
0x180022301  mov     dl, 1
0x180022303  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57933778@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57933778@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57933778> `wil::Feature<__WilFeatureTraits_Feature_57933778>::GetImpl(void)'::`2'::impl
0x18002230a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_57933778@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57933778>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002230f  lea     rbx, off_180048CC0; "MicrosoftWindows.Client.AIX_cw5n1h2txye"...
0x180022316  mov     rcx, rsi
0x180022319  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002231e  mov     r8, [rdi]
0x180022321  mov     rdx, [rbx]
0x180022324  mov     rcx, rax
0x180022327  call    cs:__imp__o__wcsnicmp
0x18002232d  test    eax, eax
0x18002232f  jz      loc_1800223EB
0x180022335  add     rbx, 10h
0x180022339  lea     rax, ?s_packagedAppSystemCategorizationOverrides@ShellLists@@3QBUSystemCategorizationOverrideEntry@1@B; ShellLists::SystemCategorizationOverrideEntry const near * const ShellLists::s_packagedAppSystemCategorizationOverrides
0x180022340  cmp     rbx, rax
0x180022343  jnz     short loc_180022316
0x180022345  lea     rbx, ?s_packagedAppSystemCategorizationOverrides@ShellLists@@3QBUSystemCategorizationOverrideEntry@1@B; ShellLists::SystemCategorizationOverrideEntry const near * const ShellLists::s_packagedAppSystemCategorizationOverrides
0x18002234c  mov     rdx, [rbx]
0x18002234f  lea     rcx, [rbp+var_50]
0x180022353  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022358  nop
0x180022359  lea     rcx, [rbp+var_50]
0x18002235d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022362  mov     rcx, rax; int
0x180022365  mov     [rsp+80h+N], 1; N
0x18002236e  mov     rdx, qword ptr [rbp+var_40]; int
0x180022372  call    ??$_Traits_find_first_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180022377  mov     r9, rax
0x18002237a  xor     r8d, r8d
0x18002237d  lea     rdx, [rbp+var_30]
0x180022381  lea     rcx, [rbp+var_50]
0x180022385  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18002238a  mov     r8, [rbp+var_20]
0x18002238e  mov     rcx, rsi
0x180022391  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022396  mov     rdx, rax
0x180022399  cmp     r8, [rdi]
0x18002239c  cmovbe  r8, [rdi]
0x1800223a0  lea     rcx, [rbp+var_30]
0x1800223a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800223a9  mov     rcx, rax
0x1800223ac  call    cs:__imp__o__wcsnicmp
0x1800223b2  lea     rcx, [rbp+var_30]
0x1800223b6  test    eax, eax
0x1800223b8  jz      short loc_180022404
0x1800223ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800223bf  nop
0x1800223c0  lea     rcx, [rbp+var_50]
0x1800223c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800223c9  add     rbx, 10h
0x1800223cd  lea     rcx, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x1800223d4  cmp     rbx, rcx
0x1800223d7  jnz     loc_18002234C
0x1800223dd  cmp     qword ptr [r14+10h], 0
0x1800223e2  jnz     short loc_1800223F7
0x1800223e4  mov     eax, 1
0x1800223e9  jmp     short loc_180022434
0x1800223eb  mov     al, [rbx+8]
0x1800223ee  neg     al
0x1800223f0  sbb     eax, eax
0x1800223f2  add     eax, 3
0x1800223f5  jmp     short loc_180022434
0x1800223f7  mov     rdx, r14
0x1800223fa  mov     rcx, rsi
0x1800223fd  call    ?GetPackageFamilyPackageComplianceClassification@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@SA?AW4PackageComplianceClassification@3456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetPackageFamilyPackageComplianceClassification(std::wstring const &,std::wstring const &)
0x180022402  jmp     short loc_180022434
0x180022404  cmp     byte ptr [rbx+8], 0
0x180022408  jz      short loc_180022420
0x18002240a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002240f  nop
0x180022410  lea     rcx, [rbp+var_50]
0x180022414  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022419  mov     eax, 2
0x18002241e  jmp     short loc_180022434
0x180022420  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022425  nop
0x180022426  lea     rcx, [rbp+var_50]
0x18002242a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002242f  mov     eax, 3
0x180022434  mov     rcx, [rbp+var_10]
0x180022438  xor     rcx, rsp; StackCookie
0x18002243b  call    __security_check_cookie
0x180022440  lea     r11, [rsp+80h+var_s0]
0x180022448  mov     rbx, [r11+30h]
0x18002244c  mov     rsi, [r11+38h]
0x180022450  mov     rsp, r11
0x180022453  pop     r14
0x180022455  pop     rdi
0x180022456  pop     rbp
0x180022457  retn
```
