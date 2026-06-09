# std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)

- ea: `0x180011100`
- end: `0x180011128`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f09c`
- `0x18002a568`

## callees

- `0x180010e60`
- `0x180010f28`
- `0x180011100`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>(v2 + 32);
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(a1);
}

```

## disassembly

```asm
0x180011100  push    rbx
0x180011102  sub     rsp, 20h
0x180011106  mov     rbx, rcx
0x180011109  mov     rcx, [rcx+8]
0x18001110d  test    rcx, rcx
0x180011110  jz      short loc_18001111B
0x180011112  add     rcx, 20h ; ' '
0x180011116  call    ??1?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>(void)
0x18001111b  mov     rcx, rbx
0x18001111e  add     rsp, 20h
0x180011122  pop     rbx
0x180011123  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)
```
