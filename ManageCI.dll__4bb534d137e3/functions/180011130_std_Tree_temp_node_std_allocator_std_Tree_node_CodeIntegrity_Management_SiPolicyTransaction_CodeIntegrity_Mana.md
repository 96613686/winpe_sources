# std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)

- ea: `0x180011130`
- end: `0x180011158`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f33c`
- `0x18002a58c`

## callees

- `0x180010e90`
- `0x180010f4c`
- `0x180011130`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>(v2 + 32);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(a1);
}

```

## disassembly

```asm
0x180011130  push    rbx
0x180011132  sub     rsp, 20h
0x180011136  mov     rbx, rcx
0x180011139  mov     rcx, [rcx+8]
0x18001113d  test    rcx, rcx
0x180011140  jz      short loc_18001114B
0x180011142  add     rcx, 20h ; ' '
0x180011146  call    ??1?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>(void)
0x18001114b  mov     rcx, rbx
0x18001114e  add     rsp, 20h
0x180011152  pop     rbx
0x180011153  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(void)
```
