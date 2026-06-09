# std::default_delete<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>>::operator()(std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>> *)

- ea: `0x1800118c0`
- end: `0x1800118e8`
- name: `??R?$default_delete@V?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@@std@@QEBAXPEAV?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@1@@Z`
- size: `40`
- prototype: `void __fastcall(__int64, _QWORD **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180011428`
- `0x180015dec`

## callees

- `0x180002ea4`
- `0x180011010`
- `0x1800118c0`

## pseudocode

```c
void __fastcall std::default_delete<std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>>::operator()(
        __int64 a1,
        _QWORD **a2)
{
  if ( a2 )
  {
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800118c0  test    rdx, rdx
0x1800118c3  jz      short locret_1800118E7
0x1800118c5  push    rbx
0x1800118c6  sub     rsp, 20h
0x1800118ca  mov     rcx, rdx
0x1800118cd  mov     rbx, rdx
0x1800118d0  call    ??1?$_Tree@V?$_Tset_traits@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>,0>>(void)
0x1800118d5  mov     edx, 10h; unsigned __int64
0x1800118da  mov     rcx, rbx; void *
0x1800118dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800118e2  add     rsp, 20h
0x1800118e6  pop     rbx
0x1800118e7  retn
```
