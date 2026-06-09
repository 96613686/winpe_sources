# g_MotionComp(long,long,uchar *,uchar const *,long,long,long,long,long)

- ea: `0x180014ed0`
- end: `0x1800151a6`
- name: `?g_MotionComp@@YAXJJPEAEPEBEJJJJJ@Z`
- size: `726`
- prototype: `void __fastcall(int, int, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014ed0`

## pseudocode

```c
void __fastcall g_MotionComp(
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
  int v15; // ebp
  unsigned __int8 *v16; // rsi
  const unsigned __int8 *v17; // r11
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  __int64 v22; // r15
  int v23; // ebp
  unsigned __int8 *v24; // rsi
  const unsigned __int8 *v25; // r11
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // esi
  __int64 v29; // r15
  __int64 v30; // r12
  __int64 v31; // r13
  __int64 v32; // r14
  int v33; // ebx
  __int64 v34; // r12
  __int64 v35; // rcx
  const unsigned __int8 *v36; // r13
  __int64 v37; // rsi
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r8
  unsigned __int64 v40; // r10
  unsigned __int64 v41; // r11
  const unsigned __int8 *v42; // [rsp+0h] [rbp-78h]
  __int64 v43; // [rsp+38h] [rbp-40h]
  int v46; // [rsp+B8h] [rbp+40h]

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
          v18 = (*(_QWORD *)v17 >> 1) & 0x7F7F7F7F7F7F7F7FLL;
          v19 = ((*(_QWORD *)&v17[v14] >> 1) & 0x7F7F7F7F7F7F7F7FLL)
              + ((*(_QWORD *)v17 | *(_QWORD *)&v17[v14]) & 0x101010101010101LL);
          v17 += a6;
          *(_QWORD *)v16 = v18 + v19;
          v16 += a5;
        }
        while ( v15 < a9 );
        v11 += 8;
      }
      while ( v11 < a9 );
    }
  }
  else
  {
    v20 = a6 * a2;
    if ( a7 )
    {
      v21 = 0;
      if ( a9 > 0 )
      {
        v22 = v20;
        do
        {
          v23 = 0;
          v24 = &v10[v21];
          v25 = &a4[v21];
          do
          {
            ++v23;
            v26 = (*(_QWORD *)v25 >> 1) & 0x7F7F7F7F7F7F7F7FLL;
            v27 = ((*(_QWORD *)&v25[v22] >> 1) & 0x7F7F7F7F7F7F7F7FLL)
                + ((*(_QWORD *)v25 | *(_QWORD *)&v25[v22]) & 0x101010101010101LL);
            v25 += a6;
            *(_QWORD *)v24 = v26 + v27;
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
      v28 = 0;
      v46 = 0;
      if ( a9 > 0 )
      {
        v29 = v20;
        v30 = a1;
        v43 = a1;
        v31 = a1 + (__int64)v20;
        do
        {
          v32 = v28;
          v42 = v9;
          v33 = 0;
          v34 = v28 + v30;
          v35 = v28 + v31;
          v36 = v42;
          v37 = v28 + v29;
          do
          {
            v38 = *(_QWORD *)&v36[v35];
            ++v33;
            v39 = *(_QWORD *)&v36[v37];
            v40 = *(_QWORD *)&v36[v32];
            v41 = *(_QWORD *)&v36[v34];
            v36 += a6;
            *(_QWORD *)&v10[v32] = ((v41 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                                 + ((v40 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                                 + ((v38 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                                 + ((v39 >> 2) & 0x3F3F3F3F3F3F3F3FLL)
                                 + ((((v41 & 0x303030303030303LL)
                                    + (v40 & 0x303030303030303LL)
                                    + (v38 & 0x303030303030303LL)
                                    + (v39 & 0x303030303030303LL)
                                    + 0x202020202020202LL) >> 2)
                                  & 0x303030303030303LL);
            v10 += a5;
          }
          while ( v33 < a9 );
          v29 = v20;
          v28 = v46 + 8;
          v30 = v43;
          v9 = a4;
          v10 = a3;
          v46 = v28;
          v31 = v43 + v20;
        }
        while ( v28 < a9 );
      }
    }
  }
}

```

## disassembly

```asm
0x180014ed0  mov     [rsp+arg_0], rbx
0x180014ed5  mov     [rsp+arg_18], r9
0x180014eda  mov     [rsp+arg_10], r8
0x180014edf  push    rbp
0x180014ee0  push    rsi
0x180014ee1  push    rdi
0x180014ee2  push    r12
0x180014ee4  push    r13
0x180014ee6  push    r14
0x180014ee8  push    r15
0x180014eea  sub     rsp, 40h
0x180014eee  cmp     [rsp+78h+arg_38], 0
0x180014ef6  mov     rbx, r9
0x180014ef9  movsxd  r9, [rsp+78h+arg_20]
0x180014f01  mov     rdi, r8
0x180014f04  movsxd  rax, [rsp+78h+arg_28]
0x180014f0c  jz      loc_180014FCE
0x180014f12  mov     r10d, [rsp+78h+arg_40]
0x180014f1a  xor     r8d, r8d
0x180014f1d  cmp     [rsp+78h+arg_30], r8d
0x180014f25  jz      short loc_180014F5B
0x180014f27  test    r10d, r10d
0x180014f2a  jle     loc_18001518E
0x180014f30  mov     r11, rax
0x180014f33  xor     edx, edx
0x180014f35  movsxd  rcx, edx
0x180014f38  add     edx, 8
0x180014f3b  mov     rax, [rcx+rbx]
0x180014f3f  mov     [rcx+rdi], rax
0x180014f43  cmp     edx, r10d
0x180014f46  jl      short loc_180014F35
0x180014f48  add     rbx, r11
0x180014f4b  add     rdi, r9
0x180014f4e  inc     r8d
0x180014f51  cmp     r8d, r10d
0x180014f54  jl      short loc_180014F33
0x180014f56  jmp     loc_18001518E
0x180014f5b  test    r10d, r10d
0x180014f5e  jle     loc_18001518E
0x180014f64  mov     r13, r9
0x180014f67  movsxd  r15, ecx
0x180014f6a  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180014f74  mov     r12, rax
0x180014f77  mov     r14, 101010101010101h
0x180014f81  movsxd  rax, r8d
0x180014f84  xor     ebp, ebp
0x180014f86  lea     rsi, [rax+rdi]
0x180014f8a  lea     r11, [rax+rbx]
0x180014f8e  mov     rax, [r15+r11]
0x180014f92  inc     ebp
0x180014f94  mov     rdx, [r11]
0x180014f97  mov     rcx, rax
0x180014f9a  or      rcx, rdx
0x180014f9d  shr     rax, 1
0x180014fa0  and     rcx, r14
0x180014fa3  shr     rdx, 1
0x180014fa6  and     rax, r9
0x180014fa9  and     rdx, r9
0x180014fac  add     rcx, rax
0x180014faf  add     r11, r12
0x180014fb2  add     rcx, rdx
0x180014fb5  mov     [rsi], rcx
0x180014fb8  add     rsi, r13
0x180014fbb  cmp     ebp, r10d
0x180014fbe  jl      short loc_180014F8E
0x180014fc0  add     r8d, 8
0x180014fc4  cmp     r8d, r10d
0x180014fc7  jl      short loc_180014F81
0x180014fc9  jmp     loc_18001518E
0x180014fce  imul    edx, eax
0x180014fd1  cmp     [rsp+78h+arg_30], 0
0x180014fd9  jz      short loc_180015059
0x180014fdb  mov     r10d, [rsp+78h+arg_40]
0x180014fe3  xor     r8d, r8d
0x180014fe6  test    r10d, r10d
0x180014fe9  jle     loc_18001518E
0x180014fef  mov     r13, r9
0x180014ff2  movsxd  r15, edx
0x180014ff5  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180014fff  mov     r12, rax
0x180015002  mov     r14, 101010101010101h
0x18001500c  movsxd  rax, r8d
0x18001500f  xor     ebp, ebp
0x180015011  lea     rsi, [rax+rdi]
0x180015015  lea     r11, [rax+rbx]
0x180015019  mov     rax, [r15+r11]
0x18001501d  inc     ebp
0x18001501f  mov     rdx, [r11]
0x180015022  mov     rcx, rax
0x180015025  or      rcx, rdx
0x180015028  shr     rax, 1
0x18001502b  and     rcx, r14
0x18001502e  shr     rdx, 1
0x180015031  and     rax, r9
0x180015034  and     rdx, r9
0x180015037  add     rcx, rax
0x18001503a  add     r11, r12
0x18001503d  add     rcx, rdx
0x180015040  mov     [rsi], rcx
0x180015043  add     rsi, r13
0x180015046  cmp     ebp, r10d
0x180015049  jl      short loc_180015019
0x18001504b  add     r8d, 8
0x18001504f  cmp     r8d, r10d
0x180015052  jl      short loc_18001500C
0x180015054  jmp     loc_18001518E
0x180015059  mov     ebp, [rsp+78h+arg_40]
0x180015060  xor     esi, esi
0x180015062  mov     [rsp+78h+arg_38], esi
0x180015069  test    ebp, ebp
0x18001506b  jle     loc_18001518E
0x180015071  movsxd  r15, edx
0x180015074  movsxd  r12, ecx
0x180015077  mov     [rsp+78h+var_48], r15
0x18001507c  mov     [rsp+78h+var_40], r12
0x180015081  mov     [rsp+78h+var_58], rax
0x180015086  lea     r13, [r12+r15]
0x18001508a  mov     [rsp+78h+var_50], r9
0x18001508f  movsxd  r14, esi
0x180015092  mov     [rsp+78h+var_78], rbx
0x180015096  xor     ebx, ebx
0x180015098  add     r12, r14
0x18001509b  lea     rcx, [r14+r13]
0x18001509f  mov     r13, [rsp+78h+var_78]
0x1800150a3  lea     rsi, [r14+r15]
0x1800150a7  lea     r15, [rcx]
0x1800150aa  mov     rcx, 303030303030303h
0x1800150b4  mov     r9, [r15+r13]
0x1800150b8  inc     ebx
0x1800150ba  mov     r8, [rsi+r13]
0x1800150be  mov     rax, r9
0x1800150c1  mov     r10, [r14+r13]
0x1800150c5  and     rax, rcx
0x1800150c8  mov     r11, [r12+r13]
0x1800150cc  mov     rdx, r8
0x1800150cf  add     r13, [rsp+78h+var_58]
0x1800150d4  and     rdx, rcx
0x1800150d7  add     rdx, rax
0x1800150da  shr     r8, 2
0x1800150de  mov     rax, r10
0x1800150e1  shr     r9, 2
0x1800150e5  and     rax, rcx
0x1800150e8  shr     r10, 2
0x1800150ec  add     rdx, rax
0x1800150ef  mov     rcx, r11
0x1800150f2  mov     rax, 303030303030303h
0x1800150fc  shr     r11, 2
0x180015100  and     rcx, rax
0x180015103  mov     rax, 202020202020202h
0x18001510d  add     rdx, rax
0x180015110  mov     rax, 3F3F3F3F3F3F3F3Fh
0x18001511a  add     rdx, rcx
0x18001511d  and     r8, rax
0x180015120  shr     rdx, 2
0x180015124  and     r9, rax
0x180015127  and     r10, rax
0x18001512a  and     r11, rax
0x18001512d  mov     rcx, 303030303030303h
0x180015137  and     rdx, rcx
0x18001513a  add     rdx, r8
0x18001513d  add     rdx, r9
0x180015140  add     rdx, r10
0x180015143  add     rdx, r11
0x180015146  mov     [r14+rdi], rdx
0x18001514a  add     rdi, [rsp+78h+var_50]
0x18001514f  cmp     ebx, ebp
0x180015151  jl      loc_1800150B4
0x180015157  mov     esi, [rsp+78h+arg_38]
0x18001515e  mov     r15, [rsp+78h+var_48]
0x180015163  add     esi, 8
0x180015166  mov     r12, [rsp+78h+var_40]
0x18001516b  mov     rbx, [rsp+78h+arg_18]
0x180015173  mov     rdi, [rsp+78h+arg_10]
0x18001517b  mov     [rsp+78h+arg_38], esi
0x180015182  lea     r13, [r12+r15]
0x180015186  cmp     esi, ebp
0x180015188  jl      loc_18001508F
0x18001518e  mov     rbx, [rsp+78h+arg_0]
0x180015196  add     rsp, 40h
0x18001519a  pop     r15
0x18001519c  pop     r14
0x18001519e  pop     r13
0x1800151a0  pop     r12
0x1800151a2  pop     rdi
0x1800151a3  pop     rsi
0x1800151a4  pop     rbp
0x1800151a5  retn
```
