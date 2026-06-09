# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::set<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>>>,void *>>>(void)

- ea: `0x18001be1c`
- end: `0x18001be38`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c014`
- `0x18001c074`
- `0x18002b394`

## callees

- `0x180004a98`
- `0x18001be1c`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>,void *>>>(
        __int64 a1)
{
  _QWORD *v1; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x50u);
}

```

## disassembly

```asm
0x18001be1c  sub     rsp, 28h
0x18001be20  mov     rcx, [rcx+8]
0x18001be24  test    rcx, rcx
0x18001be27  jz      short loc_18001BE33
0x18001be29  mov     edx, 50h ; 'P'
0x18001be2e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001be33  add     rsp, 28h
0x18001be37  retn
```
