# std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *)

- ea: `0x18000f910`
- end: `0x18000f963`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z`
- size: `83`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f910`
- `0x180010fe0`

## callees

- `0x180004a98`
- `0x18000f910`
- `0x180010e30`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  _QWORD *v6; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>(v6 + 4);
    std::_Deallocate<16>(v6, 0x118u);
  }
}

```

## disassembly

```asm
0x18000f910  push    rbx
0x18000f912  push    rbp
0x18000f913  push    rsi
0x18000f914  push    rdi
0x18000f915  sub     rsp, 28h
0x18000f919  cmp     byte ptr [r8+19h], 0
0x18000f91e  mov     rdi, r8
0x18000f921  mov     rsi, rdx
0x18000f924  mov     rbp, rcx
0x18000f927  jnz     short loc_18000F95A
0x18000f929  mov     r8, [rdi+10h]
0x18000f92d  mov     rdx, rsi
0x18000f930  mov     rcx, rbp
0x18000f933  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *)
0x18000f938  mov     rbx, rdi
0x18000f93b  mov     rdi, [rdi]
0x18000f93e  lea     rcx, [rbx+20h]
0x18000f942  call    ??1?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>::~AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>(void)
0x18000f947  mov     edx, 118h
0x18000f94c  mov     rcx, rbx
0x18000f94f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f954  cmp     byte ptr [rdi+19h], 0
0x18000f958  jz      short loc_18000F929
0x18000f95a  add     rsp, 28h
0x18000f95e  pop     rdi
0x18000f95f  pop     rsi
0x18000f960  pop     rbp
0x18000f961  pop     rbx
0x18000f962  retn
```
