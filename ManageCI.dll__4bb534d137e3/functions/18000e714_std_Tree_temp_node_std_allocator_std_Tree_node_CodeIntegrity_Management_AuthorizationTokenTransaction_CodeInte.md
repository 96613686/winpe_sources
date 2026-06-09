# std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&,uchar const * &&,unsigned __int64 &&)

- ea: `0x18000e714`
- end: `0x18000e7d0`
- name: `??$?0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@PEBE_K@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV61@$$QEAPEBE$$QEA_K@Z`
- size: `188`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f09c`
- `0x18000f1ec`

## callees

- `0x180004920`
- `0x180004a88`
- `0x18000e714`
- `0x1800103c8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v10; // rax
  int v11; // ecx
  __int64 i; // rcx
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v14 = a3;
  *a1 = a2;
  a1[1] = 0;
  v10 = std::_Allocate<16,std::_Default_allocate_traits>(280);
  a1[1] = v10;
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::construct<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,unsigned char const *,unsigned __int64>(
    v11,
    v10 + 32,
    a4,
    a5,
    a6,
    a7,
    a8);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    a1[1],
    &v14);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    a1[1] + 8LL,
    &v14);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    a1[1] + 16LL,
    &v14);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(a1[1] + i + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000e714  mov     [rsp+arg_8], rbx
0x18000e719  mov     [rsp+arg_10], r8
0x18000e71e  mov     [rsp+arg_0], rcx
0x18000e723  push    rdi
0x18000e724  sub     rsp, 40h
0x18000e728  mov     rbx, r9
0x18000e72b  mov     rdi, rcx
0x18000e72e  mov     [rcx], rdx
0x18000e731  mov     qword ptr [rcx+8], 0
0x18000e739  mov     ecx, 118h
0x18000e73e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e743  mov     [rdi+8], rax
0x18000e747  lea     rdx, [rax+20h]
0x18000e74b  mov     rax, [rsp+48h+arg_38]
0x18000e753  mov     [rsp+48h+var_18], rax
0x18000e758  mov     rax, [rsp+48h+arg_30]
0x18000e760  mov     [rsp+48h+var_20], rax
0x18000e765  mov     rax, [rsp+48h+arg_28]
0x18000e76a  mov     [rsp+48h+var_28], rax
0x18000e76f  mov     r9, [rsp+48h+arg_20]
0x18000e774  mov     r8, rbx
0x18000e777  call    ??$construct@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@PEBE_K@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@QEAV?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV81@$$QEAPEBE$$QEA_K@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::construct<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,uchar const *,unsigned __int64>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring &&,uchar const * &&,unsigned __int64 &&)
0x18000e77c  lea     rdx, [rsp+48h+arg_10]
0x18000e781  mov     rcx, [rdi+8]
0x18000e785  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000e78a  mov     rcx, [rdi+8]
0x18000e78e  add     rcx, 8
0x18000e792  lea     rdx, [rsp+48h+arg_10]
0x18000e797  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000e79c  mov     rcx, [rdi+8]
0x18000e7a0  add     rcx, 10h
0x18000e7a4  lea     rdx, [rsp+48h+arg_10]
0x18000e7a9  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000e7ae  xor     ecx, ecx
0x18000e7b0  mov     rax, [rdi+8]
0x18000e7b4  mov     byte ptr [rax+rcx+18h], 0
0x18000e7b9  inc     rcx
0x18000e7bc  cmp     rcx, 2
0x18000e7c0  jnz     short loc_18000E7B0
0x18000e7c2  mov     rax, rdi
0x18000e7c5  mov     rbx, [rsp+48h+arg_8]
0x18000e7ca  add     rsp, 40h
0x18000e7ce  pop     rdi
0x18000e7cf  retn
```
