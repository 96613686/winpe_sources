# NtfsPerformDismountOnVcb

- ea: `0x140138c70`
- end: `0x140139e17`
- name: `NtfsPerformDismountOnVcb`
- size: `4519`
- prototype: ``
- caller_count: `7`
- callee_count: `33`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020240`
- `0x1400d4804`
- `0x1400dc204`
- `0x1400e2af8`
- `0x1401c3750`
- `0x1401f6448`
- `0x14029dd80`

## callees

- `0x140004068`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140010be0`
- `0x140012e70`
- `0x14001ca10`
- `0x14001ebf0`
- `0x140021c30`
- `0x140023250`
- `0x14002c130`
- `0x140034770`
- `0x14003fe78`
- `0x14004062c`
- `0x1400592c0`
- `0x14012be50`
- `0x140137cb0`
- `0x140138b68`
- `0x140138bb0`
- `0x140138bf0`
- `0x140138c70`
- `0x140139e20`
- `0x140139e8c`
- `0x14013af60`
- `0x1401406b0`
- `0x14018dc9c`
- `0x1401cb314`
- `0x1401cfc68`
- `0x1401d29ac`
- `0x140244180`
- `0x140246c10`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401392ce`
- `ntoskrnl!KeSetEvent` at `0x1401392ce`
- `ntoskrnl!ObfDereferenceObject` at `0x140139bd8`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6ed2`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c8481`
- `ntoskrnl!ObfDereferenceObject` at `0x140139bd8`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6ed2`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c8481`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140139b9d`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140139b9d`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402a6c85`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402c8259`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402a6c85`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402c8259`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140139dde`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140139dde`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401397a0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401397a0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140139741`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140139741`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140138ee0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140138ee0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a6eb9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c8464`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a6eb9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c8464`
- `ntoskrnl!IoGetActivityIdThread` at `0x140139cf4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402a6aa6`
- `ntoskrnl!IoGetActivityIdThread` at `0x140139cf4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402a6aa6`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a69fe`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a69fe`
- `ntoskrnl!ExReleasePushLockEx` at `0x140138f1f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401390cd`
- `ntoskrnl!ExReleasePushLockEx` at `0x140138f1f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401390cd`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402a6c9c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402c8271`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402a6c9c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402c8271`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401394da`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401394da`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401394a6`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1401394a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401395e3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139bbe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401395e3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139bbe`
- `ntoskrnl!KeInitializeEvent` at `0x140139588`
- `ntoskrnl!KeInitializeEvent` at `0x140139b45`
- `ntoskrnl!KeInitializeEvent` at `0x140139588`
- `ntoskrnl!KeInitializeEvent` at `0x140139b45`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140138e45`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013948c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140138e45`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013948c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140139d4f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c8072`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140139d4f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c8072`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139287`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139287`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139865`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140139d34`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140139d34`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140138e0d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401393f2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140138e0d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401393f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401398ae`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401398ae`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401398d3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401398d3`
- `ntoskrnl!CcFlushCache` at `0x140139b7b`
- `ntoskrnl!CcFlushCache` at `0x140139b7b`

## pseudocode

```c
void __fastcall NtfsPerformDismountOnVcb(_DWORD *Context1, __int64 a2, char a3, char a4, int a5, __int64 a6)
{
  char v6; // r14
  const WCHAR *v9; // r13
  char v10; // r12
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r13
  _QWORD *v15; // rax
  _QWORD *v16; // r12
  __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // r12
  __int64 v20; // r13
  __int64 NextFcbTableEntry; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  char v24; // r14
  _DWORD *v25; // r9
  _QWORD *v26; // r14
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rax
  char v30; // r12
  __int64 v31; // r8
  __int64 v32; // r9
  _QWORD *v33; // rcx
  PVOID *p_Flink; // rax
  __int64 v35; // r9
  __int64 v36; // rdx
  struct _KEVENT *v37; // r14
  struct _KEVENT *v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // r9
  __int64 v42; // rdx
  _QWORD *v43; // rcx
  __int64 *v44; // rax
  __int64 v45; // rcx
  _QWORD *i; // rax
  __int64 **v47; // rdx
  _QWORD *v48; // rcx
  PVOID *v49; // rax
  __int64 v50; // rcx
  signed __int64 v51; // rdx
  _QWORD *Pointer; // r8
  signed __int64 v53; // rcx
  signed __int64 v54; // rax
  signed __int64 v55; // rcx
  signed __int64 v56; // rax
  char *v57; // r12
  char *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rcx
  _QWORD *v63; // r14
  _QWORD *v64; // r13
  __int64 v65; // r8
  _QWORD **v66; // r8
  SECTION_OBJECT_POINTERS *v67; // rcx
  __int64 v68; // rdx
  const char *ProcessImageFileName; // r12
  _OWORD *v70; // rax
  _OWORD *ActivityIdThread; // rax
  struct _FAST_MUTEX *v72; // r14
  char v73; // al
  __int64 v74; // rax
  __int64 v75; // rax
  unsigned __int16 v76; // dx
  const WCHAR *v77; // r14
  const WCHAR *v78; // rax
  int v79; // r13d
  int v80; // ecx
  const WCHAR *v81; // rcx
  WCHAR *v82; // rcx
  const WCHAR *v83; // rcx
  WCHAR *v84; // rcx
  __int64 v85; // rax
  __int64 v86; // r11
  int v87; // r11d
  signed __int32 v88[8]; // [rsp+C8h] [rbp-1E8h] BYREF
  int v89; // [rsp+150h] [rbp-160h]
  char v90; // [rsp+178h] [rbp-138h] BYREF
  char v91; // [rsp+179h] [rbp-137h] BYREF
  char v92; // [rsp+17Ah] [rbp-136h]
  char v93; // [rsp+17Bh] [rbp-135h]
  __int64 v94; // [rsp+180h] [rbp-130h]
  __int64 v95; // [rsp+188h] [rbp-128h]
  _DWORD *v96; // [rsp+190h] [rbp-120h]
  PEPROCESS Process; // [rsp+198h] [rbp-118h] BYREF
  _DWORD *v98; // [rsp+1A0h] [rbp-110h]
  int v99; // [rsp+1A8h] [rbp-108h]
  const WCHAR *v100; // [rsp+1B0h] [rbp-100h]
  const WCHAR *v101; // [rsp+1B8h] [rbp-F8h]
  PVOID Entry; // [rsp+1C0h] [rbp-F0h]
  const WCHAR *v103; // [rsp+1C8h] [rbp-E8h] BYREF
  __int128 v104; // [rsp+1D0h] [rbp-E0h]
  __int64 v105; // [rsp+1E0h] [rbp-D0h]
  int v106; // [rsp+1E8h] [rbp-C8h]
  _QWORD *v107; // [rsp+1F0h] [rbp-C0h]
  PVOID P; // [rsp+1F8h] [rbp-B8h]
  const WCHAR *v109; // [rsp+200h] [rbp-B0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+208h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+218h] [rbp-98h] BYREF
  __int64 v112; // [rsp+228h] [rbp-88h]
  _QWORD Event[7]; // [rsp+230h] [rbp-80h] BYREF

  v6 = a4;
  v96 = Context1;
  v94 = a2;
  v99 = a5;
  *(_QWORD *)&v104 = a6;
  v90 = 0;
  v9 = (const WCHAR *)(a2 + 4);
  v98 = (_DWORD *)(a2 + 4);
  v10 = *(_BYTE *)(a2 + 4) & 1;
  if ( (*(_DWORD *)(a2 + 6436) & 2) != 0 )
  {
    v72 = (struct _FAST_MUTEX *)(a2 + 6256);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 6256));
    if ( *(_DWORD *)(a2 + 6432) )
    {
      v74 = TxfSearchAddTxfFcbCleanupList(*((_QWORD *)Context1 + 18), 0, 5, 0, 1);
      *(_DWORD *)(v74 + 16) |= 0x100000u;
      ExReleaseFastMutexUnsafe(v72);
      NtfsRaiseStatusInternal((_DWORD)Context1, -1073741608, 0, 0, 2295238);
      __debugbreak();
    }
    ExReleaseFastMutexUnsafe(v72);
    v6 = a4;
  }
  IoStatus.Pointer = (PVOID)a2;
  v100 = v9;
  v103 = v9;
  v95 = 0;
  P = 0;
  v101 = v9;
  v92 = v10;
  v11 = *(void **)(a2 + 7992);
  if ( v11 )
  {
    IoUnregisterPlugPlayNotification(v11);
    *(_QWORD *)(a2 + 7992) = 0;
  }
  NtfsFspCloseInternal(0, a2, 1, 0, 0);
  NtfsCommitCurrentTransaction(Context1);
  if ( v6 )
  {
    v68 = *(_QWORD *)(a2 + 128);
    if ( v68 )
    {
      v91 = 0;
      NtfsAcquireExclusiveFcb(Context1, *(_QWORD *)(v68 + 184), v68, 4);
      NtfsDecrementCloseCounts((_DWORD)Context1, *(_QWORD *)(a2 + 128), 0, 0, (__int64)&v91);
      *(_QWORD *)(a2 + 128) = 0;
    }
  }
  *(_BYTE *)(a2 + 5521) = 1;
  v109 = (const WCHAR *)(Context1 + 6);
  if ( !Context1[6] && (*(_DWORD *)v9 & 0x10001000) == 0x10001000 && (*(_DWORD *)v9 & 0x8000000) == 0 )
    NtfsCheckpointVolume(Context1, a2, 1, 1, 0, 5, NtfsLarge0.QuadPart);
  NtOfsCloseIndexSafe(Context1, a2 + 160);
  NtOfsCloseIndexSafe(Context1, a2 + 152);
  NtOfsCloseIndexSafe(Context1, a2 + 144);
  NtOfsCloseIndexSafe(Context1, a2 + 136);
  NtOfsCloseIndexSafe(Context1, a2 + 112);
  NtOfsCloseIndexSafe(Context1, a2 + 120);
  v12 = *(_QWORD *)(a2 + 104);
  if ( v12 )
  {
    NtfsAcquireExclusiveFcb(Context1, *(_QWORD *)(v12 + 184), *(_QWORD *)(a2 + 104), 4);
    NtfsDecrementCloseCounts((_DWORD)Context1, *(_QWORD *)(a2 + 104), 0, 1, 0);
  }
  v13 = *(_QWORD *)(a2 + 80);
  if ( v13 )
  {
    NtfsAcquireExclusiveFcb(Context1, *(_QWORD *)(v13 + 184), *(_QWORD *)(a2 + 80), 4);
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL) + 304LL) = &v90;
    v90 = 0;
    NtfsDecrementCloseCounts((_DWORD)Context1, *(_QWORD *)(a2 + 80), 0, 1, 0);
    if ( !v90 )
    {
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL) + 304LL) = 0;
      NtfsReleaseFcbEx(Context1, *(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL), 0);
    }
    *(_QWORD *)(a2 + 80) = 0;
  }
  v14 = *(_QWORD *)(a2 + 40);
  if ( v14 )
  {
    NtfsAcquireExclusiveFcb(Context1, *(_QWORD *)(v14 + 184), *(_QWORD *)(a2 + 40), 4);
    v112 = v14 + 160;
    Entry = (PVOID)(v14 + 120);
    FsRtlAcquireHeaderMutex(v14 + 120, v14 + 160);
    v38 = (struct _KEVENT *)(v14 + 592);
    v37 = *(struct _KEVENT **)(v14 + 592);
    while ( v37 != v38 )
    {
      P = *(PVOID *)&v37->Header.Lock;
      if ( (unsigned __int8)NtfsClearCancelRoutine(*(_QWORD *)&v37[2].Header.Lock) )
      {
        if ( (HIDWORD(v37[2].Header.WaitListHead.Blink) & 1) != 0 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v14 + 212));
          v33 = *(_QWORD **)&v37->Header.Lock;
          if ( *(struct _KEVENT **)(*(_QWORD *)&v37->Header.Lock + 8LL) != v37
            || (p_Flink = (PVOID *)&v37->Header.WaitListHead.Flink->Flink, *p_Flink != v37) )
          {
LABEL_53:
            __fastfail(3u);
          }
          *p_Flink = v33;
          v33[1] = p_Flink;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 2295412);
          v36 = *(_QWORD *)&v37[2].Header.Lock;
          LOBYTE(v35) = v36 != 0;
          NtfsExtendedCompleteRequestInternal(0, v36, 3221226094LL, v35, 0);
          if ( Context1 && *((_QWORD *)Context1 + 14) == *(_QWORD *)&v37[2].Header.Lock )
            *((_QWORD *)Context1 + 14) = 0;
          *(_QWORD *)&v37[2].Header.Lock = 0;
          ExFreePoolWithTag(v37, 0);
        }
        else
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 2295422);
          LODWORD(v37[2].Header.WaitListHead.Blink) = -1073741202;
          KeSetEvent(v37 + 1, 0, 0);
        }
      }
      v37 = (struct _KEVENT *)P;
      v38 = (struct _KEVENT *)(v14 + 592);
    }
    FsRtlReleaseHeaderMutex(Entry, v112);
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  v15 = (_QWORD *)(a2 + 1960);
  v16 = *(_QWORD **)(a2 + 1960);
  while ( v16 != v15 )
  {
    v63 = v16;
    v64 = v16 - 21;
    v16 = (_QWORD *)*v16;
    if ( (unsigned __int8)NtfsClearCancelRoutine(v64) )
    {
      v39 = *v63;
      if ( *(_QWORD **)(*v63 + 8LL) != v63 )
        goto LABEL_53;
      v40 = (_QWORD *)v63[1];
      if ( (_QWORD *)*v40 != v63 )
        goto LABEL_53;
      *v40 = v39;
      *(_QWORD *)(v39 + 8) = v40;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 2295465);
      LOBYTE(v41) = v64 != 0;
      NtfsExtendedCompleteRequestInternal(0, v64, 3221226094LL, v41, 0);
      if ( Context1 && *((_QWORD **)Context1 + 14) == v64 )
        *((_QWORD *)Context1 + 14) = 0;
    }
    v15 = (_QWORD *)(a2 + 1960);
  }
  ClearFlagInterlocked(v103, 0x80000);
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  NtOfsCloseAttributeSafe(Context1, *(_QWORD *)(a2 + 40));
  v17 = *(_QWORD *)(a2 + 168);
  if ( v17 )
  {
    NtfsAcquireExclusiveFcb(Context1, *(_QWORD *)(v17 + 184), *(_QWORD *)(a2 + 168), 4);
    LOBYTE(v65) = 1;
    NtfsDeleteInternalAttributeStream(Context1, *(_QWORD *)(a2 + 168), v65, 0);
    NtfsDecrementCleanupCounts((_DWORD)Context1, *(_QWORD *)(a2 + 168), 0, 0, 0);
    NtfsDecrementCloseCounts((_DWORD)Context1, *(_QWORD *)(a2 + 168), 0, 1, 0);
    NtfsReleaseFcbEx(Context1, *(_QWORD *)(*(_QWORD *)(a2 + 168) + 184LL), 0);
    *(_QWORD *)(a2 + 168) = 0;
  }
  NtfsCloseCorruptLog(Context1, a2 + 184);
  NtfsCloseCorruptLog(Context1, a2 + 176);
  v18 = *(void **)(a2 + 4696);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    *(_QWORD *)(a2 + 4696) = 0;
  }
  NtfsStopLogFile(Context1, a2);
  if ( (*v98 & 1) != 0 )
  {
    ClearFlagInterlocked(v101, 1);
    _InterlockedOr(v88, 0);
    NtfsUpdateCorruptionHandlingVolumeSetting(Context1, a2, 0);
  }
  v103 = 0;
  v19 = v95;
  do
  {
    v20 = v19;
    v105 = v19;
    ExAcquirePushLockSharedEx(a2 + 656, 0);
    NextFcbTableEntry = NtfsGetNextFcbTableEntry(a2, &v103);
    v19 = NextFcbTableEntry;
    v95 = NextFcbTableEntry;
    if ( NextFcbTableEntry )
      _InterlockedAdd((volatile signed __int32 *)(NextFcbTableEntry + 28), 1u);
    v22 = a2 + 656;
    if ( !v20 )
    {
      ExReleasePushLockEx(v22, 0);
      continue;
    }
    _InterlockedDecrement((volatile signed __int32 *)(v20 + 28));
    ExReleasePushLockEx(v22, 0);
    v26 = 0;
    v107 = 0;
    while ( v20 )
    {
      v27 = (_QWORD *)(v20 + 64);
      if ( v26 )
        v28 = (_QWORD *)v26[21];
      else
        v28 = (_QWORD *)*v27;
      v26 = v28 - 21;
      if ( v28 == v27 )
        v26 = 0;
      v107 = v26;
      if ( !v26 )
        break;
      v29 = v26[35];
      if ( v29 )
      {
        v30 = 1;
        v93 = 1;
        if ( v26 == *(_QWORD **)(a2 + 192) || v26 == *(_QWORD **)(a2 + 88) )
        {
          NtfsAcquireExclusiveFcb(Context1, v20, v26, 1);
          v26[35] = 0;
          *(_QWORD *)(v20 + 304) = &v90;
          v90 = 0;
          NtfsDecrementCloseCounts((_DWORD)Context1, (_DWORD)v26, 0, 0, 0);
          if ( v90 )
          {
            v20 = 0;
            v105 = 0;
            goto LABEL_49;
          }
LABEL_48:
          NtfsReleaseFcbEx(Context1, v20, 0);
          *(_QWORD *)(v20 + 304) = 0;
          goto LABEL_49;
        }
        if ( v29 == *(_QWORD *)(a2 + 216) )
        {
          NtfsDecrementCloseCounts((_DWORD)Context1, *(_QWORD *)(a2 + 64), 0, 1, 0);
          v26[35] = 0;
          goto LABEL_49;
        }
        if ( v26 == *(_QWORD **)(a2 + 40) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(a2 + 1992));
          v66 = (_QWORD **)(a2 + 1976);
          for ( i = *(_QWORD **)(a2 + 1976); i != v66; i = *v66 )
          {
            v42 = *i;
            if ( *(_QWORD **)(*i + 8LL) != i )
              goto LABEL_53;
            v43 = (_QWORD *)i[1];
            if ( (_QWORD *)*v43 != i )
              goto LABEL_53;
            *v43 = v42;
            *(_QWORD *)(v42 + 8) = v43;
            *i = 0;
            v44 = i - 2;
            v45 = *v44;
            if ( *v44 )
            {
              if ( *(__int64 **)(v45 + 8) != v44 )
                goto LABEL_53;
              v47 = (__int64 **)v44[1];
              if ( *v47 != v44 )
                goto LABEL_53;
              *v47 = (__int64 *)v45;
              *(_QWORD *)(v45 + 8) = v47;
            }
          }
          ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1992));
        }
        NtfsAcquireExclusiveFcb(Context1, v20, v26, 1);
        if ( v26 == *(_QWORD **)(a2 + 72) )
        {
          v58 = (char *)(a2 + 1608);
          v57 = *(char **)(a2 + 1608);
          if ( *(_QWORD *)(a2 + 1480) )
          {
            *(_QWORD *)(a2 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
            *(_QWORD *)(a2 + 5376) = 0;
            *(_QWORD *)(a2 + 1480) = 0;
          }
          if ( (!Context1 || (Context1[4] & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0p_EtwWriteTransfer(v58, verfysup_c2003, a2);
            goto LABEL_102;
          }
          while ( v57 != v58 )
          {
            if ( (*((_DWORD *)v57 + 14) & 1) != 0 )
            {
              if ( (!Context1 || (Context1[4] & 0x100000) == 0)
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
              {
                McTemplateU0p_EtwWriteTransfer(v58, verfysup_c2017, a2);
                v58 = (char *)(a2 + 1608);
              }
              break;
            }
            v48 = *(_QWORD **)v57;
            Entry = v48;
            if ( (char *)v48[1] != v57 )
              goto LABEL_53;
            v49 = (PVOID *)*((_QWORD *)v57 + 1);
            if ( *v49 != v57 )
              goto LABEL_53;
            *v49 = v48;
            v48[1] = v49;
            *(_QWORD *)(a2 + 312) -= *((_QWORD *)v57 + 6);
            if ( (*((_DWORD *)v57 + 14) & 0x20) != 0 )
            {
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
              *(_QWORD *)(a2 + 328) -= *((_QWORD *)v57 + 6);
              v50 = *(_QWORD *)(a2 + 328);
              if ( v50 < *(_QWORD *)(a2 + 8312) )
                *(_QWORD *)(a2 + 8312) = v50;
              v51 = *(_QWORD *)(a2 + 304) - (v50 >> 8) - *(_QWORD *)(a2 + 6368) - v50;
              if ( v51 <= 0 )
                v51 = 0;
              Pointer = IoStatus.Pointer;
              do
              {
                v53 = Pointer[1043];
                v54 = v53;
                if ( v51 < v53 )
                  v54 = _InterlockedCompareExchange64(Pointer + 1043, v51, v53);
              }
              while ( v54 != v53 );
              do
              {
                v55 = Pointer[1044];
                v56 = v55;
                if ( v51 > v55 )
                  v56 = _InterlockedCompareExchange64(Pointer + 1044, v51, v55);
              }
              while ( v56 != v55 );
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
            }
            if ( (*((_DWORD *)v57 + 14) & 2) == 0 )
            {
              FsRtlUninitializeBaseMcb((PBASE_MCB)(v57 + 16));
              *((_DWORD *)v57 + 14) |= 2u;
            }
            if ( v57 != (char *)(a2 + 1688) && v57 != (char *)(a2 + 1624) )
              ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v57);
            v57 = (char *)Entry;
LABEL_102:
            v58 = (char *)(a2 + 1608);
          }
          if ( *(char **)v58 != v58 )
          {
            LOBYTE(v32) = 1;
            LOBYTE(v31) = 1;
            NtfsIncrementCloseCounts(v58, v26, v31, v32);
            *((_DWORD *)v26 + 128) |= 0x8000000u;
            NtfsWakeupDeallocatedClustersWaiters(a2, 0);
            NtfsReleaseFcbEx(Context1, v20, 0);
            NtfsMarkUnusedContextPreTrimProcessing(Context1, v59, v60, v61);
            KeInitializeEvent((PRKEVENT)(a2 + 1552), SynchronizationEvent, 0);
            _InterlockedAdd((volatile signed __int32 *)(a2 + 1540), 1u);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 1536), 0) )
            {
              if ( (!Context1 || (Context1[4] & 0x100000) == 0)
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
              {
                McTemplateU0p_EtwWriteTransfer(v62, verfysup_c2118, a2);
              }
              KeWaitForSingleObject((PVOID)(a2 + 1552), Executive, 0, 0, 0);
            }
            if ( (!Context1 || (Context1[4] & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
            {
              McTemplateU0p_EtwWriteTransfer(v62, verfysup_c2135, a2);
            }
            *(_BYTE *)(a2 + 1544) = 1;
            NtfsAcquireExclusiveFcb(Context1, v20, v26, 1);
            *(_BYTE *)(a2 + 1544) = 0;
          }
        }
        *(_QWORD *)(v20 + 304) = &v90;
        v90 = 0;
        if ( !*(_DWORD *)(v26[23] + 8LL) )
          NtfsPurgeFileRecordCache(Context1);
        LOBYTE(v31) = 1;
        v30 = NtfsDeleteInternalAttributeStream(Context1, v26, v31, 0);
        v93 = v30;
        if ( !v90 )
          goto LABEL_48;
        v20 = 0;
        v105 = 0;
        if ( v26 == *(_QWORD **)(a2 + 72) )
          *(_QWORD *)(a2 + 1576) = 0;
LABEL_49:
        if ( v30 )
        {
          if ( v26 == *(_QWORD **)(a2 + 48) )
          {
            *(_QWORD *)(a2 + 48) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 56) )
          {
            *(_QWORD *)(a2 + 56) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 64) )
          {
            *(_QWORD *)(a2 + 64) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 192) )
          {
            *(_QWORD *)(a2 + 192) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 80) )
          {
            *(_QWORD *)(a2 + 80) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 128) )
          {
            *(_QWORD *)(a2 + 128) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 32) )
          {
            *(_QWORD *)(a2 + 32) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 72) )
          {
            *(_QWORD *)(a2 + 72) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 88) )
          {
            *(_QWORD *)(a2 + 88) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 136) )
          {
            *(_QWORD *)(a2 + 136) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 208) )
          {
            *(_QWORD *)(a2 + 208) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 112) )
          {
            *(_QWORD *)(a2 + 112) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 120) )
          {
            *(_QWORD *)(a2 + 120) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 104) )
          {
            *(_QWORD *)(a2 + 104) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 96) )
          {
            *(_QWORD *)(a2 + 96) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 40) )
          {
            *(_QWORD *)(a2 + 40) = 0;
          }
          else if ( v26 == *(_QWORD **)(a2 + 200) )
          {
            *(_QWORD *)(a2 + 200) = 0;
          }
          v26 = 0;
          v107 = 0;
        }
      }
    }
    v19 = v95;
  }
  while ( v19 );
  *(_QWORD *)(a2 + 32) = 0;
  NtfsFspCloseInternal(0, a2, 1, 0, 0);
  v23 = *(unsigned int *)(a2 + 4904);
  if ( *(_DWORD *)(a2 + 260) == (_DWORD)v23 && *(_QWORD *)(a2 + 216) && (*(_DWORD *)(a2 + 572) & 8) == 0 )
  {
    memset(Event, 0, 32);
    IoStatus = 0;
    KeInitializeEvent((PRKEVENT)&Event[1], SynchronizationEvent, 0);
    v24 = a4;
    if ( a4 )
    {
      v67 = *(SECTION_OBJECT_POINTERS **)(*(_QWORD *)(a2 + 216) + 40LL);
      if ( v67 )
        CcFlushCache(v67, 0, 0, &IoStatus);
    }
    CcUninitializeCacheMap(*(PFILE_OBJECT *)(a2 + 216), &NtfsLarge0, (PCACHE_UNINITIALIZE_EVENT)Event);
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    *(_DWORD *)(a2 + 572) |= 8u;
    ObfDereferenceObject(*(PVOID *)(a2 + 216));
  }
  else
  {
    v24 = a4;
  }
  v25 = v98;
  if ( (*v98 & 0x8010000) == 0x10000 )
  {
    v91 = 0;
    v106 = *(_DWORD *)v109;
    v91 = 0;
    NtfsDeviceIoControl(Context1, *(_QWORD *)(a2 + 224), 477188, 0, &v91, 1, 0, 0, 0);
    ClearFlagInterlocked(v101, 0x10000);
  }
  if ( a3 && (*v25 & 0x800) == 0 )
    NtfsPerformDismountOnVcbNonpaged(v23, a2, v104);
  if ( dword_140092174 )
  {
    if ( (unsigned __int8)(byte_140092178 - 1) <= 2u
      || (qword_140092160 & 0x8000000) == 0
      || (v73 = 1, (qword_140092168 & 0x8000000) != qword_140092168) )
    {
      v73 = 0;
    }
    if ( v73 && (!Context1 || (Context1[4] & 0x100000LL) == 0) )
    {
      v104 = 0;
      v75 = *(_QWORD *)(a2 + 248);
      v76 = 0;
      if ( v75 )
      {
        v76 = *(_WORD *)(v75 + 6);
        if ( v76 > 0x40u || (v76 & 1) != 0 )
          v76 = 0;
        if ( v76 )
          *((_QWORD *)&v104 + 1) = v75 + 32;
      }
      if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000000) != 0 )
      {
        McTemplateU0ppww_EtwWriteTransfer(
          *(unsigned __int16 *)(a2 + 7856) >> 1,
          (unsigned int)verfysup_c2474,
          (_DWORD)Context1,
          a2,
          v76 >> 1,
          *((__int64 *)&v104 + 1),
          *(_WORD *)(a2 + 7856) >> 1,
          *(_QWORD *)(a2 + 7864));
      }
    }
  }
  if ( v92 && !v24 )
  {
    memset(&Event[4], 0, 24);
    UnicodeString = 0;
    v91 = 0;
    Process = 0;
    ProcessImageFileName = byte_140064C38;
    if ( Context1 && (v70 = (_OWORD *)*((_QWORD *)Context1 + 15)) != 0 )
    {
      *(_OWORD *)&Event[5] = *v70;
      Event[4] = &Event[5];
    }
    else
    {
      ActivityIdThread = (_OWORD *)IoGetActivityIdThread();
      if ( ActivityIdThread )
      {
        *(_OWORD *)&Event[5] = *ActivityIdThread;
        Event[4] = &Event[5];
      }
      else
      {
        Event[4] = 0;
      }
    }
    NtfsFillVcbVolumeGuid(Context1);
    NtfsRepairGetVolumeId((_DWORD)Context1, a2, 0, (unsigned int)&UnicodeString, (__int64)&v91);
    if ( PsLookupProcessByProcessId(*((HANDLE *)Context1 + 64), &Process) >= 0 )
      ProcessImageFileName = (const char *)PsGetProcessImageFileName(Process);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v77 = &word_140064400;
      v78 = &word_140064400;
      if ( *(_QWORD *)(a2 + 6736) )
        v78 = *(const WCHAR **)(a2 + 6736);
      *(_QWORD *)&v104 = v78;
      v79 = (*(_DWORD *)(a2 + 28) >> 2) & 1;
      v80 = *(_DWORD *)(a2 + 6660);
      if ( (unsigned int)(v80 - 1) > 0x13 )
        v80 = 0;
      LODWORD(v94) = v80;
      v81 = &word_140064400;
      if ( *(_QWORD *)(a2 + 6720) )
        v81 = *(const WCHAR **)(a2 + 6720);
      v109 = v81;
      v82 = (WCHAR *)&word_140064400;
      if ( *(_QWORD *)(a2 + 6704) )
        v82 = *(WCHAR **)(a2 + 6704);
      IoStatus.Pointer = v82;
      v83 = &word_140064400;
      if ( *(_QWORD *)(a2 + 6688) )
        v83 = *(const WCHAR **)(a2 + 6688);
      v103 = v83;
      v84 = (WCHAR *)&word_140064400;
      if ( *(_QWORD *)(a2 + 6672) )
        v84 = *(WCHAR **)(a2 + 6672);
      Entry = v84;
      if ( *(_QWORD *)(a2 + 7864) )
        v77 = *(const WCHAR **)(a2 + 7864);
      if ( (*v98 & 0xC00) != 0x800 && (v85 = *(_QWORD *)(a2 + 248)) != 0 && (v86 = *(_QWORD *)(v85 + 16)) != 0 )
        v87 = (*(_DWORD *)(v86 + 48) >> 8) & 1;
      else
        LOBYTE(v87) = 0;
      McTemplateK0jmztzzzzzqjqtzpqss_EtwWriteTransfer(
        Context1[128],
        (unsigned int)NTFS_ETW_VOLUME_DISMOUNT_COMPLETE,
        Event[4],
        a2 + 7824,
        a2 + 8528,
        (__int64)UnicodeString.Buffer,
        v87,
        (__int64)v77,
        (__int64)Entry,
        (__int64)v103,
        (__int64)IoStatus.Pointer,
        (__int64)v109,
        v94,
        a2 + 7808,
        *(_DWORD *)(a2 + 6792),
        v79,
        v104,
        v89,
        Context1[128],
        (__int64)ProcessImageFileName,
        (__int64)NtfsDismountReasonMapping[v99]);
    }
    if ( v91 )
      RtlFreeUnicodeString(&UnicodeString);
    if ( Process )
      ObfDereferenceObject(Process);
  }
}

```

## disassembly

```asm
0x140138c70  mov     [rsp+arg_18], r9b
0x140138c75  mov     [rsp+arg_10], r8b
0x140138c7a  push    rbx
0x140138c7b  push    rsi
0x140138c7c  push    rdi
0x140138c7d  push    r12
0x140138c7f  push    r13
0x140138c81  push    r14
0x140138c83  push    r15
0x140138c85  sub     rsp, 1B0h
0x140138c8c  mov     rax, cs:__security_cookie
0x140138c93  xor     rax, rsp
0x140138c96  mov     [rsp+1E8h+var_48], rax
0x140138c9e  mov     r14b, r9b
0x140138ca1  mov     rdi, rdx
0x140138ca4  mov     rsi, rcx
0x140138ca7  mov     [rsp+1E8h+var_120], rcx
0x140138caf  mov     [rsp+1E8h+var_130], rdx
0x140138cb7  mov     eax, [rsp+1E8h+arg_20]
0x140138cbe  mov     [rsp+1E8h+var_108], eax
0x140138cc5  mov     rax, [rsp+1E8h+arg_28]
0x140138ccd  mov     qword ptr [rsp+1E8h+var_E0], rax
0x140138cd5  xor     ebx, ebx
0x140138cd7  mov     [rsp+1E8h+var_138], bl
0x140138cde  lea     r13, [rdx+4]
0x140138ce2  mov     [rsp+1E8h+var_110], r13
0x140138cea  mov     r12b, [r13+0]
0x140138cee  lea     r15d, [rbx+1]
0x140138cf2  and     r12b, r15b
0x140138cf5  mov     eax, [rdx+1924h]
0x140138cfb  test    al, 2
0x140138cfd  jnz     loc_140139D2A
0x140138d03  mov     qword ptr [rsp+1E8h+IoStatus], rdi
0x140138d0b  mov     [rsp+1E8h+var_100], r13
0x140138d13  mov     [rsp+1E8h+var_E8], r13
0x140138d1b  mov     [rsp+1E8h+var_128], rbx
0x140138d23  mov     [rsp+1E8h+P], rbx
0x140138d2b  mov     [rsp+1E8h+var_F8], r13
0x140138d33  mov     [rsp+1E8h+var_136], r12b
0x140138d3b  mov     rcx, [rdi+1F38h]; NotificationEntry
0x140138d42  test    rcx, rcx
0x140138d45  jnz     loc_140139DDE
0x140138d4b  mov     byte ptr [rsp+1E8h+Timeout], bl
0x140138d4f  xor     r9d, r9d
0x140138d52  mov     r8b, r15b
0x140138d55  mov     rdx, rdi
0x140138d58  xor     ecx, ecx
0x140138d5a  call    NtfsFspCloseInternal
0x140138d5f  mov     rcx, rsi
0x140138d62  call    NtfsCommitCurrentTransaction
0x140138d67  test    r14b, r14b
0x140138d6a  jnz     loc_140139C27
0x140138d70  mov     [rdi+1591h], r15b
0x140138d77  lea     rax, [rsi+18h]
0x140138d7b  mov     [rsp+1E8h+var_B0], rax
0x140138d83  cmp     [rax], ebx
0x140138d85  jz      loc_140139C8C
0x140138d8b  lea     rdx, [rdi+0A0h]
0x140138d92  mov     rcx, rsi
0x140138d95  call    NtOfsCloseIndexSafe
0x140138d9a  lea     rdx, [rdi+98h]
0x140138da1  mov     rcx, rsi
0x140138da4  call    NtOfsCloseIndexSafe
0x140138da9  lea     rdx, [rdi+90h]
0x140138db0  mov     rcx, rsi
0x140138db3  call    NtOfsCloseIndexSafe
0x140138db8  lea     rdx, [rdi+88h]
0x140138dbf  mov     rcx, rsi
0x140138dc2  call    NtOfsCloseIndexSafe
0x140138dc7  lea     rdx, [rdi+70h]
0x140138dcb  mov     rcx, rsi
0x140138dce  call    NtOfsCloseIndexSafe
0x140138dd3  lea     rdx, [rdi+78h]
0x140138dd7  mov     rcx, rsi
0x140138dda  call    NtOfsCloseIndexSafe
0x140138ddf  mov     rdx, [rdi+68h]
0x140138de3  test    rdx, rdx
0x140138de6  jnz     loc_14013963B
0x140138dec  mov     rdx, [rdi+50h]
0x140138df0  test    rdx, rdx
0x140138df3  jnz     loc_140139678
0x140138df9  mov     r13, [rdi+28h]
0x140138dfd  test    r13, r13
0x140138e00  jnz     loc_14013970B
0x140138e06  lea     rcx, [rdi+240h]; Mutex
0x140138e0d  call    cs:__imp_KeAcquireGuardedMutex
0x140138e14  nop     dword ptr [rax+rax+00h]
0x140138e19  lea     rax, [rdi+7A8h]
0x140138e20  mov     r12, [rax]
0x140138e23  cmp     r12, rax
0x140138e26  jnz     loc_1401397B1
0x140138e2c  mov     edx, 80000h
0x140138e31  mov     rcx, [rsp+1E8h+var_E8]
0x140138e39  call    ClearFlagInterlocked
0x140138e3e  lea     rcx, [rdi+240h]; Mutex
0x140138e45  call    cs:__imp_KeReleaseGuardedMutex
0x140138e4c  nop     dword ptr [rax+rax+00h]
0x140138e51  mov     rdx, [rdi+28h]
0x140138e55  mov     rcx, rsi
0x140138e58  call    NtOfsCloseAttributeSafe
0x140138e5d  mov     rdx, [rdi+0A8h]
0x140138e64  test    rdx, rdx
0x140138e67  jnz     loc_1401397D5
0x140138e6d  lea     rdx, [rdi+0B8h]
0x140138e74  mov     rcx, rsi
0x140138e77  call    NtfsCloseCorruptLog
0x140138e7c  lea     rdx, [rdi+0B0h]
0x140138e83  mov     rcx, rsi
0x140138e86  call    NtfsCloseCorruptLog
0x140138e8b  mov     rcx, [rdi+1258h]; P
0x140138e92  test    rcx, rcx
0x140138e95  jnz     loc_140139863
0x140138e9b  mov     rdx, rdi
0x140138e9e  mov     rcx, rsi
0x140138ea1  call    NtfsStopLogFile
0x140138ea6  mov     rcx, [rsp+1E8h+var_110]
0x140138eae  mov     eax, [rcx]
0x140138eb0  test    r15b, al
0x140138eb3  jnz     loc_14013987D
0x140138eb9  mov     [rsp+1E8h+var_E8], rbx
0x140138ec1  mov     r12, [rsp+1E8h+var_128]
0x140138ec9  mov     r13, r12
0x140138ecc  mov     [rsp+1E8h+var_D0], r12
0x140138ed4  lea     r14, [rdi+290h]
0x140138edb  xor     edx, edx
0x140138edd  mov     rcx, r14
0x140138ee0  call    cs:__imp_ExAcquirePushLockSharedEx
0x140138ee7  nop     dword ptr [rax+rax+00h]
0x140138eec  lea     rdx, [rsp+1E8h+var_E8]
0x140138ef4  mov     rcx, rdi
0x140138ef7  call    NtfsGetNextFcbTableEntry
0x140138efc  mov     r12, rax
0x140138eff  mov     [rsp+1E8h+var_128], rax
0x140138f07  test    rax, rax
0x140138f0a  jz      short loc_140138F11
0x140138f0c  lock add [rax+1Ch], r15d
0x140138f11  xor     edx, edx
0x140138f13  mov     rcx, r14
0x140138f16  test    r13, r13
0x140138f19  jnz     loc_1401390C8
0x140138f1f  call    cs:__imp_ExReleasePushLockEx
0x140138f26  nop     dword ptr [rax+rax+00h]
0x140138f2b  test    r12, r12
0x140138f2e  jnz     short loc_140138EC9
0x140138f30  mov     [rdi+20h], rbx
0x140138f34  mov     byte ptr [rsp+1E8h+Timeout], bl
0x140138f38  xor     r9d, r9d
0x140138f3b  mov     r8b, r15b
0x140138f3e  mov     rdx, rdi
0x140138f41  xor     ecx, ecx
0x140138f43  call    NtfsFspCloseInternal
0x140138f48  mov     ecx, [rdi+1328h]
0x140138f4e  cmp     [rdi+104h], ecx
0x140138f54  jnz     short loc_140138F63
0x140138f56  cmp     [rdi+0D8h], rbx
0x140138f5d  jnz     loc_140139B0E
0x140138f63  mov     r14b, [rsp+1E8h+arg_18]
0x140138f6b  mov     r9, [rsp+1E8h+var_110]
0x140138f73  mov     eax, [r9]
0x140138f76  and     eax, 8010000h
0x140138f7b  cmp     eax, 10000h
0x140138f80  jnz     loc_140139099
0x140138f86  mov     [rsp+1E8h+var_137], bl
0x140138f8d  mov     rax, [rsp+1E8h+var_B0]
0x140138f95  mov     eax, [rax]
0x140138f97  mov     [rsp+1E8h+var_C8], eax
0x140138f9e  mov     [rsp+1E8h+var_137], bl
0x140138fa5  mov     [rsp+1E8h+var_1A8], rbx
0x140138faa  mov     dword ptr [rsp+1E8h+var_1B0], ebx
0x140138fae  mov     [rsp+1E8h+var_1B8], rbx
0x140138fb3  mov     [rsp+1E8h+var_1C0], r15d
0x140138fb8  lea     rax, [rsp+1E8h+var_137]
0x140138fc0  mov     [rsp+1E8h+Timeout], rax
0x140138fc5  xor     r9d, r9d
0x140138fc8  mov     r8d, 74804h
0x140138fce  mov     rdx, [rdi+0E0h]
0x140138fd5  mov     rcx, rsi
0x140138fd8  call    NtfsDeviceIoControl
0x140138fdd  mov     r9, [rsp+1E8h+var_110]
0x140138fe5  jmp     loc_140139087
0x140138fea  mov     edx, eax
0x140138fec  mov     cl, cs:NtfsStatusDebugFlags
0x140138ff2  test    cl, cl
0x140138ff4  jz      short loc_140139045
0x140138ff6  test    eax, eax
0x140138ff8  jz      short loc_140139045
0x140138ffa  cmp     eax, 126h
0x140138fff  jz      short loc_140139045
0x140139001  lea     ecx, [rax-12Ah]
0x140139007  cmp     ecx, 1
0x14013900a  jbe     short loc_140139045
0x14013900c  cmp     eax, 0FFFFFFEDh
0x14013900f  jnb     short loc_140139045
0x140139011  cmp     eax, 0C00000D8h
0x140139016  jz      short loc_140139045
0x140139018  cmp     eax, 0C0000016h
0x14013901d  jz      short loc_140139045
0x14013901f  cmp     eax, 0C0000011h
0x140139024  jz      short loc_140139045
0x140139026  add     eax, 7FFFFFFBh
0x14013902b  cmp     eax, 1
0x14013902e  jbe     short loc_140139045
0x140139030  cmp     edx, 103h
0x140139036  jz      short loc_140139045
0x140139038  xor     ecx, ecx
0x14013903a  mov     r8d, 230960h
0x140139040  call    NtfsStatusTraceAndDebugInternal
0x140139045  mov     rsi, [rsp+1E8h+var_120]
0x14013904d  mov     eax, [rsi+4]
0x140139050  btr     eax, 8
0x140139054  mov     [rsi+4], eax
0x140139057  mov     eax, [rsp+1E8h+var_C8]
0x14013905e  mov     [rsi+18h], eax
0x140139061  xor     ebx, ebx
0x140139063  lea     r15d, [rbx+1]
0x140139067  mov     rdi, [rsp+1E8h+var_130]
0x14013906f  mov     r9, [rsp+1E8h+var_100]
0x140139077  mov     [rsp+1E8h+var_110], r9
0x14013907f  mov     r14b, [rsp+1E8h+arg_18]
0x140139087  mov     edx, 10000h
0x14013908c  mov     rcx, [rsp+1E8h+var_F8]
0x140139094  call    ClearFlagInterlocked
0x140139099  cmp     [rsp+1E8h+arg_10], bl
0x1401390a0  jz      loc_140139BE9
0x1401390a6  test    dword ptr [r9], 800h
0x1401390ad  jnz     loc_140139BE9
0x1401390b3  mov     r8, qword ptr [rsp+1E8h+var_E0]
0x1401390bb  mov     rdx, rdi
0x1401390be  call    NtfsPerformDismountOnVcbNonpaged
0x1401390c3  jmp     loc_140139BE9
0x1401390c8  lock dec dword ptr [r13+1Ch]
0x1401390cd  call    cs:__imp_ExReleasePushLockEx
0x1401390d4  nop     dword ptr [rax+rax+00h]
0x1401390d9  mov     r14, rbx
0x1401390dc  mov     [rsp+1E8h+var_C0], rbx
0x1401390e4  test    r13, r13
0x1401390e7  jz      loc_1401391F9
0x1401390ed  lea     rax, [r13+40h]
0x1401390f1  test    r14, r14
0x1401390f4  jz      loc_1401391F1
0x1401390fa  mov     rcx, [r14+0A8h]
0x140139101  lea     r14, [rcx-0A8h]
0x140139108  cmp     rcx, rax
0x14013910b  cmovz   r14, rbx
0x14013910f  mov     [rsp+1E8h+var_C0], r14
0x140139117  test    r14, r14
0x14013911a  jz      loc_1401391F9
0x140139120  mov     rax, [r14+118h]
0x140139127  test    rax, rax
0x14013912a  jz      loc_1401391EC
0x140139130  mov     r12b, r15b
0x140139133  mov     [rsp+1E8h+var_135], r15b
0x14013913b  cmp     r14, [rdi+0C0h]
0x140139142  jz      loc_140139999
0x140139148  cmp     r14, [rdi+58h]
0x14013914c  jz      loc_140139999
0x140139152  cmp     rax, [rdi+0D8h]
0x140139159  jz      loc_14013996D
0x14013915f  cmp     r14, [rdi+28h]
0x140139163  jz      loc_1401398A4
0x140139169  mov     r9d, r15d
0x14013916c  mov     r8, r14
0x14013916f  mov     rdx, r13
0x140139172  mov     rcx, rsi
0x140139175  call    NtfsAcquireExclusiveFcb
0x14013917a  cmp     r14, [rdi+48h]
0x14013917e  jz      loc_1401398E4
0x140139184  lea     rax, [rsp+1E8h+var_138]
0x14013918c  mov     [r13+130h], rax
0x140139193  mov     [rsp+1E8h+var_138], bl
0x14013919a  mov     rax, [r14+0B8h]
0x1401391a1  cmp     [rax+8], ebx
0x1401391a4  jz      short loc_140139206
0x1401391a6  xor     r9d, r9d
0x1401391a9  mov     r8b, r15b
0x1401391ac  mov     rdx, r14
0x1401391af  mov     rcx, rsi
0x1401391b2  call    NtfsDeleteInternalAttributeStream
0x1401391b7  mov     r12b, al
0x1401391ba  mov     [rsp+1E8h+var_135], al
0x1401391c1  cmp     [rsp+1E8h+var_138], bl
0x1401391c8  jnz     loc_14013994C
0x1401391ce  xor     r8d, r8d
0x1401391d1  mov     rdx, r13
0x1401391d4  mov     rcx, rsi
0x1401391d7  call    NtfsReleaseFcbEx
0x1401391dc  mov     [r13+130h], rbx
0x1401391e3  test    r12b, r12b
0x1401391e6  jnz     loc_140139A02
0x1401391ec  jmp     loc_1401390E4
0x1401391f1  mov     rcx, [rax]
0x1401391f4  jmp     loc_140139101
0x1401391f9  mov     r12, [rsp+1E8h+var_128]
0x140139201  jmp     loc_140138F2B
0x140139206  mov     rcx, rsi
0x140139209  call    NtfsPurgeFileRecordCache
0x14013920e  jmp     short loc_1401391A6
0x140139210  mov     ecx, 3
0x140139215  int     29h; Win8: RtlFailFast(ecx)
0x140139217  lock dec dword ptr [r13+0D4h]
  ... truncated ...
```
