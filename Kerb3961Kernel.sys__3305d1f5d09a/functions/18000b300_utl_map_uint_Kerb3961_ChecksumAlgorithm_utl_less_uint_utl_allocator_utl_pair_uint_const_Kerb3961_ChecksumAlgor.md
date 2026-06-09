# utl::map<uint,Kerb3961::ChecksumAlgorithm *,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(uint &&,Kerb3961::ChecksumAlgorithm * &)

- ea: `0x18000b300`
- end: `0x18000b446`
- name: `??$try_emplace@AEAPEAUChecksumAlgorithm@Kerb3961@@$0A@@?$map@IPEAUChecksumAlgorithm@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@_N@1@$$QEAIAEAPEAUChecksumAlgorithm@Kerb3961@@@Z`
- size: `326`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c894`
- `0x180011330`
- `0x180011450`
- `0x180011640`

## callees

- `0x18000adf4`
- `0x18000b300`
- `0x180011ab8`

## pseudocode

```c
const struct std::nothrow_t *__fastcall utl::map<unsigned int,Kerb3961::ChecksumAlgorithm *,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>>::try_emplace<Kerb3961::ChecksumAlgorithm * &,0>(
        __int64 a1,
        const struct std::nothrow_t *a2,
        unsigned int *a3,
        _QWORD *a4)
{
  const struct std::nothrow_t *v6; // r14
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  char v10; // di
  _DWORD *v11; // rcx
  unsigned int v12; // r8d
  _DWORD *v13; // r10
  _DWORD *v14; // rax
  const struct std::nothrow_t *result; // rax
  _DWORD *v16; // [rsp+20h] [rbp-38h] BYREF
  char v17; // [rsp+28h] [rbp-30h]

  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  v6 = a2;
  if ( *(_QWORD *)(a1 + 16) != a1 )
  {
    v11 = *(_DWORD **)a1;
    v12 = *a3;
    v9 = 0;
    v10 = 1;
    do
    {
      if ( v12 >= v11[6] )
      {
        v9 = v11;
        LOBYTE(a2) = 1;
      }
      else
      {
        LOBYTE(a2) = 0;
      }
      v13 = v11;
      v11 = *(_DWORD **)&v11[2 * (unsigned __int8)a2 + 2];
    }
    while ( v11 != (_DWORD *)&utl::_TreeSentinel );
    if ( v9 && v9[6] < v12 )
      v9 = 0;
    v16 = v13;
    v17 = (char)a2;
    if ( !v9 )
    {
      v14 = operator new[](0x28u, a2);
      v9 = v14;
      if ( v14 )
      {
        v14[6] = *a3;
        *((_QWORD *)v14 + 4) = *a4;
        utl::_Tree<unsigned int,utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(
          a1,
          (__int64)&v16,
          v14);
        goto LABEL_16;
      }
    }
LABEL_15:
    v10 = 0;
    goto LABEL_16;
  }
  v8 = operator new[](0x28u, a2);
  v9 = v8;
  if ( !v8 )
    goto LABEL_15;
  v8[6] = *a3;
  v10 = 1;
  *((_QWORD *)v8 + 4) = *a4;
  *(_QWORD *)v8 = a1 | 1;
  *((_QWORD *)v8 + 1) = &utl::_TreeSentinel;
  *((_QWORD *)v8 + 2) = &utl::_TreeSentinel;
  *(_QWORD *)a1 = v8;
  *(_QWORD *)(a1 + 8) = v8;
  *(_QWORD *)(a1 + 16) = v8;
  ++*(_QWORD *)(a1 + 24);
LABEL_16:
  result = v6;
  *(_QWORD *)v6 = v9;
  *((_BYTE *)v6 + 8) = v10;
  return result;
}

```

## disassembly

```asm
0x18000b300  mov     [rsp+arg_8], rbx
0x18000b305  mov     [rsp+arg_10], rbp
0x18000b30a  push    rsi
0x18000b30b  push    rdi
0x18000b30c  push    r12
0x18000b30e  push    r14
0x18000b310  push    r15
0x18000b312  sub     rsp, 30h
0x18000b316  mov     qword ptr [rdx], 0
0x18000b31d  mov     r12, r9
0x18000b320  mov     byte ptr [rdx+8], 0
0x18000b324  mov     rbp, r8
0x18000b327  mov     r14, rdx
0x18000b32a  mov     r15, rcx
0x18000b32d  cmp     [rcx+10h], rcx
0x18000b331  jnz     short loc_18000B388
0x18000b333  mov     ecx, 28h ; '('; unsigned __int64
0x18000b338  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b33d  mov     rbx, rax
0x18000b340  test    rax, rax
0x18000b343  jz      loc_18000B421
0x18000b349  mov     ecx, [rbp+0]
0x18000b34c  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b353  mov     [rax+18h], ecx
0x18000b356  mov     edi, 1
0x18000b35b  mov     rcx, [r12]
0x18000b35f  mov     [rax+20h], rcx
0x18000b363  mov     rcx, r15
0x18000b366  or      rcx, rdi
0x18000b369  mov     [rax], rcx
0x18000b36c  mov     [rax+8], r9
0x18000b370  mov     [rax+10h], r9
0x18000b374  mov     [r15], rax
0x18000b377  mov     [r15+8], rax
0x18000b37b  mov     [r15+10h], rax
0x18000b37f  add     [r15+18h], rdi
0x18000b383  jmp     loc_18000B424
0x18000b388  mov     rcx, [rcx]
0x18000b38b  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000b392  mov     r8d, [r8]
0x18000b395  xor     ebx, ebx
0x18000b397  lea     edi, [rbx+1]
0x18000b39a  cmp     r8d, [rcx+18h]
0x18000b39e  jnb     short loc_18000B3A4
0x18000b3a0  xor     dl, dl
0x18000b3a2  jmp     short loc_18000B3AA
0x18000b3a4  mov     rbx, rcx
0x18000b3a7  mov     dl, dil; struct std::nothrow_t *
0x18000b3aa  movzx   eax, dl
0x18000b3ad  mov     r10, rcx
0x18000b3b0  mov     rcx, [rcx+rax*8+8]
0x18000b3b5  cmp     rcx, r9
0x18000b3b8  jnz     short loc_18000B39A
0x18000b3ba  test    rbx, rbx
0x18000b3bd  jz      short loc_18000B3C9
0x18000b3bf  xor     eax, eax
0x18000b3c1  cmp     [rbx+18h], r8d
0x18000b3c5  cmovb   rbx, rax
0x18000b3c9  mov     eax, [rsp+58h+var_2F]
0x18000b3cd  mov     [rsp+58h+var_2F], eax
0x18000b3d1  movzx   eax, [rsp+58h+var_2B]
0x18000b3d6  mov     [rsp+58h+var_2B], ax
0x18000b3db  mov     al, [rsp+58h+var_29]
0x18000b3df  mov     [rsp+58h+var_29], al
0x18000b3e3  mov     [rsp+58h+var_38], r10
0x18000b3e8  mov     [rsp+58h+var_30], dl
0x18000b3ec  test    rbx, rbx
0x18000b3ef  jnz     short loc_18000B421
0x18000b3f1  lea     ecx, [rbx+28h]; unsigned __int64
0x18000b3f4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b3f9  mov     rbx, rax
0x18000b3fc  test    rax, rax
0x18000b3ff  jz      short loc_18000B421
0x18000b401  mov     eax, [rbp+0]
0x18000b404  lea     rdx, [rsp+58h+var_38]
0x18000b409  mov     [rbx+18h], eax
0x18000b40c  mov     r8, rbx
0x18000b40f  mov     rax, [r12]
0x18000b413  mov     rcx, r15
0x18000b416  mov     [rbx+20h], rax
0x18000b41a  call    ?_InsertAt@?$_Tree@IU?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@@Z; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ReadOnlyBinary>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *,bool> const &,utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *)
0x18000b41f  jmp     short loc_18000B424
0x18000b421  xor     dil, dil
0x18000b424  mov     rax, r14
0x18000b427  mov     [rax], rbx
0x18000b42a  mov     [r14+8], dil
0x18000b42e  mov     rbx, [rsp+58h+arg_8]
0x18000b433  mov     rbp, [rsp+58h+arg_10]
0x18000b438  add     rsp, 30h
0x18000b43c  pop     r15
0x18000b43e  pop     r14
0x18000b440  pop     r12
0x18000b442  pop     rdi
0x18000b443  pop     rsi
0x18000b444  retn
```
