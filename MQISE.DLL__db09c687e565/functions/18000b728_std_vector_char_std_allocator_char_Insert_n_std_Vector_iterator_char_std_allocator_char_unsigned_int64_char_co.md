# std::vector<char,std::allocator<char>>::_Insert_n(std::_Vector_iterator<char,std::allocator<char>>,unsigned __int64,char const &)

- ea: `0x18000b728`
- end: `0x18000b983`
- name: `?_Insert_n@?$vector@DV?$allocator@D@std@@@std@@IEAAXV?$_Vector_iterator@DV?$allocator@D@std@@@2@_KAEBD@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cb9c`

## callees

- `0x180001c0c`
- `0x18000310c`
- `0x18000b728`
- `0x18000bc60`
- `0x18000e61c`
- `0x18000f5c2`

## import_xrefs

- `msvcrt!free` at `0x18000b879`
- `msvcrt!free` at `0x18000b879`
- `msvcrt!memmove_s` at `0x18000b833`
- `msvcrt!memmove_s` at `0x18000b860`
- `msvcrt!memmove_s` at `0x18000b8bb`
- `msvcrt!memmove_s` at `0x18000b905`
- `msvcrt!memmove_s` at `0x18000b929`
- `msvcrt!memmove_s` at `0x18000b833`
- `msvcrt!memmove_s` at `0x18000b860`
- `msvcrt!memmove_s` at `0x18000b8bb`
- `msvcrt!memmove_s` at `0x18000b905`
- `msvcrt!memmove_s` at `0x18000b929`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<char>::_Insert_n(__int64 a1, _BYTE *a2, size_t a3, char *a4)
{
  __int64 v7; // rdx
  size_t v8; // r8
  void **v9; // r14
  unsigned __int64 v10; // rax
  char v11; // r12
  char *v12; // rax
  unsigned __int64 v13; // rsi
  char *v14; // rax
  char *v15; // rax
  unsigned __int64 v16; // rcx
  char *v17; // rax
  int v18; // edx
  char *v19; // r12
  _BYTE *v20; // r8
  signed __int64 v21; // r13
  char *v22; // r13
  _BYTE *v23; // rcx
  char *v24; // r15
  unsigned __int64 v25; // rsi
  size_t v26; // r15
  _BYTE *v27; // rcx
  size_t v28; // r8
  signed __int64 v29; // rsi
  char *v30; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[80]; // [rsp+28h] [rbp-50h] BYREF
  char Val; // [rsp+90h] [rbp+18h]

  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
    v8 = *(_QWORD *)(a1 + 24) - v7;
  else
    v8 = 0;
  if ( !a3 )
    return;
  v9 = (void **)(a1 + 16);
  if ( v7 )
    v10 = (unsigned __int64)*v9 - v7;
  else
    v10 = 0;
  if ( ~v10 < a3 )
    std::vector<char>::_Xlen(a1, v7, v8);
  v11 = *a4;
  Val = *a4;
  if ( v7 )
    v12 = (char *)*v9 - v7;
  else
    v12 = 0;
  if ( v8 < (unsigned __int64)&v12[a3] )
  {
    v13 = 0;
    if ( ~(v8 >> 1) >= v8 )
      v13 = v8 + (v8 >> 1);
    if ( v7 )
      v14 = (char *)*v9 - v7;
    else
      v14 = 0;
    if ( v13 < (unsigned __int64)&v14[a3] )
    {
      if ( v7 )
        v15 = (char *)*v9 - v7;
      else
        v15 = 0;
      v13 = (unsigned __int64)&v15[a3];
    }
    if ( v13 )
    {
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v13) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v16 = v13;
    }
    else
    {
      v16 = 0;
    }
    v17 = (char *)MmAllocate(v16);
    try
    {
      v19 = v17;
      v30 = v17;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = a2 - v20;
      if ( a2 != v20 )
        memmove_s(v17, a2 - v20, v20, a2 - v20);
      v22 = &v19[v21];
      LOBYTE(v18) = Val;
      memset_0(v22, v18, a3);
      if ( *v9 != a2 )
        memmove_s(&v22[a3], (_BYTE *)*v9 - a2, a2, (_BYTE *)*v9 - a2);
    }
    catch ( ... )
    {
      std::allocator<std::_Tree_nod<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::_Node>::deallocate(
        a1,
        v30,
        v13);
      throw;
    }
    v23 = *(_BYTE **)(a1 + 8);
    if ( v23 )
    {
      a3 += (_BYTE *)*v9 - v23;
      free(v23);
    }
    *(_QWORD *)(a1 + 24) = &v19[v13];
    *v9 = &v19[a3];
    *(_QWORD *)(a1 + 8) = v19;
    return;
  }
  v24 = (char *)*v9;
  v25 = (_BYTE *)*v9 - a2;
  if ( v25 >= a3 )
  {
    memmove_s(*v9, a3, &v24[-a3], a3);
    *v9 = &v24[a3];
    v29 = v25 - a3;
    if ( v29 > 0 )
      memmove_s(&v24[-v29], v29, a2, v29);
    if ( a2 > &a2[a3] )
      a3 = 0;
    if ( a3 )
    {
      v28 = a3;
LABEL_50:
      LOBYTE(v7) = v11;
      memset_0(a2, v7, v28);
    }
  }
  else
  {
    if ( v25 )
      memmove_s(&a2[a3], (_BYTE *)*v9 - a2, a2, (_BYTE *)*v9 - a2);
    v26 = &a2[a3] - (_BYTE *)*v9;
    if ( v26 )
    {
      LOBYTE(v7) = v11;
      memset_0(*v9, v7, v26);
    }
    v27 = *v9;
    *v9 = (char *)*v9 + a3;
    v28 = v27 - a2;
    if ( a2 > v27 )
      v28 = 0;
    if ( v28 )
      goto LABEL_50;
  }
}

```

## disassembly

```asm
0x18000b728  mov     [rsp+arg_0], rcx
0x18000b72d  push    rbx
0x18000b72e  push    rsi
0x18000b72f  push    rdi
0x18000b730  push    r12
0x18000b732  push    r13
0x18000b734  push    r14
0x18000b736  push    r15
0x18000b738  sub     rsp, 40h
0x18000b73c  mov     rdi, r8
0x18000b73f  mov     rbx, rdx
0x18000b742  mov     r15, rcx
0x18000b745  mov     rdx, [rcx+8]
0x18000b749  test    rdx, rdx
0x18000b74c  jnz     short loc_18000B753
0x18000b74e  xor     r8d, r8d
0x18000b751  jmp     short loc_18000B75A
0x18000b753  mov     r8, [rcx+18h]
0x18000b757  sub     r8, rdx
0x18000b75a  test    rdi, rdi
0x18000b75d  jz      loc_18000B94F
0x18000b763  lea     r14, [rcx+10h]
0x18000b767  test    rdx, rdx
0x18000b76a  jnz     short loc_18000B770
0x18000b76c  xor     eax, eax
0x18000b76e  jmp     short loc_18000B776
0x18000b770  mov     rax, [r14]
0x18000b773  sub     rax, rdx
0x18000b776  not     rax
0x18000b779  cmp     rax, rdi
0x18000b77c  jb      loc_18000B95F
0x18000b782  mov     r12b, [r9]
0x18000b785  mov     byte ptr [rsp+78h+Val], r12b
0x18000b78d  test    rdx, rdx
0x18000b790  jnz     short loc_18000B796
0x18000b792  xor     eax, eax
0x18000b794  jmp     short loc_18000B79C
0x18000b796  mov     rax, [r14]
0x18000b799  sub     rax, rdx
0x18000b79c  add     rax, rdi
0x18000b79f  cmp     r8, rax
0x18000b7a2  jnb     loc_18000B898
0x18000b7a8  mov     rax, r8
0x18000b7ab  shr     rax, 1
0x18000b7ae  mov     rcx, rax
0x18000b7b1  not     rcx
0x18000b7b4  add     rax, r8
0x18000b7b7  xor     esi, esi
0x18000b7b9  cmp     rcx, r8
0x18000b7bc  cmovnb  rsi, rax
0x18000b7c0  test    rdx, rdx
0x18000b7c3  jnz     short loc_18000B7C9
0x18000b7c5  xor     eax, eax
0x18000b7c7  jmp     short loc_18000B7CF
0x18000b7c9  mov     rax, [r14]
0x18000b7cc  sub     rax, rdx
0x18000b7cf  add     rax, rdi
0x18000b7d2  cmp     rsi, rax
0x18000b7d5  jnb     short loc_18000B7EA
0x18000b7d7  test    rdx, rdx
0x18000b7da  jnz     short loc_18000B7E0
0x18000b7dc  xor     eax, eax
0x18000b7de  jmp     short loc_18000B7E6
0x18000b7e0  mov     rax, [r14]
0x18000b7e3  sub     rax, rdx
0x18000b7e6  lea     rsi, [rax+rdi]
0x18000b7ea  mov     [rsp+78h+arg_18], rsi
0x18000b7f2  test    rsi, rsi
0x18000b7f5  jnz     short loc_18000B7FB
0x18000b7f7  xor     ecx, ecx
0x18000b7f9  jmp     short loc_18000B811
0x18000b7fb  xor     edx, edx
0x18000b7fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b801  div     rsi
0x18000b804  cmp     rax, 1
0x18000b808  jb      loc_18000B965
0x18000b80e  mov     rcx, rsi; unsigned __int64
0x18000b811  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000b816  mov     r12, rax
0x18000b819  mov     [rsp+78h+var_58], rax
0x18000b81e  mov     r8, [r15+8]; Source
0x18000b822  mov     r13, rbx
0x18000b825  sub     r13, r8
0x18000b828  jz      short loc_18000B839
0x18000b82a  mov     r9, r13; SourceSize
0x18000b82d  mov     rdx, r13; DestinationSize
0x18000b830  mov     rcx, rax; Destination
0x18000b833  call    cs:__imp_memmove_s
0x18000b839  add     r13, r12
0x18000b83c  mov     r8, rdi; Size
0x18000b83f  mov     dl, byte ptr [rsp+78h+Val]; Val
0x18000b846  mov     rcx, r13; void *
0x18000b849  call    memset_0
0x18000b84e  mov     rdx, [r14]
0x18000b851  sub     rdx, rbx; DestinationSize
0x18000b854  jz      short loc_18000B867
0x18000b856  lea     rcx, [rdi+r13]; Destination
0x18000b85a  mov     r9, rdx; SourceSize
0x18000b85d  mov     r8, rbx; Source
0x18000b860  call    cs:__imp_memmove_s
0x18000b866  nop
0x18000b867  mov     rcx, [r15+8]; Block
0x18000b86b  test    rcx, rcx
0x18000b86e  jz      short loc_18000B880
0x18000b870  mov     rax, [r14]
0x18000b873  sub     rax, rcx
0x18000b876  add     rdi, rax
0x18000b879  call    cs:__imp_free
0x18000b87f  nop
0x18000b880  lea     rax, [r12+rsi]
0x18000b884  mov     [r15+18h], rax
0x18000b888  lea     rax, [rdi+r12]
0x18000b88c  mov     [r14], rax
0x18000b88f  mov     [r15+8], r12
0x18000b893  jmp     loc_18000B94F
0x18000b898  mov     r15, [r14]
0x18000b89b  mov     rsi, r15
0x18000b89e  sub     rsi, rbx
0x18000b8a1  cmp     rsi, rdi
0x18000b8a4  jnb     short loc_18000B8F6
0x18000b8a6  lea     r15, [rbx+rdi]
0x18000b8aa  test    rsi, rsi
0x18000b8ad  jz      short loc_18000B8C2
0x18000b8af  mov     r9, rsi; SourceSize
0x18000b8b2  mov     r8, rbx; Source
0x18000b8b5  mov     rdx, rsi; DestinationSize
0x18000b8b8  mov     rcx, r15; Destination
0x18000b8bb  call    cs:__imp_memmove_s
0x18000b8c1  nop
0x18000b8c2  sub     r15, [r14]
0x18000b8c5  jz      short loc_18000B8D6
0x18000b8c7  mov     r8, r15; Size
0x18000b8ca  mov     dl, r12b; Val
0x18000b8cd  mov     rcx, [r14]; void *
0x18000b8d0  call    memset_0
0x18000b8d5  nop
0x18000b8d6  mov     rcx, [r14]
0x18000b8d9  lea     rax, [rcx+rdi]
0x18000b8dd  mov     [r14], rax
0x18000b8e0  mov     r8, rcx
0x18000b8e3  sub     r8, rbx
0x18000b8e6  xor     eax, eax
0x18000b8e8  cmp     rbx, rcx
0x18000b8eb  cmova   r8, rax
0x18000b8ef  test    r8, r8
0x18000b8f2  jz      short loc_18000B94F
0x18000b8f4  jmp     short loc_18000B944
0x18000b8f6  mov     r8, r15
0x18000b8f9  sub     r8, rdi; Source
0x18000b8fc  mov     r9, rdi; SourceSize
0x18000b8ff  mov     rdx, rdi; DestinationSize
0x18000b902  mov     rcx, r15; Destination
0x18000b905  call    cs:__imp_memmove_s
0x18000b90b  lea     rax, [r15+rdi]
0x18000b90f  mov     [r14], rax
0x18000b912  sub     rsi, rdi
0x18000b915  test    rsi, rsi
0x18000b918  jle     short loc_18000B92F
0x18000b91a  sub     r15, rsi
0x18000b91d  mov     r9, rsi; SourceSize
0x18000b920  mov     r8, rbx; Source
0x18000b923  mov     rdx, rsi; DestinationSize
0x18000b926  mov     rcx, r15; Destination
0x18000b929  call    cs:__imp_memmove_s
0x18000b92f  lea     rcx, [rbx+rdi]
0x18000b933  xor     eax, eax
0x18000b935  cmp     rbx, rcx
0x18000b938  cmova   rdi, rax
0x18000b93c  test    rdi, rdi
0x18000b93f  jz      short loc_18000B94F
0x18000b941  mov     r8, rdi; Size
0x18000b944  mov     dl, r12b; Val
0x18000b947  mov     rcx, rbx; void *
0x18000b94a  call    memset_0
0x18000b94f  add     rsp, 40h
0x18000b953  pop     r15
0x18000b955  pop     r14
0x18000b957  pop     r13
0x18000b959  pop     r12
0x18000b95b  pop     rdi
0x18000b95c  pop     rsi
0x18000b95d  pop     rbx
0x18000b95e  retn
0x18000b95f  call    ?_Xlen@?$vector@DV?$allocator@D@std@@@std@@KAXXZ; std::vector<char>::_Xlen(void)
0x18000b965  xor     edx, edx; char *
0x18000b967  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000b96c  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000b971  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b978  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000b97d  call    _CxxThrowException_0
```
