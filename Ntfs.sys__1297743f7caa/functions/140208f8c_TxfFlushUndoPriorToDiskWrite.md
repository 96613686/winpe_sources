# TxfFlushUndoPriorToDiskWrite

- ea: `0x140208f8c`
- end: `0x140209556`
- name: `TxfFlushUndoPriorToDiskWrite`
- size: `1482`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1400177d0`
- `0x14010ae4c`
- `0x140268658`
- `0x140296df4`

## callees

- `0x140007ea0`
- `0x14002f45c`
- `0x14002f6d8`
- `0x140034560`
- `0x1400592c0`
- `0x1400b6e90`
- `0x14018a8a0`
- `0x140208f8c`
- `0x140209960`
- `0x140214e38`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x1402093ae`
- `ntoskrnl!CcPinRead` at `0x1402093ae`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14020910c`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14020910c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14020931b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14020931b`
- `ntoskrnl!CcUnpinData` at `0x1402093ec`
- `ntoskrnl!CcUnpinData` at `0x1402093ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209443`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b3c87`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce84c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209443`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b3c87`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce84c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402090bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402094c3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402090bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402094c3`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020912b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402092df`
- `ntoskrnl!ExReleaseFastMutex` at `0x14020912b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402092df`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140209148`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14020916e`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140209148`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14020916e`
- `ntoskrnl!ExRaiseStatus` at `0x140209156`
- `ntoskrnl!ExRaiseStatus` at `0x14020917c`
- `ntoskrnl!ExRaiseStatus` at `0x140209156`
- `ntoskrnl!ExRaiseStatus` at `0x14020917c`
- `ntoskrnl!CcFlushCache` at `0x1402093db`
- `ntoskrnl!CcFlushCache` at `0x1402093db`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402092c1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402092c1`

## pseudocode

```c
void __fastcall TxfFlushUndoPriorToDiskWrite(_DWORD *a1, __int64 a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v5; // r15
  __int64 v7; // r12
  _QWORD *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // r14
  _QWORD *v11; // r13
  ULONG i; // eax
  const CLFS_LSN *v13; // rax
  const CLFS_LSN *v14; // r12
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  unsigned __int64 v17; // r8
  __int64 v18; // rdx
  CLFS_LSN *v19; // r15
  CLFS_LSN v20; // rbx
  ULONGLONG v21; // rax
  char v22; // r15
  __int64 j; // rcx
  __int64 v24; // rdx
  __int64 k; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 m; // rdx
  char v29; // [rsp+40h] [rbp-E8h]
  int v30; // [rsp+44h] [rbp-E4h]
  ULONG DeleteCount; // [rsp+54h] [rbp-D4h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp-D0h] BYREF
  PVOID Bcb; // [rsp+60h] [rbp-C8h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-C0h]
  _QWORD *v35; // [rsp+70h] [rbp-B8h]
  __int64 v36; // [rsp+78h] [rbp-B0h]
  NTSTATUS Exception[4]; // [rsp+80h] [rbp-A8h] BYREF
  int v38; // [rsp+90h] [rbp-98h]
  PVOID RestartKey; // [rsp+98h] [rbp-90h] BYREF
  PVOID v40[2]; // [rsp+A0h] [rbp-88h] BYREF
  __int128 MatchData; // [rsp+B0h] [rbp-78h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-68h]
  __int128 v43; // [rsp+D0h] [rbp-58h]
  int v44; // [rsp+E0h] [rbp-48h]

  v5 = a3;
  v40[1] = a1;
  v7 = *(_QWORD *)(a2 + 24);
  MatchData = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  FileOffset.QuadPart = 0;
  DeleteCount = 0;
  *(_OWORD *)Exception = 0;
  v36 = 0;
  v35 = 0;
  v30 = -1;
  RestartKey = 0;
  Bcb = 0;
  v40[0] = 0;
  v29 = 0;
  v8 = 0;
  v34 = 0;
  LOBYTE(a3) = 1;
  v9 = TxfCurrentWritableVersion(*(_QWORD *)(v7 + 528), 0, a3);
  v10 = v9;
  v36 = v9;
  if ( v9 && (*(_DWORD *)(v9 + 8) & 1) == 0 )
  {
    v11 = *(_QWORD **)(*(_QWORD *)(v7 + 184) + 320LL);
    v35 = v11;
    v8 = v11 + 35;
    v34 = v11 + 35;
    LfsFlushToLsn(*(_QWORD *)(v11[2] + 232LL), v11[45]);
    if ( *(_BYTE *)(v7 + 460) )
    {
      v17 = v5;
      v18 = -*(_DWORD *)(v7 + 452);
      v5 &= v18;
      a4 = (v18 & (v17 + *(_DWORD *)(v7 + 452) - 1 + a4)) - v5;
    }
    *(_QWORD *)&MatchData = v5 >> 12;
    DWORD2(v42) = (a4 + 4095) >> 12;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 256));
    for ( i = 0; ; i = 1 )
    {
      v13 = (const CLFS_LSN *)RtlEnumerateGenericTableLikeADirectory(
                                (PRTL_AVL_TABLE)(v10 + 152),
                                TxfMatchPageRange,
                                &MatchData,
                                i,
                                &RestartKey,
                                &DeleteCount,
                                &MatchData);
      v14 = v13;
      if ( !v13 )
        break;
      v19 = (CLFS_LSN *)&v13[2];
      if ( !ClfsLsnInvalid(v13 + 2) )
      {
        v20 = *v19;
        ExReleaseFastMutex(*(PFAST_MUTEX *)(v10 + 256));
        v21 = v14[1].ullOffset >> 4;
        if ( (_DWORD)v21 != v30 )
        {
          v30 = v14[1].ullOffset >> 4;
          FileOffset.QuadPart = (unsigned int)((_DWORD)v21 << 16);
          v22 = v29;
          if ( !v29 && !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(*v8 + 16LL)) )
          {
            v22 = NtfsAcquireScbPagingResourceShared(a1, *v8);
            v29 = v22;
            for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
            {
              v24 = *(_QWORD *)&a1[2 * j + 12];
              if ( !v24 || v24 == *(_QWORD *)(*v8 + 184LL) )
              {
                *(_QWORD *)&a1[2 * (unsigned int)j + 12] = *(_QWORD *)(*v8 + 184LL);
                break;
              }
            }
          }
          CcPinRead(*(PFILE_OBJECT *)(*v8 + 280LL), &FileOffset, 0x10000u, 5u, &Bcb, v40);
          CcFlushCache(
            (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*v8 + 288LL) + 16LL),
            &FileOffset,
            0x10000u,
            (PIO_STATUS_BLOCK)Exception);
          CcUnpinData(Bcb);
          Bcb = 0;
          if ( v22 )
          {
            if ( a1 )
            {
              for ( k = 0; (unsigned int)k < 2; k = (unsigned int)(k + 1) )
              {
                if ( *(_QWORD *)&a1[2 * k + 12] == *(_QWORD *)(*v8 + 184LL) )
                  *(_QWORD *)&a1[2 * k + 12] = 0;
              }
            }
            ExReleaseResourceLite(*(PERESOURCE *)(*v8 + 16LL));
            v29 = 0;
          }
          v26 = (unsigned int)Exception[0];
          if ( Exception[0] < 0 )
          {
            a1[6] = Exception[0];
            if ( NtfsStatusDebugFlags
              && (_DWORD)v26
              && (_DWORD)v26 != 294
              && (unsigned int)(v26 - 298) > 1
              && (unsigned int)v26 < 0xFFFFFFED
              && (_DWORD)v26 != -1073741608
              && (_DWORD)v26 != -1073741802
              && (_DWORD)v26 != -1073741807
              && (unsigned int)(v26 + 2147483643) > 1
              && (_DWORD)v26 != 259 )
            {
              NtfsStatusTraceAndDebugInternal(a1, v26, 3411316);
            }
            v15 = FsRtlNormalizeNtstatus(Exception[0], -1073741591);
            ExRaiseStatus(v15);
          }
          v38 = v30;
          v19 = (CLFS_LSN *)&v14[2];
        }
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 64LL) + 4LL) & 0x1000) == 0
          && (unsigned __int8)TxfTryEnterFlushSyncRegion(v11) )
        {
          ((void (__fastcall *)(_QWORD, _QWORD))TxfFlushToLsn)(v11, (CLFS_LSN)v20.ullOffset);
          TxfLeaveFlushSyncRegion(v11);
        }
        v27 = (unsigned int)Exception[0];
        if ( Exception[0] < 0 )
        {
          a1[6] = Exception[0];
          if ( NtfsStatusDebugFlags
            && (_DWORD)v27
            && (_DWORD)v27 != 294
            && (unsigned int)(v27 - 298) > 1
            && (unsigned int)v27 < 0xFFFFFFED
            && (_DWORD)v27 != -1073741608
            && (_DWORD)v27 != -1073741802
            && (_DWORD)v27 != -1073741807
            && (unsigned int)(v27 + 2147483643) > 1
            && (_DWORD)v27 != 259 )
          {
            NtfsStatusTraceAndDebugInternal(a1, v27, 3411346);
          }
          v16 = FsRtlNormalizeNtstatus(Exception[0], -1073741591);
          ExRaiseStatus(v16);
        }
        ExAcquireFastMutex(*(PFAST_MUTEX *)(v10 + 256));
        BYTE6(v14[3].ullOffset) |= 0x20u;
        *v19 = CLFS_LSN_INVALID_EXT;
      }
      DWORD2(v42) += MatchData - v14->offset.idxRecord;
      *(CLFS_LSN *)&MatchData = *v14;
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v10 + 256));
  }
  if ( v29 )
  {
    if ( a1 )
    {
      for ( m = 0; m != 2; ++m )
      {
        if ( *(_QWORD *)&a1[2 * m + 12] == *(_QWORD *)(*v8 + 184LL) )
          *(_QWORD *)&a1[2 * m + 12] = 0;
      }
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*v8 + 16LL));
  }
  if ( v10 )
    TxfDereferenceTxfVscb((PVOID)v10);
}

```

## disassembly

```asm
0x140208f8c  mov     r11, rsp
0x140208f8f  push    rbx
0x140208f90  push    rsi
0x140208f91  push    rdi
0x140208f92  push    r12
0x140208f94  push    r13
0x140208f96  push    r14
0x140208f98  push    r15
0x140208f9a  sub     rsp, 0F0h
0x140208fa1  mov     rax, cs:__security_cookie
0x140208fa8  xor     rax, rsp
0x140208fab  mov     [rsp+128h+var_40], rax
0x140208fb3  mov     rbx, r9
0x140208fb6  mov     r15, r8
0x140208fb9  mov     rdi, rcx
0x140208fbc  mov     [rsp+128h+var_80], rcx
0x140208fc4  mov     r12, [rdx+18h]
0x140208fc8  xorps   xmm0, xmm0
0x140208fcb  xor     eax, eax
0x140208fcd  movups  xmmword ptr [r11-78h], xmm0
0x140208fd2  movups  xmmword ptr [r11-68h], xmm0
0x140208fd7  movups  xmmword ptr [r11-58h], xmm0
0x140208fdc  mov     [r11-48h], eax
0x140208fe0  mov     qword ptr [rsp+128h+FileOffset], rax
0x140208fe5  mov     [rsp+128h+var_D4], eax
0x140208fe9  movups  xmmword ptr [rsp+128h+Exception], xmm0
0x140208ff1  mov     [rsp+128h+var_B0], rax
0x140208ff6  mov     [rsp+128h+var_B8], rax
0x140208ffb  mov     [rsp+128h+var_E4], 0FFFFFFFFh
0x140209003  mov     [r11-90h], rax
0x14020900a  mov     [rsp+128h+NextFlag], eax
0x14020900e  mov     [rsp+128h+Bcb], rax
0x140209013  mov     [r11-88h], rax
0x14020901a  mov     [rsp+128h+var_E8], al
0x14020901e  mov     [rsp+128h+var_E7], al
0x140209022  mov     esi, eax
0x140209024  mov     [rsp+128h+var_C0], rax
0x140209029  mov     r8b, 1
0x14020902c  xor     edx, edx
0x14020902e  mov     rcx, [r12+210h]
0x140209036  call    TxfCurrentWritableVersion
0x14020903b  mov     r14, rax
0x14020903e  mov     [rsp+128h+var_B0], rax
0x140209043  test    rax, rax
0x140209046  jz      loc_140209507
0x14020904c  mov     eax, [rax+8]
0x14020904f  test    al, 1
0x140209051  jnz     loc_140209507
0x140209057  mov     rax, [r12+0B8h]
0x14020905f  mov     r13, [rax+140h]
0x140209066  mov     [rsp+128h+var_B8], r13
0x14020906b  lea     rsi, [r13+118h]
0x140209072  mov     [rsp+128h+var_C0], rsi
0x140209077  mov     rcx, [r13+10h]
0x14020907b  mov     rdx, [rsi+50h]
0x14020907f  mov     rcx, [rcx+0E8h]
0x140209086  call    LfsFlushToLsn
0x14020908b  cmp     byte ptr [r12+1CCh], 0
0x140209094  jnz     loc_14020928E
0x14020909a  shr     r15, 0Ch
0x14020909e  mov     qword ptr [rsp+128h+MatchData], r15
0x1402090a6  lea     rax, [rbx+0FFFh]
0x1402090ad  shr     rax, 0Ch
0x1402090b1  mov     [rsp+128h+var_60], eax
0x1402090b8  mov     rcx, [r14+100h]; FastMutex
0x1402090bf  call    cs:__imp_ExAcquireFastMutex
0x1402090c6  nop     dword ptr [rax+rax+00h]
0x1402090cb  mov     eax, [rsp+128h+NextFlag]
0x1402090cf  lea     rcx, [r14+98h]; Table
0x1402090d6  lea     rdx, [rsp+128h+MatchData]
0x1402090de  mov     [rsp+128h+Buffer], rdx; Buffer
0x1402090e3  lea     rdx, [rsp+128h+var_D4]
0x1402090e8  mov     [rsp+128h+DeleteCount], rdx; DeleteCount
0x1402090ed  lea     rdx, [rsp+128h+var_90]
0x1402090f5  mov     [rsp+128h+RestartKey], rdx; RestartKey
0x1402090fa  mov     r9d, eax; NextFlag
0x1402090fd  lea     r8, [rsp+128h+MatchData]; MatchData
0x140209105  lea     rdx, TxfMatchPageRange; MatchFunction
0x14020910c  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x140209113  nop     dword ptr [rax+rax+00h]
0x140209118  mov     r12, rax
0x14020911b  test    rax, rax
0x14020911e  jnz     loc_1402092BA
0x140209124  mov     rcx, [r14+100h]; FastMutex
0x14020912b  call    cs:__imp_ExReleaseFastMutex
0x140209132  nop     dword ptr [rax+rax+00h]
0x140209137  jmp     loc_140209507
0x14020913c  mov     edx, 0C00000E9h; GenericException
0x140209141  mov     ecx, [rsp+128h+Exception]; Exception
0x140209148  call    cs:__imp_FsRtlNormalizeNtstatus
0x14020914f  nop     dword ptr [rax+rax+00h]
0x140209154  mov     ecx, eax; Status
0x140209156  call    cs:__imp_ExRaiseStatus
0x140209162  mov     edx, 0C00000E9h; GenericException
0x140209167  mov     ecx, [rsp+128h+Exception]; Exception
0x14020916e  call    cs:__imp_FsRtlNormalizeNtstatus
0x140209175  nop     dword ptr [rax+rax+00h]
0x14020917a  mov     ecx, eax; Status
0x14020917c  call    cs:__imp_ExRaiseStatus
0x140209188  mov     [rdi+18h], edx
0x14020918b  mov     al, cs:NtfsStatusDebugFlags
0x140209191  test    al, al
0x140209193  jz      short loc_14020913C
0x140209195  test    edx, edx
0x140209197  jz      short loc_14020913C
0x140209199  cmp     edx, 126h
0x14020919f  jz      short loc_14020913C
0x1402091a1  lea     eax, [rdx-12Ah]
0x1402091a7  cmp     eax, 1
0x1402091aa  jbe     short loc_14020913C
0x1402091ac  cmp     edx, 0FFFFFFEDh
0x1402091af  jnb     short loc_14020913C
0x1402091b1  cmp     edx, 0C00000D8h
0x1402091b7  jz      short loc_14020913C
0x1402091b9  cmp     edx, 0C0000016h
0x1402091bf  jz      loc_14020913C
0x1402091c5  cmp     edx, 0C0000011h
0x1402091cb  jz      loc_14020913C
0x1402091d1  lea     eax, [rdx+7FFFFFFBh]
0x1402091d7  cmp     eax, 1
0x1402091da  jbe     loc_14020913C
0x1402091e0  cmp     edx, 103h
0x1402091e6  jz      loc_14020913C
0x1402091ec  mov     r8d, 340D74h
0x1402091f2  mov     rcx, rdi
0x1402091f5  call    NtfsStatusTraceAndDebugInternal
0x1402091fa  jmp     loc_14020913C
0x1402091ff  mov     [rdi+18h], edx
0x140209202  mov     al, cs:NtfsStatusDebugFlags
0x140209208  test    al, al
0x14020920a  jz      loc_140209162
0x140209210  test    edx, edx
0x140209212  jz      loc_140209162
0x140209218  cmp     edx, 126h
0x14020921e  jz      loc_140209162
0x140209224  lea     eax, [rdx-12Ah]
0x14020922a  cmp     eax, 1
0x14020922d  jbe     loc_140209162
0x140209233  cmp     edx, 0FFFFFFEDh
0x140209236  jnb     loc_140209162
0x14020923c  cmp     edx, 0C00000D8h
0x140209242  jz      loc_140209162
0x140209248  cmp     edx, 0C0000016h
0x14020924e  jz      loc_140209162
0x140209254  cmp     edx, 0C0000011h
0x14020925a  jz      loc_140209162
0x140209260  lea     eax, [rdx+7FFFFFFBh]
0x140209266  cmp     eax, 1
0x140209269  jbe     loc_140209162
0x14020926f  cmp     edx, 103h
0x140209275  jz      loc_140209162
0x14020927b  mov     r8d, 340D92h
0x140209281  mov     rcx, rdi
0x140209284  call    NtfsStatusTraceAndDebugInternal
0x140209289  jmp     loc_140209162
0x14020928e  mov     r8, r15
0x140209291  mov     ecx, [r12+1C4h]
0x140209299  mov     eax, ecx
0x14020929b  neg     eax
0x14020929d  movsxd  rdx, eax
0x1402092a0  and     r15, rdx
0x1402092a3  lea     eax, [rcx-1]
0x1402092a6  movsxd  rcx, eax
0x1402092a9  add     rbx, rcx
0x1402092ac  add     rbx, r8
0x1402092af  and     rbx, rdx
0x1402092b2  sub     rbx, r15
0x1402092b5  jmp     loc_14020909A
0x1402092ba  lea     r15, [rax+10h]
0x1402092be  mov     rcx, r15; plsn
0x1402092c1  call    cs:__imp_ClfsLsnInvalid
0x1402092c8  nop     dword ptr [rax+rax+00h]
0x1402092cd  test    al, al
0x1402092cf  jnz     loc_1402094DF
0x1402092d5  mov     rbx, [r15]
0x1402092d8  mov     rcx, [r14+100h]; FastMutex
0x1402092df  call    cs:__imp_ExReleaseFastMutex
0x1402092e6  nop     dword ptr [rax+rax+00h]
0x1402092eb  mov     rax, [r12+8]
0x1402092f0  shr     rax, 4
0x1402092f4  cmp     eax, [rsp+128h+var_E4]
0x1402092f8  jz      loc_140209473
0x1402092fe  mov     [rsp+128h+var_E4], eax
0x140209302  shl     eax, 10h
0x140209305  mov     qword ptr [rsp+128h+FileOffset], rax
0x14020930a  mov     r15b, [rsp+128h+var_E8]
0x14020930f  test    r15b, r15b
0x140209312  jnz     short loc_14020937C
0x140209314  mov     rcx, [rsi]
0x140209317  mov     rcx, [rcx+10h]; Resource
0x14020931b  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140209322  nop     dword ptr [rax+rax+00h]
0x140209327  test    eax, eax
0x140209329  jnz     short loc_14020937C
0x14020932b  mov     rdx, [rsi]
0x14020932e  mov     rcx, rdi
0x140209331  call    NtfsAcquireScbPagingResourceShared
0x140209336  mov     r15b, al
0x140209339  mov     [rsp+128h+var_E8], al
0x14020933d  mov     [rsp+128h+var_E0], 0
0x140209345  xor     ecx, ecx
0x140209347  mov     [rsp+128h+var_E0], ecx
0x14020934b  cmp     ecx, 2
0x14020934e  jnb     short loc_14020937C
0x140209350  mov     r8d, ecx
0x140209353  mov     rdx, [rdi+rcx*8+30h]
0x140209358  test    rdx, rdx
0x14020935b  jz      short loc_14020936D
0x14020935d  mov     rax, [rsi]
0x140209360  cmp     rdx, [rax+0B8h]
0x140209367  jz      short loc_14020936D
0x140209369  inc     ecx
0x14020936b  jmp     short loc_140209347
0x14020936d  mov     rax, [rsi]
0x140209370  mov     rcx, [rax+0B8h]
0x140209377  mov     [rdi+r8*8+30h], rcx
0x14020937c  mov     rcx, [rsi]
0x14020937f  lea     rax, [rsp+128h+var_88]
0x140209387  mov     [rsp+128h+DeleteCount], rax; Buffer
0x14020938c  lea     rax, [rsp+128h+Bcb]
0x140209391  mov     [rsp+128h+RestartKey], rax; Bcb
0x140209396  mov     r9d, 5; Flags
0x14020939c  mov     r8d, 10000h; Length
0x1402093a2  lea     rdx, [rsp+128h+FileOffset]; FileOffset
0x1402093a7  mov     rcx, [rcx+118h]; FileObject
0x1402093ae  call    cs:__imp_CcPinRead
0x1402093b5  nop     dword ptr [rax+rax+00h]
0x1402093ba  mov     rax, [rsi]
0x1402093bd  mov     rcx, [rax+120h]
0x1402093c4  add     rcx, 10h; SectionObjectPointer
0x1402093c8  lea     r9, [rsp+128h+Exception]; IoStatus
0x1402093d0  mov     r8d, 10000h; Length
0x1402093d6  lea     rdx, [rsp+128h+FileOffset]; FileOffset
0x1402093db  call    cs:__imp_CcFlushCache
0x1402093e2  nop     dword ptr [rax+rax+00h]
0x1402093e7  mov     rcx, [rsp+128h+Bcb]; Bcb
0x1402093ec  call    cs:__imp_CcUnpinData
0x1402093f3  nop     dword ptr [rax+rax+00h]
0x1402093f8  mov     [rsp+128h+Bcb], 0
0x140209401  test    r15b, r15b
0x140209404  jz      short loc_140209454
0x140209406  test    rdi, rdi
0x140209409  jz      short loc_14020943C
0x14020940b  mov     [rsp+128h+var_DC], 0
0x140209413  xor     edx, edx
0x140209415  mov     [rsp+128h+var_DC], edx
0x140209419  cmp     edx, 2
0x14020941c  jnb     short loc_14020943C
0x14020941e  mov     rax, [rsi]
0x140209421  mov     rcx, [rax+0B8h]
0x140209428  cmp     [rdi+rdx*8+30h], rcx
0x14020942d  jnz     short loc_140209438
0x14020942f  mov     qword ptr [rdi+rdx*8+30h], 0
0x140209438  inc     edx
0x14020943a  jmp     short loc_140209415
0x14020943c  mov     rcx, [rsi]
0x14020943f  mov     rcx, [rcx+10h]; Resource
0x140209443  call    cs:__imp_ExReleaseResourceLite
0x14020944a  nop     dword ptr [rax+rax+00h]
0x14020944f  mov     [rsp+128h+var_E8], 0
0x140209454  mov     edx, [rsp+128h+Exception]
0x14020945b  test    edx, edx
0x14020945d  js      loc_140209188
0x140209463  mov     eax, [rsp+128h+var_E4]
0x140209467  mov     [rsp+128h+var_98], eax
0x14020946e  lea     r15, [r12+10h]
0x140209473  mov     rax, [r14+10h]
0x140209477  mov     rcx, [rax+40h]
0x14020947b  test    dword ptr [rcx+4], 1000h
0x140209482  jnz     short loc_1402094AD
0x140209484  mov     rcx, r13
0x140209487  call    TxfTryEnterFlushSyncRegion
0x14020948c  test    al, al
0x14020948e  jz      short loc_1402094AD
0x140209490  mov     [rsp+128h+var_E7], 1
0x140209495  mov     rdx, rbx
0x140209498  mov     rcx, r13
0x14020949b  call    TxfFlushToLsn
0x1402094a0  mov     rcx, r13
0x1402094a3  call    TxfLeaveFlushSyncRegion
0x1402094a8  mov     [rsp+128h+var_E7], 0
0x1402094ad  mov     edx, [rsp+128h+Exception]
0x1402094b4  test    edx, edx
0x1402094b6  js      loc_1402091FF
0x1402094bc  mov     rcx, [r14+100h]; FastMutex
0x1402094c3  call    cs:__imp_ExAcquireFastMutex
0x1402094ca  nop     dword ptr [rax+rax+00h]
0x1402094cf  or      byte ptr [r12+1Eh], 20h
0x1402094d5  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x1402094dc  mov     [r15], rax
0x1402094df  mov     eax, dword ptr [rsp+128h+MatchData]
0x1402094e6  sub     eax, [r12]
0x1402094ea  add     [rsp+128h+var_60], eax
0x1402094f1  mov     rax, [r12]
0x1402094f5  mov     qword ptr [rsp+128h+MatchData], rax
0x1402094fd  mov     eax, 1
0x140209502  jmp     loc_1402090CF
0x140209507  cmp     [rsp+128h+var_E8], 0
0x14020950c  jnz     short loc_140209537
0x14020950e  test    r14, r14
  ... truncated ...
```
