# utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)

- ea: `0x18000e558`
- end: `0x18000e6bb`
- name: `??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a2a0`

## callees

- `0x1800029bc`
- `0x180003b74`
- `0x18000e558`

## pseudocode

```c
const struct std::nothrow_t *__fastcall utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        unsigned __int64 a1,
        const struct std::nothrow_t *a2,
        unsigned int *a3,
        __int64 *a4,
        void **a5)
{
  const struct std::nothrow_t *v7; // r14
  void **v9; // rax
  void **v10; // rbx
  char v11; // di
  void *v12; // rdx
  void **v13; // rcx
  unsigned int v14; // r8d
  void **v15; // r10
  void **v16; // rax
  void **v17; // r8
  void *v18; // rax
  const struct std::nothrow_t *result; // rax
  void **v20; // [rsp+20h] [rbp-38h] BYREF
  char v21; // [rsp+28h] [rbp-30h]

  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  v7 = a2;
  if ( *(_QWORD *)(a1 + 16) != a1 )
  {
    v13 = *(void ***)a1;
    v14 = *a3;
    v10 = 0;
    v11 = 1;
    do
    {
      if ( v14 >= *((_DWORD *)v13 + 6) )
      {
        v10 = v13;
        LOBYTE(a2) = 1;
      }
      else
      {
        LOBYTE(a2) = 0;
      }
      v15 = v13;
      v13 = (void **)v13[(unsigned __int8)a2 + 1];
    }
    while ( v13 != &utl::_TreeSentinel );
    if ( v10 && *((_DWORD *)v10 + 6) < v14 )
      v10 = 0;
    v20 = v15;
    v21 = (char)a2;
    if ( !v10 )
    {
      v16 = (void **)operator new(0x30u, a2);
      v10 = v16;
      if ( v16 )
      {
        *((_DWORD *)v16 + 6) = *a3;
        v17 = v16;
        v18 = (void *)*a4;
        v10[5] = *a5;
        v10[4] = v18;
        utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(
          a1,
          &v20,
          v17);
        goto LABEL_16;
      }
    }
LABEL_15:
    v11 = 0;
    goto LABEL_16;
  }
  v9 = (void **)operator new(0x30u, a2);
  v10 = v9;
  if ( !v9 )
    goto LABEL_15;
  *((_DWORD *)v9 + 6) = *a3;
  v11 = 1;
  v12 = *a5;
  v9[4] = (void *)*a4;
  v9[5] = v12;
  *v9 = (void *)(a1 | 1);
  v9[1] = &utl::_TreeSentinel;
  v9[2] = &utl::_TreeSentinel;
  *(_QWORD *)a1 = v9;
  *(_QWORD *)(a1 + 8) = v9;
  *(_QWORD *)(a1 + 16) = v9;
  ++*(_QWORD *)(a1 + 24);
LABEL_16:
  result = v7;
  *(_QWORD *)v7 = v10;
  *((_BYTE *)v7 + 8) = v11;
  return result;
}

```

## disassembly

```asm
0x18000e558  mov     [rsp+arg_8], rbx
0x18000e55d  mov     [rsp+arg_10], rbp
0x18000e562  push    rsi
0x18000e563  push    rdi
0x18000e564  push    r12
0x18000e566  push    r14
0x18000e568  push    r15
0x18000e56a  sub     rsp, 30h
0x18000e56e  mov     qword ptr [rdx], 0
0x18000e575  mov     r12, r9
0x18000e578  mov     byte ptr [rdx+8], 0
0x18000e57c  mov     rbp, r8
0x18000e57f  mov     r14, rdx
0x18000e582  mov     r15, rcx
0x18000e585  cmp     [rcx+10h], rcx
0x18000e589  jnz     short loc_18000E5EF
0x18000e58b  mov     ecx, 30h ; '0'; unsigned __int64
0x18000e590  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e595  mov     rbx, rax
0x18000e598  test    rax, rax
0x18000e59b  jz      loc_18000E697
0x18000e5a1  mov     ecx, [rbp+0]
0x18000e5a4  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000e5ab  mov     [rax+18h], ecx
0x18000e5ae  mov     edi, 1
0x18000e5b3  mov     rcx, [rsp+58h+arg_20]
0x18000e5bb  mov     rdx, [rcx]
0x18000e5be  mov     rcx, [r12]
0x18000e5c2  mov     [rax+20h], rcx
0x18000e5c6  mov     rcx, r15
0x18000e5c9  mov     [rax+28h], rdx
0x18000e5cd  or      rcx, rdi
0x18000e5d0  mov     [rax], rcx
0x18000e5d3  mov     [rax+8], r9
0x18000e5d7  mov     [rax+10h], r9
0x18000e5db  mov     [r15], rax
0x18000e5de  mov     [r15+8], rax
0x18000e5e2  mov     [r15+10h], rax
0x18000e5e6  add     [r15+18h], rdi
0x18000e5ea  jmp     loc_18000E69A
0x18000e5ef  mov     rcx, [rcx]
0x18000e5f2  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000e5f9  mov     r8d, [r8]
0x18000e5fc  xor     ebx, ebx
0x18000e5fe  lea     edi, [rbx+1]
0x18000e601  cmp     r8d, [rcx+18h]
0x18000e605  jnb     short loc_18000E60B
0x18000e607  xor     dl, dl
0x18000e609  jmp     short loc_18000E611
0x18000e60b  mov     rbx, rcx
0x18000e60e  mov     dl, dil; struct std::nothrow_t *
0x18000e611  movzx   eax, dl
0x18000e614  mov     r10, rcx
0x18000e617  mov     rcx, [rcx+rax*8+8]
0x18000e61c  cmp     rcx, r9
0x18000e61f  jnz     short loc_18000E601
0x18000e621  test    rbx, rbx
0x18000e624  jz      short loc_18000E630
0x18000e626  xor     eax, eax
0x18000e628  cmp     [rbx+18h], r8d
0x18000e62c  cmovb   rbx, rax
0x18000e630  mov     eax, [rsp+58h+var_2F]
0x18000e634  mov     [rsp+58h+var_2F], eax
0x18000e638  movzx   eax, [rsp+58h+var_2B]
0x18000e63d  mov     [rsp+58h+var_2B], ax
0x18000e642  mov     al, [rsp+58h+var_29]
0x18000e646  mov     [rsp+58h+var_29], al
0x18000e64a  mov     [rsp+58h+var_38], r10
0x18000e64f  mov     [rsp+58h+var_30], dl
0x18000e653  test    rbx, rbx
0x18000e656  jnz     short loc_18000E697
0x18000e658  lea     ecx, [rbx+30h]; unsigned __int64
0x18000e65b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e660  mov     rbx, rax
0x18000e663  test    rax, rax
0x18000e666  jz      short loc_18000E697
0x18000e668  mov     eax, [rbp+0]
0x18000e66b  lea     rdx, [rsp+58h+var_38]
0x18000e670  mov     [rbx+18h], eax
0x18000e673  mov     r8, rbx
0x18000e676  mov     rax, [rsp+58h+arg_20]
0x18000e67e  mov     rcx, [rax]
0x18000e681  mov     rax, [r12]
0x18000e685  mov     [rbx+28h], rcx
0x18000e689  mov     rcx, r15
0x18000e68c  mov     [rbx+20h], rax
0x18000e690  call    ?_InsertAt@?$_Tree@IU?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@@Z; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ReadOnlyBinary>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *,bool> const &,utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *)
0x18000e695  jmp     short loc_18000E69A
0x18000e697  xor     dil, dil
0x18000e69a  mov     rax, r14
0x18000e69d  mov     [rax], rbx
0x18000e6a0  mov     [r14+8], dil
0x18000e6a4  mov     rbx, [rsp+58h+arg_8]
0x18000e6a9  mov     rbp, [rsp+58h+arg_10]
0x18000e6ae  add     rsp, 30h
0x18000e6b2  pop     r15
0x18000e6b4  pop     r14
0x18000e6b6  pop     r12
0x18000e6b8  pop     rdi
0x18000e6b9  pop     rsi
0x18000e6ba  retn
```
