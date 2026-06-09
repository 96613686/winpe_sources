# dct_IV(float *,int)

- ea: `0x18001ed50`
- end: `0x18001f503`
- name: `?dct_IV@@YAXPEAMH@Z`
- size: `1971`
- prototype: `void __fastcall(float *, int)`
- caller_count: `9`
- callee_count: `27`
- tags: ``

## callers

- `0x18001cef0`
- `0x18001d16c`
- `0x18001ddc0`
- `0x18001e228`
- `0x18001e420`
- `0x18003f654`
- `0x180082834`
- `0x180085224`
- `0x1800852f8`

## callees

- `0x18001d440`
- `0x18001ed50`
- `0x18001fda0`
- `0x18001ffc0`
- `0x1800200c0`
- `0x180020f50`
- `0x180021984`
- `0x1800224d0`
- `0x18002d8b0`
- `0x180085ca8`
- `0x180086140`
- `0x1800861f0`
- `0x180086590`
- `0x180086864`
- `0x180086918`
- `0x1800869c8`
- `0x180086a7c`
- `0x180086b70`
- `0x180086c30`
- `0x180086ce0`
- `0x180086d98`
- `0x180086e50`
- `0x180087018`
- `0x1800870c8`
- `0x180087384`
- `0x180087434`
- `0x180087680`

## pseudocode

```c
void __fastcall dct_IV(float *a1, signed int a2)
{
  __int64 v2; // rbp
  int v3; // ebx
  bool v4; // zf
  unsigned int v5; // eax
  int v7; // r15d
  int v8; // r9d
  int v9; // eax
  int v11; // edx
  int v12; // r8d
  const union FLOAT_SPK near *const *v13; // r14
  char v14; // cl
  const union FLOAT_SPK *v15; // rdx
  int v16; // esi
  float *v17; // r8
  float *i; // r9
  int v19; // r8d
  int v20; // r8d
  int v21; // r9d
  float v22; // xmm7_4
  float *v23; // r8
  float v24; // xmm6_4
  int v25; // edx
  float v26; // xmm7_4
  float v27; // xmm6_4
  int v28; // r10d
  float v29; // xmm7_4
  __int64 v30; // rcx
  float v31; // xmm0_4
  float v32; // xmm4_4
  float v33; // xmm5_4
  float v34; // xmm3_4
  float v35; // xmm2_4
  float v36; // xmm0_4
  float v37; // xmm3_4
  __int64 v38; // rax
  float v39; // xmm3_4
  __int64 v40; // [rsp+A0h] [rbp+18h]
  __int64 v41; // [rsp+A0h] [rbp+18h]
  const union FLOAT_SPK near *v42; // [rsp+A0h] [rbp+18h]
  __int64 v43; // [rsp+A8h] [rbp+20h]

  v2 = a2;
  v3 = a2 >> 1;
  v4 = !_BitScanReverse(&v5, a2);
  v7 = 1;
  v8 = 31 - v5;
  v9 = 32;
  if ( !v4 )
    v9 = v8;
  v11 = 30 - v9;
  v12 = a2 >> (30 - v9 - 1);
  if ( v12 == 4 )
  {
    v13 = &SineTable1024Fl;
    v14 = 10 - v11;
    v15 = (const union FLOAT_SPK *)qword_180098968[v11];
  }
  else
  {
    v19 = v12 - 5;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        if ( v20 != 1 )
        {
          v13 = 0;
          v16 = 0;
          v15 = 0;
          goto LABEL_6;
        }
        v13 = &SineTable480Fl;
        v14 = 8 - v11;
        v15 = (const union FLOAT_SPK *)qword_1800989B8[v11];
      }
      else
      {
        v13 = &SineTable384Fl;
        v14 = 8 - v11;
        v15 = (const union FLOAT_SPK *)qword_180098A00[v11];
      }
    }
    else
    {
      v13 = &SineTable80Fl;
      v14 = 6 - v11;
      v15 = (const union FLOAT_SPK *)qword_180098A48[v11];
    }
  }
  v16 = 1 << v14;
LABEL_6:
  if ( CDK_isAVX2_FMAavailable && v3 >= 8 )
  {
    if ( (v3 & 7) == 0 )
    {
      dct_IV_func1_AVX2_FMA(v3 >> 3, v15, a1);
      goto LABEL_10;
    }
  }
  else if ( v3 < 4 )
  {
    goto LABEL_37;
  }
  if ( (v3 & 3) == 0 )
  {
    dct_IV_func1_FLOAT(v3 >> 2, v15, a1);
    goto LABEL_10;
  }
LABEL_37:
  v28 = 0;
  v17 = a1;
  for ( i = &a1[v2 - 2]; v28 < v3 - 1; i -= 2 )
  {
    v29 = *i;
    v30 = v28;
    v28 += 2;
    v40 = *((_QWORD *)v15 + v30);
    v43 = *((_QWORD *)v15 + v30 + 1);
    v31 = v17[1];
    v32 = (float)(i[1] * *(float *)&v40) - (float)(*v17 * *((float *)&v40 + 1));
    *v17 = (float)(i[1] * *((float *)&v40 + 1)) + (float)(*v17 * *(float *)&v40);
    v17[1] = v32;
    v17 += 2;
    *((_DWORD *)i + 1) = COERCE_UNSIGNED_INT((float)(v29 * *(float *)&v43) - (float)(v31 * *((float *)&v43 + 1))) ^ _xmm;
    *i = (float)(v29 * *((float *)&v43 + 1)) + (float)(v31 * *(float *)&v43);
  }
  if ( (v3 & 1) != 0 )
  {
    v41 = *((_QWORD *)v15 + v28);
    v33 = (float)(i[1] * *(float *)&v41) - (float)(*v17 * *((float *)&v41 + 1));
    *v17 = (float)(i[1] * *((float *)&v41 + 1)) + (float)(*v17 * *(float *)&v41);
    v17[1] = v33;
  }
LABEL_10:
  switch ( v3 )
  {
    case 32:
      scramble(a1, 32);
      dit_fft_fl_SSE2(a1, 5, (const union FLOAT_SPK *)&SineTable512Fl, 512, &xmmword_18009D840);
      goto LABEL_15;
    case 16:
      fft_16(a1);
      goto LABEL_15;
    case 512:
      scramble(a1, 512);
      dit_fft_fl_SSE2(a1, 9, (const union FLOAT_SPK *)&SineTable512Fl, 512, &xmmword_18009D840);
      goto LABEL_15;
  }
  if ( v3 <= 384 )
  {
    if ( v3 != 384 )
    {
      switch ( v3 )
      {
        case 2:
          v34 = a1[1];
          v35 = *a1 - a1[2];
          *a1 = *a1 + a1[2];
          v36 = v34 + a1[3];
          v37 = v34 - a1[3];
          a1[2] = v35;
          a1[1] = v36;
          a1[3] = v37;
          goto LABEL_31;
        case 3:
          fft3(a1);
          goto LABEL_31;
        case 4:
          fft_4(a1);
          goto LABEL_15;
        case 5:
          fft5(a1);
          goto LABEL_31;
        case 6:
          fft6(a1);
          goto LABEL_31;
        case 8:
          fft_8(a1);
          goto LABEL_15;
        case 10:
          fft10(a1);
          goto LABEL_31;
        case 12:
          fft12(a1);
          goto LABEL_15;
        case 15:
          fft15(a1);
          goto LABEL_31;
        case 20:
          fft20(a1);
          goto LABEL_15;
        case 24:
          fft24(a1);
          goto LABEL_15;
        case 48:
          fft48(a1);
          goto LABEL_15;
        case 60:
          fft60(a1);
          goto LABEL_15;
        case 64:
          scramble(a1, 64);
          dit_fft_fl_SSE2(a1, 6, (const union FLOAT_SPK *)&SineTable512Fl, 512, &xmmword_18009D840);
          goto LABEL_15;
        case 80:
          fft80(a1);
          goto LABEL_15;
        case 96:
          fft96(a1);
          goto LABEL_15;
        case 120:
          fft120(a1);
          goto LABEL_15;
        case 128:
          dit_fft(a1, 7, (const union FLOAT_SPK *)v17, (int)i);
          goto LABEL_15;
        case 192:
          fft192(a1);
          goto LABEL_15;
        case 240:
          fft240(a1);
          goto LABEL_15;
        case 256:
          dit_fft(a1, 8, (const union FLOAT_SPK *)v17, (int)i);
          goto LABEL_15;
        default:
          if ( v3 < 4 )
            goto LABEL_31;
          goto LABEL_14;
      }
    }
    fft384(a1);
    goto LABEL_15;
  }
  if ( v3 == 480 )
  {
    fft480(a1);
    goto LABEL_15;
  }
LABEL_14:
  if ( (v3 & 3) == 0 )
  {
LABEL_15:
    dct_IV_func2_FLOAT(v3 >> 2, (const union FLOAT_SPK *)v13, a1, v16);
    return;
  }
LABEL_31:
  v21 = v16;
  v22 = a1[(int)v2 - 1];
  v23 = &a1[(int)v2 - 2];
  v24 = *v23;
  v25 = (v3 + 1) >> 1;
  *((_DWORD *)v23 + 1) = *((_DWORD *)a1 + 1) ^ _xmm;
  if ( v25 > 1 )
  {
    do
    {
      v38 = v21;
      ++v7;
      v21 += v16;
      v42 = v13[v38];
      a1[1] = (float)(*(float *)&v42 * v24) - (float)(*((float *)&v42 + 1) * v22);
      a1 += 2;
      *v23 = (float)(*(float *)&v42 * v22) + (float)(*((float *)&v42 + 1) * v24);
      v23 -= 2;
      v22 = v23[1];
      v24 = *v23;
      v39 = (float)(a1[1] * *((float *)&v42 + 1)) + (float)(*a1 * *(float *)&v42);
      *((_DWORD *)v23 + 1) = COERCE_UNSIGNED_INT((float)(a1[1] * *(float *)&v42) - (float)(*a1 * *((float *)&v42 + 1)))
                           ^ _xmm;
      *a1 = v39;
    }
    while ( v7 < v25 );
  }
  if ( (v3 & 1) == 0 )
  {
    v26 = v22 * 0.70710677;
    v27 = v24 * 0.70710677;
    *v23 = v26 + v27;
    a1[1] = v27 - v26;
  }
}

```

## disassembly

```asm
0x18001ed50  push    rbx
0x18001ed52  push    rbp
0x18001ed53  push    rsi
0x18001ed54  push    rdi
0x18001ed55  push    r12
0x18001ed57  push    r14
0x18001ed59  push    r15
0x18001ed5b  sub     rsp, 50h
0x18001ed5f  movsxd  rbp, edx
0x18001ed62  lea     r12, __ImageBase
0x18001ed69  mov     ebx, ebp
0x18001ed6b  mov     [rsp+88h+arg_8], 0
0x18001ed76  sar     ebx, 1
0x18001ed78  mov     r9d, 1Fh
0x18001ed7e  bsr     eax, ebp
0x18001ed81  mov     edx, 1Eh
0x18001ed86  mov     rdi, rcx
0x18001ed89  mov     r15d, 1
0x18001ed8f  setnz   r8b
0x18001ed93  sub     r9d, eax
0x18001ed96  test    r8b, r8b
0x18001ed99  mov     eax, 20h ; ' '
0x18001ed9e  mov     r8d, ebp
0x18001eda1  cmovnz  eax, r9d
0x18001eda5  sub     edx, eax
0x18001eda7  lea     ecx, [rdx-1]
0x18001edaa  sar     r8d, cl
0x18001edad  cmp     r8d, 4
0x18001edb1  jnz     loc_18001EE8E
0x18001edb7  movsxd  rax, edx
0x18001edba  lea     r14, ?SineTable1024Fl@@3QBTFLOAT_SPK@@B; FLOAT_SPK const near * const SineTable1024Fl
0x18001edc1  mov     ecx, 0Ah
0x18001edc6  sub     ecx, edx
0x18001edc8  mov     rdx, ds:rva qword_180098968[r12+rax*8]; union FLOAT_SPK *
0x18001edd0  mov     esi, r15d
0x18001edd3  shl     esi, cl
0x18001edd5  cmp     cs:?CDK_isAVX2_FMAavailable@@3HA, 0; int CDK_isAVX2_FMAavailable
0x18001eddc  movaps  [rsp+88h+var_48], xmm6
0x18001ede1  movaps  [rsp+88h+var_58], xmm7
0x18001ede6  jz      loc_18001EEC8
0x18001edec  cmp     ebx, 8
0x18001edef  jl      loc_18001EEC8
0x18001edf5  test    bl, 7
0x18001edf8  jnz     loc_18001EED1
0x18001edfe  mov     ecx, ebx
0x18001ee00  mov     r8, rdi; float *
0x18001ee03  sar     ecx, 3; int
0x18001ee06  call    ?dct_IV_func1_AVX2_FMA@@YAXHPEBTFLOAT_SPK@@PEAM@Z; dct_IV_func1_AVX2_FMA(int,FLOAT_SPK const *,float *)
0x18001ee0b  cmp     ebx, 20h ; ' '
0x18001ee0e  jz      short loc_18001EE23
0x18001ee10  cmp     ebx, 10h
0x18001ee13  jnz     loc_18001EEEC
0x18001ee19  mov     rcx, rdi; float *
0x18001ee1c  call    ?fft_16@@YAXPEAM@Z; fft_16(float *)
0x18001ee21  jmp     short loc_18001EE61
0x18001ee23  mov     edx, 20h ; ' '; int
0x18001ee28  mov     rcx, rdi; float *
0x18001ee2b  call    ?scramble@@YAXPEAMH@Z; scramble(float *,int)
0x18001ee30  lea     rax, xmmword_18009D840
0x18001ee37  mov     r9d, 200h; int
0x18001ee3d  lea     r8, ?SineTable512Fl@@3QBTFLOAT_SPK@@B; union FLOAT_SPK *
0x18001ee44  mov     [rsp+88h+var_68], rax; float *
0x18001ee49  mov     edx, 5; int
0x18001ee4e  mov     rcx, rdi; float *
0x18001ee51  call    ?dit_fft_fl_SSE2@@YAXPEAMHPEBTFLOAT_SPK@@HPEBM@Z; dit_fft_fl_SSE2(float *,int,FLOAT_SPK const *,int,float const *)
0x18001ee56  jmp     short loc_18001EE61
0x18001ee58  test    bl, 3
0x18001ee5b  jnz     loc_18001EF9F
0x18001ee61  sar     ebx, 2
0x18001ee64  mov     r9d, esi; int
0x18001ee67  mov     ecx, ebx; int
0x18001ee69  mov     r8, rdi; float *
0x18001ee6c  mov     rdx, r14; union FLOAT_SPK *
0x18001ee6f  call    ?dct_IV_func2_FLOAT@@YAXHPEBTFLOAT_SPK@@PEAMH@Z; dct_IV_func2_FLOAT(int,FLOAT_SPK const *,float *,int)
0x18001ee74  movaps  xmm7, [rsp+88h+var_58]
0x18001ee79  movaps  xmm6, [rsp+88h+var_48]
0x18001ee7e  add     rsp, 50h
0x18001ee82  pop     r15
0x18001ee84  pop     r14
0x18001ee86  pop     r12
0x18001ee88  pop     rdi
0x18001ee89  pop     rsi
0x18001ee8a  pop     rbp
0x18001ee8b  pop     rbx
0x18001ee8c  retn
0x18001ee8e  sub     r8d, 5
0x18001ee92  jz      loc_18001F034
0x18001ee98  sub     r8d, r15d
0x18001ee9b  jz      loc_18001F016
0x18001eea1  cmp     r8d, r15d
0x18001eea4  jnz     loc_18001F00A
0x18001eeaa  movsxd  rax, edx
0x18001eead  lea     r14, ?SineTable480Fl@@3QBTFLOAT_SPK@@B; FLOAT_SPK const near * const SineTable480Fl
0x18001eeb4  mov     ecx, 8
0x18001eeb9  sub     ecx, edx
0x18001eebb  mov     rdx, ds:rva qword_1800989B8[r12+rax*8]
0x18001eec3  jmp     loc_18001EDD0
0x18001eec8  cmp     ebx, 4
0x18001eecb  jl      loc_18001F052
0x18001eed1  test    bl, 3
0x18001eed4  jnz     loc_18001F052
0x18001eeda  mov     ecx, ebx
0x18001eedc  mov     r8, rdi; float *
0x18001eedf  sar     ecx, 2; int
0x18001eee2  call    ?dct_IV_func1_FLOAT@@YAXHPEBTFLOAT_SPK@@PEAM@Z; dct_IV_func1_FLOAT(int,FLOAT_SPK const *,float *)
0x18001eee7  jmp     loc_18001EE0B
0x18001eeec  cmp     ebx, 200h
0x18001eef2  jnz     short loc_18001EF26
0x18001eef4  mov     edx, ebx; int
0x18001eef6  mov     rcx, rdi; float *
0x18001eef9  call    ?scramble@@YAXPEAMH@Z; scramble(float *,int)
0x18001eefe  lea     rax, xmmword_18009D840
0x18001ef05  mov     r9d, ebx; int
0x18001ef08  lea     r8, ?SineTable512Fl@@3QBTFLOAT_SPK@@B; union FLOAT_SPK *
0x18001ef0f  mov     [rsp+88h+var_68], rax; float *
0x18001ef14  mov     edx, 9; int
0x18001ef19  mov     rcx, rdi; float *
0x18001ef1c  call    ?dit_fft_fl_SSE2@@YAXPEAMHPEBTFLOAT_SPK@@HPEBM@Z; dit_fft_fl_SSE2(float *,int,FLOAT_SPK const *,int,float const *)
0x18001ef21  jmp     loc_18001EE61
0x18001ef26  cmp     ebx, 180h
0x18001ef2c  jg      loc_18001F2E3
0x18001ef32  jz      loc_18001F2D6
0x18001ef38  lea     eax, [rbx-2]; switch 255 cases
0x18001ef3b  cmp     eax, 0FEh
0x18001ef40  ja      short def_18001EF58; jumptable 000000018001EF58 default case, cases 7,9,11,13,14,16-19,21-23,25-47,49-59,61-63,65-79,81-95,97-119,121-127,129-191,193-239,241-255
0x18001ef42  cdqe
0x18001ef44  movzx   eax, ds:(byte_18001F404 - 180000000h)[r12+rax]
0x18001ef4d  mov     ecx, ds:(jpt_18001EF58 - 180000000h)[r12+rax*4]
0x18001ef55  add     rcx, r12
0x18001ef58  jmp     rcx; switch jump
0x18001ef5e  mov     edx, 40h ; '@'; jumptable 000000018001EF58 case 64
0x18001ef63  mov     rcx, rdi; float *
0x18001ef66  call    ?scramble@@YAXPEAMH@Z; scramble(float *,int)
0x18001ef6b  lea     rax, xmmword_18009D840
0x18001ef72  mov     r9d, 200h; int
0x18001ef78  lea     r8, ?SineTable512Fl@@3QBTFLOAT_SPK@@B; union FLOAT_SPK *
0x18001ef7f  mov     [rsp+88h+var_68], rax; float *
0x18001ef84  mov     edx, 6; int
0x18001ef89  mov     rcx, rdi; float *
0x18001ef8c  call    ?dit_fft_fl_SSE2@@YAXPEAMHPEBTFLOAT_SPK@@HPEBM@Z; dit_fft_fl_SSE2(float *,int,FLOAT_SPK const *,int,float const *)
0x18001ef91  jmp     loc_18001EE61
0x18001ef96  cmp     ebx, 4; jumptable 000000018001EF58 default case, cases 7,9,11,13,14,16-19,21-23,25-47,49-59,61-63,65-79,81-95,97-119,121-127,129-191,193-239,241-255
0x18001ef99  jge     loc_18001EE58
0x18001ef9f  movss   xmm0, dword ptr [rdi+4]
0x18001efa4  lea     eax, [rbp-2]
0x18001efa7  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x18001efae  lea     edx, [rbx+1]
0x18001efb1  movsxd  rcx, eax
0x18001efb4  mov     r9d, esi
0x18001efb7  movss   xmm7, dword ptr [rdi+rcx*4+4]
0x18001efbd  lea     r8, [rdi+rcx*4]
0x18001efc1  movss   xmm6, dword ptr [r8]
0x18001efc6  sar     edx, 1
0x18001efc8  movss   dword ptr [r8+4], xmm0
0x18001efce  cmp     edx, r15d
0x18001efd1  jg      loc_18001F2FC
0x18001efd7  test    bl, 1
0x18001efda  jnz     loc_18001EE74
0x18001efe0  mulss   xmm7, cs:__real@3f3504f3
0x18001efe8  mulss   xmm6, cs:__real@3f3504f3
0x18001eff0  movaps  xmm0, xmm7
0x18001eff3  addss   xmm0, xmm6
0x18001eff7  subss   xmm6, xmm7
0x18001effb  movss   dword ptr [r8], xmm0
0x18001f000  movss   dword ptr [rdi+4], xmm6
0x18001f005  jmp     loc_18001EE74
0x18001f00a  xor     r14d, r14d
0x18001f00d  xor     esi, esi
0x18001f00f  xor     edx, edx
0x18001f011  jmp     loc_18001EDD5
0x18001f016  movsxd  rax, edx
0x18001f019  lea     r14, ?SineTable384Fl@@3QBTFLOAT_SPK@@B; FLOAT_SPK const near * const SineTable384Fl
0x18001f020  mov     ecx, 8
0x18001f025  sub     ecx, edx
0x18001f027  mov     rdx, ds:rva qword_180098A00[r12+rax*8]
0x18001f02f  jmp     loc_18001EDD0
0x18001f034  movsxd  rax, edx
0x18001f037  lea     r14, ?SineTable80Fl@@3QBTFLOAT_SPK@@B; FLOAT_SPK const near * const SineTable80Fl
0x18001f03e  mov     ecx, 6
0x18001f043  sub     ecx, edx
0x18001f045  mov     rdx, ds:rva qword_180098A48[r12+rax*8]
0x18001f04d  jmp     loc_18001EDD0
0x18001f052  xor     r10d, r10d
0x18001f055  lea     r11d, [rbx-1]
0x18001f059  lea     r9, [rbp-2]
0x18001f05d  mov     r8, rdi
0x18001f060  lea     r9, [rdi+r9*4]
0x18001f064  test    r11d, r11d
0x18001f067  jle     loc_18001F135
0x18001f06d  movss   xmm5, dword ptr [r8]
0x18001f072  movss   xmm4, dword ptr [r9+4]
0x18001f078  movaps  xmm0, xmm5
0x18001f07b  movss   xmm6, dword ptr [r8+4]
0x18001f081  movaps  xmm2, xmm4
0x18001f084  movss   xmm7, dword ptr [r9]
0x18001f089  movsxd  rcx, r10d
0x18001f08c  add     r10d, 2
0x18001f090  mov     rax, [rdx+rcx*8]
0x18001f094  mov     [rsp+88h+arg_10], rax
0x18001f09c  mov     rax, [rdx+rcx*8+8]
0x18001f0a1  mulss   xmm2, dword ptr [rsp+88h+arg_10+4]
0x18001f0aa  mov     [rsp+88h+arg_18], rax
0x18001f0b2  mulss   xmm0, dword ptr [rsp+88h+arg_10]
0x18001f0bb  mulss   xmm4, dword ptr [rsp+88h+arg_10]
0x18001f0c4  mulss   xmm5, dword ptr [rsp+88h+arg_10+4]
0x18001f0cd  addss   xmm2, xmm0
0x18001f0d1  movaps  xmm0, xmm6
0x18001f0d4  mulss   xmm6, dword ptr [rsp+88h+arg_18+4]
0x18001f0dd  mulss   xmm0, dword ptr [rsp+88h+arg_18]
0x18001f0e6  subss   xmm4, xmm5
0x18001f0ea  movss   dword ptr [r8], xmm2
0x18001f0ef  movaps  xmm2, xmm7
0x18001f0f2  mulss   xmm7, dword ptr [rsp+88h+arg_18]
0x18001f0fb  mulss   xmm2, dword ptr [rsp+88h+arg_18+4]
0x18001f104  movss   dword ptr [r8+4], xmm4
0x18001f10a  subss   xmm7, xmm6
0x18001f10e  add     r8, 8
0x18001f112  addss   xmm2, xmm0
0x18001f116  xorps   xmm7, cs:__xmm@80000000800000008000000080000000
0x18001f11d  movss   dword ptr [r9+4], xmm7
0x18001f123  movss   dword ptr [r9], xmm2
0x18001f128  sub     r9, 8
0x18001f12c  cmp     r10d, r11d
0x18001f12f  jl      loc_18001F06D
0x18001f135  test    r15b, bl
0x18001f138  jz      loc_18001EE0B
0x18001f13e  movss   xmm5, dword ptr [r9+4]
0x18001f144  movss   xmm4, dword ptr [r8]
0x18001f149  movaps  xmm2, xmm5
0x18001f14c  movaps  xmm0, xmm4
0x18001f14f  movsxd  rax, r10d
0x18001f152  mov     rcx, [rdx+rax*8]
0x18001f156  mov     [rsp+88h+arg_10], rcx
0x18001f15e  mulss   xmm2, dword ptr [rsp+88h+arg_10+4]
0x18001f167  mulss   xmm0, dword ptr [rsp+88h+arg_10]
0x18001f170  mulss   xmm5, dword ptr [rsp+88h+arg_10]
0x18001f179  mulss   xmm4, dword ptr [rsp+88h+arg_10+4]
0x18001f182  addss   xmm2, xmm0
0x18001f186  subss   xmm5, xmm4
0x18001f18a  movss   dword ptr [r8], xmm2
0x18001f18f  movss   dword ptr [r8+4], xmm5
0x18001f195  jmp     loc_18001EE0B
0x18001f19a  mov     rcx, rdi; jumptable 000000018001EF58 case 8
0x18001f19d  call    fft_8
0x18001f1a2  jmp     loc_18001EE61
0x18001f1a7  movss   xmm2, dword ptr [rdi]; jumptable 000000018001EF58 case 2
0x18001f1ab  movss   xmm3, dword ptr [rdi+4]
0x18001f1b0  movaps  xmm0, xmm2
0x18001f1b3  addss   xmm0, dword ptr [rdi+8]
0x18001f1b8  subss   xmm2, dword ptr [rdi+8]
0x18001f1bd  movss   dword ptr [rdi], xmm0
0x18001f1c1  movaps  xmm0, xmm3
0x18001f1c4  addss   xmm0, dword ptr [rdi+0Ch]
0x18001f1c9  subss   xmm3, dword ptr [rdi+0Ch]
0x18001f1ce  movss   dword ptr [rdi+8], xmm2
0x18001f1d3  movss   dword ptr [rdi+4], xmm0
0x18001f1d8  movss   dword ptr [rdi+0Ch], xmm3
0x18001f1dd  jmp     loc_18001EF9F
0x18001f1e2  mov     rcx, rdi; jumptable 000000018001EF58 case 3
0x18001f1e5  call    fft3
0x18001f1ea  jmp     loc_18001EF9F
0x18001f1ef  mov     rcx, rdi; jumptable 000000018001EF58 case 4
0x18001f1f2  call    fft_4
0x18001f1f7  jmp     loc_18001EE61
0x18001f1fc  mov     rcx, rdi; jumptable 000000018001EF58 case 5
0x18001f1ff  call    fft5
0x18001f204  jmp     loc_18001EF9F
0x18001f209  mov     rcx, rdi; jumptable 000000018001EF58 case 6
0x18001f20c  call    fft6
0x18001f211  jmp     loc_18001EF9F
0x18001f216  mov     rcx, rdi; jumptable 000000018001EF58 case 10
0x18001f219  call    fft10
0x18001f21e  jmp     loc_18001EF9F
0x18001f223  mov     rcx, rdi; jumptable 000000018001EF58 case 12
0x18001f226  call    fft12
0x18001f22b  jmp     loc_18001EE61
0x18001f230  mov     rcx, rdi; jumptable 000000018001EF58 case 15
0x18001f233  call    fft15
0x18001f238  jmp     loc_18001EF9F
0x18001f23d  mov     rcx, rdi; jumptable 000000018001EF58 case 20
0x18001f240  call    fft20
0x18001f245  jmp     loc_18001EE61
0x18001f24a  mov     rcx, rdi; jumptable 000000018001EF58 case 24
0x18001f24d  call    fft24
0x18001f252  jmp     loc_18001EE61
0x18001f257  mov     rcx, rdi; jumptable 000000018001EF58 case 48
0x18001f25a  call    fft48
0x18001f25f  jmp     loc_18001EE61
0x18001f264  mov     rcx, rdi; jumptable 000000018001EF58 case 60
0x18001f267  call    fft60
0x18001f26c  jmp     loc_18001EE61
0x18001f271  mov     rcx, rdi; jumptable 000000018001EF58 case 80
0x18001f274  call    fft80
0x18001f279  jmp     loc_18001EE61
0x18001f27e  mov     rcx, rdi; jumptable 000000018001EF58 case 96
0x18001f281  call    fft96
0x18001f286  jmp     loc_18001EE61
0x18001f28b  mov     rcx, rdi; jumptable 000000018001EF58 case 120
0x18001f28e  call    fft120
0x18001f293  jmp     loc_18001EE61
  ... truncated ...
```
