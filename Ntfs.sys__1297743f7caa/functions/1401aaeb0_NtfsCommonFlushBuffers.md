# NtfsCommonFlushBuffers

- ea: `0x1401aaeb0`
- end: `0x1401abd3a`
- name: `NtfsCommonFlushBuffers`
- size: `3722`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401aae10`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c1d0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d840`
- `0x1400113f0`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x14002b680`
- `0x140059740`
- `0x14012f3ec`
- `0x14012f980`
- `0x1401305a0`
- `0x140132210`
- `0x14013af60`
- `0x14013c320`
- `0x1401403d0`
- `0x140141a3c`
- `0x140181bb0`
- `0x1401aab70`
- `0x1401aaeb0`
- `0x1401abd40`
- `0x1401ac0d0`
- `0x1401bffe4`
- `0x1401c0130`
- `0x1401d2c84`
- `0x1402156d0`
- `0x140218890`
- `0x14021d9c4`
- `0x14021dbd0`
- `0x1402308d8`
- `0x1402326c4`

## import_xrefs

- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ab4f3`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1401ab4f3`
- `ntoskrnl!KeBugCheckEx` at `0x1401abcec`
- `ntoskrnl!KeBugCheckEx` at `0x1402adf98`
- `ntoskrnl!KeBugCheckEx` at `0x1401abcec`
- `ntoskrnl!KeBugCheckEx` at `0x1402adf98`
- `ntoskrnl!PsGetThreadProcess` at `0x1401aaffd`
- `ntoskrnl!PsGetThreadProcess` at `0x1401aaffd`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1401ab021`
- `ntoskrnl!PsUpdateDiskCounters` at `0x1401ab021`
- `ntoskrnl!IoIsSystemThread` at `0x1401aafda`
- `ntoskrnl!IoIsSystemThread` at `0x1401aafda`
- `ntoskrnl!IofCallDriver` at `0x1401ab9c2`
- `ntoskrnl!IofCallDriver` at `0x1402adf3f`
- `ntoskrnl!IofCallDriver` at `0x1401ab9c2`
- `ntoskrnl!IofCallDriver` at `0x1402adf3f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab9a4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab9d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401abcb9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf26`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf4d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf67`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab9a4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401ab9d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401abcb9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf26`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf4d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402adf67`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401abc65`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402add57`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401abc65`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402add57`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401ab92d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402ade84`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401ab92d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402ade84`

## pseudocode

```c
__int64 __fastcall NtfsCommonFlushBuffers(__int64 a1, IRP *a2)
{
  ULONG_PTR v4; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  struct _FILE_OBJECT *v6; // rax
  unsigned __int16 *FsContext; // r13
  _BYTE *FsContext2; // r8
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r12
  int v12; // r15d
  UCHAR MinorFunction; // cl
  unsigned int v14; // esi
  struct _KTHREAD *Thread; // rcx
  struct _KTHREAD *CurrentThread; // rcx
  PEPROCESS ThreadProcess; // rax
  int v18; // r15d
  __int64 v19; // r15
  struct _IO_STACK_LOCATION *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // r9d
  PFILE_OBJECT v27; // r15
  char v28; // r15
  char v29; // r15
  __int64 v30; // r15
  int v31; // edx
  int v32; // edx
  int v33; // r15d
  int v34; // r15d
  int v35; // eax
  _BYTE *v36; // r15
  __int64 i; // rax
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 j; // rax
  __int64 v42; // r8
  NTSTATUS v43; // ecx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // r8
  __int64 v53; // r15
  int v54; // r12d
  __int64 v55; // r13
  struct _IO_STACK_LOCATION *v56; // rax
  _DWORD *v57; // rax
  _DWORD *v58; // rdi
  __int64 v59; // r15
  struct _IO_STACK_LOCATION *v60; // rax
  int CurrentIrql; // edi
  unsigned int v62; // ebx
  int v64; // eax
  struct _IO_STACK_LOCATION *v65; // rcx
  unsigned int v66; // ebx
  __int64 v67; // r8
  __int64 k; // rax
  ULONG_PTR v69; // rbx
  KIRQL v70; // al
  int BugCheckParameter4; // [rsp+98h] [rbp-E8h]
  char v72; // [rsp+C8h] [rbp-B8h]
  char v73; // [rsp+C9h] [rbp-B7h]
  char v74; // [rsp+CAh] [rbp-B6h]
  char v75; // [rsp+CBh] [rbp-B5h]
  char v76; // [rsp+CCh] [rbp-B4h]
  NTSTATUS v77; // [rsp+D4h] [rbp-ACh]
  struct _IO_STACK_LOCATION *v78; // [rsp+D8h] [rbp-A8h]
  __int64 v79; // [rsp+E0h] [rbp-A0h]
  __int64 v80; // [rsp+E8h] [rbp-98h] BYREF
  _BYTE *v81; // [rsp+F0h] [rbp-90h]
  int v82; // [rsp+F8h] [rbp-88h]
  int v83; // [rsp+FCh] [rbp-84h]
  __int64 v84; // [rsp+100h] [rbp-80h]
  ULONG_PTR v85; // [rsp+108h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+110h] [rbp-70h]
  __int64 v87; // [rsp+118h] [rbp-68h]
  unsigned __int16 *v88; // [rsp+120h] [rbp-60h]
  struct _IO_STACK_LOCATION *v89; // [rsp+128h] [rbp-58h]
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp-50h] BYREF
  __int64 v92; // [rsp+198h] [rbp+18h] BYREF

  v80 = 0;
  v4 = 0;
  v85 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v78 = CurrentStackLocation;
  v6 = CurrentStackLocation->FileObject;
  FileObject = v6;
  FsContext = (unsigned __int16 *)v6->FsContext;
  if ( FsContext )
  {
    FsContext2 = v6->FsContext2;
    v81 = FsContext2;
    v9 = *((_QWORD *)FsContext + 24);
    v79 = v9;
    v10 = *(_DWORD *)(v9 + 4);
    if ( (v10 & 1) == 0 && (!FsContext2 || FsContext2[88] != 4 || (v10 & 2) == 0) )
    {
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
      __debugbreak();
    }
    v84 = *((_QWORD *)FsContext + 24);
    v11 = *((_QWORD *)FsContext + 23);
    v87 = v11;
    if ( FsContext2 )
      v12 = (unsigned __int8)FsContext2[88];
    else
      v12 = 5;
  }
  else
  {
    v9 = 0;
    v79 = 0;
    v84 = 0;
    FsContext2 = 0;
    v81 = 0;
    v11 = 0;
    v87 = 0;
    v12 = 1;
  }
  if ( v12 == 1 )
  {
    v66 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1114910);
    LOBYTE(CurrentStackLocation) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, CurrentStackLocation, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 1114911);
    return v66;
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction != 1 && (*(_DWORD *)(v9 + 4) & 0x2000000) != 0 )
  {
    v66 = -1073741662;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225634LL, 1114939);
    if ( !NtfsStatusDebugFlags )
      goto LABEL_177;
    v67 = 1114940;
    goto LABEL_176;
  }
  if ( MinorFunction == 2
    && (v12 != 2 || (*(_DWORD *)(v11 + 4) & 0x20100) != 0 || (*((_DWORD *)FsContext2 + 1) & 0x10000) != 0) )
  {
    v66 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 1114970);
    if ( !NtfsStatusDebugFlags )
      goto LABEL_177;
    v67 = 1114971;
LABEL_176:
    NtfsStatusTraceAndDebugInternal(a1, v66, v67);
LABEL_177:
    LOBYTE(CurrentStackLocation) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, v66, CurrentStackLocation, 0);
    return v66;
  }
  v89 = CurrentStackLocation;
  v75 = 0;
  v73 = 0;
  v72 = 0;
  v74 = 0;
  LOBYTE(v92) = 1;
  v76 = 0;
  v88 = FsContext;
  if ( v12 == 2 )
  {
    v64 = *(_DWORD *)(v11 + 4);
    if ( (v64 & 0x100) != 0 || (v64 & 0x20000) != 0 )
      v12 = 4;
  }
  v77 = 0;
  v14 = 0;
  if ( NtfsDiskAccountingEnabled )
  {
    Thread = a2->Tail.Overlay.Thread;
    if ( !Thread || IoIsSystemThread(Thread) )
      CurrentThread = KeGetCurrentThread();
    else
      CurrentThread = a2->Tail.Overlay.Thread;
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    PsUpdateDiskCounters(ThreadProcess, 0, 0, 0, 0, 1);
  }
  v18 = v12 - 2;
  if ( !v18 )
  {
    *(_DWORD *)(a1 + 504) = 23;
    LOBYTE(FsContext2) = 1;
    v19 = v79;
    NtfsAcquireSharedVcb(a1, v79, FsContext2);
    v75 = 1;
    if ( (*(_DWORD *)(v79 + 4) & 1) == 0 )
    {
      v14 = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_145;
      v51 = 1115046;
      goto LABEL_124;
    }
    v23 = *((_DWORD *)FsContext + 64);
    if ( (v23 & 0xFFFFF000) == 0 && v23 != 128 )
    {
      NtfsAcquireExclusiveFcb(a1, v11, FsContext, 1);
      v73 = 1;
      goto LABEL_39;
    }
    v20 = v78;
    if ( v78->MinorFunction != 1 )
    {
      v24 = *((_QWORD *)FsContext + 36);
      if ( !*(_QWORD *)(v24 + 16)
        && !*(_QWORD *)(v24 + 24)
        && (*(_DWORD *)(a1 + 436) & 0x80008) == 0
        && (*((_DWORD *)FsContext + 50) & 8) == 0
        && !*((_BYTE *)FsContext + 460) )
      {
        if ( (*((_DWORD *)FsContext + 50) & 0x10) == 0
          || (v44 = *((_QWORD *)FsContext + 23), (v45 = *(_QWORD *)(v44 + 328)) != 0) && *(_QWORD *)(v45 + 24)
          || (*(_DWORD *)(v44 + 4) & 0x20020100) != 0x20000000 )
        {
          if ( (*((_DWORD *)v81 + 1) & 0x10000) == 0 && !*((_QWORD *)FsContext + 63) && !*((_QWORD *)FsContext + 66) )
          {
            if ( (LOBYTE(v21) = 1,
                  NtfsAcquirePagingResourceSharedStarveExclusive(a1, v11, v21),
                  v74 = 1,
                  v47 = *((_QWORD *)FsContext + 36),
                  *(_QWORD *)(v47 + 16))
              || *(_QWORD *)(v47 + 24)
              || (*((_DWORD *)FsContext + 50) & 8) != 0
              || *((_BYTE *)FsContext + 460)
              || (v48 = *(_DWORD *)(*((_QWORD *)FsContext + 23) + 4LL), (*((_DWORD *)FsContext + 50) & 0x10) != 0)
              && ((v46 = *((_QWORD *)FsContext + 23), (v49 = *(_QWORD *)(v46 + 328)) == 0) || !*(_QWORD *)(v49 + 24))
              && (v48 & 0x20100) == 0
              && ((v48 & 0x20000000) != 0 || (v48 & 0x10000000) == 0 && (unsigned __int8)NtfsGetPurgeKernelEAState(v46))
              || (*((_DWORD *)v81 + 1) & 0x10000) != 0
              || *((_QWORD *)FsContext + 63) && *((int *)FsContext + 50) >= 0
              || *((_QWORD *)FsContext + 66) )
            {
              NtfsReleasePagingResourcePriv(v46, v11, v21, v22);
              v74 = 0;
            }
          }
        }
        v20 = v78;
      }
    }
    if ( v74 )
    {
      LOBYTE(v20) = 0;
    }
    else
    {
      if ( v20->MinorFunction != 1 && !*((_BYTE *)FsContext + 460) )
        NtfsPerformOptimisticFlush(a1, FsContext);
      LOBYTE(v21) = 1;
      if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v11, v21) )
      {
        v82 = 0;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v82 = i;
          if ( (unsigned int)i >= 2 )
            break;
          v20 = *(struct _IO_STACK_LOCATION **)(a1 + 8 * i + 48);
          if ( !v20 || v20 == (struct _IO_STACK_LOCATION *)v11 )
          {
            *(_QWORD *)(a1 + 8 * i + 48) = v11;
            break;
          }
        }
      }
      LOBYTE(v20) = 1;
      v72 = 1;
    }
    if ( (*((_DWORD *)FsContext + 128) & 0x1000000) == 0 )
    {
      if ( v78->MinorFunction == 1 )
      {
        NtfsAcquireExclusiveScbEx(a1, FsContext, 0);
        v73 = 1;
        v43 = NtfsFlushAndPurgeScb(a1, FsContext, v42);
        v77 = v43;
        if ( v43 && v43 != 277 )
        {
          a2->IoStatus.Status = v43;
          v77 = 0;
        }
        v27 = FileObject;
        CcUninitializeCacheMap(FileObject, 0, 0);
      }
      else
      {
        if ( (_BYTE)v20 )
        {
          LOBYTE(BugCheckParameter4) = 0;
          a2->IoStatus.Status = NtfsFlushUserStream(a1, FsContext, 0, 0, BugCheckParameter4);
        }
        else
        {
          a2->IoStatus.Status = 0;
        }
        NtfsNormalizeAndCleanupTransaction(a1, &a2->IoStatus);
        v27 = FileObject;
      }
      if ( !v73 )
      {
        NtfsAcquireExclusiveScbEx(a1, FsContext, 0);
        v73 = 1;
      }
      if ( (*((_DWORD *)FsContext + 50) & 0x200) != 0 && v72 )
      {
        LOBYTE(v26) = 1;
        NtfsWriteFileSizes(a1, (_DWORD)FsContext, 0, v26, 1, 1);
      }
      LOBYTE(v25) = 1;
      NtfsUpdateScbFromFileObject(v27, FsContext, v25);
      if ( v78->MinorFunction == 4 )
        v28 = (*(_DWORD *)(v11 + 184) & 0x5FFFFF8F) != 0 ? v92 : 0;
      else
        v28 = v92;
      if ( v28 && (*(_DWORD *)(v11 + 4) & 0x10) != 0 )
        NtfsUpdateStandardInformation(a1, v11);
      if ( (*((_DWORD *)FsContext + 50) & 8) != 0 )
        v14 = NtfsFlushFcbFileRecords(a1, *((_QWORD *)FsContext + 23));
      if ( v28 )
      {
        if ( (*(_DWORD *)(v11 + 184) & 0xD00000FC) != 0 )
        {
          v92 = *((_QWORD *)v81 + 9);
          NtfsPrepareForUpdateDuplicate(a1, v11, (unsigned int)&v92, (unsigned int)&v80, 1, 0);
          v30 = v92;
          if ( !(unsigned __int8)NtfsUpdateDuplicateInfo(a1, v11) )
          {
            if ( v80 )
            {
              v31 = *(_DWORD *)(v11 + 184);
              if ( (v31 & 0xD00000FC) != 0 && (*((_DWORD *)v81 + 1) & 8) == 0 )
              {
                v32 = (v31 & 0x40000000) != 0 ? *(_DWORD *)(v11 + 184) & 0x1F4 | 8 : *(_DWORD *)(v11 + 184) & 0x1FC;
                if ( v32 )
                  NtfsReportDirNotify(
                    a1,
                    v30,
                    *(_QWORD *)(v11 + 96),
                    (_DWORD)v81 + 16,
                    *((unsigned __int16 *)v81 + 16),
                    0,
                    v32,
                    3,
                    *(_QWORD *)(v80 + 184),
                    0);
              }
            }
            if ( *(_WORD *)(v11 + 190) <= 1u )
              *(_DWORD *)(v11 + 184) &= 0x2FFFFE03u;
            NtfsUpdateLcbDuplicateInfo(v11, v30);
          }
        }
      }
      v29 = v72;
      if ( v72 )
      {
        v36 = v81;
        if ( (*((_DWORD *)v81 + 1) & 0x10000) != 0 && (v14 & 0x80000000) == 0 )
        {
          NtfsCheckpointCurrentTransaction(a1);
          NtfsReleaseAllResources(a1);
          v72 = 0;
          v73 = 0;
          if ( !v80 )
          {
            v50 = *((_QWORD *)v36 + 9);
            if ( v50 )
              v80 = *(_QWORD *)(v50 + 24);
          }
          v14 = NtfsFlushBootCritical(a1);
        }
        v29 = v72;
      }
      if ( (v14 & 0x80000000) == 0 )
      {
        NtfsCleanupTransaction(a1, v14, 0);
        NtfsCheckpointCurrentTransaction(a1);
        if ( v29 )
        {
          NtfsReleasePagingResourcePriv(v38, v11, v39, v40);
          if ( a1 )
          {
            v83 = 0;
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              v83 = j;
              if ( (unsigned int)j >= 2 )
                break;
              if ( *(_QWORD *)(a1 + 8 * j + 48) == v11 )
                *(_QWORD *)(a1 + 8 * j + 48) = 0;
            }
          }
          v72 = 0;
        }
        else if ( v74 )
        {
          NtfsReleasePagingResourcePriv(v38, FsContext, v39, v40);
          v74 = 0;
        }
        if ( v73 )
        {
          NtfsReleaseFcbEx(a1, *((_QWORD *)FsContext + 23), 0);
          v73 = 0;
        }
      }
      goto LABEL_38;
    }
    v14 = -1073741816;
    if ( NtfsStatusDebugFlags )
    {
      v51 = 1115207;
      goto LABEL_124;
    }
    goto LABEL_145;
  }
  v33 = v18 - 1;
  if ( v33 )
  {
    v34 = v33 - 1;
    if ( !v34 )
      goto LABEL_134;
    if ( v34 != 2 )
      goto LABEL_38;
  }
  v35 = FsContext ? *FsContext : 0;
  if ( v35 != 1796 )
  {
LABEL_38:
    v19 = v79;
    goto LABEL_39;
  }
LABEL_134:
  *(_DWORD *)(a1 + 504) = 22;
  LOBYTE(FsContext2) = 1;
  v19 = v79;
  NtfsFspCloseInternal(0, v79, (_DWORD)FsContext2, 0, 0);
  LOBYTE(v52) = 1;
  NtfsAcquireExclusiveVcb(a1, v79, v52);
  v75 = 1;
  if ( (*(_DWORD *)(v79 + 4) & 1) != 0 )
  {
    NtfsFlushVolume(a1);
LABEL_39:
    NtfsCleanupTransaction(a1, v14, 0);
    if ( v78->MinorFunction != 2 )
    {
      LfsFlushToLsnWithoutDiskCacheFlush(*(_QWORD *)(v19 + 232), NtfsLargeMax, 0, &v85);
      v76 = 1;
      v4 = v85;
    }
    goto LABEL_145;
  }
  v14 = -1073741202;
  if ( NtfsStatusDebugFlags )
  {
    v51 = 1115535;
LABEL_124:
    NtfsStatusTraceAndDebugInternal(0, v14, v51);
  }
LABEL_145:
  if ( NtfsDebugDiskFlush )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"<unavailable>");
  }
  if ( v75 )
    NtfsReleaseVcb(a1, v19);
  if ( v74 )
    NtfsReleasePagingResourcePriv(v20, FsContext, v21, v22);
  if ( v72 )
  {
    NtfsReleasePagingResourcePriv(v20, v11, v21, v22);
    if ( a1 )
    {
      for ( k = 0; k != 2; ++k )
      {
        if ( *(_QWORD *)(a1 + 8 * k + 48) == v11 )
          *(_QWORD *)(a1 + 8 * k + 48) = 0;
      }
    }
  }
  if ( v73 )
    NtfsReleaseFcbEx(a1, *((_QWORD *)FsContext + 23), 0);
  if ( (unsigned __int8)(v78->MinorFunction - 2) <= 1u )
  {
    if ( *(_BYTE *)(v19 + 10496) )
      NtfsIoPerfCollectFlushData(v19, a2, *(_QWORD *)(a1 + 512), *(unsigned int *)(a1 + 504), *(_QWORD *)(a1 + 496));
    if ( NtfsStatusDebugFlags
      && v14
      && v14 != 294
      && v14 - 298 > 1
      && v14 < 0xFFFFFFED
      && v14 != -1073741608
      && v14 != -1073741802
      && v14 != -1073741807
      && v14 + 2147483643 > 1
      && v14 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v14, 1115862);
    }
    LOBYTE(v22) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, v14, v22, (v14 & 0x80000000) == 0);
  }
  else
  {
    v53 = *(_QWORD *)(a1 + 512);
    v54 = *(_DWORD *)(a1 + 504);
    v55 = *(_QWORD *)(a1 + 496);
    LOBYTE(v22) = 1;
    NtfsExtendedCompleteRequestInternal(a1, 0, 0, v22, 1);
    v56 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v56[-1].MajorFunction = *(_OWORD *)&v78->MajorFunction;
    *(_OWORD *)&v56[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v78->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v56[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v78->Parameters.SetQuota + 6);
    *(_OWORD *)&v56[-1].FileObject = *(_OWORD *)&v78->FileObject;
    v56[-1].Context = v78->Context;
    v57 = ExAllocateFromLookasideListEx(&NtfsDiskFlushContextLookasideList);
    v58 = v57;
    if ( v57 )
    {
      memset(v57, 0, 0x58u);
      v58[8] = v77;
      *((_QWORD *)v58 + 10) = v53;
      *((_QWORD *)v58 + 8) = v55;
      v58[18] = v54;
      v59 = v79;
      if ( v76 )
      {
        _InterlockedAdd((volatile signed __int32 *)(v79 + 284), 1u);
        *((_QWORD *)v58 + 2) = v79;
        *((_QWORD *)v58 + 3) = v4;
      }
      v60 = a2->Tail.Overlay.CurrentStackLocation;
      v60[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)NtfsFlushCompletionRoutine;
      v60[-1].Context = v58;
      v60[-1].Control = -32;
    }
    else
    {
      v65 = a2->Tail.Overlay.CurrentStackLocation;
      v65[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)NtfsFlushCompletionRoutine;
      v65[-1].Context = (PVOID)v77;
      v65[-1].Control = -32;
      v59 = v79;
    }
    CurrentIrql = KeGetCurrentIrql();
    v62 = IofCallDriver(*(PDEVICE_OBJECT *)(v59 + 224), a2);
    if ( KeGetCurrentIrql() != CurrentIrql )
    {
      v69 = *(_QWORD *)(v59 + 224);
      v70 = KeGetCurrentIrql();
      KeBugCheckEx(0xC8u, (unsigned int)(CurrentIrql << 8) | ((unsigned __int64)v70 << 16) | 0x10, v69, 0, 0);
    }
    if ( v62 == -1073741808 )
      return v14;
    return v62;
  }
  return v14;
}

```

## disassembly

```asm
0x1401aaeb0  mov     rax, rsp
0x1401aaeb3  mov     [rax+10h], rdx
0x1401aaeb7  mov     [rax+8], rcx
0x1401aaebb  push    rbx
0x1401aaebc  push    rsi
0x1401aaebd  push    rdi
0x1401aaebe  push    r12
0x1401aaec0  push    r13
0x1401aaec2  push    r14
0x1401aaec4  push    r15
0x1401aaec6  sub     rsp, 0D0h
0x1401aaecd  mov     rsi, rdx
0x1401aaed0  mov     rdi, rcx
0x1401aaed3  mov     [rsp+108h+var_98], 0
0x1401aaedc  xor     ebx, ebx
0x1401aaede  mov     [rax-78h], rbx
0x1401aaee2  mov     r9, [rdx+0B8h]
0x1401aaee9  mov     [rsp+108h+var_A8], r9
0x1401aaeee  mov     rax, [r9+30h]
0x1401aaef2  mov     [rsp+108h+FileObject], rax
0x1401aaefa  mov     r13, [rax+18h]
0x1401aaefe  lea     r14d, [rbx+1]
0x1401aaf02  test    r13, r13
0x1401aaf05  jz      loc_1401ABB09
0x1401aaf0b  mov     r8, [rax+20h]
0x1401aaf0f  mov     [rsp+108h+var_90], r8
0x1401aaf14  mov     rdx, [r13+0C0h]
0x1401aaf1b  mov     [rsp+108h+var_A0], rdx
0x1401aaf20  mov     eax, [rdx+4]
0x1401aaf23  test    r14b, al
0x1401aaf26  jz      loc_1401ABADF
0x1401aaf2c  mov     [rsp+108h+var_80], rdx
0x1401aaf34  mov     r12, [r13+0B8h]
0x1401aaf3b  mov     [rsp+108h+var_68], r12
0x1401aaf43  test    r8, r8
0x1401aaf46  jz      loc_1401ABA59
0x1401aaf4c  movzx   r15d, byte ptr [r8+58h]
0x1401aaf51  cmp     r15d, r14d
0x1401aaf54  jz      loc_1401ABB33
0x1401aaf5a  mov     cl, [r9+1]
0x1401aaf5e  cmp     cl, r14b
0x1401aaf61  jz      short loc_1401AAF70
0x1401aaf63  test    dword ptr [rdx+4], 2000000h
0x1401aaf6a  jnz     loc_1401ABB8E
0x1401aaf70  cmp     cl, 2
0x1401aaf73  jz      loc_1401ABA64
0x1401aaf79  mov     [rsp+108h+var_58], r9
0x1401aaf81  mov     [rsp+108h+var_B5], bl
0x1401aaf85  mov     [rsp+108h+var_B7], bl
0x1401aaf89  mov     [rsp+108h+var_B8], bl
0x1401aaf8d  mov     [rsp+108h+var_B6], bl
0x1401aaf91  mov     byte ptr [rsp+108h+arg_10], r14b
0x1401aaf99  mov     [rsp+108h+var_B4], bl
0x1401aaf9d  mov     [rsp+108h+var_60], r13
0x1401aafa5  cmp     r15d, 2
0x1401aafa9  jz      loc_1401ABA08
0x1401aafaf  mov     [rsp+108h+var_AC], ebx
0x1401aafb3  xor     esi, esi
0x1401aafb5  mov     [rsp+108h+var_B0], esi
0x1401aafb9  cmp     cs:NtfsDiskAccountingEnabled, sil
0x1401aafc0  jz      short loc_1401AB02D
0x1401aafc2  mov     rax, [rsp+108h+Irp]
0x1401aafca  mov     rcx, [rax+98h]; Thread
0x1401aafd1  test    rcx, rcx
0x1401aafd4  jz      loc_1401AB4A9
0x1401aafda  call    cs:__imp_IoIsSystemThread
0x1401aafe1  nop     dword ptr [rax+rax+00h]
0x1401aafe6  test    al, al
0x1401aafe8  jnz     loc_1401AB4A9
0x1401aafee  mov     rax, [rsp+108h+Irp]
0x1401aaff6  mov     rcx, [rax+98h]; Thread
0x1401aaffd  call    cs:__imp_PsGetThreadProcess
0x1401ab004  nop     dword ptr [rax+rax+00h]
0x1401ab009  mov     rcx, rax
0x1401ab00c  mov     dword ptr [rsp+108h+var_E0], r14d
0x1401ab011  mov     dword ptr [rsp+108h+BugCheckParameter4], 0
0x1401ab019  xor     r9d, r9d
0x1401ab01c  xor     r8d, r8d
0x1401ab01f  xor     edx, edx
0x1401ab021  call    cs:__imp_PsUpdateDiskCounters
0x1401ab028  nop     dword ptr [rax+rax+00h]
0x1401ab02d  sub     r15d, 2
0x1401ab031  jnz     loc_1401AB2E9
0x1401ab037  mov     dword ptr [rdi+1F8h], 17h
0x1401ab041  mov     r8b, r14b
0x1401ab044  mov     r15, [rsp+108h+var_A0]
0x1401ab049  mov     rdx, r15
0x1401ab04c  mov     rcx, rdi
0x1401ab04f  call    NtfsAcquireSharedVcb
0x1401ab054  mov     [rsp+108h+var_B5], r14b
0x1401ab059  mov     eax, [r15+4]
0x1401ab05d  test    r14b, al
0x1401ab060  jz      loc_1401AB753
0x1401ab066  mov     eax, [r13+100h]
0x1401ab06d  test    eax, 0FFFFF000h
0x1401ab072  jz      loc_1401AB316
0x1401ab078  mov     rcx, [rsp+108h+var_A8]
0x1401ab07d  cmp     [rcx+1], r14b
0x1401ab081  jz      short loc_1401AB096
0x1401ab083  mov     rax, [r13+120h]
0x1401ab08a  xor     edx, edx
0x1401ab08c  cmp     [rax+10h], rdx
0x1401ab090  jz      loc_1401AB51F
0x1401ab096  cmp     [rsp+108h+var_B6], 0
0x1401ab09b  jz      loc_1401AB3BC
0x1401ab0a1  mov     cl, [rsp+108h+var_B8]
0x1401ab0a5  test    dword ptr [r13+200h], 1000000h
0x1401ab0b0  jnz     loc_1401AB76A
0x1401ab0b6  mov     rax, [rsp+108h+var_A8]
0x1401ab0bb  cmp     [rax+1], r14b
0x1401ab0bf  jz      loc_1401AB4B7
0x1401ab0c5  mov     r15, [rsp+108h+Irp]
0x1401ab0cd  test    cl, cl
0x1401ab0cf  jz      loc_1401AB512
0x1401ab0d5  mov     byte ptr [rsp+108h+BugCheckParameter4], 0
0x1401ab0da  xor     r9d, r9d
0x1401ab0dd  xor     r8d, r8d
0x1401ab0e0  mov     rdx, r13
0x1401ab0e3  mov     rcx, rdi
0x1401ab0e6  call    NtfsFlushUserStream
0x1401ab0eb  mov     [r15+30h], eax
0x1401ab0ef  lea     rdx, [r15+30h]
0x1401ab0f3  mov     rcx, rdi
0x1401ab0f6  call    NtfsNormalizeAndCleanupTransaction
0x1401ab0fb  mov     r15, [rsp+108h+FileObject]
0x1401ab103  cmp     [rsp+108h+var_B7], 0
0x1401ab108  jz      loc_1401AB33C
0x1401ab10e  test    dword ptr [r13+0C8h], 200h
0x1401ab119  jnz     loc_1401AB374
0x1401ab11f  mov     r8b, r14b
0x1401ab122  mov     rdx, r13
0x1401ab125  mov     rcx, r15
0x1401ab128  call    NtfsUpdateScbFromFileObject
0x1401ab12d  mov     rax, [rsp+108h+var_A8]
0x1401ab132  cmp     byte ptr [rax+1], 4
0x1401ab136  jz      loc_1401AB845
0x1401ab13c  mov     r15b, byte ptr [rsp+108h+arg_10]
0x1401ab144  test    r15b, r15b
0x1401ab147  jnz     loc_1401AB354
0x1401ab14d  mov     eax, [r13+0C8h]
0x1401ab154  test    al, 8
0x1401ab156  jz      short loc_1401AB170
0x1401ab158  mov     r8d, r14d
0x1401ab15b  mov     rdx, [r13+0B8h]; int
0x1401ab162  mov     rcx, rdi; int
0x1401ab165  call    NtfsFlushFcbFileRecords
0x1401ab16a  mov     esi, eax
0x1401ab16c  mov     [rsp+108h+var_B0], eax
0x1401ab170  test    r15b, r15b
0x1401ab173  jnz     short loc_1401AB1DC
0x1401ab175  mov     r15b, [rsp+108h+var_B8]
0x1401ab17a  test    r15b, r15b
0x1401ab17d  jnz     loc_1401AB39F
0x1401ab183  test    esi, esi
0x1401ab185  jns     loc_1401AB421
0x1401ab18b  mov     r15, [rsp+108h+var_A0]
0x1401ab190  xor     r8d, r8d
0x1401ab193  mov     edx, esi
0x1401ab195  mov     rcx, rdi
0x1401ab198  call    NtfsCleanupTransaction
0x1401ab19d  mov     rax, [rsp+108h+var_A8]
0x1401ab1a2  cmp     byte ptr [rax+1], 2
0x1401ab1a6  jz      loc_1401AB865
0x1401ab1ac  lea     r9, [rsp+108h+var_78]
0x1401ab1b4  xor     r8d, r8d
0x1401ab1b7  mov     rdx, cs:NtfsLargeMax
0x1401ab1be  mov     rcx, [r15+0E8h]
0x1401ab1c5  call    LfsFlushToLsnWithoutDiskCacheFlush
0x1401ab1ca  mov     [rsp+108h+var_B4], r14b
0x1401ab1cf  mov     rbx, [rsp+108h+var_78]
0x1401ab1d7  jmp     loc_1401AB865
0x1401ab1dc  test    dword ptr [r12+0B8h], 0D00000FCh
0x1401ab1e8  jz      short loc_1401AB175
0x1401ab1ea  mov     rax, [rsp+108h+var_90]
0x1401ab1ef  mov     rcx, [rax+48h]
0x1401ab1f3  mov     [rsp+108h+arg_10], rcx
0x1401ab1fb  mov     byte ptr [rsp+108h+var_E0], 0
0x1401ab200  mov     byte ptr [rsp+108h+BugCheckParameter4], r14b
0x1401ab205  lea     r9, [rsp+108h+var_98]
0x1401ab20a  lea     r8, [rsp+108h+arg_10]
0x1401ab212  mov     rdx, r12
0x1401ab215  mov     rcx, rdi
0x1401ab218  call    NtfsPrepareForUpdateDuplicate
0x1401ab21d  mov     r9, [rsp+108h+var_98]
0x1401ab222  mov     r15, [rsp+108h+arg_10]
0x1401ab22a  mov     r8, r15
0x1401ab22d  mov     rdx, r12; int
0x1401ab230  mov     rcx, rdi; int
0x1401ab233  call    NtfsUpdateDuplicateInfo
0x1401ab238  test    al, al
0x1401ab23a  jnz     loc_1401AB175
0x1401ab240  mov     r10, [rsp+108h+var_98]
0x1401ab245  test    r10, r10
0x1401ab248  jz      short loc_1401AB2C2
0x1401ab24a  mov     edx, [r12+0B8h]
0x1401ab252  test    edx, 0D00000FCh
0x1401ab258  jz      short loc_1401AB2C2
0x1401ab25a  mov     r8, [rsp+108h+var_90]
0x1401ab25f  mov     eax, [r8+4]
0x1401ab263  test    al, 8
0x1401ab265  jnz     short loc_1401AB2C2
0x1401ab267  bt      edx, 1Eh
0x1401ab26b  jb      loc_1401AB504
0x1401ab271  and     edx, 1FCh
0x1401ab277  test    edx, edx
0x1401ab279  jz      short loc_1401AB2C2
0x1401ab27b  movzx   ecx, word ptr [r8+20h]
0x1401ab280  lea     r9, [r8+10h]
0x1401ab284  mov     [rsp+108h+var_C0], 0
0x1401ab28d  mov     rax, [r10+0B8h]
0x1401ab294  mov     [rsp+108h+var_C8], rax
0x1401ab299  mov     [rsp+108h+var_D0], 3
0x1401ab2a1  mov     [rsp+108h+var_D8], edx
0x1401ab2a5  mov     [rsp+108h+var_E0], 0
0x1401ab2ae  mov     dword ptr [rsp+108h+BugCheckParameter4], ecx
0x1401ab2b2  mov     r8, [r12+60h]
0x1401ab2b7  mov     rdx, r15
0x1401ab2ba  mov     rcx, rdi
0x1401ab2bd  call    NtfsReportDirNotify
0x1401ab2c2  cmp     [r12+0BEh], r14w
0x1401ab2cb  ja      short loc_1401AB2D9
0x1401ab2cd  and     dword ptr [r12+0B8h], 2FFFFE03h
0x1401ab2d9  mov     rdx, r15
0x1401ab2dc  mov     rcx, r12
0x1401ab2df  call    NtfsUpdateLcbDuplicateInfo
0x1401ab2e4  jmp     loc_1401AB175
0x1401ab2e9  sub     r15d, 1
0x1401ab2ed  jz      short loc_1401AB303
0x1401ab2ef  sub     r15d, 1
0x1401ab2f3  jz      loc_1401AB788
0x1401ab2f9  cmp     r15d, 2
0x1401ab2fd  jnz     loc_1401AB18B
0x1401ab303  test    r13, r13
0x1401ab306  jz      loc_1401AB77B
0x1401ab30c  movzx   eax, word ptr [r13+0]
0x1401ab311  jmp     loc_1401AB77D
0x1401ab316  cmp     eax, 80h
0x1401ab31b  jz      loc_1401AB078
0x1401ab321  mov     r9d, r14d
0x1401ab324  mov     r8, r13
0x1401ab327  mov     rdx, r12
0x1401ab32a  mov     rcx, rdi
0x1401ab32d  call    NtfsAcquireExclusiveFcb
0x1401ab332  mov     [rsp+108h+var_B7], r14b
0x1401ab337  jmp     loc_1401AB190
0x1401ab33c  xor     r8d, r8d
0x1401ab33f  mov     rdx, r13
0x1401ab342  mov     rcx, rdi
0x1401ab345  call    NtfsAcquireExclusiveScbEx
0x1401ab34a  mov     [rsp+108h+var_B7], r14b
0x1401ab34f  jmp     loc_1401AB10E
0x1401ab354  mov     eax, [r12+4]
0x1401ab359  test    al, 10h
0x1401ab35b  jz      loc_1401AB14D
0x1401ab361  xor     r8d, r8d
0x1401ab364  mov     rdx, r12
0x1401ab367  mov     rcx, rdi
0x1401ab36a  call    NtfsUpdateStandardInformation
0x1401ab36f  jmp     loc_1401AB14D
0x1401ab374  cmp     [rsp+108h+var_B8], 0
0x1401ab379  jz      loc_1401AB11F
0x1401ab37f  mov     byte ptr [rsp+108h+var_E0], r14b
0x1401ab384  mov     byte ptr [rsp+108h+BugCheckParameter4], r14b
0x1401ab389  mov     r9b, r14b
0x1401ab38c  xor     r8d, r8d
0x1401ab38f  mov     rdx, r13
0x1401ab392  mov     rcx, rdi
0x1401ab395  call    NtfsWriteFileSizes
0x1401ab39a  jmp     loc_1401AB11F
0x1401ab39f  mov     r15, [rsp+108h+var_90]
0x1401ab3a4  test    dword ptr [r15+4], 10000h
0x1401ab3ac  jnz     loc_1401AB688
0x1401ab3b2  mov     r15b, [rsp+108h+var_B8]
0x1401ab3b7  jmp     loc_1401AB183
0x1401ab3bc  cmp     [rcx+1], r14b
0x1401ab3c0  jz      short loc_1401AB3D7
0x1401ab3c2  cmp     byte ptr [r13+1CCh], 0
0x1401ab3ca  jnz     short loc_1401AB3D7
0x1401ab3cc  mov     rdx, r13
0x1401ab3cf  mov     rcx, rdi
0x1401ab3d2  call    NtfsPerformOptimisticFlush
0x1401ab3d7  mov     r8b, r14b
0x1401ab3da  mov     rdx, r12
0x1401ab3dd  mov     rcx, rdi
0x1401ab3e0  call    NtfsAcquirePagingResourceExclusive
0x1401ab3e5  test    al, al
0x1401ab3e7  jz      short loc_1401AB415
0x1401ab3e9  mov     [rsp+108h+var_88], 0
0x1401ab3f4  xor     eax, eax
0x1401ab3f6  mov     [rsp+108h+var_88], eax
0x1401ab3fd  cmp     eax, 2
0x1401ab400  jnb     short loc_1401AB415
0x1401ab402  mov     rcx, [rdi+rax*8+30h]
0x1401ab407  test    rcx, rcx
0x1401ab40a  jnz     loc_1401AB701
0x1401ab410  mov     [rdi+rax*8+30h], r12
0x1401ab415  mov     cl, r14b
0x1401ab418  mov     [rsp+108h+var_B8], cl
0x1401ab41c  jmp     loc_1401AB0A5
0x1401ab421  xor     r8d, r8d
  ... truncated ...
```
