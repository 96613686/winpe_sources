# std::default_delete<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>>::operator()(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>> *)

- ea: `0x180011920`
- end: `0x180011948`
- name: `??R?$default_delete@V?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@std@@QEBAXPEAV?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@1@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011460`
- `0x180015e44`

## callees

- `0x180002ea4`
- `0x180011070`
- `0x180011920`

## pseudocode

```c
void __fastcall std::default_delete<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::operator()(
        __int64 a1,
        void *a2)
{
  if ( a2 )
  {
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180011920  test    rdx, rdx
0x180011923  jz      short locret_180011947
0x180011925  push    rbx
0x180011926  sub     rsp, 20h
0x18001192a  mov     rcx, rdx
0x18001192d  mov     rbx, rdx
0x180011930  call    ??1?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>(void)
0x180011935  mov     edx, 10h; unsigned __int64
0x18001193a  mov     rcx, rbx; void *
0x18001193d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011942  add     rsp, 20h
0x180011946  pop     rbx
0x180011947  retn
```
