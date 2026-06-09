# VsmmVaGpaRangepBackgroundDecommitCandidateRanges

- ea: `0x1400f0a40`
- end: `0x1400f0faa`
- name: `VsmmVaGpaRangepBackgroundDecommitCandidateRanges`
- size: `1386`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400f0910`

## callees

- `0x140007df0`
- `0x14001b440`
- `0x140021c60`
- `0x1400234f0`
- `0x1400356e0`
- `0x140037680`
- `0x1400f0a40`
- `0x1400f39c0`
- `0x1400f51b8`
- `0x1400f6378`

## import_xrefs

- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400f0e8b`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400f0e8b`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f0ebf`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400f0ebf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f0e97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f0e97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f0ede`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f0ede`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400f0ed2`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400f0ed2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400f0eaa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400f0eaa`
- `ntoskrnl!KeSetEvent` at `0x1400f0f14`
- `ntoskrnl!KeSetEvent` at `0x1400f0f14`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f0c7f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f0c7f`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400f0e21`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400f0e49`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400f0e21`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400f0e49`
- `ntoskrnl!RtlExtractBitMapEx` at `0x1400f0c4c`
- `ntoskrnl!RtlExtractBitMapEx` at `0x1400f0c4c`
- `ntoskrnl!RtlSetBitsEx` at `0x1400f0c06`
- `ntoskrnl!RtlSetBitsEx` at `0x1400f0c06`
- `ntoskrnl!RtlClearBitEx` at `0x1400f0d89`
- `ntoskrnl!RtlClearBitEx` at `0x1400f0d89`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400f0d1c`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400f0d1c`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400f0eee`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400f0eee`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400f0acf`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400f0c23`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400f0acf`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400f0c23`
- `ntoskrnl!RtlClearAllBitsEx` at `0x1400f0c5f`
- `ntoskrnl!RtlClearAllBitsEx` at `0x1400f0c5f`
- `ntoskrnl!RtlClearBitsEx` at `0x1400f0e62`
- `ntoskrnl!RtlClearBitsEx` at `0x1400f0e62`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0b1d`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0cbd`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0ddd`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0b1d`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0cbd`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400f0ddd`

## pseudocode

```c
int __fastcall VsmmVaGpaRangepBackgroundDecommitCandidateRanges(_QWORD *a1)
{
  unsigned __int64 v1; // r12
  __int64 v2; // r14
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // rdi
  unsigned __int64 NextForwardRunSet; // rax
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r15
  __int64 v9; // rsi
  unsigned __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  unsigned __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // r15
  unsigned __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rbx
  _QWORD *v25; // rbx
  _QWORD *v26; // rcx
  signed __int32 v28[8]; // [rsp+0h] [rbp-100h] BYREF
  unsigned __int64 v29; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v30; // [rsp+28h] [rbp-D8h]
  __int128 v31; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v35; // [rsp+58h] [rbp-A8h]
  _QWORD *v36; // [rsp+60h] [rbp-A0h]
  _QWORD *v37; // [rsp+68h] [rbp-98h]
  unsigned __int64 v38; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+78h] [rbp-88h] BYREF
  _SLIST_HEADER v40[3]; // [rsp+90h] [rbp-70h] BYREF
  _SLIST_HEADER ListHead; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h]
  char v43[64]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = a1[49];
  v2 = a1[48];
  v3 = a1;
  v32 = a1;
  v4 = a1[34];
  v39 = 0;
  v5 = v4 - v3[32] + v1 + 1;
  v29 = 0;
  v31 = 0;
  memset(v40, 0, sizeof(v40));
  v38 = v5;
  ListHead = 0;
  v42 = 0;
  RtlInitializeBitMapEx(&v39, *(_QWORD *)(v2 + 552), v5);
  NextForwardRunSet = v3[30];
  v33 = NextForwardRunSet;
  if ( v1 < v5 )
  {
    while ( 1 )
    {
      NextForwardRunSet = RtlFindNextForwardRunSetEx(&v39, v1, &v29);
      if ( !NextForwardRunSet )
        return NextForwardRunSet;
      v1 = v29;
      if ( NextForwardRunSet <= 0x200 )
        NextForwardRunSet = 512;
      v7 = v5 - v29;
      if ( NextForwardRunSet < v5 - v29 )
        v7 = NextForwardRunSet;
      v8 = v29 + v7;
      v35 = v8;
      if ( v29 < v8 )
        break;
LABEL_56:
      if ( v1 >= v5 )
        return NextForwardRunSet;
    }
    v36 = v3 + 67;
    v9 = v2 + 1000;
    v37 = v3 + 65;
    while ( 1 )
    {
      v10 = v8 - v1;
      v30 = v8 - v1;
      if ( (v1 & 0x1FF) != 0 )
      {
        if ( v10 > 0x200 )
        {
          v10 = ((v1 + 511) & 0xFFFFFFFFFFFFFE00uLL) - v1;
LABEL_14:
          v30 = v10;
        }
      }
      else if ( v10 > 0x200 )
      {
        v10 = 512;
        goto LABEL_14;
      }
      v11 = VsmmNtSlatAbPreAcquire(v9, 0);
      v34 = v11;
      v12 = v11;
      if ( v11 )
        VsmmNtSlatAbPostAcquire(v11);
      VsmmVaGpaRangeBeginHoldingNtVmRange(v40, v3, v1 + v3[32] - v3[49], v10);
      RtlSetBitsEx(v2 + 560, v1);
      _InterlockedOr(v28, 0);
      RtlInitializeBitMapEx(&v31, v43, v10);
      v13 = v33;
      if ( (*(_BYTE *)(v33 + 24) & 0x10) != 0 )
        RtlExtractBitMapEx(v2 + 576, &v31, v1, v10);
      else
        RtlClearAllBitsEx(&v31);
      if ( (*(_BYTE *)(v13 + 24) & 8) != 0 )
      {
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
        VsmmQueryKnownZeroVaPages(CurrentProcess);
      }
      v15 = 0;
      if ( v10 )
      {
        do
        {
          v16 = RtlFindNextForwardRunSetEx(&v31, v15, &v29);
          v17 = v16;
          if ( !v16 )
            break;
          v15 = v29;
          if ( v29 < v16 + v29 )
          {
            do
            {
              v18 = v1 + v15;
              if ( *(_DWORD *)(v2 + 268) != 2
                && *(_QWORD *)(v2 + 288)
                && !(unsigned __int8)RtlTestBitNoFenceEx(v2 + 272, v18 >> 9) )
              {
                VsmmMbpUpgradeChunk(v2, v18 >> 9);
              }
              v19 = *(_QWORD *)(v2 + 256);
              if ( (*(_DWORD *)(v2 + 264) & 8) != 0 )
                v20 = (__int64 *)(v19 + 8 * v18);
              else
                v20 = (__int64 *)(16 * v18 + v19 + 8);
              v21 = *v20;
              if ( (v21 & 0xFFFE00000000LL) != 0 || (v21 & 0x1FFFFE000LL) != 0 || (v21 & 0x3FF000000000000LL) != 0 )
                RtlClearBitEx(&v31, v15);
              ++v15;
            }
            while ( v15 < v17 + v29 );
            v10 = v30;
          }
        }
        while ( v15 < v10 );
        v12 = v34;
        v8 = v35;
      }
      v22 = 0;
      if ( v10 )
      {
        do
        {
          v23 = RtlFindNextForwardRunSetEx(&v31, v22, &v29);
          v24 = v23;
          if ( !v23 )
            break;
          VsmmMemoryBlockDecommitPrimaryRamRange(v2, v1 + v29, v23, 0);
          v22 = v24 + v29;
        }
        while ( v24 + v29 < v10 );
      }
      RtlInterlockedClearBitRunEx(v2 + 544, v1, v10);
      if ( (*(_BYTE *)(*(_QWORD *)(v2 + 8) + 24LL) & 0x10) != 0 )
      {
        _InterlockedOr(v28, 0);
        RtlInterlockedClearBitRunEx(v2 + 576, v1, v10);
      }
      RtlClearBitsEx(v2 + 560, v1, v10);
      v9 = v2 + 1000;
      ++*(_QWORD *)(v2 + 992);
      ExUnblockOnAddressPushLockEx(v2 + 1000, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v36, 0);
      RtlRbRemoveNode(v37, v40);
      ExReleasePushLockEx(v36, 0);
      KeLeaveCriticalRegion();
      NextForwardRunSet = (unsigned __int64)ExpInterlockedFlushSList(&ListHead);
      v25 = (_QWORD *)NextForwardRunSet;
      while ( v25 )
      {
        v26 = v25;
        v25 = (_QWORD *)*v25;
        LODWORD(NextForwardRunSet) = KeSetEvent((PRKEVENT)(v26 + 2), 0, 0);
      }
      if ( (_QWORD)v42 )
      {
        if ( *((_QWORD *)&v42 + 1) )
          ((void (*)(void))VsmmNtSlatAbPostReleaseEx)();
        LODWORD(NextForwardRunSet) = VsmmAutoBoostLockDereference();
      }
      if ( v12 )
        LODWORD(NextForwardRunSet) = VsmmNtSlatAbPostReleaseEx(v2 + 1000, v12);
      v3 = v32;
      v1 += v10;
      if ( v1 >= v8 )
      {
        v5 = v38;
        goto LABEL_56;
      }
    }
  }
  return NextForwardRunSet;
}

```

## disassembly

```asm
0x1400f0a40  push    rbp
0x1400f0a42  push    rbx
0x1400f0a43  push    rdi
0x1400f0a44  push    r12
0x1400f0a46  push    r14
0x1400f0a48  lea     rbp, [rsp-30h]
0x1400f0a4d  sub     rsp, 130h
0x1400f0a54  mov     rax, cs:__security_cookie
0x1400f0a5b  xor     rax, rsp
0x1400f0a5e  mov     [rbp+50h+var_30], rax
0x1400f0a62  mov     r12, [rcx+188h]
0x1400f0a69  xorps   xmm0, xmm0
0x1400f0a6c  mov     r14, [rcx+180h]
0x1400f0a73  mov     rbx, rcx
0x1400f0a76  mov     [rsp+150h+var_110], rcx
0x1400f0a7b  xorps   xmm1, xmm1
0x1400f0a7e  mov     rcx, [rcx+110h]
0x1400f0a85  movups  [rsp+150h+var_D8], xmm0
0x1400f0a8a  sub     rcx, [rbx+100h]
0x1400f0a91  lea     rdi, [r12+1]
0x1400f0a96  add     rdi, rcx
0x1400f0a99  mov     [rsp+150h+var_130], 0
0x1400f0aa2  movups  [rsp+150h+var_120], xmm1
0x1400f0aa7  mov     r8, rdi
0x1400f0aaa  lea     rcx, [rsp+150h+var_D8]
0x1400f0aaf  movups  [rbp+50h+var_C0], xmm0
0x1400f0ab3  mov     [rsp+150h+var_E0], rdi
0x1400f0ab8  movups  [rbp+50h+var_B0], xmm0
0x1400f0abc  movups  [rbp+50h+var_A0], xmm0
0x1400f0ac0  movups  xmmword ptr [rbp+50h+ListHead], xmm0
0x1400f0ac4  movups  [rbp+50h+var_80], xmm0
0x1400f0ac8  mov     rdx, [r14+228h]
0x1400f0acf  call    cs:__imp_RtlInitializeBitMapEx
0x1400f0ad6  nop     dword ptr [rax+rax+00h]
0x1400f0adb  mov     rax, [rbx+0F0h]
0x1400f0ae2  mov     [rsp+150h+var_108], rax
0x1400f0ae7  cmp     r12, rdi
0x1400f0aea  jnb     loc_1400F0F8E
0x1400f0af0  mov     [rsp+150h+arg_8], rsi
0x1400f0af8  mov     [rsp+150h+arg_10], r13
0x1400f0b00  mov     [rsp+150h+arg_18], r15
0x1400f0b08  nop     dword ptr [rax+rax+00000000h]
0x1400f0b10  lea     r8, [rsp+150h+var_130]
0x1400f0b15  mov     rdx, r12
0x1400f0b18  lea     rcx, [rsp+150h+var_D8]
0x1400f0b1d  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400f0b24  nop     dword ptr [rax+rax+00h]
0x1400f0b29  test    rax, rax
0x1400f0b2c  jz      loc_1400F0F76
0x1400f0b32  mov     r12, [rsp+150h+var_130]
0x1400f0b37  mov     ecx, 200h
0x1400f0b3c  cmp     rax, rcx
0x1400f0b3f  mov     r15, rdi
0x1400f0b42  cmovbe  rax, rcx
0x1400f0b46  sub     r15, r12
0x1400f0b49  cmp     rax, r15
0x1400f0b4c  cmovb   r15, rax
0x1400f0b50  add     r15, r12
0x1400f0b53  mov     [rsp+150h+var_F8], r15
0x1400f0b58  cmp     r12, r15
0x1400f0b5b  jnb     loc_1400F0F6D
0x1400f0b61  lea     rax, [rbx+218h]
0x1400f0b68  mov     [rsp+150h+var_F0], rax
0x1400f0b6d  lea     rsi, [r14+3E8h]
0x1400f0b74  lea     rax, [rbx+208h]
0x1400f0b7b  mov     [rsp+150h+var_E8], rax
0x1400f0b80  mov     r13, r15
0x1400f0b83  sub     r13, r12
0x1400f0b86  mov     [rsp+150h+var_128], r13
0x1400f0b8b  test    r12, 1FFh
0x1400f0b92  jz      short loc_1400F0BAD
0x1400f0b94  cmp     r13, rcx
0x1400f0b97  jbe     short loc_1400F0BBA
0x1400f0b99  lea     r13, [r12+1FFh]
0x1400f0ba1  and     r13, 0FFFFFFFFFFFFFE00h
0x1400f0ba8  sub     r13, r12
0x1400f0bab  jmp     short loc_1400F0BB5
0x1400f0bad  cmp     r13, rcx
0x1400f0bb0  jbe     short loc_1400F0BBA
0x1400f0bb2  mov     r13, rcx
0x1400f0bb5  mov     [rsp+150h+var_128], r13
0x1400f0bba  xor     edx, edx
0x1400f0bbc  mov     rcx, rsi
0x1400f0bbf  call    VsmmNtSlatAbPreAcquire
0x1400f0bc4  mov     [rsp+150h+var_100], rax
0x1400f0bc9  mov     rdi, rax
0x1400f0bcc  test    rax, rax
0x1400f0bcf  jz      short loc_1400F0BD9
0x1400f0bd1  mov     rcx, rax
0x1400f0bd4  call    VsmmNtSlatAbPostAcquire
0x1400f0bd9  mov     r8, [rbx+100h]
0x1400f0be0  lea     rcx, [rbp+50h+var_C0]
0x1400f0be4  sub     r8, [rbx+188h]
0x1400f0beb  mov     r9, r13
0x1400f0bee  add     r8, r12
0x1400f0bf1  mov     rdx, rbx
0x1400f0bf4  call    VsmmVaGpaRangeBeginHoldingNtVmRange
0x1400f0bf9  mov     r8, r13
0x1400f0bfc  lea     rcx, [r14+230h]
0x1400f0c03  mov     rdx, r12
0x1400f0c06  call    cs:__imp_RtlSetBitsEx
0x1400f0c0d  nop     dword ptr [rax+rax+00h]
0x1400f0c12  lock or [rsp+150h+var_150], 0
0x1400f0c17  mov     r8, r13
0x1400f0c1a  lea     rdx, [rbp+50h+var_70]
0x1400f0c1e  lea     rcx, [rsp+150h+var_120]
0x1400f0c23  call    cs:__imp_RtlInitializeBitMapEx
0x1400f0c2a  nop     dword ptr [rax+rax+00h]
0x1400f0c2f  mov     rbx, [rsp+150h+var_108]
0x1400f0c34  test    byte ptr [rbx+18h], 10h
0x1400f0c38  jz      short loc_1400F0C5A
0x1400f0c3a  lea     rcx, [r14+240h]
0x1400f0c41  mov     r9, r13
0x1400f0c44  mov     r8, r12
0x1400f0c47  lea     rdx, [rsp+150h+var_120]
0x1400f0c4c  call    cs:__imp_RtlExtractBitMapEx
0x1400f0c53  nop     dword ptr [rax+rax+00h]
0x1400f0c58  jmp     short loc_1400F0C6B
0x1400f0c5a  lea     rcx, [rsp+150h+var_120]
0x1400f0c5f  call    cs:__imp_RtlClearAllBitsEx
0x1400f0c66  nop     dword ptr [rax+rax+00h]
0x1400f0c6b  test    byte ptr [rbx+18h], 8
0x1400f0c6f  jz      short loc_1400F0C9E
0x1400f0c71  mov     rbx, r12
0x1400f0c74  shl     rbx, 0Ch
0x1400f0c78  add     rbx, [r14+3B8h]
0x1400f0c7f  call    cs:__imp_PsGetCurrentProcess
0x1400f0c86  nop     dword ptr [rax+rax+00h]
0x1400f0c8b  lea     r9, [rsp+150h+var_120]
0x1400f0c90  mov     r8, r13
0x1400f0c93  mov     rcx, rax; PROCESS
0x1400f0c96  mov     rdx, rbx
0x1400f0c99  call    VsmmQueryKnownZeroVaPages
0x1400f0c9e  xor     esi, esi
0x1400f0ca0  test    r13, r13
0x1400f0ca3  jz      loc_1400F0DC1
0x1400f0ca9  nop     dword ptr [rax+00000000h]
0x1400f0cb0  lea     r8, [rsp+150h+var_130]
0x1400f0cb5  mov     rdx, rsi
0x1400f0cb8  lea     rcx, [rsp+150h+var_120]
0x1400f0cbd  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400f0cc4  nop     dword ptr [rax+rax+00h]
0x1400f0cc9  mov     r15, rax
0x1400f0ccc  test    rax, rax
0x1400f0ccf  jz      loc_1400F0DB7
0x1400f0cd5  mov     rsi, [rsp+150h+var_130]
0x1400f0cda  lea     rcx, [rax+rsi]
0x1400f0cde  cmp     rsi, rcx
0x1400f0ce1  jnb     loc_1400F0DAE
0x1400f0ce7  mov     r13, 1FFFFE000h
0x1400f0cf1  cmp     dword ptr [r14+10Ch], 2
0x1400f0cf9  lea     rbx, [r12+rsi]
0x1400f0cfd  jz      short loc_1400F0D38
0x1400f0cff  mov     rax, [r14+120h]
0x1400f0d06  test    rax, rax
0x1400f0d09  jz      short loc_1400F0D37
0x1400f0d0b  mov     rdi, rbx
0x1400f0d0e  lea     rcx, [r14+110h]
0x1400f0d15  shr     rdi, 9
0x1400f0d19  mov     rdx, rdi
0x1400f0d1c  call    cs:__imp_RtlTestBitNoFenceEx
0x1400f0d23  nop     dword ptr [rax+rax+00h]
0x1400f0d28  test    al, al
0x1400f0d2a  jnz     short loc_1400F0D37
0x1400f0d2c  mov     rdx, rdi
0x1400f0d2f  mov     rcx, r14
0x1400f0d32  call    VsmmMbpUpgradeChunk
0x1400f0d37  nop
0x1400f0d38  mov     eax, [r14+108h]
0x1400f0d3f  mov     rcx, [r14+100h]
0x1400f0d46  test    al, 8
0x1400f0d48  jnz     short loc_1400F0D57
0x1400f0d4a  shl     rbx, 4
0x1400f0d4e  lea     rax, [rcx+8]
0x1400f0d52  add     rax, rbx
0x1400f0d55  jmp     short loc_1400F0D5B
0x1400f0d57  lea     rax, [rcx+rbx*8]
0x1400f0d5b  mov     rax, [rax]
0x1400f0d5e  mov     rcx, 0FFFE00000000h
0x1400f0d68  test    rcx, rax
0x1400f0d6b  jnz     short loc_1400F0D81
0x1400f0d6d  test    r13, rax
0x1400f0d70  jnz     short loc_1400F0D81
0x1400f0d72  mov     rcx, 3FF000000000000h
0x1400f0d7c  test    rcx, rax
0x1400f0d7f  jz      short loc_1400F0D95
0x1400f0d81  mov     rdx, rsi
0x1400f0d84  lea     rcx, [rsp+150h+var_120]
0x1400f0d89  call    cs:__imp_RtlClearBitEx
0x1400f0d90  nop     dword ptr [rax+rax+00h]
0x1400f0d95  mov     rcx, [rsp+150h+var_130]
0x1400f0d9a  inc     rsi
0x1400f0d9d  add     rcx, r15
0x1400f0da0  cmp     rsi, rcx
0x1400f0da3  jb      loc_1400F0CF1
0x1400f0da9  mov     r13, [rsp+150h+var_128]
0x1400f0dae  cmp     rsi, r13
0x1400f0db1  jb      loc_1400F0CB0
0x1400f0db7  mov     rdi, [rsp+150h+var_100]
0x1400f0dbc  mov     r15, [rsp+150h+var_F8]
0x1400f0dc1  xor     eax, eax
0x1400f0dc3  test    r13, r13
0x1400f0dc6  jz      short loc_1400F0E14
0x1400f0dc8  nop     dword ptr [rax+rax+00000000h]
0x1400f0dd0  lea     r8, [rsp+150h+var_130]
0x1400f0dd5  mov     rdx, rax
0x1400f0dd8  lea     rcx, [rsp+150h+var_120]
0x1400f0ddd  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400f0de4  nop     dword ptr [rax+rax+00h]
0x1400f0de9  mov     rbx, rax
0x1400f0dec  test    rax, rax
0x1400f0def  jz      short loc_1400F0E14
0x1400f0df1  mov     rdx, [rsp+150h+var_130]
0x1400f0df6  xor     r9d, r9d
0x1400f0df9  add     rdx, r12
0x1400f0dfc  mov     r8, rax
0x1400f0dff  mov     rcx, r14
0x1400f0e02  call    VsmmMemoryBlockDecommitPrimaryRamRange
0x1400f0e07  mov     rax, [rsp+150h+var_130]
0x1400f0e0c  add     rax, rbx
0x1400f0e0f  cmp     rax, r13
0x1400f0e12  jb      short loc_1400F0DD0
0x1400f0e14  mov     r8, r13
0x1400f0e17  lea     rcx, [r14+220h]
0x1400f0e1e  mov     rdx, r12
0x1400f0e21  call    cs:__imp_RtlInterlockedClearBitRunEx
0x1400f0e28  nop     dword ptr [rax+rax+00h]
0x1400f0e2d  mov     rax, [r14+8]
0x1400f0e31  test    byte ptr [rax+18h], 10h
0x1400f0e35  jz      short loc_1400F0E55
0x1400f0e37  lock or [rsp+150h+var_150], 0
0x1400f0e3c  lea     rcx, [r14+240h]
0x1400f0e43  mov     r8, r13
0x1400f0e46  mov     rdx, r12
0x1400f0e49  call    cs:__imp_RtlInterlockedClearBitRunEx
0x1400f0e50  nop     dword ptr [rax+rax+00h]
0x1400f0e55  mov     r8, r13
0x1400f0e58  lea     rcx, [r14+230h]
0x1400f0e5f  mov     rdx, r12
0x1400f0e62  call    cs:__imp_RtlClearBitsEx
0x1400f0e69  nop     dword ptr [rax+rax+00h]
0x1400f0e6e  mov     rax, [r14+3E0h]
0x1400f0e75  lea     rsi, [r14+3E8h]
0x1400f0e7c  inc     rax
0x1400f0e7f  xor     edx, edx
0x1400f0e81  mov     rcx, rsi
0x1400f0e84  mov     [r14+3E0h], rax
0x1400f0e8b  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400f0e92  nop     dword ptr [rax+rax+00h]
0x1400f0e97  call    cs:__imp_KeEnterCriticalRegion
0x1400f0e9e  nop     dword ptr [rax+rax+00h]
0x1400f0ea3  mov     rcx, [rsp+150h+var_F0]
0x1400f0ea8  xor     edx, edx
0x1400f0eaa  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400f0eb1  nop     dword ptr [rax+rax+00h]
0x1400f0eb6  mov     rcx, [rsp+150h+var_E8]
0x1400f0ebb  lea     rdx, [rbp+50h+var_C0]
0x1400f0ebf  call    cs:__imp_RtlRbRemoveNode
0x1400f0ec6  nop     dword ptr [rax+rax+00h]
0x1400f0ecb  mov     rcx, [rsp+150h+var_F0]
0x1400f0ed0  xor     edx, edx
0x1400f0ed2  call    cs:__imp_ExReleasePushLockEx
0x1400f0ed9  nop     dword ptr [rax+rax+00h]
0x1400f0ede  call    cs:__imp_KeLeaveCriticalRegion
0x1400f0ee5  nop     dword ptr [rax+rax+00h]
0x1400f0eea  lea     rcx, [rbp+50h+ListHead]; ListHead
0x1400f0eee  call    cs:__imp_ExpInterlockedFlushSList
0x1400f0ef5  nop     dword ptr [rax+rax+00h]
0x1400f0efa  mov     rbx, rax
0x1400f0efd  nop     dword ptr [rax]
0x1400f0f00  test    rbx, rbx
0x1400f0f03  jz      short loc_1400F0F22
0x1400f0f05  mov     rcx, rbx
0x1400f0f08  xor     r8d, r8d; Wait
0x1400f0f0b  mov     rbx, [rbx]
0x1400f0f0e  add     rcx, 10h; Event
0x1400f0f12  xor     edx, edx; Increment
0x1400f0f14  call    cs:__imp_KeSetEvent
0x1400f0f1b  nop     dword ptr [rax+rax+00h]
0x1400f0f20  jmp     short loc_1400F0F00
0x1400f0f22  mov     rcx, qword ptr [rbp+50h+var_80]
0x1400f0f26  test    rcx, rcx
0x1400f0f29  jz      short loc_1400F0F42
0x1400f0f2b  mov     rdx, qword ptr [rbp+50h+var_80+8]
0x1400f0f2f  test    rdx, rdx
0x1400f0f32  jz      short loc_1400F0F3D
0x1400f0f34  call    VsmmNtSlatAbPostReleaseEx
0x1400f0f39  mov     rcx, qword ptr [rbp+50h+var_80]
0x1400f0f3d  call    VsmmAutoBoostLockDereference
0x1400f0f42  test    rdi, rdi
0x1400f0f45  jz      short loc_1400F0F52
0x1400f0f47  mov     rdx, rdi
0x1400f0f4a  mov     rcx, rsi
0x1400f0f4d  call    VsmmNtSlatAbPostReleaseEx
0x1400f0f52  mov     rbx, [rsp+150h+var_110]
0x1400f0f57  add     r12, r13
0x1400f0f5a  mov     ecx, 200h
0x1400f0f5f  cmp     r12, r15
0x1400f0f62  jb      loc_1400F0B80
0x1400f0f68  mov     rdi, [rsp+150h+var_E0]
  ... truncated ...
```
