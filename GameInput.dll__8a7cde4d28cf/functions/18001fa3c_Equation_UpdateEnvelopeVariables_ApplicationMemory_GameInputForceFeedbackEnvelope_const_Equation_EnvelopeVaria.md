# Equation::UpdateEnvelopeVariables(ApplicationMemory &,GameInputForceFeedbackEnvelope const *,Equation::EnvelopeVariables *)

- ea: `0x18001fa3c`
- end: `0x180020218`
- name: `?UpdateEnvelopeVariables@Equation@@IEAAJAEAVApplicationMemory@@PEBUGameInputForceFeedbackEnvelope@@PEAUEnvelopeVariables@1@@Z`
- size: `2012`
- prototype: `__int64 __fastcall(Equation *__hidden this, struct ApplicationMemory *, const struct GameInputForceFeedbackEnvelope *, struct Equation::EnvelopeVariables *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180020860`
- `0x180021684`
- `0x180021a30`

## callees

- `0x180001304`
- `0x180017e70`
- `0x18001fa3c`
- `0x180020718`

## pseudocode

```c
__int64 __fastcall Equation::UpdateEnvelopeVariables(
        Equation *this,
        struct ApplicationMemory *a2,
        const struct GameInputForceFeedbackEnvelope *a3,
        struct Equation::EnvelopeVariables *a4)
{
  unsigned int v4; // r13d
  unsigned __int64 v6; // rcx
  unsigned __int64 v8; // r9
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __m128i v14; // xmm8
  __m128i v15; // xmm6
  float v16; // xmm6_4
  __int64 v17; // rcx
  __int64 v18; // r15
  float v19; // xmm12_4
  __m128i v20; // xmm9
  float v21; // xmm9_4
  __int64 v22; // rcx
  float v23; // xmm8_4
  __int64 v24; // rax
  __m128i v25; // xmm11
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __m128i v28; // xmm7
  __m128i v29; // xmm10
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  __m128i v32; // xmm0
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned __int16 v35; // ax
  void *v36; // r8
  __int16 v37; // r10
  unsigned int updated; // ebx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rcx
  char *v42; // rdx
  __m128i v44; // xmm6
  float v45; // xmm6_4
  unsigned __int16 v46; // ax
  void *v47; // r8
  unsigned __int16 v48; // ax
  void *v49; // r8
  unsigned __int16 v50; // ax
  void *v51; // r8
  unsigned __int16 v52; // ax
  void *v53; // r8
  unsigned __int16 v54; // ax
  void *v55; // r8
  unsigned __int16 v56; // ax
  void *v57; // r8
  unsigned __int16 v58; // ax
  void *v59; // r8
  unsigned int v60; // [rsp+F8h] [rbp+67h] BYREF
  int v61; // [rsp+108h] [rbp+77h] BYREF
  const char *v62; // [rsp+110h] [rbp+7Fh] BYREF

  v4 = *((_DWORD *)a3 + 9);
  v6 = *(_QWORD *)a3;
  if ( v4 > 1 )
    v4 = 1;
  v8 = *((_QWORD *)a3 + 1);
  v11 = -1;
  if ( v8 < ~v6 )
    v11 = v8 + v6;
  if ( v6 < ~v11 )
    v12 = v6 + v11;
  else
    v12 = -1;
  if ( v4 )
    v13 = v12;
  else
    v13 = 0;
  *((_QWORD *)this + 8) = v13;
  v14 = (__m128i)LODWORD(FLOAT_N1_0);
  v15 = (__m128i)LODWORD(FLOAT_N1_0);
  if ( v12 )
  {
    v15 = 0;
    if ( v12 < 0 )
      v16 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v16 = (float)(int)v12;
    *(float *)v15.m128i_i32 = v16 * *(float *)(*((_QWORD *)this + 5) + 4LL);
  }
  v17 = *(_QWORD *)a3;
  v18 = *((_QWORD *)a3 + 5);
  v19 = *(float *)(*((_QWORD *)this + 5) + 4LL);
  if ( *(_QWORD *)a3 )
  {
    v20 = 0;
    if ( *(__int64 *)a3 < 0 )
      v21 = (float)(v17 & 1 | (*(_QWORD *)a3 >> 1)) + (float)(v17 & 1 | (*(_QWORD *)a3 >> 1));
    else
      v21 = (float)(int)v17;
    *(float *)v20.m128i_i32 = v21 * v19;
  }
  else
  {
    v20 = (__m128i)LODWORD(FLOAT_N1_0);
  }
  v22 = *((_QWORD *)a3 + 2);
  if ( v22 )
  {
    v14 = 0;
    if ( v22 < 0 )
    {
      v24 = *((_QWORD *)a3 + 2) & 1LL | (*((_QWORD *)a3 + 2) >> 1);
      v23 = (float)(int)v24 + (float)(int)v24;
    }
    else
    {
      v23 = (float)(int)v22;
    }
    *(float *)v14.m128i_i32 = v23 * v19;
  }
  v25 = (__m128i)*((unsigned int *)a3 + 6);
  v26 = _mm_cvtsi128_si32(v25);
  if ( (unsigned __int8)(v26 >> 23) == 0xFF && (v26 & 0x7FFFFF) != 0
    || (v27 = _mm_cvtsi128_si32(v25), !(unsigned __int8)(v27 >> 23)) && (v27 & 0x7FFFFF) != 0 )
  {
    v28 = 0;
    v25 = 0;
  }
  else
  {
    v28 = 0;
    if ( *(float *)v25.m128i_i32 < 0.0 )
    {
      v25 = 0;
      goto LABEL_34;
    }
  }
  if ( *(float *)v25.m128i_i32 > 1.0 )
    v25 = (__m128i)LODWORD(FLOAT_1_0);
LABEL_34:
  v29 = (__m128i)*((unsigned int *)a3 + 8);
  v30 = _mm_cvtsi128_si32(v29);
  if ( (unsigned __int8)(v30 >> 23) == 0xFF && (v30 & 0x7FFFFF) != 0
    || (v31 = _mm_cvtsi128_si32(v29), !(unsigned __int8)(v31 >> 23)) && (v31 & 0x7FFFFF) != 0 )
  {
    v29 = 0;
  }
  else if ( *(float *)v28.m128i_i32 > *(float *)v29.m128i_i32 )
  {
    v29 = 0;
    goto LABEL_41;
  }
  if ( *(float *)v29.m128i_i32 > 1.0 )
    v29 = (__m128i)LODWORD(FLOAT_1_0);
LABEL_41:
  v32 = (__m128i)*((unsigned int *)a3 + 7);
  v33 = _mm_cvtsi128_si32(v32);
  if ( (unsigned __int8)(v33 >> 23) != 0xFF || (v33 & 0x7FFFFF) == 0 )
  {
    v34 = _mm_cvtsi128_si32(v32);
    if ( (unsigned __int8)(v34 >> 23) || (v34 & 0x7FFFFF) == 0 )
    {
      if ( *(float *)v28.m128i_i32 > *(float *)v32.m128i_i32 )
        goto LABEL_49;
      v28 = (__m128i)*((unsigned int *)a3 + 7);
    }
  }
  if ( *(float *)v28.m128i_i32 > 1.0 )
    v28 = (__m128i)LODWORD(FLOAT_1_0);
LABEL_49:
  if ( *(float *)a4 != *(float *)v15.m128i_i32 )
  {
    v35 = Equation::LookupVariableAddress(this, L"DURATION");
    if ( v35 == v37 )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v35, v36, _mm_cvtsi128_si32(v15));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 314;
      v42 = (char *)word_18005DC9A;
LABEL_56:
      v62 = "onecore\\xbox\\gameinput\\feedback\\gipequationmanager\\Equation.cpp";
      v60 = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v41,
        (unsigned __int8 *)v42,
        v39,
        v40,
        (__int64 **)&v62,
        (__int64)&v61,
        (__int64)&v60);
      return updated;
    }
    *(_DWORD *)a4 = v15.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  v44 = 0;
  if ( v18 < 0 )
    v45 = (float)(v18 & 1 | (unsigned int)((unsigned __int64)v18 >> 1))
        + (float)(v18 & 1 | (unsigned int)((unsigned __int64)v18 >> 1));
  else
    v45 = (float)(int)v18;
  *(float *)v44.m128i_i32 = v45 * v19;
  if ( *((float *)a4 + 1) != *(float *)v44.m128i_i32 )
  {
    v46 = Equation::LookupVariableAddress(this, L"STARTDELAY");
    if ( v46 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v46, v47, _mm_cvtsi128_si32(v44));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 324;
      v42 = byte_18005DC1D;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 1) = v44.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((_DWORD *)a4 + 2) != v4 )
  {
    v48 = Equation::LookupVariableAddress(this, L"LOOPCOUNT");
    if ( v48 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v48, v49, v4);
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 333;
      v42 = (char *)&unk_18005E628;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 2) = v4;
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((float *)a4 + 3) != *(float *)v20.m128i_i32 )
  {
    v50 = Equation::LookupVariableAddress(this, L"ATTACKTIME");
    if ( v50 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v50, v51, _mm_cvtsi128_si32(v20));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 342;
      v42 = &byte_18005CA47;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 3) = v20.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((float *)a4 + 4) != *(float *)v14.m128i_i32 )
  {
    v52 = Equation::LookupVariableAddress(this, L"FADETIME");
    if ( v52 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v52, v53, _mm_cvtsi128_si32(v14));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 351;
      v42 = &byte_18005B517;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 4) = v14.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((float *)a4 + 5) != *(float *)v25.m128i_i32 )
  {
    v54 = Equation::LookupVariableAddress(this, L"ATTACKLEVEL");
    if ( v54 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v54, v55, _mm_cvtsi128_si32(v25));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 360;
      v42 = (char *)&word_18005A346;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 5) = v25.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((float *)a4 + 6) != *(float *)v29.m128i_i32 )
  {
    v56 = Equation::LookupVariableAddress(this, L"FADELEVEL");
    if ( v56 == 0xFFFF )
      return 2147549183LL;
    updated = ApplicationMemory::UpdateVariable(a2, v56, v57, _mm_cvtsi128_si32(v29));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 369;
      v42 = byte_18005AB35;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 6) = v29.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((float *)a4 + 7) == *(float *)v28.m128i_i32 )
    return 0;
  v58 = Equation::LookupVariableAddress(this, L"MAGNITUDE");
  if ( v58 != 0xFFFF )
  {
    updated = ApplicationMemory::UpdateVariable(a2, v58, v59, _mm_cvtsi128_si32(v28));
    if ( (updated & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        return updated;
      v41 = qword_180069010;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        return updated;
      v61 = 378;
      v42 = byte_18005C953;
      goto LABEL_56;
    }
    *((_DWORD *)a4 + 7) = v28.m128i_i32[0];
    *((_QWORD *)this + 10) = 0;
    return 0;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18001fa3c  mov     rax, rsp
0x18001fa3f  mov     [rax+10h], rbx
0x18001fa43  push    rbp
0x18001fa44  push    rsi
0x18001fa45  push    rdi
0x18001fa46  push    r12
0x18001fa48  push    r13
0x18001fa4a  push    r14
0x18001fa4c  push    r15
0x18001fa4e  lea     rbp, [rax-5Fh]
0x18001fa52  sub     rsp, 0B0h
0x18001fa59  mov     r13d, [r8+24h]
0x18001fa5d  mov     r10d, 1
0x18001fa63  movaps  xmmword ptr [rax-48h], xmm6
0x18001fa67  cmp     r13d, r10d
0x18001fa6a  movaps  xmmword ptr [rax-58h], xmm7
0x18001fa6e  mov     rdi, rcx
0x18001fa71  mov     rcx, [r8]
0x18001fa74  cmova   r13d, r10d
0x18001fa78  movaps  xmmword ptr [rax-68h], xmm8
0x18001fa7d  mov     rsi, r9
0x18001fa80  mov     r9, [r8+8]
0x18001fa84  mov     r14, r8
0x18001fa87  movaps  xmmword ptr [rax-78h], xmm9
0x18001fa8c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fa90  movaps  [rsp+0E0h+var_88+8], xmm10
0x18001fa96  mov     rax, rcx
0x18001fa99  not     rax
0x18001fa9c  movaps  [rsp+0E0h+var_98+8], xmm11
0x18001faa2  movaps  [rsp+0E0h+var_A8+8], xmm12
0x18001faa8  mov     r12, rdx
0x18001faab  mov     rdx, r8
0x18001faae  cmp     r9, rax
0x18001fab1  jnb     short loc_18001FAB7
0x18001fab3  lea     rdx, [r9+rcx]
0x18001fab7  mov     rax, rdx
0x18001faba  not     rax
0x18001fabd  cmp     rcx, rax
0x18001fac0  jb      short loc_18001FAC7
0x18001fac2  mov     rdx, r8
0x18001fac5  jmp     short loc_18001FACA
0x18001fac7  add     rdx, rcx
0x18001faca  test    r13d, r13d
0x18001facd  jnz     short loc_18001FAD4
0x18001facf  xor     r8d, r8d
0x18001fad2  jmp     short loc_18001FB3F
0x18001fad4  cmp     r13d, r10d
0x18001fad7  jnz     short loc_18001FADE
0x18001fad9  mov     r8, rdx
0x18001fadc  jmp     short loc_18001FB3F
0x18001fade  mov     rax, [r14+28h]
0x18001fae2  mov     r11, rdx
0x18001fae5  not     r11
0x18001fae8  mov     r10, r8
0x18001faeb  cmp     rax, r11
0x18001faee  jnb     short loc_18001FAF4
0x18001faf0  lea     r10, [rdx+rax]
0x18001faf4  mov     ebx, r10d
0x18001faf7  lea     ecx, [r13-1]
0x18001fafb  shr     r10, 20h
0x18001faff  imul    r10, rcx
0x18001fb03  imul    rbx, rcx
0x18001fb07  mov     eax, r10d
0x18001fb0a  shr     r10, 20h
0x18001fb0e  mov     r9, rbx
0x18001fb11  shr     r9, 20h
0x18001fb15  add     r9, rax
0x18001fb18  mov     rax, r9
0x18001fb1b  shr     rax, 20h
0x18001fb1f  add     r10, rax
0x18001fb22  jz      short loc_18001FB29
0x18001fb24  mov     r9, r8
0x18001fb27  jmp     short loc_18001FB30
0x18001fb29  shl     r9, 20h
0x18001fb2d  add     r9, rbx
0x18001fb30  cmp     r9, r11
0x18001fb33  jnb     short loc_18001FB39
0x18001fb35  lea     r8, [r9+rdx]
0x18001fb39  mov     r10d, 1
0x18001fb3f  mov     [rdi+40h], r8
0x18001fb43  movss   xmm8, cs:__real@bf800000
0x18001fb4c  movaps  xmm6, xmm8
0x18001fb50  test    rdx, rdx
0x18001fb53  jz      short loc_18001FB7F
0x18001fb55  mov     rcx, [rdi+28h]
0x18001fb59  xorps   xmm6, xmm6
0x18001fb5c  js      short loc_18001FB65
0x18001fb5e  cvtsi2ss xmm6, rdx
0x18001fb63  jmp     short loc_18001FB7A
0x18001fb65  mov     rax, rdx
0x18001fb68  and     rdx, r10
0x18001fb6b  shr     rax, 1
0x18001fb6e  or      rax, rdx
0x18001fb71  cvtsi2ss xmm6, rax
0x18001fb76  addss   xmm6, xmm6
0x18001fb7a  mulss   xmm6, dword ptr [rcx+4]
0x18001fb7f  mov     rax, [rdi+28h]
0x18001fb83  mov     rcx, [r14]
0x18001fb86  mov     r15, [r14+28h]
0x18001fb8a  movss   xmm12, dword ptr [rax+4]
0x18001fb90  test    rcx, rcx
0x18001fb93  jz      short loc_18001FBBF
0x18001fb95  xorps   xmm9, xmm9
0x18001fb99  js      short loc_18001FBA2
0x18001fb9b  cvtsi2ss xmm9, rcx
0x18001fba0  jmp     short loc_18001FBB8
0x18001fba2  mov     rax, rcx
0x18001fba5  and     rcx, r10
0x18001fba8  shr     rax, 1
0x18001fbab  or      rax, rcx
0x18001fbae  cvtsi2ss xmm9, rax
0x18001fbb3  addss   xmm9, xmm9
0x18001fbb8  mulss   xmm9, xmm12
0x18001fbbd  jmp     short loc_18001FBC3
0x18001fbbf  movaps  xmm9, xmm8
0x18001fbc3  mov     rcx, [r14+10h]
0x18001fbc7  test    rcx, rcx
0x18001fbca  jz      short loc_18001FBF4
0x18001fbcc  xorps   xmm8, xmm8
0x18001fbd0  js      short loc_18001FBD9
0x18001fbd2  cvtsi2ss xmm8, rcx
0x18001fbd7  jmp     short loc_18001FBEF
0x18001fbd9  mov     rax, rcx
0x18001fbdc  and     rcx, r10
0x18001fbdf  shr     rax, 1
0x18001fbe2  or      rax, rcx
0x18001fbe5  cvtsi2ss xmm8, rax
0x18001fbea  addss   xmm8, xmm8
0x18001fbef  mulss   xmm8, xmm12
0x18001fbf4  movss   xmm11, dword ptr [r14+18h]
0x18001fbfa  mov     r8b, 0FFh
0x18001fbfd  movss   xmm1, cs:__real@3f800000
0x18001fc05  mov     edx, 7FFFFFh
0x18001fc0a  movd    ecx, xmm11
0x18001fc0f  mov     eax, ecx
0x18001fc11  shr     eax, 17h
0x18001fc14  cmp     al, r8b
0x18001fc17  jnz     short loc_18001FC1D
0x18001fc19  test    edx, ecx
0x18001fc1b  jnz     short loc_18001FC37
0x18001fc1d  movd    ecx, xmm11
0x18001fc22  mov     eax, ecx
0x18001fc24  shr     eax, 17h
0x18001fc27  test    al, al
0x18001fc29  jnz     loc_18001FD7D
0x18001fc2f  test    edx, ecx
0x18001fc31  jz      loc_18001FD7D
0x18001fc37  xorps   xmm7, xmm7
0x18001fc3a  xorps   xmm11, xmm11
0x18001fc3e  comiss  xmm11, xmm1
0x18001fc42  jbe     short loc_18001FC48
0x18001fc44  movaps  xmm11, xmm1
0x18001fc48  movss   xmm10, dword ptr [r14+20h]
0x18001fc4e  movd    ecx, xmm10
0x18001fc53  mov     eax, ecx
0x18001fc55  shr     eax, 17h
0x18001fc58  cmp     al, r8b
0x18001fc5b  jnz     short loc_18001FC61
0x18001fc5d  test    edx, ecx
0x18001fc5f  jnz     short loc_18001FC7B
0x18001fc61  movd    ecx, xmm10
0x18001fc66  mov     eax, ecx
0x18001fc68  shr     eax, 17h
0x18001fc6b  test    al, al
0x18001fc6d  jnz     loc_18001FD93
0x18001fc73  test    edx, ecx
0x18001fc75  jz      loc_18001FD93
0x18001fc7b  xorps   xmm10, xmm10
0x18001fc7f  comiss  xmm10, xmm1
0x18001fc83  jbe     short loc_18001FC89
0x18001fc85  movaps  xmm10, xmm1
0x18001fc89  movss   xmm0, dword ptr [r14+1Ch]
0x18001fc8f  movd    ecx, xmm0
0x18001fc93  mov     eax, ecx
0x18001fc95  shr     eax, 17h
0x18001fc98  cmp     al, r8b
0x18001fc9b  jnz     short loc_18001FCA5
0x18001fc9d  test    edx, ecx
0x18001fc9f  jnz     loc_18001FDA6
0x18001fca5  movd    ecx, xmm0
0x18001fca9  xor     r14d, r14d
0x18001fcac  mov     eax, ecx
0x18001fcae  shr     eax, 17h
0x18001fcb1  test    al, al
0x18001fcb3  jnz     short loc_18001FCB9
0x18001fcb5  test    edx, ecx
0x18001fcb7  jnz     short loc_18001FCC1
0x18001fcb9  comiss  xmm7, xmm0
0x18001fcbc  ja      short loc_18001FCC9
0x18001fcbe  movaps  xmm7, xmm0
0x18001fcc1  comiss  xmm7, xmm1
0x18001fcc4  jbe     short loc_18001FCC9
0x18001fcc6  movaps  xmm7, xmm1
0x18001fcc9  movss   xmm0, dword ptr [rsi]
0x18001fccd  mov     r10d, 0FFFFh
0x18001fcd3  ucomiss xmm0, xmm6
0x18001fcd6  jp      short loc_18001FCDE
0x18001fcd8  jz      loc_18001FDB6
0x18001fcde  lea     rdx, aDuration; "DURATION"
0x18001fce5  mov     rcx, rdi; this
0x18001fce8  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001fced  cmp     ax, r10w
0x18001fcf1  jz      loc_1800201D4
0x18001fcf7  movd    r9d, xmm6; unsigned int
0x18001fcfc  movzx   edx, ax; unsigned __int16
0x18001fcff  mov     rcx, r12; this
0x18001fd02  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001fd07  mov     ebx, eax
0x18001fd09  test    eax, eax
0x18001fd0b  jns     loc_18001FDAE
0x18001fd11  mov     ecx, cs:dword_180069000
0x18001fd17  cmp     ecx, 2
0x18001fd1a  jbe     short loc_18001FD76
0x18001fd1c  mov     rdx, cs:qword_180069018
0x18001fd23  mov     rcx, cs:qword_180069010
0x18001fd2a  test    cl, 8
0x18001fd2d  jz      short loc_18001FD76
0x18001fd2f  mov     rax, rdx
0x18001fd32  and     eax, 8
0x18001fd35  cmp     rax, rdx
0x18001fd38  jnz     short loc_18001FD76
0x18001fd3a  mov     [rbp+57h+arg_10], 13Ah
0x18001fd41  lea     rdx, word_18005DC9A
0x18001fd48  lea     rax, aOnecoreXboxGam_14; "onecore\\xbox\\gameinput\\feedback\\gip"...
0x18001fd4f  mov     [rbp+57h+arg_18], rax
0x18001fd53  lea     rax, [rbp+57h+arg_0]
0x18001fd57  mov     [rsp+0E0h+var_B0], rax
0x18001fd5c  lea     rax, [rbp+57h+arg_10]
0x18001fd60  mov     [rsp+0E0h+var_B8], rax
0x18001fd65  lea     rax, [rbp+57h+arg_18]
0x18001fd69  mov     [rsp+0E0h+var_C0], rax
0x18001fd6e  mov     [rbp+57h+arg_0], ebx
0x18001fd71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001fd76  mov     eax, ebx
0x18001fd78  jmp     loc_1800201D9
0x18001fd7d  xorps   xmm7, xmm7
0x18001fd80  comiss  xmm7, xmm11
0x18001fd84  jbe     loc_18001FC3E
0x18001fd8a  xorps   xmm11, xmm11
0x18001fd8e  jmp     loc_18001FC48
0x18001fd93  comiss  xmm7, xmm10
0x18001fd97  jbe     loc_18001FC7F
0x18001fd9d  xorps   xmm10, xmm10
0x18001fda1  jmp     loc_18001FC89
0x18001fda6  xor     r14d, r14d
0x18001fda9  jmp     loc_18001FCC1
0x18001fdae  movss   dword ptr [rsi], xmm6
0x18001fdb2  mov     [rdi+50h], r14
0x18001fdb6  xorps   xmm6, xmm6
0x18001fdb9  test    r15, r15
0x18001fdbc  js      short loc_18001FDC5
0x18001fdbe  cvtsi2ss xmm6, r15
0x18001fdc3  jmp     short loc_18001FDDB
0x18001fdc5  mov     rax, r15
0x18001fdc8  and     r15d, 1
0x18001fdcc  shr     rax, 1
0x18001fdcf  or      rax, r15
0x18001fdd2  cvtsi2ss xmm6, rax
0x18001fdd7  addss   xmm6, xmm6
0x18001fddb  movss   xmm0, dword ptr [rsi+4]
0x18001fde0  mulss   xmm6, xmm12
0x18001fde5  ucomiss xmm0, xmm6
0x18001fde8  jp      short loc_18001FDF7
0x18001fdea  jnz     short loc_18001FDF7
0x18001fdec  mov     r15d, 0FFFFh
0x18001fdf2  jmp     loc_18001FE7D
0x18001fdf7  lea     rdx, aStartdelay; "STARTDELAY"
0x18001fdfe  mov     rcx, rdi; this
0x18001fe01  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
0x18001fe06  mov     r15d, 0FFFFh
0x18001fe0c  cmp     ax, r15w
0x18001fe10  jz      loc_1800201D4
0x18001fe16  movd    r9d, xmm6; unsigned int
0x18001fe1b  movzx   edx, ax; unsigned __int16
0x18001fe1e  mov     rcx, r12; this
0x18001fe21  call    ?UpdateVariable@ApplicationMemory@@QEAAJGPEAXI@Z; ApplicationMemory::UpdateVariable(ushort,void *,uint)
0x18001fe26  mov     ebx, eax
0x18001fe28  test    eax, eax
0x18001fe2a  jns     short loc_18001FE74
0x18001fe2c  mov     ecx, cs:dword_180069000
0x18001fe32  cmp     ecx, 2
0x18001fe35  jbe     loc_18001FD76
0x18001fe3b  mov     rdx, cs:qword_180069018
0x18001fe42  mov     rcx, cs:qword_180069010
0x18001fe49  test    cl, 8
0x18001fe4c  jz      loc_18001FD76
0x18001fe52  mov     rax, rdx
0x18001fe55  and     eax, 8
0x18001fe58  cmp     rax, rdx
0x18001fe5b  jnz     loc_18001FD76
0x18001fe61  mov     [rbp+57h+arg_10], 144h
0x18001fe68  lea     rdx, byte_18005DC1D
0x18001fe6f  jmp     loc_18001FD48
0x18001fe74  movss   dword ptr [rsi+4], xmm6
0x18001fe79  mov     [rdi+50h], r14
0x18001fe7d  cmp     [rsi+8], r13d
0x18001fe81  jz      short loc_18001FF00
0x18001fe83  lea     rdx, aLoopcount; "LOOPCOUNT"
0x18001fe8a  mov     rcx, rdi; this
0x18001fe8d  call    ?LookupVariableAddress@Equation@@IEAAGPEBG@Z; Equation::LookupVariableAddress(ushort const *)
  ... truncated ...
```
