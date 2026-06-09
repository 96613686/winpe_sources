# std::default_delete<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>>::operator()(std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>> *)

- ea: `0x1800118f0`
- end: `0x180011918`
- name: `??R?$default_delete@V?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@std@@QEBAXPEAV?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@1@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, _QWORD **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011444`
- `0x180015e18`

## callees

- `0x180002ea4`
- `0x180011040`
- `0x1800118f0`

## pseudocode

```c
void __fastcall std::default_delete<std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::operator()(
        __int64 a1,
        _QWORD **a2)
{
  if ( a2 )
  {
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800118f0  test    rdx, rdx
0x1800118f3  jz      short locret_180011917
0x1800118f5  push    rbx
0x1800118f6  sub     rsp, 20h
0x1800118fa  mov     rcx, rdx
0x1800118fd  mov     rbx, rdx
0x180011900  call    ??1?$_Tree@V?$_Tset_traits@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>(void)
0x180011905  mov     edx, 10h; unsigned __int64
0x18001190a  mov     rcx, rbx; void *
0x18001190d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011912  add     rsp, 20h
0x180011916  pop     rbx
0x180011917  retn
```
