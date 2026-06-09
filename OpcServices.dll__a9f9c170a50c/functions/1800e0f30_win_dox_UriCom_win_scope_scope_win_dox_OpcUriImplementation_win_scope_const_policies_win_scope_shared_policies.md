# win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetPath_Safe(wchar_t * *,bool *)

- ea: `0x1800e0f30`
- end: `0x1800e102c`
- name: `?GetPath_Safe@?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017dd0`
- `0x18005ab90`
- `0x180076424`
- `0x1800e0f30`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e0fd7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e0fd7`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1002`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1002`

## string_xrefs

- `0x1800e0f7e`: `UriCom`
- `0x1800e0fbe`: `UriCom`
- `0x1800e0f59`: `pbstrPath`
- `0x1800e0f6c`: `GetPath`
- `0x1800e0fac`: `GetPath`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetPath_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Path; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 467, L"UriCom", L"GetPath", L"pbstrPath", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 468, L"UriCom", L"GetPath", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  Path = win_dox::UriImplementation::GetPath(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(Path + 8);
  if ( *(_QWORD *)(Path + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e0f30  push    rbx
0x1800e0f32  push    rsi
0x1800e0f33  push    rdi
0x1800e0f34  sub     rsp, 70h
0x1800e0f38  mov     rax, cs:__security_cookie
0x1800e0f3f  xor     rax, rsp
0x1800e0f42  mov     [rsp+88h+var_20], rax
0x1800e0f47  mov     rdi, r8
0x1800e0f4a  mov     rbx, rdx
0x1800e0f4d  mov     rsi, rcx
0x1800e0f50  test    rdx, rdx
0x1800e0f53  jnz     short loc_1800E0F90
0x1800e0f55  mov     [rsp+88h+var_50], edx
0x1800e0f59  lea     rax, aPbstrpath; "pbstrPath"
0x1800e0f60  mov     [rsp+88h+var_58], rax
0x1800e0f65  lea     rdx, aNoFilename; "(no filename)"
0x1800e0f6c  lea     rax, aGetpath; "GetPath"
0x1800e0f73  mov     r9d, 1D3h
0x1800e0f79  mov     [rsp+88h+var_60], rax
0x1800e0f7e  lea     rax, aUricom; "UriCom"
0x1800e0f85  mov     [rsp+88h+var_68], rax
0x1800e0f8a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0f90  test    rdi, rdi
0x1800e0f93  jnz     short loc_1800E0FD0
0x1800e0f95  mov     [rsp+88h+var_50], edi
0x1800e0f99  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e0fa0  mov     [rsp+88h+var_58], rax
0x1800e0fa5  lea     rdx, aNoFilename; "(no filename)"
0x1800e0fac  lea     rax, aGetpath; "GetPath"
0x1800e0fb3  mov     r9d, 1D4h
0x1800e0fb9  mov     [rsp+88h+var_60], rax
0x1800e0fbe  lea     rax, aUricom; "UriCom"
0x1800e0fc5  mov     [rsp+88h+var_68], rax
0x1800e0fca  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0fd0  lea     rcx, psz; psz
0x1800e0fd7  call    cs:__imp_SysAllocString
0x1800e0fdd  mov     [rbx], rax
0x1800e0fe0  mov     r8, rdi
0x1800e0fe3  mov     rcx, [rsi+10h]
0x1800e0fe7  lea     rdx, [rsp+88h+var_48]
0x1800e0fec  call    ?GetPath@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPath(bool *)
0x1800e0ff1  cmp     qword ptr [rax+20h], 8
0x1800e0ff6  lea     rdx, [rax+8]
0x1800e0ffa  jb      short loc_1800E0FFF
0x1800e0ffc  mov     rdx, [rdx]; psz
0x1800e0fff  mov     rcx, rbx; pbstr
0x1800e1002  call    cs:__imp_SysReAllocString
0x1800e1008  xor     r8d, r8d
0x1800e100b  lea     rcx, [rsp+88h+var_48]
0x1800e1010  mov     dl, 1
0x1800e1012  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e1017  mov     rcx, [rsp+88h+var_20]
0x1800e101c  xor     rcx, rsp; StackCookie
0x1800e101f  call    __security_check_cookie
0x1800e1024  add     rsp, 70h
0x1800e1028  pop     rdi
0x1800e1029  pop     rsi
0x1800e102a  pop     rbx
0x1800e102b  retn
```
