# std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *> *)

- ea: `0x18000f96c`
- end: `0x18000f9bf`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z`
- size: `83`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f96c`
- `0x180011010`

## callees

- `0x180004a98`
- `0x18000f96c`
- `0x180010e60`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  _QWORD *v6; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>(v6 + 4);
    std::_Deallocate<16>(v6, 0x118u);
  }
}

```

## disassembly

```asm
0x18000f96c  push    rbx
0x18000f96e  push    rbp
0x18000f96f  push    rsi
0x18000f970  push    rdi
0x18000f971  sub     rsp, 28h
0x18000f975  cmp     byte ptr [r8+19h], 0
0x18000f97a  mov     rdi, r8
0x18000f97d  mov     rsi, rdx
0x18000f980  mov     rbp, rcx
0x18000f983  jnz     short loc_18000F9B6
0x18000f985  mov     r8, [rdi+10h]
0x18000f989  mov     rdx, rsi
0x18000f98c  mov     rcx, rbp
0x18000f98f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,void *> *)
0x18000f994  mov     rbx, rdi
0x18000f997  mov     rdi, [rdi]
0x18000f99a  lea     rcx, [rbx+20h]
0x18000f99e  call    ??1?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>(void)
0x18000f9a3  mov     edx, 118h
0x18000f9a8  mov     rcx, rbx
0x18000f9ab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f9b0  cmp     byte ptr [rdi+19h], 0
0x18000f9b4  jz      short loc_18000F985
0x18000f9b6  add     rsp, 28h
0x18000f9ba  pop     rdi
0x18000f9bb  pop     rsi
0x18000f9bc  pop     rbp
0x18000f9bd  pop     rbx
0x18000f9be  retn
```
