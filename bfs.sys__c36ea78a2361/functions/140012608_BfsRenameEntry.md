# BfsRenameEntry

- ea: `0x140012608`
- end: `0x140012c39`
- name: `BfsRenameEntry`
- size: `1585`
- prototype: `__int64 __fastcall(__int64, __int64, struct _RTL_BITMAP *, struct _RTL_BITMAP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000a930`

## callees

- `0x140006d20`
- `0x14001093c`
- `0x140011404`
- `0x140011838`
- `0x140011a24`
- `0x140011b1c`
- `0x140011bc8`
- `0x140011ea8`
- `0x140012608`
- `0x140012c40`
- `0x140013860`
- `0x140013980`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400127fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400128ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012a51`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012bc9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400127fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400128ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012a51`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012b57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012bc9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001287e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400129ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b9c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012beb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001287e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400129ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012b9c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012beb`
- `ntoskrnl!RtlSetBits` at `0x140012b06`
- `ntoskrnl!RtlSetBits` at `0x140012b06`
- `ntoskrnl!RtlClearBits` at `0x1400129de`
- `ntoskrnl!RtlClearBits` at `0x1400129de`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400129c3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400129c3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400127ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400128b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012a40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012b46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012bb8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400127ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400128b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012a40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012b46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012bb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001288a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012ba8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012bf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001288a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012a0b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012ba8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012bf7`

## pseudocode

```c
__int64 __fastcall BfsRenameEntry(__int64 a1, __int64 a2, struct _RTL_BITMAP *a3, struct _RTL_BITMAP *a4)
{
  __int64 result; // rax
  struct _RTL_BITMAP v9; // xmm2
  __int64 v10; // rdi
  int EntryBlock; // ebx
  void *v12; // rcx
  struct _RTL_BITMAP v13; // xmm2
  __int64 v14; // rbx
  int v15; // esi
  __int64 v16; // rsi
  __int64 Entry; // rax
  __int64 v18; // r14
  int *v19; // rax
  int *v20; // rbx
  __int64 v21; // r12
  int *v22; // rcx
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
  int v33; // eax
  __int64 v34; // r14
  _DWORD *inserted; // rbx
  __int64 v36; // rdx
  int *v37; // rax
  _OWORD *v38; // rcx
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  int v47; // eax
  __int64 v48; // rbx
  __int64 v49; // [rsp+30h] [rbp-D0h] BYREF
  ULONG StartingIndex[4]; // [rsp+38h] [rbp-C8h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+58h] [rbp-A8h] BYREF
  void *v53[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  __int128 v55; // [rsp+88h] [rbp-78h] BYREF
  int v56[5]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v57[524]; // [rsp+B4h] [rbp-4Ch] BYREF

  v49 = 0;
  *(_QWORD *)StartingIndex = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  v55 = 0;
  result = BfsCreateDirectory(a1 + 48, a2, 1, StartingIndex);
  if ( (int)result < 0 )
    return result;
  v10 = *(_QWORD *)StartingIndex;
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
      BfsDereferenceTableEntry((PVOID)(v10 - 8));
      if ( EntryBlock < 0 )
        return (unsigned int)EntryBlock;
      v10 = *(_QWORD *)StartingIndex;
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
        BfsDereferenceTableEntry((PVOID)(v14 - 8));
      if ( v15 < 0 )
      {
        BfsDereferenceTableEntry((PVOID)(v10 - 8));
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
        EntryBlock = BfsWriteBlock(a1, (unsigned int)v49, *(_QWORD *)StartingIndex);
    }
    else
    {
      EntryBlock = -1073741275;
    }
    ExReleasePushLockExclusiveEx(v10, 0);
    KeLeaveCriticalRegion();
    BfsDereferenceTableEntry((PVOID)(v16 - 8));
LABEL_7:
    v12 = (void *)(v10 - 8);
    goto LABEL_37;
  }
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  LODWORD(v49) = 0;
  *(_QWORD *)StartingIndex = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v10, 0);
  v19 = (int *)BfsFindEntry(v10, v53);
  v20 = v19;
  if ( v19 )
  {
    v21 = 4;
    v22 = v56;
    v23 = 4;
    do
    {
      v24 = *((_OWORD *)v19 + 1);
      *(_OWORD *)v22 = *(_OWORD *)v19;
      v25 = *((_OWORD *)v19 + 2);
      *((_OWORD *)v22 + 1) = v24;
      v26 = *((_OWORD *)v19 + 3);
      *((_OWORD *)v22 + 2) = v25;
      v27 = *((_OWORD *)v19 + 4);
      *((_OWORD *)v22 + 3) = v26;
      v28 = *((_OWORD *)v19 + 5);
      *((_OWORD *)v22 + 4) = v27;
      v29 = *((_OWORD *)v19 + 6);
      *((_OWORD *)v22 + 5) = v28;
      v30 = *((_OWORD *)v19 + 7);
      v19 += 32;
      *((_OWORD *)v22 + 6) = v29;
      *((_OWORD *)v22 + 7) = v30;
      v22 += 32;
      --v23;
    }
    while ( v23 );
    v31 = *(_OWORD *)v19;
    v32 = v19[4];
    *(_OWORD *)v22 = v31;
    v22[4] = v32;
    memset(v57, 0, 0x200u);
    memmove(v57, Src[1], LOWORD(Src[0]));
    v33 = BfsGetEntryBlock(v10, v20, StartingIndex, &v49);
    if ( v33 >= 0 )
    {
      v34 = *(_QWORD *)StartingIndex;
      StartingIndex[0] = BfsGetEntryIndex(*(_QWORD *)StartingIndex, v20);
      RtlInitializeBitMap(&BitMapHeader, (PULONG)(v34 + 15968), 0x1Eu);
      RtlClearBits(&BitMapHeader, StartingIndex[0], 1u);
      memset(v20, 0, 0x214u);
      ExReleasePushLockExclusiveEx(v10, 0);
      KeLeaveCriticalRegion();
      inserted = BfsInsertDirectoryEntry(v16, v56[0], v56[1], v56[2], (__int64)Src);
      if ( !inserted )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v10, 0);
        v36 = 532LL * StartingIndex[0];
        v37 = v56;
        v38 = (_OWORD *)(v36 + v34 + 8);
        do
        {
          v39 = *((_OWORD *)v37 + 1);
          *v38 = *(_OWORD *)v37;
          v40 = *((_OWORD *)v37 + 2);
          v38[1] = v39;
          v41 = *((_OWORD *)v37 + 3);
          v38[2] = v40;
          v42 = *((_OWORD *)v37 + 4);
          v38[3] = v41;
          v43 = *((_OWORD *)v37 + 5);
          v38[4] = v42;
          v44 = *((_OWORD *)v37 + 6);
          v38[5] = v43;
          v45 = *((_OWORD *)v37 + 7);
          v37 += 32;
          v38[6] = v44;
          v38[7] = v45;
          v38 += 8;
          --v21;
        }
        while ( v21 );
        v46 = *(_OWORD *)v37;
        v47 = v37[4];
        v48 = v36 + v34;
        *v38 = v46;
        *((_DWORD *)v38 + 4) = v47;
        memset((void *)(v36 + v34 + 28), 0, 0x200u);
        memmove((void *)(v48 + 28), v53[1], LOWORD(v53[0]));
        RtlSetBits(&BitMapHeader, StartingIndex[0], 1u);
        BfsWriteBlock(a1, (unsigned int)v49, v34);
        EntryBlock = -1073741801;
        goto LABEL_35;
      }
      if ( v56[0] == 2 )
      {
        StartingIndex[0] = 0;
        Src[0] = 0;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v16, 0);
        inserted[3] = v56[3];
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
      v33 = BfsWriteBlock(a1, (unsigned int)v49, v34);
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
  BfsDereferenceTableEntry((PVOID)(v10 - 8));
  v12 = (void *)(v16 - 8);
LABEL_37:
  BfsDereferenceTableEntry(v12);
  return (unsigned int)EntryBlock;
}

```

## disassembly

```asm
0x140012608  push    rbp
0x14001260a  push    rbx
0x14001260b  push    rsi
0x14001260c  push    rdi
0x14001260d  push    r12
0x14001260f  push    r14
0x140012611  push    r15
0x140012613  lea     rbp, [rsp-1D0h]
0x14001261b  sub     rsp, 2D0h
0x140012622  mov     rax, cs:__security_cookie
0x140012629  xor     rax, rsp
0x14001262c  mov     [rbp+200h+var_40], rax
0x140012633  xorps   xmm0, xmm0
0x140012636  mov     [rsp+300h+var_2D0], 0
0x14001263f  mov     rsi, r9
0x140012642  mov     qword ptr [rsp+300h+StartingIndex], 0
0x14001264b  mov     rbx, r8
0x14001264e  lea     r9, [rsp+300h+StartingIndex]
0x140012653  mov     r15, rcx
0x140012656  xorps   xmm1, xmm1
0x140012659  mov     r8d, 1
0x14001265f  add     rcx, 30h ; '0'
0x140012663  movups  xmmword ptr [rsp+300h+var_298], xmm0
0x140012668  mov     r14, rdx
0x14001266b  movups  [rsp+300h+var_288], xmm1
0x140012670  movups  [rbp+200h+var_278], xmm0
0x140012674  call    BfsCreateDirectory
0x140012679  test    eax, eax
0x14001267b  js      loc_140012C17
0x140012681  movups  xmm2, xmmword ptr [rbx]
0x140012684  mov     rdi, qword ptr [rsp+300h+StartingIndex]
0x140012689  lea     rcx, [rsp+300h+Src]
0x14001268e  mov     rdx, rbx
0x140012691  mov     qword ptr [rsp+300h+StartingIndex], rdi
0x140012696  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm2
0x14001269b  call    BfsGetFinalPathComponent
0x1400126a0  mov     ebx, 2
0x1400126a5  movups  xmm1, xmmword ptr [rax]
0x1400126a8  movd    eax, xmm2
0x1400126ac  movdqu  xmmword ptr [rsp+300h+var_298], xmm1
0x1400126b2  cmp     ax, bx
0x1400126b5  jb      short loc_140012713
0x1400126b7  lea     r8, [rsp+300h+var_288]
0x1400126bc  lea     rdx, [rsp+300h+BitMapHeader]
0x1400126c1  lea     rcx, [rsp+300h+Src]
0x1400126c6  call    BfsGetPathComponent
0x1400126cb  movups  xmm1, xmmword ptr [rax]
0x1400126ce  movd    eax, xmm1
0x1400126d2  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm1
0x1400126d7  cmp     ax, bx
0x1400126da  jb      short loc_140012713
0x1400126dc  lea     r9, [rsp+300h+StartingIndex]
0x1400126e1  mov     r8d, 1
0x1400126e7  lea     rdx, [rsp+300h+var_288]
0x1400126ec  mov     rcx, rdi
0x1400126ef  call    BfsCreateDirectory
0x1400126f4  lea     rcx, [rdi-8]; Buffer
0x1400126f8  mov     ebx, eax
0x1400126fa  call    BfsDereferenceTableEntry
0x1400126ff  test    ebx, ebx
0x140012701  js      loc_140012C15
0x140012707  mov     rdi, qword ptr [rsp+300h+StartingIndex]
0x14001270c  mov     ebx, 2
0x140012711  jmp     short loc_1400126B7
0x140012713  lea     r9, [rsp+300h+var_2D0]
0x140012718  mov     r8d, 1
0x14001271e  mov     rdx, r14
0x140012721  lea     rcx, [r15+30h]
0x140012725  call    BfsCreateDirectory
0x14001272a  mov     ebx, eax
0x14001272c  test    eax, eax
0x14001272e  jns     short loc_140012739
0x140012730  lea     rcx, [rdi-8]
0x140012734  jmp     loc_140012C10
0x140012739  movups  xmm2, xmmword ptr [rsi]
0x14001273c  mov     rdx, rsi
0x14001273f  lea     rcx, [rsp+300h+Src]
0x140012744  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm2
0x140012749  call    BfsGetFinalPathComponent
0x14001274e  mov     ebx, 2
0x140012753  movups  xmm1, xmmword ptr [rax]
0x140012756  movd    eax, xmm2
0x14001275a  movdqu  xmmword ptr [rsp+300h+Src], xmm1
0x140012760  cmp     ax, bx
0x140012763  jb      short loc_1400127CE
0x140012765  lea     r8, [rbp+200h+var_278]
0x140012769  lea     rdx, [rsp+300h+BitMapHeader]
0x14001276e  lea     rcx, [rsp+300h+StartingIndex]
0x140012773  call    BfsGetPathComponent
0x140012778  movups  xmm1, xmmword ptr [rax]
0x14001277b  movd    eax, xmm1
0x14001277f  movups  xmmword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], xmm1
0x140012784  cmp     ax, bx
0x140012787  jb      short loc_1400127CE
0x140012789  mov     rbx, [rsp+300h+var_2D0]
0x14001278e  lea     r9, [rsp+300h+var_2D0]
0x140012793  mov     rcx, rbx
0x140012796  lea     rdx, [rbp+200h+var_278]
0x14001279a  mov     r8d, 1
0x1400127a0  call    BfsCreateDirectory
0x1400127a5  mov     esi, eax
0x1400127a7  cmp     rbx, rdi
0x1400127aa  jz      short loc_1400127B5
0x1400127ac  lea     rcx, [rbx-8]; Buffer
0x1400127b0  call    BfsDereferenceTableEntry
0x1400127b5  mov     ebx, 2
0x1400127ba  test    esi, esi
0x1400127bc  jns     short loc_140012765
0x1400127be  lea     rcx, [rdi-8]; Buffer
0x1400127c2  call    BfsDereferenceTableEntry
0x1400127c7  mov     eax, esi
0x1400127c9  jmp     loc_140012C17
0x1400127ce  mov     rsi, [rsp+300h+var_2D0]
0x1400127d3  cmp     rdi, rsi
0x1400127d6  jnz     loc_1400128A4
0x1400127dc  mov     dword ptr [rsp+300h+var_2D0], 0
0x1400127e4  mov     qword ptr [rsp+300h+StartingIndex], 0
0x1400127ed  call    cs:__imp_KeEnterCriticalRegion
0x1400127f4  nop     dword ptr [rax+rax+00h]
0x1400127f9  xor     edx, edx
0x1400127fb  mov     rcx, rdi
0x1400127fe  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012805  nop     dword ptr [rax+rax+00h]
0x14001280a  lea     rdx, [rsp+300h+var_298]
0x14001280f  mov     rcx, rdi
0x140012812  call    BfsFindEntry
0x140012817  mov     r14, rax
0x14001281a  test    rax, rax
0x14001281d  jnz     short loc_140012826
0x14001281f  mov     ebx, 0C0000225h
0x140012824  jmp     short loc_140012879
0x140012826  xor     edx, edx; Val
0x140012828  lea     rcx, [rax+14h]; void *
0x14001282c  mov     r8d, 200h; Size
0x140012832  call    memset
0x140012837  movzx   r8d, word ptr [rsp+300h+Src]; Size
0x14001283d  lea     rcx, [r14+14h]; void *
0x140012841  mov     rdx, [rsp+300h+Src+8]; Src
0x140012846  call    memmove
0x14001284b  lea     r9, [rsp+300h+var_2D0]
0x140012850  mov     rdx, r14
0x140012853  lea     r8, [rsp+300h+StartingIndex]
0x140012858  mov     rcx, rdi
0x14001285b  call    BfsGetEntryBlock
0x140012860  mov     ebx, eax
0x140012862  test    eax, eax
0x140012864  js      short loc_140012879
0x140012866  mov     r8, qword ptr [rsp+300h+StartingIndex]
0x14001286b  mov     rcx, r15
0x14001286e  mov     edx, dword ptr [rsp+300h+var_2D0]
0x140012872  call    BfsWriteBlock
0x140012877  mov     ebx, eax
0x140012879  xor     edx, edx
0x14001287b  mov     rcx, rdi
0x14001287e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012885  nop     dword ptr [rax+rax+00h]
0x14001288a  call    cs:__imp_KeLeaveCriticalRegion
0x140012891  nop     dword ptr [rax+rax+00h]
0x140012896  lea     rcx, [rsi-8]; Buffer
0x14001289a  call    BfsDereferenceTableEntry
0x14001289f  jmp     loc_140012730
0x1400128a4  xor     eax, eax
0x1400128a6  mov     qword ptr [rsp+300h+BitMapHeader+4], rax
0x1400128ab  mov     qword ptr [rsp+300h+BitMapHeader.SizeOfBitMap], rax
0x1400128b0  mov     dword ptr [rsp+300h+var_2D0], eax
0x1400128b4  mov     qword ptr [rsp+300h+StartingIndex], rax
0x1400128b9  call    cs:__imp_KeEnterCriticalRegion
0x1400128c0  nop     dword ptr [rax+rax+00h]
0x1400128c5  xor     edx, edx
0x1400128c7  mov     rcx, rdi
0x1400128ca  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400128d1  nop     dword ptr [rax+rax+00h]
0x1400128d6  lea     rdx, [rsp+300h+var_298]
0x1400128db  mov     rcx, rdi
0x1400128de  call    BfsFindEntry
0x1400128e3  mov     rbx, rax
0x1400128e6  test    rax, rax
0x1400128e9  jnz     short loc_1400128F5
0x1400128eb  mov     ebx, 0C0000225h
0x1400128f0  jmp     loc_140012BE6
0x1400128f5  mov     r12d, 4
0x1400128fb  lea     rcx, [rbp+200h+var_260]
0x1400128ff  mov     edx, r12d
0x140012902  lea     r8d, [r12+7Ch]
0x140012907  movups  xmm0, xmmword ptr [rax]
0x14001290a  movups  xmm1, xmmword ptr [rax+10h]
0x14001290e  movups  xmmword ptr [rcx], xmm0
0x140012911  movups  xmm0, xmmword ptr [rax+20h]
0x140012915  movups  xmmword ptr [rcx+10h], xmm1
0x140012919  movups  xmm1, xmmword ptr [rax+30h]
0x14001291d  movups  xmmword ptr [rcx+20h], xmm0
0x140012921  movups  xmm0, xmmword ptr [rax+40h]
0x140012925  movups  xmmword ptr [rcx+30h], xmm1
0x140012929  movups  xmm1, xmmword ptr [rax+50h]
0x14001292d  movups  xmmword ptr [rcx+40h], xmm0
0x140012931  movups  xmm0, xmmword ptr [rax+60h]
0x140012935  movups  xmmword ptr [rcx+50h], xmm1
0x140012939  movups  xmm1, xmmword ptr [rax+70h]
0x14001293d  add     rax, r8
0x140012940  movups  xmmword ptr [rcx+60h], xmm0
0x140012944  movups  xmmword ptr [rcx+70h], xmm1
0x140012948  add     rcx, r8
0x14001294b  sub     rdx, 1; Val
0x14001294f  jnz     short loc_140012907
0x140012951  movups  xmm0, xmmword ptr [rax]
0x140012954  mov     eax, [rax+10h]
0x140012957  mov     r8d, 200h; Size
0x14001295d  movups  xmmword ptr [rcx], xmm0
0x140012960  mov     [rcx+10h], eax
0x140012963  lea     rcx, [rbp+200h+var_24C]; void *
0x140012967  call    memset
0x14001296c  movzx   r8d, word ptr [rsp+300h+Src]; Size
0x140012972  lea     rcx, [rbp+200h+var_24C]; void *
0x140012976  mov     rdx, [rsp+300h+Src+8]; Src
0x14001297b  call    memmove
0x140012980  lea     r9, [rsp+300h+var_2D0]
0x140012985  mov     rdx, rbx
0x140012988  lea     r8, [rsp+300h+StartingIndex]
0x14001298d  mov     rcx, rdi
0x140012990  call    BfsGetEntryBlock
0x140012995  test    eax, eax
0x140012997  js      loc_140012BE4
0x14001299d  mov     r14, qword ptr [rsp+300h+StartingIndex]
0x1400129a2  mov     rdx, rbx
0x1400129a5  mov     rcx, r14
0x1400129a8  call    BfsGetEntryIndex
0x1400129ad  lea     rdx, [r14+3E60h]; BitMapBuffer
0x1400129b4  mov     [rsp+300h+StartingIndex], eax
0x1400129b8  mov     r8d, 1Eh; SizeOfBitMap
0x1400129be  lea     rcx, [rsp+300h+BitMapHeader]; BitMapHeader
0x1400129c3  call    cs:__imp_RtlInitializeBitMap
0x1400129ca  nop     dword ptr [rax+rax+00h]
0x1400129cf  mov     edx, [rsp+300h+StartingIndex]; StartingIndex
0x1400129d3  lea     rcx, [rsp+300h+BitMapHeader]; BitMapHeader
0x1400129d8  mov     r8d, 1; NumberToClear
0x1400129de  call    cs:__imp_RtlClearBits
0x1400129e5  nop     dword ptr [rax+rax+00h]
0x1400129ea  xor     edx, edx; Val
0x1400129ec  mov     r8d, 214h; Size
0x1400129f2  mov     rcx, rbx; void *
0x1400129f5  call    memset
0x1400129fa  xor     edx, edx
0x1400129fc  mov     rcx, rdi
0x1400129ff  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012a06  nop     dword ptr [rax+rax+00h]
0x140012a0b  call    cs:__imp_KeLeaveCriticalRegion
0x140012a12  nop     dword ptr [rax+rax+00h]
0x140012a17  mov     r9d, [rbp+200h+var_258]
0x140012a1b  lea     rax, [rsp+300h+Src]
0x140012a20  mov     r8d, [rbp+200h+var_25C]
0x140012a24  mov     rcx, rsi
0x140012a27  mov     edx, [rbp+200h+var_260]
0x140012a2a  mov     [rsp+300h+var_2E0], rax
0x140012a2f  call    BfsInsertDirectoryEntry
0x140012a34  mov     rbx, rax
0x140012a37  test    rax, rax
0x140012a3a  jnz     loc_140012B2B
0x140012a40  call    cs:__imp_KeEnterCriticalRegion
0x140012a47  nop     dword ptr [rax+rax+00h]
0x140012a4c  xor     edx, edx
0x140012a4e  mov     rcx, rdi
0x140012a51  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012a58  nop     dword ptr [rax+rax+00h]
0x140012a5d  mov     eax, [rsp+300h+StartingIndex]
0x140012a61  lea     rcx, [r14+8]
0x140012a65  imul    rdx, rax, 214h
0x140012a6c  lea     rax, [rbp+200h+var_260]
0x140012a70  mov     r8d, 80h
0x140012a76  add     rcx, rdx
0x140012a79  movups  xmm0, xmmword ptr [rax]
0x140012a7c  movups  xmm1, xmmword ptr [rax+10h]
0x140012a80  movups  xmmword ptr [rcx], xmm0
0x140012a83  movups  xmm0, xmmword ptr [rax+20h]
0x140012a87  movups  xmmword ptr [rcx+10h], xmm1
0x140012a8b  movups  xmm1, xmmword ptr [rax+30h]
0x140012a8f  movups  xmmword ptr [rcx+20h], xmm0
0x140012a93  movups  xmm0, xmmword ptr [rax+40h]
0x140012a97  movups  xmmword ptr [rcx+30h], xmm1
0x140012a9b  movups  xmm1, xmmword ptr [rax+50h]
0x140012a9f  movups  xmmword ptr [rcx+40h], xmm0
0x140012aa3  movups  xmm0, xmmword ptr [rax+60h]
0x140012aa7  movups  xmmword ptr [rcx+50h], xmm1
0x140012aab  movups  xmm1, xmmword ptr [rax+70h]
0x140012aaf  add     rax, r8
0x140012ab2  movups  xmmword ptr [rcx+60h], xmm0
0x140012ab6  movups  xmmword ptr [rcx+70h], xmm1
0x140012aba  add     rcx, r8
0x140012abd  sub     r12, 1
0x140012ac1  jnz     short loc_140012A79
0x140012ac3  movups  xmm0, xmmword ptr [rax]
0x140012ac6  mov     eax, [rax+10h]
0x140012ac9  lea     rbx, [rdx+r14]
0x140012acd  xor     edx, edx; Val
0x140012acf  mov     r8d, 200h; Size
0x140012ad5  movups  xmmword ptr [rcx], xmm0
0x140012ad8  mov     [rcx+10h], eax
0x140012adb  lea     rcx, [rbx+1Ch]; void *
0x140012adf  call    memset
0x140012ae4  movzx   r8d, word ptr [rsp+300h+var_298]; Size
0x140012aea  lea     rcx, [rbx+1Ch]; void *
  ... truncated ...
```
