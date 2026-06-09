# NtfsDeleteScb

- ea: `0x140129550`
- end: `0x140129ff1`
- name: `NtfsDeleteScb`
- size: `2721`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cf580`
- `0x1400e9dc0`
- `0x140128a10`
- `0x140128da0`
- `0x14012a140`
- `0x140194cb8`
- `0x1401ff4b0`

## callees

- `0x14000ea70`
- `0x1400132a8`
- `0x140025c10`
- `0x140027f70`
- `0x140028680`
- `0x14004a4ac`
- `0x140129550`
- `0x14012a000`
- `0x14012bbd0`
- `0x140140b00`
- `0x1401db1b4`
- `0x1401e3280`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140129593`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129967`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140129967`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e3c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e52`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e3c`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140129e52`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1401296ca`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x1401296ca`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a9a`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140129a9a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14012961e`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14012961e`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140129643`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140129643`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1401296b2`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x1401296b2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140129a49`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140129a49`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012986c`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14012986c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140129906`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140129906`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140129a02`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401299ef`
- `ntoskrnl!ExReleasePushLockEx` at `0x140129a02`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012980d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d7a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129729`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14012980d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140129d7a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129bf6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140129bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401297bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129b0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401297bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129a76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129b0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129f16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129fe0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129b4b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140129b4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ef2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140129ef2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140129df0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129aae`
- `ntoskrnl!ExAcquireFastMutex` at `0x140129aae`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129adb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140129adb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d94`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140129d94`

## pseudocode

```c
void __fastcall NtfsDeleteScb(__int64 a1, PFSRTL_ADVANCED_FCB_HEADER *a2)
{
  PFSRTL_ADVANCED_FCB_HEADER v4; // rcx
  __int64 p_FileContextSupportPointer; // rax
  __int64 v6; // r8
  _QWORD *v7; // rdx
  PERESOURCE Resource; // rsi
  struct _ERESOURCE *SpinLock; // r14
  CSHORT NodeTypeCode; // bp
  LARGE_INTEGER AllocationSize; // rcx
  LARGE_MCB *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  FILE_LOCK *v15; // rcx
  PERESOURCE v16; // rcx
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  struct _LIST_ENTRY **FastMutex; // rdx
  LARGE_INTEGER v21; // rcx
  _DWORD *v22; // rdx
  __int64 v23; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v24; // rsi
  int PushLock; // eax
  __int64 **v26; // r14
  PFAST_MUTEX v27; // rcx
  PFSRTL_ADVANCED_FCB_HEADER v28; // rdx
  CSHORT v29; // cx
  _WORD *v30; // r14
  LARGE_INTEGER *p_AllocationSize; // r15
  _QWORD *QuadPart; // rdx
  _WORD *v33; // r12
  _WORD *v34; // r13
  _QWORD *v35; // rax
  __int64 v36; // r15
  __int64 v37; // rax
  int v38; // edx
  __int64 v39; // r8
  unsigned __int64 v40; // rax
  _QWORD *v41; // r9
  __int64 v42; // r8
  _QWORD *v43; // rcx
  _QWORD *v44; // r12
  unsigned int v45; // edx
  int v46; // eax
  __int64 v47; // r8
  void *v48; // rcx
  PNOTIFY_SYNC *p_Blink; // rcx
  OWNER_ENTRY *i; // rcx
  PERESOURCE PagingIoResource; // rax
  __int64 v52; // rdi
  PERESOURCE v53; // rax
  POWNER_ENTRY OwnerTable; // rcx
  PERESOURCE v55; // rdx
  signed __int64 v56; // r8
  signed __int64 v57; // rax
  bool v58; // zf
  __int64 v59; // rtt
  signed __int64 SharedWaiters; // rax
  PVOID v61; // rtt
  __int64 v62; // r13
  LARGE_INTEGER *v63; // rax
  __int64 *v64; // rdi
  __int64 v65; // rax
  __int64 **v66; // rcx
  void *v67; // rcx
  void *v68; // rcx
  ULONG *v69; // rdx
  ULONG *p_ActiveEntries; // rax
  ULONG *v71; // rdx
  __int64 v72; // r8
  struct _LIST_ENTRY *Flink; // rdx
  __int64 v74; // r8
  char *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rcx
  _QWORD *v78; // [rsp+40h] [rbp-58h]
  _DWORD *v79; // [rsp+48h] [rbp-50h]
  __int64 v80; // [rsp+58h] [rbp-40h]
  _QWORD *v81; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v82; // [rsp+B0h] [rbp+18h]
  __int64 v83; // [rsp+B8h] [rbp+20h]

  v4 = *a2;
  p_FileContextSupportPointer = (__int64)&(*a2)[1].FileContextSupportPointer;
  v6 = *(_QWORD *)p_FileContextSupportPointer;
  if ( *(_QWORD *)(*(_QWORD *)p_FileContextSupportPointer + 8LL) != p_FileContextSupportPointer )
    goto LABEL_83;
  v7 = *(_QWORD **)&(*a2)[2].NodeTypeCode;
  if ( *v7 != p_FileContextSupportPointer )
    goto LABEL_83;
  Resource = v4[2].Resource;
  SpinLock = (struct _ERESOURCE *)Resource->SpinLock;
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *(_QWORD *)&(*a2)[2].NodeTypeCode = MmBadPointer;
  (*a2)[1].FileContextSupportPointer = *(PVOID **)&(*a2)[2].NodeTypeCode;
  NodeTypeCode = (*a2)->NodeTypeCode;
  if ( LODWORD((*a2)[2].FileContextSupportPointer) == 176 && (Resource[1].NumberOfSharedWaiters & 0x10000000) != 0 )
  {
    v69 = 0;
    p_ActiveEntries = &Resource->ActiveEntries;
    while ( 1 )
    {
      v71 = v69 ? (ULONG *)*((_QWORD *)v69 + 21) : *(ULONG **)p_ActiveEntries;
      if ( v71 == p_ActiveEntries )
        break;
      v69 = v71 - 42;
      if ( !v69 )
        break;
      if ( v69[64] == 160 )
      {
        v72 = *((_QWORD *)v69 + 74);
        *(_OWORD *)(v69 + 150) = 0;
        *(_OWORD *)(v69 + 154) = 0;
        *((_QWORD *)v69 + 79) = 0;
        if ( v72 )
        {
          v77 = 712;
          if ( *(_QWORD *)(*(_QWORD *)(v72 + 192) + 48LL) != v72 )
            v77 = 742;
          *(_BYTE *)(v77 + v72) = 0;
        }
        *((_BYTE *)v69 + 742) = 0;
        break;
      }
    }
  }
  AllocationSize = (*a2)[3].AllocationSize;
  if ( AllocationSize.QuadPart && *(_DWORD *)(AllocationSize.QuadPart + 4) )
  {
    ExAcquireResourceSharedLite(SpinLock + 8, 1u);
    Flink = SpinLock[10].SystemResourcesList.Flink;
    v74 = *(unsigned int *)((*a2)[3].AllocationSize.QuadPart + 4);
    if ( (BYTE6(Flink->Flink) & 1) != 0 )
      v75 = (char *)&Flink[1].Blink + (unsigned int)LOWORD(Flink->Flink) * ((_DWORD)v74 - 1);
    else
      v75 = (char *)Flink + v74;
    *(_QWORD *)(*((_QWORD *)v75 + 4) + 24LL) = 0;
    if ( (*a2)[3].Resource )
      *(_BYTE *)(*((_QWORD *)v75 + 4) + 20LL) = 1;
    (*a2)[3].Resource = 0;
    ExReleaseResourceLite(SpinLock + 8);
  }
  NtfsUninitializeNtfsMcb(&(*a2)[4].FastMutex);
  v12 = (LARGE_MCB *)*a2;
  if ( NodeTypeCode == 1798 )
  {
    FsRtlUninitializeLargeMcb(v12 + 20);
    FsRtlUninitializeLargeMcb((PLARGE_MCB)&(*a2)[7].FilterContexts);
  }
  else
  {
    FsRtlUninitializeOplock(&v12[2].BaseMcb.Mapping);
    if ( NodeTypeCode == 1797 )
    {
      v15 = (FILE_LOCK *)(*a2)[6].FilterContexts.Flink;
      if ( v15 )
        FsRtlFreeFileLock(v15);
      v16 = (*a2)[7].Resource;
      if ( v16 )
      {
        ExFreePoolWithTag(v16, 0);
        (*a2)[7].Resource = 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v30 = *a2;
        p_AllocationSize = &(*a2)[7].AllocationSize;
        QuadPart = (_QWORD *)p_AllocationSize->QuadPart;
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart == p_AllocationSize )
          break;
        v81 = QuadPart - 1;
        NtfsFullDeleteLcb(0, QuadPart[2], &v81);
      }
      if ( *((_QWORD *)v30 + 83) )
      {
        v33 = v30 + 80;
        v34 = v30 + 60;
        FsRtlAcquireHeaderMutex(v30 + 60, v30 + 80);
        if ( (LARGE_INTEGER *)p_AllocationSize->QuadPart != p_AllocationSize )
        {
          v62 = p_AllocationSize->QuadPart - 8;
          do
          {
            if ( (*(_DWORD *)(v62 + 4) & 0x20) != 0 )
            {
              NtfsRemoveHashEntry(
                a1,
                *(_QWORD *)(*(_QWORD *)(v62 + 48) + 96LL) + 4968LL,
                *(unsigned int *)(v62 + 184),
                v62);
              *(_DWORD *)(v62 + 184) = 0;
              ClearFlagInterlocked(v62 + 4, 32);
            }
            v63 = *(LARGE_INTEGER **)(v62 + 8);
            v62 = (__int64)&v63[-1];
          }
          while ( v63 != p_AllocationSize );
          v34 = v30 + 60;
        }
        if ( *v30 != 1796 )
        {
          v35 = (_QWORD *)(*((_QWORD *)v30 + 23) + 48LL);
          if ( (_QWORD *)*v35 != v35 )
          {
            v36 = *v35 - 56LL;
            do
            {
              if ( (*(_DWORD *)(v36 + 4) & 0x20) != 0 )
              {
                v37 = *(_QWORD *)(v36 + 48);
                v38 = *(_DWORD *)(v36 + 184);
                LODWORD(v81) = v38;
                v39 = *(_QWORD *)(v37 + 96) + 4968LL;
                v79 = (_DWORD *)v39;
                if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x80000000LL) != 0 )
                {
                  McTemplateU0pdpw_EtwWriteTransfer(
                    *(unsigned __int16 *)(v36 + 72) >> 1,
                    v38,
                    v39,
                    v38,
                    v36,
                    *(_WORD *)(v36 + 72) >> 1,
                    *(_QWORD *)(v36 + 80));
                  v39 = (__int64)v79;
                }
                v80 = v39 + 16;
                ExAcquirePushLockSharedEx(v39 + 16, 0);
                v40 = (unsigned int)v81 & (*v79 - 1);
                if ( (unsigned int)v40 < v79[1] )
                  v40 = (unsigned int)v81 & (2 * *v79 - 1);
                v83 = 16 * (v40 & 0x3FF);
                v78 = &v79[2 * (v40 >> 10) + 6];
                ExAcquirePushLockExclusiveEx(*v78 + 8LL + v83, 0);
                v41 = v78;
                v42 = v83;
                v43 = *(_QWORD **)(v83 + *v78);
                if ( v43 )
                {
                  v44 = (_QWORD *)(v83 + *v78);
                  v45 = 0;
                  v46 = (int)v81;
                  v82 = 0;
                  do
                  {
                    if ( *((_DWORD *)v43 + 4) == v46 && v43[1] == v36 )
                    {
                      *v44 = *v43;
                      ExFreePoolWithTag(v43, 0);
                      v46 = (int)v81;
                      v45 = v82;
                    }
                    else
                    {
                      ++v45;
                      v44 = v43;
                      v82 = v45;
                    }
                    v43 = (_QWORD *)*v44;
                  }
                  while ( *v44 );
                  v33 = v30 + 80;
                  if ( v45 <= 5 || v79[2] )
                  {
                    v41 = v78;
                    v42 = v83;
                  }
                  else
                  {
                    v42 = v83;
                    v41 = v78;
                    if ( *v79 < 0x8000u )
                      v79[2] = 1;
                  }
                }
                ExReleasePushLockEx(v42 + 8 + *v41, 0);
                ExReleasePushLockEx(v80, 0);
                *(_DWORD *)(v36 + 184) = 0;
                if ( (*(_DWORD *)(v36 + 4) & 0x20) != 0 )
                  _InterlockedAnd((volatile signed __int32 *)(v36 + 4), 0xFFFFFFDF);
              }
              v47 = *(_QWORD *)(v36 + 56);
              v36 = v47 - 56;
            }
            while ( v47 != *((_QWORD *)v30 + 23) + 48LL );
          }
        }
        FsRtlReleaseHeaderMutex(v34, v33);
        v48 = (void *)*((_QWORD *)v30 + 83);
        *((_QWORD *)v30 + 83) = 0;
        *((_DWORD *)v30 + 164) = 0;
        *((_DWORD *)v30 + 168) = 0;
        ExFreePoolWithTag(v48, 0);
      }
      p_Blink = (PNOTIFY_SYNC *)&(*a2)[8].FilterContexts.Blink;
      if ( *p_Blink )
        FsRtlNotifyUninitializeSync(p_Blink);
      ExAcquireFastMutex((PFAST_MUTEX)&Resource[1].SystemResourcesList.Flink->Blink);
      for ( i = (OWNER_ENTRY *)Resource->OwnerEntry.OwnerThread;
            i != &Resource->OwnerEntry;
            i = (OWNER_ENTRY *)i->OwnerThread )
      {
        i[5].OwnerThread = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)&Resource[1].SystemResourcesList.Flink->Blink);
    }
  }
  NtfsDeleteEncryptionContext(*a2, v13, v14);
  v17 = (*a2)[5].FilterContexts.Flink;
  if ( v17 )
    v17[5].Flink = 0;
  v18 = NtfsAddStructToRollbackList(a1, 1830, *a2, 0);
  if ( v18 )
    NtfsProcessRollbackStruct(a1, v18, 16);
  v19 = *(_QWORD *)(a1 + 144);
  if ( a1 != v19 )
  {
    v76 = NtfsAddStructToRollbackList(v19, 1830, *a2, 0);
    if ( v76 )
      NtfsProcessRollbackStruct(*(_QWORD *)(a1 + 144), v76, 16);
  }
  if ( ((*a2)->Flags2 & 2) != 0 )
    FsRtlTeardownPerStreamContexts(*a2);
  if ( (*a2)[1].Resource )
    ExCleanupAutoExpandPushLock();
  FastMutex = (struct _LIST_ENTRY **)(*a2)->FastMutex;
  if ( FastMutex != &(*a2)[2].Resource[1].SystemResourcesList.Flink->Blink && FastMutex )
    ExFreeToLookasideListEx(&NtfsFastMutexNonpagedLookasideList, FastMutex);
  v21 = (*a2)[3].AllocationSize;
  if ( v21.QuadPart )
  {
    FsLibUninitializeRangeLock(v21.QuadPart + 48);
    v22 = (_DWORD *)(*a2)[3].AllocationSize.QuadPart;
    if ( (v22[17] & 1) != 0 )
      *(_WORD *)v22 = 0;
    else
      ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v22);
  }
  NtfsFreeScbAttributeName((*a2)[3].Resource);
  if ( ((*a2)[5].PushLock & 0x8000) != 0 )
    ExFreePoolWithTag((PVOID)(*a2)[7].PushLock, 0);
  v23 = *(_QWORD *)&(*a2)[6].NodeTypeCode;
  if ( v23 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v23 + 64) + 136LL), 1u);
    TxfDereferenceTxfScb(*(PVOID *)&(*a2)[6].NodeTypeCode);
  }
  v24 = *a2;
  PushLock = (*a2)[5].PushLock;
  if ( (PushLock & 0x10) != 0 || NodeTypeCode == 1798 )
    goto LABEL_121;
  if ( NodeTypeCode != 1797 )
    goto LABEL_37;
  v26 = *(__int64 ***)&v24[7].NodeTypeCode;
  if ( !v26 )
    goto LABEL_37;
  v27 = v24[6].FastMutex;
  if ( v27 && (PushLock & 0x2000) != 0 )
  {
    PagingIoResource = v24[2].PagingIoResource;
    v52 = ((__int64)v27 + PagingIoResource[4].ActiveEntries) >> LOBYTE(PagingIoResource[4].NumberOfSharedWaiters);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)&PagingIoResource[6].SpinLock);
    v24[2].PagingIoResource[3].OwnerTable = (POWNER_ENTRY)((char *)v24[2].PagingIoResource[3].OwnerTable - v52);
    v53 = v24[2].PagingIoResource;
    OwnerTable = v53[3].OwnerTable;
    if ( (__int64)OwnerTable < (signed __int64)v53[79].SpinLock )
      v53[79].SpinLock = (KSPIN_LOCK)OwnerTable;
    v55 = v24[2].PagingIoResource;
    v56 = v55[2].SpinLock
        - *(_QWORD *)&v55[61].ActiveCount
        - ((__int64)v55[3].OwnerTable >> 8)
        - (unsigned __int64)v55[3].OwnerTable;
    if ( v56 <= 0 )
      v56 = 0;
    do
    {
      v57 = *(_QWORD *)&v55[80].ActiveCount;
      if ( v56 >= v57 )
        break;
      v59 = *(_QWORD *)&v55[80].ActiveCount;
      v58 = v59 == _InterlockedCompareExchange64((volatile signed __int64 *)&v55[80].ActiveCount, v56, v57);
      v55 = v24[2].PagingIoResource;
    }
    while ( !v58 );
    do
    {
      SharedWaiters = (signed __int64)v55[80].SharedWaiters;
      if ( v56 <= SharedWaiters )
        break;
      v61 = v55[80].SharedWaiters;
      v58 = v61 == (PVOID)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&v55[80].SharedWaiters,
                            v56,
                            SharedWaiters);
      v55 = v24[2].PagingIoResource;
    }
    while ( !v58 );
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)&v55[6].SpinLock);
  }
  v24[6].FastMutex = 0;
  if ( *v26 )
  {
    while ( 1 )
    {
      v64 = *v26;
      v65 = **v26;
      if ( *(__int64 **)(v65 + 8) != *v26 )
        break;
      v66 = (__int64 **)v64[1];
      if ( *v66 != v64 )
        break;
      *v66 = (__int64 *)v65;
      *(_QWORD *)(v65 + 8) = v66;
      v67 = (void *)v64[3];
      if ( v67 )
        ExFreePoolWithTag(v67, 0);
      v68 = (void *)v64[4];
      if ( v68 )
        ExFreePoolWithTag(v68, 0);
      ExFreePoolWithTag(v64, 0);
      if ( v64 == (__int64 *)v26 )
        goto LABEL_36;
    }
LABEL_83:
    __fastfail(3u);
  }
  ExFreePoolWithTag(v26, 0);
LABEL_36:
  *(_QWORD *)&v24[7].NodeTypeCode = 0;
LABEL_37:
  v28 = *a2;
  if ( *a2 == (PFSRTL_ADVANCED_FCB_HEADER)&(*a2)[2].Resource[3].OwnerEntry.0 )
  {
    v28->NodeTypeCode = 0;
    goto LABEL_40;
  }
  v29 = v28->NodeTypeCode;
  v28->NodeTypeCode = 0;
  if ( v29 != 1797 )
  {
LABEL_121:
    ExFreePoolWithTag(*a2, 0);
    goto LABEL_40;
  }
  ExFreeToLookasideListEx(&NtfsScbDataLookasideList, *a2);
LABEL_40:
  *a2 = 0;
}

```

## disassembly

```asm
0x140129550  push    rbx
0x140129552  push    rbp
0x140129553  push    rsi
0x140129554  push    rdi
0x140129555  push    r12
0x140129557  push    r14
0x140129559  push    r15
0x14012955b  sub     rsp, 60h
0x14012955f  mov     rdi, rcx
0x140129562  mov     rbx, rdx
0x140129565  mov     rcx, [rdx]
0x140129568  lea     rax, [rcx+0A8h]
0x14012956f  mov     r8, [rax]
0x140129572  cmp     [r8+8], rax
0x140129576  jnz     loc_140129C07
0x14012957c  mov     rdx, [rax+8]
0x140129580  cmp     [rdx], rax
0x140129583  jnz     loc_140129C07
0x140129589  mov     rsi, [rcx+0B8h]
0x140129590  xor     r12d, r12d
0x140129593  mov     rax, cs:MmBadPointer
0x14012959a  mov     r14, [rsi+60h]
0x14012959e  mov     [rdx], r8
0x1401295a1  mov     [r8+8], rdx
0x1401295a5  mov     rcx, [rax]
0x1401295a8  mov     rdx, [rbx]
0x1401295ab  mov     [rdx+0B0h], rcx
0x1401295b2  mov     rcx, [rbx]
0x1401295b5  mov     rax, [rcx+0B0h]
0x1401295bc  mov     [rcx+0A8h], rax
0x1401295c3  mov     rax, [rbx]
0x1401295c6  cmp     dword ptr [rax+100h], 0B0h
0x1401295d0  movzx   ebp, word ptr [rax]
0x1401295d3  jz      loc_140129CEA
0x1401295d9  mov     rax, [rbx]
0x1401295dc  mov     rcx, [rax+120h]
0x1401295e3  test    rcx, rcx
0x1401295e6  jz      short loc_1401295F2
0x1401295e8  cmp     [rcx+4], r12d
0x1401295ec  jnz     loc_140129D8B
0x1401295f2  mov     rcx, [rbx]
0x1401295f5  add     rcx, 190h
0x1401295fc  call    NtfsUninitializeNtfsMcb
0x140129601  mov     rcx, [rbx]
0x140129604  mov     r15d, 706h
0x14012960a  mov     r14d, 705h
0x140129610  cmp     bp, r15w
0x140129614  jz      loc_140129E35
0x14012961a  add     rcx, 58h ; 'X'; Oplock
0x14012961e  call    cs:__imp_FsRtlUninitializeOplock
0x140129625  nop     dword ptr [rax+rax+00h]
0x14012962a  cmp     bp, r14w
0x14012962e  jnz     loc_140129830
0x140129634  mov     rax, [rbx]
0x140129637  mov     rcx, [rax+248h]; FileLock
0x14012963e  test    rcx, rcx
0x140129641  jz      short loc_14012964F
0x140129643  call    cs:__imp_FsRtlFreeFileLock
0x14012964a  nop     dword ptr [rax+rax+00h]
0x14012964f  mov     rax, [rbx]
0x140129652  mov     rcx, [rax+270h]; P
0x140129659  test    rcx, rcx
0x14012965c  jnz     loc_140129F14
0x140129662  mov     rcx, [rbx]
0x140129665  call    NtfsDeleteEncryptionContext
0x14012966a  mov     rax, [rbx]
0x14012966d  mov     rcx, [rax+1F0h]
0x140129674  test    rcx, rcx
0x140129677  jz      short loc_14012967D
0x140129679  mov     [rcx+50h], r12
0x14012967d  mov     r8, [rbx]
0x140129680  mov     edx, 726h
0x140129685  xor     r9d, r9d
0x140129688  mov     rcx, rdi
0x14012968b  call    NtfsAddStructToRollbackList
0x140129690  test    rax, rax
0x140129693  jnz     loc_140129F9B
0x140129699  mov     rcx, [rdi+90h]
0x1401296a0  cmp     rdi, rcx
0x1401296a3  jnz     loc_140129E8F
0x1401296a9  mov     rcx, [rbx]; AdvancedHeader
0x1401296ac  test    byte ptr [rcx+6], 2
0x1401296b0  jz      short loc_1401296BE
0x1401296b2  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x1401296b9  nop     dword ptr [rax+rax+00h]
0x1401296be  mov     rax, [rbx]
0x1401296c1  mov     rcx, [rax+60h]
0x1401296c5  test    rcx, rcx
0x1401296c8  jz      short loc_1401296D6
0x1401296ca  call    cs:__imp_ExCleanupAutoExpandPushLock
0x1401296d1  nop     dword ptr [rax+rax+00h]
0x1401296d6  mov     rax, [rbx]
0x1401296d9  mov     rdx, [rax+30h]; Entry
0x1401296dd  mov     rax, [rax+0B8h]
0x1401296e4  mov     rcx, [rax+68h]
0x1401296e8  add     rcx, 8
0x1401296ec  cmp     rdx, rcx
0x1401296ef  jnz     loc_140129D6A
0x1401296f5  mov     rax, [rbx]
0x1401296f8  mov     rcx, [rax+120h]
0x1401296ff  test    rcx, rcx
0x140129702  jz      short loc_140129735
0x140129704  add     rcx, 30h ; '0'
0x140129708  call    FsLibUninitializeRangeLock
0x14012970d  mov     rax, [rbx]
0x140129710  mov     rdx, [rax+120h]; Entry
0x140129717  mov     eax, [rdx+44h]
0x14012971a  test    al, 1
0x14012971c  jnz     loc_140129AF8
0x140129722  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140129729  call    cs:__imp_ExFreeToLookasideListEx
0x140129730  nop     dword ptr [rax+rax+00h]
0x140129735  mov     rcx, [rbx]
0x140129738  mov     rcx, [rcx+110h]
0x14012973f  call    NtfsFreeScbAttributeName
0x140129744  mov     rcx, [rbx]
0x140129747  test    dword ptr [rcx+200h], 8000h
0x140129751  jnz     loc_140129FB1
0x140129757  mov     rax, [rbx]
0x14012975a  mov     rcx, [rax+210h]
0x140129761  test    rcx, rcx
0x140129764  jnz     loc_140129EE5
0x14012976a  mov     rsi, [rbx]
0x14012976d  mov     eax, [rsi+200h]
0x140129773  test    al, 10h
0x140129775  jnz     loc_140129B0A
0x14012977b  cmp     bp, r15w
0x14012977f  jz      loc_140129B0A
0x140129785  cmp     bp, r14w
0x140129789  jnz     short loc_1401297D6
0x14012978b  mov     r14, [rsi+268h]
0x140129792  test    r14, r14
0x140129795  jz      short loc_1401297D0
0x140129797  mov     rcx, [rsi+240h]
0x14012979e  test    rcx, rcx
0x1401297a1  jnz     loc_140129B20
0x1401297a7  mov     [rsi+240h], r12
0x1401297ae  cmp     qword ptr [r14], 0
0x1401297b2  jnz     loc_140129C90
0x1401297b8  xor     edx, edx; Tag
0x1401297ba  mov     rcx, r14; P
0x1401297bd  call    cs:__imp_ExFreePoolWithTag
0x1401297c4  nop     dword ptr [rax+rax+00h]
0x1401297c9  mov     [rsi+268h], r12
0x1401297d0  mov     r14d, 705h
0x1401297d6  mov     rdx, [rbx]
0x1401297d9  mov     rax, [rdx+0B8h]
0x1401297e0  add     rax, 170h
0x1401297e6  cmp     rdx, rax
0x1401297e9  jz      loc_140129B01
0x1401297ef  movzx   ecx, word ptr [rdx]
0x1401297f2  mov     [rdx], r12w
0x1401297f6  mov     rax, [rbx]
0x1401297f9  cmp     cx, r14w
0x1401297fd  jnz     loc_140129E63
0x140129803  mov     rdx, rax; Entry
0x140129806  lea     rcx, NtfsScbDataLookasideList; Lookaside
0x14012980d  call    cs:__imp_ExFreeToLookasideListEx
0x140129814  nop     dword ptr [rax+rax+00h]
0x140129819  mov     [rbx], r12
0x14012981c  add     rsp, 60h
0x140129820  pop     r15
0x140129822  pop     r14
0x140129824  pop     r12
0x140129826  pop     rdi
0x140129827  pop     rsi
0x140129828  pop     rbp
0x140129829  pop     rbx
0x14012982a  retn
0x140129830  mov     r14, [rbx]
0x140129833  lea     r15, [r14+280h]
0x14012983a  mov     rdx, [r15]
0x14012983d  cmp     rdx, r15
0x140129840  jnz     loc_140129C40
0x140129846  cmp     [r14+298h], r12
0x14012984d  jz      loc_140129A8A
0x140129853  mov     [rsp+98h+arg_0], r13
0x14012985b  lea     r12, [r14+0A0h]
0x140129862  lea     r13, [r14+78h]
0x140129866  mov     rdx, r12
0x140129869  mov     rcx, r13
0x14012986c  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140129873  nop     dword ptr [rax+rax+00h]
0x140129878  mov     rax, [r15]
0x14012987b  cmp     rax, r15
0x14012987e  jnz     loc_140129C64
0x140129884  mov     eax, 704h
0x140129889  cmp     [r14], ax
0x14012988d  jz      loc_140129A43
0x140129893  mov     rax, [r14+0B8h]
0x14012989a  add     rax, 30h ; '0'
0x14012989e  mov     r15, [rax]
0x1401298a1  cmp     r15, rax
0x1401298a4  jz      loc_140129A43
0x1401298aa  add     r15, 0FFFFFFFFFFFFFFC8h
0x1401298ae  mov     eax, [r15+4]
0x1401298b2  test    al, 20h
0x1401298b4  jz      loc_140129A27
0x1401298ba  mov     rax, [r15+30h]
0x1401298be  mov     edx, [r15+0B8h]
0x1401298c5  mov     dword ptr [rsp+98h+arg_8], edx
0x1401298cc  mov     r8, [rax+60h]
0x1401298d0  add     r8, 1368h
0x1401298d7  mov     [rsp+98h+var_50], r8
0x1401298dc  test    rdi, rdi
0x1401298df  jz      short loc_1401298EB
0x1401298e1  mov     eax, [rdi+10h]
0x1401298e4  bt      rax, 14h
0x1401298e9  jb      short loc_1401298F8
0x1401298eb  cmp     byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 0
0x1401298f2  jl      loc_140129F70
0x1401298f8  lea     rax, [r8+10h]
0x1401298fc  xor     edx, edx
0x1401298fe  mov     rcx, rax
0x140129901  mov     [rsp+98h+var_40], rax
0x140129906  call    cs:__imp_ExAcquirePushLockSharedEx
0x14012990d  nop     dword ptr [rax+rax+00h]
0x140129912  mov     r8, [rsp+98h+var_50]
0x140129917  mov     ecx, dword ptr [rsp+98h+arg_8]
0x14012991e  mov     edx, [r8]
0x140129921  lea     eax, [rdx-1]
0x140129924  and     eax, ecx
0x140129926  cmp     eax, [r8+4]
0x14012992a  jnb     short loc_140129935
0x14012992c  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x140129933  and     eax, ecx
0x140129935  mov     rcx, rax
0x140129938  add     r8, 18h
0x14012993c  shr     rax, 0Ah
0x140129940  and     ecx, 3FFh
0x140129946  shl     rcx, 4
0x14012994a  xor     edx, edx
0x14012994c  mov     [rsp+98h+arg_18], rcx
0x140129954  lea     rax, [r8+rax*8]
0x140129958  mov     [rsp+98h+var_58], rax
0x14012995d  mov     rax, [rax]
0x140129960  add     rax, 8
0x140129964  add     rcx, rax
0x140129967  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14012996e  nop     dword ptr [rax+rax+00h]
0x140129973  mov     r9, [rsp+98h+var_58]
0x140129978  mov     r8, [rsp+98h+arg_18]
0x140129980  mov     rcx, [r9]
0x140129983  add     rcx, r8
0x140129986  mov     [rsp+98h+var_48], rcx
0x14012998b  mov     rcx, [rcx]; P
0x14012998e  test    rcx, rcx
0x140129991  jz      short loc_1401299E3
0x140129993  mov     r12, [rsp+98h+var_48]
0x140129998  xor     edx, edx
0x14012999a  mov     eax, dword ptr [rsp+98h+arg_8]
0x1401299a1  mov     [rsp+98h+arg_10], edx
0x1401299a8  cmp     [rcx+10h], eax
0x1401299ab  jz      loc_140129C0E
0x1401299b1  inc     edx
0x1401299b3  mov     r12, rcx
0x1401299b6  mov     [rsp+98h+arg_10], edx
0x1401299bd  mov     rcx, [r12]
0x1401299c1  test    rcx, rcx
0x1401299c4  jnz     short loc_1401299A8
0x1401299c6  lea     r12, [r14+0A0h]
0x1401299cd  cmp     edx, 5
0x1401299d0  ja      loc_140129E01
0x1401299d6  mov     r9, [rsp+98h+var_58]
0x1401299db  mov     r8, [rsp+98h+arg_18]
0x1401299e3  mov     rcx, [r9]
0x1401299e6  add     r8, 8
0x1401299ea  add     rcx, r8
0x1401299ed  xor     edx, edx
0x1401299ef  call    cs:__imp_ExReleasePushLockEx
0x1401299f6  nop     dword ptr [rax+rax+00h]
0x1401299fb  mov     rcx, [rsp+98h+var_40]
0x140129a00  xor     edx, edx
0x140129a02  call    cs:__imp_ExReleasePushLockEx
0x140129a09  nop     dword ptr [rax+rax+00h]
0x140129a0e  mov     dword ptr [r15+0B8h], 0
0x140129a19  mov     eax, [r15+4]
0x140129a1d  test    al, 20h
0x140129a1f  jz      short loc_140129A27
0x140129a21  lock and dword ptr [r15+4], 0FFFFFFDFh
0x140129a27  mov     r8, [r15+38h]
0x140129a2b  mov     rax, [r14+0B8h]
0x140129a32  add     rax, 30h ; '0'
0x140129a36  lea     r15, [r8-38h]
0x140129a3a  cmp     r8, rax
0x140129a3d  jnz     loc_1401298AE
0x140129a43  mov     rdx, r12
0x140129a46  mov     rcx, r13
0x140129a49  call    cs:__imp_FsRtlReleaseHeaderMutex
0x140129a50  nop     dword ptr [rax+rax+00h]
0x140129a55  mov     rcx, [r14+298h]; P
0x140129a5c  xor     r12d, r12d
0x140129a5f  xor     edx, edx; Tag
0x140129a61  mov     [r14+298h], r12
0x140129a68  mov     [r14+290h], r12d
0x140129a6f  mov     [r14+2A0h], r12d
0x140129a76  call    cs:__imp_ExFreePoolWithTag
0x140129a7d  nop     dword ptr [rax+rax+00h]
0x140129a82  mov     r13, [rsp+98h+arg_0]
0x140129a8a  mov     rcx, [rbx]
  ... truncated ...
```
