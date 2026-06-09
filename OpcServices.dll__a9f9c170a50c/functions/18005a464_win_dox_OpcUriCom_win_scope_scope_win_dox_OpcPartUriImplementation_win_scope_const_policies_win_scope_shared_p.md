# win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(IUri *,IOpcPartUri * *)

- ea: `0x18005a464`
- end: `0x18005a580`
- name: `?CombinePartUri_Safe@?$OpcUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIUri@@PEAPEAUIOpcPartUri@@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a42c`

## callees

- `0x180005d50`
- `0x1800186d0`
- `0x18005a464`
- `0x18005ab90`
- `0x18005b1a0`
- `0x18012a010`

## string_xrefs

- `0x18005a522`: `OpcUriCom`
- `0x18005a561`: `OpcUriCom`
- `0x18005a516`: `CombinePartUri`
- `0x18005a555`: `CombinePartUri`
- `0x18005a50a`: `combinedUri`
- `0x18005a549`: `relativeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  _BYTE v7[40]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v8; // [rsp+90h] [rbp+18h] BYREF
  __int64 v9; // [rsp+98h] [rbp+20h] BYREF

  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 123, L"OpcUriCom", L"CombinePartUri", L"combinedUri", 0);
  *a3 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 127, L"OpcUriCom", L"CombinePartUri", L"relativeUri", 0);
  win_dox::to_interface<IReceiver>::resolve(&v9, a2);
  v5 = win_dox::OpcUriImplementation::CombinePartUri(*(_QWORD *)(a1 + 16), v7, &v9);
  win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(&v8, v5);
  result = v8;
  v8 = 0;
  *a3 = result;
  if ( v9 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return result;
}

```

## disassembly

```asm
0x18005a464  mov     rax, rsp
0x18005a467  push    rdi
0x18005a468  sub     rsp, 70h
0x18005a46c  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18005a474  mov     [rax+8], rbx
0x18005a478  mov     rbx, r8
0x18005a47b  mov     rdi, rcx
0x18005a47e  test    r8, r8
0x18005a481  jz      short loc_18005A502
0x18005a483  mov     qword ptr [r8], 0
0x18005a48a  test    rdx, rdx
0x18005a48d  jz      loc_18005A541
0x18005a493  lea     rcx, [rax+20h]
0x18005a497  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18005a49c  nop
0x18005a49d  lea     r8, [rsp+78h+arg_18]
0x18005a4a5  lea     rdx, [rsp+78h+var_28]
0x18005a4aa  mov     rcx, [rdi+10h]
0x18005a4ae  call    ?CombinePartUri@OpcUriImplementation@win_dox@@QEAA?AVOpcPartUri@2@AEBVUri@2@@Z; win_dox::OpcUriImplementation::CombinePartUri(win_dox::Uri const &)
0x18005a4b3  mov     rdx, rax
0x18005a4b6  lea     rcx, [rsp+78h+arg_10]
0x18005a4be  call    ??$resolve@VOpcPartUri@win_dox@@@?$to_interface_with_create@UIOpcPartUri@@@win_dox@@SA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VOpcPartUri@1@@Z; win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(win_dox::OpcPartUri)
0x18005a4c3  mov     rax, [rsp+78h+arg_10]
0x18005a4cb  mov     [rsp+78h+arg_10], 0
0x18005a4d7  mov     [rbx], rax
0x18005a4da  mov     rcx, [rsp+78h+arg_18]
0x18005a4e2  test    rcx, rcx
0x18005a4e5  jz      short loc_18005A4F4
0x18005a4e7  mov     rax, [rcx]
0x18005a4ea  mov     rax, [rax+10h]
0x18005a4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4f3  nop
0x18005a4f4  mov     rbx, [rsp+78h+arg_0]
0x18005a4fc  add     rsp, 70h
0x18005a500  pop     rdi
0x18005a501  retn
0x18005a502  mov     [rsp+78h+var_40], 0
0x18005a50a  lea     rax, aCombineduri; "combinedUri"
0x18005a511  mov     [rsp+78h+var_48], rax
0x18005a516  lea     rax, aCombineparturi; "CombinePartUri"
0x18005a51d  mov     [rsp+78h+var_50], rax
0x18005a522  lea     rax, aOpcuricom; "OpcUriCom"
0x18005a529  mov     [rsp+78h+var_58], rax
0x18005a52e  mov     r9d, 7Bh ; '{'
0x18005a534  lea     rdx, aNoFilename; "(no filename)"
0x18005a53b  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18005a541  mov     [rsp+78h+var_40], 0
0x18005a549  lea     rax, aRelativeuri; "relativeUri"
0x18005a550  mov     [rsp+78h+var_48], rax
0x18005a555  lea     rax, aCombineparturi; "CombinePartUri"
0x18005a55c  mov     [rsp+78h+var_50], rax
0x18005a561  lea     rax, aOpcuricom; "OpcUriCom"
0x18005a568  mov     [rsp+78h+var_58], rax
0x18005a56d  mov     r9d, 7Fh
0x18005a573  lea     rdx, aNoFilename; "(no filename)"
0x18005a57a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```
