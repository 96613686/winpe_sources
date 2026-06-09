# TxfRollforwardRedo

- ea: `0x1401d6998`
- end: `0x1401d7da5`
- name: `TxfRollforwardRedo`
- size: `5133`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fd954`
- `0x1401f4270`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x14000cb00`
- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x140010e98`
- `0x1400291f0`
- `0x140029d80`
- `0x1400414f4`
- `0x1400592c0`
- `0x140059740`
- `0x1400ffd84`
- `0x140133f80`
- `0x14013add0`
- `0x1401403d0`
- `0x140188078`
- `0x140188d34`
- `0x1401d437c`
- `0x1401d54d8`
- `0x1401d5b20`
- `0x1401d6074`
- `0x1401d6998`
- `0x1401d912c`
- `0x14020a774`
- `0x14020b644`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1401d7c67`
- `ntoskrnl!KeReleaseMutex` at `0x1401d7c67`
- `ntoskrnl!DbgPrintEx` at `0x1401d7003`
- `ntoskrnl!DbgPrintEx` at `0x1401d7146`
- `ntoskrnl!DbgPrintEx` at `0x1401d7390`
- `ntoskrnl!DbgPrintEx` at `0x1401d74eb`
- `ntoskrnl!DbgPrintEx` at `0x1401d7616`
- `ntoskrnl!DbgPrintEx` at `0x1401d77c3`
- `ntoskrnl!DbgPrintEx` at `0x1401d794f`
- `ntoskrnl!DbgPrintEx` at `0x1401d7b07`
- `ntoskrnl!DbgPrintEx` at `0x1402cc852`
- `ntoskrnl!DbgPrintEx` at `0x1401d7003`
- `ntoskrnl!DbgPrintEx` at `0x1401d7146`
- `ntoskrnl!DbgPrintEx` at `0x1401d7390`
- `ntoskrnl!DbgPrintEx` at `0x1401d74eb`
- `ntoskrnl!DbgPrintEx` at `0x1401d7616`
- `ntoskrnl!DbgPrintEx` at `0x1401d77c3`
- `ntoskrnl!DbgPrintEx` at `0x1401d794f`
- `ntoskrnl!DbgPrintEx` at `0x1401d7b07`
- `ntoskrnl!DbgPrintEx` at `0x1402cc852`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d7c45`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d7c45`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d707c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d707c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d70b5`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d70b5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6b2d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6d98`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6b2d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6d98`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d709a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d756a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d709a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d756a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f66`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f96`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f66`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f96`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d6ec0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d6ec0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d6bda`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d6bda`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d79d6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402b07c5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d79d6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402b07c5`

## pseudocode

```c
__int64 __fastcall TxfRollforwardRedo(__int64 a1, CLFS_LSN *a2, _QWORD *a3)
{
  CLFS_LSN *v6; // r12
  int v7; // eax
  int IrpContextForRecovery; // ecx
  __int64 v9; // rbx
  NTSTATUS Redo; // edi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r15d
  __int16 v17; // cx
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // r9d
  volatile signed __int64 *v23; // rdi
  PVOID v24; // r15
  int v25; // edi
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  unsigned __int64 v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  unsigned __int64 v35; // rax
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // ecx
  unsigned __int64 v40; // rax
  __int64 v41; // rcx
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // ecx
  signed __int64 v45; // rdx
  unsigned __int64 v46; // rax
  __int64 v47; // rcx
  unsigned __int64 v48; // rax
  __int64 v49; // rcx
  int v50; // ecx
  int v52; // edi
  CLFS_LSN *v53; // rax
  CLFS_RECORD_INDEX idxRecord; // eax
  unsigned int v55; // eax
  __int64 v56; // r8
  unsigned __int64 v57; // rax
  __int64 v58; // rcx
  unsigned __int64 v59; // rax
  __int64 v60; // rcx
  CLS_RECORD_TYPE peRecordType; // [rsp+94h] [rbp-3A4h] BYREF
  char v62; // [rsp+95h] [rbp-3A3h]
  char v63; // [rsp+96h] [rbp-3A2h]
  char v64; // [rsp+97h] [rbp-3A1h]
  PVOID ppvReadBuffer; // [rsp+98h] [rbp-3A0h] BYREF
  int v66[2]; // [rsp+A0h] [rbp-398h] BYREF
  ULONG pcbBuffer; // [rsp+A8h] [rbp-390h] BYREF
  CLFS_LSN plsnRecord; // [rsp+B0h] [rbp-388h] BYREF
  PVOID pvReadContext; // [rsp+B8h] [rbp-380h] BYREF
  CLFS_LSN plsn1; // [rsp+C0h] [rbp-378h] BYREF
  int *v71; // [rsp+C8h] [rbp-370h]
  CLFS_LSN plsnFirst; // [rsp+D0h] [rbp-368h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-360h]
  CLFS_LSN *v74; // [rsp+E0h] [rbp-358h]
  CLFS_LSN plsnUndoNext; // [rsp+E8h] [rbp-350h] BYREF
  unsigned int *v76; // [rsp+F0h] [rbp-348h]
  CLFS_LSN *plsn2; // [rsp+F8h] [rbp-340h]
  _QWORD *v78; // [rsp+100h] [rbp-338h]
  _QWORD *v79; // [rsp+108h] [rbp-330h]
  CLFS_LSN plsnPrevious; // [rsp+110h] [rbp-328h] BYREF
  __int64 v81; // [rsp+118h] [rbp-320h]
  __int64 v82; // [rsp+120h] [rbp-318h] BYREF
  __int64 v83; // [rsp+128h] [rbp-310h] BYREF
  _OWORD v84[2]; // [rsp+130h] [rbp-308h] BYREF
  __int64 v85; // [rsp+150h] [rbp-2E8h]
  int v86[164]; // [rsp+160h] [rbp-2D8h] BYREF

  v79 = a3;
  plsn2 = a2;
  v71 = (int *)a3;
  v73 = a1;
  v74 = a2;
  v78 = a3;
  memset(v84, 0, sizeof(v84));
  v85 = 0;
  memset(v86, 0, sizeof(v86));
  pvReadContext = 0;
  ppvReadBuffer = 0;
  pcbBuffer = 0;
  plsnFirst.ullOffset = CLFS_LSN_NULL_EXT;
  plsnUndoNext.ullOffset = CLFS_LSN_NULL_EXT;
  plsnPrevious.ullOffset = CLFS_LSN_NULL_EXT;
  plsnRecord.ullOffset = CLFS_LSN_NULL_EXT;
  v82 = CLFS_LSN_NULL_EXT;
  v83 = CLFS_LSN_NULL_EXT;
  plsn1.ullOffset = CLFS_LSN_NULL_EXT;
  peRecordType = 0;
  *(_QWORD *)v66 = 0;
  v6 = (CLFS_LSN *)(a1 + 128);
  v76 = (unsigned int *)(a1 + 128);
  v7 = *(_DWORD *)(a1 + 128);
  if ( (v7 & 4) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3145956);
    return 3221225485LL;
  }
  if ( (v7 & 2) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 1075380276, 3145964);
    return 1075380276;
  }
  IrpContextForRecovery = TxfCreateIrpContextForRecovery(a1, v86, v84);
  if ( a2 || a3 )
  {
    if ( IrpContextForRecovery == -1073741432 )
      NtfsCheckpointForLogFileFull(v86);
    NtfsAcquireExclusiveScbEx(v86, *(_QWORD *)(a1 + 288), 0);
    TxfUpdateTopsMetadataStream((int)v86, 0, 0, (__int64)a3, a2, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    NtfsCheckpointCurrentTransaction(v86);
    NtfsCleanupIrpContext((__int64)v86, 0, v56);
    IrpContextForRecovery = 0;
    *(_DWORD *)(*(_QWORD *)&v86[36] + 24LL) = 0;
    v6 = (CLFS_LSN *)v76;
    if ( a2 )
      *(CLFS_LSN *)(a1 + 432) = *a2;
    else
      *(_QWORD *)(a1 + 440) = *a3;
  }
  v74 = v6;
  v71 = v86;
  v63 = 0;
  v62 = 0;
  v9 = 0;
  v81 = 0;
  v6->offset.idxRecord |= 4u;
  if ( IrpContextForRecovery < 0 )
    return (unsigned int)IrpContextForRecovery;
  if ( ClfsLsnNull((const CLFS_LSN *)(a1 + 448)) )
  {
    plsnFirst = *(CLFS_LSN *)(a1 + 408);
  }
  else
  {
    plsnFirst = *(CLFS_LSN *)(a1 + 448);
    v62 = 1;
    v64 = 1;
  }
  v86[109] |= 0x10u;
  NtfsPurgeFileRecordCache(v86);
  v86[1] |= 0x200u;
  peRecordType = 3;
  Redo = ClfsReadLogRecord(
           *(PVOID *)(a1 + 512),
           &plsnFirst,
           ClfsContextForward,
           &ppvReadBuffer,
           &pcbBuffer,
           &peRecordType,
           &plsnUndoNext,
           &plsnPrevious,
           &pvReadContext);
  v86[1] &= ~0x200u;
  v86[109] &= ~0x10u;
  if ( Redo < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
  {
    if ( Redo == -1073741801
      || (v31 = (unsigned int)(Redo + 1073741697), (unsigned int)v31 <= 0x22)
      && (v32 = 0x408000001LL, _bittest64(&v32, v31)) )
    {
      ++HIDWORD((*TxfData)[1]);
      v16 = 2097219;
      goto LABEL_124;
    }
    if ( Redo == -1072037845
      || Redo == -1073741202
      || Redo == -1073741435
      || Redo == -1073741496
      || (v33 = (unsigned int)(Redo + 1073741667), (unsigned int)v33 <= 0x23)
      && (v34 = 0x800000041LL, _bittest64(&v34, v33)) )
    {
      v16 = 2097219;
    }
    else
    {
      v16 = 2097219;
      if ( ((unsigned int)(Redo + 1073741811) > 0x15 || !_bittest(&v16, Redo + 1073741811))
        && Redo != -2147483626
        && Redo != -1072037841 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 388, "Status", Redo);
LABEL_124:
        Redo = TxfHandleRecoveryError((unsigned int)v86, a1, 2, Redo, 0);
        goto LABEL_190;
      }
    }
    ++LODWORD((*TxfData)[2]);
    goto LABEL_124;
  }
  if ( Redo < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)Redo < 0xFFFFFFED
      && Redo != -1073741802
      && Redo != -1073741807
      && (unsigned int)(Redo + 2147483643) > 1
      && Redo != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)Redo, 3146129);
    }
    v12 = 3146130;
LABEL_12:
    TxfHardErrorFcn(v86, a1, (unsigned int)Redo, v12);
    goto LABEL_13;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 528), 1u);
  plsnRecord = plsnFirst;
  if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbBuffer, v11) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3146140);
    v12 = 3146141;
LABEL_85:
    Redo = -1072103376;
    goto LABEL_12;
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) != 3 )
  {
    if ( v62 )
    {
      v62 = 0;
      v64 = 0;
    }
    else
    {
      if ( plsn2 && ClfsLsnGreater(&plsnRecord, plsn2)
        || (v17 = *(_WORD *)ppvReadBuffer, ((*(_WORD *)ppvReadBuffer - 4) & 0xFFF3) == 0)
        && v17 != 12
        && v78
        && *((_QWORD *)ppvReadBuffer + 10) > *v79 )
      {
        if ( ClfsLsnLess(&plsn1, (const CLFS_LSN *)(a1 + 432)) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3146195);
          Redo = -1073741811;
          if ( !(unsigned __int8)TxfRmInForcedRecovery(a1) )
            goto LABEL_13;
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            471,
            "Status",
            -1073741811);
          goto LABEL_50;
        }
        if ( v9 < *(_QWORD *)(a1 + 440) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3146209);
          Redo = -1073741811;
          if ( !(unsigned __int8)TxfRmInForcedRecovery(a1) )
            goto LABEL_13;
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            485,
            "Status",
            -1073741811);
          v21 = 0x2000;
        }
        else
        {
          if ( !ClfsLsnLess(&plsn1, (const CLFS_LSN *)(a1 + 408)) || !(unsigned __int8)TxfRmInForcedRecovery(a1) )
          {
            v63 = 1;
            *(CLFS_LSN *)(a1 + 456) = plsn1;
LABEL_54:
            Redo = 0;
            goto LABEL_13;
          }
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3146232);
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            506,
            "Status",
            -1073741811);
LABEL_50:
          v21 = 128;
        }
        ++LODWORD((*TxfData)[2]);
        v22 = -1073741811;
LABEL_52:
        TxfHandleRecoveryError((unsigned int)v86, a1, v21, v22, (__int64)ppvReadBuffer);
        goto LABEL_35;
      }
      if ( v17 == 32 || (v18 = *((_DWORD *)ppvReadBuffer + 1), v18 == 24) )
      {
        *(CLFS_LSN *)(a1 + 448) = plsnRecord;
        ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 472));
        v23 = (volatile signed __int64 *)(a1 + 464);
        if ( ClfsLsnGreater(&plsnRecord, (const CLFS_LSN *)(a1 + 464)) )
        {
          do
            v45 = _InterlockedCompareExchange64(v23, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
          while ( v45 != _InterlockedCompareExchange64(v23, plsnRecord.ullOffset, v45) );
        }
        ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 472));
        v24 = ppvReadBuffer;
        if ( *(_WORD *)ppvReadBuffer == 32 )
        {
          v25 = TxfActOnAllDirtyFilesInRm((unsigned int)v86, a1, 0, 0);
          if ( v25 < 0 )
          {
            if ( (unsigned __int8)TxfRmInForcedRecovery(a1) )
            {
              DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 563, "Status", v25);
              if ( v25 == -1073741801
                || (v26 = (unsigned int)(v25 + 1073741697), (unsigned int)v26 <= 0x22)
                && (v27 = 0x408000001LL, _bittest64(&v27, v26)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( v25 == -1072037845
                     || v25 == -1073741202
                     || v25 == -1073741435
                     || v25 == -1073741496
                     || (v28 = (unsigned int)(v25 + 1073741667), (unsigned int)v28 <= 0x23)
                     && (v29 = 0x800000041LL, _bittest64(&v29, v28))
                     || (unsigned int)(v25 + 1073741811) <= 0x15 && (v30 = 2097219, _bittest(&v30, v25 + 1073741811))
                     || v25 == -2147483626
                     || v25 == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              TxfHandleRecoveryError((unsigned int)v86, a1, 64, v25, (__int64)v24);
            }
          }
        }
      }
      else if ( v17 == 1 && v18 == 22 )
      {
        Redo = TxfProcessTransactionSummaryRecord(v86, a1, ppvReadBuffer, &plsnRecord);
        if ( Redo )
          goto LABEL_13;
      }
      else
      {
        Redo = TxfTransMgrSearchAddTrans(a1, (char *)ppvReadBuffer + 32, 0, 19, 0, v66);
        if ( (Redo < 0 || !*(_QWORD *)v66) && (unsigned __int8)TxfRmInForcedRecovery(a1) )
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 602, "Status", Redo);
          if ( Redo == -1073741801
            || (v35 = (unsigned int)(Redo + 1073741697), (unsigned int)v35 <= 0x22)
            && (v36 = 0x408000001LL, _bittest64(&v36, v35)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( Redo == -1072037845
                 || Redo == -1073741202
                 || Redo == -1073741435
                 || Redo == -1073741496
                 || (v37 = (unsigned int)(Redo + 1073741667), (unsigned int)v37 <= 0x23)
                 && (v38 = 0x800000041LL, _bittest64(&v38, v37))
                 || (unsigned int)(Redo + 1073741811) <= 0x15 && (v39 = 2097219, _bittest(&v39, Redo + 1073741811))
                 || Redo == -2147483626
                 || Redo == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          v22 = Redo;
          v21 = 256;
          goto LABEL_52;
        }
        if ( Redo )
        {
          v12 = 3146338;
          goto LABEL_12;
        }
        v19 = ((*((_WORD *)ppvReadBuffer + 36) & 1) << 24) | ((*((_WORD *)ppvReadBuffer + 36) & 2) << 24);
        if ( (*((_WORD *)ppvReadBuffer + 36) & 0x10) != 0 )
          _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v66 + 16LL), 0x40000u);
        ClfsLsnNull((const CLFS_LSN *)(*(_QWORD *)v66 + 40LL));
        _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)v66 + 16LL), 0xFCFFFFFF);
        _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v66 + 16LL), v19);
        Redo = TxfTransDoNextRedo((int)v86, v66[0], (int)ppvReadBuffer);
        if ( Redo < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
        {
          if ( Redo == -1073741801
            || (v40 = (unsigned int)(Redo + 1073741697), (unsigned int)v40 <= 0x22)
            && (v41 = 0x408000001LL, _bittest64(&v41, v40)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( Redo == -1072037845
                 || Redo == -1073741202
                 || Redo == -1073741435
                 || Redo == -1073741496
                 || (v42 = (unsigned int)(Redo + 1073741667), (unsigned int)v42 <= 0x23)
                 && (v43 = 0x800000041LL, _bittest64(&v43, v42))
                 || (unsigned int)(Redo + 1073741811) <= 0x15 && (v44 = 2097219, _bittest(&v44, Redo + 1073741811))
                 || Redo == -2147483626
                 || Redo == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          else
          {
            DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 724, "Status", Redo);
          }
          Redo = TxfHandleRecoveryError((unsigned int)v86, a1, 4096, Redo, (__int64)ppvReadBuffer);
        }
        if ( Redo < 0 )
        {
          v12 = 3146467;
          goto LABEL_12;
        }
        LOBYTE(v20) = 1;
        TxfDereferenceTransaction(v66, v20);
      }
      plsn1 = plsnRecord;
      if ( ((*(_WORD *)ppvReadBuffer - 4) & 0xFFF3) == 0 && *(_WORD *)ppvReadBuffer != 12 )
      {
        if ( *((_QWORD *)ppvReadBuffer + 10) > v9 )
          v9 = *((_QWORD *)ppvReadBuffer + 10);
        v81 = v9;
      }
    }
LABEL_35:
    v86[109] |= 0x10u;
    NtfsPurgeFileRecordCache(v86);
    v86[1] |= 0x200u;
    peRecordType = 3;
    Redo = ClfsReadNextLogRecord(
             pvReadContext,
             &ppvReadBuffer,
             &pcbBuffer,
             &peRecordType,
             0,
             &plsnUndoNext,
             &plsnPrevious,
             &plsnRecord);
    v86[1] &= ~0x200u;
    v86[109] &= ~0x10u;
    if ( (int)(Redo + 0x80000000) >= 0 )
    {
      if ( Redo == -1073741807 )
        goto LABEL_54;
      if ( (unsigned __int8)TxfRmInForcedRecovery(a1) )
      {
        if ( Redo == -1073741801
          || (v46 = (unsigned int)(Redo + 1073741697), (unsigned int)v46 <= 0x22)
          && (v47 = 0x408000001LL, _bittest64(&v47, v46)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( Redo == -1072037845
               || Redo == -1073741202
               || Redo == -1073741435
               || Redo == -1073741496
               || (v48 = (unsigned int)(Redo + 1073741667), (unsigned int)v48 <= 0x23)
               && (v49 = 0x800000041LL, _bittest64(&v49, v48))
               || (unsigned int)(Redo + 1073741811) <= 0x15 && (v50 = 2097219, _bittest(&v50, Redo + 1073741811))
               || Redo == -2147483626
               || Redo == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        else
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 802, "Status", Redo);
        }
        Redo = TxfHandleRecoveryError((unsigned int)v86, a1, 512, Redo, 0);
      }
    }
    if ( Redo == -1073741807 )
      goto LABEL_54;
    if ( Redo < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)Redo < 0xFFFFFFED
        && Redo != -1073741802
        && (unsigned int)(Redo + 2147483643) > 1
        && Redo != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)Redo, 3146548);
      }
      v12 = 3146549;
      goto LABEL_12;
    }
    if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbBuffer, v14) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3146557);
      v12 = 3146558;
      goto LABEL_85;
    }
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3222863877LL, 3146159);
  Redo = -1072103419;
LABEL_13:
  v16 = 2097219;
LABEL_190:
  v86[109] &= ~0x10u;
  if ( *(_QWORD *)v66 )
  {
    LOBYTE(v13) = 1;
    TxfDereferenceTransaction(v66, v13);
  }
  if ( pvReadContext )
  {
    NtfsPurgeFileRecordCache(v86);
    v86[1] |= 0x200u;
    ClfsTerminateReadLog(pvReadContext);
    v86[1] &= ~0x200u;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 528));
  }
  if ( Redo >= 0 )
  {
    TxfUpdateHighestFlushedLsn(a1, &plsn1, v14, v15);
    v52 = TxfActOnAllDirtyFilesInRm((unsigned int)v86, a1, (__int64)&plsn1, 0);
    if ( v52 < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 926, "Status", v52);
      if ( v52 == -1073741801
        || (v57 = (unsigned int)(v52 + 1073741697), (unsigned int)v57 <= 0x22)
        && (v58 = 0x408000001LL, _bittest64(&v58, v57)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v52 == -1072037845
             || v52 == -1073741202
             || v52 == -1073741435
             || v52 == -1073741496
             || (v59 = (unsigned int)(v52 + 1073741667), (unsigned int)v59 <= 0x23)
             && (v60 = 0x800000041LL, _bittest64(&v60, v59))
             || (unsigned int)(v52 + 1073741811) <= 0x15 && _bittest(&v16, v52 + 1073741811)
             || v52 == -2147483626
             || v52 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      v52 = TxfHandleRecoveryError((unsigned int)v86, a1, 1024, v52, 0);
    }
    if ( v52 < 0 )
    {
      TxfHardErrorFcn(v86, a1, (unsigned int)v52, 3146668);
      v53 = v74;
    }
    else
    {
      v53 = v74;
      v74->offset.idxRecord &= ~4u;
    }
    idxRecord = v53->offset.idxRecord;
    if ( v63 )
      v55 = idxRecord | 0x200;
    else
      v55 = idxRecord & 0xFFFFFDFF;
    *v76 = v55;
    TxfComputeTargetLsnsForCheckpoint(a1, 1, &v82, &v83);
    KeWaitForSingleObject(*(PVOID *)(a1 + 544), Executive, 0, 0, 0);
    if ( v9 > *(_QWORD *)(a1 + 536) )
      *(_QWORD *)(a1 + 536) = v9;
    KeReleaseMutex(*(PRKMUTEX *)(a1 + 544), 0);
    Redo = TxfTransMgrCheckpoint((int)v86, a1 + 448, 0, 0, 0, 0, 0);
    if ( Redo < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
      Redo = TxfHandleRecoveryError((unsigned int)v86, a1, 2048, Redo, 0);
    *(_QWORD *)(a1 + 440) = v9;
    TxfDeleteLinks(a1, 0, 0, 0);
  }
  else if ( Redo != -1072103419 )
  {
    TxfHardErrorFcn(v86, a1, (unsigned int)Redo, 3146762);
  }
  v86[3] &= ~0x10000u;
  NtfsCleanupIrpContext((__int64)v86, 0, v14);
  return (unsigned int)Redo;
}

```

## disassembly

```asm
0x1401d6998  push    rbx
0x1401d699a  push    rsi
0x1401d699b  push    rdi
0x1401d699c  push    r12
0x1401d699e  push    r13
0x1401d69a0  push    r14
0x1401d69a2  push    r15
0x1401d69a4  sub     rsp, 400h
0x1401d69ab  mov     rax, cs:__security_cookie
0x1401d69b2  xor     rax, rsp
0x1401d69b5  mov     [rsp+438h+var_48], rax
0x1401d69bd  mov     [rsp+438h+var_330], r8
0x1401d69c5  mov     rbx, rdx
0x1401d69c8  mov     [rsp+438h+plsn2], rdx
0x1401d69d0  mov     r14, rcx
0x1401d69d3  mov     [rsp+438h+var_370], r8
0x1401d69db  mov     [rsp+438h+var_360], rcx
0x1401d69e3  mov     [rsp+438h+var_358], rdx
0x1401d69eb  mov     rdi, r8
0x1401d69ee  mov     [rsp+438h+var_338], r8
0x1401d69f6  xorps   xmm0, xmm0
0x1401d69f9  xor     eax, eax
0x1401d69fb  movups  [rsp+438h+var_308], xmm0
0x1401d6a03  movups  [rsp+438h+var_2F8], xmm0
0x1401d6a0b  mov     [rsp+438h+var_2E8], rax
0x1401d6a13  xor     edx, edx; Val
0x1401d6a15  mov     r8d, 290h; Size
0x1401d6a1b  lea     rcx, [rsp+438h+var_2D8]; void *
0x1401d6a23  call    memset
0x1401d6a28  xor     esi, esi
0x1401d6a2a  mov     [rsp+438h+pvReadContext], rsi
0x1401d6a32  mov     [rsp+438h+ppvReadBuffer], rsi
0x1401d6a3a  mov     [rsp+438h+pcbBuffer], esi
0x1401d6a41  mov     rax, cs:CLFS_LSN_NULL_EXT
0x1401d6a48  mov     qword ptr [rsp+438h+plsnFirst], rax
0x1401d6a50  mov     qword ptr [rsp+438h+var_350], rax
0x1401d6a58  mov     qword ptr [rsp+438h+var_328], rax
0x1401d6a60  mov     qword ptr [rsp+438h+plsnRecord], rax
0x1401d6a68  mov     [rsp+438h+var_318], rax
0x1401d6a70  mov     [rsp+438h+var_310], rax
0x1401d6a78  mov     qword ptr [rsp+438h+plsn1], rax
0x1401d6a80  mov     [rsp+438h+var_3A4], sil
0x1401d6a88  mov     qword ptr [rsp+438h+var_398], rsi
0x1401d6a90  lea     r12, [r14+80h]
0x1401d6a97  mov     [rsp+438h+var_348], r12
0x1401d6a9f  mov     eax, [r12]
0x1401d6aa3  lea     r15d, [rsi+4]
0x1401d6aa7  test    r15b, al
0x1401d6aaa  jnz     loc_1401D7CFD
0x1401d6ab0  test    al, 2
0x1401d6ab2  jz      loc_1401D7D23
0x1401d6ab8  lea     r8, [rsp+438h+var_308]
0x1401d6ac0  lea     rdx, [rsp+438h+var_2D8]
0x1401d6ac8  mov     rcx, r14
0x1401d6acb  call    TxfCreateIrpContextForRecovery
0x1401d6ad0  mov     ecx, eax
0x1401d6ad2  test    rbx, rbx
0x1401d6ad5  jnz     loc_1402CC6CA
0x1401d6adb  test    rdi, rdi
0x1401d6ade  jnz     loc_1402CC6CA
0x1401d6ae4  mov     [rsp+438h+var_358], r12
0x1401d6aec  lea     r13, [rsp+438h+var_2D8]
0x1401d6af4  mov     [rsp+438h+var_370], r13
0x1401d6afc  mov     [rsp+438h+var_3A2], sil
0x1401d6b04  mov     [rsp+438h+var_3A3], sil
0x1401d6b0c  mov     rbx, rsi
0x1401d6b0f  mov     [rsp+438h+var_320], rbx
0x1401d6b17  or      [r12], r15d
0x1401d6b1b  test    ecx, ecx
0x1401d6b1d  js      loc_1401D7D49
0x1401d6b23  lea     rdi, [r14+1C0h]
0x1401d6b2a  mov     rcx, rdi; plsn
0x1401d6b2d  call    cs:__imp_ClfsLsnNull
0x1401d6b34  nop     dword ptr [rax+rax+00h]
0x1401d6b39  mov     r12d, 1
0x1401d6b3f  test    al, al
0x1401d6b41  jz      loc_1401D727C
0x1401d6b47  mov     rax, [r14+198h]
0x1401d6b4e  mov     qword ptr [rsp+438h+plsnFirst], rax
0x1401d6b56  or      [rsp+438h+var_124], 10h
0x1401d6b5e  lea     rcx, [rsp+438h+var_2D8]
0x1401d6b66  call    NtfsPurgeFileRecordCache
0x1401d6b6b  bts     [rsp+438h+var_2D4], 9
0x1401d6b74  mov     [rsp+438h+var_3A4], 3
0x1401d6b7c  lea     rax, [rsp+438h+pvReadContext]
0x1401d6b84  mov     [rsp+438h+ppvReadContext], rax; ppvReadContext
0x1401d6b89  lea     rax, [rsp+438h+var_328]
0x1401d6b91  mov     [rsp+438h+plsnPrevious], rax; plsnPrevious
0x1401d6b96  lea     rax, [rsp+438h+var_350]
0x1401d6b9e  mov     [rsp+438h+plsnUndoNext], rax; plsnUndoNext
0x1401d6ba3  lea     rax, [rsp+438h+var_3A4]
0x1401d6bab  mov     [rsp+438h+peRecordType], rax; peRecordType
0x1401d6bb0  lea     rax, [rsp+438h+pcbBuffer]
0x1401d6bb8  mov     [rsp+438h+pcbReadBuffer], rax; pcbReadBuffer
0x1401d6bbd  lea     r9, [rsp+438h+ppvReadBuffer]; ppvReadBuffer
0x1401d6bc5  mov     r8d, 3; peContextMode
0x1401d6bcb  lea     rdx, [rsp+438h+plsnFirst]; plsnFirst
0x1401d6bd3  mov     rcx, [r14+200h]; pvMarshalContext
0x1401d6bda  call    cs:__imp_ClfsReadLogRecord
0x1401d6be1  nop     dword ptr [rax+rax+00h]
0x1401d6be6  mov     edi, eax
0x1401d6be8  mov     [rsp+438h+var_3A8], eax
0x1401d6bef  btr     [rsp+438h+var_2D4], 9
0x1401d6bf8  and     [rsp+438h+var_124], 0FFFFFFEFh
0x1401d6c00  test    eax, eax
0x1401d6c02  js      loc_1401D7415
0x1401d6c08  test    edi, edi
0x1401d6c0a  jns     short loc_1401D6C60
0x1401d6c0c  mov     al, cs:NtfsStatusDebugFlags
0x1401d6c12  test    al, al
0x1401d6c14  jnz     loc_1401D71F1
0x1401d6c1a  mov     r9d, 300192h
0x1401d6c20  lea     rcx, [rsp+438h+var_2D8]
0x1401d6c28  mov     r8d, edi
0x1401d6c2b  mov     rdx, r14
0x1401d6c2e  call    TxfHardErrorFcn
0x1401d6c33  mov     r15d, 200043h
0x1401d6c39  jmp     loc_1401D79A1
0x1401d6c3e  cmp     cx, 0Ch
0x1401d6c42  jz      loc_1401D6E48
0x1401d6c48  mov     rax, [r15+50h]
0x1401d6c4c  cmp     rax, rbx
0x1401d6c4f  cmovg   rbx, rax
0x1401d6c53  mov     [rsp+438h+var_320], rbx
0x1401d6c5b  jmp     loc_1401D6E48
0x1401d6c60  lock add [r14+210h], r12d
0x1401d6c68  mov     rax, qword ptr [rsp+438h+plsnFirst]
0x1401d6c70  mov     qword ptr [rsp+438h+plsnRecord], rax
0x1401d6c78  mov     edx, [rsp+438h+pcbBuffer]
0x1401d6c7f  mov     rcx, [rsp+438h+ppvReadBuffer]
0x1401d6c87  call    TxfValidateLogRecord
0x1401d6c8c  test    al, al
0x1401d6c8e  jz      loc_1401D72BC
0x1401d6c94  mov     r15d, 0C000000Dh
0x1401d6c9a  lea     rdi, aStatus; "Status"
0x1401d6ca1  mov     ecx, 4
0x1401d6ca6  mov     eax, ecx
0x1401d6ca8  lock cmpxchg [r14+84h], ecx
0x1401d6cb1  cmp     eax, 3
0x1401d6cb4  jz      loc_1401D724F
0x1401d6cba  cmp     [rsp+438h+var_3A3], sil
0x1401d6cc2  jnz     loc_1401D7549
0x1401d6cc8  mov     rax, [rsp+438h+plsn2]
0x1401d6cd0  test    rax, rax
0x1401d6cd3  jnz     loc_1401D755F
0x1401d6cd9  mov     rdx, [rsp+438h+ppvReadBuffer]
0x1401d6ce1  movzx   ecx, word ptr [rdx]
0x1401d6ce4  lea     eax, [rcx-4]
0x1401d6ce7  mov     r8d, 0FFF3h
0x1401d6ced  test    r8w, ax
0x1401d6cf1  jz      loc_1401D6F2A
0x1401d6cf7  cmp     cx, 20h ; ' '
0x1401d6cfb  jz      loc_1401D7066
0x1401d6d01  mov     eax, [rdx+4]
0x1401d6d04  cmp     eax, 18h
0x1401d6d07  jz      loc_1401D7066
0x1401d6d0d  cmp     cx, r12w
0x1401d6d11  jz      loc_1401D759F
0x1401d6d17  add     rdx, 20h ; ' '
0x1401d6d1b  lea     rax, [rsp+438h+var_398]
0x1401d6d23  mov     [rsp+438h+peRecordType], rax
0x1401d6d28  mov     [rsp+438h+pcbReadBuffer], rsi
0x1401d6d2d  mov     r9d, 13h
0x1401d6d33  xor     r8d, r8d
0x1401d6d36  mov     rcx, r14
0x1401d6d39  call    TxfTransMgrSearchAddTrans
0x1401d6d3e  mov     edi, eax
0x1401d6d40  mov     [rsp+438h+var_3A8], eax
0x1401d6d47  test    eax, eax
0x1401d6d49  js      loc_1401D75D9
0x1401d6d4f  cmp     qword ptr [rsp+438h+var_398], rsi
0x1401d6d57  jz      loc_1401D75D9
0x1401d6d5d  test    edi, edi
0x1401d6d5f  jnz     loc_1401D76CF
0x1401d6d65  mov     rax, [rsp+438h+ppvReadBuffer]
0x1401d6d6d  movzx   ecx, word ptr [rax+48h]
0x1401d6d71  mov     edi, ecx
0x1401d6d73  and     edi, 2
0x1401d6d76  shl     edi, 18h
0x1401d6d79  mov     eax, ecx
0x1401d6d7b  and     eax, r12d
0x1401d6d7e  shl     eax, 18h
0x1401d6d81  or      edi, eax
0x1401d6d83  test    cl, 10h
0x1401d6d86  jnz     loc_1401D76DA
0x1401d6d8c  mov     rcx, qword ptr [rsp+438h+var_398]
0x1401d6d94  add     rcx, 28h ; '('; plsn
0x1401d6d98  call    cs:__imp_ClfsLsnNull
0x1401d6d9f  nop     dword ptr [rax+rax+00h]
0x1401d6da4  mov     rax, qword ptr [rsp+438h+var_398]
0x1401d6dac  lock and dword ptr [rax+10h], 0FCFFFFFFh
0x1401d6db4  mov     rax, qword ptr [rsp+438h+var_398]
0x1401d6dbc  lock or [rax+10h], edi
0x1401d6dc0  mov     rax, [rsp+438h+ppvReadBuffer]
0x1401d6dc8  mov     [rsp+438h+pcbReadBuffer], rax; int
0x1401d6dcd  mov     r9, qword ptr [rsp+438h+var_350]
0x1401d6dd5  mov     r8, qword ptr [rsp+438h+plsnRecord]
0x1401d6ddd  mov     rdx, qword ptr [rsp+438h+var_398]; int
0x1401d6de5  lea     rcx, [rsp+438h+var_2D8]; int
0x1401d6ded  call    TxfTransDoNextRedo
0x1401d6df2  mov     edi, eax
0x1401d6df4  mov     [rsp+438h+var_3A8], eax
0x1401d6dfb  test    eax, eax
0x1401d6dfd  js      loc_1401D76EF
0x1401d6e03  test    edi, edi
0x1401d6e05  js      loc_1401D7241
0x1401d6e0b  mov     dl, r12b
0x1401d6e0e  lea     rcx, [rsp+438h+var_398]
0x1401d6e16  call    TxfDereferenceTransaction
0x1401d6e1b  mov     rax, qword ptr [rsp+438h+plsnRecord]
0x1401d6e23  mov     qword ptr [rsp+438h+plsn1], rax
0x1401d6e2b  mov     r15, [rsp+438h+ppvReadBuffer]
0x1401d6e33  movzx   ecx, word ptr [r15]
0x1401d6e37  lea     eax, [rcx-4]
0x1401d6e3a  mov     edx, 0FFF3h
0x1401d6e3f  test    dx, ax
0x1401d6e42  jz      loc_1401D6C3E
0x1401d6e48  mov     r15d, 0C000000Dh
0x1401d6e4e  or      [rsp+438h+var_124], 10h
0x1401d6e56  lea     rcx, [rsp+438h+var_2D8]
0x1401d6e5e  call    NtfsPurgeFileRecordCache
0x1401d6e63  bts     [rsp+438h+var_2D4], 9
0x1401d6e6c  mov     [rsp+438h+var_3A4], 3
0x1401d6e74  lea     rax, [rsp+438h+plsnRecord]
0x1401d6e7c  mov     [rsp+438h+plsnPrevious], rax; plsnRecord
0x1401d6e81  lea     rax, [rsp+438h+var_328]
0x1401d6e89  mov     [rsp+438h+plsnUndoNext], rax; plsnPrevious
0x1401d6e8e  lea     rax, [rsp+438h+var_350]
0x1401d6e96  mov     [rsp+438h+peRecordType], rax; plsnUndoNext
0x1401d6e9b  mov     [rsp+438h+pcbReadBuffer], rsi; plsnUser
0x1401d6ea0  lea     r9, [rsp+438h+var_3A4]; peRecordType
0x1401d6ea8  lea     r8, [rsp+438h+pcbBuffer]; pcbBuffer
0x1401d6eb0  lea     rdx, [rsp+438h+ppvReadBuffer]; ppvBuffer
0x1401d6eb8  mov     rcx, [rsp+438h+pvReadContext]; pvReadContext
0x1401d6ec0  call    cs:__imp_ClfsReadNextLogRecord
0x1401d6ec7  nop     dword ptr [rax+rax+00h]
0x1401d6ecc  mov     edi, eax
0x1401d6ece  mov     [rsp+438h+var_3A8], eax
0x1401d6ed5  btr     [rsp+438h+var_2D4], 9
0x1401d6ede  and     [rsp+438h+var_124], 0FFFFFFEFh
0x1401d6ee6  mov     ecx, 80000000h
0x1401d6eeb  add     eax, ecx
0x1401d6eed  test    ecx, eax
0x1401d6eef  jz      loc_1401D704C
0x1401d6ef5  cmp     edi, 0C0000011h
0x1401d6efb  jz      loc_1401D7058
0x1401d6f01  test    edi, edi
0x1401d6f03  js      loc_1401D73A7
0x1401d6f09  mov     edx, [rsp+438h+pcbBuffer]
0x1401d6f10  mov     rcx, [rsp+438h+ppvReadBuffer]
0x1401d6f18  call    TxfValidateLogRecord
0x1401d6f1d  test    al, al
0x1401d6f1f  jz      loc_1401D73EB
0x1401d6f25  jmp     loc_1401D6C9A
0x1401d6f2a  cmp     cx, 0Ch
0x1401d6f2e  jz      loc_1401D6CF7
0x1401d6f34  cmp     [rsp+438h+var_338], rsi
0x1401d6f3c  jz      loc_1401D6CF7
0x1401d6f42  mov     rax, [rsp+438h+var_330]
0x1401d6f4a  mov     rax, [rax]
0x1401d6f4d  cmp     [rdx+50h], rax
0x1401d6f51  jle     loc_1401D6CF7
0x1401d6f57  lea     rdx, [r14+1B0h]; plsn2
0x1401d6f5e  lea     rcx, [rsp+438h+plsn1]; plsn1
0x1401d6f66  call    cs:__imp_ClfsLsnLess
0x1401d6f6d  nop     dword ptr [rax+rax+00h]
0x1401d6f72  test    al, al
0x1401d6f74  jnz     loc_1401D72DA
0x1401d6f7a  cmp     rbx, [r14+1B8h]
0x1401d6f81  jl      loc_1401D732D
0x1401d6f87  lea     rdx, [r14+198h]; plsn2
0x1401d6f8e  lea     rcx, [rsp+438h+plsn1]; plsn1
0x1401d6f96  call    cs:__imp_ClfsLsnLess
0x1401d6f9d  nop     dword ptr [rax+rax+00h]
0x1401d6fa2  test    al, al
0x1401d6fa4  jz      loc_1401D7583
0x1401d6faa  mov     rcx, r14
0x1401d6fad  call    TxfRmInForcedRecovery
0x1401d6fb2  test    al, al
0x1401d6fb4  jz      loc_1401D7583
0x1401d6fba  mov     al, cs:NtfsStatusDebugFlags
0x1401d6fc0  test    al, al
0x1401d6fc2  jz      short loc_1401D6FD4
0x1401d6fc4  mov     r8d, 3001F8h
0x1401d6fca  mov     edx, r15d
0x1401d6fcd  xor     ecx, ecx
0x1401d6fcf  call    NtfsStatusTraceAndDebugInternal
0x1401d6fd4  mov     [rsp+438h+var_3A8], r15d
0x1401d6fdc  mov     dword ptr [rsp+438h+plsnUndoNext], r15d
0x1401d6fe1  mov     [rsp+438h+peRecordType], rdi
0x1401d6fe6  mov     dword ptr [rsp+438h+pcbReadBuffer], 1FAh
0x1401d6fee  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x1401d6ff5  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x1401d6ffc  xor     edx, edx; Level
0x1401d6ffe  mov     ecx, 82h; ComponentId
0x1401d7003  call    cs:__imp_DbgPrintEx
0x1401d700a  nop     dword ptr [rax+rax+00h]
0x1401d700f  mov     r8d, 80h
0x1401d7015  mov     rax, cs:TxfData
0x1401d701c  add     [rax+10h], r12d
  ... truncated ...
```
