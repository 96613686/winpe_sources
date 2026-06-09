# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &)

- ea: `0x18000f33c`
- end: `0x18000f4b0`
- name: `??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@Management@CodeIntegrity@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c00`

## callees

- `0x180003864`
- `0x180004920`
- `0x180004a88`
- `0x18000d27c`
- `0x18000f33c`
- `0x180010434`
- `0x180011130`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f45f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f45f`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v8; // r13
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rbx
  int v12; // r15d
  const void **v13; // r14
  __int64 v14; // r13
  __int64 *v16; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v17; // [rsp+28h] [rbp-8h]
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF
  _QWORD *v19; // [rsp+80h] [rbp+50h]

  v18 = *a1;
  v16 = a1;
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(0xE0u);
  v19 = v8;
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::construct<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &>(
    v9,
    v8 + 4,
    a3,
    a4,
    v16,
    v8);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    v8,
    &v18);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    v8 + 1,
    &v18);
  std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
    v8 + 2,
    &v18);
  *((_WORD *)v8 + 12) = 0;
  v10 = *a1;
  v11 = *(_QWORD *)(*a1 + 8);
  v12 = 0;
  v18 = 0;
  v13 = (const void **)(v8 + 6);
  if ( !*(_BYTE *)(v11 + 25) )
  {
    do
    {
      v14 = v11;
      if ( memcmp_0(*(const void **)(v11 + 48), *v13, 0x10u) >= 0 )
      {
        v12 = 1;
        v10 = v11;
      }
      else
      {
        v12 = 0;
        v11 += 16;
      }
      v11 = *(_QWORD *)v11;
    }
    while ( !*(_BYTE *)(v11 + 25) );
    v11 = v14;
    v8 = v19;
  }
  if ( *(_BYTE *)(v10 + 25) || memcmp_0(*v13, *(const void **)(v10 + 48), 0x10u) < 0 )
  {
    if ( a1[1] == 0x124924924924924LL )
      std::_Xlength_error("map/set too long");
    v17 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(&v16);
    v16 = (__int64 *)v11;
    v17 = __PAIR64__(v18, v12);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(
                      a1,
                      &v16,
                      v8);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(&v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f33c  mov     [rsp-38h+arg_8], rbx
0x18000f341  push    rbp
0x18000f342  push    rsi
0x18000f343  push    rdi
0x18000f344  push    r12
0x18000f346  push    r13
0x18000f348  push    r14
0x18000f34a  push    r15
0x18000f34c  mov     rbp, rsp
0x18000f34f  sub     rsp, 30h
0x18000f353  mov     rbx, r9
0x18000f356  mov     rdi, r8
0x18000f359  mov     rsi, rdx
0x18000f35c  mov     r12, rcx
0x18000f35f  mov     rax, [rcx]
0x18000f362  mov     [rbp+arg_0], rax
0x18000f366  mov     [rbp+var_10], rcx
0x18000f36a  mov     [rbp+var_8], 0
0x18000f372  mov     ecx, 0E0h
0x18000f377  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000f37c  mov     r13, rax
0x18000f37f  mov     [rbp+arg_10], rax
0x18000f383  mov     [rbp+var_8], rax
0x18000f387  lea     rdx, [rax+20h]
0x18000f38b  mov     r9, rbx
0x18000f38e  mov     r8, rdi
0x18000f391  call    ??$construct@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@23@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@QEAV?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVSiPolicyView@45@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::construct<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &>(std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,CodeIntegrity::Management::SiPolicyView const &)
0x18000f396  lea     rdx, [rbp+arg_0]
0x18000f39a  mov     rcx, r13
0x18000f39d  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000f3a2  lea     rcx, [r13+8]
0x18000f3a6  lea     rdx, [rbp+arg_0]
0x18000f3aa  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000f3af  lea     rcx, [r13+10h]
0x18000f3b3  lea     rdx, [rbp+arg_0]
0x18000f3b7  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18000f3bc  xor     ecx, ecx
0x18000f3be  mov     [r13+18h], cx
0x18000f3c3  mov     rdi, [r12]
0x18000f3c7  mov     rbx, [rdi+8]
0x18000f3cb  mov     r15d, ecx
0x18000f3ce  xor     eax, eax
0x18000f3d0  mov     [rbp+arg_0], rax
0x18000f3d4  lea     r14, [r13+30h]
0x18000f3d8  cmp     [rbx+19h], cl
0x18000f3db  jnz     short loc_18000F419
0x18000f3dd  mov     r13, rbx
0x18000f3e0  mov     r8d, 10h; Size
0x18000f3e6  mov     rdx, [r14]; Buf2
0x18000f3e9  mov     rcx, [rbx+30h]; Buf1
0x18000f3ed  call    memcmp_0
0x18000f3f2  xor     ecx, ecx
0x18000f3f4  test    eax, eax
0x18000f3f6  jns     short loc_18000F401
0x18000f3f8  mov     r15d, ecx
0x18000f3fb  add     rbx, 10h
0x18000f3ff  jmp     short loc_18000F40A
0x18000f401  mov     r15d, 1
0x18000f407  mov     rdi, rbx
0x18000f40a  mov     rbx, [rbx]
0x18000f40d  cmp     [rbx+19h], cl
0x18000f410  jz      short loc_18000F3DD
0x18000f412  mov     rbx, r13
0x18000f415  mov     r13, [rbp+arg_10]
0x18000f419  cmp     [rdi+19h], cl
0x18000f41c  jnz     short loc_18000F447
0x18000f41e  mov     r8d, 10h; Size
0x18000f424  mov     rdx, [rdi+30h]; Buf2
0x18000f428  mov     rcx, [r14]; Buf1
0x18000f42b  call    memcmp_0
0x18000f430  xor     ecx, ecx
0x18000f432  test    eax, eax
0x18000f434  js      short loc_18000F447
0x18000f436  mov     [rsi], rdi
0x18000f439  mov     [rsi+8], cl
0x18000f43c  lea     rcx, [rbp+var_10]
0x18000f440  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)
0x18000f445  jmp     short loc_18000F498
0x18000f447  mov     rax, 124924924924924h
0x18000f451  cmp     [r12+8], rax
0x18000f456  jnz     short loc_18000F466
0x18000f458  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000f45f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f466  mov     [rbp+var_8], rcx
0x18000f46a  lea     rcx, [rbp+var_10]
0x18000f46e  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)
0x18000f473  mov     [rbp+var_10], rbx
0x18000f477  mov     dword ptr [rbp+var_8], r15d
0x18000f47b  mov     rax, [rbp+arg_0]
0x18000f47f  mov     dword ptr [rbp+var_8+4], eax
0x18000f482  mov     r8, r13
0x18000f485  lea     rdx, [rbp+var_10]
0x18000f489  mov     rcx, r12
0x18000f48c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)
0x18000f491  mov     [rsi], rax
0x18000f494  mov     byte ptr [rsi+8], 1
0x18000f498  mov     rax, rsi
0x18000f49b  mov     rbx, [rsp+30h+arg_8]
0x18000f4a0  add     rsp, 30h
0x18000f4a4  pop     r15
0x18000f4a6  pop     r14
0x18000f4a8  pop     r13
0x18000f4aa  pop     r12
0x18000f4ac  pop     rdi
0x18000f4ad  pop     rsi
0x18000f4ae  pop     rbp
0x18000f4af  retn
```
