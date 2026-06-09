# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetRawUri_Safe(wchar_t * *,bool *)

- ea: `0x1800e16a0`
- end: `0x1800e179c`
- name: `?GetRawUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017dd0`
- `0x18005ab90`
- `0x18009507c`
- `0x1800e16a0`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e1747`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e1747`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1772`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1772`

## string_xrefs

- `0x1800e16ee`: `UriCom`
- `0x1800e172e`: `UriCom`
- `0x1800e16c9`: `pbstrRawUri`
- `0x1800e16dc`: `GetRawUri`
- `0x1800e171c`: `GetRawUri`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetRawUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 RawUri; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 557, L"UriCom", L"GetRawUri", L"pbstrRawUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 558, L"UriCom", L"GetRawUri", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  RawUri = win_dox::UriImplementation::GetRawUri(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(RawUri + 8);
  if ( *(_QWORD *)(RawUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e16a0  push    rbx
0x1800e16a2  push    rsi
0x1800e16a3  push    rdi
0x1800e16a4  sub     rsp, 70h
0x1800e16a8  mov     rax, cs:__security_cookie
0x1800e16af  xor     rax, rsp
0x1800e16b2  mov     [rsp+88h+var_20], rax
0x1800e16b7  mov     rdi, r8
0x1800e16ba  mov     rbx, rdx
0x1800e16bd  mov     rsi, rcx
0x1800e16c0  test    rdx, rdx
0x1800e16c3  jnz     short loc_1800E1700
0x1800e16c5  mov     [rsp+88h+var_50], edx
0x1800e16c9  lea     rax, aPbstrrawuri; "pbstrRawUri"
0x1800e16d0  mov     [rsp+88h+var_58], rax
0x1800e16d5  lea     rdx, aNoFilename; "(no filename)"
0x1800e16dc  lea     rax, aGetrawuri; "GetRawUri"
0x1800e16e3  mov     r9d, 22Dh
0x1800e16e9  mov     [rsp+88h+var_60], rax
0x1800e16ee  lea     rax, aUricom; "UriCom"
0x1800e16f5  mov     [rsp+88h+var_68], rax
0x1800e16fa  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e1700  test    rdi, rdi
0x1800e1703  jnz     short loc_1800E1740
0x1800e1705  mov     [rsp+88h+var_50], edi
0x1800e1709  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e1710  mov     [rsp+88h+var_58], rax
0x1800e1715  lea     rdx, aNoFilename; "(no filename)"
0x1800e171c  lea     rax, aGetrawuri; "GetRawUri"
0x1800e1723  mov     r9d, 22Eh
0x1800e1729  mov     [rsp+88h+var_60], rax
0x1800e172e  lea     rax, aUricom; "UriCom"
0x1800e1735  mov     [rsp+88h+var_68], rax
0x1800e173a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e1740  lea     rcx, psz; psz
0x1800e1747  call    cs:__imp_SysAllocString
0x1800e174d  mov     [rbx], rax
0x1800e1750  mov     r8, rdi
0x1800e1753  mov     rcx, [rsi+10h]
0x1800e1757  lea     rdx, [rsp+88h+var_48]
0x1800e175c  call    ?GetRawUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetRawUri(bool *)
0x1800e1761  cmp     qword ptr [rax+20h], 8
0x1800e1766  lea     rdx, [rax+8]
0x1800e176a  jb      short loc_1800E176F
0x1800e176c  mov     rdx, [rdx]; psz
0x1800e176f  mov     rcx, rbx; pbstr
0x1800e1772  call    cs:__imp_SysReAllocString
0x1800e1778  xor     r8d, r8d
0x1800e177b  lea     rcx, [rsp+88h+var_48]
0x1800e1780  mov     dl, 1
0x1800e1782  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e1787  mov     rcx, [rsp+88h+var_20]
0x1800e178c  xor     rcx, rsp; StackCookie
0x1800e178f  call    __security_check_cookie
0x1800e1794  add     rsp, 70h
0x1800e1798  pop     rdi
0x1800e1799  pop     rsi
0x1800e179a  pop     rbx
0x1800e179b  retn
```
