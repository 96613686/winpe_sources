# NtfsDismountVolume

- ea: `0x14029dd80`
- end: `0x14029ef7c`
- name: `NtfsDismountVolume`
- size: `4604`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401f58e0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x140010be0`
- `0x14001c910`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021e60`
- `0x14003e734`
- `0x14003fe78`
- `0x14004487c`
- `0x14004514c`
- `0x1400477cc`
- `0x140047a3c`
- `0x14004839c`
- `0x14004a1e8`
- `0x140055094`
- `0x1400592a4`
- `0x1400592c0`
- `0x1400b7d0c`
- `0x1400d44bc`
- `0x1400dfe70`
- `0x1400f24b0`
- `0x140138c70`
- `0x1401cb314`
- `0x1401cecc4`
- `0x1401d29ac`
- `0x1401d2c84`
- `0x14021e8d4`
- `0x1402308d8`
- `0x140299478`
- `0x14029dd80`
- `0x14029f5fc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14029e7ff`
- `ntoskrnl!KeSetEvent` at `0x1402c1661`
- `ntoskrnl!KeSetEvent` at `0x14029e7ff`
- `ntoskrnl!KeSetEvent` at `0x1402c1661`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029e304`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029ed1e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402c1984`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029e304`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14029ed1e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402c1984`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029df52`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e2e8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e310`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029ed34`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029df52`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e2e8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029e310`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14029ed34`
- `ntoskrnl!FsRtlDismountComplete` at `0x14029ead5`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402c16b0`
- `ntoskrnl!FsRtlDismountComplete` at `0x14029ead5`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402c16b0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029e512`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029ed05`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c15f6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c196b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029e512`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14029ed05`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c15f6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c196b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14029dea1`
- `ntoskrnl!IoGetActivityIdThread` at `0x14029dea1`
- `ntoskrnl!KeClearEvent` at `0x14029e78b`
- `ntoskrnl!KeClearEvent` at `0x14029e78b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e125`
- `ntoskrnl!KeWaitForSingleObject` at `0x14029e125`

## pseudocode

```c
__int64 __fastcall NtfsDismountVolume(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *ActivityIdThread; // rax
  __int64 v8; // rsi
  int *v9; // r12
  __int64 v10; // rax
  unsigned __int16 v11; // dx
  char v12; // r13
  const WCHAR *v13; // r13
  const WCHAR *v14; // rbx
  int v15; // r10d
  int v16; // r11d
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rcx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // edx
  ULONGLONG v25; // rbx
  ULONGLONG v26; // rbx
  __int64 v27; // r9
  const WCHAR *v28; // rcx
  int v29; // r10d
  int v30; // r11d
  const WCHAR *v31; // rcx
  const WCHAR *v32; // rcx
  const WCHAR *v33; // rcx
  const WCHAR *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // edx
  __int64 v38; // r8
  int v39; // eax
  __int64 v40; // r8
  __int64 v41; // rcx
  int v42; // r9d
  int v43; // ecx
  int v44; // eax
  __int64 v45; // rcx
  int v46; // r9d
  __int64 v47; // rdx
  unsigned int v48; // eax
  __int64 v49; // r8
  int v50; // r10d
  int v51; // r11d
  int v52; // ebx
  __int64 v53; // rdx
  unsigned int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // rsi
  __int64 v57; // rcx
  __int64 v58; // r14
  __int64 v59; // r9
  int v60; // r8d
  const WCHAR *v61; // r13
  const WCHAR *v62; // r12
  int v63; // r11d
  int v64; // r15d
  const WCHAR *v65; // rcx
  const WCHAR *v66; // rcx
  const WCHAR *v67; // rcx
  const WCHAR *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // r10
  int v71; // r10d
  ULONGLONG v72; // rsi
  __int16 QuadPart; // r9
  __int64 v75; // rax
  unsigned __int16 v76; // cx
  __int64 v77; // [rsp+B8h] [rbp-238h] BYREF
  __int64 v78; // [rsp+140h] [rbp-1B0h]
  char v79; // [rsp+158h] [rbp-198h] BYREF
  char v80; // [rsp+159h] [rbp-197h]
  char v81; // [rsp+15Ah] [rbp-196h]
  char v82; // [rsp+15Bh] [rbp-195h]
  char v83; // [rsp+15Ch] [rbp-194h]
  int v84; // [rsp+160h] [rbp-190h]
  const WCHAR *v85; // [rsp+168h] [rbp-188h]
  __int64 v86; // [rsp+170h] [rbp-180h]
  __int64 v87; // [rsp+178h] [rbp-178h] BYREF
  const WCHAR *v88; // [rsp+180h] [rbp-170h]
  const WCHAR *v89; // [rsp+188h] [rbp-168h]
  PFILE_OBJECT FileObject; // [rsp+190h] [rbp-160h]
  PFILE_OBJECT v91; // [rsp+198h] [rbp-158h] BYREF
  const WCHAR *v92; // [rsp+1A0h] [rbp-150h]
  ULONGLONG UnbiasedInterruptTime; // [rsp+1A8h] [rbp-148h]
  __int64 v94[2]; // [rsp+1B0h] [rbp-140h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+1C0h] [rbp-130h] BYREF
  int v96; // [rsp+1D0h] [rbp-120h]
  __int64 v97; // [rsp+1D8h] [rbp-118h] BYREF
  struct _UNICODE_STRING v98; // [rsp+1E0h] [rbp-110h] BYREF
  __int64 v99[2]; // [rsp+1F0h] [rbp-100h] BYREF
  __int64 v100; // [rsp+200h] [rbp-F0h]
  __int64 *v101; // [rsp+208h] [rbp-E8h]
  __int128 v102; // [rsp+210h] [rbp-E0h] BYREF
  __int64 v103; // [rsp+220h] [rbp-D0h]
  __int128 v104; // [rsp+228h] [rbp-C8h] BYREF
  __int128 v105; // [rsp+238h] [rbp-B8h] BYREF
  char v106[8]; // [rsp+248h] [rbp-A8h] BYREF

  v101 = &v77;
  v86 = a1;
  v100 = a2;
  v87 = 0;
  v91 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v97 = 0;
  UnbiasedInterruptTime = 0;
  v83 = 0;
  FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a2 + 184) + 48LL);
  NtfsDecodeFileObject(a1, (_DWORD)FileObject, (unsigned int)&v87, (unsigned int)v94, (__int64)v99, (__int64)&v91, 1);
  if ( a1 && (v4 = *(_QWORD **)(a1 + 120)) != 0 )
  {
    *((_QWORD *)&v102 + 1) = *v4;
    v103 = v4[1];
    *(_QWORD *)&v102 = (char *)&v102 + 8;
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v4);
    if ( ActivityIdThread )
    {
      *((_QWORD *)&v102 + 1) = *ActivityIdThread;
      v103 = ActivityIdThread[1];
      *(_QWORD *)&v102 = (char *)&v102 + 8;
    }
    else
    {
      *(_QWORD *)&v102 = 0;
    }
  }
  v8 = v87;
  v105 = *(_OWORD *)(v87 + 8512);
  v97 = *(_QWORD *)(v87 + 8528);
  LODWORD(v85) = *(_DWORD *)(v87 + 8536);
  v96 = (int)v85;
  if ( (*(_DWORD *)(v87 + 24) & 4) != 0 )
    v104 = *(_OWORD *)(v87 + 7824);
  else
    v104 = 0;
  v9 = (int *)(a1 + 12);
  if ( (*(_DWORD *)(a1 + 12) & 0x40000) == 0 )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryDismountBegin(
        (unsigned int)&v102,
        (unsigned int)&v104,
        (unsigned int)&v105,
        (unsigned int)&v97,
        (_DWORD)v85,
        (*v9 & 1) == 0);
    v83 = 1;
  }
  if ( (*v9 & 0x40000) == 0 )
  {
    if ( dword_140092174
      && (unsigned __int8)(byte_140092178 - 1) > 2u
      && (qword_140092160 & 0x8000000) != 0
      && (qword_140092168 & 0x8000000) == qword_140092168
      && (*(_DWORD *)(a1 + 16) & 0x100000) == 0 )
    {
      v10 = *(_QWORD *)(v8 + 248);
      v11 = *(_WORD *)(v10 + 6);
      if ( v11 > 0x40u || (v11 & 1) != 0 )
        v11 = 0;
      *(_DWORD *)(&UnicodeString.MaximumLength + 1) = 0;
      v5 = 0;
      if ( v11 )
        v5 = v10 + 32;
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000000) != 0 )
        McTemplateU0ppww_EtwWriteTransfer(
          *(unsigned __int16 *)(v8 + 7856) >> 1,
          (unsigned int)fsctrl_c3971,
          a1,
          v8,
          v11 >> 1,
          v5,
          *(_WORD *)(v8 + 7856) >> 1,
          *(_QWORD *)(v8 + 7864));
    }
    NtfsSendBeginDismountEvent(a1, v8, v5, 0);
  }
  if ( !v91 || (v91->CurrentByteOffset.LowPart & 0x200) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v91 )
        QuadPart = v91->CurrentByteOffset.QuadPart;
      else
        LOBYTE(QuadPart) = 0;
      v75 = *(_QWORD *)(v8 + 248);
      v76 = *(_WORD *)(v75 + 6);
      if ( v76 > 0x40u || (v76 & 1) != 0 )
        v76 = 0;
      McTemplateU0ppwwd_EtwWriteTransfer(
        v76 >> 1,
        (unsigned int)fsctrl_c3986,
        (unsigned int)KeGetCurrentThread(),
        v8,
        *(_WORD *)(v8 + 7872) >> 1,
        *(_QWORD *)(v8 + 7880),
        v76 >> 1,
        v75 + 32,
        QuadPart);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 1183645);
    LOBYTE(v6) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225506LL, v6, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 1183646);
    return 3221225506LL;
  }
  v91 = FileObject;
  v99[0] = a1 + 12;
  v84 = -1073741823;
  v80 = 0;
  v82 = 0;
  v81 = 0;
  v12 = 1;
  if ( (*v9 & 0x40000) == 0 )
  {
    UnicodeString = 0;
    v79 = 0;
    KeWaitForSingleObject((PVOID)(v8 + 6632), Executive, 0, 0, 0);
    NtfsFillVcbVolumeGuid(a1);
    NtfsRepairGetVolumeId(a1, v8, 0, (unsigned int)&UnicodeString, (__int64)&v79);
    v13 = &word_140064400;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v14 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6736) )
        v14 = *(const WCHAR **)(v8 + 6736);
      v15 = (*(_DWORD *)(v8 + 28) >> 2) & 1;
      v16 = *(_DWORD *)(v8 + 6660);
      if ( (unsigned int)(v16 - 1) > 0x13 )
        LOBYTE(v16) = 0;
      v17 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6720) )
        v17 = *(const WCHAR **)(v8 + 6720);
      v92 = v17;
      v18 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6704) )
        v18 = *(const WCHAR **)(v8 + 6704);
      v85 = v18;
      v19 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6688) )
        v19 = *(const WCHAR **)(v8 + 6688);
      v88 = v19;
      v20 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6672) )
        v20 = *(const WCHAR **)(v8 + 6672);
      v89 = v20;
      v21 = &word_140064400;
      if ( *(_QWORD *)(v8 + 7864) )
        v21 = *(const WCHAR **)(v8 + 7864);
      v94[0] = (__int64)v21;
      if ( (*(_DWORD *)(v8 + 4) & 0xC00) != 0x800
        && (v22 = *(_QWORD *)(v8 + 248)) != 0
        && (v23 = *(_QWORD *)(v22 + 16)) != 0 )
      {
        v24 = (*(_DWORD *)(v23 + 48) >> 8) & 1;
      }
      else
      {
        v24 = 0;
      }
      McTemplateK0jmztzzzzzqjqtz_EtwWriteTransfer(
        v8 + 7808,
        v24,
        v102,
        v8 + 7824,
        v8 + 8528,
        (__int64)UnicodeString.Buffer,
        v24,
        v94[0],
        (__int64)v89,
        (__int64)v88,
        (__int64)v85,
        (__int64)v92,
        v16,
        v8 + 7808,
        *(_DWORD *)(v8 + 6792),
        v15,
        (__int64)v14);
    }
    v25 = KeQueryUnbiasedInterruptTime();
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    v26 = (KeQueryUnbiasedInterruptTime() - v25) / 0xA / 0x3E8;
    IoPerfPrintTimeInterval(v26, 2, v106, v27);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v28 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6736) )
        v28 = *(const WCHAR **)(v8 + 6736);
      v94[0] = (__int64)v28;
      v29 = (*(_DWORD *)(v8 + 28) >> 2) & 1;
      v30 = *(_DWORD *)(v8 + 6660);
      if ( (unsigned int)(v30 - 1) > 0x13 )
        LOBYTE(v30) = 0;
      v31 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6720) )
        v31 = *(const WCHAR **)(v8 + 6720);
      v89 = v31;
      v32 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6704) )
        v32 = *(const WCHAR **)(v8 + 6704);
      v88 = v32;
      v33 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6688) )
        v33 = *(const WCHAR **)(v8 + 6688);
      v92 = v33;
      v34 = &word_140064400;
      if ( *(_QWORD *)(v8 + 6672) )
        v34 = *(const WCHAR **)(v8 + 6672);
      v85 = v34;
      if ( *(_QWORD *)(v8 + 7864) )
        v13 = *(const WCHAR **)(v8 + 7864);
      if ( (*(_DWORD *)(v8 + 4) & 0xC00) != 0x800
        && (v35 = *(_QWORD *)(v8 + 248)) != 0
        && (v36 = *(_QWORD *)(v35 + 16)) != 0 )
      {
        v37 = (*(_DWORD *)(v36 + 48) >> 8) & 1;
      }
      else
      {
        v37 = 0;
      }
      McTemplateK0jmztzzzzzqjqtzzx_EtwWriteTransfer(
        v8 + 7808,
        v37,
        v102,
        v8 + 7824,
        v8 + 8528,
        (__int64)UnicodeString.Buffer,
        v37,
        (__int64)v13,
        (__int64)v85,
        (__int64)v92,
        (__int64)v88,
        (__int64)v89,
        v30,
        v8 + 7808,
        *(_DWORD *)(v8 + 6792),
        v29,
        v94[0],
        (__int64)v106,
        v26);
    }
    if ( v79 )
      RtlFreeUnicodeString(&UnicodeString);
    v12 = 1;
  }
  while ( 1 )
  {
    NtfsPurgeFileRecordCache(a1);
    NtfsAcquireCheckpointSynchronization(a1, v8, 80);
    v81 = 1;
    LOBYTE(v38) = 1;
    NtfsAcquireExclusiveVcb(a1, v8, v38);
    v80 = 1;
    if ( *(_DWORD *)(v8 + 280) )
    {
      v46 = *(_DWORD *)(v8 + 4);
      if ( (v46 & 2) != 0 )
      {
        v50 = *(_DWORD *)(v8 + 260);
        v51 = *(_DWORD *)(v8 + 268);
        v52 = *(_DWORD *)(v8 + 264);
        if ( v52 == v50 + ~v51 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v40 = 1183785;
LABEL_118:
            NtfsStatusTraceAndDebugInternal(0, 3221226685LL, v40);
          }
LABEL_119:
          v84 = -1073740611;
          goto LABEL_131;
        }
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v53 = *(_QWORD *)(v8 + 248);
          v54 = *(unsigned __int16 *)(v53 + 6);
          if ( v54 > 0x40 || (v54 & 1) != 0 )
            v54 = 0;
          LODWORD(FileObject) = v54;
          LOWORD(v94[0]) = v54;
          v94[1] = v53 + 32;
          McTemplateU0ppwwdddd_EtwWriteTransfer(
            *(unsigned __int16 *)(v8 + 7872) >> 1,
            (unsigned int)fsctrl_c4145,
            (unsigned int)KeGetCurrentThread(),
            v8,
            *(_WORD *)(v8 + 7872) >> 1,
            *(_QWORD *)(v8 + 7880),
            (unsigned __int16)v54 >> 1,
            v53 + 32,
            v46,
            v52,
            v50,
            v51);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v49 = 1183807;
      }
      else
      {
        if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0)
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v47 = *(_QWORD *)(v8 + 248);
          v48 = *(unsigned __int16 *)(v47 + 6);
          if ( v48 > 0x40 || (v48 & 1) != 0 )
            v48 = 0;
          LODWORD(v92) = v48;
          LOWORD(v99[0]) = v48;
          v99[1] = v47 + 32;
          McTemplateU0ppwwd_EtwWriteTransfer(
            *(unsigned __int16 *)(v8 + 7872) >> 1,
            (unsigned int)fsctrl_c4117,
            (unsigned int)KeGetCurrentThread(),
            v8,
            *(_WORD *)(v8 + 7872) >> 1,
            *(_QWORD *)(v8 + 7880),
            (unsigned __int16)v48 >> 1,
            v47 + 32,
            v46);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_130;
        v49 = 1183776;
      }
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, v49);
LABEL_130:
      v84 = -1073741790;
      goto LABEL_131;
    }
    v82 = 1;
    v39 = *(_DWORD *)(v8 + 4);
    if ( (v39 & 1) == 0 )
      break;
    if ( (unsigned __int8)NtfsIsDismountProtectedStateSepVolume(a1, *(_QWORD *)(v8 + 224)) )
    {
      if ( NtfsStatusDebugFlags )
      {
        v40 = 1183847;
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    v94[0] = v8 + 4;
    v88 = (const WCHAR *)(v8 + 4);
    if ( !v12 )
    {
      v89 = (const WCHAR *)(v8 + 5521);
      if ( !*(_BYTE *)(v8 + 5521) && NtfsFlushTrimRequestsOnDismount )
        NtfsFlushAllTrimHintsSynchronous(a1, v8);
      *(_BYTE *)(v8 + 5521) = 1;
      v43 = *v9;
      if ( (*v9 & 0x40000) == 0 && (*(_DWORD *)(v8 + 4) & 0x2000000) == 0 )
      {
        *(_DWORD *)(a1 + 392) = 8;
        *v9 = v43 | 0x40000;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225864LL, 1183951);
        NtfsRaiseStatusInternal(a1, -1073741432, 0, 0, 1183951);
        __debugbreak();
        JUMPOUT(0x14029EF7CLL);
      }
      if ( (*(_DWORD *)(v8 + 24) & 0x40000) != 0 )
      {
        KeClearEvent(*(PRKEVENT *)(v8 + 1432));
        v44 = NtfsFlushVolume(a1);
        v84 = v44;
        if ( (*(_DWORD *)(v8 + 24) & 0x40000) != 0
          && ((v45 = *(_QWORD *)(v8 + 64)) == 0 || (*(_DWORD *)(v45 + 200) & 0x20000) != 0)
          || v44 != -1073741797 && !(unsigned __int8)NtfsAreClustersDangling(a1, v8) )
        {
          NtfsFlushVolume(a1);
          KeSetEvent(*(PRKEVENT *)(v8 + 1432), 0, 0);
          goto LABEL_103;
        }
        NtfsFlushVolume(a1);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226652LL, 1184020);
        v84 = -1073740644;
        local_unwind_0(v101, &loc_14029EA95);
      }
      NtfsFlushVolume(a1);
LABEL_103:
      NtfsPerformDismountOnVcb((_DWORD *)a1, v8, 0, 0, 0, 0);
      SetFlagInterlocked(v88, 2);
      *(_QWORD *)(v8 + 1472) = (char *)&FileObject->Type + 1;
      NtfsSetDirectWritesAllowed(*(_QWORD *)(v8 + 248));
LABEL_104:
      v84 = 0;
      goto LABEL_131;
    }
    NtfsReleaseVcb(a1, v8);
    v80 = 0;
    NtfsReleaseCheckpointSynchronization(v41, v8, 16);
    v81 = 0;
    TxfShutdownVolume(a1, v8, 0, v42, 0);
    v12 = 0;
  }
  if ( (v39 & 0x800000) == 0 )
    goto LABEL_104;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 1183833);
  v84 = -1073741202;
LABEL_131:
  v55 = v84;
  if ( v84 || !v82 )
  {
    v56 = v87;
  }
  else
  {
    v56 = v87;
    SetFlagInterlocked(v87 + 4, 0x800000);
  }
  FsRtlDismountComplete(*(_QWORD *)(v56 + 224), v55);
  NtfsReleaseCheckpointSynchronization(v57, v56, 16);
  v58 = v86;
  if ( (v55 & 0x80000000) != 0 )
    NtfsUpdateDeleteNotificationVolumeSetting(v86, v56, 0);
  NtfsReleaseVcb(v58, v56);
  if ( (int)(v55 + 0x80000000) >= 0 && v55 != -1073741202 )
  {
    v98 = 0;
    v79 = 0;
    NtfsFillVcbVolumeGuid(v58);
    LOBYTE(v60) = 1;
    NtfsRepairGetVolumeId(v58, *(_QWORD *)(v58 + 104), v60, (unsigned int)&v98, (__int64)&v79);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x80000) != 0 )
    {
      v61 = &word_140064400;
      v62 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6736) )
        v62 = *(const WCHAR **)(v56 + 6736);
      v63 = (*(_DWORD *)(v56 + 28) >> 2) & 1;
      v64 = *(_DWORD *)(v56 + 6660);
      if ( (unsigned int)(v64 - 1) > 0x13 )
        LOBYTE(v64) = 0;
      v65 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6720) )
        v65 = *(const WCHAR **)(v56 + 6720);
      v99[0] = (__int64)v65;
      v66 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6704) )
        v66 = *(const WCHAR **)(v56 + 6704);
      v94[0] = (__int64)v66;
      v67 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6688) )
        v67 = *(const WCHAR **)(v56 + 6688);
      v89 = v67;
      v68 = &word_140064400;
      if ( *(_QWORD *)(v56 + 6672) )
        v68 = *(const WCHAR **)(v56 + 6672);
      v88 = v68;
      if ( *(_QWORD *)(v56 + 7864) )
        v61 = *(const WCHAR **)(v56 + 7864);
      if ( (*(_DWORD *)(v56 + 4) & 0xC00) != 0x800
        && (v69 = *(_QWORD *)(v56 + 248)) != 0
        && (v70 = *(_QWORD *)(v69 + 16)) != 0 )
      {
        v71 = (*(_DWORD *)(v70 + 48) >> 8) & 1;
      }
      else
      {
        LOBYTE(v71) = 0;
      }
      McTemplateK0jmztzzzzzqjqtzpd_EtwWriteTransfer(
        v56 + 7808,
        v56 + 8528,
        v102,
        v56 + 7824,
        v56 + 8528,
        (__int64)v98.Buffer,
        v71,
        (__int64)v61,
        (__int64)v88,
        (__int64)v89,
        v94[0],
        v99[0],
        v64,
        v56 + 7808,
        *(_DWORD *)(v56 + 6792),
        v63,
        (__int64)v62,
        v78,
        v55);
    }
    if ( v79 )
      RtlFreeUnicodeString(&v98);
    FsRtlNotifyVolumeEvent(v91, 2u);
  }
  if ( v83 )
  {
    v72 = KeQueryUnbiasedInterruptTime();
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryDismountEnd(
        (unsigned int)&v102,
        (unsigned int)&v104,
        (unsigned int)&v105,
        (unsigned int)&v97,
        v96,
        v55,
        v72 - UnbiasedInterruptTime);
  }
  if ( NtfsStatusDebugFlags && v55 && v55 - 298 > 1 && v55 + 2147483643 > 1 )
    NtfsStatusTraceAndDebugInternal(v58, v55, 1184192);
  LOBYTE(v59) = v100 != 0;
  NtfsExtendedCompleteRequestInternal(v58, v100, v55, v59, (v55 & 0x80000000) == 0);
  return v55;
}

```

## disassembly

```asm
0x14029dd80  mov     r11, rsp
0x14029dd83  mov     [r11+18h], rbx
0x14029dd87  mov     [r11+20h], rsi
0x14029dd8b  push    rdi
0x14029dd8c  push    r12
0x14029dd8e  push    r13
0x14029dd90  push    r14
0x14029dd92  push    r15
0x14029dd94  sub     rsp, 210h
0x14029dd9b  mov     rax, cs:__security_cookie
0x14029dda2  xor     rax, rsp
0x14029dda5  mov     [rsp+238h+var_38], rax
0x14029ddad  mov     [rsp+238h+var_E8], rsp
0x14029ddb5  mov     rbx, rdx
0x14029ddb8  mov     r14, rcx
0x14029ddbb  mov     [rsp+238h+var_180], rcx
0x14029ddc3  mov     [rsp+238h+var_F0], rdx
0x14029ddcb  xor     edi, edi
0x14029ddcd  mov     [r11-178h], rdi
0x14029ddd4  mov     [r11-158h], rdi
0x14029dddb  xorps   xmm0, xmm0
0x14029ddde  xor     eax, eax
0x14029dde0  movups  [rsp+238h+var_E0], xmm0
0x14029dde8  mov     [r11-0D0h], rax
0x14029ddef  movups  [rsp+238h+var_C8], xmm0
0x14029ddf7  xorps   xmm1, xmm1
0x14029ddfa  movups  [rsp+238h+var_B8], xmm1
0x14029de02  mov     [r11-118h], rdi
0x14029de09  mov     [rsp+238h+var_148], rdi
0x14029de11  mov     [rsp+238h+var_194], dil
0x14029de19  mov     rax, [rdx+0B8h]
0x14029de20  mov     rax, [rax+30h]
0x14029de24  mov     [rsp+238h+FileObject], rax
0x14029de2c  mov     byte ptr [rsp+238h+var_208], 1
0x14029de31  lea     rcx, [r11-158h]
0x14029de38  mov     [rsp+238h+var_210], rcx
0x14029de3d  lea     rcx, [r11-100h]
0x14029de44  mov     [rsp+238h+Timeout], rcx
0x14029de49  lea     r9, [r11-140h]
0x14029de50  lea     r8, [r11-178h]
0x14029de57  mov     rdx, rax
0x14029de5a  mov     rcx, r14
0x14029de5d  call    NtfsDecodeFileObject
0x14029de62  test    r14, r14
0x14029de65  jz      short loc_14029DEA1
0x14029de67  mov     rcx, [r14+78h]
0x14029de6b  test    rcx, rcx
0x14029de6e  jz      short loc_14029DEA1
0x14029de70  mov     rax, [rcx]
0x14029de73  mov     qword ptr [rsp+238h+var_E0+8], rax
0x14029de7b  mov     rax, [rcx+8]
0x14029de7f  mov     [rsp+238h+var_D0], rax
0x14029de87  lea     rax, [rsp+238h+var_E0+8]
0x14029de8f  mov     qword ptr [rsp+238h+var_E0], rax
0x14029de97  mov     rax, qword ptr [rsp+238h+var_E0]
0x14029de9f  jmp     short loc_14029DEE3
0x14029dea1  call    cs:__imp_IoGetActivityIdThread
0x14029dea8  nop     dword ptr [rax+rax+00h]
0x14029dead  test    rax, rax
0x14029deb0  jz      short loc_14029DEDB
0x14029deb2  mov     rcx, [rax]
0x14029deb5  mov     qword ptr [rsp+238h+var_E0+8], rcx
0x14029debd  mov     rax, [rax+8]
0x14029dec1  mov     [rsp+238h+var_D0], rax
0x14029dec9  lea     rax, [rsp+238h+var_E0+8]
0x14029ded1  mov     qword ptr [rsp+238h+var_E0], rax
0x14029ded9  jmp     short loc_14029DEE3
0x14029dedb  mov     qword ptr [rsp+238h+var_E0], rdi
0x14029dee3  mov     rsi, [rsp+238h+var_178]
0x14029deeb  movups  xmm0, xmmword ptr [rsi+2140h]
0x14029def2  movdqu  [rsp+238h+var_B8], xmm0
0x14029defb  mov     rax, [rsi+2150h]
0x14029df02  mov     [rsp+238h+var_118], rax
0x14029df0a  mov     eax, [rsi+2158h]
0x14029df10  mov     dword ptr [rsp+238h+var_188], eax
0x14029df17  mov     [rsp+238h+var_120], eax
0x14029df1e  mov     eax, [rsi+18h]
0x14029df21  test    al, 4
0x14029df23  jz      short loc_14029DF37
0x14029df25  movups  xmm0, xmmword ptr [rsi+1E90h]
0x14029df2c  movdqu  [rsp+238h+var_C8], xmm0
0x14029df35  jmp     short loc_14029DF42
0x14029df37  xorps   xmm0, xmm0
0x14029df3a  movups  [rsp+238h+var_C8], xmm0
0x14029df42  lea     r12, [r14+0Ch]
0x14029df46  mov     r15d, 40000h
0x14029df4c  test    [r12], r15d
0x14029df50  jnz     short loc_14029DFBE
0x14029df52  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029df59  nop     dword ptr [rax+rax+00h]
0x14029df5e  mov     [rsp+238h+var_148], rax
0x14029df66  mov     r13d, 200h
0x14029df6c  mov     ecx, r13d
0x14029df6f  call    NtfsTelemetryGuard
0x14029df74  test    al, al
0x14029df76  jz      short loc_14029DFB4
0x14029df78  mov     eax, [r12]
0x14029df7c  not     al
0x14029df7e  and     al, 1
0x14029df80  mov     byte ptr [rsp+238h+var_210], al
0x14029df84  mov     eax, dword ptr [rsp+238h+var_188]
0x14029df8b  mov     dword ptr [rsp+238h+Timeout], eax
0x14029df8f  lea     r9, [rsp+238h+var_118]
0x14029df97  lea     r8, [rsp+238h+var_B8]
0x14029df9f  lea     rdx, [rsp+238h+var_C8]
0x14029dfa7  lea     rcx, [rsp+238h+var_E0]
0x14029dfaf  call    NtfsTelemetryDismountBegin
0x14029dfb4  mov     [rsp+238h+var_194], 1
0x14029dfbc  jmp     short loc_14029DFC4
0x14029dfbe  mov     r13d, 200h
0x14029dfc4  test    [r12], r15d
0x14029dfc8  jnz     loc_14029E097
0x14029dfce  cmp     cs:dword_140092174, edi
0x14029dfd4  jz      loc_14029E089
0x14029dfda  mov     al, cs:byte_140092178
0x14029dfe0  dec     al
0x14029dfe2  cmp     al, 2
0x14029dfe4  jbe     loc_14029E089
0x14029dfea  mov     edx, 8000000h
0x14029dfef  test    cs:qword_140092160, rdx
0x14029dff6  jz      loc_14029E089
0x14029dffc  mov     rax, cs:qword_140092168
0x14029e003  and     rax, rdx
0x14029e006  cmp     rax, cs:qword_140092168
0x14029e00d  jnz     short loc_14029E089
0x14029e00f  mov     eax, [r14+10h]
0x14029e013  bt      rax, 14h
0x14029e018  jb      short loc_14029E089
0x14029e01a  mov     rax, [rsi+0F8h]
0x14029e021  movzx   edx, word ptr [rax+6]
0x14029e025  cmp     dx, 40h ; '@'
0x14029e029  ja      short loc_14029E030
0x14029e02b  test    dl, 1
0x14029e02e  jz      short loc_14029E032
0x14029e030  mov     edx, edi
0x14029e032  xor     ecx, ecx
0x14029e034  mov     dword ptr [rsp+238h+UnicodeString+4], ecx
0x14029e03b  mov     r8, rdi
0x14029e03e  test    dx, dx
0x14029e041  jz      short loc_14029E047
0x14029e043  lea     r8, [rax+20h]
0x14029e047  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 4
0x14029e04e  jz      short loc_14029E089
0x14029e050  movzx   ecx, word ptr [rsi+1EB0h]
0x14029e057  shr     ecx, 1
0x14029e059  movzx   edx, dx
0x14029e05c  shr     edx, 1
0x14029e05e  mov     rax, [rsi+1EB8h]
0x14029e065  mov     [rsp+238h+var_200], rax
0x14029e06a  mov     dword ptr [rsp+238h+var_208], ecx
0x14029e06e  mov     [rsp+238h+var_210], r8
0x14029e073  mov     dword ptr [rsp+238h+Timeout], edx
0x14029e077  mov     r9, rsi
0x14029e07a  mov     r8, r14
0x14029e07d  lea     rdx, fsctrl_c3971
0x14029e084  call    McTemplateU0ppww_EtwWriteTransfer
0x14029e089  xor     r9d, r9d
0x14029e08c  mov     rdx, rsi
0x14029e08f  mov     rcx, r14
0x14029e092  call    NtfsSendBeginDismountEvent
0x14029e097  mov     rcx, [rsp+238h+var_158]
0x14029e09f  test    rcx, rcx
0x14029e0a2  jz      loc_14029EE22
0x14029e0a8  test    [rcx+68h], r13w
0x14029e0ad  jz      loc_14029EE22
0x14029e0b3  mov     rax, [rsp+238h+FileObject]
0x14029e0bb  mov     [rsp+238h+var_158], rax
0x14029e0c3  mov     [rsp+238h+var_100], r12
0x14029e0cb  mov     [rsp+238h+var_190], 0C0000001h
0x14029e0d6  mov     [rsp+238h+var_197], dil
0x14029e0de  mov     [rsp+238h+var_195], dil
0x14029e0e6  mov     [rsp+238h+var_196], dil
0x14029e0ee  mov     r13b, 1
0x14029e0f1  mov     eax, [r12]
0x14029e0f5  test    r15d, eax
0x14029e0f8  jnz     loc_14029E521
0x14029e0fe  xorps   xmm0, xmm0
0x14029e101  movups  xmmword ptr [rsp+238h+UnicodeString.Length], xmm0
0x14029e109  mov     [rsp+238h+var_198], dil
0x14029e111  lea     rcx, [rsi+19E8h]; Object
0x14029e118  mov     [rsp+238h+Timeout], rdi; Timeout
0x14029e11d  xor     r9d, r9d; Alertable
0x14029e120  xor     r8d, r8d; WaitMode
0x14029e123  xor     edx, edx; WaitReason
0x14029e125  call    cs:__imp_KeWaitForSingleObject
0x14029e12c  nop     dword ptr [rax+rax+00h]
0x14029e131  nop
0x14029e132  mov     rcx, r14
0x14029e135  call    NtfsFillVcbVolumeGuid
0x14029e13a  lea     rax, [rsp+238h+var_198]
0x14029e142  mov     [rsp+238h+Timeout], rax
0x14029e147  lea     r9, [rsp+238h+UnicodeString]
0x14029e14f  xor     r8d, r8d
0x14029e152  mov     rdx, rsi
0x14029e155  mov     rcx, r14
0x14029e158  call    NtfsRepairGetVolumeId
0x14029e15d  lea     r13, word_140064400
0x14029e164  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+2, 4
0x14029e16b  jz      loc_14029E2E8
0x14029e171  mov     rax, [rsi+1A50h]
0x14029e178  mov     rbx, r13
0x14029e17b  test    rax, rax
0x14029e17e  cmovnz  rbx, rax
0x14029e182  mov     r10d, [rsi+1Ch]
0x14029e186  shr     r10d, 2
0x14029e18a  and     r10d, 1
0x14029e18e  mov     r11d, [rsi+1A04h]
0x14029e195  lea     eax, [r11-1]
0x14029e199  cmp     eax, 13h
0x14029e19c  cmova   r11d, edi
0x14029e1a0  mov     rax, [rsi+1A40h]
0x14029e1a7  mov     rcx, r13
0x14029e1aa  test    rax, rax
0x14029e1ad  cmovnz  rcx, rax
0x14029e1b1  mov     [rsp+238h+var_150], rcx
0x14029e1b9  mov     rax, [rsi+1A30h]
0x14029e1c0  mov     rcx, r13
0x14029e1c3  test    rax, rax
0x14029e1c6  cmovnz  rcx, rax
0x14029e1ca  mov     [rsp+238h+var_188], rcx
0x14029e1d2  mov     rax, [rsi+1A20h]
0x14029e1d9  mov     rcx, r13
0x14029e1dc  test    rax, rax
0x14029e1df  cmovnz  rcx, rax
0x14029e1e3  mov     [rsp+238h+var_170], rcx
0x14029e1eb  mov     rax, [rsi+1A10h]
0x14029e1f2  mov     rcx, r13
0x14029e1f5  test    rax, rax
0x14029e1f8  cmovnz  rcx, rax
0x14029e1fc  mov     [rsp+238h+var_168], rcx
0x14029e204  mov     rax, [rsi+1EB8h]
0x14029e20b  mov     rcx, r13
0x14029e20e  test    rax, rax
0x14029e211  cmovnz  rcx, rax
0x14029e215  mov     [rsp+238h+var_140], rcx
0x14029e21d  mov     eax, [rsi+4]
0x14029e220  and     eax, 0C00h
0x14029e225  cmp     eax, 800h
0x14029e22a  jz      short loc_14029E24C
0x14029e22c  mov     rax, [rsi+0F8h]
0x14029e233  test    rax, rax
0x14029e236  jz      short loc_14029E24C
0x14029e238  mov     rdx, [rax+10h]
0x14029e23c  test    rdx, rdx
0x14029e23f  jz      short loc_14029E24C
0x14029e241  mov     edx, [rdx+30h]
0x14029e244  shr     edx, 8
0x14029e247  and     edx, 1
0x14029e24a  jmp     short loc_14029E24E
0x14029e24c  mov     edx, edi
0x14029e24e  mov     r8, qword ptr [rsp+238h+var_E0]
0x14029e256  lea     rcx, [rsi+1E80h]
0x14029e25d  lea     r9, [rsi+1E90h]
0x14029e264  mov     [rsp+238h+var_1B8], rbx
0x14029e26c  mov     [rsp+238h+var_1C0], r10d
0x14029e271  mov     eax, [rsi+1A88h]
0x14029e277  mov     [rsp+238h+var_1C8], eax
0x14029e27b  mov     [rsp+238h+var_1D0], rcx
0x14029e280  mov     [rsp+238h+var_1D8], r11d
0x14029e285  mov     rax, [rsp+238h+var_150]
0x14029e28d  mov     [rsp+238h+var_1E0], rax
0x14029e292  mov     rax, [rsp+238h+var_188]
0x14029e29a  mov     [rsp+238h+var_1E8], rax
0x14029e29f  mov     rax, [rsp+238h+var_170]
0x14029e2a7  mov     [rsp+238h+var_1F0], rax
0x14029e2ac  mov     rax, [rsp+238h+var_168]
0x14029e2b4  mov     [rsp+238h+var_1F8], rax
0x14029e2b9  mov     rax, [rsp+238h+var_140]
0x14029e2c1  mov     [rsp+238h+var_200], rax
0x14029e2c6  mov     dword ptr [rsp+238h+var_208], edx
0x14029e2ca  mov     rax, [rsp+238h+UnicodeString.Buffer]
0x14029e2d2  mov     [rsp+238h+var_210], rax
0x14029e2d7  lea     rax, [rsi+2150h]
0x14029e2de  mov     [rsp+238h+Timeout], rax
0x14029e2e3  call    McTemplateK0jmztzzzzzqjqtz_EtwWriteTransfer
0x14029e2e8  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029e2ef  nop     dword ptr [rax+rax+00h]
0x14029e2f4  mov     rbx, rax
0x14029e2f7  mov     edx, 1; EventCode
0x14029e2fc  mov     rcx, [rsp+238h+FileObject]; FileObject
0x14029e304  call    cs:__imp_FsRtlNotifyVolumeEvent
0x14029e30b  nop     dword ptr [rax+rax+00h]
0x14029e310  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14029e317  nop     dword ptr [rax+rax+00h]
0x14029e31c  mov     rcx, rax
0x14029e31f  sub     rcx, rbx
0x14029e322  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14029e32c  mul     rcx
0x14029e32f  mov     rbx, rdx
0x14029e332  shr     rbx, 3
0x14029e336  mov     rax, 624DD2F1A9FBE77h
0x14029e340  mul     rbx
0x14029e343  sub     rbx, rdx
0x14029e346  shr     rbx, 1
0x14029e349  add     rbx, rdx
0x14029e34c  shr     rbx, 9
0x14029e350  lea     r8, [rsp+238h+var_A8]
0x14029e358  mov     edx, 2
0x14029e35d  mov     rcx, rbx
0x14029e360  call    IoPerfPrintTimeInterval
  ... truncated ...
```
