# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPathAndQuery_Safe(wchar_t * *,bool *)

- ea: `0x1800c7a60`
- end: `0x1800c7b5c`
- name: `?GetPathAndQuery_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017dd0`
- `0x18005ab90`
- `0x1800c7a60`
- `0x1800c7b64`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800c7b07`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c7b07`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800c7b32`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800c7b32`

## string_xrefs

- `0x1800c7aae`: `UriCom`
- `0x1800c7aee`: `UriCom`
- `0x1800c7a89`: `pbstrPathAndQuery`
- `0x1800c7a9c`: `GetPathAndQuery`
- `0x1800c7adc`: `GetPathAndQuery`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPathAndQuery_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 PathAndQuery; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      497,
      L"UriCom",
      L"GetPathAndQuery",
      L"pbstrPathAndQuery",
      0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      498,
      L"UriCom",
      L"GetPathAndQuery",
      L"propertyNotDefined",
      0);
  *a2 = SysAllocString(&psz);
  PathAndQuery = win_dox::UriImplementation::GetPathAndQuery(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(PathAndQuery + 8);
  if ( *(_QWORD *)(PathAndQuery + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800c7a60  push    rbx
0x1800c7a62  push    rsi
0x1800c7a63  push    rdi
0x1800c7a64  sub     rsp, 70h
0x1800c7a68  mov     rax, cs:__security_cookie
0x1800c7a6f  xor     rax, rsp
0x1800c7a72  mov     [rsp+88h+var_20], rax
0x1800c7a77  mov     rdi, r8
0x1800c7a7a  mov     rbx, rdx
0x1800c7a7d  mov     rsi, rcx
0x1800c7a80  test    rdx, rdx
0x1800c7a83  jnz     short loc_1800C7AC0
0x1800c7a85  mov     [rsp+88h+var_50], edx
0x1800c7a89  lea     rax, aPbstrpathandqu; "pbstrPathAndQuery"
0x1800c7a90  mov     [rsp+88h+var_58], rax
0x1800c7a95  lea     rdx, aNoFilename; "(no filename)"
0x1800c7a9c  lea     rax, aGetpathandquer; "GetPathAndQuery"
0x1800c7aa3  mov     r9d, 1F1h
0x1800c7aa9  mov     [rsp+88h+var_60], rax
0x1800c7aae  lea     rax, aUricom; "UriCom"
0x1800c7ab5  mov     [rsp+88h+var_68], rax
0x1800c7aba  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800c7ac0  test    rdi, rdi
0x1800c7ac3  jnz     short loc_1800C7B00
0x1800c7ac5  mov     [rsp+88h+var_50], edi
0x1800c7ac9  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800c7ad0  mov     [rsp+88h+var_58], rax
0x1800c7ad5  lea     rdx, aNoFilename; "(no filename)"
0x1800c7adc  lea     rax, aGetpathandquer; "GetPathAndQuery"
0x1800c7ae3  mov     r9d, 1F2h
0x1800c7ae9  mov     [rsp+88h+var_60], rax
0x1800c7aee  lea     rax, aUricom; "UriCom"
0x1800c7af5  mov     [rsp+88h+var_68], rax
0x1800c7afa  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800c7b00  lea     rcx, psz; psz
0x1800c7b07  call    cs:__imp_SysAllocString
0x1800c7b0d  mov     [rbx], rax
0x1800c7b10  mov     r8, rdi
0x1800c7b13  mov     rcx, [rsi+10h]
0x1800c7b17  lea     rdx, [rsp+88h+var_48]
0x1800c7b1c  call    ?GetPathAndQuery@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPathAndQuery(bool *)
0x1800c7b21  cmp     qword ptr [rax+20h], 8
0x1800c7b26  lea     rdx, [rax+8]
0x1800c7b2a  jb      short loc_1800C7B2F
0x1800c7b2c  mov     rdx, [rdx]; psz
0x1800c7b2f  mov     rcx, rbx; pbstr
0x1800c7b32  call    cs:__imp_SysReAllocString
0x1800c7b38  xor     r8d, r8d
0x1800c7b3b  lea     rcx, [rsp+88h+var_48]
0x1800c7b40  mov     dl, 1
0x1800c7b42  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c7b47  mov     rcx, [rsp+88h+var_20]
0x1800c7b4c  xor     rcx, rsp; StackCookie
0x1800c7b4f  call    __security_check_cookie
0x1800c7b54  add     rsp, 70h
0x1800c7b58  pop     rdi
0x1800c7b59  pop     rsi
0x1800c7b5a  pop     rbx
0x1800c7b5b  retn
```
