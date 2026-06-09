# TxfLogOldStreamData

- ea: `0x140100f80`
- end: `0x140101603`
- name: `TxfLogOldStreamData`
- size: `1667`
- prototype: `__int64 __fastcall(int, int, int, int, PLARGE_INTEGER, ULONG Length, __int64, __int64, __int64, int, int, int, int, __int16, char, PVOID Buffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140039038`

## callees

- `0x14000c450`
- `0x140012e70`
- `0x140059440`
- `0x1400b6e90`
- `0x1401004bc`
- `0x140100e88`
- `0x140100f80`
- `0x1401016a0`
- `0x140163fc8`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140101142`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140101142`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140101519`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c4cbb`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140101519`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c4cbb`
- `ntoskrnl!CcMapData` at `0x1401011dc`
- `ntoskrnl!CcMapData` at `0x1401011dc`
- `ntoskrnl!CcPreparePinWrite` at `0x1401012c8`
- `ntoskrnl!CcPreparePinWrite` at `0x1401012c8`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140101202`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140101202`
- `ntoskrnl!CcUnpinData` at `0x14010156b`
- `ntoskrnl!CcUnpinData` at `0x140101584`
- `ntoskrnl!CcUnpinData` at `0x1402c4d0e`
- `ntoskrnl!CcUnpinData` at `0x1402c4d27`
- `ntoskrnl!CcUnpinData` at `0x14010156b`
- `ntoskrnl!CcUnpinData` at `0x140101584`
- `ntoskrnl!CcUnpinData` at `0x1402c4d0e`
- `ntoskrnl!CcUnpinData` at `0x1402c4d27`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101413`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401014e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401015c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4b5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4c85`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4d80`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101413`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401014e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401015c9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4b5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4c85`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4d80`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101103`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101435`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101503`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4ba9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4ca5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101103`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101435`
- `ntoskrnl!ExAcquireFastMutex` at `0x140101503`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4ba9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4ca5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010118e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010152c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4ae2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4cce`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010118e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010152c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4ae2`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4cce`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401013cc`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402c4b03`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1401013cc`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402c4b03`

## pseudocode

```c
void __fastcall TxfLogOldStreamData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        union _LARGE_INTEGER *a4,
        PLARGE_INTEGER a5,
        ULONG Length,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        int a13,
        __int16 a14,
        char a15,
        CLFS_LSN *Buffer)
{
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // r12
  _QWORD *v23; // r13
  unsigned int v24; // r15d
  unsigned __int64 v25; // rcx
  CLFS_RECORD_INDEX idxRecord; // eax
  __int64 i; // rcx
  __int64 v28; // rdx
  __int64 v29; // r10
  __int64 j; // r9
  __int64 n; // rdx
  char v32; // r12
  _BYTE *v33; // r9
  __int64 v34; // rdx
  unsigned int ii; // r8d
  __int64 k; // r8
  __int64 m; // rdx
  PVOID v38; // rdi
  __int64 jj; // r8
  char v40; // [rsp+51h] [rbp-A7h]
  unsigned __int8 NewElement; // [rsp+53h] [rbp-A5h] BYREF
  int v42; // [rsp+54h] [rbp-A4h]
  int v43; // [rsp+58h] [rbp-A0h]
  unsigned int v44; // [rsp+5Ch] [rbp-9Ch] BYREF
  int v45; // [rsp+60h] [rbp-98h]
  PVOID VirtualAddress; // [rsp+68h] [rbp-90h] BYREF
  PVOID inserted; // [rsp+70h] [rbp-88h]
  __int64 v48; // [rsp+78h] [rbp-80h]
  int v49; // [rsp+80h] [rbp-78h]
  __int64 v50; // [rsp+88h] [rbp-70h]
  __int64 v51; // [rsp+90h] [rbp-68h]
  PVOID v52; // [rsp+98h] [rbp-60h] BYREF
  PVOID Bcb; // [rsp+A0h] [rbp-58h] BYREF
  PVOID Src; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-48h]
  __int64 v56; // [rsp+B8h] [rbp-40h]
  PFILE_OBJECT FileObject; // [rsp+108h] [rbp+10h]
  union _LARGE_INTEGER *FileOffset; // [rsp+118h] [rbp+20h]
  char v59; // [rsp+170h] [rbp+78h]

  FileOffset = a4;
  FileObject = (PFILE_OBJECT)a2;
  Src = 0;
  VirtualAddress = 0;
  Bcb = 0;
  v52 = 0;
  v19 = *(_QWORD *)(a2 + 24);
  v20 = *(_QWORD *)(v19 + 184);
  v50 = v20;
  v21 = *(_QWORD *)(v20 + 320);
  v55 = v21;
  NewElement = 0;
  v44 = 0;
  if ( !Buffer && !a7 )
    return;
  v56 = v20;
  v40 = 0;
  v45 = 0;
  inserted = 0;
  v59 = 0;
  v22 = 0;
  v51 = 0;
  v23 = (_QWORD *)(v21 + 280);
  v48 = v21 + 280;
  if ( !a10 && !*(_QWORD *)(a2 + 48) )
  {
    NtfsCreateInternalAttributeStream(a1, v19, 0, 0, 0, 0);
    FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a2 + 24) + 280LL);
    a4 = FileOffset;
  }
  if ( Buffer )
  {
    Buffer[2] = CLFS_LSN_INVALID_EXT;
    BYTE6(Buffer[3].ullOffset) = 0;
    Buffer->ullOffset = (unsigned __int64)a4->QuadPart >> 12;
    v24 = Length;
    Buffer[3].offset.idxRecord = Length >> 12;
    Buffer[1].ullOffset = (unsigned int)((unsigned __int64)a5->QuadPart >> 12);
    WORD2(Buffer[3].ullOffset) = a14;
    v25 = *(_QWORD *)(a3 + 96);
    if ( a4->QuadPart + (unsigned __int64)Length <= v25 )
      Buffer[4].offset.idxRecord = Length;
    else
      Buffer[4].offset.idxRecord = v25 - a4->QuadPart;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    v45 = 1;
    idxRecord = Buffer[3].offset.idxRecord;
    if ( a12 )
    {
      BYTE6(Buffer[3].ullOffset) |= 2u;
      inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), Buffer, 16 * idxRecord + 36, &NewElement);
    }
    else
    {
      v51 = TxfInsertNewTopsRange(*(_QWORD *)(v55 + 16), a3, Buffer[1].ullOffset, idxRecord, 0, (__int64)&v44);
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    v45 = 0;
    if ( a10 )
    {
      if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v50 + 104) + 64LL)) )
      {
        NtfsAcquireSharedFcb(a1, v50, 0, 0);
        v40 = 1;
      }
    }
    else
    {
      CcMapData(FileObject, FileOffset, Length, 1u, &Bcb, &Src);
    }
    v59 = NtfsAcquireScbPagingResourceShared(a1, *v23);
    if ( a1 )
    {
      v49 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v49 = i;
        if ( (unsigned int)i >= 2 )
          break;
        v28 = *(_QWORD *)(a1 + 8 * i + 48);
        if ( !v28 || v28 == *(_QWORD *)(*v23 + 184LL) )
        {
          *(_QWORD *)(a1 + 8LL * (unsigned int)i + 48) = *(_QWORD *)(*v23 + 184LL);
          break;
        }
      }
    }
    CcPreparePinWrite(*(PFILE_OBJECT *)(*v23 + 280LL), a5, Length, 0, 3u, &v52, &VirtualAddress);
    if ( a10 )
      TxfReadFileNonCached(FileObject, FileOffset, Length, VirtualAddress);
    else
      memmove(VirtualAddress, Src, Length);
    v29 = 0;
    for ( j = 0; ; j = (unsigned int)(j + 512) )
    {
      v43 = v29;
      v42 = j;
      if ( (unsigned int)j >= Length )
        break;
      *((_WORD *)&Buffer[4].ullOffset + v29 + 2) = *(_WORD *)((char *)VirtualAddress + j);
      *(_WORD *)((char *)VirtualAddress + j) = WORD2(Buffer[3].ullOffset);
      v29 = (unsigned int)(v29 + 1);
    }
    v22 = 1;
  }
  else
  {
    v24 = Length;
  }
  TxfDoWriteFileLogging(a1, a3, *((_QWORD *)FileObject->FsContext + 23), a7, a8, a9, (__int64)Buffer, a11, a13);
  if ( Buffer )
  {
    if ( ClfsLsnInvalid(Buffer + 2) )
    {
      if ( v22 )
      {
        for ( k = 0; (unsigned int)k < v24; k = (unsigned int)(k + 512) )
          *(_WORD *)((char *)VirtualAddress + k) = 0;
      }
      v32 = v59;
      if ( v59 )
      {
        if ( a1 )
        {
          for ( m = 0; m != 2; ++m )
          {
            if ( *(_QWORD *)(a1 + 8 * m + 48) == *(_QWORD *)(*v23 + 184LL) )
              *(_QWORD *)(a1 + 8 * m + 48) = 0;
          }
        }
        ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
        v32 = 0;
      }
      v38 = inserted;
      if ( !inserted )
      {
        if ( v51 )
          *(_WORD *)(16LL * v44 + v51 + 26) |= 1u;
        goto LABEL_59;
      }
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), v38);
    }
    else
    {
      if ( a1 )
      {
        for ( n = 0; n != 2; ++n )
        {
          if ( *(_QWORD *)(a1 + 8 * n + 48) == *(_QWORD *)(*v23 + 184LL) )
            *(_QWORD *)(a1 + 8 * n + 48) = 0;
        }
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
      v32 = 0;
      if ( !inserted )
        goto LABEL_59;
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      v33 = inserted;
      *((CLFS_LSN *)inserted + 2) = Buffer[2];
      v33[30] |= 1u;
      v34 = 0;
      for ( ii = 0; ii < v24; ii += 512 )
      {
        *(_WORD *)&v33[2 * v34 + 36] = *((_WORD *)&Buffer[4].ullOffset + v34 + 2);
        v34 = (unsigned int)(v34 + 1);
      }
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
  }
  else
  {
    v32 = v59;
  }
LABEL_59:
  if ( v52 )
    CcUnpinData(v52);
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v32 )
  {
    if ( a1 )
    {
      for ( jj = 0; jj != 2; ++jj )
      {
        if ( *(_QWORD *)(a1 + 8 * jj + 48) == *(_QWORD *)(*v23 + 184LL) )
          *(_QWORD *)(a1 + 8 * jj + 48) = 0;
      }
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
  }
  if ( v40 )
    NtfsReleaseFcbEx(a1, v50, 0);
}

```

## disassembly

```asm
0x140100f80  mov     rax, rsp
0x140100f83  mov     [rax+20h], r9
0x140100f87  mov     [rax+18h], r8
0x140100f8b  mov     [rax+10h], rdx
0x140100f8f  mov     [rax+8], rcx
0x140100f93  push    rbx
0x140100f94  push    rsi
0x140100f95  push    rdi
0x140100f96  push    r12
0x140100f98  push    r13
0x140100f9a  push    r14
0x140100f9c  push    r15
0x140100f9e  sub     rsp, 0C0h
0x140100fa5  mov     r14, r8
0x140100fa8  mov     rsi, rdx
0x140100fab  mov     rbx, rcx
0x140100fae  xor     r8d, r8d
0x140100fb1  mov     [rax-50h], r8
0x140100fb5  mov     [rsp+0F8h+VirtualAddress], r8
0x140100fba  mov     [rax-58h], r8
0x140100fbe  mov     [rax-60h], r8
0x140100fc2  mov     rdx, [rdx+18h]
0x140100fc6  mov     rax, [rdx+0B8h]
0x140100fcd  mov     [rsp+0F8h+var_70], rax
0x140100fd5  mov     rcx, [rax+140h]
0x140100fdc  mov     [rsp+0F8h+var_48], rcx
0x140100fe4  mov     [rsp+0F8h+NewElement], r8b
0x140100fe9  mov     [rsp+0F8h+var_9C], r8d
0x140100fee  mov     rdi, [rsp+0F8h+Buffer]
0x140100ff6  test    rdi, rdi
0x140100ff9  jnz     short loc_140101009
0x140100ffb  cmp     [rsp+0F8h+arg_30], r8
0x140101003  jz      loc_1401015EF
0x140101009  mov     [rsp+0F8h+var_40], rax
0x140101011  mov     [rsp+0F8h+var_A7], r8b
0x140101016  mov     [rsp+0F8h+var_98], r8d
0x14010101b  mov     [rsp+0F8h+var_88], r8
0x140101020  mov     al, r8b
0x140101023  mov     [rsp+0F8h+arg_70], al
0x14010102a  mov     [rsp+0F8h+var_A8], al
0x14010102e  mov     r12b, r8b
0x140101031  mov     [rsp+0F8h+var_A6], r8b
0x140101036  mov     [rsp+0F8h+var_68], r8
0x14010103e  lea     r13, [rcx+118h]
0x140101045  mov     [rsp+0F8h+var_80], r13
0x14010104a  cmp     [rsp+0F8h+arg_48], r8d
0x140101052  jnz     short loc_14010108D
0x140101054  cmp     [rsi+30h], r8
0x140101058  jnz     short loc_14010108D
0x14010105a  mov     [rsp+0F8h+var_D0], r8
0x14010105f  mov     [rsp+0F8h+Bcb], r8
0x140101064  xor     r9d, r9d
0x140101067  mov     rcx, rbx
0x14010106a  call    NtfsCreateInternalAttributeStream
0x14010106f  mov     rax, [rsi+18h]
0x140101073  mov     rsi, [rax+118h]
0x14010107a  mov     [rsp+0F8h+FileObject], rsi
0x140101082  mov     r9, [rsp+0F8h+FileOffset]
0x14010108a  xor     r8d, r8d
0x14010108d  test    rdi, rdi
0x140101090  jz      loc_140101356
0x140101096  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x14010109d  mov     [rdi+10h], rax
0x1401010a1  mov     [rdi+1Eh], r8b
0x1401010a5  mov     rax, [r9]
0x1401010a8  shr     rax, 0Ch
0x1401010ac  mov     [rdi], rax
0x1401010af  mov     r15d, [rsp+0F8h+Length]
0x1401010b7  mov     eax, r15d
0x1401010ba  shr     eax, 0Ch
0x1401010bd  mov     [rdi+18h], eax
0x1401010c0  mov     rax, [rsp+0F8h+arg_20]
0x1401010c8  mov     rax, [rax]
0x1401010cb  shr     rax, 0Ch
0x1401010cf  mov     eax, eax
0x1401010d1  mov     [rdi+8], rax
0x1401010d5  movzx   eax, [rsp+0F8h+arg_68]
0x1401010dd  mov     [rdi+1Ch], ax
0x1401010e1  mov     rcx, [r14+60h]
0x1401010e5  mov     rdx, [r9]
0x1401010e8  lea     rax, [rdx+r15]
0x1401010ec  cmp     rax, rcx
0x1401010ef  jbe     short loc_1401010F8
0x1401010f1  sub     ecx, edx
0x1401010f3  mov     [rdi+20h], ecx
0x1401010f6  jmp     short loc_1401010FC
0x1401010f8  mov     [rdi+20h], r15d
0x1401010fc  mov     rcx, [r14+100h]; FastMutex
0x140101103  call    cs:__imp_ExAcquireFastMutex
0x14010110a  nop     dword ptr [rax+rax+00h]
0x14010110f  mov     esi, 1
0x140101114  mov     [rsp+0F8h+var_98], esi
0x140101118  mov     eax, [rdi+18h]
0x14010111b  xor     r12d, r12d
0x14010111e  cmp     [rsp+0F8h+arg_58], r12d
0x140101126  jz      short loc_140101155
0x140101128  or      byte ptr [rdi+1Eh], 2
0x14010112c  shl     eax, 4
0x14010112f  lea     r8d, [rax+24h]; BufferSize
0x140101133  lea     rcx, [r14+98h]; Table
0x14010113a  lea     r9, [rsp+0F8h+NewElement]; NewElement
0x14010113f  mov     rdx, rdi; Buffer
0x140101142  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140101149  nop     dword ptr [rax+rax+00h]
0x14010114e  mov     [rsp+0F8h+var_88], rax
0x140101153  jmp     short loc_140101187
0x140101155  lea     rcx, [rsp+0F8h+var_9C]
0x14010115a  mov     [rsp+0F8h+var_D0], rcx
0x14010115f  mov     [rsp+0F8h+Bcb], r12
0x140101164  mov     r9d, eax
0x140101167  mov     r8, [rdi+8]
0x14010116b  mov     rdx, r14
0x14010116e  mov     rcx, [rsp+0F8h+var_48]
0x140101176  mov     rcx, [rcx+10h]
0x14010117a  call    TxfInsertNewTopsRange
0x14010117f  mov     [rsp+0F8h+var_68], rax
0x140101187  mov     rcx, [r14+100h]; FastMutex
0x14010118e  call    cs:__imp_ExReleaseFastMutex
0x140101195  nop     dword ptr [rax+rax+00h]
0x14010119a  mov     [rsp+0F8h+var_98], r12d
0x14010119f  cmp     [rsp+0F8h+arg_48], r12d
0x1401011a7  mov     r12, [rsp+0F8h+FileObject]
0x1401011af  jnz     short loc_1401011E8
0x1401011b1  lea     rax, [rsp+0F8h+Src]
0x1401011b9  mov     [rsp+0F8h+var_D0], rax; Buffer
0x1401011be  lea     rax, [rsp+0F8h+var_58]
0x1401011c6  mov     [rsp+0F8h+Bcb], rax; Bcb
0x1401011cb  mov     r9d, esi; Flags
0x1401011ce  mov     r8d, r15d; Length
0x1401011d1  mov     rdx, [rsp+0F8h+FileOffset]; FileOffset
0x1401011d9  mov     rcx, r12; FileObject
0x1401011dc  call    cs:__imp_CcMapData
0x1401011e3  nop     dword ptr [rax+rax+00h]
0x1401011e8  cmp     [rsp+0F8h+arg_48], 0
0x1401011f0  jz      short loc_14010122D
0x1401011f2  mov     rcx, [rsp+0F8h+var_70]
0x1401011fa  mov     rcx, [rcx+68h]
0x1401011fe  add     rcx, 40h ; '@'; Resource
0x140101202  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140101209  nop     dword ptr [rax+rax+00h]
0x14010120e  test    eax, eax
0x140101210  jnz     short loc_14010122D
0x140101212  xor     r9d, r9d
0x140101215  xor     r8d, r8d
0x140101218  mov     rdx, [rsp+0F8h+var_70]
0x140101220  mov     rcx, rbx
0x140101223  call    NtfsAcquireSharedFcb
0x140101228  mov     [rsp+0F8h+var_A7], sil
0x14010122d  mov     rdx, [r13+0]
0x140101231  mov     rcx, rbx
0x140101234  call    NtfsAcquireScbPagingResourceShared
0x140101239  mov     [rsp+0F8h+arg_70], al
0x140101240  mov     [rsp+0F8h+var_A8], al
0x140101244  test    rbx, rbx
0x140101247  jz      short loc_140101290
0x140101249  mov     [rsp+0F8h+var_78], 0
0x140101254  xor     ecx, ecx
0x140101256  mov     [rsp+0F8h+var_78], ecx
0x14010125d  cmp     ecx, 2
0x140101260  jnb     short loc_140101290
0x140101262  mov     r8d, ecx
0x140101265  mov     rdx, [rbx+rcx*8+30h]
0x14010126a  test    rdx, rdx
0x14010126d  jz      short loc_140101280
0x14010126f  mov     rax, [r13+0]
0x140101273  cmp     rdx, [rax+0B8h]
0x14010127a  jz      short loc_140101280
0x14010127c  add     ecx, esi
0x14010127e  jmp     short loc_140101256
0x140101280  mov     rax, [r13+0]
0x140101284  mov     rcx, [rax+0B8h]
0x14010128b  mov     [rbx+r8*8+30h], rcx
0x140101290  mov     rcx, [r13+0]
0x140101294  lea     rax, [rsp+0F8h+VirtualAddress]
0x140101299  mov     [rsp+0F8h+var_C8], rax; Buffer
0x14010129e  lea     rax, [rsp+0F8h+var_60]
0x1401012a6  mov     [rsp+0F8h+var_D0], rax; Bcb
0x1401012ab  mov     dword ptr [rsp+0F8h+Bcb], 3; Flags
0x1401012b3  xor     r9d, r9d; Zero
0x1401012b6  mov     r8d, r15d; Length
0x1401012b9  mov     rdx, [rsp+0F8h+arg_20]; FileOffset
0x1401012c1  mov     rcx, [rcx+118h]; FileObject
0x1401012c8  call    cs:__imp_CcPreparePinWrite
0x1401012cf  nop     dword ptr [rax+rax+00h]
0x1401012d4  cmp     [rsp+0F8h+arg_48], 0
0x1401012dc  jz      short loc_1401012F8
0x1401012de  mov     r9, [rsp+0F8h+VirtualAddress]; VirtualAddress
0x1401012e3  mov     r8d, r15d; Length
0x1401012e6  mov     rdx, [rsp+0F8h+FileOffset]; StartingOffset
0x1401012ee  mov     rcx, r12; FileObject
0x1401012f1  call    TxfReadFileNonCached
0x1401012f6  jmp     short loc_14010130D
0x1401012f8  mov     r8, r15; Size
0x1401012fb  mov     rdx, [rsp+0F8h+Src]; Src
0x140101303  mov     rcx, [rsp+0F8h+VirtualAddress]; void *
0x140101308  call    memmove
0x14010130d  xor     r10d, r10d
0x140101310  xor     r9d, r9d
0x140101313  mov     [rsp+0F8h+var_A0], r10d
0x140101318  mov     [rsp+0F8h+var_A4], r9d
0x14010131d  cmp     r9d, r15d
0x140101320  jnb     short loc_14010134C
0x140101322  mov     rax, [rsp+0F8h+VirtualAddress]
0x140101327  movzx   ecx, word ptr [r9+rax]
0x14010132c  mov     [rdi+r10*2+24h], cx
0x140101332  movzx   ecx, word ptr [rdi+1Ch]
0x140101336  mov     rax, [rsp+0F8h+VirtualAddress]
0x14010133b  mov     [r9+rax], cx
0x140101340  add     r10d, esi
0x140101343  add     r9d, 200h
0x14010134a  jmp     short loc_140101313
0x14010134c  mov     r12b, sil
0x14010134f  mov     [rsp+0F8h+var_A6], sil
0x140101354  jmp     short loc_140101363
0x140101356  mov     esi, 1
0x14010135b  mov     r15d, [rsp+0F8h+Length]
0x140101363  mov     r8, [rsp+0F8h+FileObject]
0x14010136b  mov     r8, [r8+18h]
0x14010136f  mov     eax, [rsp+0F8h+arg_60]
0x140101376  mov     [rsp+0F8h+var_B8], eax
0x14010137a  mov     eax, [rsp+0F8h+arg_50]
0x140101381  mov     [rsp+0F8h+var_C0], eax
0x140101385  mov     [rsp+0F8h+var_C8], rdi
0x14010138a  mov     rax, [rsp+0F8h+arg_40]
0x140101392  mov     [rsp+0F8h+var_D0], rax
0x140101397  mov     rax, [rsp+0F8h+arg_38]
0x14010139f  mov     [rsp+0F8h+Bcb], rax
0x1401013a4  mov     r9, [rsp+0F8h+arg_30]
0x1401013ac  mov     r8, [r8+0B8h]
0x1401013b3  mov     rdx, r14
0x1401013b6  mov     rcx, rbx
0x1401013b9  call    TxfDoWriteFileLogging
0x1401013be  nop
0x1401013bf  test    rdi, rdi
0x1401013c2  jz      loc_140101556
0x1401013c8  lea     rcx, [rdi+10h]; plsn
0x1401013cc  call    cs:__imp_ClfsLsnInvalid
0x1401013d3  nop     dword ptr [rax+rax+00h]
0x1401013d8  test    al, al
0x1401013da  jnz     loc_14010147E
0x1401013e0  test    rbx, rbx
0x1401013e3  jz      short loc_14010140B
0x1401013e5  xor     edx, edx
0x1401013e7  mov     rax, [r13+0]
0x1401013eb  mov     rcx, [rax+0B8h]
0x1401013f2  cmp     [rbx+rdx*8+30h], rcx
0x1401013f7  jnz     short loc_140101402
0x1401013f9  mov     qword ptr [rbx+rdx*8+30h], 0
0x140101402  add     rdx, rsi
0x140101405  cmp     rdx, 2
0x140101409  jnz     short loc_1401013E7
0x14010140b  mov     rcx, [r13+0]
0x14010140f  mov     rcx, [rcx+10h]; Resource
0x140101413  call    cs:__imp_ExReleaseResourceLite
0x14010141a  nop     dword ptr [rax+rax+00h]
0x14010141f  xor     r12b, r12b
0x140101422  cmp     [rsp+0F8h+var_88], 0
0x140101428  jz      loc_14010155E
0x14010142e  mov     rcx, [r14+100h]; FastMutex
0x140101435  call    cs:__imp_ExAcquireFastMutex
0x14010143c  nop     dword ptr [rax+rax+00h]
0x140101441  mov     rax, [rdi+10h]
0x140101445  mov     r9, [rsp+0F8h+var_88]
0x14010144a  mov     [r9+10h], rax
0x14010144e  or      [r9+1Eh], sil
0x140101452  xor     edx, edx
0x140101454  xor     r8d, r8d
0x140101457  test    r15d, r15d
0x14010145a  jz      loc_140101525
0x140101460  movzx   eax, word ptr [rdi+rdx*2+24h]
0x140101465  mov     [r9+rdx*2+24h], ax
0x14010146b  add     edx, esi
0x14010146d  add     r8d, 200h
0x140101474  cmp     r8d, r15d
0x140101477  jb      short loc_140101460
0x140101479  jmp     loc_140101525
0x14010147e  test    r12b, r12b
0x140101481  jz      short loc_1401014A3
0x140101483  xor     r8d, r8d
0x140101486  test    r15d, r15d
0x140101489  jz      short loc_1401014A3
0x14010148b  xor     ecx, ecx
0x14010148d  mov     rax, [rsp+0F8h+VirtualAddress]
0x140101492  mov     [r8+rax], cx
0x140101497  add     r8d, 200h
0x14010149e  cmp     r8d, r15d
0x1401014a1  jb      short loc_14010148B
0x1401014a3  mov     r12b, [rsp+0F8h+arg_70]
0x1401014ab  test    r12b, r12b
0x1401014ae  jz      short loc_1401014F2
0x1401014b0  test    rbx, rbx
0x1401014b3  jz      short loc_1401014DB
0x1401014b5  xor     edx, edx
0x1401014b7  mov     rax, [r13+0]
0x1401014bb  mov     rcx, [rax+0B8h]
0x1401014c2  cmp     [rbx+rdx*8+30h], rcx
0x1401014c7  jnz     short loc_1401014D2
0x1401014c9  mov     qword ptr [rbx+rdx*8+30h], 0
0x1401014d2  add     rdx, rsi
0x1401014d5  cmp     rdx, 2
  ... truncated ...
```
