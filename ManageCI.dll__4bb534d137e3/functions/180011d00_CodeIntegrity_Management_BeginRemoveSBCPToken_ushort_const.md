# CodeIntegrity::Management::BeginRemoveSBCPToken(ushort const *)

- ea: `0x180011d00`
- end: `0x180011f11`
- name: `?BeginRemoveSBCPToken@Management@CodeIntegrity@@YAXPEBG@Z`
- size: `529`
- prototype: `void __fastcall(CodeIntegrity::Management *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x180002a90`
- `0x18000828c`
- `0x180008474`
- `0x18000d470`
- `0x18000eab0`
- `0x18000f1ec`
- `0x180010534`
- `0x1800109d8`
- `0x180010a1c`
- `0x180011308`
- `0x1800114f8`
- `0x180011d00`
- `0x18001417c`
- `0x180015518`
- `0x1800159fc`
- `0x180015a6c`
- `0x180021af4`

## string_xrefs

- `0x180011e43`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::BeginRemoveSBCPToken(
        CodeIntegrity::Management *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  const struct CodeIntegrity::Management::AuthorizationToken *v11; // rbx
  const WCHAR *v12; // rax
  int v13; // eax
  wil *v14; // rsi
  __int64 v15; // rcx
  CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *v16; // rbx
  int v17; // eax
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // [rsp+20h] [rbp-A8h]
  __int64 v21; // [rsp+20h] [rbp-A8h]
  __int64 v22; // [rsp+40h] [rbp-88h] BYREF
  __int64 v23; // [rsp+48h] [rbp-80h] BYREF
  __int64 v24; // [rsp+50h] [rbp-78h] BYREF
  __int64 *v25; // [rsp+58h] [rbp-70h] BYREF
  struct _UNICODE_STRING *v26; // [rsp+60h] [rbp-68h] BYREF
  char v27; // [rsp+68h] [rbp-60h]
  _BYTE v28[32]; // [rsp+78h] [rbp-50h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v23 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
    qword_180039710,
    &v22,
    qword_180039720);
  try
  {
    if ( v22 == *(_QWORD *)qword_180039710 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0xFA, v3, v4, v20);
    v5 = (__int64 *)(v22 + 64);
    v6 = std::wstring::wstring((__int64)v28, (__int64)this);
    v7 = std::operator+<unsigned short>(v29, qword_180039720);
    std::wstring::wstring(&v25, v8, v7, v6);
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(
      v5,
      &v22,
      (__int64)&v25);
    std::wstring::_Tidy_deallocate((__int64)&v25);
    std::wstring::_Tidy_deallocate((__int64)v29);
    std::wstring::_Tidy_deallocate((__int64)v28);
    if ( v22 == *v5 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x100, v9, v10, v20);
    v11 = (const struct CodeIntegrity::Management::AuthorizationToken *)(v22 + 32);
    v25 = &v23;
    v26 = 0;
    v27 = 1;
    CodeIntegrity::Management::detail::SbcpTokenView::name(v22 + 32, v28);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    v13 = SIPolicyPmDeleteTokenBegin(v12, &v26);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x108,
        (int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)v13,
        v20);
    std::wstring::_Tidy_deallocate((__int64)v28);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>((__int64)&v25);
    v14 = (wil *)qword_180039838;
    v15 = *((_QWORD *)v11 + 11);
    v22 = *((_QWORD *)v11 + 12) - v15;
    v24 = v15;
    v21 = std::wstring::wstring((__int64)v28, (__int64)this);
  }
  catch ( std::exception )
  {
    v16 = qword_180039708;
    v17 = wil::ResultFromCaughtException(v14);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveSBCPToken(v16, v17);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x117, v18, v19);
  }
  if ( v22 == *(_QWORD *)qword_180039710 )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0xFA, v3, v4, v20);
  v5 = (__int64 *)(v22 + 64);
  v6 = std::wstring::wstring((__int64)v28, (__int64)this);
  v7 = std::operator+<unsigned short>(v29, qword_180039720);
}

```

## disassembly

```asm
0x180011d00  mov     [rsp+arg_8], rbx
0x180011d05  mov     [rsp+arg_10], rsi
0x180011d0a  push    rdi
0x180011d0b  sub     rsp, 0C0h
0x180011d12  mov     rax, cs:__security_cookie
0x180011d19  xor     rax, rsp
0x180011d1c  mov     [rsp+0C8h+var_10], rax
0x180011d24  mov     rdi, rcx
0x180011d27  mov     [rsp+0C8h+var_80], 0
0x180011d30  lea     r8, qword_180039720
0x180011d37  lea     rdx, [rsp+0C8h+var_88]
0x180011d3c  mov     rcx, cs:qword_180039710
0x180011d43  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x180011d48  mov     rax, [rsp+0C8h+var_88]
0x180011d4d  mov     rcx, cs:qword_180039710
0x180011d54  cmp     rax, [rcx]
0x180011d57  jnz     short loc_180011D6B
0x180011d59  mov     rcx, [rsp+0C8h]; this
0x180011d61  mov     edx, 0FAh; void *
0x180011d66  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011d6b  lea     rbx, [rax+40h]
0x180011d6f  mov     rdx, rdi
0x180011d72  lea     rcx, [rsp+0C8h+var_50]
0x180011d77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011d7c  mov     rsi, rax
0x180011d7f  lea     rdx, qword_180039720
0x180011d86  lea     rcx, [rsp+0C8h+var_30]
0x180011d8e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180011d93  nop
0x180011d94  mov     r9, rsi
0x180011d97  mov     r8, rax
0x180011d9a  lea     rcx, [rsp+0C8h+var_70]
0x180011d9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180011da4  lea     r8, [rsp+0C8h+var_70]
0x180011da9  lea     rdx, [rsp+0C8h+var_88]
0x180011dae  mov     rcx, rbx
0x180011db1  call    ??$find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@$0A@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(std::wstring const &)
0x180011db6  lea     rcx, [rsp+0C8h+var_70]
0x180011dbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011dc0  nop
0x180011dc1  lea     rcx, [rsp+0C8h+var_30]
0x180011dc9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011dce  nop
0x180011dcf  lea     rcx, [rsp+0C8h+var_50]
0x180011dd4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011dd9  mov     rax, [rsp+0C8h+var_88]
0x180011dde  cmp     rax, [rbx]
0x180011de1  jnz     short loc_180011DF5
0x180011de3  mov     rcx, [rsp+0C8h]; this
0x180011deb  mov     edx, 100h; void *
0x180011df0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011df5  lea     rbx, [rax+20h]
0x180011df9  lea     rax, [rsp+0C8h+var_80]
0x180011dfe  mov     [rsp+0C8h+var_70], rax
0x180011e03  mov     [rsp+0C8h+var_68], 0
0x180011e0c  mov     [rsp+0C8h+var_60], 1
0x180011e11  lea     rdx, [rsp+0C8h+var_50]
0x180011e16  mov     rcx, rbx
0x180011e19  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x180011e1e  nop
0x180011e1f  mov     rcx, rax
0x180011e22  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011e27  lea     rdx, [rsp+0C8h+var_68]
0x180011e2c  mov     rcx, rax; SourceString
0x180011e2f  call    SIPolicyPmDeleteTokenBegin
0x180011e34  mov     rcx, [rsp+0C8h]; this
0x180011e3c  test    eax, eax
0x180011e3e  jns     short loc_180011E55
0x180011e40  mov     r9d, eax; char *
0x180011e43  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180011e4a  mov     edx, 108h; void *
0x180011e4f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180011e55  lea     rcx, [rsp+0C8h+var_50]
0x180011e5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011e5f  nop
0x180011e60  lea     rcx, [rsp+0C8h+var_70]
0x180011e65  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180011e6a  mov     rsi, cs:qword_180039838
0x180011e71  mov     rcx, [rbx+58h]
0x180011e75  mov     rax, [rbx+60h]
0x180011e79  sub     rax, rcx
0x180011e7c  mov     [rsp+0C8h+var_88], rax
0x180011e81  mov     [rsp+0C8h+var_78], rcx
0x180011e86  mov     rdx, rdi
0x180011e89  lea     rcx, [rsp+0C8h+var_50]
0x180011e8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011e93  nop
0x180011e94  lea     rcx, [rsp+0C8h+var_88]
0x180011e99  mov     [rsp+0C8h+var_98], rcx
0x180011e9e  lea     rcx, [rsp+0C8h+var_78]
0x180011ea3  mov     [rsp+0C8h+var_A0], rcx
0x180011ea8  mov     [rsp+0C8h+var_A8], rax
0x180011ead  lea     r9, qword_180039720
0x180011eb4  lea     r8, [rsp+0C8h+var_80]
0x180011eb9  lea     rdx, [rsp+0C8h+var_70]
0x180011ebe  mov     rcx, rsi
0x180011ec1  call    ??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@PEBE_K@?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV51@$$QEAPEBE$$QEA_K@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,uchar const *,unsigned __int64>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring &&,uchar const * &&,unsigned __int64 &&)
0x180011ec6  nop
0x180011ec7  lea     rcx, [rsp+0C8h+var_50]
0x180011ecc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011ed1  mov     rdx, rbx; struct CodeIntegrity::Management::AuthorizationToken *
0x180011ed4  mov     rcx, cs:qword_180039708; this
0x180011edb  call    ?InstrumentRemoveSBCPToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRemoveSBCPToken(CodeIntegrity::Management::AuthorizationToken const &)
0x180011ee0  nop
0x180011ee1  lea     rcx, [rsp+0C8h+var_80]
0x180011ee6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011eeb  nop
0x180011eec  mov     rcx, [rsp+0C8h+var_10]
0x180011ef4  xor     rcx, rsp; StackCookie
0x180011ef7  call    __security_check_cookie
0x180011efc  lea     r11, [rsp+0C8h+var_8]
0x180011f04  mov     rbx, [r11+18h]
0x180011f08  mov     rsi, [r11+20h]
0x180011f0c  mov     rsp, r11
0x180011f0f  pop     rdi
0x180011f10  retn
```
