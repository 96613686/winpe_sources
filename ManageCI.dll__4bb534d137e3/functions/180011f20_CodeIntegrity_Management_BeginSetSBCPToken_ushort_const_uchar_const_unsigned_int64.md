# CodeIntegrity::Management::BeginSetSBCPToken(ushort const *,uchar const *,unsigned __int64)

- ea: `0x180011f20`
- end: `0x180012107`
- name: `?BeginSetSBCPToken@Management@CodeIntegrity@@YAXPEBGPEBE_K@Z`
- size: `487`
- prototype: `void __fastcall(CodeIntegrity::Management *this, const unsigned __int16 *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008af0`

## callees

- `0x180002a90`
- `0x180005494`
- `0x18000828c`
- `0x180008474`
- `0x18000d470`
- `0x18000eab0`
- `0x18000f09c`
- `0x1800109d8`
- `0x180010a1c`
- `0x180011308`
- `0x1800114f8`
- `0x180011f20`
- `0x1800139d0`
- `0x180018834`
- `0x180021ffc`

## string_xrefs

- `0x180012020`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::BeginSetSBCPToken(
        CodeIntegrity::Management *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3)
{
  int v4; // edi
  __int64 v6; // r14
  __int64 v7; // rax
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  int updated; // eax
  __int64 v11; // rdi
  wil *v12; // rcx
  CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *v13; // rbx
  int v14; // eax
  unsigned int v15; // r8d
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-1E8h]
  __int64 v18; // [rsp+20h] [rbp-1E8h]
  __int64 v19; // [rsp+40h] [rbp-1C8h] BYREF
  const unsigned __int8 *v20; // [rsp+48h] [rbp-1C0h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-1B8h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-1B0h] BYREF
  char v23; // [rsp+68h] [rbp-1A0h]
  _BYTE v24[32]; // [rsp+70h] [rbp-198h] BYREF
  _BYTE v25[32]; // [rsp+90h] [rbp-178h] BYREF
  _BYTE v26[32]; // [rsp+B0h] [rbp-158h] BYREF
  _BYTE v27[32]; // [rsp+D0h] [rbp-138h] BYREF
  _BYTE v28[240]; // [rsp+F0h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v4 = (int)a2;
  v21 = a2;
  v20 = a3;
  v19 = 0;
  try
  {
    std::wstring::wstring(v25, this);
    CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
      (unsigned int)v28,
      (unsigned int)qword_180039720,
      (unsigned int)v25,
      v4,
      (__int64)a3);
    std::wstring::_Tidy_deallocate(v25);
    v22[0] = &v19;
    v22[1] = 0;
    v23 = 1;
    v6 = std::wstring::wstring(v24, this);
    v7 = std::operator+<unsigned short>(v27, qword_180039720);
    std::wstring::wstring(v26, v8, v7, v6);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    updated = SIPolicyPmUpdateTokenBegin(v9);
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)updated,
        v17);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v27);
    std::wstring::_Tidy_deallocate(v24);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v22);
    v11 = qword_180039718;
    v18 = std::wstring::wstring(v24, this);
    v12 = (wil *)v11;
  }
  catch ( std::exception )
  {
    v13 = qword_180039708;
    v14 = wil::ResultFromCaughtException(v12);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveCIPolicy(v13, v14);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x1E1, v15, v16);
  }
  std::wstring::wstring(v25, this);
  CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
    (unsigned int)v28,
    (unsigned int)qword_180039720,
    (unsigned int)v25,
    v4,
    (__int64)a3);
  std::wstring::_Tidy_deallocate(v25);
  v22[0] = &v19;
  v22[1] = 0;
}

```

## disassembly

```asm
0x180011f20  mov     [rsp+arg_18], rbx
0x180011f25  push    rsi
0x180011f26  push    rdi
0x180011f27  push    r14
0x180011f29  sub     rsp, 1F0h
0x180011f30  mov     rax, cs:__security_cookie
0x180011f37  xor     rax, rsp
0x180011f3a  mov     [rsp+208h+var_28], rax
0x180011f42  mov     rsi, r8
0x180011f45  mov     rdi, rdx
0x180011f48  mov     rbx, rcx
0x180011f4b  mov     [rsp+208h+var_1B8], rdx
0x180011f50  mov     [rsp+208h+var_1C0], r8
0x180011f55  mov     [rsp+208h+var_1C8], 0
0x180011f5e  mov     rdx, rcx
0x180011f61  lea     rcx, [rsp+208h+var_178]
0x180011f69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011f6e  mov     qword ptr [rsp+208h+var_1E8], rsi; int
0x180011f73  mov     r9, rdi
0x180011f76  lea     r8, [rsp+208h+var_178]
0x180011f7e  lea     rdx, qword_180039720
0x180011f85  lea     rcx, [rsp+208h+var_118]
0x180011f8d  call    ?CreateAuthorizationToken@AuthorizationToken@Management@CodeIntegrity@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBE_K@Z; CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(std::wstring const &,std::wstring const &,uchar const *,unsigned __int64)
0x180011f92  nop
0x180011f93  lea     rcx, [rsp+208h+var_178]
0x180011f9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011fa0  lea     rax, [rsp+208h+var_1C8]
0x180011fa5  mov     [rsp+208h+var_1B0], rax
0x180011faa  mov     [rsp+208h+var_1A8], 0
0x180011fb3  mov     [rsp+208h+var_1A0], 1
0x180011fb8  mov     rdx, rbx
0x180011fbb  lea     rcx, [rsp+208h+var_198]
0x180011fc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011fc5  mov     r14, rax
0x180011fc8  lea     rdx, qword_180039720
0x180011fcf  lea     rcx, [rsp+208h+var_138]
0x180011fd7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180011fdc  nop
0x180011fdd  mov     r9, r14
0x180011fe0  mov     r8, rax
0x180011fe3  lea     rcx, [rsp+208h+var_158]
0x180011feb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180011ff0  nop
0x180011ff1  lea     rcx, [rsp+208h+var_158]
0x180011ff9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011ffe  mov     rcx, rax; SourceString
0x180012001  lea     r9, [rsp+208h+var_1A8]
0x180012006  mov     r8d, esi
0x180012009  mov     rdx, rdi
0x18001200c  call    SIPolicyPmUpdateTokenBegin
0x180012011  mov     rcx, [rsp+208h]; this
0x180012019  test    eax, eax
0x18001201b  jns     short loc_180012032
0x18001201d  mov     r9d, eax; char *
0x180012020  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180012027  mov     edx, 1D3h; void *
0x18001202c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012032  lea     rcx, [rsp+208h+var_158]
0x18001203a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001203f  nop
0x180012040  lea     rcx, [rsp+208h+var_138]
0x180012048  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001204d  nop
0x18001204e  lea     rcx, [rsp+208h+var_198]
0x180012053  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012058  nop
0x180012059  lea     rcx, [rsp+208h+var_1B0]
0x18001205e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180012063  mov     rdi, cs:qword_180039718
0x18001206a  mov     rdx, rbx
0x18001206d  lea     rcx, [rsp+208h+var_198]
0x180012072  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012077  nop
0x180012078  lea     rcx, [rsp+208h+var_1C0]
0x18001207d  mov     [rsp+208h+var_1D8], rcx
0x180012082  lea     rcx, [rsp+208h+var_1B8]
0x180012087  mov     [rsp+208h+var_1E0], rcx
0x18001208c  mov     qword ptr [rsp+208h+var_1E8], rax
0x180012091  lea     r9, qword_180039720
0x180012098  lea     r8, [rsp+208h+var_1C8]
0x18001209d  lea     rdx, [rsp+208h+var_1B0]
0x1800120a2  mov     rcx, rdi
0x1800120a5  call    ??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@AEAPEBEAEA_K@?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV51@AEAPEBEAEA_K@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,uchar const * &,unsigned __int64 &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring &&,uchar const * &,unsigned __int64 &)
0x1800120aa  nop
0x1800120ab  lea     rcx, [rsp+208h+var_198]
0x1800120b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800120b5  lea     rdx, [rsp+208h+var_118]; struct CodeIntegrity::Management::AuthorizationToken *
0x1800120bd  mov     rcx, cs:qword_180039708; this
0x1800120c4  call    ?InstrumentAddSBCPToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddSBCPToken(CodeIntegrity::Management::AuthorizationToken const &)
0x1800120c9  nop
0x1800120ca  lea     rcx, [rsp+208h+var_118]; this
0x1800120d2  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x1800120d7  nop
0x1800120d8  lea     rcx, [rsp+208h+var_1C8]
0x1800120dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800120e2  nop
0x1800120e3  mov     rcx, [rsp+208h+var_28]
0x1800120eb  xor     rcx, rsp; StackCookie
0x1800120ee  call    __security_check_cookie
0x1800120f3  mov     rbx, [rsp+208h+arg_18]
0x1800120fb  add     rsp, 1F0h
0x180012102  pop     r14
0x180012104  pop     rdi
0x180012105  pop     rsi
0x180012106  retn
```
