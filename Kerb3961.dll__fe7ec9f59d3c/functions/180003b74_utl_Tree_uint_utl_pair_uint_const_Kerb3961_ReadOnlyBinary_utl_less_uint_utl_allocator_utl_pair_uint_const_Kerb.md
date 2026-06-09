# utl::_Tree<uint,utl::pair<uint const,Kerb3961::ReadOnlyBinary>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *,bool> const &,utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *)

- ea: `0x180003b74`
- end: `0x180003cbb`
- name: `?_InsertAt@?$_Tree@IU?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@@Z`
- size: `327`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031a8`
- `0x18000e130`
- `0x18000e558`

## callees

- `0x180003b74`

## pseudocode

```c
char __fastcall utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned __int64 v3; // r9
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r11
  __int64 v8; // rsi
  unsigned __int64 v9; // r8
  __int64 v10; // rbp
  __int64 v11; // rdi
  unsigned __int64 *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rbx
  _QWORD *v17; // rdx
  __int64 v18; // rdi
  unsigned __int64 *v19; // rcx
  _QWORD *v20; // r9

  v3 = *(_QWORD *)a2;
  v5 = *(unsigned __int8 *)(a2 + 8);
  *a3 = *(_QWORD *)a2;
  a3[1] = &utl::_TreeSentinel;
  a3[2] = &utl::_TreeSentinel;
  *(_QWORD *)(v3 + 8 * v5 + 8) = a3;
  LOBYTE(v5) = -(char)v5;
  v6 = (-(__int64)((_BYTE)v5 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 16;
  if ( *(_QWORD *)(v6 + a1) == v3 )
    *(_QWORD *)(v6 + a1) = a3;
  v7 = 1;
  while ( 1 )
  {
    v8 = *(_QWORD *)v3;
    if ( (*(_QWORD *)v3 & 1) != 0 )
      break;
    v9 = v8 & 0xFFFFFFFFFFFFFFFEuLL;
    v10 = *(_QWORD *)((v8 & 0xFFFFFFFFFFFFFFFEuLL) + 16);
    v11 = -(__int64)(v3 != v10) & 8;
    if ( (**(_BYTE **)((v8 & 0xFFFFFFFFFFFFFFFEuLL) + v11 + 8) & 1) != 0 )
    {
      v12 = *(unsigned __int64 **)(v11 + v3 + 8);
      if ( (*(_BYTE *)v12 & 1) == 0 )
      {
        v13 = 1;
        v14 = 8;
        if ( v10 == v3 )
          v13 = 2;
        v15 = (_QWORD *)v12[v13];
        *v12 = v9;
        if ( *(_QWORD *)(v9 + 16) == v3 )
          v14 = 16;
        *(_QWORD *)(v14 + v9) = v12;
        *(_QWORD *)v3 = v12;
        *v15 &= 1uLL;
        *v15 |= v3;
        *(_QWORD *)(v11 + v3 + 8) = v15;
        v12[v13] = v3;
      }
      v16 = 8;
      v17 = (_QWORD *)(*(_QWORD *)v9 & 0xFFFFFFFFFFFFFFFEuLL);
      v18 = 1;
      if ( v10 == v3 )
        v16 = 16;
      else
        v18 = 2;
      v19 = *(unsigned __int64 **)(v16 + v9);
      v20 = (_QWORD *)v19[v18];
      *v19 = *(_QWORD *)v9 & 0xFFFFFFFFFFFFFFFEuLL | 1;
      if ( (*v17 & 0xFFFFFFFFFFFFFFFEuLL) == v9 )
      {
        *v17 = v19;
      }
      else
      {
        if ( v17[2] == v9 )
          v7 = 2;
        v17[v7] = v19;
      }
      *(_QWORD *)v9 = v19;
      v5 = (v8 ^ *v20) & 0xFFFFFFFFFFFFFFFEuLL;
      *v20 ^= v5;
      *(_QWORD *)(v16 + v9) = v20;
      v19[v18] = v9;
      break;
    }
    **(_QWORD **)(v9 + 8) |= 1uLL;
    v5 = *(_QWORD *)(v9 + 16);
    *(_QWORD *)v5 |= 1uLL;
    v3 = *(_QWORD *)v9 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( a1 == v3 )
      break;
    *(_QWORD *)v9 = v3;
  }
  ++*(_QWORD *)(a1 + 24);
  return v5;
}

```

## disassembly

```asm
0x180003b74  push    rbx
0x180003b76  push    rbp
0x180003b77  push    rsi
0x180003b78  push    rdi
0x180003b79  push    r14
0x180003b7b  mov     r9, [rdx]
0x180003b7e  mov     r10, rcx
0x180003b81  movzx   eax, byte ptr [rdx+8]
0x180003b85  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180003b8c  mov     [r8], r9
0x180003b8f  mov     r14d, 10h
0x180003b95  mov     [r8+8], rcx
0x180003b99  mov     [r8+10h], rcx
0x180003b9d  mov     [r9+rax*8+8], r8
0x180003ba2  neg     al
0x180003ba4  sbb     rdx, rdx
0x180003ba7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180003bab  add     rdx, r14
0x180003bae  cmp     [rdx+r10], r9
0x180003bb2  jnz     short loc_180003BB8
0x180003bb4  mov     [rdx+r10], r8
0x180003bb8  mov     r11d, 8
0x180003bbe  mov     rsi, [r9]
0x180003bc1  test    sil, 1
0x180003bc5  jnz     loc_180003CB0
0x180003bcb  mov     r8, rsi
0x180003bce  and     r8, 0FFFFFFFFFFFFFFFEh
0x180003bd2  mov     rbp, [r8+10h]
0x180003bd6  mov     rax, rbp
0x180003bd9  sub     rax, r9
0x180003bdc  neg     rax
0x180003bdf  sbb     rdi, rdi
0x180003be2  and     rdi, r11
0x180003be5  mov     rax, [r8+rdi+8]
0x180003bea  test    byte ptr [rax], 1
0x180003bed  jnz     short loc_180003C14
0x180003bef  mov     rax, [r8+8]
0x180003bf3  or      qword ptr [rax], 1
0x180003bf7  mov     rax, [r8+10h]
0x180003bfb  or      qword ptr [rax], 1
0x180003bff  mov     r9, [r8]
0x180003c02  and     r9, 0FFFFFFFFFFFFFFFEh
0x180003c06  cmp     r10, r9
0x180003c09  jz      loc_180003CB0
0x180003c0f  mov     [r8], r9
0x180003c12  jmp     short loc_180003BBE
0x180003c14  mov     rbx, [rdi+r9+8]
0x180003c19  test    byte ptr [rbx], 1
0x180003c1c  jnz     short loc_180003C51
0x180003c1e  cmp     rbp, r9
0x180003c21  mov     rdx, r11
0x180003c24  mov     rax, r11
0x180003c27  cmovz   rdx, r14
0x180003c2b  mov     rcx, [rdx+rbx]
0x180003c2f  mov     [rbx], r8
0x180003c32  cmp     [r8+10h], r9
0x180003c36  cmovz   rax, r14
0x180003c3a  mov     [rax+r8], rbx
0x180003c3e  mov     [r9], rbx
0x180003c41  and     qword ptr [rcx], 1
0x180003c45  or      [rcx], r9
0x180003c48  mov     [rdi+r9+8], rcx
0x180003c4d  mov     [rdx+rbx], r9
0x180003c51  mov     rdx, [r8]
0x180003c54  mov     rbx, r11
0x180003c57  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180003c5b  mov     rdi, r11
0x180003c5e  cmp     rbp, r9
0x180003c61  mov     rax, rdx
0x180003c64  cmovz   rbx, r14
0x180003c68  cmovnz  rdi, r14
0x180003c6c  or      rax, 1
0x180003c70  mov     rcx, [rbx+r8]
0x180003c74  mov     r9, [rdi+rcx]
0x180003c78  mov     [rcx], rax
0x180003c7b  mov     rax, [rdx]
0x180003c7e  and     rax, 0FFFFFFFFFFFFFFFEh
0x180003c82  cmp     rax, r8
0x180003c85  jnz     short loc_180003C8C
0x180003c87  mov     [rdx], rcx
0x180003c8a  jmp     short loc_180003C98
0x180003c8c  cmp     [rdx+10h], r8
0x180003c90  cmovz   r11, r14
0x180003c94  mov     [r11+rdx], rcx
0x180003c98  mov     [r8], rcx
0x180003c9b  mov     rax, [r9]
0x180003c9e  xor     rax, rsi
0x180003ca1  and     rax, 0FFFFFFFFFFFFFFFEh
0x180003ca5  xor     [r9], rax
0x180003ca8  mov     [rbx+r8], r9
0x180003cac  mov     [rdi+rcx], r8
0x180003cb0  inc     qword ptr [r10+18h]
0x180003cb4  pop     r14
0x180003cb6  pop     rdi
0x180003cb7  pop     rsi
0x180003cb8  pop     rbp
0x180003cb9  pop     rbx
0x180003cba  retn
```
