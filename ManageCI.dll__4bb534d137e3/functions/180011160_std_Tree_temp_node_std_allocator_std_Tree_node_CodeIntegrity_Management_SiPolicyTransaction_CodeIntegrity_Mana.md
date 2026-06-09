# std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)

- ea: `0x180011160`
- end: `0x180011188`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f4b8`
- `0x18002a5c2`

## callees

- `0x180010eb8`
- `0x180010f4c`
- `0x180011160`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>(v2 + 32);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(a1);
}

```

## disassembly

```asm
0x180011160  push    rbx
0x180011162  sub     rsp, 20h
0x180011166  mov     rbx, rcx
0x180011169  mov     rcx, [rcx+8]
0x18001116d  test    rcx, rcx
0x180011170  jz      short loc_18001117B
0x180011172  add     rcx, 20h ; ' '
0x180011176  call    ??1?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>(void)
0x18001117b  mov     rcx, rbx
0x18001117e  add     rsp, 20h
0x180011182  pop     rbx
0x180011183  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)
```
