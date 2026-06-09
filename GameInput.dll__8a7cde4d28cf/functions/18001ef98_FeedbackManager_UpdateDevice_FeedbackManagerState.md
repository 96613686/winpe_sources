# FeedbackManager::UpdateDevice(FeedbackManagerState *)

- ea: `0x18001ef98`
- end: `0x18001f398`
- name: `?UpdateDevice@FeedbackManager@@CA_KPEAUFeedbackManagerState@@@Z`
- size: `1024`
- prototype: `unsigned __int64 __fastcall(struct FeedbackManagerState *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022390`

## callees

- `0x18000d658`
- `0x1800123f0`
- `0x180019b5c`
- `0x18001a274`
- `0x18001ef98`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001efb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001efb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f009`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f009`

## pseudocode

```c
unsigned __int64 __fastcall FeedbackManager::UpdateDevice(RTL_SRWLOCK *this, __int64 a2)
{
  unsigned __int64 v3; // rbx
  __int64 *v4; // rsi
  char v5; // bp
  volatile signed __int8 *Ptr; // rax
  unsigned __int64 refreshed; // r15
  char v8; // bl
  _DWORD *v9; // r14
  unsigned __int64 v10; // r13
  unsigned __int64 v11; // r12
  __int64 *v12; // r12
  unsigned int v13; // r13d
  unsigned int v14; // ebx
  unsigned int v15; // edx
  int v16; // ecx
  _DWORD *v17; // r11
  char *v18; // r10
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  _DWORD *v22; // rax
  int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // r9d
  char v27; // al
  _DWORD *v28; // rcx
  __int64 v29; // rax
  int v30; // edx
  __m64 *v31; // rbx
  PVOID v32; // rcx
  void (__fastcall *v33)(PVOID, __m128d *); // rax
  __m128d v35; // [rsp+30h] [rbp-68h] BYREF
  __m128d v36; // [rsp+40h] [rbp-58h]
  unsigned int v37; // [rsp+A0h] [rbp+8h]
  unsigned int v38; // [rsp+A8h] [rbp+10h]
  unsigned __int64 v39; // [rsp+B0h] [rbp+18h]

  v3 = GameInputCurrentTime(this, a2);
  v4 = 0;
  AcquireSRWLockExclusive(this);
  v5 = 1;
  if ( this[2].Ptr )
  {
    if ( BYTE3(this[21].Ptr) )
    {
      Ptr = (volatile signed __int8 *)this[1].Ptr;
      if ( Ptr )
      {
        _InterlockedIncrement8(Ptr + 4504);
        v4 = (__int64 *)this[1].Ptr;
      }
    }
    refreshed = FeedbackManagerState::RefreshCache((FeedbackManagerState *)this, v3);
    v8 = 1;
  }
  else
  {
    refreshed = -1;
    v8 = 0;
  }
  ReleaseSRWLockExclusive(this);
  if ( v8 && !BYTE1(this[21].Ptr) )
  {
    v9 = this[11].Ptr;
    v39 = -1;
    v10 = -1;
    v11 = -1;
    if ( v9 )
    {
      v12 = v4;
      if ( !v4 )
        v12 = (__int64 *)this[14].Ptr;
      v13 = 0;
      v38 = *((_DWORD *)this[7].Ptr + 1);
      if ( v38 )
      {
        while ( 1 )
        {
          (*(void (__fastcall **)(__int64 *, _QWORD))(*v12 + 48))(v12, v13);
          v14 = 0;
          v15 = *((unsigned __int16 *)this[7].Ptr + 14 * v13 + 6);
          v37 = v15;
          if ( *((_WORD *)this[7].Ptr + 14 * v13 + 6) )
            break;
LABEL_34:
          if ( ++v13 >= v38 )
            goto LABEL_35;
        }
        while ( 1 )
        {
          v16 = v9[4];
          if ( v9[5] == v16 )
            goto LABEL_30;
          v17 = &v9[44 * (v16 & 1) + 6];
          v18 = (char *)&v9[44 * ((v16 - 1) & 1LL)];
          if ( !*v17 )
            break;
          if ( *v17 == 3 )
          {
            v9[5] = v16;
            if ( !*((_DWORD *)v18 + 6) )
              goto LABEL_21;
          }
LABEL_30:
          v20 = v39;
          if ( v39 > *(_QWORD *)v9 )
            v20 = *(_QWORD *)v9;
          v39 = v20;
          if ( BYTE1(this[21].Ptr) )
            goto LABEL_72;
          v9 += 94;
          if ( ++v14 >= v15 )
            goto LABEL_34;
        }
        v9[5] = v16;
        if ( !*((_DWORD *)v18 + 6)
          && !(unsigned __int8)FeedbackParamsCache<ForceFeedbackEffectParams>::CompareParams(v17 + 4, v18 + 40) )
        {
LABEL_29:
          v15 = v37;
          goto LABEL_30;
        }
LABEL_21:
        if ( *v17 )
        {
          if ( *v17 == 3 || *((_DWORD *)v18 + 6) )
          {
            v19 = *v12;
            goto LABEL_28;
          }
          v17 = v18 + 24;
        }
        v19 = *v12;
        if ( v17 != (_DWORD *)-16LL )
        {
          (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v19 + 40))(v12, v13, v14);
          goto LABEL_29;
        }
LABEL_28:
        (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v19 + 32))(v12, v13, v14);
        goto LABEL_29;
      }
LABEL_35:
      while ( 1 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64 *))(*v12 + 56))(v12);
        v10 = v21;
        if ( BYTE1(this[21].Ptr) )
          goto LABEL_72;
        if ( v21 )
        {
          v11 = v39;
          break;
        }
      }
    }
    v22 = this[13].Ptr;
    if ( v22 )
    {
      v23 = v22[4];
      if ( v22[5] != v23 )
      {
        v24 = 8LL * (v23 & 1);
        v25 = 8 * ((v23 - 1) & 1LL);
        v26 = v22[v24 + 6];
        if ( v26 )
        {
          if ( v26 == 3 )
          {
            v22[5] = v23;
            if ( !v22[v25 + 6] )
              goto LABEL_52;
          }
        }
        else
        {
          v22[5] = v23;
          if ( v22[v25 + 6]
            || (*(float *)&v22[v24 + 10] != *(float *)&v22[v25 + 10]
             || *(float *)&v22[v24 + 11] != *(float *)&v22[v25 + 11]
             || *(float *)&v22[v24 + 12] != *(float *)&v22[v25 + 12]
             || *(float *)&v22[v24 + 13] != *(float *)&v22[v25 + 13]
              ? (v27 = 1)
              : (v27 = 0),
                v27) )
          {
LABEL_52:
            v28 = this[13].Ptr;
            v29 = 8 * (v28[4] & 1LL);
            v30 = v28[v29 + 6];
            if ( v30 && (v30 == 3 || (v29 = 8 * ((v28[4] - 1) & 1LL), v28[v29 + 6])) )
              v31 = 0;
            else
              v31 = (__m64 *)&v28[v29 + 10];
            v32 = this[17].Ptr;
            v33 = *(void (__fastcall **)(PVOID, __m128d *))(*(_QWORD *)v32 + 168LL);
            if ( v31 )
            {
              v35 = _mm_cvtps_pd((__m64)v31->m64_u64);
              v36 = _mm_cvtps_pd(v31[1]);
              v33(v32, &v35);
              if ( v31->m64_f32[0] == 0.0
                && v31->m64_f32[1] == 0.0
                && *(float *)&v31[1].m64_u64 == 0.0
                && *((float *)&v31[1] + 1) == 0.0 )
              {
                v5 = 0;
              }
              BYTE2(this[21].Ptr) = v5;
            }
            else
            {
              v35 = 0;
              v36 = 0;
              v33(v32, &v35);
              BYTE2(this[21].Ptr) = 0;
            }
          }
        }
      }
    }
    if ( v10 < refreshed )
      refreshed = v10;
    if ( v11 < refreshed )
      refreshed = v11;
    if ( v4 )
      GipEquationManager::ReleaseReference(v4);
    return refreshed;
  }
LABEL_72:
  if ( v4 )
    GipEquationManager::ReleaseReference(v4);
  return -1;
}

```

## disassembly

```asm
0x18001ef98  push    rbx
0x18001ef9a  push    rbp
0x18001ef9b  push    rsi
0x18001ef9c  push    rdi
0x18001ef9d  push    r12
0x18001ef9f  push    r13
0x18001efa1  push    r14
0x18001efa3  push    r15
0x18001efa5  sub     rsp, 58h
0x18001efa9  mov     rdi, rcx
0x18001efac  call    GameInputCurrentTime
0x18001efb1  mov     rcx, rdi; SRWLock
0x18001efb4  mov     rbx, rax
0x18001efb7  xor     esi, esi
0x18001efb9  call    cs:__imp_AcquireSRWLockExclusive
0x18001efc0  nop     dword ptr [rax+rax+00h]
0x18001efc5  lea     ebp, [rsi+1]
0x18001efc8  cmp     [rdi+10h], rsi
0x18001efcc  jz      short loc_18001F000
0x18001efce  cmp     [rdi+0ABh], sil
0x18001efd5  jz      short loc_18001EFED
0x18001efd7  mov     rax, [rdi+8]
0x18001efdb  test    rax, rax
0x18001efde  jz      short loc_18001EFED
0x18001efe0  nop
0x18001efe1  lock inc byte ptr [rax+1198h]
0x18001efe8  nop
0x18001efe9  mov     rsi, [rdi+8]
0x18001efed  mov     rdx, rbx; unsigned __int64
0x18001eff0  mov     rcx, rdi; this
0x18001eff3  call    ?RefreshCache@FeedbackManagerState@@QEAA_K_K@Z; FeedbackManagerState::RefreshCache(unsigned __int64)
0x18001eff8  mov     r15, rax
0x18001effb  mov     bl, bpl
0x18001effe  jmp     short loc_18001F006
0x18001f000  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001f004  xor     bl, bl
0x18001f006  mov     rcx, rdi; SRWLock
0x18001f009  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f010  nop     dword ptr [rax+rax+00h]
0x18001f015  test    bl, bl
0x18001f017  jz      loc_18001F375
0x18001f01d  mov     al, [rdi+0A9h]
0x18001f023  nop
0x18001f024  test    al, al
0x18001f026  jnz     loc_18001F375
0x18001f02c  mov     r14, [rdi+58h]
0x18001f030  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f034  mov     [rsp+98h+arg_10], rax
0x18001f03c  mov     r13, rax
0x18001f03f  mov     r12, rax
0x18001f042  test    r14, r14
0x18001f045  jz      loc_18001F1E3
0x18001f04b  mov     r12, rsi
0x18001f04e  test    rsi, rsi
0x18001f051  jnz     short loc_18001F057
0x18001f053  mov     r12, [rdi+70h]
0x18001f057  mov     rax, [rdi+38h]
0x18001f05b  xor     r13d, r13d
0x18001f05e  mov     eax, [rax+4]
0x18001f061  mov     [rsp+98h+arg_8], eax
0x18001f068  test    eax, eax
0x18001f06a  jz      loc_18001F1B4
0x18001f070  mov     rcx, [rdi+98h]
0x18001f077  mov     edx, r13d
0x18001f07a  mov     rax, [r12]
0x18001f07e  mov     ebx, r13d
0x18001f081  movss   xmm2, dword ptr [rcx+r13*4]
0x18001f087  mov     rcx, r12
0x18001f08a  mov     rax, [rax+30h]
0x18001f08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f093  mov     rax, [rdi+38h]
0x18001f097  imul    rcx, rbx, 1Ch
0x18001f09b  xor     ebx, ebx
0x18001f09d  movzx   edx, word ptr [rcx+rax+0Ch]
0x18001f0a2  mov     [rsp+98h+arg_0], edx
0x18001f0a9  test    edx, edx
0x18001f0ab  jz      loc_18001F1A3
0x18001f0b1  mov     ecx, [r14+10h]
0x18001f0b5  cmp     [r14+14h], ecx
0x18001f0b9  jz      loc_18001F16C
0x18001f0bf  mov     eax, ecx
0x18001f0c1  and     rax, rbp
0x18001f0c4  imul    r11, rax, 0B0h
0x18001f0cb  lea     eax, [rcx-1]
0x18001f0ce  and     rax, rbp
0x18001f0d1  add     r11, 18h
0x18001f0d5  imul    r10, rax, 0B0h
0x18001f0dc  add     r11, r14
0x18001f0df  add     r10, r14
0x18001f0e2  cmp     dword ptr [r11], 0
0x18001f0e6  jnz     short loc_18001F106
0x18001f0e8  mov     [r14+14h], ecx
0x18001f0ec  cmp     dword ptr [r10+18h], 0
0x18001f0f1  jnz     short loc_18001F117
0x18001f0f3  lea     rdx, [r10+28h]
0x18001f0f7  lea     rcx, [r11+10h]
0x18001f0fb  call    ?CompareParams@?$FeedbackParamsCache@UForceFeedbackEffectParams@@@@CA_NAEBUForceFeedbackEffectParams@@0@Z; FeedbackParamsCache<ForceFeedbackEffectParams>::CompareParams(ForceFeedbackEffectParams const &,ForceFeedbackEffectParams const &)
0x18001f100  test    al, al
0x18001f102  jz      short loc_18001F165
0x18001f104  jmp     short loc_18001F117
0x18001f106  cmp     dword ptr [r11], 3
0x18001f10a  jnz     short loc_18001F16C
0x18001f10c  mov     [r14+14h], ecx
0x18001f110  cmp     dword ptr [r10+18h], 0
0x18001f115  jnz     short loc_18001F16C
0x18001f117  mov     eax, [r11]
0x18001f11a  test    eax, eax
0x18001f11c  jz      short loc_18001F12E
0x18001f11e  cmp     eax, 3
0x18001f121  jz      short loc_18001F14F
0x18001f123  cmp     dword ptr [r10+18h], 0
0x18001f128  jnz     short loc_18001F14F
0x18001f12a  lea     r11, [r10+18h]
0x18001f12e  mov     rax, [r12]
0x18001f132  lea     r9, [r11+10h]
0x18001f136  test    r9, r9
0x18001f139  jz      short loc_18001F153
0x18001f13b  mov     rax, [rax+28h]
0x18001f13f  mov     r8d, ebx
0x18001f142  mov     edx, r13d
0x18001f145  mov     rcx, r12
0x18001f148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f14d  jmp     short loc_18001F165
0x18001f14f  mov     rax, [r12]
0x18001f153  mov     rax, [rax+20h]
0x18001f157  mov     r8d, ebx
0x18001f15a  mov     edx, r13d
0x18001f15d  mov     rcx, r12
0x18001f160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f165  mov     edx, [rsp+98h+arg_0]
0x18001f16c  mov     rcx, [rsp+98h+arg_10]
0x18001f174  cmp     rcx, [r14]
0x18001f177  mov     al, [rdi+0A9h]
0x18001f17d  cmova   rcx, [r14]
0x18001f181  nop
0x18001f182  mov     [rsp+98h+arg_10], rcx
0x18001f18a  test    al, al
0x18001f18c  jnz     loc_18001F375
0x18001f192  add     r14, 178h
0x18001f199  add     ebx, ebp
0x18001f19b  cmp     ebx, edx
0x18001f19d  jb      loc_18001F0B1
0x18001f1a3  add     r13d, ebp
0x18001f1a6  cmp     r13d, [rsp+98h+arg_8]
0x18001f1ae  jb      loc_18001F070
0x18001f1b4  mov     rax, [r12]
0x18001f1b8  mov     rcx, r12
0x18001f1bb  mov     rax, [rax+38h]
0x18001f1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c4  mov     cl, [rdi+0A9h]
0x18001f1ca  mov     r13, rax
0x18001f1cd  nop
0x18001f1ce  test    cl, cl
0x18001f1d0  jnz     loc_18001F375
0x18001f1d6  test    rax, rax
0x18001f1d9  jz      short loc_18001F1B4
0x18001f1db  mov     r12, [rsp+98h+arg_10]
0x18001f1e3  mov     rax, [rdi+68h]
0x18001f1e7  test    rax, rax
0x18001f1ea  jz      loc_18001F355
0x18001f1f0  mov     r8d, [rax+10h]
0x18001f1f4  cmp     [rax+14h], r8d
0x18001f1f8  jz      loc_18001F355
0x18001f1fe  mov     edx, r8d
0x18001f201  lea     ecx, [r8-1]
0x18001f205  and     rdx, rbp
0x18001f208  and     rcx, rbp
0x18001f20b  shl     rdx, 5
0x18001f20f  shl     rcx, 5
0x18001f213  mov     r9d, [rdx+rax+18h]
0x18001f218  test    r9d, r9d
0x18001f21b  jnz     short loc_18001F275
0x18001f21d  mov     [rax+14h], r8d
0x18001f221  cmp     [rcx+rax+18h], r9d
0x18001f226  jnz     short loc_18001F28E
0x18001f228  movss   xmm0, dword ptr [rdx+rax+28h]
0x18001f22e  ucomiss xmm0, dword ptr [rcx+rax+28h]
0x18001f233  jp      short loc_18001F268
0x18001f235  jnz     short loc_18001F268
0x18001f237  movss   xmm0, dword ptr [rdx+rax+2Ch]
0x18001f23d  ucomiss xmm0, dword ptr [rcx+rax+2Ch]
0x18001f242  jp      short loc_18001F268
0x18001f244  jnz     short loc_18001F268
0x18001f246  movss   xmm0, dword ptr [rdx+rax+30h]
0x18001f24c  ucomiss xmm0, dword ptr [rcx+rax+30h]
0x18001f251  jp      short loc_18001F268
0x18001f253  jnz     short loc_18001F268
0x18001f255  movss   xmm0, dword ptr [rdx+rax+34h]
0x18001f25b  ucomiss xmm0, dword ptr [rcx+rax+34h]
0x18001f260  jp      short loc_18001F268
0x18001f262  jnz     short loc_18001F268
0x18001f264  xor     al, al
0x18001f266  jmp     short loc_18001F26B
0x18001f268  mov     al, bpl
0x18001f26b  test    al, al
0x18001f26d  jz      loc_18001F355
0x18001f273  jmp     short loc_18001F28E
0x18001f275  cmp     r9d, 3
0x18001f279  jnz     loc_18001F355
0x18001f27f  mov     [rax+14h], r8d
0x18001f283  cmp     dword ptr [rcx+rax+18h], 0
0x18001f288  jnz     loc_18001F355
0x18001f28e  mov     rcx, [rdi+68h]
0x18001f292  mov     r8d, [rcx+10h]
0x18001f296  mov     eax, r8d
0x18001f299  and     rax, rbp
0x18001f29c  shl     rax, 5
0x18001f2a0  mov     edx, [rax+rcx+18h]
0x18001f2a4  test    edx, edx
0x18001f2a6  jnz     short loc_18001F2B1
0x18001f2a8  lea     rbx, [rcx+28h]
0x18001f2ac  add     rbx, rax
0x18001f2af  jmp     short loc_18001F2CA
0x18001f2b1  cmp     edx, 3
0x18001f2b4  jz      short loc_18001F2C8
0x18001f2b6  lea     eax, [r8-1]
0x18001f2ba  and     rax, rbp
0x18001f2bd  shl     rax, 5
0x18001f2c1  cmp     dword ptr [rax+rcx+18h], 0
0x18001f2c6  jz      short loc_18001F2A8
0x18001f2c8  xor     ebx, ebx
0x18001f2ca  mov     rcx, [rdi+88h]
0x18001f2d1  lea     rdx, [rsp+98h+var_68]
0x18001f2d6  mov     rax, [rcx]
0x18001f2d9  mov     rax, [rax+0A8h]
0x18001f2e0  test    rbx, rbx
0x18001f2e3  jz      short loc_18001F339
0x18001f2e5  cvtps2pd xmm0, qword ptr [rbx]
0x18001f2e8  movaps  [rsp+98h+var_68], xmm0
0x18001f2ed  cvtps2pd xmm0, qword ptr [rbx+8]
0x18001f2f1  movaps  [rsp+98h+var_58], xmm0
0x18001f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fb  movss   xmm0, dword ptr [rbx]
0x18001f2ff  xorps   xmm1, xmm1
0x18001f302  ucomiss xmm0, xmm1
0x18001f305  jp      short loc_18001F330
0x18001f307  jnz     short loc_18001F330
0x18001f309  movss   xmm0, dword ptr [rbx+4]
0x18001f30e  ucomiss xmm0, xmm1
0x18001f311  jp      short loc_18001F330
0x18001f313  jnz     short loc_18001F330
0x18001f315  movss   xmm0, dword ptr [rbx+8]
0x18001f31a  ucomiss xmm0, xmm1
0x18001f31d  jp      short loc_18001F330
0x18001f31f  jnz     short loc_18001F330
0x18001f321  movss   xmm0, dword ptr [rbx+0Ch]
0x18001f326  ucomiss xmm0, xmm1
0x18001f329  jp      short loc_18001F330
0x18001f32b  jnz     short loc_18001F330
0x18001f32d  xor     bpl, bpl
0x18001f330  mov     [rdi+0AAh], bpl
0x18001f337  jmp     short loc_18001F355
0x18001f339  xorps   xmm0, xmm0
0x18001f33c  xorps   xmm1, xmm1
0x18001f33f  movaps  [rsp+98h+var_68], xmm0
0x18001f344  movaps  [rsp+98h+var_58], xmm1
0x18001f349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f34e  mov     byte ptr [rdi+0AAh], 0
0x18001f355  cmp     r13, r15
0x18001f358  cmovb   r15, r13
0x18001f35c  cmp     r12, r15
0x18001f35f  cmovb   r15, r12
0x18001f363  test    rsi, rsi
0x18001f366  jz      short loc_18001F370
0x18001f368  mov     rcx, rsi; P
0x18001f36b  call    ?ReleaseReference@GipEquationManager@@QEAAXXZ; GipEquationManager::ReleaseReference(void)
0x18001f370  mov     rax, r15
0x18001f373  jmp     short loc_18001F386
0x18001f375  test    rsi, rsi
0x18001f378  jz      short loc_18001F382
0x18001f37a  mov     rcx, rsi; P
0x18001f37d  call    ?ReleaseReference@GipEquationManager@@QEAAXXZ; GipEquationManager::ReleaseReference(void)
0x18001f382  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f386  add     rsp, 58h
0x18001f38a  pop     r15
0x18001f38c  pop     r14
0x18001f38e  pop     r13
0x18001f390  pop     r12
0x18001f392  pop     rdi
0x18001f393  pop     rsi
0x18001f394  pop     rbp
0x18001f395  pop     rbx
0x18001f396  retn
```
