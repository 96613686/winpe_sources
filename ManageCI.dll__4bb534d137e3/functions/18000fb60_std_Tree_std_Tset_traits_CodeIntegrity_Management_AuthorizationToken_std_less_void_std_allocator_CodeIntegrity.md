# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Find_lower_bound<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000fb60`
- end: `0x18000fc0c`
- name: `??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `172`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010534`

## callees

- `0x180002a90`
- `0x180008474`
- `0x18000fb60`
- `0x1800159b8`
- `0x180015a6c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Find_lower_bound<std::wstring>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // rdx
  __int64 *v6; // rdi
  __int64 v7; // rax
  int v8; // ebx
  int v9; // eax
  _BYTE v11[32]; // [rsp+20h] [rbp-48h] BYREF

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = CodeIntegrity::Management::detail::SbcpTokenView::name(v6 + 4, v11);
    v8 = std::wstring::compare(v7, a3);
    std::wstring::_Tidy_deallocate(v11);
    if ( v8 >= 0 )
    {
      a2[2] = v6;
      v9 = 1;
    }
    else
    {
      v6 += 2;
      v9 = 0;
    }
    *((_DWORD *)a2 + 2) = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x18000fb60  mov     [rsp+arg_0], rbx
0x18000fb65  push    rbp
0x18000fb66  push    rsi
0x18000fb67  push    rdi
0x18000fb68  sub     rsp, 50h
0x18000fb6c  mov     rax, cs:__security_cookie
0x18000fb73  xor     rax, rsp
0x18000fb76  mov     [rsp+68h+var_28], rax
0x18000fb7b  mov     rax, [rcx]
0x18000fb7e  mov     rsi, rdx
0x18000fb81  mov     rbp, r8
0x18000fb84  mov     rdx, [rax+8]
0x18000fb88  mov     [rsi], rdx
0x18000fb8b  mov     rdi, rdx
0x18000fb8e  mov     qword ptr [rsi+8], 0
0x18000fb96  mov     rax, [rcx]
0x18000fb99  mov     [rsi+10h], rax
0x18000fb9d  cmp     byte ptr [rdx+19h], 0
0x18000fba1  jnz     short loc_18000FBEF
0x18000fba3  lea     rcx, [rdi+20h]
0x18000fba7  mov     [rsi], rdi
0x18000fbaa  lea     rdx, [rsp+68h+var_48]
0x18000fbaf  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x18000fbb4  mov     rdx, rbp
0x18000fbb7  mov     rcx, rax
0x18000fbba  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x18000fbbf  lea     rcx, [rsp+68h+var_48]
0x18000fbc4  mov     ebx, eax
0x18000fbc6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fbcb  shr     ebx, 1Fh
0x18000fbce  test    bl, bl
0x18000fbd0  jz      short loc_18000FBDA
0x18000fbd2  add     rdi, 10h
0x18000fbd6  xor     eax, eax
0x18000fbd8  jmp     short loc_18000FBE3
0x18000fbda  mov     [rsi+10h], rdi
0x18000fbde  mov     eax, 1
0x18000fbe3  mov     [rsi+8], eax
0x18000fbe6  mov     rdi, [rdi]
0x18000fbe9  cmp     byte ptr [rdi+19h], 0
0x18000fbed  jz      short loc_18000FBA3
0x18000fbef  mov     rax, rsi
0x18000fbf2  mov     rcx, [rsp+68h+var_28]
0x18000fbf7  xor     rcx, rsp; StackCookie
0x18000fbfa  call    __security_check_cookie
0x18000fbff  mov     rbx, [rsp+68h+arg_0]
0x18000fc04  add     rsp, 50h
0x18000fc08  pop     rdi
0x18000fc09  pop     rsi
0x18000fc0a  pop     rbp
0x18000fc0b  retn
```
