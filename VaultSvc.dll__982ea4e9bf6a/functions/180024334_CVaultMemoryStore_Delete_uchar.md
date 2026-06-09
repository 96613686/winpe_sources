# CVaultMemoryStore::Delete(uchar)

- ea: `0x180024334`
- end: `0x18002444c`
- name: `?Delete@CVaultMemoryStore@@IEAAXE@Z`
- size: `280`
- prototype: `void __fastcall(CVaultMemoryStore *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800379f8`
- `0x180039cb0`

## callees

- `0x1800047a0`
- `0x180012210`
- `0x180024334`
- `0x180024460`
- `0x1800244c0`
- `0x18002471c`
- `0x180024a50`
- `0x180037b0c`
- `0x180037b40`
- `0x18004d010`

## pseudocode

```c
void __fastcall CVaultMemoryStore::Delete(CVaultMemoryStore *this)
{
  char *v2; // rdi
  __int64 v3; // rbx
  _QWORD **v4; // rdi
  __int64 v5; // rax
  _QWORD *v6; // rbx
  __int64 j; // rbx
  _QWORD *v8; // rax
  __int64 i; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 14) )
  {
    v2 = (char *)this + 40;
    v3 = *((_QWORD *)this + 5);
    std::_Tree_val<std::_Tree_simple_types<std::pair<_tagSIDArray const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,unsigned long>,void *>>>(
      (__int64)this + 40,
      (__int64)this + 40,
      *(__int64 **)(v3 + 8));
    *(_QWORD *)(v3 + 8) = v3;
    *(_QWORD *)v3 = v3;
    *(_QWORD *)(v3 + 16) = v3;
    *((_QWORD *)v2 + 1) = 0;
    v4 = (_QWORD **)((char *)this + 8);
    v5 = **((_QWORD **)this + 1);
    for ( i = v5; ; v5 = i )
    {
      v6 = *v4;
      if ( (_QWORD *)v5 == *v4 )
        break;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 48) + 8LL))(*(_QWORD *)(v5 + 48));
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,IVaultSchema *>>>,std::_Iterator_base0>::operator++(&i);
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_VAULT_CAUB const,IVaultCredential *>,void *>>>(
      (char *)this + 8,
      (char *)this + 8,
      v6[1]);
    v6[1] = v6;
    *v6 = v6;
    v6[2] = v6;
    *((_QWORD *)this + 2) = 0;
    for ( j = **((_QWORD **)this + 3); j != *((_QWORD *)this + 3); j = i )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(j + 48) + 8LL))(*(_QWORD *)(j + 48));
      VaultFreeInternal(*(HLOCAL *)(j + 40));
      i = j;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>::operator++(&i);
      v8 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Extract(
                       (char *)this + 24,
                       j);
      std::_Deallocate<16>(v8, 0x38u);
    }
    IVaultSecurable::FreeVaultSecurable(*((HLOCAL *)this + 37));
    *((_DWORD *)this + 14) = 1;
  }
}

```

## disassembly

```asm
0x180024334  mov     [rsp+arg_8], rbx
0x180024339  mov     [rsp+arg_10], rsi
0x18002433e  push    rdi
0x18002433f  sub     rsp, 20h
0x180024343  cmp     dword ptr [rcx+38h], 0
0x180024347  mov     rsi, rcx
0x18002434a  jnz     loc_18002443C
0x180024350  lea     rdi, [rcx+28h]
0x180024354  mov     rbx, [rdi]
0x180024357  mov     rdx, rdi
0x18002435a  mov     rcx, rdi
0x18002435d  mov     r8, [rbx+8]
0x180024361  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_tagSIDArray@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_tagSIDArray@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_tagSIDArray const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *>> &,std::_Tree_node<std::pair<_tagSIDArray const,ulong>,void *> *)
0x180024366  mov     [rbx+8], rbx
0x18002436a  mov     [rbx], rbx
0x18002436d  mov     [rbx+10h], rbx
0x180024371  mov     qword ptr [rdi+8], 0
0x180024379  lea     rdi, [rsi+8]
0x18002437d  mov     rax, [rdi]
0x180024380  mov     rax, [rax]
0x180024383  mov     [rsp+28h+arg_0], rax
0x180024388  mov     rbx, [rdi]
0x18002438b  cmp     rax, rbx
0x18002438e  jz      short loc_1800243B1
0x180024390  mov     rcx, [rax+30h]
0x180024394  mov     rax, [rcx]
0x180024397  mov     rax, [rax+8]
0x18002439b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243a0  lea     rcx, [rsp+28h+arg_0]
0x1800243a5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUIVaultSchema@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,IVaultSchema *>>>,std::_Iterator_base0>::operator++(void)
0x1800243aa  mov     rax, [rsp+28h+arg_0]
0x1800243af  jmp     short loc_180024388
0x1800243b1  mov     r8, [rbx+8]
0x1800243b5  mov     rdx, rdi
0x1800243b8  mov     rcx, rdi
0x1800243bb  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_VAULT_CAUB const,IVaultCredential *>,void *>>>(std::allocator<std::_Tree_node<std::pair<_VAULT_CAUB const,IVaultCredential *>,void *>> &,std::_Tree_node<std::pair<_VAULT_CAUB const,IVaultCredential *>,void *> *)
0x1800243c0  mov     [rbx+8], rbx
0x1800243c4  mov     [rbx], rbx
0x1800243c7  mov     [rbx+10h], rbx
0x1800243cb  mov     qword ptr [rdi+8], 0
0x1800243d3  lea     rdi, [rsi+18h]
0x1800243d7  mov     rbx, [rdi]
0x1800243da  mov     rbx, [rbx]
0x1800243dd  cmp     rbx, [rdi]
0x1800243e0  jz      short loc_180024429
0x1800243e2  mov     rcx, [rbx+30h]
0x1800243e6  mov     rax, [rcx]
0x1800243e9  mov     rax, [rax+8]
0x1800243ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243f2  mov     rcx, [rbx+28h]; hMem
0x1800243f6  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x1800243fb  lea     rcx, [rsp+28h+arg_0]
0x180024400  mov     [rsp+28h+arg_0], rbx
0x180024405  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>::operator++(void)
0x18002440a  mov     rdx, rbx
0x18002440d  mov     rcx, rdi
0x180024410  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_VAULT_CAUB@@PEAUIVaultCredential@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_VAULT_CAUB const,IVaultCredential *>>>,std::_Iterator_base0>)
0x180024415  mov     edx, 38h ; '8'
0x18002441a  mov     rcx, rax
0x18002441d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180024422  mov     rbx, [rsp+28h+arg_0]
0x180024427  jmp     short loc_1800243DD
0x180024429  mov     rcx, [rsi+128h]; hMem
0x180024430  call    ?FreeVaultSecurable@IVaultSecurable@@SAXPEAV1@@Z; IVaultSecurable::FreeVaultSecurable(IVaultSecurable *)
0x180024435  mov     dword ptr [rsi+38h], 1
0x18002443c  mov     rbx, [rsp+28h+arg_8]
0x180024441  mov     rsi, [rsp+28h+arg_10]
0x180024446  add     rsp, 20h
0x18002444a  pop     rdi
0x18002444b  retn
```
