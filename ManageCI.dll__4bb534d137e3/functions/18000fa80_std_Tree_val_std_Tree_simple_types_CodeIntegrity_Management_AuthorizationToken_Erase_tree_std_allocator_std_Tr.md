# std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *> *)

- ea: `0x18000fa80`
- end: `0x18000fad5`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@1@@Z`
- size: `85`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fa80`
- `0x1800110a0`

## callees

- `0x180004a98`
- `0x1800057d8`
- `0x18000fa80`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  _QWORD *v6; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    CodeIntegrity::Management::AuthorizationToken::`scalar deleting destructor'(
      (CodeIntegrity::Management::AuthorizationToken *)(v6 + 4),
      0);
    std::_Deallocate<16>(v6, 0x108u);
  }
}

```

## disassembly

```asm
0x18000fa80  push    rbx
0x18000fa82  push    rbp
0x18000fa83  push    rsi
0x18000fa84  push    rdi
0x18000fa85  sub     rsp, 28h
0x18000fa89  cmp     byte ptr [r8+19h], 0
0x18000fa8e  mov     rdi, r8
0x18000fa91  mov     rsi, rdx
0x18000fa94  mov     rbp, rcx
0x18000fa97  jnz     short loc_18000FACC
0x18000fa99  mov     r8, [rdi+10h]
0x18000fa9d  mov     rdx, rsi
0x18000faa0  mov     rcx, rbp
0x18000faa3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@@1@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CodeIntegrity::Management::AuthorizationToken>>::_Erase_tree<std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>>>(std::allocator<std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *>> &,std::_Tree_node<CodeIntegrity::Management::AuthorizationToken,void *> *)
0x18000faa8  mov     rbx, rdi
0x18000faab  xor     edx, edx; unsigned int
0x18000faad  mov     rdi, [rdi]
0x18000fab0  lea     rcx, [rbx+20h]; this
0x18000fab4  call    ??_GAuthorizationToken@Management@CodeIntegrity@@QEAAPEAXI@Z; CodeIntegrity::Management::AuthorizationToken::`scalar deleting destructor'(uint)
0x18000fab9  mov     edx, 108h
0x18000fabe  mov     rcx, rbx
0x18000fac1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fac6  cmp     byte ptr [rdi+19h], 0
0x18000faca  jz      short loc_18000FA99
0x18000facc  add     rsp, 28h
0x18000fad0  pop     rdi
0x18000fad1  pop     rsi
0x18000fad2  pop     rbp
0x18000fad3  pop     rbx
0x18000fad4  retn
```
