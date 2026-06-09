# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>>,0>>::_Emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>> &&)

- ea: `0x18001a094`
- end: `0x18001a19e`
- name: `??$_Emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@1@@Z`
- size: `266`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c714`

## callees

- `0x180004920`
- `0x180004a88`
- `0x18000d27c`
- `0x18000fadc`
- `0x18000fd38`
- `0x18001a094`
- `0x18001b240`
- `0x18001c014`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a0f7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a0f7`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Emplace<std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rax
  __int128 v9; // xmm6
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rbx
  __int64 v13; // rcx
  _OWORD v15[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+90h] [rbp+38h] BYREF

  v8 = std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Find_lower_bound<std::wstring>(
         a1,
         v15);
  v9 = *(_OWORD *)v8;
  v10 = *(_QWORD *)(v8 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v11,
                          v10,
                          a3) )
  {
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x333333333333333LL )
      std::_Xlength_error("map/set too long");
    v16 = *a1;
    v15[0] = (unsigned __int64)a1;
    v12 = std::_Allocate<16,std::_Default_allocate_traits>(0x50u);
    *((_QWORD *)&v15[0] + 1) = v12;
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>::construct<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken>>(
      v13,
      v12 + 4,
      a3,
      a4);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12,
      &v16);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12 + 1,
      &v16);
    std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(
      v12 + 2,
      &v16);
    *((_WORD *)v12 + 12) = 0;
    *((_QWORD *)&v15[0] + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(v15);
    v15[0] = v9;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(
                      a1,
                      v15,
                      v12);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18001a094  push    rbp
0x18001a096  push    rbx
0x18001a097  push    rsi
0x18001a098  push    rdi
0x18001a099  push    r14
0x18001a09b  push    r15
0x18001a09d  mov     rbp, rsp
0x18001a0a0  sub     rsp, 58h
0x18001a0a4  movaps  [rsp+58h+var_18], xmm6
0x18001a0a9  mov     r15, r9
0x18001a0ac  mov     r14, r8
0x18001a0af  mov     rdi, rdx
0x18001a0b2  mov     rsi, rcx
0x18001a0b5  lea     rdx, [rbp+var_38]
0x18001a0b9  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001a0be  movups  xmm6, xmmword ptr [rax]
0x18001a0c1  mov     rbx, [rax+10h]
0x18001a0c5  mov     r8, r14
0x18001a0c8  mov     rdx, rbx
0x18001a0cb  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *> * const,std::wstring const &)
0x18001a0d0  test    al, al
0x18001a0d2  jz      short loc_18001A0E0
0x18001a0d4  mov     [rdi], rbx
0x18001a0d7  mov     byte ptr [rdi+8], 0
0x18001a0db  jmp     loc_18001A189
0x18001a0e0  mov     rax, 333333333333333h
0x18001a0ea  cmp     [rsi+8], rax
0x18001a0ee  jnz     short loc_18001A0FE
0x18001a0f0  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001a0f7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001a0fe  mov     rax, [rsi]
0x18001a101  mov     [rbp+arg_0], rax
0x18001a105  mov     qword ptr [rbp+var_38], rsi
0x18001a109  mov     qword ptr [rbp+var_38+8], 0
0x18001a111  mov     ecx, 50h ; 'P'
0x18001a116  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001a11b  mov     rbx, rax
0x18001a11e  mov     qword ptr [rbp+var_38+8], rax
0x18001a122  lea     rdx, [rax+20h]
0x18001a126  mov     r9, r15
0x18001a129  mov     r8, r14
0x18001a12c  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>::construct<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>> &,std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>> * const,std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken> &&)
0x18001a131  lea     rdx, [rbp+arg_0]
0x18001a135  mov     rcx, rbx
0x18001a138  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a13d  lea     rcx, [rbx+8]
0x18001a141  lea     rdx, [rbp+arg_0]
0x18001a145  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a14a  lea     rcx, [rbx+10h]
0x18001a14e  lea     rdx, [rbp+arg_0]
0x18001a152  call    ??$_Construct_in_place@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &>(std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * &)
0x18001a157  mov     word ptr [rbx+18h], 0
0x18001a15d  mov     qword ptr [rbp+var_38+8], 0
0x18001a165  lea     rcx, [rbp+var_38]
0x18001a169  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(void)
0x18001a16e  movdqu  [rbp+var_38], xmm6
0x18001a173  mov     r8, rbx
0x18001a176  lea     rdx, [rbp+var_38]
0x18001a17a  mov     rcx, rsi
0x18001a17d  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)
0x18001a182  mov     [rdi], rax
0x18001a185  mov     byte ptr [rdi+8], 1
0x18001a189  mov     rax, rdi
0x18001a18c  movaps  xmm6, [rsp+58h+var_18]
0x18001a191  add     rsp, 58h
0x18001a195  pop     r15
0x18001a197  pop     r14
0x18001a199  pop     rdi
0x18001a19a  pop     rsi
0x18001a19b  pop     rbx
0x18001a19c  pop     rbp
0x18001a19d  retn
```
