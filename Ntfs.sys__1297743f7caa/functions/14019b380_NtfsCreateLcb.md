# NtfsCreateLcb

- ea: `0x14019b380`
- end: `0x14019ba5a`
- name: `NtfsCreateLcb`
- size: `1754`
- prototype: ``
- caller_count: `17`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400d2654`
- `0x14012c80c`
- `0x140132210`
- `0x14014a980`
- `0x1401842cc`
- `0x14018cb98`
- `0x140199220`
- `0x1401c3750`
- `0x14020d880`
- `0x140227568`
- `0x1402376fc`
- `0x1402475a4`
- `0x14024ad64`
- `0x14024c8e4`
- `0x14024fbf4`
- `0x140258198`
- `0x140265594`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x14000c290`
- `0x140021b10`
- `0x1400410a8`
- `0x140059440`
- `0x140059740`
- `0x140059c60`
- `0x14014de30`
- `0x140162110`
- `0x14019a768`
- `0x14019b380`
- `0x140207e90`

## import_xrefs

- `ntoskrnl!RtlGetNtSystemRoot` at `0x14019b5e1`
- `ntoskrnl!RtlGetNtSystemRoot` at `0x14019b5e1`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14019b81b`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14019b81b`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14019b56e`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14019b56e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac99f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac99f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b94c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b94c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac9c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac9c2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b4b7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b4b7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b673`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b761`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b82f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b673`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b761`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019b82f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b63f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b6a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b7a1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b63f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b6a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b7a1`

## pseudocode

```c
__int64 __fastcall NtfsCreateLcb(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 *a4, char a5, __int64 a6)
{
  __int64 v7; // rbx
  __int64 v9; // r13
  _BYTE *v10; // rdi
  __int64 v11; // r10
  __int64 v12; // rdx
  char v13; // r15
  __int64 result; // rax
  int v15; // eax
  _DWORD *v16; // rdi
  __int16 v17; // r12
  __int64 v18; // rdx
  _QWORD *PoolWithTag; // rdx
  void *v20; // rcx
  __int64 v21; // rdx
  char v22; // cl
  _QWORD *v23; // r9
  _WORD *v24; // rcx
  __int64 v25; // rax
  char v26; // r14
  int v27; // eax
  _DWORD *v28; // r9
  _QWORD *v29; // rcx
  __int64 v30; // r15
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r15
  _QWORD *v35; // rdx
  char v36; // dl
  _DWORD *v37; // rax
  int v38; // eax
  int v39; // [rsp+28h] [rbp-60h]
  _QWORD *v40; // [rsp+98h] [rbp+10h] BYREF

  v7 = a3;
  v9 = a1;
  LOBYTE(v40) = 1;
  v10 = &v40;
  if ( a6 )
    v10 = (_BYTE *)a6;
  v11 = *(_QWORD *)(a2 + 184);
  v12 = *(_QWORD *)(v11 + 320);
  if ( v12 )
  {
    a1 = *(_QWORD *)(a3 + 320);
    if ( a1 )
    {
      if ( a1 != v12 )
      {
        if ( (*(_DWORD *)(a3 + 4) & 8) == 0
          || (v38 = *(_DWORD *)(a3 + 8), v38 != 5) && *(_DWORD *)(a1 + 88) != v38
          || v12 != *(_QWORD *)(*(_QWORD *)(v12 + 16) + 6248LL) )
        {
          NtfsAttachCorruption_BadOrOrphanFRS(v9, 2, 2239799, (_DWORD)a4, v11 + 8, v11, 0);
          NtfsAttachRepairInfoPriv(v9, 256, 0, 0x13700222D37LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v9, 3221225730LL, 2239799);
          NtfsRaiseStatusInternal(v9, -1073741566, *(_QWORD *)(a2 + 184) + 8, *(_QWORD *)(a2 + 184), 2239799);
          __debugbreak();
        }
      }
    }
  }
  v13 = a5;
  result = NtfsFindExistingLcb(a1, v11, a3, (_DWORD)a4, a5, 1);
  if ( result )
  {
    *v10 = 1;
  }
  else if ( *v10 )
  {
    LOBYTE(a6) = 0;
    *v10 = 0;
    v15 = *(_DWORD *)(v7 + 4);
    if ( (v15 & 0x200) == 0 || (v16 = (_DWORD *)(v7 + 1144), *(_WORD *)(v7 + 1144)) )
    {
      if ( (v15 & 0x400) == 0 || (v16 = (_DWORD *)(v7 + 1352), *(_WORD *)(v7 + 1352)) )
      {
        v16 = ExAllocateFromLookasideListEx(&NtfsLcbLookasideList);
        LOBYTE(v17) = 0;
      }
      else
      {
        LOBYTE(v17) = 17;
      }
    }
    else
    {
      LOBYTE(v17) = 17;
    }
    memset(v16, 0, 0xD4u);
    *v16 = 14157579;
    v18 = *a4;
    v40 = v16 + 48;
    if ( (unsigned __int8)v17 >= (unsigned __int16)((unsigned __int16)v18 >> 1) )
    {
      PoolWithTag = v16 + 36;
      *((_QWORD *)v16 + 24) = v16 + 36;
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v18 + 66, 0x7346744Eu);
      *v40 = PoolWithTag;
      v17 = *a4 >> 1;
    }
    *PoolWithTag = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
    *(_BYTE *)(*((_QWORD *)v16 + 24) + 64LL) = *a4 >> 1;
    *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) = v13;
    v20 = (void *)(*((_QWORD *)v16 + 24) + 66LL);
    *((_QWORD *)v16 + 10) = v20;
    *((_WORD *)v16 + 36) = *a4;
    *((_WORD *)v16 + 37) = 2 * (unsigned __int8)v17;
    memmove(v20, *((const void **)a4 + 1), *a4);
    v22 = *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) & 3;
    if ( (unsigned __int8)(v22 - 1) <= 1u )
    {
      if ( v22 == 2 )
      {
        LOBYTE(v21) = 1;
        v37 = (_DWORD *)NtfsLookupLcbByFlags(v7, v21);
        if ( v37 )
        {
          v16[9] = v37[9];
          v16[10] = v37[10];
          v16[11] = v37[11];
        }
      }
      else if ( v22 == 1 )
      {
        v28 = 0;
        v29 = *(_QWORD **)(v7 + 48);
        while ( v29 != (_QWORD *)(v7 + 48) )
        {
          if ( (*((_DWORD *)v29 - 13) & 2) != 0 )
          {
            v29 = (_QWORD *)*v29;
          }
          else
          {
            if ( *(_BYTE *)(v29[17] + 65LL) == 2 )
            {
              v28 = v29 - 7;
              break;
            }
            v29 = (_QWORD *)*v29;
          }
        }
        if ( v28 )
        {
          v16[9] = v28[9];
          v16[10] = v28[10];
          v16[11] = v28[11];
        }
      }
    }
    if ( (*(_DWORD *)(v7 + 176) & 0x10000000) != 0 )
    {
      v30 = 0;
      while ( 1 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v7 + 104) + 8LL));
        v31 = v7 + 48;
        v32 = *(_QWORD *)(v7 + 48);
        if ( v32 != v7 + 48 )
        {
          v33 = *(_QWORD *)(v7 + 48);
LABEL_46:
          if ( !v30 )
          {
            v34 = v33;
            goto LABEL_48;
          }
          goto LABEL_66;
        }
LABEL_50:
        v30 = 0;
        while ( 1 )
        {
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v7 + 104) + 8LL));
          if ( !v30 )
          {
            *((_QWORD *)v16 + 17) = NtfsCreateScb(v9, v7, 160, &NtfsFileNameIndex, 1, 0, 0);
            goto LABEL_16;
          }
          if ( (*(_DWORD *)(v30 + 4) & 2) != 0 )
            break;
          if ( (v36 = *(_BYTE *)(*((_QWORD *)v16 + 24) + 65LL) & 3, v36 == 2)
            && (*(_BYTE *)(*(_QWORD *)(v30 + 192) + 65LL) & 3) == 1
            || v36 == 1 && (*(_BYTE *)(*(_QWORD *)(v30 + 192) + 65LL) & 3) == 2 )
          {
            if ( a2 == *(_QWORD *)(v30 + 24) )
              break;
          }
          v7 = 0x17600222DCFLL;
          a6 = 0x17600222DCFLL;
          NtfsAttachCorruptionSimple(v9, 2, 2, 2239951, 0, v39);
          NtfsAttachRepairInfoPriv(v9, 0, 0, 0x17600222DCFLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v9, 3221225522LL, 2239951);
          NtfsRaiseStatusInternal(v9, -1073741774, 0, 0, 2239951);
LABEL_66:
          v34 = *(_QWORD *)(v30 + 56);
          if ( v34 == v31 )
            goto LABEL_50;
          v33 = v32;
LABEL_48:
          v30 = v34 - 56;
          if ( (*(_DWORD *)(v30 + 4) & 2) != 0 )
            goto LABEL_46;
        }
      }
    }
LABEL_16:
    FsRtlAcquireHeaderMutex(a2 + 120, a2 + 160);
    v23 = *(_QWORD **)(a2 + 648);
    if ( *v23 != a2 + 640 )
      goto LABEL_17;
    *((_QWORD *)v16 + 1) = a2 + 640;
    *((_QWORD *)v16 + 2) = v23;
    *v23 = v16 + 2;
    *(_QWORD *)(a2 + 648) = v16 + 2;
    *((_QWORD *)v16 + 3) = a2;
    FsRtlReleaseHeaderMutex(a2 + 120, a2 + 160);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v7 + 104) + 8LL));
    v35 = *(_QWORD **)(v7 + 56);
    if ( *v35 != v7 + 48 )
LABEL_17:
      __fastfail(3u);
    *((_QWORD *)v16 + 7) = v7 + 48;
    *((_QWORD *)v16 + 8) = v35;
    *v35 = v16 + 14;
    *(_QWORD *)(v7 + 56) = v16 + 14;
    *((_QWORD *)v16 + 6) = v7;
    *((_QWORD *)v16 + 16) = v16 + 30;
    *((_QWORD *)v16 + 15) = v16 + 30;
    if ( !TxfSearchingForSystemRoot )
      goto LABEL_24;
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 96) + 248LL) + 16LL) + 48LL) & 0x100) == 0 )
      goto LABEL_24;
    if ( !*(_QWORD *)(a2 + 664) )
      goto LABEL_24;
    v24 = (_WORD *)(RtlGetNtSystemRoot() + 4);
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    if ( *(unsigned __int16 *)(a2 + 656) == 2 * v25 )
    {
      v27 = memcmp(v24, *(const void **)(a2 + 664), 2 * v25);
      v26 = a6;
      if ( !v27 )
        v26 = 1;
    }
    else
    {
LABEL_24:
      v26 = a6;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) & 0x1800000) != 0 )
      *(_DWORD *)(v7 + 4) |= 0x1000000u;
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v7 + 104) + 8LL));
    if ( v26 )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 104LL) + 8LL));
      *(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) |= 0x800000u;
      TxfSearchingForSystemRoot = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 104LL) + 8LL));
    }
    return (__int64)v16;
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14019b380  mov     rax, rsp
0x14019b383  mov     [rax+8], rbx
0x14019b387  mov     [rax+18h], rsi
0x14019b38b  push    rdi
0x14019b38c  push    r12
0x14019b38e  push    r13
0x14019b390  push    r14
0x14019b392  push    r15
0x14019b394  sub     rsp, 60h
0x14019b398  mov     r14, r9
0x14019b39b  mov     rbx, r8
0x14019b39e  mov     rsi, rdx
0x14019b3a1  mov     r13, rcx
0x14019b3a4  mov     byte ptr [rax+10h], 1
0x14019b3a8  xorps   xmm0, xmm0
0x14019b3ab  movdqu  xmmword ptr [rax-40h], xmm0
0x14019b3b0  lea     rdi, [rax+10h]
0x14019b3b4  mov     rax, [rsp+88h+arg_28]
0x14019b3bc  test    rax, rax
0x14019b3bf  cmovnz  rdi, rax
0x14019b3c3  mov     r10, [rdx+0B8h]
0x14019b3ca  mov     rdx, [r10+140h]
0x14019b3d1  test    rdx, rdx
0x14019b3d4  jz      short loc_14019B3EB
0x14019b3d6  mov     rcx, [r8+140h]
0x14019b3dd  test    rcx, rcx
0x14019b3e0  jz      short loc_14019B3EB
0x14019b3e2  cmp     rcx, rdx
0x14019b3e5  jnz     loc_14019B99F
0x14019b3eb  mov     byte ptr [rsp+88h+var_60], 1
0x14019b3f0  movzx   r15d, [rsp+88h+arg_20]
0x14019b3f9  mov     byte ptr [rsp+88h+var_68], r15b
0x14019b3fe  mov     rdx, r10
0x14019b401  call    NtfsFindExistingLcb
0x14019b406  mov     [rsp+88h+var_48], rax
0x14019b40b  test    rax, rax
0x14019b40e  jz      short loc_14019B42E
0x14019b410  mov     byte ptr [rdi], 1
0x14019b413  lea     r11, [rsp+88h+var_28]
0x14019b418  mov     rbx, [r11+30h]
0x14019b41c  mov     rsi, [r11+40h]
0x14019b420  mov     rsp, r11
0x14019b423  pop     r15
0x14019b425  pop     r14
0x14019b427  pop     r13
0x14019b429  pop     r12
0x14019b42b  pop     rdi
0x14019b42c  retn
0x14019b42e  cmp     byte ptr [rdi], 0
0x14019b431  jz      loc_14019BA45
0x14019b437  mov     byte ptr [rsp+88h+arg_28], 0
0x14019b43f  mov     byte ptr [rdi], 0
0x14019b442  mov     eax, [rbx+4]
0x14019b445  bt      eax, 9
0x14019b449  jnb     loc_14019B925
0x14019b44f  lea     rdi, [rbx+478h]
0x14019b456  cmp     word ptr [rdi], 0
0x14019b45a  jnz     loc_14019B925
0x14019b460  mov     [rsp+88h+var_48], rdi
0x14019b465  mov     r12b, 11h
0x14019b468  xor     edx, edx; Val
0x14019b46a  mov     r8d, 0D4h; Size
0x14019b470  mov     rcx, rdi; void *
0x14019b473  call    memset
0x14019b478  mov     dword ptr [rdi], 0D8070Bh
0x14019b47e  movzx   edx, word ptr [r14]
0x14019b482  lea     r8, [rdi+0C0h]
0x14019b489  mov     [rsp+88h+arg_8], r8
0x14019b491  movzx   ecx, dx
0x14019b494  shr     cx, 1
0x14019b497  movzx   eax, r12b
0x14019b49b  cmp     ax, cx
0x14019b49e  jnb     loc_14019B6DF
0x14019b4a4  add     rdx, 42h ; 'B'; NumberOfBytes
0x14019b4a8  mov     ecx, cs:PoolType
0x14019b4ae  or      ecx, 10h; PoolType
0x14019b4b1  mov     r8d, 7346744Eh; Tag
0x14019b4b7  call    cs:__imp_ExAllocatePoolWithTag
0x14019b4be  nop     dword ptr [rax+rax+00h]
0x14019b4c3  mov     rdx, rax
0x14019b4c6  mov     [rsp+88h+var_38], rax
0x14019b4cb  mov     rax, [rsp+88h+arg_8]
0x14019b4d3  mov     [rax], rdx
0x14019b4d6  movzx   r12d, word ptr [r14]
0x14019b4da  shr     r12w, 1
0x14019b4de  mov     rax, [rsi+0B8h]
0x14019b4e5  mov     rcx, [rax+8]
0x14019b4e9  mov     [rdx], rcx
0x14019b4ec  movzx   ecx, word ptr [r14]
0x14019b4f0  shr     cx, 1
0x14019b4f3  mov     rax, [rdi+0C0h]
0x14019b4fa  mov     [rax+40h], cl
0x14019b4fd  mov     rax, [rdi+0C0h]
0x14019b504  mov     [rax+41h], r15b
0x14019b508  mov     rcx, [rdi+0C0h]
0x14019b50f  add     rcx, 42h ; 'B'; void *
0x14019b513  mov     [rdi+50h], rcx
0x14019b517  movzx   eax, word ptr [r14]
0x14019b51b  mov     [rdi+48h], ax
0x14019b51f  movzx   eax, r12b
0x14019b523  add     ax, ax
0x14019b526  mov     [rdi+4Ah], ax
0x14019b52a  movzx   r8d, word ptr [r14]; Size
0x14019b52e  mov     rdx, [r14+8]; Src
0x14019b532  call    memmove
0x14019b537  mov     rax, [rdi+0C0h]
0x14019b53e  movzx   ecx, byte ptr [rax+41h]
0x14019b542  and     cl, 3
0x14019b545  lea     eax, [rcx-1]
0x14019b548  cmp     al, 1
0x14019b54a  jbe     loc_14019B6EE
0x14019b550  xor     r14d, r14d
0x14019b553  test    dword ptr [rbx+0B0h], 10000000h
0x14019b55d  jnz     loc_14019B756
0x14019b563  lea     rdx, [rsi+0A0h]
0x14019b56a  lea     rcx, [rsi+78h]
0x14019b56e  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14019b575  nop     dword ptr [rax+rax+00h]
0x14019b57a  lea     r8, [rsi+280h]
0x14019b581  mov     r9, [r8+8]
0x14019b585  cmp     [r9], r8
0x14019b588  jz      loc_14019B7FA
0x14019b58e  mov     ecx, 3
0x14019b593  int     29h; Win8: RtlFailFast(ecx)
0x14019b595  lea     rax, [rdi+38h]
0x14019b599  mov     [rax], rcx
0x14019b59c  mov     [rax+8], rdx
0x14019b5a0  mov     [rdx], rax
0x14019b5a3  mov     [rcx+8], rax
0x14019b5a7  mov     [rdi+30h], rbx
0x14019b5ab  lea     rax, [rdi+78h]
0x14019b5af  mov     [rax+8], rax
0x14019b5b3  mov     [rax], rax
0x14019b5b6  cmp     cs:TxfSearchingForSystemRoot, 0
0x14019b5bd  jz      short loc_14019B61F
0x14019b5bf  mov     rax, [rbx+60h]
0x14019b5c3  mov     rcx, [rax+0F8h]
0x14019b5ca  mov     rax, [rcx+10h]
0x14019b5ce  test    dword ptr [rax+30h], 100h
0x14019b5d5  jz      short loc_14019B61F
0x14019b5d7  cmp     qword ptr [rsi+298h], 0
0x14019b5df  jz      short loc_14019B61F
0x14019b5e1  call    cs:__imp_RtlGetNtSystemRoot
0x14019b5e8  nop     dword ptr [rax+rax+00h]
0x14019b5ed  lea     rcx, [rax+4]; Buf1
0x14019b5f1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14019b5f8  nop     dword ptr [rax+rax+00000000h]
0x14019b600  lea     rax, [rax+1]
0x14019b604  cmp     word ptr [rcx+rax*2], 0
0x14019b609  jnz     short loc_14019B600
0x14019b60b  lea     r8, [rax+rax]; Size
0x14019b60f  movzx   eax, word ptr [rsi+290h]
0x14019b616  cmp     rax, r8
0x14019b619  jz      loc_14019B6B7
0x14019b61f  mov     r14d, dword ptr [rsp+88h+arg_28]
0x14019b627  mov     rax, [rsi+0B8h]
0x14019b62e  test    dword ptr [rax+4], 1800000h
0x14019b635  jnz     short loc_14019B655
0x14019b637  mov     rcx, [rbx+68h]
0x14019b63b  add     rcx, 8; FastMutex
0x14019b63f  call    cs:__imp_ExReleaseFastMutex
0x14019b646  nop     dword ptr [rax+rax+00h]
0x14019b64b  test    r14b, r14b
0x14019b64e  jnz     short loc_14019B664
0x14019b650  jmp     loc_14019B997
0x14019b655  mov     eax, [rbx+4]
0x14019b658  bts     eax, 18h
0x14019b65c  mov     [rbx+4], eax
0x14019b65f  mov     eax, [rbx+4]
0x14019b662  jmp     short loc_14019B637
0x14019b664  mov     rax, [rsi+0B8h]
0x14019b66b  mov     rcx, [rax+68h]
0x14019b66f  add     rcx, 8; FastMutex
0x14019b673  call    cs:__imp_ExAcquireFastMutex
0x14019b67a  nop     dword ptr [rax+rax+00h]
0x14019b67f  mov     rcx, [rsi+0B8h]
0x14019b686  mov     eax, [rcx+4]
0x14019b689  bts     eax, 17h
0x14019b68d  mov     [rcx+4], eax
0x14019b690  mov     eax, [rcx+4]
0x14019b693  mov     cs:TxfSearchingForSystemRoot, 0
0x14019b69a  mov     rax, [rsi+0B8h]
0x14019b6a1  mov     rcx, [rax+68h]
0x14019b6a5  add     rcx, 8; FastMutex
0x14019b6a9  call    cs:__imp_ExReleaseFastMutex
0x14019b6b0  nop     dword ptr [rax+rax+00h]
0x14019b6b5  jmp     short loc_14019B650
0x14019b6b7  mov     rdx, [rsi+298h]; Buf2
0x14019b6be  call    memcmp
0x14019b6c3  mov     r14d, dword ptr [rsp+88h+arg_28]
0x14019b6cb  movzx   r14d, r14b
0x14019b6cf  mov     ecx, 1
0x14019b6d4  test    eax, eax
0x14019b6d6  cmovz   r14d, ecx
0x14019b6da  jmp     loc_14019B627
0x14019b6df  lea     rdx, [rdi+90h]
0x14019b6e6  mov     [r8], rdx
0x14019b6e9  jmp     loc_14019B4DE
0x14019b6ee  cmp     cl, 2
0x14019b6f1  jz      loc_14019B96D
0x14019b6f7  cmp     cl, 1
0x14019b6fa  jnz     loc_14019B550
0x14019b700  xor     r14d, r14d
0x14019b703  mov     r9d, r14d
0x14019b706  lea     r8, [rbx+30h]
0x14019b70a  mov     rcx, [r8]
0x14019b70d  cmp     rcx, r8
0x14019b710  jz      short loc_14019B733
0x14019b712  mov     eax, [rcx-34h]
0x14019b715  test    al, 2
0x14019b717  jnz     loc_14019B7E5
0x14019b71d  mov     rax, [rcx+88h]
0x14019b724  cmp     byte ptr [rax+41h], 2
0x14019b728  jz      short loc_14019B72F
0x14019b72a  mov     rcx, [rcx]
0x14019b72d  jmp     short loc_14019B70D
0x14019b72f  lea     r9, [rcx-38h]
0x14019b733  test    r9, r9
0x14019b736  jz      loc_14019B553
0x14019b73c  mov     eax, [r9+24h]
0x14019b740  mov     [rdi+24h], eax
0x14019b743  mov     eax, [r9+28h]
0x14019b747  mov     [rdi+28h], eax
0x14019b74a  mov     eax, [r9+2Ch]
0x14019b74e  mov     [rdi+2Ch], eax
0x14019b751  jmp     loc_14019B553
0x14019b756  mov     r15, r14
0x14019b759  mov     rcx, [rbx+68h]
0x14019b75d  add     rcx, 8; FastMutex
0x14019b761  call    cs:__imp_ExAcquireFastMutex
0x14019b768  nop     dword ptr [rax+rax+00h]
0x14019b76d  lea     r8, [rbx+30h]
0x14019b771  mov     rdx, [r8]
0x14019b774  cmp     rdx, r8
0x14019b777  jz      short loc_14019B796
0x14019b779  mov     rcx, rdx
0x14019b77c  test    r15, r15
0x14019b77f  jnz     loc_14019B8FB
0x14019b785  mov     r15, rcx
0x14019b788  add     r15, 0FFFFFFFFFFFFFFC8h
0x14019b78c  mov     eax, [r15+4]
0x14019b790  test    al, 2
0x14019b792  jnz     short loc_14019B77C
0x14019b794  jmp     short loc_14019B799
0x14019b796  mov     r15, r14
0x14019b799  mov     rcx, [rbx+68h]
0x14019b79d  add     rcx, 8; FastMutex
0x14019b7a1  call    cs:__imp_ExReleaseFastMutex
0x14019b7a8  nop     dword ptr [rax+rax+00h]
0x14019b7ad  test    r15, r15
0x14019b7b0  jnz     short loc_14019B7ED
0x14019b7b2  mov     [rsp+88h+var_58], r14
0x14019b7b7  mov     [rsp+88h+var_60], r14
0x14019b7bc  mov     byte ptr [rsp+88h+var_68], 1
0x14019b7c1  lea     r9, NtfsFileNameIndex
0x14019b7c8  mov     r8d, 0A0h
0x14019b7ce  mov     rdx, rbx
0x14019b7d1  mov     rcx, r13
0x14019b7d4  call    NtfsCreateScb
0x14019b7d9  mov     [rdi+88h], rax
0x14019b7e0  jmp     loc_14019B563
0x14019b7e5  mov     rcx, [rcx]
0x14019b7e8  jmp     loc_14019B70D
0x14019b7ed  mov     eax, [r15+4]
0x14019b7f1  test    al, 2
0x14019b7f3  jz      short loc_14019B851
0x14019b7f5  jmp     loc_14019B759
0x14019b7fa  lea     rax, [rdi+8]
0x14019b7fe  mov     [rax], r8
0x14019b801  mov     [rax+8], r9
0x14019b805  mov     [r9], rax
0x14019b808  mov     [r8+8], rax
0x14019b80c  mov     [rdi+18h], rsi
0x14019b810  lea     rdx, [rsi+0A0h]
0x14019b817  lea     rcx, [rsi+78h]
0x14019b81b  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14019b822  nop     dword ptr [rax+rax+00h]
0x14019b827  mov     rcx, [rbx+68h]
0x14019b82b  add     rcx, 8; FastMutex
0x14019b82f  call    cs:__imp_ExAcquireFastMutex
0x14019b836  nop     dword ptr [rax+rax+00h]
0x14019b83b  lea     rcx, [rbx+30h]
0x14019b83f  mov     rdx, [rcx+8]
0x14019b843  cmp     [rdx], rcx
0x14019b846  jnz     loc_14019B58E
0x14019b84c  jmp     loc_14019B595
0x14019b851  mov     rax, [rdi+0C0h]
0x14019b858  movzx   edx, byte ptr [rax+41h]
0x14019b85c  and     dl, 3
0x14019b85f  cmp     dl, 2
0x14019b862  jnz     short loc_14019B877
0x14019b864  mov     rax, [r15+0C0h]
0x14019b86b  movzx   ecx, byte ptr [rax+41h]
0x14019b86f  and     cl, 3
0x14019b872  cmp     cl, 1
0x14019b875  jz      short loc_14019B88F
0x14019b877  cmp     dl, 1
0x14019b87a  jnz     short loc_14019B899
0x14019b87c  mov     rax, [r15+0C0h]
0x14019b883  movzx   ecx, byte ptr [rax+41h]
  ... truncated ...
```
