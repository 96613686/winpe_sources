# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>,void *> *)

- ea: `0x18000f8b4`
- end: `0x18000f907`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@1@@Z`
- size: `83`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f8b4`
- `0x180010fb0`

## callees

- `0x180004a98`
- `0x18000f8b4`
- `0x180011380`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  _QWORD *v6; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>::~pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>(v6 + 4);
    std::_Deallocate<16>(v6, 0x50u);
  }
}

```

## disassembly

```asm
0x18000f8b4  push    rbx
0x18000f8b6  push    rbp
0x18000f8b7  push    rsi
0x18000f8b8  push    rdi
0x18000f8b9  sub     rsp, 28h
0x18000f8bd  cmp     byte ptr [r8+19h], 0
0x18000f8c2  mov     rdi, r8
0x18000f8c5  mov     rsi, rdx
0x18000f8c8  mov     rbp, rcx
0x18000f8cb  jnz     short loc_18000F8FE
0x18000f8cd  mov     r8, [rdi+10h]
0x18000f8d1  mov     rdx, rsi
0x18000f8d4  mov     rcx, rbp
0x18000f8d7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *> *)
0x18000f8dc  mov     rbx, rdi
0x18000f8df  mov     rdi, [rdi]
0x18000f8e2  lea     rcx, [rbx+20h]
0x18000f8e6  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>::~pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>(void)
0x18000f8eb  mov     edx, 50h ; 'P'
0x18000f8f0  mov     rcx, rbx
0x18000f8f3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f8f8  cmp     byte ptr [rdi+19h], 0
0x18000f8fc  jz      short loc_18000F8CD
0x18000f8fe  add     rsp, 28h
0x18000f902  pop     rdi
0x18000f903  pop     rsi
0x18000f904  pop     rbp
0x18000f905  pop     rbx
0x18000f906  retn
```
