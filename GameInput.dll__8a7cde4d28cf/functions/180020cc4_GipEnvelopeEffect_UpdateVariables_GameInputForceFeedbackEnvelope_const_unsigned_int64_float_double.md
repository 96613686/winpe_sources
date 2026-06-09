# GipEnvelopeEffect::UpdateVariables(GameInputForceFeedbackEnvelope const *,unsigned __int64,float,double)

- ea: `0x180020cc4`
- end: `0x18002144c`
- name: `?UpdateVariables@GipEnvelopeEffect@@IEAAPEAUGipEffectData@@PEBUGameInputForceFeedbackEnvelope@@_KMN@Z`
- size: `1928`
- prototype: `struct GipEffectData *__fastcall(GipEnvelopeEffect *__hidden this, const struct GameInputForceFeedbackEnvelope *, unsigned __int64, float, double)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001d9b0`
- `0x18001dab0`
- `0x180021454`

## callees

- `0x180020c3c`
- `0x180020cc4`
- `0x18004c8a5`
- `0x18004c8e0`

## pseudocode

```c
struct GipEffectData *__fastcall GipEnvelopeEffect::UpdateVariables(
        GipEnvelopeEffect *this,
        const struct GameInputForceFeedbackEnvelope *a2,
        unsigned __int64 a3,
        float a4,
        double a5)
{
  struct GipEffectData *updated; // rbx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rcx
  char v12; // r13
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // rax
  double v20; // xmm0_8
  double v21; // xmm0_8
  double v22; // xmm0_8
  __int16 *v23; // rdx
  char v24; // r8
  double v25; // xmm2_8
  double v26; // xmm1_8
  __int64 v27; // r9
  char i; // cl
  double v29; // xmm0_8
  __int64 v30; // rax
  __m128d v31; // xmm1
  float v32; // xmm3_4
  __int16 *v33; // rdx
  __int16 v34; // ax
  float v35; // xmm3_4
  __int16 *v36; // rcx
  __int16 v37; // ax
  __m128d v38; // xmm1
  float v39; // xmm3_4
  __int16 v40; // ax
  double v41; // xmm1_8
  float v42; // xmm3_4
  __int16 v43; // ax
  __m128i v44; // xmm0
  float v45; // ecx
  __int16 v46; // ax
  double v47; // xmm2_8
  double v48; // xmm0_8
  float v49; // xmm1_4
  __int16 v50; // ax
  float *v51; // rcx
  __int16 v52; // ax
  __int64 j; // rdx
  float v54; // xmm0_4
  float v55; // xmm1_4
  __int16 v56; // ax
  float v57; // xmm1_4
  __int16 v58; // ax
  float v59; // xmm1_4
  __int16 v60; // ax
  float v61; // xmm1_4
  __int16 v62; // cx
  float v64; // [rsp+20h] [rbp-60h] BYREF
  __int16 v65; // [rsp+28h] [rbp-58h] BYREF
  double v66; // [rsp+30h] [rbp-50h]
  __int16 v67; // [rsp+38h] [rbp-48h]
  double v68; // [rsp+40h] [rbp-40h]
  __int16 v69; // [rsp+48h] [rbp-38h]
  double v70; // [rsp+50h] [rbp-30h]
  __m128i si128; // [rsp+58h] [rbp-28h] BYREF
  __m128i v72; // [rsp+68h] [rbp-18h]

  updated = GipEffect::UpdateVariables(this, a4);
  if ( *(_BYTE *)updated
    || *(_QWORD *)a2 != *((_QWORD *)this + 23)
    || *((_QWORD *)a2 + 1) != *((_QWORD *)this + 24)
    || *((_QWORD *)a2 + 2) != *((_QWORD *)this + 25)
    || *((_QWORD *)a2 + 5) != *((_QWORD *)this + 28)
    || *((_DWORD *)a2 + 9) != *((_DWORD *)this + 55) )
  {
    *(_OWORD *)((char *)this + 184) = *(_OWORD *)a2;
    *(_OWORD *)((char *)this + 200) = *((_OWORD *)a2 + 1);
    *(_OWORD *)((char *)this + 216) = *((_OWORD *)a2 + 2);
    v9 = *((_QWORD *)a2 + 1);
    v10 = *(_QWORD *)a2 / 0x3E8uLL;
    if ( v9 == -1 )
      v11 = -1;
    else
      v11 = v9 / 0x3E8;
    v12 = 0;
    v13 = *((unsigned int *)a2 + 9);
    v14 = *((_QWORD *)a2 + 2) / 0x3E8uLL;
    v15 = *((_QWORD *)a2 + 5) / 0x3E8uLL;
    v16 = a3 / 0x3E8;
    if ( v11 == -1 )
    {
      if ( v16 > 0x1000000 )
        v16 = 0x1000000;
    }
    else
    {
      v17 = v11 + v14 + v10;
      if ( !v17 )
        goto LABEL_24;
      if ( v16 >= v17 )
      {
        v16 -= v17;
        v18 = v17 + v15;
        v12 = 1;
        if ( v13 != 0xFFFFFFFF )
          --v13;
        if ( v16 >= v18 )
        {
          v19 = v16 / v18;
          v16 %= v18;
          if ( v13 != 0xFFFFFFFF )
          {
            if ( v19 < v13 )
              v13 -= v19;
            else
              v13 = 0;
          }
        }
        if ( !v13 )
        {
LABEL_24:
          v13 = 1;
          v15 = 0;
          v14 = 0;
          v11 = 0;
          v10 = 0;
          v16 = 0;
        }
      }
    }
    v65 = 770;
    if ( (v14 & 0x8000000000000000uLL) != 0LL )
      v20 = (double)(int)(v14 & 1 | (v14 >> 1)) + (double)(int)(v14 & 1 | (v14 >> 1));
    else
      v20 = (double)(int)v14;
    v66 = v20;
    v67 = 514;
    if ( (v11 & 0x8000000000000000uLL) != 0LL )
      v21 = (double)(int)(v11 & 1 | (v11 >> 1)) + (double)(int)(v11 & 1 | (v11 >> 1));
    else
      v21 = (double)(int)v11;
    v68 = v21;
    v69 = 513;
    if ( (v10 & 0x8000000000000000uLL) != 0LL )
      v22 = (double)(int)(v10 & 1 | (v10 >> 1)) + (double)(int)(v10 & 1 | (v10 >> 1));
    else
      v22 = (double)(int)v10;
    v70 = v22;
    if ( (char *)this + 232 <= (char *)this + 236 )
      memset_0((char *)this + 232, 0, -(__int64)((char *)this + 236 >= (char *)this + 232) & 4);
    v23 = &v65;
    v24 = 4;
    si128 = _mm_load_si128((const __m128i *)&_xmm_c000000000000000c008000000000000);
    v72 = _mm_load_si128((const __m128i *)&_xmm);
    v25 = 0.0;
    do
    {
      v26 = *((double *)v23 + 1);
      if ( v26 != 0.0 )
      {
        if ( v24 == 4 )
        {
          v24 = 3;
          *((_BYTE *)this + 235) = *((_BYTE *)v23 + 1);
        }
        v27 = v24;
        for ( i = 0; (unsigned __int8)i < 4u; ++i )
        {
          if ( i >= v24 )
            v29 = v26;
          else
            v29 = DOUBLE_1_0;
          v30 = i;
          *(double *)&si128.m128i_i64[v30] = v29 + *(double *)&si128.m128i_i64[v30];
        }
        --v24;
        *((_BYTE *)this + v27 + 231) = *(_BYTE *)v23;
      }
      v23 += 8;
    }
    while ( v23 != (__int16 *)&si128 );
    v31 = (__m128d)si128;
    v32 = *(double *)si128.m128i_i64;
    if ( *((_BYTE *)this + 100) || *((float *)this + 24) != v32 )
    {
      *((float *)this + 24) = v32;
      v33 = (__int16 *)((char *)updated + 2);
      *((_BYTE *)this + 100) = 0;
      v34 = *((_WORD *)updated + 1);
      *(_BYTE *)updated = 1;
      if ( (v34 & 2) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *v33 = v34 | 2;
      }
      *((float *)updated + 2) = v32;
    }
    else
    {
      v33 = (__int16 *)((char *)updated + 2);
    }
    v35 = _mm_unpackhi_pd(v31, v31).m128d_f64[0];
    if ( *((_BYTE *)this + 116) || (v36 = v33, *((float *)this + 28) != v35) )
    {
      *((float *)this + 28) = v35;
      v36 = (__int16 *)((char *)updated + 2);
      *((_BYTE *)this + 116) = 0;
      v37 = *((_WORD *)updated + 1);
      *(_BYTE *)updated = 1;
      if ( (v37 & 8) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *v36 = v37 | 8;
      }
      *((float *)updated + 4) = v35;
    }
    v38 = (__m128d)v72;
    v39 = *(double *)v72.m128i_i64;
    if ( *((_BYTE *)this + 132) || (v36 = v33, *((float *)this + 32) != v39) )
    {
      *((float *)this + 32) = v39;
      *((_BYTE *)this + 132) = 0;
      v40 = *v36;
      *(_BYTE *)updated = 1;
      if ( (v40 & 0x20) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *v36 = v40 | 0x20;
      }
      *((float *)updated + 6) = v39;
    }
    v41 = _mm_unpackhi_pd(v38, v38).m128d_f64[0];
    if ( v41 >= 1.844674407370955e19 )
      v42 = FLOAT_2_6843546e8;
    else
      v42 = v41;
    if ( *((_BYTE *)this + 148) || *((float *)this + 36) != v42 )
    {
      *((float *)this + 36) = v42;
      *((_BYTE *)this + 148) = 0;
      v43 = *v33;
      *(_BYTE *)updated = 1;
      if ( (v43 & 0x80u) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *v33 = v43 | 0x80;
      }
      *((float *)updated + 8) = v42;
    }
    v44 = 0;
    if ( (v15 & 0x8000000000000000uLL) != 0LL )
      *(float *)v44.m128i_i32 = (float)(int)(v15 & 1 | (v15 >> 1)) + (float)(int)(v15 & 1 | (v15 >> 1));
    else
      *(float *)v44.m128i_i32 = (float)(int)v15;
    LODWORD(v45) = _mm_cvtsi128_si32(v44) ^ 0x80000000;
    if ( *((_BYTE *)this + 164) || *((float *)this + 40) != v45 )
    {
      *((float *)this + 40) = v45;
      *((_BYTE *)this + 164) = 0;
      v46 = *v33;
      *(_BYTE *)updated = 1;
      if ( (v46 & 0x200) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *((_WORD *)updated + 1) = v46 | 0x200;
      }
      *((float *)updated + 10) = v45;
    }
    if ( v12 )
    {
      if ( (v15 & 0x8000000000000000uLL) != 0LL )
        v47 = (double)(int)(v15 & 1 | (v15 >> 1)) + (double)(int)(v15 & 1 | (v15 >> 1));
      else
        v47 = (double)(int)v15;
      *(_QWORD *)&v25 = *(_QWORD *)&v47 ^ _xmm;
    }
    if ( (v16 & 0x8000000000000000uLL) != 0LL )
      v48 = (double)(int)(v16 & 1 | (v16 >> 1)) + (double)(int)(v16 & 1 | (v16 >> 1));
    else
      v48 = (double)(int)v16;
    v49 = v48 - v25;
    if ( *((_BYTE *)this + 172) || *((float *)this + 42) != v49 )
    {
      *((float *)this + 42) = v49;
      *((_BYTE *)this + 172) = 0;
      v50 = *((_WORD *)updated + 1);
      *(_BYTE *)updated = 1;
      if ( (v50 & 0x400) == 0 )
      {
        ++*((_BYTE *)updated + 1);
        *((_WORD *)updated + 1) = v50 | 0x400;
      }
      *((float *)updated + 11) = v49;
    }
    if ( v13 >= 0xFFFFFFFF )
    {
      v51 = (float *)&GipEffect::c_infiniteFloatValue;
    }
    else
    {
      v51 = (float *)&GipEffect::c_maxAbsFloatValue;
      v64 = (float)(int)v13;
      if ( (float)(int)v13 <= 16777216.0 )
        v51 = &v64;
    }
    *((float *)this + 44) = *v51;
    *((_BYTE *)this + 180) = 0;
    v52 = *((_WORD *)updated + 1);
    *(_BYTE *)updated = 1;
    if ( (v52 & 0x800) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *((_WORD *)updated + 1) = v52 | 0x800;
    }
    *((float *)updated + 12) = *v51;
  }
  for ( j = 0; j != 4; ++j )
  {
    if ( *((_BYTE *)this + j + 232) )
    {
      switch ( *((_BYTE *)this + j + 232) )
      {
        case 1:
          v54 = *((float *)a2 + 6);
          break;
        case 2:
          v54 = *((float *)a2 + 7);
          break;
        case 3:
          v54 = *((float *)a2 + 8);
          break;
        default:
          continue;
      }
      *(double *)&si128.m128i_i64[j] = v54 * a5;
    }
    else
    {
      si128.m128i_i64[j] = 0;
    }
  }
  v55 = *(double *)si128.m128i_i64;
  if ( *((_BYTE *)this + 108) || *((float *)this + 26) != v55 )
  {
    *((float *)this + 26) = v55;
    *((_BYTE *)this + 108) = 0;
    v56 = *((_WORD *)updated + 1);
    if ( (v56 & 4) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *((_WORD *)updated + 1) = v56 | 4;
    }
    *((float *)updated + 3) = v55;
  }
  v57 = *(double *)&si128.m128i_i64[1];
  if ( *((_BYTE *)this + 124) || *((float *)this + 30) != v57 )
  {
    *((float *)this + 30) = v57;
    *((_BYTE *)this + 124) = 0;
    v58 = *((_WORD *)updated + 1);
    if ( (v58 & 0x10) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *((_WORD *)updated + 1) = v58 | 0x10;
    }
    *((float *)updated + 5) = v57;
  }
  v59 = *(double *)v72.m128i_i64;
  if ( *((_BYTE *)this + 140) || *((float *)this + 34) != v59 )
  {
    *((float *)this + 34) = v59;
    *((_BYTE *)this + 140) = 0;
    v60 = *((_WORD *)updated + 1);
    if ( (v60 & 0x40) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *((_WORD *)updated + 1) = v60 | 0x40;
    }
    *((float *)updated + 7) = v59;
  }
  v61 = *(double *)&v72.m128i_i64[1];
  if ( *((_BYTE *)this + 156) || *((float *)this + 38) != v61 )
  {
    *((float *)this + 38) = v61;
    *((_BYTE *)this + 156) = 0;
    v62 = *((_WORD *)updated + 1);
    if ( (v62 & 0x100) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *((_WORD *)updated + 1) = v62 | 0x100;
    }
    *((float *)updated + 9) = v61;
  }
  return updated;
}

```

## disassembly

```asm
0x180020cc4  mov     [rsp-38h+arg_8], rbx
0x180020cc9  push    rbp
0x180020cca  push    rsi
0x180020ccb  push    rdi
0x180020ccc  push    r12
0x180020cce  push    r13
0x180020cd0  push    r14
0x180020cd2  push    r15
0x180020cd4  mov     rbp, rsp
0x180020cd7  sub     rsp, 80h
0x180020cde  mov     rax, cs:__security_cookie
0x180020ce5  xor     rax, rsp
0x180020ce8  mov     [rbp+var_8], rax
0x180020cec  movaps  xmm1, xmm3; float
0x180020cef  mov     rsi, r8
0x180020cf2  mov     r12, rdx
0x180020cf5  mov     rdi, rcx
0x180020cf8  call    ?UpdateVariables@GipEffect@@IEAAPEAUGipEffectData@@M@Z; GipEffect::UpdateVariables(float)
0x180020cfd  mov     r10d, 4
0x180020d03  xor     r11d, r11d
0x180020d06  mov     rbx, rax
0x180020d09  lea     r8d, [r10+0Ch]
0x180020d0d  cmp     [rax], r11b
0x180020d10  jnz     short loc_180020D5A
0x180020d12  mov     rax, [rdi+0B8h]
0x180020d19  cmp     [r12], rax
0x180020d1d  jnz     short loc_180020D5A
0x180020d1f  mov     rax, [rdi+0C0h]
0x180020d26  cmp     [r12+8], rax
0x180020d2b  jnz     short loc_180020D5A
0x180020d2d  mov     rax, [rdi+0C8h]
0x180020d34  cmp     [r12+10h], rax
0x180020d39  jnz     short loc_180020D5A
0x180020d3b  mov     rax, [rdi+0E0h]
0x180020d42  cmp     [r12+28h], rax
0x180020d47  jnz     short loc_180020D5A
0x180020d49  mov     eax, [rdi+0DCh]
0x180020d4f  cmp     [r12+24h], eax
0x180020d54  jz      loc_1800212BA
0x180020d5a  movups  xmm0, xmmword ptr [r12]
0x180020d5f  mov     r10, 624DD2F1A9FBE77h
0x180020d69  mov     rax, r10
0x180020d6c  movups  xmmword ptr [rdi+0B8h], xmm0
0x180020d73  movups  xmm1, xmmword ptr [r12+10h]
0x180020d79  movups  xmmword ptr [rdi+0C8h], xmm1
0x180020d80  movups  xmm0, xmmword ptr [r12+20h]
0x180020d86  movups  xmmword ptr [rdi+0D8h], xmm0
0x180020d8d  mov     r8, [r12]
0x180020d91  mov     rcx, [r12+8]
0x180020d96  mul     r8
0x180020d99  sub     r8, rdx
0x180020d9c  shr     r8, 1
0x180020d9f  add     r8, rdx
0x180020da2  shr     r8, 9
0x180020da6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020daa  jz      short loc_180020DC1
0x180020dac  mov     rax, r10
0x180020daf  mul     rcx
0x180020db2  sub     rcx, rdx
0x180020db5  shr     rcx, 1
0x180020db8  add     rcx, rdx
0x180020dbb  shr     rcx, 9
0x180020dbf  jmp     short loc_180020DC5
0x180020dc1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020dc5  mov     r9, [r12+10h]
0x180020dca  mov     rax, r10
0x180020dcd  mov     r15, [r12+28h]
0x180020dd2  mov     r13b, r11b
0x180020dd5  mov     r14d, [r12+24h]
0x180020dda  mul     r9
0x180020ddd  mov     rax, r10
0x180020de0  sub     r9, rdx
0x180020de3  shr     r9, 1
0x180020de6  add     r9, rdx
0x180020de9  mul     r15
0x180020dec  mov     rax, r10
0x180020def  shr     r9, 9
0x180020df3  sub     r15, rdx
0x180020df6  shr     r15, 1
0x180020df9  add     r15, rdx
0x180020dfc  mul     rsi
0x180020dff  shr     r15, 9
0x180020e03  sub     rsi, rdx
0x180020e06  shr     rsi, 1
0x180020e09  add     rsi, rdx
0x180020e0c  shr     rsi, 9
0x180020e10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020e14  jnz     short loc_180020E24
0x180020e16  mov     eax, 1000000h
0x180020e1b  cmp     rsi, rax
0x180020e1e  cmova   rsi, rax
0x180020e22  jmp     short loc_180020E8A
0x180020e24  lea     rdx, [r9+r8]
0x180020e28  add     rdx, rcx
0x180020e2b  jz      short loc_180020E75
0x180020e2d  cmp     rsi, rdx
0x180020e30  jb      short loc_180020E8A
0x180020e32  sub     rsi, rdx
0x180020e35  lea     r10, [rdx+r15]
0x180020e39  mov     eax, 0FFFFFFFFh
0x180020e3e  mov     r13b, 1
0x180020e41  cmp     r14, rax
0x180020e44  jz      short loc_180020E49
0x180020e46  dec     r14
0x180020e49  cmp     rsi, r10
0x180020e4c  jb      short loc_180020E70
0x180020e4e  xor     edx, edx
0x180020e50  mov     rax, rsi
0x180020e53  div     r10
0x180020e56  mov     rsi, rdx
0x180020e59  mov     edx, 0FFFFFFFFh
0x180020e5e  cmp     r14, rdx
0x180020e61  jz      short loc_180020E70
0x180020e63  cmp     rax, r14
0x180020e66  jb      short loc_180020E6D
0x180020e68  mov     r14, r11
0x180020e6b  jmp     short loc_180020E70
0x180020e6d  sub     r14, rax
0x180020e70  test    r14, r14
0x180020e73  jnz     short loc_180020E8A
0x180020e75  mov     r14d, 1
0x180020e7b  mov     r15, r11
0x180020e7e  mov     r9, r11
0x180020e81  mov     rcx, r11
0x180020e84  mov     r8, r11
0x180020e87  mov     rsi, r11
0x180020e8a  mov     [rbp+var_58], 302h
0x180020e90  xorps   xmm0, xmm0
0x180020e93  test    r9, r9
0x180020e96  js      short loc_180020E9F
0x180020e98  cvtsi2sd xmm0, r9
0x180020e9d  jmp     short loc_180020EB5
0x180020e9f  mov     rax, r9
0x180020ea2  and     r9d, 1
0x180020ea6  shr     rax, 1
0x180020ea9  or      rax, r9
0x180020eac  cvtsi2sd xmm0, rax
0x180020eb1  addsd   xmm0, xmm0
0x180020eb5  movsd   [rbp+var_50], xmm0
0x180020eba  xorps   xmm0, xmm0
0x180020ebd  mov     [rbp+var_48], 202h
0x180020ec3  test    rcx, rcx
0x180020ec6  js      short loc_180020ECF
0x180020ec8  cvtsi2sd xmm0, rcx
0x180020ecd  jmp     short loc_180020EE4
0x180020ecf  mov     rax, rcx
0x180020ed2  and     ecx, 1
0x180020ed5  shr     rax, 1
0x180020ed8  or      rax, rcx
0x180020edb  cvtsi2sd xmm0, rax
0x180020ee0  addsd   xmm0, xmm0
0x180020ee4  movsd   [rbp+var_40], xmm0
0x180020ee9  xorps   xmm0, xmm0
0x180020eec  mov     [rbp+var_38], 201h
0x180020ef2  test    r8, r8
0x180020ef5  js      short loc_180020EFE
0x180020ef7  cvtsi2sd xmm0, r8
0x180020efc  jmp     short loc_180020F14
0x180020efe  mov     rax, r8
0x180020f01  and     r8d, 1
0x180020f05  shr     rax, 1
0x180020f08  or      rax, r8
0x180020f0b  cvtsi2sd xmm0, rax
0x180020f10  addsd   xmm0, xmm0
0x180020f14  lea     rcx, [rdi+0E8h]; void *
0x180020f1b  movsd   [rbp+var_30], xmm0
0x180020f20  lea     rax, [rcx+4]
0x180020f24  mov     r10d, 4
0x180020f2a  cmp     rax, rcx
0x180020f2d  sbb     r8, r8
0x180020f30  not     r8
0x180020f33  and     r8, r10; Size
0x180020f36  cmp     rcx, rax
0x180020f39  ja      short loc_180020F49
0x180020f3b  xor     edx, edx; Val
0x180020f3d  call    memset_0
0x180020f42  xor     r11d, r11d
0x180020f45  lea     r10d, [r11+4]
0x180020f49  movdqa  xmm0, cs:__xmm@c000000000000000c008000000000000
0x180020f51  lea     rdx, [rbp+var_58]
0x180020f55  movdqa  xmm1, cs:__xmm@0000000000000000bff0000000000000
0x180020f5d  mov     r8b, r10b
0x180020f60  movups  [rbp+var_28], xmm0
0x180020f64  movups  [rbp+var_18], xmm1
0x180020f68  xorps   xmm2, xmm2
0x180020f6b  movsd   xmm1, qword ptr [rdx+8]
0x180020f70  ucomisd xmm1, xmm2
0x180020f74  jp      short loc_180020F78
0x180020f76  jz      short loc_180020FC6
0x180020f78  cmp     r8b, r10b
0x180020f7b  jnz     short loc_180020F89
0x180020f7d  mov     al, [rdx+1]
0x180020f80  mov     r8b, 3
0x180020f83  mov     [rdi+0EBh], al
0x180020f89  movsx   r9, r8b
0x180020f8d  mov     cl, r11b
0x180020f90  cmp     cl, r8b
0x180020f93  jge     short loc_180020F9F
0x180020f95  movsd   xmm0, cs:__real@3ff0000000000000
0x180020f9d  jmp     short loc_180020FA2
0x180020f9f  movaps  xmm0, xmm1
0x180020fa2  movsx   rax, cl
0x180020fa6  inc     cl
0x180020fa8  addsd   xmm0, qword ptr [rbp+rax*8+var_28]
0x180020fae  movsd   qword ptr [rbp+rax*8+var_28], xmm0
0x180020fb4  cmp     cl, r10b
0x180020fb7  jb      short loc_180020F90
0x180020fb9  mov     al, [rdx]
0x180020fbb  dec     r8b
0x180020fbe  mov     [r9+rdi+0E7h], al
0x180020fc6  add     rdx, 10h
0x180020fca  lea     rax, [rbp+var_28]
0x180020fce  cmp     rdx, rax
0x180020fd1  jnz     short loc_180020F6B
0x180020fd3  xorps   xmm3, xmm3
0x180020fd6  movups  xmm1, [rbp+var_28]
0x180020fda  cvtsd2ss xmm3, xmm1
0x180020fde  cmp     [rdi+64h], r11b
0x180020fe2  jnz     short loc_180020FF6
0x180020fe4  movss   xmm0, dword ptr [rdi+60h]
0x180020fe9  ucomiss xmm0, xmm3
0x180020fec  jp      short loc_180020FF6
0x180020fee  jnz     short loc_180020FF6
0x180020ff0  lea     rdx, [rbx+2]
0x180020ff4  jmp     short loc_18002101C
0x180020ff6  movss   dword ptr [rdi+60h], xmm3
0x180020ffb  lea     rdx, [rbx+2]
0x180020fff  mov     [rdi+64h], r11b
0x180021003  movzx   eax, word ptr [rdx]
0x180021006  mov     byte ptr [rbx], 1
0x180021009  test    al, 2
0x18002100b  jnz     short loc_180021017
0x18002100d  inc     byte ptr [rbx+1]
0x180021010  or      ax, 2
0x180021014  mov     [rdx], ax
0x180021017  movss   dword ptr [rbx+8], xmm3
0x18002101c  xorps   xmm3, xmm3
0x18002101f  unpckhpd xmm1, xmm1
0x180021023  cvtsd2ss xmm3, xmm1
0x180021027  cmp     [rdi+74h], r11b
0x18002102b  jnz     short loc_18002103C
0x18002102d  movss   xmm0, dword ptr [rdi+70h]
0x180021032  mov     rcx, rdx
0x180021035  ucomiss xmm0, xmm3
0x180021038  jp      short loc_18002103C
0x18002103a  jz      short loc_180021062
0x18002103c  movss   dword ptr [rdi+70h], xmm3
0x180021041  lea     rcx, [rbx+2]
0x180021045  mov     [rdi+74h], r11b
0x180021049  movzx   eax, word ptr [rcx]
0x18002104c  mov     byte ptr [rbx], 1
0x18002104f  test    al, 8
0x180021051  jnz     short loc_18002105D
0x180021053  inc     byte ptr [rbx+1]
0x180021056  or      ax, 8
0x18002105a  mov     [rcx], ax
0x18002105d  movss   dword ptr [rbx+10h], xmm3
0x180021062  xorps   xmm3, xmm3
0x180021065  movups  xmm1, [rbp+var_18]
0x180021069  cvtsd2ss xmm3, xmm1
0x18002106d  cmp     [rdi+84h], r11b
0x180021074  jnz     short loc_180021088
0x180021076  movss   xmm0, dword ptr [rdi+80h]
0x18002107e  mov     rcx, rdx
0x180021081  ucomiss xmm0, xmm3
0x180021084  jp      short loc_180021088
0x180021086  jz      short loc_1800210B0
0x180021088  movss   dword ptr [rdi+80h], xmm3
0x180021090  mov     [rdi+84h], r11b
0x180021097  movzx   eax, word ptr [rcx]
0x18002109a  mov     byte ptr [rbx], 1
0x18002109d  test    al, 20h
0x18002109f  jnz     short loc_1800210AB
0x1800210a1  inc     byte ptr [rbx+1]
0x1800210a4  or      ax, 20h
0x1800210a8  mov     [rcx], ax
0x1800210ab  movss   dword ptr [rbx+18h], xmm3
0x1800210b0  movsd   xmm0, cs:__real@43f0000000000000
0x1800210b8  unpckhpd xmm1, xmm1
0x1800210bc  comisd  xmm0, xmm1
0x1800210c0  jbe     short loc_1800210CB
0x1800210c2  xorps   xmm3, xmm3
0x1800210c5  cvtsd2ss xmm3, xmm1
0x1800210c9  jmp     short loc_1800210D3
0x1800210cb  movss   xmm3, cs:__real@4d800000
0x1800210d3  cmp     [rdi+94h], r11b
0x1800210da  jnz     short loc_1800210EB
0x1800210dc  movss   xmm0, dword ptr [rdi+90h]
0x1800210e4  ucomiss xmm0, xmm3
0x1800210e7  jp      short loc_1800210EB
0x1800210e9  jz      short loc_180021117
0x1800210eb  movss   dword ptr [rdi+90h], xmm3
0x1800210f3  mov     ecx, 80h
0x1800210f8  mov     [rdi+94h], r11b
0x1800210ff  movzx   eax, word ptr [rdx]
0x180021102  mov     byte ptr [rbx], 1
0x180021105  test    cl, al
0x180021107  jnz     short loc_180021112
0x180021109  inc     byte ptr [rbx+1]
0x18002110c  or      ax, cx
  ... truncated ...
```
