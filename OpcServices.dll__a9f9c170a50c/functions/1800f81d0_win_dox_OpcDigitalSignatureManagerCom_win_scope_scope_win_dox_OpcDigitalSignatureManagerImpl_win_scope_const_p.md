# win_dox::OpcDigitalSignatureManagerCom<win_scope::scope<win_dox::OpcDigitalSignatureManagerImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignatureManager,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcDigitalSignatureManagerImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignatureManager,win_scope::report_policy_throw>>::ReplaceSignatureXml_Safe(IOpcPartUri *,uchar const *,uint,IOpcDigitalSignature * *)

- ea: `0x1800f81d0`
- end: `0x1800f8313`
- name: `?ReplaceSignatureXml_Safe@?$OpcDigitalSignatureManagerCom@V?$scope@PEAVOpcDigitalSignatureManagerImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcDigitalSignatureManager@@V?$ScopeInnerStore@V?$scope@PEAVOpcDigitalSignatureManagerImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcDigitalSignatureManager@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAUIOpcPartUri@@PEBEIPEAPEAUIOpcDigitalSignature@@@Z`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001a0e4`
- `0x1800425d8`
- `0x18005ab90`
- `0x18009e350`
- `0x1800f81d0`
- `0x1800fce48`

## string_xrefs

- `0x1800f8210`: `OpcDigitalSignatureManagerCom`
- `0x1800f8252`: `OpcDigitalSignatureManagerCom`
- `0x1800f8292`: `OpcDigitalSignatureManagerCom`
- `0x1800f8205`: `ReplaceSignatureXml`
- `0x1800f8246`: `ReplaceSignatureXml`
- `0x1800f8286`: `ReplaceSignatureXml`
- `0x1800f827a`: `newSignatureXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_dox::OpcDigitalSignatureManagerCom<win_scope::scope<win_dox::OpcDigitalSignatureManagerImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignatureManager,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcDigitalSignatureManagerImpl *,win_scope::const_policies<win_scope::shared_policies>>,IOpcDigitalSignatureManager,win_scope::report_policy_throw>>::ReplaceSignatureXml_Safe(
        __int64 a1,
        struct IOpcPartUri *a2,
        __int64 a3,
        int a4,
        _QWORD *a5)
{
  _QWORD *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 result; // rax
  _QWORD v10[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h] BYREF
  int v12; // [rsp+58h] [rbp-30h]
  _BYTE v13[40]; // [rsp+60h] [rbp-28h] BYREF

  v10[1] = -2;
  v5 = a5;
  if ( !a5 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      392,
      L"OpcDigitalSignatureManagerCom",
      L"ReplaceSignatureXml",
      L"digitalSignature",
      0);
  *a5 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      395,
      L"OpcDigitalSignatureManagerCom",
      L"ReplaceSignatureXml",
      L"signaturePartName",
      0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      397,
      L"OpcDigitalSignatureManagerCom",
      L"ReplaceSignatureXml",
      L"newSignatureXml",
      0);
  v11 = a3;
  v12 = a4;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v13, a2);
  v8 = win_dox::OpcDigitalSignatureManagerImpl::ReplaceSignatureXml(v6, &a5, v7, &v11);
  win_dox::to_interface_with_create<IOpcSignatureCustomObject>::resolve<win_dox::OpcSignatureCustomObject>(v10, v8);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v13);
  result = v10[0];
  *v5 = v10[0];
  return result;
}

```

## disassembly

```asm
0x1800f81d0  mov     r11, rsp
0x1800f81d3  push    rdi
0x1800f81d4  sub     rsp, 80h
0x1800f81db  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1800f81e3  mov     [r11+8], rbx
0x1800f81e7  mov     rdi, [rsp+88h+arg_20]
0x1800f81ef  xor     eax, eax
0x1800f81f1  test    rdi, rdi
0x1800f81f4  jnz     short loc_1800F822E
0x1800f81f6  mov     [rsp+88h+var_50], eax
0x1800f81fa  lea     rax, aDigitalsignatu; "digitalSignature"
0x1800f8201  mov     [r11-58h], rax
0x1800f8205  lea     rax, aReplacesignatu; "ReplaceSignatureXml"
0x1800f820c  mov     [r11-60h], rax
0x1800f8210  lea     rax, aOpcdigitalsign; "OpcDigitalSignatureManagerCom"
0x1800f8217  mov     [r11-68h], rax
0x1800f821b  mov     r9d, 188h
0x1800f8221  lea     rdx, aNoFilename; "(no filename)"
0x1800f8228  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f822e  mov     [rdi], rax
0x1800f8231  test    rdx, rdx
0x1800f8234  jnz     short loc_1800F8271
0x1800f8236  mov     [rsp+88h+var_50], eax
0x1800f823a  lea     rax, aSignaturepartn; "signaturePartName"
0x1800f8241  mov     [rsp+88h+var_58], rax
0x1800f8246  lea     rax, aReplacesignatu; "ReplaceSignatureXml"
0x1800f824d  mov     [rsp+88h+var_60], rax
0x1800f8252  lea     rax, aOpcdigitalsign; "OpcDigitalSignatureManagerCom"
0x1800f8259  mov     [rsp+88h+var_68], rax
0x1800f825e  mov     r9d, 18Bh
0x1800f8264  lea     rdx, aNoFilename; "(no filename)"
0x1800f826b  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f8271  test    r8, r8
0x1800f8274  jnz     short loc_1800F82B1
0x1800f8276  mov     [rsp+88h+var_50], eax
0x1800f827a  lea     rax, aNewsignaturexm; "newSignatureXml"
0x1800f8281  mov     [rsp+88h+var_58], rax
0x1800f8286  lea     rax, aReplacesignatu; "ReplaceSignatureXml"
0x1800f828d  mov     [rsp+88h+var_60], rax
0x1800f8292  lea     rax, aOpcdigitalsign; "OpcDigitalSignatureManagerCom"
0x1800f8299  mov     [rsp+88h+var_68], rax
0x1800f829e  mov     r9d, 18Dh
0x1800f82a4  lea     rdx, aNoFilename; "(no filename)"
0x1800f82ab  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f82b1  mov     [rsp+88h+var_38], r8
0x1800f82b6  mov     [rsp+88h+var_30], r9d
0x1800f82bb  mov     rbx, [rcx+10h]
0x1800f82bf  lea     rcx, [rsp+88h+var_28]; this
0x1800f82c4  call    ??$?0PEAUIOpcPartUri@@@OpcPartUri@win_dox@@QEAA@PEAUIOpcPartUri@@@Z; win_dox::OpcPartUri::OpcPartUri(IOpcPartUri *)
0x1800f82c9  nop
0x1800f82ca  lea     r9, [rsp+88h+var_38]
0x1800f82cf  mov     r8, rax
0x1800f82d2  lea     rdx, [rsp+88h+arg_20]
0x1800f82da  mov     rcx, rbx
0x1800f82dd  call    ?ReplaceSignatureXml@OpcDigitalSignatureManagerImpl@win_dox@@QEAA?AVOpcDigitalSignature@2@AEBVOpcPartUri@2@AEBU?$SMART_VECTOR@PEBE@2@@Z; win_dox::OpcDigitalSignatureManagerImpl::ReplaceSignatureXml(win_dox::OpcPartUri const &,win_dox::SMART_VECTOR<uchar const *> const &)
0x1800f82e2  mov     rdx, rax
0x1800f82e5  lea     rcx, [rsp+88h+var_48]
0x1800f82ea  call    ??$resolve@VOpcSignatureCustomObject@win_dox@@@?$to_interface_with_create@UIOpcSignatureCustomObject@@@win_dox@@SA?AV?$scope@PEAUIOpcSignatureCustomObject@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureCustomObject@1@@Z; win_dox::to_interface_with_create<IOpcSignatureCustomObject>::resolve<win_dox::OpcSignatureCustomObject>(win_dox::OpcSignatureCustomObject)
0x1800f82ef  nop
0x1800f82f0  lea     rcx, [rsp+88h+var_28]; this
0x1800f82f5  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800f82fa  mov     rax, [rsp+88h+var_48]
0x1800f82ff  mov     [rdi], rax
0x1800f8302  mov     rbx, [rsp+88h+arg_0]
0x1800f830a  add     rsp, 80h
0x1800f8311  pop     rdi
0x1800f8312  retn
```
