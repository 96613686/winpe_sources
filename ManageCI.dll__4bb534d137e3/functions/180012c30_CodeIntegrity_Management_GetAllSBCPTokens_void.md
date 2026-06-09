# CodeIntegrity::Management::GetAllSBCPTokens(void)

- ea: `0x180012c30`
- end: `0x180012d08`
- name: `?GetAllSBCPTokens@Management@CodeIntegrity@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `216`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008cc0`

## callees

- `0x18000f768`
- `0x1800104b4`
- `0x180010cdc`
- `0x180012c30`
- `0x1800159fc`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::Management::GetAllSBCPTokens(_QWORD *a1)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  __int64 j; // rcx
  _QWORD *result; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 i; // rax
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+18h] BYREF

  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
    (__int64 *)qword_180039710,
    &v13,
    (__int64)qword_180039720);
  std::vector<_GUID>::vector<_GUID>(a1);
  j = qword_180039710;
  if ( v13 == *(_QWORD *)qword_180039710 )
    return a1;
  v6 = **(_QWORD **)(v13 + 64);
  try
  {
    while ( !*(_BYTE *)(v6 + 25) )
    {
      v7 = v6 + 88;
      v8 = a1[1];
      if ( v8 == a1[2] )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v8, v7);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
          j,
          v8,
          v7);
        a1[1] += 32LL;
      }
      j = *(_QWORD *)(v6 + 16);
      if ( *(_BYTE *)(j + 25) )
      {
        for ( i = *(_QWORD *)(v6 + 8); !*(_BYTE *)(i + 25) && v6 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v6 = i;
        v6 = i;
      }
      else
      {
        v6 = *(_QWORD *)(v6 + 16);
        for ( j = *(_QWORD *)j; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
          v6 = j;
      }
    }
    result = a1;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0xD0, v2, v3);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0xD1, v10, v11);
  }
  while ( !*(_BYTE *)(v6 + 25) )
  {
    v7 = v6 + 88;
    v8 = a1[1];
    if ( v8 == a1[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, v8, v7);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
        j,
        v8,
        v7);
      a1[1] += 32LL;
    }
    j = *(_QWORD *)(v6 + 16);
    if ( *(_BYTE *)(j + 25) )
    {
      for ( i = *(_QWORD *)(v6 + 8); !*(_BYTE *)(i + 25) && v6 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v6 = i;
      v6 = i;
    }
    else
    {
      v6 = *(_QWORD *)(v6 + 16);
      for ( j = *(_QWORD *)j; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
        v6 = j;
    }
  }
}

```

## disassembly

```asm
0x180012c30  mov     rax, rsp
0x180012c33  mov     [rax+20h], rbx
0x180012c37  mov     [rax+8], rcx
0x180012c3b  push    rdi
0x180012c3c  sub     rsp, 20h
0x180012c40  mov     rdi, rcx
0x180012c43  mov     ebx, 1
0x180012c48  mov     [rax+10h], ebx
0x180012c4b  lea     r8, qword_180039720
0x180012c52  lea     rdx, [rax+18h]
0x180012c56  mov     rcx, cs:qword_180039710
0x180012c5d  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x180012c62  mov     rcx, rdi
0x180012c65  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180012c6a  nop
0x180012c6b  mov     [rsp+28h+arg_8], ebx
0x180012c6f  mov     rax, [rsp+28h+arg_10]
0x180012c74  mov     rcx, cs:qword_180039710
0x180012c7b  cmp     rax, [rcx]
0x180012c7e  jnz     short loc_180012C85
0x180012c80  mov     rax, rdi
0x180012c83  jmp     short loc_180012CFC
0x180012c85  mov     rbx, [rax+40h]
0x180012c89  mov     rbx, [rbx]
0x180012c8c  cmp     byte ptr [rbx+19h], 0
0x180012c90  jnz     short loc_180012CF9
0x180012c92  lea     r8, [rbx+58h]
0x180012c96  mov     rdx, [rdi+8]
0x180012c9a  cmp     rdx, [rdi+10h]
0x180012c9e  jz      short loc_180012CAC
0x180012ca0  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x180012ca5  add     qword ptr [rdi+8], 20h ; ' '
0x180012caa  jmp     short loc_180012CB4
0x180012cac  mov     rcx, rdi
0x180012caf  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180012cb4  mov     rcx, [rbx+10h]
0x180012cb8  cmp     byte ptr [rcx+19h], 0
0x180012cbc  jz      short loc_180012CDC
0x180012cbe  mov     rax, [rbx+8]
0x180012cc2  jmp     short loc_180012CD1
0x180012cc4  cmp     rbx, [rax+10h]
0x180012cc8  jnz     short loc_180012CD7
0x180012cca  mov     rbx, rax
0x180012ccd  mov     rax, [rax+8]
0x180012cd1  cmp     byte ptr [rax+19h], 0
0x180012cd5  jz      short loc_180012CC4
0x180012cd7  mov     rbx, rax
0x180012cda  jmp     short loc_180012C8C
0x180012cdc  mov     rbx, rcx
0x180012cdf  mov     rcx, [rcx]
0x180012ce2  cmp     byte ptr [rcx+19h], 0
0x180012ce6  jnz     short loc_180012C8C
0x180012ce8  mov     rbx, rcx
0x180012ceb  mov     rax, [rcx]
0x180012cee  mov     rcx, rax
0x180012cf1  cmp     byte ptr [rax+19h], 0
0x180012cf5  jz      short loc_180012CE8
0x180012cf7  jmp     short loc_180012C8C
0x180012cf9  mov     rax, rdi
0x180012cfc  mov     rbx, [rsp+28h+arg_18]
0x180012d01  add     rsp, 20h
0x180012d05  pop     rdi
0x180012d06  retn
```
