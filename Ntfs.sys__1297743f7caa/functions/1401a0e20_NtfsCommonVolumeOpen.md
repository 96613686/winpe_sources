# NtfsCommonVolumeOpen

- ea: `0x1401a0e20`
- end: `0x1401a1dff`
- name: `NtfsCommonVolumeOpen`
- size: `4063`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401a1e10`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c1d0`
- `0x14000c290`
- `0x14000d1e0`
- `0x140010be0`
- `0x140012e70`
- `0x14001c2e0`
- `0x14001e810`
- `0x140020de0`
- `0x14003c34c`
- `0x14003e734`
- `0x140044778`
- `0x14004487c`
- `0x14004f0ac`
- `0x1400592c0`
- `0x140059740`
- `0x1400b454c`
- `0x1400dfe70`
- `0x14013af60`
- `0x1401403d0`
- `0x140184220`
- `0x140184ed0`
- `0x140185c50`
- `0x14019cad0`
- `0x1401a0e20`
- `0x1401aab70`
- `0x1401d2c84`
- `0x1401f1d80`
- `0x140205910`
- `0x1402308d8`
- `0x140232a2c`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a103e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a1c78`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402ace22`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a103e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1401a1c78`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402ace22`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1401a127e`
- `ntoskrnl!FsRtlAreVolumeStartupApplicationsComplete` at `0x1401a127e`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1401a158f`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1401a158f`
- `ntoskrnl!ObGetObjectSecurity` at `0x1401a1aa3`
- `ntoskrnl!ObGetObjectSecurity` at `0x1401a1aa3`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401a1b01`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1401a1b01`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a102a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a102a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a18b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a18b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a1899`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a1899`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1c4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acde5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1c4c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402acde5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a108b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a108b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1401a136d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1401a136d`

## pseudocode

```c
__int64 __fastcall NtfsCommonVolumeOpen(__int64 a1, __int64 a2)
{
  BOOL v2; // edi
  __int64 v4; // rsi
  __int64 v5; // r13
  PFILE_OBJECT v6; // rbx
  __int64 v7; // r9
  NTSTATUS LogFileInformation; // edi
  bool v9; // r15
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  __int64 v15; // r8
  __int64 v16; // rcx
  _DWORD *v17; // rbx
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  int v23; // ebx
  __int64 v24; // rax
  __int64 v25; // rax
  FILE_OBJECT *v26; // rdi
  __int64 v27; // r10
  unsigned int v28; // eax
  unsigned __int16 v29; // cx
  NTSTATUS v30; // eax
  int v31; // edx
  int v32; // r8d
  bool v33; // cl
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // rdx
  unsigned int v38; // eax
  NTSTATUS v39; // eax
  int v40; // edx
  int v41; // r8d
  __int64 v42; // r10
  unsigned int v43; // eax
  PFILE_OBJECT v44; // rdi
  PWSTR Buffer; // rbx
  __int64 v46; // rcx
  __int64 v47; // r13
  __int64 v48; // rbx
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // r9
  char v52; // r13
  BOOL v53; // ecx
  __int64 v54; // rax
  char v56; // [rsp+82h] [rbp-176h]
  char v57; // [rsp+83h] [rbp-175h]
  unsigned __int8 MemoryAllocated; // [rsp+84h] [rbp-174h] BYREF
  char v59; // [rsp+85h] [rbp-173h]
  char v60; // [rsp+86h] [rbp-172h]
  char v61; // [rsp+87h] [rbp-171h]
  int v62; // [rsp+88h] [rbp-170h]
  char v63; // [rsp+8Ch] [rbp-16Ch]
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-168h]
  BOOL v65; // [rsp+98h] [rbp-160h]
  __int64 v66; // [rsp+A0h] [rbp-158h] BYREF
  _QWORD *v67; // [rsp+A8h] [rbp-150h]
  char v68; // [rsp+B0h] [rbp-148h]
  int v69; // [rsp+B4h] [rbp-144h]
  __int64 v70; // [rsp+B8h] [rbp-140h]
  __int64 v71; // [rsp+C0h] [rbp-138h]
  ULONG pcbInfoBuffer; // [rsp+C8h] [rbp-130h] BYREF
  __int64 v73; // [rsp+D0h] [rbp-128h]
  int v74; // [rsp+D8h] [rbp-120h]
  unsigned int v75; // [rsp+DCh] [rbp-11Ch]
  unsigned int v76; // [rsp+E0h] [rbp-118h]
  int v77; // [rsp+E4h] [rbp-114h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+E8h] [rbp-110h] BYREF
  __int16 v79; // [rsp+F8h] [rbp-100h]
  __int64 v80; // [rsp+100h] [rbp-F8h]
  unsigned __int16 v81; // [rsp+108h] [rbp-F0h]
  __int64 v82; // [rsp+110h] [rbp-E8h]
  __int16 v83; // [rsp+118h] [rbp-E0h]
  __int64 v84; // [rsp+120h] [rbp-D8h]
  __int16 v85; // [rsp+128h] [rbp-D0h]
  __int64 v86; // [rsp+130h] [rbp-C8h]
  CLFS_INFORMATION pinfoBuffer; // [rsp+140h] [rbp-B8h] BYREF

  v70 = a2;
  v73 = a1;
  v62 = -1073741823;
  v4 = 0;
  v71 = 0;
  v67 = 0;
  v66 = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v63 = 0;
  v60 = 0;
  LOBYTE(v2) = 0;
  v65 = v2;
  MemoryAllocated = 0;
  v61 = 0;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(PFILE_OBJECT *)(v5 + 48);
  FileObject = v6;
  SecurityDescriptor[1] = v6;
  *(_DWORD *)(a1 + 504) = 26;
  v7 = *(unsigned __int8 *)(v5 + 19);
  if ( (((_DWORD)v7 - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      McTemplateU0pd_EtwWriteTransfer(a1, create_c5645, KeGetCurrentThread(), v7);
    }
    LogFileInformation = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 661013);
    v62 = -1073741790;
    v9 = 1;
    goto LABEL_148;
  }
  v9 = 1;
  if ( (*(_DWORD *)(v5 + 16) & 1) != 0 )
  {
    LogFileInformation = -1073741811;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_12:
      v62 = LogFileInformation;
      goto LABEL_148;
    }
    v10 = 661023;
LABEL_11:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)LogFileInformation, v10);
    goto LABEL_12;
  }
  if ( TxfGetTransactionFromFileObject(*(_QWORD *)(v5 + 48), 0) )
  {
    LogFileInformation = -1072103334;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_12;
    v10 = 661040;
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(a1 + 104);
  if ( (*(_DWORD *)(v12 + 6436) & 2) != 0 )
  {
    v13 = *(_QWORD *)(v12 + 6248);
    if ( v13 )
    {
      if ( (*(_DWORD *)(v13 + 136) & 0x4000) != 0 && (*(_DWORD *)(a1 + 436) & 0x100000) == 0 )
LABEL_191:
        TxfParkRequest(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 6248LL) + 24LL) + 1280LL, 0);
    }
  }
  v4 = *(_QWORD *)(a1 + 104);
  v71 = v4;
  if ( (*(_BYTE *)(v5 + 26) & 6) != 0 )
  {
    LOBYTE(v11) = 1;
    NtfsAcquireSharedVcb(a1, v4, v11);
  }
  else
  {
    KeWaitForSingleObject((PVOID)(v4 + 6632), Executive, 0, 0, 0);
    FsRtlNotifyVolumeEvent(v6, 3u);
    v60 = 1;
    LOBYTE(v14) = 1;
    NtfsFspCloseInternal(0, v4, v14, 0, 0);
    if ( (*(_DWORD *)(v4 + 6436) & 2) != 0 )
    {
      v16 = *(_QWORD *)(v4 + 6248);
      if ( v16 )
      {
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v16 + 24) + 912LL), 1u);
        v59 = 1;
      }
    }
    LOBYTE(v15) = 1;
    NtfsAcquireExclusiveVcb(a1, v4, v15);
    *(_BYTE *)(v4 + 5521) = 1;
    v61 = 1;
  }
  v56 = 1;
  v17 = (_DWORD *)(v4 + 4);
  v18 = *(unsigned int *)(v4 + 4);
  if ( (v18 & 0x802) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v19 = *(_QWORD *)(v4 + 248);
      v20 = *(unsigned __int16 *)(v19 + 6);
      if ( v20 > 0x40 || (v20 & 1) != 0 )
        v20 = 0;
      v65 = v20;
      v79 = v20;
      v80 = v19 + 32;
      McTemplateU0ppwwd_EtwWriteTransfer(
        *(unsigned __int16 *)(v4 + 7872) >> 1,
        (unsigned int)create_c5763,
        (unsigned int)KeGetCurrentThread(),
        v4,
        *(_WORD *)(v4 + 7872) >> 1,
        *(_QWORD *)(v4 + 7880),
        (unsigned __int16)v20 >> 1,
        v19 + 32,
        v18);
    }
    LogFileInformation = -1073741790;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_36;
    v21 = 661134;
    goto LABEL_35;
  }
  if ( !(unsigned __int8)NtfsPingVolume(a1, v4, 0, v18) || (*v17 & 1) == 0 )
  {
    *(_DWORD *)(a1 + 4) |= 0x200000u;
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 661165);
    goto LABEL_191;
  }
  v67 = *(_QWORD **)(*(_QWORD *)(v4 + 192) + 184LL);
  NtfsAcquireExclusiveFcb(a1, v67, 0, 0);
  NtfsAccessCheck(a1, 0, v67, 0, v70, *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v70 + 184) + 8LL) + 16LL), 0, 0, 0);
  NtfsReleaseFcbEx(a1, v67, 0);
  v57 = 0;
  v22 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL) + 20LL);
  if ( (*(_BYTE *)(v5 + 26) & 6) != 0 )
  {
    if ( (v22 & 7) != 0 )
      v65 = (*v17 & 0x2000000) == 0;
    goto LABEL_124;
  }
  if ( (v22 & 6) != 0 )
  {
    MemoryAllocated = 1;
    v68 = 1;
    if ( FsRtlAreVolumeStartupApplicationsComplete() )
      *(_WORD *)(v5 + 26) &= ~1u;
  }
  if ( (*(_BYTE *)(v5 + 26) & 1) == 0 )
  {
    v23 = 0;
    v69 = 0;
    v24 = *(_QWORD *)(v4 + 168);
    if ( v24 )
    {
      v23 = *(_DWORD *)(v24 + 208);
      v69 = v23;
    }
    if ( v59
      && (_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v4 + 6248) + 132LL), 4, 4) == 2
       || _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v4 + 6248) + 132LL), 4, 4) == 1) )
    {
      v25 = *(_QWORD *)(v4 + 6248);
      if ( *(_QWORD *)(v25 + 72) )
        v69 = ++v23;
      v26 = *(FILE_OBJECT **)(v25 + 496);
      if ( v26 )
      {
        memset(&pinfoBuffer, 0, sizeof(pinfoBuffer));
        pcbInfoBuffer = 120;
        LogFileInformation = ClfsGetLogFileInformation(v26, &pinfoBuffer, &pcbInfoBuffer);
        v62 = LogFileInformation;
        if ( LogFileInformation < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)LogFileInformation < 0xFFFFFFED
            && LogFileInformation != -1073741802
            && (unsigned int)(LogFileInformation + 2147483643) > 1
            && LogFileInformation != -1073741807
            && LogFileInformation != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)LogFileInformation, 661272);
          }
          goto LABEL_147;
        }
        v23 += pinfoBuffer.TotalContainers + 1;
        v69 = v23;
      }
    }
    if ( *(_DWORD *)(v4 + 256) != v23 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000) != 0 )
      {
        v27 = *(_QWORD *)(v4 + 248);
        v28 = *(unsigned __int16 *)(v27 + 6);
        if ( v28 > 0x40 || (v28 & 1) != 0 )
        {
          v29 = 0;
          v74 = 0;
        }
        else
        {
          v29 = *(_WORD *)(v27 + 6);
          v74 = v29;
        }
        v81 = v29;
        v82 = v27 + 32;
        McTemplateU0ppwwddd_EtwWriteTransfer(
          v29 >> 1,
          (unsigned int)create_c5927,
          (unsigned int)KeGetCurrentThread(),
          v4,
          *(_WORD *)(v4 + 7872) >> 1,
          *(_QWORD *)(v4 + 7880),
          v29 >> 1,
          v27 + 32,
          *(_WORD *)(v5 + 26),
          *(_DWORD *)(v4 + 256),
          v23);
      }
      LogFileInformation = -1073741757;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_36;
      v21 = 661300;
      goto LABEL_35;
    }
  }
  v30 = NtfsFlushVolume(a1);
  LogFileInformation = v30;
  v62 = v30;
  if ( v30 == -1073741797 || v30 == -1073741774 || v30 == -1073741566 )
  {
    LogFileInformation = 0;
    v62 = 0;
  }
  v31 = *(_DWORD *)(v4 + 260);
  v32 = *(_DWORD *)(v4 + 268);
  if ( (*(_BYTE *)(v5 + 26) & 1) != 0 )
    v33 = *(_DWORD *)(v4 + 264) != v31 - v32;
  else
    v33 = v31 != v32;
  if ( v33 )
  {
    if ( LogFileInformation < 0 )
      goto LABEL_100;
    NtfsCheckpointCurrentTransaction(a1);
    *(_DWORD *)(a1 + 4) &= ~0x2000u;
    while ( 1 )
    {
      v34 = *(_QWORD *)(a1 + 152);
      if ( v34 == a1 + 152 )
        break;
      NtfsReleaseFcbWithPaging(a1, v34 - 80);
    }
    NtfsReleaseVcb(a1, v4);
    CcWaitForCurrentLazyWriterActivity();
    LOBYTE(v35) = 1;
    NtfsAcquireExclusiveVcb(a1, v4, v35);
    v56 = 1;
    v36 = *(_DWORD *)(v4 + 4);
    if ( (v36 & 0x802) != 0 )
    {
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v37 = *(_QWORD *)(v4 + 248);
        v38 = *(unsigned __int16 *)(v37 + 6);
        if ( v38 > 0x40 || (v38 & 1) != 0 )
          v38 = 0;
        v75 = v38;
        v83 = v38;
        v84 = v37 + 32;
        McTemplateU0ppwwd_EtwWriteTransfer(
          *(unsigned __int16 *)(v4 + 7872) >> 1,
          (unsigned int)create_c6033,
          (unsigned int)KeGetCurrentThread(),
          v4,
          *(_WORD *)(v4 + 7872) >> 1,
          *(_QWORD *)(v4 + 7880),
          (unsigned __int16)v38 >> 1,
          v37 + 32,
          v36);
      }
      LogFileInformation = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_36;
      v21 = 661404;
      goto LABEL_35;
    }
    v39 = NtfsFlushVolume(a1);
    LogFileInformation = v39;
    v62 = v39;
    if ( v39 == -1073741797 || v39 == -1073741774 || v39 == -1073741566 )
    {
      LogFileInformation = 0;
      v62 = 0;
    }
    NtfsWakeAndWaitForRepairThreadToTerminate(v4);
    v33 = 0;
    v40 = *(_DWORD *)(v4 + 260);
    v41 = *(_DWORD *)(v4 + 268);
    if ( (*(_BYTE *)(v5 + 26) & 1) != 0 )
    {
      if ( *(_DWORD *)(v4 + 264) != v40 - v41 )
      {
        v33 = 1;
        if ( NtfsTrackVolumeOpenSharingViolation )
LABEL_99:
          __int2c();
      }
    }
    else if ( v40 != v41 )
    {
      v33 = 1;
      if ( NtfsTrackVolumeOpenSharingViolation )
        goto LABEL_99;
    }
LABEL_100:
    if ( v33 )
    {
      if ( LogFileInformation < 0 )
        goto LABEL_147;
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000) != 0 )
      {
        v42 = *(_QWORD *)(v4 + 248);
        v43 = *(unsigned __int16 *)(v42 + 6);
        if ( v43 > 0x40 || (v43 & 1) != 0 )
          v43 = 0;
        v76 = v43;
        v85 = v43;
        v86 = v42 + 32;
        McTemplateU0ppwwdddd_EtwWriteTransfer(
          *(unsigned __int16 *)(v5 + 26),
          (unsigned int)create_c6122,
          (unsigned int)KeGetCurrentThread(),
          v4,
          *(_WORD *)(v4 + 7872) >> 1,
          *(_QWORD *)(v4 + 7880),
          (unsigned __int16)v43 >> 1,
          v42 + 32,
          *(_WORD *)(v5 + 26),
          *(_DWORD *)(v4 + 264),
          *(_DWORD *)(v4 + 260),
          *(_DWORD *)(v4 + 268));
      }
      LogFileInformation = -1073741757;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_36:
        v62 = LogFileInformation;
LABEL_147:
        v6 = FileObject;
        goto LABEL_148;
      }
      v21 = 661497;
LABEL_35:
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)LogFileInformation, v21);
      goto LABEL_36;
    }
  }
  if ( LogFileInformation < 0 )
  {
    if ( LogFileInformation != -1073741797 && LogFileInformation != -1073741774 && LogFileInformation != -1073741566 )
      goto LABEL_147;
    v62 = 0;
  }
  if ( MemoryAllocated )
    v63 = 1;
LABEL_124:
  v44 = FileObject;
  Buffer = FileObject->FileName.Buffer;
  FileObject->FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x10u, 0x4346744Eu);
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  v6 = v44;
  *(_OWORD *)v44->FileName.Buffer = *(_OWORD *)L"\\$Volume";
  *(_DWORD *)&v44->FileName.Length = 1048592;
  v44->Flags &= ~0x40u;
  v44->Flags |= 8u;
  NtfsAcquireExclusiveFcb(a1, v67, 0, 0);
  v57 = 1;
  LogFileInformation = NtfsOpenAttribute(
                         a1,
                         (__int64)v67,
                         2,
                         (__int64)&NtfsEmptyString,
                         128,
                         *((_DWORD *)v67 + 5) == 0 ? 2 : 0,
                         4,
                         0,
                         2,
                         0,
                         v4 + 192,
                         0,
                         (__int64)&v66);
  v62 = LogFileInformation;
  if ( LogFileInformation >= 0 )
  {
    if ( (*(_BYTE *)(v5 + 26) & 7) == 1
      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL) + 20LL) & 1) != 0
      && (*(_DWORD *)(v4 + 4) & 0x2000000) == 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v4 + 272), 1u);
      SetFlagInterlocked(v66 + 8, 0x80000);
    }
    v46 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL);
    if ( (*(_BYTE *)(v46 + 20) & 3) == 3 || (unsigned __int8)NtfsCanAdministerVolume(v46, v70, v67, 0, 0) )
    {
      *(_WORD *)(v66 + 104) |= 0x200u;
      v47 = v70;
    }
    else
    {
      v48 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL);
      v47 = v70;
      LOBYTE(v49) = NtfsEffectiveMode(v70);
      if ( (unsigned __int8)NtfsPrivilegeCheck(28, v48 + 32, v49) )
      {
        *(_WORD *)(v66 + 104) |= 0x200u;
      }
      else
      {
        MemoryAllocated = 0;
        SecurityDescriptor[0] = 0;
        v77 = 3;
        if ( !ObGetObjectSecurity(*(PVOID *)(*(_QWORD *)(v4 + 248) + 16LL), SecurityDescriptor, &MemoryAllocated)
          && SecurityDescriptor[0] )
        {
          if ( (unsigned __int8)NtfsCanAdministerVolume(v50, v47, v67, SecurityDescriptor[0], &v77) )
            *(_WORD *)(v66 + 104) |= 0x200u;
          ObReleaseObjectSecurity(SecurityDescriptor[0], MemoryAllocated);
        }
      }
    }
    if ( v65 )
      SetFlagInterlocked(v66 + 4, 512);
    SetFlagInterlocked(v66 + 8, 2048);
    if ( v63 )
    {
      SetFlagInterlocked(v4 + 4, 2);
      v6 = FileObject;
      *(_QWORD *)(v4 + 1472) = FileObject;
      v60 = 0;
    }
    else
    {
      v6 = FileObject;
    }
    *(_QWORD *)(v47 + 56) = 1;
  }
LABEL_148:
  NtfsCleanupTransaction(a1, (unsigned int)LogFileInformation, 0);
  if ( !LogFileInformation )
  {
    v6->FileName.Buffer = 0;
    *(_DWORD *)&v6->FileName.Length = 0;
    SetFlagInterlocked(v66 + 4, 0x4000);
  }
  if ( v57 )
    NtfsReleaseFcbEx(a1, v67, 0);
  v52 = v56;
  if ( v61 && LogFileInformation < 0 )
  {
    if ( !v56 )
      v52 = NtfsAcquireExclusiveVcb(a1, v4, 0);
    NtfsUpdateDeleteNotificationVolumeSetting(a1, v4, 0);
  }
  if ( v52 )
    NtfsReleaseVcb(a1, v4);
  if ( v59 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v4 + 6248) + 24LL) + 912LL));
  if ( v60 )
  {
    NtfsPurgeFileRecordCache(a1);
    if ( (*(_DWORD *)(v4 + 4) & 1) != 0 )
      FsRtlNotifyVolumeEvent(v6, 4u);
  }
  if ( (*(_DWORD *)(a1 + 12) & 2) != 0 )
  {
    if ( NtfsStatusDebugFlags
      && LogFileInformation
      && LogFileInformation != 294
      && (unsigned int)(LogFileInformation - 298) > 1
      && (unsigned int)LogFileInformation < 0xFFFFFFED
      && LogFileInformation != -1073741802
      && (unsigned int)(LogFileInformation + 2147483643) > 1
      && LogFileInformation != -1073741807
      && LogFileInformation != 259
      && LogFileInformation != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, (unsigned int)LogFileInformation, 661812);
    }
    v53 = LogFileInformation >= 0;
    v54 = 0;
  }
  else
  {
    if ( NtfsStatusDebugFlags
      && LogFileInformation
      && LogFileInformation != 294
      && (unsigned int)(LogFileInformation - 298) > 1
      && (unsigned int)LogFileInformation < 0xFFFFFFED
      && LogFileInformation != -1073741802
      && (unsigned int)(LogFileInformation + 2147483643) > 1
      && LogFileInformation != -1073741807
      && LogFileInformation != 259
      && LogFileInformation != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, (unsigned int)LogFileInformation, 661814);
    }
    v53 = LogFileInformation >= 0;
    v9 = v70 != 0;
    v54 = v70;
  }
  LOBYTE(v51) = v9;
  NtfsExtendedCompleteRequestInternal(a1, v54, (unsigned int)LogFileInformation, v51, v53);
  return (unsigned int)LogFileInformation;
}

```

## disassembly

```asm
0x1401a0e20  mov     r11, rsp
0x1401a0e23  mov     [r11+18h], rbx
0x1401a0e27  mov     [r11+20h], rsi
0x1401a0e2b  push    rdi
0x1401a0e2c  push    r12
0x1401a0e2e  push    r13
0x1401a0e30  push    r14
0x1401a0e32  push    r15
0x1401a0e34  sub     rsp, 1D0h
0x1401a0e3b  mov     rax, cs:__security_cookie
0x1401a0e42  xor     rax, rsp
0x1401a0e45  mov     [rsp+1F8h+var_38], rax
0x1401a0e4d  mov     [rsp+1F8h+var_140], rdx
0x1401a0e55  mov     r14, rcx
0x1401a0e58  mov     [rsp+1F8h+var_128], rcx
0x1401a0e60  mov     [rsp+1F8h+var_170], 0C0000001h
0x1401a0e6b  xor     r12d, r12d
0x1401a0e6e  mov     esi, r12d
0x1401a0e71  mov     [r11-138h], r12
0x1401a0e78  mov     [r11-150h], r12
0x1401a0e7f  mov     [r11-158h], r12
0x1401a0e86  mov     al, r12b
0x1401a0e89  mov     [rsp+1F8h+var_176], al
0x1401a0e90  mov     [rsp+1F8h+var_178], al
0x1401a0e97  mov     [r11-175h], r12b
0x1401a0e9e  mov     [r11-173h], r12b
0x1401a0ea5  mov     [r11-16Ch], r12b
0x1401a0eac  mov     [r11-172h], r12b
0x1401a0eb3  mov     dil, r12b
0x1401a0eb6  mov     [rsp+1F8h+var_160], edi
0x1401a0ebd  mov     [r11-174h], r12b
0x1401a0ec4  mov     [r11-171h], r12b
0x1401a0ecb  mov     r13, [rdx+0B8h]
0x1401a0ed2  mov     rbx, [r13+30h]
0x1401a0ed6  mov     [rsp+1F8h+FileObject], rbx
0x1401a0ede  mov     [rsp+1F8h+var_108], rbx
0x1401a0ee6  mov     dword ptr [rcx+1F8h], 1Ah
0x1401a0ef0  movzx   r9d, byte ptr [r13+13h]
0x1401a0ef5  lea     eax, [r9-1]
0x1401a0ef9  test    eax, 0FFFFFFFDh
0x1401a0efe  jz      short loc_1401A0F5A
0x1401a0f00  mov     eax, [rcx+10h]
0x1401a0f03  bt      rax, 14h
0x1401a0f08  jb      short loc_1401A0F2A
0x1401a0f0a  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1401a0f11  test    al, 20h
0x1401a0f13  jz      short loc_1401A0F2A
0x1401a0f15  mov     r8, gs:188h
0x1401a0f1e  lea     rdx, create_c5645
0x1401a0f25  call    McTemplateU0pd_EtwWriteTransfer
0x1401a0f2a  mov     al, cs:NtfsStatusDebugFlags
0x1401a0f30  mov     edi, 0C0000022h
0x1401a0f35  test    al, al
0x1401a0f37  jz      short loc_1401A0F48
0x1401a0f39  mov     r8d, 0A1615h
0x1401a0f3f  mov     edx, edi
0x1401a0f41  xor     ecx, ecx
0x1401a0f43  call    NtfsStatusTraceAndDebugInternal
0x1401a0f48  mov     [rsp+1F8h+var_170], edi
0x1401a0f4f  mov     r15d, 1
0x1401a0f55  jmp     loc_1401A1B8E
0x1401a0f5a  mov     eax, [r13+10h]
0x1401a0f5e  mov     r15d, 1
0x1401a0f64  test    r15b, al
0x1401a0f67  jz      short loc_1401A0F93
0x1401a0f69  mov     al, cs:NtfsStatusDebugFlags
0x1401a0f6f  mov     edi, 0C000000Dh
0x1401a0f74  test    al, al
0x1401a0f76  jz      short loc_1401A0F87
0x1401a0f78  mov     r8d, 0A161Fh
0x1401a0f7e  mov     edx, edi
0x1401a0f80  xor     ecx, ecx
0x1401a0f82  call    NtfsStatusTraceAndDebugInternal
0x1401a0f87  mov     [rsp+1F8h+var_170], edi
0x1401a0f8e  jmp     loc_1401A1B8E
0x1401a0f93  xor     edx, edx
0x1401a0f95  mov     rcx, [r13+30h]
0x1401a0f99  call    TxfGetTransactionFromFileObject
0x1401a0f9e  test    rax, rax
0x1401a0fa1  jz      short loc_1401A0FBA
0x1401a0fa3  mov     al, cs:NtfsStatusDebugFlags
0x1401a0fa9  mov     edi, 0C019005Ah
0x1401a0fae  test    al, al
0x1401a0fb0  jz      short loc_1401A0F87
0x1401a0fb2  mov     r8d, 0A1630h
0x1401a0fb8  jmp     short loc_1401A0F7E
0x1401a0fba  mov     rcx, [r14+68h]
0x1401a0fbe  mov     eax, [rcx+1924h]
0x1401a0fc4  test    al, 2
0x1401a0fc6  jz      short loc_1401A0FF5
0x1401a0fc8  mov     rax, [rcx+1868h]
0x1401a0fcf  test    rax, rax
0x1401a0fd2  jz      short loc_1401A0FF5
0x1401a0fd4  mov     eax, [rax+88h]
0x1401a0fda  mov     r12d, 100000h
0x1401a0fe0  bt      eax, 0Eh
0x1401a0fe4  jnb     short loc_1401A0FFB
0x1401a0fe6  test    [r14+1B4h], r12d
0x1401a0fed  jz      loc_1401A1DDC
0x1401a0ff3  jmp     short loc_1401A0FFB
0x1401a0ff5  mov     r12d, 100000h
0x1401a0ffb  mov     rsi, [r14+68h]
0x1401a0fff  mov     [rsp+1F8h+var_138], rsi
0x1401a1007  test    byte ptr [r13+1Ah], 6
0x1401a100c  jnz     loc_1401A10BE
0x1401a1012  lea     rcx, [rsi+19E8h]; Object
0x1401a1019  mov     [rsp+1F8h+Timeout], 0; Timeout
0x1401a1022  xor     r9d, r9d; Alertable
0x1401a1025  xor     r8d, r8d; WaitMode
0x1401a1028  xor     edx, edx; WaitReason
0x1401a102a  call    cs:__imp_KeWaitForSingleObject
0x1401a1031  nop     dword ptr [rax+rax+00h]
0x1401a1036  mov     edx, 3; EventCode
0x1401a103b  mov     rcx, rbx; FileObject
0x1401a103e  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1401a1045  nop     dword ptr [rax+rax+00h]
0x1401a104a  mov     [rsp+1F8h+var_172], r15b
0x1401a1052  mov     byte ptr [rsp+1F8h+Timeout], 0
0x1401a1057  xor     r9d, r9d
0x1401a105a  mov     r8b, r15b
0x1401a105d  mov     rdx, rsi
0x1401a1060  xor     ecx, ecx
0x1401a1062  call    NtfsFspCloseInternal
0x1401a1067  mov     eax, [rsi+1924h]
0x1401a106d  test    al, 2
0x1401a106f  jz      short loc_1401A109F
0x1401a1071  mov     rcx, [rsi+1868h]
0x1401a1078  test    rcx, rcx
0x1401a107b  jz      short loc_1401A109F
0x1401a107d  mov     rcx, [rcx+18h]
0x1401a1081  add     rcx, 390h; Resource
0x1401a1088  mov     dl, r15b; Wait
0x1401a108b  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a1092  nop     dword ptr [rax+rax+00h]
0x1401a1097  mov     [rsp+1F8h+var_173], r15b
0x1401a109f  mov     r8b, r15b
0x1401a10a2  mov     rdx, rsi
0x1401a10a5  mov     rcx, r14
0x1401a10a8  call    NtfsAcquireExclusiveVcb
0x1401a10ad  mov     [rsi+1591h], r15b
0x1401a10b4  mov     [rsp+1F8h+var_171], r15b
0x1401a10bc  jmp     short loc_1401A10CC
0x1401a10be  mov     r8b, r15b
0x1401a10c1  mov     rdx, rsi
0x1401a10c4  mov     rcx, r14
0x1401a10c7  call    NtfsAcquireSharedVcb
0x1401a10cc  mov     al, r15b
0x1401a10cf  mov     [rsp+1F8h+var_176], al
0x1401a10d6  mov     [rsp+1F8h+var_178], al
0x1401a10dd  lea     rbx, [rsi+4]
0x1401a10e1  mov     r9d, [rbx]
0x1401a10e4  test    r9d, 802h
0x1401a10eb  jz      loc_1401A11A9
0x1401a10f1  mov     eax, [r14+10h]
0x1401a10f5  test    r12, rax
0x1401a10f8  jnz     loc_1401A117F
0x1401a10fe  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1401a1105  test    al, 20h
0x1401a1107  jz      short loc_1401A117F
0x1401a1109  mov     rdx, [rsi+0F8h]
0x1401a1110  movzx   eax, word ptr [rdx+6]
0x1401a1114  cmp     eax, 40h ; '@'
0x1401a1117  ja      short loc_1401A111E
0x1401a1119  test    r15b, al
0x1401a111c  jz      short loc_1401A1120
0x1401a111e  xor     eax, eax
0x1401a1120  mov     [rsp+1F8h+var_160], eax
0x1401a1127  mov     [rsp+1F8h+var_100], ax
0x1401a112f  add     rdx, 20h ; ' '
0x1401a1133  mov     [rsp+1F8h+var_F8], rdx
0x1401a113b  mov     r8, gs:188h
0x1401a1144  movzx   eax, ax
0x1401a1147  shr     eax, 1
0x1401a1149  movzx   ecx, word ptr [rsi+1EC0h]
0x1401a1150  shr     ecx, 1
0x1401a1152  mov     [rsp+1F8h+var_1B8], r9d
0x1401a1157  mov     [rsp+1F8h+var_1C0], rdx
0x1401a115c  mov     dword ptr [rsp+1F8h+var_1C8], eax
0x1401a1160  mov     rax, [rsi+1EC8h]
0x1401a1167  mov     [rsp+1F8h+var_1D0], rax
0x1401a116c  mov     dword ptr [rsp+1F8h+Timeout], ecx
0x1401a1170  mov     r9, rsi
0x1401a1173  lea     rdx, create_c5763
0x1401a117a  call    McTemplateU0ppwwd_EtwWriteTransfer
0x1401a117f  mov     al, cs:NtfsStatusDebugFlags
0x1401a1185  mov     edi, 0C0000022h
0x1401a118a  test    al, al
0x1401a118c  jz      short loc_1401A119D
0x1401a118e  mov     r8d, 0A168Eh
0x1401a1194  mov     edx, edi
0x1401a1196  xor     ecx, ecx
0x1401a1198  call    NtfsStatusTraceAndDebugInternal
0x1401a119d  mov     [rsp+1F8h+var_170], edi
0x1401a11a4  jmp     loc_1401A1B86
0x1401a11a9  xor     r8d, r8d
0x1401a11ac  mov     rdx, rsi
0x1401a11af  mov     rcx, r14
0x1401a11b2  call    NtfsPingVolume
0x1401a11b7  test    al, al
0x1401a11b9  jz      loc_1401A1DB4
0x1401a11bf  mov     eax, [rbx]
0x1401a11c1  test    r15b, al
0x1401a11c4  jz      loc_1401A1DB4
0x1401a11ca  mov     rax, [rsi+0C0h]
0x1401a11d1  mov     rax, [rax+0B8h]
0x1401a11d8  mov     [rsp+1F8h+var_150], rax
0x1401a11e0  xor     r9d, r9d
0x1401a11e3  xor     r8d, r8d
0x1401a11e6  mov     rdx, rax
0x1401a11e9  mov     rcx, r14
0x1401a11ec  call    NtfsAcquireExclusiveFcb
0x1401a11f1  mov     [rsp+1F8h+var_175], r15b
0x1401a11f9  mov     rcx, [rsp+1F8h+var_140]
0x1401a1201  mov     rax, [rcx+0B8h]
0x1401a1208  mov     rax, [rax+8]
0x1401a120c  xor     edx, edx
0x1401a120e  mov     byte ptr [rsp+1F8h+var_1B8], dl
0x1401a1212  mov     byte ptr [rsp+1F8h+var_1C0], dl
0x1401a1216  mov     byte ptr [rsp+1F8h+var_1C8], dl
0x1401a121a  mov     eax, [rax+10h]
0x1401a121d  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x1401a1221  mov     [rsp+1F8h+Timeout], rcx
0x1401a1226  xor     r9d, r9d
0x1401a1229  mov     r8, [rsp+1F8h+var_150]
0x1401a1231  mov     rcx, r14
0x1401a1234  call    NtfsAccessCheck
0x1401a1239  xor     r8d, r8d
0x1401a123c  mov     rdx, [rsp+1F8h+var_150]
0x1401a1244  mov     rcx, r14
0x1401a1247  call    NtfsReleaseFcbEx
0x1401a124c  mov     [rsp+1F8h+var_175], 0
0x1401a1254  mov     rax, [r13+8]
0x1401a1258  mov     rcx, [rax+8]
0x1401a125c  mov     eax, [rcx+14h]
0x1401a125f  test    byte ptr [r13+1Ah], 6
0x1401a1264  jnz     loc_1401A1859
0x1401a126a  test    al, 6
0x1401a126c  jz      short loc_1401A1298
0x1401a126e  mov     [rsp+1F8h+MemoryAllocated], r15b
0x1401a1276  mov     [rsp+1F8h+var_148], r15b
0x1401a127e  call    cs:__imp_FsRtlAreVolumeStartupApplicationsComplete
0x1401a1285  nop     dword ptr [rax+rax+00h]
0x1401a128a  test    al, al
0x1401a128c  jz      short loc_1401A1298
0x1401a128e  mov     eax, 0FFFEh
0x1401a1293  and     [r13+1Ah], ax
0x1401a1298  test    [r13+1Ah], r15b
0x1401a129c  jnz     loc_1401A14D4
0x1401a12a2  xor     ebx, ebx
0x1401a12a4  mov     [rsp+1F8h+var_144], ebx
0x1401a12ab  mov     rax, [rsi+0A8h]
0x1401a12b2  test    rax, rax
0x1401a12b5  jz      short loc_1401A12C4
0x1401a12b7  mov     ebx, [rax+0D0h]
0x1401a12bd  mov     [rsp+1F8h+var_144], ebx
0x1401a12c4  cmp     [rsp+1F8h+var_173], 0
0x1401a12cc  jz      loc_1401A13F6
0x1401a12d2  mov     rcx, [rsi+1868h]
0x1401a12d9  mov     edx, 4
0x1401a12de  mov     r8d, 84h
0x1401a12e4  mov     eax, edx
0x1401a12e6  lock cmpxchg [rcx+r8], edx
0x1401a12ec  cmp     eax, 2
0x1401a12ef  jz      short loc_1401A1309
0x1401a12f1  mov     rcx, [rsi+1868h]
0x1401a12f8  mov     eax, edx
0x1401a12fa  lock cmpxchg [rcx+r8], edx
0x1401a1300  cmp     eax, r15d
0x1401a1303  jnz     loc_1401A13F6
0x1401a1309  mov     rax, [rsi+1868h]
0x1401a1310  cmp     qword ptr [rax+48h], 0
0x1401a1315  jz      short loc_1401A1321
0x1401a1317  add     ebx, r15d
0x1401a131a  mov     [rsp+1F8h+var_144], ebx
0x1401a1321  mov     rdi, [rax+1F0h]
0x1401a1328  test    rdi, rdi
0x1401a132b  jz      loc_1401A13F6
0x1401a1331  xor     edx, edx; Val
0x1401a1333  lea     r8d, [rdx+78h]; Size
0x1401a1337  lea     rcx, [rsp+1F8h+pinfoBuffer]; void *
0x1401a133f  call    memset
0x1401a1344  mov     [rsp+1F8h+pcbInfoBuffer], 0
0x1401a134f  mov     [rsp+1F8h+pcbInfoBuffer], 78h ; 'x'
0x1401a135a  lea     r8, [rsp+1F8h+pcbInfoBuffer]; pcbInfoBuffer
0x1401a1362  lea     rdx, [rsp+1F8h+pinfoBuffer]; pinfoBuffer
0x1401a136a  mov     rcx, rdi; plfoLog
0x1401a136d  call    cs:__imp_ClfsGetLogFileInformation
0x1401a1374  nop     dword ptr [rax+rax+00h]
0x1401a1379  mov     edi, eax
0x1401a137b  mov     [rsp+1F8h+var_170], eax
0x1401a1382  test    eax, eax
0x1401a1384  jns     short loc_1401A13E4
0x1401a1386  mov     al, cs:NtfsStatusDebugFlags
0x1401a138c  test    al, al
0x1401a138e  jz      loc_1401A1B86
0x1401a1394  cmp     edi, 0FFFFFFEDh
0x1401a1397  jnb     loc_1401A1B86
0x1401a139d  cmp     edi, 0C0000016h
0x1401a13a3  jz      loc_1401A1B86
0x1401a13a9  lea     eax, [rdi+7FFFFFFBh]
  ... truncated ...
```
