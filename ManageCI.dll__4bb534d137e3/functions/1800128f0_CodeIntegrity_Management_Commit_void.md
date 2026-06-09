# CodeIntegrity::Management::Commit(void)

- ea: `0x1800128f0`
- end: `0x180012ae7`
- name: `?Commit@Management@CodeIntegrity@@YAXXZ`
- size: `503`
- prototype: `void __fastcall(CodeIntegrity::Management *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008b70`

## callees

- `0x180002a90`
- `0x18000d470`
- `0x180011684`
- `0x1800128f0`
- `0x180013d14`
- `0x180013f00`
- `0x180014ee0`
- `0x1800150c8`
- `0x18001590c`
- `0x18001595c`
- `0x180015dc0`
- `0x180015dec`
- `0x180015e18`
- `0x180015e44`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x180012a7e`
- `ntdll!NtSetSystemInformation` at `0x180012a7e`

## string_xrefs

- `0x180012a90`: `onecore\base\ci\management\dll\ntextensions.cpp`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Commit(CodeIntegrity::Management *this)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rax
  const struct CodeIntegrity::Management::AuthorizationToken *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  const struct CodeIntegrity::Management::AuthorizationToken *v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  CodeIntegrity::Management *v15; // rcx
  wil *v16; // rcx
  int v17; // r15d
  __int64 v18; // rbx
  __int64 v19; // rdi
  int v20; // esi
  int v21; // r14d
  int v22; // eax
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-48h]
  __int64 v28; // [rsp+30h] [rbp-38h] BYREF
  _OWORD SystemInformation[2]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = **(_QWORD **)qword_180039830;
  v28 = v1;
  try
  {
    while ( !*(_BYTE *)(v1 + 25) )
    {
      v2 = v1 + 32;
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(v1 + 32);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(
        qword_180039708,
        (const struct CodeIntegrity::Management::SiPolicyView *)(v2 + 16));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v28);
      v1 = v28;
    }
    v3 = **(_QWORD **)qword_180039840;
    v28 = v3;
    while ( !*(_BYTE *)(v3 + 25) )
    {
      v4 = v3 + 32;
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(v3 + 32);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(
        qword_180039708,
        (const struct CodeIntegrity::Management::SiPolicyView *)(v4 + 16));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v28);
      v3 = v28;
    }
    v5 = **(_QWORD **)qword_180039718;
    v28 = v5;
    while ( !*(_BYTE *)(v5 + 25) )
    {
      v6 = (const struct CodeIntegrity::Management::AuthorizationToken *)(v5 + 32);
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(v5 + 264);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(
        qword_180039708,
        v6);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v28);
      v5 = v28;
    }
    v7 = qword_180039838;
    v8 = **(_QWORD **)qword_180039838;
    v28 = v8;
    while ( !*(_BYTE *)(v8 + 25) )
    {
      v9 = (const struct CodeIntegrity::Management::AuthorizationToken *)(v8 + 32);
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(v8 + 264);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(
        qword_180039708,
        v9);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v28);
      v8 = v28;
      v7 = qword_180039838;
    }
    if ( *(_QWORD *)(qword_180039830 + 8)
      || *(_QWORD *)(qword_180039840 + 8)
      || *(_QWORD *)(qword_180039718 + 8)
      || *(_QWORD *)(v7 + 8) )
    {
      memset(SystemInformation, 0, sizeof(SystemInformation));
      LODWORD(SystemInformation[0]) = 0x10000000;
      v10 = NtSetSystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\base\\ci\\management\\dll\\ntextensions.cpp",
          (const char *)(unsigned int)v10,
          v27);
    }
    wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(qword_180039708);
    std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(
      v11,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(
      v12,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(
      v13,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(
      v14,
      0);
    CodeIntegrity::Management::Start(v15);
  }
  catch ( std::exception )
  {
    v17 = (int)qword_180039708;
    v18 = qword_180039840;
    v19 = qword_180039830;
    v20 = qword_180039838;
    v21 = qword_180039718;
    v22 = wil::ResultFromCaughtException(v16);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitFailure(
      v17,
      v22,
      v21,
      v20,
      v19,
      v18);
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x2B9, v23, v24);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x2BA, v25, v26);
  }
}

```

## disassembly

```asm
0x1800128f0  mov     [rsp+arg_0], rbx
0x1800128f5  push    rdi
0x1800128f6  sub     rsp, 60h
0x1800128fa  mov     rax, cs:__security_cookie
0x180012901  xor     rax, rsp
0x180012904  mov     [rsp+68h+var_10], rax
0x180012909  mov     rax, cs:qword_180039830
0x180012910  mov     rax, [rax]
0x180012913  mov     rax, [rax]
0x180012916  mov     [rsp+68h+var_38], rax
0x18001291b  xor     edi, edi
0x18001291d  cmp     [rax+19h], dil
0x180012921  jnz     short loc_180012950
0x180012923  lea     rbx, [rax+20h]
0x180012927  mov     rcx, rbx
0x18001292a  call    ?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(void)
0x18001292f  lea     rdx, [rbx+10h]; struct CodeIntegrity::Management::SiPolicyView *
0x180012933  mov     rcx, cs:qword_180039708; this
0x18001293a  call    ?InstrumentCommitCiPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x18001293f  lea     rcx, [rsp+68h+var_38]
0x180012944  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180012949  mov     rax, [rsp+68h+var_38]
0x18001294e  jmp     short loc_18001291D
0x180012950  mov     rax, cs:qword_180039840
0x180012957  mov     rax, [rax]
0x18001295a  mov     rax, [rax]
0x18001295d  mov     [rsp+68h+var_38], rax
0x180012962  cmp     [rax+19h], dil
0x180012966  jnz     short loc_180012995
0x180012968  lea     rbx, [rax+20h]
0x18001296c  mov     rcx, rbx
0x18001296f  call    ?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(void)
0x180012974  lea     rdx, [rbx+10h]; struct CodeIntegrity::Management::SiPolicyView *
0x180012978  mov     rcx, cs:qword_180039708; this
0x18001297f  call    ?InstrumentCommitCiPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitCiPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x180012984  lea     rcx, [rsp+68h+var_38]
0x180012989  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x18001298e  mov     rax, [rsp+68h+var_38]
0x180012993  jmp     short loc_180012962
0x180012995  mov     rax, cs:qword_180039718
0x18001299c  mov     rax, [rax]
0x18001299f  mov     rax, [rax]
0x1800129a2  mov     [rsp+68h+var_38], rax
0x1800129a7  cmp     [rax+19h], dil
0x1800129ab  jnz     short loc_1800129DD
0x1800129ad  lea     rbx, [rax+20h]
0x1800129b1  lea     rcx, [rbx+0E8h]
0x1800129b8  call    ?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::commit(void)
0x1800129bd  mov     rdx, rbx; struct CodeIntegrity::Management::AuthorizationToken *
0x1800129c0  mov     rcx, cs:qword_180039708; this
0x1800129c7  call    ?InstrumentCommitSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)
0x1800129cc  lea     rcx, [rsp+68h+var_38]
0x1800129d1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x1800129d6  mov     rax, [rsp+68h+var_38]
0x1800129db  jmp     short loc_1800129A7
0x1800129dd  mov     rcx, cs:qword_180039838
0x1800129e4  mov     rax, [rcx]
0x1800129e7  mov     rax, [rax]
0x1800129ea  mov     [rsp+68h+var_38], rax
0x1800129ef  cmp     [rax+19h], dil
0x1800129f3  jnz     short loc_180012A2C
0x1800129f5  lea     rbx, [rax+20h]
0x1800129f9  lea     rcx, [rbx+0E8h]
0x180012a00  call    ?commit@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::commit(void)
0x180012a05  mov     rdx, rbx; struct CodeIntegrity::Management::AuthorizationToken *
0x180012a08  mov     rcx, cs:qword_180039708; this
0x180012a0f  call    ?InstrumentCommitSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)
0x180012a14  lea     rcx, [rsp+68h+var_38]
0x180012a19  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180012a1e  mov     rax, [rsp+68h+var_38]
0x180012a23  mov     rcx, cs:qword_180039838
0x180012a2a  jmp     short loc_1800129EF
0x180012a2c  mov     rax, cs:qword_180039830
0x180012a33  cmp     [rax+8], rdi
0x180012a37  ja      short loc_180012A59
0x180012a39  mov     rax, cs:qword_180039840
0x180012a40  cmp     [rax+8], rdi
0x180012a44  ja      short loc_180012A59
0x180012a46  mov     rax, cs:qword_180039718
0x180012a4d  cmp     [rax+8], rdi
0x180012a51  ja      short loc_180012A59
0x180012a53  cmp     [rcx+8], rdi
0x180012a57  jbe     short loc_180012AA1
0x180012a59  xorps   xmm0, xmm0
0x180012a5c  movups  [rsp+68h+SystemInformation], xmm0
0x180012a61  movups  [rsp+68h+var_20], xmm0
0x180012a66  mov     dword ptr [rsp+68h+SystemInformation], 10000000h
0x180012a6e  mov     r8d, 20h ; ' '; SystemInformationLength
0x180012a74  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x180012a79  mov     ecx, 0A4h; SystemInformationClass
0x180012a7e  call    cs:__imp_NtSetSystemInformation
0x180012a84  mov     rcx, [rsp+68h]; this
0x180012a89  test    eax, eax
0x180012a8b  jns     short loc_180012AA1
0x180012a8d  mov     r9d, eax; char *
0x180012a90  lea     r8, aOnecoreBaseCiM_0; "onecore\\base\\ci\\management\\dll\\nte"...
0x180012a97  mov     edx, 8Dh; void *
0x180012a9c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180012aa1  mov     rcx, cs:qword_180039708
0x180012aa8  call    ?Stop@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012aad  xor     edx, edx
0x180012aaf  call    ?reset@?$unique_ptr@V?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>> *)
0x180012ab4  xor     edx, edx
0x180012ab6  call    ?reset@?$unique_ptr@V?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>> *)
0x180012abb  xor     edx, edx
0x180012abd  call    ?reset@?$unique_ptr@V?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>> *)
0x180012ac2  xor     edx, edx
0x180012ac4  call    ?reset@?$unique_ptr@V?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>> *)
0x180012ac9  call    ?Start@Management@CodeIntegrity@@YAXXZ; CodeIntegrity::Management::Start(void)
0x180012ace  nop
0x180012acf  mov     rcx, [rsp+68h+var_10]
0x180012ad4  xor     rcx, rsp; StackCookie
0x180012ad7  call    __security_check_cookie
0x180012adc  mov     rbx, [rsp+68h+arg_0]
0x180012ae1  add     rsp, 60h
0x180012ae5  pop     rdi
0x180012ae6  retn
```
