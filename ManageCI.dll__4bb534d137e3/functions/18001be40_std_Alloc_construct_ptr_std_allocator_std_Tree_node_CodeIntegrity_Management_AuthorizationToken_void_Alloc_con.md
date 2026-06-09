# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(void)

- ea: `0x18001be40`
- end: `0x18001be5c`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c044`
- `0x18001c080`
- `0x18002b3b8`

## callees

- `0x180004a98`
- `0x18001be40`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(
        __int64 a1)
{
  _QWORD *v1; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x108u);
}

```

## disassembly

```asm
0x18001be40  sub     rsp, 28h
0x18001be44  mov     rcx, [rcx+8]
0x18001be48  test    rcx, rcx
0x18001be4b  jz      short loc_18001BE57
0x18001be4d  mov     edx, 108h
0x18001be52  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001be57  add     rsp, 28h
0x18001be5b  retn
```
