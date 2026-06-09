# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Reallocate_grow_by<`std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Replace<wchar_t>(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,`std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Replace<wchar_t>(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x14000f014`
- end: `0x14000f18d`
- name: `??$_Reallocate_grow_by@V_lambda_1_@?1???$_Replace@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@_K_KQEB_W0@Z@_K_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Replace@_W@01@AEAAAEAV01@0_KQEB_W0@Z@11PEB_W1@Z`
- size: `377`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, __int64, __int64, void *Srca, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000df0c`

## callees

- `0x1400088f4`
- `0x140009527`
- `0x14000d940`
- `0x14000eb3c`
- `0x14000f014`

## pseudocode

```c
void **__fastcall ____Reallocate_grow_by_V_lambda_1___1_____Replace__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23__K_KQEB_W0_Z__K_KPEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Replace__W_01_AEAAAEAV01_0_KQEB_W0_Z_11PEB_W1_Z(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        void *Srca,
        __int64 a7)
{
  char *v7; // rbx
  __int64 v8; // r8
  unsigned __int64 v11; // r14
  char *v12; // rbp
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  void *v16; // rcx
  size_t v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  char *v20; // rbx
  _QWORD *v21; // rsi
  char *v22; // r12
  size_t v23; // r13
  __int64 v24; // rbx
  size_t v25; // rbp
  char *v26; // r15
  char *v27; // rbx
  unsigned __int64 v28; // rdx
  _BYTE *v29; // rcx
  void **result; // rax
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF

  v7 = (char *)Src[2];
  v8 = 0x7FFFFFFFFFFFFFFELL;
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v7 < a2 )
    std::_Xlen_string();
  v11 = (unsigned __int64)Src[3];
  v12 = &v7[a2];
  v13 = (unsigned __int64)&v7[a2] | 7;
  if ( v13 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v14 = v11 >> 1;
    if ( v11 <= 0x7FFFFFFFFFFFFFFELL - (v11 >> 1) )
    {
      v8 = v11 + v14;
      if ( v13 >= v11 + v14 )
        v8 = v13;
    }
  }
  v31 = v8;
  v15 = std::wstring::_Allocate_for_capacity<0>(v13, &v31);
  v16 = (void *)v31;
  v17 = 2 * a4;
  v18 = a5;
  v19 = a7;
  v20 = &v7[-a4 - a5];
  Src[2] = v12;
  v21 = v15;
  Src[3] = v16;
  v22 = (char *)v15 + 2 * a4;
  v23 = 2LL * (_QWORD)v20 + 2;
  v24 = a4 + v18;
  v31 = a4 + v18;
  v25 = 2 * v19;
  v26 = (char *)v15 + 2 * a4 + 2 * v19;
  if ( v11 <= 7 )
  {
    memcpy_0(v15, Src, v17);
    memcpy_0(v22, Srca, v25);
    memcpy_0(v26, (char *)Src + 2 * v24, v23);
  }
  else
  {
    v27 = (char *)*Src;
    memcpy_0(v15, *Src, v17);
    memcpy_0(v22, Srca, v25);
    memcpy_0(v26, &v27[2 * v31], v23);
    v28 = 2 * v11 + 2;
    if ( v28 < 0x1000 )
    {
      v29 = v27;
    }
    else
    {
      v29 = (_BYTE *)*((_QWORD *)v27 - 1);
      if ( (unsigned __int64)(v27 - v29 - 8) > 0x1F )
        __fastfail(5u);
      v28 = 2 * v11 + 41;
    }
    operator delete(v29, v28);
  }
  result = Src;
  *Src = v21;
  return result;
}

```

## disassembly

```asm
0x14000f014  push    rbx
0x14000f016  push    rbp
0x14000f017  push    rsi
0x14000f018  push    rdi
0x14000f019  push    r12
0x14000f01b  push    r13
0x14000f01d  push    r14
0x14000f01f  push    r15
0x14000f021  sub     rsp, 28h
0x14000f025  mov     rbx, [rcx+10h]
0x14000f029  mov     r8, 7FFFFFFFFFFFFFFEh
0x14000f033  mov     rax, r8
0x14000f036  mov     r15, r9
0x14000f039  sub     rax, rbx
0x14000f03c  mov     rdi, rcx
0x14000f03f  cmp     rax, rdx
0x14000f042  jb      loc_14000F187
0x14000f048  mov     r14, [rcx+18h]
0x14000f04c  lea     rbp, [rbx+rdx]
0x14000f050  mov     rcx, rbp
0x14000f053  or      rcx, 7
0x14000f057  cmp     rcx, r8
0x14000f05a  ja      short loc_14000F078
0x14000f05c  mov     rdx, r14
0x14000f05f  mov     rax, r8
0x14000f062  shr     rdx, 1
0x14000f065  sub     rax, rdx
0x14000f068  cmp     r14, rax
0x14000f06b  ja      short loc_14000F078
0x14000f06d  lea     r8, [r14+rdx]
0x14000f071  cmp     rcx, r8
0x14000f074  cmovnb  r8, rcx
0x14000f078  lea     rdx, [rsp+68h+arg_0]
0x14000f07d  mov     [rsp+68h+arg_0], r8
0x14000f082  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x14000f087  mov     rcx, [rsp+68h+arg_0]
0x14000f08c  lea     r8, [r15+r15]; Size
0x14000f090  mov     rdx, [rsp+68h+arg_20]
0x14000f098  sub     rbx, r15
0x14000f09b  mov     r9, [rsp+68h+arg_30]
0x14000f0a3  sub     rbx, rdx
0x14000f0a6  mov     [rdi+10h], rbp
0x14000f0aa  mov     rsi, rax
0x14000f0ad  mov     [rdi+18h], rcx
0x14000f0b1  lea     r12, [r8+rax]
0x14000f0b5  mov     rcx, rsi; void *
0x14000f0b8  lea     r13, ds:2[rbx*2]
0x14000f0c0  lea     rbx, [r15+rdx]
0x14000f0c4  mov     [rsp+68h+arg_0], rbx
0x14000f0c9  lea     rax, [r15+r9]
0x14000f0cd  lea     rbp, [r9+r9]
0x14000f0d1  lea     r15, [rsi+rax*2]
0x14000f0d5  cmp     r14, 7
0x14000f0d9  jbe     short loc_14000F146
0x14000f0db  mov     rbx, [rdi]
0x14000f0de  mov     rdx, rbx; Src
0x14000f0e1  call    memcpy_0
0x14000f0e6  mov     rdx, [rsp+68h+Src]; Src
0x14000f0ee  mov     r8, rbp; Size
0x14000f0f1  mov     rcx, r12; void *
0x14000f0f4  call    memcpy_0
0x14000f0f9  mov     rax, [rsp+68h+arg_0]
0x14000f0fe  mov     r8, r13; Size
0x14000f101  mov     rcx, r15; void *
0x14000f104  lea     rdx, [rbx+rax*2]; Src
0x14000f108  call    memcpy_0
0x14000f10d  lea     rdx, ds:2[r14*2]; unsigned __int64
0x14000f115  cmp     rdx, 1000h
0x14000f11c  jb      short loc_14000F13C
0x14000f11e  mov     rcx, [rbx-8]
0x14000f122  sub     rbx, rcx
0x14000f125  sub     rbx, 8
0x14000f129  cmp     rbx, 1Fh
0x14000f12d  ja      short loc_14000F135
0x14000f12f  add     rdx, 27h ; '''
0x14000f133  jmp     short loc_14000F13F
0x14000f135  mov     ecx, 5
0x14000f13a  int     29h; Win8: RtlFailFast(ecx)
0x14000f13c  mov     rcx, rbx; void *
0x14000f13f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f144  jmp     short loc_14000F170
0x14000f146  mov     rdx, rdi; Src
0x14000f149  call    memcpy_0
0x14000f14e  mov     rdx, [rsp+68h+Src]; Src
0x14000f156  mov     r8, rbp; Size
0x14000f159  mov     rcx, r12; void *
0x14000f15c  call    memcpy_0
0x14000f161  lea     rdx, [rdi+rbx*2]; Src
0x14000f165  mov     r8, r13; Size
0x14000f168  mov     rcx, r15; void *
0x14000f16b  call    memcpy_0
0x14000f170  mov     rax, rdi
0x14000f173  mov     [rax], rsi
0x14000f176  add     rsp, 28h
0x14000f17a  pop     r15
0x14000f17c  pop     r14
0x14000f17e  pop     r13
0x14000f180  pop     r12
0x14000f182  pop     rdi
0x14000f183  pop     rsi
0x14000f184  pop     rbp
0x14000f185  pop     rbx
0x14000f186  retn
0x14000f187  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
