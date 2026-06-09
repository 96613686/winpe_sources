# NtfsDeleteUsnJournal

- ea: `0x14026ff48`
- end: `0x140270e55`
- name: `NtfsDeleteUsnJournal`
- size: `3853`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401f58e0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021e60`
- `0x14002b4a0`
- `0x14002c130`
- `0x140037854`
- `0x14003ebc4`
- `0x140054410`
- `0x1400592c0`
- `0x14012c23c`
- `0x140138bb0`
- `0x1401403d0`
- `0x1401cb314`
- `0x1401cf29c`
- `0x1401d29ac`
- `0x1401d2c84`
- `0x1402308d8`
- `0x14026ff48`
- `0x1402a4280`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140270a22`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140270a22`
- `ntoskrnl!KeSetEvent` at `0x140270708`
- `ntoskrnl!KeSetEvent` at `0x140270708`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140270733`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140270733`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140270604`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140270604`
- `ntoskrnl!RtlInitUnicodeString` at `0x140270afd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140270afd`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140270a95`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140270a95`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140270d15`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bacd6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140270d15`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bacd6`
- `ntoskrnl!IoGetActivityIdThread` at `0x140270a46`
- `ntoskrnl!IoGetActivityIdThread` at `0x140270a46`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402709f6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402709f6`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140270c25`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140270c25`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270910`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270983`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402bac47`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270910`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270983`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402bac47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402706c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402706c7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140270800`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027086c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140270800`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027086c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140270526`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140270526`
- `ntoskrnl!ExReleaseResourceLite` at `0x14027054d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14027054d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140270749`
- `ntoskrnl!ExAcquireFastMutex` at `0x140270749`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402707bd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402707bd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14026ffe8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14026ffe8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140270aa8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140270aa8`
- `ntoskrnl!CcFlushCache` at `0x140270596`
- `ntoskrnl!CcFlushCache` at `0x140270596`

## pseudocode

```c
__int64 __fastcall NtfsDeleteUsnJournal(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // r13
  __int16 v6; // di
  unsigned int v7; // esi
  __int64 v8; // rbx
  _DWORD *v9; // r12
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // r10
  unsigned __int16 v20; // ax
  int v21; // eax
  __int64 v23; // rbx
  __int64 v24; // r8
  int v25; // ecx
  __int64 v26; // r12
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // rdi
  __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rbx
  __int64 v33; // r9
  PEPROCESS v34; // rcx
  PEPROCESS *v35; // rax
  __int64 v36; // rdx
  _QWORD **v37; // r8
  _QWORD *i; // rax
  __int64 v39; // rdx
  _QWORD *v40; // rcx
  __int64 *v41; // rax
  __int64 v42; // rcx
  __int64 **v43; // rdx
  _QWORD *v44; // rdx
  char v45; // di
  __int64 v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rcx
  int ActivityIdIrp; // eax
  char *v50; // rdx
  _QWORD *ActivityIdThread; // rax
  WCHAR *v52; // rdx
  const WCHAR *v53; // rcx
  int v54; // r8d
  const WCHAR *v55; // rcx
  const WCHAR *v56; // rcx
  const WCHAR *v57; // rcx
  const WCHAR *v58; // rcx
  __int64 v59; // rax
  int v60; // edi
  int v61; // ebx
  __int64 ProcessImageFileName; // rax
  int v63; // r8d
  _QWORD *v64; // rdx
  int BugCheckOnFailure; // [rsp+A8h] [rbp-168h]
  char v66; // [rsp+128h] [rbp-E8h]
  char v67; // [rsp+129h] [rbp-E7h]
  char v68; // [rsp+12Ah] [rbp-E6h] BYREF
  char v69; // [rsp+12Bh] [rbp-E5h]
  char v70; // [rsp+12Ch] [rbp-E4h]
  char v71; // [rsp+12Dh] [rbp-E3h]
  int v72; // [rsp+130h] [rbp-E0h]
  __int64 v73; // [rsp+138h] [rbp-D8h]
  PEPROCESS CurrentProcess; // [rsp+140h] [rbp-D0h]
  __int64 v75; // [rsp+148h] [rbp-C8h]
  __int64 v76; // [rsp+150h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp-B8h] BYREF
  __int64 v78; // [rsp+168h] [rbp-A8h]
  const WCHAR *v79; // [rsp+170h] [rbp-A0h]
  const WCHAR *v80; // [rsp+178h] [rbp-98h]
  const WCHAR *v81; // [rsp+180h] [rbp-90h]
  const WCHAR *v82; // [rsp+188h] [rbp-88h]
  const WCHAR *v83; // [rsp+190h] [rbp-80h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+198h] [rbp-78h] BYREF
  __int128 v85; // [rsp+1A8h] [rbp-68h] BYREF
  __int128 v86; // [rsp+1B8h] [rbp-58h]
  __int128 v87; // [rsp+1C8h] [rbp-48h] BYREF
  __int64 v88; // [rsp+1D8h] [rbp-38h]

  v4 = a2;
  v75 = a1;
  LOBYTE(v6) = 0;
  v7 = 0;
  v72 = 0;
  v78 = 0;
  v85 = 0;
  v86 = 0;
  v8 = a2[23];
  *(_DWORD *)(a1 + 12) |= 1u;
  v9 = (_DWORD *)a2[3];
  if ( v9 )
    goto LABEL_11;
  v10 = a2[1];
  if ( !v10 )
  {
    v11 = -1073741592;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225704LL, 2823394);
    LOBYTE(a4) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, 3221225704LL, a4, 0);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 2823395;
    goto LABEL_184;
  }
  v9 = (*(_BYTE *)(v10 + 10) & 5) != 0
     ? *(_DWORD **)(v10 + 24)
     : MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
  if ( v9 )
  {
LABEL_11:
    if ( *(_DWORD *)(v8 + 16) < 0x10u )
    {
      v11 = -1073741592;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225704LL, 2823400);
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221225704LL, a4, 0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 2823401;
      goto LABEL_184;
    }
    v13 = *(_QWORD *)(v8 + 48);
    v14 = *(_QWORD *)(v13 + 24);
    if ( v14 )
    {
      v15 = *(_QWORD *)(v13 + 32);
      v16 = *(_QWORD *)(v14 + 192);
      v17 = *(_DWORD *)(v16 + 4);
      if ( (v17 & 1) == 0 && (!v15 || *(_BYTE *)(v15 + 88) != 4 || (v17 & 2) == 0) )
      {
        NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
        JUMPOUT(0x140270E55LL);
      }
      CurrentProcess = *(PEPROCESS *)(v14 + 184);
    }
    else
    {
      v16 = 0;
      v15 = 0;
      CurrentProcess = 0;
    }
    v73 = v16;
    if ( *((_BYTE *)v4 + 64) && (!v15 || !_bittest16((const signed __int16 *)(v15 + 104), 9u)) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        if ( v15 )
          v6 = *(_WORD *)(v15 + 104);
        v18 = v15 + 16;
        if ( !v15 )
          v18 = 0;
        v19 = *(_QWORD *)(v16 + 248);
        v20 = *(_WORD *)(v19 + 6);
        if ( v20 > 0x40u || (v20 & 1) != 0 )
          v20 = 0;
        McTemplateU0ppwwpiwd_EtwWriteTransfer(
          *(_QWORD *)(v14 + 184),
          (unsigned int)usnsup_c5371,
          (unsigned int)KeGetCurrentThread(),
          v16,
          *(_WORD *)(v16 + 7872) >> 1,
          *(_QWORD *)(v16 + 7880),
          v20 >> 1,
          v19 + 32,
          (char)CurrentProcess,
          *(_QWORD *)(*(_QWORD *)(v14 + 184) + 8LL),
          *(_WORD *)v18 >> 1,
          *(_QWORD *)(v18 + 8),
          v6);
      }
      v11 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 2823433);
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221225506LL, a4, 0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 2823434;
      goto LABEL_184;
    }
    v21 = v9[2];
    if ( !v21 )
    {
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 0, a4, 1);
      return 0;
    }
    if ( (v21 & 0xFFFFFFFC) != 0 )
    {
      v7 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 2823449);
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221225485LL, a4, 0);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 2823450);
      return v7;
    }
    if ( (*(_DWORD *)(v16 + 4) & 0x2000000) != 0 )
    {
      v11 = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225634LL, 2823455);
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v4, 3221225634LL, a4, 0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 2823456;
      goto LABEL_184;
    }
    v71 = 0;
    v66 = 0;
    v23 = 0;
    v76 = 0;
    v70 = 0;
    v69 = 0;
    DestinationString = *(struct _UNICODE_STRING *)v9;
    NtfsAcquireCheckpointSynchronization(a1, v16, 18);
    v67 = 1;
    LOBYTE(v24) = 1;
    NtfsAcquireExclusiveVcb(a1, v16, v24);
    v71 = 1;
    v85 = *(_OWORD *)(v16 + 1896);
    v86 = *(_OWORD *)(v16 + 1912);
    v25 = *(_DWORD *)(v16 + 4);
    if ( (v25 & 1) == 0 )
    {
      LOBYTE(v26) = 0;
      v7 = -1073741202;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_57:
        v72 = v7;
        goto LABEL_126;
      }
      v27 = 2823495;
LABEL_56:
      NtfsStatusTraceAndDebugInternal(0, v7, v27);
      goto LABEL_57;
    }
    if ( (v9[2] & 1) != 0 )
    {
      if ( (v25 & 0x100000) != 0 )
      {
        LOBYTE(v26) = 0;
        if ( !NtfsStatusDebugFlags )
        {
LABEL_63:
          v7 = -1073741129;
          goto LABEL_57;
        }
        v28 = 2823523;
LABEL_62:
        NtfsStatusTraceAndDebugInternal(0, 3221226167LL, v28);
        goto LABEL_63;
      }
      if ( *(int *)(v16 + 24) < 0 && *((_BYTE *)v4 + 64) )
      {
        LOBYTE(v26) = 0;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_63;
        v28 = 2823535;
        goto LABEL_62;
      }
      if ( (v25 & 0x200000) != 0 || *(_QWORD *)(v16 + 40) )
      {
        v29 = *(_QWORD *)(v16 + 40);
        if ( v29 && *(_QWORD *)v9 != *(_QWORD *)(v16 + 1912) )
        {
          LOBYTE(v26) = 0;
          v7 = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_57;
          v27 = 2823555;
          goto LABEL_56;
        }
        NtfsSetVolumeInformationFlags(a1, v16, 16, 16, 1, 0);
        NtfsCheckpointCurrentTransaction(a1);
        ClearFlagInterlocked(v16 + 4, 0x80000);
        NtfsFlushVolume(a1);
        v76 = v29;
        if ( v29 )
        {
          NtfsAcquireExclusiveScbEx(a1, v29, 0);
          v78 = *(_QWORD *)(v29 + 32);
        }
        SetFlagInterlocked(v16 + 4, 0x100000);
        *(_WORD *)(v16 + 2148) = 0;
        *(_DWORD *)(v16 + 2144) = 0;
        ExAcquireResourceExclusiveLite((PERESOURCE)(v16 + 8032), 1u);
        *(_DWORD *)(v16 + 8008) &= ~1u;
        *(_QWORD *)(v16 + 8016) = 0;
        *(_QWORD *)(v16 + 8024) = 0;
        ExReleaseResourceLite((PERESOURCE)(v16 + 8032));
        *(_WORD *)(v16 + 2150) = 0;
        *(_DWORD *)(v16 + 2152) = 0;
        *(_QWORD *)(v16 + 40) = 0;
        if ( v29 )
        {
          IoStatus = 0;
          CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v29 + 288) + 16LL), 0, 0, &IoStatus);
          NtfsPurgeCacheSection(a1, v29, 0, 0, 0);
          *(_DWORD *)(v29 + 512) &= ~1u;
          *(_QWORD *)(v29 + 464) = 0;
        }
        *(_QWORD *)(v16 + 1952) = 0;
        *(_QWORD *)(v16 + 1944) = 0;
        NtfsReleaseCheckpointSynchronization(v30, v16, 18);
        v67 = 0;
        if ( v29 )
        {
          FsRtlAcquireHeaderMutex(v29 + 120, v29 + 160);
          v31 = (_QWORD *)(v29 + 592);
          v32 = *(_QWORD **)(v29 + 592);
          while ( v32 != v31 )
          {
            CurrentProcess = (PEPROCESS)*v32;
            if ( (unsigned __int8)NtfsClearCancelRoutine(v32[6]) )
            {
              if ( (*((_DWORD *)v32 + 17) & 1) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v29 + 212));
                v34 = (PEPROCESS)*v32;
                if ( *(_QWORD **)(*v32 + 8LL) != v32 || (v35 = (PEPROCESS *)v32[1], *v35 != (PEPROCESS)v32) )
                  __fastfail(3u);
                *v35 = v34;
                *((_QWORD *)v34 + 1) = v35;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221226167LL, 2823685);
                v36 = v32[6];
                LOBYTE(v33) = v36 != 0;
                NtfsExtendedCompleteRequestInternal(0, v36, 3221226167LL, v33, 0);
                if ( a1 && *(_QWORD *)(a1 + 112) == v32[6] )
                  *(_QWORD *)(a1 + 112) = 0;
                v32[6] = 0;
                ExFreePoolWithTag(v32, 0);
              }
              else
              {
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221226167LL, 2823695);
                *((_DWORD *)v32 + 16) = -1073741129;
                KeSetEvent((PRKEVENT)v32 + 1, 0, 0);
              }
            }
            v32 = CurrentProcess;
            v31 = (_QWORD *)(v29 + 592);
          }
          FsRtlReleaseHeaderMutex(v29 + 120, v29 + 160);
          ExAcquireFastMutex((PFAST_MUTEX)(v16 + 1992));
          v37 = (_QWORD **)(v16 + 1976);
          for ( i = *(_QWORD **)(v16 + 1976); i != v37; i = *v37 )
          {
            v39 = *i;
            if ( *(_QWORD **)(*i + 8LL) != i || (v40 = (_QWORD *)i[1], (_QWORD *)*v40 != i) )
              __fastfail(3u);
            *v40 = v39;
            *(_QWORD *)(v39 + 8) = v40;
            *i = 0;
            v41 = i - 2;
            v42 = *v41;
            if ( *v41 )
            {
              if ( *(__int64 **)(v42 + 8) != v41 || (v43 = (__int64 **)v41[1], *v43 != v41) )
                __fastfail(3u);
              *v43 = (__int64 *)v42;
              *(_QWORD *)(v42 + 8) = v43;
            }
          }
          ExReleaseFastMutex((PFAST_MUTEX)(v16 + 1992));
          NtOfsCloseAttributeSafe(a1, v29);
          v23 = 0;
          v76 = 0;
        }
        else
        {
          v23 = v76;
        }
        v70 = 1;
        if ( (v9[2] & 2) != 0 )
        {
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v16 + 576));
          LOBYTE(v6) = 1;
          v66 = 1;
        }
        else
        {
          LOBYTE(v6) = 0;
        }
        NtfsPostSpecial(a1, v16, (unsigned int)NtfsDeleteUsnSpecial, v16 + 2144, 13);
      }
    }
    if ( (*(_DWORD *)(v16 + 4) & 0x100000) != 0 && (v9[2] & 2) != 0 )
    {
      LOBYTE(v26) = 0;
      if ( !(_BYTE)v6 )
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v16 + 576));
      v7 = 259;
      v72 = 259;
      if ( (unsigned __int8)NtfsSetCancelRoutine(v4, NtfsCancelDeleteUsnJournal, 0, 1, BugCheckOnFailure) )
      {
        v44 = *(_QWORD **)(v16 + 1968);
        if ( *v44 != v16 + 1960 )
          __fastfail(3u);
        v4[21] = v16 + 1960;
        v4[22] = v44;
        *v44 = v4 + 21;
        *(_QWORD *)(v16 + 1968) = v4 + 21;
        v69 = 1;
      }
      else
      {
        v7 = -1073741536;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221225760LL, 2823791);
        v72 = -1073741536;
      }
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v16 + 576));
      v45 = 0;
      goto LABEL_127;
    }
    LOBYTE(v26) = 0;
LABEL_126:
    v45 = v66;
LABEL_127:
    if ( (unsigned __int8)NtfsTelemetryGuard(2048) )
      NtfsTelemetryUsnDelete(a1, v16, (unsigned int)&DestinationString, (unsigned int)&v85, v70, v69, v7);
    if ( v45 )
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v16 + 576));
    if ( v23 )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v23 + 184), 0);
    NtfsReleaseVcb(a1, v16);
    if ( v67 )
      NtfsReleaseCheckpointSynchronization(v46, v16, 18);
    if ( (v7 & 0x80000000) == 0 )
    {
      v87 = 0;
      v88 = 0;
      v68 = 0;
      DestinationString = 0;
      CurrentProcess = IoGetCurrentProcess();
      if ( v7 == 259 || !v4 )
      {
        ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v48);
        if ( ActivityIdThread )
        {
          *((_QWORD *)&v87 + 1) = *ActivityIdThread;
          v88 = ActivityIdThread[1];
          *(_QWORD *)&v87 = (char *)&v87 + 8;
        }
        else
        {
          *(_QWORD *)&v87 = 0;
        }
      }
      else
      {
        ActivityIdIrp = IoGetActivityIdIrp(v4, (char *)&v87 + 8);
        v50 = (char *)&v87 + 8;
        if ( ActivityIdIrp < 0 )
          v50 = 0;
        *(_QWORD *)&v87 = v50;
      }
      if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(v16 + 2160))
        || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v16 + 2160)) )
      {
        NtfsFillVcbVolumeGuid(a1);
      }
      NtfsRepairGetVolumeId(a1, v16, 0, (unsigned int)&DestinationString, (__int64)&v68);
      if ( !DestinationString.Length )
        RtlInitUnicodeString(&DestinationString, L"??");
      if ( (Microsoft_Windows_NtfsEnableBits & 0x800) != 0 )
      {
        v52 = (WCHAR *)&word_140064400;
        v53 = &word_140064400;
        if ( *(_QWORD *)(v16 + 6736) )
          v53 = *(const WCHAR **)(v16 + 6736);
        v79 = v53;
        LODWORD(v75) = (*(_DWORD *)(v16 + 28) >> 2) & 1;
        v54 = *(_DWORD *)(v16 + 6660);
        if ( (unsigned int)(v54 - 1) > 0x13 )
          v54 = 0;
        LODWORD(v73) = v54;
        v55 = &word_140064400;
        if ( *(_QWORD *)(v16 + 6720) )
          v55 = *(const WCHAR **)(v16 + 6720);
        v80 = v55;
        v56 = &word_140064400;
        if ( *(_QWORD *)(v16 + 6704) )
          v56 = *(const WCHAR **)(v16 + 6704);
        v81 = v56;
        v57 = &word_140064400;
        if ( *(_QWORD *)(v16 + 6688) )
          v57 = *(const WCHAR **)(v16 + 6688);
        v82 = v57;
        v58 = &word_140064400;
        if ( *(_QWORD *)(v16 + 6672) )
          v58 = *(const WCHAR **)(v16 + 6672);
        v83 = v58;
        if ( *(_QWORD *)(v16 + 7864) )
          v52 = *(WCHAR **)(v16 + 7864);
        IoStatus.Pointer = v52;
        if ( (*(_DWORD *)(v16 + 4) & 0xC00) != 0x800 )
        {
          v59 = *(_QWORD *)(v16 + 248);
          if ( v59 )
          {
            v26 = *(_QWORD *)(v59 + 16);
            if ( v26 )
              LODWORD(v26) = (*(_DWORD *)(v26 + 48) >> 8) & 1;
          }
        }
        v60 = v87;
        v61 = *(_DWORD *)(v16 + 6792);
        ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
        McTemplateK0jmztzzzzzqjqtzsii_EtwWriteTransfer(
          ProcessImageFileName,
          v16 + 7808,
          v60,
          v16 + 7824,
          v16 + 8528,
          (__int64)DestinationString.Buffer,
          v26,
          (__int64)IoStatus.Pointer,
          (__int64)v83,
          (__int64)v82,
          (__int64)v81,
          (__int64)v80,
          v73,
          v16 + 7808,
          v61,
          v75,
          (__int64)v79,
          ProcessImageFileName,
          v86,
          v78);
      }
      if ( v68 )
        RtlFreeUnicodeString(&DestinationString);
    }
    if ( NtfsStatusDebugFlags && v7 && v7 - 298 > 1 && v7 + 2147483643 > 1 && v7 != 259 )
      NtfsStatusTraceAndDebugInternal(a1, v7, 2823918);
    v63 = 0;
    v64 = v4;
    if ( v7 == 259 )
    {
      v64 = 0;
      v4 = 0;
    }
    LOBYTE(v47) = v64 != 0;
    LOBYTE(v63) = (v7 & 0x80000000) == 0;
    NtfsExtendedCompleteRequestInternal(a1, v4, v7, v47, v63);
    return v7;
  }
  v11 = -1073741670;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 2823388);
  LOBYTE(a4) = v4 != 0;
  NtfsExtendedCompleteRequestInternal(a1, v4, 3221225626LL, a4, 0);
  if ( !NtfsStatusDebugFlags )
    return v11;
  v12 = 2823389;
LABEL_184:
  NtfsStatusTraceAndDebugInternal(0, v11, v12);
  return v11;
}

```

## disassembly

```asm
0x14026ff48  mov     r11, rsp
0x14026ff4b  mov     [r11+18h], rbx
0x14026ff4f  mov     [r11+20h], rsi
0x14026ff53  push    rdi
0x14026ff54  push    r12
0x14026ff56  push    r13
0x14026ff58  push    r14
0x14026ff5a  push    r15
0x14026ff5c  sub     rsp, 160h
0x14026ff63  mov     rax, cs:__security_cookie
0x14026ff6a  xor     rax, rsp
0x14026ff6d  mov     [rsp+188h+var_30], rax
0x14026ff75  mov     r13, rdx
0x14026ff78  mov     r15, rcx
0x14026ff7b  mov     [rsp+188h+var_C8], rcx
0x14026ff83  xor     edi, edi
0x14026ff85  mov     esi, edi
0x14026ff87  mov     [rsp+188h+var_E0], edi
0x14026ff8e  mov     [r11-0A8h], rdi
0x14026ff95  xorps   xmm0, xmm0
0x14026ff98  movups  xmmword ptr [r11-68h], xmm0
0x14026ff9d  movups  xmmword ptr [r11-58h], xmm0
0x14026ffa2  mov     rbx, [rdx+0B8h]
0x14026ffa9  or      dword ptr [rcx+0Ch], 1
0x14026ffad  mov     r12, [rdx+18h]
0x14026ffb1  test    r12, r12
0x14026ffb4  jnz     loc_14027004D
0x14026ffba  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14026ffbe  test    rcx, rcx
0x14026ffc1  jz      loc_140270DBB
0x14026ffc7  test    byte ptr [rcx+0Ah], 5
0x14026ffcb  jz      short loc_14026FFD3
0x14026ffcd  mov     r12, [rcx+18h]
0x14026ffd1  jmp     short loc_14026FFF7
0x14026ffd3  mov     [rsp+188h+Priority], 40000010h; Priority
0x14026ffdb  mov     [rsp+188h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14026ffdf  xor     r9d, r9d; RequestedAddress
0x14026ffe2  xor     edx, edx; AccessMode
0x14026ffe4  lea     r8d, [r9+1]; CacheType
0x14026ffe8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14026ffef  nop     dword ptr [rax+rax+00h]
0x14026fff4  mov     r12, rax
0x14026fff7  test    r12, r12
0x14026fffa  jnz     short loc_14027004D
0x14026fffc  mov     al, cs:NtfsStatusDebugFlags
0x140270002  mov     ebx, 0C000009Ah
0x140270007  test    al, al
0x140270009  jz      short loc_14027001B
0x14027000b  mov     r8d, 2B14DCh
0x140270011  mov     edx, ebx
0x140270013  mov     rcx, r15
0x140270016  call    NtfsStatusTraceAndDebugInternal
0x14027001b  test    r13, r13
0x14027001e  setnz   r9b
0x140270022  mov     [rsp+188h+BugCheckOnFailure], edi
0x140270026  mov     r8d, ebx
0x140270029  mov     rdx, r13
0x14027002c  mov     rcx, r15
0x14027002f  call    NtfsExtendedCompleteRequestInternal
0x140270034  mov     al, cs:NtfsStatusDebugFlags
0x14027003a  test    al, al
0x14027003c  jz      loc_140270E0C
0x140270042  mov     r8d, 2B14DDh
0x140270048  jmp     loc_140270E03
0x14027004d  cmp     dword ptr [rbx+10h], 10h
0x140270051  jnb     short loc_1402700A4
0x140270053  mov     al, cs:NtfsStatusDebugFlags
0x140270059  mov     ebx, 0C00000E8h
0x14027005e  test    al, al
0x140270060  jz      short loc_140270072
0x140270062  mov     r8d, 2B14E8h
0x140270068  mov     edx, ebx
0x14027006a  mov     rcx, r15
0x14027006d  call    NtfsStatusTraceAndDebugInternal
0x140270072  test    r13, r13
0x140270075  setnz   r9b
0x140270079  mov     [rsp+188h+BugCheckOnFailure], edi
0x14027007d  mov     r8d, ebx
0x140270080  mov     rdx, r13
0x140270083  mov     rcx, r15
0x140270086  call    NtfsExtendedCompleteRequestInternal
0x14027008b  mov     al, cs:NtfsStatusDebugFlags
0x140270091  test    al, al
0x140270093  jz      loc_140270E0C
0x140270099  mov     r8d, 2B14E9h
0x14027009f  jmp     loc_140270E03
0x1402700a4  mov     rcx, [rbx+30h]
0x1402700a8  mov     r8, [rcx+18h]
0x1402700ac  test    r8, r8
0x1402700af  jz      short loc_1402700F0
0x1402700b1  mov     rcx, [rcx+20h]
0x1402700b5  mov     r14, [r8+0C0h]
0x1402700bc  mov     eax, [r14+4]
0x1402700c0  test    al, 1
0x1402700c2  jnz     short loc_1402700DF
0x1402700c4  test    rcx, rcx
0x1402700c7  jz      loc_140270E3C
0x1402700cd  cmp     byte ptr [rcx+58h], 4
0x1402700d1  jnz     loc_140270E3C
0x1402700d7  test    al, 2
0x1402700d9  jz      loc_140270E3C
0x1402700df  mov     rax, [r8+0B8h]
0x1402700e6  mov     [rsp+188h+var_D0], rax
0x1402700ee  jmp     short loc_1402700FE
0x1402700f0  mov     r14, rdi
0x1402700f3  mov     rcx, rdi
0x1402700f6  mov     [rsp+188h+var_D0], rdi
0x1402700fe  mov     [rsp+188h+var_D8], r14
0x140270106  cmp     [r13+40h], dil
0x14027010a  jz      loc_14027023C
0x140270110  test    rcx, rcx
0x140270113  jz      short loc_140270121
0x140270115  bt      word ptr [rcx+68h], 9
0x14027011b  jb      loc_14027023C
0x140270121  mov     eax, [r15+10h]
0x140270125  bt      rax, 14h
0x14027012a  jb      loc_1402701EB
0x140270130  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140270137  test    al, 20h
0x140270139  jz      loc_1402701EB
0x14027013f  test    rcx, rcx
0x140270142  jz      short loc_140270148
0x140270144  movzx   edi, word ptr [rcx+68h]
0x140270148  xor     edx, edx
0x14027014a  test    rcx, rcx
0x14027014d  lea     r9, [rcx+10h]
0x140270151  jnz     short loc_140270156
0x140270153  mov     r9d, edx
0x140270156  mov     r10, [r14+0F8h]
0x14027015d  movzx   eax, word ptr [r10+6]
0x140270162  cmp     ax, 40h ; '@'
0x140270166  ja      short loc_14027016C
0x140270168  test    al, 1
0x14027016a  jz      short loc_14027016E
0x14027016c  mov     eax, edx
0x14027016e  movzx   edx, word ptr [r9]
0x140270172  shr     edx, 1
0x140270174  mov     rcx, [r8+0B8h]
0x14027017b  add     r10, 20h ; ' '
0x14027017f  movzx   r11d, ax
0x140270183  shr     r11d, 1
0x140270186  movzx   ebx, word ptr [r14+1EC0h]
0x14027018e  shr     ebx, 1
0x140270190  mov     r8, gs:188h
0x140270199  mov     [rsp+188h+var_128], edi
0x14027019d  mov     rax, [r9+8]
0x1402701a1  mov     [rsp+188h+var_130], rax
0x1402701a6  mov     dword ptr [rsp+188h+var_138], edx
0x1402701aa  mov     rax, [rcx+8]
0x1402701ae  mov     [rsp+188h+var_140], rax
0x1402701b3  mov     rax, [rsp+188h+var_D0]
0x1402701bb  mov     [rsp+188h+var_148], rax
0x1402701c0  mov     [rsp+188h+var_150], r10
0x1402701c5  mov     [rsp+188h+var_158], r11d
0x1402701ca  mov     rax, [r14+1EC8h]
0x1402701d1  mov     qword ptr [rsp+188h+Priority], rax
0x1402701d6  mov     [rsp+188h+BugCheckOnFailure], ebx
0x1402701da  mov     r9, r14
0x1402701dd  lea     rdx, usnsup_c5371
0x1402701e4  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x1402701e9  xor     edi, edi
0x1402701eb  mov     al, cs:NtfsStatusDebugFlags
0x1402701f1  mov     ebx, 0C0000022h
0x1402701f6  test    al, al
0x1402701f8  jz      short loc_14027020A
0x1402701fa  mov     r8d, 2B1509h
0x140270200  mov     edx, ebx
0x140270202  mov     rcx, r15
0x140270205  call    NtfsStatusTraceAndDebugInternal
0x14027020a  test    r13, r13
0x14027020d  setnz   r9b
0x140270211  mov     [rsp+188h+BugCheckOnFailure], edi
0x140270215  mov     r8d, ebx
0x140270218  mov     rdx, r13
0x14027021b  mov     rcx, r15
0x14027021e  call    NtfsExtendedCompleteRequestInternal
0x140270223  mov     al, cs:NtfsStatusDebugFlags
0x140270229  test    al, al
0x14027022b  jz      loc_140270E0C
0x140270231  mov     r8d, 2B150Ah
0x140270237  jmp     loc_140270E03
0x14027023c  mov     eax, [r12+8]
0x140270241  test    eax, eax
0x140270243  jnz     short loc_14027026F
0x140270245  mov     al, cs:NtfsStatusDebugFlags
0x14027024b  test    r13, r13
0x14027024e  setnz   r9b
0x140270252  mov     [rsp+188h+BugCheckOnFailure], 1
0x14027025a  xor     r8d, r8d
0x14027025d  mov     rdx, r13
0x140270260  mov     rcx, r15
0x140270263  call    NtfsExtendedCompleteRequestInternal
0x140270268  xor     eax, eax
0x14027026a  jmp     loc_140270E0E
0x14027026f  test    eax, 0FFFFFFFCh
0x140270274  jz      short loc_1402702CE
0x140270276  mov     al, cs:NtfsStatusDebugFlags
0x14027027c  mov     esi, 0C000000Dh
0x140270281  test    al, al
0x140270283  jz      short loc_140270295
0x140270285  mov     r8d, 2B1519h
0x14027028b  mov     edx, esi
0x14027028d  mov     rcx, r15
0x140270290  call    NtfsStatusTraceAndDebugInternal
0x140270295  test    r13, r13
0x140270298  setnz   r9b
0x14027029c  mov     [rsp+188h+BugCheckOnFailure], edi
0x1402702a0  mov     r8d, esi
0x1402702a3  mov     rdx, r13
0x1402702a6  mov     rcx, r15
0x1402702a9  call    NtfsExtendedCompleteRequestInternal
0x1402702ae  mov     al, cs:NtfsStatusDebugFlags
0x1402702b4  test    al, al
0x1402702b6  jz      short loc_1402702C7
0x1402702b8  mov     r8d, 2B151Ah
0x1402702be  mov     edx, esi
0x1402702c0  xor     ecx, ecx
0x1402702c2  call    NtfsStatusTraceAndDebugInternal
0x1402702c7  mov     eax, esi
0x1402702c9  jmp     loc_140270E0E
0x1402702ce  test    dword ptr [r14+4], 2000000h
0x1402702d6  jz      short loc_140270329
0x1402702d8  mov     al, cs:NtfsStatusDebugFlags
0x1402702de  mov     ebx, 0C00000A2h
0x1402702e3  test    al, al
0x1402702e5  jz      short loc_1402702F7
0x1402702e7  mov     r8d, 2B151Fh
0x1402702ed  mov     edx, ebx
0x1402702ef  mov     rcx, r15
0x1402702f2  call    NtfsStatusTraceAndDebugInternal
0x1402702f7  test    r13, r13
0x1402702fa  setnz   r9b
0x1402702fe  mov     [rsp+188h+BugCheckOnFailure], edi
0x140270302  mov     r8d, ebx
0x140270305  mov     rdx, r13
0x140270308  mov     rcx, r15
0x14027030b  call    NtfsExtendedCompleteRequestInternal
0x140270310  mov     al, cs:NtfsStatusDebugFlags
0x140270316  test    al, al
0x140270318  jz      loc_140270E0C
0x14027031e  mov     r8d, 2B1520h
0x140270324  jmp     loc_140270E03
0x140270329  mov     [rsp+188h+var_E3], dil
0x140270331  mov     [rsp+188h+var_E7], dil
0x140270339  mov     [rsp+188h+var_E8], dil
0x140270341  xor     eax, eax
0x140270343  mov     ebx, eax
0x140270345  mov     [rsp+188h+var_C0], rax
0x14027034d  mov     [rsp+188h+var_E4], al
0x140270354  mov     [rsp+188h+var_E5], al
0x14027035b  movups  xmm0, xmmword ptr [r12]
0x140270360  movdqu  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x140270369  lea     r8d, [rax+12h]
0x14027036d  mov     rdx, r14
0x140270370  mov     rcx, r15
0x140270373  call    NtfsAcquireCheckpointSynchronization
0x140270378  mov     [rsp+188h+var_E7], 1
0x140270380  mov     r8b, 1
0x140270383  mov     rdx, r14
0x140270386  mov     rcx, r15
0x140270389  call    NtfsAcquireExclusiveVcb
0x14027038e  mov     [rsp+188h+var_E3], 1
0x140270396  movups  xmm0, xmmword ptr [r14+768h]
0x14027039e  movups  [rsp+188h+var_68], xmm0
0x1402703a6  movups  xmm1, xmmword ptr [r14+778h]
0x1402703ae  movups  [rsp+188h+var_58], xmm1
0x1402703b6  mov     ecx, [r14+4]
0x1402703ba  test    cl, 1
0x1402703bd  jnz     short loc_1402703EC
0x1402703bf  mov     al, cs:NtfsStatusDebugFlags
0x1402703c5  xor     r12d, r12d
0x1402703c8  mov     esi, 0C000026Eh
0x1402703cd  test    al, al
0x1402703cf  jz      short loc_1402703E0
0x1402703d1  mov     r8d, 2B1547h
0x1402703d7  mov     edx, esi
0x1402703d9  xor     ecx, ecx
0x1402703db  call    NtfsStatusTraceAndDebugInternal
0x1402703e0  mov     [rsp+188h+var_E0], esi
0x1402703e7  jmp     loc_14027092C
0x1402703ec  mov     eax, [r12+8]
0x1402703f1  test    al, 1
0x1402703f3  jz      loc_140270842
0x1402703f9  bt      ecx, 14h
0x1402703fd  jnb     short loc_140270425
0x1402703ff  mov     al, cs:NtfsStatusDebugFlags
0x140270405  xor     r12d, r12d
0x140270408  test    al, al
0x14027040a  jz      short loc_14027041E
0x14027040c  mov     r8d, 2B1563h
0x140270412  xor     ecx, ecx
0x140270414  mov     edx, 0C00002B7h
0x140270419  call    NtfsStatusTraceAndDebugInternal
0x14027041e  mov     esi, 0C00002B7h
0x140270423  jmp     short loc_1402703E0
0x140270425  xor     edx, edx
0x140270427  cmp     [r14+18h], edx
0x14027042b  jge     short loc_140270448
0x14027042d  cmp     [r13+40h], dl
0x140270431  jz      short loc_140270448
  ... truncated ...
```
