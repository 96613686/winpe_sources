# std::default_delete<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>>::operator()(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>> *)

- ea: `0x180011890`
- end: `0x1800118b8`
- name: `??R?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@std@@QEBAXPEAV?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@1@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, _QWORD **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001140c`
- `0x180015dc0`

## callees

- `0x180002ea4`
- `0x180010fe0`
- `0x180011890`

## pseudocode

```c
void __fastcall std::default_delete<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>>::operator()(
        __int64 a1,
        _QWORD **a2)
{
  if ( a2 )
  {
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180011890  test    rdx, rdx
0x180011893  jz      short locret_1800118B7
0x180011895  push    rbx
0x180011896  sub     rsp, 20h
0x18001189a  mov     rcx, rdx
0x18001189d  mov     rbx, rdx
0x1800118a0  call    ??1?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>,0>>(void)
0x1800118a5  mov     edx, 10h; unsigned __int64
0x1800118aa  mov     rcx, rbx; void *
0x1800118ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800118b2  add     rsp, 20h
0x1800118b6  pop     rbx
0x1800118b7  retn
```
