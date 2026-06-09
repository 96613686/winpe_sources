# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(void)

- ea: `0x180010f28`
- end: `0x180010f44`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800110d0`
- `0x180011100`
- `0x18002a503`

## callees

- `0x180004a98`
- `0x180010f28`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,void *>>>(
        __int64 a1)
{
  _QWORD *v1; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x118u);
}

```

## disassembly

```asm
0x180010f28  sub     rsp, 28h
0x180010f2c  mov     rcx, [rcx+8]
0x180010f30  test    rcx, rcx
0x180010f33  jz      short loc_180010F3F
0x180010f35  mov     edx, 118h
0x180010f3a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010f3f  add     rsp, 28h
0x180010f43  retn
```
