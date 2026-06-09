# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<void>,0>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010534`
- end: `0x1800105c1`
- name: `??$find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@$0A@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `141`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011d00`
- `0x180012e20`
- `0x180013660`

## callees

- `0x180002a90`
- `0x180008474`
- `0x18000fb60`
- `0x180010534`
- `0x1800159b8`
- `0x180015a6c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]

  std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Find_lower_bound<std::wstring>(
    (__int64)a1,
    v10,
    a3);
  v6 = v11;
  if ( *(_BYTE *)(v11 + 25)
    || (v7 = CodeIntegrity::Management::detail::SbcpTokenView::name(v11 + 32, v10),
        v8 = (unsigned int)std::wstring::compare(a3, v7) >> 31,
        std::wstring::_Tidy_deallocate(v10),
        (_BYTE)v8) )
  {
    v6 = *a1;
  }
  *a2 = v6;
  return a2;
}

```

## disassembly

```asm
0x180010534  mov     [rsp+arg_18], rbx
0x180010539  push    rsi
0x18001053a  push    rdi
0x18001053b  push    r14
0x18001053d  sub     rsp, 50h
0x180010541  mov     rax, cs:__security_cookie
0x180010548  xor     rax, rsp
0x18001054b  mov     [rsp+68h+var_28], rax
0x180010550  mov     rsi, rdx
0x180010553  mov     rbx, r8
0x180010556  lea     rdx, [rsp+68h+var_48]
0x18001055b  mov     r14, rcx
0x18001055e  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180010563  mov     rdi, [rsp+68h+var_38]
0x180010568  cmp     byte ptr [rdi+19h], 0
0x18001056c  jnz     short loc_18001059A
0x18001056e  lea     rcx, [rdi+20h]
0x180010572  lea     rdx, [rsp+68h+var_48]
0x180010577  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x18001057c  mov     rdx, rax
0x18001057f  mov     rcx, rbx
0x180010582  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180010587  mov     ebx, eax
0x180010589  lea     rcx, [rsp+68h+var_48]
0x18001058e  shr     ebx, 1Fh
0x180010591  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010596  test    bl, bl
0x180010598  jz      short loc_18001059D
0x18001059a  mov     rdi, [r14]
0x18001059d  mov     [rsi], rdi
0x1800105a0  mov     rax, rsi
0x1800105a3  mov     rcx, [rsp+68h+var_28]
0x1800105a8  xor     rcx, rsp; StackCookie
0x1800105ab  call    __security_check_cookie
0x1800105b0  mov     rbx, [rsp+68h+arg_18]
0x1800105b8  add     rsp, 50h
0x1800105bc  pop     r14
0x1800105be  pop     rdi
0x1800105bf  pop     rsi
0x1800105c0  retn
```
