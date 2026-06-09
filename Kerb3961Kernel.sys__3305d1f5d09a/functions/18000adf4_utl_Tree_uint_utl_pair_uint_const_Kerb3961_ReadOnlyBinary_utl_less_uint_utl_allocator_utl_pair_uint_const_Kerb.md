# utl::_Tree<uint,utl::pair<uint const,Kerb3961::ReadOnlyBinary>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *,bool> const &,utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *)

- ea: `0x18000adf4`
- end: `0x18000af46`
- name: `?_InsertAt@?$_Tree@IU?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@@Z`
- size: `338`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aac8`
- `0x18000b300`

## callees

- `0x18000adf4`

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
  __int64 v11; // rbx
  unsigned __int64 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 *v15; // rcx
  __int64 v16; // rbx
  _QWORD *v17; // rcx
  __int64 v18; // rdi
  unsigned __int64 *v19; // rdx
  unsigned __int64 *v20; // r9

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
        v15 = (unsigned __int64 *)v12[v13];
        *v12 = v9;
        if ( *(_QWORD *)(v9 + 16) == v3 )
          v14 = 16;
        *(_QWORD *)(v14 + v9) = v12;
        *(_QWORD *)v3 = v12;
        *v15 = v3 | *(_DWORD *)v15 & 1;
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
      v20 = (unsigned __int64 *)v19[v18];
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
      v5 = *v20;
      *v20 ^= (v8 ^ *v20) & 0xFFFFFFFFFFFFFFFEuLL;
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
0x18000adf4  push    rbx
0x18000adf6  push    rbp
0x18000adf7  push    rsi
0x18000adf8  push    rdi
0x18000adf9  push    r14
0x18000adfb  mov     r9, [rdx]
0x18000adfe  mov     r10, rcx
0x18000ae01  movzx   eax, byte ptr [rdx+8]
0x18000ae05  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000ae0c  mov     [r8], r9
0x18000ae0f  mov     r14d, 10h
0x18000ae15  mov     [r8+8], rcx
0x18000ae19  mov     [r8+10h], rcx
0x18000ae1d  mov     [r9+rax*8+8], r8
0x18000ae22  neg     al
0x18000ae24  sbb     rdx, rdx
0x18000ae27  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000ae2b  add     rdx, r14
0x18000ae2e  cmp     [rdx+r10], r9
0x18000ae32  jnz     short loc_18000AE38
0x18000ae34  mov     [rdx+r10], r8
0x18000ae38  mov     r11d, 8
0x18000ae3e  mov     rsi, [r9]
0x18000ae41  test    sil, 1
0x18000ae45  jnz     loc_18000AF3A
0x18000ae4b  mov     r8, rsi
0x18000ae4e  and     r8, 0FFFFFFFFFFFFFFFEh
0x18000ae52  mov     rbp, [r8+10h]
0x18000ae56  mov     rax, rbp
0x18000ae59  sub     rax, r9
0x18000ae5c  neg     rax
0x18000ae5f  sbb     rbx, rbx
0x18000ae62  and     rbx, r11
0x18000ae65  mov     rax, [r8+rbx+8]
0x18000ae6a  test    byte ptr [rax], 1
0x18000ae6d  jnz     short loc_18000AE94
0x18000ae6f  mov     rax, [r8+8]
0x18000ae73  or      qword ptr [rax], 1
0x18000ae77  mov     rax, [r8+10h]
0x18000ae7b  or      qword ptr [rax], 1
0x18000ae7f  mov     r9, [r8]
0x18000ae82  and     r9, 0FFFFFFFFFFFFFFFEh
0x18000ae86  cmp     r10, r9
0x18000ae89  jz      loc_18000AF3A
0x18000ae8f  mov     [r8], r9
0x18000ae92  jmp     short loc_18000AE3E
0x18000ae94  mov     rdi, [rbx+r9+8]
0x18000ae99  test    byte ptr [rdi], 1
0x18000ae9c  jnz     short loc_18000AED5
0x18000ae9e  cmp     rbp, r9
0x18000aea1  mov     rdx, r11
0x18000aea4  mov     rax, r11
0x18000aea7  cmovz   rdx, r14
0x18000aeab  mov     rcx, [rdx+rdi]
0x18000aeaf  mov     [rdi], r8
0x18000aeb2  cmp     [r8+10h], r9
0x18000aeb6  cmovz   rax, r14
0x18000aeba  mov     [rax+r8], rdi
0x18000aebe  mov     [r9], rdi
0x18000aec1  mov     eax, [rcx]
0x18000aec3  and     eax, 1
0x18000aec6  or      rax, r9
0x18000aec9  mov     [rcx], rax
0x18000aecc  mov     [rbx+r9+8], rcx
0x18000aed1  mov     [rdx+rdi], r9
0x18000aed5  mov     rcx, [r8]
0x18000aed8  mov     rbx, r11
0x18000aedb  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000aedf  mov     rdi, r11
0x18000aee2  cmp     rbp, r9
0x18000aee5  mov     rax, rcx
0x18000aee8  cmovz   rbx, r14
0x18000aeec  cmovnz  rdi, r14
0x18000aef0  or      rax, 1
0x18000aef4  mov     rdx, [rbx+r8]
0x18000aef8  mov     r9, [rdi+rdx]
0x18000aefc  mov     [rdx], rax
0x18000aeff  mov     rax, [rcx]
0x18000af02  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000af06  cmp     rax, r8
0x18000af09  jnz     short loc_18000AF10
0x18000af0b  mov     [rcx], rdx
0x18000af0e  jmp     short loc_18000AF1C
0x18000af10  cmp     [rcx+10h], r8
0x18000af14  cmovz   r11, r14
0x18000af18  mov     [r11+rcx], rdx
0x18000af1c  mov     [r8], rdx
0x18000af1f  mov     rax, [r9]
0x18000af22  mov     rcx, rax
0x18000af25  xor     rcx, rsi
0x18000af28  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000af2c  xor     rcx, rax
0x18000af2f  mov     [r9], rcx
0x18000af32  mov     [rbx+r8], r9
0x18000af36  mov     [rdi+rdx], r8
0x18000af3a  inc     qword ptr [r10+18h]
0x18000af3e  pop     r14
0x18000af40  pop     rdi
0x18000af41  pop     rsi
0x18000af42  pop     rbp
0x18000af43  pop     rbx
0x18000af44  retn
```
