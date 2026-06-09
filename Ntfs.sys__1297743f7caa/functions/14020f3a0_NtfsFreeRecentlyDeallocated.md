# NtfsFreeRecentlyDeallocated

- ea: `0x14020f3a0`
- end: `0x140210c08`
- name: `NtfsFreeRecentlyDeallocated`
- size: `6248`
- prototype: ``
- caller_count: `5`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004514c`
- `0x1400cc78c`
- `0x1401cfc68`
- `0x14021ec20`
- `0x14027e418`

## callees

- `0x14000549c`
- `0x140007670`
- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140030a80`
- `0x14003b914`
- `0x14003c184`
- `0x14003c34c`
- `0x14003fae0`
- `0x14004062c`
- `0x140040d48`
- `0x14004a8c0`
- `0x14004c7b8`
- `0x1400592c0`
- `0x140059740`
- `0x1400b75cc`
- `0x14012e540`
- `0x14016aa80`
- `0x1401cf29c`
- `0x14020f3a0`
- `0x140214400`
- `0x14024354c`
- `0x1402774cc`
- `0x140292d60`
- `0x14029aa00`
- `0x14029aaac`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x14020fd97`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14020fd97`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x14020f6f3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140210533`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402b4550`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x14020f6f3`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140210533`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x1402b4550`
- `ntoskrnl!IofCompleteRequest` at `0x140210b9d`
- `ntoskrnl!IofCompleteRequest` at `0x140210b9d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020ff86`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020ff86`
- `ntoskrnl!RtlFindFirstRunClear` at `0x1402101a3`
- `ntoskrnl!RtlFindFirstRunClear` at `0x1402101a3`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x14021084d`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402b47f5`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x14021084d`
- `ntoskrnl!FsRtlResetBaseMcb` at `0x1402b47f5`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x1402108b3`
- `ntoskrnl!FsRtlNumberOfRunsInBaseMcb` at `0x1402108b3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b441e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b486e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b441e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402b486e`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140210566`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402b457b`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140210566`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402b457b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140210838`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b47dc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140210838`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b47dc`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140210822`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b47c6`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140210822`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b47c6`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140210960`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140210960`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140210925`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140210925`
- `ntoskrnl!KeWaitForSingleObject` at `0x140210003`
- `ntoskrnl!KeWaitForSingleObject` at `0x140210003`
- `ntoskrnl!KeInitializeEvent` at `0x14020ff3c`
- `ntoskrnl!KeInitializeEvent` at `0x14020ff3c`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1402102bf`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x1402102bf`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140210644`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402107d4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4674`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4784`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140210644`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402107d4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4674`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b4784`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020fe40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210ae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b48de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020fe40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140210ae5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b48de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14020fe86`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14020fe86`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14021059e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140210729`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b45bd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b46c6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14021059e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140210729`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b45bd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402b46c6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14021069c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402106e7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14021069c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1402106e7`

## pseudocode

```c
void __fastcall NtfsFreeRecentlyDeallocated(int *a1, LONGLONG a2, _QWORD *a3, char a4)
{
  int *v5; // r15
  _QWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 *v8; // rdx
  char *v9; // rdi
  _QWORD *v10; // rcx
  _DWORD *v11; // rbx
  int v12; // r8d
  LONGLONG v13; // r8
  __int64 *v14; // rdx
  __int64 v15; // rdi
  int v16; // r12d
  __int64 v17; // rcx
  ULONG i; // r12d
  __int64 v19; // rdi
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rcx
  int appended; // eax
  PVOID *v24; // rbx
  PVOID *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned __int64 v28; // r9
  __int64 v29; // r10
  unsigned __int64 v30; // rdx
  PVOID *v31; // rcx
  unsigned __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r9
  __int64 v35; // r11
  unsigned __int64 v36; // rax
  PVOID *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  char *v42; // rbx
  int v43; // eax
  __int64 v44; // rcx
  __int64 *v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  PVOID *v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rax
  unsigned __int64 v51; // r9
  __int64 v52; // r10
  unsigned __int64 v53; // rdx
  BOOLEAN v54; // al
  ULONG OutputBufferLength; // ebx
  int *PoolWithTag; // rdi
  unsigned int v57; // eax
  size_t v58; // r8
  int v59; // ecx
  struct _DEVICE_OBJECT *v60; // rsi
  PIRP v61; // rax
  IRP *v62; // rdi
  int v63; // eax
  __int64 v64; // rcx
  unsigned int v65; // ebx
  unsigned int Status; // ebx
  bool v67; // di
  char v68; // si
  ULONG FirstRunClear; // eax
  int v70; // ecx
  ULONG NextForwardRunClear; // ebx
  unsigned __int64 v72; // r8
  __int64 v73; // rdx
  char v74; // r9
  unsigned int v75; // eax
  char *v76; // rsi
  PVOID v77; // rdx
  PVOID v78; // rdx
  ULONG v79; // ebx
  char *v80; // rdi
  _QWORD *v81; // rbx
  LONGLONG v82; // rcx
  __int64 v83; // rcx
  signed __int64 v84; // rdx
  LONGLONG v85; // r8
  signed __int64 v86; // rcx
  signed __int64 v87; // rax
  signed __int64 v88; // rcx
  signed __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rcx
  signed __int64 v93; // rdx
  LONGLONG v94; // r8
  signed __int64 v95; // rcx
  signed __int64 v96; // rax
  signed __int64 v97; // rcx
  signed __int64 v98; // rax
  _QWORD *v99; // rcx
  PVOID *v100; // rax
  int v101; // eax
  char *v102; // rbx
  char *v103; // rax
  __int64 v104; // rcx
  _QWORD *v105; // rax
  __int64 v106; // rcx
  char v107; // [rsp+B8h] [rbp-208h]
  char v108; // [rsp+B9h] [rbp-207h]
  char v109; // [rsp+BAh] [rbp-206h]
  char v110; // [rsp+BBh] [rbp-205h]
  _BYTE v111[4]; // [rsp+BCh] [rbp-204h] BYREF
  int v112; // [rsp+C0h] [rbp-200h]
  __int64 SectorCount; // [rsp+C8h] [rbp-1F8h] BYREF
  PVOID v114; // [rsp+D0h] [rbp-1F0h]
  ULONG StartingIndex; // [rsp+D8h] [rbp-1E8h] BYREF
  bool v116; // [rsp+DCh] [rbp-1E4h]
  ULONG v117; // [rsp+E0h] [rbp-1E0h]
  __int64 Lbn; // [rsp+E8h] [rbp-1D8h] BYREF
  PVOID v119[2]; // [rsp+F0h] [rbp-1D0h] BYREF
  unsigned int v120; // [rsp+100h] [rbp-1C0h]
  PVOID Entry[2]; // [rsp+108h] [rbp-1B8h] BYREF
  int v122; // [rsp+118h] [rbp-1A8h] BYREF
  PVOID v123; // [rsp+120h] [rbp-1A0h] BYREF
  LONGLONG v124[3]; // [rsp+128h] [rbp-198h] BYREF
  ULONG v125; // [rsp+140h] [rbp-180h]
  ULONG v126; // [rsp+144h] [rbp-17Ch]
  PVOID P; // [rsp+148h] [rbp-178h]
  char *v128; // [rsp+150h] [rbp-170h]
  LONGLONG v129; // [rsp+158h] [rbp-168h] BYREF
  __int64 v130; // [rsp+160h] [rbp-160h] BYREF
  unsigned int v131; // [rsp+168h] [rbp-158h] BYREF
  char *v132; // [rsp+170h] [rbp-150h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+178h] [rbp-148h] BYREF
  PVOID *v134; // [rsp+188h] [rbp-138h]
  PVOID *v135; // [rsp+190h] [rbp-130h]
  unsigned __int64 v136; // [rsp+198h] [rbp-128h]
  _QWORD *v137; // [rsp+1A0h] [rbp-120h]
  __int64 Vbn; // [rsp+1A8h] [rbp-118h] BYREF
  _DWORD *v139; // [rsp+1B0h] [rbp-110h]
  LONGLONG v140; // [rsp+1B8h] [rbp-108h]
  PVOID *v141; // [rsp+1C0h] [rbp-100h]
  PVOID *v142; // [rsp+1C8h] [rbp-F8h]
  __int64 v143; // [rsp+1D0h] [rbp-F0h]
  PVOID *v144; // [rsp+1D8h] [rbp-E8h]
  PVOID *v145; // [rsp+1E0h] [rbp-E0h]
  __int64 v146; // [rsp+1E8h] [rbp-D8h]
  PVOID *v147; // [rsp+1F0h] [rbp-D0h]
  PVOID *v148; // [rsp+1F8h] [rbp-C8h]
  __int64 v149; // [rsp+200h] [rbp-C0h]
  _QWORD *v150; // [rsp+208h] [rbp-B8h]
  char *v151; // [rsp+218h] [rbp-A8h]
  char *v152; // [rsp+220h] [rbp-A0h]
  char *v153; // [rsp+228h] [rbp-98h]
  char *v154; // [rsp+230h] [rbp-90h]
  ULONG v155; // [rsp+238h] [rbp-88h]
  struct _KEVENT Event; // [rsp+240h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+258h] [rbp-68h] BYREF
  __int128 InputBuffer; // [rsp+268h] [rbp-58h] BYREF

  v5 = a1;
  v137 = a3;
  v124[2] = (LONGLONG)a1;
  v124[1] = a2;
  v122 = 0;
  *(_OWORD *)Entry = 0;
  *(_OWORD *)v119 = 0;
  if ( (!a1 || (a1[4] & 0x100000LL) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    McTemplateU0piq_EtwWriteTransfer((_DWORD)a1, a2, a2, *a3, a4);
  }
  v6 = (_QWORD *)(a2 + 1608);
  if ( (_QWORD *)*v6 == v6 || (v7 = *(_QWORD *)(a2 + 72)) == 0 )
  {
    if ( (!v5 || (v5[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    {
      v8 = logsup_c7211;
      goto LABEL_301;
    }
    return;
  }
  v140 = a2;
  v150 = (_QWORD *)(a2 + 1608);
  NtfsAcquireExclusiveScbEx(v5, v7, 0);
  if ( (_QWORD *)*v6 == v6 )
  {
    NtfsReleaseFcbEx(v5, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
    if ( (!v5 || (v5[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    {
      v8 = logsup_c7231;
LABEL_301:
      McTemplateU0p_EtwWriteTransfer(a1, v8, a2);
      return;
    }
    return;
  }
  v125 = 0;
  P = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v152 = (char *)(a2 + 1608);
  v151 = (char *)(a2 + 1608);
  v107 = *(_BYTE *)(a2 + 5521);
  v111[1] = v107;
  v9 = *(char **)(a2 + 1616);
  v114 = v9;
  v128 = v9;
  while ( 1 )
  {
LABEL_13:
    v10 = v150;
    if ( (_QWORD *)*v10 == v10 )
      goto LABEL_31;
    if ( v108 )
      goto LABEL_288;
    v11 = v9 + 56;
    v139 = v9 + 56;
    v12 = *((_DWORD *)v9 + 14);
    if ( (v12 & 1) == 0 && (v12 & 0x30) == 0 )
    {
      v10 = (_QWORD *)*((_QWORD *)v9 + 5);
      if ( (!v10 || *v137 <= (__int64)v10) && !a4 )
        goto LABEL_31;
    }
    if ( (*((_DWORD *)v9 + 14) & 1) == 0 )
      break;
    if ( (!v5 || (v5[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer(v10, logsup_c7283, a2, *((_QWORD *)v9 + 6));
    }
    v9 = (char *)*((_QWORD *)v9 + 1);
    v114 = v9;
    v128 = v9;
    if ( v9 == v151 )
    {
      if ( (!v5 || (v5[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
      {
        v13 = a2;
        v14 = logsup_c7298;
        goto LABEL_30;
      }
      goto LABEL_31;
    }
  }
  v154 = v9;
  v153 = v9 + 56;
  if ( v9 != v152 )
  {
    v16 = 0;
    v112 = 0;
    v111[0] = 0;
    v123 = 0;
    v126 = 0;
    Vbn = 0;
    Lbn = 0;
    SectorCount = 0;
    v17 = *((_QWORD *)v9 + 6);
    if ( v17 <= 0 )
    {
      v42 = (char *)v114;
      goto LABEL_209;
    }
    if ( (!v5 || (v5[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0ppiid_EtwWriteTransfer(v17, (unsigned int)logsup_c7352, a2, (_DWORD)v9, v17, *((_QWORD *)v9 + 5), v12);
    }
    for ( i = 0; ; ++i )
    {
      v126 = i;
      if ( !FsRtlGetNextBaseMcbEntry((PBASE_MCB)(v9 + 16), i, &Vbn, &Lbn, &SectorCount) )
      {
LABEL_203:
        v74 = v107;
        goto LABEL_204;
      }
      v19 = Lbn;
      if ( Vbn == Lbn )
        break;
LABEL_202:
      v9 = (char *)v114;
    }
    v17 = SectorCount;
    v20 = SectorCount;
    if ( (!v5 || (v5[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
    {
      McTemplateU0ppdii_EtwWriteTransfer(SectorCount, (unsigned int)logsup_c7375, a2, (_DWORD)v114, i, Lbn, SectorCount);
      v17 = SectorCount;
    }
    if ( (*(_DWORD *)(a2 + 24) & 0x40000) != 0 && (*v11 & 0x10) == 0 )
    {
      if ( (!v5 || (v5[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
      {
        McTemplateU0_EtwWriteTransfer(v17, logsup_c7398);
        LODWORD(v17) = SectorCount;
      }
      Entry[1] = Entry;
      Entry[0] = Entry;
      v109 = 1;
      v119[1] = v119;
      v119[0] = v119;
      v110 = 1;
      v21 = FsLibGroupSubExtentsByDanglingMdl(
              *(_QWORD *)(a2 + 224),
              Lbn,
              v17,
              *(_DWORD *)(a2 + 356),
              (__int64)Entry,
              (__int64)v119,
              0);
      v120 = v21;
      if ( v21 < 0 )
      {
        if ( !v5 || (v22 = (unsigned int)v5[4], (v22 & 0x100000) == 0) )
        {
          if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            McTemplateU0q_EtwWriteTransfer(v22, logsup_c7423, (unsigned int)v21);
        }
        FsLibUninitializeExtentList(v119);
        v119[1] = v119;
        v119[0] = v119;
        FsLibUninitializeExtentList(Entry);
        Entry[1] = Entry;
        Entry[0] = Entry;
        appended = FsLibAppendExtent(Entry, Lbn, SectorCount);
        v120 = appended;
        if ( appended < 0 )
        {
          if ( !v5 || (v17 = (unsigned int)v5[4], (v17 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
              McTemplateU0q_EtwWriteTransfer(v17, logsup_c7441, (unsigned int)appended);
          }
          v108 = 1;
          goto LABEL_207;
        }
      }
      SectorCount = 0;
      v24 = (PVOID *)v119[0];
      if ( v119[0] == v119 )
        goto LABEL_108;
      v144 = v119;
      v25 = (PVOID *)v119[0];
      v145 = (PVOID *)v119[0];
      v26 = 0;
      v146 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      while ( !v25[2 * v27 + 4] )
      {
        v47 = *((unsigned int *)v25 + 4);
        if ( v28 >= v47 || (v27 = v29 + 1, v29 + 1 >= v47) )
        {
          v25 = (PVOID *)*v25;
          if ( v25 == v119 )
          {
            v146 = v26 + 1;
            goto LABEL_108;
          }
          v145 = v25;
          v26 = 0;
          v146 = 0;
          v27 = 0;
          v28 = 0;
          v29 = 0;
        }
        else
        {
          v26 = v29 + 1;
          v146 = v29 + 1;
          v28 = ++v29;
        }
      }
      v30 = 0;
      v134 = v119;
      v31 = 0;
      v135 = 0;
      if ( v119[0] != v119 )
      {
        v31 = (PVOID *)v119[0];
        v135 = (PVOID *)v119[0];
        v30 = 0;
        v136 = 0;
        v32 = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        while ( 1 )
        {
          if ( v31[2 * v33 + 4] )
          {
            Lbn = (__int64)v31[2 * v34 + 3];
            SectorCount = (__int64)v31[2 * v33 + 4];
            break;
          }
          v36 = *((unsigned int *)v31 + 4);
          if ( v32 >= v36 || (v32 = v35 + 1, v35 + 1 >= v36) )
          {
            v37 = (PVOID *)*v31;
            if ( *v31 == v134 )
            {
              v136 = ++v30;
              break;
            }
            v31 = (PVOID *)*v31;
            v135 = v37;
            v30 = 0;
            v32 = 0;
            v33 = 0;
            v34 = 0;
            v35 = 0;
          }
          else
          {
            v30 = v35 + 1;
            v33 = v35 + 1;
            v34 = ++v35;
          }
          v136 = v30;
        }
      }
      if ( v31 && v30 < *((unsigned int *)v31 + 4) )
      {
        v31[2 * v30 + 4] = 0;
        v24 = (PVOID *)v119[0];
      }
      if ( v24 == v119 )
      {
LABEL_108:
        v42 = (char *)v114;
      }
      else
      {
        v141 = v119;
        v142 = v24;
        v38 = 0;
        v143 = 0;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        while ( !v24[2 * v39 + 4] )
        {
          v46 = *((unsigned int *)v24 + 4);
          if ( v40 >= v46 || (v39 = v41 + 1, v41 + 1 >= v46) )
          {
            v24 = (PVOID *)*v24;
            if ( v24 == v119 )
            {
              v143 = v38 + 1;
              goto LABEL_108;
            }
            v142 = v24;
            v38 = 0;
            v143 = 0;
            v39 = 0;
            v40 = 0;
            v41 = 0;
          }
          else
          {
            v38 = v41 + 1;
            v143 = v41 + 1;
            v40 = ++v41;
          }
        }
        v42 = (char *)v114;
        v43 = NtfsAddToMatchingDeallocatedClusters((_DWORD)v5, a2, (unsigned int)v119, (_DWORD)v114, 0, 16);
        v120 = v43;
        if ( v43 < 0 )
        {
          if ( !v5 || (v44 = (unsigned int)v5[4], (v44 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            {
              v45 = logsup_c7500;
              goto LABEL_94;
            }
          }
          goto LABEL_95;
        }
      }
      v48 = (PVOID *)Entry[0];
      if ( Entry[0] == Entry )
      {
LABEL_125:
        if ( (!v5 || (v5[4] & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
        {
          McTemplateU0_EtwWriteTransfer(v48, logsup_c7574);
        }
      }
      else
      {
        v147 = Entry;
        v148 = (PVOID *)Entry[0];
        v49 = 0;
        v149 = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        while ( !v48[2 * v50 + 4] )
        {
          v53 = *((unsigned int *)v48 + 4);
          if ( v51 >= v53 || (v50 = v52 + 1, v52 + 1 >= v53) )
          {
            v48 = (PVOID *)*v48;
            if ( v48 == Entry )
            {
              v149 = v49 + 1;
              goto LABEL_125;
            }
            v148 = v48;
            v49 = 0;
            v149 = 0;
            v50 = 0;
            v51 = 0;
            v52 = 0;
          }
          else
          {
            v49 = v52 + 1;
            v149 = v52 + 1;
            v51 = ++v52;
          }
        }
        if ( (*((_DWORD *)v42 + 14) & 0x20) == 0 )
          _InterlockedIncrement64((volatile signed __int64 *)(a2 + 8792));
        v43 = NtfsAddToMatchingDeallocatedClusters((_DWORD)v5, a2, (unsigned int)Entry, (_DWORD)v42, 1, 32);
        v120 = v43;
        if ( v43 < 0 )
        {
          if ( !v5 || (v44 = (unsigned int)v5[4], (v44 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x400000000LL) != 0 )
            {
              v45 = logsup_c7551;
LABEL_94:
              McTemplateU0q_EtwWriteTransfer(v44, v45, (unsigned int)v43);
            }
          }
LABEL_95:
          NtfsRemoveExtentFromClustersVerifiedForDangling(v44, a2, v42, v19, v20);
          v108 = 1;
          goto LABEL_208;
        }
      }
      FsLibUninitializeExtentList(Entry);
      v109 = 0;
      FsLibUninitializeExtentList(v119);
      v110 = 0;
      v17 = SectorCount;
    }
    if ( (*(_DWORD *)(a2 + 5524) & 1) == 0
      || (v54 = KeAreAllApcsDisabled(), v17 = SectorCount, v54)
      || (unsigned __int64)(SectorCount - 1) > 0xFFFFFFFE )
    {
LABEL_197:
      if ( v17 )
      {
        if ( v107 )
        {
          if ( !(unsigned __int8)NtfsAddCachedRun((_DWORD)v5, a2, Lbn, v17, 2, 1) )
            goto LABEL_203;
        }
        else
        {
          NtfsSendUnusedClustersHint(v5, Lbn, v17, &v123, v111);
        }
      }
      ++v112;
      v11 = v139;
      goto LABEL_202;
    }
    InputBuffer = 0;
    OutputBufferLength = 4 * ((8 * (unsigned int)((unsigned __int64)SectorCount >> 3) + 39) >> 5);
    v155 = OutputBufferLength;
    LODWORD(InputBuffer) = *(_DWORD *)(a2 + 356);
    DWORD1(InputBuffer) = SectorCount;
    *((_QWORD *)&InputBuffer + 1) = Lbn;
    PoolWithTag = (int *)P;
    if ( P )
    {
      v57 = v125;
      if ( v125 >= OutputBufferLength )
      {
LABEL_140:
        if ( !PoolWithTag )
          goto LABEL_197;
        v58 = v57;
        if ( v57 <= 4 )
          v58 = 4;
        memset(PoolWithTag, 0, v58);
        if ( (!v5 || (v5[4] & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0ppd_EtwWriteTransfer(v59, (unsigned int)logsup_c7675, a2, Lbn, SectorCount);
        }
        v60 = *(struct _DEVICE_OBJECT **)(a2 + 224);
        memset(&Event, 0, sizeof(Event));
        IoStatusBlock = 0;
        v131 = 0;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        v61 = IoBuildDeviceIoControlRequest(
                0x564052u,
                v60,
                &InputBuffer,
                0x10u,
                PoolWithTag,
                OutputBufferLength,
                0,
                &Event,
                &IoStatusBlock);
        v62 = v61;
        if ( !v61 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v5, 3221225626LL, 1184656);
          NtfsRaiseStatusInternal((_DWORD)v5, -1073741670, 0, 0, 1184656);
          __debugbreak();
        }
        v61->Tail.Overlay.CurrentStackLocation[-1].Flags = v61->Tail.Overlay.CurrentStackLocation[-1].Flags;
        v63 = NtfsCallStorageDriver(v5, v60, v61, *((_QWORD *)v5 + 13), 0, 0, &v131);
        v65 = v63;
        if ( v63 < 0 )
        {
          v62->IoStatus.Status = v63;
          IofCompleteRequest(v62, 1);
          if ( NtfsStatusDebugFlags
            && v65 < 0xFFFFFFED
            && v65 != -1073741802
            && v65 + 2147483643 > 1
            && v65 != -1073741807
            && v65 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(v5, v65, 1184685);
          }
          NtfsRaiseStatusInternal((_DWORD)v5, v65, 0, 0, 1184685);
          __debugbreak();
          JUMPOUT(0x140210C08LL);
        }
        Status = v131;
        if ( v131 == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          Status = IoStatusBlock.Status;
        }
        if ( Status
          && NtfsStatusDebugFlags
          && (((Status - 294) & 0xFFFFFFFA) != 0 || Status == 295)
          && Status < 0xFFFFFFED
          && Status != -1073741802
          && Status + 2147483643 > 1
          && Status != -1073741807
          && Status != 259
          && Status != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(v5, Status, 1184703);
        }
        v120 = Status;
        if ( (Status & 0x80000000) == 0 )
        {
          *(&BitMapHeader.SizeOfBitMap + 1) = 0;
          StartingIndex = 0;
          v67 = 0;
          v116 = 0;
          v68 = 0;
          v111[0] = 0;
          BitMapHeader.SizeOfBitMap = SectorCount;
          BitMapHeader.Buffer = (PULONG)P;
          FirstRunClear = RtlFindFirstRunClear(&BitMapHeader, &StartingIndex);
          NextForwardRunClear = FirstRunClear;
          if ( !v5 || (v70 = v5[4], (v70 & 0x100000) == 0) )
          {
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
              McTemplateU0ppd_EtwWriteTransfer(v70, (unsigned int)logsup_c7731, a2, Lbn + StartingIndex, FirstRunClear);
          }
          v72 = SectorCount;
          v73 = StartingIndex;
          v74 = v107;
          while ( 1 )
          {
            if ( !NextForwardRunClear )
            {
LABEL_185:
              v17 = 0;
              SectorCount = 0;
              if ( v74 )
              {
                if ( !v67 )
                  goto LABEL_197;
              }
              else if ( !v68 )
              {
                goto LABEL_197;
              }
LABEL_204:
              if ( !v74 )
                NtfsSendUnusedClustersHint(v5, 0, 0, &v123, v111);
LABEL_207:
              v42 = (char *)v114;
LABEL_208:
              v16 = v112;
LABEL_209:
              v76 = (char *)*((_QWORD *)v42 + 1);
              if ( v123 )
              {
                if ( (!v5 || (v5[4] & 0x100000) == 0)
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
                {
                  McTemplateU0pp_EtwWriteTransfer(v17, logsup_c7934, a2, v123);
                }
                NtfsFreeMarkUnusedContext(v123);
                v123 = 0;
              }
              if ( v109 )
              {
                while ( 1 )
                {
                  v77 = Entry[0];
                  if ( Entry[0] == Entry )
                    break;
                  if ( *((PVOID **)Entry[0] + 1) != Entry )
                    goto LABEL_267;
                  v90 = *(_QWORD *)Entry[0];
                  if ( *(PVOID *)(*(_QWORD *)Entry[0] + 8LL) != Entry[0] )
                    goto LABEL_267;
                  Entry[0] = *(PVOID *)Entry[0];
                  *(_QWORD *)(v90 + 8) = Entry;
                  ExFreeToPagedLookasideList(&FsLibExtentArrayLookasideList, v77);
                }
                v109 = 0;
              }
              if ( v110 )
              {
                while ( 1 )
                {
                  v78 = v119[0];
                  if ( v119[0] == v119 )
                    break;
                  if ( *((PVOID **)v119[0] + 1) != v119 )
                    goto LABEL_267;
                  v91 = *(_QWORD *)v119[0];
                  if ( *(PVOID *)(*(_QWORD *)v119[0] + 8LL) != v119[0] )
                    goto LABEL_267;
                  v119[0] = *(PVOID *)v119[0];
                  *(_QWORD *)(v91 + 8) = v119;
                  ExFreeToPagedLookasideList(&FsLibExtentArrayLookasideList, v78);
                }
                v110 = 0;
              }
              if ( v108 )
              {
                v129 = 0;
                v130 = 0;
                v124[0] = 0;
                v79 = 0;
                v117 = 0;
                v80 = v154;
                do
                {
                  FsRtlGetNextBaseMcbEntry((PBASE_MCB)(v80 + 16), v79, &v129, &v130, v124);
                  if ( v129 == v130 )
                  {
                    v81 = v114;
                    FsRtlRemoveBaseMcbEntry((PBASE_MCB)((char *)v114 + 16), v129, v124[0]);
                    v82 = v124[0];
                    *(_QWORD *)(a2 + 312) -= v124[0];
                    v81[6] -= v82;
                    if ( (v81[7] & 0x20) != 0 )
                    {
                      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                      *(_QWORD *)(a2 + 328) -= v124[0];
                      v83 = *(_QWORD *)(a2 + 328);
                      if ( v83 < *(_QWORD *)(a2 + 8312) )
                        *(_QWORD *)(a2 + 8312) = v83;
                      v84 = *(_QWORD *)(a2 + 304) - (v83 >> 8) - *(_QWORD *)(a2 + 6368) - v83;
                      if ( v84 <= 0 )
                        v84 = 0;
                      v85 = v140;
                      do
                      {
                        v86 = *(_QWORD *)(v85 + 8344);
                        v87 = v86;
                        if ( v84 < v86 )
                          v87 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8344), v84, v86);
                      }
                      while ( v87 != v86 );
                      do
                      {
                        v88 = *(_QWORD *)(v85 + 8352);
                        v89 = v88;
                        if ( v84 > v88 )
                          v89 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8352), v84, v88);
                      }
                      while ( v89 != v88 );
                      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                    }
                    v112 = --v16;
                    v79 = 1;
                  }
                  else
                  {
                    ++v79;
                  }
                  v117 = v79;
                }
                while ( v16 > 0 );
              }
              else
              {
                *(_QWORD *)(a2 + 312) -= *((_QWORD *)v42 + 6);
                if ( (*((_DWORD *)v42 + 14) & 0x20) != 0 )
                {
                  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                  *(_QWORD *)(a2 + 328) -= *((_QWORD *)v114 + 6);
                  v92 = *(_QWORD *)(a2 + 328);
                  if ( v92 < *(_QWORD *)(a2 + 8312) )
                    *(_QWORD *)(a2 + 8312) = v92;
                  v93 = *(_QWORD *)(a2 + 304) - (v92 >> 8) - *(_QWORD *)(a2 + 6368) - v92;
                  if ( v93 <= 0 )
                    v93 = 0;
                  v94 = v140;
                  do
                  {
                    v95 = *(_QWORD *)(v94 + 8344);
                    v96 = v95;
                    if ( v93 < v95 )
                      v96 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8344), v93, v95);
                  }
                  while ( v96 != v95 );
                  do
                  {
                    v97 = *(_QWORD *)(v94 + 8352);
                    v98 = v97;
                    if ( v93 > v97 )
                      v98 = _InterlockedCompareExchange64((volatile signed __int64 *)(a2 + 8352), v93, v97);
                  }
                  while ( v98 != v97 );
                  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
                  v42 = (char *)v114;
                }
                v99 = *(_QWORD **)v42;
                if ( *(char **)(*(_QWORD *)v42 + 8LL) != v42 || (v100 = (PVOID *)*((_QWORD *)v42 + 1), *v100 != v42) )
LABEL_267:
                  __fastfail(3u);
                *v100 = v99;
                v99[1] = v100;
                if ( v42 == (char *)(a2 + 1624) || v42 == (char *)(a2 + 1688) )
                {
                  *(_QWORD *)v42 = 0;
                  FsRtlResetBaseMcb((PBASE_MCB)(v42 + 16));
                }
                else
                {
                  FsRtlUninitializeBaseMcb((PBASE_MCB)(v42 + 16));
                  ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v42);
                }
              }
              v9 = v76;
              v114 = v76;
              v128 = v76;
              goto LABEL_13;
            }
            if ( (unsigned int)v73 + NextForwardRunClear <= v72 )
            {
              v75 = NextForwardRunClear;
            }
            else
            {
              if ( (unsigned int)v73 >= v72 )
                goto LABEL_185;
              v75 = v72 - v73;
            }
            if ( !v74 )
              break;
            if ( !v67 )
            {
              v67 = (unsigned __int8)NtfsAddCachedRun((_DWORD)v5, a2, (int)Lbn + (int)v73, v75, 2, 1) == 0;
              v116 = v67;
              goto LABEL_177;
            }
LABEL_178:
            v73 = NextForwardRunClear + (unsigned int)v73;
            StartingIndex = v73;
            if ( (unsigned int)v73 >= v72 )
            {
              NextForwardRunClear = 0;
            }
            else
            {
              NextForwardRunClear = RtlFindNextForwardRunClear(&BitMapHeader, v73, &StartingIndex);
              v72 = SectorCount;
              v73 = StartingIndex;
              v74 = v107;
            }
            if ( v74 )
            {
              if ( v67 )
                goto LABEL_185;
            }
            else if ( v68 )
            {
              goto LABEL_185;
            }
          }
          NtfsSendUnusedClustersHint(v5, Lbn + v73, v75, &v123, v111);
          v68 = v111[0];
LABEL_177:
          v74 = v107;
          LODWORD(v73) = StartingIndex;
          v72 = SectorCount;
          goto LABEL_178;
        }
        if ( Status != -1073741808
          && Status != -1073741822
          && (!v5 || (v5[4] & 0x100000) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 1) != 0 )
        {
          McTemplateU0pd_EtwWriteTransfer(v64, logsup_c7850, a2, Status);
        }
        *(_DWORD *)(a2 + 5524) &= ~1u;
        v17 = SectorCount;
        goto LABEL_197;
      }
      if ( P != &v122 )
      {
        ExFreePoolWithTag(P, 0);
        P = 0;
        v17 = SectorCount;
      }
    }
    v57 = OutputBufferLength;
    v125 = OutputBufferLength;
    if ( OutputBufferLength > 4 )
    {
      PoolWithTag = (int *)ExAllocatePoolWithTag((POOL_TYPE)512, OutputBufferLength, 0x4C46744Eu);
      P = PoolWithTag;
      v17 = SectorCount;
      v57 = v125;
    }
    else
    {
      PoolWithTag = &v122;
      P = &v122;
    }
    goto LABEL_140;
  }
  if ( (!v5 || (v5[4] & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    v13 = a2;
    v14 = logsup_c7313;
LABEL_30:
    McTemplateU0p_EtwWriteTransfer(v10, v14, v13);
  }
LABEL_31:
  if ( !v108 )
  {
    v15 = *(_QWORD *)(a2 + 1608);
    if ( v15 == a2 + 1608 )
    {
      v15 = 0;
    }
    else if ( v15 )
    {
      if ( FsRtlNumberOfRunsInBaseMcb((PBASE_MCB)(v15 + 16)) <= 0x200 )
      {
        v101 = *(_DWORD *)(v15 + 56);
        if ( (v101 & 1) == 0 && (v101 & 0x30) == 0 && !*(_QWORD *)(v15 + 48) )
          goto LABEL_288;
      }
    }
    v132 = 0;
    v102 = (char *)(a2 + 1624);
    if ( *(_QWORD *)(a2 + 1624) )
    {
      v102 = 0;
      if ( !*(_QWORD *)(a2 + 1688) )
        v102 = (char *)(a2 + 1688);
    }
    v132 = v102;
    if ( v102 )
    {
      *((_QWORD *)v102 + 5) = 0;
      *((_DWORD *)v102 + 14) = 0;
      *((_QWORD *)v102 + 6) = 0;
    }
    else
    {
      v103 = (char *)ExAllocateFromLookasideListEx(&NtfsDeallocatedClustersLookasideList);
      v102 = v103;
      v132 = v103;
      if ( v103 )
      {
        *(_OWORD *)v103 = 0;
        *((_OWORD *)v103 + 1) = 0;
        *((_OWORD *)v103 + 2) = 0;
        *((_OWORD *)v103 + 3) = 0;
        FsRtlInitializeBaseMcbEx((PBASE_MCB)(v103 + 16), PoolType, 1u);
      }
    }
    if ( v102 )
    {
      if ( v15 )
      {
        *(_QWORD *)(v15 + 40) = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
        *((_QWORD *)v5 + 2) |= 0x4000000uLL;
        if ( (*((_QWORD *)v5 + 2) & 0x100000LL) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000000LL) != 0 )
        {
          McTemplateU0pp_EtwWriteTransfer(v104, strucsup_c17526, v15, *(_QWORD *)(v15 + 40));
        }
      }
      v105 = (_QWORD *)(a2 + 1608);
      v106 = *(_QWORD *)(a2 + 1608);
      if ( *(_QWORD *)(v106 + 8) != a2 + 1608 )
        __fastfail(3u);
      *(_QWORD *)v102 = v106;
      *((_QWORD *)v102 + 1) = v105;
      *(_QWORD *)(v106 + 8) = v102;
      *v105 = v102;
    }
  }
LABEL_288:
  if ( (v5[4] & 0x200LL) != 0 && (*(_DWORD *)(a2 + 5524) & 6) == 2 )
  {
    NtfsPostSpecial((_DWORD)v5, *((_QWORD *)v5 + 13), (unsigned int)NtfsBackgroundBitmapScanWorker, 0, 32);
    *(_DWORD *)(a2 + 5524) |= 4u;
  }
  NtfsReleaseFcbEx(v5, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
  if ( P )
  {
    a1 = &v122;
    if ( P != &v122 )
      ExFreePoolWithTag(P, 0);
  }
  if ( (v5[4] & 0x100000LL) == 0
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
  {
    v8 = logsup_c8159;
    goto LABEL_301;
  }
}

```

## disassembly

```asm
0x14020f3a0  mov     [rsp+arg_18], r9b
0x14020f3a5  push    rbx
0x14020f3a6  push    rsi
0x14020f3a7  push    rdi
0x14020f3a8  push    r12
0x14020f3aa  push    r13
0x14020f3ac  push    r14
0x14020f3ae  push    r15
0x14020f3b0  sub     rsp, 220h
0x14020f3b7  mov     rax, cs:__security_cookie
0x14020f3be  xor     rax, rsp
0x14020f3c1  mov     [rsp+258h+var_48], rax
0x14020f3c9  mov     r13, rdx
0x14020f3cc  mov     r15, rcx
0x14020f3cf  mov     [rsp+258h+var_120], r8
0x14020f3d7  mov     [rsp+258h+var_188], rcx
0x14020f3df  mov     [rsp+258h+var_190], rdx
0x14020f3e7  xor     r14d, r14d
0x14020f3ea  mov     [rsp+258h+var_1A8], r14d
0x14020f3f2  xorps   xmm0, xmm0
0x14020f3f5  movups  xmmword ptr [rsp+258h+Entry], xmm0
0x14020f3fd  xorps   xmm1, xmm1
0x14020f400  movups  xmmword ptr [rsp+258h+var_1D0], xmm1
0x14020f408  test    rcx, rcx
0x14020f40b  jz      short loc_14020F417
0x14020f40d  mov     eax, [rcx+10h]
0x14020f410  bt      rax, 14h
0x14020f415  jb      short loc_14020F437
0x14020f417  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f41e  jz      short loc_14020F437
0x14020f420  movzx   eax, [rsp+258h+arg_18]
0x14020f428  mov     dword ptr [rsp+258h+SectorCount], eax
0x14020f42c  mov     r9, [r8]
0x14020f42f  mov     r8, r13
0x14020f432  call    McTemplateU0piq_EtwWriteTransfer
0x14020f437  lea     rdi, [r13+648h]
0x14020f43e  cmp     [rdi], rdi
0x14020f441  jz      loc_140210B0E
0x14020f447  mov     rdx, [r13+48h]
0x14020f44b  test    rdx, rdx
0x14020f44e  jz      loc_140210B0E
0x14020f454  mov     [rsp+258h+var_108], r13
0x14020f45c  mov     [rsp+258h+var_B8], rdi
0x14020f464  xor     r8d, r8d
0x14020f467  mov     rcx, r15
0x14020f46a  call    NtfsAcquireExclusiveScbEx
0x14020f46f  cmp     [rdi], rdi
0x14020f472  jnz     short loc_14020F4B7
0x14020f474  mov     rdx, [r13+48h]
0x14020f478  xor     r8d, r8d
0x14020f47b  mov     rdx, [rdx+0B8h]
0x14020f482  mov     rcx, r15
0x14020f485  call    NtfsReleaseFcbEx
0x14020f48a  test    r15, r15
0x14020f48d  jz      short loc_14020F49E
0x14020f48f  mov     eax, [r15+10h]
0x14020f493  bt      rax, 14h
0x14020f498  jb      loc_140210B36
0x14020f49e  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f4a5  jz      loc_140210B36
0x14020f4ab  lea     rdx, logsup_c7231
0x14020f4b2  jmp     loc_140210B2E
0x14020f4b7  mov     [rsp+258h+var_180], r14d
0x14020f4bf  mov     [rsp+258h+P], r14
0x14020f4c7  mov     [rsp+258h+var_207], r14b
0x14020f4cc  mov     [rsp+258h+var_206], r14b
0x14020f4d1  mov     [rsp+258h+var_205], r14b
0x14020f4d6  mov     [rsp+258h+var_A0], rdi
0x14020f4de  mov     [rsp+258h+var_A8], rdi
0x14020f4e6  movzx   edx, byte ptr [r13+1591h]
0x14020f4ee  mov     [rsp+258h+var_208], dl
0x14020f4f2  mov     [rsp+258h+var_203], dl
0x14020f4f6  mov     rdi, [r13+650h]
0x14020f4fd  mov     [rsp+258h+var_1F0], rdi
0x14020f502  mov     [rsp+258h+var_170], rdi
0x14020f50a  mov     esi, 1
0x14020f50f  nop
0x14020f510  mov     rcx, [rsp+258h+var_B8]
0x14020f518  cmp     [rcx], rcx
0x14020f51b  jz      loc_14020F5E0
0x14020f521  cmp     [rsp+258h+var_207], 0
0x14020f526  jnz     loc_1402109EB
0x14020f52c  lea     rbx, [rdi+38h]
0x14020f530  mov     [rsp+258h+var_110], rbx
0x14020f538  mov     r8d, [rbx]
0x14020f53b  mov     edx, r8d
0x14020f53e  and     edx, 1
0x14020f541  jnz     short loc_14020F569
0x14020f543  test    r8b, 30h
0x14020f547  jnz     short loc_14020F569
0x14020f549  mov     rcx, [rdi+28h]
0x14020f54d  test    rcx, rcx
0x14020f550  jz      short loc_14020F55F
0x14020f552  mov     rax, [rsp+258h+var_120]
0x14020f55a  cmp     [rax], rcx
0x14020f55d  jg      short loc_14020F569
0x14020f55f  cmp     [rsp+258h+arg_18], 0
0x14020f567  jz      short loc_14020F5E0
0x14020f569  test    edx, edx
0x14020f56b  jz      loc_14020F60B
0x14020f571  test    r15, r15
0x14020f574  jz      short loc_14020F581
0x14020f576  mov     eax, [r15+10h]
0x14020f57a  bt      rax, 14h
0x14020f57f  jb      short loc_14020F59D
0x14020f581  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14020f588  jz      short loc_14020F59D
0x14020f58a  mov     r9, [rdi+30h]
0x14020f58e  mov     r8, r13
0x14020f591  lea     rdx, logsup_c7283
0x14020f598  call    McTemplateU0pp_EtwWriteTransfer
0x14020f59d  mov     rdi, [rdi+8]
0x14020f5a1  mov     [rsp+258h+var_1F0], rdi
0x14020f5a6  mov     [rsp+258h+var_170], rdi
0x14020f5ae  cmp     rdi, [rsp+258h+var_A8]
0x14020f5b6  jnz     short loc_14020F606
0x14020f5b8  test    r15, r15
0x14020f5bb  jz      short loc_14020F5C8
0x14020f5bd  mov     eax, [r15+10h]
0x14020f5c1  bt      rax, 14h
0x14020f5c6  jb      short loc_14020F5E0
0x14020f5c8  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f5cf  jz      short loc_14020F5E0
0x14020f5d1  mov     r8, r13
0x14020f5d4  lea     rdx, logsup_c7298
0x14020f5db  call    McTemplateU0p_EtwWriteTransfer
0x14020f5e0  cmp     [rsp+258h+var_207], 0
0x14020f5e5  jnz     loc_1402109EB
0x14020f5eb  lea     rax, [r13+648h]
0x14020f5f2  mov     rdi, [rax]
0x14020f5f5  cmp     rdi, rax
0x14020f5f8  jnz     loc_1402108AA
0x14020f5fe  mov     rdi, r14
0x14020f601  jmp     loc_1402108DC
0x14020f606  jmp     loc_14020F510
0x14020f60b  mov     [rsp+258h+var_90], rdi
0x14020f613  mov     [rsp+258h+var_98], rbx
0x14020f61b  cmp     rdi, [rsp+258h+var_A0]
0x14020f623  jnz     short loc_14020F64A
0x14020f625  test    r15, r15
0x14020f628  jz      short loc_14020F635
0x14020f62a  mov     eax, [r15+10h]
0x14020f62e  bt      rax, 14h
0x14020f633  jb      short loc_14020F5E0
0x14020f635  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x14020f63c  jz      short loc_14020F5E0
0x14020f63e  mov     r8, r13
0x14020f641  lea     rdx, logsup_c7313
0x14020f648  jmp     short loc_14020F5DB
0x14020f64a  mov     r12d, r14d
0x14020f64d  mov     [rsp+258h+var_200], r14d
0x14020f652  mov     [rsp+258h+var_204], 0
0x14020f657  mov     [rsp+258h+var_1A0], r14
0x14020f65f  mov     [rsp+258h+var_17C], r14d
0x14020f667  mov     [rsp+258h+Vbn], r14
0x14020f66f  mov     [rsp+258h+Lbn], r14
0x14020f677  mov     [rsp+258h+var_1F8], r14
0x14020f67c  mov     rcx, [rdi+30h]
0x14020f680  test    rcx, rcx
0x14020f683  jle     loc_140210412
0x14020f689  test    r15, r15
0x14020f68c  jz      short loc_14020F699
0x14020f68e  mov     eax, [r15+10h]
0x14020f692  bt      rax, 14h
0x14020f697  jb      short loc_14020F6C7
0x14020f699  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14020f6a0  jz      short loc_14020F6C7
0x14020f6a2  mov     dword ptr [rsp+258h+InternalDeviceIoControl], r8d
0x14020f6a7  mov     rax, [rdi+28h]
0x14020f6ab  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f6b0  mov     [rsp+258h+SectorCount], rcx
0x14020f6b5  mov     r9, rdi
0x14020f6b8  mov     r8, r13
0x14020f6bb  lea     rdx, logsup_c7352
0x14020f6c2  call    McTemplateU0ppiid_EtwWriteTransfer
0x14020f6c7  mov     r12d, r14d
0x14020f6ca  mov     [rsp+258h+var_17C], r12d
0x14020f6d2  lea     rcx, [rdi+10h]; Mcb
0x14020f6d6  lea     rax, [rsp+258h+var_1F8]
0x14020f6db  mov     [rsp+258h+SectorCount], rax; SectorCount
0x14020f6e0  lea     r9, [rsp+258h+Lbn]; Lbn
0x14020f6e8  lea     r8, [rsp+258h+Vbn]; Vbn
0x14020f6f0  mov     edx, r12d; RunIndex
0x14020f6f3  call    cs:__imp_FsRtlGetNextBaseMcbEntry
0x14020f6fa  nop     dword ptr [rax+rax+00h]
0x14020f6ff  test    al, al
0x14020f701  jz      loc_1402103E6
0x14020f707  mov     rdi, [rsp+258h+Lbn]
0x14020f70f  cmp     [rsp+258h+Vbn], rdi
0x14020f717  jnz     loc_1402103D9
0x14020f71d  mov     rcx, [rsp+258h+var_1F8]
0x14020f722  mov     rsi, rcx
0x14020f725  test    r15, r15
0x14020f728  jz      short loc_14020F735
0x14020f72a  mov     eax, [r15+10h]
0x14020f72e  bt      rax, 14h
0x14020f733  jb      short loc_14020F76E
0x14020f735  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 2
0x14020f73c  jz      short loc_14020F76E
0x14020f73e  mov     qword ptr [rsp+258h+InternalDeviceIoControl], rcx
0x14020f743  mov     rax, [rsp+258h+Lbn]
0x14020f74b  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f750  mov     dword ptr [rsp+258h+SectorCount], r12d
0x14020f755  mov     r9, [rsp+258h+var_1F0]
0x14020f75a  mov     r8, r13
0x14020f75d  lea     rdx, logsup_c7375
0x14020f764  call    McTemplateU0ppdii_EtwWriteTransfer
0x14020f769  mov     rcx, [rsp+258h+var_1F8]
0x14020f76e  test    dword ptr [r13+18h], 40000h
0x14020f776  jz      loc_14020FD88
0x14020f77c  mov     eax, [rbx]
0x14020f77e  test    al, 10h
0x14020f780  jnz     loc_14020FD88
0x14020f786  test    r15, r15
0x14020f789  jz      short loc_14020F796
0x14020f78b  mov     eax, [r15+10h]
0x14020f78f  bt      rax, 14h
0x14020f794  jb      short loc_14020F7B0
0x14020f796  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 2
0x14020f79d  jz      short loc_14020F7B0
0x14020f79f  lea     rdx, logsup_c7398
0x14020f7a6  call    McTemplateU0_EtwWriteTransfer
0x14020f7ab  mov     rcx, [rsp+258h+var_1F8]
0x14020f7b0  lea     rax, [rsp+258h+Entry]
0x14020f7b8  mov     [rsp+258h+Entry+8], rax
0x14020f7c0  lea     rax, [rsp+258h+Entry]
0x14020f7c8  mov     [rsp+258h+Entry], rax
0x14020f7d0  mov     [rsp+258h+var_206], 1
0x14020f7d5  lea     rax, [rsp+258h+var_1D0]
0x14020f7dd  mov     [rsp+258h+var_1D0+8], rax
0x14020f7e5  lea     rax, [rsp+258h+var_1D0]
0x14020f7ed  mov     [rsp+258h+var_1D0], rax
0x14020f7f5  mov     [rsp+258h+var_205], 1
0x14020f7fa  mov     qword ptr [rsp+258h+InternalDeviceIoControl], r14
0x14020f7ff  lea     rax, [rsp+258h+var_1D0]
0x14020f807  mov     qword ptr [rsp+258h+OutputBufferLength], rax
0x14020f80c  lea     rax, [rsp+258h+Entry]
0x14020f814  mov     [rsp+258h+SectorCount], rax
0x14020f819  mov     r9d, [r13+164h]
0x14020f820  mov     r8, rcx
0x14020f823  mov     rdx, [rsp+258h+Lbn]
0x14020f82b  mov     rcx, [r13+0E0h]
0x14020f832  call    FsLibGroupSubExtentsByDanglingMdl
0x14020f837  mov     [rsp+258h+var_1C0], eax
0x14020f83e  test    eax, eax
0x14020f840  jns     loc_14020F91F
0x14020f846  test    r15, r15
0x14020f849  jz      short loc_14020F856
0x14020f84b  mov     ecx, [r15+10h]
0x14020f84f  bt      rcx, 14h
0x14020f854  jb      short loc_14020F86E
0x14020f856  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 4
0x14020f85d  jz      short loc_14020F86E
0x14020f85f  mov     r8d, eax
0x14020f862  lea     rdx, logsup_c7423
0x14020f869  call    McTemplateU0q_EtwWriteTransfer
0x14020f86e  lea     rcx, [rsp+258h+var_1D0]
0x14020f876  call    FsLibUninitializeExtentList
0x14020f87b  lea     rax, [rsp+258h+var_1D0]
0x14020f883  mov     [rsp+258h+var_1D0+8], rax
0x14020f88b  lea     rax, [rsp+258h+var_1D0]
0x14020f893  mov     [rsp+258h+var_1D0], rax
0x14020f89b  lea     rcx, [rsp+258h+Entry]
0x14020f8a3  call    FsLibUninitializeExtentList
0x14020f8a8  lea     rax, [rsp+258h+Entry]
0x14020f8b0  mov     [rsp+258h+Entry+8], rax
0x14020f8b8  lea     rax, [rsp+258h+Entry]
0x14020f8c0  mov     [rsp+258h+Entry], rax
0x14020f8c8  mov     r8, [rsp+258h+var_1F8]
0x14020f8cd  mov     rdx, [rsp+258h+Lbn]
0x14020f8d5  lea     rcx, [rsp+258h+Entry]
0x14020f8dd  call    FsLibAppendExtent
0x14020f8e2  mov     [rsp+258h+var_1C0], eax
0x14020f8e9  test    eax, eax
0x14020f8eb  jns     short loc_14020F91F
0x14020f8ed  test    r15, r15
0x14020f8f0  jz      short loc_14020F8FD
0x14020f8f2  mov     ecx, [r15+10h]
0x14020f8f6  bt      rcx, 14h
0x14020f8fb  jb      short loc_14020F915
0x14020f8fd  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+4, 4
0x14020f904  jz      short loc_14020F915
0x14020f906  mov     r8d, eax
0x14020f909  lea     rdx, logsup_c7441
0x14020f910  call    McTemplateU0q_EtwWriteTransfer
0x14020f915  mov     [rsp+258h+var_207], 1
0x14020f91a  jmp     loc_140210419
0x14020f91f  mov     [rsp+258h+var_1F8], r14
0x14020f924  lea     rax, [rsp+258h+var_1D0]
0x14020f92c  mov     rbx, [rsp+258h+var_1D0]
0x14020f934  cmp     rbx, rax
0x14020f937  jz      loc_14020FC10
0x14020f93d  lea     r11, [rsp+258h+var_1D0]
0x14020f945  mov     [rsp+258h+var_E8], r11
0x14020f94d  mov     [rsp+258h+var_E0], r14
0x14020f955  mov     rcx, rbx
0x14020f958  mov     [rsp+258h+var_E0], rbx
0x14020f960  mov     r8, r14
0x14020f963  mov     [rsp+258h+var_D8], r14
0x14020f96b  mov     rax, r14
  ... truncated ...
```
