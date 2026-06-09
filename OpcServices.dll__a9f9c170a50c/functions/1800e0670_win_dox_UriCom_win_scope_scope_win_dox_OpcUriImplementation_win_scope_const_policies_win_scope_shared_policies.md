# win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(wchar_t * *,bool *)

- ea: `0x1800e0670`
- end: `0x1800e076c`
- name: `?GetAbsoluteUri_Safe@?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017dd0`
- `0x18005ab90`
- `0x180077974`
- `0x1800e0670`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e0717`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e0717`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0742`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0742`

## string_xrefs

- `0x1800e06be`: `UriCom`
- `0x1800e06fe`: `UriCom`
- `0x1800e0699`: `pbstrAbsoluteUri`
- `0x1800e06ac`: `GetAbsoluteUri`
- `0x1800e06ec`: `GetAbsoluteUri`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 AbsoluteUri; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 221, L"UriCom", L"GetAbsoluteUri", L"pbstrAbsoluteUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      222,
      L"UriCom",
      L"GetAbsoluteUri",
      L"propertyNotDefined",
      0);
  *a2 = SysAllocString(&psz);
  AbsoluteUri = win_dox::UriImplementation::GetAbsoluteUri(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(AbsoluteUri + 8);
  if ( *(_QWORD *)(AbsoluteUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e0670  push    rbx
0x1800e0672  push    rsi
0x1800e0673  push    rdi
0x1800e0674  sub     rsp, 70h
0x1800e0678  mov     rax, cs:__security_cookie
0x1800e067f  xor     rax, rsp
0x1800e0682  mov     [rsp+88h+var_20], rax
0x1800e0687  mov     rdi, r8
0x1800e068a  mov     rbx, rdx
0x1800e068d  mov     rsi, rcx
0x1800e0690  test    rdx, rdx
0x1800e0693  jnz     short loc_1800E06D0
0x1800e0695  mov     [rsp+88h+var_50], edx
0x1800e0699  lea     rax, aPbstrabsoluteu; "pbstrAbsoluteUri"
0x1800e06a0  mov     [rsp+88h+var_58], rax
0x1800e06a5  lea     rdx, aNoFilename; "(no filename)"
0x1800e06ac  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x1800e06b3  mov     r9d, 0DDh
0x1800e06b9  mov     [rsp+88h+var_60], rax
0x1800e06be  lea     rax, aUricom; "UriCom"
0x1800e06c5  mov     [rsp+88h+var_68], rax
0x1800e06ca  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e06d0  test    rdi, rdi
0x1800e06d3  jnz     short loc_1800E0710
0x1800e06d5  mov     [rsp+88h+var_50], edi
0x1800e06d9  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e06e0  mov     [rsp+88h+var_58], rax
0x1800e06e5  lea     rdx, aNoFilename; "(no filename)"
0x1800e06ec  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x1800e06f3  mov     r9d, 0DEh
0x1800e06f9  mov     [rsp+88h+var_60], rax
0x1800e06fe  lea     rax, aUricom; "UriCom"
0x1800e0705  mov     [rsp+88h+var_68], rax
0x1800e070a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0710  lea     rcx, psz; psz
0x1800e0717  call    cs:__imp_SysAllocString
0x1800e071d  mov     [rbx], rax
0x1800e0720  mov     r8, rdi
0x1800e0723  mov     rcx, [rsi+10h]
0x1800e0727  lea     rdx, [rsp+88h+var_48]
0x1800e072c  call    ?GetAbsoluteUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetAbsoluteUri(bool *)
0x1800e0731  cmp     qword ptr [rax+20h], 8
0x1800e0736  lea     rdx, [rax+8]
0x1800e073a  jb      short loc_1800E073F
0x1800e073c  mov     rdx, [rdx]; psz
0x1800e073f  mov     rcx, rbx; pbstr
0x1800e0742  call    cs:__imp_SysReAllocString
0x1800e0748  xor     r8d, r8d
0x1800e074b  lea     rcx, [rsp+88h+var_48]
0x1800e0750  mov     dl, 1
0x1800e0752  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e0757  mov     rcx, [rsp+88h+var_20]
0x1800e075c  xor     rcx, rsp; StackCookie
0x1800e075f  call    __security_check_cookie
0x1800e0764  add     rsp, 70h
0x1800e0768  pop     rdi
0x1800e0769  pop     rsi
0x1800e076a  pop     rbx
0x1800e076b  retn
```
