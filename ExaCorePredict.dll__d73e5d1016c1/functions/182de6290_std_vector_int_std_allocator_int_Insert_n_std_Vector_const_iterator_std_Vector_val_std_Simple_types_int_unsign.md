# std::vector<int,std::allocator<int>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<int>>>,unsigned __int64,int const &)

- ea: `0x182de6290`
- end: `0x182de6545`
- name: `?_Insert_n@?$vector@HV?$allocator@H@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@H@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@H@std@@@std@@@2@_KAEBH@Z`
- size: `693`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x182de7900`
- `0x183087290`
- `0x183281e40`
- `0x183282040`
- `0x183282ce0`
- `0x183282ee0`
- `0x183283b40`
- `0x183283d40`
- `0x1832849a0`
- `0x183284ba0`
- `0x183285880`
- `0x183285a80`
- `0x183286760`
- `0x183286960`
- `0x183287680`
- `0x1832878c0`
- `0x1832886a0`
- `0x1832888a0`
- `0x183289510`
- `0x183289720`

## callees

- `0x182d75f40`
- `0x182da94f0`
- `0x182da9d90`
- `0x182de6290`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de6393`
- `VCRUNTIME140!memmove` at `0x182de63b0`
- `VCRUNTIME140!memmove` at `0x182de642e`
- `VCRUNTIME140!memmove` at `0x182de64c7`
- `VCRUNTIME140!memmove` at `0x182de64ed`
- `VCRUNTIME140!memmove` at `0x182de6393`
- `VCRUNTIME140!memmove` at `0x182de63b0`
- `VCRUNTIME140!memmove` at `0x182de642e`
- `VCRUNTIME140!memmove` at `0x182de64c7`
- `VCRUNTIME140!memmove` at `0x182de64ed`

## pseudocode

```c
_QWORD *__fastcall std::vector<int>::_Insert_n(CxVector *a1, _QWORD *a2, char *a3, unsigned __int64 a4, int *a5)
{
  _BYTE *v9; // r8
  __int64 v10; // r12
  char *v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rsi
  __int64 v18; // r14
  unsigned __int64 v19; // rdi
  __int64 v20; // r14
  char *v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  int v24; // eax
  int v25; // r15d
  char *i; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-78h]
  char v30; // [rsp+20h] [rbp-78h]
  char v31; // [rsp+30h] [rbp-68h]
  CxVector *v32; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-58h]
  __int64 v34; // [rsp+48h] [rbp-50h]
  __int64 v35; // [rsp+50h] [rbp-48h]

  v35 = -2;
  v32 = a1;
  v9 = *(_BYTE **)a1;
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 2;
  if ( a4 )
  {
    v11 = (char *)*((_QWORD *)a1 + 1);
    if ( (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v11) >> 2 >= a4 )
    {
      v20 = 4 * a4;
      if ( (v11 - a3) >> 2 >= a4 )
      {
        v25 = *a5;
        memmove(v11, &v11[-v20], 4 * a4);
        *((_QWORD *)a1 + 1) = &v11[v20];
        memmove(&a3[4 * a4], a3, (size_t)&v11[-4LL * a4 - (_QWORD)a3]);
        for ( i = a3; i != &a3[v20]; i += 4 )
          *(_DWORD *)i = v25;
      }
      else
      {
        LODWORD(v32) = *a5;
        memmove(&a3[v20], a3, v11 - a3);
        try
        {
          v30 = v31;
          std::_Uninit_alloc_fill_n1<int *,unsigned __int64,std::allocator<int>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 2),
            &v32,
            a1,
            v30);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += v20;
        v21 = a3;
        v22 = 0;
        v23 = (unsigned __int64)(*((_QWORD *)a1 + 1) - v20 - (_QWORD)a3 + 3) >> 2;
        if ( (unsigned __int64)a3 > *((_QWORD *)a1 + 1) - v20 )
          v23 = 0;
        if ( v23 )
        {
          v24 = (int)v32;
          do
          {
            *(_DWORD *)v21 = v24;
            v21 += 4;
            ++v22;
          }
          while ( v22 != v23 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 2;
      if ( 0x3FFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v9) >> 2;
      v15 = 0;
      if ( 0x3FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v33 = v13;
      v16 = std::allocator<int>::allocate(a1, v13);
      v17 = (char *)v16;
      v34 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 2;
      try
      {
        v29 = v31;
        std::_Uninit_alloc_fill_n1<int *,unsigned __int64,std::allocator<int>>(v16 + 4 * v18, a4, a5, a1, v29);
        memmove(v17, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[4 * a4 + 4 * v18], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v32);
        std::_Wrap_alloc<std::allocator<float>>::deallocate(Pointer, v34, v33);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 2) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<float>::deallocate(a1, *(_QWORD *)a1, (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 2);
      *((_QWORD *)a1 + 2) = &v17[4 * v13];
      *((_QWORD *)a1 + 1) = &v17[4 * v19];
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 4 * v10;
  return a2;
}

```

## disassembly

```asm
0x182de6290  mov     [rsp+Src], r8
0x182de6295  push    rbx
0x182de6296  push    rsi
0x182de6297  push    rdi
0x182de6298  push    r12
0x182de629a  push    r13
0x182de629c  push    r14
0x182de629e  push    r15
0x182de62a0  sub     rsp, 60h
0x182de62a4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x182de62ad  mov     rdi, r9
0x182de62b0  mov     rax, r8
0x182de62b3  mov     r13, rdx
0x182de62b6  mov     rbx, rcx
0x182de62b9  mov     [rsp+98h+var_60], rcx
0x182de62be  mov     r8, [rcx]
0x182de62c1  mov     r12, rax
0x182de62c4  sub     r12, r8
0x182de62c7  sar     r12, 2
0x182de62cb  test    r9, r9
0x182de62ce  jz      loc_182DE6527
0x182de62d4  mov     rsi, [rcx+8]
0x182de62d8  mov     rdx, [rcx+10h]
0x182de62dc  mov     rcx, rdx
0x182de62df  sub     rcx, rsi
0x182de62e2  sar     rcx, 2
0x182de62e6  cmp     rcx, r9
0x182de62e9  jnb     loc_182DE63F8
0x182de62ef  sub     rsi, r8
0x182de62f2  sar     rsi, 2
0x182de62f6  mov     r9, 3FFFFFFFFFFFFFFFh
0x182de6300  mov     rax, r9
0x182de6303  sub     rax, rsi
0x182de6306  cmp     rax, rdi
0x182de6309  jnb     short loc_182DE6314
0x182de630b  mov     rcx, rbx
0x182de630e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de6314  lea     r15, [rdi+rsi]
0x182de6318  sub     rdx, r8
0x182de631b  sar     rdx, 2
0x182de631f  mov     rax, rdx
0x182de6322  shr     rax, 1
0x182de6325  sub     r9, rax
0x182de6328  add     rax, rdx
0x182de632b  xor     ecx, ecx
0x182de632d  cmp     r9, rdx
0x182de6330  cmovnb  rcx, rax
0x182de6334  cmp     rcx, r15
0x182de6337  cmovnb  r15, rcx
0x182de633b  mov     [rsp+98h+var_58], r15
0x182de6340  mov     rdx, r15
0x182de6343  mov     rcx, rbx
0x182de6346  call    ?allocate@?$allocator@H@std@@QEAAPEAH_K@Z; std::allocator<int>::allocate(unsigned __int64)
0x182de634b  mov     rsi, rax
0x182de634e  mov     [rsp+98h+var_50], rax
0x182de6353  mov     r14, [rsp+98h+Src]
0x182de635b  sub     r14, [rbx]
0x182de635e  sar     r14, 2
0x182de6362  lea     rcx, [rax+r14*4]
0x182de6366  movzx   eax, [rsp+98h+var_68]
0x182de636b  mov     [rsp+98h+var_78], al
0x182de636f  mov     r9, rbx
0x182de6372  mov     r8, [rsp+98h+arg_20]
0x182de637a  mov     rdx, rdi
0x182de637d  call    ??$_Uninit_alloc_fill_n1@PEAH_KV?$allocator@H@std@@@std@@YAXPEAH_KPEBHAEAU?$_Wrap_alloc@V?$allocator@H@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<int *,unsigned __int64,std::allocator<int>>(int *,unsigned __int64,int const *,std::_Wrap_alloc<std::allocator<int>> &,std::integral_constant<bool,0>)
0x182de6382  mov     rdx, [rbx]; Src
0x182de6385  mov     r8, [rsp+98h+Src]
0x182de638d  sub     r8, rdx; Size
0x182de6390  mov     rcx, rsi; void *
0x182de6393  call    cs:__imp_memmove
0x182de6399  mov     r8, [rbx+8]
0x182de639d  lea     rax, [rdi+r14]
0x182de63a1  lea     rcx, [rsi+rax*4]; void *
0x182de63a5  mov     rdx, [rsp+98h+Src]; Src
0x182de63ad  sub     r8, rdx; Size
0x182de63b0  call    cs:__imp_memmove
0x182de63b6  nop
0x182de63b7  mov     rdx, [rbx]
0x182de63ba  mov     rax, [rbx+8]
0x182de63be  sub     rax, rdx
0x182de63c1  sar     rax, 2
0x182de63c5  add     rdi, rax
0x182de63c8  test    rdx, rdx
0x182de63cb  jz      short loc_182DE63E0
0x182de63cd  mov     r8, [rbx+10h]
0x182de63d1  sub     r8, rdx
0x182de63d4  sar     r8, 2
0x182de63d8  mov     rcx, rbx
0x182de63db  call    ?deallocate@?$allocator@M@std@@QEAAXPEAM_K@Z; std::allocator<float>::deallocate(float *,unsigned __int64)
0x182de63e0  lea     rax, [rsi+r15*4]
0x182de63e4  mov     [rbx+10h], rax
0x182de63e8  lea     rax, [rsi+rdi*4]
0x182de63ec  mov     [rbx+8], rax
0x182de63f0  mov     [rbx], rsi
0x182de63f3  jmp     loc_182DE6527
0x182de63f8  mov     rcx, rsi
0x182de63fb  sub     rcx, rax
0x182de63fe  sar     rcx, 2
0x182de6402  lea     r14, ds:0[r9*4]
0x182de640a  cmp     rcx, rdi
0x182de640d  jnb     loc_182DE64B0
0x182de6413  mov     rcx, [rsp+98h+arg_20]
0x182de641b  mov     edx, [rcx]
0x182de641d  mov     dword ptr [rsp+98h+var_60], edx
0x182de6421  lea     rcx, [r14+rax]; void *
0x182de6425  sub     rsi, rax
0x182de6428  mov     r8, rsi; Size
0x182de642b  mov     rdx, rax; Src
0x182de642e  call    cs:__imp_memmove
0x182de6434  nop
0x182de6435  mov     rax, [rbx+8]
0x182de6439  sub     rax, [rsp+98h+Src]
0x182de6441  sar     rax, 2
0x182de6445  sub     rdi, rax
0x182de6448  movzx   eax, [rsp+98h+var_68]
0x182de644d  mov     [rsp+98h+var_78], al
0x182de6451  mov     r9, rbx
0x182de6454  lea     r8, [rsp+98h+var_60]
0x182de6459  mov     rdx, rdi
0x182de645c  mov     rcx, [rbx+8]
0x182de6460  call    ??$_Uninit_alloc_fill_n1@PEAH_KV?$allocator@H@std@@@std@@YAXPEAH_KPEBHAEAU?$_Wrap_alloc@V?$allocator@H@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<int *,unsigned __int64,std::allocator<int>>(int *,unsigned __int64,int const *,std::_Wrap_alloc<std::allocator<int>> &,std::integral_constant<bool,0>)
0x182de6465  nop
0x182de6466  add     [rbx+8], r14
0x182de646a  mov     rax, [rbx+8]
0x182de646e  sub     rax, r14
0x182de6471  mov     rdx, [rsp+98h+Src]
0x182de6479  xor     ecx, ecx
0x182de647b  mov     r8, rax
0x182de647e  sub     r8, rdx
0x182de6481  add     r8, 3
0x182de6485  shr     r8, 2
0x182de6489  cmp     rdx, rax
0x182de648c  cmova   r8, rcx
0x182de6490  test    r8, r8
0x182de6493  jz      loc_182DE6527
0x182de6499  mov     eax, dword ptr [rsp+98h+var_60]
0x182de649d  nop     dword ptr [rax]
0x182de64a0  mov     [rdx], eax
0x182de64a2  lea     rdx, [rdx+4]
0x182de64a6  inc     rcx
0x182de64a9  cmp     rcx, r8
0x182de64ac  jnz     short loc_182DE64A0
0x182de64ae  jmp     short loc_182DE6527
0x182de64b0  mov     rax, [rsp+98h+arg_20]
0x182de64b8  mov     r15d, [rax]
0x182de64bb  mov     rdx, rsi
0x182de64be  sub     rdx, r14; Src
0x182de64c1  mov     r8, r14; Size
0x182de64c4  mov     rcx, rsi; void *
0x182de64c7  call    cs:__imp_memmove
0x182de64cd  lea     rax, [r14+rsi]
0x182de64d1  mov     [rbx+8], rax
0x182de64d5  imul    r8, rdi, -4
0x182de64d9  mov     rdx, [rsp+98h+Src]; Src
0x182de64e1  sub     r8, rdx
0x182de64e4  add     r8, rsi; Size
0x182de64e7  sub     rsi, r8
0x182de64ea  mov     rcx, rsi; void *
0x182de64ed  call    cs:__imp_memmove
0x182de64f3  mov     r8, [rsp+98h+Src]
0x182de64fb  lea     rax, [r14+r8]
0x182de64ff  cmp     r8, rax
0x182de6502  jz      short loc_182DE6527
0x182de6504  nop     dword ptr [rax+00h]
0x182de6508  nop     dword ptr [rax+rax+00000000h]
0x182de6510  mov     [r8], r15d
0x182de6513  add     r8, 4
0x182de6517  mov     rdx, [rsp+98h+Src]
0x182de651f  add     rdx, r14
0x182de6522  cmp     r8, rdx
0x182de6525  jnz     short loc_182DE6510
0x182de6527  mov     rcx, [rbx]
0x182de652a  lea     rdx, [rcx+r12*4]
0x182de652e  mov     [r13+0], rdx
0x182de6532  mov     rax, r13
0x182de6535  add     rsp, 60h
0x182de6539  pop     r15
0x182de653b  pop     r14
0x182de653d  pop     r13
0x182de653f  pop     r12
0x182de6541  pop     rdi
0x182de6542  pop     rsi
0x182de6543  pop     rbx
0x182de6544  retn
```
