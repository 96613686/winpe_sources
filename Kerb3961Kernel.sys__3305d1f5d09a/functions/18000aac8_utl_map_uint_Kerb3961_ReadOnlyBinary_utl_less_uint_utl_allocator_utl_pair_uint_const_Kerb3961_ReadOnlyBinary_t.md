# utl::map<uint,Kerb3961::ReadOnlyBinary,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,uchar const *,0>(uint const &,unsigned __int64 const &,uchar const * &&)

- ea: `0x18000aac8`
- end: `0x18000ac2c`
- name: `??$try_emplace@AEB_KPEBE$0A@@?$map@IUReadOnlyBinary@Kerb3961@@U?$less@I@utl@@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@4@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@1@AEBIAEB_K$$QEAPEBE@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b510`

## callees

- `0x18000aac8`
- `0x18000adf4`
- `0x180011ab8`

## pseudocode

```c
const struct std::nothrow_t *__fastcall utl::map<unsigned int,Kerb3961::ReadOnlyBinary,utl::less<unsigned int>,utl::allocator<utl::pair<unsigned int const,Kerb3961::ReadOnlyBinary>>>::try_emplace<unsigned __int64 const &,unsigned char const *,0>(
        unsigned __int64 a1,
        const struct std::nothrow_t *a2,
        unsigned int *a3,
        __int64 *a4,
        _QWORD *a5)
{
  const struct std::nothrow_t *v7; // r14
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  char v11; // di
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  unsigned int v14; // r8d
  _DWORD *v15; // r10
  _DWORD *v16; // rax
  _DWORD *v17; // r8
  __int64 v18; // rax
  const struct std::nothrow_t *result; // rax
  _DWORD *v20; // [rsp+20h] [rbp-38h] BYREF
  char v21; // [rsp+28h] [rbp-30h]

  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  v7 = a2;
  if ( *(_QWORD *)(a1 + 16) != a1 )
  {
    v13 = *(_DWORD **)a1;
    v14 = *a3;
    v10 = 0;
    v11 = 1;
    do
    {
      if ( v14 >= v13[6] )
      {
        v10 = v13;
        LOBYTE(a2) = 1;
      }
      else
      {
        LOBYTE(a2) = 0;
      }
      v15 = v13;
      v13 = *(_DWORD **)&v13[2 * (unsigned __int8)a2 + 2];
    }
    while ( v13 != (_DWORD *)&utl::_TreeSentinel );
    if ( v10 && v10[6] < v14 )
      v10 = 0;
    v20 = v15;
    v21 = (char)a2;
    if ( !v10 )
    {
      v16 = operator new[](0x30u, a2);
      v10 = v16;
      if ( v16 )
      {
        v16[6] = *a3;
        v17 = v16;
        v18 = *a4;
        *((_QWORD *)v10 + 5) = *a5;
        *((_QWORD *)v10 + 4) = v18;
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
  v9 = operator new[](0x30u, a2);
  v10 = v9;
  if ( !v9 )
    goto LABEL_15;
  v9[6] = *a3;
  v11 = 1;
  v12 = *a5;
  *((_QWORD *)v9 + 4) = *a4;
  *((_QWORD *)v9 + 5) = v12;
  *(_QWORD *)v9 = a1 | 1;
  *((_QWORD *)v9 + 1) = &utl::_TreeSentinel;
  *((_QWORD *)v9 + 2) = &utl::_TreeSentinel;
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
0x18000aac8  mov     [rsp+arg_8], rbx
0x18000aacd  mov     [rsp+arg_10], rbp
0x18000aad2  push    rsi
0x18000aad3  push    rdi
0x18000aad4  push    r12
0x18000aad6  push    r14
0x18000aad8  push    r15
0x18000aada  sub     rsp, 30h
0x18000aade  mov     qword ptr [rdx], 0
0x18000aae5  mov     r12, r9
0x18000aae8  mov     byte ptr [rdx+8], 0
0x18000aaec  mov     rbp, r8
0x18000aaef  mov     r14, rdx
0x18000aaf2  mov     r15, rcx
0x18000aaf5  cmp     [rcx+10h], rcx
0x18000aaf9  jnz     short loc_18000AB5F
0x18000aafb  mov     ecx, 30h ; '0'; unsigned __int64
0x18000ab00  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ab05  mov     rbx, rax
0x18000ab08  test    rax, rax
0x18000ab0b  jz      loc_18000AC07
0x18000ab11  mov     ecx, [rbp+0]
0x18000ab14  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000ab1b  mov     [rax+18h], ecx
0x18000ab1e  mov     edi, 1
0x18000ab23  mov     rcx, [rsp+58h+arg_20]
0x18000ab2b  mov     rdx, [rcx]
0x18000ab2e  mov     rcx, [r12]
0x18000ab32  mov     [rax+20h], rcx
0x18000ab36  mov     rcx, r15
0x18000ab39  mov     [rax+28h], rdx
0x18000ab3d  or      rcx, rdi
0x18000ab40  mov     [rax], rcx
0x18000ab43  mov     [rax+8], r9
0x18000ab47  mov     [rax+10h], r9
0x18000ab4b  mov     [r15], rax
0x18000ab4e  mov     [r15+8], rax
0x18000ab52  mov     [r15+10h], rax
0x18000ab56  add     [r15+18h], rdi
0x18000ab5a  jmp     loc_18000AC0A
0x18000ab5f  mov     rcx, [rcx]
0x18000ab62  lea     r9, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18000ab69  mov     r8d, [r8]
0x18000ab6c  xor     ebx, ebx
0x18000ab6e  lea     edi, [rbx+1]
0x18000ab71  cmp     r8d, [rcx+18h]
0x18000ab75  jnb     short loc_18000AB7B
0x18000ab77  xor     dl, dl
0x18000ab79  jmp     short loc_18000AB81
0x18000ab7b  mov     rbx, rcx
0x18000ab7e  mov     dl, dil; struct std::nothrow_t *
0x18000ab81  movzx   eax, dl
0x18000ab84  mov     r10, rcx
0x18000ab87  mov     rcx, [rcx+rax*8+8]
0x18000ab8c  cmp     rcx, r9
0x18000ab8f  jnz     short loc_18000AB71
0x18000ab91  test    rbx, rbx
0x18000ab94  jz      short loc_18000ABA0
0x18000ab96  xor     eax, eax
0x18000ab98  cmp     [rbx+18h], r8d
0x18000ab9c  cmovb   rbx, rax
0x18000aba0  mov     eax, [rsp+58h+var_2F]
0x18000aba4  mov     [rsp+58h+var_2F], eax
0x18000aba8  movzx   eax, [rsp+58h+var_2B]
0x18000abad  mov     [rsp+58h+var_2B], ax
0x18000abb2  mov     al, [rsp+58h+var_29]
0x18000abb6  mov     [rsp+58h+var_29], al
0x18000abba  mov     [rsp+58h+var_38], r10
0x18000abbf  mov     [rsp+58h+var_30], dl
0x18000abc3  test    rbx, rbx
0x18000abc6  jnz     short loc_18000AC07
0x18000abc8  lea     ecx, [rbx+30h]; unsigned __int64
0x18000abcb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000abd0  mov     rbx, rax
0x18000abd3  test    rax, rax
0x18000abd6  jz      short loc_18000AC07
0x18000abd8  mov     eax, [rbp+0]
0x18000abdb  lea     rdx, [rsp+58h+var_38]
0x18000abe0  mov     [rbx+18h], eax
0x18000abe3  mov     r8, rbx
0x18000abe6  mov     rax, [rsp+58h+arg_20]
0x18000abee  mov     rcx, [rax]
0x18000abf1  mov     rax, [r12]
0x18000abf5  mov     [rbx+28h], rcx
0x18000abf9  mov     rcx, r15
0x18000abfc  mov     [rbx+20h], rax
0x18000ac00  call    ?_InsertAt@?$_Tree@IU?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@U?$less@I@2@V?$allocator@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBIUReadOnlyBinary@Kerb3961@@@utl@@@2@@Z; utl::_Tree<uint,utl::pair<uint const,Kerb3961::ReadOnlyBinary>,utl::less<uint>,utl::allocator<utl::pair<uint const,Kerb3961::ReadOnlyBinary>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *,bool> const &,utl::_TreeNode<utl::pair<uint const,Kerb3961::ReadOnlyBinary>> *)
0x18000ac05  jmp     short loc_18000AC0A
0x18000ac07  xor     dil, dil
0x18000ac0a  mov     rax, r14
0x18000ac0d  mov     [rax], rbx
0x18000ac10  mov     [r14+8], dil
0x18000ac14  mov     rbx, [rsp+58h+arg_8]
0x18000ac19  mov     rbp, [rsp+58h+arg_10]
0x18000ac1e  add     rsp, 30h
0x18000ac22  pop     r15
0x18000ac24  pop     r14
0x18000ac26  pop     r12
0x18000ac28  pop     rdi
0x18000ac29  pop     rsi
0x18000ac2a  retn
```
