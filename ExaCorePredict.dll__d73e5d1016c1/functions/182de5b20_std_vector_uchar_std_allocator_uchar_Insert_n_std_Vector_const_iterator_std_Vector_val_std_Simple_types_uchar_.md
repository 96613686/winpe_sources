# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,unsigned __int64,uchar const &)

- ea: `0x182de5b20`
- end: `0x182de5d2a`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@2@_KAEBE@Z`
- size: `522`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x182de79a0`
- `0x183086f70`
- `0x183282130`
- `0x183282520`
- `0x183282fc0`
- `0x1832833a0`
- `0x183283e20`
- `0x183284200`
- `0x183284c90`
- `0x183285080`
- `0x183285b70`
- `0x183285f60`
- `0x183286a50`
- `0x183286e40`
- `0x1832879d0`
- `0x183287e50`
- `0x183288980`
- `0x183288d60`
- `0x183289800`
- `0x183289be0`

## callees

- `0x1815cc2e0`
- `0x182da9c80`
- `0x182de5b20`
- `0x183066770`
- `0x1832dbeb0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de5c09`
- `VCRUNTIME140!memmove` at `0x182de5c25`
- `VCRUNTIME140!memmove` at `0x182de5c81`
- `VCRUNTIME140!memmove` at `0x182de5cd3`
- `VCRUNTIME140!memmove` at `0x182de5cf5`
- `VCRUNTIME140!memmove` at `0x182de5c09`
- `VCRUNTIME140!memmove` at `0x182de5c25`
- `VCRUNTIME140!memmove` at `0x182de5c81`
- `VCRUNTIME140!memmove` at `0x182de5cd3`
- `VCRUNTIME140!memmove` at `0x182de5cf5`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned char>::_Insert_n(CxVector *a1, _QWORD *a2, _BYTE *a3, size_t a4, _BYTE *a5)
{
  _BYTE *v8; // rcx
  signed __int64 v9; // r12
  __int64 v10; // r15
  __int64 v11; // r15
  size_t v12; // rdi
  unsigned __int64 v13; // r8
  size_t v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  char *v17; // r15
  size_t v18; // r14
  int v19; // ebx
  void *v20; // rcx
  size_t v21; // r8
  int v22; // edx
  int v23; // edi
  struct CxVector *Pointer; // rax
  __int64 v27; // [rsp+38h] [rbp-50h]

  v8 = *(_BYTE **)a1;
  v9 = a3 - v8;
  if ( a4 )
  {
    v10 = *((_QWORD *)a1 + 1);
    if ( *((_QWORD *)a1 + 2) - v10 >= a4 )
    {
      if ( v10 - (__int64)a3 >= a4 )
      {
        v23 = (unsigned __int8)*a5;
        memmove(*((void **)a1 + 1), (const void *)(v10 - a4), a4);
        *((_QWORD *)a1 + 1) = a4 + v10;
        memmove(&a3[a4], a3, v10 - a4 - (_QWORD)a3);
        v22 = v23;
        v21 = a4;
        v20 = a3;
      }
      else
      {
        LOBYTE(v19) = *a5;
        memmove(&a3[a4], a3, v10 - (_QWORD)a3);
        try
        {
          v19 = (unsigned __int8)v19;
          memset_0(*((void **)a1 + 1), (unsigned __int8)v19, (size_t)&a3[a4 - *((_QWORD *)a1 + 1)]);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += a4;
        v20 = a3;
        v21 = *((_QWORD *)a1 + 1) - a4 - (_QWORD)a3;
        v22 = v19;
      }
      memset_0(v20, v22, v21);
    }
    else
    {
      v11 = v10 - (_QWORD)v8;
      if ( ~v11 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v12 = a4 + v11;
      v13 = *((_QWORD *)a1 + 2) - (_QWORD)v8;
      v14 = 0;
      if ( ~(v13 >> 1) >= v13 )
        v14 = v13 + (v13 >> 1);
      if ( v14 >= v12 )
        v12 = v14;
      v15 = std::_Wrap_alloc<std::allocator<unsigned char>>::allocate(a1, v12);
      v16 = v15;
      v27 = v15;
      v17 = &a3[-*(_QWORD *)a1];
      try
      {
        memset_0(&v17[v15], (unsigned __int8)*a5, a4);
        memmove((void *)v16, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[a4 + v16], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(a1);
        std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(Pointer, v27, v12);
        throw;
      }
      v18 = *((_QWORD *)a1 + 1) - *(_QWORD *)a1 + a4;
      if ( *(_QWORD *)a1 )
        std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(
          a1,
          *(_QWORD *)a1,
          *((_QWORD *)a1 + 2) - *(_QWORD *)a1);
      *((_QWORD *)a1 + 2) = v16 + v12;
      *((_QWORD *)a1 + 1) = v18 + v16;
      *(_QWORD *)a1 = v16;
    }
  }
  *a2 = v9 + *(_QWORD *)a1;
  return a2;
}

```

## disassembly

```asm
0x182de5b20  mov     [rsp+Src], r8
0x182de5b25  push    rbx
0x182de5b26  push    rsi
0x182de5b27  push    rdi
0x182de5b28  push    r12
0x182de5b2a  push    r13
0x182de5b2c  push    r14
0x182de5b2e  push    r15
0x182de5b30  sub     rsp, 50h
0x182de5b34  mov     [rsp+88h+var_48], 0FFFFFFFFFFFFFFFEh
0x182de5b3d  mov     r14, r9
0x182de5b40  mov     rax, r8
0x182de5b43  mov     r13, rdx
0x182de5b46  mov     rsi, rcx
0x182de5b49  mov     [rsp+88h+var_60], rcx
0x182de5b4e  mov     r9, [rsp+88h+arg_20]
0x182de5b56  mov     [rsp+88h+var_68], r9
0x182de5b5b  mov     rcx, [rcx]
0x182de5b5e  mov     r12, r8
0x182de5b61  sub     r12, rcx
0x182de5b64  test    r14, r14
0x182de5b67  jz      loc_182DE5D0D
0x182de5b6d  mov     r8, [rsi+10h]
0x182de5b71  mov     r15, [rsi+8]
0x182de5b75  mov     rdx, r8
0x182de5b78  sub     rdx, r15
0x182de5b7b  cmp     rdx, r14
0x182de5b7e  jnb     loc_182DE5C65
0x182de5b84  sub     r15, rcx
0x182de5b87  mov     rax, r15
0x182de5b8a  not     rax
0x182de5b8d  cmp     rax, r14
0x182de5b90  jnb     short loc_182DE5B9B
0x182de5b92  mov     rcx, rsi
0x182de5b95  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de5b9b  lea     rdi, [r14+r15]
0x182de5b9f  sub     r8, rcx
0x182de5ba2  mov     rax, r8
0x182de5ba5  shr     rax, 1
0x182de5ba8  mov     rcx, rax
0x182de5bab  not     rcx
0x182de5bae  add     rax, r8
0x182de5bb1  xor     edx, edx
0x182de5bb3  cmp     rcx, r8
0x182de5bb6  cmovnb  rdx, rax
0x182de5bba  cmp     rdx, rdi
0x182de5bbd  cmovnb  rdi, rdx
0x182de5bc1  mov     [rsp+88h+var_58], rdi
0x182de5bc6  mov     rdx, rdi
0x182de5bc9  mov     rcx, rsi
0x182de5bcc  call    ?allocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::allocate(unsigned __int64)
0x182de5bd1  mov     rbx, rax
0x182de5bd4  mov     [rsp+88h+var_50], rax
0x182de5bd9  mov     r15, [rsp+88h+Src]
0x182de5be1  sub     r15, [rsi]
0x182de5be4  lea     rcx, [r15+rax]; void *
0x182de5be8  mov     rax, [rsp+88h+var_68]
0x182de5bed  movzx   edx, byte ptr [rax]; Val
0x182de5bf0  mov     r8, r14; Size
0x182de5bf3  call    memset_0
0x182de5bf8  mov     rdx, [rsi]; Src
0x182de5bfb  mov     r8, [rsp+88h+Src]
0x182de5c03  sub     r8, rdx; Size
0x182de5c06  mov     rcx, rbx; void *
0x182de5c09  call    cs:__imp_memmove
0x182de5c0f  mov     r8, [rsi+8]
0x182de5c13  lea     rcx, [r14+r15]
0x182de5c17  add     rcx, rbx; void *
0x182de5c1a  mov     rdx, [rsp+88h+Src]; Src
0x182de5c22  sub     r8, rdx; Size
0x182de5c25  call    cs:__imp_memmove
0x182de5c2b  nop
0x182de5c2c  mov     rdx, [rsi]
0x182de5c2f  mov     rax, [rsi+8]
0x182de5c33  sub     rax, rdx
0x182de5c36  add     r14, rax
0x182de5c39  test    rdx, rdx
0x182de5c3c  jz      short loc_182DE5C4D
0x182de5c3e  mov     r8, [rsi+10h]
0x182de5c42  sub     r8, rdx
0x182de5c45  mov     rcx, rsi
0x182de5c48  call    ?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)
0x182de5c4d  lea     rax, [rbx+rdi]
0x182de5c51  mov     [rsi+10h], rax
0x182de5c55  lea     rax, [r14+rbx]
0x182de5c59  mov     [rsi+8], rax
0x182de5c5d  mov     [rsi], rbx
0x182de5c60  jmp     loc_182DE5D0D
0x182de5c65  mov     rcx, r15
0x182de5c68  sub     rcx, rax
0x182de5c6b  cmp     rcx, r14
0x182de5c6e  jnb     short loc_182DE5CC0
0x182de5c70  movzx   ebx, byte ptr [r9]
0x182de5c74  lea     rcx, [r14+rax]; void *
0x182de5c78  sub     r15, rax
0x182de5c7b  mov     r8, r15; Size
0x182de5c7e  mov     rdx, rax; Src
0x182de5c81  call    cs:__imp_memmove
0x182de5c87  nop
0x182de5c88  mov     r8, r14
0x182de5c8b  sub     r8, [rsi+8]
0x182de5c8f  add     r8, [rsp+88h+Src]; Size
0x182de5c97  movzx   ebx, bl
0x182de5c9a  mov     edx, ebx; Val
0x182de5c9c  mov     rcx, [rsi+8]; void *
0x182de5ca0  call    memset_0
0x182de5ca5  nop
0x182de5ca6  add     [rsi+8], r14
0x182de5caa  mov     r8, [rsi+8]
0x182de5cae  sub     r8, r14
0x182de5cb1  mov     rcx, [rsp+88h+Src]
0x182de5cb9  sub     r8, rcx
0x182de5cbc  mov     edx, ebx
0x182de5cbe  jmp     short loc_182DE5D08
0x182de5cc0  movzx   edi, byte ptr [r9]
0x182de5cc4  mov     rbx, r15
0x182de5cc7  sub     rbx, r14
0x182de5cca  mov     r8, r14; Size
0x182de5ccd  mov     rdx, rbx; Src
0x182de5cd0  mov     rcx, r15; void *
0x182de5cd3  call    cs:__imp_memmove
0x182de5cd9  lea     rax, [r14+r15]
0x182de5cdd  mov     [rsi+8], rax
0x182de5ce1  mov     rdx, [rsp+88h+Src]; Src
0x182de5ce9  sub     rbx, rdx
0x182de5cec  sub     r15, rbx
0x182de5cef  mov     r8, rbx; Size
0x182de5cf2  mov     rcx, r15; void *
0x182de5cf5  call    cs:__imp_memmove
0x182de5cfb  mov     edx, edi; Val
0x182de5cfd  mov     r8, r14; Size
0x182de5d00  mov     rcx, [rsp+88h+Src]; void *
0x182de5d08  call    memset_0
0x182de5d0d  mov     rdx, [rsi]
0x182de5d10  add     rdx, r12
0x182de5d13  mov     [r13+0], rdx
0x182de5d17  mov     rax, r13
0x182de5d1a  add     rsp, 50h
0x182de5d1e  pop     r15
0x182de5d20  pop     r14
0x182de5d22  pop     r13
0x182de5d24  pop     r12
0x182de5d26  pop     rdi
0x182de5d27  pop     rsi
0x182de5d28  pop     rbx
0x182de5d29  retn
```
