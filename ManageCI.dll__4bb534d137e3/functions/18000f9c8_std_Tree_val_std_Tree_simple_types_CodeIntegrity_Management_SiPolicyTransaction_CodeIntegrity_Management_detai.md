# std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *)

- ea: `0x18000f9c8`
- end: `0x18000fa1b`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z`
- size: `83`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f9c8`
- `0x180011040`

## callees

- `0x180004a98`
- `0x18000f9c8`
- `0x180010e90`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  _QWORD *v6; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>(v6 + 4);
    std::_Deallocate<16>(v6, 0xE0u);
  }
}

```

## disassembly

```asm
0x18000f9c8  push    rbx
0x18000f9ca  push    rbp
0x18000f9cb  push    rsi
0x18000f9cc  push    rdi
0x18000f9cd  sub     rsp, 28h
0x18000f9d1  cmp     byte ptr [r8+19h], 0
0x18000f9d6  mov     rdi, r8
0x18000f9d9  mov     rsi, rdx
0x18000f9dc  mov     rbp, rcx
0x18000f9df  jnz     short loc_18000FA12
0x18000f9e1  mov     r8, [rdi+10h]
0x18000f9e5  mov     rdx, rsi
0x18000f9e8  mov     rcx, rbp
0x18000f9eb  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>> &,std::_Tree_node<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *> *)
0x18000f9f0  mov     rbx, rdi
0x18000f9f3  mov     rdi, [rdi]
0x18000f9f6  lea     rcx, [rbx+20h]
0x18000f9fa  call    ??1?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>::~SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>(void)
0x18000f9ff  mov     edx, 0E0h
0x18000fa04  mov     rcx, rbx
0x18000fa07  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fa0c  cmp     byte ptr [rdi+19h], 0
0x18000fa10  jz      short loc_18000F9E1
0x18000fa12  add     rsp, 28h
0x18000fa16  pop     rdi
0x18000fa17  pop     rsi
0x18000fa18  pop     rbp
0x18000fa19  pop     rbx
0x18000fa1a  retn
```
