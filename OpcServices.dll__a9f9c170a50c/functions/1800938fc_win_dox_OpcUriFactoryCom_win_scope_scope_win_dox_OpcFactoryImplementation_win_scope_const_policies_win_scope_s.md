# win_dox::OpcUriFactoryCom<win_scope::scope<win_dox::OpcFactoryImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcFactory>::CreatePartUri_Safe(wchar_t const *,IOpcPartUri * *)

- ea: `0x1800938fc`
- end: `0x1800939ef`
- name: `?CreatePartUri_Safe@?$OpcUriFactoryCom@V?$scope@PEAVOpcFactoryImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcFactory@@@win_dox@@AEAAXPEB_WPEAPEAUIOpcPartUri@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800938c4`

## callees

- `0x18000c4f4`
- `0x180018d18`
- `0x1800425d8`
- `0x18005ab90`
- `0x1800938fc`
- `0x18012a010`

## string_xrefs

- `0x180093919`: `partUri`
- `0x18009392f`: `OpcUriFactoryCom`
- `0x180093973`: `OpcUriFactoryCom`
- `0x180093924`: `CreatePartUri`
- `0x180093967`: `CreatePartUri`
- `0x18009395b`: `pwzURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::OpcUriFactoryCom<win_scope::scope<win_dox::OpcFactoryImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcFactory>::CreatePartUri_Safe(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *Interface; // rax
  __int64 v5; // rcx
  _BYTE v6[32]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v7; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 84, L"OpcUriFactoryCom", L"CreatePartUri", L"partUri", 0);
  *a3 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 90, L"OpcUriFactoryCom", L"CreatePartUri", L"pwzURI", 0);
  win_dox::CreatePartUriInternal(v6, a2);
  Interface = (__int64 *)win_dox::OpcRelationshipReceiver::GetInterface(v6, &v7);
  v5 = *Interface;
  *Interface = 0;
  *a3 = v5;
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v6);
}

```

## disassembly

```asm
0x1800938fc  mov     r11, rsp
0x1800938ff  push    rbx
0x180093900  sub     rsp, 60h
0x180093904  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18009390c  mov     rbx, r8
0x18009390f  test    r8, r8
0x180093912  jnz     short loc_18009394B
0x180093914  mov     [rsp+68h+var_30], r8d
0x180093919  lea     rax, aParturi_0; "partUri"
0x180093920  mov     [r11-38h], rax
0x180093924  lea     rax, aCreateparturi; "CreatePartUri"
0x18009392b  mov     [r11-40h], rax
0x18009392f  lea     rax, aOpcurifactoryc; "OpcUriFactoryCom"
0x180093936  mov     [r11-48h], rax
0x18009393a  lea     r9d, [r8+54h]
0x18009393e  lea     rdx, aNoFilename; "(no filename)"
0x180093945  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18009394b  mov     qword ptr [r8], 0
0x180093952  test    rdx, rdx
0x180093955  jnz     short loc_180093990
0x180093957  mov     [rsp+68h+var_30], edx
0x18009395b  lea     rax, aPwzuri; "pwzURI"
0x180093962  mov     [rsp+68h+var_38], rax
0x180093967  lea     rax, aCreateparturi; "CreatePartUri"
0x18009396e  mov     [rsp+68h+var_40], rax
0x180093973  lea     rax, aOpcurifactoryc; "OpcUriFactoryCom"
0x18009397a  mov     [rsp+68h+var_48], rax
0x18009397f  lea     r9d, [rdx+5Ah]
0x180093983  lea     rdx, aNoFilename; "(no filename)"
0x18009398a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180093990  lea     rcx, [rsp+68h+var_20]
0x180093995  call    ?CreatePartUriInternal@win_dox@@YA?AVOpcPartUri@1@PEB_W@Z; win_dox::CreatePartUriInternal(wchar_t const *)
0x18009399a  nop
0x18009399b  lea     rdx, [rsp+68h+arg_10]
0x1800939a3  lea     rcx, [rsp+68h+var_20]
0x1800939a8  call    ?GetInterface@OpcRelationshipReceiver@win_dox@@QEBA?AV?$scope@PEAUIOpcRelationshipReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcRelationshipReceiver::GetInterface(void)
0x1800939ad  mov     rcx, [rax]
0x1800939b0  mov     qword ptr [rax], 0
0x1800939b7  mov     [rbx], rcx
0x1800939ba  mov     rcx, [rsp+68h+arg_10]
0x1800939c2  test    rcx, rcx
0x1800939c5  jz      short loc_1800939DF
0x1800939c7  mov     rax, [rcx]
0x1800939ca  mov     rax, [rax+10h]
0x1800939ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939d3  mov     [rsp+68h+arg_10], 0
0x1800939df  lea     rcx, [rsp+68h+var_20]; this
0x1800939e4  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800939e9  add     rsp, 60h
0x1800939ed  pop     rbx
0x1800939ee  retn
```
