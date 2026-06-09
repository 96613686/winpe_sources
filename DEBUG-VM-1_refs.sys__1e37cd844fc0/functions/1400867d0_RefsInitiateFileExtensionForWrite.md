# RefsInitiateFileExtensionForWrite

- ea: `0x1400867d0`
- end: `0x140087299`
- name: `RefsInitiateFileExtensionForWrite`
- size: `2761`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400a2c60`
- `0x140328fd0`

## callees

- `0x140011c60`
- `0x14001b59c`
- `0x1400298a0`
- `0x140036670`
- `0x140038480`
- `0x140076060`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400867d0`
- `0x140089680`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x14010b6e0`
- `0x14010b848`
- `0x1401f3fc0`
- `0x140302e10`
- `0x140323140`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400870c6`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400870c6`
- `ntoskrnl!KeSetEvent` at `0x140086bbb`
- `ntoskrnl!KeSetEvent` at `0x140086bbb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400868c5`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1400868c5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087018`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140087018`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400869d8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140086b70`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140086f55`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400869d8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140086b70`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140086f55`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400869e7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140086b7f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140086f64`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400869e7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140086b7f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140086f64`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086a2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086bcb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086fa4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086a2e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086bcb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140086fa4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086a3a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086bd7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086fb0`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086a3a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086bd7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140086fb0`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086c42`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086dc4`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086e1e`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086c42`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086dc4`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140086e1e`
- `ntoskrnl!ExReleaseFastResource` at `0x140086c65`
- `ntoskrnl!ExReleaseFastResource` at `0x140086cb8`
- `ntoskrnl!ExReleaseFastResource` at `0x14008725e`
- `ntoskrnl!ExReleaseFastResource` at `0x140086c65`
- `ntoskrnl!ExReleaseFastResource` at `0x140086cb8`
- `ntoskrnl!ExReleaseFastResource` at `0x14008725e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008727a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008727a`
- `ntoskrnl!CcSetFileSizesEx` at `0x140200e56`
- `ntoskrnl!CcSetFileSizesEx` at `0x140200e56`

## string_xrefs

- `0x140200cac`: `write.c`
- `0x140200e0b`: `write.c`

## pseudocode

```c
void __fastcall RefsInitiateFileExtensionForWrite(
        struct _IRP_CONTEXT **a1,
        __int64 a2,
        __int64 a3,
        LARGE_INTEGER *a4,
        _BYTE *a5)
{
  LARGE_INTEGER **v5; // rdi
  __int64 v7; // rax
  struct _IRP_CONTEXT *v8; // r9
  LARGE_INTEGER v10; // rcx
  LARGE_INTEGER v12; // r12
  LARGE_INTEGER v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  LARGE_INTEGER v17; // r8
  char v18; // cl
  LARGE_INTEGER v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // r15
  __int64 v22; // r15
  __int64 v23; // rbx
  unsigned __int8 v24; // r15
  __int64 v25; // rcx
  unsigned int v26; // r8d
  struct _IRP_CONTEXT *v27; // r15
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  _QWORD *v30; // rax
  LARGE_INTEGER v31; // rax
  LARGE_INTEGER v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  LARGE_INTEGER *i; // rbx
  struct _FAST_MUTEX *v36; // rdi
  LARGE_INTEGER **QuadPart; // rax
  LARGE_INTEGER *v38; // rsi
  int v39; // eax
  _QWORD *v40; // rbx
  _QWORD *v41; // r15
  __int16 v42; // r12
  _QWORD *v43; // rsi
  _QWORD *v44; // rcx
  struct _IRP_CONTEXT *v45; // rax
  struct _IRP_CONTEXT *v46; // r8
  _QWORD **v47; // r12
  _QWORD *v48; // rcx
  _QWORD *v49; // rax
  _QWORD *v50; // r13
  _QWORD *v51; // r13
  struct _IRP_CONTEXT **v52; // rdi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v54; // r8
  unsigned int j; // edx
  __int64 v56; // rcx
  struct _IRP_CONTEXT **v57; // rax
  struct _IRP_CONTEXT *v58; // rcx
  int v59; // eax
  _BYTE *v60; // r12
  struct _FAST_MUTEX *v61; // rbx
  _QWORD *v62; // rcx
  _QWORD *v63; // rcx
  __int64 v64; // rcx
  struct _IRP_CONTEXT *k; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v67; // rcx
  bool v68; // zf
  int v69; // ecx
  _QWORD *v70; // rbx
  _QWORD *v71; // rcx
  _QWORD *v72; // rax
  _QWORD *NPagedPerProcessorLookaside; // rcx
  _QWORD *v74; // rax
  _QWORD *v75; // rdx
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rcx
  LARGE_INTEGER v81; // rdx
  _QWORD *v82; // rax
  __int64 v83; // rcx
  struct _FAST_MUTEX *v84; // rdi
  __int64 v85; // rdx
  _QWORD *v86; // rcx
  unsigned int v87; // eax
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  int v91; // eax
  int v92; // ebx
  int v93; // ecx
  unsigned int v94; // ebx
  _QWORD *v95; // rcx
  __int64 v96; // r15
  __int64 v97; // rdx
  unsigned int v98; // r8d
  NTSTATUS v99; // ebx
  unsigned int v100; // r8d
  _QWORD *v102; // [rsp+48h] [rbp-49h] BYREF
  NTSTATUS Status[2]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v104; // [rsp+58h] [rbp-39h]
  _BYTE *v105; // [rsp+60h] [rbp-31h]
  _QWORD v106[2]; // [rsp+70h] [rbp-21h] BYREF
  struct _CC_FILE_SIZES FileSizes; // [rsp+80h] [rbp-11h] BYREF

  v5 = (LARGE_INTEGER **)(a2 + 464);
  v105 = a5;
  v7 = *(_QWORD *)(a2 + 464);
  v8 = (struct _IRP_CONTEXT *)a1;
  v10 = *(LARGE_INTEGER *)(a2 + 32);
  v106[0] = v10.QuadPart;
  v12 = v10;
  if ( v7 != a2 + 464 )
  {
    v13 = *(LARGE_INTEGER *)(v7 - 16);
    if ( v13.QuadPart > v10.QuadPart )
      v12 = v13;
  }
  v14 = *((_QWORD *)v8 + 8);
  v15 = *(_DWORD *)(a2 + 152);
  v102 = (_QWORD *)v14;
  if ( (v15 & 8) == 0 || (v15 & 0x40) != 0 )
  {
    v16 = *(unsigned int *)(v14 + 544);
    v17 = a4[1];
    v18 = *(_BYTE *)(v14 + 552);
    v19 = *(LARGE_INTEGER *)(a2 + 424);
    v20 = (v12.QuadPart + v16) >> v18;
    v21 = v17.QuadPart + v16;
    if ( v17.QuadPart >= v19.QuadPart )
      v21 = v19.QuadPart + v16;
    v22 = v21 >> v18;
    if ( v20 < v22 )
    {
      *(_OWORD *)&FileSizes.AllocationSize.LowPart = 0;
      v96 = v22 - v20;
      RefsBindMinstoreTransaction(v8);
      RefsAcquireRangeLock(
        (struct _IRP_CONTEXT *)a1,
        *(struct _SCB_NONPAGED **)(a2 + 248),
        v20 << *((_BYTE *)v102 + 552),
        v96 << *((_BYTE *)v102 + 552),
        1,
        (struct _RANGE_LOCK_STATE *)&FileSizes);
      v97 = *(_QWORD *)(a2 + 432);
      *(_QWORD *)Status = v20;
      v104 = v96;
      Status[0] = MsSetRangeValidState(a1[3], v97, Status, 0);
      RefsReleaseRangeLock(
        *(struct _SCB_NONPAGED **)(a2 + 248),
        v20 << *((_BYTE *)v102 + 552),
        v96 << *((_BYTE *)v102 + 552),
        1,
        (struct _RANGE_LOCK_STATE *)&FileSizes);
      v99 = Status[0];
      if ( Status[0] < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            &WPP_333749fe71273bc3659f43e52285135c_Traceguids,
            (unsigned int)Status[0]);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v99, (struct _IRP_CONTEXT *)a1, "write.c", 0x2E9u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v99, v98);
        __debugbreak();
      }
      RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
      v8 = (struct _IRP_CONTEXT *)a1;
    }
  }
  v23 = *(_QWORD *)(a2 + 136);
  v24 = *((_BYTE *)v8 + 8) & 1;
  Status[0] = 0;
  while ( 1 )
  {
    v25 = *(_WORD *)v23 == 2050 ? v23 : *(_QWORD *)(v23 + 136);
    if ( (unsigned __int8)ExAcquireFastResourceExclusive(*(_QWORD *)(v25 + 88) + 64LL, 0, v24) )
      break;
    if ( ++Status[0] )
    {
      v27 = (struct _IRP_CONTEXT *)a1;
      v94 = -1073741608;
      goto LABEL_177;
    }
    KeDelayExecutionThread(0, 0, &RefsShortDelay);
  }
  if ( (*(_BYTE *)(v23 + 8) & 1) != 0 || (*(_DWORD *)(a2 + 300) & 0x40) != 0 )
  {
    v27 = (struct _IRP_CONTEXT *)a1;
    if ( ((*((_BYTE *)a1 + 40) - 2) & 0xEF) != 0 )
    {
      RefsReleaseResource(a1, v23);
      v94 = -1073741533;
LABEL_177:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_31376ab3b8073048edfb14e725e449b5_Traceguids, v94);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v94, v27, "ResrcSup.c", 0x4C0u);
      RefsRaiseStatusInternal(v27, v94, v26);
      __debugbreak();
    }
  }
  else
  {
    v27 = (struct _IRP_CONTEXT *)a1;
  }
  v28 = (_QWORD *)(v23 + 64);
  if ( !*(_QWORD *)(v23 + 64) )
  {
    v29 = *((_QWORD *)v27 + 14);
    v30 = (_QWORD *)((char *)v27 + 112);
    if ( *(struct _IRP_CONTEXT **)(v29 + 8) != (struct _IRP_CONTEXT *)((char *)v27 + 112) )
      goto LABEL_31;
    *v28 = v29;
    *(_QWORD *)(v23 + 72) = v30;
    *(_QWORD *)(v29 + 8) = v28;
    *v30 = v28;
  }
  ++*(_WORD *)(v23 + 28);
  if ( (*(_DWORD *)(a2 + 152) & 0x200) != 0 )
  {
    v70 = (_QWORD *)((char *)v27 + 640);
    v71 = 0;
    v72 = (_QWORD *)*((_QWORD *)v27 + 80);
    if ( v72 != (_QWORD *)((char *)v27 + 640) )
    {
      while ( v72 != v70 )
      {
        if ( *((_WORD *)v72 - 4) == 2087 )
        {
          v71 = v72 - 1;
          break;
        }
        v72 = (_QWORD *)*v72;
      }
    }
    if ( !*(_QWORD *)(a2 + 280) )
    {
      if ( v71 )
        NPagedPerProcessorLookaside = RefsAllocateNPagedPerProcessorLookaside(RefsScbSnapshotLookasideList);
      else
        NPagedPerProcessorLookaside = (_QWORD *)((char *)v27 + 728);
      *(_DWORD *)NPagedPerProcessorLookaside = 4720679;
      v74 = NPagedPerProcessorLookaside + 1;
      v75 = (_QWORD *)*((_QWORD *)v27 + 81);
      if ( (_QWORD *)*v75 != v70 )
        goto LABEL_31;
      *v74 = v70;
      NPagedPerProcessorLookaside[2] = v75;
      *v75 = v74;
      *((_QWORD *)v27 + 81) = v74;
      if ( (*(_DWORD *)(a2 + 152) & 0x200) != 0 )
      {
        NPagedPerProcessorLookaside[3] = *(_QWORD *)(a2 + 24);
        NPagedPerProcessorLookaside[4] = *(_QWORD *)(a2 + 32);
        v76 = *(_QWORD *)(a2 + 40);
      }
      else
      {
        NPagedPerProcessorLookaside[3] = 0;
        v76 = 0;
        NPagedPerProcessorLookaside[4] = 0;
      }
      NPagedPerProcessorLookaside[5] = v76;
      NPagedPerProcessorLookaside[6] = a2;
      *((_DWORD *)NPagedPerProcessorLookaside + 15) = 0;
      *((_DWORD *)NPagedPerProcessorLookaside + 14) = *(_DWORD *)(a2 + 152);
      *(_QWORD *)(a2 + 280) = NPagedPerProcessorLookaside;
      NPagedPerProcessorLookaside[8] = v27;
      if ( (*(_DWORD *)(a2 + 300) & 0x20) != 0
        || (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 96LL))
        || (v88 = *((_QWORD *)v27 + 7), a2 == v88)
        || (v89 = *(_QWORD *)(a2 + 136), v89 == v88)
        || (v90 = *(_QWORD *)(*((_QWORD *)v27 + 13) + 56LL), v89 == v90)
        || a2 == v90 )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 280) + 60LL) |= 1u;
      }
    }
    v77 = *(_QWORD *)(a2 + 280);
    if ( v77 )
    {
      if ( *(struct _IRP_CONTEXT **)(v77 + 64) == v27 && (*(_DWORD *)(v77 + 60) & 1) == 0 )
      {
        if ( (*(_DWORD *)(a2 + 300) & 0x20) != 0
          || (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 96LL))
          || (v78 = *((_QWORD *)v27 + 7), a2 == v78)
          || (v79 = *(_QWORD *)(a2 + 136), v79 == v78)
          || (v80 = *(_QWORD *)(*((_QWORD *)v27 + 13) + 56LL), a2 == v80)
          || v79 == v80 )
        {
          *(_DWORD *)(*(_QWORD *)(a2 + 280) + 60LL) |= 1u;
          *(_QWORD *)(*(_QWORD *)(a2 + 280) + 24LL) = *(_QWORD *)(a2 + 24);
          *(_QWORD *)(*(_QWORD *)(a2 + 280) + 32LL) = *(_QWORD *)(a2 + 32);
        }
      }
    }
  }
  if ( *(__int16 *)(a2 + 256) < 0 )
  {
    v91 = *(_DWORD *)(a2 + 152);
    if ( ((v91 & 8) == 0 || (v91 & 0x40) != 0) && (v106[0] & (_DWORD)v102[68]) != 0 )
    {
      v92 = 1;
      v106[0] >>= *((_BYTE *)v102 + 552);
      FileSizes.AllocationSize.QuadPart = 0;
      FileSizes.FileSize.QuadPart = 0;
      *(_QWORD *)Status = 0;
      v106[1] = 1;
      RefsLookupAllocation(v27, a2, v106, 4);
      if ( HIBYTE(Status[0]) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            &WPP_333749fe71273bc3659f43e52285135c_Traceguids,
            3221266439LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073700857, v27, "write.c", 0x30Du);
        RefsRaiseStatusInternal(v27, -1073700857, v100);
        __debugbreak();
      }
      if ( !_bittest16((const signed __int16 *)(a2 + 256), 0xDu)
        || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 144) + 112LL) + 3396LL) & 0x800000) == 0 )
      {
        v92 = 0;
      }
      *((_DWORD *)v27 + 174) = v92;
    }
  }
  v31 = a4[1];
  if ( v31.QuadPart > *(_QWORD *)(a2 + 24) )
  {
    v93 = *(_DWORD *)(a2 + 152);
    if ( (v93 & 8) != 0 && (v93 & 0x40) == 0 )
    {
      if ( !(unsigned __int8)RefsAddAllocationForResidentWrite(v27, (struct _SCB *)a2) )
        goto LABEL_21;
      v31 = a4[1];
    }
    if ( v31.QuadPart > *(_QWORD *)(a2 + 24) )
      RefsAddAllocationForNonResidentWrite(v27, (struct DataSCB *)a2, (__int64)v105);
  }
LABEL_21:
  v32 = a4[1];
  if ( v32.QuadPart > *(_QWORD *)(a2 + 424) )
    *(LARGE_INTEGER *)(a2 + 424) = v32;
  v33 = *(_QWORD *)(a2 + 248);
  v34 = *(_QWORD *)(v33 + 16);
  if ( v34 )
  {
    v81 = a4[1];
    if ( v81.QuadPart > *(_QWORD *)(v34 + 8) )
    {
      FileSizes.AllocationSize.QuadPart = *(_QWORD *)(a2 + 24);
      FileSizes.ValidDataLength.QuadPart = *(_QWORD *)(a2 + 40);
      FileSizes.FileSize = v81;
      if ( v81.QuadPart <= v12.QuadPart )
        FileSizes.FileSize = v12;
      v106[0] = v33 + 8;
      CcSetFileSizesEx((PFILE_OBJECT)&v102, &FileSizes);
    }
  }
  if ( (*(_DWORD *)(a2 + 152) & 0x10) != 0 )
  {
    *(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) |= 0x10uLL;
    *(_DWORD *)(a3 + 4) |= 0x10000u;
  }
  RefsCheckpointCurrentTransaction(v27);
  *v105 |= 4u;
  for ( i = *v5; i != (LARGE_INTEGER *)v5 && i[-2].QuadPart > a4[1].QuadPart; i = (LARGE_INTEGER *)i->QuadPart )
    ;
  v36 = *(struct _FAST_MUTEX **)(a2 + 48);
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe(v36);
  QuadPart = (LARGE_INTEGER **)i[1].QuadPart;
  v38 = a4 + 3;
  if ( *QuadPart != i )
LABEL_31:
    __fastfail(3u);
  v38->QuadPart = (LONGLONG)i;
  v38[1].QuadPart = (LONGLONG)QuadPart;
  *QuadPart = v38;
  i[1].QuadPart = (LONGLONG)v38;
  ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(a2 + 48));
  KeLeaveGuardedRegion();
  v39 = *((_DWORD *)v27 + 1);
  if ( (v39 & 0x2000) != 0 )
  {
    v95 = v102 + 151;
    *((_DWORD *)v27 + 1) = v39 & 0xFFFFCFFF;
    ExReleaseFastResource(v95, 0);
  }
  v40 = (_QWORD *)*((_QWORD *)v27 + 14);
  v41 = (_QWORD *)((char *)v27 + 112);
LABEL_36:
  if ( v40 != v41 )
  {
    v42 = *((_WORD *)v40 - 18);
    v43 = v40 - 8;
    v44 = v40;
    v102 = v40;
    v40 = (_QWORD *)*v40;
    LOWORD(Status[0]) = v42;
    while ( !*v44 )
    {
LABEL_48:
      if ( *(_WORD *)v43 == 2050 )
        v51 = v43;
      else
        v51 = (_QWORD *)v43[17];
      v52 = 0;
      CurrentThread = KeGetCurrentThread();
      v54 = v51[11] + 64LL;
      v42 = Status[0];
      for ( j = 0; j < 2; ++j )
      {
        v56 = 14LL * j;
        v57 = &a1[v56 + 44];
        if ( *v57 == (struct _IRP_CONTEXT *)v54 && a1[v56 + 45] == CurrentThread )
        {
          v52 = &a1[v56 + 44];
          if ( v57 )
            goto LABEL_65;
          break;
        }
      }
      for ( k = a1[72]; k != (struct _IRP_CONTEXT *)(a1 + 72); k = *(struct _IRP_CONTEXT **)k )
      {
        if ( *((_QWORD *)k - 12) == v54 && *((struct _KTHREAD **)k - 11) == CurrentThread )
        {
          v52 = (struct _IRP_CONTEXT **)((char *)k - 96);
          break;
        }
      }
LABEL_65:
      IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v51[11] + 64LL);
      if ( !v52 )
      {
        v67 = (struct _ERESOURCE *)(v51[11] + 64LL);
        if ( IsFastResourceHeldExclusive )
          ExReleaseFastResource(v67, 0);
        else
          ExReleaseResourceLite(v67);
        goto LABEL_68;
      }
      v69 = *((_DWORD *)v52 + 4);
      if ( IsFastResourceHeldExclusive )
      {
        if ( !v69 )
          goto LABEL_74;
        *((_DWORD *)v52 + 4) = v69 - 1;
        if ( v69 != 1 )
          goto LABEL_74;
LABEL_73:
        *v52 = 0;
        v52[1] = 0;
        goto LABEL_74;
      }
      *((_DWORD *)v52 + 4) = v69 - 1;
      if ( v69 == 1 )
        goto LABEL_73;
LABEL_74:
      ExReleaseFastResource(v51[11] + 64LL, v52 + 3);
LABEL_68:
      v44 = v102;
LABEL_69:
      v68 = v42-- == 1;
      LOWORD(Status[0]) = v42;
      if ( v68 )
        goto LABEL_36;
    }
    if ( *((_WORD *)v43 + 14) != 1 )
      goto LABEL_47;
    v45 = a1[3];
    if ( v45 && *((_QWORD *)v45 + 18) && ((v43[1] & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
      goto LABEL_69;
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v44);
    v47 = (_QWORD **)((char *)v46 + 640);
    v48[1] = 0;
    *v48 = 0;
    v49 = (_QWORD *)*((_QWORD *)v46 + 80);
    if ( v49 == (_QWORD *)((char *)v46 + 640) )
      goto LABEL_47;
    v50 = 0;
    while ( v49 != v47 )
    {
      if ( *((_WORD *)v49 - 4) == 2087 )
      {
        v50 = v49 - 1;
        break;
      }
      v49 = (_QWORD *)*v49;
    }
    if ( !v50 )
    {
LABEL_47:
      --*((_WORD *)v43 + 14);
      goto LABEL_48;
    }
    while ( 1 )
    {
      v82 = *v47;
      v106[0] = 0;
      if ( v82 != v47 )
      {
        if ( v50 )
          v82 = (_QWORD *)v50[1];
        while ( v82 != v47 )
        {
          if ( *((_WORD *)v82 - 4) == 2087 )
          {
            v106[0] = v82 - 1;
            break;
          }
          v82 = (_QWORD *)*v82;
        }
      }
      v83 = v50[6];
      if ( v83 )
      {
        if ( *(_QWORD **)(v83 + 136) != v43 )
          goto LABEL_125;
        if ( ((*(_DWORD *)(v83 + 152) & 0x2000) != 0 || (*(_DWORD *)(v83 + 300) & 0x40) != 0)
          && (*(_DWORD *)(v83 + 152) & 0x2000) != 0 )
        {
          _InterlockedAnd((volatile signed __int32 *)(v83 + 152), 0xFFFFDFFF);
        }
        v84 = *(struct _FAST_MUTEX **)(v50[6] + 48LL);
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe(v84);
        _InterlockedIncrement((volatile signed __int32 *)(v50[6] + 172LL));
        *(_QWORD *)(v50[6] + 280LL) = 0;
        ++*(_DWORD *)(v50[6] + 172LL);
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(v50[6] + 48LL));
        KeLeaveGuardedRegion();
        v46 = (struct _IRP_CONTEXT *)a1;
      }
      v85 = v50[1];
      if ( *(_QWORD **)(v85 + 8) != v50 + 1 )
        goto LABEL_31;
      v86 = (_QWORD *)v50[2];
      if ( (_QWORD *)*v86 != v50 + 1 )
        goto LABEL_31;
      *v86 = v85;
      *(_QWORD *)(v85 + 8) = v86;
      if ( v50 != (_QWORD *)((char *)v46 + 728) )
      {
        v87 = *((_DWORD *)v50 - 2);
        if ( v87 >= RefsNumberProcessors )
          v87 %= RefsNumberProcessors;
        ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v87], v50 - 1);
        v46 = (struct _IRP_CONTEXT *)a1;
      }
LABEL_125:
      v50 = (_QWORD *)v106[0];
      if ( !v106[0] )
        goto LABEL_47;
    }
  }
  v58 = (struct _IRP_CONTEXT *)a1;
  if ( a1[6] )
  {
    RefsReleaseSharedResources((struct _IRP_CONTEXT *)a1);
    v58 = (struct _IRP_CONTEXT *)a1;
  }
  v59 = *(_DWORD *)(a2 + 152);
  v60 = v105;
  if ( (v59 & 8) == 0 || (v59 & 0x40) != 0 || (*v105 & 8) == 0 )
  {
    *((_QWORD *)v58 + 7) = 0;
    v61 = *(struct _FAST_MUTEX **)(a2 + 48);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v61);
    v62 = (_QWORD *)(a2 + 448);
    if ( (_QWORD *)*v62 == v62 )
    {
      *(_QWORD *)(a2 + 440) = 0;
    }
    else
    {
      v63 = (_QWORD *)*v62;
      *(_QWORD *)(a2 + 440) |= 3uLL;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v63);
      *(_QWORD *)(v64 + 8) = 0;
      *(_QWORD *)v64 = 0;
      KeSetEvent((PRKEVENT)(v64 + 16), 0, 0);
    }
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(a2 + 48));
    KeLeaveGuardedRegion();
    v60[1] &= ~4u;
  }
}

```

## disassembly

```asm
0x1400867d0  push    rbp
0x1400867d2  push    rsi
0x1400867d3  push    rdi
0x1400867d4  push    r12
0x1400867d6  push    r13
0x1400867d8  push    r14
0x1400867da  lea     rbp, [rsp-27h]
0x1400867df  sub     rsp, 0B8h
0x1400867e6  mov     rax, cs:__security_cookie
0x1400867ed  xor     rax, rsp
0x1400867f0  mov     [rbp+4Fh+var_48], rax
0x1400867f4  mov     rax, [rbp+4Fh+arg_20]
0x1400867f8  lea     rdi, [rdx+1D0h]
0x1400867ff  mov     [rbp+4Fh+var_80], rax
0x140086803  mov     rsi, r9
0x140086806  mov     rax, [rdi]
0x140086809  mov     r9, rcx
0x14008680c  mov     [rbp+4Fh+var_A0], rcx
0x140086810  mov     r13, r8
0x140086813  mov     rcx, [rdx+20h]
0x140086817  mov     r14, rdx
0x14008681a  mov     [rbp+4Fh+var_70], rcx
0x14008681e  mov     r12, rcx
0x140086821  cmp     rax, rdi
0x140086824  jz      short loc_140086831
0x140086826  mov     rax, [rax-10h]
0x14008682a  cmp     rax, rcx
0x14008682d  cmovg   r12, rax
0x140086831  mov     rcx, [r9+40h]
0x140086835  mov     eax, [rdx+98h]
0x14008683b  mov     [rsp+0E0h+var_30], rbx
0x140086843  mov     [rbp+4Fh+var_98], rcx
0x140086847  mov     [rsp+0E0h+var_38], r15
0x14008684f  test    al, 8
0x140086851  jnz     loc_140086E87
0x140086857  mov     eax, [rcx+220h]
0x14008685d  mov     r8, [rsi+8]
0x140086861  movsx   ecx, byte ptr [rcx+228h]
0x140086868  mov     rdx, [rdx+1A8h]
0x14008686f  lea     rbx, [r12+rax]
0x140086873  sar     rbx, cl
0x140086876  lea     r15, [r8+rax]
0x14008687a  cmp     r8, rdx
0x14008687d  jge     loc_140086A07
0x140086883  sar     r15, cl
0x140086886  cmp     rbx, r15
0x140086889  jl      loc_140200BC0
0x14008688f  movzx   r15d, byte ptr [r9+8]
0x140086894  mov     rbx, [r14+88h]
0x14008689b  and     r15b, 1
0x14008689f  mov     [rbp+4Fh+Status], 0
0x1400868a6  mov     eax, 802h
0x1400868ab  cmp     [rbx], ax
0x1400868ae  jnz     loc_140086A10
0x1400868b4  mov     rcx, rbx
0x1400868b7  mov     rcx, [rcx+58h]
0x1400868bb  movzx   r8d, r15b
0x1400868bf  add     rcx, 40h ; '@'
0x1400868c3  xor     edx, edx
0x1400868c5  call    cs:__imp_ExAcquireFastResourceExclusive
0x1400868cc  nop     dword ptr [rax+rax+00h]
0x1400868d1  test    al, al
0x1400868d3  jz      loc_1400870AA
0x1400868d9  test    byte ptr [rbx+8], 1
0x1400868dd  jnz     loc_140087212
0x1400868e3  mov     eax, [r14+12Ch]
0x1400868ea  test    al, 40h
0x1400868ec  jnz     loc_140087212
0x1400868f2  mov     r15, [rbp+4Fh+var_A0]
0x1400868f6  cmp     qword ptr [rbx+40h], 0
0x1400868fb  lea     rcx, [rbx+40h]
0x1400868ff  jnz     short loc_140086921
0x140086901  mov     rdx, [r15+70h]
0x140086905  lea     rax, [r15+70h]
0x140086909  cmp     [rdx+8], rax
0x14008690d  jnz     loc_140086A00
0x140086913  mov     [rcx], rdx
0x140086916  mov     [rcx+8], rax
0x14008691a  mov     [rdx+8], rcx
0x14008691e  mov     [rax], rcx
0x140086921  inc     word ptr [rbx+1Ch]
0x140086925  mov     r8d, 827h
0x14008692b  test    dword ptr [r14+98h], 200h
0x140086936  jnz     loc_140086CFD
0x14008693c  cmp     word ptr [r14+100h], 0
0x140086945  jl      loc_14008717A
0x14008694b  mov     rax, [rsi+8]
0x14008694f  cmp     rax, [r14+18h]
0x140086953  jg      loc_1400871BB
0x140086959  mov     rax, [rsi+8]
0x14008695d  cmp     rax, [r14+1A8h]
0x140086964  jg      loc_140086EC8
0x14008696a  mov     rcx, [r14+0F8h]
0x140086971  mov     rax, [rcx+10h]
0x140086975  test    rax, rax
0x140086978  jnz     loc_140086E94
0x14008697e  mov     eax, [r14+98h]
0x140086985  test    al, 10h
0x140086987  jz      short loc_1400869A8
0x140086989  mov     rcx, [r14+88h]
0x140086990  mov     rax, [rcx+8]
0x140086994  or      rax, 10h
0x140086998  mov     [rcx+8], rax
0x14008699c  mov     eax, [r13+4]
0x1400869a0  bts     eax, 10h
0x1400869a4  mov     [r13+4], eax
0x1400869a8  mov     rcx, r15; struct _IRP_CONTEXT *
0x1400869ab  call    ?RefsCheckpointCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointCurrentTransaction(_IRP_CONTEXT *)
0x1400869b0  mov     r12, [rbp+4Fh+var_80]
0x1400869b4  or      byte ptr [r12], 4
0x1400869b9  mov     rbx, [rdi]
0x1400869bc  nop     dword ptr [rax+00h]
0x1400869c0  cmp     rbx, rdi
0x1400869c3  jz      short loc_1400869D4
0x1400869c5  mov     rax, [rsi+8]
0x1400869c9  cmp     [rbx-10h], rax
0x1400869cd  jle     short loc_1400869D4
0x1400869cf  mov     rbx, [rbx]
0x1400869d2  jmp     short loc_1400869C0
0x1400869d4  mov     rdi, [r14+30h]
0x1400869d8  call    cs:__imp_KeEnterGuardedRegion
0x1400869df  nop     dword ptr [rax+rax+00h]
0x1400869e4  mov     rcx, rdi; FastMutex
0x1400869e7  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400869ee  nop     dword ptr [rax+rax+00h]
0x1400869f3  mov     rax, [rbx+8]
0x1400869f7  add     rsi, 18h
0x1400869fb  cmp     [rax], rbx
0x1400869fe  jz      short loc_140086A1C
0x140086a00  mov     ecx, 3
0x140086a05  int     29h; Win8: RtlFailFast(ecx)
0x140086a07  lea     r15, [rdx+rax]
0x140086a0b  jmp     loc_140086883
0x140086a10  mov     rcx, [rbx+88h]
0x140086a17  jmp     loc_1400868B7
0x140086a1c  mov     [rsi], rbx
0x140086a1f  mov     [rsi+8], rax
0x140086a23  mov     [rax], rsi
0x140086a26  mov     [rbx+8], rsi
0x140086a2a  mov     rcx, [r14+30h]; FastMutex
0x140086a2e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140086a35  nop     dword ptr [rax+rax+00h]
0x140086a3a  call    cs:__imp_KeLeaveGuardedRegion
0x140086a41  nop     dword ptr [rax+rax+00h]
0x140086a46  mov     eax, [r15+4]
0x140086a4a  bt      eax, 0Dh
0x140086a4e  jb      loc_140087248
0x140086a54  mov     rbx, [r15+70h]
0x140086a58  add     r15, 70h ; 'p'
0x140086a5c  cmp     rbx, r15
0x140086a5f  jz      loc_140086B44
0x140086a65  movzx   r12d, word ptr [rbx-24h]
0x140086a6a  lea     rsi, [rbx-40h]
0x140086a6e  mov     rcx, rbx
0x140086a71  mov     [rbp+4Fh+var_98], rbx
0x140086a75  mov     rbx, [rbx]
0x140086a78  mov     eax, 0FFFFh
0x140086a7d  mov     word ptr [rbp+4Fh+Status], r12w
0x140086a82  cmp     qword ptr [rcx], 0
0x140086a86  jz      short loc_140086AED
0x140086a88  cmp     word ptr [rsi+1Ch], 1
0x140086a8d  jnz     short loc_140086AE9
0x140086a8f  mov     r8, [rbp+4Fh+var_A0]
0x140086a93  mov     rax, [r8+18h]
0x140086a97  test    rax, rax
0x140086a9a  jnz     loc_14008703F
0x140086aa0  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140086aa5  xor     edx, edx
0x140086aa7  lea     r12, [r8+280h]
0x140086aae  mov     [rcx+8], rdx
0x140086ab2  mov     [rcx], rdx
0x140086ab5  mov     rax, [r12]
0x140086ab9  cmp     rax, r12
0x140086abc  jz      short loc_140086AE4
0x140086abe  mov     r13d, edx
0x140086ac1  cmp     rax, r12
0x140086ac4  jz      short loc_140086ADB
0x140086ac6  mov     r9d, 827h
0x140086acc  cmp     [rax-8], r9w
0x140086ad1  jnz     loc_1400870D7
0x140086ad7  lea     r13, [rax-8]
0x140086adb  test    r13, r13
0x140086ade  jnz     loc_140086EE0
0x140086ae4  mov     eax, 0FFFFh
0x140086ae9  add     [rsi+1Ch], ax
0x140086aed  mov     r12d, 802h
0x140086af3  cmp     [rsi], r12w
0x140086af7  jnz     loc_140086CF1
0x140086afd  mov     r13, rsi
0x140086b00  mov     r8, [r13+58h]
0x140086b04  xor     edi, edi
0x140086b06  mov     r9, gs:188h
0x140086b0f  add     r8, 40h ; '@'
0x140086b13  movzx   r12d, word ptr [rbp+4Fh+Status]
0x140086b18  xor     edx, edx
0x140086b1a  mov     r10, [rbp+4Fh+var_A0]
0x140086b1e  cmp     edx, 2
0x140086b21  jnb     loc_140086C2C
0x140086b27  mov     eax, edx
0x140086b29  imul    rcx, rax, 70h ; 'p'
0x140086b2d  lea     rax, [r10+160h]
0x140086b34  add     rax, rcx
0x140086b37  cmp     [rax], r8
0x140086b3a  jz      loc_140086CC6
0x140086b40  inc     edx
0x140086b42  jmp     short loc_140086B1A
0x140086b44  mov     rcx, [rbp+4Fh+var_A0]; struct _IRP_CONTEXT *
0x140086b48  cmp     qword ptr [rcx+30h], 0
0x140086b4d  jnz     loc_14008728B
0x140086b53  mov     eax, [r14+98h]
0x140086b5a  mov     r12, [rbp+4Fh+var_80]
0x140086b5e  test    al, 8
0x140086b60  jnz     loc_140086BEB
0x140086b66  xor     edi, edi
0x140086b68  mov     [rcx+38h], rdi
0x140086b6c  mov     rbx, [r14+30h]
0x140086b70  call    cs:__imp_KeEnterGuardedRegion
0x140086b77  nop     dword ptr [rax+rax+00h]
0x140086b7c  mov     rcx, rbx; FastMutex
0x140086b7f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140086b86  nop     dword ptr [rax+rax+00h]
0x140086b8b  lea     rcx, [r14+1C0h]
0x140086b92  cmp     [rcx], rcx
0x140086b95  jz      loc_140086CE5
0x140086b9b  mov     rcx, [rcx]
0x140086b9e  or      qword ptr [r14+1B8h], 3
0x140086ba6  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140086bab  mov     [rcx+8], rdi
0x140086baf  xor     edx, edx; Increment
0x140086bb1  mov     [rcx], rdi
0x140086bb4  xor     r8d, r8d; Wait
0x140086bb7  add     rcx, 10h; Event
0x140086bbb  call    cs:__imp_KeSetEvent
0x140086bc2  nop     dword ptr [rax+rax+00h]
0x140086bc7  mov     rcx, [r14+30h]; FastMutex
0x140086bcb  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140086bd2  nop     dword ptr [rax+rax+00h]
0x140086bd7  call    cs:__imp_KeLeaveGuardedRegion
0x140086bde  nop     dword ptr [rax+rax+00h]
0x140086be3  and     byte ptr [r12+1], 0FBh
0x140086be9  jmp     short loc_140086BFE
0x140086beb  test    al, 40h
0x140086bed  jnz     loc_140086B66
0x140086bf3  test    byte ptr [r12], 8
0x140086bf8  jz      loc_140086B66
0x140086bfe  mov     r15, [rsp+0E0h+var_38]
0x140086c06  mov     rbx, [rsp+0E0h+var_30]
0x140086c0e  mov     rcx, [rbp+4Fh+var_48]
0x140086c12  xor     rcx, rsp; StackCookie
0x140086c15  call    __security_check_cookie
0x140086c1a  add     rsp, 0B8h
0x140086c21  pop     r14
0x140086c23  pop     r13
0x140086c25  pop     r12
0x140086c27  pop     rdi
0x140086c28  pop     rsi
0x140086c29  pop     rbp
0x140086c2a  retn
0x140086c2c  lea     rax, [r10+240h]
0x140086c33  mov     rcx, [rax]
0x140086c36  cmp     rcx, rax
0x140086c39  jnz     loc_140087102
0x140086c3f  mov     rcx, r8
0x140086c42  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140086c49  nop     dword ptr [rax+rax+00h]
0x140086c4e  test    rdi, rdi
0x140086c51  jnz     short loc_140086C8E
0x140086c53  mov     rcx, [r13+58h]
0x140086c57  add     rcx, 40h ; '@'; Resource
0x140086c5b  test    al, al
0x140086c5d  jz      loc_14008727A
0x140086c63  xor     edx, edx
0x140086c65  call    cs:__imp_ExReleaseFastResource
0x140086c6c  nop     dword ptr [rax+rax+00h]
0x140086c71  mov     rcx, [rbp+4Fh+var_98]
0x140086c75  mov     eax, 0FFFFh
0x140086c7a  add     r12w, ax
0x140086c7e  mov     word ptr [rbp+4Fh+Status], r12w
0x140086c83  jz      loc_140086A5C
0x140086c89  jmp     loc_140086A82
0x140086c8e  mov     ecx, [rdi+10h]
0x140086c91  test    al, al
0x140086c93  jnz     loc_1400870DF
0x140086c99  lea     eax, [rcx-1]
0x140086c9c  mov     [rdi+10h], eax
0x140086c9f  test    eax, eax
0x140086ca1  jnz     short loc_140086CAC
0x140086ca3  xor     eax, eax
0x140086ca5  mov     [rdi], rax
0x140086ca8  mov     [rdi+8], rax
0x140086cac  mov     rcx, [r13+58h]
0x140086cb0  lea     rdx, [rdi+18h]
0x140086cb4  add     rcx, 40h ; '@'
0x140086cb8  call    cs:__imp_ExReleaseFastResource
0x140086cbf  nop     dword ptr [rax+rax+00h]
0x140086cc4  jmp     short loc_140086C71
0x140086cc6  cmp     [rcx+r10+168h], r9
0x140086cce  jnz     loc_140086B40
0x140086cd4  mov     rdi, rax
0x140086cd7  test    rax, rax
  ... truncated ...
```
