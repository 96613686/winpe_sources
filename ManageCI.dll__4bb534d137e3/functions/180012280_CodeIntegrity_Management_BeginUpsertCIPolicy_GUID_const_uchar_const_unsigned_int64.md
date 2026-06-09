# CodeIntegrity::Management::BeginUpsertCIPolicy(_GUID const *,uchar const *,unsigned __int64)

- ea: `0x180012280`
- end: `0x1800123d0`
- name: `?BeginUpsertCIPolicy@Management@CodeIntegrity@@YAXPEBU_GUID@@PEBE_K@Z`
- size: `336`
- prototype: `void __fastcall(CodeIntegrity::Management *this, struct _GUID *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008b30`

## callees

- `0x180002a90`
- `0x180005600`
- `0x18000d470`
- `0x180010500`
- `0x180011308`
- `0x1800114f8`
- `0x180012280`
- `0x1800137fc`
- `0x1800154c0`
- `0x18001758c`
- `0x180021bd8`

## string_xrefs

- `0x18001234c`: `onecore\base\ci\management\dll\manageci.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::BeginUpsertCIPolicy(
        CodeIntegrity::Management *this,
        struct _GUID *a2,
        const unsigned __int8 *a3)
{
  ULONG v3; // esi
  unsigned int v6; // r8d
  __int64 v7; // rax
  int updated; // eax
  wil *v9; // rcx
  CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction *v10; // rbx
  int v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14[2]; // [rsp+20h] [rbp-E8h] BYREF
  int *v15; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+30h] [rbp-D8h] BYREF
  char v17; // [rsp+38h] [rbp-D0h]
  __int64 v18[11]; // [rsp+40h] [rbp-C8h] BYREF
  char v19; // [rsp+9Dh] [rbp-6Bh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v3 = (unsigned int)a3;
  *(_QWORD *)v14 = 0;
  try
  {
    CodeIntegrity::Management::SiPolicyView::SiPolicyView(
      (CodeIntegrity::Management::SiPolicyView *)v18,
      (const unsigned __int8 *)a2,
      (unsigned __int64)a3);
    if ( v19 )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x126, v6, (const char *)0x80070005LL, v14[0]);
    v7 = *(_QWORD *)v18[0] - *(_QWORD *)this;
    if ( *(_QWORD *)v18[0] == *(_QWORD *)this )
      v7 = *(_QWORD *)(v18[0] + 8) - *((_QWORD *)this + 1);
    if ( v7 )
      wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x12B, v6, (const char *)0x80004005LL, v14[0]);
    v15 = v14;
    v16 = 0;
    v17 = 1;
    updated = SIPolicyPmUpdatePolicyBegin(v18[0], a2, v3, &v16);
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\base\\ci\\management\\dll\\manageci.cpp",
        (const char *)(unsigned int)updated,
        v14[0]);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v15);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddCIPolicy(
      qword_180039708,
      (const struct CodeIntegrity::Management::SiPolicyView *)v18);
    ((void (__fastcall *)(__int64, int **, int *, __int64 *))std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView>)(
      qword_180039830,
      &v15,
      v14,
      v18);
  }
  catch ( std::exception )
  {
    v10 = qword_180039708;
    v11 = wil::ResultFromCaughtException(v9);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddCIPolicy(v10, v11);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x13E, v12, v13);
  }
  CodeIntegrity::Management::SiPolicyView::SiPolicyView(
    (CodeIntegrity::Management::SiPolicyView *)v18,
    (const unsigned __int8 *)a2,
    (unsigned __int64)a3);
  if ( v19 )
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x126, v6, (const char *)0x80070005LL, v14[0]);
}

```

## disassembly

```asm
0x180012280  mov     [rsp+arg_0], rbx
0x180012285  mov     [rsp+arg_18], rsi
0x18001228a  push    rdi
0x18001228b  sub     rsp, 100h
0x180012292  mov     rax, cs:__security_cookie
0x180012299  xor     rax, rsp
0x18001229c  mov     [rsp+108h+var_18], rax
0x1800122a4  mov     rsi, r8
0x1800122a7  mov     rdi, rdx
0x1800122aa  mov     rbx, rcx
0x1800122ad  mov     qword ptr [rsp+108h+var_E8], 0; int
0x1800122b6  lea     rcx, [rsp+108h+var_C8]; this
0x1800122bb  call    ??0SiPolicyView@Management@CodeIntegrity@@QEAA@PEBE_K@Z; CodeIntegrity::Management::SiPolicyView::SiPolicyView(uchar const *,unsigned __int64)
0x1800122c0  nop
0x1800122c1  cmp     [rsp+108h+var_6B], 0
0x1800122c9  jz      short loc_1800122E3
0x1800122cb  mov     rcx, [rsp+108h]; this
0x1800122d3  mov     edx, 126h; void *
0x1800122d8  mov     r9d, 80070005h; char *
0x1800122de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800122e3  mov     rcx, [rsp+108h+var_C8]
0x1800122e8  mov     rax, [rcx]
0x1800122eb  sub     rax, [rbx]
0x1800122ee  jnz     short loc_1800122F8
0x1800122f0  mov     rax, [rcx+8]
0x1800122f4  sub     rax, [rbx+8]
0x1800122f8  test    rax, rax
0x1800122fb  jz      short loc_180012315
0x1800122fd  mov     rcx, [rsp+108h]; this
0x180012305  mov     edx, 12Bh; void *
0x18001230a  mov     r9d, 80004005h; char *
0x180012310  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012315  lea     rax, [rsp+108h+var_E8]
0x18001231a  mov     [rsp+108h+var_E0], rax
0x18001231f  mov     [rsp+108h+var_D8], 0
0x180012328  mov     [rsp+108h+var_D0], 1
0x18001232d  mov     r8d, esi
0x180012330  lea     r9, [rsp+108h+var_D8]
0x180012335  mov     rdx, rdi
0x180012338  call    SIPolicyPmUpdatePolicyBegin
0x18001233d  mov     rcx, [rsp+108h]; this
0x180012345  test    eax, eax
0x180012347  jns     short loc_18001235E
0x180012349  mov     r9d, eax; char *
0x18001234c  lea     r8, aOnecoreBaseCiM_1; "onecore\\base\\ci\\management\\dll\\man"...
0x180012353  mov     edx, 132h; void *
0x180012358  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001235e  lea     rcx, [rsp+108h+var_E0]
0x180012363  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180012368  lea     rdx, [rsp+108h+var_C8]; struct CodeIntegrity::Management::SiPolicyView *
0x18001236d  mov     rcx, cs:qword_180039708; this
0x180012374  call    ?InstrumentAddCIPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentAddCIPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x180012379  lea     r9, [rsp+108h+var_C8]
0x18001237e  lea     r8, [rsp+108h+var_E8]
0x180012383  lea     rdx, [rsp+108h+var_E0]
0x180012388  mov     rcx, cs:qword_180039830
0x18001238f  call    ??$emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@VSiPolicyView@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAVSiPolicyView@Management@CodeIntegrity@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView &&)
0x180012394  nop
0x180012395  lea     rcx, [rsp+108h+var_C8]; this
0x18001239a  call    ??1SiPolicyView@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::SiPolicyView::~SiPolicyView(void)
0x18001239f  nop
0x1800123a0  lea     rcx, [rsp+108h+var_E8]
0x1800123a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800123aa  nop
0x1800123ab  mov     rcx, [rsp+108h+var_18]
0x1800123b3  xor     rcx, rsp; StackCookie
0x1800123b6  call    __security_check_cookie
0x1800123bb  lea     r11, [rsp+108h+var_8]
0x1800123c3  mov     rbx, [r11+10h]
0x1800123c7  mov     rsi, [r11+28h]
0x1800123cb  mov     rsp, r11
0x1800123ce  pop     rdi
0x1800123cf  retn
```
