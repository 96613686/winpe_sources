# av_encryption_init_info_get_side_data

- ea: `0x180036f40`
- end: `0x180037171`
- name: `av_encryption_init_info_get_side_data`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180036dd0`
- `0x180036ed0`
- `0x180036f40`
- `0x1800449c0`
- `0x180078c32`
- `0x18007a960`

## pseudocode

```c
__m128i **__fastcall av_encryption_init_info_get_side_data(unsigned int *a1, unsigned __int64 a2)
{
  unsigned int v2; // edi
  __m128i **v5; // rbx
  unsigned int v6; // eax
  unsigned int *v7; // rsi
  unsigned __int64 v8; // rbp
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // rbp
  const __m128i *v14; // rsi
  __m128i **inited; // rax
  __m128i **v16; // r14
  const __m128i *v17; // rsi
  unsigned __int64 v18; // rbp
  unsigned __int64 v19; // r12
  unsigned __int64 v21; // [rsp+20h] [rbp-58h]
  unsigned __int64 v22; // [rsp+30h] [rbp-48h]
  unsigned __int64 v23; // [rsp+90h] [rbp+18h]
  __m128i **v24; // [rsp+98h] [rbp+20h]

  v2 = 0;
  v5 = 0;
  if ( a1 && a2 >= 4 )
  {
    v6 = byteswap_ulong(*a1);
    v7 = a1 + 1;
    v8 = a2 - 4;
    v22 = v6;
    v9 = 0;
    if ( !v6 )
      return v5;
    while ( v8 >= 0x10 )
    {
      v10 = byteswap_ulong(*v7);
      v23 = byteswap_ulong(v7[1]);
      v11 = byteswap_ulong(v7[2]);
      v21 = v11;
      v12 = byteswap_ulong(v7[3]);
      v13 = v8 - 16;
      if ( v13 < v12 + v10 + v23 * (unsigned int)v11 )
      {
        if ( !v5 )
          return 0;
        if ( *((_DWORD *)v5 + 6) )
        {
          do
            av_free((void *)v5[2]->m128i_i64[v2++]);
          while ( v2 < *((_DWORD *)v5 + 6) );
        }
        goto LABEL_27;
      }
      _mm_lfence();
      v14 = (const __m128i *)(v7 + 4);
      inited = (__m128i **)av_encryption_init_info_alloc((unsigned int)v10, v23, (unsigned int)v11, (unsigned int)v12);
      v16 = inited;
      if ( !inited )
      {
        if ( !v5 )
          return 0;
        if ( *((_DWORD *)v5 + 6) )
        {
          do
            av_free((void *)v5[2]->m128i_i64[v2++]);
          while ( v2 < *((_DWORD *)v5 + 6) );
        }
        goto LABEL_27;
      }
      _mm_lfence();
      if ( v9 )
        v24[6] = (__m128i *)inited;
      else
        v5 = inited;
      v24 = inited;
      sub_18007A960(*inited, v14, v10);
      v17 = (const __m128i *)((char *)v14 + v10);
      v18 = v13 - v10;
      v19 = 0;
      if ( v23 )
      {
        _mm_lfence();
        do
        {
          sub_18007A960((__m128i *)v16[2]->m128i_i64[v19], v17, v21);
          v17 = (const __m128i *)((char *)v17 + v21);
          v18 -= v21;
          ++v19;
        }
        while ( v19 < v23 );
        v2 = 0;
      }
      sub_18007A960(v16[4], v17, v12);
      v7 = (unsigned __int32 *)((char *)v17->m128i_u32 + v12);
      v8 = v18 - v12;
      if ( ++v9 >= v22 )
        return v5;
    }
    if ( !v5 )
      return 0;
    if ( *((_DWORD *)v5 + 6) )
    {
      do
        av_free((void *)v5[2]->m128i_i64[v2++]);
      while ( v2 < *((_DWORD *)v5 + 6) );
    }
LABEL_27:
    av_encryption_init_info_free(v5[6]);
    av_free(*v5);
    av_free(v5[2]);
    av_free(v5[4]);
    av_free(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180036f40  mov     [rsp+arg_8], rbx
0x180036f45  push    rbp
0x180036f46  push    rsi
0x180036f47  push    rdi
0x180036f48  push    r12
0x180036f4a  push    r13
0x180036f4c  push    r14
0x180036f4e  push    r15
0x180036f50  sub     rsp, 40h
0x180036f54  xor     edi, edi
0x180036f56  mov     rbp, rdx
0x180036f59  mov     rsi, rcx
0x180036f5c  mov     ebx, edi
0x180036f5e  test    rcx, rcx
0x180036f61  jz      loc_180037157
0x180036f67  cmp     rdx, 4
0x180036f6b  jb      loc_180037157
0x180036f71  mov     ecx, [rcx]; Number
0x180036f73  call    _byteswap_ulong
0x180036f78  mov     eax, eax
0x180036f7a  add     rsi, 4
0x180036f7e  sub     rbp, 4
0x180036f82  mov     [rsp+78h+var_48], rax
0x180036f87  mov     r15d, edi
0x180036f8a  test    rax, rax
0x180036f8d  jz      loc_1800370BC
0x180036f93  cmp     rbp, 10h
0x180036f97  jb      loc_18003710C
0x180036f9d  mov     ecx, [rsi]; Number
0x180036f9f  call    _byteswap_ulong
0x180036fa4  mov     ecx, [rsi+4]; Number
0x180036fa7  mov     r12d, eax
0x180036faa  call    _byteswap_ulong
0x180036faf  mov     ecx, [rsi+8]; Number
0x180036fb2  mov     eax, eax
0x180036fb4  mov     [rsp+78h+arg_10], rax
0x180036fbc  call    _byteswap_ulong
0x180036fc1  mov     ecx, [rsi+0Ch]; Number
0x180036fc4  mov     r14d, eax
0x180036fc7  mov     [rsp+78h+var_58], r14
0x180036fcc  call    _byteswap_ulong
0x180036fd1  mov     rdx, [rsp+78h+arg_10]
0x180036fd9  lea     rcx, [rbp-10h]
0x180036fdd  mov     r13d, eax
0x180036fe0  mov     rbp, rcx
0x180036fe3  mov     eax, r14d
0x180036fe6  mov     [rsp+78h+var_50], r13
0x180036feb  imul    rax, rdx
0x180036fef  add     rax, r12
0x180036ff2  add     rax, r13
0x180036ff5  cmp     rcx, rax
0x180036ff8  jb      loc_1800370EA
0x180036ffe  lfence
0x180037001  mov     r9d, r13d
0x180037004  mov     r8d, r14d
0x180037007  mov     ecx, r12d
0x18003700a  add     rsi, 10h
0x18003700e  call    av_encryption_init_info_alloc
0x180037013  mov     r14, rax
0x180037016  test    rax, rax
0x180037019  jz      loc_1800370C4
0x18003701f  lfence
0x180037022  test    r15, r15
0x180037025  jnz     short loc_18003702C
0x180037027  mov     rbx, rax
0x18003702a  jmp     short loc_180037038
0x18003702c  mov     rax, [rsp+78h+arg_18]
0x180037034  mov     [rax+30h], r14
0x180037038  mov     rcx, [r14]
0x18003703b  mov     r8, r12
0x18003703e  mov     rdx, rsi
0x180037041  mov     [rsp+78h+arg_18], r14
0x180037049  call    sub_18007A960
0x18003704e  add     rsi, r12
0x180037051  sub     rbp, r12
0x180037054  mov     r12, rdi
0x180037057  cmp     [rsp+78h+arg_10], rdi
0x18003705f  jbe     short loc_180037099
0x180037061  lfence
0x180037064  mov     rdi, [rsp+78h+var_58]
0x180037069  mov     r13, [rsp+78h+arg_10]
0x180037071  mov     rcx, [r14+10h]
0x180037075  mov     r8, rdi
0x180037078  mov     rdx, rsi
0x18003707b  mov     rcx, [rcx+r12*8]
0x18003707f  call    sub_18007A960
0x180037084  add     rsi, rdi
0x180037087  sub     rbp, rdi
0x18003708a  inc     r12
0x18003708d  cmp     r12, r13
0x180037090  jb      short loc_180037071
0x180037092  mov     r13, [rsp+78h+var_50]
0x180037097  xor     edi, edi
0x180037099  mov     rcx, [r14+20h]
0x18003709d  mov     r8, r13
0x1800370a0  mov     rdx, rsi
0x1800370a3  call    sub_18007A960
0x1800370a8  add     rsi, r13
0x1800370ab  sub     rbp, r13
0x1800370ae  inc     r15
0x1800370b1  cmp     r15, [rsp+78h+var_48]
0x1800370b6  jb      loc_180036F93
0x1800370bc  mov     rax, rbx
0x1800370bf  jmp     loc_180037159
0x1800370c4  test    rbx, rbx
0x1800370c7  jz      loc_180037157
0x1800370cd  cmp     [rbx+18h], edi
0x1800370d0  jbe     short loc_18003712C
0x1800370d2  mov     rcx, [rbx+10h]
0x1800370d6  mov     eax, edi
0x1800370d8  mov     rcx, [rcx+rax*8]; Block
0x1800370dc  call    av_free
0x1800370e1  inc     edi
0x1800370e3  cmp     edi, [rbx+18h]
0x1800370e6  jb      short loc_1800370D2
0x1800370e8  jmp     short loc_18003712C
0x1800370ea  test    rbx, rbx
0x1800370ed  jz      short loc_180037157
0x1800370ef  cmp     [rbx+18h], edi
0x1800370f2  jbe     short loc_18003712C
0x1800370f4  mov     rcx, [rbx+10h]
0x1800370f8  mov     eax, edi
0x1800370fa  mov     rcx, [rcx+rax*8]; Block
0x1800370fe  call    av_free
0x180037103  inc     edi
0x180037105  cmp     edi, [rbx+18h]
0x180037108  jb      short loc_1800370F4
0x18003710a  jmp     short loc_18003712C
0x18003710c  test    rbx, rbx
0x18003710f  jz      short loc_180037157
0x180037111  cmp     [rbx+18h], edi
0x180037114  jbe     short loc_18003712C
0x180037116  mov     rcx, [rbx+10h]
0x18003711a  mov     eax, edi
0x18003711c  mov     rcx, [rcx+rax*8]; Block
0x180037120  call    av_free
0x180037125  inc     edi
0x180037127  cmp     edi, [rbx+18h]
0x18003712a  jb      short loc_180037116
0x18003712c  mov     rcx, [rbx+30h]; Block
0x180037130  call    av_encryption_init_info_free
0x180037135  mov     rcx, [rbx]; Block
0x180037138  call    av_free
0x18003713d  mov     rcx, [rbx+10h]; Block
0x180037141  call    av_free
0x180037146  mov     rcx, [rbx+20h]; Block
0x18003714a  call    av_free
0x18003714f  mov     rcx, rbx; Block
0x180037152  call    av_free
0x180037157  xor     eax, eax
0x180037159  mov     rbx, [rsp+78h+arg_8]
0x180037161  add     rsp, 40h
0x180037165  pop     r15
0x180037167  pop     r14
0x180037169  pop     r13
0x18003716b  pop     r12
0x18003716d  pop     rdi
0x18003716e  pop     rsi
0x18003716f  pop     rbp
0x180037170  retn
```
