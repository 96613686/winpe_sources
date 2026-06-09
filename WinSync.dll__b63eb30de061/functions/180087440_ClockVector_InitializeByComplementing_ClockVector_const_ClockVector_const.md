# ClockVector::InitializeByComplementing(ClockVector const &,ClockVector const &)

- ea: `0x180087440`
- end: `0x18008770c`
- name: `?InitializeByComplementing@ClockVector@@QEAAJAEBV1@0@Z`
- size: `716`
- prototype: `__int64 __fastcall(ClockVector *__hidden this, const struct ClockVector *, const struct ClockVector *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180087360`

## callees

- `0x18000a0f0`
- `0x18000fa00`
- `0x18000fa48`
- `0x18001a038`
- `0x18001ae20`
- `0x18001d310`
- `0x180024994`
- `0x180087440`

## string_xrefs

- `0x18008747d`: `ClockVector::InitializeByComplementing`
- `0x1800876dd`: `ClockVector::InitializeByComplementing`

## pseudocode

```c
__int64 __fastcall ClockVector::InitializeByComplementing(
        ClockVector *this,
        const struct ClockVector *a2,
        const struct ClockVector *a3)
{
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rsi
  char *v9; // r15
  unsigned int v10; // esi
  _BYTE *v11; // rbp
  char *v12; // rax
  char *v13; // rsi
  char *v14; // r12
  __int64 v15; // r11
  __int64 v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // r14
  __int64 v19; // rdx
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // xmm0_8
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // xmm0_8
  int v29; // edx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r9
  __int64 v33; // r10
  int v34; // eax
  int v35; // ecx
  int v36; // ecx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
      "ClockVector::InitializeByComplementing");
  }
  if ( !*((_DWORD *)a2 + 7) )
  {
    v10 = 0;
    v11 = (char *)a2 + 36;
    *((_DWORD *)this + 7) = 0;
    goto LABEL_41;
  }
  v6 = *((unsigned int *)a2 + 7);
  v7 = (char *)SeAlloc(saturated_mul(v6, 0x10u));
  v8 = v7;
  if ( v7 )
    `vector constructor iterator'(
      v7,
      16,
      (unsigned int)v6,
      (void (__fastcall *)(char *))SyncVersion::`default constructor closure');
  else
    v8 = 0;
  v9 = (char *)this + 40;
  v10 = ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Attach((char *)this + 40, v8);
  if ( v10 )
    goto LABEL_15;
  v11 = (char *)a2 + 36;
  if ( (*((_BYTE *)a2 + 36) & 2) != 0 )
  {
    v12 = (char *)SeAlloc(saturated_mul(v6, 0xCu));
    v13 = v12;
    if ( v12 )
      `vector constructor iterator'(v12, 12, v6, (void (__fastcall *)(char *))FeedVersion::FeedVersion);
    else
      v13 = 0;
    v14 = (char *)this + 48;
    v10 = ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Attach((char *)this + 48, v13);
    if ( v10 )
    {
LABEL_15:
      ClockVector::Recycle(this);
      goto LABEL_42;
    }
  }
  else
  {
    v14 = (char *)this + 48;
  }
  v15 = 0;
  v16 = 0;
  if ( !*((_DWORD *)a2 + 7) )
    goto LABEL_36;
  v17 = 0;
  while ( v17 < *((_DWORD *)a3 + 7) )
  {
    v18 = *((_QWORD *)a2 + 5);
    v19 = *((_QWORD *)a3 + 5);
    while ( *(_DWORD *)(v19 + 16LL * v17) < *(_DWORD *)(v18 + 16LL * (unsigned int)v15) )
    {
      if ( ++v17 >= *((_DWORD *)a3 + 7) )
        goto LABEL_32;
    }
    if ( *(_DWORD *)(v18 + 16LL * (unsigned int)v15) != *(_DWORD *)(v19 + 16LL * v17) )
    {
      v20 = (*((_BYTE *)a2 + 36) & 2) == 0;
      goto LABEL_28;
    }
    if ( *(_QWORD *)(v18 + 16LL * (unsigned int)v15 + 8) > *(_QWORD *)(v19 + 16LL * v17 + 8) )
    {
      v20 = (*v11 & 2) == 0;
LABEL_28:
      if ( !v20 )
      {
        v21 = *((_QWORD *)a2 + 6);
        v22 = *(_QWORD *)(v21 + 12 * v15);
        v23 = *(_DWORD *)(v21 + 12 * v15 + 8);
        v24 = 3 * v16;
        v25 = *((_QWORD *)this + 6);
        *(_QWORD *)(v25 + 4 * v24) = v22;
        *(_DWORD *)(v25 + 4 * v24 + 8) = v23;
      }
      v26 = 2LL * (unsigned int)v16;
      v16 = (unsigned int)(v16 + 1);
      *(_OWORD *)(*((_QWORD *)this + 5) + 8 * v26) = *(_OWORD *)(v18 + 16LL * (unsigned int)v15);
    }
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= *((_DWORD *)a2 + 7) )
      break;
  }
LABEL_32:
  v9 = (char *)this + 40;
LABEL_36:
  while ( (unsigned int)v15 < *((_DWORD *)a2 + 7) )
  {
    if ( (*((_BYTE *)a2 + 36) & 2) != 0 )
    {
      v27 = *((_QWORD *)a2 + 6);
      v28 = *(_QWORD *)(v27 + 12 * v15);
      v29 = *(_DWORD *)(v27 + 12 * v15 + 8);
      v30 = 3 * v16;
      v31 = *((_QWORD *)this + 6);
      *(_QWORD *)(v31 + 4 * v30) = v28;
      *(_DWORD *)(v31 + 4 * v30 + 8) = v29;
    }
    v32 = 2LL * (unsigned int)v15;
    v33 = 2LL * (unsigned int)v16;
    v15 = (unsigned int)(v15 + 1);
    v16 = (unsigned int)(v16 + 1);
    *(_OWORD *)(*((_QWORD *)this + 5) + 8 * v33) = *(_OWORD *)(*((_QWORD *)a2 + 5) + 8 * v32);
  }
  *((_DWORD *)this + 7) = v16;
  if ( !(_DWORD)v16 )
  {
    ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Recycle(v9);
    ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Recycle(v14);
  }
LABEL_41:
  v34 = *((_DWORD *)a2 + 8);
  *((_DWORD *)this + 9) |= 1u;
  v35 = *((_DWORD *)this + 9);
  *((_DWORD *)this + 8) = v34;
  v36 = *((_DWORD *)this + 9) ^ (*(_DWORD *)v11 ^ v35) & 2;
  *((_DWORD *)this + 9) = v36;
  *((_DWORD *)this + 9) = v36 ^ (*(_DWORD *)v11 ^ v36) & 4;
LABEL_42:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids,
      (unsigned int)"ClockVector::InitializeByComplementing",
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180087440  push    rbx
0x180087442  push    rbp
0x180087443  push    rsi
0x180087444  push    rdi
0x180087445  push    r12
0x180087447  push    r13
0x180087449  push    r14
0x18008744b  push    r15
0x18008744d  sub     rsp, 38h
0x180087451  mov     r13, r8
0x180087454  mov     rdi, rdx
0x180087457  mov     rbx, rcx
0x18008745a  mov     rcx, cs:WPP_GLOBAL_Control
0x180087461  lea     r12, WPP_GLOBAL_Control
0x180087468  cmp     rcx, r12
0x18008746b  jz      short loc_180087495
0x18008746d  test    byte ptr [rcx+1Ch], 40h
0x180087471  jz      short loc_180087495
0x180087473  cmp     byte ptr [rcx+19h], 5
0x180087477  jb      short loc_180087495
0x180087479  mov     rcx, [rcx+10h]
0x18008747d  lea     r9, aClockvectorIni; "ClockVector::InitializeByComplementing"
0x180087484  mov     edx, 1Ah
0x180087489  lea     r8, WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids
0x180087490  call    WPP_SF_s
0x180087495  cmp     dword ptr [rdi+1Ch], 0
0x180087499  jbe     loc_180087692
0x18008749f  mov     r14d, [rdi+1Ch]
0x1800874a3  mov     ebp, 10h
0x1800874a8  mov     eax, ebp
0x1800874aa  mul     r14
0x1800874ad  lea     rcx, [rbp-11h]
0x1800874b1  cmovb   rax, rcx
0x1800874b5  mov     rcx, rax; unsigned __int64
0x1800874b8  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x1800874bd  mov     rsi, rax
0x1800874c0  test    rax, rax
0x1800874c3  jz      short loc_1800874DB
0x1800874c5  lea     r9, ??_FSyncVersion@@QEAAXXZ; void *(*)(void *)
0x1800874cc  mov     r8d, r14d; unsigned __int64
0x1800874cf  mov     edx, ebp; unsigned __int64
0x1800874d1  mov     rcx, rax; void *
0x1800874d4  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800874d9  jmp     short loc_1800874DD
0x1800874db  xor     esi, esi
0x1800874dd  lea     r15, [rbx+28h]
0x1800874e1  mov     rdx, rsi
0x1800874e4  mov     rcx, r15
0x1800874e7  call    ?Attach@?$ScopedPtrBase@USyncVersion@@V?$ScopedArrayPtr@USyncVersion@@@@@@QEAAJPEAUSyncVersion@@@Z; ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Attach(SyncVersion *)
0x1800874ec  mov     esi, eax
0x1800874ee  test    eax, eax
0x1800874f0  jnz     short loc_180087554
0x1800874f2  lea     rbp, [rdi+24h]
0x1800874f6  test    byte ptr [rbp+0], 2
0x1800874fa  jz      short loc_180087561
0x1800874fc  lea     r12d, [rax+0Ch]
0x180087500  lea     rcx, [r12-0Dh]
0x180087505  mov     eax, r12d
0x180087508  mul     r14
0x18008750b  cmovb   rax, rcx
0x18008750f  mov     rcx, rax; unsigned __int64
0x180087512  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180087517  mov     rsi, rax
0x18008751a  test    rax, rax
0x18008751d  jz      short loc_180087536
0x18008751f  lea     r9, ??0FeedVersion@@QEAA@XZ; void *(*)(void *)
0x180087526  mov     r8, r14; unsigned __int64
0x180087529  mov     edx, r12d; unsigned __int64
0x18008752c  mov     rcx, rax; void *
0x18008752f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180087534  jmp     short loc_180087538
0x180087536  xor     esi, esi
0x180087538  lea     r12, [rbx+30h]
0x18008753c  mov     rdx, rsi
0x18008753f  mov     rcx, r12
0x180087542  call    ?Attach@?$ScopedPtrBase@USyncVersion@@V?$ScopedArrayPtr@USyncVersion@@@@@@QEAAJPEAUSyncVersion@@@Z; ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Attach(SyncVersion *)
0x180087547  mov     esi, eax
0x180087549  test    eax, eax
0x18008754b  jz      short loc_180087565
0x18008754d  lea     r12, WPP_GLOBAL_Control
0x180087554  mov     rcx, rbx; this
0x180087557  call    ?Recycle@ClockVector@@QEAAXXZ; ClockVector::Recycle(void)
0x18008755c  jmp     loc_1800876C1
0x180087561  lea     r12, [rbx+30h]
0x180087565  xor     r11d, r11d
0x180087568  xor     r8d, r8d
0x18008756b  cmp     [rdi+1Ch], r8d
0x18008756f  jbe     loc_18008766A
0x180087575  xor     r9d, r9d
0x180087578  cmp     r9d, [r13+1Ch]
0x18008757c  jnb     loc_180087617
0x180087582  mov     r14, [rdi+28h]
0x180087586  mov     rdx, [r13+28h]
0x18008758a  mov     r10d, r11d
0x18008758d  add     r10, r10
0x180087590  mov     ecx, [r14+r10*8]
0x180087594  mov     eax, r9d
0x180087597  add     rax, rax
0x18008759a  cmp     [rdx+rax*8], ecx
0x18008759d  jnb     short loc_1800875AA
0x18008759f  inc     r9d
0x1800875a2  cmp     r9d, [r13+1Ch]
0x1800875a6  jb      short loc_180087594
0x1800875a8  jmp     short loc_180087617
0x1800875aa  mov     ecx, r9d
0x1800875ad  add     rcx, rcx
0x1800875b0  mov     eax, [rdx+rcx*8]
0x1800875b3  cmp     [r14+r10*8], eax
0x1800875b7  jnz     short loc_1800875CB
0x1800875b9  mov     rax, [rdx+rcx*8+8]
0x1800875be  cmp     [r14+r10*8+8], rax
0x1800875c3  jbe     short loc_18008760A
0x1800875c5  test    byte ptr [rbp+0], 2
0x1800875c9  jmp     short loc_1800875CF
0x1800875cb  test    byte ptr [rdi+24h], 2
0x1800875cf  jz      short loc_1800875F3
0x1800875d1  mov     rax, [rdi+30h]
0x1800875d5  lea     rcx, [r11+r11*2]
0x1800875d9  movsd   xmm0, qword ptr [rax+rcx*4]
0x1800875de  mov     edx, [rax+rcx*4+8]
0x1800875e2  lea     rcx, [r8+r8*2]
0x1800875e6  mov     rax, [rbx+30h]
0x1800875ea  movsd   qword ptr [rax+rcx*4], xmm0
0x1800875ef  mov     [rax+rcx*4+8], edx
0x1800875f3  mov     rax, [rbx+28h]
0x1800875f7  movups  xmm0, xmmword ptr [r14+r10*8]
0x1800875fc  mov     ecx, r8d
0x1800875ff  add     rcx, rcx
0x180087602  inc     r8d
0x180087605  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x18008760a  inc     r11d
0x18008760d  cmp     r11d, [rdi+1Ch]
0x180087611  jb      loc_180087578
0x180087617  lea     r15, [rbx+28h]
0x18008761b  jmp     short loc_18008766A
0x18008761d  test    byte ptr [rdi+24h], 2
0x180087621  mov     r9d, r11d
0x180087624  mov     r10d, r8d
0x180087627  jz      short loc_18008764B
0x180087629  mov     rax, [rdi+30h]
0x18008762d  lea     rcx, [r11+r11*2]
0x180087631  movsd   xmm0, qword ptr [rax+rcx*4]
0x180087636  mov     edx, [rax+rcx*4+8]
0x18008763a  lea     rcx, [r8+r8*2]
0x18008763e  mov     rax, [rbx+30h]
0x180087642  movsd   qword ptr [rax+rcx*4], xmm0
0x180087647  mov     [rax+rcx*4+8], edx
0x18008764b  mov     rax, [rdi+28h]
0x18008764f  add     r9, r9
0x180087652  add     r10, r10
0x180087655  inc     r11d
0x180087658  inc     r8d
0x18008765b  movups  xmm0, xmmword ptr [rax+r9*8]
0x180087660  mov     rax, [rbx+28h]
0x180087664  movdqu  xmmword ptr [rax+r10*8], xmm0
0x18008766a  cmp     r11d, [rdi+1Ch]
0x18008766e  jb      short loc_18008761D
0x180087670  mov     [rbx+1Ch], r8d
0x180087674  test    r8d, r8d
0x180087677  jnz     short loc_180087689
0x180087679  mov     rcx, r15
0x18008767c  call    ?Recycle@?$ScopedPtrBase@USyncVersion@@V?$ScopedArrayPtr@USyncVersion@@@@@@QEAAXXZ; ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Recycle(void)
0x180087681  mov     rcx, r12
0x180087684  call    ?Recycle@?$ScopedPtrBase@USyncVersion@@V?$ScopedArrayPtr@USyncVersion@@@@@@QEAAXXZ; ScopedPtrBase<SyncVersion,ScopedArrayPtr<SyncVersion>>::Recycle(void)
0x180087689  lea     r12, WPP_GLOBAL_Control
0x180087690  jmp     short loc_18008769B
0x180087692  xor     esi, esi
0x180087694  lea     rbp, [rdi+24h]
0x180087698  mov     [rbx+1Ch], esi
0x18008769b  mov     eax, [rdi+20h]
0x18008769e  or      dword ptr [rbx+24h], 1
0x1800876a2  mov     ecx, [rbx+24h]
0x1800876a5  mov     [rbx+20h], eax
0x1800876a8  xor     ecx, [rbp+0]
0x1800876ab  and     ecx, 2
0x1800876ae  xor     ecx, [rbx+24h]
0x1800876b1  mov     [rbx+24h], ecx
0x1800876b4  mov     eax, ecx
0x1800876b6  xor     eax, [rbp+0]
0x1800876b9  and     eax, 4
0x1800876bc  xor     eax, ecx
0x1800876be  mov     [rbx+24h], eax
0x1800876c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800876c8  cmp     rcx, r12
0x1800876cb  jz      short loc_1800876F9
0x1800876cd  test    byte ptr [rcx+1Ch], 40h
0x1800876d1  jz      short loc_1800876F9
0x1800876d3  cmp     byte ptr [rcx+19h], 5
0x1800876d7  jb      short loc_1800876F9
0x1800876d9  mov     rcx, [rcx+10h]
0x1800876dd  lea     r9, aClockvectorIni; "ClockVector::InitializeByComplementing"
0x1800876e4  mov     edx, 1Bh
0x1800876e9  mov     [rsp+78h+var_58], esi
0x1800876ed  lea     r8, WPP_362d7c742a68350205e0bfe72ed984ca_Traceguids
0x1800876f4  call    WPP_SF_sD
0x1800876f9  mov     eax, esi
0x1800876fb  add     rsp, 38h
0x1800876ff  pop     r15
0x180087701  pop     r14
0x180087703  pop     r13
0x180087705  pop     r12
0x180087707  pop     rdi
0x180087708  pop     rsi
0x180087709  pop     rbp
0x18008770a  pop     rbx
0x18008770b  retn
```
