# std::vector<float,std::allocator<float>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<float>>>,unsigned __int64,float const &)

- ea: `0x182de6550`
- end: `0x182de6813`
- name: `?_Insert_n@?$vector@MV?$allocator@M@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@M@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@M@std@@@std@@@2@_KAEBM@Z`
- size: `707`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x182de7950`
- `0x1830874b0`
- `0x183281f50`
- `0x183282df0`
- `0x183283c50`
- `0x183284ab0`
- `0x183285990`
- `0x183286870`
- `0x1832877b0`
- `0x1832887b0`
- `0x183289620`

## callees

- `0x182d75f70`
- `0x182da94f0`
- `0x182da9d90`
- `0x182de6550`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de6658`
- `VCRUNTIME140!memmove` at `0x182de6675`
- `VCRUNTIME140!memmove` at `0x182de66f7`
- `VCRUNTIME140!memmove` at `0x182de679a`
- `VCRUNTIME140!memmove` at `0x182de67c0`
- `VCRUNTIME140!memmove` at `0x182de6658`
- `VCRUNTIME140!memmove` at `0x182de6675`
- `VCRUNTIME140!memmove` at `0x182de66f7`
- `VCRUNTIME140!memmove` at `0x182de679a`
- `VCRUNTIME140!memmove` at `0x182de67c0`

## pseudocode

```c
_QWORD *__fastcall std::vector<float>::_Insert_n(CxVector *a1, _QWORD *a2, char *a3, unsigned __int64 a4, int *a5)
{
  _BYTE *v9; // r8
  __int64 v10; // r15
  char *v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // r13
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
  int v24; // xmm0_4
  int v25; // xmm6_4
  char *i; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-88h]
  char v30; // [rsp+20h] [rbp-88h]
  char v31; // [rsp+30h] [rbp-78h]
  CxVector *v32; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-68h]
  __int64 v34; // [rsp+48h] [rbp-60h]
  __int64 v35; // [rsp+50h] [rbp-58h]

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
          std::_Uninit_alloc_fill_n1<float *,unsigned __int64,std::allocator<float>>(
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
        std::_Uninit_alloc_fill_n1<float *,unsigned __int64,std::allocator<float>>(v16 + 4 * v18, a4, a5, a1, v29);
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
0x182de6550  mov     [rsp+Src], r8
0x182de6555  push    rbx
0x182de6556  push    rsi
0x182de6557  push    rdi
0x182de6558  push    r12
0x182de655a  push    r13
0x182de655c  push    r14
0x182de655e  push    r15
0x182de6560  sub     rsp, 70h
0x182de6564  mov     [rsp+0A8h+var_58], 0FFFFFFFFFFFFFFFEh
0x182de656d  movaps  [rsp+0A8h+var_48], xmm6
0x182de6572  mov     rdi, r9
0x182de6575  mov     rax, r8
0x182de6578  mov     r12, rdx
0x182de657b  mov     rbx, rcx
0x182de657e  mov     [rsp+0A8h+var_70], rcx
0x182de6583  mov     r8, [rcx]
0x182de6586  mov     r15, rax
0x182de6589  sub     r15, r8
0x182de658c  sar     r15, 2
0x182de6590  test    r9, r9
0x182de6593  jz      loc_182DE67F0
0x182de6599  mov     rsi, [rcx+8]
0x182de659d  mov     rdx, [rcx+10h]
0x182de65a1  mov     rcx, rdx
0x182de65a4  sub     rcx, rsi
0x182de65a7  sar     rcx, 2
0x182de65ab  cmp     rcx, r9
0x182de65ae  jnb     loc_182DE66BD
0x182de65b4  sub     rsi, r8
0x182de65b7  sar     rsi, 2
0x182de65bb  mov     r9, 3FFFFFFFFFFFFFFFh
0x182de65c5  mov     rax, r9
0x182de65c8  sub     rax, rsi
0x182de65cb  cmp     rax, rdi
0x182de65ce  jnb     short loc_182DE65D9
0x182de65d0  mov     rcx, rbx
0x182de65d3  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de65d9  lea     r13, [rdi+rsi]
0x182de65dd  sub     rdx, r8
0x182de65e0  sar     rdx, 2
0x182de65e4  mov     rax, rdx
0x182de65e7  shr     rax, 1
0x182de65ea  sub     r9, rax
0x182de65ed  add     rax, rdx
0x182de65f0  xor     ecx, ecx
0x182de65f2  cmp     r9, rdx
0x182de65f5  cmovnb  rcx, rax
0x182de65f9  cmp     rcx, r13
0x182de65fc  cmovnb  r13, rcx
0x182de6600  mov     [rsp+0A8h+var_68], r13
0x182de6605  mov     rdx, r13
0x182de6608  mov     rcx, rbx
0x182de660b  call    ?allocate@?$allocator@H@std@@QEAAPEAH_K@Z; std::allocator<int>::allocate(unsigned __int64)
0x182de6610  mov     rsi, rax
0x182de6613  mov     [rsp+0A8h+var_60], rax
0x182de6618  mov     r14, [rsp+0A8h+Src]
0x182de6620  sub     r14, [rbx]
0x182de6623  sar     r14, 2
0x182de6627  lea     rcx, [rax+r14*4]
0x182de662b  movzx   eax, [rsp+0A8h+var_78]
0x182de6630  mov     [rsp+0A8h+var_88], al
0x182de6634  mov     r9, rbx
0x182de6637  mov     r8, [rsp+0A8h+arg_20]
0x182de663f  mov     rdx, rdi
0x182de6642  call    ??$_Uninit_alloc_fill_n1@PEAM_KV?$allocator@M@std@@@std@@YAXPEAM_KPEBMAEAU?$_Wrap_alloc@V?$allocator@M@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<float *,unsigned __int64,std::allocator<float>>(float *,unsigned __int64,float const *,std::_Wrap_alloc<std::allocator<float>> &,std::integral_constant<bool,0>)
0x182de6647  mov     rdx, [rbx]; Src
0x182de664a  mov     r8, [rsp+0A8h+Src]
0x182de6652  sub     r8, rdx; Size
0x182de6655  mov     rcx, rsi; void *
0x182de6658  call    cs:__imp_memmove
0x182de665e  mov     r8, [rbx+8]
0x182de6662  lea     rax, [rdi+r14]
0x182de6666  lea     rcx, [rsi+rax*4]; void *
0x182de666a  mov     rdx, [rsp+0A8h+Src]; Src
0x182de6672  sub     r8, rdx; Size
0x182de6675  call    cs:__imp_memmove
0x182de667b  nop
0x182de667c  mov     rdx, [rbx]
0x182de667f  mov     rax, [rbx+8]
0x182de6683  sub     rax, rdx
0x182de6686  sar     rax, 2
0x182de668a  add     rdi, rax
0x182de668d  test    rdx, rdx
0x182de6690  jz      short loc_182DE66A5
0x182de6692  mov     r8, [rbx+10h]
0x182de6696  sub     r8, rdx
0x182de6699  sar     r8, 2
0x182de669d  mov     rcx, rbx
0x182de66a0  call    ?deallocate@?$allocator@M@std@@QEAAXPEAM_K@Z; std::allocator<float>::deallocate(float *,unsigned __int64)
0x182de66a5  lea     rax, [rsi+r13*4]
0x182de66a9  mov     [rbx+10h], rax
0x182de66ad  lea     rax, [rsi+rdi*4]
0x182de66b1  mov     [rbx+8], rax
0x182de66b5  mov     [rbx], rsi
0x182de66b8  jmp     loc_182DE67F0
0x182de66bd  mov     rcx, rsi
0x182de66c0  sub     rcx, rax
0x182de66c3  sar     rcx, 2
0x182de66c7  lea     r14, ds:0[r9*4]
0x182de66cf  cmp     rcx, rdi
0x182de66d2  jnb     loc_182DE6782
0x182de66d8  mov     rcx, [rsp+0A8h+arg_20]
0x182de66e0  movss   xmm0, dword ptr [rcx]
0x182de66e4  movss   dword ptr [rsp+0A8h+var_70], xmm0
0x182de66ea  lea     rcx, [r14+rax]; void *
0x182de66ee  sub     rsi, rax
0x182de66f1  mov     r8, rsi; Size
0x182de66f4  mov     rdx, rax; Src
0x182de66f7  call    cs:__imp_memmove
0x182de66fd  nop
0x182de66fe  mov     rax, [rbx+8]
0x182de6702  sub     rax, [rsp+0A8h+Src]
0x182de670a  sar     rax, 2
0x182de670e  sub     rdi, rax
0x182de6711  movzx   eax, [rsp+0A8h+var_78]
0x182de6716  mov     [rsp+0A8h+var_88], al
0x182de671a  mov     r9, rbx
0x182de671d  lea     r8, [rsp+0A8h+var_70]
0x182de6722  mov     rdx, rdi
0x182de6725  mov     rcx, [rbx+8]
0x182de6729  call    ??$_Uninit_alloc_fill_n1@PEAM_KV?$allocator@M@std@@@std@@YAXPEAM_KPEBMAEAU?$_Wrap_alloc@V?$allocator@M@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<float *,unsigned __int64,std::allocator<float>>(float *,unsigned __int64,float const *,std::_Wrap_alloc<std::allocator<float>> &,std::integral_constant<bool,0>)
0x182de672e  nop
0x182de672f  add     [rbx+8], r14
0x182de6733  mov     rax, [rbx+8]
0x182de6737  sub     rax, r14
0x182de673a  mov     rdx, [rsp+0A8h+Src]
0x182de6742  xor     ecx, ecx
0x182de6744  mov     r8, rax
0x182de6747  sub     r8, rdx
0x182de674a  add     r8, 3
0x182de674e  shr     r8, 2
0x182de6752  cmp     rdx, rax
0x182de6755  cmova   r8, rcx
0x182de6759  test    r8, r8
0x182de675c  jz      loc_182DE67F0
0x182de6762  movss   xmm0, dword ptr [rsp+0A8h+var_70]
0x182de6768  nop     dword ptr [rax+rax+00000000h]
0x182de6770  movss   dword ptr [rdx], xmm0
0x182de6774  lea     rdx, [rdx+4]
0x182de6778  inc     rcx
0x182de677b  cmp     rcx, r8
0x182de677e  jnz     short loc_182DE6770
0x182de6780  jmp     short loc_182DE67F0
0x182de6782  mov     rax, [rsp+0A8h+arg_20]
0x182de678a  movss   xmm6, dword ptr [rax]
0x182de678e  mov     rdx, rsi
0x182de6791  sub     rdx, r14; Src
0x182de6794  mov     r8, r14; Size
0x182de6797  mov     rcx, rsi; void *
0x182de679a  call    cs:__imp_memmove
0x182de67a0  lea     rax, [r14+rsi]
0x182de67a4  mov     [rbx+8], rax
0x182de67a8  imul    r8, rdi, -4
0x182de67ac  mov     rdx, [rsp+0A8h+Src]; Src
0x182de67b4  sub     r8, rdx
0x182de67b7  add     r8, rsi; Size
0x182de67ba  sub     rsi, r8
0x182de67bd  mov     rcx, rsi; void *
0x182de67c0  call    cs:__imp_memmove
0x182de67c6  mov     r8, [rsp+0A8h+Src]
0x182de67ce  lea     rax, [r14+r8]
0x182de67d2  cmp     r8, rax
0x182de67d5  jz      short loc_182DE67F0
0x182de67d7  movss   dword ptr [r8], xmm6
0x182de67dc  add     r8, 4
0x182de67e0  mov     rdx, [rsp+0A8h+Src]
0x182de67e8  add     rdx, r14
0x182de67eb  cmp     r8, rdx
0x182de67ee  jnz     short loc_182DE67D7
0x182de67f0  mov     rcx, [rbx]
0x182de67f3  lea     rdx, [rcx+r15*4]
0x182de67f7  mov     [r12], rdx
0x182de67fb  mov     rax, r12
0x182de67fe  movaps  xmm6, [rsp+0A8h+var_48]
0x182de6803  add     rsp, 70h
0x182de6807  pop     r15
0x182de6809  pop     r14
0x182de680b  pop     r13
0x182de680d  pop     r12
0x182de680f  pop     rdi
0x182de6810  pop     rsi
0x182de6811  pop     rbx
0x182de6812  retn
```
