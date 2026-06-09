# CodeIntegrity::Management::Rollback(void)

- ea: `0x180014d20`
- end: `0x180014e79`
- name: `?Rollback@Management@CodeIntegrity@@YAXXZ`
- size: `345`
- prototype: `void __fastcall(CodeIntegrity::Management *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x180011684`
- `0x180014548`
- `0x180014734`
- `0x180014d20`
- `0x180014ee0`
- `0x1800150c8`
- `0x180015dc0`
- `0x180015dec`
- `0x180015e18`
- `0x180015e44`
- `0x180015f44`
- `0x180015f68`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::Rollback(CodeIntegrity::Management *this)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax
  const struct CodeIntegrity::Management::AuthorizationToken *v6; // rbx
  __int64 v7; // rax
  const struct CodeIntegrity::Management::AuthorizationToken *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  CodeIntegrity::Management *v13; // rcx
  wil *v14; // rcx
  int v15; // r15d
  __int64 v16; // rbx
  __int64 v17; // rdi
  int v18; // esi
  int v19; // r14d
  int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v26; // [rsp+40h] [rbp+8h] BYREF

  v1 = **(_QWORD **)qword_180039830;
  v26 = v1;
  try
  {
    while ( !*(_BYTE *)(v1 + 25) )
    {
      v2 = v1 + 32;
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(v1 + 32);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackCiPolicy(
        qword_180039708,
        (const struct CodeIntegrity::Management::SiPolicyView *)(v2 + 16));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v26);
      v1 = v26;
    }
    v3 = **(_QWORD **)qword_180039840;
    v26 = v3;
    while ( !*(_BYTE *)(v3 + 25) )
    {
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::rollback(v3 + 32);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackCiPolicy(
        qword_180039708,
        (const struct CodeIntegrity::Management::SiPolicyView *)(v4 + 16));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v26);
      v3 = v26;
    }
    v5 = **(_QWORD **)qword_180039718;
    v26 = v5;
    while ( !*(_BYTE *)(v5 + 25) )
    {
      v6 = (const struct CodeIntegrity::Management::AuthorizationToken *)(v5 + 32);
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(v5 + 264);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(
        qword_180039708,
        v6);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v26);
      v5 = v26;
    }
    v7 = **(_QWORD **)qword_180039838;
    v26 = v7;
    while ( !*(_BYTE *)(v7 + 25) )
    {
      CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::rollback(v7 + 264);
      CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(
        qword_180039708,
        v8);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(&v26);
      v7 = v26;
    }
    wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(qword_180039708);
    std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(
      v9,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(
      v10,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(
      v11,
      0);
    std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(
      v12,
      0);
    CodeIntegrity::Management::Start(v13);
  }
  catch ( std::exception )
  {
    v15 = (int)qword_180039708;
    v16 = qword_180039840;
    v17 = qword_180039830;
    v18 = qword_180039838;
    v19 = qword_180039718;
    v20 = wil::ResultFromCaughtException(v14);
    CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackFailure(
      v15,
      v20,
      v19,
      v18,
      v17,
      v16);
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x2E7, v21, v22);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0x2E8, v23, v24);
  }
}

```

## disassembly

```asm
0x180014d20  mov     [rsp+arg_8], rbx
0x180014d25  push    rdi
0x180014d26  sub     rsp, 30h
0x180014d2a  mov     rax, cs:qword_180039830
0x180014d31  mov     rax, [rax]
0x180014d34  mov     rax, [rax]
0x180014d37  mov     [rsp+38h+arg_0], rax
0x180014d3c  xor     edi, edi
0x180014d3e  cmp     [rax+19h], dil
0x180014d42  jnz     short loc_180014D71
0x180014d44  lea     rbx, [rax+20h]
0x180014d48  mov     rcx, rbx
0x180014d4b  call    ?rollback@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(void)
0x180014d50  lea     rdx, [rbx+10h]; struct CodeIntegrity::Management::SiPolicyView *
0x180014d54  mov     rcx, cs:qword_180039708; this
0x180014d5b  call    ?InstrumentRollbackCiPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackCiPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x180014d60  lea     rcx, [rsp+38h+arg_0]
0x180014d65  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180014d6a  mov     rax, [rsp+38h+arg_0]
0x180014d6f  jmp     short loc_180014D3E
0x180014d71  mov     rax, cs:qword_180039840
0x180014d78  mov     rax, [rax]
0x180014d7b  mov     rax, [rax]
0x180014d7e  mov     [rsp+38h+arg_0], rax
0x180014d83  cmp     [rax+19h], dil
0x180014d87  jnz     short loc_180014DB3
0x180014d89  lea     rcx, [rax+20h]
0x180014d8d  call    ?rollback@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::rollback(void)
0x180014d92  lea     rdx, [rcx+10h]; struct CodeIntegrity::Management::SiPolicyView *
0x180014d96  mov     rcx, cs:qword_180039708; this
0x180014d9d  call    ?InstrumentRollbackCiPolicy@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVSiPolicyView@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackCiPolicy(CodeIntegrity::Management::SiPolicyView const &)
0x180014da2  lea     rcx, [rsp+38h+arg_0]
0x180014da7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180014dac  mov     rax, [rsp+38h+arg_0]
0x180014db1  jmp     short loc_180014D83
0x180014db3  mov     rax, cs:qword_180039718
0x180014dba  mov     rax, [rax]
0x180014dbd  mov     rax, [rax]
0x180014dc0  mov     [rsp+38h+arg_0], rax
0x180014dc5  cmp     [rax+19h], dil
0x180014dc9  jnz     short loc_180014DFB
0x180014dcb  lea     rbx, [rax+20h]
0x180014dcf  lea     rcx, [rbx+0E8h]
0x180014dd6  call    ?rollback@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UUpsertTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::UpsertTag>::rollback(void)
0x180014ddb  mov     rdx, rbx; struct CodeIntegrity::Management::AuthorizationToken *
0x180014dde  mov     rcx, cs:qword_180039708; this
0x180014de5  call    ?InstrumentRollbackSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)
0x180014dea  lea     rcx, [rsp+38h+arg_0]
0x180014def  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180014df4  mov     rax, [rsp+38h+arg_0]
0x180014df9  jmp     short loc_180014DC5
0x180014dfb  mov     rax, cs:qword_180039838
0x180014e02  mov     rax, [rax]
0x180014e05  mov     rax, [rax]
0x180014e08  mov     [rsp+38h+arg_0], rax
0x180014e0d  cmp     [rax+19h], dil
0x180014e11  jnz     short loc_180014E40
0x180014e13  lea     rdx, [rax+20h]
0x180014e17  lea     rcx, [rdx+0E8h]
0x180014e1e  call    ?rollback@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEBAXXZ; CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::rollback(void)
0x180014e23  mov     rcx, cs:qword_180039708; this
0x180014e2a  call    ?InstrumentRollbackSbcpToken@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXAEBVAuthorizationToken@45@@Z; CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackSbcpToken(CodeIntegrity::Management::AuthorizationToken const &)
0x180014e2f  lea     rcx, [rsp+38h+arg_0]
0x180014e34  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>,std::_Iterator_base0>::operator++(void)
0x180014e39  mov     rax, [rsp+38h+arg_0]
0x180014e3e  jmp     short loc_180014E0D
0x180014e40  mov     rcx, cs:qword_180039708
0x180014e47  call    ?Stop@?$ActivityBase@VManageCIProvider@Telemetry@Management@CodeIntegrity@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CodeIntegrity::Management::Telemetry::ManageCIProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014e4c  xor     edx, edx
0x180014e4e  call    ?reset@?$unique_ptr@V?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>> *)
0x180014e53  xor     edx, edx
0x180014e55  call    ?reset@?$unique_ptr@V?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>> *)
0x180014e5a  xor     edx, edx
0x180014e5c  call    ?reset@?$unique_ptr@V?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::reset(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>> *)
0x180014e61  xor     edx, edx
0x180014e63  call    ?reset@?$unique_ptr@V?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@U?$default_delete@V?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@2@@std@@QEAAXPEAV?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@2@@Z; std::unique_ptr<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::reset(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>> *)
0x180014e68  call    ?Start@Management@CodeIntegrity@@YAXXZ; CodeIntegrity::Management::Start(void)
0x180014e6d  nop
0x180014e6e  mov     rbx, [rsp+38h+arg_8]
0x180014e73  add     rsp, 30h
0x180014e77  pop     rdi
0x180014e78  retn
```
