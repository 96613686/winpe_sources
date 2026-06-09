# win_dox::OpcUriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(IUri *,IOpcPartUri * *)

- ea: `0x18005a8c0`
- end: `0x18005a9ce`
- name: `?CombinePartUri_Safe@?$OpcUriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIUri@@PEAPEAUIOpcPartUri@@@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a3f4`

## callees

- `0x180005d50`
- `0x1800186d0`
- `0x18005a8c0`
- `0x18005ab90`
- `0x18005b1a0`
- `0x18012a010`

## string_xrefs

- `0x18005a8fa`: `OpcUriCom`
- `0x18005a93e`: `OpcUriCom`
- `0x18005a8ef`: `CombinePartUri`
- `0x18005a932`: `CombinePartUri`
- `0x18005a8e4`: `combinedUri`
- `0x18005a926`: `relativeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::OpcUriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(
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
0x18005a8c0  mov     r11, rsp
0x18005a8c3  push    rdi
0x18005a8c4  sub     rsp, 70h
0x18005a8c8  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x18005a8d0  mov     [r11+8], rbx
0x18005a8d4  mov     rbx, r8
0x18005a8d7  mov     rdi, rcx
0x18005a8da  test    r8, r8
0x18005a8dd  jnz     short loc_18005A916
0x18005a8df  mov     [rsp+78h+var_40], r8d
0x18005a8e4  lea     rax, aCombineduri; "combinedUri"
0x18005a8eb  mov     [r11-48h], rax
0x18005a8ef  lea     rax, aCombineparturi; "CombinePartUri"
0x18005a8f6  mov     [r11-50h], rax
0x18005a8fa  lea     rax, aOpcuricom; "OpcUriCom"
0x18005a901  mov     [r11-58h], rax
0x18005a905  lea     r9d, [r8+7Bh]
0x18005a909  lea     rdx, aNoFilename; "(no filename)"
0x18005a910  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18005a916  mov     qword ptr [r8], 0
0x18005a91d  test    rdx, rdx
0x18005a920  jnz     short loc_18005A95B
0x18005a922  mov     [rsp+78h+var_40], edx
0x18005a926  lea     rax, aRelativeuri; "relativeUri"
0x18005a92d  mov     [rsp+78h+var_48], rax
0x18005a932  lea     rax, aCombineparturi; "CombinePartUri"
0x18005a939  mov     [rsp+78h+var_50], rax
0x18005a93e  lea     rax, aOpcuricom; "OpcUriCom"
0x18005a945  mov     [rsp+78h+var_58], rax
0x18005a94a  lea     r9d, [rdx+7Fh]
0x18005a94e  lea     rdx, aNoFilename; "(no filename)"
0x18005a955  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18005a95b  lea     rcx, [rsp+78h+arg_18]
0x18005a963  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18005a968  nop
0x18005a969  lea     r8, [rsp+78h+arg_18]
0x18005a971  lea     rdx, [rsp+78h+var_28]
0x18005a976  mov     rcx, [rdi+10h]
0x18005a97a  call    ?CombinePartUri@OpcUriImplementation@win_dox@@QEAA?AVOpcPartUri@2@AEBVUri@2@@Z; win_dox::OpcUriImplementation::CombinePartUri(win_dox::Uri const &)
0x18005a97f  mov     rdx, rax
0x18005a982  lea     rcx, [rsp+78h+arg_10]
0x18005a98a  call    ??$resolve@VOpcPartUri@win_dox@@@?$to_interface_with_create@UIOpcPartUri@@@win_dox@@SA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VOpcPartUri@1@@Z; win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(win_dox::OpcPartUri)
0x18005a98f  mov     rax, [rsp+78h+arg_10]
0x18005a997  mov     [rsp+78h+arg_10], 0
0x18005a9a3  mov     [rbx], rax
0x18005a9a6  mov     rcx, [rsp+78h+arg_18]
0x18005a9ae  test    rcx, rcx
0x18005a9b1  jz      short loc_18005A9C0
0x18005a9b3  mov     rax, [rcx]
0x18005a9b6  mov     rax, [rax+10h]
0x18005a9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9bf  nop
0x18005a9c0  mov     rbx, [rsp+78h+arg_0]
0x18005a9c8  add     rsp, 70h
0x18005a9cc  pop     rdi
0x18005a9cd  retn
```
