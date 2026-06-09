# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetDisplayUri_Safe(wchar_t * *,bool *)

- ea: `0x1800980f0`
- end: `0x1800981ef`
- name: `?GetDisplayUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18005ab90`
- `0x1800980f0`
- `0x1800981f8`
- `0x1800cce54`
- `0x180117740`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180098197`
- `OLEAUT32!__imp_SysAllocString` at `0x180098197`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800981c2`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800981c2`

## string_xrefs

- `0x18009812c`: `GetDisplayUri`
- `0x18009816c`: `GetDisplayUri`
- `0x18009813e`: `UriCom`
- `0x18009817e`: `UriCom`
- `0x180098119`: `pbstrDisplayUri`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetDisplayUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 DisplayUri; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+40h] [rbp-48h] BYREF
  void *Block; // [rsp+48h] [rbp-40h]
  unsigned __int64 v10; // [rsp+60h] [rbp-28h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 285, L"UriCom", L"GetDisplayUri", L"pbstrDisplayUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 286, L"UriCom", L"GetDisplayUri", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&psz);
  DisplayUri = win_dox::UriImplementation::GetDisplayUri(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(DisplayUri + 8);
  if ( *(_QWORD *)(DisplayUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x1800980f0  push    rbx
0x1800980f2  push    rsi
0x1800980f3  push    rdi
0x1800980f4  sub     rsp, 70h
0x1800980f8  mov     rax, cs:__security_cookie
0x1800980ff  xor     rax, rsp
0x180098102  mov     [rsp+88h+var_20], rax
0x180098107  mov     rdi, r8
0x18009810a  mov     rbx, rdx
0x18009810d  mov     rsi, rcx
0x180098110  test    rdx, rdx
0x180098113  jnz     short loc_180098150
0x180098115  mov     [rsp+88h+var_50], edx
0x180098119  lea     rax, aPbstrdisplayur; "pbstrDisplayUri"
0x180098120  mov     [rsp+88h+var_58], rax
0x180098125  lea     rdx, aNoFilename; "(no filename)"
0x18009812c  lea     rax, aGetdisplayuri; "GetDisplayUri"
0x180098133  mov     r9d, 11Dh
0x180098139  mov     [rsp+88h+var_60], rax
0x18009813e  lea     rax, aUricom; "UriCom"
0x180098145  mov     [rsp+88h+var_68], rax
0x18009814a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180098150  test    rdi, rdi
0x180098153  jnz     short loc_180098190
0x180098155  mov     [rsp+88h+var_50], edi
0x180098159  lea     rax, aPropertynotdef; "propertyNotDefined"
0x180098160  mov     [rsp+88h+var_58], rax
0x180098165  lea     rdx, aNoFilename; "(no filename)"
0x18009816c  lea     rax, aGetdisplayuri; "GetDisplayUri"
0x180098173  mov     r9d, 11Eh
0x180098179  mov     [rsp+88h+var_60], rax
0x18009817e  lea     rax, aUricom; "UriCom"
0x180098185  mov     [rsp+88h+var_68], rax
0x18009818a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180098190  lea     rcx, psz; psz
0x180098197  call    cs:__imp_SysAllocString
0x18009819d  mov     [rbx], rax
0x1800981a0  mov     r8, rdi
0x1800981a3  mov     rcx, [rsi+10h]
0x1800981a7  lea     rdx, [rsp+88h+var_48]
0x1800981ac  call    ?GetDisplayUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetDisplayUri(bool *)
0x1800981b1  cmp     qword ptr [rax+20h], 8
0x1800981b6  lea     rdx, [rax+8]
0x1800981ba  jb      short loc_1800981BF
0x1800981bc  mov     rdx, [rdx]; psz
0x1800981bf  mov     rcx, rbx; pbstr
0x1800981c2  call    cs:__imp_SysReAllocString
0x1800981c8  cmp     [rsp+88h+var_28], 8
0x1800981ce  jb      short loc_1800981DA
0x1800981d0  mov     rcx, [rsp+88h+Block]; Block
0x1800981d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800981da  mov     rcx, [rsp+88h+var_20]
0x1800981df  xor     rcx, rsp; StackCookie
0x1800981e2  call    __security_check_cookie
0x1800981e7  add     rsp, 70h
0x1800981eb  pop     rdi
0x1800981ec  pop     rsi
0x1800981ed  pop     rbx
0x1800981ee  retn
```
