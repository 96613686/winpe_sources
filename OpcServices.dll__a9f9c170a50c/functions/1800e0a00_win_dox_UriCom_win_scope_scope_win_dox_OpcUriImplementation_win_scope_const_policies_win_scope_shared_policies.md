# win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetExtension_Safe(wchar_t * *,bool *)

- ea: `0x1800e0a00`
- end: `0x1800e0afc`
- name: `?GetExtension_Safe@?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180017dd0`
- `0x18005ab90`
- `0x18007c3f4`
- `0x1800e0a00`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e0aa7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e0aa7`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0ad2`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0ad2`

## string_xrefs

- `0x1800e0a4e`: `UriCom`
- `0x1800e0a8e`: `UriCom`
- `0x1800e0a29`: `pbstrExtension`
- `0x1800e0a3c`: `GetExtension`
- `0x1800e0a7c`: `GetExtension`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetExtension_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Extension; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 347, L"UriCom", L"GetExtension", L"pbstrExtension", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 348, L"UriCom", L"GetExtension", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  Extension = win_dox::UriImplementation::GetExtension(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(Extension + 8);
  if ( *(_QWORD *)(Extension + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e0a00  push    rbx
0x1800e0a02  push    rsi
0x1800e0a03  push    rdi
0x1800e0a04  sub     rsp, 70h
0x1800e0a08  mov     rax, cs:__security_cookie
0x1800e0a0f  xor     rax, rsp
0x1800e0a12  mov     [rsp+88h+var_20], rax
0x1800e0a17  mov     rdi, r8
0x1800e0a1a  mov     rbx, rdx
0x1800e0a1d  mov     rsi, rcx
0x1800e0a20  test    rdx, rdx
0x1800e0a23  jnz     short loc_1800E0A60
0x1800e0a25  mov     [rsp+88h+var_50], edx
0x1800e0a29  lea     rax, aPbstrextension; "pbstrExtension"
0x1800e0a30  mov     [rsp+88h+var_58], rax
0x1800e0a35  lea     rdx, aNoFilename; "(no filename)"
0x1800e0a3c  lea     rax, aGetextension; "GetExtension"
0x1800e0a43  mov     r9d, 15Bh
0x1800e0a49  mov     [rsp+88h+var_60], rax
0x1800e0a4e  lea     rax, aUricom; "UriCom"
0x1800e0a55  mov     [rsp+88h+var_68], rax
0x1800e0a5a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0a60  test    rdi, rdi
0x1800e0a63  jnz     short loc_1800E0AA0
0x1800e0a65  mov     [rsp+88h+var_50], edi
0x1800e0a69  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e0a70  mov     [rsp+88h+var_58], rax
0x1800e0a75  lea     rdx, aNoFilename; "(no filename)"
0x1800e0a7c  lea     rax, aGetextension; "GetExtension"
0x1800e0a83  mov     r9d, 15Ch
0x1800e0a89  mov     [rsp+88h+var_60], rax
0x1800e0a8e  lea     rax, aUricom; "UriCom"
0x1800e0a95  mov     [rsp+88h+var_68], rax
0x1800e0a9a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0aa0  lea     rcx, psz; psz
0x1800e0aa7  call    cs:__imp_SysAllocString
0x1800e0aad  mov     [rbx], rax
0x1800e0ab0  mov     r8, rdi
0x1800e0ab3  mov     rcx, [rsi+10h]
0x1800e0ab7  lea     rdx, [rsp+88h+var_48]
0x1800e0abc  call    ?GetExtension@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetExtension(bool *)
0x1800e0ac1  cmp     qword ptr [rax+20h], 8
0x1800e0ac6  lea     rdx, [rax+8]
0x1800e0aca  jb      short loc_1800E0ACF
0x1800e0acc  mov     rdx, [rdx]; psz
0x1800e0acf  mov     rcx, rbx; pbstr
0x1800e0ad2  call    cs:__imp_SysReAllocString
0x1800e0ad8  xor     r8d, r8d
0x1800e0adb  lea     rcx, [rsp+88h+var_48]
0x1800e0ae0  mov     dl, 1
0x1800e0ae2  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e0ae7  mov     rcx, [rsp+88h+var_20]
0x1800e0aec  xor     rcx, rsp; StackCookie
0x1800e0aef  call    __security_check_cookie
0x1800e0af4  add     rsp, 70h
0x1800e0af8  pop     rdi
0x1800e0af9  pop     rsi
0x1800e0afa  pop     rbx
0x1800e0afb  retn
```
