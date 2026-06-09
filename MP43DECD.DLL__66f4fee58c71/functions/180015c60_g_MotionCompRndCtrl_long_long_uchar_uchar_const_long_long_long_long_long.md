# g_MotionCompRndCtrl(long,long,uchar *,uchar const *,long,long,long,long,long)

- ea: `0x180015c60`
- end: `0x180015f5a`
- name: `?g_MotionCompRndCtrl@@YAXJJPEAEPEBEJJJJJ@Z`
- size: `762`
- prototype: `void __fastcall(int, int, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015c60`

## pseudocode

```c
void __fastcall g_MotionCompRndCtrl(
        int a1,
        int a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  const unsigned __int8 *v9; // rbx
  unsigned __int8 *v10; // rdi
  int v11; // r8d
  int i; // edx
  __int64 v13; // rcx
  __int64 v14; // r15
  int v15; // r14d
  unsigned __int8 *v16; // rsi
  const unsigned __int8 *v17; // r10
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // r8d
  __int64 v22; // r15
  int v23; // r14d
  unsigned __int8 *v24; // rsi
  const unsigned __int8 *v25; // r10
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // esi
  __int64 v30; // r13
  __int64 v31; // r12
  __int64 v32; // rax
  __int64 v33; // r14
  const unsigned __int8 *v34; // rdi
  unsigned __int8 *v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rsi
  int v39; // r12d
  unsigned __int64 v40; // r8
  unsigned __int64 v41; // r9
  unsigned __int64 v42; // r10
  unsigned __int64 v43; // r11
  unsigned __int8 *v44; // [rsp+8h] [rbp-70h]
  __int64 v45; // [rsp+28h] [rbp-50h]
  __int64 v46; // [rsp+30h] [rbp-48h]
  __int64 v47; // [rsp+38h] [rbp-40h]
  int v50; // [rsp+B8h] [rbp+40h]

  v9 = a4;
  v10 = a3;
  if ( a8 )
  {
    v11 = 0;
    if ( a7 )
    {
      if ( a9 > 0 )
      {
        do
        {
          for ( i = 0; i < a9; i += 8 )
          {
            v13 = i;
            *(_QWORD *)&v10[v13] = *(_QWORD *)&v9[v13];
          }
          v9 += a6;
          v10 += a5;
          ++v11;
        }
        while ( v11 < a9 );
      }
    }
    else if ( a9 > 0 )
    {
      v14 = a1;
      do
      {
        v15 = 0;
        v16 = &v10[v11];
        v17 = &a4[v11];
        do
        {
          ++v15;
          v18 = *(_QWORD *)&v17[v14];
          v19 = *(_QWORD *)v17;
          v20 = v18 & *(_QWORD *)v17;
          v17 += a6;
          *(_QWORD *)v16 = (v20 & 0x101010101010101LL)
                         + ((v18 >> 1) & 0x7F7F7F7F7F7F7F7FLL)
                         + ((v19 >> 1) & 0x7F7F7F7F7F7F7F7FLL);
          v16 += a5;
        }
        while ( v15 < a9 );
        v11 += 8;
      }
      while ( v11 < a9 );
    }
  }
  else if ( a7 )
  {
    if ( a9 > 0 )
    {
      v21 = 0;
      v22 = a6 * a2;
      do
      {
        v23 = 0;
        v24 = &v10[v21];
        v25 = &a4[v21];
        do
        {
          ++v23;
          v26 = *(_QWORD *)v25;
          v27 = *(_QWORD *)&v25[v22];
          v28 = *(_QWORD *)v25 & v27;
          v25 += a6;
          *(_QWORD *)v24 = (v28 & 0x101010101010101LL)
                         + ((v26 >> 1) & 0x7F7F7F7F7F7F7F7FLL)
                         + ((v27 >> 1) & 0x7F7F7F7F7F7F7F7FLL);
          v24 += a5;
        }
        while ( v23 < a9 );
        v21 += 8;
      }
      while ( v21 < a9 );
    }
  }
  else
  {
    v29 = 0;
    v50 = 0;
    if ( a9 > 0 )
    {
      v30 = a1;
      v47 = a1;
      v31 = a2 * a6;
      v46 = v31;
      v32 = v31 + a1;
      do
      {
        v33 = v29;
        v44 = v10;
        v34 = v9;
        v35 = v44;
        v36 = v29 + v32;
        v37 = v29 + v30;
        v45 = v37;
        v38 = v31 + v29;
        v39 = 0;
        do
        {
          v40 = *(_QWORD *)&v34[v37];
          ++v39;
          v41 = *(_QWORD *)&v34[v38];
          v42 = *(_QWORD *)&v34[v36];
          v43 = *(_QWORD *)&v34[v33];
          v34 += a6;
          v37 = v45;
          *(_QWORD *)&v35[v33] = ((v43 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                               + ((v42 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                               + ((v41 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                               + ((v40 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                               + ((((v43 & 0x303030303030303LL)
                                  + (v42 & 0x303030303030303LL)
                                  + (v41 & 0x303030303030303LL)
                                  + (v40 & 0x303030303030303LL)
                                  + 0x101010101010101LL) >> 2)
                                & 0x303030303030303LL);
          v35 += a5;
        }
        while ( v39 < a9 );
        v31 = v46;
        v29 = v50 + 8;
        v30 = v47;
        v9 = a4;
        v10 = a3;
        v50 = v29;
        v32 = v46 + v47;
      }
      while ( v29 < a9 );
    }
  }
}

```

## disassembly

```asm
0x180015c60  mov     [rsp+arg_0], rbx
0x180015c65  mov     [rsp+arg_18], r9
0x180015c6a  mov     [rsp+arg_10], r8
0x180015c6f  push    rbp
0x180015c70  push    rsi
0x180015c71  push    rdi
0x180015c72  push    r12
0x180015c74  push    r13
0x180015c76  push    r14
0x180015c78  push    r15
0x180015c7a  sub     rsp, 40h
0x180015c7e  cmp     [rsp+78h+arg_38], 0
0x180015c86  mov     rbx, r9
0x180015c89  movsxd  r9, [rsp+78h+arg_20]
0x180015c91  mov     rdi, r8
0x180015c94  movsxd  r10, [rsp+78h+arg_28]
0x180015c9c  jz      loc_180015D5E
0x180015ca2  mov     r11d, [rsp+78h+arg_40]
0x180015caa  xor     r8d, r8d
0x180015cad  cmp     [rsp+78h+arg_30], r8d
0x180015cb5  jz      short loc_180015CE8
0x180015cb7  test    r11d, r11d
0x180015cba  jle     loc_180015F42
0x180015cc0  xor     edx, edx
0x180015cc2  movsxd  rcx, edx
0x180015cc5  add     edx, 8
0x180015cc8  mov     rax, [rcx+rbx]
0x180015ccc  mov     [rdi+rcx], rax
0x180015cd0  cmp     edx, r11d
0x180015cd3  jl      short loc_180015CC2
0x180015cd5  add     rbx, r10
0x180015cd8  add     rdi, r9
0x180015cdb  inc     r8d
0x180015cde  cmp     r8d, r11d
0x180015ce1  jl      short loc_180015CC0
0x180015ce3  jmp     loc_180015F42
0x180015ce8  test    r11d, r11d
0x180015ceb  jle     loc_180015F42
0x180015cf1  mov     r13, r9
0x180015cf4  movsxd  r15, ecx
0x180015cf7  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180015d01  mov     r12, r10
0x180015d04  mov     rbp, 101010101010101h
0x180015d0e  movsxd  rax, r8d
0x180015d11  xor     r14d, r14d
0x180015d14  lea     rsi, [rax+rdi]
0x180015d18  lea     r10, [rax+rbx]
0x180015d1c  mov     rcx, [r10]
0x180015d1f  inc     r14d
0x180015d22  mov     rax, [r15+r10]
0x180015d26  mov     rdx, rcx
0x180015d29  and     rcx, [r15+r10]
0x180015d2d  add     r10, r12
0x180015d30  shr     rdx, 1
0x180015d33  and     rcx, rbp
0x180015d36  and     rdx, r9
0x180015d39  shr     rax, 1
0x180015d3c  and     rax, r9
0x180015d3f  add     rdx, rax
0x180015d42  add     rdx, rcx
0x180015d45  mov     [rsi], rdx
0x180015d48  add     rsi, r13
0x180015d4b  cmp     r14d, r11d
0x180015d4e  jl      short loc_180015D1C
0x180015d50  add     r8d, 8
0x180015d54  cmp     r8d, r11d
0x180015d57  jl      short loc_180015D0E
0x180015d59  jmp     loc_180015F42
0x180015d5e  cmp     [rsp+78h+arg_30], 0
0x180015d66  jz      loc_180015DF0
0x180015d6c  mov     r11d, [rsp+78h+arg_40]
0x180015d74  test    r11d, r11d
0x180015d77  jle     loc_180015F42
0x180015d7d  xor     r8d, r8d
0x180015d80  mov     r13, r9
0x180015d83  imul    edx, r10d
0x180015d87  mov     r12, r10
0x180015d8a  mov     rbp, 101010101010101h
0x180015d94  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180015d9e  movsxd  r15, edx
0x180015da1  movsxd  rax, r8d
0x180015da4  xor     r14d, r14d
0x180015da7  lea     rsi, [rax+rdi]
0x180015dab  lea     r10, [rax+rbx]
0x180015daf  mov     rdx, [r15+r10]
0x180015db3  inc     r14d
0x180015db6  mov     rax, [r10]
0x180015db9  mov     rcx, rdx
0x180015dbc  and     rdx, [r10]
0x180015dbf  add     r10, r12
0x180015dc2  shr     rcx, 1
0x180015dc5  and     rdx, rbp
0x180015dc8  and     rcx, r9
0x180015dcb  shr     rax, 1
0x180015dce  and     rax, r9
0x180015dd1  add     rcx, rax
0x180015dd4  add     rcx, rdx
0x180015dd7  mov     [rsi], rcx
0x180015dda  add     rsi, r13
0x180015ddd  cmp     r14d, r11d
0x180015de0  jl      short loc_180015DAF
0x180015de2  add     r8d, 8
0x180015de6  cmp     r8d, r11d
0x180015de9  jl      short loc_180015DA1
0x180015deb  jmp     loc_180015F42
0x180015df0  mov     r15d, [rsp+78h+arg_40]
0x180015df8  xor     esi, esi
0x180015dfa  mov     [rsp+78h+arg_38], esi
0x180015e01  test    r15d, r15d
0x180015e04  jle     loc_180015F42
0x180015e0a  mov     eax, r10d
0x180015e0d  movsxd  r13, ecx
0x180015e10  imul    eax, edx
0x180015e13  mov     rbp, 101010101010101h
0x180015e1d  mov     [rsp+78h+var_40], r13
0x180015e22  mov     [rsp+78h+var_60], r10
0x180015e27  mov     [rsp+78h+var_58], r9
0x180015e2c  movsxd  r12, eax
0x180015e2f  mov     [rsp+78h+var_48], r12
0x180015e34  lea     rax, [r12+r13]
0x180015e38  movsxd  r14, esi
0x180015e3b  mov     [rsp+78h+var_70], rdi
0x180015e40  mov     rdi, rbx
0x180015e43  mov     rbx, [rsp+78h+var_70]
0x180015e48  mov     [rsp+78h+var_78], 0
0x180015e4f  lea     rcx, [r14+rax]
0x180015e53  lea     rax, [r14+r13]
0x180015e57  lea     r13, [rcx]
0x180015e5a  mov     [rsp+78h+var_50], rax
0x180015e5f  lea     rsi, [r12+r14]
0x180015e63  mov     rcx, 303030303030303h
0x180015e6d  mov     r12d, [rsp+78h+var_78]
0x180015e71  mov     r8, [rax+rdi]
0x180015e75  inc     r12d
0x180015e78  mov     r9, [rsi+rdi]
0x180015e7c  mov     rdx, r8
0x180015e7f  mov     r10, [rdi+r13]
0x180015e83  and     rdx, rcx
0x180015e86  mov     r11, [r14+rdi]
0x180015e8a  mov     rax, r9
0x180015e8d  add     rdi, [rsp+78h+var_60]
0x180015e92  and     rax, rcx
0x180015e95  add     rdx, rax
0x180015e98  shr     r8, 2
0x180015e9c  mov     rax, r10
0x180015e9f  shr     r9, 2
0x180015ea3  and     rax, rcx
0x180015ea6  shr     r10, 2
0x180015eaa  add     rdx, rax
0x180015ead  mov     rcx, r11
0x180015eb0  add     rdx, rbp
0x180015eb3  shr     r11, 2
0x180015eb7  mov     rax, 303030303030303h
0x180015ec1  and     rcx, rax
0x180015ec4  add     rdx, rcx
0x180015ec7  mov     rcx, rax
0x180015eca  shr     rdx, 2
0x180015ece  and     rdx, rax
0x180015ed1  mov     rax, 3F3F3F3F3F3F3F3Fh
0x180015edb  and     r8, rax
0x180015ede  and     r9, rax
0x180015ee1  add     rdx, r8
0x180015ee4  and     r10, rax
0x180015ee7  add     rdx, r9
0x180015eea  and     r11, rax
0x180015eed  mov     rax, [rsp+78h+var_50]
0x180015ef2  add     rdx, r10
0x180015ef5  add     rdx, r11
0x180015ef8  mov     [r14+rbx], rdx
0x180015efc  add     rbx, [rsp+78h+var_58]
0x180015f01  cmp     r12d, r15d
0x180015f04  jl      loc_180015E71
0x180015f0a  mov     esi, [rsp+78h+arg_38]
0x180015f11  mov     r12, [rsp+78h+var_48]
0x180015f16  add     esi, 8
0x180015f19  mov     r13, [rsp+78h+var_40]
0x180015f1e  mov     rbx, [rsp+78h+arg_18]
0x180015f26  mov     rdi, [rsp+78h+arg_10]
0x180015f2e  mov     [rsp+78h+arg_38], esi
0x180015f35  lea     rax, [r12+r13]
0x180015f39  cmp     esi, r15d
0x180015f3c  jl      loc_180015E38
0x180015f42  mov     rbx, [rsp+78h+arg_0]
0x180015f4a  add     rsp, 40h
0x180015f4e  pop     r15
0x180015f50  pop     r14
0x180015f52  pop     r13
0x180015f54  pop     r12
0x180015f56  pop     rdi
0x180015f57  pop     rsi
0x180015f58  pop     rbp
0x180015f59  retn
```
