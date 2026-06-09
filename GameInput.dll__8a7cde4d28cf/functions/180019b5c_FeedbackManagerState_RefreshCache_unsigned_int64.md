# FeedbackManagerState::RefreshCache(unsigned __int64)

- ea: `0x180019b5c`
- end: `0x18001a09c`
- name: `?RefreshCache@FeedbackManagerState@@QEAA_K_K@Z`
- size: `1344`
- prototype: `unsigned __int64 __fastcall(FeedbackManagerState *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001ef98`

## callees

- `0x18000d658`
- `0x180019904`
- `0x180019b5c`
- `0x18001b3b8`
- `0x180020220`
- `0x180023dbc`

## pseudocode

```c
unsigned __int64 __fastcall FeedbackManagerState::RefreshCache(FeedbackManagerState *this, unsigned __int64 a2)
{
  char v2; // r10
  __int64 v3; // r14
  unsigned __int64 v4; // rdi
  unsigned __int64 v7; // rcx
  float v8; // xmm6_4
  __int64 v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __m128i v18; // xmm0
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // r12d
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r15
  unsigned __int64 updated; // rcx
  int v26; // ecx
  char v27; // r8
  __int64 v28; // r10
  int v29; // edx
  _DWORD *v30; // rbx
  unsigned __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  unsigned int v34; // r9d
  __int64 v35; // r12
  __int64 v36; // r8
  __int64 v37; // r14
  unsigned __int64 v38; // rcx
  int v39; // r8d
  int v40; // ecx
  unsigned __int64 v41; // r15
  __int64 v42; // r13
  unsigned int VersionIfNewer; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int128 v46; // xmm0
  unsigned int v47; // eax
  __int64 v48; // r11
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rax
  __int64 v51; // rcx
  unsigned __int64 *v52; // rcx
  unsigned __int64 v53; // r9
  __int64 v54; // rdx
  __int64 v56; // [rsp+30h] [rbp-78h]
  __int64 v57; // [rsp+30h] [rbp-78h]
  char v58; // [rsp+B0h] [rbp+8h]
  unsigned int v59; // [rsp+C0h] [rbp+18h]
  unsigned int v60; // [rsp+C0h] [rbp+18h]
  __int64 v61; // [rsp+C8h] [rbp+20h] BYREF

  v2 = *((_BYTE *)this + 168);
  *((_BYTE *)this + 168) = 0;
  v3 = *((_QWORD *)this + 11);
  v4 = -1;
  v58 = v2;
  if ( v3 )
  {
    if ( *((_QWORD *)this + 3) >= a2 )
    {
      v8 = 0.0;
    }
    else
    {
      v7 = a2 - *((_QWORD *)this + 3);
      if ( v7 >= 0x271000 )
      {
        v8 = FLOAT_1_0;
      }
      else
      {
        v8 = (float)(int)v7 / 2560000.0;
        v4 = a2 + 40000;
      }
    }
    v9 = 0;
    LODWORD(v61) = *(_DWORD *)(*((_QWORD *)this + 7) + 4LL);
    if ( (_DWORD)v61 )
    {
      while ( 1 )
      {
        v10 = *((_QWORD *)this + 2);
        v11 = *(unsigned int *)(v10 + 24);
        v12 = v11 + v10;
        v13 = -v11;
        if ( (v12 & -(__int64)(v13 != 0)) != 0 )
        {
          v14 = *(unsigned int *)((v12 & -(__int64)(v13 != 0)) + 4 * v9);
          v15 = v14 + v10;
          v16 = -v14;
          v17 = v15 & -(__int64)(v16 != 0);
          v56 = v17;
          if ( v17 )
          {
            if ( (v18 = _mm_cvtsi32_si128(*(_DWORD *)((v15 & -(__int64)(v16 != 0)) + 0xC)),
                  v19 = _mm_cvtsi128_si32(v18),
                  (unsigned __int8)(v19 >> 23) == 0xFF)
              && (v19 & 0x7FFFFF) != 0
              || (v20 = _mm_cvtsi128_si32(v18), !(unsigned __int8)(v20 >> 23)) && (v20 & 0x7FFFFF) != 0
              || *(float *)v18.m128i_i32 < 0.0 )
            {
              v18.m128i_i32[0] = 0;
            }
            else if ( *(float *)v18.m128i_i32 > 1.0 )
            {
              *(float *)v18.m128i_i32 = FLOAT_1_0;
            }
            if ( *(float *)v18.m128i_i32 > v8 )
              *(float *)v18.m128i_i32 = v8;
            v21 = 0;
            *(_DWORD *)(*((_QWORD *)this + 19) + 4 * v9) = v18.m128i_i32[0];
            v22 = *(unsigned __int16 *)(28LL * (unsigned int)v9 + *((_QWORD *)this + 7) + 12);
            v59 = v22;
            if ( *(_WORD *)(28LL * (unsigned int)v9 + *((_QWORD *)this + 7) + 12) )
              break;
          }
        }
LABEL_45:
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= (unsigned int)v61 )
          goto LABEL_46;
      }
      while ( 1 )
      {
        v23 = (*(unsigned int *)(v17 + 8) + v17) & ((unsigned __int128)-(__int128)*(unsigned int *)(v17 + 8) >> 64);
        if ( v23 )
        {
          v24 = v23 + 136LL * v21;
          if ( v24 )
            break;
        }
LABEL_44:
        v17 = v56;
        v3 += 376;
        if ( ++v21 >= v22 )
          goto LABEL_45;
      }
      if ( !v2 )
      {
        updated = *(_QWORD *)v3;
        if ( a2 < *(_QWORD *)v3 )
        {
LABEL_42:
          if ( updated < v4 )
            v4 = updated;
          goto LABEL_44;
        }
      }
      v26 = *(_DWORD *)(v3 + 16);
      v27 = *((_BYTE *)this + 40);
      v28 = *((_QWORD *)this + 4);
      v29 = *(_DWORD *)(176LL * (v26 & 1) + v3 + 24);
      if ( !v29 || v29 == 3 )
      {
        *(_DWORD *)(v3 + 16) = v26 + 1;
        LOBYTE(v26) = v26 + 1;
      }
      v30 = (_DWORD *)(v3 + 176LL * (v26 & 1) + 24);
      updated = FeedbackParamsCache<ForceFeedbackEffectParams>::UpdateParams(
                  v24,
                  v28,
                  v27,
                  v3 + 176LL * (((_BYTE)v26 - 1) & 1) + 24,
                  v30);
      if ( *v30 == 2 )
      {
        if ( a2 >= *(_QWORD *)(v3 + 8) )
        {
          if ( !*(_QWORD *)(v3 + 8) )
          {
LABEL_40:
            *(_QWORD *)v3 = updated;
            if ( *((_BYTE *)this + 169) )
              return -1;
            v22 = v59;
            v2 = v58;
            goto LABEL_42;
          }
          _InterlockedAnd64((volatile signed __int64 *)(v24 + 8), 0xFFFFFFFFFFFFFFFEuLL);
          *(_QWORD *)(v3 + 8) = 0;
        }
        v31 = ~a2;
      }
      else
      {
        _InterlockedOr64((volatile signed __int64 *)(v24 + 8), 1u);
        v31 = ~a2;
        if ( ~a2 > 0x1E8480 )
          v32 = a2 + 2000000;
        else
          v32 = -1;
        *(_QWORD *)(v3 + 8) = v32;
      }
      if ( v31 > 0x1F40 )
        updated = a2 + 8000;
      else
        updated = -1;
      goto LABEL_40;
    }
  }
LABEL_46:
  v33 = *((_QWORD *)this + 12);
  if ( v33 )
  {
    v34 = *((_DWORD *)this + 13);
    v35 = 0;
    v60 = v34;
    if ( v34 )
    {
      while ( 1 )
      {
        v36 = (*(unsigned int *)(*((_QWORD *)this + 2) + 12LL) + *((_QWORD *)this + 2))
            & -(__int64)(*(_DWORD *)(*((_QWORD *)this + 2) + 12LL) != 0);
        if ( v36 )
        {
          v37 = v36 + 48 * v35;
          if ( v37 )
            break;
        }
LABEL_77:
        v33 += 152;
        v35 = (unsigned int)(v35 + 1);
        if ( (unsigned int)v35 >= v34 )
          goto LABEL_78;
      }
      if ( !v2 )
      {
        v38 = *(_QWORD *)v33;
        if ( a2 < *(_QWORD *)v33 )
        {
LABEL_75:
          if ( v38 < v4 )
            v4 = v38;
          goto LABEL_77;
        }
      }
      v39 = *(_DWORD *)(v33 + 16);
      v57 = *((_QWORD *)this + 4);
      v40 = *(_DWORD *)(((unsigned __int64)(v39 & 1) << 6) + v33 + 24);
      if ( !v40 || v40 == 3 )
      {
        *(_DWORD *)(v33 + 16) = v39 + 1;
        LOBYTE(v39) = v39 + 1;
      }
      v41 = (unsigned __int64)(v39 & 1) << 6;
      v42 = v41 + v33;
      VersionIfNewer = VersionedDataGuard::GetVersionIfNewer(
                         v37,
                         48,
                         *(_QWORD *)(((unsigned __int64)(((_BYTE)v39 - 1) & 1) << 6) + v33 + 32),
                         v41 + v33 + 32);
      v45 = VersionIfNewer;
      if ( !VersionIfNewer )
      {
        while ( 1 )
        {
          *(_QWORD *)(v42 + 40) = *(_QWORD *)(v37 + 8);
          *(_DWORD *)(v42 + 48) = *(_DWORD *)(v37 + 16);
          v46 = *(_OWORD *)(v37 + 24);
          v61 = 0;
          *(_OWORD *)(v42 + 56) = v46;
          *(_OWORD *)(v42 + 72) = *(_OWORD *)(v37 + 40);
          v47 = VersionedDataGuard::GetVersionIfNewer(v37, 48, 0, &v61);
          v45 = v47;
          if ( v47 || v61 == *(_QWORD *)(v48 + 32) )
            break;
          *(_QWORD *)(v48 + 32) = v61;
        }
      }
      *(_DWORD *)(v41 + v33 + 24) = v45;
      v49 = GameInputCurrentTime(v45, v44);
      if ( !*(_DWORD *)(v41 + v33 + 24) )
      {
        anonymous_namespace_::SanitizeFeedbackEffectState(v49, v57, (unsigned __int64 *)(v42 + 40));
        *(_QWORD *)(v41 + v33 + 80) = 0;
      }
      if ( *(_DWORD *)(v41 + v33 + 24) == 2 )
      {
        if ( a2 >= *(_QWORD *)(v33 + 8) )
        {
          if ( !*(_QWORD *)(v33 + 8) )
            goto LABEL_64;
          _InterlockedAnd64((volatile signed __int64 *)v37, 0xFFFFFFFFFFFFFFFEuLL);
          *(_QWORD *)(v33 + 8) = 0;
        }
        v50 = ~a2;
      }
      else
      {
        _InterlockedOr64((volatile signed __int64 *)v37, 1u);
        v50 = ~a2;
        if ( ~a2 > 0x1E8480 )
          v51 = a2 + 2000000;
        else
          v51 = -1;
        *(_QWORD *)(v33 + 8) = v51;
      }
      if ( v50 > 0x1F40 )
      {
        v38 = a2 + 8000;
        goto LABEL_73;
      }
LABEL_64:
      v38 = -1;
LABEL_73:
      *(_QWORD *)v33 = v38;
      if ( *((_BYTE *)this + 169) )
        return -1;
      v34 = v60;
      v2 = v58;
      goto LABEL_75;
    }
  }
LABEL_78:
  v52 = (unsigned __int64 *)*((_QWORD *)this + 13);
  if ( v52 )
  {
    v53 = *v52;
    if ( v2 || a2 >= v53 )
    {
      v54 = (*(unsigned int *)(*((_QWORD *)this + 2) + 4LL) + *((_QWORD *)this + 2))
          & -(__int64)(*(_DWORD *)(*((_QWORD *)this + 2) + 4LL) != 0);
      if ( v54 )
        v53 = FeedbackParamsCache<GameInputRumbleParams>::Refresh(v52, v54, a2, v53);
    }
    if ( v53 < v4 )
      return v53;
  }
  return v4;
}

```

## disassembly

```asm
0x180019b5c  mov     rax, rsp
0x180019b5f  mov     [rax+10h], rbx
0x180019b63  push    rbp
0x180019b64  push    rsi
0x180019b65  push    rdi
0x180019b66  push    r12
0x180019b68  push    r13
0x180019b6a  push    r14
0x180019b6c  push    r15
0x180019b6e  sub     rsp, 70h
0x180019b72  xor     r10d, r10d
0x180019b75  movaps  xmmword ptr [rax-48h], xmm6
0x180019b79  nop
0x180019b7a  movaps  xmmword ptr [rax-58h], xmm7
0x180019b7e  xchg    r10b, [rcx+0A8h]
0x180019b85  nop
0x180019b86  movaps  xmmword ptr [rax-68h], xmm8
0x180019b8b  mov     r14, [rcx+58h]
0x180019b8f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180019b93  mov     [rsp+0A8h+arg_0], r10d
0x180019b9b  mov     rbp, rdx
0x180019b9e  mov     rsi, rcx
0x180019ba1  test    r14, r14
0x180019ba4  jz      loc_180019E34
0x180019baa  xorps   xmm7, xmm7
0x180019bad  movss   xmm8, cs:__real@3f800000
0x180019bb6  cmp     [rcx+18h], rdx
0x180019bba  jnb     short loc_180019C07
0x180019bbc  mov     rcx, rdx
0x180019bbf  sub     rcx, [rsi+18h]
0x180019bc3  cmp     rcx, 271000h
0x180019bca  jnb     short loc_180019C01
0x180019bcc  xorps   xmm6, xmm6
0x180019bcf  test    rcx, rcx
0x180019bd2  js      short loc_180019BDB
0x180019bd4  cvtsi2ss xmm6, rcx
0x180019bd9  jmp     short loc_180019BF0
0x180019bdb  mov     rax, rcx
0x180019bde  and     ecx, 1
0x180019be1  shr     rax, 1
0x180019be4  or      rax, rcx
0x180019be7  cvtsi2ss xmm6, rax
0x180019bec  addss   xmm6, xmm6
0x180019bf0  divss   xmm6, cs:__real@4a1c4000
0x180019bf8  lea     rdi, [rdx+9C40h]
0x180019bff  jmp     short loc_180019C0A
0x180019c01  movaps  xmm6, xmm8
0x180019c05  jmp     short loc_180019C0A
0x180019c07  xorps   xmm6, xmm6
0x180019c0a  mov     rax, [rsi+38h]
0x180019c0e  xor     r13d, r13d
0x180019c11  mov     eax, [rax+4]
0x180019c14  mov     dword ptr [rsp+0A8h+arg_18], eax
0x180019c1b  test    eax, eax
0x180019c1d  jz      loc_180019E34
0x180019c23  mov     rdx, [rsi+10h]
0x180019c27  mov     eax, [rdx+18h]
0x180019c2a  lea     rcx, [rax+rdx]
0x180019c2e  neg     rax
0x180019c31  sbb     r8, r8
0x180019c34  and     r8, rcx
0x180019c37  jz      loc_180019E23
0x180019c3d  mov     ecx, [r8+r13*4]
0x180019c41  lea     rax, [rcx+rdx]
0x180019c45  neg     rcx
0x180019c48  sbb     rdx, rdx
0x180019c4b  and     rdx, rax
0x180019c4e  mov     [rsp+0A8h+var_78], rdx
0x180019c53  jz      loc_180019E23
0x180019c59  mov     eax, [rdx+0Ch]
0x180019c5c  nop
0x180019c5d  movd    xmm0, eax
0x180019c61  movd    ecx, xmm0
0x180019c65  mov     eax, ecx
0x180019c67  shr     eax, 17h
0x180019c6a  cmp     al, 0FFh
0x180019c6c  jnz     short loc_180019C76
0x180019c6e  test    ecx, 7FFFFFh
0x180019c74  jnz     short loc_180019C90
0x180019c76  movd    ecx, xmm0
0x180019c7a  mov     eax, ecx
0x180019c7c  shr     eax, 17h
0x180019c7f  test    al, al
0x180019c81  jnz     short loc_180019C8B
0x180019c83  test    ecx, 7FFFFFh
0x180019c89  jnz     short loc_180019C90
0x180019c8b  comiss  xmm7, xmm0
0x180019c8e  jbe     short loc_180019C95
0x180019c90  movaps  xmm0, xmm7
0x180019c93  jmp     short loc_180019C9F
0x180019c95  comiss  xmm0, xmm8
0x180019c99  jbe     short loc_180019C9F
0x180019c9b  movaps  xmm0, xmm8
0x180019c9f  comiss  xmm0, xmm6
0x180019ca2  jbe     short loc_180019CA7
0x180019ca4  movaps  xmm0, xmm6
0x180019ca7  mov     rax, [rsi+98h]
0x180019cae  xor     r12d, r12d
0x180019cb1  mov     ecx, r13d
0x180019cb4  imul    rcx, 1Ch
0x180019cb8  movss   dword ptr [rax+r13*4], xmm0
0x180019cbe  mov     rax, [rsi+38h]
0x180019cc2  movzx   r8d, word ptr [rcx+rax+0Ch]
0x180019cc8  mov     [rsp+0A8h+arg_10], r8d
0x180019cd0  test    r8d, r8d
0x180019cd3  jz      loc_180019E23
0x180019cd9  mov     eax, [rdx+8]
0x180019cdc  lea     rcx, [rax+rdx]
0x180019ce0  neg     rax
0x180019ce3  sbb     rdx, rdx
0x180019ce6  and     rdx, rcx
0x180019ce9  jz      loc_180019E0B
0x180019cef  mov     eax, r12d
0x180019cf2  imul    r15, rax, 88h
0x180019cf9  add     r15, rdx
0x180019cfc  jz      loc_180019E0B
0x180019d02  test    r10b, r10b
0x180019d05  jnz     short loc_180019D13
0x180019d07  mov     rcx, [r14]
0x180019d0a  cmp     rbp, rcx
0x180019d0d  jb      loc_180019E04
0x180019d13  mov     ecx, [r14+10h]
0x180019d17  mov     eax, ecx
0x180019d19  mov     r8b, [rsi+28h]
0x180019d1d  and     eax, 1
0x180019d20  mov     r10, [rsi+20h]
0x180019d24  imul    rax, 0B0h
0x180019d2b  mov     edx, [rax+r14+18h]
0x180019d30  test    edx, edx
0x180019d32  jz      short loc_180019D39
0x180019d34  cmp     edx, 3
0x180019d37  jnz     short loc_180019D42
0x180019d39  lea     eax, [rcx+1]
0x180019d3c  mov     [r14+10h], eax
0x180019d40  mov     ecx, eax
0x180019d42  mov     eax, ecx
0x180019d44  mov     rdx, r10
0x180019d47  and     eax, 1
0x180019d4a  imul    rbx, rax, 0B0h
0x180019d51  lea     eax, [rcx-1]
0x180019d54  mov     rcx, r15
0x180019d57  and     eax, 1
0x180019d5a  add     rbx, 18h
0x180019d5e  imul    r9, rax, 0B0h
0x180019d65  add     rbx, r14
0x180019d68  add     r9, 18h
0x180019d6c  mov     [rsp+0A8h+var_88], rbx
0x180019d71  add     r9, r14
0x180019d74  call    ?UpdateParams@?$FeedbackParamsCache@UForceFeedbackEffectParams@@@@CA_KPEAVForceFeedbackEffectState@@_KEAEAUCachedParams@1@2@Z; FeedbackParamsCache<ForceFeedbackEffectParams>::UpdateParams(ForceFeedbackEffectState *,unsigned __int64,uchar,FeedbackParamsCache<ForceFeedbackEffectParams>::CachedParams &,FeedbackParamsCache<ForceFeedbackEffectParams>::CachedParams &)
0x180019d79  cmp     dword ptr [rbx], 2
0x180019d7c  mov     rcx, rax
0x180019d7f  jnz     short loc_180019DA6
0x180019d81  cmp     rbp, [r14+8]
0x180019d85  jb      short loc_180019D9E
0x180019d87  cmp     qword ptr [r14+8], 0
0x180019d8c  jz      short loc_180019DE2
0x180019d8e  nop
0x180019d8f  lock and qword ptr [r15+8], 0FFFFFFFFFFFFFFFEh
0x180019d95  nop
0x180019d96  mov     qword ptr [r14+8], 0
0x180019d9e  mov     rax, rbp
0x180019da1  not     rax
0x180019da4  jmp     short loc_180019DCD
0x180019da6  nop
0x180019da7  lock or qword ptr [r15+8], 1
0x180019dad  mov     rax, rbp
0x180019db0  nop
0x180019db1  not     rax
0x180019db4  cmp     rax, 1E8480h
0x180019dba  ja      short loc_180019DC2
0x180019dbc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019dc0  jmp     short loc_180019DC9
0x180019dc2  lea     rcx, [rbp+1E8480h]
0x180019dc9  mov     [r14+8], rcx
0x180019dcd  cmp     rax, 1F40h
0x180019dd3  ja      short loc_180019DDB
0x180019dd5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019dd9  jmp     short loc_180019DE2
0x180019ddb  lea     rcx, [rbp+1F40h]
0x180019de2  mov     [r14], rcx
0x180019de5  mov     al, [rsi+0A9h]
0x180019deb  nop
0x180019dec  test    al, al
0x180019dee  jnz     loc_18001A096
0x180019df4  mov     r8d, [rsp+0A8h+arg_10]
0x180019dfc  mov     r10d, [rsp+0A8h+arg_0]
0x180019e04  cmp     rcx, rdi
0x180019e07  cmovb   rdi, rcx
0x180019e0b  mov     rdx, [rsp+0A8h+var_78]
0x180019e10  add     r14, 178h
0x180019e17  inc     r12d
0x180019e1a  cmp     r12d, r8d
0x180019e1d  jb      loc_180019CD9
0x180019e23  inc     r13d
0x180019e26  cmp     r13d, dword ptr [rsp+0A8h+arg_18]
0x180019e2e  jb      loc_180019C23
0x180019e34  mov     rbx, [rsi+60h]
0x180019e38  test    rbx, rbx
0x180019e3b  jz      loc_18001A02D
0x180019e41  mov     r9d, [rsi+34h]
0x180019e45  xor     r12d, r12d
0x180019e48  mov     [rsp+0A8h+arg_10], r9d
0x180019e50  test    r9d, r9d
0x180019e53  jz      loc_18001A02D
0x180019e59  mov     rax, [rsi+10h]
0x180019e5d  mov     ecx, [rax+0Ch]
0x180019e60  lea     rdx, [rcx+rax]
0x180019e64  neg     rcx
0x180019e67  sbb     r8, r8
0x180019e6a  and     r8, rdx
0x180019e6d  jz      loc_18001A01A
0x180019e73  lea     r14, [r12+r12*2]
0x180019e77  shl     r14, 4
0x180019e7b  add     r14, r8
0x180019e7e  jz      loc_18001A01A
0x180019e84  test    r10b, r10b
0x180019e87  jnz     short loc_180019E95
0x180019e89  mov     rcx, [rbx]
0x180019e8c  cmp     rbp, rcx
0x180019e8f  jb      loc_18001A013
0x180019e95  mov     rax, [rsi+20h]
0x180019e99  mov     r8d, [rbx+10h]
0x180019e9d  mov     [rsp+0A8h+var_78], rax
0x180019ea2  mov     eax, r8d
0x180019ea5  and     eax, 1
0x180019ea8  shl     rax, 6
0x180019eac  mov     ecx, [rax+rbx+18h]
0x180019eb0  test    ecx, ecx
0x180019eb2  jz      short loc_180019EB9
0x180019eb4  cmp     ecx, 3
0x180019eb7  jnz     short loc_180019EC3
0x180019eb9  lea     eax, [r8+1]
0x180019ebd  mov     [rbx+10h], eax
0x180019ec0  mov     r8d, eax
0x180019ec3  mov     r15d, r8d
0x180019ec6  mov     edx, 30h ; '0'
0x180019ecb  and     r15d, 1
0x180019ecf  mov     rcx, r14
0x180019ed2  shl     r15, 6
0x180019ed6  dec     r8d
0x180019ed9  and     r8d, 1
0x180019edd  shl     r8, 6
0x180019ee1  lea     r11, [r15+rbx]
0x180019ee5  lea     r9, [r11+20h]
0x180019ee9  lea     r13, [r15+rbx]
0x180019eed  mov     r8, [r8+rbx+20h]
0x180019ef2  call    ?GetVersionIfNewer@VersionedDataGuard@@QEBA?AW4VersionedDataStatus@@I_KAEA_K@Z; VersionedDataGuard::GetVersionIfNewer(uint,unsigned __int64,unsigned __int64 &)
0x180019ef7  mov     ecx, eax
0x180019ef9  test    eax, eax
0x180019efb  jnz     short loc_180019F5E
0x180019efd  mov     rax, [r14+8]
0x180019f01  lea     r9, [rsp+0A8h+arg_18]
0x180019f09  mov     [r13+28h], rax
0x180019f0d  xor     r8d, r8d
0x180019f10  mov     eax, [r14+10h]
0x180019f14  mov     rcx, r14
0x180019f17  mov     [r13+30h], eax
0x180019f1b  movups  xmm0, xmmword ptr [r14+18h]
0x180019f20  lea     edx, [r8+30h]
0x180019f24  mov     [rsp+0A8h+arg_18], 0
0x180019f30  movups  xmmword ptr [r13+38h], xmm0
0x180019f35  movups  xmm1, xmmword ptr [r14+28h]
0x180019f3a  movups  xmmword ptr [r13+48h], xmm1
0x180019f3f  call    ?GetVersionIfNewer@VersionedDataGuard@@QEBA?AW4VersionedDataStatus@@I_KAEA_K@Z; VersionedDataGuard::GetVersionIfNewer(uint,unsigned __int64,unsigned __int64 &)
0x180019f44  mov     ecx, eax
0x180019f46  test    eax, eax
0x180019f48  jnz     short loc_180019F5E
0x180019f4a  mov     rax, [rsp+0A8h+arg_18]
0x180019f52  cmp     rax, [r11+20h]
0x180019f56  jz      short loc_180019F5E
0x180019f58  mov     [r11+20h], rax
0x180019f5c  jmp     short loc_180019EFD
0x180019f5e  mov     [r15+rbx+18h], ecx
0x180019f63  call    GameInputCurrentTime
0x180019f68  cmp     dword ptr [r15+rbx+18h], 0
0x180019f6e  jnz     short loc_180019F8A
0x180019f70  mov     rdx, [rsp+0A8h+var_78]
0x180019f75  lea     r8, [r13+28h]
0x180019f79  mov     rcx, rax
0x180019f7c  call    _anonymous_namespace___SanitizeFeedbackEffectState
0x180019f81  mov     qword ptr [r15+rbx+50h], 0
0x180019f8a  cmp     dword ptr [r15+rbx+18h], 2
0x180019f90  jnz     short loc_180019FBC
0x180019f92  cmp     rbp, [rbx+8]
0x180019f96  jb      short loc_180019FB4
0x180019f98  cmp     qword ptr [rbx+8], 0
0x180019f9d  jnz     short loc_180019FA5
0x180019f9f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019fa3  jmp     short loc_180019FF1
0x180019fa5  nop
0x180019fa6  lock and qword ptr [r14], 0FFFFFFFFFFFFFFFEh
0x180019fab  nop
0x180019fac  mov     qword ptr [rbx+8], 0
0x180019fb4  mov     rax, rbp
0x180019fb7  not     rax
0x180019fba  jmp     short loc_180019FE2
0x180019fbc  nop
0x180019fbd  lock or qword ptr [r14], 1
0x180019fc2  mov     rax, rbp
0x180019fc5  nop
  ... truncated ...
```
