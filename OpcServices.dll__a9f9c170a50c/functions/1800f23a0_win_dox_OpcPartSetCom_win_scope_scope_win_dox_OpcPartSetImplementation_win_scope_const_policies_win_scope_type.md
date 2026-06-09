# win_dox::OpcPartSetCom<win_scope::scope<win_dox::OpcPartSetImplementation *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,IOpcPartSet>::CreatePart_Safe(IOpcPartUri *,wchar_t const *,__MIDL___MIDL_itf_msopc_0000_0002_0002,IOpcPart * *)

- ea: `0x1800f23a0`
- end: `0x1800f2518`
- name: `?CreatePart_Safe@?$OpcPartSetCom@V?$scope@PEAVOpcPartSetImplementation@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@UIOpcPartSet@@@win_dox@@AEAAXPEAUIOpcPartUri@@PEB_WW4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAPEAUIOpcPart@@@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180017dd0`
- `0x18001a0e4`
- `0x18001a810`
- `0x1800425d8`
- `0x18005ab90`
- `0x18009bc98`
- `0x1800f23a0`
- `0x1800f3e9c`
- `0x180117740`

## string_xrefs

- `0x1800f23eb`: `CreatePart`
- `0x1800f2430`: `CreatePart`
- `0x1800f246e`: `CreatePart`
- `0x1800f23f7`: `OpcPartSetCom`
- `0x1800f243c`: `OpcPartSetCom`
- `0x1800f247a`: `OpcPartSetCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall win_dox::OpcPartSetCom<win_scope::scope<win_dox::OpcPartSetImplementation *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,IOpcPartSet>::CreatePart_Safe(
        __int64 a1,
        struct IOpcPartUri *a2,
        __int64 a3,
        int a4,
        _QWORD *a5)
{
  win_dox::OpcPartSetImplementation *v8; // rbx
  __int64 Part; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  _QWORD v12[3]; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v13[24]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v14[40]; // [rsp+70h] [rbp-1h] BYREF

  v12[2] = -2;
  if ( !a5 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 114, L"OpcPartSetCom", L"CreatePart", L"part", 0);
  *a5 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 117, L"OpcPartSetCom", L"CreatePart", L"name", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 119, L"OpcPartSetCom", L"CreatePart", L"contentType", 0);
  win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v13, a2);
  v8 = *(win_dox::OpcPartSetImplementation **)(a1 + 16);
  std::wstring::wstring(v14, a3);
  Part = win_dox::OpcPartSetImplementation::CreatePart(v8, a4);
  win_dox::to_interface_with_create<IOpcPartEnumerator>::resolve<win_dox::Enumerator<IOpcPartEnumerator>>(v12, Part);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v14, v10, 0);
  v11 = v12[0];
  v12[0] = 0;
  *a5 = v11;
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v13);
}

```

## disassembly

```asm
0x1800f23a0  push    rbp
0x1800f23a2  push    rbx
0x1800f23a3  push    rsi
0x1800f23a4  push    rdi
0x1800f23a5  push    r14
0x1800f23a7  lea     rbp, [rsp-2Fh]
0x1800f23ac  sub     rsp, 0A0h
0x1800f23b3  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x1800f23bb  mov     rax, cs:__security_cookie
0x1800f23c2  xor     rax, rsp
0x1800f23c5  mov     [rbp+4Fh+var_28], rax
0x1800f23c9  mov     r14d, r9d
0x1800f23cc  mov     rsi, r8
0x1800f23cf  mov     rbx, rcx
0x1800f23d2  mov     rdi, [rbp+4Fh+arg_20]
0x1800f23d6  test    rdi, rdi
0x1800f23d9  jnz     short loc_1800F2414
0x1800f23db  mov     [rsp+0C0h+var_88], edi
0x1800f23df  lea     rax, aPart_0; "part"
0x1800f23e6  mov     [rsp+0C0h+var_90], rax
0x1800f23eb  lea     rax, aCreatepart; "CreatePart"
0x1800f23f2  mov     [rsp+0C0h+var_98], rax
0x1800f23f7  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f23fe  mov     [rsp+0C0h+var_A0], rax
0x1800f2403  lea     r9d, [rdi+72h]
0x1800f2407  lea     rdx, aNoFilename; "(no filename)"
0x1800f240e  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2414  mov     qword ptr [rdi], 0
0x1800f241b  test    rdx, rdx
0x1800f241e  jnz     short loc_1800F2459
0x1800f2420  mov     [rsp+0C0h+var_88], edx
0x1800f2424  lea     rax, aName; "name"
0x1800f242b  mov     [rsp+0C0h+var_90], rax
0x1800f2430  lea     rax, aCreatepart; "CreatePart"
0x1800f2437  mov     [rsp+0C0h+var_98], rax
0x1800f243c  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f2443  mov     [rsp+0C0h+var_A0], rax
0x1800f2448  lea     r9d, [rdx+75h]
0x1800f244c  lea     rdx, aNoFilename; "(no filename)"
0x1800f2453  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2459  test    rsi, rsi
0x1800f245c  jnz     short loc_1800F2497
0x1800f245e  mov     [rsp+0C0h+var_88], esi
0x1800f2462  lea     rax, aContenttype_0; "contentType"
0x1800f2469  mov     [rsp+0C0h+var_90], rax
0x1800f246e  lea     rax, aCreatepart; "CreatePart"
0x1800f2475  mov     [rsp+0C0h+var_98], rax
0x1800f247a  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f2481  mov     [rsp+0C0h+var_A0], rax
0x1800f2486  lea     r9d, [rsi+77h]
0x1800f248a  lea     rdx, aNoFilename; "(no filename)"
0x1800f2491  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2497  lea     rcx, [rbp+4Fh+var_68]; this
0x1800f249b  call    ??$?0PEAUIOpcPartUri@@@OpcPartUri@win_dox@@QEAA@PEAUIOpcPartUri@@@Z; win_dox::OpcPartUri::OpcPartUri(IOpcPartUri *)
0x1800f24a0  nop
0x1800f24a1  mov     rbx, [rbx+10h]
0x1800f24a5  mov     rdx, rsi
0x1800f24a8  lea     rcx, [rbp+4Fh+var_50]
0x1800f24ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800f24b1  nop
0x1800f24b2  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1800f24b7  lea     r9, [rbp+4Fh+var_50]
0x1800f24bb  lea     r8, [rbp+4Fh+var_68]
0x1800f24bf  lea     rdx, [rbp+4Fh+var_78]
0x1800f24c3  mov     rcx, rbx
0x1800f24c6  call    ?CreatePart@OpcPartSetImplementation@win_dox@@QEAA?AVOpcPart@2@AEBVOpcPartUri@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@@Z; win_dox::OpcPartSetImplementation::CreatePart(win_dox::OpcPartUri const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0000_0002_0002)
0x1800f24cb  mov     rdx, rax
0x1800f24ce  lea     rcx, [rbp+4Fh+var_80]
0x1800f24d2  call    ??$resolve@V?$Enumerator@UIOpcPartEnumerator@@@win_dox@@@?$to_interface_with_create@UIOpcPartEnumerator@@@win_dox@@SA?AV?$scope@PEAUIOpcPartEnumerator@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$Enumerator@UIOpcPartEnumerator@@@1@@Z; win_dox::to_interface_with_create<IOpcPartEnumerator>::resolve<win_dox::Enumerator<IOpcPartEnumerator>>(win_dox::Enumerator<IOpcPartEnumerator>)
0x1800f24d7  nop
0x1800f24d8  xor     r8d, r8d
0x1800f24db  mov     dl, 1
0x1800f24dd  lea     rcx, [rbp+4Fh+var_50]
0x1800f24e1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800f24e6  mov     rax, [rbp+4Fh+var_80]
0x1800f24ea  mov     [rbp+4Fh+var_80], 0
0x1800f24f2  mov     [rdi], rax
0x1800f24f5  lea     rcx, [rbp+4Fh+var_68]; this
0x1800f24f9  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800f24fe  mov     rcx, [rbp+4Fh+var_28]
0x1800f2502  xor     rcx, rsp; StackCookie
0x1800f2505  call    __security_check_cookie
0x1800f250a  add     rsp, 0A0h
0x1800f2511  pop     r14
0x1800f2513  pop     rdi
0x1800f2514  pop     rsi
0x1800f2515  pop     rbx
0x1800f2516  pop     rbp
0x1800f2517  retn
```
