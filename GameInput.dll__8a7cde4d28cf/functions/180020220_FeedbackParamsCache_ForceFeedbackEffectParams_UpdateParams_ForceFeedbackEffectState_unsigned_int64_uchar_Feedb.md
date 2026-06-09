# FeedbackParamsCache<ForceFeedbackEffectParams>::UpdateParams(ForceFeedbackEffectState *,unsigned __int64,uchar,FeedbackParamsCache<ForceFeedbackEffectParams>::CachedParams &,FeedbackParamsCache<ForceFeedbackEffectParams>::CachedParams &)

- ea: `0x180020220`
- end: `0x18002070f`
- name: `?UpdateParams@?$FeedbackParamsCache@UForceFeedbackEffectParams@@@@CA_KPEAVForceFeedbackEffectState@@_KEAEAUCachedParams@1@2@Z`
- size: `1263`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180019b5c`

## callees

- `0x18000d658`
- `0x180014dcc`
- `0x18001b3b8`
- `0x18001b558`
- `0x18001b790`
- `0x18001bacc`
- `0x18001bd14`
- `0x180020220`
- `0x180023dbc`
- `0x180024908`
- `0x18004c8a5`

## pseudocode

```c
__int64 FeedbackParamsCache<ForceFeedbackEffectParams>::UpdateParams(__int64 a1, __int64 a2, char a3, __int64 a4, ...)
{
  __int64 v4; // rsi
  __int64 v5; // r13
  char v6; // r15
  _QWORD *v8; // r14
  unsigned int *v9; // rdi
  int VersionIfNewer; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  __m128i v15; // xmm0
  unsigned int v16; // eax
  unsigned int v17; // ecx
  float v18; // xmm1_4
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v22; // r8
  unsigned int v23; // eax
  bool v24; // zf
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v32; // rcx
  int v33; // ecx
  unsigned __int64 ForceFeedbackEffectDuration; // rax
  __int64 v35; // r10
  __int64 v36; // r11
  unsigned __int64 v37; // rax
  __int64 v38; // rcx
  unsigned __int64 v39; // rax
  __int64 v40; // r10
  __int64 v41; // r11
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  unsigned __int64 v44; // rax
  __int64 v48; // [rsp+80h] [rbp+28h] BYREF
  va_list va; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v48 = va_arg(va1, _QWORD);
  v4 = v48;
  v5 = a4;
  v6 = a3;
  v8 = (_QWORD *)(v48 + 8);
  v9 = (unsigned int *)(v48 + 16);
  VersionIfNewer = VersionedDataGuard::GetVersionIfNewer(a1 + 8, 136, *(_QWORD *)(a4 + 8), v48 + 8);
  if ( !VersionIfNewer )
  {
    while ( 1 )
    {
      *(_QWORD *)(v4 + 24) = *(_QWORD *)(a1 + 16);
      *v9 = *(_DWORD *)(a1 + 24);
      v9[4] = *(_DWORD *)(a1 + 28);
      ForceFeedbackEffectState::SafeCopyParams(*(unsigned int *)(a1 + 28), a1 + 32, v9 + 6);
      v48 = 0;
      VersionIfNewer = VersionedDataGuard::GetVersionIfNewer(a1 + 8, 136, 0, (__int64 *)va);
      if ( VersionIfNewer )
        break;
      v12 = v48;
      if ( v48 == *v8 )
        break;
      *v8 = v48;
    }
    v6 = a3;
    v5 = a4;
  }
  *(_DWORD *)v4 = VersionIfNewer;
  v13 = GameInputCurrentTime(v12, v11);
  v14 = v13;
  if ( *(_DWORD *)v4 )
  {
    if ( *(_DWORD *)v4 == 3 )
    {
      *(_QWORD *)a1 = 8 * (v13 - a2);
      _mm_mfence();
      *v9 = 0;
      *(_QWORD *)(v4 + 24) = 0;
      *(_QWORD *)(v4 + 144) = -1;
      *(_QWORD *)(v4 + 152) = 0;
      *(_QWORD *)(v4 + 160) = 0;
      *(_QWORD *)(v4 + 168) = 0;
    }
    else if ( !*(_DWORD *)v5 )
    {
      v9 = (unsigned int *)(v5 + 16);
      goto LABEL_48;
    }
    return -1;
  }
  v15 = (__m128i)*v9;
  v16 = _mm_cvtsi128_si32(v15);
  if ( (unsigned __int8)(v16 >> 23) == 0xFF && (v16 & 0x7FFFFF) != 0
    || (v17 = _mm_cvtsi128_si32(v15), !(unsigned __int8)(v17 >> 23)) && (v17 & 0x7FFFFF) != 0 )
  {
    v15.m128i_i32[0] = 0;
LABEL_14:
    v18 = *(float *)v15.m128i_i32;
    goto LABEL_15;
  }
  v18 = 0.0;
  if ( *(float *)v15.m128i_i32 >= 0.0 )
  {
    v18 = FLOAT_1_0;
    if ( *(float *)v15.m128i_i32 <= 1.0 )
      goto LABEL_14;
  }
LABEL_15:
  *(float *)v9 = v18;
  anonymous_namespace_::SanitizeFeedbackEffectState(v14, a2, (unsigned __int64 *)(v4 + 24));
  v19 = *(unsigned int *)(v4 + 32);
  if ( (int)v19 > 5 )
  {
    v19 = (unsigned int)(v19 - 6);
    if ( (_DWORD)v19 )
    {
      v29 = (unsigned int)(v19 - 1);
      if ( (_DWORD)v29 )
      {
        v29 = (unsigned int)(v29 - 1);
        if ( (_DWORD)v29 )
        {
          v29 = (unsigned int)(v29 - 1);
          if ( (_DWORD)v29 )
          {
            if ( (_DWORD)v29 != 1 )
              goto LABEL_35;
            v30 = 10;
          }
          else
          {
            v30 = 9;
          }
        }
        else
        {
          v30 = 8;
        }
      }
      else
      {
        v30 = 7;
      }
      LOBYTE(v29) = v6;
      anonymous_namespace_::SanitizeForceFeedbackConditionParams(v29, v30, v9 + 6);
      goto LABEL_22;
    }
  }
  else if ( (_DWORD)v19 != 5 )
  {
    if ( (_DWORD)v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v19 = (unsigned int)(v20 - 1);
        if ( !(_DWORD)v19 )
          goto LABEL_21;
        v19 = (unsigned int)(v19 - 1);
        if ( (unsigned int)v19 <= 1 )
          goto LABEL_21;
LABEL_35:
        *v9 = 0;
        *(_QWORD *)(v4 + 24) = 0;
        memset_0(v9 + 4, 0, 0x70u);
        goto LABEL_22;
      }
      anonymous_namespace_::SanitizeForceFeedbackEnvelope(v9 + 6);
      LOBYTE(v26) = v6;
      anonymous_namespace_::SanitizeForceFeedbackMagnitude(v26, v9 + 18);
      v28 = v9 + 25;
    }
    else
    {
      anonymous_namespace_::SanitizeForceFeedbackEnvelope(v9 + 6);
      v28 = v9 + 18;
    }
    LOBYTE(v27) = v6;
    anonymous_namespace_::SanitizeForceFeedbackMagnitude(v27, v28);
    goto LABEL_22;
  }
LABEL_21:
  LOBYTE(v19) = v6;
  anonymous_namespace_::SanitizeForceFeedbackPeriodicParams(v19, v9 + 6);
LABEL_22:
  v21 = *(_QWORD *)(v4 + 24) & 7LL;
  v22 = *(_QWORD *)(v4 + 24) >> 3;
  v23 = *(_BYTE *)(v4 + 24) & 7 | 0xFFFFFFF8;
  *(_QWORD *)(v4 + 144) = 0;
  v24 = (*(_BYTE *)(v4 + 24) & 4) == 0;
  *(_QWORD *)(v4 + 152) = v22;
  if ( v24 )
    v23 = v21;
  if ( v23 && v22 == *(_QWORD *)(v5 + 152) )
  {
    *(_QWORD *)(v4 + 160) = *(_QWORD *)(v5 + 160);
    v25 = *(_QWORD *)(v5 + 168);
  }
  else
  {
    *(_QWORD *)(v4 + 160) = 0;
    v25 = 0;
  }
  *(_QWORD *)(v4 + 168) = v25;
LABEL_48:
  if ( !v9 )
    return -1;
  v32 = *((_QWORD *)v9 + 1) & 7LL;
  if ( (v9[2] & 4) != 0 )
    LODWORD(v32) = v32 | 0xFFFFFFF8;
  if ( (_DWORD)v32 )
  {
    v33 = v32 - 1;
    if ( v33 )
    {
      if ( v33 != 1 || *((_QWORD *)v9 + 16) )
        return *((_QWORD *)v9 + 16);
      ForceFeedbackEffectDuration = anonymous_namespace_::GetForceFeedbackEffectDuration(v9 + 4);
      if ( ForceFeedbackEffectDuration < ~v36 )
        v37 = v36 + ForceFeedbackEffectDuration;
      else
        v37 = -1;
      *((_QWORD *)v9 + 16) = v37;
      if ( v37 <= v14 )
      {
        *(_QWORD *)a1 = 8 * (v37 - a2);
        _mm_mfence();
        *((_QWORD *)v9 + 1) = 8LL * *((_QWORD *)v9 + 16);
        *((_QWORD *)v9 + 18) = 0;
        *((_QWORD *)v9 + 19) = 0;
      }
      else
      {
        *(_QWORD *)a1 = (8 * (v35 - a2)) | 2;
        _mm_mfence();
        v24 = *((_QWORD *)v9 + 18) == 0;
        *((_QWORD *)v9 + 1) = 8 * v35;
        if ( v24 )
          *((_QWORD *)v9 + 18) = v14;
      }
    }
    else
    {
      if ( *((_QWORD *)v9 + 16) )
      {
        v43 = a2;
      }
      else
      {
        v38 = *((_QWORD *)v9 + 18);
        if ( v38 )
        {
          *((_QWORD *)v9 + 18) = 0;
          *((_QWORD *)v9 + 19) += v14 - v38;
        }
        v39 = anonymous_namespace_::GetForceFeedbackEffectDuration(v9 + 4);
        if ( v39 < ~v41 )
          v42 = v41 + v39;
        else
          v42 = -1;
        v43 = a2;
        *((_QWORD *)v9 + 16) = v42;
        if ( v42 > v14 )
        {
          *(_QWORD *)a1 = (8 * (v40 - a2)) | 1;
          _mm_mfence();
          *((_QWORD *)v9 + 1) = (8 * v41) | 1;
        }
      }
      v44 = *((_QWORD *)v9 + 16);
      if ( v44 > v14 )
        return *((_QWORD *)v9 + 16);
      *(_QWORD *)a1 = 8 * (v44 - v43);
      _mm_mfence();
      *((_QWORD *)v9 + 1) = 8LL * *((_QWORD *)v9 + 16);
      *((_QWORD *)v9 + 18) = 0;
      *((_QWORD *)v9 + 19) = 0;
    }
    goto LABEL_75;
  }
  if ( !*((_QWORD *)v9 + 16) )
  {
    *(_QWORD *)a1 = 8 * ((*((_QWORD *)v9 + 1) >> 3) - a2);
    _mm_mfence();
LABEL_75:
    *((_QWORD *)v9 + 16) = -1;
  }
  return *((_QWORD *)v9 + 16);
}

```

## disassembly

```asm
0x180020220  mov     rax, rsp
0x180020223  mov     [rax+8], rbx
0x180020227  mov     [rax+20h], r9
0x18002022b  mov     [rax+18h], r8b
0x18002022f  mov     [rax+10h], rdx
0x180020233  push    rbp
0x180020234  push    rsi
0x180020235  push    rdi
0x180020236  push    r12
0x180020238  push    r13
0x18002023a  push    r14
0x18002023c  push    r15
0x18002023e  sub     rsp, 20h
0x180020242  mov     rsi, [rsp+58h+arg_20]
0x18002024a  mov     r13, r9
0x18002024d  mov     r15b, r8b
0x180020250  mov     r12, rcx
0x180020253  mov     edx, 88h
0x180020258  add     rcx, 8
0x18002025c  mov     r8, [r13+8]
0x180020260  lea     r14, [rsi+8]
0x180020264  mov     r9, r14
0x180020267  lea     rdi, [rsi+10h]
0x18002026b  call    ?GetVersionIfNewer@VersionedDataGuard@@QEBA?AW4VersionedDataStatus@@I_KAEA_K@Z; VersionedDataGuard::GetVersionIfNewer(uint,unsigned __int64,unsigned __int64 &)
0x180020270  test    eax, eax
0x180020272  jnz     short loc_1800202E5
0x180020274  mov     rax, [r12+10h]
0x180020279  lea     r8, [rdi+18h]
0x18002027d  mov     [rsi+18h], rax
0x180020281  lea     rdx, [r12+20h]
0x180020286  mov     eax, [r12+18h]
0x18002028b  mov     [rdi], eax
0x18002028d  mov     eax, [r12+1Ch]
0x180020292  mov     [rdi+10h], eax
0x180020295  mov     ecx, [r12+1Ch]
0x18002029a  call    ?SafeCopyParams@ForceFeedbackEffectState@@CAXW4GameInputForceFeedbackEffectKind@@AEBT_unnamed_type_data_@GameInputForceFeedbackParams@@AEAT34@@Z; ForceFeedbackEffectState::SafeCopyParams(GameInputForceFeedbackEffectKind,GameInputForceFeedbackParams::_unnamed_type_data_ const &,GameInputForceFeedbackParams::_unnamed_type_data_ &)
0x18002029f  lea     r9, [rsp+58h+arg_20]
0x1800202a7  mov     [rsp+58h+arg_20], 0
0x1800202b3  xor     r8d, r8d
0x1800202b6  lea     rcx, [r12+8]
0x1800202bb  mov     edx, 88h
0x1800202c0  call    ?GetVersionIfNewer@VersionedDataGuard@@QEBA?AW4VersionedDataStatus@@I_KAEA_K@Z; VersionedDataGuard::GetVersionIfNewer(uint,unsigned __int64,unsigned __int64 &)
0x1800202c5  test    eax, eax
0x1800202c7  jnz     short loc_1800202DB
0x1800202c9  mov     rcx, [rsp+58h+arg_20]
0x1800202d1  cmp     rcx, [r14]
0x1800202d4  jz      short loc_1800202DB
0x1800202d6  mov     [r14], rcx
0x1800202d9  jmp     short loc_180020274
0x1800202db  mov     r15b, [rsp+58h+arg_10]
0x1800202e0  mov     r13, [rsp+58h+arg_18]
0x1800202e5  mov     [rsi], eax
0x1800202e7  call    GameInputCurrentTime
0x1800202ec  xor     r9d, r9d
0x1800202ef  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800202f3  mov     r14, rax
0x1800202f6  cmp     [rsi], r9d
0x1800202f9  jnz     loc_1800204A4
0x1800202ff  movss   xmm0, dword ptr [rdi]
0x180020303  mov     edx, 7FFFFFh
0x180020308  movd    eax, xmm0
0x18002030c  mov     ecx, eax
0x18002030e  shr     ecx, 17h
0x180020311  cmp     cl, 0FFh
0x180020314  jnz     short loc_18002031A
0x180020316  test    edx, eax
0x180020318  jnz     short loc_18002032B
0x18002031a  movd    ecx, xmm0
0x18002031e  mov     eax, ecx
0x180020320  shr     eax, 17h
0x180020323  test    al, al
0x180020325  jnz     short loc_180020330
0x180020327  test    edx, ecx
0x180020329  jz      short loc_180020330
0x18002032b  xorps   xmm0, xmm0
0x18002032e  jmp     short loc_180020345
0x180020330  xorps   xmm1, xmm1
0x180020333  comiss  xmm1, xmm0
0x180020336  ja      short loc_180020348
0x180020338  movss   xmm1, cs:__real@3f800000
0x180020340  comiss  xmm0, xmm1
0x180020343  ja      short loc_180020348
0x180020345  movaps  xmm1, xmm0
0x180020348  mov     rdx, [rsp+58h+arg_8]
0x18002034d  lea     r8, [rsi+18h]
0x180020351  mov     rcx, r14
0x180020354  movss   dword ptr [rdi], xmm1
0x180020358  call    _anonymous_namespace___SanitizeFeedbackEffectState
0x18002035d  mov     ecx, [rsi+20h]
0x180020360  cmp     ecx, 5
0x180020363  jg      loc_180020427
0x180020369  jz      short loc_18002038B
0x18002036b  test    ecx, ecx
0x18002036d  jz      loc_18002040D
0x180020373  sub     ecx, 1
0x180020376  jz      short loc_1800203F2
0x180020378  sub     ecx, 1
0x18002037b  jz      short loc_18002038B
0x18002037d  sub     ecx, 1
0x180020380  jz      short loc_18002038B
0x180020382  cmp     ecx, 1
0x180020385  jnz     loc_180020444
0x18002038b  lea     rdx, [rdi+18h]
0x18002038f  mov     cl, r15b
0x180020392  call    _anonymous_namespace___SanitizeForceFeedbackPeriodicParams
0x180020397  mov     rcx, [rsi+18h]
0x18002039b  xor     r9d, r9d
0x18002039e  mov     r8, [rsi+18h]
0x1800203a2  and     ecx, 7
0x1800203a5  shr     r8, 3
0x1800203a9  mov     eax, ecx
0x1800203ab  or      eax, 0FFFFFFF8h
0x1800203ae  mov     [rsi+90h], r9
0x1800203b5  test    byte ptr [rsi+18h], 4
0x1800203b9  mov     [rsi+98h], r8
0x1800203c0  cmovz   eax, ecx
0x1800203c3  test    eax, eax
0x1800203c5  jz      loc_180020491
0x1800203cb  cmp     r8, [r13+98h]
0x1800203d2  jnz     loc_180020491
0x1800203d8  mov     rax, [r13+0A0h]
0x1800203df  mov     [rsi+0A0h], rax
0x1800203e6  mov     rax, [r13+0A8h]
0x1800203ed  jmp     loc_18002049B
0x1800203f2  lea     rcx, [rdi+18h]
0x1800203f6  call    _anonymous_namespace___SanitizeForceFeedbackEnvelope
0x1800203fb  lea     rdx, [rdi+48h]
0x1800203ff  mov     cl, r15b
0x180020402  call    _anonymous_namespace___SanitizeForceFeedbackMagnitude
0x180020407  lea     rdx, [rdi+64h]
0x18002040b  jmp     short loc_18002041A
0x18002040d  lea     rcx, [rdi+18h]
0x180020411  call    _anonymous_namespace___SanitizeForceFeedbackEnvelope
0x180020416  lea     rdx, [rdi+48h]
0x18002041a  mov     cl, r15b
0x18002041d  call    _anonymous_namespace___SanitizeForceFeedbackMagnitude
0x180020422  jmp     loc_180020397
0x180020427  sub     ecx, 6
0x18002042a  jz      loc_18002038B
0x180020430  sub     ecx, 1
0x180020433  jz      short loc_18002047B
0x180020435  sub     ecx, 1
0x180020438  jz      short loc_180020474
0x18002043a  sub     ecx, 1
0x18002043d  jz      short loc_18002046D
0x18002043f  cmp     ecx, 1
0x180020442  jz      short loc_180020466
0x180020444  xor     edx, edx; Val
0x180020446  mov     dword ptr [rdi], 0
0x18002044c  lea     rcx, [rdi+10h]; void *
0x180020450  mov     qword ptr [rsi+18h], 0
0x180020458  lea     r8d, [rdx+70h]; Size
0x18002045c  call    memset_0
0x180020461  jmp     loc_180020397
0x180020466  mov     edx, 0Ah
0x18002046b  jmp     short loc_180020480
0x18002046d  mov     edx, 9
0x180020472  jmp     short loc_180020480
0x180020474  mov     edx, 8
0x180020479  jmp     short loc_180020480
0x18002047b  mov     edx, 7
0x180020480  lea     r8, [rdi+18h]
0x180020484  mov     cl, r15b
0x180020487  call    _anonymous_namespace___SanitizeForceFeedbackConditionParams
0x18002048c  jmp     loc_180020397
0x180020491  mov     [rsi+0A0h], r9
0x180020498  mov     rax, r9
0x18002049b  mov     [rsi+0A8h], rax
0x1800204a2  jmp     short loc_180020500
0x1800204a4  cmp     dword ptr [rsi], 3
0x1800204a7  jnz     short loc_1800204F6
0x1800204a9  sub     r14, [rsp+58h+arg_8]
0x1800204ae  nop
0x1800204af  shl     r14, 3
0x1800204b3  mov     [r12], r14
0x1800204b7  mfence
0x1800204ba  mov     [rdi], r9d
0x1800204bd  mov     [rsi+18h], r9
0x1800204c1  mov     [rsi+90h], rbp
0x1800204c8  mov     [rsi+98h], r9
0x1800204cf  mov     [rsi+0A0h], r9
0x1800204d6  mov     [rsi+0A8h], r9
0x1800204dd  mov     rax, rbp
0x1800204e0  mov     rbx, [rsp+58h+arg_0]
0x1800204e5  add     rsp, 20h
0x1800204e9  pop     r15
0x1800204eb  pop     r14
0x1800204ed  pop     r13
0x1800204ef  pop     r12
0x1800204f1  pop     rdi
0x1800204f2  pop     rsi
0x1800204f3  pop     rbp
0x1800204f4  retn
0x1800204f6  cmp     [r13+0], r9d
0x1800204fa  jnz     short loc_1800204DD
0x1800204fc  lea     rdi, [r13+10h]
0x180020500  test    rdi, rdi
0x180020503  jz      short loc_1800204DD
0x180020505  mov     rcx, [rdi+8]
0x180020509  mov     r10, rcx
0x18002050c  and     ecx, 7
0x18002050f  shr     r10, 3
0x180020513  test    cl, 4
0x180020516  jz      short loc_180020520
0x180020518  mov     eax, 0FFFFFFF8h
0x18002051d  or      rcx, rax
0x180020520  test    ecx, ecx
0x180020522  jz      loc_1800206E2
0x180020528  sub     ecx, 1
0x18002052b  jz      loc_180020604
0x180020531  cmp     ecx, 1
0x180020534  jnz     loc_180020703
0x18002053a  cmp     [rdi+80h], r9
0x180020541  jnz     loc_180020703
0x180020547  mov     rcx, [rdi+98h]
0x18002054e  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180020552  mov     rax, r10
0x180020555  mov     r11, rbp
0x180020558  not     rax
0x18002055b  cmp     rcx, rax
0x18002055e  jnb     short loc_180020564
0x180020560  lea     r11, [rcx+r10]
0x180020564  lea     rcx, [rdi+10h]
0x180020568  call    _anonymous_namespace___GetForceFeedbackEffectDuration
0x18002056d  mov     rcx, r11
0x180020570  not     rcx
0x180020573  cmp     rax, rcx
0x180020576  jb      short loc_18002057D
0x180020578  mov     rax, rbp
0x18002057b  jmp     short loc_180020580
0x18002057d  add     rax, r11
0x180020580  mov     [rdi+80h], rax
0x180020587  nop
0x180020588  cmp     rax, r14
0x18002058b  jbe     short loc_1800205CA
0x18002058d  mov     rax, r10
0x180020590  sub     rax, [rsp+58h+arg_8]
0x180020595  shl     rax, 3
0x180020599  or      rax, 2
0x18002059d  mov     [r12], rax
0x1800205a1  mfence
0x1800205a4  cmp     qword ptr [rdi+90h], 0
0x1800205ac  lea     rax, ds:0[r10*8]
0x1800205b4  mov     [rdi+8], rax
0x1800205b8  jnz     loc_1800206FC
0x1800205be  mov     [rdi+90h], r14
0x1800205c5  jmp     loc_1800206FC
0x1800205ca  sub     rax, [rsp+58h+arg_8]
0x1800205cf  shl     rax, 3
0x1800205d3  mov     [r12], rax
0x1800205d7  mfence
0x1800205da  mov     rax, [rdi+80h]
0x1800205e1  shl     rax, 3
0x1800205e5  mov     [rdi+8], rax
0x1800205e9  mov     qword ptr [rdi+90h], 0
0x1800205f4  mov     qword ptr [rdi+98h], 0
0x1800205ff  jmp     loc_1800206FC
0x180020604  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180020608  cmp     [rdi+80h], r9
0x18002060f  jnz     loc_1800206DB
0x180020615  mov     rcx, [rdi+90h]
0x18002061c  test    rcx, rcx
0x18002061f  jz      short loc_180020635
0x180020621  mov     rax, r14
0x180020624  mov     [rdi+90h], r9
0x18002062b  sub     rax, rcx
0x18002062e  add     [rdi+98h], rax
0x180020635  mov     rcx, [rdi+98h]
0x18002063c  mov     rax, r10
0x18002063f  not     rax
0x180020642  mov     r11, rbp
0x180020645  cmp     rcx, rax
0x180020648  jnb     short loc_18002064E
0x18002064a  lea     r11, [rcx+r10]
0x18002064e  lea     rcx, [rdi+10h]
0x180020652  call    _anonymous_namespace___GetForceFeedbackEffectDuration
0x180020657  mov     rcx, r11
0x18002065a  not     rcx
0x18002065d  cmp     rax, rcx
0x180020660  jb      short loc_180020667
0x180020662  mov     rax, rbp
0x180020665  jmp     short loc_18002066A
0x180020667  add     rax, r11
0x18002066a  mov     rcx, [rsp+58h+arg_8]
0x18002066f  mov     [rdi+80h], rax
0x180020676  cmp     rax, r14
0x180020679  jbe     short loc_18002069E
0x18002067b  sub     r10, rcx
0x18002067e  nop
0x18002067f  shl     r10, 3
0x180020683  or      r10, 1
0x180020687  mov     [r12], r10
0x18002068b  mfence
0x18002068e  lea     rax, ds:0[r11*8]
0x180020696  or      rax, 1
0x18002069a  mov     [rdi+8], rax
0x18002069e  xor     r9d, r9d
0x1800206a1  mov     rax, [rdi+80h]
0x1800206a8  cmp     rax, r14
0x1800206ab  ja      short loc_180020703
  ... truncated ...
```
