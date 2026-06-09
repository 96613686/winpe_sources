# TxfUndoMoveAttr

- ea: `0x14010dca4`
- end: `0x14010f099`
- name: `TxfUndoMoveAttr`
- size: `5109`
- prototype: ``
- caller_count: `3`
- callee_count: `36`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140106398`
- `0x140133f80`
- `0x1401d8390`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x14002c3d0`
- `0x1400388bc`
- `0x1400410a8`
- `0x14005286c`
- `0x140059740`
- `0x1400f95cc`
- `0x140106888`
- `0x14010a938`
- `0x14010d094`
- `0x14010dca4`
- `0x140125100`
- `0x140133244`
- `0x1401403d0`
- `0x140141a3c`
- `0x1401597b8`
- `0x140162110`
- `0x140191424`
- `0x140195324`
- `0x14019a768`
- `0x1401aab70`
- `0x1401c0130`
- `0x1401db1b4`
- `0x1401e06b0`
- `0x1401fd870`
- `0x14021d748`
- `0x14022bd14`
- `0x140278dd4`
- `0x14029135c`
- `0x14029c0a8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14010f034`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c621c`
- `ntoskrnl!ObfDereferenceObject` at `0x14010f034`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c621c`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14010f005`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c61ec`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14010f005`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c61ec`
- `ntoskrnl!DbgPrintEx` at `0x14010dec4`
- `ntoskrnl!DbgPrintEx` at `0x14010dffa`
- `ntoskrnl!DbgPrintEx` at `0x14010e41d`
- `ntoskrnl!DbgPrintEx` at `0x14010e575`
- `ntoskrnl!DbgPrintEx` at `0x14010eed7`
- `ntoskrnl!DbgPrintEx` at `0x14010f079`
- `ntoskrnl!DbgPrintEx` at `0x14010dec4`
- `ntoskrnl!DbgPrintEx` at `0x14010dffa`
- `ntoskrnl!DbgPrintEx` at `0x14010e41d`
- `ntoskrnl!DbgPrintEx` at `0x14010e575`
- `ntoskrnl!DbgPrintEx` at `0x14010eed7`
- `ntoskrnl!DbgPrintEx` at `0x14010f079`
- `ntoskrnl!ExRaiseStatus` at `0x14010e44b`
- `ntoskrnl!ExRaiseStatus` at `0x14010e644`
- `ntoskrnl!ExRaiseStatus` at `0x14010e44b`
- `ntoskrnl!ExRaiseStatus` at `0x14010e644`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010de81`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010dfb7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010e2a8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb07`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb23`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb8d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010de81`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010dfb7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010e2a8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb07`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb23`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb8d`

## pseudocode

```c
char __fastcall TxfUndoMoveAttr(__int64 a1, CLFS_LSN *a2, __int64 a3, const CLFS_LSN *a4, CLFS_LSN *a5, int a6)
{
  CLFS_LSN *v7; // r15
  const CLFS_LSN *v9; // rsi
  __int64 n; // rax
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // r12
  const CLFS_LSN *v14; // r14
  __int64 v15; // r15
  BOOLEAN v16; // al
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r8
  BOOLEAN v23; // al
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // eax
  WCHAR *v29; // rax
  CLFS_LSN v30; // rbx
  __int64 v31; // r8
  unsigned int v32; // eax
  const CLFS_LSN *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  char v36; // r14
  __int64 v37; // r9
  const CLFS_LSN *v38; // rcx
  CLFS_LSN *v39; // rbx
  BOOLEAN ShouldProcessRedoCancelBasedOnLsn; // al
  __int64 v41; // r8
  __int64 v42; // r8
  unsigned int i; // eax
  const CLFS_LSN *v44; // rcx
  unsigned int j; // eax
  const CLFS_LSN *v46; // rcx
  __int64 v47; // rcx
  int v48; // ecx
  unsigned __int64 v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // rax
  __int64 v52; // rdx
  int v53; // eax
  char v54; // bl
  char v55; // dl
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  unsigned int k; // eax
  __int64 v60; // r8
  unsigned int m; // eax
  const CLFS_LSN *v62; // rcx
  __int16 *v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rax
  __int16 *v66; // r12
  __int64 v67; // rcx
  int v68; // r9d
  __int64 v69; // rcx
  CLFS_RECORD_INDEX idxRecord; // r12d
  unsigned int v71; // eax
  CLFS_RECORD_INDEX v72; // eax
  BOOLEAN v73; // al
  BOOLEAN v74; // al
  CLFS_LSN v75; // rdx
  __int64 v76; // r14
  __int16 *v77; // rax
  int v78; // ecx
  __int64 v79; // rdx
  int v80; // ecx
  __int64 v81; // rdx
  __int64 v82; // rsi
  __int16 *v83; // r14
  unsigned __int64 v84; // rax
  __int64 v85; // rdx
  unsigned __int64 v86; // rax
  __int64 v87; // rdx
  int v88; // eax
  PFILE_OBJECT v89; // rbx
  _DWORD *FsContext; // rax
  int v92; // [rsp+20h] [rbp-188h]
  int v93; // [rsp+20h] [rbp-188h]
  int v94; // [rsp+30h] [rbp-178h]
  int v95; // [rsp+30h] [rbp-178h]
  char v96; // [rsp+70h] [rbp-138h]
  char v97; // [rsp+71h] [rbp-137h] BYREF
  char v98; // [rsp+72h] [rbp-136h] BYREF
  char v99; // [rsp+73h] [rbp-135h]
  char v100; // [rsp+74h] [rbp-134h]
  char v101; // [rsp+75h] [rbp-133h]
  char v102; // [rsp+76h] [rbp-132h]
  CLFS_LSN v103; // [rsp+78h] [rbp-130h] BYREF
  UNICODE_STRING v104; // [rsp+80h] [rbp-128h] BYREF
  unsigned int v105; // [rsp+90h] [rbp-118h]
  unsigned int v106; // [rsp+94h] [rbp-114h]
  unsigned int v107; // [rsp+98h] [rbp-110h]
  unsigned int v108; // [rsp+9Ch] [rbp-10Ch]
  unsigned int v109; // [rsp+A0h] [rbp-108h]
  CLFS_RECORD_INDEX v110; // [rsp+A4h] [rbp-104h]
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-100h] BYREF
  __int16 *v112; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v113; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v114; // [rsp+C0h] [rbp-E8h] BYREF
  __int64 v115; // [rsp+C8h] [rbp-E0h]
  __int64 v116; // [rsp+D0h] [rbp-D8h]
  CLFS_LSN v117; // [rsp+D8h] [rbp-D0h]
  const CLFS_LSN *v118; // [rsp+E0h] [rbp-C8h]
  _QWORD v119[2]; // [rsp+E8h] [rbp-C0h] BYREF
  __int128 v120; // [rsp+F8h] [rbp-B0h] BYREF
  _QWORD v121[19]; // [rsp+110h] [rbp-98h] BYREF

  v7 = a2;
  v117 = a2[26];
  v119[1] = v117.ullOffset;
  v9 = 0;
  v118 = 0;
  v119[0] = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  memset(v121, 0, 0x58u);
  v96 = 0;
  v104 = 0;
  FileObject = 0;
  v101 = 0;
  v97 = 0;
  v100 = 0;
  v98 = 0;
  v120 = 0;
  v103.ullOffset = 0;
  v102 = 0;
  v110 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x70u )
    TxfRaiseBoundsCheckFailure();
  *(_QWORD *)&v120 = *(_QWORD *)(a3 + 80);
  TxfOpenFileCheckId(
    a1,
    (PRTL_AVL_TABLE *)v7,
    a3,
    (unsigned __int64 *)&v120,
    0,
    2,
    *(_BYTE *)(a3 + 74) & 8,
    0,
    v119,
    &v113);
  LODWORD(n) = TxfOpenFileCheckId(
                 a1,
                 (PRTL_AVL_TABLE *)v7,
                 a3,
                 (unsigned __int64 *)(a3 + 88),
                 0,
                 2,
                 *(_BYTE *)(a3 + 74) & 8,
                 0,
                 &v112,
                 &v114);
  v12 = n;
  if ( (_DWORD)n == -1072103368 )
    goto LABEL_242;
  v13 = v113;
  if ( v113 )
    v14 = *(const CLFS_LSN **)(*(_QWORD *)(v113 + 24) + 184LL);
  else
    v14 = 0;
  v15 = v114;
  if ( v114 )
    v9 = *(const CLFS_LSN **)(*(_QWORD *)(v114 + 24) + 184LL);
  v118 = v9;
  v11 = 0;
  if ( !v113 )
    goto LABEL_51;
  if ( !v114 )
  {
    v16 = ClfsLsnLess(v14 + 30, a4);
    v11 = 0;
    if ( v16 )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20172, "Status", v12);
      if ( v12 == -1073741801
        || (v17 = (unsigned int)(v12 + 1073741697), (unsigned int)v17 <= 0x22)
        && (v18 = 0x408000001LL, _bittest64(&v18, v17)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v12 == -1072037845
             || v12 == -1073741202
             || v12 == -1073741435
             || v12 == -1073741496
             || (v19 = (unsigned int)(v12 + 1073741667), (unsigned int)v19 <= 0x23)
             && (v20 = 0x800000041LL, _bittest64(&v20, v19))
             || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
             && (v21 = 2097219, _bittest(&v21, v11))
             || v12 == -2147483626
             || v12 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      LOBYTE(n) = NtfsStatusDebugFlags;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_30;
      v22 = 3231437;
LABEL_29:
      LOBYTE(n) = NtfsStatusTraceAndDebugInternal(0, 3221225730LL, v22);
LABEL_30:
      v7 = a2;
LABEL_242:
      v36 = 0;
      goto LABEL_243;
    }
  }
  if ( !v13 )
  {
LABEL_51:
    if ( v15 )
    {
      v23 = ClfsLsnLess(v9 + 30, a4);
      v11 = 0;
      if ( v23 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20186, "Status", v12);
        if ( v12 == -1073741801
          || (v24 = (unsigned int)(v12 + 1073741697), (unsigned int)v24 <= 0x22)
          && (v25 = 0x408000001LL, _bittest64(&v25, v24)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v12 == -1072037845
               || v12 == -1073741202
               || v12 == -1073741435
               || v12 == -1073741496
               || (v26 = (unsigned int)(v12 + 1073741667), (unsigned int)v26 <= 0x23)
               && (v27 = 0x800000041LL, _bittest64(&v27, v26))
               || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
               && (v28 = 2097219, _bittest(&v28, v11))
               || v12 == -2147483626
               || v12 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        LOBYTE(n) = NtfsStatusDebugFlags;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_30;
        v22 = 3231451;
        goto LABEL_29;
      }
    }
    if ( !v13 )
      goto LABEL_224;
  }
  if ( !v15 )
  {
LABEL_224:
    v7 = a2;
    LODWORD(n) = a2[2].offset.idxRecord;
    if ( (n & 0x10) == 0 )
      goto LABEL_242;
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20203, "Status", v12);
    if ( v12 == -1073741801
      || (v84 = (unsigned int)(v12 + 1073741697), (unsigned int)v84 <= 0x22)
      && (v85 = 0x408000001LL, _bittest64(&v85, v84)) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v12 == -1072037845
           || v12 == -1073741202
           || v12 == -1073741435
           || v12 == -1073741496
           || (v86 = (unsigned int)(v12 + 1073741667), (unsigned int)v86 <= 0x23)
           && (v87 = 0x800000041LL, _bittest64(&v87, v86))
           || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
           && (v88 = 2097219, _bittest(&v88, v11))
           || v12 == -2147483626
           || v12 == -1072037841 )
    {
      ++LODWORD((*TxfData)[2]);
    }
    LOBYTE(n) = NtfsStatusDebugFlags;
    if ( NtfsStatusDebugFlags )
      LOBYTE(n) = NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3231468);
    goto LABEL_133;
  }
  v104.MaximumLength = 2 * *(_WORD *)(a3 + 104);
  v104.Length = v104.MaximumLength;
  if ( v104.MaximumLength )
    v29 = (WCHAR *)(a3 + *(unsigned __int16 *)(a3 + 106));
  else
    v29 = 0;
  v104.Buffer = v29;
  v30 = v117;
  NtfsAcquireSharedVcb(a1, *(_QWORD *)(v117.ullOffset + 16), 0);
  v101 = 1;
  if ( (*(_DWORD *)(*(_QWORD *)(v30.ullOffset + 16) + 4LL) & 1) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 3231500);
    NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3231500);
  }
  if ( *(_DWORD *)(a3 + 108) == 128 )
  {
    if ( !v9[14].ullOffset )
    {
      NtfsAcquireExclusiveFcb(a1, v9, 0, 0);
      NtfsAddPagingIoToFcb(a1, v9, 0);
      NtfsReleaseFcbEx(a1, v9, 0);
    }
    LOBYTE(v31) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v9, v31) )
    {
      v32 = 0;
      v105 = 0;
      while ( v32 < 2 )
      {
        v33 = *(const CLFS_LSN **)(a1 + 8LL * v32 + 48);
        if ( !v33 || v33 == v9 )
        {
          *(_QWORD *)(a1 + 8LL * v32 + 48) = v9;
          break;
        }
        v105 = ++v32;
      }
    }
  }
  NtfsAcquireExclusiveFcb(a1, v9, 0, 0);
  if ( (a2[2].offset.idxRecord & 0x1000) == 0 )
  {
    if ( a6 )
    {
      LOBYTE(v35) = 1;
      v7 = a2;
      if ( !(unsigned __int8)TxfAlreadyWroteClr(a1, a2, 15, v35) )
      {
        memset(v121, 0, 0x58u);
        v96 = 1;
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v14[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
            NtfsAddPagingIoToFcb(a1, v14, 0);
            NtfsReleaseFcbEx(a1, v14, 0);
          }
          LOBYTE(v42) = 1;
          NtfsAcquirePagingResourceExclusive(0, v14, v42);
          v106 = 0;
          for ( i = 0; ; ++i )
          {
            v106 = i;
            if ( i >= 2 )
              break;
            v44 = *(const CLFS_LSN **)(a1 + 8LL * i + 48);
            if ( !v44 || v44 == v14 )
            {
              *(_QWORD *)(a1 + 8LL * i + 48) = v14;
              break;
            }
          }
          v100 = 1;
          v97 = 1;
        }
        NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
        v97 = 1;
        v98 = 1;
        LOBYTE(v94) = 0;
        v99 = NtfsLookupInFileRecord(a1, v14, &v14[1], *(unsigned int *)(a3 + 108), &v104, 0, v94, 0, 0, v121);
        if ( !v99 )
        {
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "txftrans.c",
            20404,
            "Status",
            -1073741566);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3231674);
          ExRaiseStatus(-1073741566);
        }
        TxfWriteMoveAttrLogRecord(a1, (_DWORD)a2, 0, 0, 0, a3);
      }
      v103 = a2[37];
    }
    else
    {
      v38 = v14 + 30;
      v39 = a5;
      if ( a5 )
      {
        ShouldProcessRedoCancelBasedOnLsn = TxfShouldProcessRedoCancelBasedOnLsn(v38, v34, &v14[30], a4, a5);
      }
      else
      {
        v39 = (CLFS_LSN *)a4;
        ShouldProcessRedoCancelBasedOnLsn = ClfsLsnLess(v38, a4);
      }
      if ( !ShouldProcessRedoCancelBasedOnLsn )
      {
        LOBYTE(n) = v98;
        v7 = a2;
        goto LABEL_97;
      }
      v103 = *v39;
      v7 = a2;
    }
    LOBYTE(n) = 1;
LABEL_97:
    if ( !(_BYTE)n )
    {
LABEL_133:
      v36 = 0;
      goto LABEL_243;
    }
    if ( !v97 )
    {
      if ( *(_DWORD *)(a3 + 108) == 128 )
      {
        if ( !v14[14].ullOffset )
        {
          NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
          NtfsAddPagingIoToFcb(a1, v14, 0);
          NtfsReleaseFcbEx(a1, v14, 0);
        }
        LOBYTE(v41) = 1;
        NtfsAcquirePagingResourceExclusive(0, v14, v41);
        v107 = 0;
        for ( j = 0; ; ++j )
        {
          v107 = j;
          if ( j >= 2 )
            break;
          v46 = *(const CLFS_LSN **)(a1 + 8LL * j + 48);
          if ( !v46 || v46 == v14 )
          {
            *(_QWORD *)(a1 + 8LL * j + 48) = v14;
            break;
          }
        }
        v100 = 1;
        v97 = 1;
      }
      NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
      v98 = 1;
    }
    v47 = *(unsigned int *)(a3 + 108);
    if ( *(_DWORD *)(a3 + 108) != 128 )
    {
      if ( *(_DWORD *)(a3 + 108) != 192 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 21038, "Status", v47);
        v48 = *(_DWORD *)(a3 + 108);
        if ( v48 == -1073741801
          || (v49 = (unsigned int)(v48 + 1073741697), (unsigned int)v49 <= 0x22)
          && (v50 = 0x408000001LL, _bittest64(&v50, v49)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v48 == -1072037845
               || v48 == -1073741202
               || v48 == -1073741435
               || v48 == -1073741496
               || (v51 = (unsigned int)(v48 + 1073741667), (unsigned int)v51 <= 0x23)
               && (v52 = 0x800000041LL, _bittest64(&v52, v51))
               || (unsigned int)(v48 + 1073741811) <= 0x15 && (v53 = 2097219, _bittest(&v53, v48 + 1073741811))
               || v48 == -2147483626
               || v48 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3222863920LL, 3232303);
        ExRaiseStatus(-1072103376);
      }
      if ( v96 )
      {
        NtfsCleanupAttributeContext(v47, v121);
        v96 = 0;
      }
      LOBYTE(n) = TxfRedoUndoMoveReparsePoint(a1, v103.ullOffset);
      goto LABEL_133;
    }
    if ( v96 )
      NtfsCleanupAttributeContext(v47, v121);
    memset(v121, 0, 0x58u);
    v54 = 1;
    LOBYTE(v94) = 0;
    LOBYTE(n) = NtfsLookupInFileRecord(a1, v14, &v14[1], *(unsigned int *)(a3 + 108), &v104, 0, v94, 0, 0, v121);
    v55 = n;
    v99 = n;
    if ( (_BYTE)n && !v104.Length )
    {
      LOBYTE(n) = v121[0];
      if ( *(_BYTE *)(v121[0] + 8LL) )
      {
        n = -*(_QWORD *)(v121[0] + 40LL);
        LOBYTE(v11) = *(_QWORD *)(v121[0] + 40LL) != 0 ? v55 : 0;
        v55 = v11;
        v99 = v11;
      }
      else if ( !*(_DWORD *)(v121[0] + 16LL) )
      {
        v55 = 0;
        v99 = 0;
      }
    }
    if ( !v55 )
    {
      v36 = 0;
      goto LABEL_244;
    }
    NtfsReleaseFcbEx(a1, v14, 0);
    v98 = 0;
    if ( v100 )
    {
      if ( a1 )
      {
        v108 = 0;
        for ( k = 0; ; ++k )
        {
          v108 = k;
          if ( k >= 2 )
            break;
          v56 = k;
          if ( *(const CLFS_LSN **)(a1 + 8LL * k + 48) == v14 )
            *(_QWORD *)(a1 + 8LL * k + 48) = 0;
        }
      }
      NtfsReleasePagingResourcePriv(v56, v14, v57, v58);
      v97 = 0;
    }
    NtfsFlushFcb(a1, (_DWORD)v9);
    if ( v14[14].ullOffset )
    {
      LOBYTE(v60) = 1;
      NtfsAcquirePagingResourceExclusive(0, v14, v60);
      v109 = 0;
      for ( m = 0; ; ++m )
      {
        v109 = m;
        if ( m >= 2 )
          break;
        v62 = *(const CLFS_LSN **)(a1 + 8LL * m + 48);
        if ( !v62 || v62 == v14 )
        {
          *(_QWORD *)(a1 + 8LL * m + 48) = v14;
          break;
        }
      }
      v97 = 1;
    }
    NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
    v98 = 1;
    v63 = NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, 0, 0);
    v64 = (__int64)v63;
    v115 = (__int64)v63;
    if ( v63 )
    {
      v65 = *((_QWORD *)v63 + 66);
      if ( v65 )
        *(_DWORD *)(v65 + 24) = *(_DWORD *)(v65 + 24);
    }
    v66 = NtfsCreateScb(a1, (__int64)v14, *(_DWORD *)(a3 + 108), &v104, 0, 0, 0);
    v112 = v66;
    NtfsCleanupAttributeContext(v67, v121);
    memset(v121, 0, 0x58u);
    v96 = 1;
    LOBYTE(v95) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *((_QWORD *)v66 + 23),
                             *((_QWORD *)v66 + 23) + 8LL,
                             *((unsigned int *)v66 + 64),
                             v66 + 132,
                             0,
                             v95,
                             0,
                             0,
                             v121)
      && (*((_DWORD *)v66 + 128) & 4) == 0 )
    {
      v64 = 0xA9003150A6LL;
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 3231910, v68, *((_QWORD *)v66 + 23) + 8LL, *((_QWORD *)v66 + 23), 0);
      NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9003150A6LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3231910);
      NtfsRaiseStatusInternal(a1, -1073741566, *((_QWORD *)v66 + 23) + 8, *((_QWORD *)v66 + 23), 3231910);
    }
    TxfPrepareToMoveAttribute(a1, (int)v14, (int)v9, v121, 0);
    TxfMoveAttrInternal(a1, (_DWORD)v14, v121, 0, (__int64)&FileObject);
    NtfsConditionallyFixupQuota(a1, v9);
    NtfsConditionallyFixupQuota(a1, v14);
    if ( !v64 )
    {
      v64 = (__int64)NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, 0, 0);
      v115 = v64;
    }
    idxRecord = v9[22].offset.idxRecord;
    v110 = idxRecord;
    v102 = 1;
    if ( !v104.Length )
    {
      if ( *(_BYTE *)(v64 + 460) )
        v71 = idxRecord | 0x800;
      else
        v71 = idxRecord & 0xFFFFF7FF;
      v9[22].offset.idxRecord = v71;
      v9[23].offset.idxRecord |= 4u;
    }
    v72 = v9[22].offset.idxRecord;
    if ( *(__int16 *)(v64 + 460) >= 0 )
    {
      if ( (v72 & 0x200) == 0 )
        goto LABEL_180;
      NtfsCleanupAttributeContext(v69, v121);
      v96 = 0;
      if ( (unsigned __int8)NtfsIsSparseStreamRemaining(a1, (int)v9) )
        goto LABEL_180;
      v9[22].offset.idxRecord &= ~0x200u;
    }
    else
    {
      v9[22].offset.idxRecord = v72 | 0x200;
    }
    v9[23].offset.idxRecord |= 4u;
LABEL_180:
    if ( v9[22].offset.idxRecord != idxRecord )
      NtfsUpdateStandardInformation(a1, (_DWORD)v9);
    if ( ClfsLsnLess(v9 + 30, &v103) )
    {
      v73 = ClfsLsnLess(v9 + 30, &v103);
      TxfUpdateTxfDataAttributeMembers(
        a1,
        (int)v9,
        v92,
        0,
        (v9->offset.cidContainer & 0x100000) == 0,
        (__int64)&v103,
        (unsigned __int64)&v103 & -(__int64)(v73 != 0),
        0,
        0,
        0,
        0);
      v74 = ClfsLsnLess(v14 + 30, &v103);
      TxfUpdateTxfDataAttributeMembers(
        a1,
        (int)v14,
        v93,
        0,
        (v14->offset.cidContainer & 0x100000) == 0,
        (__int64)&v103,
        (unsigned __int64)&v103 & -(__int64)(v74 != 0),
        0,
        0,
        0,
        0);
    }
    LOBYTE(n) = NtfsCheckpointCurrentTransaction(a1);
    v75 = v9[41];
    if ( v75.ullOffset )
    {
      v116 = 0;
      n = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))TxfCreateTxfScb)(
            (const CLFS_LSN)v9[12].ullOffset,
            (CLFS_LSN)v75.ullOffset,
            *(unsigned int *)(a3 + 108),
            &v104,
            1,
            1);
      v76 = n;
      v116 = n;
      if ( n )
      {
        v77 = NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, n, 0);
        if ( v77 )
        {
          if ( v77 != (__int16 *)v64 )
          {
            *(_QWORD *)(v64 + 464) = 0;
            *(_QWORD *)(v64 + 24) = 0;
            if ( (*(_DWORD *)(v64 + 200) & 0x20000) != 0 && *(__int64 *)(v64 + 32) < 0 && *(__int64 *)(v64 + 40) < 0 )
            {
              v78 = *(_DWORD *)(v64 + 200);
              if ( (v78 & 0x20000) != 0 )
              {
                v79 = *(_QWORD *)(v64 + 464);
                if ( v79 < 0 || *(__int64 *)(v64 + 40) > 0 && (!*(_QWORD *)(*(_QWORD *)(v64 + 288) + 16LL) || v79 > 0) )
                  *(_QWORD *)(v64 + 464) = 0;
              }
              *(_QWORD *)(v64 + 40) = 0;
            }
            *(_QWORD *)(v64 + 32) = 0;
            v80 = *(_DWORD *)(v64 + 200);
            if ( (v80 & 0x20000) != 0 )
            {
              v81 = *(_QWORD *)(v64 + 464);
              if ( v81 < 0 || *(__int64 *)(v64 + 40) > 0 && (!*(_QWORD *)(*(_QWORD *)(v64 + 288) + 16LL) || v81 > 0) )
                *(_QWORD *)(v64 + 464) = 0;
            }
            *(_QWORD *)(v64 + 40) = 0;
            *(_DWORD *)(v64 + 256) = 0;
            *(_DWORD *)(v64 + 512) |= 0x40u;
          }
          v64 = (__int64)v77;
          v115 = (__int64)v77;
          *((_DWORD *)v77 + 64) = 128;
          *((_DWORD *)v77 + 128) &= ~0x200000u;
          *(_DWORD *)(v76 + 24) &= 0xFFFFFFF9;
        }
        LOBYTE(n) = TxfDereferenceTxfScb((PVOID)v76);
        if ( v64 )
        {
          ClearFlagInterlocked(v64 + 200, 268960303);
          *(_DWORD *)(v64 + 512) &= 0xFFFEFFBF;
          LOBYTE(n) = NtfsUpdateScbFromAttribute(a1, v64, 0);
        }
      }
      else
      {
        v76 = *(_QWORD *)(v64 + 528);
        v116 = v76;
      }
      if ( v76 )
      {
        v82 = *(_QWORD *)(v76 + 56);
        v83 = v112;
        while ( v82 )
        {
          LODWORD(n) = *(_DWORD *)(v82 + 8);
          if ( (n & 1) != 0 )
            break;
          if ( *(_QWORD *)(v82 + 120) && *(__int16 **)(v82 + 112) == v83 )
          {
            TxfDetachBackupAttributeFromTxfVscb(v82);
            for ( n = *(_QWORD *)(v82 + 40); n; n = *(_QWORD *)(n + 40) )
              _InterlockedOr((volatile signed __int32 *)(n + 8), 0x800u);
          }
          v82 = *(_QWORD *)(v82 + 32);
        }
      }
    }
    if ( v64 )
    {
      v11 = *(_QWORD *)(v64 + 528);
      if ( v11 )
      {
        *(_QWORD *)(v11 + 96) = *(_QWORD *)(v64 + 40);
        *(_QWORD *)(*(_QWORD *)(v64 + 528) + 104LL) = *(_QWORD *)(v64 + 32);
        v11 = *(_QWORD *)(v64 + 528);
        LODWORD(n) = *(_DWORD *)(v11 + 24);
        *(_DWORD *)(v11 + 24) = n;
      }
    }
    v7 = a2;
    goto LABEL_133;
  }
  v36 = 1;
  v37 = *(_QWORD *)(v15 + 24);
  v7 = a2;
  LOBYTE(n) = TxfRebuildMoveAttrIsolationDuringRecovery(
                a1,
                (_DWORD)a2,
                *(_QWORD *)(v13 + 24),
                v37,
                (__int64)&v104,
                (__int64)&v97,
                (__int64)&v98);
LABEL_243:
  v54 = v96;
LABEL_244:
  if ( v101 )
    LOBYTE(n) = NtfsReleaseVcb(a1, *(_QWORD *)(v117.ullOffset + 16));
  if ( v54 )
    LOBYTE(n) = NtfsCleanupAttributeContext(v11, v121);
  v89 = FileObject;
  if ( FileObject )
  {
    if ( FileObject->PrivateCacheMap )
      CcUninitializeCacheMap(FileObject, 0, 0);
    FsContext = v89->FsContext;
    if ( FsContext && (FsContext[50] & 0x4000) == 0 )
    {
      *(_DWORD *)&v89->FileName.Length = 0;
      v89->FileName.Buffer = 0;
    }
    LOBYTE(n) = ObfDereferenceObject(v89);
  }
  if ( (v7[2].offset.idxRecord & 0x1000) != 0 && !v36 )
    LOBYTE(n) = DbgPrintEx(
                  0x82u,
                  0,
                  "%s:%d -- TxF corruption detected, %s == 0x%x",
                  "txftrans.c",
                  21102,
                  "Status",
                  -1073741823);
  return n;
}

```

## disassembly

```asm
0x14010dca4  mov     r11, rsp
0x14010dca7  mov     [r11+20h], r9
0x14010dcab  mov     [r11+10h], rdx
0x14010dcaf  mov     [r11+8], rcx
0x14010dcb3  push    rbx
0x14010dcb4  push    rsi
0x14010dcb5  push    rdi
0x14010dcb6  push    r12
0x14010dcb8  push    r13
0x14010dcba  push    r14
0x14010dcbc  push    r15
0x14010dcbe  sub     rsp, 170h
0x14010dcc5  mov     r13, r8
0x14010dcc8  mov     r15, rdx
0x14010dccb  mov     rdi, rcx
0x14010dcce  mov     rax, [rdx+0D0h]
0x14010dcd5  mov     [rsp+1A8h+var_D0], rax
0x14010dcdd  mov     [rsp+1A8h+var_B8], rax
0x14010dce5  xor     esi, esi
0x14010dce7  mov     [r11-0C8h], rsi
0x14010dcee  mov     [r11-0C0h], rsi
0x14010dcf5  mov     [r11-0F8h], rsi
0x14010dcfc  mov     [r11-0F0h], rsi
0x14010dd03  mov     [r11-0E8h], rsi
0x14010dd0a  xor     edx, edx; Val
0x14010dd0c  lea     r8d, [rsi+58h]; Size
0x14010dd10  lea     rcx, [r11-98h]; void *
0x14010dd17  call    memset
0x14010dd1c  mov     [rsp+1A8h+var_138], sil
0x14010dd21  xorps   xmm0, xmm0
0x14010dd24  movups  [rsp+1A8h+var_128], xmm0
0x14010dd2c  mov     [rsp+1A8h+FileObject], rsi
0x14010dd34  mov     [rsp+1A8h+var_133], sil
0x14010dd39  mov     [rsp+1A8h+var_137], sil
0x14010dd3e  mov     [rsp+1A8h+var_134], sil
0x14010dd43  mov     [rsp+1A8h+var_136], sil
0x14010dd48  mov     [rsp+1A8h+arg_10], sil
0x14010dd50  movups  [rsp+1A8h+var_B0], xmm0
0x14010dd58  mov     qword ptr [rsp+1A8h+var_130], rsi
0x14010dd5d  mov     [rsp+1A8h+var_132], sil
0x14010dd62  mov     [rsp+1A8h+var_104], esi
0x14010dd69  cmp     dword ptr [r13+40h], 70h ; 'p'
0x14010dd6e  jnb     short loc_14010DD76
0x14010dd70  call    TxfRaiseBoundsCheckFailure
0x14010dd76  mov     rax, [r13+50h]
0x14010dd7a  mov     qword ptr [rsp+1A8h+var_B0], rax
0x14010dd82  mov     al, [r13+4Ah]
0x14010dd86  and     al, 8
0x14010dd88  lea     rcx, [rsp+1A8h+var_F0]
0x14010dd90  mov     [rsp+1A8h+var_160], rcx
0x14010dd95  lea     rcx, [rsp+1A8h+var_C0]
0x14010dd9d  mov     [rsp+1A8h+var_168], rcx
0x14010dda2  mov     [rsp+1A8h+var_170], rsi
0x14010dda7  mov     byte ptr [rsp+1A8h+var_178], al
0x14010ddab  mov     ebx, 2
0x14010ddb0  mov     [rsp+1A8h+var_180], ebx
0x14010ddb4  mov     qword ptr [rsp+1A8h+var_188], rsi
0x14010ddb9  lea     r9, [rsp+1A8h+var_B0]
0x14010ddc1  mov     r8, r13
0x14010ddc4  mov     rdx, r15
0x14010ddc7  mov     rcx, rdi
0x14010ddca  call    TxfOpenFileCheckId
0x14010ddcf  mov     al, [r13+4Ah]
0x14010ddd3  and     al, 8
0x14010ddd5  lea     r9, [r13+58h]
0x14010ddd9  lea     rcx, [rsp+1A8h+var_E8]
0x14010dde1  mov     [rsp+1A8h+var_160], rcx
0x14010dde6  lea     rcx, [rsp+1A8h+var_F8]
0x14010ddee  mov     [rsp+1A8h+var_168], rcx
0x14010ddf3  mov     [rsp+1A8h+var_170], rsi
0x14010ddf8  mov     byte ptr [rsp+1A8h+var_178], al
0x14010ddfc  mov     [rsp+1A8h+var_180], ebx
0x14010de00  mov     qword ptr [rsp+1A8h+var_188], rsi
0x14010de05  mov     r8, r13
0x14010de08  mov     rdx, r15
0x14010de0b  mov     rcx, rdi
0x14010de0e  call    TxfOpenFileCheckId
0x14010de13  mov     ebx, eax
0x14010de15  cmp     eax, 0C0190038h
0x14010de1a  jz      loc_14010EFA8
0x14010de20  mov     r12, [rsp+1A8h+var_F0]
0x14010de28  test    r12, r12
0x14010de2b  jz      short loc_14010DE3B
0x14010de2d  mov     rcx, [r12+18h]
0x14010de32  mov     r14, [rcx+0B8h]
0x14010de39  jmp     short loc_14010DE3E
0x14010de3b  mov     r14, rsi
0x14010de3e  mov     r15, [rsp+1A8h+var_E8]
0x14010de46  test    r15, r15
0x14010de49  jz      short loc_14010DE56
0x14010de4b  mov     rax, [r15+18h]
0x14010de4f  mov     rsi, [rax+0B8h]
0x14010de56  mov     [rsp+1A8h+var_C8], rsi
0x14010de5e  xor     ecx, ecx
0x14010de60  test    r12, r12
0x14010de63  jz      loc_14010DF9F
0x14010de69  test    r15, r15
0x14010de6c  jnz     loc_14010DF96
0x14010de72  lea     rcx, [r14+0F0h]; plsn1
0x14010de79  mov     rdx, [rsp+1A8h+plsn2]; plsn2
0x14010de81  call    cs:__imp_ClfsLsnLess
0x14010de88  nop     dword ptr [rax+rax+00h]
0x14010de8d  xor     ecx, ecx
0x14010de8f  test    al, al
0x14010de91  jz      loc_14010DF96
0x14010de97  mov     [rsp+1A8h+var_178], ebx
0x14010de9b  lea     rsi, aStatus; "Status"
0x14010dea2  mov     qword ptr [rsp+1A8h+var_180], rsi
0x14010dea7  mov     [rsp+1A8h+var_188], 4ECCh
0x14010deaf  lea     r9, aTxftransC; "txftrans.c"
0x14010deb6  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14010debd  xor     edx, edx; Level
0x14010debf  mov     ecx, 82h; ComponentId
0x14010dec4  call    cs:__imp_DbgPrintEx
0x14010decb  nop     dword ptr [rax+rax+00h]
0x14010ded0  cmp     ebx, 0C0000017h
0x14010ded6  jz      loc_14010DF63
0x14010dedc  lea     eax, [rbx+3FFFFF81h]
0x14010dee2  cmp     eax, 22h ; '"'
0x14010dee5  ja      short loc_14010DEF7
0x14010dee7  mov     rdx, 408000001h
0x14010def1  bt      rdx, rax
0x14010def5  jb      short loc_14010DF63
0x14010def7  cmp     ebx, 0C01A002Bh
0x14010defd  jz      short loc_14010DF57
0x14010deff  cmp     ebx, 0C000026Eh
0x14010df05  jz      short loc_14010DF57
0x14010df07  cmp     ebx, 0C0000185h
0x14010df0d  jz      short loc_14010DF57
0x14010df0f  cmp     ebx, 0C0000148h
0x14010df15  jz      short loc_14010DF57
0x14010df17  lea     eax, [rbx+3FFFFF63h]
0x14010df1d  cmp     eax, 23h ; '#'
0x14010df20  ja      short loc_14010DF32
0x14010df22  mov     rdx, 800000041h
0x14010df2c  bt      rdx, rax
0x14010df30  jb      short loc_14010DF57
0x14010df32  lea     ecx, [rbx+3FFFFFF3h]
0x14010df38  cmp     ecx, 15h
0x14010df3b  ja      short loc_14010DF47
0x14010df3d  mov     eax, 200043h
0x14010df42  bt      eax, ecx
0x14010df45  jb      short loc_14010DF57
0x14010df47  cmp     ebx, 80000016h
0x14010df4d  jz      short loc_14010DF57
0x14010df4f  cmp     ebx, 0C01A002Fh
0x14010df55  jnz     short loc_14010DF6D
0x14010df57  mov     rax, cs:TxfData
0x14010df5e  inc     dword ptr [rax+10h]
0x14010df61  jmp     short loc_14010DF6D
0x14010df63  mov     rax, cs:TxfData
0x14010df6a  inc     dword ptr [rax+0Ch]
0x14010df6d  mov     al, cs:NtfsStatusDebugFlags
0x14010df73  test    al, al
0x14010df75  jz      short loc_14010DF89
0x14010df77  mov     r8d, 314ECDh
0x14010df7d  xor     ecx, ecx
0x14010df7f  mov     edx, 0C0000102h
0x14010df84  call    NtfsStatusTraceAndDebugInternal
0x14010df89  mov     r15, [rsp+1A8h+arg_8]
0x14010df91  jmp     loc_14010EFAF
0x14010df96  test    r12, r12
0x14010df99  jnz     loc_14010E0C5
0x14010df9f  test    r15, r15
0x14010dfa2  jz      loc_14010E0BC
0x14010dfa8  lea     rcx, [rsi+0F0h]; plsn1
0x14010dfaf  mov     rdx, [rsp+1A8h+plsn2]; plsn2
0x14010dfb7  call    cs:__imp_ClfsLsnLess
0x14010dfbe  nop     dword ptr [rax+rax+00h]
0x14010dfc3  xor     ecx, ecx
0x14010dfc5  test    al, al
0x14010dfc7  jz      loc_14010E0BC
0x14010dfcd  mov     [rsp+1A8h+var_178], ebx
0x14010dfd1  lea     rsi, aStatus; "Status"
0x14010dfd8  mov     qword ptr [rsp+1A8h+var_180], rsi
0x14010dfdd  mov     [rsp+1A8h+var_188], 4EDAh
0x14010dfe5  lea     r9, aTxftransC; "txftrans.c"
0x14010dfec  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14010dff3  xor     edx, edx; Level
0x14010dff5  mov     ecx, 82h; ComponentId
0x14010dffa  call    cs:__imp_DbgPrintEx
0x14010e001  nop     dword ptr [rax+rax+00h]
0x14010e006  cmp     ebx, 0C0000017h
0x14010e00c  jz      loc_14010E099
0x14010e012  lea     eax, [rbx+3FFFFF81h]
0x14010e018  cmp     eax, 22h ; '"'
0x14010e01b  ja      short loc_14010E02D
0x14010e01d  mov     rdx, 408000001h
0x14010e027  bt      rdx, rax
0x14010e02b  jb      short loc_14010E099
0x14010e02d  cmp     ebx, 0C01A002Bh
0x14010e033  jz      short loc_14010E08D
0x14010e035  cmp     ebx, 0C000026Eh
0x14010e03b  jz      short loc_14010E08D
0x14010e03d  cmp     ebx, 0C0000185h
0x14010e043  jz      short loc_14010E08D
0x14010e045  cmp     ebx, 0C0000148h
0x14010e04b  jz      short loc_14010E08D
0x14010e04d  lea     eax, [rbx+3FFFFF63h]
0x14010e053  cmp     eax, 23h ; '#'
0x14010e056  ja      short loc_14010E068
0x14010e058  mov     rdx, 800000041h
0x14010e062  bt      rdx, rax
0x14010e066  jb      short loc_14010E08D
0x14010e068  lea     ecx, [rbx+3FFFFFF3h]
0x14010e06e  cmp     ecx, 15h
0x14010e071  ja      short loc_14010E07D
0x14010e073  mov     eax, 200043h
0x14010e078  bt      eax, ecx
0x14010e07b  jb      short loc_14010E08D
0x14010e07d  cmp     ebx, 80000016h
0x14010e083  jz      short loc_14010E08D
0x14010e085  cmp     ebx, 0C01A002Fh
0x14010e08b  jnz     short loc_14010E0A3
0x14010e08d  mov     rax, cs:TxfData
0x14010e094  inc     dword ptr [rax+10h]
0x14010e097  jmp     short loc_14010E0A3
0x14010e099  mov     rax, cs:TxfData
0x14010e0a0  inc     dword ptr [rax+0Ch]
0x14010e0a3  mov     al, cs:NtfsStatusDebugFlags
0x14010e0a9  test    al, al
0x14010e0ab  jz      loc_14010DF89
0x14010e0b1  mov     r8d, 314EDBh
0x14010e0b7  jmp     loc_14010DF7D
0x14010e0bc  test    r12, r12
0x14010e0bf  jz      loc_14010EE96
0x14010e0c5  test    r15, r15
0x14010e0c8  jz      loc_14010EE96
0x14010e0ce  movzx   eax, word ptr [r13+68h]
0x14010e0d3  add     ax, ax
0x14010e0d6  mov     word ptr [rsp+1A8h+var_128+2], ax
0x14010e0de  mov     word ptr [rsp+1A8h+var_128], ax
0x14010e0e6  jz      short loc_14010E0F2
0x14010e0e8  movzx   eax, word ptr [r13+6Ah]
0x14010e0ed  add     rax, r13
0x14010e0f0  jmp     short loc_14010E0F5
0x14010e0f2  mov     rax, rcx
0x14010e0f5  mov     qword ptr [rsp+1A8h+var_128+8], rax
0x14010e0fd  xor     r8d, r8d
0x14010e100  mov     rbx, [rsp+1A8h+var_D0]
0x14010e108  mov     rdx, [rbx+10h]
0x14010e10c  mov     rcx, rdi
0x14010e10f  call    NtfsAcquireSharedVcb
0x14010e114  mov     [rsp+1A8h+var_133], 1
0x14010e119  mov     rax, [rbx+10h]
0x14010e11d  mov     ecx, [rax+4]
0x14010e120  test    cl, 1
0x14010e123  jnz     short loc_14010E15E
0x14010e125  mov     al, cs:NtfsStatusDebugFlags
0x14010e12b  test    al, al
0x14010e12d  jz      short loc_14010E142
0x14010e12f  mov     edx, 0C000026Eh
0x14010e134  mov     r8d, 314F0Ch
0x14010e13a  mov     rcx, rdi
0x14010e13d  call    NtfsStatusTraceAndDebugInternal
0x14010e142  mov     qword ptr [rsp+1A8h+var_188], 314F0Ch
0x14010e14b  xor     r9d, r9d
0x14010e14e  xor     r8d, r8d
0x14010e151  mov     edx, 0C000026Eh
0x14010e156  mov     rcx, rdi
0x14010e159  call    NtfsRaiseStatusInternal
0x14010e15e  cmp     dword ptr [r13+6Ch], 80h
0x14010e166  jnz     short loc_14010E1E5
0x14010e168  xor     ebx, ebx
0x14010e16a  cmp     [rsi+70h], rbx
0x14010e16e  jnz     short loc_14010E19D
0x14010e170  xor     r9d, r9d
0x14010e173  xor     r8d, r8d
0x14010e176  mov     rdx, rsi
0x14010e179  mov     rcx, rdi
0x14010e17c  call    NtfsAcquireExclusiveFcb
0x14010e181  xor     r8d, r8d
0x14010e184  mov     rdx, rsi
0x14010e187  mov     rcx, rdi
0x14010e18a  call    NtfsAddPagingIoToFcb
0x14010e18f  xor     r8d, r8d
0x14010e192  mov     rdx, rsi
0x14010e195  mov     rcx, rdi
0x14010e198  call    NtfsReleaseFcbEx
0x14010e19d  mov     r8b, 1
0x14010e1a0  mov     rdx, rsi
0x14010e1a3  mov     rcx, rdi
0x14010e1a6  call    NtfsAcquirePagingResourceExclusive
0x14010e1ab  test    al, al
0x14010e1ad  jz      short loc_14010E1E5
0x14010e1af  mov     [rsp+1A8h+var_118], ebx
0x14010e1b6  mov     eax, ebx
0x14010e1b8  mov     [rsp+1A8h+var_118], ebx
0x14010e1bf  cmp     eax, 2
0x14010e1c2  jnb     short loc_14010E1E5
0x14010e1c4  mov     edx, eax
0x14010e1c6  mov     rcx, [rdi+rdx*8+30h]
0x14010e1cb  test    rcx, rcx
0x14010e1ce  jz      short loc_14010E1E0
0x14010e1d0  cmp     rcx, rsi
0x14010e1d3  jz      short loc_14010E1E0
0x14010e1d5  inc     eax
0x14010e1d7  mov     [rsp+1A8h+var_118], eax
0x14010e1de  jmp     short loc_14010E1BF
0x14010e1e0  mov     [rdi+rdx*8+30h], rsi
  ... truncated ...
```
