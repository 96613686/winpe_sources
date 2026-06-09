# HidForceFeedbackEffect::Apply(HidForceFeedbackEffect::TargetConfig *,unsigned __int64 *,uint *,unsigned __int64 *,HidForceFeedbackEffect::SourceConfig const &,unsigned __int64)

- ea: `0x180011168`
- end: `0x1800118d8`
- name: `?Apply@HidForceFeedbackEffect@@AEBAJPEAUTargetConfig@1@PEA_KPEAI1AEBUSourceConfig@1@_K@Z`
- size: `1904`
- prototype: `__int64 __fastcall(HidForceFeedbackEffect *__hidden this, struct HidForceFeedbackEffect::TargetConfig *, unsigned __int64 *, unsigned int *, unsigned __int64 *, const struct HidForceFeedbackEffect::SourceConfig *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800108f4`

## callees

- `0x180001304`
- `0x18000d68c`
- `0x180011168`
- `0x1800118e0`
- `0x1800119a8`
- `0x180011b50`
- `0x180012594`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackEffect::Apply(
        HidForceFeedbackEffect *this,
        struct HidForceFeedbackEffect::TargetConfig *a2,
        unsigned __int64 *a3,
        unsigned int *a4,
        unsigned __int64 *a5,
        const struct HidForceFeedbackEffect::SourceConfig *a6)
{
  const struct HidForceFeedbackEffect::SourceConfig *v6; // r12
  unsigned __int64 *v8; // rbx
  bool v11; // zf
  bool v12; // cc
  int *v14; // r14
  float *v15; // rdx
  __m128i v16; // xmm0
  unsigned int v17; // r8d
  unsigned int v18; // eax
  float v19; // xmm3_4
  __m128i v20; // xmm1
  unsigned int v21; // edx
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // r9d
  unsigned int v25; // edx
  unsigned int v26; // eax
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // edx
  unsigned __int8 v31; // r10
  unsigned __int8 v32; // r11
  __int64 v33; // rax
  __m128i v34; // xmm0
  unsigned int v35; // edx
  unsigned int v36; // eax
  __m128i v37; // xmm0
  unsigned int v38; // edx
  unsigned int v39; // eax
  __m128i v40; // xmm0
  unsigned int v41; // edx
  unsigned int v42; // eax
  __m128i v43; // xmm0
  unsigned int v44; // edx
  unsigned int v45; // eax
  __m128i v46; // xmm0
  unsigned int v47; // r8d
  unsigned int v48; // eax
  int v49; // eax
  float v50; // xmm1_4
  int v51; // esi
  __m128i v52; // xmm0
  unsigned int v53; // edx
  unsigned int v54; // eax
  unsigned __int8 v55; // r10
  unsigned __int8 v56; // r11
  int v57; // eax
  float v58; // xmm5_4
  __m128i v59; // xmm0
  unsigned int v60; // edx
  unsigned int v61; // eax
  unsigned int v62; // edx
  unsigned int v63; // eax
  unsigned __int64 v64; // [rsp+38h] [rbp-28h]
  float v65; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int64 *v66; // [rsp+B0h] [rbp+50h] BYREF

  v66 = a3;
  v6 = a6;
  v8 = a5;
  v11 = *(_DWORD *)a6 == 5;
  v12 = *(_DWORD *)a6 <= 5;
  *a3 = 0;
  *a4 = 0;
  *v8 = 0;
  v65 = 0.0;
  if ( v12 )
  {
    if ( v11 )
      goto LABEL_7;
    if ( *(_DWORD *)v6 )
    {
      if ( *(_DWORD *)v6 != 1 )
      {
        if ( *(_DWORD *)v6 == 2 || (unsigned int)(*(_DWORD *)v6 - 3) <= 1 )
        {
LABEL_7:
          v14 = (int *)((char *)a2 + 132);
          HidForceFeedbackEffect::ApplyDirection(this, a2, *(unsigned int *)v6);
          HidForceFeedbackEffect::ApplyEnvelope(
            this,
            a2,
            &v65,
            v66,
            a4,
            v8,
            (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 8),
            v64);
          v15 = (float *)((char *)v6 + 68);
          if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 1980LL) & 1) != 0 )
          {
            v16 = _mm_cvtsi32_si128(*(_DWORD *)v15 & 0x7FFFFFFF);
            *(float *)v16.m128i_i32 = (float)(*(float *)v16.m128i_i32 * v65) * 10000.0;
            v17 = _mm_cvtsi128_si32(v16);
            v18 = v17 >> 23;
            if ( (unsigned __int8)(v17 >> 23) < 0x96u )
            {
              if ( (unsigned __int8)v18 >= 0x7Fu )
                v16.m128i_i32[0] = v17 & (-1 << (-106 - v18));
              else
                v16.m128i_i32[0] = 0;
            }
            v49 = (int)*(float *)v16.m128i_i32;
          }
          else
          {
            v49 = 0;
          }
          *v14 = v49;
          v50 = *((float *)v6 + 22);
          v51 = *(_DWORD *)v6;
          if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 1980LL) & 1) == 0 || *v15 >= 0.0 )
            goto LABEL_78;
          if ( v51 > 5 )
          {
            if ( v51 == 6 )
            {
              v51 = 5;
            }
            else if ( v51 == 7 || v51 == 8 || (unsigned int)(v51 - 9) < 2 )
            {
              goto LABEL_95;
            }
          }
          else
          {
            if ( v51 != 5 )
            {
              if ( (unsigned int)v51 >= 2 )
              {
                if ( v51 == 2 || (unsigned int)(v51 - 3) <= 1 )
                  v50 = v50 + 180.0;
                goto LABEL_78;
              }
LABEL_95:
              GameInputFailFast(2147942487LL, 339);
              JUMPOUT(0x1800118D7LL);
            }
            v51 = 6;
          }
LABEL_78:
          v52 = (__m128i)*((unsigned int *)v6 + 23);
          *(float *)v52.m128i_i32 = *(float *)v52.m128i_i32 * 10000.0;
          v53 = _mm_cvtsi128_si32(v52);
          v54 = v53 >> 23;
          if ( (unsigned __int8)(v53 >> 23) < 0x96u )
          {
            if ( (unsigned __int8)v54 >= 0x7Fu )
              v52.m128i_i32[0] = v53 & (-1 << (-106 - v54));
            else
              v52.m128i_i32[0] = 0;
          }
          *((_DWORD *)a2 + 34) = (int)*(float *)v52.m128i_i32;
          *((_DWORD *)a2 + 35) = ConvertPhase(v50);
          v57 = 0;
          v58 = *((float *)v6 + 21);
          if ( v58 > 0.0 )
          {
            v59 = (__m128i)LODWORD(FLOAT_1000000_0);
            *(float *)v59.m128i_i32 = 1000000.0 / v58;
            v60 = _mm_cvtsi128_si32(v59);
            v61 = v60 >> 23;
            if ( (unsigned __int8)(v60 >> 23) < v55 )
            {
              if ( (unsigned __int8)v61 >= v56 )
                v59.m128i_i32[0] = v60 & (-1 << (v55 - v61));
              else
                v59.m128i_i32[0] = 0;
            }
            v57 = (int)*(float *)v59.m128i_i32;
          }
          *((_DWORD *)a2 + 36) = v57;
          v46 = (__m128i)*((unsigned int *)v6 + 29);
          *(float *)v46.m128i_i32 = *(float *)v46.m128i_i32 * 10000.0;
          *(_DWORD *)a2 = v51;
          *((_DWORD *)a2 + 2) = 80;
          v62 = _mm_cvtsi128_si32(v46);
          v63 = v62 >> 23;
          if ( (unsigned __int8)(v62 >> 23) < v55 )
          {
            if ( (unsigned __int8)v63 >= v56 )
              v46.m128i_i32[0] = v62 & (-1 << (v55 - v63));
            else
              v46.m128i_i32[0] = 0;
          }
          v23 = 16;
LABEL_93:
          v24 = (int)*(float *)v46.m128i_i32;
          goto LABEL_94;
        }
LABEL_26:
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          LODWORD(a5) = -2147024809;
          a6 = (const struct HidForceFeedbackEffect::SourceConfig *)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffect.cpp";
          LODWORD(v66) = 380;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            8,
            (unsigned __int8 *)&dword_18005A93C,
            (__int64)a3,
            (__int64)a4,
            (__int64 **)&a6,
            (__int64)&v66,
            (__int64)&a5);
        }
        return 2147942487LL;
      }
      v14 = (int *)((char *)a2 + 132);
      HidForceFeedbackEffect::ApplyDirection(this, a2, 1);
      HidForceFeedbackEffect::ApplyEnvelope(
        this,
        a2,
        &v65,
        a3,
        a4,
        a5,
        (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 8),
        v64);
      v19 = v65;
      HidForceFeedbackEffect::ApplySignedScalar(
        this,
        (int *)a2 + 33,
        (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 56),
        v65);
      HidForceFeedbackEffect::ApplySignedScalar(
        this,
        (int *)a2 + 34,
        (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 84),
        v19);
      v20 = (__m128i)*((unsigned int *)v6 + 29);
      *(float *)v20.m128i_i32 = *(float *)v20.m128i_i32 * 10000.0;
      *(_DWORD *)a2 = *(_DWORD *)v6;
      *((_DWORD *)a2 + 2) = 80;
      v21 = _mm_cvtsi128_si32(v20);
      v22 = v21 >> 23;
      if ( (unsigned __int8)(v21 >> 23) < 0x96u )
      {
        if ( (unsigned __int8)v22 >= 0x7Fu )
          v20.m128i_i32[0] = v21 & (-1 << (-106 - v22));
        else
          v20.m128i_i32[0] = 0;
      }
      v23 = 8;
    }
    else
    {
      v14 = (int *)((char *)a2 + 132);
      HidForceFeedbackEffect::ApplyDirection(this, a2, 0);
      HidForceFeedbackEffect::ApplyEnvelope(
        this,
        a2,
        &v65,
        a3,
        a4,
        a5,
        (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 8),
        v64);
      HidForceFeedbackEffect::ApplySignedScalar(
        this,
        (int *)a2 + 33,
        (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 56),
        v65);
      v20 = (__m128i)*((unsigned int *)v6 + 29);
      *(float *)v20.m128i_i32 = *(float *)v20.m128i_i32 * 10000.0;
      *(_DWORD *)a2 = *(_DWORD *)v6;
      *((_DWORD *)a2 + 2) = 80;
      v25 = _mm_cvtsi128_si32(v20);
      v26 = v25 >> 23;
      if ( (unsigned __int8)(v25 >> 23) < 0x96u )
      {
        if ( (unsigned __int8)v26 >= 0x7Fu )
          v20.m128i_i32[0] = v25 & (-1 << (-106 - v26));
        else
          v20.m128i_i32[0] = 0;
      }
      v23 = 4;
    }
    v24 = (int)*(float *)v20.m128i_i32;
LABEL_94:
    *((_DWORD *)a2 + 7) = -1;
    *((_DWORD *)a2 + 6) = v24;
    *((_QWORD *)a2 + 9) = v14;
    *((_DWORD *)a2 + 16) = v23;
    return 0;
  }
  if ( *(_DWORD *)v6 == 6 )
    goto LABEL_7;
  if ( *(_DWORD *)v6 != 7 && *(_DWORD *)v6 != 8 && (unsigned int)(*(_DWORD *)v6 - 9) >= 2 )
    goto LABEL_26;
  v14 = (int *)((char *)a2 + 132);
  HidForceFeedbackEffect::ApplyDirection(this, a2, *(unsigned int *)v6);
  v30 = 0;
  *v8 = 0;
  v31 = -106;
  *a3 = -1;
  *((_DWORD *)a2 + 4) = -1;
  v32 = 127;
  v33 = *((_QWORD *)this + 1);
  *a4 = 1;
  if ( (*(_BYTE *)(v33 + 1980) & 1) != 0 )
  {
    v34 = (__m128i)*((unsigned int *)v6 + 14);
    *(float *)v34.m128i_i32 = *(float *)v34.m128i_i32 * 10000.0;
    v35 = _mm_cvtsi128_si32(v34);
    v36 = v35 >> 23;
    if ( (unsigned __int8)(v35 >> 23) < 0x96u )
    {
      if ( (unsigned __int8)v36 >= 0x7Fu )
        v34.m128i_i32[0] = v35 & (-1 << (-106 - v36));
      else
        v34.m128i_i32[0] = 0;
    }
    *v14 = (int)*(float *)v34.m128i_i32;
    HidForceFeedbackEffect::ApplySignedScalar(
      this,
      (int *)a2 + 34,
      (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 8),
      *((float *)v6 + 9));
    HidForceFeedbackEffect::ApplySignedScalar(
      this,
      (int *)a2 + 35,
      (const struct HidForceFeedbackEffect::SourceConfig *)((char *)v6 + 8),
      *((float *)v6 + 10));
    v28 = 0x7FFFFFFF;
    v37 = _mm_cvtsi32_si128(*((_DWORD *)v6 + 12) & 0x7FFFFFFF);
    *(float *)v37.m128i_i32 = *(float *)v37.m128i_i32 * 10000.0;
    v38 = _mm_cvtsi128_si32(v37);
    v39 = v38 >> 23;
    if ( (unsigned __int8)(v38 >> 23) < v31 )
    {
      if ( (unsigned __int8)v39 >= v32 )
        v37.m128i_i32[0] = v38 & (-1 << (v31 - v39));
      else
        v37.m128i_i32[0] = 0;
    }
    *((_DWORD *)a2 + 36) = (int)*(float *)v37.m128i_i32;
    v40 = _mm_cvtsi32_si128(*((_DWORD *)v6 + 11) & 0x7FFFFFFF);
    *(float *)v40.m128i_i32 = *(float *)v40.m128i_i32 * 10000.0;
    v41 = _mm_cvtsi128_si32(v40);
    v42 = v41 >> 23;
    if ( (unsigned __int8)(v41 >> 23) < v31 )
    {
      if ( (unsigned __int8)v42 >= v32 )
        v40.m128i_i32[0] = v41 & (-1 << (v31 - v42));
      else
        v40.m128i_i32[0] = 0;
    }
    *((_DWORD *)a2 + 37) = (int)*(float *)v40.m128i_i32;
    v43 = (__m128i)*((unsigned int *)v6 + 13);
    *(float *)v43.m128i_i32 = *(float *)v43.m128i_i32 * 10000.0;
    v44 = _mm_cvtsi128_si32(v43);
    v45 = v44 >> 23;
    if ( (unsigned __int8)(v44 >> 23) < v31 )
    {
      if ( (unsigned __int8)v45 >= v32 )
        v43.m128i_i32[0] = v44 & (-1 << (v31 - v45));
      else
        v43.m128i_i32[0] = 0;
    }
    v30 = 1;
    *((_DWORD *)a2 + 38) = (int)*(float *)v43.m128i_i32;
  }
  if ( v30 == *((_DWORD *)a2 + 9) )
  {
    v46 = (__m128i)*((unsigned int *)v6 + 29);
    *(_DWORD *)a2 = *(_DWORD *)v6;
    *(float *)v46.m128i_i32 = *(float *)v46.m128i_i32 * 10000.0;
    *((_DWORD *)a2 + 2) = 80;
    v47 = _mm_cvtsi128_si32(v46);
    v48 = v47 >> 23;
    if ( (unsigned __int8)(v47 >> 23) < v31 )
    {
      if ( (unsigned __int8)v48 >= v32 )
        v46.m128i_i32[0] = v47 & (-1 << (v31 - v48));
      else
        v46.m128i_i32[0] = 0;
    }
    v23 = 24 * v30;
    goto LABEL_93;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    LODWORD(a5) = -2147418113;
    a6 = (const struct HidForceFeedbackEffect::SourceConfig *)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffect.cpp";
    LODWORD(v66) = 374;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      8,
      (unsigned __int8 *)word_18005BD22,
      v28,
      v29,
      (__int64 **)&a6,
      (__int64)&v66,
      (__int64)&a5);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180011168  mov     rax, rsp
0x18001116b  mov     [rax+10h], rbx
0x18001116f  mov     [rax+18h], r8
0x180011173  push    rbp
0x180011174  push    rsi
0x180011175  push    rdi
0x180011176  push    r12
0x180011178  push    r13
0x18001117a  push    r14
0x18001117c  push    r15
0x18001117e  mov     rbp, rsp
0x180011181  sub     rsp, 60h
0x180011185  mov     r12, [rbp+arg_28]
0x180011189  mov     rdi, rdx
0x18001118c  mov     rbx, [rbp+arg_20]
0x180011190  xor     edx, edx
0x180011192  movaps  xmmword ptr [rax-48h], xmm6
0x180011196  mov     rsi, r9
0x180011199  movaps  xmmword ptr [rax-58h], xmm7
0x18001119d  mov     r13, r8
0x1800111a0  cmp     dword ptr [r12], 5
0x1800111a5  mov     r15, rcx
0x1800111a8  mov     [r8], rdx
0x1800111ab  xorps   xmm6, xmm6
0x1800111ae  mov     [r9], edx
0x1800111b1  mov     [rbx], rdx
0x1800111b4  mov     [rbp+arg_0], edx
0x1800111b7  jg      loc_180011402
0x1800111bd  jz      short loc_1800111E7
0x1800111bf  mov     ecx, [r12]
0x1800111c3  test    ecx, ecx
0x1800111c5  jz      loc_180011352
0x1800111cb  sub     ecx, 1
0x1800111ce  jz      loc_18001128A
0x1800111d4  sub     ecx, 1
0x1800111d7  jz      short loc_1800111E7
0x1800111d9  sub     ecx, 1
0x1800111dc  jz      short loc_1800111E7
0x1800111de  cmp     ecx, 1
0x1800111e1  jnz     loc_18001142B
0x1800111e7  mov     r8d, [r12]
0x1800111eb  lea     r13, [r12+8]
0x1800111f0  mov     rdx, rdi
0x1800111f3  lea     r14, [rdi+84h]
0x1800111fa  mov     rcx, r15
0x1800111fd  call    ?ApplyDirection@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@W4GameInputForceFeedbackEffectKind@@@Z; HidForceFeedbackEffect::ApplyDirection(HidForceFeedbackEffect::TargetConfig *,GameInputForceFeedbackEffectKind)
0x180011202  mov     r9, [rbp+arg_10]; unsigned __int64 *
0x180011206  lea     r8, [rbp+arg_0]; float *
0x18001120a  mov     [rsp+60h+var_30], r13; struct GameInputForceFeedbackEnvelope *
0x18001120f  mov     rdx, rdi; struct HidForceFeedbackEffect::TargetConfig *
0x180011212  mov     [rsp+60h+var_38], rbx; unsigned __int64 *
0x180011217  mov     rcx, r15; this
0x18001121a  mov     [rsp+60h+var_40], rsi; unsigned int *
0x18001121f  call    ?ApplyEnvelope@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@PEAMPEA_KPEAI2PEBUGameInputForceFeedbackEnvelope@@_K@Z; HidForceFeedbackEffect::ApplyEnvelope(HidForceFeedbackEffect::TargetConfig *,float *,unsigned __int64 *,uint *,unsigned __int64 *,GameInputForceFeedbackEnvelope const *,unsigned __int64)
0x180011224  mov     rax, [r15+8]
0x180011228  lea     rdx, [r13+3Ch]
0x18001122c  movss   xmm7, cs:__real@461c4000
0x180011234  or      ebx, 0FFFFFFFFh
0x180011237  mov     r10d, 96h
0x18001123d  mov     r11b, 7Fh
0x180011240  test    byte ptr [rax+7BCh], 1
0x180011247  jz      loc_180011718
0x18001124d  mov     eax, [rdx]
0x18001124f  mov     r8d, 7FFFFFFFh
0x180011255  and     eax, r8d
0x180011258  movd    xmm0, eax
0x18001125c  mulss   xmm0, [rbp+arg_0]
0x180011261  mulss   xmm0, xmm7
0x180011265  movd    r8d, xmm0
0x18001126a  mov     eax, r8d
0x18001126d  shr     eax, 17h
0x180011270  cmp     al, r10b
0x180011273  jnb     loc_180011711
0x180011279  cmp     al, r11b
0x18001127c  jnb     loc_1800116FE
0x180011282  xorps   xmm0, xmm0
0x180011285  jmp     loc_180011711
0x18001128a  mov     r8d, 1
0x180011290  lea     rbx, [r12+8]
0x180011295  mov     rdx, rdi
0x180011298  lea     r14, [rdi+84h]
0x18001129f  mov     rcx, r15
0x1800112a2  call    ?ApplyDirection@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@W4GameInputForceFeedbackEffectKind@@@Z; HidForceFeedbackEffect::ApplyDirection(HidForceFeedbackEffect::TargetConfig *,GameInputForceFeedbackEffectKind)
0x1800112a7  mov     rax, [rbp+arg_20]
0x1800112ab  lea     r8, [rbp+arg_0]; float *
0x1800112af  mov     [rsp+60h+var_30], rbx; struct GameInputForceFeedbackEnvelope *
0x1800112b4  mov     r9, r13; unsigned __int64 *
0x1800112b7  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x1800112bc  mov     rdx, rdi; struct HidForceFeedbackEffect::TargetConfig *
0x1800112bf  mov     rcx, r15; this
0x1800112c2  mov     [rsp+60h+var_40], rsi; unsigned int *
0x1800112c7  call    ?ApplyEnvelope@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@PEAMPEA_KPEAI2PEBUGameInputForceFeedbackEnvelope@@_K@Z; HidForceFeedbackEffect::ApplyEnvelope(HidForceFeedbackEffect::TargetConfig *,float *,unsigned __int64 *,uint *,unsigned __int64 *,GameInputForceFeedbackEnvelope const *,unsigned __int64)
0x1800112cc  movss   xmm3, [rbp+arg_0]; float
0x1800112d1  lea     r8, [rbx+30h]; struct GameInputForceFeedbackMagnitude *
0x1800112d5  mov     rcx, r15; this
0x1800112d8  mov     rdx, r14; int *
0x1800112db  call    ?ApplySignedScalar@HidForceFeedbackEffect@@AEBAXPEAJAEBUGameInputForceFeedbackMagnitude@@M@Z; HidForceFeedbackEffect::ApplySignedScalar(long *,GameInputForceFeedbackMagnitude const &,float)
0x1800112e0  lea     r8, [rbx+4Ch]; struct GameInputForceFeedbackMagnitude *
0x1800112e4  mov     rcx, r15; this
0x1800112e7  lea     rdx, [r14+4]; int *
0x1800112eb  call    ?ApplySignedScalar@HidForceFeedbackEffect@@AEBAXPEAJAEBUGameInputForceFeedbackMagnitude@@M@Z; HidForceFeedbackEffect::ApplySignedScalar(long *,GameInputForceFeedbackMagnitude const &,float)
0x1800112f0  movss   xmm1, dword ptr [r12+74h]
0x1800112f7  or      ebx, 0FFFFFFFFh
0x1800112fa  mov     eax, [r12]
0x1800112fe  mov     r10d, 96h
0x180011304  mulss   xmm1, cs:__real@461c4000
0x18001130c  mov     [rdi], eax
0x18001130e  mov     dword ptr [rdi+8], 50h ; 'P'
0x180011315  movd    edx, xmm1
0x180011319  mov     eax, edx
0x18001131b  shr     eax, 17h
0x18001131e  cmp     al, r10b
0x180011321  jnb     short loc_180011343
0x180011323  mov     r11b, 7Fh
0x180011326  cmp     al, r11b
0x180011329  jnb     short loc_180011330
0x18001132b  xorps   xmm1, xmm1
0x18001132e  jmp     short loc_180011343
0x180011330  movzx   eax, al
0x180011333  sub     r10d, eax
0x180011336  mov     eax, ebx
0x180011338  mov     cl, r10b
0x18001133b  shl     eax, cl
0x18001133d  and     eax, edx
0x18001133f  movd    xmm1, eax
0x180011343  mov     ecx, 8
0x180011348  cvttss2si r9, xmm1
0x18001134d  jmp     loc_180011882
0x180011352  xor     r8d, r8d
0x180011355  lea     rbx, [r12+8]
0x18001135a  mov     rdx, rdi
0x18001135d  lea     r14, [rdi+84h]
0x180011364  mov     rcx, r15
0x180011367  call    ?ApplyDirection@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@W4GameInputForceFeedbackEffectKind@@@Z; HidForceFeedbackEffect::ApplyDirection(HidForceFeedbackEffect::TargetConfig *,GameInputForceFeedbackEffectKind)
0x18001136c  mov     rax, [rbp+arg_20]
0x180011370  lea     r8, [rbp+arg_0]; float *
0x180011374  mov     [rsp+60h+var_30], rbx; struct GameInputForceFeedbackEnvelope *
0x180011379  mov     r9, r13; unsigned __int64 *
0x18001137c  mov     [rsp+60h+var_38], rax; unsigned __int64 *
0x180011381  mov     rdx, rdi; struct HidForceFeedbackEffect::TargetConfig *
0x180011384  mov     rcx, r15; this
0x180011387  mov     [rsp+60h+var_40], rsi; unsigned int *
0x18001138c  call    ?ApplyEnvelope@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@PEAMPEA_KPEAI2PEBUGameInputForceFeedbackEnvelope@@_K@Z; HidForceFeedbackEffect::ApplyEnvelope(HidForceFeedbackEffect::TargetConfig *,float *,unsigned __int64 *,uint *,unsigned __int64 *,GameInputForceFeedbackEnvelope const *,unsigned __int64)
0x180011391  movss   xmm3, [rbp+arg_0]; float
0x180011396  lea     r8, [rbx+30h]; struct GameInputForceFeedbackMagnitude *
0x18001139a  mov     rcx, r15; this
0x18001139d  mov     rdx, r14; int *
0x1800113a0  call    ?ApplySignedScalar@HidForceFeedbackEffect@@AEBAXPEAJAEBUGameInputForceFeedbackMagnitude@@M@Z; HidForceFeedbackEffect::ApplySignedScalar(long *,GameInputForceFeedbackMagnitude const &,float)
0x1800113a5  movss   xmm1, dword ptr [r12+74h]
0x1800113ac  or      ebx, 0FFFFFFFFh
0x1800113af  mov     eax, [r12]
0x1800113b3  mov     r10d, 96h
0x1800113b9  mulss   xmm1, cs:__real@461c4000
0x1800113c1  mov     [rdi], eax
0x1800113c3  mov     dword ptr [rdi+8], 50h ; 'P'
0x1800113ca  movd    edx, xmm1
0x1800113ce  mov     eax, edx
0x1800113d0  shr     eax, 17h
0x1800113d3  cmp     al, r10b
0x1800113d6  jnb     short loc_1800113F8
0x1800113d8  mov     r11b, 7Fh
0x1800113db  cmp     al, r11b
0x1800113de  jnb     short loc_1800113E5
0x1800113e0  xorps   xmm1, xmm1
0x1800113e3  jmp     short loc_1800113F8
0x1800113e5  movzx   eax, al
0x1800113e8  sub     r10d, eax
0x1800113eb  mov     eax, ebx
0x1800113ed  mov     cl, r10b
0x1800113f0  shl     eax, cl
0x1800113f2  and     eax, edx
0x1800113f4  movd    xmm1, eax
0x1800113f8  mov     ecx, 4
0x1800113fd  jmp     loc_180011348
0x180011402  mov     ecx, [r12]
0x180011406  sub     ecx, 6
0x180011409  jz      loc_1800111E7
0x18001140f  sub     ecx, 1
0x180011412  jz      loc_1800114A2
0x180011418  sub     ecx, 1
0x18001141b  jz      loc_1800114A2
0x180011421  sub     ecx, 1
0x180011424  jz      short loc_1800114A2
0x180011426  cmp     ecx, 1
0x180011429  jz      short loc_1800114A2
0x18001142b  mov     eax, cs:dword_180069000
0x180011431  cmp     eax, 2
0x180011434  jbe     short loc_180011498
0x180011436  mov     rdx, cs:qword_180069018
0x18001143d  mov     ecx, 8
0x180011442  mov     rax, cs:qword_180069010
0x180011449  test    cl, al
0x18001144b  jz      short loc_180011498
0x18001144d  mov     rax, rdx
0x180011450  and     rax, rcx
0x180011453  cmp     rax, rdx
0x180011456  jnz     short loc_180011498
0x180011458  lea     rax, aOnecoreXboxGam_25; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18001145f  mov     dword ptr [rbp+arg_20], 80070057h
0x180011466  mov     [rbp+arg_28], rax
0x18001146a  lea     rdx, dword_18005A93C
0x180011471  lea     rax, [rbp+arg_20]
0x180011475  mov     dword ptr [rbp+arg_10], 17Ch
0x18001147c  mov     [rsp+60h+var_30], rax
0x180011481  lea     rax, [rbp+arg_10]
0x180011485  mov     [rsp+60h+var_38], rax
0x18001148a  lea     rax, [rbp+arg_28]
0x18001148e  mov     [rsp+60h+var_40], rax
0x180011493  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011498  mov     eax, 80070057h
0x18001149d  jmp     loc_1800118A5
0x1800114a2  mov     r8d, [r12]
0x1800114a6  lea     r14, [rdi+84h]
0x1800114ad  mov     rdx, rdi
0x1800114b0  mov     rcx, r15
0x1800114b3  call    ?ApplyDirection@HidForceFeedbackEffect@@AEBAXPEAUTargetConfig@1@W4GameInputForceFeedbackEffectKind@@@Z; HidForceFeedbackEffect::ApplyDirection(HidForceFeedbackEffect::TargetConfig *,GameInputForceFeedbackEffectKind)
0x1800114b8  movss   xmm2, cs:__real@461c4000
0x1800114c0  xor     edx, edx
0x1800114c2  mov     qword ptr [rbx], 0
0x1800114c9  mov     r10d, 96h
0x1800114cf  or      ebx, 0FFFFFFFFh
0x1800114d2  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x1800114da  mov     [rdi+10h], ebx
0x1800114dd  mov     r11b, 7Fh
0x1800114e0  mov     rax, [r15+8]
0x1800114e4  mov     dword ptr [rsi], 1
0x1800114ea  test    byte ptr [rax+7BCh], 1
0x1800114f1  jz      loc_180011631
0x1800114f7  movss   xmm0, dword ptr [r12+38h]
0x1800114fe  mulss   xmm0, xmm2
0x180011502  movd    edx, xmm0
0x180011506  mov     eax, edx
0x180011508  shr     eax, 17h
0x18001150b  cmp     al, r10b
0x18001150e  jnb     short loc_18001152C
0x180011510  cmp     al, r11b
0x180011513  jnb     short loc_18001151A
0x180011515  xorps   xmm0, xmm0
0x180011518  jmp     short loc_18001152C
0x18001151a  movzx   eax, al
0x18001151d  mov     ecx, r10d
0x180011520  sub     ecx, eax
0x180011522  mov     eax, ebx
0x180011524  shl     eax, cl
0x180011526  and     eax, edx
0x180011528  movd    xmm0, eax
0x18001152c  cvttss2si eax, xmm0
0x180011530  lea     rdx, [r14+4]; int *
0x180011534  mov     rcx, r15; this
0x180011537  lea     r8, [r12+8]; struct GameInputForceFeedbackMagnitude *
0x18001153c  mov     [r14], eax
0x18001153f  movss   xmm3, dword ptr [r12+24h]; float
0x180011546  call    ?ApplySignedScalar@HidForceFeedbackEffect@@AEBAXPEAJAEBUGameInputForceFeedbackMagnitude@@M@Z; HidForceFeedbackEffect::ApplySignedScalar(long *,GameInputForceFeedbackMagnitude const &,float)
0x18001154b  movss   xmm3, dword ptr [r12+28h]; float
0x180011552  lea     r8, [r12+8]; struct GameInputForceFeedbackMagnitude *
0x180011557  mov     rcx, r15; this
0x18001155a  lea     rdx, [r14+8]; int *
0x18001155e  call    ?ApplySignedScalar@HidForceFeedbackEffect@@AEBAXPEAJAEBUGameInputForceFeedbackMagnitude@@M@Z; HidForceFeedbackEffect::ApplySignedScalar(long *,GameInputForceFeedbackMagnitude const &,float)
0x180011563  mov     eax, [r12+30h]
0x180011568  mov     r8d, 7FFFFFFFh
0x18001156e  and     eax, r8d
0x180011571  movd    xmm0, eax
0x180011575  mulss   xmm0, xmm2
0x180011579  movd    edx, xmm0
0x18001157d  mov     eax, edx
0x18001157f  shr     eax, 17h
0x180011582  cmp     al, r10b
0x180011585  jnb     short loc_1800115A3
0x180011587  cmp     al, r11b
0x18001158a  jnb     short loc_180011591
0x18001158c  xorps   xmm0, xmm0
0x18001158f  jmp     short loc_1800115A3
0x180011591  movzx   eax, al
0x180011594  mov     ecx, r10d
0x180011597  sub     ecx, eax
0x180011599  mov     eax, ebx
0x18001159b  shl     eax, cl
0x18001159d  and     eax, edx
0x18001159f  movd    xmm0, eax
0x1800115a3  cvttss2si rax, xmm0
0x1800115a8  mov     [r14+0Ch], eax
0x1800115ac  mov     eax, [r12+2Ch]
0x1800115b1  and     eax, r8d
0x1800115b4  movd    xmm0, eax
0x1800115b8  mulss   xmm0, xmm2
0x1800115bc  movd    edx, xmm0
0x1800115c0  mov     eax, edx
0x1800115c2  shr     eax, 17h
0x1800115c5  cmp     al, r10b
0x1800115c8  jnb     short loc_1800115E6
0x1800115ca  cmp     al, r11b
0x1800115cd  jnb     short loc_1800115D4
0x1800115cf  xorps   xmm0, xmm0
0x1800115d2  jmp     short loc_1800115E6
0x1800115d4  movzx   eax, al
0x1800115d7  mov     ecx, r10d
0x1800115da  sub     ecx, eax
0x1800115dc  mov     eax, ebx
0x1800115de  shl     eax, cl
0x1800115e0  and     eax, edx
  ... truncated ...
```
