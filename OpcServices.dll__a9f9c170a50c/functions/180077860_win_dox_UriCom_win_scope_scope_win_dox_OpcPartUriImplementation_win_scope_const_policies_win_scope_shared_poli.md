# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(wchar_t * *,bool *)

- ea: `0x180077860`
- end: `0x18007796d`
- name: `?GetAbsoluteUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18005ab90`
- `0x180077860`
- `0x180077974`
- `0x1800cce54`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007789a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007789a`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800778c5`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800778c5`

## string_xrefs

- `0x180077920`: `UriCom`
- `0x18007795b`: `UriCom`
- `0x180077902`: `pbstrAbsoluteUri`
- `0x180077914`: `GetAbsoluteUri`
- `0x18007794f`: `GetAbsoluteUri`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 AbsoluteUri; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

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
  AbsoluteUri = win_dox::UriImplementation::GetAbsoluteUri(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(AbsoluteUri + 8);
  if ( *(_QWORD *)(AbsoluteUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180077860  push    rbx
0x180077862  push    rsi
0x180077863  push    rdi
0x180077864  sub     rsp, 80h
0x18007786b  mov     rax, cs:__security_cookie
0x180077872  xor     rax, rsp
0x180077875  mov     [rsp+98h+var_28], rax
0x18007787a  xor     eax, eax
0x18007787c  mov     rdi, r8
0x18007787f  mov     rbx, rdx
0x180077882  mov     rsi, rcx
0x180077885  test    rdx, rdx
0x180077888  jz      short loc_1800778F7
0x18007788a  test    r8, r8
0x18007788d  jz      loc_180077932
0x180077893  lea     rcx, psz; psz
0x18007789a  call    cs:__imp_SysAllocString
0x1800778a0  mov     [rbx], rax
0x1800778a3  mov     r8, rdi
0x1800778a6  mov     rcx, [rsi+10h]
0x1800778aa  lea     rdx, [rsp+98h+var_50]
0x1800778af  call    ?GetAbsoluteUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetAbsoluteUri(bool *)
0x1800778b4  cmp     qword ptr [rax+20h], 8
0x1800778b9  lea     rdx, [rax+8]
0x1800778bd  jb      short loc_1800778C2
0x1800778bf  mov     rdx, [rdx]; psz
0x1800778c2  mov     rcx, rbx; pbstr
0x1800778c5  call    cs:__imp_SysReAllocString
0x1800778cb  cmp     [rsp+98h+var_30], 8
0x1800778d1  jnb     short loc_1800778EB
0x1800778d3  mov     rcx, [rsp+98h+var_28]
0x1800778d8  xor     rcx, rsp; StackCookie
0x1800778db  call    __security_check_cookie
0x1800778e0  add     rsp, 80h
0x1800778e7  pop     rdi
0x1800778e8  pop     rsi
0x1800778e9  pop     rbx
0x1800778ea  retn
0x1800778eb  mov     rcx, [rsp+98h+Block]; Block
0x1800778f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800778f5  jmp     short loc_1800778D3
0x1800778f7  mov     [rsp+98h+var_60], eax
0x1800778fb  lea     rdx, aNoFilename; "(no filename)"
0x180077902  lea     rax, aPbstrabsoluteu; "pbstrAbsoluteUri"
0x180077909  mov     r9d, 0DDh
0x18007790f  mov     [rsp+98h+var_68], rax
0x180077914  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x18007791b  mov     [rsp+98h+var_70], rax
0x180077920  lea     rax, aUricom; "UriCom"
0x180077927  mov     [rsp+98h+var_78], rax
0x18007792c  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180077932  mov     [rsp+98h+var_60], eax
0x180077936  lea     rdx, aNoFilename; "(no filename)"
0x18007793d  lea     rax, aPropertynotdef; "propertyNotDefined"
0x180077944  mov     r9d, 0DEh
0x18007794a  mov     [rsp+98h+var_68], rax
0x18007794f  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x180077956  mov     [rsp+98h+var_70], rax
0x18007795b  lea     rax, aUricom; "UriCom"
0x180077962  mov     [rsp+98h+var_78], rax
0x180077967  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```
