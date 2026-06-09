# RefsDeleteVcb(_IRP_CONTEXT *,_VCB *)

- ea: `0x1403407b0`
- end: `0x140341012`
- name: `?RefsDeleteVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@@Z`
- size: `2146`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _VCB *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400aecd8`

## callees

- `0x140037820`
- `0x140049050`
- `0x140075ae0`
- `0x14007a100`
- `0x140085570`
- `0x1400889f0`
- `0x140089640`
- `0x14008c720`
- `0x1400a79b0`
- `0x1400abb88`
- `0x1400b1590`
- `0x1400cd09c`
- `0x1402fd1a4`
- `0x140315614`
- `0x1403158a0`
- `0x140315bb4`
- `0x14032ca30`
- `0x1403407b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140340f80`
- `ntoskrnl!ObfDereferenceObject` at `0x140340f80`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140340c53`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140340c53`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140340a87`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140340c99`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140340a87`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x140340c99`
- `ntoskrnl!MmFreeMappingAddress` at `0x140340f36`
- `ntoskrnl!MmFreeMappingAddress` at `0x140340f53`
- `ntoskrnl!MmFreeMappingAddress` at `0x140340f36`
- `ntoskrnl!MmFreeMappingAddress` at `0x140340f53`
- `ntoskrnl!ExAcquireFastMutex` at `0x1403407fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x1403407fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x14034082b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14034082b`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140340e06`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140340e06`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140340b4c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140340b4c`
- `ntoskrnl!FsRtlHeatUninit` at `0x1403408b0`
- `ntoskrnl!FsRtlHeatUninit` at `0x1403408b0`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140340d66`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x140340d66`
- `ntoskrnl!ExDeleteFastResource` at `0x140340dec`
- `ntoskrnl!ExDeleteFastResource` at `0x140340f93`
- `ntoskrnl!ExDeleteFastResource` at `0x140340dec`
- `ntoskrnl!ExDeleteFastResource` at `0x140340f93`
- `ntoskrnl!IoDeleteDevice` at `0x140340fef`
- `ntoskrnl!IoDeleteDevice` at `0x140340fef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140340b5b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140340b5b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140340bcb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140340bcb`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140340bd7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140340bd7`
- `ntoskrnl!ExReleaseFastResource` at `0x140340ad5`
- `ntoskrnl!ExReleaseFastResource` at `0x140340ce7`
- `ntoskrnl!ExReleaseFastResource` at `0x140340ad5`
- `ntoskrnl!ExReleaseFastResource` at `0x140340ce7`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140340aa2`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140340cb4`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140340aa2`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x140340cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034081b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340850`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340923`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340947`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034096b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340dba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340eaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340f6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034081b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340850`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403408ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340923`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340947`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034096b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d25`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340dba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340eaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340f6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340fad`

## pseudocode

```c
void __fastcall RefsDeleteVcb(struct _IRP_CONTEXT *a1, struct _VCB *a2)
{
  char *v2; // rbx
  struct _VCB *v3; // rbp
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  SmsCheckpointContext *v11; // r14
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  CmsReferenced *v17; // rcx
  __int64 v18; // rcx
  CmsReferenced *v19; // rcx
  __int64 v20; // rcx
  CmsReferenced *v21; // rcx
  __int64 v22; // rcx
  CmsReferenced *v23; // rcx
  __int64 v24; // rcx
  CmsReferenced *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  struct _FCB *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // r8
  struct _FCB *v32; // rsi
  __int64 v33; // r8
  PFAST_MUTEX *p_FastMutex; // rbp
  __int64 p_OldIrql; // r14
  struct _FAST_MUTEX *v36; // rbx
  _QWORD *v37; // rsi
  _QWORD *v38; // rax
  _QWORD *v39; // rdi
  struct _FCB *v40; // rbx
  __int64 v41; // rcx
  struct _FCB *v42; // rsi
  LARGE_INTEGER *p_FileSize; // rdi
  __int64 v44; // rbx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  void *v48; // rcx
  void *v49; // rcx
  PVOID *v50; // rbx
  USHORT HighestNodeNumber; // ax
  unsigned int v52; // r14d
  unsigned int v53; // r15d
  __int64 v54; // r8
  unsigned int i; // esi
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  __int64 v60; // rax
  void *v61; // rcx
  void *v62; // rcx
  void *v63; // rcx
  void *v64; // rcx
  void *v65; // rcx
  void *v66; // rcx
  void *v67; // rcx
  _OWORD v68[4]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v69; // [rsp+60h] [rbp-48h]
  char v70; // [rsp+B0h] [rbp+8h] BYREF
  struct _VCB *v71; // [rsp+B8h] [rbp+10h]
  struct _FCB *NextFcbTableEntry; // [rsp+C0h] [rbp+18h] BYREF

  v71 = a2;
  v2 = (char *)a2 + 10104;
  v3 = a2;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  if ( *((_QWORD *)a2 + 1263) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)((char *)a2 + 10152));
    FsLibIoFailureResetTable(v2);
    v5 = (void *)_InterlockedExchange64((volatile __int64 *)v2, 0);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    ExReleaseFastMutex((PFAST_MUTEX)(v2 + 48));
  }
  *((_WORD *)v3 + 5124) = 0;
  v6 = (void *)_InterlockedExchange64((volatile __int64 *)v3 + 1280, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  v7 = *((_QWORD *)a1 + 13);
  v8 = v7 + 160;
  if ( (*(_QWORD *)(v7 + 8) & 0x20000000000LL) == 0 )
  {
    MsInitializeFastResourceOwnerEntry(v8);
    *(_QWORD *)(v9 + 8) |= v10;
  }
  v11 = (struct _VCB *)((char *)v3 + 1312);
  MsAcquireFastResourceExclusive((char *)v3 + 1312, v8, *((_BYTE *)a1 + 8) & 1);
  if ( (*((_DWORD *)v3 + 7) & 0x20) != 0 )
    FsRtlHeatUninit((char *)v3 + 6564, (char *)v3 + 6588);
  NtOfsPurgeSecurityCache(v3, 1u);
  *((_BYTE *)v3 + 6561) = 1;
  v12 = (void *)*((_QWORD *)v3 + 788);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  *(_OWORD *)((char *)v3 + 6296) = 0;
  v13 = (void *)*((_QWORD *)v3 + 790);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  *(_OWORD *)((char *)v3 + 6312) = 0;
  v14 = (void *)*((_QWORD *)v3 + 792);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  *(_OWORD *)((char *)v3 + 6328) = 0;
  v15 = (void *)*((_QWORD *)v3 + 794);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  *(_OWORD *)((char *)v3 + 6344) = 0;
  v16 = (void *)*((_QWORD *)v3 + 770);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  *(_OWORD *)((char *)v3 + 6152) = 0;
  v17 = (CmsReferenced *)*((_QWORD *)v3 + 1346);
  if ( v17 )
    CmsReferenced::Release(v17);
  v18 = *((_QWORD *)v3 + 1345);
  if ( v18 )
    MsReleaseTable(v18);
  v19 = (CmsReferenced *)*((_QWORD *)v3 + 1352);
  if ( v19 )
    CmsReferenced::Release(v19);
  v20 = *((_QWORD *)v3 + 1351);
  if ( v20 )
    MsReleaseTable(v20);
  v21 = (CmsReferenced *)*((_QWORD *)v3 + 1358);
  if ( v21 )
    CmsReferenced::Release(v21);
  v22 = *((_QWORD *)v3 + 1357);
  if ( v22 )
    MsReleaseTable(v22);
  v23 = (CmsReferenced *)*((_QWORD *)v3 + 1364);
  if ( v23 )
    CmsReferenced::Release(v23);
  v24 = *((_QWORD *)v3 + 1363);
  if ( v24 )
    MsReleaseTable(v24);
  v25 = (CmsReferenced *)*((_QWORD *)v3 + 1370);
  if ( v25 )
    CmsReferenced::Release(v25);
  v26 = *((_QWORD *)v3 + 1369);
  if ( v26 )
    MsReleaseTable(v26);
  v27 = *((_QWORD *)v3 + 1375);
  if ( v27 )
    MsReleaseTable(v27);
  v28 = *((_QWORD *)v3 + 25);
  if ( v28 )
  {
    v29 = *(struct _FCB **)(v28 + 48);
    RefsAcquireExclusiveFcb(a1, v29, 0, 1);
    RefsDeleteLcb(v30, *((_QWORD *)v3 + 25), 0);
    RefsReleaseFcb(a1, v29);
  }
  NextFcbTableEntry = 0;
  ExInitializeFastOwnerEntry(v68);
  LOBYTE(v31) = 1;
  ExAcquireFastResourceShared((char *)v3 + 624, v68, v31);
  NextFcbTableEntry = RefsGetNextFcbTableEntry(v3, (void **)&NextFcbTableEntry);
  v32 = NextFcbTableEntry;
  ExReleaseFastResource((char *)v3 + 624, v68);
  if ( v32 )
  {
    do
    {
      RefsAcquireExclusiveFcb(a1, v32, 0, 1);
      p_FastMutex = &v32->Header.FastMutex;
      while ( *p_FastMutex != (PFAST_MUTEX)p_FastMutex )
      {
        p_OldIrql = (__int64)&(*p_FastMutex)[-3].OldIrql;
        if ( *p_FastMutex == (PFAST_MUTEX)120 )
          break;
        if ( (unsigned __int16)(*(_WORD *)p_OldIrql - 2051) <= 1u )
        {
          v36 = *(struct _FAST_MUTEX **)(p_OldIrql + 48);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v36);
          _InterlockedIncrement((volatile signed __int32 *)(p_OldIrql + 172));
          v37 = (_QWORD *)(p_OldIrql + 376);
          while ( 1 )
          {
            v38 = (_QWORD *)*v37;
            if ( (_QWORD *)*v37 == v37 )
              break;
            v39 = v38 - 1;
            if ( v38 == (_QWORD *)8 )
              break;
            v40 = (struct _FCB *)v39[6];
            RefsAcquireExclusiveFcb(a1, v40, 0, 1);
            RefsDeleteLcb(v41, v39, 0);
            RefsReleaseFcb(a1, v40);
          }
          ++*(_DWORD *)(p_OldIrql + 172);
          ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(p_OldIrql + 48));
          KeLeaveGuardedRegion();
        }
        RefsDeleteScb(a1, (struct _SCB *)p_OldIrql);
      }
      v42 = NextFcbTableEntry;
      v3 = v71;
      p_FileSize = &NextFcbTableEntry->Header.FileSize;
      while ( (LARGE_INTEGER *)p_FileSize->QuadPart != p_FileSize )
      {
        v44 = p_FileSize->QuadPart - 32;
        if ( p_FileSize->QuadPart == 32 )
          break;
        RefsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v44 + 24) + 136LL), 0, 1);
        LOBYTE(v45) = 1;
        RefsDeleteLcb(v46, v44, v45);
      }
      LOBYTE(v33) = 1;
      ExAcquireFastResourceExclusive((char *)v3 + 624, 0, v33);
      v70 = 0;
      v42->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v70;
      RefsDeleteFcb(a1, v42, (unsigned __int8 *)&NextFcbTableEntry);
      NextFcbTableEntry = 0;
      ExInitializeFastOwnerEntry(v68);
      LOBYTE(v47) = 1;
      ExAcquireFastResourceShared((char *)v3 + 624, v68, v47);
      NextFcbTableEntry = RefsGetNextFcbTableEntry(v3, (void **)&NextFcbTableEntry);
      v32 = NextFcbTableEntry;
      ExReleaseFastResource((char *)v3 + 624, v68);
    }
    while ( v32 );
    v11 = (struct _VCB *)((char *)v3 + 1312);
  }
  *((_QWORD *)v3 + 100) = 0;
  v48 = (void *)*((_QWORD *)v3 + 103);
  if ( v48 )
    ExFreePoolWithTag(v48, 0);
  *((_OWORD *)v3 + 51) = 0;
  v49 = (void *)*((_QWORD *)v3 + 1634);
  if ( v49 )
    ExFreePoolWithTag(v49, 0);
  *(_OWORD *)((char *)v3 + 13064) = 0;
  FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)v3 + 108);
  if ( (*((_DWORD *)v3 + 6) & 0x400) != 0 )
  {
    ExFreePoolWithTag(*((PVOID *)v3 + 26), 0);
    *((_QWORD *)v3 + 26) = 0;
  }
  v50 = (PVOID *)((char *)v3 + 3624);
  if ( (char *)v3 + 3624 != (char *)v3 + 5672 )
  {
    do
    {
      if ( *v50 )
      {
        ExFreePoolWithTag(*v50, 0);
        *v50 = 0;
      }
      ++v50;
    }
    while ( v50 != (PVOID *)((char *)v3 + 5672) );
  }
  RefsReleaseVcb(a1, v3);
  SmsCheckpointContext::~SmsCheckpointContext(v11);
  ExDeleteFastResource((char *)v3 + 6168);
  if ( *((_QWORD *)v3 + 730) )
  {
    HighestNodeNumber = KeQueryHighestNodeNumber();
    v52 = 0;
    v53 = HighestNodeNumber + 1;
    if ( HighestNodeNumber != -1 )
    {
      do
      {
        v54 = *((_QWORD *)v3 + 730);
        if ( *(_QWORD *)(v54 + 16LL * v52 + 8) )
        {
          for ( i = 0; i < *(_DWORD *)(v54 + 16LL * v52); ++i )
          {
            v56 = 48LL * i;
            while ( 1 )
            {
              v54 = *((_QWORD *)v3 + 730);
              v57 = *(_QWORD *)(v54 + 16LL * v52 + 8);
              if ( *(_QWORD *)(v56 + v57 + 32) == v56 + v57 + 32 )
                break;
              v58 = v56 + v57 + 32;
              v59 = *(__int64 **)v58;
              if ( *(_QWORD *)(*(_QWORD *)v58 + 8LL) != v58 || (v60 = *v59, *(__int64 **)(*v59 + 8) != v59) )
                __fastfail(3u);
              *(_QWORD *)v58 = v60;
              *(_QWORD *)(v60 + 8) = v58;
              ExFreePoolWithTag(v59, 0);
            }
          }
          ExFreePoolWithTag(*(PVOID *)(v54 + 16LL * v52 + 8), 0);
        }
        ++v52;
      }
      while ( v52 < v53 );
    }
    ExFreePoolWithTag(*((PVOID *)v3 + 730), 0);
    *((_QWORD *)v3 + 730) = 0;
  }
  v61 = (void *)*((_QWORD *)v3 + 731);
  if ( v61 )
  {
    ExFreePoolWithTag(v61, 0);
    *((_QWORD *)v3 + 731) = 0;
  }
  v62 = (void *)*((_QWORD *)v3 + 101);
  if ( v62 )
  {
    ExFreePoolWithTag(v62, 0);
    *((_QWORD *)v3 + 101) = 0;
  }
  v63 = (void *)*((_QWORD *)v3 + 734);
  if ( v63 )
    MmFreeMappingAddress(v63, 0x62666552u);
  v64 = (void *)*((_QWORD *)v3 + 742);
  if ( v64 )
    MmFreeMappingAddress(v64, 0x62666552u);
  v65 = (void *)*((_QWORD *)v3 + 750);
  if ( v65 )
    ExFreePoolWithTag(v65, 0);
  ObfDereferenceObject(*((PVOID *)v3 + 24));
  ExDeleteFastResource((char *)v3 + 1208);
  v66 = (void *)*((_QWORD *)v3 + 451);
  if ( v66 )
  {
    ExFreePoolWithTag(v66, 0);
    *((_QWORD *)v3 + 451) = 0;
  }
  MsKmeDeleteReservedIoRequestsForVcb(v3);
  MsKmeDeleteReservedIoRunsForVcb(v3);
  v67 = (void *)*((_QWORD *)v3 + 1339);
  if ( v67 )
  {
    operator delete(v67);
    *((_QWORD *)v3 + 1339) = 0;
  }
  IoDeleteDevice((PDEVICE_OBJECT)((char *)v3 - 384));
}

```

## disassembly

```asm
0x1403407b0  mov     [rsp+arg_8], rdx
0x1403407b5  push    rbx
0x1403407b6  push    rbp
0x1403407b7  push    rsi
0x1403407b8  push    rdi
0x1403407b9  push    r13
0x1403407bb  push    r14
0x1403407bd  push    r15
0x1403407bf  sub     rsp, 70h
0x1403407c3  xorps   xmm0, xmm0
0x1403407c6  lea     rbx, [rdx+2778h]
0x1403407cd  xor     eax, eax
0x1403407cf  xor     r13d, r13d
0x1403407d2  mov     rbp, rdx
0x1403407d5  mov     r15, rcx
0x1403407d8  movups  [rsp+0A8h+var_88], xmm0
0x1403407dd  mov     [rsp+0A8h+var_48], rax
0x1403407e2  movups  [rsp+0A8h+var_78], xmm0
0x1403407e7  movups  [rsp+0A8h+var_68], xmm0
0x1403407ec  movups  [rsp+0A8h+var_58], xmm0
0x1403407f1  cmp     [rbx], rax
0x1403407f4  jz      short loc_140340837
0x1403407f6  lea     rcx, [rbx+30h]; FastMutex
0x1403407fa  call    cs:__imp_ExAcquireFastMutex
0x140340801  nop     dword ptr [rax+rax+00h]
0x140340806  mov     rcx, rbx
0x140340809  call    FsLibIoFailureResetTable
0x14034080e  mov     ecx, r13d
0x140340811  xchg    rcx, [rbx]; P
0x140340814  test    rcx, rcx
0x140340817  jz      short loc_140340827
0x140340819  xor     edx, edx; Tag
0x14034081b  call    cs:__imp_ExFreePoolWithTag
0x140340822  nop     dword ptr [rax+rax+00h]
0x140340827  lea     rcx, [rbx+30h]; FastMutex
0x14034082b  call    cs:__imp_ExReleaseFastMutex
0x140340832  nop     dword ptr [rax+rax+00h]
0x140340837  mov     rcx, r13
0x14034083a  mov     [rbp+2808h], r13w
0x140340842  xchg    rcx, [rbp+2800h]; P
0x140340849  test    rcx, rcx
0x14034084c  jz      short loc_14034085C
0x14034084e  xor     edx, edx; Tag
0x140340850  call    cs:__imp_ExFreePoolWithTag
0x140340857  nop     dword ptr [rax+rax+00h]
0x14034085c  mov     rdx, [r15+68h]
0x140340860  mov     r8, 20000000000h
0x14034086a  lea     rcx, [rdx+0A0h]
0x140340871  test    [rdx+8], r8
0x140340875  jnz     short loc_140340880
0x140340877  call    MsInitializeFastResourceOwnerEntry
0x14034087c  or      [rdx+8], r8
0x140340880  movzx   r8d, byte ptr [r15+8]
0x140340885  lea     r14, [rbp+520h]
0x14034088c  mov     rdx, rcx
0x14034088f  and     r8b, 1
0x140340893  mov     rcx, r14
0x140340896  call    MsAcquireFastResourceExclusive
0x14034089b  mov     eax, [rbp+1Ch]
0x14034089e  test    al, 20h
0x1403408a0  jz      short loc_1403408BC
0x1403408a2  lea     rdx, [rbp+19BCh]
0x1403408a9  lea     rcx, [rbp+19A4h]
0x1403408b0  call    cs:__imp_FsRtlHeatUninit
0x1403408b7  nop     dword ptr [rax+rax+00h]
0x1403408bc  mov     dl, 1; unsigned __int8
0x1403408be  mov     rcx, rbp; struct _VCB *
0x1403408c1  call    ?NtOfsPurgeSecurityCache@@YAXPEAU_VCB@@E@Z; NtOfsPurgeSecurityCache(_VCB *,uchar)
0x1403408c6  mov     byte ptr [rbp+19A1h], 1
0x1403408cd  mov     rcx, [rbp+18A0h]; P
0x1403408d4  test    rcx, rcx
0x1403408d7  jz      short loc_1403408E7
0x1403408d9  xor     edx, edx; Tag
0x1403408db  call    cs:__imp_ExFreePoolWithTag
0x1403408e2  nop     dword ptr [rax+rax+00h]
0x1403408e7  xorps   xmm0, xmm0
0x1403408ea  movups  xmmword ptr [rbp+1898h], xmm0
0x1403408f1  mov     rcx, [rbp+18B0h]; P
0x1403408f8  test    rcx, rcx
0x1403408fb  jz      short loc_14034090B
0x1403408fd  xor     edx, edx; Tag
0x1403408ff  call    cs:__imp_ExFreePoolWithTag
0x140340906  nop     dword ptr [rax+rax+00h]
0x14034090b  xorps   xmm0, xmm0
0x14034090e  movups  xmmword ptr [rbp+18A8h], xmm0
0x140340915  mov     rcx, [rbp+18C0h]; P
0x14034091c  test    rcx, rcx
0x14034091f  jz      short loc_14034092F
0x140340921  xor     edx, edx; Tag
0x140340923  call    cs:__imp_ExFreePoolWithTag
0x14034092a  nop     dword ptr [rax+rax+00h]
0x14034092f  xorps   xmm0, xmm0
0x140340932  movups  xmmword ptr [rbp+18B8h], xmm0
0x140340939  mov     rcx, [rbp+18D0h]; P
0x140340940  test    rcx, rcx
0x140340943  jz      short loc_140340953
0x140340945  xor     edx, edx; Tag
0x140340947  call    cs:__imp_ExFreePoolWithTag
0x14034094e  nop     dword ptr [rax+rax+00h]
0x140340953  xorps   xmm0, xmm0
0x140340956  movups  xmmword ptr [rbp+18C8h], xmm0
0x14034095d  mov     rcx, [rbp+1810h]; P
0x140340964  test    rcx, rcx
0x140340967  jz      short loc_140340977
0x140340969  xor     edx, edx; Tag
0x14034096b  call    cs:__imp_ExFreePoolWithTag
0x140340972  nop     dword ptr [rax+rax+00h]
0x140340977  xorps   xmm0, xmm0
0x14034097a  movups  xmmword ptr [rbp+1808h], xmm0
0x140340981  mov     rcx, [rbp+2A10h]; this
0x140340988  test    rcx, rcx
0x14034098b  jz      short loc_140340992
0x14034098d  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x140340992  mov     rcx, [rbp+2A08h]
0x140340999  test    rcx, rcx
0x14034099c  jz      short loc_1403409A3
0x14034099e  call    MsReleaseTable
0x1403409a3  mov     rcx, [rbp+2A40h]; this
0x1403409aa  test    rcx, rcx
0x1403409ad  jz      short loc_1403409B4
0x1403409af  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1403409b4  mov     rcx, [rbp+2A38h]
0x1403409bb  test    rcx, rcx
0x1403409be  jz      short loc_1403409C5
0x1403409c0  call    MsReleaseTable
0x1403409c5  mov     rcx, [rbp+2A70h]; this
0x1403409cc  test    rcx, rcx
0x1403409cf  jz      short loc_1403409D6
0x1403409d1  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1403409d6  mov     rcx, [rbp+2A68h]
0x1403409dd  test    rcx, rcx
0x1403409e0  jz      short loc_1403409E7
0x1403409e2  call    MsReleaseTable
0x1403409e7  mov     rcx, [rbp+2AA0h]; this
0x1403409ee  test    rcx, rcx
0x1403409f1  jz      short loc_1403409F8
0x1403409f3  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x1403409f8  mov     rcx, [rbp+2A98h]
0x1403409ff  test    rcx, rcx
0x140340a02  jz      short loc_140340A09
0x140340a04  call    MsReleaseTable
0x140340a09  mov     rcx, [rbp+2AD0h]; this
0x140340a10  test    rcx, rcx
0x140340a13  jz      short loc_140340A1A
0x140340a15  call    ?Release@CmsReferenced@@QEAAXXZ; CmsReferenced::Release(void)
0x140340a1a  mov     rcx, [rbp+2AC8h]
0x140340a21  test    rcx, rcx
0x140340a24  jz      short loc_140340A2B
0x140340a26  call    MsReleaseTable
0x140340a2b  mov     rcx, [rbp+2AF8h]
0x140340a32  test    rcx, rcx
0x140340a35  jz      short loc_140340A3C
0x140340a37  call    MsReleaseTable
0x140340a3c  mov     rbx, [rbp+0C8h]
0x140340a43  test    rbx, rbx
0x140340a46  jz      short loc_140340A7A
0x140340a48  mov     rbx, [rbx+30h]
0x140340a4c  mov     r9d, 1
0x140340a52  mov     rdx, rbx
0x140340a55  xor     r8d, r8d
0x140340a58  mov     rcx, r15
0x140340a5b  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140340a60  mov     rdx, [rbp+0C8h]
0x140340a67  xor     r8d, r8d
0x140340a6a  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x140340a6f  mov     rdx, rbx; struct _FCB *
0x140340a72  mov     rcx, r15; struct _IRP_CONTEXT *
0x140340a75  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x140340a7a  lea     rcx, [rsp+0A8h+var_88]
0x140340a7f  mov     [rsp+0A8h+arg_10], r13
0x140340a87  call    cs:__imp_ExInitializeFastOwnerEntry
0x140340a8e  nop     dword ptr [rax+rax+00h]
0x140340a93  mov     r8b, 1
0x140340a96  lea     rdx, [rsp+0A8h+var_88]
0x140340a9b  lea     rcx, [rbp+270h]
0x140340aa2  call    cs:__imp_ExAcquireFastResourceShared
0x140340aa9  nop     dword ptr [rax+rax+00h]
0x140340aae  lea     rdx, [rsp+0A8h+arg_10]; void **
0x140340ab6  mov     rcx, rbp; struct _VCB *
0x140340ab9  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x140340abe  lea     rcx, [rbp+270h]
0x140340ac5  mov     [rsp+0A8h+arg_10], rax
0x140340acd  lea     rdx, [rsp+0A8h+var_88]
0x140340ad2  mov     rsi, rax
0x140340ad5  call    cs:__imp_ExReleaseFastResource
0x140340adc  nop     dword ptr [rax+rax+00h]
0x140340ae1  test    rsi, rsi
0x140340ae4  jz      loc_140340D10
0x140340aea  mov     [rsp+0A8h+arg_18], r12
0x140340af2  mov     ebx, 803h
0x140340af7  nop     word ptr [rax+rax+00000000h]
0x140340b00  mov     r9d, 1
0x140340b06  xor     r8d, r8d
0x140340b09  mov     rdx, rsi
0x140340b0c  mov     rcx, r15
0x140340b0f  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140340b14  lea     rbp, [rsi+30h]
0x140340b18  nop     dword ptr [rax+rax+00000000h]
0x140340b20  mov     r14, [rbp+0]
0x140340b24  cmp     r14, rbp
0x140340b27  jz      loc_140340BF8
0x140340b2d  add     r14, 0FFFFFFFFFFFFFF88h
0x140340b31  jz      loc_140340BF8
0x140340b37  movzx   eax, word ptr [r14]
0x140340b3b  sub     ax, bx
0x140340b3e  cmp     ax, 1
0x140340b42  ja      loc_140340BE8
0x140340b48  mov     rbx, [r14+30h]
0x140340b4c  call    cs:__imp_KeEnterGuardedRegion
0x140340b53  nop     dword ptr [rax+rax+00h]
0x140340b58  mov     rcx, rbx; FastMutex
0x140340b5b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140340b62  nop     dword ptr [rax+rax+00h]
0x140340b67  lock inc dword ptr [r14+0ACh]
0x140340b6f  lea     rsi, [r14+178h]
0x140340b76  mov     rax, [rsi]
0x140340b79  cmp     rax, rsi
0x140340b7c  jz      short loc_140340BB7
0x140340b7e  lea     rdi, [rax-8]
0x140340b82  test    rdi, rdi
0x140340b85  jz      short loc_140340BB7
0x140340b87  mov     rbx, [rdi+30h]
0x140340b8b  mov     r9d, 1
0x140340b91  mov     rdx, rbx
0x140340b94  xor     r8d, r8d
0x140340b97  mov     rcx, r15
0x140340b9a  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140340b9f  xor     r8d, r8d
0x140340ba2  mov     rdx, rdi
0x140340ba5  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x140340baa  mov     rdx, rbx; struct _FCB *
0x140340bad  mov     rcx, r15; struct _IRP_CONTEXT *
0x140340bb0  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x140340bb5  jmp     short loc_140340B76
0x140340bb7  mov     eax, [r14+0ACh]
0x140340bbe  inc     eax
0x140340bc0  mov     [r14+0ACh], eax
0x140340bc7  mov     rcx, [r14+30h]; FastMutex
0x140340bcb  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140340bd2  nop     dword ptr [rax+rax+00h]
0x140340bd7  call    cs:__imp_KeLeaveGuardedRegion
0x140340bde  nop     dword ptr [rax+rax+00h]
0x140340be3  mov     ebx, 803h
0x140340be8  mov     rdx, r14; struct _SCB *
0x140340beb  mov     rcx, r15; struct _IRP_CONTEXT *
0x140340bee  call    RefsDeleteScb
0x140340bf3  jmp     loc_140340B20
0x140340bf8  mov     rsi, [rsp+0A8h+arg_10]
0x140340c00  mov     rbp, [rsp+0A8h+arg_8]
0x140340c08  lea     rdi, [rsi+20h]
0x140340c0c  nop     dword ptr [rax+00h]
0x140340c10  mov     rbx, [rdi]
0x140340c13  cmp     rbx, rdi
0x140340c16  jz      short loc_140340C47
0x140340c18  add     rbx, 0FFFFFFFFFFFFFFE0h
0x140340c1c  jz      short loc_140340C47
0x140340c1e  mov     rdx, [rbx+18h]
0x140340c22  mov     r9d, 1
0x140340c28  xor     r8d, r8d
0x140340c2b  mov     rcx, r15
0x140340c2e  mov     rdx, [rdx+88h]
0x140340c35  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140340c3a  mov     r8b, 1
0x140340c3d  mov     rdx, rbx
0x140340c40  call    ?RefsDeleteLcb@@YAXPEAU_IRP_CONTEXT@@PEAU_LCB@@W4LockParentScb@@@Z; RefsDeleteLcb(_IRP_CONTEXT *,_LCB *,LockParentScb)
0x140340c45  jmp     short loc_140340C10
0x140340c47  mov     r8b, 1
0x140340c4a  lea     rcx, [rbp+270h]
0x140340c51  xor     edx, edx
0x140340c53  call    cs:__imp_ExAcquireFastResourceExclusive
0x140340c5a  nop     dword ptr [rax+rax+00h]
0x140340c5f  lea     rax, [rsp+0A8h+arg_0]
0x140340c67  mov     [rsp+0A8h+arg_0], 0
0x140340c6f  lea     r8, [rsp+0A8h+arg_10]; unsigned __int8 *
0x140340c77  mov     [rsi+0F8h], rax
0x140340c7e  mov     rdx, rsi; struct _FCB *
0x140340c81  mov     rcx, r15; struct _IRP_CONTEXT *
0x140340c84  call    ?RefsDeleteFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z; RefsDeleteFcb(_IRP_CONTEXT *,_FCB *,uchar *)
0x140340c89  xor     r13d, r13d
0x140340c8c  lea     rcx, [rsp+0A8h+var_88]
0x140340c91  mov     [rsp+0A8h+arg_10], r13
0x140340c99  call    cs:__imp_ExInitializeFastOwnerEntry
0x140340ca0  nop     dword ptr [rax+rax+00h]
0x140340ca5  mov     r8b, 1
0x140340ca8  lea     rdx, [rsp+0A8h+var_88]
0x140340cad  lea     rcx, [rbp+270h]
0x140340cb4  call    cs:__imp_ExAcquireFastResourceShared
0x140340cbb  nop     dword ptr [rax+rax+00h]
0x140340cc0  lea     rdx, [rsp+0A8h+arg_10]; void **
0x140340cc8  mov     rcx, rbp; struct _VCB *
0x140340ccb  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x140340cd0  lea     rcx, [rbp+270h]
0x140340cd7  mov     [rsp+0A8h+arg_10], rax
0x140340cdf  lea     rdx, [rsp+0A8h+var_88]
0x140340ce4  mov     rsi, rax
0x140340ce7  call    cs:__imp_ExReleaseFastResource
0x140340cee  nop     dword ptr [rax+rax+00h]
0x140340cf3  mov     ebx, 803h
0x140340cf8  test    rsi, rsi
0x140340cfb  jnz     loc_140340B00
  ... truncated ...
```
