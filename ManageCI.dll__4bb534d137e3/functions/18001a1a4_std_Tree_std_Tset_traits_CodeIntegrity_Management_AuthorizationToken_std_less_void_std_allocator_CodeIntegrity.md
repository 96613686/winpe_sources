# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Emplace<CodeIntegrity::Management::AuthorizationToken>(CodeIntegrity::Management::AuthorizationToken &&)

- ea: `0x18001a1a4`
- end: `0x18001a2f9`
- name: `??$_Emplace@VAuthorizationToken@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@_N@1@$$QEAVAuthorizationToken@Management@CodeIntegrity@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c714`

## callees

- `0x180004920`
- `0x180004a88`
- `0x18000d27c`
- `0x1800168d8`
- `0x18001a1a4`
- `0x18001b398`
- `0x18001c044`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a24c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a24c`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Emplace<CodeIntegrity::Management::AuthorizationToken>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rbx
  int v8; // r15d
  _QWORD *v9; // r13
  char v10; // cl
  __int64 *v11; // rax
  __int64 *v12; // rbx
  __int64 v13; // rcx
  _QWORD *v15; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-8h]
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+80h] [rbp+50h]

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v8 = 0;
  v18 = 0;
  if ( *((_BYTE *)v7 + 25) )
  {
    v9 = v7;
  }
  else
  {
    do
    {
      v9 = v7;
      v10 = CodeIntegrity::Management::detail::SbcpTokenView::operator<(v7 + 4, a3);
      if ( v10 )
      {
        v8 = 0;
      }
      else
      {
        v8 = 1;
        v6 = v7;
      }
      v11 = v7 + 2;
      if ( !v10 )
        v11 = v7;
      v7 = (__int64 *)*v11;
    }
    while ( !*(_BYTE *)(*v11 + 25) );
  }
  if ( *((_BYTE *)v6 + 25) || (unsigned __int8)CodeIntegrity::Management::detail::SbcpTokenView::operator<(a3, v6 + 4) )
  {
    if ( a1[1] == 0xF83E0F83E0F83ELL )
      std::_Xlength_error("map/set too long");
    v17 = *a1;
    v15 = a1;
    v12 = std::_Allocate<16,std::_Default_allocate_traits>(0x108u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::construct<CodeIntegrity::Management::AuthorizationToken,CodeIntegrity::Management::AuthorizationToken>(
      v13,
      v12 + 4,
      a3);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12,
      &v17);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12 + 1,
      &v17);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12 + 2,
      &v17);
    *((_WORD *)v12 + 12) = 0;
    v16 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(&v15);
    v15 = v9;
    v16 = __PAIR64__(v18, v8);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(
                      a1,
                      &v15,
                      v12);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18001a1a4  mov     [rsp-38h+arg_8], rbx
0x18001a1a9  push    rbp
0x18001a1aa  push    rsi
0x18001a1ab  push    rdi
0x18001a1ac  push    r12
0x18001a1ae  push    r13
0x18001a1b0  push    r14
0x18001a1b2  push    r15
0x18001a1b4  mov     rbp, rsp
0x18001a1b7  sub     rsp, 30h
0x18001a1bb  mov     r12, r8
0x18001a1be  mov     rsi, rdx
0x18001a1c1  mov     r14, rcx
0x18001a1c4  mov     rdi, [rcx]
0x18001a1c7  mov     rbx, [rdi+8]
0x18001a1cb  xor     r15d, r15d
0x18001a1ce  xor     eax, eax
0x18001a1d0  mov     [rbp+arg_10], rax
0x18001a1d4  cmp     [rbx+19h], al
0x18001a1d7  jnz     short loc_18001A211
0x18001a1d9  mov     r13, rbx
0x18001a1dc  lea     rcx, [rbx+20h]
0x18001a1e0  mov     rdx, r12
0x18001a1e3  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18001a1e8  mov     cl, al
0x18001a1ea  test    al, al
0x18001a1ec  jz      short loc_18001A1F3
0x18001a1ee  xor     r15d, r15d
0x18001a1f1  jmp     short loc_18001A1FC
0x18001a1f3  mov     r15d, 1
0x18001a1f9  mov     rdi, rbx
0x18001a1fc  lea     rax, [rbx+10h]
0x18001a200  test    cl, cl
0x18001a202  cmovz   rax, rbx
0x18001a206  mov     rbx, [rax]
0x18001a209  cmp     byte ptr [rbx+19h], 0
0x18001a20d  jz      short loc_18001A1D9
0x18001a20f  jmp     short loc_18001A214
0x18001a211  mov     r13, rbx
0x18001a214  cmp     byte ptr [rdi+19h], 0
0x18001a218  jnz     short loc_18001A235
0x18001a21a  lea     rdx, [rdi+20h]
0x18001a21e  mov     rcx, r12
0x18001a221  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18001a226  test    al, al
0x18001a228  jnz     short loc_18001A235
0x18001a22a  mov     [rsi], rdi
0x18001a22d  mov     [rsi+8], al
0x18001a230  jmp     loc_18001A2E1
0x18001a235  mov     rax, 0F83E0F83E0F83Eh
0x18001a23f  cmp     [r14+8], rax
0x18001a243  jnz     short loc_18001A253
0x18001a245  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001a24c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001a253  mov     rax, [r14]
0x18001a256  mov     [rbp+arg_0], rax
0x18001a25a  mov     [rbp+var_10], r14
0x18001a25e  mov     [rbp+var_8], 0
0x18001a266  mov     ecx, 108h
0x18001a26b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001a270  mov     rbx, rax
0x18001a273  mov     [rbp+var_8], rax
0x18001a277  lea     rdx, [rax+20h]
0x18001a27b  mov     r8, r12
0x18001a27e  call    ??$construct@VAuthorizationToken@Management@CodeIntegrity@@V123@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@QEAVAuthorizationToken@Management@CodeIntegrity@@$$QEAV345@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::construct<CodeIntegrity::Management::AuthorizationToken,CodeIntegrity::Management::AuthorizationToken>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>> &,CodeIntegrity::Management::AuthorizationToken * const,CodeIntegrity::Management::AuthorizationToken &&)
0x18001a283  lea     rdx, [rbp+arg_0]
0x18001a287  mov     rcx, rbx
0x18001a28a  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a28f  lea     rcx, [rbx+8]
0x18001a293  lea     rdx, [rbp+arg_0]
0x18001a297  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a29c  lea     rcx, [rbx+10h]
0x18001a2a0  lea     rdx, [rbp+arg_0]
0x18001a2a4  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a2a9  xor     ecx, ecx
0x18001a2ab  mov     [rbx+18h], cx
0x18001a2af  mov     [rbp+var_8], rcx
0x18001a2b3  lea     rcx, [rbp+var_10]
0x18001a2b7  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(void)
0x18001a2bc  mov     [rbp+var_10], r13
0x18001a2c0  mov     dword ptr [rbp+var_8], r15d
0x18001a2c4  mov     rax, [rbp+arg_10]
0x18001a2c8  mov     dword ptr [rbp+var_8+4], eax
0x18001a2cb  mov     r8, rbx
0x18001a2ce  lea     rdx, [rbp+var_10]
0x18001a2d2  mov     rcx, r14
0x18001a2d5  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)
0x18001a2da  mov     [rsi], rax
0x18001a2dd  mov     byte ptr [rsi+8], 1
0x18001a2e1  mov     rax, rsi
0x18001a2e4  mov     rbx, [rsp+30h+arg_8]
0x18001a2e9  add     rsp, 30h
0x18001a2ed  pop     r15
0x18001a2ef  pop     r14
0x18001a2f1  pop     r13
0x18001a2f3  pop     r12
0x18001a2f5  pop     rdi
0x18001a2f6  pop     rsi
0x18001a2f7  pop     rbp
0x18001a2f8  retn
```
