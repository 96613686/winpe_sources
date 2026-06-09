# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPath_Safe(wchar_t * *,bool *)

- ea: `0x180076310`
- end: `0x18007641d`
- name: `?GetPath_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18005ab90`
- `0x180076310`
- `0x180076424`
- `0x1800cce54`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007634a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007634a`
- `OLEAUT32!__imp_SysReAllocString` at `0x180076375`
- `OLEAUT32!__imp_SysReAllocString` at `0x180076375`

## string_xrefs

- `0x1800763d0`: `UriCom`
- `0x18007640b`: `UriCom`
- `0x1800763b2`: `pbstrPath`
- `0x1800763c4`: `GetPath`
- `0x1800763ff`: `GetPath`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPath_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Path; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 467, L"UriCom", L"GetPath", L"pbstrPath", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 468, L"UriCom", L"GetPath", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  Path = win_dox::UriImplementation::GetPath(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(Path + 8);
  if ( *(_QWORD *)(Path + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180076310  push    rbx
0x180076312  push    rsi
0x180076313  push    rdi
0x180076314  sub     rsp, 80h
0x18007631b  mov     rax, cs:__security_cookie
0x180076322  xor     rax, rsp
0x180076325  mov     [rsp+98h+var_28], rax
0x18007632a  xor     eax, eax
0x18007632c  mov     rdi, r8
0x18007632f  mov     rbx, rdx
0x180076332  mov     rsi, rcx
0x180076335  test    rdx, rdx
0x180076338  jz      short loc_1800763A7
0x18007633a  test    r8, r8
0x18007633d  jz      loc_1800763E2
0x180076343  lea     rcx, psz; psz
0x18007634a  call    cs:__imp_SysAllocString
0x180076350  mov     [rbx], rax
0x180076353  mov     r8, rdi
0x180076356  mov     rcx, [rsi+10h]
0x18007635a  lea     rdx, [rsp+98h+var_50]
0x18007635f  call    ?GetPath@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPath(bool *)
0x180076364  cmp     qword ptr [rax+20h], 8
0x180076369  lea     rdx, [rax+8]
0x18007636d  jb      short loc_180076372
0x18007636f  mov     rdx, [rdx]; psz
0x180076372  mov     rcx, rbx; pbstr
0x180076375  call    cs:__imp_SysReAllocString
0x18007637b  cmp     [rsp+98h+var_30], 8
0x180076381  jnb     short loc_18007639B
0x180076383  mov     rcx, [rsp+98h+var_28]
0x180076388  xor     rcx, rsp; StackCookie
0x18007638b  call    __security_check_cookie
0x180076390  add     rsp, 80h
0x180076397  pop     rdi
0x180076398  pop     rsi
0x180076399  pop     rbx
0x18007639a  retn
0x18007639b  mov     rcx, [rsp+98h+Block]; Block
0x1800763a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800763a5  jmp     short loc_180076383
0x1800763a7  mov     [rsp+98h+var_60], eax
0x1800763ab  lea     rdx, aNoFilename; "(no filename)"
0x1800763b2  lea     rax, aPbstrpath; "pbstrPath"
0x1800763b9  mov     r9d, 1D3h
0x1800763bf  mov     [rsp+98h+var_68], rax
0x1800763c4  lea     rax, aGetpath; "GetPath"
0x1800763cb  mov     [rsp+98h+var_70], rax
0x1800763d0  lea     rax, aUricom; "UriCom"
0x1800763d7  mov     [rsp+98h+var_78], rax
0x1800763dc  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800763e2  mov     [rsp+98h+var_60], eax
0x1800763e6  lea     rdx, aNoFilename; "(no filename)"
0x1800763ed  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800763f4  mov     r9d, 1D4h
0x1800763fa  mov     [rsp+98h+var_68], rax
0x1800763ff  lea     rax, aGetpath; "GetPath"
0x180076406  mov     [rsp+98h+var_70], rax
0x18007640b  lea     rax, aUricom; "UriCom"
0x180076412  mov     [rsp+98h+var_78], rax
0x180076417  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```
