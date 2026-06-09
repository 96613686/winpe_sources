# RefsOpenAttribute

- ea: `0x140308440`
- end: `0x1403096c1`
- name: `RefsOpenAttribute`
- size: `4737`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1402986f0`
- `0x14029b914`
- `0x1403096d0`
- `0x14030bca0`
- `0x140332e30`

## callees

- `0x14002b340`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400872e0`
- `0x14008bd10`
- `0x140092890`
- `0x140093bc0`
- `0x1400946c0`
- `0x14009c190`
- `0x1400a2890`
- `0x1400d0fd8`
- `0x1400e7a10`
- `0x1400e7c94`
- `0x1401f4400`
- `0x140302e10`
- `0x140307e40`
- `0x140308440`
- `0x140309cb0`
- `0x14030bb50`
- `0x140333e98`

## import_xrefs

- `ntoskrnl!MmCanFileBeTruncated` at `0x140308a66`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140308a66`
- `ntoskrnl!IoSetLinkShareAccess` at `0x140308613`
- `ntoskrnl!IoSetLinkShareAccess` at `0x140308613`
- `ntoskrnl!IoUpdateLinkShareAccessEx` at `0x140308bd7`
- `ntoskrnl!IoUpdateLinkShareAccessEx` at `0x140308bd7`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140308d46`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x14030917d`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140308d46`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x14030917d`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140309657`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14030969a`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140309657`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14030969a`
- `ntoskrnl!IoRemoveShareAccess` at `0x1403421e2`
- `ntoskrnl!IoRemoveShareAccess` at `0x1403421e2`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403086df`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403086df`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14030867b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140308c30`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14030867b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140308c30`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140308739`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140308739`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403086ef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403086ef`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140308ed9`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140308ed9`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140308956`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140308956`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403087b7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403087b7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403087c3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403087c3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403094ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140309537`
- `ntoskrnl!ExReleasePushLockEx` at `0x1403094ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140309537`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140309581`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140309581`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14030947f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14030947f`

## string_xrefs

- `0x140308b18`: `Create.c`
- `0x140308f94`: `Create.c`
- `0x140309014`: `Create.c`
- `0x140309092`: `Create.c`
- `0x14030912d`: `Create.c`
- `0x1403091e8`: `Create.c`
- `0x140309295`: `Create.c`
- `0x140309343`: `Create.c`
- `0x1403093a6`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenAttribute(
        struct _IRP **a1,
        __int64 a2,
        __int64 a3,
        struct _LCB *a4,
        __int64 a5,
        struct _FCB *a6,
        __int16 a7,
        __int64 a8,
        unsigned __int16 a9,
        int a10,
        char a11,
        int a12,
        int a13,
        __int64 a14,
        struct _SCB **a15,
        _QWORD *a16)
{
  struct _IRP **v16; // r13
  struct _IRP **v18; // r10
  unsigned int v19; // ebx
  char v20; // r12
  unsigned int v21; // r11d
  __int64 Scb; // rdx
  unsigned __int16 v23; // si
  int v24; // r8d
  __int64 v25; // rbx
  int v26; // ecx
  unsigned __int8 v27; // al
  unsigned int v28; // edx
  struct _SCB *v29; // r9
  char v30; // r12
  int v31; // eax
  unsigned int v32; // r10d
  unsigned int v33; // r11d
  char *v34; // rcx
  __int64 v35; // rbx
  bool v36; // cl
  PERESOURCE Resource; // rax
  char *PoolWithTag; // rsi
  PMRX_NET_ROOT pNetRoot; // rbx
  struct _SCB **v40; // rdx
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  __int64 v42; // rax
  _QWORD *v43; // rdx
  __int64 *v44; // r11
  __int64 v45; // r9
  struct _SCB *v46; // rdx
  __int64 v47; // r8
  struct _SCB *v48; // r9
  __int16 v49; // cx
  __int16 v50; // ax
  struct _SCB *v51; // rcx
  __int64 v52; // rax
  unsigned int v53; // r8d
  int v54; // ecx
  int v55; // eax
  __int64 v56; // r10
  char *v57; // rcx
  __int16 v58; // ax
  __int16 v59; // ax
  char v60; // cl
  int v61; // r8d
  __int64 v62; // r9
  struct _SCB *v63; // rbx
  __int64 v64; // rsi
  __int64 v65; // rax
  unsigned __int8 v66; // dl
  __int16 v67; // ax
  struct _SCB *v68; // rcx
  bool IsTransactionActive; // r13
  struct _IRP_CONTEXT *v70; // rcx
  __int64 v71; // rbx
  int v72; // eax
  unsigned int v74; // [rsp+48h] [rbp-A0h]
  unsigned int v75; // [rsp+50h] [rbp-98h]
  __int64 v76; // [rsp+80h] [rbp-68h]
  struct _SCB *v77; // [rsp+A0h] [rbp-48h]

  v16 = (struct _IRP **)a4;
  v18 = a1;
  v19 = 0;
  v74 = 0;
  v20 = 0;
  v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) + 20LL);
  v75 = v21;
  Scb = (__int64)*a15;
  v23 = a9;
  if ( !*a15 )
  {
    Scb = RefsCreateScb(a1, a6, a9, a8, 0, 0);
    *a15 = (struct _SCB *)Scb;
    v21 = v75;
    v18 = a1;
  }
  v24 = *(_DWORD *)(Scb + 152);
  if ( (v24 & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v19 = -1073741738;
    }
    else
    {
      v19 = -1073741738;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 181, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225558LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741738, 0, "Create.c", 0x3D38u);
  }
  else
  {
    if ( *(_DWORD *)(Scb + 344) && (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 6) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = -1073741790;
      }
      else
      {
        v19 = -1073741790;
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          182,
          &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
          3221225506LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790, 0, "Create.c", 0x3D44u);
      return v19;
    }
    if ( a14 )
      goto LABEL_66;
    if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
    {
      if ( *(_WORD *)Scb != 2053 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v19 = -1073741811;
        }
        else
        {
          v19 = -1073741811;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            183,
            &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741811, 0, "Create.c", 0x3D56u);
        return v19;
      }
      if ( *(_DWORD *)(Scb + 160)
        || (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 0xFFFFFF7F) != 0
        || (v25 = a2 + 26, (*(_BYTE *)(a2 + 26) & 7) != 7) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v19 = -1073741598;
        }
        else
        {
          v19 = -1073741598;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            184,
            &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225698LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741598, 0, "Create.c", 0x3D65u);
        return v19;
      }
    }
    else
    {
      v25 = a2 + 26;
    }
    v26 = a10;
    if ( a10 != 2 )
      goto LABEL_90;
    if ( (v21 & 0x10027) != 0
      && (*(_WORD *)v25 & 2) == 0
      && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 248) + 8LL)) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = -1073741757;
      }
      else
      {
        v19 = -1073741757;
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          185,
          &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
          3221225539LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741757, 0, "Create.c", 0x3D8Bu);
      return v19;
    }
    if ( (*(_BYTE *)v25 & 1) != 0 )
    {
      v27 = 0;
LABEL_12:
      if ( !v20 || v27 )
        v28 = 0;
      else
        v28 = 0x80000000;
      v29 = *a15;
      v30 = a11;
      if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
      {
        v31 = 1;
      }
      else if ( a11 == 4 )
      {
        v31 = 2;
      }
      else
      {
        v31 = 0;
      }
      v32 = *(unsigned __int16 *)v25;
      v33 = v75;
      v34 = 0;
      if ( v31 && (v31 & 1) != 0 && !v16 )
      {
        if ( !*((_WORD *)v29 + 112)
          && ((v67 = *((_WORD *)v29 + 108), v67 == 128) || !v67 && (*((_DWORD *)v29 + 38) & 0x10) != 0)
          || *((_WORD *)v29 + 108) == 160 )
        {
          v33 = v75 & 0xFFFEFFFF;
          v32 |= 4u;
        }
      }
      if ( v16 )
      {
        v34 = (char *)v16 + 108;
        if ( *((_WORD *)v29 + 112)
          || (v58 = *((_WORD *)v29 + 108), v58 != 128) && (v58 || (*((_DWORD *)v29 + 38) & 0x10) == 0) )
        {
          if ( *((_WORD *)v29 + 108) != 160 )
            v28 |= 0x80u;
        }
      }
      IoSetLinkShareAccess(v33, v32, *(_QWORD *)(a2 + 48), (char *)v29 + 188, v34, v28);
      while ( 1 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(a2 + 48) + 75LL) )
        {
          v68 = *a15;
          if ( (*((_DWORD *)*a15 + 75) & 0x1000) == 0 && *(_WORD *)v68 == 2053 )
          {
            if ( *((_QWORD *)v68 + 47) )
            {
              IsTransactionActive = RefsIsTransactionActive((struct _IRP_CONTEXT *)a1);
              v19 = RefsBindMinstoreTransactionNoRaise(v70);
              if ( (v19 & 0x80000000) != 0 )
                return v19;
              v71 = a3 + 784;
              ExAcquirePushLockExclusiveEx(a3 + 784, 0);
              v72 = MsAddReservationForSparseWrite(
                      a1[3],
                      *((_QWORD *)*a15 + 54),
                      (__int64)(*(unsigned int *)(a3 + 544) + *((_QWORD *)*a15 + 47)) >> *(_BYTE *)(a3 + 552));
              v74 = v72;
              if ( !IsTransactionActive )
              {
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                v72 = v74;
              }
              if ( v72 < 0 )
              {
                ExReleasePushLockEx(v71, 0);
                return v74;
              }
              *(_QWORD *)(a3 + 256) += (__int64)(*(unsigned int *)(a3 + 544) + *((_QWORD *)*a15 + 47)) >> *(_BYTE *)(a3 + 552);
              ExReleasePushLockEx(v71, 0);
            }
            *((_DWORD *)*a15 + 75) |= 0x1000u;
          }
        }
        v35 = *(_QWORD *)(a2 + 48);
        v36 = v23 == 160 || (a13 & 0x20000) != 0;
        v77 = *a15;
        Resource = a6->Header.Resource;
        if ( v36 )
        {
          if ( ((unsigned __int16)Resource & 0x400) == 0
            || (PoolWithTag = (char *)&a6[1].1 + 144, *((_WORD *)&a6[1].1 + 72)) )
          {
            PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsCcbLookasideList);
          }
          memset(PoolWithTag, 0, 0x1E8u);
          *(_DWORD *)PoolWithTag = 31983624;
        }
        else
        {
          if ( ((unsigned __int16)Resource & 0x200) == 0
            || (PoolWithTag = (char *)&a6[1].pBufferingStateChangeCompletedEvent,
                LOWORD(a6[1].pBufferingStateChangeCompletedEvent)) )
          {
            if ( ((unsigned __int8)Resource & 2) != 0 )
              PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x88u, 0x63666552u);
            else
              PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsCcbDataLookasideList);
          }
          memset(PoolWithTag, 0, 0x88u);
          *(_DWORD *)PoolWithTag = 8914953;
        }
        *((_DWORD *)PoolWithTag + 1) = a13;
        if ( _VCB::IsSystemVolume((_VCB *)a6->Header.FileContextSupportPointer) )
        {
          if ( (Feature_ReFS_Fake_TxF__private_featureState & 0x10) == 0 )
          {
            v76 = (unsigned int)Feature_ReFS_Fake_TxF__private_featureState | 1LL;
            wil_details_FeatureReporting_ReportUsageToService(&Feature_ReFS_Fake_TxF__private_descriptor, v76, 3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v76,
              3,
              &Feature_ReFS_Fake_TxF__private_descriptor);
          }
          TransactionParameterBlock = IoGetTransactionParameterBlock((PFILE_OBJECT)v35);
          if ( TransactionParameterBlock && TransactionParameterBlock->TransactionObject )
            *((_DWORD *)PoolWithTag + 2) |= 0x80000000;
        }
        *((_OWORD *)PoolWithTag + 1) = *(_OWORD *)(v35 + 88);
        *((_WORD *)PoolWithTag + 16) = a7;
        *((_QWORD *)PoolWithTag + 16) = v35;
        pNetRoot = a6->pNetRoot;
        KeEnterGuardedRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)&pNetRoot->pSrvCall);
        v40 = (struct _SCB **)*((_QWORD *)v77 + 34);
        if ( *v40 != (struct _SCB *)((char *)v77 + 264) )
LABEL_33:
          __fastfail(3u);
        *((_QWORD *)PoolWithTag + 5) = (char *)v77 + 264;
        *((_QWORD *)PoolWithTag + 6) = v40;
        *v40 = (struct _SCB *)(PoolWithTag + 40);
        *((_QWORD *)v77 + 34) = PoolWithTag + 40;
        if ( a4 )
        {
          v42 = _LCB::LcbChildCcbsWritable(a4);
          v43 = *(_QWORD **)(v42 + 8);
          if ( *v43 != v42 )
            goto LABEL_33;
          *((_QWORD *)PoolWithTag + 7) = v42;
          *((_QWORD *)PoolWithTag + 8) = v43;
          *v43 = PoolWithTag + 56;
          *(_QWORD *)(v42 + 8) = PoolWithTag + 56;
          *((_QWORD *)PoolWithTag + 9) = a4;
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)&a6->pNetRoot->pSrvCall);
        KeLeaveGuardedRegion();
        *a16 = PoolWithTag;
        RefsIncrementCloseCounts(
          *a15,
          ((__int64)a6->spacer.Resource & 4) != 0,
          *(_WORD *)(*(_QWORD *)(a2 + 48) + 75LL) == 0);
        RefsIncrementCleanupCounts(*a15, a4, (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) >> 3) & 1);
        v23 = 128;
        if ( (a13 & 0x20000) != 0 )
          *((_DWORD *)*a15 + 75) |= 0x80u;
        v45 = *v44;
        v46 = *a15;
        v47 = *(_QWORD *)(a2 + 48);
        *(_QWORD *)(v47 + 24) = *a15;
        *(_QWORD *)(v47 + 32) = v45;
        *(_QWORD *)(v47 + 16) = *(_QWORD *)(*((_QWORD *)v46 + 18) + 208LL);
        *(_QWORD *)(v47 + 40) = 0;
        if ( v30 == 4 )
          *(_DWORD *)(v47 + 80) |= 0x400000u;
        if ( v45 )
          *(_BYTE *)(v45 + 80) = v30;
        if ( v30 == 3 )
        {
          if ( (*(_DWORD *)(*((_QWORD *)v46 + 17) + 8LL) & 0x2000LL) != 0 )
            *((_WORD *)v46 + 128) |= 0x4000u;
        }
        else
        {
          *(_QWORD *)(v47 + 40) = *((_QWORD *)v46 + 31) + 8LL;
        }
        if ( (*((_DWORD *)v46 + 75) & 0x100) != 0 )
          *(_DWORD *)(v47 + 80) |= 0x8000u;
        if ( a12
          || (v75 & 7) == 0
          || (*((_DWORD *)*a15 + 38) & 0x20) == 0
          || (v50 = *((_WORD *)*a15 + 108), v25 = 176, v50 != 128) && v50 != 176
          || (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 8) == 0
          || (v51 = *a15, *((_DWORD *)*a15 + 40) != *((_DWORD *)*a15 + 39))
          || *((__int16 *)v51 + 128) < 0
          || (v52 = *((_QWORD *)v51 + 31), !*(_QWORD *)(v52 + 8))
          || *(_QWORD *)(v52 + 24)
          || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v52 + 8), 0)
          || (*(_DWORD *)(*((_QWORD *)*a15 + 17) + 8LL) & 0x100LL) != 0 )
        {
          v16 = a1;
          goto LABEL_57;
        }
        v16 = a1;
        if ( !a6->Context || (*((_DWORD *)a1 + 1) & 0x10000) != 0 || (unsigned __int8)MsIsFastResourceHeldExclusive() )
          break;
        *((_DWORD *)a1 + 1) |= 0x10000u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            189,
            &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, (struct _IRP_CONTEXT *)a1, "Create.c", 0x3E76u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741608, v53);
LABEL_90:
        v54 = v26 - 1;
        if ( v54 )
        {
          if ( v54 == 2 )
            v25 = a2 + 26;
          if ( (v21 & 0x10027) != 0 && (*(_WORD *)v25 & 2) == 0 )
          {
            if ( MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 248) + 8LL)) )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                v19 = -1073741757;
              }
              else
              {
                v19 = -1073741757;
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  187,
                  &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                  3221225539LL);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741757, 0, "Create.c", 0x3DCDu);
              return v19;
            }
            v21 = v75;
            v18 = a1;
          }
          if ( (*(_BYTE *)v25 & 1) != 0 )
            goto LABEL_131;
          v66 = RefsWriteCheck((struct _IRP_CONTEXT *)v18, a6, v18[9]);
          if ( !v66 && (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) != 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v19 = -1073741790;
            }
            else
            {
              v19 = -1073741790;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                188,
                &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221225506LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741790, 0, "Create.c", 0x3DE1u);
            return v19;
          }
          v21 = v75;
          v61 = -2147483647;
          if ( v66 )
LABEL_131:
            v61 = 1;
          if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
          {
            v62 = 1;
            v30 = a11;
          }
          else
          {
            v30 = a11;
            if ( a11 == 4 )
              v62 = 2;
            else
              v62 = 0;
          }
          v19 = RefsCheckShareAccess(v21, *(unsigned __int16 *)v25, *(_QWORD *)(a2 + 48), v62, *a15, v16, v61);
          v74 = v19;
          if ( (v19 & 0x80000000) != 0 )
            return v19;
        }
        else
        {
          v30 = a11;
          if ( (*(_DWORD *)(a5 + 144) & 0x40) != 0 )
          {
            v55 = 1;
          }
          else if ( a11 == 4 )
          {
            v55 = 2;
          }
          else
          {
            v55 = 0;
          }
          v56 = *(_QWORD *)(a2 + 48);
          v57 = 0;
          if ( v55 && (v55 & 1) != 0 && !v16 )
          {
            if ( !*(_WORD *)(Scb + 224) && ((v59 = *(_WORD *)(Scb + 216), v59 == 128) || !v59 && (v24 & 0x10) != 0)
              || *(_WORD *)(Scb + 216) == 160 )
            {
              *(_BYTE *)(v56 + 76) = 0;
              *(_BYTE *)(v56 + 79) = 1;
            }
          }
          if ( v16 )
            v57 = (char *)v16 + 108;
          IoUpdateLinkShareAccessEx(v56, Scb + 188, v57);
        }
      }
      RefsFlushAndPurgeScb((struct _IRP_CONTEXT *)a1, *a15);
LABEL_57:
      v48 = *a15;
      v49 = *((_WORD *)*a15 + 108);
      if ( (v49 != 128 && v49 != 176 || *(_WORD *)v48 != 2053 || *(struct _SCB **)(*((_QWORD *)v48 + 18) + 72LL) == v48)
        && (v49 != 160
         || *((_WORD *)v48 + 112) != 8
         || **((_QWORD **)v48 + 29) != *(_QWORD *)RefsFileNameIndex.Buffer
         || (unsigned __int16)(*(_WORD *)v48 - 2051) > 1u) )
      {
        goto LABEL_128;
      }
      v19 = FsRtlCheckOplockEx((POPLOCK)v48 + 11, v16[9], 2u, 0, 0, 0);
      if ( (*(_DWORD *)(a2 + 16) & 0x10000) == 0
        || (v19 = FsRtlOplockFsctrl((POPLOCK)*a15 + 11, v16[9], *((_DWORD *)*a15 + 40)),
            v74 = v19,
            (v19 & 0x80000000) != 0) )
      {
LABEL_64:
        if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
          FsRtlOplockFsctrl((POPLOCK)*a15 + 11, v16[9], 1u);
LABEL_66:
        if ( (*((_DWORD *)&a6->1 + 38) & 0x100) != 0 )
        {
          *((_DWORD *)*a15 + 75) |= 0x100u;
          *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) |= 0x8000u;
        }
        return v19;
      }
      v63 = *a15;
      v64 = *((_QWORD *)*a15 + 18);
      if ( (*(_DWORD *)(v64 + 24) & 0x4000005) == 1
        && *(_WORD *)v63 == 2053
        && (*((_DWORD *)v63 + 75) & 0x40) == 0
        && *(char *)(*((_QWORD *)v63 + 17) + 8LL) >= 0 )
      {
        if ( (*((_DWORD *)v63 + 38) & 0x20) == 0 )
        {
LABEL_126:
          v60 = 2;
LABEL_127:
          *((_BYTE *)*a15 + 5) = v60;
LABEL_128:
          v19 = v74;
          goto LABEL_64;
        }
        if ( FsRtlOplockIsFastIoPossible((POPLOCK)v63 + 11) )
        {
          if ( *((__int16 *)v63 + 128) >= 0 )
          {
            v65 = *((_QWORD *)v63 + 48);
            if ( (!v65 || !*(_BYTE *)(v65 + 16))
              && (*(_DWORD *)(v64 + 24) & 0x2000000) == 0
              && (*(_BYTE *)(*((_QWORD *)v63 + 17) + 8LL) & 0x20) == 0 )
            {
              *((_BYTE *)*a15 + 5) = 1;
              v19 = v74;
              goto LABEL_64;
            }
          }
          goto LABEL_126;
        }
      }
      v60 = 0;
      goto LABEL_127;
    }
    v27 = RefsWriteCheck((struct _IRP_CONTEXT *)a1, a6, a1[9]);
    v20 = 1;
    if ( v27 || (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) == 0 )
      goto LABEL_12;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v19 = -1073741790;
    }
    else
    {
      v19 = -1073741790;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 186, &WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "Create.c", 0x3DA1u);
  }
  return v19;
}

```

## disassembly

```asm
0x140308440  mov     [rsp+arg_18], r9
0x140308445  mov     [rsp+arg_10], r8
0x14030844a  mov     [rsp+arg_8], rdx
0x14030844f  mov     [rsp+arg_0], rcx
0x140308454  push    rbx
0x140308455  push    rsi
0x140308456  push    rdi
0x140308457  push    r12
0x140308459  push    r13
0x14030845b  push    r14
0x14030845d  push    r15
0x14030845f  sub     rsp, 0B0h
0x140308466  mov     r13, r9
0x140308469  mov     rdi, rdx
0x14030846c  mov     r10, rcx
0x14030846f  xor     ebx, ebx
0x140308471  mov     [rsp+0E8h+var_A0], ebx
0x140308475  mov     [rsp+0E8h+var_A8], bl
0x140308479  xor     r12b, r12b
0x14030847c  mov     rax, [rdx+8]
0x140308480  mov     rdx, [rax+8]
0x140308484  mov     r11d, [rdx+14h]
0x140308488  mov     [rsp+0E8h+var_98], r11d
0x14030848d  mov     r14, [rsp+0E8h+arg_70]
0x140308495  mov     rdx, [r14]
0x140308498  movzx   esi, [rsp+0E8h+arg_40]
0x1403084a0  mov     r15, [rsp+0E8h+arg_28]
0x1403084a8  test    rdx, rdx
0x1403084ab  jnz     short loc_1403084DD
0x1403084ad  mov     [rsp+0E8h+PostIrpRoutine], rdx
0x1403084b2  mov     dword ptr [rsp+0E8h+CompletionRoutine], edx
0x1403084b6  mov     r9, [rsp+0E8h+arg_38]
0x1403084be  movzx   r8d, si
0x1403084c2  mov     rdx, r15
0x1403084c5  call    ?RefsCreateScb@@YAPEAU_SCB@@PEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@PEBU_UNICODE_STRING@@W4REFS_CREATE_SCB_INFLAGS@@PEAE@Z; RefsCreateScb(_IRP_CONTEXT *,_FCB *,_REFS_ATTRIBUTE_TYPE_CODE,_UNICODE_STRING const *,REFS_CREATE_SCB_INFLAGS,uchar *)
0x1403084ca  mov     rdx, rax
0x1403084cd  mov     [r14], rax
0x1403084d0  mov     r11d, [rsp+0E8h+var_98]
0x1403084d5  mov     r10, [rsp+0E8h+arg_0]
0x1403084dd  mov     r8d, [rdx+98h]
0x1403084e4  mov     eax, r8d
0x1403084e7  and     eax, 2
0x1403084ea  jnz     loc_140308F3D
0x1403084f0  cmp     [rdx+158h], eax
0x1403084f6  jnz     loc_140308FAD
0x1403084fc  cmp     [rsp+0E8h+arg_68], 0
0x140308505  jnz     loc_140308982
0x14030850b  test    dword ptr [rdi+10h], 100000h
0x140308512  jnz     loc_14030902D
0x140308518  lea     rbx, [rdi+1Ah]
0x14030851c  mov     ecx, [rsp+0E8h+arg_48]
0x140308523  cmp     ecx, 2
0x140308526  jnz     loc_140308B39
0x14030852c  test    r11d, 10027h
0x140308533  setnz   cl
0x140308536  mov     r8d, 1
0x14030853c  movzx   eax, word ptr [rbx]
0x14030853f  bt      ax, r8w
0x140308544  setnb   al
0x140308547  test    al, cl
0x140308549  jnz     loc_140308D3B
0x14030854f  test    byte ptr [rbx], 1
0x140308552  jz      loc_14030935C
0x140308558  xor     al, al
0x14030855a  test    r12b, r12b
0x14030855d  jnz     loc_1403093BF
0x140308563  xor     edx, edx
0x140308565  mov     r9, [r14]
0x140308568  mov     rax, [rsp+0E8h+arg_20]
0x140308570  mov     ecx, [rax+90h]
0x140308576  movzx   r12d, [rsp+0E8h+arg_50]
0x14030857f  test    cl, 40h
0x140308582  jnz     loc_140308CD8
0x140308588  cmp     r12b, 4
0x14030858c  jnz     loc_1403093D1
0x140308592  mov     eax, 2
0x140308597  mov     r8, [rdi+30h]
0x14030859b  movzx   r10d, word ptr [rbx]
0x14030859f  mov     [rsp+0E8h+var_70], edx
0x1403085a3  mov     [rsp+0E8h+var_78], r10d
0x1403085a8  mov     r11d, [rsp+0E8h+var_98]
0x1403085ad  mov     [rsp+0E8h+var_80], r11d
0x1403085b2  xor     ecx, ecx
0x1403085b4  mov     [rsp+0E8h+var_50], rcx
0x1403085bc  test    eax, eax
0x1403085be  jnz     loc_140308CEC
0x1403085c4  mov     ebx, 0A0h
0x1403085c9  test    r13, r13
0x1403085cc  jz      short loc_1403085FD
0x1403085ce  lea     rcx, [r13+6Ch]
0x1403085d2  mov     [rsp+0E8h+var_50], rcx
0x1403085da  mov     r13d, 80h
0x1403085e0  cmp     word ptr [r9+0E0h], 0
0x1403085e9  jz      loc_140308C41
0x1403085ef  cmp     [r9+0D8h], bx
0x1403085f7  jnz     loc_14030940C
0x1403085fd  add     r9, 0BCh
0x140308604  mov     dword ptr [rsp+0E8h+PostIrpRoutine], edx
0x140308608  mov     [rsp+0E8h+CompletionRoutine], rcx
0x14030860d  mov     edx, r10d
0x140308610  mov     ecx, r11d
0x140308613  call    cs:__imp_IoSetLinkShareAccess
0x14030861a  nop     dword ptr [rax+rax+00h]
0x14030861f  mov     edx, 0A0h
0x140308624  mov     [rsp+0E8h+var_A8], 1
0x140308629  mov     rax, [rdi+30h]
0x14030862d  cmp     byte ptr [rax+4Bh], 0
0x140308631  jnz     loc_140309418
0x140308637  mov     rbx, [rdi+30h]
0x14030863b  mov     [rsp+0E8h+var_60], rbx
0x140308643  mov     r13d, [rsp+0E8h+arg_60]
0x14030864b  cmp     si, dx
0x14030864e  jnz     loc_14030955A
0x140308654  mov     cl, 1
0x140308656  mov     rax, [r14]
0x140308659  mov     [rsp+0E8h+var_48], rax
0x140308661  mov     rax, [r15+8]
0x140308665  test    cl, cl
0x140308667  jz      loc_140308BE8
0x14030866d  bt      rax, 0Ah
0x140308672  jb      short loc_14030868C
0x140308674  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x14030867b  call    cs:__imp_ExAllocateFromLookasideListEx
0x140308682  nop     dword ptr [rax+rax+00h]
0x140308687  mov     rsi, rax
0x14030868a  jmp     short loc_140308699
0x14030868c  lea     rsi, [r15+320h]
0x140308693  cmp     word ptr [rsi], 0
0x140308697  jnz     short loc_140308674
0x140308699  xor     edx, edx; Val
0x14030869b  mov     r8d, 1E8h; Size
0x1403086a1  mov     rcx, rsi; void *
0x1403086a4  call    memset
0x1403086a9  mov     dword ptr [rsi], 1E80808h
0x1403086af  mov     [rsi+4], r13d
0x1403086b3  mov     rcx, [r15+50h]; this
0x1403086b7  call    ?IsSystemVolume@_VCB@@QEBA_NXZ; _VCB::IsSystemVolume(void)
0x1403086bc  test    al, al
0x1403086be  jnz     short loc_14030871A
0x1403086c0  movups  xmm0, xmmword ptr [rbx+58h]
0x1403086c4  movups  xmmword ptr [rsi+10h], xmm0
0x1403086c8  movzx   eax, [rsp+0E8h+arg_30]
0x1403086d0  mov     [rsi+20h], ax
0x1403086d4  mov     [rsi+80h], rbx
0x1403086db  mov     rbx, [r15+58h]
0x1403086df  call    cs:__imp_KeEnterGuardedRegion
0x1403086e6  nop     dword ptr [rax+rax+00h]
0x1403086eb  lea     rcx, [rbx+8]; FastMutex
0x1403086ef  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1403086f6  nop     dword ptr [rax+rax+00h]
0x1403086fb  mov     rcx, [rsp+0E8h+var_48]
0x140308703  add     rcx, 108h
0x14030870a  mov     rdx, [rcx+8]
0x14030870e  cmp     [rdx], rcx
0x140308711  jz      short loc_140308765
0x140308713  mov     ecx, 3
0x140308718  int     29h; Win8: RtlFailFast(ecx)
0x14030871a  mov     [rsp+0E8h+var_90], 0
0x140308723  mov     ecx, cs:Feature_ReFS_Fake_TxF__private_featureState
0x140308729  mov     dword ptr [rsp+0E8h+var_90], ecx
0x14030872d  test    cl, 10h
0x140308730  jz      loc_140309595
0x140308736  mov     rcx, rbx; FileObject
0x140308739  call    cs:__imp_IoGetTransactionParameterBlock
0x140308740  nop     dword ptr [rax+rax+00h]
0x140308745  test    rax, rax
0x140308748  jz      loc_1403086C0
0x14030874e  cmp     qword ptr [rax+8], 0
0x140308753  jz      loc_1403086C0
0x140308759  or      dword ptr [rsi+8], 80000000h
0x140308760  jmp     loc_1403086C0
0x140308765  lea     rax, [rsi+28h]
0x140308769  mov     [rax], rcx
0x14030876c  mov     [rax+8], rdx
0x140308770  mov     [rdx], rax
0x140308773  mov     [rcx+8], rax
0x140308777  mov     rbx, [rsp+0E8h+arg_18]
0x14030877f  test    rbx, rbx
0x140308782  jz      short loc_1403087AF
0x140308784  mov     rcx, rbx
0x140308787  call    ?LcbChildCcbsWritable@_LCB@@QEAAAEAU?$ListHead@U_CCB@@$0DI@@@XZ; _LCB::LcbChildCcbsWritable(void)
0x14030878c  mov     rdx, [rax+8]
0x140308790  cmp     [rdx], rax
0x140308793  jnz     loc_140308713
0x140308799  lea     rcx, [rsi+38h]
0x14030879d  mov     [rcx], rax
0x1403087a0  mov     [rcx+8], rdx
0x1403087a4  mov     [rdx], rcx
0x1403087a7  mov     [rax+8], rcx
0x1403087ab  mov     [rsi+48h], rbx
0x1403087af  mov     rcx, [r15+58h]
0x1403087b3  add     rcx, 8; FastMutex
0x1403087b7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1403087be  nop     dword ptr [rax+rax+00h]
0x1403087c3  call    cs:__imp_KeLeaveGuardedRegion
0x1403087ca  nop     dword ptr [rax+rax+00h]
0x1403087cf  mov     r11, [rsp+0E8h+arg_78]
0x1403087d7  mov     [r11], rsi
0x1403087da  mov     [rsp+0E8h+var_A8], 0
0x1403087df  mov     rax, [rdi+30h]
0x1403087e3  movzx   ecx, byte ptr [rax+4Bh]
0x1403087e7  movzx   eax, byte ptr [rax+4Ch]
0x1403087eb  or      al, cl
0x1403087ed  setz    r8b; unsigned __int8
0x1403087f1  movzx   edx, byte ptr [r15+8]
0x1403087f6  shr     dl, 2
0x1403087f9  and     dl, 1; unsigned __int8
0x1403087fc  mov     rcx, [r14]; struct _SCB *
0x1403087ff  call    ?RefsIncrementCloseCounts@@YAXAEAU_SCB@@EE@Z; RefsIncrementCloseCounts(_SCB &,uchar,uchar)
0x140308804  mov     r8, [rdi+30h]
0x140308808  mov     r8d, [r8+50h]
0x14030880c  shr     r8d, 3
0x140308810  and     r8d, 1; unsigned int
0x140308814  mov     rdx, rbx; struct _LCB *
0x140308817  mov     rcx, [r14]; struct _SCB *
0x14030881a  call    ?RefsIncrementCleanupCounts@@YAXAEAU_SCB@@PEAU_LCB@@K@Z; RefsIncrementCleanupCounts(_SCB &,_LCB *,ulong)
0x14030881f  mov     esi, 80h
0x140308824  bt      r13d, 11h
0x140308829  jb      loc_1403095EC
0x14030882f  mov     r9, [r11]
0x140308832  mov     rdx, [r14]
0x140308835  mov     r8, [rdi+30h]
0x140308839  mov     [r8+18h], rdx
0x14030883d  mov     [r8+20h], r9
0x140308841  mov     rax, [rdx+90h]
0x140308848  mov     rcx, [rax+0D0h]
0x14030884f  mov     [r8+10h], rcx
0x140308853  xor     r10d, r10d
0x140308856  mov     [r8+28h], r10
0x14030885a  cmp     r12b, 4
0x14030885e  jz      loc_1403089ED
0x140308864  test    r9, r9
0x140308867  jz      short loc_14030886D
0x140308869  mov     [r9+50h], r12b
0x14030886d  cmp     r12b, 3
0x140308871  jnz     loc_1403089D9
0x140308877  mov     rax, [rdx+88h]
0x14030887e  mov     ecx, [rax+8]
0x140308881  bt      rcx, 0Dh
0x140308886  jb      loc_1403095FA
0x14030888c  test    dword ptr [rdx+12Ch], 100h
0x140308896  jnz     loc_14030960B
0x14030889c  cmp     [rsp+0E8h+arg_58], r10d
0x1403088a4  jnz     short loc_1403088BE
0x1403088a6  test    byte ptr [rsp+0E8h+var_98], 7
0x1403088ab  jz      short loc_1403088BE
0x1403088ad  mov     rcx, [r14]
0x1403088b0  mov     eax, [rcx+98h]
0x1403088b6  test    al, 20h
0x1403088b8  jnz     loc_1403089FE
0x1403088be  mov     ebx, 0B0h
0x1403088c3  mov     r13, [rsp+0E8h+arg_0]
0x1403088cb  mov     r9, [r14]
0x1403088ce  movzx   ecx, word ptr [r9+0D8h]
0x1403088d6  cmp     cx, si
0x1403088d9  jz      loc_1403089B3
0x1403088df  cmp     cx, bx
0x1403088e2  jz      loc_1403089B3
0x1403088e8  mov     r12d, 805h
0x1403088ee  mov     ebx, 0A0h
0x1403088f3  cmp     cx, bx
0x1403088f6  jnz     loc_140308DB2
0x1403088fc  cmp     word ptr [r9+0E0h], 8
0x140308905  jnz     loc_140308DB2
0x14030890b  mov     rax, [r9+0E8h]
0x140308912  mov     rcx, cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Buffer; _UNICODE_STRING const RefsFileNameIndex ...
0x140308919  mov     rdx, [rax]
0x14030891c  cmp     rdx, [rcx]
0x14030891f  jnz     loc_140308DB2
0x140308925  mov     ecx, 803h
0x14030892a  movzx   eax, word ptr [r9]
0x14030892e  sub     ax, cx
0x140308931  cmp     ax, 1
0x140308935  ja      loc_140308DB2
0x14030893b  lea     rcx, [r9+58h]; Oplock
0x14030893f  mov     [rsp+0E8h+PostIrpRoutine], r10; PostIrpRoutine
0x140308944  mov     [rsp+0E8h+CompletionRoutine], r10; CompletionRoutine
0x140308949  xor     r9d, r9d; Context
0x14030894c  mov     r8d, 2; Flags
0x140308952  mov     rdx, [r13+48h]; Irp
0x140308956  call    cs:__imp_FsRtlCheckOplockEx
0x14030895d  nop     dword ptr [rax+rax+00h]
0x140308962  mov     ebx, eax
0x140308964  mov     [rsp+0E8h+var_A4], eax
0x140308968  test    dword ptr [rdi+10h], 10000h
0x14030896f  jnz     loc_140309645
0x140308975  test    dword ptr [rdi+10h], 100000h
0x14030897c  jnz     loc_140309689
0x140308982  test    dword ptr [r15+98h], 100h
0x14030898d  jz      loc_1403096AB
0x140308993  mov     rax, [r14]
0x140308996  or      dword ptr [rax+12Ch], 100h
0x1403089a0  mov     rcx, [rdi+30h]
0x1403089a4  mov     eax, [rcx+50h]
0x1403089a7  bts     eax, 0Fh
0x1403089ab  mov     [rcx+50h], eax
0x1403089ae  jmp     loc_1403096AB
0x1403089b3  mov     r12d, 805h
0x1403089b9  cmp     [r9], r12w
0x1403089bd  jnz     loc_1403088EE
  ... truncated ...
```
