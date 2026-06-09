# GipCoefficientEffect::UpdateVariables(GameInputForceFeedbackConditionParams const *,float)

- ea: `0x180020990`
- end: `0x180020b86`
- name: `?UpdateVariables@GipCoefficientEffect@@IEAAXPEBUGameInputForceFeedbackConditionParams@@M@Z`
- size: `502`
- prototype: `void __fastcall(GipCoefficientEffect *__hidden this, const struct GameInputForceFeedbackConditionParams *, float)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001da40`

## callees

- `0x180020990`
- `0x180020b8c`

## pseudocode

```c
void __fastcall GipCoefficientEffect::UpdateVariables(
        GipCoefficientEffect *this,
        const struct GameInputForceFeedbackConditionParams *a2,
        float a3)
{
  struct GipEffectData *updated; // rax
  struct GipEffectData *v6; // r8
  float v7; // xmm1_4
  __int16 v8; // ax
  float v9; // xmm1_4
  __int16 v10; // ax
  __m128i v11; // xmm1
  __m128i v12; // xmm3
  float v13; // xmm4_4
  float v14; // xmm2_4
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  __int16 v17; // ax
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  __int16 v20; // ax

  updated = GipConditionEffect::UpdateVariables(this, a2, a3);
  v6 = updated;
  v7 = *((float *)a2 + 11) + *((float *)a2 + 12);
  if ( *((_BYTE *)this + 116) || *((float *)this + 28) != v7 )
  {
    *((float *)this + 28) = v7;
    *((_BYTE *)this + 116) = 0;
    v8 = *((_WORD *)updated + 1);
    if ( (v8 & 8) == 0 )
    {
      ++*((_BYTE *)v6 + 1);
      *((_WORD *)v6 + 1) = v8 | 8;
    }
    *((float *)v6 + 4) = v7;
  }
  v9 = *((float *)a2 + 12) - *((float *)a2 + 11);
  if ( *((_BYTE *)this + 124) || *((float *)this + 30) != v9 )
  {
    *((float *)this + 30) = v9;
    *((_BYTE *)this + 124) = 0;
    v10 = *((_WORD *)v6 + 1);
    if ( (v10 & 0x10) == 0 )
    {
      ++*((_BYTE *)v6 + 1);
      *((_WORD *)v6 + 1) = v10 | 0x10;
    }
    *((float *)v6 + 5) = v9;
  }
  v11 = (__m128i)*((unsigned int *)a2 + 7);
  if ( *((int *)a2 + 3) < 0 )
    v11 = _mm_cvtsi32_si128(_mm_cvtsi128_si32(v11) ^ 0x80000000);
  v12 = (__m128i)*((unsigned int *)a2 + 8);
  if ( *((int *)a2 + 3) < 0 )
    v12 = _mm_cvtsi32_si128(_mm_cvtsi128_si32(v12) ^ 0x80000000);
  v13 = 0.0;
  v14 = FLOAT_N1_6777216e7;
  v15 = _mm_cvtsi128_si32(v11);
  if ( (unsigned __int8)(v15 >> 23) == 0xFF && (v15 & 0x7FFFFF) != 0
    || (v16 = _mm_cvtsi128_si32(v11), !(unsigned __int8)(v16 >> 23)) && (v16 & 0x7FFFFF) != 0 )
  {
    v11.m128i_i32[0] = 0;
  }
  else if ( *(float *)v11.m128i_i32 < -16777216.0 )
  {
    *(float *)v11.m128i_i32 = FLOAT_N1_6777216e7;
    goto LABEL_22;
  }
  if ( *(float *)v11.m128i_i32 > 16777216.0 )
    *(float *)v11.m128i_i32 = FLOAT_1_6777216e7;
LABEL_22:
  if ( *((_BYTE *)this + 132) || *((float *)this + 32) != *(float *)v11.m128i_i32 )
  {
    *((_DWORD *)this + 32) = v11.m128i_i32[0];
    *((_BYTE *)this + 132) = 0;
    v17 = *((_WORD *)v6 + 1);
    if ( (v17 & 0x20) == 0 )
    {
      ++*((_BYTE *)v6 + 1);
      *((_WORD *)v6 + 1) = v17 | 0x20;
    }
    *((_DWORD *)v6 + 6) = v11.m128i_i32[0];
  }
  v18 = _mm_cvtsi128_si32(v12);
  if ( (unsigned __int8)(v18 >> 23) != 0xFF || (v18 & 0x7FFFFF) == 0 )
  {
    v19 = _mm_cvtsi128_si32(v12);
    if ( (unsigned __int8)(v19 >> 23) || (v19 & 0x7FFFFF) == 0 )
    {
      if ( *(float *)v12.m128i_i32 < -16777216.0 )
        goto LABEL_38;
      v13 = *(float *)v12.m128i_i32;
    }
  }
  if ( v13 <= 16777216.0 )
    v14 = v13;
  else
    v14 = FLOAT_1_6777216e7;
LABEL_38:
  if ( *((_BYTE *)this + 140) || *((float *)this + 34) != v14 )
  {
    *((float *)this + 34) = v14;
    *((_BYTE *)this + 140) = 0;
    v20 = *((_WORD *)v6 + 1);
    if ( (v20 & 0x40) == 0 )
    {
      ++*((_BYTE *)v6 + 1);
      *((_WORD *)v6 + 1) = v20 | 0x40;
    }
    *((float *)v6 + 7) = v14;
  }
}

```

## disassembly

```asm
0x180020990  mov     [rsp+arg_0], rbx
0x180020995  push    rdi
0x180020996  sub     rsp, 20h
0x18002099a  mov     rdi, rdx
0x18002099d  mov     rbx, rcx
0x1800209a0  call    ?UpdateVariables@GipConditionEffect@@IEAAPEAUGipEffectData@@PEBUGameInputForceFeedbackConditionParams@@M@Z; GipConditionEffect::UpdateVariables(GameInputForceFeedbackConditionParams const *,float)
0x1800209a5  movss   xmm1, dword ptr [rdi+2Ch]
0x1800209aa  xor     edx, edx
0x1800209ac  mov     r8, rax
0x1800209af  mov     r10b, 1
0x1800209b2  addss   xmm1, dword ptr [rdi+30h]
0x1800209b7  cmp     [rbx+74h], dl
0x1800209ba  jnz     short loc_1800209C8
0x1800209bc  movss   xmm0, dword ptr [rbx+70h]
0x1800209c1  ucomiss xmm0, xmm1
0x1800209c4  jp      short loc_1800209C8
0x1800209c6  jz      short loc_1800209EB
0x1800209c8  movss   dword ptr [rbx+70h], xmm1
0x1800209cd  mov     [rbx+74h], dl
0x1800209d0  movzx   eax, word ptr [rax+2]
0x1800209d4  test    al, 8
0x1800209d6  jnz     short loc_1800209E5
0x1800209d8  add     [r8+1], r10b
0x1800209dc  or      ax, 8
0x1800209e0  mov     [r8+2], ax
0x1800209e5  movss   dword ptr [r8+10h], xmm1
0x1800209eb  movss   xmm1, dword ptr [rdi+30h]
0x1800209f0  subss   xmm1, dword ptr [rdi+2Ch]
0x1800209f5  cmp     [rbx+7Ch], dl
0x1800209f8  jnz     short loc_180020A06
0x1800209fa  movss   xmm0, dword ptr [rbx+78h]
0x1800209ff  ucomiss xmm0, xmm1
0x180020a02  jp      short loc_180020A06
0x180020a04  jz      short loc_180020A2A
0x180020a06  movss   dword ptr [rbx+78h], xmm1
0x180020a0b  mov     [rbx+7Ch], dl
0x180020a0e  movzx   eax, word ptr [r8+2]
0x180020a13  test    al, 10h
0x180020a15  jnz     short loc_180020A24
0x180020a17  add     [r8+1], r10b
0x180020a1b  or      ax, 10h
0x180020a1f  mov     [r8+2], ax
0x180020a24  movss   dword ptr [r8+14h], xmm1
0x180020a2a  mov     ecx, [rdi+0Ch]
0x180020a2d  mov     r9d, 80000000h
0x180020a33  movss   xmm1, dword ptr [rdi+1Ch]
0x180020a38  shr     ecx, 1Fh
0x180020a3b  test    cl, cl
0x180020a3d  jz      short loc_180020A4A
0x180020a3f  movd    eax, xmm1
0x180020a43  xor     eax, r9d
0x180020a46  movd    xmm1, eax
0x180020a4a  movss   xmm3, dword ptr [rdi+20h]
0x180020a4f  test    cl, cl
0x180020a51  jz      short loc_180020A5E
0x180020a53  movd    eax, xmm3
0x180020a57  xor     eax, r9d
0x180020a5a  movd    xmm3, eax
0x180020a5e  movss   xmm5, cs:__real@4b800000
0x180020a66  xorps   xmm4, xmm4
0x180020a69  movss   xmm2, cs:__real@cb800000
0x180020a71  mov     r9d, 7FFFFFh
0x180020a77  movd    ecx, xmm1
0x180020a7b  mov     eax, ecx
0x180020a7d  shr     eax, 17h
0x180020a80  cmp     al, 0FFh
0x180020a82  jnz     short loc_180020A89
0x180020a84  test    r9d, ecx
0x180020a87  jnz     short loc_180020AA3
0x180020a89  movd    ecx, xmm1
0x180020a8d  mov     eax, ecx
0x180020a8f  shr     eax, 17h
0x180020a92  test    al, al
0x180020a94  jnz     loc_180020B25
0x180020a9a  test    r9d, ecx
0x180020a9d  jz      loc_180020B25
0x180020aa3  xorps   xmm1, xmm1
0x180020aa6  comiss  xmm1, xmm5
0x180020aa9  jbe     short loc_180020AAE
0x180020aab  movaps  xmm1, xmm5
0x180020aae  cmp     [rbx+84h], dl
0x180020ab4  jnz     short loc_180020AC5
0x180020ab6  movss   xmm0, dword ptr [rbx+80h]
0x180020abe  ucomiss xmm0, xmm1
0x180020ac1  jp      short loc_180020AC5
0x180020ac3  jz      short loc_180020AEF
0x180020ac5  movss   dword ptr [rbx+80h], xmm1
0x180020acd  mov     [rbx+84h], dl
0x180020ad3  movzx   eax, word ptr [r8+2]
0x180020ad8  test    al, 20h
0x180020ada  jnz     short loc_180020AE9
0x180020adc  add     [r8+1], r10b
0x180020ae0  or      ax, 20h
0x180020ae4  mov     [r8+2], ax
0x180020ae9  movss   dword ptr [r8+18h], xmm1
0x180020aef  movd    ecx, xmm3
0x180020af3  mov     eax, ecx
0x180020af5  shr     eax, 17h
0x180020af8  cmp     al, 0FFh
0x180020afa  jnz     short loc_180020B01
0x180020afc  test    r9d, ecx
0x180020aff  jnz     short loc_180020B1B
0x180020b01  movd    ecx, xmm3
0x180020b05  mov     eax, ecx
0x180020b07  shr     eax, 17h
0x180020b0a  test    al, al
0x180020b0c  jnz     short loc_180020B13
0x180020b0e  test    r9d, ecx
0x180020b11  jnz     short loc_180020B1B
0x180020b13  comiss  xmm2, xmm3
0x180020b16  ja      short loc_180020B39
0x180020b18  movaps  xmm4, xmm3
0x180020b1b  comiss  xmm4, xmm5
0x180020b1e  jbe     short loc_180020B36
0x180020b20  movaps  xmm2, xmm5
0x180020b23  jmp     short loc_180020B39
0x180020b25  comiss  xmm2, xmm1
0x180020b28  jbe     loc_180020AA6
0x180020b2e  movaps  xmm1, xmm2
0x180020b31  jmp     loc_180020AAE
0x180020b36  movaps  xmm2, xmm4
0x180020b39  cmp     [rbx+8Ch], dl
0x180020b3f  jnz     short loc_180020B50
0x180020b41  movss   xmm0, dword ptr [rbx+88h]
0x180020b49  ucomiss xmm0, xmm2
0x180020b4c  jp      short loc_180020B50
0x180020b4e  jz      short loc_180020B7A
0x180020b50  movss   dword ptr [rbx+88h], xmm2
0x180020b58  mov     [rbx+8Ch], dl
0x180020b5e  movzx   eax, word ptr [r8+2]
0x180020b63  test    al, 40h
0x180020b65  jnz     short loc_180020B74
0x180020b67  add     [r8+1], r10b
0x180020b6b  or      ax, 40h
0x180020b6f  mov     [r8+2], ax
0x180020b74  movss   dword ptr [r8+1Ch], xmm2
0x180020b7a  mov     rbx, [rsp+28h+arg_0]
0x180020b7f  add     rsp, 20h
0x180020b83  pop     rdi
0x180020b84  retn
```
