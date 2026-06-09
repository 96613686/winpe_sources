# g_MotionCompRndCtrl(long,long,uchar *,uchar const *,long,long,long,long,long)

- ea: `0x180015d20`
- end: `0x18001601a`
- name: `?g_MotionCompRndCtrl@@YAXJJPEAEPEBEJJJJJ@Z`
- size: `762`
- prototype: `void __fastcall(int, int, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015d20`

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
0x180015d20  mov     [rsp+arg_0], rbx
0x180015d25  mov     [rsp+arg_18], r9
0x180015d2a  mov     [rsp+arg_10], r8
0x180015d2f  push    rbp
0x180015d30  push    rsi
0x180015d31  push    rdi
0x180015d32  push    r12
0x180015d34  push    r13
0x180015d36  push    r14
0x180015d38  push    r15
0x180015d3a  sub     rsp, 40h
0x180015d3e  cmp     [rsp+78h+arg_38], 0
0x180015d46  mov     rbx, r9
0x180015d49  movsxd  r9, [rsp+78h+arg_20]
0x180015d51  mov     rdi, r8
0x180015d54  movsxd  r10, [rsp+78h+arg_28]
0x180015d5c  jz      loc_180015E1E
0x180015d62  mov     r11d, [rsp+78h+arg_40]
0x180015d6a  xor     r8d, r8d
0x180015d6d  cmp     [rsp+78h+arg_30], r8d
0x180015d75  jz      short loc_180015DA8
0x180015d77  test    r11d, r11d
0x180015d7a  jle     loc_180016002
0x180015d80  xor     edx, edx
0x180015d82  movsxd  rcx, edx
0x180015d85  add     edx, 8
0x180015d88  mov     rax, [rcx+rbx]
0x180015d8c  mov     [rdi+rcx], rax
0x180015d90  cmp     edx, r11d
0x180015d93  jl      short loc_180015D82
0x180015d95  add     rbx, r10
0x180015d98  add     rdi, r9
0x180015d9b  inc     r8d
0x180015d9e  cmp     r8d, r11d
0x180015da1  jl      short loc_180015D80
0x180015da3  jmp     loc_180016002
0x180015da8  test    r11d, r11d
0x180015dab  jle     loc_180016002
0x180015db1  mov     r13, r9
0x180015db4  movsxd  r15, ecx
0x180015db7  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180015dc1  mov     r12, r10
0x180015dc4  mov     rbp, 101010101010101h
0x180015dce  movsxd  rax, r8d
0x180015dd1  xor     r14d, r14d
0x180015dd4  lea     rsi, [rax+rdi]
0x180015dd8  lea     r10, [rax+rbx]
0x180015ddc  mov     rcx, [r10]
0x180015ddf  inc     r14d
0x180015de2  mov     rax, [r15+r10]
0x180015de6  mov     rdx, rcx
0x180015de9  and     rcx, [r15+r10]
0x180015ded  add     r10, r12
0x180015df0  shr     rdx, 1
0x180015df3  and     rcx, rbp
0x180015df6  and     rdx, r9
0x180015df9  shr     rax, 1
0x180015dfc  and     rax, r9
0x180015dff  add     rdx, rax
0x180015e02  add     rdx, rcx
0x180015e05  mov     [rsi], rdx
0x180015e08  add     rsi, r13
0x180015e0b  cmp     r14d, r11d
0x180015e0e  jl      short loc_180015DDC
0x180015e10  add     r8d, 8
0x180015e14  cmp     r8d, r11d
0x180015e17  jl      short loc_180015DCE
0x180015e19  jmp     loc_180016002
0x180015e1e  cmp     [rsp+78h+arg_30], 0
0x180015e26  jz      loc_180015EB0
0x180015e2c  mov     r11d, [rsp+78h+arg_40]
0x180015e34  test    r11d, r11d
0x180015e37  jle     loc_180016002
0x180015e3d  xor     r8d, r8d
0x180015e40  mov     r13, r9
0x180015e43  imul    edx, r10d
0x180015e47  mov     r12, r10
0x180015e4a  mov     rbp, 101010101010101h
0x180015e54  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180015e5e  movsxd  r15, edx
0x180015e61  movsxd  rax, r8d
0x180015e64  xor     r14d, r14d
0x180015e67  lea     rsi, [rax+rdi]
0x180015e6b  lea     r10, [rax+rbx]
0x180015e6f  mov     rdx, [r15+r10]
0x180015e73  inc     r14d
0x180015e76  mov     rax, [r10]
0x180015e79  mov     rcx, rdx
0x180015e7c  and     rdx, [r10]
0x180015e7f  add     r10, r12
0x180015e82  shr     rcx, 1
0x180015e85  and     rdx, rbp
0x180015e88  and     rcx, r9
0x180015e8b  shr     rax, 1
0x180015e8e  and     rax, r9
0x180015e91  add     rcx, rax
0x180015e94  add     rcx, rdx
0x180015e97  mov     [rsi], rcx
0x180015e9a  add     rsi, r13
0x180015e9d  cmp     r14d, r11d
0x180015ea0  jl      short loc_180015E6F
0x180015ea2  add     r8d, 8
0x180015ea6  cmp     r8d, r11d
0x180015ea9  jl      short loc_180015E61
0x180015eab  jmp     loc_180016002
0x180015eb0  mov     r15d, [rsp+78h+arg_40]
0x180015eb8  xor     esi, esi
0x180015eba  mov     [rsp+78h+arg_38], esi
0x180015ec1  test    r15d, r15d
0x180015ec4  jle     loc_180016002
0x180015eca  mov     eax, r10d
0x180015ecd  movsxd  r13, ecx
0x180015ed0  imul    eax, edx
0x180015ed3  mov     rbp, 101010101010101h
0x180015edd  mov     [rsp+78h+var_40], r13
0x180015ee2  mov     [rsp+78h+var_60], r10
0x180015ee7  mov     [rsp+78h+var_58], r9
0x180015eec  movsxd  r12, eax
0x180015eef  mov     [rsp+78h+var_48], r12
0x180015ef4  lea     rax, [r12+r13]
0x180015ef8  movsxd  r14, esi
0x180015efb  mov     [rsp+78h+var_70], rdi
0x180015f00  mov     rdi, rbx
0x180015f03  mov     rbx, [rsp+78h+var_70]
0x180015f08  mov     [rsp+78h+var_78], 0
0x180015f0f  lea     rcx, [r14+rax]
0x180015f13  lea     rax, [r14+r13]
0x180015f17  lea     r13, [rcx]
0x180015f1a  mov     [rsp+78h+var_50], rax
0x180015f1f  lea     rsi, [r12+r14]
0x180015f23  mov     rcx, 303030303030303h
0x180015f2d  mov     r12d, [rsp+78h+var_78]
0x180015f31  mov     r8, [rax+rdi]
0x180015f35  inc     r12d
0x180015f38  mov     r9, [rsi+rdi]
0x180015f3c  mov     rdx, r8
0x180015f3f  mov     r10, [rdi+r13]
0x180015f43  and     rdx, rcx
0x180015f46  mov     r11, [r14+rdi]
0x180015f4a  mov     rax, r9
0x180015f4d  add     rdi, [rsp+78h+var_60]
0x180015f52  and     rax, rcx
0x180015f55  add     rdx, rax
0x180015f58  shr     r8, 2
0x180015f5c  mov     rax, r10
0x180015f5f  shr     r9, 2
0x180015f63  and     rax, rcx
0x180015f66  shr     r10, 2
0x180015f6a  add     rdx, rax
0x180015f6d  mov     rcx, r11
0x180015f70  add     rdx, rbp
0x180015f73  shr     r11, 2
0x180015f77  mov     rax, 303030303030303h
0x180015f81  and     rcx, rax
0x180015f84  add     rdx, rcx
0x180015f87  mov     rcx, rax
0x180015f8a  shr     rdx, 2
0x180015f8e  and     rdx, rax
0x180015f91  mov     rax, 3F3F3F3F3F3F3F3Fh
0x180015f9b  and     r8, rax
0x180015f9e  and     r9, rax
0x180015fa1  add     rdx, r8
0x180015fa4  and     r10, rax
0x180015fa7  add     rdx, r9
0x180015faa  and     r11, rax
0x180015fad  mov     rax, [rsp+78h+var_50]
0x180015fb2  add     rdx, r10
0x180015fb5  add     rdx, r11
0x180015fb8  mov     [r14+rbx], rdx
0x180015fbc  add     rbx, [rsp+78h+var_58]
0x180015fc1  cmp     r12d, r15d
0x180015fc4  jl      loc_180015F31
0x180015fca  mov     esi, [rsp+78h+arg_38]
0x180015fd1  mov     r12, [rsp+78h+var_48]
0x180015fd6  add     esi, 8
0x180015fd9  mov     r13, [rsp+78h+var_40]
0x180015fde  mov     rbx, [rsp+78h+arg_18]
0x180015fe6  mov     rdi, [rsp+78h+arg_10]
0x180015fee  mov     [rsp+78h+arg_38], esi
0x180015ff5  lea     rax, [r12+r13]
0x180015ff9  cmp     esi, r15d
0x180015ffc  jl      loc_180015EF8
0x180016002  mov     rbx, [rsp+78h+arg_0]
0x18001600a  add     rsp, 40h
0x18001600e  pop     r15
0x180016010  pop     r14
0x180016012  pop     r13
0x180016014  pop     r12
0x180016016  pop     rdi
0x180016017  pop     rsi
0x180016018  pop     rbp
0x180016019  retn
```
