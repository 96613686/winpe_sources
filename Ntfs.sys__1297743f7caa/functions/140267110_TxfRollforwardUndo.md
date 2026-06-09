# TxfRollforwardUndo

- ea: `0x140267110`
- end: `0x14026805c`
- name: `TxfRollforwardUndo`
- size: `3916`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fdc04`
- `0x1401f4270`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x140010e98`
- `0x1400291f0`
- `0x140029d80`
- `0x1400414f4`
- `0x140049d00`
- `0x1400592c0`
- `0x140059740`
- `0x1400fa428`
- `0x140188d34`
- `0x1401ac0d0`
- `0x1401d4f90`
- `0x1401d5b20`
- `0x1401d6074`
- `0x1401d6108`
- `0x140214e38`
- `0x140267110`
- `0x140268064`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140267263`
- `ntoskrnl!DbgPrintEx` at `0x140267431`
- `ntoskrnl!DbgPrintEx` at `0x1402675b5`
- `ntoskrnl!DbgPrintEx` at `0x1402676ef`
- `ntoskrnl!DbgPrintEx` at `0x140267a62`
- `ntoskrnl!DbgPrintEx` at `0x140267b80`
- `ntoskrnl!DbgPrintEx` at `0x140267e22`
- `ntoskrnl!DbgPrintEx` at `0x140267f56`
- `ntoskrnl!DbgPrintEx` at `0x140267263`
- `ntoskrnl!DbgPrintEx` at `0x140267431`
- `ntoskrnl!DbgPrintEx` at `0x1402675b5`
- `ntoskrnl!DbgPrintEx` at `0x1402676ef`
- `ntoskrnl!DbgPrintEx` at `0x140267a62`
- `ntoskrnl!DbgPrintEx` at `0x140267b80`
- `ntoskrnl!DbgPrintEx` at `0x140267e22`
- `ntoskrnl!DbgPrintEx` at `0x140267f56`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402677ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267899`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402678ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267ca5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402677ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267899`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402678ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267ca5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267808`
- `ntoskrnl!ExReleaseResourceLite` at `0x14026793a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267cc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267d2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ba1c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267808`
- `ntoskrnl!ExReleaseResourceLite` at `0x14026793a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267cc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267d2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ba1c0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140267d61`
- `ntoskrnl!ExAcquireFastMutex` at `0x140267d61`
- `ntoskrnl!ExReleaseFastMutex` at `0x140267d8c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140267d8c`
- `ntoskrnl!ExRaiseStatus` at `0x1402679b6`
- `ntoskrnl!ExRaiseStatus` at `0x140267c8a`
- `ntoskrnl!ExRaiseStatus` at `0x1402679b6`
- `ntoskrnl!ExRaiseStatus` at `0x140267c8a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsSetEndOfLog` at `0x1402673d1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsSetEndOfLog` at `0x1402673d1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x140267519`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x140267519`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x140267555`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x140267555`

## pseudocode

```c
__int64 __fastcall TxfRollforwardUndo(__int64 a1)
{
  int v2; // eax
  __int64 result; // rax
  NTSTATUS MarshallingArea; // ebx
  __int64 v5; // r13
  __int64 v6; // r15
  int v7; // r14d
  __int64 v8; // r9
  __int64 v9; // r8
  _QWORD *v10; // r14
  _QWORD *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // r8
  char v14; // dl
  int KtmResourceManagerObject; // eax
  __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rax
  __int64 j; // rcx
  char v21; // r15
  int v22; // ecx
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // r8
  unsigned __int64 v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // eax
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned __int64 v39; // rax
  __int64 v40; // rcx
  int v41; // ecx
  int cbMarshallingBuffer; // [rsp+20h] [rbp-358h]
  _QWORD *i; // [rsp+50h] [rbp-328h] BYREF
  _QWORD v44[3]; // [rsp+58h] [rbp-320h] BYREF
  __int64 v45; // [rsp+70h] [rbp-308h] BYREF
  _OWORD v46[2]; // [rsp+78h] [rbp-300h] BYREF
  __int64 v47; // [rsp+98h] [rbp-2E0h]
  _QWORD v48[82]; // [rsp+A0h] [rbp-2D8h] BYREF

  v44[1] = a1;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  memset(v48, 0, sizeof(v48));
  v44[0] = CLFS_LSN_NULL_EXT;
  v2 = *(_DWORD *)(a1 + 128);
  if ( (v2 & 4) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 3147025);
    return 3221225485LL;
  }
  if ( (v2 & 2) != 0 )
  {
    v44[2] = v48;
    result = TxfCreateIrpContextForRecovery(a1, v48, v46);
    if ( (int)result < 0 )
      return result;
    *(_DWORD *)(a1 + 128) |= 4u;
    MarshallingArea = TxfScanForHighestTxfFileId((unsigned int)v48);
    if ( MarshallingArea >= 0 || !(unsigned __int8)TxfRmInForcedRecovery(a1) )
    {
      v5 = 0x408000001LL;
      v6 = 0x800000041LL;
      v7 = 2097219;
LABEL_32:
      if ( MarshallingArea >= 0 )
      {
        if ( (*(_DWORD *)(a1 + 128) & 0x200) != 0 )
        {
          NtfsPurgeFileRecordCache(v48);
          HIDWORD(v48[0]) |= 0x200u;
          MarshallingArea = ClfsSetEndOfLog(*(PLOG_FILE_OBJECT *)(a1 + 496), (PCLFS_LSN)(a1 + 456));
          HIDWORD(v48[0]) &= ~0x200u;
          if ( MarshallingArea < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
          {
            DbgPrintEx(
              0x82u,
              0,
              "%s:%d -- TxF corruption detected, %s == 0x%x",
              "TxfRecovery.c",
              1370,
              "Status",
              MarshallingArea);
            if ( MarshallingArea == -1073741801
              || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( MarshallingArea == -1072037845
                   || MarshallingArea == -1073741202
                   || MarshallingArea == -1073741435
                   || MarshallingArea == -1073741496
                   || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                   && _bittest64(&v6, MarshallingArea + 1073741667)
                   || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                   && _bittest(&v7, MarshallingArea + 1073741811)
                   || MarshallingArea == -2147483626
                   || MarshallingArea == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            MarshallingArea = TxfHandleRecoveryError((unsigned int)v48, a1, 2, MarshallingArea, 0);
          }
          if ( MarshallingArea < 0 )
          {
            v8 = 3147104;
            goto LABEL_34;
          }
          NtfsPurgeFileRecordCache(v48);
          HIDWORD(v48[0]) |= 0x200u;
          ClfsDeleteMarshallingArea(*(PVOID *)(a1 + 512));
          MarshallingArea = ClfsCreateMarshallingArea(
                              *(PLOG_FILE_OBJECT *)(a1 + 496),
                              PoolType,
                              0,
                              0,
                              0x40000u,
                              0xAu,
                              0x14u,
                              (PVOID *)(a1 + 512));
          HIDWORD(v48[0]) &= ~0x200u;
          if ( MarshallingArea < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
          {
            DbgPrintEx(
              0x82u,
              0,
              "%s:%d -- TxF corruption detected, %s == 0x%x",
              "TxfRecovery.c",
              1402,
              "Status",
              MarshallingArea);
            if ( MarshallingArea == -1073741801
              || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( MarshallingArea == -1072037845
                   || MarshallingArea == -1073741202
                   || MarshallingArea == -1073741435
                   || MarshallingArea == -1073741496
                   || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                   && _bittest64(&v6, MarshallingArea + 1073741667)
                   || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                   && _bittest(&v7, MarshallingArea + 1073741811)
                   || MarshallingArea == -2147483626
                   || MarshallingArea == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            MarshallingArea = TxfHandleRecoveryError((unsigned int)v48, a1, 2, MarshallingArea, 0);
          }
          if ( MarshallingArea < 0 )
          {
            v8 = 3147136;
            goto LABEL_34;
          }
          *(_DWORD *)(a1 + 128) &= ~0x200u;
        }
        LOBYTE(cbMarshallingBuffer) = 0;
        MarshallingArea = NtfsFlushUserStream(v48, *(_QWORD *)(a1 + 280), 0, 0, cbMarshallingBuffer);
        if ( MarshallingArea < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
        {
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            1429,
            "Status",
            MarshallingArea);
          if ( MarshallingArea == -1073741801
            || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( MarshallingArea == -1072037845
                 || MarshallingArea == -1073741202
                 || MarshallingArea == -1073741435
                 || MarshallingArea == -1073741496
                 || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                 && _bittest64(&v6, MarshallingArea + 1073741667)
                 || (unsigned int)(MarshallingArea + 1073741811) <= 0x15 && _bittest(&v7, MarshallingArea + 1073741811)
                 || MarshallingArea == -2147483626
                 || MarshallingArea == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          MarshallingArea = TxfHandleRecoveryError((unsigned int)v48, a1, 4, MarshallingArea, 0);
        }
        if ( MarshallingArea >= 0 )
        {
          v10 = *(_QWORD **)(a1 + 168);
          while ( v10 != (_QWORD *)(a1 + 168) )
          {
            v11 = v10 - 15;
            i = v11;
            v10 = (_QWORD *)*v10;
            if ( (v11[2] & 9) != 1 )
            {
              ExAcquireResourceExclusiveLite((PERESOURCE)(v11[3] + 80LL), 1u);
              *((_DWORD *)v11 + 109) |= 1u;
              ExReleaseResourceLite((PERESOURCE)(v11[3] + 80LL));
              MarshallingArea = TxfTransMgrAbort((unsigned int)v48, (_DWORD)v11);
              TxfDereferenceTransaction(&i, 0);
              if ( MarshallingArea < 0 && !(unsigned __int8)TxfRmInForcedRecovery(a1) )
              {
                v12 = 3147221;
                v13 = (unsigned int)MarshallingArea;
LABEL_103:
                TxfHardErrorFcn(v48, a1, v13, v12);
                v14 = 0;
                goto LABEL_178;
              }
            }
          }
          TxfProcessTxfVscbDereferencesForEOT(a1);
          KtmResourceManagerObject = TxfCreateKtmResourceManagerObject((__int64)v48, a1);
          MarshallingArea = KtmResourceManagerObject;
          if ( KtmResourceManagerObject < 0 )
          {
            v12 = 3147242;
            v13 = (unsigned int)KtmResourceManagerObject;
            goto LABEL_103;
          }
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 160), 1u);
          v14 = 1;
          v16 = *(_QWORD *)(a1 + 152);
          for ( i = (_QWORD *)v16; ; i = *(_QWORD **)(v17 + 104) )
          {
            v17 = v16;
            if ( !v16 || (*(_DWORD *)(v16 + 16) & 0x2000) == 0 )
              break;
            v16 = *(_QWORD *)(v16 + 104);
          }
          while ( v16 )
          {
            if ( !v14 )
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 160), 1u);
            v18 = v16;
            v45 = v16;
            v19 = *(_QWORD *)(v16 + 104);
            v16 = v19;
            i = (_QWORD *)v19;
            for ( j = v19; v19 && (*(_DWORD *)(j + 16) & 0x2000) != 0; j = v16 )
            {
              v16 = *(_QWORD *)(j + 104);
              i = (_QWORD *)v16;
              v19 = v16;
            }
            ExReleaseResourceLite(*(PERESOURCE *)(a1 + 160));
            v21 = 1;
            if ( (*(_DWORD *)(v18 + 16) & 0x4001) != 0 && *(_QWORD *)(v18 + 240) )
            {
              if ( (*(_DWORD *)(v18 + 16) & 0x4001) == 0x4001 )
              {
                v21 = 0;
              }
              else
              {
                if ( !(unsigned __int8)TxfRmInForcedRecovery(a1) )
                {
                  if ( (v48[2] & 0x100000LL) == 0
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                  {
                    McTemplateU0spj_EtwWriteTransfer(
                      v22,
                      (unsigned int)txfrecovery_c1622,
                      (unsigned int)"TxfRollforwardUndo",
                      a1,
                      a1 + 672);
                  }
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 3222863878LL, 3147358);
                  MarshallingArea = -1072103418;
                  goto LABEL_134;
                }
                DbgPrintEx(
                  0x82u,
                  0,
                  "%s:%d -- TxF corruption detected, %s == 0x%x",
                  "TxfRecovery.c",
                  1634,
                  "Status",
                  MarshallingArea);
                if ( MarshallingArea == -1073741801
                  || (v23 = (unsigned int)(MarshallingArea + 1073741697), (unsigned int)v23 <= 0x22)
                  && (v24 = 0x408000001LL, _bittest64(&v24, v23)) )
                {
                  ++HIDWORD((*TxfData)[1]);
                }
                else if ( MarshallingArea == -1072037845
                       || MarshallingArea == -1073741202
                       || MarshallingArea == -1073741435
                       || MarshallingArea == -1073741496
                       || (v25 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v25 <= 0x23)
                       && (v26 = 0x800000041LL, _bittest64(&v26, v25))
                       || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                       && (v27 = 2097219, _bittest(&v27, MarshallingArea + 1073741811))
                       || MarshallingArea == -2147483626
                       || MarshallingArea == -1072037841 )
                {
                  ++LODWORD((*TxfData)[2]);
                }
                v28 = TxfHandleRecoveryError((unsigned int)v48, a1, 8, -1072103418, v18);
                MarshallingArea = v28;
                if ( v28 < 0 )
                {
                  v29 = 3147371;
                  v30 = (unsigned int)v28;
                  goto LABEL_152;
                }
              }
            }
            if ( *(_QWORD *)(v18 + 88) != v18 + 88 )
            {
              if ( !(unsigned __int8)TxfRmInForcedRecovery(a1) )
              {
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(v48, 3222863920LL, 3147409);
                ExRaiseStatus(-1072103376);
              }
              DbgPrintEx(
                0x82u,
                0,
                "%s:%d -- TxF corruption detected, %s == 0x%x",
                "TxfRecovery.c",
                1684,
                "Status",
                MarshallingArea);
              if ( MarshallingArea == -1073741801
                || (v31 = (unsigned int)(MarshallingArea + 1073741697), (unsigned int)v31 <= 0x22)
                && (v32 = 0x408000001LL, _bittest64(&v32, v31)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( MarshallingArea == -1072037845
                     || MarshallingArea == -1073741202
                     || MarshallingArea == -1073741435
                     || MarshallingArea == -1073741496
                     || (v33 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v33 <= 0x23)
                     && (v34 = 0x800000041LL, _bittest64(&v34, v33))
                     || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                     && (v35 = 2097219, _bittest(&v35, MarshallingArea + 1073741811))
                     || MarshallingArea == -2147483626
                     || MarshallingArea == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              v36 = TxfHandleRecoveryError((unsigned int)v48, a1, 16, -1072103376, v18);
              MarshallingArea = v36;
              if ( v36 < 0 )
              {
                TxfHardErrorFcn(v48, a1, (unsigned int)v36, 3147421);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(v48, 3222863920LL, 3147422);
                ExRaiseStatus(-1072103376);
              }
            }
            if ( v21 )
            {
              ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v18 + 24) + 80LL), 1u);
              *(_DWORD *)(v18 + 436) |= 1u;
              ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v18 + 24) + 80LL));
              MarshallingArea = TxfTransMgrAbort((unsigned int)v48, v18);
              TxfDereferenceTransaction(&v45, 0);
              if ( MarshallingArea < 0 && !(unsigned __int8)TxfRmInForcedRecovery(a1) )
              {
                v29 = 3147461;
                v30 = (unsigned int)MarshallingArea;
LABEL_152:
                TxfHardErrorFcn(v48, a1, v30, v29);
LABEL_134:
                v14 = 0;
                break;
              }
            }
            v14 = 0;
          }
          v5 = 0x408000001LL;
LABEL_178:
          if ( v14 )
            ExReleaseResourceLite(*(PERESOURCE *)(a1 + 160));
          if ( MarshallingArea >= 0 || (unsigned __int8)TxfRmInForcedRecovery(a1) )
          {
            ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 472));
            v44[0] = _InterlockedCompareExchange64(
                       (volatile signed __int64 *)(a1 + 464),
                       NtfsLarge0.QuadPart,
                       NtfsLarge0.QuadPart);
            ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 472));
            TxfFlushToLsn(a1, v44[0]);
            TxfUpdateHighestFlushedLsn(a1, v44, v37, v38);
            MarshallingArea = TxfActOnAllDirtyFilesInRm((unsigned int)v48, a1, (__int64)v44, 0);
            if ( MarshallingArea < 0 && (unsigned __int8)TxfRmInForcedRecovery(a1) )
            {
              DbgPrintEx(
                0x82u,
                0,
                "%s:%d -- TxF corruption detected, %s == 0x%x",
                "TxfRecovery.c",
                1783,
                "Status",
                MarshallingArea);
              if ( MarshallingArea == -1073741801
                || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( MarshallingArea == -1072037845
                     || MarshallingArea == -1073741202
                     || MarshallingArea == -1073741435
                     || MarshallingArea == -1073741496
                     || (v39 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v39 <= 0x23)
                     && (v40 = 0x800000041LL, _bittest64(&v40, v39))
                     || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                     && (v41 = 2097219, _bittest(&v41, MarshallingArea + 1073741811))
                     || MarshallingArea == -2147483626
                     || MarshallingArea == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              MarshallingArea = TxfHandleRecoveryError((unsigned int)v48, a1, 32, MarshallingArea, 0);
            }
            if ( MarshallingArea >= 0 )
            {
              *(_DWORD *)(a1 + 128) &= ~4u;
              goto LABEL_204;
            }
            v8 = 3147517;
          }
          else
          {
            v8 = 3147480;
          }
        }
        else
        {
          v8 = 3147163;
        }
      }
      else
      {
        v8 = 3147078;
      }
LABEL_34:
      TxfHardErrorFcn(v48, a1, (unsigned int)MarshallingArea, v8);
LABEL_204:
      HIDWORD(v48[1]) &= ~0x10000u;
      NtfsCleanupIrpContext((__int64)v48, 0, v9);
      return (unsigned int)MarshallingArea;
    }
    DbgPrintEx(
      0x82u,
      0,
      "%s:%d -- TxF corruption detected, %s == 0x%x",
      "TxfRecovery.c",
      1344,
      "Status",
      MarshallingArea);
    v5 = 0x408000001LL;
    if ( MarshallingArea == -1073741801
      || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
    {
      ++HIDWORD((*TxfData)[1]);
      v6 = 0x800000041LL;
      v7 = 2097219;
      goto LABEL_30;
    }
    if ( MarshallingArea == -1072037845
      || MarshallingArea == -1073741202
      || MarshallingArea == -1073741435
      || MarshallingArea == -1073741496 )
    {
      v6 = 0x800000041LL;
    }
    else
    {
      v6 = 0x800000041LL;
      if ( (unsigned int)(MarshallingArea + 1073741667) > 0x23 || !_bittest64(&v6, MarshallingArea + 1073741667) )
      {
        v7 = 2097219;
        if ( ((unsigned int)(MarshallingArea + 1073741811) > 0x15 || !_bittest(&v7, MarshallingArea + 1073741811))
          && MarshallingArea != -2147483626
          && MarshallingArea != -1072037841 )
        {
          goto LABEL_30;
        }
        goto LABEL_28;
      }
    }
    v7 = 2097219;
LABEL_28:
    ++LODWORD((*TxfData)[2]);
LABEL_30:
    MarshallingArea = TxfHandleRecoveryError((unsigned int)v48, a1, 1, MarshallingArea, 0);
    goto LABEL_32;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 1075380276, 3147034);
  return 1075380276;
}

```

## disassembly

```asm
0x140267110  push    rbx
0x140267112  push    rdi
0x140267113  push    r12
0x140267115  push    r13
0x140267117  push    r14
0x140267119  push    r15
0x14026711b  sub     rsp, 348h
0x140267122  mov     rax, cs:__security_cookie
0x140267129  xor     rax, rsp
0x14026712c  mov     [rsp+378h+var_48], rax
0x140267134  mov     rdi, rcx
0x140267137  mov     [rsp+378h+var_318], rcx
0x14026713c  xorps   xmm0, xmm0
0x14026713f  xor     eax, eax
0x140267141  movups  [rsp+378h+var_300], xmm0
0x140267146  movups  [rsp+378h+var_2F0], xmm0
0x14026714e  mov     [rsp+378h+var_2E0], rax
0x140267156  xor     edx, edx; Val
0x140267158  mov     r8d, 290h; Size
0x14026715e  lea     rcx, [rsp+378h+var_2D8]; void *
0x140267166  call    memset
0x14026716b  mov     rax, cs:CLFS_LSN_NULL_EXT
0x140267172  mov     [rsp+378h+var_320], rax
0x140267177  mov     eax, [rdi+80h]
0x14026717d  test    al, 4
0x14026717f  jz      short loc_1402671A7
0x140267181  mov     al, cs:NtfsStatusDebugFlags
0x140267187  test    al, al
0x140267189  jz      short loc_14026719D
0x14026718b  mov     edx, 0C000000Dh
0x140267190  xor     ecx, ecx
0x140267192  mov     r8d, 300511h
0x140267198  call    NtfsStatusTraceAndDebugInternal
0x14026719d  mov     eax, 0C000000Dh
0x1402671a2  jmp     loc_140268039
0x1402671a7  test    al, 2
0x1402671a9  jnz     short loc_1402671D1
0x1402671ab  mov     al, cs:NtfsStatusDebugFlags
0x1402671b1  test    al, al
0x1402671b3  jz      short loc_1402671C7
0x1402671b5  mov     edx, 40190034h
0x1402671ba  xor     ecx, ecx
0x1402671bc  mov     r8d, 30051Ah
0x1402671c2  call    NtfsStatusTraceAndDebugInternal
0x1402671c7  mov     eax, 40190034h
0x1402671cc  jmp     loc_140268039
0x1402671d1  xor     al, al
0x1402671d3  mov     [rsp+378h+var_338], al
0x1402671d7  lea     r12, [rsp+378h+var_2D8]
0x1402671df  mov     [rsp+378h+var_310], r12
0x1402671e4  lea     r8, [rsp+378h+var_300]
0x1402671e9  lea     rdx, [rsp+378h+var_2D8]
0x1402671f1  mov     rcx, rdi
0x1402671f4  call    TxfCreateIrpContextForRecovery
0x1402671f9  test    eax, eax
0x1402671fb  js      loc_140268039
0x140267201  or      dword ptr [rdi+80h], 4
0x140267208  mov     rdx, rdi
0x14026720b  lea     rcx, [rsp+378h+var_2D8]
0x140267213  call    TxfScanForHighestTxfFileId
0x140267218  mov     ebx, eax
0x14026721a  mov     [rsp+378h+var_334], eax
0x14026721e  test    eax, eax
0x140267220  jns     loc_140267362
0x140267226  mov     rcx, rdi
0x140267229  call    TxfRmInForcedRecovery
0x14026722e  test    al, al
0x140267230  jz      loc_140267362
0x140267236  mov     [rsp+378h+cMaxReadBuffers], ebx
0x14026723a  lea     rax, aStatus; "Status"
0x140267241  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x140267246  mov     [rsp+378h+cbMarshallingBuffer], 540h
0x14026724e  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x140267255  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14026725c  xor     edx, edx; Level
0x14026725e  mov     ecx, 82h; ComponentId
0x140267263  call    cs:__imp_DbgPrintEx
0x14026726a  nop     dword ptr [rax+rax+00h]
0x14026726f  mov     r13, 408000001h
0x140267279  cmp     ebx, 0C0000017h
0x14026727f  jz      loc_14026731E
0x140267285  lea     eax, [rbx+3FFFFF81h]
0x14026728b  cmp     eax, 22h ; '"'
0x14026728e  ja      short loc_14026729C
0x140267290  cdqe
0x140267292  bt      r13, rax
0x140267296  jb      loc_14026731E
0x14026729c  cmp     ebx, 0C01A002Bh
0x1402672a2  jz      short loc_140267302
0x1402672a4  cmp     ebx, 0C000026Eh
0x1402672aa  jz      short loc_140267302
0x1402672ac  cmp     ebx, 0C0000185h
0x1402672b2  jz      short loc_140267302
0x1402672b4  cmp     ebx, 0C0000148h
0x1402672ba  jz      short loc_140267302
0x1402672bc  lea     eax, [rbx+3FFFFF63h]
0x1402672c2  mov     r15, 800000041h
0x1402672cc  cmp     eax, 23h ; '#'
0x1402672cf  ja      short loc_1402672D9
0x1402672d1  cdqe
0x1402672d3  bt      r15, rax
0x1402672d7  jb      short loc_14026730C
0x1402672d9  lea     eax, [rbx+3FFFFFF3h]
0x1402672df  mov     r14d, 200043h
0x1402672e5  cmp     eax, 15h
0x1402672e8  ja      short loc_1402672F0
0x1402672ea  bt      r14d, eax
0x1402672ee  jb      short loc_140267312
0x1402672f0  cmp     ebx, 80000016h
0x1402672f6  jz      short loc_140267312
0x1402672f8  cmp     ebx, 0C01A002Fh
0x1402672fe  jnz     short loc_140267338
0x140267300  jmp     short loc_140267312
0x140267302  mov     r15, 800000041h
0x14026730c  mov     r14d, 200043h
0x140267312  mov     rax, cs:TxfData
0x140267319  inc     dword ptr [rax+10h]
0x14026731c  jmp     short loc_140267338
0x14026731e  mov     rax, cs:TxfData
0x140267325  inc     dword ptr [rax+0Ch]
0x140267328  mov     r15, 800000041h
0x140267332  mov     r14d, 200043h
0x140267338  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x140267341  mov     r9d, ebx
0x140267344  mov     r8d, 1
0x14026734a  mov     rdx, rdi
0x14026734d  lea     rcx, [rsp+378h+var_2D8]
0x140267355  call    TxfHandleRecoveryError
0x14026735a  mov     ebx, eax
0x14026735c  mov     [rsp+378h+var_334], eax
0x140267360  jmp     short loc_14026737C
0x140267362  mov     r13, 408000001h
0x14026736c  mov     r15, 800000041h
0x140267376  mov     r14d, 200043h
0x14026737c  test    ebx, ebx
0x14026737e  jns     short loc_14026739E
0x140267380  mov     r9d, 300546h
0x140267386  lea     rcx, [rsp+378h+var_2D8]
0x14026738e  mov     r8d, ebx
0x140267391  mov     rdx, rdi
0x140267394  call    TxfHardErrorFcn
0x140267399  jmp     loc_140267EF8
0x14026739e  mov     ebx, 200h
0x1402673a3  test    [rdi+80h], ebx
0x1402673a9  jz      loc_140267685
0x1402673af  lea     rcx, [rsp+378h+var_2D8]
0x1402673b7  call    NtfsPurgeFileRecordCache
0x1402673bc  or      [rsp+378h+var_2D4], ebx
0x1402673c3  lea     rdx, [rdi+1C8h]; plsnEnd
0x1402673ca  mov     rcx, [rdi+1F0h]; plfoLog
0x1402673d1  call    cs:__imp_ClfsSetEndOfLog
0x1402673d8  nop     dword ptr [rax+rax+00h]
0x1402673dd  mov     ebx, eax
0x1402673df  mov     [rsp+378h+var_334], eax
0x1402673e3  btr     [rsp+378h+var_2D4], 9
0x1402673ec  test    eax, eax
0x1402673ee  jns     loc_1402674EA
0x1402673f4  mov     rcx, rdi
0x1402673f7  call    TxfRmInForcedRecovery
0x1402673fc  test    al, al
0x1402673fe  jz      loc_1402674EA
0x140267404  mov     [rsp+378h+cMaxReadBuffers], ebx
0x140267408  lea     rax, aStatus; "Status"
0x14026740f  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x140267414  mov     [rsp+378h+cbMarshallingBuffer], 55Ah
0x14026741c  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x140267423  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14026742a  xor     edx, edx; Level
0x14026742c  mov     ecx, 82h; ComponentId
0x140267431  call    cs:__imp_DbgPrintEx
0x140267438  nop     dword ptr [rax+rax+00h]
0x14026743d  cmp     ebx, 0C0000017h
0x140267443  jz      short loc_1402674B8
0x140267445  lea     eax, [rbx+3FFFFF81h]
0x14026744b  cmp     eax, 22h ; '"'
0x14026744e  ja      short loc_140267458
0x140267450  cdqe
0x140267452  bt      r13, rax
0x140267456  jb      short loc_1402674B8
0x140267458  cmp     ebx, 0C01A002Bh
0x14026745e  jz      short loc_1402674AC
0x140267460  cmp     ebx, 0C000026Eh
0x140267466  jz      short loc_1402674AC
0x140267468  cmp     ebx, 0C0000185h
0x14026746e  jz      short loc_1402674AC
0x140267470  cmp     ebx, 0C0000148h
0x140267476  jz      short loc_1402674AC
0x140267478  lea     eax, [rbx+3FFFFF63h]
0x14026747e  cmp     eax, 23h ; '#'
0x140267481  ja      short loc_14026748B
0x140267483  cdqe
0x140267485  bt      r15, rax
0x140267489  jb      short loc_1402674AC
0x14026748b  lea     eax, [rbx+3FFFFFF3h]
0x140267491  cmp     eax, 15h
0x140267494  ja      short loc_14026749C
0x140267496  bt      r14d, eax
0x14026749a  jb      short loc_1402674AC
0x14026749c  cmp     ebx, 80000016h
0x1402674a2  jz      short loc_1402674AC
0x1402674a4  cmp     ebx, 0C01A002Fh
0x1402674aa  jnz     short loc_1402674C2
0x1402674ac  mov     rax, cs:TxfData
0x1402674b3  inc     dword ptr [rax+10h]
0x1402674b6  jmp     short loc_1402674C2
0x1402674b8  mov     rax, cs:TxfData
0x1402674bf  inc     dword ptr [rax+0Ch]
0x1402674c2  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x1402674cb  mov     r9d, ebx
0x1402674ce  mov     r8d, 2
0x1402674d4  mov     rdx, rdi
0x1402674d7  lea     rcx, [rsp+378h+var_2D8]
0x1402674df  call    TxfHandleRecoveryError
0x1402674e4  mov     ebx, eax
0x1402674e6  mov     [rsp+378h+var_334], eax
0x1402674ea  lea     rcx, [rsp+378h+var_2D8]
0x1402674f2  test    ebx, ebx
0x1402674f4  jns     short loc_140267501
0x1402674f6  mov     r9d, 300560h
0x1402674fc  jmp     loc_14026738E
0x140267501  call    NtfsPurgeFileRecordCache
0x140267506  bts     [rsp+378h+var_2D4], 9
0x14026750f  lea     rbx, [rdi+200h]
0x140267516  mov     rcx, [rbx]; pvMarshalContext
0x140267519  call    cs:__imp_ClfsDeleteMarshallingArea
0x140267520  nop     dword ptr [rax+rax+00h]
0x140267525  mov     [rsp+378h+ppvMarshalContext], rbx; ppvMarshalContext
0x14026752a  mov     [rsp+378h+cMaxReadBuffers], 14h; cMaxReadBuffers
0x140267532  mov     [rsp+378h+cMaxWriteBuffers], 0Ah; cMaxWriteBuffers
0x14026753a  mov     [rsp+378h+cbMarshallingBuffer], 40000h; cbMarshallingBuffer
0x140267542  xor     r9d, r9d; pfnFreeBuffer
0x140267545  xor     r8d, r8d; pfnAllocBuffer
0x140267548  mov     edx, cs:PoolType; ePoolType
0x14026754e  mov     rcx, [rdi+1F0h]; plfoLog
0x140267555  call    cs:__imp_ClfsCreateMarshallingArea
0x14026755c  nop     dword ptr [rax+rax+00h]
0x140267561  mov     ebx, eax
0x140267563  mov     [rsp+378h+var_334], eax
0x140267567  btr     [rsp+378h+var_2D4], 9
0x140267570  test    eax, eax
0x140267572  jns     loc_14026766E
0x140267578  mov     rcx, rdi
0x14026757b  call    TxfRmInForcedRecovery
0x140267580  test    al, al
0x140267582  jz      loc_14026766E
0x140267588  mov     [rsp+378h+cMaxReadBuffers], ebx
0x14026758c  lea     rax, aStatus; "Status"
0x140267593  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x140267598  mov     [rsp+378h+cbMarshallingBuffer], 57Ah
0x1402675a0  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x1402675a7  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x1402675ae  xor     edx, edx; Level
0x1402675b0  mov     ecx, 82h; ComponentId
0x1402675b5  call    cs:__imp_DbgPrintEx
0x1402675bc  nop     dword ptr [rax+rax+00h]
0x1402675c1  cmp     ebx, 0C0000017h
0x1402675c7  jz      short loc_14026763C
0x1402675c9  lea     eax, [rbx+3FFFFF81h]
0x1402675cf  cmp     eax, 22h ; '"'
0x1402675d2  ja      short loc_1402675DC
0x1402675d4  cdqe
0x1402675d6  bt      r13, rax
0x1402675da  jb      short loc_14026763C
0x1402675dc  cmp     ebx, 0C01A002Bh
0x1402675e2  jz      short loc_140267630
0x1402675e4  cmp     ebx, 0C000026Eh
0x1402675ea  jz      short loc_140267630
0x1402675ec  cmp     ebx, 0C0000185h
0x1402675f2  jz      short loc_140267630
0x1402675f4  cmp     ebx, 0C0000148h
0x1402675fa  jz      short loc_140267630
0x1402675fc  lea     eax, [rbx+3FFFFF63h]
0x140267602  cmp     eax, 23h ; '#'
0x140267605  ja      short loc_14026760F
0x140267607  cdqe
0x140267609  bt      r15, rax
0x14026760d  jb      short loc_140267630
0x14026760f  lea     eax, [rbx+3FFFFFF3h]
0x140267615  cmp     eax, 15h
0x140267618  ja      short loc_140267620
0x14026761a  bt      r14d, eax
0x14026761e  jb      short loc_140267630
0x140267620  cmp     ebx, 80000016h
0x140267626  jz      short loc_140267630
0x140267628  cmp     ebx, 0C01A002Fh
0x14026762e  jnz     short loc_140267646
0x140267630  mov     rax, cs:TxfData
0x140267637  inc     dword ptr [rax+10h]
0x14026763a  jmp     short loc_140267646
0x14026763c  mov     rax, cs:TxfData
0x140267643  inc     dword ptr [rax+0Ch]
0x140267646  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x14026764f  mov     r9d, ebx
0x140267652  mov     r8d, 2
0x140267658  mov     rdx, rdi
0x14026765b  lea     rcx, [rsp+378h+var_2D8]
0x140267663  call    TxfHandleRecoveryError
0x140267668  mov     ebx, eax
0x14026766a  mov     [rsp+378h+var_334], eax
0x14026766e  test    ebx, ebx
  ... truncated ...
```
