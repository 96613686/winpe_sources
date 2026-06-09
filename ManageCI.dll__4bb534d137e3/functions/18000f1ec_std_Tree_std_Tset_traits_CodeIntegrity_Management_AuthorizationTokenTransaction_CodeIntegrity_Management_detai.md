# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uchar const *,unsigned __int64>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&,uchar const * &&,unsigned __int64 &&)

- ea: `0x18000f1ec`
- end: `0x18000f334`
- name: `??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@PEBE_K@?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV51@$$QEAPEBE$$QEA_K@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64 *, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011d00`

## callees

- `0x18000d27c`
- `0x18000e714`
- `0x18000f1ec`
- `0x1800110d0`
- `0x1800168d8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f2d7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f2d7`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,unsigned char const *,unsigned __int64>(
        __int64 *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // rbx
  int v12; // ebp
  __int64 v13; // r14
  char v14; // cl
  __int64 *v15; // rax
  __int64 v16; // rbx
  __int64 v18; // [rsp+40h] [rbp-58h] BYREF
  __int64 v19; // [rsp+48h] [rbp-50h]
  __int64 v20; // [rsp+50h] [rbp-48h] BYREF
  int v21; // [rsp+58h] [rbp-40h]
  int v22; // [rsp+5Ch] [rbp-3Ch]

  std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
    &v18,
    (__int64)a1,
    *a1,
    a3,
    a4,
    a5,
    a6,
    a7);
  v9 = v19;
  v10 = *a1;
  v11 = *(_QWORD *)(*a1 + 8);
  v12 = 0;
  if ( *(_BYTE *)(v11 + 25) )
  {
    v13 = *(_QWORD *)(*a1 + 8);
  }
  else
  {
    do
    {
      v13 = v11;
      v14 = CodeIntegrity::Management::detail::SbcpTokenView::operator<(v11 + 32, v9 + 32);
      if ( v14 )
      {
        v12 = 0;
      }
      else
      {
        v12 = 1;
        v10 = v11;
      }
      v15 = (__int64 *)(v11 + 16);
      if ( !v14 )
        v15 = (__int64 *)v11;
      v11 = *v15;
    }
    while ( !*(_BYTE *)(*v15 + 25) );
  }
  if ( *(_BYTE *)(v10 + 25)
    || (unsigned __int8)CodeIntegrity::Management::detail::SbcpTokenView::operator<(v9 + 32, v10 + 32) )
  {
    if ( a1[1] == 0xEA0EA0EA0EA0EALL )
      std::_Xlength_error("map/set too long");
    v16 = v19;
    v19 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(&v18);
    v20 = v13;
    v21 = v12;
    v22 = 0;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(
                      a1,
                      &v20,
                      v16);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(&v18);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f1ec  mov     r11, rsp
0x18000f1ef  push    rbx
0x18000f1f0  push    rbp
0x18000f1f1  push    rsi
0x18000f1f2  push    rdi
0x18000f1f3  push    r12
0x18000f1f5  push    r14
0x18000f1f7  push    r15
0x18000f1f9  sub     rsp, 60h
0x18000f1fd  mov     rdi, rdx
0x18000f200  mov     r15, rcx
0x18000f203  mov     rax, [rsp+98h+arg_30]
0x18000f20b  mov     [r11-60h], rax
0x18000f20f  mov     rax, [rsp+98h+arg_28]
0x18000f217  mov     [r11-68h], rax
0x18000f21b  mov     rax, [rsp+98h+arg_20]
0x18000f223  mov     [r11-70h], rax
0x18000f227  mov     [r11-78h], r9
0x18000f22b  mov     r9, r8
0x18000f22e  mov     r8, [rcx]
0x18000f231  mov     rdx, rcx
0x18000f234  lea     rcx, [r11-58h]
0x18000f238  call    ??$?0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@PEBE_K@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV61@$$QEAPEBE$$QEA_K@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring &&,uchar const * &&,unsigned __int64 &&)
0x18000f23d  nop
0x18000f23e  mov     r12, [rsp+98h+var_50]
0x18000f243  mov     rsi, [r15]
0x18000f246  mov     rbx, [rsi+8]
0x18000f24a  xor     ebp, ebp
0x18000f24c  xor     eax, eax
0x18000f24e  mov     [rsp+98h+arg_30], rax
0x18000f256  cmp     [rbx+19h], al
0x18000f259  jnz     short loc_18000F293
0x18000f25b  mov     r14, rbx
0x18000f25e  lea     rcx, [rbx+20h]
0x18000f262  lea     rdx, [r12+20h]
0x18000f267  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18000f26c  mov     cl, al
0x18000f26e  test    al, al
0x18000f270  jz      short loc_18000F276
0x18000f272  xor     ebp, ebp
0x18000f274  jmp     short loc_18000F27E
0x18000f276  mov     ebp, 1
0x18000f27b  mov     rsi, rbx
0x18000f27e  lea     rax, [rbx+10h]
0x18000f282  test    cl, cl
0x18000f284  cmovz   rax, rbx
0x18000f288  mov     rbx, [rax]
0x18000f28b  cmp     byte ptr [rbx+19h], 0
0x18000f28f  jz      short loc_18000F25B
0x18000f291  jmp     short loc_18000F296
0x18000f293  mov     r14, rbx
0x18000f296  cmp     byte ptr [rsi+19h], 0
0x18000f29a  jnz     short loc_18000F2C0
0x18000f29c  lea     rdx, [rsi+20h]
0x18000f2a0  lea     rcx, [r12+20h]
0x18000f2a5  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18000f2aa  test    al, al
0x18000f2ac  jnz     short loc_18000F2C0
0x18000f2ae  mov     [rdi], rsi
0x18000f2b1  mov     [rdi+8], al
0x18000f2b4  lea     rcx, [rsp+98h+var_58]
0x18000f2b9  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)
0x18000f2be  jmp     short loc_18000F322
0x18000f2c0  mov     rax, 0EA0EA0EA0EA0EAh
0x18000f2ca  cmp     [r15+8], rax
0x18000f2ce  jnz     short loc_18000F2DE
0x18000f2d0  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000f2d7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f2de  mov     rbx, [rsp+98h+var_50]
0x18000f2e3  mov     [rsp+98h+var_50], 0
0x18000f2ec  lea     rcx, [rsp+98h+var_58]
0x18000f2f1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)
0x18000f2f6  mov     [rsp+98h+var_48], r14
0x18000f2fb  mov     [rsp+98h+var_40], ebp
0x18000f2ff  mov     rax, [rsp+98h+arg_30]
0x18000f307  mov     [rsp+98h+var_3C], eax
0x18000f30b  mov     r8, rbx
0x18000f30e  lea     rdx, [rsp+98h+var_48]
0x18000f313  mov     rcx, r15
0x18000f316  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)
0x18000f31b  mov     [rdi], rax
0x18000f31e  mov     byte ptr [rdi+8], 1
0x18000f322  mov     rax, rdi
0x18000f325  add     rsp, 60h
0x18000f329  pop     r15
0x18000f32b  pop     r14
0x18000f32d  pop     r12
0x18000f32f  pop     rdi
0x18000f330  pop     rsi
0x18000f331  pop     rbp
0x18000f332  pop     rbx
0x18000f333  retn
```
