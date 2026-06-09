# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>>,0>>::find(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800159fc`
- end: `0x180015a4b`
- name: `?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `79`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011d00`
- `0x180012c30`
- `0x180012e20`
- `0x180013660`
- `0x18001c714`

## callees

- `0x18000fadc`
- `0x18000fd38`
- `0x1800159fc`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 *result; // rax
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Find_lower_bound<std::wstring>(
    (__int64)a1,
    &v10,
    a3);
  v6 = a3;
  v7 = v11;
  if ( !std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Lower_bound_duplicate<std::wstring>(
          v8,
          v11,
          v6) )
    v7 = *a1;
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x1800159fc  mov     [rsp+arg_0], rbx
0x180015a01  mov     [rsp+arg_8], rsi
0x180015a06  push    rdi
0x180015a07  sub     rsp, 40h
0x180015a0b  mov     rdi, rdx
0x180015a0e  mov     rbx, r8
0x180015a11  lea     rdx, [rsp+48h+var_28]
0x180015a16  mov     rsi, rcx
0x180015a19  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180015a1e  mov     r8, rbx
0x180015a21  mov     rbx, [rsp+48h+var_18]
0x180015a26  mov     rdx, rbx
0x180015a29  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *> * const,std::wstring const &)
0x180015a2e  test    al, al
0x180015a30  jnz     short loc_180015A35
0x180015a32  mov     rbx, [rsi]
0x180015a35  mov     rsi, [rsp+48h+arg_8]
0x180015a3a  mov     rax, rdi
0x180015a3d  mov     [rdi], rbx
0x180015a40  mov     rbx, [rsp+48h+arg_0]
0x180015a45  add     rsp, 40h
0x180015a49  pop     rdi
0x180015a4a  retn
```
