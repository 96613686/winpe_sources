# TxfOpenFileProcessing

- ea: `0x14019dcc8`
- end: `0x14019f267`
- name: `TxfOpenFileProcessing`
- size: `5535`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14019c170`
- `0x14019cad0`
- `0x1402195a0`
- `0x140227568`
- `0x1402376fc`
- `0x140261f90`
- `0x14029cb00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14001c8c0`
- `0x14002b520`
- `0x14002b680`
- `0x140034560`
- `0x140035e70`
- `0x140059440`
- `0x140059740`
- `0x1400b454c`
- `0x14012be50`
- `0x14012c23c`
- `0x14013c320`
- `0x1401403d0`
- `0x14017e980`
- `0x140187df0`
- `0x14018a8a0`
- `0x14018dc9c`
- `0x14018e0cc`
- `0x1401924c0`
- `0x1401968a0`
- `0x140196b20`
- `0x14019dcc8`
- `0x1401ac0d0`
- `0x1401c2960`
- `0x140204dfc`
- `0x140243c50`
- `0x140245e30`
- `0x140264ca4`
- `0x140265518`
- `0x14029acc0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14019eadc`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14019eadc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14019eab2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14019eab2`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14019e8a4`
- `ntoskrnl!FsRtlCurrentOplock` at `0x14019e8a4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f185`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f1aa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f185`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14019f1aa`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e0c7`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e248`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e271`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e0c7`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e248`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019e271`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14019e987`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14019e987`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019eb2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019eb2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019ea82`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14019ea82`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019e967`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14019e967`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019df31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e1ca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e73c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019ee52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f063`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f146`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019df31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e1ca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019e73c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019ee52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f063`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14019f146`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019de15`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e582`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e5a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e645`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e6a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019efab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f03f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f1d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f22e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acbe4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019de15`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e19b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e582`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e5a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e645`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019e6a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019efab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f03f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f1d5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14019f22e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acbe4`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14019e21c`
- `ntoskrnl!MmCanFileBeTruncated` at `0x14019e21c`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019de30`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019deb5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019ed5d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019f01a`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019de30`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019deb5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019ed5d`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14019f01a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e554`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e609`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e554`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14019e609`
- `ntoskrnl!ExRaiseStatus` at `0x14019e032`
- `ntoskrnl!ExRaiseStatus` at `0x14019e07b`
- `ntoskrnl!ExRaiseStatus` at `0x14019e455`
- `ntoskrnl!ExRaiseStatus` at `0x14019e8ed`
- `ntoskrnl!ExRaiseStatus` at `0x14019e032`
- `ntoskrnl!ExRaiseStatus` at `0x14019e07b`
- `ntoskrnl!ExRaiseStatus` at `0x14019e455`
- `ntoskrnl!ExRaiseStatus` at `0x14019e8ed`

## pseudocode

```c
__int64 __fastcall TxfOpenFileProcessing(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 *a9)
{
  __int64 v9; // rdi
  __int64 v10; // r13
  __int64 v12; // r9
  unsigned __int8 v13; // r12
  int v14; // ecx
  bool v15; // r10
  __int64 v16; // r14
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // r15
  __int64 v22; // rdx
  unsigned int v23; // r15d
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  char v29; // al
  _QWORD *v30; // r15
  __int64 v31; // rdx
  __int64 v32; // r8
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r15
  __int64 v36; // r8
  _QWORD *v37; // rax
  PVOID v38; // rax
  int v39; // ecx
  int v40; // r15d
  __int64 v41; // rax
  __int64 v42; // r12
  __int64 v43; // r15
  NTSTATUS v44; // r15d
  __int64 v45; // r11
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  char v49; // al
  __int64 v50; // r15
  __int64 NextChildScb; // rax
  __int16 v52; // r10
  char v53; // r11
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // r15
  int v57; // edx
  __int64 v58; // rax
  __int64 v59; // r15
  __int64 v60; // rcx
  int v61; // edx
  unsigned int v62; // ecx
  USHORT v63; // r8
  unsigned int v64; // eax
  __int64 v65; // rcx
  volatile signed __int32 *v66; // rax
  volatile signed __int32 *v67; // r15
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // r11
  __int64 v73; // rdx
  __int64 v74; // r10
  __int64 v75; // r8
  __int64 TxfFo; // rax
  int v77; // r9d
  _DWORD *v78; // rdx
  __int64 v79; // rax
  int v81; // [rsp+20h] [rbp-D8h]
  char v82; // [rsp+38h] [rbp-C0h]
  unsigned __int8 v83; // [rsp+50h] [rbp-A8h]
  unsigned int v84; // [rsp+54h] [rbp-A4h]
  int v85; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+60h] [rbp-98h]
  signed __int32 v87; // [rsp+68h] [rbp-90h] BYREF
  __int64 v88; // [rsp+70h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-80h] BYREF
  __int64 v90; // [rsp+88h] [rbp-70h]
  __int64 v91; // [rsp+90h] [rbp-68h]
  PVOID Entry; // [rsp+98h] [rbp-60h]
  __int64 v93; // [rsp+A0h] [rbp-58h]
  __int64 v94; // [rsp+A8h] [rbp-50h]
  char v95; // [rsp+100h] [rbp+8h] BYREF
  __int64 v96; // [rsp+108h] [rbp+10h] BYREF
  __int64 v97; // [rsp+118h] [rbp+20h]

  v97 = a4;
  v96 = a2;
  v9 = a3;
  v10 = a2;
  v12 = 0;
  v13 = 0;
  v95 = 0;
  v14 = *(_DWORD *)(a1 + 436);
  v15 = (a5 & 0x10D0116) != 0 || (v14 & 6) != 0;
  v83 = v15;
  v16 = 0;
  v93 = 0;
  v17 = *(_QWORD *)(a2 + 320);
  v84 = 0;
  v87 = 0;
  v88 = 0;
  Entry = 0;
  LODWORD(v90) = *(_DWORD *)(a1 + 28);
  v18 = a8;
  if ( a8 )
    v19 = *(_QWORD *)(a8 + 176);
  else
    v19 = *(_QWORD *)(*(_QWORD *)(a1 + 112) + 184LL);
  v91 = v19;
  v20 = *(_DWORD *)(v17 + 136);
  if ( (v20 & 0x4000) != 0 && (v14 & 0x100000) == 0 && ((v20 & 0x80000) == 0 || (*(_DWORD *)(v10 + 4) & 0x40000) != 0) )
    TxfParkRequest(a1, *(_QWORD *)(v17 + 24) + 1280LL, 0);
  if ( a8 )
    goto LABEL_28;
  while ( 1 )
  {
    v21 = *(_QWORD *)(a1 + 400);
    v86 = v21;
    if ( !v21 )
    {
      v17 = 1;
      goto LABEL_7;
    }
    v39 = *(_DWORD *)(v10 + 8);
    if ( (v39 == 5 || *(_DWORD *)(*(_QWORD *)(v10 + 320) + 88LL) == v39)
      && v17 != *(_QWORD *)(*(_QWORD *)(v17 + 16) + 6248LL)
      && v15
      && a6 == (_DWORD)v12 )
    {
      break;
    }
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 528) == v12 )
        TxfSetUpNtfsPtrs(v9, 0, 0);
    }
    else if ( *(_QWORD *)(v10 + 328) == v12 )
    {
      *(_QWORD *)(v10 + 328) = TxfCreateTxfFcb(
                                 *(_QWORD *)(v10 + 96),
                                 v17,
                                 (_QWORD *)(v10 + 8),
                                 *(_WORD *)(v10 + 4) & 0x400,
                                 0,
                                 0);
    }
    v16 = *(_QWORD *)(v10 + 328);
    v93 = v16;
    v17 = 1;
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v16 + 136), 1u);
    v95 = 1;
    v13 = 0;
    if ( a6 && v21 != *(_QWORD *)(v16 + 24) )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
      v12 = 0;
      v95 = 0;
      goto LABEL_7;
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
    v95 = 0;
    v23 = NtfsUpgradeFileSecurity(a1);
    v84 = v23;
    v85 = v23;
    if ( v23 )
      goto LABEL_265;
    v40 = v90;
    if ( (_DWORD)v90 != *(_DWORD *)(a1 + 28) )
      NtfsCheckpointCurrentTransaction(a1);
    v16 = *(_QWORD *)(v10 + 328);
    v93 = v16;
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v16 + 136), 1u);
    v95 = 1;
    if ( (v83 || (v41 = *(_QWORD *)(v16 + 24)) != 0 && v41 == v86) && (*(_DWORD *)(a1 + 436) & 2) == 0 )
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
      v95 = 0;
      v82 = v40 != 0;
      v42 = a8;
      v43 = v97;
      TxfPrepareFileForTxfLogging(a1, a8, 1, 0, v82);
    }
    else
    {
      ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
      v95 = 0;
      v43 = v97;
      v42 = a8;
    }
    if ( v42
      && v83
      && a9
      && (*(_DWORD *)(v91 + 16) & 0x1000) != 0
      && v43
      && v9
      && (!*(_WORD *)(v9 + 264) || *(_DWORD *)(v9 + 256) != 128) )
    {
      v44 = TxfPrepareFileForPotentialTxLinkDelete(a1);
      v84 = v44;
      v85 = v44;
      if ( v44 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v44 < 0xFFFFFFED
          && v44 != -1073741802
          && v44 != -1073741807
          && (unsigned int)(v44 + 2147483643) > 1
          && v44 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v44, 2624476);
        }
        ExRaiseStatus(v44);
      }
      *(_DWORD *)(v42 + 192) |= 1u;
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v16 + 136), 1u);
    v13 = 1;
    v95 = 1;
    v45 = 0;
    if ( !v83 )
      goto LABEL_178;
    if ( *(_DWORD *)(v10 + 284) )
    {
      if ( v10 != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 96) + 32LL) + 184LL) )
      {
        v46 = *(_QWORD *)(*(_QWORD *)(v16 + 40) + 96LL);
        if ( !v46 || v10 != *(_QWORD *)(v46 + 184) )
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2624515);
      }
    }
    v47 = *(_DWORD *)(v16 + 4);
    if ( (v47 & 1) == 0 )
    {
      if ( *(_BYTE *)v91 == (_BYTE)v45
        && (v9 && *(_DWORD *)(v9 + 256) == 128 || (*(_DWORD *)(v10 + 176) & 0x10000000) == 0) )
      {
        v48 = *(_QWORD *)(*(_QWORD *)(v91 + 8) + 8LL);
        if ( (*(_DWORD *)(v48 + 24) & 0x2000000) != 0 )
        {
          *(_DWORD *)(v48 + 20) &= ~0x20u;
          v49 = a5 & 0xDF;
          a5 &= ~0x20u;
        }
        else
        {
          v49 = a5;
        }
        if ( (v49 & 0x20) != 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3222863940LL, 2624547);
          v85 = -1072103356;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3222863940LL, 2624547);
          ExRaiseStatus(-1072103356);
        }
      }
      v50 = v45;
      while ( 1 )
      {
        NextChildScb = NtfsGetNextChildScb(v10, v50, 0);
        v50 = NextChildScb;
        if ( !NextChildScb )
          break;
        v54 = *(_DWORD *)(NextChildScb + 256);
        if ( (v54 == 128 && *(_WORD *)v50 == 1797
           || v54 == 160
           && *(_WORD *)(v50 + 264) == v52
           && **(_QWORD **)(v50 + 272) == 0x30003300490024LL
           && (unsigned __int16)(*(_WORD *)v50 - 1795) <= 1u)
          && FsRtlCurrentOplock((POPLOCK)(v50 + 88)) )
        {
          v55 = TxfSearchAddTxfFcbCleanupList(*(_QWORD *)(a1 + 144), 0, 5, 0, 1);
          *(_DWORD *)(v55 + 16) |= 0x80000u;
          *(_QWORD *)(v55 + 40) = *(_QWORD *)(v10 + 8);
          *(_BYTE *)(v55 + 48) = 0;
          ExRaiseStatus(-1073741608);
        }
      }
      v56 = TxfSearchAddTxfFcbCleanupList(a1, v16, 1, 0, v53);
      *(_DWORD *)(v56 + 16) |= 0x800u;
      *(_DWORD *)(v16 + 4) |= 1u;
      v57 = *(_DWORD *)(v16 + 4);
      v58 = v86;
      *(_QWORD *)(v16 + 24) = v86;
      if ( (*(_DWORD *)(v10 + 4) & 0x1800000) != 0 )
      {
        _InterlockedOr((volatile signed __int32 *)(v58 + 16), 4u);
        v57 = *(_DWORD *)(v16 + 4);
      }
      if ( (a5 & 6) != 0 )
        *(_DWORD *)(v16 + 4) = v57 | 0x4000000;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v16 + 40) + 16LL) + 6176LL));
      ++*(_WORD *)(v16 + 16);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v16 + 40) + 16LL) + 6176LL));
      TxfTransAddTxfFcbToPendingList(v86, v16);
      v45 = 0;
      if ( *(_QWORD *)(v10 + 296) )
      {
        NtfsFreeFcbUsnRecord(a1, &v96);
        v45 = 0;
      }
      *(_DWORD *)(v16 + 4) &= ~0x10000u;
      if ( (*(_DWORD *)(a1 + 436) & 2) != 0 )
        goto LABEL_178;
      *(_DWORD *)(v56 + 16) &= ~0x800u;
      *(_DWORD *)(*(_QWORD *)(v10 + 328) + 148LL) |= 0x400000u;
      if ( !a7 )
        goto LABEL_178;
      v59 = v97;
      if ( !v97 )
        goto LABEL_178;
      v60 = *(_QWORD *)(v97 + 24);
      if ( !v60 )
        goto LABEL_178;
      v32 = *(_QWORD *)(v97 + 192);
      if ( (*(_BYTE *)(v32 + 65) & 3) == 2 )
        goto LABEL_178;
      *(_QWORD *)&DestinationString.Length = 0;
      DestinationString.Buffer = 0;
      v61 = *(unsigned __int16 *)(v60 + 656);
      v62 = v61 + 2 * *(unsigned __int8 *)(v32 + 64);
      v63 = v62 + 2;
      if ( (unsigned __int16)v61 <= 2u )
        v63 = v62;
      v64 = v62 + 2;
      if ( (unsigned __int16)v61 <= 2u )
        v64 = v62;
      if ( v64 <= 0xFFFE )
      {
        DestinationString.MaximumLength = v63;
        DestinationString.Buffer = (PWSTR)ExAllocatePoolWithTag(PoolType, v64, 0x30667854u);
        v45 = 0;
        if ( DestinationString.Buffer )
        {
          RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(*(_QWORD *)(v59 + 24) + 656LL));
          if ( *(_WORD *)(*(_QWORD *)(v59 + 24) + 656LL) > 2u )
            RtlAppendUnicodeToString(&DestinationString, L"\\");
          memmove(
            (char *)DestinationString.Buffer + DestinationString.Length,
            (const void *)(*(_QWORD *)(v59 + 192) + 66LL),
            2LL * *(unsigned __int8 *)(*(_QWORD *)(v59 + 192) + 64LL));
          DestinationString.Length += 2 * *(unsigned __int8 *)(*(_QWORD *)(v59 + 192) + 64LL);
          ExFreePoolWithTag(DestinationString.Buffer, 0);
          v45 = 0;
        }
LABEL_178:
        v65 = v86;
        goto LABEL_179;
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225734LL, 2624717);
      NtfsRaiseStatusInternal(a1, -1073741562, 0, 0, 2624717);
LABEL_59:
      v30 = ExAllocateFromLookasideListEx(&TxfFcbInfoLookasideList);
      memset(v30, 0, 0x50u);
      *((_OWORD *)v30 + 1) = *(_OWORD *)(v10 + 128);
      *((_OWORD *)v30 + 2) = *(_OWORD *)(v10 + 144);
      *((_OWORD *)v30 + 3) = *(_OWORD *)(v10 + 160);
      v30[8] = *(_QWORD *)(v10 + 176);
      *((_DWORD *)v30 + 18) = *(_DWORD *)(v10 + 280);
      v33 = (_QWORD *)(v16 + 88);
      v34 = *(_QWORD *)(v16 + 88);
      if ( *(_QWORD *)(v34 + 8) != v16 + 88 )
        __fastfail(3u);
      *v30 = v34;
      v30[1] = v33;
      *(_QWORD *)(v34 + 8) = v30;
      *v33 = v30;
      *(_DWORD *)(v16 + 4) |= 8u;
      *((_WORD *)v30 + 39) |= 1u;
      v12 = 0;
      goto LABEL_187;
    }
    while ( 1 )
    {
      if ( (a5 & 6) != 0 )
        *(_DWORD *)(v16 + 4) = v47 | 0x4000000;
      if ( (*(_DWORD *)(v10 + 4) & 0x1800000) == 0 )
        goto LABEL_178;
      v65 = v86;
      _InterlockedOr((volatile signed __int32 *)(v86 + 16), 4u);
LABEL_179:
      if ( (*(_DWORD *)(v16 + 4) & 1) == 0 || *(_QWORD *)(v16 + 24) != v65 || (*(_DWORD *)(a1 + 436) & 2) != 0 )
        goto LABEL_185;
      v23 = TxfSavepointProcessing(a1, v65, v10, 0, v45, v45, 1, 1, 1);
      v84 = v23;
      v85 = v23;
      v12 = 0;
      if ( v23 )
        goto LABEL_265;
      if ( (*(_DWORD *)(v16 + 4) & 0x8000) == 0 )
      {
        TxfLogFcbInfoRecord(a1, v86, v10, 1, 0, 0);
LABEL_185:
        v12 = 0;
      }
      if ( (*(_DWORD *)(v16 + 4) & 8) == 0 )
        goto LABEL_59;
LABEL_187:
      if ( !v9 )
        goto LABEL_212;
      v96 = *(_QWORD *)(v9 + 528);
      LOBYTE(v32) = 1;
      LOBYTE(v31) = 1;
      v66 = (volatile signed __int32 *)TxfCurrentWritableVersion(v96, v31, v32);
      v67 = v66;
      v12 = 0;
      if ( v66 )
      {
        v87 = *((_DWORD *)v66 + 2);
        Entry = (PVOID)v66;
      }
      if ( (*(_DWORD *)(a1 + 436) & 4) == 0
        && *(_DWORD *)(v9 + 256) == 128
        && (((*(_BYTE *)(v96 + 24) & 1) == 0) & !_bittest(&v87, 0xFu)) != 0 )
      {
        TxfFlushStreamForOpenProcessing(a1, v9, (unsigned int)&v87, (unsigned int)&v95, (__int64)&v88);
        *(_DWORD *)(*(_QWORD *)(v9 + 528) + 24LL) |= 0x80000000;
        v13 = v95;
        v12 = 0;
      }
      if ( !v67 )
      {
        TxfCreateTxfVscb(a1, v9, 1, 0);
        LOBYTE(v68) = 1;
        LOBYTE(v69) = 1;
        v67 = (volatile signed __int32 *)TxfCurrentWritableVersion(v96, v69, v68);
        Entry = (PVOID)v67;
        v12 = 0;
      }
      *((_DWORD *)v67 + 2) |= v87;
      if ( (*(_DWORD *)(v16 + 4) & 1) == 0 || *(_QWORD *)(v16 + 24) != v86 )
        goto LABEL_212;
      if ( (v67[2] & 2) != 0 )
        break;
      v70 = TxfSearchAddTxfFcbCleanupList(a1, v16, 1, 0, 0);
      v90 = v70;
      _InterlockedAdd(v67 + 1, 1u);
      _InterlockedOr(v67 + 2, 2u);
      *(_QWORD *)(v70 + 24) = v67;
      *(_DWORD *)(v70 + 16) |= 0x400u;
      v71 = v96;
      *(_DWORD *)(v96 + 24) |= 0x20u;
      if ( (*(_DWORD *)(a1 + 436) & 4) != 0 || *(_DWORD *)(v9 + 256) != 128 || (*(_DWORD *)(v71 + 24) & 1) != 0 )
        goto LABEL_211;
      v13 = 0;
      if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v9 + 184) + 112LL)) )
      {
        if ( *(_QWORD *)(v86 + 320) != v86 + 320 )
          _InterlockedOr(v67 + 2, 0x100u);
        v35 = v96;
        if ( (*(_DWORD *)(v96 + 24) & 8) == 0 )
          TxfLogCurrentAttrSizesUndo(a1, v86, v9, 1);
        ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
        v95 = 0;
        LOBYTE(v36) = 1;
        NtfsDeleteInternalAttributeStream(a1, v9, v36, 0);
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v16 + 136), 1u);
        v13 = 1;
        v95 = 1;
        _InterlockedAdd((volatile signed __int32 *)(v9 + 212), 1u);
        v88 = v9;
        if ( !*(_QWORD *)(v35 + 112)
          && (*(_DWORD *)(v9 + 208) && (unsigned int)(*(_DWORD *)(v9 + 212) - 1) > *(_DWORD *)(v35 + 32)
           || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v9 + 288) + 16LL), 0))
          && *(_DWORD *)(*(_QWORD *)(v9 + 288) + 64LL) )
        {
          v37 = ExAllocateFromLookasideListEx(&TxfDefaultReaderSectionLookasideList);
          *(_QWORD *)(v35 + 112) = v37;
          *v37 = *(_QWORD *)(v9 + 288);
          *(_QWORD *)(*(_QWORD *)(v35 + 112) + 8LL) = v9;
          v38 = ExAllocateFromLookasideListEx(&NtfsScbNonpagedLookasideList);
          *(_QWORD *)(v9 + 288) = v38;
          memset(v38, 0, 0x48u);
          **(_WORD **)(v9 + 288) = 1799;
          *(_WORD *)(*(_QWORD *)(v9 + 288) + 2LL) = 72;
          *(_QWORD *)(*(_QWORD *)(v9 + 288) + 40LL) = *(_QWORD *)(v9 + 192);
          *(_DWORD *)(*(_QWORD *)(v9 + 288) + 68LL) = 0;
        }
        NtfsCheckpointCurrentTransaction(a1);
        _InterlockedDecrement((volatile signed __int32 *)(v9 + 212));
        v12 = 0;
        v88 = 0;
        *(_DWORD *)(v90 + 16) &= ~0x400u;
        goto LABEL_212;
      }
      *(_DWORD *)(a1 + 436) |= 0x10000u;
      v47 = NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625074);
    }
    v23 = TxfSavepointProcessing(a1, v86, v10, v9, v97, 0, v13, 1, 1);
    v84 = v23;
    v85 = v23;
    v12 = 0;
    if ( v23 )
      goto LABEL_265;
    if ( *(_DWORD *)(a1 + 28) != (_DWORD)v90 )
    {
      NtfsCheckpointCurrentTransaction(a1);
LABEL_211:
      v12 = 0;
    }
LABEL_212:
    if ( a9 )
    {
      v94 = 0;
      if ( !v13 )
      {
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v16 + 136), 1u);
        v95 = 1;
      }
      v72 = a8;
      v73 = *(unsigned __int16 *)(a8 + 70);
      if ( v83 )
      {
        if ( (unsigned __int16)v73 <= 0xFFFDu )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3222863909LL, 2625311);
          NtfsRaiseStatusInternal(a1, -1072103387, 0, 0, 2625311);
LABEL_76:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3222863906LL, 2625383);
          NtfsRaiseStatusInternal(a1, -1072103390, 0, 0, 2625383);
LABEL_79:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3222863907LL, 2625392);
          NtfsRaiseStatusInternal(a1, -1072103389, 0, 0, 2625392);
LABEL_82:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3222863906LL, 2625373);
          NtfsRaiseStatusInternal(a1, -1072103390, 0, 0, 2625373);
LABEL_85:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3222863908LL, 2625403);
          NtfsRaiseStatusInternal(a1, -1072103388, 0, 0, 2625403);
LABEL_88:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3222863940LL, 2625496);
          v85 = -1072103356;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3222863940LL, 2625496);
          ExRaiseStatus(-1072103356);
        }
        *(_WORD *)(a8 + 70) = -1;
        v73 = 0xFFFF;
LABEL_222:
        v21 = v86;
      }
      else
      {
        if ( (_WORD)v73 != 0xFFFE )
          goto LABEL_222;
        v21 = v86;
        if ( v86 == *(_QWORD *)(v16 + 24) )
        {
          *(_WORD *)(a8 + 70) = -1;
          v73 = 0xFFFF;
        }
        else
        {
          *(_WORD *)(a8 + 70) = 0;
          v73 = 0;
        }
      }
      v74 = *(_QWORD *)(v9 + 528);
      v75 = *(_QWORD *)(v74 + 56);
      v94 = v75;
      if ( (_WORD)v73 == 0xFFFF )
      {
        v73 = 0xFFFF;
      }
      else
      {
        while ( 1 )
        {
          if ( !v75 )
            goto LABEL_82;
          if ( *(_WORD *)(v75 + 304) <= (unsigned __int16)v73 || (*(_DWORD *)(v75 + 8) & 1) != 0 )
            break;
          v75 = *(_QWORD *)(v75 + 32);
          v94 = v75;
        }
        if ( *(_WORD *)(v75 + 304) != (_WORD)v73 )
          goto LABEL_82;
        if ( (_WORD)v73 )
        {
          if ( (*(_DWORD *)(v75 + 8) & 0x2000) != 0 )
            goto LABEL_79;
        }
        else
        {
          if ( (*(_DWORD *)(*(_QWORD *)(v75 + 16) + 24LL) & 1) != 0 )
            goto LABEL_76;
          v73 = 0;
        }
      }
      if ( (_WORD)v73 && *(_QWORD *)(*(_QWORD *)(v74 + 64) + 24LL) != *(_QWORD *)(a1 + 400) )
        goto LABEL_85;
      if ( !v72 )
        v73 = 0xFFFF;
      TxfFo = TxfCreateTxfFo(a1, v73, v75, v83);
      *a9 = TxfFo;
      ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
      v12 = 0;
      v13 = 0;
      v95 = 0;
      if ( v83 && a7 )
        *(_DWORD *)(a7 + 80) &= ~0x10u;
    }
    else
    {
      v21 = v86;
    }
LABEL_7:
    v16 = *(_QWORD *)(v10 + 328);
    v93 = v16;
    if ( !v13 && v16 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v16 + 136), 1u);
      v13 = 1;
      v95 = 1;
      v12 = 0;
    }
    v22 = v91;
    if ( *(_BYTE *)v91 != (_BYTE)v12 )
    {
LABEL_9:
      if ( v21 )
        goto LABEL_10;
      if ( !v9 )
        goto LABEL_10;
      v21 = *(_QWORD *)(v9 + 528);
      if ( !v21 || v83 == (_BYTE)v12 || a6 != (_DWORD)v12 || (*(_DWORD *)(a1 + 436) & 0x80008) != 0 )
        goto LABEL_10;
      if ( *(_QWORD *)(v21 + 112) == v12 )
        goto LABEL_254;
      if ( v13 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v21 + 64) + 136LL));
        v13 = 0;
        v95 = 0;
      }
      IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v10 + 112));
      v10 = 0;
      if ( IsResourceAcquiredExclusiveLite )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v9 + 288) + 16LL) )
        {
          _InterlockedAdd((volatile signed __int32 *)(v9 + 212), 1u);
          v88 = v9;
          LOBYTE(v81) = 0;
          v85 = NtfsFlushUserStream(a1, v9, 0, 0, v81);
          NtfsNormalizeAndCleanupTransaction(a1, &v85);
          if ( (*(_DWORD *)(v9 + 200) & 0x200) != 0 )
          {
            LOBYTE(v77) = 1;
            NtfsWriteFileSizes(a1, v9, 0, v77, 1, 1);
          }
          NtfsPurgeCacheSection(a1, v9, 0, 0, 0);
          _InterlockedDecrement((volatile signed __int32 *)(v9 + 212));
          v88 = 0;
          v84 = v85;
        }
        LOBYTE(v25) = 1;
        NtfsDeleteInternalAttributeStream(a1, v9, v25, 0);
        v12 = 0;
LABEL_254:
        if ( !v13 )
        {
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v21 + 64) + 136LL), 1u);
          v95 = 1;
          v12 = 0;
        }
        if ( *(_QWORD *)(v21 + 112) != v12 )
        {
          v78 = *(_DWORD **)(v9 + 288);
          if ( v78[16] == (_DWORD)v12 )
          {
            if ( (v78[17] & 1) != 0 )
              *(_WORD *)v78 = v12;
            else
              ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v78);
          }
          *(_QWORD *)(v9 + 288) = **(_QWORD **)(v21 + 112);
          ExFreeToLookasideListEx(&TxfDefaultReaderSectionLookasideList, *(PVOID *)(v21 + 112));
          *(_QWORD *)(v21 + 112) = 0;
        }
        v79 = *(_QWORD *)(v21 + 56);
        if ( v79 )
          _InterlockedOr((volatile signed __int32 *)(v79 + 8), 1u);
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v21 + 64) + 136LL));
        v13 = 0;
        v95 = 0;
LABEL_10:
        v23 = v84;
        goto LABEL_265;
      }
      *(_DWORD *)(a1 + 436) |= 0x10000u;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625566);
    }
    if ( v16
      && (*(_DWORD *)(v16 + 4) & 0x4200000) != 0
      && (v9 && *(_DWORD *)(v9 + 256) == 128 || (*(_DWORD *)(v10 + 176) & 0x10000000) == 0)
      && (v21 == *(_QWORD *)(v16 + 24) || !v21) )
    {
      v28 = *(_QWORD *)(*(_QWORD *)(v22 + 8) + 8LL);
      if ( (*(_DWORD *)(v28 + 24) & 0x2000000) != 0 )
      {
        *(_DWORD *)(v28 + 20) &= ~0x20u;
        v29 = a5 & 0xDF;
        a5 &= ~0x20u;
      }
      else
      {
        v29 = a5;
      }
      if ( (v29 & 0x20) != 0 )
        goto LABEL_88;
    }
    if ( *(_BYTE *)v22 != (_BYTE)v12 )
      goto LABEL_9;
    if ( !v9 )
      goto LABEL_9;
    v26 = *(_QWORD *)(v9 + 528);
    if ( !v26 || (*(_DWORD *)(v26 + 24) & 0x1000) == 0 )
      goto LABEL_9;
    v13 = 0;
    if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v10 + 112)) )
    {
      if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 528) + 64LL) + 136LL)) )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 184) + 328LL) + 136LL));
        ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(v9 + 184) + 328LL) + 136LL), 1u);
      }
      v95 = 0;
      TxfPublishCommittedChangesToDefaultReaderSection(a1, v9);
      v12 = 0;
      goto LABEL_9;
    }
    *(_DWORD *)(a1 + 4) |= 0x10000u;
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 2625513);
LABEL_28:
    v27 = *(_QWORD *)(a1 + 400);
    if ( !v27 || v15 && *(_QWORD *)(v27 + 240) == v12 )
    {
      LOBYTE(a3) = v15;
      TxfSetupTransactionContextForCreate(a1, v18, a3, v10);
      v15 = v83;
      v12 = 0;
    }
  }
  v23 = -1072103361;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3222863935LL, 2624276);
  v85 = -1072103361;
LABEL_265:
  if ( v88 )
    _InterlockedDecrement((volatile signed __int32 *)(v88 + 212));
  if ( Entry )
  {
    TxfDereferenceTxfVscb(Entry);
    v13 = 0;
  }
  if ( v13 )
    ExReleaseResourceLite(*(PERESOURCE *)(v16 + 136));
  return v23;
}

```

## disassembly

```asm
0x14019dcc8  mov     r11, rsp
0x14019dccb  mov     [r11+20h], r9
0x14019dccf  mov     [r11+10h], rdx
0x14019dcd3  push    rbx
0x14019dcd4  push    rsi
0x14019dcd5  push    rdi
0x14019dcd6  push    r12
0x14019dcd8  push    r13
0x14019dcda  push    r14
0x14019dcdc  push    r15
0x14019dcde  sub     rsp, 0C0h
0x14019dce5  mov     rdi, r8
0x14019dce8  mov     r13, rdx
0x14019dceb  mov     rbx, rcx
0x14019dcee  xor     r9d, r9d
0x14019dcf1  mov     r12b, r9b
0x14019dcf4  mov     [r11+8], r9b
0x14019dcf8  mov     ecx, [rcx+1B4h]
0x14019dcfe  test    cl, 6
0x14019dd01  setnz   r10b
0x14019dd05  test    dword ptr [r11+28h], 10D0116h
0x14019dd0d  setnz   al
0x14019dd10  or      r10b, al
0x14019dd13  mov     [rsp+0F8h+var_A8], r10b
0x14019dd18  mov     r14d, r9d
0x14019dd1b  mov     [r11-58h], r9
0x14019dd1f  mov     rsi, [rdx+140h]
0x14019dd26  mov     [rsp+0F8h+var_A4], r9d
0x14019dd2b  mov     [rsp+0F8h+var_90], r9d
0x14019dd30  mov     [rsp+0F8h+var_88], r9
0x14019dd35  mov     [r11-60h], r9
0x14019dd39  mov     eax, [rbx+1Ch]
0x14019dd3c  mov     dword ptr [rsp+0F8h+var_70], eax
0x14019dd43  mov     rdx, [rsp+0F8h+arg_38]
0x14019dd4b  test    rdx, rdx
0x14019dd4e  jz      loc_14019F23C
0x14019dd54  mov     rax, [rdx+0B0h]
0x14019dd5b  mov     [rsp+0F8h+var_68], rax
0x14019dd63  mov     eax, [rsi+88h]
0x14019dd69  bt      eax, 0Eh
0x14019dd6d  jb      loc_14019E461
0x14019dd73  test    rdx, rdx
0x14019dd76  jnz     loc_14019DEF3
0x14019dd7c  mov     r15, [rbx+190h]
0x14019dd83  mov     [rsp+0F8h+var_98], r15
0x14019dd88  test    r15, r15
0x14019dd8b  jnz     loc_14019E4B0
0x14019dd91  lea     esi, [r15+1]
0x14019dd95  mov     r14, [r13+148h]
0x14019dd9c  mov     [rsp+0F8h+var_58], r14
0x14019dda4  test    r12b, r12b
0x14019dda7  jz      loc_14019DF1E
0x14019ddad  mov     rdx, [rsp+0F8h+var_68]
0x14019ddb5  cmp     [rdx], r9b
0x14019ddb8  jz      loc_14019DE79
0x14019ddbe  test    r15, r15
0x14019ddc1  jz      short loc_14019DDCD
0x14019ddc3  mov     r15d, [rsp+0F8h+var_A4]
0x14019ddc8  jmp     loc_14019F1F4
0x14019ddcd  test    rdi, rdi
0x14019ddd0  jz      short loc_14019DDC3
0x14019ddd2  mov     r15, [rdi+210h]
0x14019ddd9  test    r15, r15
0x14019dddc  jz      short loc_14019DDC3
0x14019ddde  cmp     [rsp+0F8h+var_A8], r9b
0x14019dde3  jz      short loc_14019DDC3
0x14019dde5  cmp     [rsp+0F8h+arg_28], r9d
0x14019dded  jnz     short loc_14019DDC3
0x14019ddef  test    dword ptr [rbx+1B4h], 80008h
0x14019ddf9  jnz     short loc_14019DDC3
0x14019ddfb  cmp     [r15+70h], r9
0x14019ddff  jz      loc_14019F133
0x14019de05  test    r12b, r12b
0x14019de08  jz      short loc_14019DE2C
0x14019de0a  mov     rcx, [r15+40h]
0x14019de0e  mov     rcx, [rcx+88h]; Resource
0x14019de15  call    cs:__imp_ExReleaseResourceLite
0x14019de1c  nop     dword ptr [rax+rax+00h]
0x14019de21  xor     r12b, r12b
0x14019de24  mov     [rsp+0F8h+arg_0], r12b
0x14019de2c  mov     rcx, [r13+70h]; Resource
0x14019de30  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14019de37  nop     dword ptr [rax+rax+00h]
0x14019de3c  xor     r13d, r13d
0x14019de3f  test    al, al
0x14019de41  jnz     loc_14019F08A
0x14019de47  mov     eax, [rbx+1B4h]
0x14019de4d  bts     eax, 10h
0x14019de51  mov     [rbx+1B4h], eax
0x14019de57  mov     al, cs:NtfsStatusDebugFlags
0x14019de5d  mov     [rsp+0F8h+var_D8], 28101Eh
0x14019de66  xor     r9d, r9d
0x14019de69  xor     r8d, r8d
0x14019de6c  mov     edx, 0C00000D8h
0x14019de71  mov     rcx, rbx
0x14019de74  call    NtfsRaiseStatusInternal
0x14019de79  test    r14, r14
0x14019de7c  jnz     loc_14019DF50
0x14019de82  cmp     [rdx], r9b
0x14019de85  jnz     loc_14019DDBE
0x14019de8b  test    rdi, rdi
0x14019de8e  jz      loc_14019DDBE
0x14019de94  mov     rax, [rdi+210h]
0x14019de9b  test    rax, rax
0x14019de9e  jz      loc_14019DDBE
0x14019dea4  test    dword ptr [rax+18h], 1000h
0x14019deab  jz      loc_14019DDBE
0x14019deb1  mov     rcx, [r13+70h]; Resource
0x14019deb5  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14019debc  nop     dword ptr [rax+rax+00h]
0x14019dec1  xor     r12d, r12d
0x14019dec4  test    al, al
0x14019dec6  jnz     loc_14019F008
0x14019decc  bts     dword ptr [rbx+4], 10h
0x14019ded1  mov     al, cs:NtfsStatusDebugFlags
0x14019ded7  mov     [rsp+0F8h+var_D8], 280FE9h
0x14019dee0  xor     r9d, r9d
0x14019dee3  xor     r8d, r8d
0x14019dee6  mov     edx, 0C00000D8h
0x14019deeb  mov     rcx, rbx
0x14019deee  call    NtfsRaiseStatusInternal
0x14019def3  mov     rax, [rbx+190h]
0x14019defa  test    rax, rax
0x14019defd  jnz     loc_14019E495
0x14019df03  mov     r9, r13
0x14019df06  mov     r8b, r10b
0x14019df09  mov     rcx, rbx
0x14019df0c  call    TxfSetupTransactionContextForCreate
0x14019df11  mov     r10b, [rsp+0F8h+var_A8]
0x14019df16  xor     r9d, r9d
0x14019df19  jmp     loc_14019DD7C
0x14019df1e  test    r14, r14
0x14019df21  jz      loc_14019DDAD
0x14019df27  mov     dl, sil; Wait
0x14019df2a  mov     rcx, [r14+88h]; Resource
0x14019df31  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14019df38  nop     dword ptr [rax+rax+00h]
0x14019df3d  mov     r12b, sil
0x14019df40  mov     [rsp+0F8h+arg_0], sil
0x14019df48  xor     r9d, r9d
0x14019df4b  jmp     loc_14019DDAD
0x14019df50  test    dword ptr [r14+4], 4200000h
0x14019df58  jz      loc_14019DE82
0x14019df5e  test    rdi, rdi
0x14019df61  jz      short loc_14019DF6F
0x14019df63  cmp     dword ptr [rdi+100h], 80h
0x14019df6d  jz      short loc_14019DF80
0x14019df6f  test    dword ptr [r13+0B0h], 10000000h
0x14019df7a  jnz     loc_14019DE82
0x14019df80  cmp     r15, [r14+18h]
0x14019df84  jz      short loc_14019DF8F
0x14019df86  test    r15, r15
0x14019df89  jnz     loc_14019DE82
0x14019df8f  mov     rax, [rdx+8]
0x14019df93  mov     rcx, [rax+8]
0x14019df97  test    dword ptr [rcx+18h], 2000000h
0x14019df9e  jz      loc_14019EFF4
0x14019dfa4  and     dword ptr [rcx+14h], 0FFFFFFDFh
0x14019dfa8  mov     eax, [rsp+0F8h+arg_20]
0x14019dfaf  and     eax, 0FFFFFFDFh
0x14019dfb2  mov     [rsp+0F8h+arg_20], eax
0x14019dfb9  jmp     loc_14019EFFB
0x14019dfbe  mov     al, cs:NtfsStatusDebugFlags
0x14019dfc4  mov     r15d, 0C019003Fh
0x14019dfca  test    al, al
0x14019dfcc  jz      short loc_14019DFDE
0x14019dfce  mov     r8d, 280B14h
0x14019dfd4  mov     edx, r15d
0x14019dfd7  xor     ecx, ecx
0x14019dfd9  call    NtfsStatusTraceAndDebugInternal
0x14019dfde  mov     [rsp+0F8h+var_A0], r15d
0x14019dfe3  jmp     loc_14019F1F4
0x14019dfe8  mov     al, cs:NtfsStatusDebugFlags
0x14019dfee  test    al, al
0x14019dff0  jz      short loc_14019E02F
0x14019dff2  cmp     r15d, 0FFFFFFEDh
0x14019dff6  jnb     short loc_14019E02F
0x14019dff8  cmp     r15d, 0C0000016h
0x14019dfff  jz      short loc_14019E02F
0x14019e001  cmp     r15d, 0C0000011h
0x14019e008  jz      short loc_14019E02F
0x14019e00a  lea     eax, [r15+7FFFFFFBh]
0x14019e011  cmp     eax, esi
0x14019e013  jbe     short loc_14019E02F
0x14019e015  cmp     r15d, 0C00000D8h
0x14019e01c  jz      short loc_14019E02F
0x14019e01e  mov     r8d, 280BDCh
0x14019e024  mov     edx, r15d
0x14019e027  mov     rcx, rbx
0x14019e02a  call    NtfsStatusTraceAndDebugInternal
0x14019e02f  mov     ecx, r15d; Status
0x14019e032  call    cs:__imp_ExRaiseStatus
0x14019e03e  mov     al, cs:NtfsStatusDebugFlags
0x14019e044  mov     ebx, 0C0190044h
0x14019e049  test    al, al
0x14019e04b  jz      short loc_14019E05C
0x14019e04d  mov     r8d, 280C23h
0x14019e053  mov     edx, ebx
0x14019e055  xor     ecx, ecx
0x14019e057  call    NtfsStatusTraceAndDebugInternal
0x14019e05c  mov     [rsp+0F8h+var_A0], ebx
0x14019e060  mov     al, cs:NtfsStatusDebugFlags
0x14019e066  test    al, al
0x14019e068  jz      short loc_14019E079
0x14019e06a  mov     r8d, 280C23h
0x14019e070  mov     edx, ebx
0x14019e072  xor     ecx, ecx
0x14019e074  call    NtfsStatusTraceAndDebugInternal
0x14019e079  mov     ecx, ebx; Status
0x14019e07b  call    cs:__imp_ExRaiseStatus
0x14019e087  mov     al, cs:NtfsStatusDebugFlags
0x14019e08d  test    al, al
0x14019e08f  jz      short loc_14019E0A4
0x14019e091  mov     edx, 0C0000106h
0x14019e096  mov     r8d, 280CCDh
0x14019e09c  mov     rcx, rbx
0x14019e09f  call    NtfsStatusTraceAndDebugInternal
0x14019e0a4  mov     [rsp+0F8h+var_D8], 280CCDh
0x14019e0ad  xor     r9d, r9d
0x14019e0b0  xor     r8d, r8d
0x14019e0b3  mov     edx, 0C0000106h
0x14019e0b8  mov     rcx, rbx
0x14019e0bb  call    NtfsRaiseStatusInternal
0x14019e0c0  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x14019e0c7  call    cs:__imp_ExAllocateFromLookasideListEx
0x14019e0ce  nop     dword ptr [rax+rax+00h]
0x14019e0d3  mov     r15, rax
0x14019e0d6  xor     edx, edx; Val
0x14019e0d8  lea     r8d, [rdx+50h]; Size
0x14019e0dc  mov     rcx, rax; void *
0x14019e0df  call    memset
0x14019e0e4  movups  xmm0, xmmword ptr [r13+80h]
0x14019e0ec  movups  xmmword ptr [r15+10h], xmm0
0x14019e0f1  movups  xmm1, xmmword ptr [r13+90h]
0x14019e0f9  movups  xmmword ptr [r15+20h], xmm1
0x14019e0fe  movups  xmm0, xmmword ptr [r13+0A0h]
0x14019e106  movups  xmmword ptr [r15+30h], xmm0
0x14019e10b  movsd   xmm1, qword ptr [r13+0B0h]
0x14019e114  movsd   qword ptr [r15+40h], xmm1
0x14019e11a  mov     eax, [r13+118h]
0x14019e121  mov     [r15+48h], eax
0x14019e125  lea     rax, [r14+58h]
0x14019e129  mov     rcx, [rax]
0x14019e12c  cmp     [rcx+8], rax
0x14019e130  jz      short loc_14019E139
0x14019e132  mov     ecx, 3
0x14019e137  int     29h; Win8: RtlFailFast(ecx)
0x14019e139  mov     [r15], rcx
0x14019e13c  mov     [r15+8], rax
0x14019e140  mov     [rcx+8], r15
0x14019e144  mov     [rax], r15
0x14019e147  or      dword ptr [r14+4], 8
0x14019e14c  or      [r15+4Eh], si
0x14019e151  xor     r9d, r9d
0x14019e154  jmp     loc_14019EBD1
0x14019e159  mov     rcx, [rsp+0F8h+var_98]
0x14019e15e  lea     rax, [rcx+140h]
0x14019e165  cmp     [rax], rax
0x14019e168  jz      short loc_14019E173
0x14019e16a  lock or dword ptr [r15+8], 100h
0x14019e173  mov     r15, [rsp+0F8h+arg_8]
0x14019e17b  mov     eax, [r15+18h]
0x14019e17f  test    al, 8
0x14019e181  jnz     short loc_14019E194
0x14019e183  mov     r9d, esi
0x14019e186  mov     r8, rdi
0x14019e189  mov     rdx, rcx
0x14019e18c  mov     rcx, rbx
0x14019e18f  call    TxfLogCurrentAttrSizesUndo
0x14019e194  mov     rcx, [r14+88h]; Resource
0x14019e19b  call    cs:__imp_ExReleaseResourceLite
0x14019e1a2  nop     dword ptr [rax+rax+00h]
0x14019e1a7  mov     [rsp+0F8h+arg_0], r12b
0x14019e1af  xor     r9d, r9d
0x14019e1b2  mov     r8b, sil
0x14019e1b5  mov     rdx, rdi
0x14019e1b8  mov     rcx, rbx
0x14019e1bb  call    NtfsDeleteInternalAttributeStream
0x14019e1c0  mov     dl, sil; Wait
0x14019e1c3  mov     rcx, [r14+88h]; Resource
0x14019e1ca  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14019e1d1  nop     dword ptr [rax+rax+00h]
0x14019e1d6  mov     r12b, sil
0x14019e1d9  mov     [rsp+0F8h+arg_0], sil
0x14019e1e1  lock add [rdi+0D4h], esi
0x14019e1e8  mov     [rsp+0F8h+var_88], rdi
0x14019e1ed  xor     eax, eax
0x14019e1ef  cmp     [r15+70h], rax
0x14019e1f3  jnz     loc_14019E2D2
0x14019e1f9  cmp     [rdi+0D0h], eax
0x14019e1ff  jz      short loc_14019E20F
0x14019e201  mov     eax, [rdi+0D4h]
0x14019e207  sub     eax, esi
0x14019e209  cmp     eax, [r15+20h]
0x14019e20d  ja      short loc_14019E230
0x14019e20f  mov     rcx, [rdi+120h]
0x14019e216  add     rcx, 10h; SectionPointer
0x14019e21a  xor     edx, edx; NewFileSize
0x14019e21c  call    cs:__imp_MmCanFileBeTruncated
0x14019e223  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
