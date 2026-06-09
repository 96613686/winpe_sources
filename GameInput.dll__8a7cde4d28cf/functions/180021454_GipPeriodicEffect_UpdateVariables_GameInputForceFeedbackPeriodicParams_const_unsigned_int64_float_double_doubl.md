# GipPeriodicEffect::UpdateVariables(GameInputForceFeedbackPeriodicParams const *,unsigned __int64,float,double,double *)

- ea: `0x180021454`
- end: `0x18002167e`
- name: `?UpdateVariables@GipPeriodicEffect@@IEAAPEAUGipEffectData@@PEBUGameInputForceFeedbackPeriodicParams@@_KMNPEAN@Z`
- size: `554`
- prototype: `struct GipEffectData *__fastcall(GipPeriodicEffect *__hidden this, const struct GameInputForceFeedbackPeriodicParams *, unsigned __int64, float, double, double *)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001dbe0`
- `0x18001dc10`
- `0x18001dc40`
- `0x18001dce0`
- `0x18001dd80`

## callees

- `0x180020cc4`
- `0x180021454`

## pseudocode

```c
struct GipEffectData *__fastcall GipPeriodicEffect::UpdateVariables(
        GipPeriodicEffect *this,
        const struct GameInputForceFeedbackPeriodicParams *a2,
        unsigned __int64 a3,
        float a4,
        double a5,
        double *a6)
{
  float v6; // xmm1_4
  char v9; // si
  struct GipEffectData *updated; // rdx
  double v11; // xmm2_8
  double v12; // xmm1_8
  __m128i v13; // xmm3
  int v14; // r8d
  float v15; // xmm4_4
  _WORD *v16; // rcx
  __int16 v17; // ax
  float v18; // xmm2_4
  _WORD *v19; // r9
  __int16 v20; // ax
  __int16 v21; // ax

  v6 = *((float *)a2 + 19);
  if ( v6 <= 0.0 || v6 >= 1000.0 )
  {
    v9 = 0;
    a4 = 0.0;
  }
  else
  {
    v9 = 1;
  }
  updated = GipEnvelopeEffect::UpdateVariables(this, a2, a3, a4, *((float *)a2 + 15) * a5);
  if ( v9 )
  {
    v11 = 1000.0 / *((float *)a2 + 19);
    if ( ((*(_QWORD *)&v11 >> 52) & 0x7FF) == 0xFF && (*(_QWORD *)&v11 & 0xFFFFFFFFFFFFFLL) != 0
      || ((*(_QWORD *)&v11 >> 52) & 0x7FF) == 0 && (*(_QWORD *)&v11 & 0xFFFFFFFFFFFFFLL) != 0 )
    {
      v11 = 0.0;
    }
    v12 = DOUBLE_1_0;
    if ( v11 >= 1.0 )
    {
      v12 = DOUBLE_1_6777216e7;
      if ( v11 <= 16777216.0 )
        v12 = v11;
    }
  }
  else
  {
    v12 = DOUBLE_1000_0;
  }
  v13 = (__m128i)*((unsigned int *)a2 + 21);
  v14 = _mm_cvtsi128_si32(v13);
  if ( *((int *)a2 + 15) < 0 )
  {
    v14 ^= 0x80000000;
    v13.m128i_i32[0] = v14;
  }
  v15 = *((float *)a2 + 20) / 360.0 * v12;
  if ( *((_BYTE *)this + 244) || *((float *)this + 60) != v15 )
  {
    v16 = (_WORD *)((char *)updated + 2);
    *((float *)this + 60) = v15;
    *((_BYTE *)this + 244) = 0;
    v17 = *((_WORD *)updated + 1);
    if ( (v17 & 0x1000) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *v16 = v17 | 0x1000;
    }
    *((float *)updated + 13) = v15;
  }
  else
  {
    v16 = (_WORD *)((char *)updated + 2);
  }
  v18 = v12;
  if ( *((_BYTE *)this + 252) || (v19 = v16, *((float *)this + 62) != v18) )
  {
    v19 = (_WORD *)((char *)updated + 2);
    *((float *)this + 62) = v18;
    *((_BYTE *)this + 252) = 0;
    v20 = *((_WORD *)updated + 1);
    if ( (v20 & 0x2000) == 0 )
    {
      ++*((_BYTE *)updated + 1);
      *v19 = v20 | 0x2000;
    }
    *((float *)updated + 14) = v18;
  }
  if ( *((_BYTE *)this + 260) )
  {
    v16 = v19;
  }
  else if ( *((float *)this + 64) == *(float *)v13.m128i_i32 )
  {
    goto LABEL_35;
  }
  *((_DWORD *)this + 64) = v13.m128i_i32[0];
  *((_BYTE *)this + 260) = 0;
  v21 = *v16;
  if ( (*v16 & 0x4000) == 0 )
  {
    ++*((_BYTE *)updated + 1);
    *v16 = v21 | 0x4000;
  }
  *((_DWORD *)updated + 15) = v14;
LABEL_35:
  if ( a6 )
    *a6 = v12;
  return updated;
}

```

## disassembly

```asm
0x180021454  mov     [rsp+arg_0], rbx
0x180021459  mov     [rsp+arg_8], rsi
0x18002145e  push    rdi
0x18002145f  sub     rsp, 30h
0x180021463  movss   xmm1, dword ptr [rdx+4Ch]
0x180021468  mov     rdi, rdx
0x18002146b  comiss  xmm1, cs:__real@00000000
0x180021472  mov     rbx, rcx
0x180021475  jbe     short loc_180021489
0x180021477  movss   xmm0, cs:__real@447a0000
0x18002147f  comiss  xmm0, xmm1
0x180021482  jbe     short loc_180021489
0x180021484  mov     sil, 1
0x180021487  jmp     short loc_18002148F
0x180021489  xor     sil, sil
0x18002148c  xorps   xmm3, xmm3; float
0x18002148f  movss   xmm0, dword ptr [rdx+3Ch]
0x180021494  cvtps2pd xmm0, xmm0
0x180021497  mulsd   xmm0, [rsp+38h+arg_20]
0x18002149d  movsd   [rsp+38h+var_18], xmm0; double
0x1800214a3  call    ?UpdateVariables@GipEnvelopeEffect@@IEAAPEAUGipEffectData@@PEBUGameInputForceFeedbackEnvelope@@_KMN@Z; GipEnvelopeEffect::UpdateVariables(GameInputForceFeedbackEnvelope const *,unsigned __int64,float,double)
0x1800214a8  mov     rdx, rax
0x1800214ab  test    sil, sil
0x1800214ae  jz      loc_180021534
0x1800214b4  movss   xmm0, dword ptr [rdi+4Ch]
0x1800214b9  mov     r10d, 7FFh
0x1800214bf  movsd   xmm2, cs:__real@408f400000000000
0x1800214c7  mov     r8d, 0FFh
0x1800214cd  cvtps2pd xmm0, xmm0
0x1800214d0  mov     r9, 0FFFFFFFFFFFFFh
0x1800214da  divsd   xmm2, xmm0
0x1800214de  movq    rax, xmm2
0x1800214e3  mov     rcx, rax
0x1800214e6  shr     rcx, 34h
0x1800214ea  and     cx, r10w
0x1800214ee  cmp     cx, r8w
0x1800214f2  jnz     short loc_1800214F9
0x1800214f4  test    r9, rax
0x1800214f7  jnz     short loc_180021510
0x1800214f9  movq    rcx, xmm2
0x1800214fe  mov     rax, rcx
0x180021501  shr     rax, 34h
0x180021505  test    r10w, ax
0x180021509  jnz     short loc_180021513
0x18002150b  test    r9, rcx
0x18002150e  jz      short loc_180021513
0x180021510  xorps   xmm2, xmm2
0x180021513  movsd   xmm1, cs:__real@3ff0000000000000
0x18002151b  comisd  xmm1, xmm2
0x18002151f  ja      short loc_18002153C
0x180021521  movsd   xmm1, cs:__real@4170000000000000
0x180021529  comisd  xmm2, xmm1
0x18002152d  ja      short loc_18002153C
0x18002152f  movaps  xmm1, xmm2
0x180021532  jmp     short loc_18002153C
0x180021534  movsd   xmm1, cs:__real@408f400000000000
0x18002153c  movss   xmm2, dword ptr [rdi+50h]
0x180021541  mov     eax, [rdi+3Ch]
0x180021544  movss   xmm3, dword ptr [rdi+54h]
0x180021549  cvtps2pd xmm2, xmm2
0x18002154c  shr     eax, 1Fh
0x18002154f  movd    r8d, xmm3
0x180021554  divsd   xmm2, cs:__real@4076800000000000
0x18002155c  mulsd   xmm2, xmm1
0x180021560  test    al, al
0x180021562  jz      short loc_18002156E
0x180021564  btc     r8d, 1Fh
0x180021569  movd    xmm3, r8d
0x18002156e  cmp     byte ptr [rbx+0F4h], 0
0x180021575  cvtpd2ps xmm4, xmm2
0x180021579  jnz     short loc_180021590
0x18002157b  movss   xmm0, dword ptr [rbx+0F0h]
0x180021583  ucomiss xmm0, xmm4
0x180021586  jp      short loc_180021590
0x180021588  jnz     short loc_180021590
0x18002158a  lea     rcx, [rdx+2]
0x18002158e  jmp     short loc_1800215C1
0x180021590  lea     rcx, [rdx+2]
0x180021594  movss   dword ptr [rbx+0F0h], xmm4
0x18002159c  mov     byte ptr [rbx+0F4h], 0
0x1800215a3  mov     r9d, 1000h
0x1800215a9  movzx   eax, word ptr [rcx]
0x1800215ac  test    r9w, ax
0x1800215b0  jnz     short loc_1800215BC
0x1800215b2  inc     byte ptr [rdx+1]
0x1800215b5  or      ax, r9w
0x1800215b9  mov     [rcx], ax
0x1800215bc  movss   dword ptr [rdx+34h], xmm4
0x1800215c1  cmp     byte ptr [rbx+0FCh], 0
0x1800215c8  cvtpd2ps xmm2, xmm1
0x1800215cc  jnz     short loc_1800215E0
0x1800215ce  movss   xmm0, dword ptr [rbx+0F8h]
0x1800215d6  mov     r9, rcx
0x1800215d9  ucomiss xmm0, xmm2
0x1800215dc  jp      short loc_1800215E0
0x1800215de  jz      short loc_180021613
0x1800215e0  lea     r9, [rdx+2]
0x1800215e4  movss   dword ptr [rbx+0F8h], xmm2
0x1800215ec  mov     byte ptr [rbx+0FCh], 0
0x1800215f3  mov     r10d, 2000h
0x1800215f9  movzx   eax, word ptr [r9]
0x1800215fd  test    r10w, ax
0x180021601  jnz     short loc_18002160E
0x180021603  inc     byte ptr [rdx+1]
0x180021606  or      ax, r10w
0x18002160a  mov     [r9], ax
0x18002160e  movss   dword ptr [rdx+38h], xmm2
0x180021613  cmp     byte ptr [rbx+104h], 0
0x18002161a  jnz     short loc_18002162D
0x18002161c  movss   xmm0, dword ptr [rbx+100h]
0x180021624  ucomiss xmm0, xmm3
0x180021627  jp      short loc_180021630
0x180021629  jz      short loc_18002165C
0x18002162b  jmp     short loc_180021630
0x18002162d  mov     rcx, r9
0x180021630  movss   dword ptr [rbx+100h], xmm3
0x180021638  mov     r9d, 4000h
0x18002163e  mov     byte ptr [rbx+104h], 0
0x180021645  movzx   eax, word ptr [rcx]
0x180021648  test    r9w, ax
0x18002164c  jnz     short loc_180021658
0x18002164e  inc     byte ptr [rdx+1]
0x180021651  or      ax, r9w
0x180021655  mov     [rcx], ax
0x180021658  mov     [rdx+3Ch], r8d
0x18002165c  mov     rax, [rsp+38h+arg_28]
0x180021661  test    rax, rax
0x180021664  jz      short loc_18002166A
0x180021666  movsd   qword ptr [rax], xmm1
0x18002166a  mov     rbx, [rsp+38h+arg_0]
0x18002166f  mov     rax, rdx
0x180021672  mov     rsi, [rsp+38h+arg_8]
0x180021677  add     rsp, 30h
0x18002167b  pop     rdi
0x18002167c  retn
```
