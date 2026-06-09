# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,uchar const * &,unsigned __int64 &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&,uchar const * &,unsigned __int64 &)

- ea: `0x18000f09c`
- end: `0x18000f1e4`
- name: `??$_Emplace@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@AEAPEBEAEA_K@?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@_N@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV51@AEAPEBEAEA_K@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64 *, __int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011f20`

## callees

- `0x18000d27c`
- `0x18000e714`
- `0x18000f09c`
- `0x180011100`
- `0x1800168d8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f187`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f187`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring,unsigned char const * &,unsigned __int64 &>(
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
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(&v18);
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
    std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(&v18);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f09c  mov     r11, rsp
0x18000f09f  push    rbx
0x18000f0a0  push    rbp
0x18000f0a1  push    rsi
0x18000f0a2  push    rdi
0x18000f0a3  push    r12
0x18000f0a5  push    r14
0x18000f0a7  push    r15
0x18000f0a9  sub     rsp, 60h
0x18000f0ad  mov     rdi, rdx
0x18000f0b0  mov     r15, rcx
0x18000f0b3  mov     rax, [rsp+98h+arg_30]
0x18000f0bb  mov     [r11-60h], rax
0x18000f0bf  mov     rax, [rsp+98h+arg_28]
0x18000f0c7  mov     [r11-68h], rax
0x18000f0cb  mov     rax, [rsp+98h+arg_20]
0x18000f0d3  mov     [r11-70h], rax
0x18000f0d7  mov     [r11-78h], r9
0x18000f0db  mov     r9, r8
0x18000f0de  mov     r8, [rcx]
0x18000f0e1  mov     rdx, rcx
0x18000f0e4  lea     rcx, [r11-58h]
0x18000f0e8  call    ??$?0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@PEBE_K@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV61@$$QEAPEBE$$QEA_K@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,std::wstring const &,std::wstring &&,uchar const * &&,unsigned __int64 &&)
0x18000f0ed  nop
0x18000f0ee  mov     r12, [rsp+98h+var_50]
0x18000f0f3  mov     rsi, [r15]
0x18000f0f6  mov     rbx, [rsi+8]
0x18000f0fa  xor     ebp, ebp
0x18000f0fc  xor     eax, eax
0x18000f0fe  mov     [rsp+98h+arg_30], rax
0x18000f106  cmp     [rbx+19h], al
0x18000f109  jnz     short loc_18000F143
0x18000f10b  mov     r14, rbx
0x18000f10e  lea     rcx, [rbx+20h]
0x18000f112  lea     rdx, [r12+20h]
0x18000f117  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18000f11c  mov     cl, al
0x18000f11e  test    al, al
0x18000f120  jz      short loc_18000F126
0x18000f122  xor     ebp, ebp
0x18000f124  jmp     short loc_18000F12E
0x18000f126  mov     ebp, 1
0x18000f12b  mov     rsi, rbx
0x18000f12e  lea     rax, [rbx+10h]
0x18000f132  test    cl, cl
0x18000f134  cmovz   rax, rbx
0x18000f138  mov     rbx, [rax]
0x18000f13b  cmp     byte ptr [rbx+19h], 0
0x18000f13f  jz      short loc_18000F10B
0x18000f141  jmp     short loc_18000F146
0x18000f143  mov     r14, rbx
0x18000f146  cmp     byte ptr [rsi+19h], 0
0x18000f14a  jnz     short loc_18000F170
0x18000f14c  lea     rdx, [rsi+20h]
0x18000f150  lea     rcx, [r12+20h]
0x18000f155  call    ??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z; CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)
0x18000f15a  test    al, al
0x18000f15c  jnz     short loc_18000F170
0x18000f15e  mov     [rdi], rsi
0x18000f161  mov     [rdi+8], al
0x18000f164  lea     rcx, [rsp+98h+var_58]
0x18000f169  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)
0x18000f16e  jmp     short loc_18000F1D2
0x18000f170  mov     rax, 0EA0EA0EA0EA0EAh
0x18000f17a  cmp     [r15+8], rax
0x18000f17e  jnz     short loc_18000F18E
0x18000f180  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000f187  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f18e  mov     rbx, [rsp+98h+var_50]
0x18000f193  mov     [rsp+98h+var_50], 0
0x18000f19c  lea     rcx, [rsp+98h+var_58]
0x18000f1a1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)
0x18000f1a6  mov     [rsp+98h+var_48], r14
0x18000f1ab  mov     [rsp+98h+var_40], ebp
0x18000f1af  mov     rax, [rsp+98h+arg_30]
0x18000f1b7  mov     [rsp+98h+var_3C], eax
0x18000f1bb  mov     r8, rbx
0x18000f1be  lea     rdx, [rsp+98h+var_48]
0x18000f1c3  mov     rcx, r15
0x18000f1c6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Insert_node(std::_Tree_id<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *>,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> * const)
0x18000f1cb  mov     [rdi], rax
0x18000f1ce  mov     byte ptr [rdi+8], 1
0x18000f1d2  mov     rax, rdi
0x18000f1d5  add     rsp, 60h
0x18000f1d9  pop     r15
0x18000f1db  pop     r14
0x18000f1dd  pop     r12
0x18000f1df  pop     rdi
0x18000f1e0  pop     rsi
0x18000f1e1  pop     rbp
0x18000f1e2  pop     rbx
0x18000f1e3  retn
```
