# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetExtension_Safe(wchar_t * *,bool *)

- ea: `0x18007c2e0`
- end: `0x18007c3ed`
- name: `?GetExtension_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18005ab90`
- `0x18007c2e0`
- `0x18007c3f4`
- `0x1800cce54`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007c31a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c31a`
- `OLEAUT32!__imp_SysReAllocString` at `0x18007c345`
- `OLEAUT32!__imp_SysReAllocString` at `0x18007c345`

## string_xrefs

- `0x18007c3a0`: `UriCom`
- `0x18007c3db`: `UriCom`
- `0x18007c382`: `pbstrExtension`
- `0x18007c394`: `GetExtension`
- `0x18007c3cf`: `GetExtension`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetExtension_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Extension; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 347, L"UriCom", L"GetExtension", L"pbstrExtension", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 348, L"UriCom", L"GetExtension", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  Extension = win_dox::UriImplementation::GetExtension(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(Extension + 8);
  if ( *(_QWORD *)(Extension + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x18007c2e0  push    rbx
0x18007c2e2  push    rsi
0x18007c2e3  push    rdi
0x18007c2e4  sub     rsp, 80h
0x18007c2eb  mov     rax, cs:__security_cookie
0x18007c2f2  xor     rax, rsp
0x18007c2f5  mov     [rsp+98h+var_28], rax
0x18007c2fa  xor     eax, eax
0x18007c2fc  mov     rdi, r8
0x18007c2ff  mov     rbx, rdx
0x18007c302  mov     rsi, rcx
0x18007c305  test    rdx, rdx
0x18007c308  jz      short loc_18007C377
0x18007c30a  test    r8, r8
0x18007c30d  jz      loc_18007C3B2
0x18007c313  lea     rcx, psz; psz
0x18007c31a  call    cs:__imp_SysAllocString
0x18007c320  mov     [rbx], rax
0x18007c323  mov     r8, rdi
0x18007c326  mov     rcx, [rsi+10h]
0x18007c32a  lea     rdx, [rsp+98h+var_50]
0x18007c32f  call    ?GetExtension@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetExtension(bool *)
0x18007c334  cmp     qword ptr [rax+20h], 8
0x18007c339  lea     rdx, [rax+8]
0x18007c33d  jb      short loc_18007C342
0x18007c33f  mov     rdx, [rdx]; psz
0x18007c342  mov     rcx, rbx; pbstr
0x18007c345  call    cs:__imp_SysReAllocString
0x18007c34b  cmp     [rsp+98h+var_30], 8
0x18007c351  jnb     short loc_18007C36B
0x18007c353  mov     rcx, [rsp+98h+var_28]
0x18007c358  xor     rcx, rsp; StackCookie
0x18007c35b  call    __security_check_cookie
0x18007c360  add     rsp, 80h
0x18007c367  pop     rdi
0x18007c368  pop     rsi
0x18007c369  pop     rbx
0x18007c36a  retn
0x18007c36b  mov     rcx, [rsp+98h+Block]; Block
0x18007c370  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c375  jmp     short loc_18007C353
0x18007c377  mov     [rsp+98h+var_60], eax
0x18007c37b  lea     rdx, aNoFilename; "(no filename)"
0x18007c382  lea     rax, aPbstrextension; "pbstrExtension"
0x18007c389  mov     r9d, 15Bh
0x18007c38f  mov     [rsp+98h+var_68], rax
0x18007c394  lea     rax, aGetextension; "GetExtension"
0x18007c39b  mov     [rsp+98h+var_70], rax
0x18007c3a0  lea     rax, aUricom; "UriCom"
0x18007c3a7  mov     [rsp+98h+var_78], rax
0x18007c3ac  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18007c3b2  mov     [rsp+98h+var_60], eax
0x18007c3b6  lea     rdx, aNoFilename; "(no filename)"
0x18007c3bd  lea     rax, aPropertynotdef; "propertyNotDefined"
0x18007c3c4  mov     r9d, 15Ch
0x18007c3ca  mov     [rsp+98h+var_68], rax
0x18007c3cf  lea     rax, aGetextension; "GetExtension"
0x18007c3d6  mov     [rsp+98h+var_70], rax
0x18007c3db  lea     rax, aUricom; "UriCom"
0x18007c3e2  mov     [rsp+98h+var_78], rax
0x18007c3e7  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```
