# std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>(void)

- ea: `0x1800110a0`
- end: `0x1800110ca`
- name: `??1?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011380`
- `0x1800113a8`
- `0x18001c714`

## callees

- `0x180004a98`
- `0x18000fa80`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>(
        _QWORD **a1)
{
  std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(
    (__int64)a1,
    (__int64)a1,
    (__int64 *)(*a1)[1]);
  std::_Deallocate<16>(*a1, 0x108u);
}

```

## disassembly

```asm
0x1800110a0  push    rbx
0x1800110a2  sub     rsp, 20h
0x1800110a6  mov     r8, [rcx]
0x1800110a9  mov     rdx, rcx
0x1800110ac  mov     rbx, rcx
0x1800110af  mov     r8, [r8+8]
0x1800110b3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *> *)
0x1800110b8  mov     rcx, [rbx]
0x1800110bb  mov     edx, 108h
0x1800110c0  add     rsp, 20h
0x1800110c4  pop     rbx
0x1800110c5  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
