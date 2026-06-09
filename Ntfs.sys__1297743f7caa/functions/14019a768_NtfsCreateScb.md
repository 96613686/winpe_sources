# NtfsCreateScb

- ea: `0x14019a768`
- end: `0x14019b371`
- name: `NtfsCreateScb`
- size: `3081`
- prototype: ``
- caller_count: `72`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400bf8d0`
- `0x1400cb1a4`
- `0x1400cc78c`
- `0x1400cf580`
- `0x1400ddcb8`
- `0x1400e7fc8`
- `0x1400e9dc0`
- `0x1400ebc50`
- `0x1400ebef8`
- `0x1400ee9b0`
- `0x1400f783c`
- `0x1400f80c4`
- `0x1400f8a64`
- `0x1400ff2e4`
- `0x14010881c`
- `0x140109820`
- `0x14010a938`
- `0x14010c36c`
- `0x14010dca4`
- `0x140110248`
- `0x140125fc0`
- `0x1401305a0`
- `0x140132210`
- `0x140132768`
- `0x140135868`
- `0x140143730`
- `0x140145ddc`
- `0x140150044`
- `0x140151b18`
- `0x1401578f0`
- `0x140158130`
- `0x14015c700`
- `0x14015efc0`
- `0x140163b00`
- `0x14016581c`
- `0x14016842c`
- `0x140180158`
- `0x14018cb98`
- `0x1401924c0`
- `0x140194cb8`
- `0x1401975f0`
- `0x140198cd0`
- `0x140199220`
- `0x14019a010`
- `0x14019b380`
- `0x14019bf50`
- `0x14019c170`
- `0x14019cad0`
- `0x14019f350`
- `0x1401a2d00`

## callees

- `0x14000d510`
- `0x1400132a8`
- `0x140025af0`
- `0x140025c10`
- `0x140027f70`
- `0x14002b990`
- `0x14002c750`
- `0x14002fe54`
- `0x140059440`
- `0x140059740`
- `0x140059c60`
- `0x1401968a0`
- `0x14019a768`
- `0x1401db1b4`
- `0x1401fd870`
- `0x140212b00`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1402ac846`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1402ac85f`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1402ac846`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x1402ac85f`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14019aba8`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x14019aba8`
- `ntoskrnl!FsRtlInitializeEofLock` at `0x14019ac70`
- `ntoskrnl!FsRtlInitializeEofLock` at `0x14019ac70`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14019ad13`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14019ad13`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1402ac878`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x1402ac878`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac89d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac8fb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac918`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac89d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac8fb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ac918`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019ae3d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b094`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b1f5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019ae3d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b094`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019b1f5`
- `ntoskrnl!KeInitializeEvent` at `0x14019b220`
- `ntoskrnl!KeInitializeEvent` at `0x14019b220`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac8d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac8d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019afad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b075`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b0c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019afad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b075`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019b0c8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019a7c7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14019a7c7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019a84a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b28d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b2dd`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b360`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ac7d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019a84a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b28d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b2dd`
- `ntoskrnl!ExReleaseFastMutex` at `0x14019b360`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402ac7d4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14019a85f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14019a85f`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14019b1ad`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14019b1ce`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14019b1ad`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14019b1ce`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019a97c`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019a97c`

## pseudocode

```c
__int16 *__fastcall NtfsCreateScb(
        __int64 a1,
        __int64 a2,
        int a3,
        const UNICODE_STRING *a4,
        char a5,
        __int64 a6,
        char *a7)
{
  char *v11; // rdi
  __int64 v12; // rbx
  _QWORD *v13; // r15
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  BOOL v16; // eax
  char v17; // r15
  PIRP TopLevelIrp; // rax
  struct _LIST_ENTRY *Flink; // rdx
  PIRP v20; // r8
  __int64 v21; // rax
  __int64 *i; // rcx
  char v24; // bl
  unsigned int v25; // eax
  __int16 v26; // di
  int v27; // eax
  __int16 *v28; // rsi
  __int64 v29; // rdx
  __int64 v30; // r8
  _QWORD *v31; // rdx
  __int64 v32; // rcx
  char v33; // bl
  USHORT Length; // dx
  int v35; // eax
  __int64 v36; // rdx
  _WORD *v37; // rcx
  POOL_TYPE v38; // ecx
  int v39; // edx
  PVOID v40; // rax
  __int16 v41; // ax
  __int64 *k; // rcx
  PVOID v43; // rax
  _WORD *v44; // rax
  __int64 EresourcePriv; // rax
  __int16 *PoolWithTag; // rax
  unsigned int j; // ecx
  bool v48; // zf
  __int16 v49; // ax
  struct _KEVENT *v50; // rax
  char v51; // [rsp+3Ch] [rbp-8Ch] BYREF
  __int16 *v52; // [rsp+40h] [rbp-88h]
  unsigned int v53; // [rsp+48h] [rbp-80h]
  _OWORD v54[2]; // [rsp+50h] [rbp-78h] BYREF
  _WORD *v55; // [rsp+70h] [rbp-58h]
  __int64 v56; // [rsp+78h] [rbp-50h]
  _WORD *v57; // [rsp+80h] [rbp-48h]
  _WORD *v58; // [rsp+88h] [rbp-40h]
  _WORD *v59; // [rsp+90h] [rbp-38h]
  __int16 v61; // [rsp+100h] [rbp+38h]

  memset(v54, 0, sizeof(v54));
  v11 = &v51;
  if ( a7 )
    v11 = a7;
  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
  v12 = 0;
  v13 = (_QWORD *)(a2 + 64);
  while ( 1 )
  {
    if ( v12 )
      v14 = *(_QWORD **)(v12 + 168);
    else
      v14 = (_QWORD *)*v13;
    v12 = (__int64)(v14 - 21);
    if ( v14 == v13 )
      v12 = 0;
    v52 = (__int16 *)v12;
    if ( !v12 )
      break;
    v15 = *(_QWORD *)(v12 + 528);
    if ( a6 )
    {
      v16 = *(_QWORD *)(v12 + 528) == a6;
    }
    else
    {
      if ( (!v15 || (*(_DWORD *)(v15 + 24) & 6) == 0)
        && a3 == *(_DWORD *)(v12 + 256)
        && (*(_DWORD *)(v12 + 512) & 0x1000040) == 0
        && *(_WORD *)(v12 + 264) == a4->Length
        && !memcmp(*(const void **)(v12 + 272), a4->Buffer, *(unsigned __int16 *)(v12 + 264)) )
      {
LABEL_12:
        if ( a3 == 160
          && (a4 == &NtfsFileNameIndex || !a4->Length || a4->Length == 8 && *(_QWORD *)a4->Buffer == 0x30003300490024LL) )
        {
          for ( i = *(__int64 **)(a2 + 48); i != (__int64 *)(a2 + 48); i = (__int64 *)*i )
          {
            if ( !i[10] )
              _InterlockedExchange64(i + 10, v12);
          }
        }
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
        v17 = 1;
        *v11 = 1;
        TopLevelIrp = IoGetTopLevelIrp();
        v20 = TopLevelIrp;
        if ( !TopLevelIrp
          || !HIBYTE(TopLevelIrp->Type)
          || (Flink = TopLevelIrp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink, (HIDWORD(Flink->Flink) & 0x200) == 0) )
        {
          v17 = 0;
        }
        if ( *(_BYTE *)(a1 + 32) != 3
          && (*(_DWORD *)(a1 + 16) & 0x200000LL) == 0
          && (!v17 || ((__int64)TopLevelIrp->AssociatedIrp.MasterIrp->ThreadListEntry.Flink[1].Flink & 0x200000LL) == 0) )
        {
          v21 = *(_QWORD *)(*(_QWORD *)(v12 + 192) + 48LL);
          if ( !v21 || *(_QWORD *)(v12 + 184) != *(_QWORD *)(v21 + 184) )
          {
            if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v12 + 184) + 104LL) + 64LL)) )
              NtfsSnapshotScb(a1, v12);
          }
        }
        if ( (*(_DWORD *)(v12 + 200) & 0x1000000) != 0 )
          NtfsDeleteEncryptionContext(v12, Flink, v20);
        return (__int16 *)v12;
      }
      v16 = 0;
    }
    if ( v16 )
      goto LABEL_12;
  }
  if ( a5 )
  {
    ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
    return 0;
  }
  v24 = 17;
  v59 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  memset(v54, 0, sizeof(v54));
  *v11 = 0;
  v25 = *(_DWORD *)(a2 + 8);
  if ( a3 == 160 )
  {
    v48 = v25 == 5;
    v49 = 1796;
    if ( !v48 )
      v49 = 1795;
    v61 = v49;
    v26 = 776;
  }
  else if ( v25 <= 1 && (a3 == 128 || a3 == 176) )
  {
    v61 = 1798;
    v26 = 720;
  }
  else
  {
    v61 = 1797;
    v26 = 640;
    if ( ((a3 & 0xFFFFF000) != 0 || a3 == 128) && (*(_DWORD *)(a2 + 4) & 0x100) == 0 )
      v24 = 20;
  }
  v27 = *(_DWORD *)(a2 + 4);
  if ( (v27 & 2) != 0 || a3 == 32 )
  {
    PoolWithTag = (__int16 *)ExAllocatePoolWithTag((POOL_TYPE)528, v26, 0x6E66744Eu);
    v24 |= 2u;
    goto LABEL_118;
  }
  if ( a3 == 160 )
  {
    if ( (v27 & 0x400) != 0 )
    {
      v28 = (__int16 *)(a2 + 368);
      if ( !*(_WORD *)(a2 + 368) )
        goto LABEL_52;
    }
    PoolWithTag = (__int16 *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x308u, 0x5366744Eu);
    *(_QWORD *)&v54[0] = PoolWithTag;
    v52 = PoolWithTag;
LABEL_119:
    v28 = PoolWithTag;
    goto LABEL_53;
  }
  if ( a3 != 128 || (v28 = (__int16 *)(a2 + 368), *(_WORD *)(a2 + 368)) )
  {
    PoolWithTag = (__int16 *)ExAllocateFromLookasideListEx(&NtfsScbDataLookasideList);
    v24 |= 0x20u;
LABEL_118:
    *(_QWORD *)&v54[0] = PoolWithTag;
    v52 = PoolWithTag;
    goto LABEL_119;
  }
LABEL_52:
  v52 = v28;
LABEL_53:
  memset(v28, 0, v26);
  *v28 = v61;
  v28[1] = v26;
  if ( (v24 & 4) != 0 )
  {
    if ( !*(_QWORD *)(a2 + 112) )
    {
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) == 0 || *(_BYTE *)(a1 + 32) || !*(_QWORD *)(a1 + 112) )
        goto LABEL_107;
      v53 = 0;
      for ( j = 0; ; ++j )
      {
        v53 = j;
        if ( j >= 2 )
          break;
        if ( *(_QWORD *)(a1 + 8LL * j + 48) )
          goto LABEL_107;
      }
      if ( *(_QWORD *)(a1 + 64) )
      {
LABEL_107:
        if ( !*(_QWORD *)(a2 + 112) )
        {
          v44 = *(_WORD **)(a2 + 104);
          if ( *v44 == 1859 )
            EresourcePriv = (__int64)(v44 + 140);
          else
            EresourcePriv = NtfsAllocateEresourcePriv(1859, v29, v30);
          *(_QWORD *)(a2 + 112) = EresourcePriv;
        }
      }
      else
      {
        LOBYTE(v30) = 1;
        NtfsAddPagingIoToFcb(a1, a2, v30);
      }
    }
    *((_QWORD *)v28 + 2) = *(_QWORD *)(a2 + 112);
  }
  v31 = (_QWORD *)(a2 + 64);
  v32 = *(_QWORD *)(a2 + 64);
  if ( *(_QWORD *)(v32 + 8) != a2 + 64 )
    __fastfail(3u);
  *((_QWORD *)v28 + 21) = v32;
  *((_QWORD *)v28 + 22) = v31;
  *(_QWORD *)(v32 + 8) = v28 + 84;
  *v31 = v28 + 84;
  v33 = v24 | 8;
  *((_QWORD *)v28 + 23) = a2;
  *((_QWORD *)v28 + 24) = *(_QWORD *)(a2 + 96);
  Length = a4->Length;
  if ( a4->Length )
  {
    if ( Length == 8 && *(_QWORD *)a4->Buffer == 0x30003300490024LL )
    {
      *(UNICODE_STRING *)(v28 + 132) = NtfsFileNameIndex;
    }
    else
    {
      v28[132] = Length;
      v28[133] = a4->Length + 2;
      v43 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), a4->Length + 2LL, 0x7346744Eu);
      *((_QWORD *)&v54[0] + 1) = v43;
      *((_QWORD *)v28 + 34) = v43;
      memmove(v43, a4->Buffer, a4->Length);
      *(_WORD *)(*((_QWORD *)v28 + 34) + 2 * ((unsigned __int64)a4->Length >> 1)) = 0;
    }
  }
  *((_DWORD *)v28 + 64) = a3;
  if ( a3 == 128 && (*(_DWORD *)(*((_QWORD *)v28 + 23) + 4LL) & 0x100) == 0 )
    *((_DWORD *)v28 + 128) |= 0x80u;
  if ( v61 == 1798 )
  {
    FsRtlInitializeLargeMcb((PLARGE_MCB)v28 + 20, (POOL_TYPE)512);
    v57 = v28 + 320;
    FsRtlInitializeLargeMcb((PLARGE_MCB)v28 + 21, (POOL_TYPE)512);
    v58 = v28 + 336;
  }
  if ( (v33 & 2) != 0 )
  {
    *((_DWORD *)v28 + 128) |= 0x10u;
    v50 = (struct _KEVENT *)ExAllocateFromLookasideListEx(&NtfsFastMutexNonpagedLookasideList);
    *((_QWORD *)v28 + 6) = v50;
    *((_QWORD *)&v54[1] + 1) = v50;
    v50->Header.LockNV = 1;
    v50->Header.WaitListHead.Flink = 0;
    LODWORD(v50->Header.WaitListHead.Blink) = 0;
    KeInitializeEvent(v50 + 1, SynchronizationEvent, 0);
  }
  else
  {
    *((_QWORD *)v28 + 6) = *(_QWORD *)(a2 + 104) + 8LL;
  }
  v35 = *(_DWORD *)(a2 + 4);
  if ( (v35 & 4) != 0 )
  {
    *((_BYTE *)v28 + 4) |= 0x40u;
    *((_BYTE *)v28 + 6) |= 8u;
  }
  else
  {
    if ( (v35 & 2) != 0 || (v36 = 0, PoolType == 512) )
      v36 = 1;
    ExInitializeAutoExpandPushLock(v28 + 280, v36);
    *((_BYTE *)v28 + 4) |= 0x40u;
    *((_BYTE *)v28 + 6) |= 2u;
    *((_BYTE *)v28 + 7) = *((_BYTE *)v28 + 7) & 0xF | 0x50;
    *((_QWORD *)v28 + 8) = v28 + 28;
    *((_QWORD *)v28 + 7) = v28 + 28;
    *((_QWORD *)v28 + 9) = 0;
    *((_QWORD *)v28 + 10) = 0;
    *((_QWORD *)v28 + 11) = 0;
    *((_QWORD *)v28 + 12) = 0;
    *((_DWORD *)v28 + 26) = 0;
    *((_QWORD *)v28 + 14) = 0;
    if ( a2 != -336 )
      *((_QWORD *)v28 + 10) = a2 + 336;
    if ( v28 != (__int16 *)-560LL )
      *((_QWORD *)v28 + 12) = v28 + 280;
  }
  v37 = (_WORD *)(*(_QWORD *)(a2 + 104) + 168LL);
  if ( *v37 )
  {
    v40 = ExAllocateFromLookasideListEx(&NtfsScbNonpagedLookasideList);
    *(_QWORD *)&v54[1] = v40;
    *((_QWORD *)v28 + 36) = v40;
    memset(v40, 0, 0x48u);
    **((_WORD **)v28 + 36) = 1799;
    *(_WORD *)(*((_QWORD *)v28 + 36) + 2LL) = 72;
    *(_QWORD *)(*((_QWORD *)v28 + 36) + 40LL) = *((_QWORD *)v28 + 24);
    *(_DWORD *)(*((_QWORD *)v28 + 36) + 68LL) = 0;
  }
  else
  {
    *(_QWORD *)&v54[1] = *(_QWORD *)(a2 + 104) + 168LL;
    *((_QWORD *)v28 + 36) = v37;
    memset(v37, 0, 0x48u);
    **((_WORD **)v28 + 36) = 1799;
    *(_WORD *)(*((_QWORD *)v28 + 36) + 2LL) = 72;
    *(_QWORD *)(*((_QWORD *)v28 + 36) + 40LL) = *((_QWORD *)v28 + 24);
    *(_DWORD *)(*((_QWORD *)v28 + 36) + 68LL) = 1;
  }
  FsRtlInitializeEofLock(v28 + 60, v28);
  v38 = PoolType;
  if ( (*((_DWORD *)v28 + 128) & 0x10) != 0 )
    v38 = 512;
  NtfsInitializeNtfsMcb(v28 + 200, v28, v28 + 152, (*((_DWORD *)v28 + 128) & 0x10) != 0 ? 512 : 1, v38);
  v55 = v28 + 200;
  FsLibInitializeRangeLock(*((_QWORD *)v28 + 36) + 48LL);
  v56 = *((_QWORD *)v28 + 36) + 48LL;
  *((_QWORD *)v28 + 61) = v28 + 240;
  *((_QWORD *)v28 + 60) = v28 + 240;
  if ( (unsigned __int16)(v61 - 1795) <= 2u )
  {
    FsRtlInitializeOplock((POPLOCK)v28 + 11);
    v59 = v28 + 44;
  }
  if ( v61 == 1797 )
  {
    *((_QWORD *)v28 + 75) = v28 + 296;
    *((_QWORD *)v28 + 74) = v28 + 296;
    if ( (v33 & 4) == 0
      && *(_QWORD *)(*(_QWORD *)(a2 + 96) + 1944LL) == *(_QWORD *)(a2 + 8)
      && a4->Length == 4
      && *(_DWORD *)a4->Buffer == 4849700 )
    {
      *((_DWORD *)v28 + 128) |= 1u;
    }
  }
  else
  {
    *((_QWORD *)v28 + 73) = v28 + 288;
    *((_QWORD *)v28 + 72) = v28 + 288;
    if ( a3 == 160 )
    {
      *((_QWORD *)v28 + 81) = v28 + 320;
      *((_QWORD *)v28 + 80) = v28 + 320;
      *((_QWORD *)v28 + 95) = v28 + 376;
      *((_QWORD *)v28 + 94) = v28 + 376;
      v41 = v28[132];
      if ( !v41 || v41 == 8 && **((_QWORD **)v28 + 34) == 0x30003300490024LL )
      {
        FsLibInitializeGenericTableAvl(v28 + 348);
        for ( k = *(__int64 **)(a2 + 48); k != (__int64 *)(a2 + 48); k = (__int64 *)*k )
          _InterlockedExchange64(k + 10, (__int64)v28);
      }
    }
  }
  NtfsCheckScbForCache(v28, 4);
  if ( (v33 & 1) != 0 )
    *((_DWORD *)v28 + 128) |= 0x20u;
  if ( (*(_DWORD *)(a2 + 4) & 0x80u) != 0 )
    *((_DWORD *)v28 + 128) |= 0x10000u;
  if ( (*(_DWORD *)(a2 + 4) & 0x8000000) != 0 )
    *((_DWORD *)v28 + 128) |= 0x4000000u;
  if ( *((_DWORD *)v28 + 64) == 160 && *((wchar_t **)v28 + 34) != L"$I30" )
    *((_DWORD *)v28 + 128) |= v39;
  *((_QWORD *)v28 + 1) = *(_QWORD *)(a2 + 104) + 64LL;
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 24LL) & 0x40000) != 0 )
    *((_DWORD *)v28 + 55) = 1;
  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
  TxfSetUpNtfsPtrs(v28, a6, 1);
  return v28;
}

```

## disassembly

```asm
0x14019a768  mov     r11, rsp
0x14019a76b  mov     [r11+8], rbx
0x14019a76f  mov     [r11+18h], rsi
0x14019a773  mov     [r11+20h], r9
0x14019a777  mov     [r11+10h], rdx
0x14019a77b  push    rdi
0x14019a77c  push    r12
0x14019a77e  push    r13
0x14019a780  push    r14
0x14019a782  push    r15
0x14019a784  sub     rsp, 0A0h
0x14019a78b  mov     rsi, r9
0x14019a78e  mov     r12d, r8d
0x14019a791  mov     r14, rdx
0x14019a794  mov     r13, rcx
0x14019a797  xor     ecx, ecx
0x14019a799  mov     [r11-78h], rcx
0x14019a79d  xorps   xmm0, xmm0
0x14019a7a0  xor     eax, eax
0x14019a7a2  movups  [rsp+0C8h+var_78+8], xmm0
0x14019a7a7  mov     [r11-60h], rax
0x14019a7ab  lea     rdi, [rsp+0C8h+var_8C]
0x14019a7b0  mov     rax, [rsp+0C8h+arg_30]
0x14019a7b8  test    rax, rax
0x14019a7bb  cmovnz  rdi, rax
0x14019a7bf  mov     rcx, [rdx+68h]
0x14019a7c3  add     rcx, 8; FastMutex
0x14019a7c7  call    cs:__imp_ExAcquireFastMutex
0x14019a7ce  nop     dword ptr [rax+rax+00h]
0x14019a7d3  xor     r9d, r9d
0x14019a7d6  mov     ebx, r9d
0x14019a7d9  lea     r15, [r14+40h]
0x14019a7dd  test    rbx, rbx
0x14019a7e0  jz      loc_14019A8F0
0x14019a7e6  mov     rcx, [rbx+0A8h]
0x14019a7ed  lea     rbx, [rcx-0A8h]
0x14019a7f4  cmp     rcx, r15
0x14019a7f7  cmovz   rbx, r9
0x14019a7fb  mov     [rsp+0C8h+var_88], rbx
0x14019a800  test    rbx, rbx
0x14019a803  jz      loc_14019A9CF
0x14019a809  mov     rcx, [rbx+210h]
0x14019a810  cmp     [rsp+0C8h+arg_28], r9
0x14019a818  jz      loc_14019A8F8
0x14019a81e  mov     eax, r9d
0x14019a821  cmp     rcx, [rsp+0C8h+arg_28]
0x14019a829  setz    al
0x14019a82c  test    eax, eax
0x14019a82e  jz      short loc_14019A7DD
0x14019a830  cmp     r12d, 0A0h
0x14019a837  mov     r12d, 8
0x14019a83d  jz      loc_14019A9A0
0x14019a843  mov     rcx, [r14+68h]
0x14019a847  add     rcx, r12; FastMutex
0x14019a84a  call    cs:__imp_ExReleaseFastMutex
0x14019a851  nop     dword ptr [rax+rax+00h]
0x14019a856  mov     r15d, 1
0x14019a85c  mov     [rdi], r15b
0x14019a85f  call    cs:__imp_IoGetTopLevelIrp
0x14019a866  nop     dword ptr [rax+rax+00h]
0x14019a86b  mov     r8, rax
0x14019a86e  xor     edi, edi
0x14019a870  test    rax, rax
0x14019a873  jnz     loc_14019A949
0x14019a879  mov     r15b, dil
0x14019a87c  cmp     byte ptr [r13+20h], 3
0x14019a881  jz      short loc_14019A8BF
0x14019a883  mov     eax, [r13+10h]
0x14019a887  bt      rax, 15h
0x14019a88c  jb      short loc_14019A8BF
0x14019a88e  test    r15b, r15b
0x14019a891  jnz     loc_14019B331
0x14019a897  mov     rax, [rbx+0C0h]
0x14019a89e  mov     rax, [rax+30h]
0x14019a8a2  test    rax, rax
0x14019a8a5  jz      loc_14019A96D
0x14019a8ab  mov     rax, [rax+0B8h]
0x14019a8b2  cmp     [rbx+0B8h], rax
0x14019a8b9  jnz     loc_14019A96D
0x14019a8bf  test    dword ptr [rbx+0C8h], 1000000h
0x14019a8c9  jnz     loc_14019B34C
0x14019a8cf  mov     rax, rbx
0x14019a8d2  lea     r11, [rsp+0C8h+var_28]
0x14019a8da  mov     rbx, [r11+30h]
0x14019a8de  mov     rsi, [r11+40h]
0x14019a8e2  mov     rsp, r11
0x14019a8e5  pop     r15
0x14019a8e7  pop     r14
0x14019a8e9  pop     r13
0x14019a8eb  pop     r12
0x14019a8ed  pop     rdi
0x14019a8ee  retn
0x14019a8f0  mov     rcx, [r15]
0x14019a8f3  jmp     loc_14019A7ED
0x14019a8f8  test    rcx, rcx
0x14019a8fb  jnz     loc_14019B2C5
0x14019a901  cmp     r12d, [rbx+100h]
0x14019a908  jnz     short loc_14019A916
0x14019a90a  test    dword ptr [rbx+200h], 1000040h
0x14019a914  jz      short loc_14019A91E
0x14019a916  mov     eax, r9d
0x14019a919  jmp     loc_14019A82C
0x14019a91e  movzx   eax, word ptr [rbx+108h]
0x14019a925  cmp     ax, [rsi]
0x14019a928  jnz     short loc_14019A916
0x14019a92a  mov     r8d, eax; Size
0x14019a92d  mov     rdx, [rsi+8]; Buf2
0x14019a931  mov     rcx, [rbx+110h]; Buf1
0x14019a938  call    memcmp
0x14019a93d  xor     r9d, r9d
0x14019a940  test    eax, eax
0x14019a942  jnz     short loc_14019A916
0x14019a944  jmp     loc_14019A830
0x14019a949  cmp     [rax+1], dil
0x14019a94d  jz      loc_14019A879
0x14019a953  mov     rcx, [rax+18h]
0x14019a957  mov     rdx, [rcx+20h]
0x14019a95b  test    dword ptr [rdx+4], 200h
0x14019a962  jnz     loc_14019A87C
0x14019a968  jmp     loc_14019A879
0x14019a96d  mov     rax, [rbx+0B8h]
0x14019a974  mov     rcx, [rax+68h]
0x14019a978  add     rcx, 40h ; '@'; Resource
0x14019a97c  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14019a983  nop     dword ptr [rax+rax+00h]
0x14019a988  test    al, al
0x14019a98a  jz      loc_14019A8BF
0x14019a990  mov     rdx, rbx
0x14019a993  mov     rcx, r13
0x14019a996  call    NtfsSnapshotScb
0x14019a99b  jmp     loc_14019A8BF
0x14019a9a0  lea     rax, NtfsFileNameIndex
0x14019a9a7  cmp     rsi, rax
0x14019a9aa  jnz     loc_14019B2F0
0x14019a9b0  lea     rdx, [r14+30h]
0x14019a9b4  mov     rcx, [rdx]
0x14019a9b7  cmp     rcx, rdx
0x14019a9ba  jz      loc_14019A843
0x14019a9c0  cmp     [rcx+50h], r9
0x14019a9c4  jz      loc_14019B325
0x14019a9ca  mov     rcx, [rcx]
0x14019a9cd  jmp     short loc_14019A9B7
0x14019a9cf  cmp     [rsp+0C8h+arg_20], r9b
0x14019a9d7  jnz     loc_14019B2D5
0x14019a9dd  mov     bl, 11h
0x14019a9df  mov     [rsp+0C8h+var_98], bl
0x14019a9e3  mov     [rsp+0C8h+var_38], r9
0x14019a9eb  mov     [rsp+0C8h+var_58], r9
0x14019a9f0  mov     [rsp+0C8h+var_50], r9
0x14019a9f5  mov     [rsp+0C8h+var_48], r9
0x14019a9fd  mov     [rsp+0C8h+var_40], r9
0x14019aa05  xorps   xmm0, xmm0
0x14019aa08  movups  [rsp+0C8h+var_78], xmm0
0x14019aa0d  movups  xmmword ptr [rsp+60h], xmm0
0x14019aa12  mov     [rdi], r9b
0x14019aa15  mov     eax, [r14+8]
0x14019aa19  mov     r8d, 0A0h
0x14019aa1f  cmp     r12d, r8d
0x14019aa22  jz      loc_14019B135
0x14019aa28  mov     r15d, 1
0x14019aa2e  cmp     eax, r15d
0x14019aa31  jbe     loc_14019B16A
0x14019aa37  mov     eax, 705h
0x14019aa3c  mov     dword ptr [rsp+0C8h+arg_30], eax
0x14019aa43  mov     [rsp+0C8h+var_94], ax
0x14019aa48  mov     edi, 280h
0x14019aa4d  mov     [rsp+0C8h+var_90], di
0x14019aa52  test    r12d, 0FFFFF000h
0x14019aa59  jnz     loc_14019B031
0x14019aa5f  cmp     r12d, 80h
0x14019aa66  jz      loc_14019B031
0x14019aa6c  mov     edx, 308h; NumberOfBytes
0x14019aa71  mov     eax, [r14+4]
0x14019aa75  test    al, 2
0x14019aa77  jnz     loc_14019B0B9
0x14019aa7d  cmp     r12d, 20h ; ' '
0x14019aa81  jz      loc_14019B0B9
0x14019aa87  cmp     r12d, r8d
0x14019aa8a  jz      loc_14019B04F
0x14019aa90  cmp     r12d, 80h
0x14019aa97  jnz     loc_14019B08D
0x14019aa9d  lea     rsi, [r14+170h]
0x14019aaa4  cmp     [rsi], r9w
0x14019aaa8  jnz     loc_14019B08D
0x14019aaae  mov     [rsp+0C8h+var_88], rsi
0x14019aab3  movsx   r8, di; Size
0x14019aab7  xor     edx, edx; Val
0x14019aab9  mov     rcx, rsi; void *
0x14019aabc  call    memset
0x14019aac1  mov     eax, dword ptr [rsp+0C8h+arg_30]
0x14019aac8  mov     [rsi], ax
0x14019aacb  mov     [rsi+2], di
0x14019aacf  xor     edi, edi
0x14019aad1  test    bl, 4
0x14019aad4  jnz     loc_14019AFEE
0x14019aada  lea     rdx, [r14+40h]
0x14019aade  mov     rcx, [rdx]
0x14019aae1  cmp     [rcx+8], rdx
0x14019aae5  jz      short loc_14019AAEE
0x14019aae7  mov     ecx, 3
0x14019aaec  int     29h; Win8: RtlFailFast(ecx)
0x14019aaee  lea     rax, [rsi+0A8h]
0x14019aaf5  mov     [rax], rcx
0x14019aaf8  mov     [rax+8], rdx
0x14019aafc  mov     [rcx+8], rax
0x14019ab00  mov     [rdx], rax
0x14019ab03  mov     ecx, 8
0x14019ab08  or      bl, cl
0x14019ab0a  mov     [rsp+0C8h+var_98], bl
0x14019ab0e  mov     [rsi+0B8h], r14
0x14019ab15  mov     rax, [r14+60h]
0x14019ab19  mov     [rsi+0C0h], rax
0x14019ab20  mov     r13, [rsp+0C8h+arg_18]
0x14019ab28  movzx   edx, word ptr [r13+0]
0x14019ab2d  test    dx, dx
0x14019ab30  jnz     loc_14019ADFA
0x14019ab36  mov     [rsi+100h], r12d
0x14019ab3d  mov     edx, 80h
0x14019ab42  cmp     r12d, edx
0x14019ab45  jz      loc_14019ADD2
0x14019ab4b  mov     eax, 706h
0x14019ab50  mov     r13d, 200h
0x14019ab56  cmp     word ptr [rsp+0C8h+arg_30], ax
0x14019ab5e  jz      loc_14019B1A0
0x14019ab64  test    bl, 2
0x14019ab67  jnz     loc_14019B1E7
0x14019ab6d  mov     rax, [r14+68h]
0x14019ab71  add     rax, 8
0x14019ab75  mov     [rsi+30h], rax
0x14019ab79  xor     edi, edi
0x14019ab7b  mov     eax, [r14+4]
0x14019ab7f  test    al, 4
0x14019ab81  jnz     loc_14019ADBC
0x14019ab87  test    al, 2
0x14019ab89  jnz     loc_14019B231
0x14019ab8f  mov     edx, edi
0x14019ab91  cmp     cs:PoolType, r13d
0x14019ab98  jz      loc_14019B231
0x14019ab9e  lea     rdi, [rsi+230h]
0x14019aba5  mov     rcx, rdi
0x14019aba8  call    cs:__imp_ExInitializeAutoExpandPushLock
0x14019abaf  nop     dword ptr [rax+rax+00h]
0x14019abb4  or      byte ptr [rsi+4], 40h
0x14019abb8  or      byte ptr [rsi+6], 2
0x14019abbc  mov     al, [rsi+7]
0x14019abbf  and     al, 0Fh
0x14019abc1  or      al, 50h
0x14019abc3  mov     [rsi+7], al
0x14019abc6  lea     rax, [rsi+38h]
0x14019abca  mov     [rax+8], rax
0x14019abce  mov     [rax], rax
0x14019abd1  xor     ecx, ecx
0x14019abd3  mov     [rsi+48h], rcx
0x14019abd7  mov     [rsi+50h], rcx
0x14019abdb  mov     [rsi+58h], rcx
0x14019abdf  mov     [rsi+60h], rcx
0x14019abe3  mov     [rsi+68h], ecx
0x14019abe6  mov     [rsi+70h], rcx
0x14019abea  lea     rax, [r14+150h]
0x14019abf1  test    rax, rax
0x14019abf4  jnz     loc_14019ADF1
0x14019abfa  test    rdi, rdi
0x14019abfd  jz      short loc_14019AC03
0x14019abff  mov     [rsi+60h], rdi
0x14019ac03  mov     rcx, [r14+68h]
0x14019ac07  add     rcx, 0A8h; void *
0x14019ac0e  xor     eax, eax
0x14019ac10  cmp     [rcx], ax
0x14019ac13  jnz     loc_14019AE36
0x14019ac19  mov     [rsp+60h], rcx
0x14019ac1e  mov     [rsi+120h], rcx
0x14019ac25  lea     edi, [rax+48h]
0x14019ac28  mov     r8d, edi; Size
0x14019ac2b  xor     edx, edx; Val
0x14019ac2d  call    memset
0x14019ac32  mov     rax, [rsi+120h]
0x14019ac39  mov     ecx, 707h
0x14019ac3e  mov     [rax], cx
0x14019ac41  mov     rax, [rsi+120h]
0x14019ac48  mov     [rax+2], di
0x14019ac4c  mov     rcx, [rsi+120h]
0x14019ac53  mov     rax, [rsi+0C0h]
0x14019ac5a  mov     [rcx+28h], rax
0x14019ac5e  mov     rax, [rsi+120h]
0x14019ac65  mov     [rax+44h], r15d
0x14019ac69  lea     rcx, [rsi+78h]
0x14019ac6d  mov     rdx, rsi
0x14019ac70  call    cs:__imp_FsRtlInitializeEofLock
0x14019ac77  nop     dword ptr [rax+rax+00h]
0x14019ac7c  mov     eax, [rsi+200h]
0x14019ac82  and     eax, 10h
0x14019ac85  mov     ecx, cs:PoolType
0x14019ac8b  cmovnz  ecx, r13d
0x14019ac8f  lea     rdi, [rsi+190h]
0x14019ac96  neg     eax
0x14019ac98  sbb     r9d, r9d
0x14019ac9b  and     r9d, 1FFh
0x14019aca2  add     r9d, r15d
0x14019aca5  lea     r8, [rsi+130h]
0x14019acac  mov     [rsp+0C8h+var_A8], ecx
  ... truncated ...
```
