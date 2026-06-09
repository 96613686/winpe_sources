# CLpc_Read(CDK_BITSTREAM *,float (* const)[16],float * const,float * const,float * const,uchar *,int,int,int)

- ea: `0x180080608`
- end: `0x180080afc`
- name: `?CLpc_Read@@YAHPEAUCDK_BITSTREAM@@QEAY0BA@MQEAM22PEAEHHH@Z`
- size: `1268`
- prototype: `__int64 __fastcall(struct CDK_BITSTREAM *, float (*const)[16], float *const, float *const, float *const, unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180044774`

## callees

- `0x180013550`
- `0x18004d320`
- `0x18004dc9c`
- `0x180080608`
- `0x180081000`
- `0x1800815e4`
- `0x180081628`

## pseudocode

```c
__int64 __fastcall CLpc_Read(
        struct CDK_BITSTREAM *a1,
        float (*const a2)[16],
        float *const a3,
        float *const a4,
        float *const a5,
        unsigned __int8 *a6,
        int a7,
        int a8,
        int a9)
{
  float *v9; // rbx
  __int64 result; // rax
  unsigned int v14; // r15d
  __int64 v15; // rcx
  BOOL v16; // r13d
  int v17; // esi
  __int64 v18; // rbx
  int v19; // eax
  char *v20; // rdx
  __int64 i; // rcx
  float v22; // xmm6_4
  int vlclbf_n; // eax
  int v24; // eax
  __int64 j; // rax
  unsigned int v26; // ebx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 n; // rcx
  __int64 k; // rcx
  __int64 v32; // r8
  __int64 m; // rcx
  __int64 ii; // rcx
  __int64 jj; // rax
  int kk; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  float *v39; // rcx
  float v40; // xmm0_4
  __int64 mm; // rcx
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int nn; // r8d
  float v46; // xmm1_4
  int i1; // r9d
  __int64 v48; // rax
  int v49; // r9d
  float *v50; // rdx
  int i2; // ecx
  float *v52; // r8
  float v53; // xmm1_4
  __int64 i3; // rax
  float v55; // xmm0_4
  __int64 v56; // rax
  __int64 i4; // rbx
  __int64 v58; // r14
  float *v59; // rsi
  float v60; // xmm1_4
  __int128 v63; // [rsp+38h] [rbp-40h]
  int v64; // [rsp+48h] [rbp-30h]

  v9 = &(*a2)[64];
  v64 = 1;
  v63 = 0;
  vlpc_1st_dec(a1, &(*a2)[64]);
  result = vlpc_2st_dec(a1, v9, 0);
  v14 = 0;
  if ( (_DWORD)result )
    return result;
  if ( a7 )
  {
    v17 = 0;
    v16 = 1;
  }
  else
  {
    LODWORD(v63) = 1;
    v15 = 0;
    v16 = a8 == 0;
    do
    {
      (*a2)[v15] = a3[v15];
      ++v15;
    }
    while ( v15 != 16 );
    v17 = 2;
  }
  while ( v17 < 3 && (v17 != 2 || *a6 != 3) )
  {
    v18 = (__int64)v17 << 6;
    *((_DWORD *)&v63 + v17) = 1;
    v19 = CDKreadBit((__int64)a1);
    v20 = (char *)*a2 + v18;
    if ( v19 )
    {
      for ( i = 0; i != 16; ++i )
        *(float *)&v20[4 * i] = (*a2)[i + 64];
      v14 = 3;
      v18 = (__int64)v17 << 6;
    }
    else
    {
      vlpc_1st_dec(a1, v20);
    }
    result = vlpc_2st_dec(a1, (char *)*a2 + v18, v14);
    v14 = 0;
    if ( (_DWORD)result )
      return result;
    v17 += 2;
  }
  v22 = FLOAT_0_5;
  if ( *a6 < 2u )
  {
    DWORD1(v63) = 1;
    vlclbf_n = get_vlclbf_n(a1, 2);
    if ( vlclbf_n )
    {
      v24 = vlclbf_n - 1;
      if ( v24 )
      {
        if ( v24 == 1 )
        {
          if ( v16 )
          {
            for ( j = 0; j != 16; ++j )
              (*a2)[j + 16] = (float)((*a2)[j + 32] * 0.5) + (float)((*a2)[j] * 0.5);
          }
          else
          {
            for ( k = 0; k != 16; ++k )
              (*a2)[k + 16] = (*a2)[k + 32];
          }
        }
        goto LABEL_24;
      }
      vlpc_1st_dec(a1, &(*a2)[16]);
      v32 = 0;
    }
    else
    {
      for ( m = 0; m != 16; ++m )
        (*a2)[m + 16] = (*a2)[m + 32];
      v32 = 2;
    }
    result = vlpc_2st_dec(a1, &(*a2)[16], v32);
    if ( (_DWORD)result )
      return result;
  }
LABEL_24:
  if ( a6[2] < 2u )
  {
    HIDWORD(v63) = 1;
    v26 = 0;
    v27 = get_vlclbf_n(a1, 3);
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 != 1 )
            goto LABEL_48;
          for ( n = 0; n != 16; ++n )
            (*a2)[n + 48] = (*a2)[n + 64];
        }
        else
        {
          for ( ii = 0; ii != 16; ++ii )
            (*a2)[ii + 48] = (*a2)[ii + 32];
        }
        v26 = 2;
      }
      else
      {
        vlpc_1st_dec(a1, &(*a2)[48]);
      }
    }
    else
    {
      for ( jj = 0; jj != 16; ++jj )
        (*a2)[jj + 48] = (float)((*a2)[jj + 64] * 0.5) + (float)((*a2)[jj + 32] * 0.5);
      v26 = 1;
    }
LABEL_48:
    result = vlpc_2st_dec(a1, &(*a2)[48], v26);
    if ( (_DWORD)result )
      return result;
  }
  if ( !v16 && !a9 )
  {
    for ( kk = 1; kk < 5; ++kk )
    {
      v37 = kk;
      if ( *((_DWORD *)&v63 + kk) )
      {
        v38 = 0;
        v39 = &(*a2)[16 * v37];
        do
        {
          if ( *a6 )
            v40 = (float)(*((float *)&cdk_dec_lsf_init + v38) * 0.25) + (float)(v39[v38] * 0.75);
          else
            v40 = v39[v38];
          (*a2)[v38++] = v40;
        }
        while ( v38 != 16 );
        break;
      }
    }
  }
  for ( mm = 0; mm != 16; ++mm )
    a3[mm] = (*a2)[mm + 64];
  v42 = 0;
  v43 = 4;
  do
    v42 += *((_DWORD *)&v63 + (unsigned int)v43--);
  while ( v43 >= 0 && v42 < 3 );
  v44 = v42 - 2;
  if ( v44 )
  {
    if ( v44 == 1 )
      v22 = FLOAT_0_33333334;
    else
      v22 = FLOAT_1_0;
  }
  for ( nn = 0; nn < 16; ++nn )
  {
    v46 = 0.0;
    for ( i1 = 4; i1 > v43; --i1 )
    {
      if ( *((_DWORD *)&v63 + i1) )
        v46 = v46 + (float)(v22 * (*a2)[16 * i1 + nn]);
    }
    v48 = (unsigned int)nn;
    a4[v48] = v46;
  }
  v49 = 0;
  v50 = (float *)a2;
  for ( i2 = 1; i2 < 5; ++i2 )
  {
    if ( *((_DWORD *)&v63 + (unsigned int)i2) )
    {
      v52 = v50;
      v53 = 0.0;
      v50 = &(*a2)[16 * (unsigned __int64)(unsigned int)i2];
      for ( i3 = 0; i3 != 16; ++i3 )
      {
        v55 = v50[i3] - v52[i3];
        v53 = v53 + (float)(v55 * v55);
      }
      v56 = v49;
      v49 = i2;
      a5[v56] = fminf(fmaxf(1.25 - (float)(v53 / 400000.0), 0.0), 1.0);
    }
    else
    {
      a5[i2] = -1.0;
    }
  }
  for ( i4 = 0; i4 != 5; ++i4 )
  {
    if ( *((_DWORD *)&v63 + i4) )
    {
      v58 = 0;
      v59 = &(*a2)[16 * i4];
      do
      {
        v60 = cos(v59[v58] * 0.0004908738521234052);
        v59[v58++] = v60;
      }
      while ( v58 != 16 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180080608  push    rbp
0x18008060a  push    rbx
0x18008060b  push    rsi
0x18008060c  push    rdi
0x18008060d  push    r12
0x18008060f  push    r13
0x180080611  push    r14
0x180080613  push    r15
0x180080615  mov     rbp, rsp
0x180080618  sub     rsp, 78h
0x18008061c  movaps  [rsp+78h+var_18], xmm6
0x180080621  mov     rax, cs:__security_cookie
0x180080628  xor     rax, rsp
0x18008062b  mov     [rbp+var_28], rax
0x18008062f  mov     rax, [rbp+arg_20]
0x180080633  lea     rbx, [rdx+100h]
0x18008063a  mov     rdi, rdx
0x18008063d  mov     [rbp+var_50], r9
0x180080641  xorps   xmm0, xmm0
0x180080644  mov     [rbp+var_58], r8
0x180080648  mov     rdx, rbx
0x18008064b  mov     [rbp+var_48], rax
0x18008064f  mov     r14, r8
0x180080652  mov     [rbp+var_30], 1
0x180080659  mov     r12, rcx
0x18008065c  movdqu  [rbp+var_40], xmm0
0x180080661  call    vlpc_1st_dec
0x180080666  xor     r8d, r8d
0x180080669  mov     rdx, rbx
0x18008066c  mov     rcx, r12
0x18008066f  call    vlpc_2st_dec
0x180080674  xor     r15d, r15d
0x180080677  test    eax, eax
0x180080679  jnz     loc_180080AD9
0x18008067f  cmp     [rbp+arg_30], r15d
0x180080683  jnz     short loc_1800806B2
0x180080685  cmp     [rbp+arg_38], r15d
0x18008068c  mov     r13d, r15d
0x18008068f  mov     dword ptr [rbp+var_40], 1
0x180080696  mov     ecx, r15d
0x180080699  setz    r13b
0x18008069d  mov     eax, [r14+rcx*4]
0x1800806a1  mov     [rdi+rcx*4], eax
0x1800806a4  inc     rcx
0x1800806a7  cmp     rcx, 10h
0x1800806ab  jnz     short loc_18008069D
0x1800806ad  lea     esi, [rcx-0Eh]
0x1800806b0  jmp     short loc_1800806BB
0x1800806b2  mov     esi, r15d
0x1800806b5  mov     r13d, 1
0x1800806bb  cmp     esi, 3
0x1800806be  jge     short loc_18008073B
0x1800806c0  cmp     esi, 2
0x1800806c3  jnz     short loc_1800806CE
0x1800806c5  mov     rax, [rbp+arg_28]
0x1800806c9  cmp     byte ptr [rax], 3
0x1800806cc  jz      short loc_18008073B
0x1800806ce  movsxd  r14, esi
0x1800806d1  mov     rcx, r12
0x1800806d4  mov     rbx, r14
0x1800806d7  shl     rbx, 6
0x1800806db  mov     dword ptr [rbp+r14*4+var_40], 1
0x1800806e4  call    CDKreadBit
0x1800806e9  lea     rdx, [rbx+rdi]
0x1800806ed  test    eax, eax
0x1800806ef  jnz     short loc_1800806FB
0x1800806f1  mov     rcx, r12
0x1800806f4  call    vlpc_1st_dec
0x1800806f9  jmp     short loc_18008071C
0x1800806fb  mov     rcx, r15
0x1800806fe  mov     eax, [rdi+rcx*4+100h]
0x180080705  mov     [rdx+rcx*4], eax
0x180080708  inc     rcx
0x18008070b  cmp     rcx, 10h
0x18008070f  jnz     short loc_1800806FE
0x180080711  mov     rbx, r14
0x180080714  lea     r15d, [rcx-0Dh]
0x180080718  shl     rbx, 6
0x18008071c  lea     rdx, [rbx+rdi]
0x180080720  mov     r8d, r15d
0x180080723  mov     rcx, r12
0x180080726  call    vlpc_2st_dec
0x18008072b  xor     r15d, r15d
0x18008072e  test    eax, eax
0x180080730  jnz     loc_180080AD9
0x180080736  add     esi, 2
0x180080739  jmp     short loc_1800806BB
0x18008073b  mov     rsi, [rbp+arg_28]
0x18008073f  movss   xmm6, cs:__real@3f000000
0x180080747  cmp     byte ptr [rsi], 2
0x18008074a  jnb     short loc_1800807AB
0x18008074c  mov     edx, 2
0x180080751  mov     dword ptr [rbp+var_40+4], 1
0x180080758  mov     rcx, r12
0x18008075b  call    get_vlclbf_n
0x180080760  test    eax, eax
0x180080762  jz      loc_18008084C
0x180080768  sub     eax, 1
0x18008076b  jz      loc_180080824
0x180080771  cmp     eax, 1
0x180080774  jnz     short loc_1800807AB
0x180080776  test    r13d, r13d
0x180080779  jz      loc_18008080B
0x18008077f  mov     rax, r15
0x180080782  movss   xmm1, dword ptr [rdi+rax*4+80h]
0x18008078b  movss   xmm0, dword ptr [rdi+rax*4]
0x180080790  mulss   xmm1, xmm6
0x180080794  mulss   xmm0, xmm6
0x180080798  addss   xmm1, xmm0
0x18008079c  movss   dword ptr [rdi+rax*4+40h], xmm1
0x1800807a2  inc     rax
0x1800807a5  cmp     rax, 10h
0x1800807a9  jnz     short loc_180080782
0x1800807ab  cmp     byte ptr [rsi+2], 2
0x1800807af  jnb     loc_1800808EB
0x1800807b5  mov     edx, 3
0x1800807ba  mov     dword ptr [rbp+var_40+0Ch], 1
0x1800807c1  mov     rcx, r12
0x1800807c4  mov     ebx, r15d
0x1800807c7  call    get_vlclbf_n
0x1800807cc  test    eax, eax
0x1800807ce  jz      loc_18008089B
0x1800807d4  sub     eax, 1
0x1800807d7  jz      loc_18008088A
0x1800807dd  sub     eax, 1
0x1800807e0  jz      loc_180080869
0x1800807e6  cmp     eax, 1
0x1800807e9  jnz     loc_1800808D1
0x1800807ef  mov     rcx, r15
0x1800807f2  mov     eax, [rdi+rcx*4+100h]
0x1800807f9  mov     [rdi+rcx*4+0C0h], eax
0x180080800  inc     rcx
0x180080803  cmp     rcx, 10h
0x180080807  jnz     short loc_1800807F2
0x180080809  jmp     short loc_180080883
0x18008080b  mov     rcx, r15
0x18008080e  mov     eax, [rdi+rcx*4+80h]
0x180080815  mov     [rdi+rcx*4+40h], eax
0x180080819  inc     rcx
0x18008081c  cmp     rcx, 10h
0x180080820  jnz     short loc_18008080E
0x180080822  jmp     short loc_1800807AB
0x180080824  lea     rdx, [rdi+40h]
0x180080828  mov     rcx, r12
0x18008082b  call    vlpc_1st_dec
0x180080830  xor     r8d, r8d
0x180080833  lea     rdx, [rdi+40h]
0x180080837  mov     rcx, r12
0x18008083a  call    vlpc_2st_dec
0x18008083f  test    eax, eax
0x180080841  jz      loc_1800807AB
0x180080847  jmp     loc_180080AD9
0x18008084c  mov     rcx, r15
0x18008084f  mov     eax, [rdi+rcx*4+80h]
0x180080856  mov     [rdi+rcx*4+40h], eax
0x18008085a  inc     rcx
0x18008085d  cmp     rcx, 10h
0x180080861  jnz     short loc_18008084F
0x180080863  lea     r8d, [rcx-0Eh]
0x180080867  jmp     short loc_180080833
0x180080869  mov     rcx, r15
0x18008086c  mov     eax, [rdi+rcx*4+80h]
0x180080873  mov     [rdi+rcx*4+0C0h], eax
0x18008087a  inc     rcx
0x18008087d  cmp     rcx, 10h
0x180080881  jnz     short loc_18008086C
0x180080883  mov     ebx, 2
0x180080888  jmp     short loc_1800808D1
0x18008088a  lea     rdx, [rdi+0C0h]
0x180080891  mov     rcx, r12
0x180080894  call    vlpc_1st_dec
0x180080899  jmp     short loc_1800808D1
0x18008089b  mov     rax, r15
0x18008089e  movss   xmm1, dword ptr [rdi+rax*4+100h]
0x1800808a7  movss   xmm0, dword ptr [rdi+rax*4+80h]
0x1800808b0  mulss   xmm1, xmm6
0x1800808b4  mulss   xmm0, xmm6
0x1800808b8  addss   xmm1, xmm0
0x1800808bc  movss   dword ptr [rdi+rax*4+0C0h], xmm1
0x1800808c5  inc     rax
0x1800808c8  cmp     rax, 10h
0x1800808cc  jnz     short loc_18008089E
0x1800808ce  lea     ebx, [rax-0Fh]
0x1800808d1  lea     rdx, [rdi+0C0h]
0x1800808d8  mov     r8d, ebx
0x1800808db  mov     rcx, r12
0x1800808de  call    vlpc_2st_dec
0x1800808e3  test    eax, eax
0x1800808e5  jnz     loc_180080AD9
0x1800808eb  test    r13d, r13d
0x1800808ee  jnz     short loc_18008095F
0x1800808f0  cmp     [rbp+arg_40], r15d
0x1800808f7  jnz     short loc_18008095F
0x1800808f9  lea     eax, [r13+1]
0x1800808fd  cmp     eax, 5
0x180080900  jge     short loc_18008095F
0x180080902  movsxd  rcx, eax
0x180080905  cmp     dword ptr [rbp+rcx*4+var_40], r15d
0x18008090a  jnz     short loc_180080910
0x18008090c  inc     eax
0x18008090e  jmp     short loc_1800808FD
0x180080910  movss   xmm2, cs:__real@3e800000
0x180080918  mov     rax, r15
0x18008091b  movss   xmm3, cs:__real@3f400000
0x180080923  shl     rcx, 6
0x180080927  add     rcx, rdi
0x18008092a  movss   xmm1, dword ptr [rcx+rax*4]
0x18008092f  cmp     [rsi], r15b
0x180080932  jbe     short loc_18008094E
0x180080934  lea     rdx, ?cdk_dec_lsf_init@@3QBMB; float const near * const cdk_dec_lsf_init
0x18008093b  mulss   xmm1, xmm3
0x18008093f  movss   xmm0, dword ptr [rdx+rax*4]
0x180080944  mulss   xmm0, xmm2
0x180080948  addss   xmm0, xmm1
0x18008094c  jmp     short loc_180080951
0x18008094e  movaps  xmm0, xmm1
0x180080951  movss   dword ptr [rdi+rax*4], xmm0
0x180080956  inc     rax
0x180080959  cmp     rax, 10h
0x18008095d  jnz     short loc_18008092A
0x18008095f  mov     r14, [rbp+var_58]
0x180080963  mov     rcx, r15
0x180080966  mov     r13d, 1
0x18008096c  mov     eax, [rdi+rcx*4+100h]
0x180080973  mov     [r14+rcx*4], eax
0x180080977  add     rcx, r13
0x18008097a  cmp     rcx, 10h
0x18008097e  jnz     short loc_18008096C
0x180080980  mov     r10d, 4
0x180080986  mov     ecx, r15d
0x180080989  mov     edx, r10d
0x18008098c  mov     eax, edx
0x18008098e  add     ecx, dword ptr [rbp+rax*4+var_40]
0x180080992  sub     edx, r13d
0x180080995  js      short loc_18008099C
0x180080997  cmp     ecx, 3
0x18008099a  jl      short loc_18008098C
0x18008099c  movss   xmm2, cs:__real@3f800000
0x1800809a4  sub     ecx, 2
0x1800809a7  jz      short loc_1800809BB
0x1800809a9  cmp     ecx, r13d
0x1800809ac  jz      short loc_1800809B3
0x1800809ae  movaps  xmm6, xmm2
0x1800809b1  jmp     short loc_1800809BB
0x1800809b3  movss   xmm6, cs:__real@3eaaaaab
0x1800809bb  mov     r8d, r15d
0x1800809be  xor     r12d, r12d
0x1800809c1  mov     r15, [rbp+var_50]
0x1800809c5  xorps   xmm1, xmm1
0x1800809c8  mov     r9d, r10d
0x1800809cb  cmp     edx, r10d
0x1800809ce  jge     short loc_1800809F8
0x1800809d0  movsxd  rcx, r9d
0x1800809d3  cmp     dword ptr [rbp+rcx*4+var_40], r12d
0x1800809d8  jz      short loc_1800809F0
0x1800809da  shl     rcx, 4
0x1800809de  movaps  xmm0, xmm6
0x1800809e1  mov     eax, r8d
0x1800809e4  add     rcx, rax
0x1800809e7  mulss   xmm0, dword ptr [rdi+rcx*4]
0x1800809ec  addss   xmm1, xmm0
0x1800809f0  sub     r9d, r13d
0x1800809f3  cmp     r9d, edx
0x1800809f6  jg      short loc_1800809D0
0x1800809f8  mov     eax, r8d
0x1800809fb  add     r8d, r13d
0x1800809fe  movss   dword ptr [r15+rax*4], xmm1
0x180080a04  cmp     r8d, 10h
0x180080a08  jl      short loc_1800809C5
0x180080a0a  mov     r10, [rbp+var_48]
0x180080a0e  mov     r9d, r12d
0x180080a11  mov     rdx, rdi
0x180080a14  mov     ecx, r13d
0x180080a17  mov     eax, ecx
0x180080a19  cmp     dword ptr [rbp+rax*4+var_40], r12d
0x180080a1e  jz      short loc_180080A7B
0x180080a20  shl     rax, 6
0x180080a24  mov     r8, rdx
0x180080a27  xorps   xmm1, xmm1
0x180080a2a  lea     rdx, [rax+rdi]
0x180080a2e  mov     rax, r12
0x180080a31  movss   xmm0, dword ptr [rdx+rax*4]
0x180080a36  subss   xmm0, dword ptr [r8+rax*4]
0x180080a3c  add     rax, r13
0x180080a3f  mulss   xmm0, xmm0
0x180080a43  addss   xmm1, xmm0
0x180080a47  cmp     rax, 10h
0x180080a4b  jnz     short loc_180080A31
0x180080a4d  divss   xmm1, cs:__real@48c35000
0x180080a55  movsxd  rax, r9d
0x180080a58  mov     r9d, ecx
0x180080a5b  movss   xmm0, cs:__real@3fa00000
0x180080a63  subss   xmm0, xmm1
0x180080a67  maxss   xmm0, cs:__real@00000000
0x180080a6f  minss   xmm0, xmm2
0x180080a73  movss   dword ptr [r10+rax*4], xmm0
0x180080a79  jmp     short loc_180080A83
0x180080a7b  mov     dword ptr [r10+rax*4], 0BF800000h
0x180080a83  add     ecx, r13d
0x180080a86  cmp     ecx, 5
  ... truncated ...
```
