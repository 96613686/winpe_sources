# CInteractionContextWrapper::_UpdateInteractionOutput(INTERACTION_CONTEXT_OUTPUT const *,InteractionOutput *)

- ea: `0x1801fd15c`
- end: `0x1801fd535`
- name: `?_UpdateInteractionOutput@CInteractionContextWrapper@@AEAAXPEBUINTERACTION_CONTEXT_OUTPUT@@PEAUInteractionOutput@@@Z`
- size: `985`
- prototype: `void(CInteractionContextWrapper *__hidden this, const struct INTERACTION_CONTEXT_OUTPUT *, struct InteractionOutput *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801e59fc`
- `0x18027acc0`

## callees

- `0x1800df6a4`
- `0x18018eb18`
- `0x1801ba51c`
- `0x1801f2ce0`
- `0x1801fd15c`
- `0x180228490`

## import_xrefs

- `win32u!NtDCompositionGetFrameStatistics` at `0x1801fd2f2`
- `win32u!NtDCompositionGetFrameStatistics` at `0x1801fd2f2`
- `NInput!__imp_OutputPredictionInteractionContext` at `0x1801fd35f`
- `NInput!__imp_OutputPredictionInteractionContext` at `0x1801fd35f`

## pseudocode

```c
void __fastcall CInteractionContextWrapper::_UpdateInteractionOutput(
        CInteractionContextWrapper *this,
        const struct INTERACTION_CONTEXT_OUTPUT *a2,
        struct InteractionOutput *a3)
{
  int v6; // ecx
  float v7; // xmm0_4
  float v8; // xmm6_4
  float v9; // xmm7_4
  const struct DEVICE_INFO *v10; // rax
  const struct tagRECT *v11; // r15
  const struct MANIPULATION_TRANSFORM *v12; // r14
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  const struct MANIPULATION_TRANSFORM *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  float v20; // [rsp+B8h] [rbp-80h] BYREF
  float v21; // [rsp+BCh] [rbp-7Ch] BYREF
  int v22; // [rsp+C0h] [rbp-78h] BYREF
  int v23; // [rsp+C4h] [rbp-74h] BYREF
  int v24; // [rsp+C8h] [rbp-70h] BYREF
  int v25; // [rsp+CCh] [rbp-6Ch] BYREF
  int v26; // [rsp+D0h] [rbp-68h] BYREF
  float v27; // [rsp+D4h] [rbp-64h] BYREF
  float v28; // [rsp+D8h] [rbp-60h] BYREF
  int v29; // [rsp+DCh] [rbp-5Ch] BYREF
  int v30; // [rsp+E0h] [rbp-58h] BYREF
  int v31; // [rsp+E4h] [rbp-54h] BYREF
  int v32; // [rsp+E8h] [rbp-50h] BYREF
  int v33; // [rsp+ECh] [rbp-4Ch] BYREF
  int v34; // [rsp+F0h] [rbp-48h] BYREF
  int v35; // [rsp+F4h] [rbp-44h] BYREF
  CInteractionContextWrapper *v36; // [rsp+F8h] [rbp-40h] BYREF
  __int128 v37; // [rsp+100h] [rbp-38h] BYREF
  int v38; // [rsp+110h] [rbp-28h]
  __int128 v39; // [rsp+118h] [rbp-20h] BYREF
  __int128 v40; // [rsp+128h] [rbp-10h]
  __int64 v41; // [rsp+138h] [rbp+0h]

  *((_DWORD *)a3 + 10) = *((_DWORD *)a2 + 3);
  *((_DWORD *)a3 + 11) = *((_DWORD *)a2 + 4);
  v6 = *(_DWORD *)a2;
  if ( ((*(_DWORD *)a2 - 1) & 0xFFFFFFFC) == 0 && v6 != 3 )
  {
    *(_DWORD *)a3 = v6;
    *((_DWORD *)a3 + 1) = *((_DWORD *)a2 + 1);
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( *((_DWORD *)a2 + 19) == 2 )
      {
        if ( *((float *)a2 + 10) == 0.0 )
        {
          if ( *((float *)a2 + 11) != 0.0 )
            *((_DWORD *)a3 + 5) = 2;
        }
        else
        {
          *((_DWORD *)a3 + 5) = 1;
        }
      }
      else if ( *((_DWORD *)a2 + 19) == 1 )
      {
        *((_DWORD *)a3 + 5) = 0;
      }
      *((float *)a3 + 2) = *((float *)a2 + 5) + *((float *)a3 + 2);
      *((float *)a3 + 3) = *((float *)a2 + 6) + *((float *)a3 + 3);
      v7 = *((float *)a2 + 7);
      if ( v7 != 0.0 )
        *((float *)a3 + 4) = v7 * *((float *)a3 + 4);
      *((_DWORD *)a3 + 6) = *((_DWORD *)a2 + 15);
      *((_DWORD *)a3 + 7) = *((_DWORD *)a2 + 16);
      *((_DWORD *)a3 + 8) = *((_DWORD *)a2 + 17);
      *((_DWORD *)a3 + 9) = 0;
      *((_DWORD *)a3 + 12) = *((_DWORD *)a2 + 12);
      *((_DWORD *)a3 + 13) = *((_DWORD *)a2 + 13);
    }
  }
  v8 = *((float *)a3 + 2);
  v9 = *((float *)a3 + 3);
  v20 = v8;
  v21 = v9;
  v37 = 0;
  v38 = 0;
  if ( !CCommonRegistryData::m_fDisableInteractionOutputPrediction
    && !CCommonRegistryData::m_cForceDisableInteractionOutputPrediction
    && (*((_DWORD *)this + 58) & 0x180000) == 0 )
  {
    v10 = CPointerDeviceCache::Query(*((void **)this + 30));
    v11 = (const struct tagRECT *)(((unsigned __int64)v10 + 16) & -(__int64)(*((_BYTE *)v10 + 48) != 0));
    v41 = 0;
    v39 = 0;
    v40 = 0;
    if ( (int)NtDCompositionGetFrameStatistics(&v39, 0) >= 0 )
    {
      v12 = 0;
      if ( *(_DWORD *)a2 == 1 )
      {
        v13 = 1000 * (__int64)v40 / *((_QWORD *)&v40 + 1);
        v14 = 1000 * (__int64)v39 / *((_QWORD *)&v40 + 1);
        if ( v13 || v14 || 1000 * v41 / *((_QWORD *)&v40 + 1) )
        {
          v15 = OutputPredictionInteractionContext(
                  *((_QWORD *)this + 2),
                  1000,
                  v13,
                  v14,
                  1000 * v41 / *((_QWORD *)&v40 + 1),
                  &v37);
          v16 = (const struct MANIPULATION_TRANSFORM *)&v37;
          if ( v15 < 0 )
            v16 = 0;
          v12 = v16;
        }
      }
      CInteractionContextTransformHelper::CalculatePrediction(
        (CInteractionContextWrapper *)((char *)this + 328),
        a2,
        v12,
        v11,
        *((_DWORD *)this + 79),
        *((float *)a3 + 2),
        *((float *)a3 + 3),
        &v20,
        &v21);
      v8 = v20;
      v9 = v21;
    }
  }
  if ( (unsigned int)dword_1803B9858 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1803B9858, 2) )
  {
    v19 = *((_DWORD *)a3 + 4);
    v21 = *((float *)a3 + 11);
    v20 = *((float *)a3 + 10);
    v22 = *((_DWORD *)a3 + 9);
    v23 = *((_DWORD *)a3 + 8);
    v24 = *((_DWORD *)a3 + 7);
    v25 = *((_DWORD *)a3 + 6);
    v29 = DWORD1(v37);
    v30 = v37;
    v31 = *((_DWORD *)a2 + 11);
    v32 = *((_DWORD *)a2 + 10);
    v34 = *((_DWORD *)a3 + 3);
    v35 = *((_DWORD *)a3 + 2);
    v27 = v9;
    v28 = v8;
    v26 = v19;
    v33 = v19;
    v36 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)&unk_18039677B,
      v17,
      v18,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  *((float *)a3 + 2) = v8;
  *((float *)a3 + 3) = v9;
}

```

## disassembly

```asm
0x1801fd15c  mov     rax, rsp
0x1801fd15f  mov     [rax+20h], rbx
0x1801fd163  push    rbp
0x1801fd164  push    rsi
0x1801fd165  push    rdi
0x1801fd166  push    r14
0x1801fd168  push    r15
0x1801fd16a  lea     rbp, [rax-58h]
0x1801fd16e  sub     rsp, 160h
0x1801fd175  movaps  xmmword ptr [rax-38h], xmm6
0x1801fd179  movaps  xmmword ptr [rax-48h], xmm7
0x1801fd17d  mov     rax, cs:__security_cookie
0x1801fd184  xor     rax, rsp
0x1801fd187  mov     [rbp+50h+var_48], rax
0x1801fd18b  mov     eax, [rdx+0Ch]
0x1801fd18e  mov     rsi, rcx
0x1801fd191  mov     [r8+28h], eax
0x1801fd195  mov     rbx, r8
0x1801fd198  mov     eax, [rdx+10h]
0x1801fd19b  mov     rdi, rdx
0x1801fd19e  mov     [r8+2Ch], eax
0x1801fd1a2  mov     ecx, [rdx]
0x1801fd1a4  lea     eax, [rcx-1]
0x1801fd1a7  test    eax, 0FFFFFFFCh
0x1801fd1ac  jnz     loc_1801FD276
0x1801fd1b2  cmp     ecx, 3
0x1801fd1b5  jz      loc_1801FD276
0x1801fd1bb  mov     [r8], ecx
0x1801fd1be  mov     eax, [rdx+4]
0x1801fd1c1  mov     [r8+4], eax
0x1801fd1c5  cmp     dword ptr [rdx], 1
0x1801fd1c8  jnz     loc_1801FD276
0x1801fd1ce  cmp     dword ptr [rdx+4Ch], 2
0x1801fd1d2  xorps   xmm2, xmm2
0x1801fd1d5  jnz     short loc_1801FD203
0x1801fd1d7  movss   xmm0, dword ptr [rdx+28h]
0x1801fd1dc  ucomiss xmm0, xmm2
0x1801fd1df  jp      short loc_1801FD1F9
0x1801fd1e1  jnz     short loc_1801FD1F9
0x1801fd1e3  movss   xmm0, dword ptr [rdx+2Ch]
0x1801fd1e8  ucomiss xmm0, xmm2
0x1801fd1eb  jp      short loc_1801FD1EF
0x1801fd1ed  jz      short loc_1801FD211
0x1801fd1ef  mov     dword ptr [r8+14h], 2
0x1801fd1f7  jmp     short loc_1801FD211
0x1801fd1f9  mov     dword ptr [r8+14h], 1
0x1801fd201  jmp     short loc_1801FD211
0x1801fd203  cmp     dword ptr [rdx+4Ch], 1
0x1801fd207  jnz     short loc_1801FD211
0x1801fd209  mov     dword ptr [r8+14h], 0
0x1801fd211  movss   xmm0, dword ptr [rdx+14h]
0x1801fd216  addss   xmm0, dword ptr [r8+8]
0x1801fd21c  movss   dword ptr [r8+8], xmm0
0x1801fd222  movss   xmm1, dword ptr [rdx+18h]
0x1801fd227  addss   xmm1, dword ptr [r8+0Ch]
0x1801fd22d  movss   dword ptr [r8+0Ch], xmm1
0x1801fd233  movss   xmm0, dword ptr [rdx+1Ch]
0x1801fd238  ucomiss xmm0, xmm2
0x1801fd23b  jp      short loc_1801FD23F
0x1801fd23d  jz      short loc_1801FD24B
0x1801fd23f  mulss   xmm0, dword ptr [r8+10h]
0x1801fd245  movss   dword ptr [r8+10h], xmm0
0x1801fd24b  mov     eax, [rdx+3Ch]
0x1801fd24e  mov     [r8+18h], eax
0x1801fd252  mov     eax, [rdx+40h]
0x1801fd255  mov     [r8+1Ch], eax
0x1801fd259  mov     eax, [rdx+44h]
0x1801fd25c  mov     [r8+20h], eax
0x1801fd260  mov     dword ptr [r8+24h], 0
0x1801fd268  mov     eax, [rdx+30h]
0x1801fd26b  mov     [r8+30h], eax
0x1801fd26f  mov     eax, [rdx+34h]
0x1801fd272  mov     [r8+34h], eax
0x1801fd276  movss   xmm6, dword ptr [r8+8]
0x1801fd27c  xor     eax, eax
0x1801fd27e  cmp     cs:?m_fDisableInteractionOutputPrediction@CCommonRegistryData@@0HA, eax; int CCommonRegistryData::m_fDisableInteractionOutputPrediction
0x1801fd284  xorps   xmm0, xmm0
0x1801fd287  movss   xmm7, dword ptr [r8+0Ch]
0x1801fd28d  movss   [rbp+50h+var_D0], xmm6
0x1801fd292  movss   [rbp+50h+var_CC], xmm7
0x1801fd297  movups  [rbp+50h+var_88], xmm0
0x1801fd29b  mov     [rbp+50h+var_78], eax
0x1801fd29e  jnz     loc_1801FD3C3
0x1801fd2a4  cmp     cs:?m_cForceDisableInteractionOutputPrediction@CCommonRegistryData@@0IA, eax; uint CCommonRegistryData::m_cForceDisableInteractionOutputPrediction
0x1801fd2aa  ja      loc_1801FD3C3
0x1801fd2b0  test    dword ptr [rsi+0E8h], 180000h
0x1801fd2ba  jnz     loc_1801FD3C3
0x1801fd2c0  mov     rcx, [rsi+0F0h]; void *
0x1801fd2c7  call    ?Query@CPointerDeviceCache@@SAAEBUDEVICE_INFO@@PEAX@Z; CPointerDeviceCache::Query(void *)
0x1801fd2cc  xorps   xmm0, xmm0
0x1801fd2cf  mov     cl, [rax+30h]
0x1801fd2d2  add     rax, 10h
0x1801fd2d6  neg     cl
0x1801fd2d8  lea     rcx, [rbp+50h+var_70]
0x1801fd2dc  sbb     r15, r15
0x1801fd2df  xor     edx, edx
0x1801fd2e1  and     r15, rax
0x1801fd2e4  xor     eax, eax
0x1801fd2e6  mov     [rbp+50h+var_50], rax
0x1801fd2ea  movups  [rbp+50h+var_70], xmm0
0x1801fd2ee  movups  [rbp+50h+var_60], xmm0
0x1801fd2f2  call    cs:__imp_NtDCompositionGetFrameStatistics
0x1801fd2f8  test    eax, eax
0x1801fd2fa  js      loc_1801FD3C3
0x1801fd300  xor     r14d, r14d
0x1801fd303  cmp     dword ptr [rdi], 1
0x1801fd306  jnz     short loc_1801FD372
0x1801fd308  mov     rcx, qword ptr [rbp+50h+var_60+8]
0x1801fd30c  imul    rax, qword ptr [rbp+50h+var_60], 3E8h
0x1801fd314  cqo
0x1801fd316  idiv    rcx
0x1801fd319  mov     r8, rax
0x1801fd31c  imul    rax, qword ptr [rbp+50h+var_70], 3E8h
0x1801fd324  cqo
0x1801fd326  idiv    rcx
0x1801fd329  mov     r9, rax
0x1801fd32c  imul    rax, [rbp+50h+var_50], 3E8h
0x1801fd334  cqo
0x1801fd336  idiv    rcx
0x1801fd339  test    r8, r8
0x1801fd33c  jnz     short loc_1801FD348
0x1801fd33e  test    r9, r9
0x1801fd341  jnz     short loc_1801FD348
0x1801fd343  test    rax, rax
0x1801fd346  jz      short loc_1801FD372
0x1801fd348  lea     rcx, [rbp+50h+var_88]
0x1801fd34c  mov     edx, 3E8h
0x1801fd351  mov     qword ptr [rsp+180h+var_158], rcx
0x1801fd356  mov     rcx, [rsi+10h]
0x1801fd35a  mov     qword ptr [rsp+180h+var_160], rax
0x1801fd35f  call    cs:__imp_OutputPredictionInteractionContext
0x1801fd365  test    eax, eax
0x1801fd367  lea     rcx, [rbp+50h+var_88]
0x1801fd36b  cmovs   rcx, r14
0x1801fd36f  mov     r14, rcx
0x1801fd372  movss   xmm0, dword ptr [rbx+0Ch]
0x1801fd377  lea     rax, [rbp+50h+var_CC]
0x1801fd37b  movss   xmm1, dword ptr [rbx+8]
0x1801fd380  lea     rcx, [rsi+148h]; this
0x1801fd387  mov     [rsp+180h+var_140], rax; float *
0x1801fd38c  mov     r9, r15; struct tagRECT *
0x1801fd38f  lea     rax, [rbp+50h+var_D0]
0x1801fd393  mov     r8, r14; struct MANIPULATION_TRANSFORM *
0x1801fd396  mov     [rsp+180h+var_148], rax; float *
0x1801fd39b  mov     rdx, rdi; struct INTERACTION_CONTEXT_OUTPUT *
0x1801fd39e  mov     eax, [rsi+13Ch]
0x1801fd3a4  movss   [rsp+180h+var_150], xmm0; float
0x1801fd3aa  movss   [rsp+180h+var_158], xmm1; float
0x1801fd3b0  mov     [rsp+180h+var_160], eax; unsigned int
0x1801fd3b4  call    ?CalculatePrediction@CInteractionContextTransformHelper@@QEAAXAEBUINTERACTION_CONTEXT_OUTPUT@@PEBUMANIPULATION_TRANSFORM@@PEBUtagRECT@@IMMPEAM3@Z; CInteractionContextTransformHelper::CalculatePrediction(INTERACTION_CONTEXT_OUTPUT const &,MANIPULATION_TRANSFORM const *,tagRECT const *,uint,float,float,float *,float *)
0x1801fd3b9  movss   xmm6, [rbp+50h+var_D0]
0x1801fd3be  movss   xmm7, [rbp+50h+var_CC]
0x1801fd3c3  mov     eax, cs:dword_1803B9858
0x1801fd3c9  cmp     eax, 4
0x1801fd3cc  jbe     loc_1801FD4FE
0x1801fd3d2  mov     edx, 2
0x1801fd3d7  lea     rcx, dword_1803B9858
0x1801fd3de  call    _tlgKeywordOn
0x1801fd3e3  test    al, al
0x1801fd3e5  jz      loc_1801FD4FE
0x1801fd3eb  mov     eax, [rbx+2Ch]
0x1801fd3ee  lea     rdx, unk_18039677B
0x1801fd3f5  mov     ecx, [rbx+10h]
0x1801fd3f8  mov     [rbp+50h+var_CC], eax
0x1801fd3fb  mov     eax, [rbx+28h]
0x1801fd3fe  mov     [rbp+50h+var_D0], eax
0x1801fd401  mov     eax, [rbx+24h]
0x1801fd404  mov     [rbp+50h+var_C8], eax
0x1801fd407  mov     eax, [rbx+20h]
0x1801fd40a  mov     [rbp+50h+var_C4], eax
0x1801fd40d  mov     eax, [rbx+1Ch]
0x1801fd410  mov     [rbp+50h+var_C0], eax
0x1801fd413  mov     eax, [rbx+18h]
0x1801fd416  mov     [rbp+50h+var_BC], eax
0x1801fd419  mov     eax, dword ptr [rbp+50h+var_88+4]
0x1801fd41c  mov     [rbp+50h+var_AC], eax
0x1801fd41f  mov     eax, dword ptr [rbp+50h+var_88]
0x1801fd422  mov     [rbp+50h+var_A8], eax
0x1801fd425  mov     eax, [rdi+2Ch]
0x1801fd428  mov     [rbp+50h+var_A4], eax
0x1801fd42b  mov     eax, [rdi+28h]
0x1801fd42e  mov     [rbp+50h+var_A0], eax
0x1801fd431  mov     eax, [rbx+0Ch]
0x1801fd434  mov     [rbp+50h+var_98], eax
0x1801fd437  mov     eax, [rbx+8]
0x1801fd43a  mov     [rbp+50h+var_94], eax
0x1801fd43d  lea     rax, [rbp+50h+var_CC]
0x1801fd441  mov     [rsp+180h+var_E0], rax
0x1801fd449  lea     rax, [rbp+50h+var_D0]
0x1801fd44d  mov     [rsp+180h+var_E8], rax
0x1801fd455  lea     rax, [rbp+50h+var_C8]
0x1801fd459  mov     [rsp+180h+var_F0], rax
0x1801fd461  lea     rax, [rbp+50h+var_C4]
0x1801fd465  mov     [rsp+180h+var_F8], rax
0x1801fd46d  lea     rax, [rbp+50h+var_C0]
0x1801fd471  mov     [rsp+180h+var_100], rax
0x1801fd479  lea     rax, [rbp+50h+var_BC]
0x1801fd47d  mov     [rsp+180h+var_108], rax
0x1801fd482  lea     rax, [rbp+50h+var_B8]
0x1801fd486  mov     [rsp+180h+var_110], rax
0x1801fd48b  lea     rax, [rbp+50h+var_B4]
0x1801fd48f  mov     [rsp+180h+var_118], rax
0x1801fd494  lea     rax, [rbp+50h+var_B0]
0x1801fd498  mov     [rsp+180h+var_120], rax
0x1801fd49d  lea     rax, [rbp+50h+var_AC]
0x1801fd4a1  mov     [rsp+180h+var_128], rax
0x1801fd4a6  lea     rax, [rbp+50h+var_A8]
0x1801fd4aa  mov     [rsp+180h+var_130], rax
0x1801fd4af  lea     rax, [rbp+50h+var_A4]
0x1801fd4b3  mov     [rsp+180h+var_138], rax
0x1801fd4b8  lea     rax, [rbp+50h+var_A0]
0x1801fd4bc  mov     [rsp+180h+var_140], rax
0x1801fd4c1  lea     rax, [rbp+50h+var_9C]
0x1801fd4c5  mov     [rsp+180h+var_148], rax
0x1801fd4ca  lea     rax, [rbp+50h+var_98]
0x1801fd4ce  mov     qword ptr [rsp+180h+var_150], rax
0x1801fd4d3  lea     rax, [rbp+50h+var_94]
0x1801fd4d7  mov     qword ptr [rsp+180h+var_158], rax
0x1801fd4dc  lea     rax, [rbp+50h+var_90]
0x1801fd4e0  mov     qword ptr [rsp+180h+var_160], rax
0x1801fd4e5  movss   [rbp+50h+var_B4], xmm7
0x1801fd4ea  movss   [rbp+50h+var_B0], xmm6
0x1801fd4ef  mov     [rbp+50h+var_B8], ecx
0x1801fd4f2  mov     [rbp+50h+var_9C], ecx
0x1801fd4f5  mov     [rbp+50h+var_90], rsi
0x1801fd4f9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444444444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801fd4fe  movss   dword ptr [rbx+8], xmm6
0x1801fd503  movss   dword ptr [rbx+0Ch], xmm7
0x1801fd508  mov     rcx, [rbp+50h+var_48]
0x1801fd50c  xor     rcx, rsp; StackCookie
0x1801fd50f  call    __security_check_cookie
0x1801fd514  lea     r11, [rsp+180h+var_20]
0x1801fd51c  mov     rbx, [r11+48h]
0x1801fd520  movaps  xmm6, xmmword ptr [r11-10h]
0x1801fd525  movaps  xmm7, xmmword ptr [r11-20h]
0x1801fd52a  mov     rsp, r11
0x1801fd52d  pop     r15
0x1801fd52f  pop     r14
0x1801fd531  pop     rdi
0x1801fd532  pop     rsi
0x1801fd533  pop     rbp
0x1801fd534  retn
```
