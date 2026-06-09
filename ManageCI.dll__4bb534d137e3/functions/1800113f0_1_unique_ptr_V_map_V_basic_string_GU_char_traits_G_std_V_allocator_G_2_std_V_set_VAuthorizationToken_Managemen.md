# ??1?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@@2@@std@@QEAA@XZ

- ea: `0x1800113f0`
- end: `0x180011406`
- name: `??1?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014ee0`
- `0x18002b548`
- `0x18002b940`

## callees

- `0x1800113f0`
- `0x180011860`

## pseudocode

```c
__int64 __fastcall __1__unique_ptr_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_VAuthorizationToken_Management_CodeIntegrity__U__less_X_std__V__allocator_VAuthorizationToken_Management_CodeIntegrity___5__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_VAuthorizationToken_Management_CodeIntegrity__U__less_X_std__V__allocator_VAuthorizationToken_Management_CodeIntegrity___5__2__std___2__std__U__default_delete_V__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_VAuthorizationToken_Management_CodeIntegrity__U__less_X_std__V__allocator_VAuthorizationToken_Management_CodeIntegrity___5__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__set_VAuthorizationToken_Management_CodeIntegrity__U__less_X_std__V__allocator_VAuthorizationToken_Management_CodeIntegrity___5__2__std___2__std___2__std__QEAA_XZ(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<std::map<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>>>::operator()();
  return result;
}

```

## disassembly

```asm
0x1800113f0  sub     rsp, 28h
0x1800113f4  mov     rdx, [rcx]
0x1800113f7  test    rdx, rdx
0x1800113fa  jz      short loc_180011401
0x1800113fc  call    ??R?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@@std@@QEBAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@1@@Z; std::default_delete<std::map<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>>>::operator()(std::map<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>> *)
0x180011401  add     rsp, 28h
0x180011405  retn
```
