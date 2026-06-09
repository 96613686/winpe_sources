# g_MotionComp(long,long,uchar *,uchar const *,long,long,long,long,long)

- ea: `0x180014f90`
- end: `0x180015266`
- name: `?g_MotionComp@@YAXJJPEAEPEBEJJJJJ@Z`
- size: `726`
- prototype: `void __fastcall(int, int, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014f90`

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
0x180014f90  mov     [rsp+arg_0], rbx
0x180014f95  mov     [rsp+arg_18], r9
0x180014f9a  mov     [rsp+arg_10], r8
0x180014f9f  push    rbp
0x180014fa0  push    rsi
0x180014fa1  push    rdi
0x180014fa2  push    r12
0x180014fa4  push    r13
0x180014fa6  push    r14
0x180014fa8  push    r15
0x180014faa  sub     rsp, 40h
0x180014fae  cmp     [rsp+78h+arg_38], 0
0x180014fb6  mov     rbx, r9
0x180014fb9  movsxd  r9, [rsp+78h+arg_20]
0x180014fc1  mov     rdi, r8
0x180014fc4  movsxd  rax, [rsp+78h+arg_28]
0x180014fcc  jz      loc_18001508E
0x180014fd2  mov     r10d, [rsp+78h+arg_40]
0x180014fda  xor     r8d, r8d
0x180014fdd  cmp     [rsp+78h+arg_30], r8d
0x180014fe5  jz      short loc_18001501B
0x180014fe7  test    r10d, r10d
0x180014fea  jle     loc_18001524E
0x180014ff0  mov     r11, rax
0x180014ff3  xor     edx, edx
0x180014ff5  movsxd  rcx, edx
0x180014ff8  add     edx, 8
0x180014ffb  mov     rax, [rcx+rbx]
0x180014fff  mov     [rcx+rdi], rax
0x180015003  cmp     edx, r10d
0x180015006  jl      short loc_180014FF5
0x180015008  add     rbx, r11
0x18001500b  add     rdi, r9
0x18001500e  inc     r8d
0x180015011  cmp     r8d, r10d
0x180015014  jl      short loc_180014FF3
0x180015016  jmp     loc_18001524E
0x18001501b  test    r10d, r10d
0x18001501e  jle     loc_18001524E
0x180015024  mov     r13, r9
0x180015027  movsxd  r15, ecx
0x18001502a  mov     r9, 7F7F7F7F7F7F7F7Fh
0x180015034  mov     r12, rax
0x180015037  mov     r14, 101010101010101h
0x180015041  movsxd  rax, r8d
0x180015044  xor     ebp, ebp
0x180015046  lea     rsi, [rax+rdi]
0x18001504a  lea     r11, [rax+rbx]
0x18001504e  mov     rax, [r15+r11]
0x180015052  inc     ebp
0x180015054  mov     rdx, [r11]
0x180015057  mov     rcx, rax
0x18001505a  or      rcx, rdx
0x18001505d  shr     rax, 1
0x180015060  and     rcx, r14
0x180015063  shr     rdx, 1
0x180015066  and     rax, r9
0x180015069  and     rdx, r9
0x18001506c  add     rcx, rax
0x18001506f  add     r11, r12
0x180015072  add     rcx, rdx
0x180015075  mov     [rsi], rcx
0x180015078  add     rsi, r13
0x18001507b  cmp     ebp, r10d
0x18001507e  jl      short loc_18001504E
0x180015080  add     r8d, 8
0x180015084  cmp     r8d, r10d
0x180015087  jl      short loc_180015041
0x180015089  jmp     loc_18001524E
0x18001508e  imul    edx, eax
0x180015091  cmp     [rsp+78h+arg_30], 0
0x180015099  jz      short loc_180015119
0x18001509b  mov     r10d, [rsp+78h+arg_40]
0x1800150a3  xor     r8d, r8d
0x1800150a6  test    r10d, r10d
0x1800150a9  jle     loc_18001524E
0x1800150af  mov     r13, r9
0x1800150b2  movsxd  r15, edx
0x1800150b5  mov     r9, 7F7F7F7F7F7F7F7Fh
0x1800150bf  mov     r12, rax
0x1800150c2  mov     r14, 101010101010101h
0x1800150cc  movsxd  rax, r8d
0x1800150cf  xor     ebp, ebp
0x1800150d1  lea     rsi, [rax+rdi]
0x1800150d5  lea     r11, [rax+rbx]
0x1800150d9  mov     rax, [r15+r11]
0x1800150dd  inc     ebp
0x1800150df  mov     rdx, [r11]
0x1800150e2  mov     rcx, rax
0x1800150e5  or      rcx, rdx
0x1800150e8  shr     rax, 1
0x1800150eb  and     rcx, r14
0x1800150ee  shr     rdx, 1
0x1800150f1  and     rax, r9
0x1800150f4  and     rdx, r9
0x1800150f7  add     rcx, rax
0x1800150fa  add     r11, r12
0x1800150fd  add     rcx, rdx
0x180015100  mov     [rsi], rcx
0x180015103  add     rsi, r13
0x180015106  cmp     ebp, r10d
0x180015109  jl      short loc_1800150D9
0x18001510b  add     r8d, 8
0x18001510f  cmp     r8d, r10d
0x180015112  jl      short loc_1800150CC
0x180015114  jmp     loc_18001524E
0x180015119  mov     ebp, [rsp+78h+arg_40]
0x180015120  xor     esi, esi
0x180015122  mov     [rsp+78h+arg_38], esi
0x180015129  test    ebp, ebp
0x18001512b  jle     loc_18001524E
0x180015131  movsxd  r15, edx
0x180015134  movsxd  r12, ecx
0x180015137  mov     [rsp+78h+var_48], r15
0x18001513c  mov     [rsp+78h+var_40], r12
0x180015141  mov     [rsp+78h+var_58], rax
0x180015146  lea     r13, [r12+r15]
0x18001514a  mov     [rsp+78h+var_50], r9
0x18001514f  movsxd  r14, esi
0x180015152  mov     [rsp+78h+var_78], rbx
0x180015156  xor     ebx, ebx
0x180015158  add     r12, r14
0x18001515b  lea     rcx, [r14+r13]
0x18001515f  mov     r13, [rsp+78h+var_78]
0x180015163  lea     rsi, [r14+r15]
0x180015167  lea     r15, [rcx]
0x18001516a  mov     rcx, 303030303030303h
0x180015174  mov     r9, [r15+r13]
0x180015178  inc     ebx
0x18001517a  mov     r8, [rsi+r13]
0x18001517e  mov     rax, r9
0x180015181  mov     r10, [r14+r13]
0x180015185  and     rax, rcx
0x180015188  mov     r11, [r12+r13]
0x18001518c  mov     rdx, r8
0x18001518f  add     r13, [rsp+78h+var_58]
0x180015194  and     rdx, rcx
0x180015197  add     rdx, rax
0x18001519a  shr     r8, 2
0x18001519e  mov     rax, r10
0x1800151a1  shr     r9, 2
0x1800151a5  and     rax, rcx
0x1800151a8  shr     r10, 2
0x1800151ac  add     rdx, rax
0x1800151af  mov     rcx, r11
0x1800151b2  mov     rax, 303030303030303h
0x1800151bc  shr     r11, 2
0x1800151c0  and     rcx, rax
0x1800151c3  mov     rax, 202020202020202h
0x1800151cd  add     rdx, rax
0x1800151d0  mov     rax, 3F3F3F3F3F3F3F3Fh
0x1800151da  add     rdx, rcx
0x1800151dd  and     r8, rax
0x1800151e0  shr     rdx, 2
0x1800151e4  and     r9, rax
0x1800151e7  and     r10, rax
0x1800151ea  and     r11, rax
0x1800151ed  mov     rcx, 303030303030303h
0x1800151f7  and     rdx, rcx
0x1800151fa  add     rdx, r8
0x1800151fd  add     rdx, r9
0x180015200  add     rdx, r10
0x180015203  add     rdx, r11
0x180015206  mov     [r14+rdi], rdx
0x18001520a  add     rdi, [rsp+78h+var_50]
0x18001520f  cmp     ebx, ebp
0x180015211  jl      loc_180015174
0x180015217  mov     esi, [rsp+78h+arg_38]
0x18001521e  mov     r15, [rsp+78h+var_48]
0x180015223  add     esi, 8
0x180015226  mov     r12, [rsp+78h+var_40]
0x18001522b  mov     rbx, [rsp+78h+arg_18]
0x180015233  mov     rdi, [rsp+78h+arg_10]
0x18001523b  mov     [rsp+78h+arg_38], esi
0x180015242  lea     r13, [r12+r15]
0x180015246  cmp     esi, ebp
0x180015248  jl      loc_18001514F
0x18001524e  mov     rbx, [rsp+78h+arg_0]
0x180015256  add     rsp, 40h
0x18001525a  pop     r15
0x18001525c  pop     r14
0x18001525e  pop     r13
0x180015260  pop     r12
0x180015262  pop     rdi
0x180015263  pop     rsi
0x180015264  pop     rbp
0x180015265  retn
```
