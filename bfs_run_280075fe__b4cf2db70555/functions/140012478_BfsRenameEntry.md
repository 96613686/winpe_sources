# BfsRenameEntry

- ea: `0x140012478`
- end: `0x140012aa9`
- name: `BfsRenameEntry`
- size: `1585`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000a7a0`

## callees

- `0x140006b90`
- `0x14001079c`
- `0x14001126c`
- `0x1400116a0`
- `0x140011894`
- `0x14001198c`
- `0x140011a38`
- `0x140011d18`
- `0x140012478`
- `0x140012ab0`
- `0x140013730`
- `0x140013840`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001266e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001273a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400128c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400129c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012a39`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001266e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001273a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400128c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400129c7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012a39`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400126ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001286f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012a0c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012a5b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400126ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001286f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012a0c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012a5b`
- `ntoskrnl!RtlSetBits` at `0x140012976`
- `ntoskrnl!RtlSetBits` at `0x140012976`
- `ntoskrnl!RtlClearBits` at `0x14001284e`
- `ntoskrnl!RtlClearBits` at `0x14001284e`
- `ntoskrnl!RtlInitializeBitMap` at `0x140012833`
- `ntoskrnl!RtlInitializeBitMap` at `0x140012833`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001265d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012729`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400128b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400129b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012a28`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001265d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012729`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400128b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400129b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012a28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400126fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001287b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a18`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400126fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001287b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a18`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a67`

## pseudocode

```c
__int64 __fastcall BfsRenameEntry(__int64 a1, __int64 a2, struct _RTL_BITMAP *a3, struct _RTL_BITMAP *a4)
{
  __int64 result; // rax
  struct _RTL_BITMAP v9; // xmm2
  volatile signed __int32 *v10; // rdi
  NTSTATUS EntryBlock; // ebx
  volatile signed __int32 *v12; // rcx
  struct _RTL_BITMAP v13; // xmm2
  volatile signed __int32 *v14; // rbx
  int v15; // esi
  volatile signed __int32 *v16; // rsi
  __int64 Entry; // rax
  __int64 v18; // r14
  _OWORD *v19; // rax
  void *v20; // rbx
  __int64 v21; // r12
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  int v32; // eax
  NTSTATUS v33; // eax
  ULONG *v34; // r14
  __int64 inserted; // rbx
  __int64 v36; // rdx
  _OWORD *v37; // rax
  ULONG *v38; // rcx
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  ULONG v47; // eax
  ULONG *v48; // rbx
  volatile signed __int32 *v49; // [rsp+30h] [rbp-D0h] BYREF
  ULONG StartingIndex[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+58h] [rbp-A8h] BYREF
  void *v53[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  __int128 v55; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v56[5]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v57[524]; // [rsp+B4h] [rbp-4Ch] BYREF

  v49 = 0;
  *(_QWORD *)StartingIndex = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  v55 = 0;
  result = BfsCreateDirectory(a1 + 48, a2, 1, StartingIndex);
  if ( (int)result < 0 )
    return result;
  v10 = *(volatile signed __int32 **)StartingIndex;
  BitMapHeader = *a3;
  v9 = BitMapHeader;
  *(_OWORD *)v53 = *(_OWORD *)BfsGetFinalPathComponent(Src, a3);
  if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)v9) >= 2u )
  {
    while ( 1 )
    {
      BitMapHeader = *(struct _RTL_BITMAP *)BfsGetPathComponent(Src, &BitMapHeader, &v54);
      if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)BitMapHeader) < 2u )
        break;
      EntryBlock = BfsCreateDirectory(v10, &v54, 1, StartingIndex);
      BfsDereferenceTableEntry(v10 - 2);
      if ( EntryBlock < 0 )
        return (unsigned int)EntryBlock;
      v10 = *(volatile signed __int32 **)StartingIndex;
    }
  }
  EntryBlock = BfsCreateDirectory(a1 + 48, a2, 1, &v49);
  if ( EntryBlock < 0 )
    goto LABEL_7;
  BitMapHeader = *a4;
  v13 = BitMapHeader;
  *(_OWORD *)Src = *(_OWORD *)BfsGetFinalPathComponent(Src, a4);
  if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)v13) >= 2u )
  {
    while ( 1 )
    {
      BitMapHeader = *(struct _RTL_BITMAP *)BfsGetPathComponent(StartingIndex, &BitMapHeader, &v55);
      if ( (unsigned __int16)_mm_cvtsi128_si32((__m128i)BitMapHeader) < 2u )
        break;
      v14 = v49;
      v15 = BfsCreateDirectory(v49, &v55, 1, &v49);
      if ( v14 != v10 )
        BfsDereferenceTableEntry(v14 - 2);
      if ( v15 < 0 )
      {
        BfsDereferenceTableEntry(v10 - 2);
        return (unsigned int)v15;
      }
    }
  }
  v16 = v49;
  if ( v10 == v49 )
  {
    LODWORD(v49) = 0;
    *(_QWORD *)StartingIndex = 0;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v10, 0);
    Entry = BfsFindEntry(v10, v53);
    v18 = Entry;
    if ( Entry )
    {
      memset((void *)(Entry + 20), 0, 0x200u);
      memmove((void *)(v18 + 20), Src[1], LOWORD(Src[0]));
      EntryBlock = BfsGetEntryBlock(v10, v18, StartingIndex, &v49);
      if ( EntryBlock >= 0 )
        EntryBlock = BfsWriteBlock(a1, (int)v49, *(void **)StartingIndex);
    }
    else
    {
      EntryBlock = -1073741275;
    }
    ExReleasePushLockExclusiveEx(v10, 0);
    KeLeaveCriticalRegion();
    BfsDereferenceTableEntry(v16 - 2);
LABEL_7:
    v12 = v10 - 2;
    goto LABEL_37;
  }
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  LODWORD(v49) = 0;
  *(_QWORD *)StartingIndex = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v10, 0);
  v19 = (_OWORD *)BfsFindEntry(v10, v53);
  v20 = v19;
  if ( v19 )
  {
    v21 = 4;
    v22 = v56;
    v23 = 4;
    do
    {
      v24 = v19[1];
      *v22 = *v19;
      v25 = v19[2];
      v22[1] = v24;
      v26 = v19[3];
      v22[2] = v25;
      v27 = v19[4];
      v22[3] = v26;
      v28 = v19[5];
      v22[4] = v27;
      v29 = v19[6];
      v22[5] = v28;
      v30 = v19[7];
      v19 += 8;
      v22[6] = v29;
      v22[7] = v30;
      v22 += 8;
      --v23;
    }
    while ( v23 );
    v31 = *v19;
    v32 = *((_DWORD *)v19 + 4);
    *v22 = v31;
    *((_DWORD *)v22 + 4) = v32;
    memset(v57, 0, 0x200u);
    memmove(v57, Src[1], LOWORD(Src[0]));
    v33 = BfsGetEntryBlock(v10, v20, StartingIndex, &v49);
    if ( v33 >= 0 )
    {
      v34 = *(ULONG **)StartingIndex;
      StartingIndex[0] = BfsGetEntryIndex(*(_QWORD *)StartingIndex, v20);
      RtlInitializeBitMap(&BitMapHeader, v34 + 3992, 0x1Eu);
      RtlClearBits(&BitMapHeader, StartingIndex[0], 1u);
      memset(v20, 0, 0x214u);
      ExReleasePushLockExclusiveEx(v10, 0);
      KeLeaveCriticalRegion();
      inserted = BfsInsertDirectoryEntry((_DWORD)v16, v56[0], v56[1], v56[2], (__int64)Src);
      if ( !inserted )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v10, 0);
        v36 = 133LL * StartingIndex[0];
        v37 = v56;
        v38 = &v34[v36 + 2];
        do
        {
          v39 = v37[1];
          *(_OWORD *)v38 = *v37;
          v40 = v37[2];
          *((_OWORD *)v38 + 1) = v39;
          v41 = v37[3];
          *((_OWORD *)v38 + 2) = v40;
          v42 = v37[4];
          *((_OWORD *)v38 + 3) = v41;
          v43 = v37[5];
          *((_OWORD *)v38 + 4) = v42;
          v44 = v37[6];
          *((_OWORD *)v38 + 5) = v43;
          v45 = v37[7];
          v37 += 8;
          *((_OWORD *)v38 + 6) = v44;
          *((_OWORD *)v38 + 7) = v45;
          v38 += 32;
          --v21;
        }
        while ( v21 );
        v46 = *v37;
        v47 = *((_DWORD *)v37 + 4);
        v48 = &v34[v36];
        *(_OWORD *)v38 = v46;
        v38[4] = v47;
        memset(&v34[v36 + 7], 0, 0x200u);
        memmove(v48 + 7, v53[1], LOWORD(v53[0]));
        RtlSetBits(&BitMapHeader, StartingIndex[0], 1u);
        BfsWriteBlock(a1, (int)v49, v34);
        EntryBlock = -1073741801;
        goto LABEL_35;
      }
      if ( v56[0] == 2 )
      {
        StartingIndex[0] = 0;
        Src[0] = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v16, 0);
        *(_DWORD *)(inserted + 12) = v56[3];
        EntryBlock = BfsGetEntryBlock(v16, inserted, Src, StartingIndex);
        if ( EntryBlock >= 0 )
          EntryBlock = BfsWriteBlock(a1, StartingIndex[0], Src[0]);
        ExReleasePushLockExclusiveEx(v16, 0);
        KeLeaveCriticalRegion();
        if ( EntryBlock < 0 )
          goto LABEL_36;
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v10, 0);
      v33 = BfsWriteBlock(a1, (int)v49, v34);
    }
    EntryBlock = v33;
  }
  else
  {
    EntryBlock = -1073741275;
  }
LABEL_35:
  ExReleasePushLockExclusiveEx(v10, 0);
  KeLeaveCriticalRegion();
LABEL_36:
  BfsDereferenceTableEntry(v10 - 2);
  v12 = v16 - 2;
LABEL_37:
  BfsDereferenceTableEntry(v12);
  return (unsigned int)EntryBlock;
}

```

## disassembly

```asm
0x140012478  push    rbp
0x14001247a  push    rbx
0x14001247b  push    rsi
0x14001247c  push    rdi
0x14001247d  push    r12
0x14001247f  push    r14
0x140012481  push    r15
0x140012483  lea     rbp, [rsp-1D0h]
0x14001248b  sub     rsp, 2D0h
0x140012492  mov     rax, cs:__security_cookie
0x140012499  xor     rax, rsp
0x14001249c  mov     [rbp+200h+var_40], rax
0x1400124a3  xorps   xmm0, xmm0
0x1400124a6  mov     [rsp+300h+var_2D0], 0
0x1400124af  mov     rsi, r9
0x1400124b2  mov     qword ptr [rsp+300h+StartingIndex], 0
0x1400124bb  mov     rbx, r8
0x1400124be  lea     r9, [rsp+300h+StartingIndex]
0x1400124c3  mov     r15, rcx
0x1400124c6  xorps   xmm1, xmm1
0x1400124c9  mov     r8d, 1
0x1400124cf  add     rcx, 30h ; '0'
0x1400124d3  movups  xmmword ptr [rsp+300h+var_298], xmm0
0x1400124d8  mov     r14, rdx
0x1400124db  movups  [rsp+300h+var_288], xmm1
0x1400124e0  movups  [rbp+200h+var_278], xmm0
0x1400124e4  call    BfsCreateDirectory
0x1400124e9  test    eax, eax
0x1400124eb  js      loc_140012A87
0x1400124f1  movups  xmm2, xmmword ptr [rbx]
0x1400124f4  mov     rdi, qword ptr [rsp+300h+StartingIndex]
0x1400124f9  lea     rcx, [rsp+300h+Src]
0x1400124fe  mov     rdx, rbx
0x140012501  mov     qword ptr [rsp+300h+StartingIndex], rdi
0x140012506  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm2
0x14001250b  call    BfsGetFinalPathComponent
0x140012510  mov     ebx, 2
0x140012515  movups  xmm1, xmmword ptr [rax]
0x140012518  movd    eax, xmm2
0x14001251c  movdqu  xmmword ptr [rsp+300h+var_298], xmm1
0x140012522  cmp     ax, bx
0x140012525  jb      short loc_140012583
0x140012527  lea     r8, [rsp+300h+var_288]
0x14001252c  lea     rdx, [rsp+300h+BitMapHeader]
0x140012531  lea     rcx, [rsp+300h+Src]
0x140012536  call    BfsGetPathComponent
0x14001253b  movups  xmm1, xmmword ptr [rax]
0x14001253e  movd    eax, xmm1
0x140012542  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm1
0x140012547  cmp     ax, bx
0x14001254a  jb      short loc_140012583
0x14001254c  lea     r9, [rsp+300h+StartingIndex]
0x140012551  mov     r8d, 1
0x140012557  lea     rdx, [rsp+300h+var_288]
0x14001255c  mov     rcx, rdi
0x14001255f  call    BfsCreateDirectory
0x140012564  lea     rcx, [rdi-8]; Buffer
0x140012568  mov     ebx, eax
0x14001256a  call    BfsDereferenceTableEntry
0x14001256f  test    ebx, ebx
0x140012571  js      loc_140012A85
0x140012577  mov     rdi, qword ptr [rsp+300h+StartingIndex]
0x14001257c  mov     ebx, 2
0x140012581  jmp     short loc_140012527
0x140012583  lea     r9, [rsp+300h+var_2D0]
0x140012588  mov     r8d, 1
0x14001258e  mov     rdx, r14
0x140012591  lea     rcx, [r15+30h]
0x140012595  call    BfsCreateDirectory
0x14001259a  mov     ebx, eax
0x14001259c  test    eax, eax
0x14001259e  jns     short loc_1400125A9
0x1400125a0  lea     rcx, [rdi-8]
0x1400125a4  jmp     loc_140012A80
0x1400125a9  movups  xmm2, xmmword ptr [rsi]
0x1400125ac  mov     rdx, rsi
0x1400125af  lea     rcx, [rsp+300h+Src]
0x1400125b4  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm2
0x1400125b9  call    BfsGetFinalPathComponent
0x1400125be  mov     ebx, 2
0x1400125c3  movups  xmm1, xmmword ptr [rax]
0x1400125c6  movd    eax, xmm2
0x1400125ca  movdqu  xmmword ptr [rsp+300h+Src], xmm1
0x1400125d0  cmp     ax, bx
0x1400125d3  jb      short loc_14001263E
0x1400125d5  lea     r8, [rbp+200h+var_278]
0x1400125d9  lea     rdx, [rsp+300h+BitMapHeader]
0x1400125de  lea     rcx, [rsp+300h+StartingIndex]
0x1400125e3  call    BfsGetPathComponent
0x1400125e8  movups  xmm1, xmmword ptr [rax]
0x1400125eb  movd    eax, xmm1
0x1400125ef  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm1
0x1400125f4  cmp     ax, bx
0x1400125f7  jb      short loc_14001263E
0x1400125f9  mov     rbx, [rsp+300h+var_2D0]
0x1400125fe  lea     r9, [rsp+300h+var_2D0]
0x140012603  mov     rcx, rbx
0x140012606  lea     rdx, [rbp+200h+var_278]
0x14001260a  mov     r8d, 1
0x140012610  call    BfsCreateDirectory
0x140012615  mov     esi, eax
0x140012617  cmp     rbx, rdi
0x14001261a  jz      short loc_140012625
0x14001261c  lea     rcx, [rbx-8]; Buffer
0x140012620  call    BfsDereferenceTableEntry
0x140012625  mov     ebx, 2
0x14001262a  test    esi, esi
0x14001262c  jns     short loc_1400125D5
0x14001262e  lea     rcx, [rdi-8]; Buffer
0x140012632  call    BfsDereferenceTableEntry
0x140012637  mov     eax, esi
0x140012639  jmp     loc_140012A87
0x14001263e  mov     rsi, [rsp+300h+var_2D0]
0x140012643  cmp     rdi, rsi
0x140012646  jnz     loc_140012714
0x14001264c  mov     dword ptr [rsp+300h+var_2D0], 0
0x140012654  mov     qword ptr [rsp+300h+StartingIndex], 0
0x14001265d  call    cs:__imp_KeEnterCriticalRegion
0x140012664  nop     dword ptr [rax+rax+00h]
0x140012669  xor     edx, edx
0x14001266b  mov     rcx, rdi
0x14001266e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012675  nop     dword ptr [rax+rax+00h]
0x14001267a  lea     rdx, [rsp+300h+var_298]
0x14001267f  mov     rcx, rdi
0x140012682  call    BfsFindEntry
0x140012687  mov     r14, rax
0x14001268a  test    rax, rax
0x14001268d  jnz     short loc_140012696
0x14001268f  mov     ebx, 0C0000225h
0x140012694  jmp     short loc_1400126E9
0x140012696  xor     edx, edx; Val
0x140012698  lea     rcx, [rax+14h]; void *
0x14001269c  mov     r8d, 200h; Size
0x1400126a2  call    memset
0x1400126a7  movzx   r8d, word ptr [rsp+300h+Src]; Size
0x1400126ad  lea     rcx, [r14+14h]; void *
0x1400126b1  mov     rdx, [rsp+300h+Src+8]; Src
0x1400126b6  call    memmove
0x1400126bb  lea     r9, [rsp+300h+var_2D0]
0x1400126c0  mov     rdx, r14
0x1400126c3  lea     r8, [rsp+300h+StartingIndex]
0x1400126c8  mov     rcx, rdi
0x1400126cb  call    BfsGetEntryBlock
0x1400126d0  mov     ebx, eax
0x1400126d2  test    eax, eax
0x1400126d4  js      short loc_1400126E9
0x1400126d6  mov     r8, qword ptr [rsp+300h+StartingIndex]
0x1400126db  mov     rcx, r15
0x1400126de  mov     edx, dword ptr [rsp+300h+var_2D0]
0x1400126e2  call    BfsWriteBlock
0x1400126e7  mov     ebx, eax
0x1400126e9  xor     edx, edx
0x1400126eb  mov     rcx, rdi
0x1400126ee  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400126f5  nop     dword ptr [rax+rax+00h]
0x1400126fa  call    cs:__imp_KeLeaveCriticalRegion
0x140012701  nop     dword ptr [rax+rax+00h]
0x140012706  lea     rcx, [rsi-8]; Buffer
0x14001270a  call    BfsDereferenceTableEntry
0x14001270f  jmp     loc_1400125A0
0x140012714  xor     eax, eax
0x140012716  mov     qword ptr [rsp+300h+BitMapHeader+4], rax
0x14001271b  mov     qword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], rax
0x140012720  mov     dword ptr [rsp+300h+var_2D0], eax
0x140012724  mov     qword ptr [rsp+300h+StartingIndex], rax
0x140012729  call    cs:__imp_KeEnterCriticalRegion
0x140012730  nop     dword ptr [rax+rax+00h]
0x140012735  xor     edx, edx
0x140012737  mov     rcx, rdi
0x14001273a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012741  nop     dword ptr [rax+rax+00h]
0x140012746  lea     rdx, [rsp+300h+var_298]
0x14001274b  mov     rcx, rdi
0x14001274e  call    BfsFindEntry
0x140012753  mov     rbx, rax
0x140012756  test    rax, rax
0x140012759  jnz     short loc_140012765
0x14001275b  mov     ebx, 0C0000225h
0x140012760  jmp     loc_140012A56
0x140012765  mov     r12d, 4
0x14001276b  lea     rcx, [rbp+200h+var_260]
0x14001276f  mov     edx, r12d
0x140012772  lea     r8d, [r12+7Ch]
0x140012777  movups  xmm0, xmmword ptr [rax]
0x14001277a  movups  xmm1, xmmword ptr [rax+10h]
0x14001277e  movups  xmmword ptr [rcx], xmm0
0x140012781  movups  xmm0, xmmword ptr [rax+20h]
0x140012785  movups  xmmword ptr [rcx+10h], xmm1
0x140012789  movups  xmm1, xmmword ptr [rax+30h]
0x14001278d  movups  xmmword ptr [rcx+20h], xmm0
0x140012791  movups  xmm0, xmmword ptr [rax+40h]
0x140012795  movups  xmmword ptr [rcx+30h], xmm1
0x140012799  movups  xmm1, xmmword ptr [rax+50h]
0x14001279d  movups  xmmword ptr [rcx+40h], xmm0
0x1400127a1  movups  xmm0, xmmword ptr [rax+60h]
0x1400127a5  movups  xmmword ptr [rcx+50h], xmm1
0x1400127a9  movups  xmm1, xmmword ptr [rax+70h]
0x1400127ad  add     rax, r8
0x1400127b0  movups  xmmword ptr [rcx+60h], xmm0
0x1400127b4  movups  xmmword ptr [rcx+70h], xmm1
0x1400127b8  add     rcx, r8
0x1400127bb  sub     rdx, 1; Val
0x1400127bf  jnz     short loc_140012777
0x1400127c1  movups  xmm0, xmmword ptr [rax]
0x1400127c4  mov     eax, [rax+10h]
0x1400127c7  mov     r8d, 200h; Size
0x1400127cd  movups  xmmword ptr [rcx], xmm0
0x1400127d0  mov     [rcx+10h], eax
0x1400127d3  lea     rcx, [rbp+200h+var_24C]; void *
0x1400127d7  call    memset
0x1400127dc  movzx   r8d, word ptr [rsp+300h+Src]; Size
0x1400127e2  lea     rcx, [rbp+200h+var_24C]; void *
0x1400127e6  mov     rdx, [rsp+300h+Src+8]; Src
0x1400127eb  call    memmove
0x1400127f0  lea     r9, [rsp+300h+var_2D0]
0x1400127f5  mov     rdx, rbx
0x1400127f8  lea     r8, [rsp+300h+StartingIndex]
0x1400127fd  mov     rcx, rdi
0x140012800  call    BfsGetEntryBlock
0x140012805  test    eax, eax
0x140012807  js      loc_140012A54
0x14001280d  mov     r14, qword ptr [rsp+300h+StartingIndex]
0x140012812  mov     rdx, rbx
0x140012815  mov     rcx, r14
0x140012818  call    BfsGetEntryIndex
0x14001281d  lea     rdx, [r14+3E60h]; BitMapBuffer
0x140012824  mov     [rsp+300h+StartingIndex], eax
0x140012828  mov     r8d, 1Eh; SizeOfBitMap
0x14001282e  lea     rcx, [rsp+300h+BitMapHeader]; BitMapHeader
0x140012833  call    cs:__imp_RtlInitializeBitMap
0x14001283a  nop     dword ptr [rax+rax+00h]
0x14001283f  mov     edx, [rsp+300h+StartingIndex]; StartingIndex
0x140012843  lea     rcx, [rsp+300h+BitMapHeader]; BitMapHeader
0x140012848  mov     r8d, 1; NumberToClear
0x14001284e  call    cs:__imp_RtlClearBits
0x140012855  nop     dword ptr [rax+rax+00h]
0x14001285a  xor     edx, edx; Val
0x14001285c  mov     r8d, 214h; Size
0x140012862  mov     rcx, rbx; void *
0x140012865  call    memset
0x14001286a  xor     edx, edx
0x14001286c  mov     rcx, rdi
0x14001286f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012876  nop     dword ptr [rax+rax+00h]
0x14001287b  call    cs:__imp_KeLeaveCriticalRegion
0x140012882  nop     dword ptr [rax+rax+00h]
0x140012887  mov     r9d, [rbp+200h+var_258]
0x14001288b  lea     rax, [rsp+300h+Src]
0x140012890  mov     r8d, [rbp+200h+var_25C]
0x140012894  mov     rcx, rsi
0x140012897  mov     edx, [rbp+200h+var_260]
0x14001289a  mov     [rsp+300h+var_2E0], rax
0x14001289f  call    BfsInsertDirectoryEntry
0x1400128a4  mov     rbx, rax
0x1400128a7  test    rax, rax
0x1400128aa  jnz     loc_14001299B
0x1400128b0  call    cs:__imp_KeEnterCriticalRegion
0x1400128b7  nop     dword ptr [rax+rax+00h]
0x1400128bc  xor     edx, edx
0x1400128be  mov     rcx, rdi
0x1400128c1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400128c8  nop     dword ptr [rax+rax+00h]
0x1400128cd  mov     eax, [rsp+300h+StartingIndex]
0x1400128d1  lea     rcx, [r14+8]
0x1400128d5  imul    rdx, rax, 214h
0x1400128dc  lea     rax, [rbp+200h+var_260]
0x1400128e0  mov     r8d, 80h
0x1400128e6  add     rcx, rdx
0x1400128e9  movups  xmm0, xmmword ptr [rax]
0x1400128ec  movups  xmm1, xmmword ptr [rax+10h]
0x1400128f0  movups  xmmword ptr [rcx], xmm0
0x1400128f3  movups  xmm0, xmmword ptr [rax+20h]
0x1400128f7  movups  xmmword ptr [rcx+10h], xmm1
0x1400128fb  movups  xmm1, xmmword ptr [rax+30h]
0x1400128ff  movups  xmmword ptr [rcx+20h], xmm0
0x140012903  movups  xmm0, xmmword ptr [rax+40h]
0x140012907  movups  xmmword ptr [rcx+30h], xmm1
0x14001290b  movups  xmm1, xmmword ptr [rax+50h]
0x14001290f  movups  xmmword ptr [rcx+40h], xmm0
0x140012913  movups  xmm0, xmmword ptr [rax+60h]
0x140012917  movups  xmmword ptr [rcx+50h], xmm1
0x14001291b  movups  xmm1, xmmword ptr [rax+70h]
0x14001291f  add     rax, r8
0x140012922  movups  xmmword ptr [rcx+60h], xmm0
0x140012926  movups  xmmword ptr [rcx+70h], xmm1
0x14001292a  add     rcx, r8
0x14001292d  sub     r12, 1
0x140012931  jnz     short loc_1400128E9
0x140012933  movups  xmm0, xmmword ptr [rax]
0x140012936  mov     eax, [rax+10h]
0x140012939  lea     rbx, [rdx+r14]
0x14001293d  xor     edx, edx; Val
0x14001293f  mov     r8d, 200h; Size
0x140012945  movups  xmmword ptr [rcx], xmm0
0x140012948  mov     [rcx+10h], eax
0x14001294b  lea     rcx, [rbx+1Ch]; void *
0x14001294f  call    memset
0x140012954  movzx   r8d, word ptr [rsp+300h+var_298]; Size
0x14001295a  lea     rcx, [rbx+1Ch]; void *
  ... truncated ...
```
