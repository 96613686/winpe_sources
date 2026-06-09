# TxfFsctlModifyRm

- ea: `0x1400fc0e0`
- end: `0x1400fd533`
- name: `TxfFsctlModifyRm`
- size: `5203`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1402491f8`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x14000cb00`
- `0x14000d1e0`
- `0x140010be0`
- `0x1400291f0`
- `0x140029d80`
- `0x14004088c`
- `0x140052020`
- `0x140052f94`
- `0x140054360`
- `0x1400592c0`
- `0x1400f9d98`
- `0x1400fa6e8`
- `0x1400fc0e0`
- `0x14010d198`
- `0x14013add0`
- `0x1401403d0`
- `0x140188d34`
- `0x140191424`
- `0x14020b644`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fc2da`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fd250`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fc2da`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fd250`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd2b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd2cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd43e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd4b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4660`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c46d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd2b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd2cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd43e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd4b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4660`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c46d8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd1d8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd1d8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSizeAsClient` at `0x1400fcdfd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtSetLogFileSizeAsClient` at `0x1400fcdfd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRemovePolicy` at `0x1400fccf3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtRemovePolicy` at `0x1400fccf3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc797`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc883`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc968`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fca48`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcb56`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcc58`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc797`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc883`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fc968`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fca48`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcb56`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsMgmtInstallPolicy` at `0x1400fcc58`

## pseudocode

```c
__int64 __fastcall TxfFsctlModifyRm(unsigned __int64 a1, unsigned __int64 a2, unsigned int a3, int *a4)
{
  int v6; // r13d
  int v7; // edx
  __int64 v8; // r15
  __int64 v9; // r8
  NTSTATUS NewRMGuid; // ebx
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r12d
  __int64 v17; // r8
  __int64 v18; // r8
  int *v19; // r13
  int v20; // ecx
  unsigned int v21; // eax
  __int64 v22; // r8
  int v23; // eax
  int v24; // ecx
  unsigned int v25; // eax
  unsigned __int64 v26; // r13
  __int64 v27; // r12
  int v28; // edx
  int v29; // ecx
  int v30; // ecx
  int *v31; // rdx
  int v32; // r12d
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r10
  __int64 v37; // r8
  bool v38; // r13
  int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // r12
  __int64 v42; // rax
  __int64 v43; // r13
  int v44; // eax
  int v45; // eax
  unsigned int v46; // eax
  int CompletionRoutine; // [rsp+20h] [rbp-158h]
  bool v49; // [rsp+90h] [rbp-E8h]
  char v50[3]; // [rsp+91h] [rbp-E7h] BYREF
  NTSTATUS v51; // [rsp+94h] [rbp-E4h]
  char v52; // [rsp+98h] [rbp-E0h]
  char v53; // [rsp+99h] [rbp-DFh]
  char v54; // [rsp+9Ah] [rbp-DEh]
  char v55; // [rsp+9Bh] [rbp-DDh] BYREF
  int v56; // [rsp+9Ch] [rbp-DCh] BYREF
  int v57; // [rsp+A0h] [rbp-D8h] BYREF
  int v58; // [rsp+A4h] [rbp-D4h] BYREF
  __int16 v59; // [rsp+A8h] [rbp-D0h] BYREF
  int v60; // [rsp+ACh] [rbp-CCh]
  int *v61; // [rsp+B0h] [rbp-C8h] BYREF
  int *v62; // [rsp+B8h] [rbp-C0h]
  __int64 v63; // [rsp+C0h] [rbp-B8h] BYREF
  unsigned __int64 NewSizeInContainers; // [rsp+C8h] [rbp-B0h] BYREF
  _QWORD v65[2]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-98h]
  __int64 v67; // [rsp+E8h] [rbp-90h]
  __int64 v68; // [rsp+F0h] [rbp-88h] BYREF
  int v69; // [rsp+F8h] [rbp-80h]
  int v70; // [rsp+FCh] [rbp-7Ch]
  int *v71; // [rsp+100h] [rbp-78h]
  unsigned __int64 ResultingSizeInContainers; // [rsp+108h] [rbp-70h] BYREF
  _CLFS_MGMT_POLICY Policy; // [rsp+110h] [rbp-68h] BYREF
  __int128 v74; // [rsp+128h] [rbp-50h] BYREF

  v61 = a4;
  NewSizeInContainers = a2;
  v71 = a4;
  v65[1] = a1;
  *(_QWORD *)&v74 = a2;
  v62 = a4;
  memset(&Policy, 0, sizeof(Policy));
  v68 = 0;
  v65[0] = 0;
  v50 = 0;
  v6 = 0;
  LODWORD(v63) = 0;
  v56 = 0;
  if ( !a4 || a3 < 0x28 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687828;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  v7 = *a4;
  if ( (*a4 & 0xFFFC0200) != 0 || !v7 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687838;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  if ( (v7 & 0x84) == 0x84
    || (*a4 & 0x108) == 0x108
    || (*a4 & 0x30) == 48
    || (*a4 & 0xC00) == 3072
    || (v7 & 0x4000) != 0 && (v7 & 0x8000) != 0
    || (v7 & 0x10000) != 0 && (v7 & 0x20000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687863;
      goto LABEL_239;
    }
    return (unsigned int)-1073741811;
  }
  v8 = *(_QWORD *)(a2 + 320);
  v67 = v8;
  if ( ((v7 & 0x4000) != 0 || (v7 & 0x8000) != 0) && v8 != *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2687874;
LABEL_239:
      NewRMGuid = -1073741811;
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, v9);
      return (unsigned int)NewRMGuid;
    }
    return (unsigned int)-1073741811;
  }
  ResultingSizeInContainers = a1;
  NewRMGuid = 0;
  v51 = 0;
  v66 = v8;
  v52 = 0;
  v49 = 0;
  v54 = 0;
  v53 = 0;
  if ( (v7 & 0x10000) != 0 || (v7 & 0x20000) != 0 )
  {
    v11 = *(_QWORD *)(v8 + 16);
    if ( v8 == *(_QWORD *)(v11 + 6248) && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 248) + 16LL) + 48LL) & 0x100) != 0 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v9 = 2687887;
        goto LABEL_239;
      }
      return (unsigned int)-1073741811;
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v8 + 24) + 912LL), 1u);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 132), 4, 4) == 2 )
  {
LABEL_30:
    if ( (*(_DWORD *)(*(_QWORD *)(NewSizeInContainers + 96) + 4LL) & 0x2000000) != 0 )
    {
      NewRMGuid = -1073741662;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_28;
      v12 = 2687928;
      goto LABEL_27;
    }
    v13 = *v61;
    v14 = 0;
    if ( (*v61 & 0x4000) != 0 )
      v14 = 0x200000;
    v58 = v14;
    v69 = v14;
    v15 = 0;
    if ( (v13 & 0x8000) != 0 )
      v15 = 0x200000;
    v57 = v15;
    v70 = v15;
    if ( (v13 & 0x10000) != 0 )
    {
      v6 = 4;
      LODWORD(v63) = 4;
      v16 = 8;
      v56 = 8;
    }
    else
    {
      v16 = v56;
    }
    if ( (v13 & 0x20000) != 0 )
    {
      v6 |= 8u;
      LODWORD(v63) = v6;
      v16 |= 4u;
      v56 = v16;
    }
    if ( v14 || v15 )
    {
      NtfsAcquireExclusiveFcb(a1, NewSizeInContainers, 0, 0);
      TxfUpdateTxfDataAttributeMembers(a1, NewSizeInContainers, CompletionRoutine, v58, v57, 0, 0, 0, 0, 0, 0);
      if ( v53 || !v6 && !v16 )
      {
        NtfsCheckpointCurrentTransaction(a1);
        *(_DWORD *)(a1 + 4) |= 0x400u;
        NtfsCleanupIrpContext(a1, 0, v17);
        NewRMGuid = 0;
        v51 = 0;
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    }
    if ( v53 )
      goto LABEL_221;
    if ( v6 || v56 )
    {
      NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v8 + 288), 0);
      TxfUpdateTopsMetadataStream(a1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, (__int64)&v63, (__int64)&v56);
      NtfsCheckpointCurrentTransaction(a1);
      *(_DWORD *)(a1 + 4) |= 0x400u;
      NtfsCleanupIrpContext(a1, 0, v18);
      NewRMGuid = 0;
      v51 = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    }
    v19 = v61;
    if ( (*v61 & 2) != 0 )
    {
      v74 = *(_OWORD *)(v8 + 672);
      NewRMGuid = TxfCreateNewRMGuid(a1);
      v51 = NewRMGuid;
      if ( NewRMGuid < 0 )
        goto LABEL_221;
      if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0spjj_EtwWriteTransfer(
          v20,
          (unsigned int)txfctrl_c1120,
          (unsigned int)"TxfFsctlModifyRm",
          v8,
          (__int64)&v74,
          v8 + 672);
      }
    }
    if ( (*v19 & 4) != 0 )
    {
      v21 = v62[1];
      if ( v21 < 2 )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688119;
        goto LABEL_27;
      }
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      *(_QWORD *)&Policy.PolicyFlags = 1;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = v21;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688145;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x80u) != 0 )
    {
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMaximumSize;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0xFFFFFFFFLL;
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688174;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 8) != 0 )
    {
      Policy.PolicyFlags = 0;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0;
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMinimumSize;
      Policy.PolicyParameters.MaximumSize.Containers = v62[2];
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688207;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x100) != 0 )
    {
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyMinimumSize;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0xFFFFFFFFLL;
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688236;
        goto LABEL_71;
      }
    }
    v23 = *v19 & 0x20;
    v24 = *v19 & 0x10;
    if ( v24 || v23 )
    {
      Policy.PolicyFlags = 0;
      Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = 0;
      Policy.Version = 1;
      Policy.LengthInBytes = 24;
      Policy.PolicyType = ClfsMgmtPolicyGrowthRate;
      if ( v24 )
      {
        Policy.PolicyParameters.MaximumSize.Containers = v62[4];
      }
      else if ( v23 )
      {
        Policy.PolicyParameters.GrowthRate.RelativeGrowthPercentage = v62[4];
      }
      Policy.PolicyFlags = 1;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v8 + 496), &Policy, 0x18u);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NewRMGuid < 0 )
      {
        if ( !NtfsStatusDebugFlags
          || (unsigned int)NewRMGuid >= 0xFFFFFFED
          || NewRMGuid == -1073741802
          || NewRMGuid == -1073741807
          || (unsigned int)(NewRMGuid + 2147483643) <= 1
          || NewRMGuid == -1073741608 )
        {
          goto LABEL_221;
        }
        v22 = 2688275;
        goto LABEL_71;
      }
    }
    if ( (*v19 & 0x40) != 0 )
    {
      v25 = v62[5];
      v26 = ResultingSizeInContainers;
      if ( v25 )
      {
        Policy.Version = 1;
        Policy.LengthInBytes = 24;
        Policy.PolicyType = ClfsMgmtPolicyAutoShrink;
        Policy.PolicyParameters.NewContainerSuffix.NextContainerSuffix = v25;
        Policy.PolicyFlags = 1;
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(v26 + 4) |= 0x200u;
        v27 = v66;
        NewRMGuid = ClfsMgmtInstallPolicy(*(PLOG_FILE_OBJECT *)(v66 + 496), &Policy, 0x18u);
        v51 = NewRMGuid;
        *(_DWORD *)(v26 + 4) &= ~0x200u;
        if ( NewRMGuid < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)NewRMGuid >= 0xFFFFFFED
            || NewRMGuid == -1073741802
            || NewRMGuid == -1073741807
            || (unsigned int)(NewRMGuid + 2147483643) <= 1
            || NewRMGuid == -1073741608 )
          {
            goto LABEL_221;
          }
          v22 = 2688306;
          goto LABEL_71;
        }
      }
      else
      {
        NtfsPurgeFileRecordCache(a1);
        *(_DWORD *)(v26 + 4) |= 0x200u;
        v27 = v66;
        NewRMGuid = ClfsMgmtRemovePolicy(*(PLOG_FILE_OBJECT *)(v66 + 496), ClfsMgmtPolicyAutoShrink);
        v51 = NewRMGuid;
        *(_DWORD *)(v26 + 4) &= ~0x200u;
        if ( NewRMGuid < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)NewRMGuid >= 0xFFFFFFED
            || NewRMGuid == -1073741802
            || NewRMGuid == -1073741807
            || (unsigned int)(NewRMGuid + 2147483643) <= 1
            || NewRMGuid == -1073741608 )
          {
            goto LABEL_221;
          }
          v22 = 2688325;
LABEL_71:
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)NewRMGuid, v22);
          goto LABEL_221;
        }
      }
      v19 = v61;
    }
    else
    {
      v27 = v66;
    }
    v28 = *v19;
    v29 = *v19 & 0x800;
    if ( (*v19 & 0x400) != 0 || v29 )
    {
      NewSizeInContainers = 0;
      ResultingSizeInContainers = 0;
      NewSizeInContainers = (unsigned int)v62[3];
      if ( (v28 & 0x1000) != 0 && v29 )
        NewSizeInContainers = 0;
      NtfsPurgeFileRecordCache(a1);
      *(_DWORD *)(a1 + 4) |= 0x200u;
      NewRMGuid = ClfsMgmtSetLogFileSizeAsClient(
                    *(PLOG_FILE_OBJECT *)(v8 + 496),
                    *(PCLFS_MGMT_CLIENT *)(v8 + 560),
                    &NewSizeInContainers,
                    &ResultingSizeInContainers,
                    0,
                    0);
      v51 = NewRMGuid;
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( NtfsStatusDebugFlags
        && NewRMGuid
        && NewRMGuid != 294
        && (unsigned int)(NewRMGuid - 298) > 1
        && (unsigned int)NewRMGuid < 0xFFFFFFED
        && NewRMGuid != -1073741608
        && NewRMGuid != -1073741802
        && NewRMGuid != -1073741807
        && (unsigned int)(NewRMGuid + 2147483643) > 1
        && NewRMGuid != 259 )
      {
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)NewRMGuid, 2688357);
      }
    }
    v30 = *v19;
    if ( (*v19 & 1) != 0 )
    {
      if ( v8 == *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688370;
        goto LABEL_27;
      }
      v31 = v62;
      if ( (unsigned __int16)(*((_WORD *)v62 + 16) - 1) > 1u )
      {
        NewRMGuid = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_28;
        v12 = 2688377;
        goto LABEL_27;
      }
    }
    else
    {
      v31 = v62;
    }
    if ( (v30 & 0x2000) != 0 )
    {
      v32 = 0;
      v60 = 0;
      v58 = 0;
      v57 = 0;
      LODWORD(v61) = 0;
      v59 = 0;
      if ( (v30 & 0x84) != 0 )
      {
        v32 = 4;
        v60 = 4;
        v33 = v31[1];
        v58 = v33;
        if ( (v30 & 0x80u) != 0 )
          v33 = 0;
        v58 = v33;
      }
      if ( (v30 & 0x108) != 0 )
      {
        v32 |= 8u;
        v60 = v32;
        v34 = v31[2];
        v57 = v34;
        if ( (v30 & 0x100) != 0 )
          v34 = 0;
        v57 = v34;
      }
      if ( (v30 & 0x30) != 0 )
      {
        v32 |= 0x10u;
        v60 = v32;
        v35 = v31[4];
        LODWORD(v61) = v35;
        if ( (v30 & 0x20) != 0 )
          LODWORD(v61) = v35 | 0x80000000;
      }
      if ( (v30 & 0x40) != 0 && (unsigned int)v31[5] <= 0x64 )
      {
        v32 |= 0x40u;
        v60 = v32;
        v59 = *((_WORD *)v31 + 10);
      }
      if ( NewRMGuid == -1073741432 )
        NtfsCheckpointForLogFileFull(a1);
      NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v8 + 288), 0);
      if ( (*v19 & 1) != 0 )
        v36 = (__int64)(v62 + 8);
      else
        v36 = 0;
      TxfUpdateTopsMetadataStream(
        a1,
        0,
        0,
        0,
        0,
        0,
        0,
        (unsigned __int64)&v58 & -(__int64)((v32 & 4) != 0),
        (unsigned __int64)&v57 & -(__int64)((v32 & 8) != 0),
        (unsigned __int64)&v61 & -(__int64)((v32 & 0x10) != 0),
        (unsigned __int64)&v59 & -(__int64)((v32 & 0x40) != 0),
        v36,
        0,
        0);
      NtfsCheckpointCurrentTransaction(a1);
      *(_DWORD *)(a1 + 4) |= 0x400u;
      NtfsCleanupIrpContext(a1, 0, v37);
      NewRMGuid = 0;
      v51 = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
      v27 = v66;
    }
    if ( (*v19 & 1) == 0 )
      goto LABEL_221;
    v38 = *((_WORD *)v62 + 16) == 2;
    v49 = v38;
    if ( *((_WORD *)v62 + 16) != 2 )
      goto LABEL_184;
    if ( v8 != *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) && (*(_DWORD *)(v8 + 128) & 0x10) != 0 )
    {
LABEL_185:
      NewRMGuid = 0;
LABEL_186:
      v51 = NewRMGuid;
      goto LABEL_222;
    }
    if ( *((_WORD *)v62 + 16) != 2 )
    {
LABEL_184:
      if ( v8 == *(_QWORD *)(*(_QWORD *)(v8 + 16) + 6248LL) || (*(_DWORD *)(v8 + 128) & 0x10) == 0 )
        goto LABEL_185;
    }
    v39 = *(_DWORD *)(v27 + 128);
    if ( *((_WORD *)v62 + 16) == 2 )
      v40 = v39 | 0x10;
    else
      v40 = v39 & 0xFFFFFFEF;
    *(_DWORD *)(v27 + 128) = v40;
    v54 = 1;
    while ( 1 )
    {
      if ( !v50 )
      {
        ExAcquireResourceSharedLite(*(PERESOURCE *)(v8 + 160), 1u);
        v50 = 1;
      }
      if ( v68 )
      {
        if ( v52 )
        {
          v65[0] = v68;
          v52 = 0;
        }
        v42 = *(_QWORD *)(v68 + 104);
        v41 = v42;
        v68 = v42;
        v43 = v42;
      }
      else
      {
        v41 = *(_QWORD *)(v8 + 152);
        v68 = v41;
        v42 = v41;
        v43 = v41;
      }
      if ( !v42 )
        goto LABEL_221;
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v43 + 24) + 80LL), 1u);
      ++*(_DWORD *)(v43 + 4);
      v52 = 1;
      if ( (*(_DWORD *)(v43 + 16) & 0x20000) == 0
        || (v55 = 1, TxfWaitForEnlistmentCompletion(0, v41, (unsigned int)&v55, v8 + 144, (__int64)&v50), v55) )
      {
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v43 + 24) + 80LL));
      }
      if ( v50 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(v8 + 160));
        v50 = 0;
      }
      if ( v65[0] )
        TxfDereferenceTransaction(v65, 0);
      if ( *(_QWORD *)(v43 + 232) )
      {
        v38 = v49;
        v44 = TxfTransSwitchLoggingMode(v41, v49);
        v51 = v44;
        if ( (unsigned int)(v44 + 1072103403) > 1 && v44 != -1073741431 && v44 < 0 )
        {
          if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
          {
            McTemplateU0spjpjd_EtwWriteTransfer(
              v8 + 672,
              (unsigned int)txfctrl_c1700,
              (unsigned int)"TxfFsctlModifyRm",
              v8,
              v8 + 672,
              v41,
              v41 + 256,
              v44);
          }
          NewRMGuid = TxfTryAbortTransaction(a1, v8, v41, 0, 0);
          v51 = NewRMGuid;
          if ( NewRMGuid < 0 )
          {
            if ( (*(_DWORD *)(v41 + 16) & 1) != 0 )
            {
              NewRMGuid = -1073741670;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 2688702);
              goto LABEL_186;
            }
            NewRMGuid = TxfTryAbortTransaction(a1, v8, v41, 0, 0);
            v51 = NewRMGuid;
          }
          if ( (unsigned int)(NewRMGuid + 1072103403) > 1 )
            goto LABEL_222;
        }
        NewRMGuid = 0;
        v51 = 0;
      }
    }
  }
  if ( (*v61 & 0xFFFF3FFF) == 0 )
  {
    v53 = 1;
    goto LABEL_30;
  }
  NewRMGuid = -1072103419;
  if ( NtfsStatusDebugFlags )
  {
    v12 = 2687910;
LABEL_27:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)NewRMGuid, v12);
  }
LABEL_28:
  v51 = NewRMGuid;
LABEL_221:
  v38 = v49;
LABEL_222:
  if ( v50 )
    ExReleaseResourceLite(*(PERESOURCE *)(v8 + 160));
  if ( v65[0] )
    TxfDereferenceTransaction(v65, 0);
  if ( v52 )
    TxfDereferenceTransaction(&v68, 0);
  if ( v54 && NewRMGuid < 0 )
  {
    v45 = *(_DWORD *)(v66 + 128);
    if ( v38 )
      v46 = v45 & 0xFFFFFFEF;
    else
      v46 = v45 | 0x10;
    *(_DWORD *)(v66 + 128) = v46;
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v8 + 24) + 912LL));
  return (unsigned int)NewRMGuid;
}

```

## disassembly

```asm
0x1400fc0e0  mov     r11, rsp
0x1400fc0e3  push    rbx
0x1400fc0e4  push    rsi
0x1400fc0e5  push    rdi
0x1400fc0e6  push    r12
0x1400fc0e8  push    r13
0x1400fc0ea  push    r14
0x1400fc0ec  push    r15
0x1400fc0ee  sub     rsp, 140h
0x1400fc0f5  mov     rax, cs:__security_cookie
0x1400fc0fc  xor     rax, rsp
0x1400fc0ff  mov     [rsp+178h+var_40], rax
0x1400fc107  mov     [rsp+178h+var_C8], r9
0x1400fc10f  mov     r10, rdx
0x1400fc112  mov     [rsp+178h+NewSizeInContainers], rdx
0x1400fc11a  mov     rsi, rcx
0x1400fc11d  mov     [rsp+178h+var_78], r9
0x1400fc125  mov     [rsp+178h+var_A0], rcx
0x1400fc12d  mov     qword ptr [rsp+178h+var_50], rdx
0x1400fc135  mov     [rsp+178h+var_C0], r9
0x1400fc13d  xorps   xmm0, xmm0
0x1400fc140  xor     eax, eax
0x1400fc142  movups  xmmword ptr [r11-68h], xmm0
0x1400fc147  mov     [r11-58h], rax
0x1400fc14b  xor     edi, edi
0x1400fc14d  mov     [r11-88h], rdi
0x1400fc154  mov     [r11-0A8h], rdi
0x1400fc15b  mov     [rsp+178h+var_E7], dil
0x1400fc163  mov     r13d, edi
0x1400fc166  mov     dword ptr [rsp+178h+var_B8], edi
0x1400fc16d  mov     dword ptr [rsp+178h+var_DC], edi
0x1400fc174  test    r9, r9
0x1400fc177  jz      loc_1400FD4F6
0x1400fc17d  cmp     r8d, 28h ; '('
0x1400fc181  jb      loc_1400FD4F6
0x1400fc187  mov     edx, [r9]
0x1400fc18a  test    edx, 0FFFC0200h
0x1400fc190  jnz     loc_1400FD4D6
0x1400fc196  test    edx, edx
0x1400fc198  jz      loc_1400FD4D6
0x1400fc19e  mov     eax, edx
0x1400fc1a0  and     eax, 84h
0x1400fc1a5  cmp     al, 84h
0x1400fc1a7  jz      loc_1400FD4C4
0x1400fc1ad  mov     eax, edx
0x1400fc1af  and     eax, 108h
0x1400fc1b4  cmp     eax, 108h
0x1400fc1b9  jz      loc_1400FD4C4
0x1400fc1bf  mov     eax, edx
0x1400fc1c1  mov     ecx, 0C00h
0x1400fc1c6  and     eax, ecx
0x1400fc1c8  cmp     eax, ecx
0x1400fc1ca  setz    cl
0x1400fc1cd  mov     eax, edx
0x1400fc1cf  and     eax, 30h
0x1400fc1d2  cmp     al, 30h ; '0'
0x1400fc1d4  setz    al
0x1400fc1d7  or      cl, al
0x1400fc1d9  jnz     loc_1400FD4C4
0x1400fc1df  mov     eax, edx
0x1400fc1e1  and     eax, 4000h
0x1400fc1e6  mov     r12d, 8000h
0x1400fc1ec  jz      short loc_1400FC1F7
0x1400fc1ee  test    r12d, edx
0x1400fc1f1  jnz     loc_1400FD4C4
0x1400fc1f7  mov     ecx, edx
0x1400fc1f9  and     ecx, 10000h
0x1400fc1ff  jz      short loc_1400FC20B
0x1400fc201  bt      edx, 11h
0x1400fc205  jb      loc_1400FD4C4
0x1400fc20b  mov     r15, [r10+140h]
0x1400fc212  mov     [rsp+178h+var_90], r15
0x1400fc21a  test    eax, eax
0x1400fc21c  jnz     short loc_1400FC223
0x1400fc21e  test    r12d, edx
0x1400fc221  jz      short loc_1400FC249
0x1400fc223  mov     rax, [r15+10h]
0x1400fc227  cmp     r15, [rax+1868h]
0x1400fc22e  jz      short loc_1400FC249
0x1400fc230  mov     al, cs:NtfsStatusDebugFlags
0x1400fc236  test    al, al
0x1400fc238  jz      loc_1400FD508
0x1400fc23e  mov     r8d, 290382h
0x1400fc244  jmp     loc_1400FD4E6
0x1400fc249  mov     [rsp+178h+ResultingSizeInContainers], rsi
0x1400fc251  mov     ebx, edi
0x1400fc253  mov     [rsp+178h+var_E4], ebx
0x1400fc25a  mov     [rsp+178h+var_98], r15
0x1400fc262  mov     [rsp+178h+var_E0], dil
0x1400fc26a  mov     [rsp+178h+var_E8], dil
0x1400fc272  mov     [rsp+178h+var_DE], dil
0x1400fc27a  mov     [rsp+178h+var_DF], dil
0x1400fc282  test    ecx, ecx
0x1400fc284  jnz     short loc_1400FC28C
0x1400fc286  bt      edx, 11h
0x1400fc28a  jnb     short loc_1400FC2C6
0x1400fc28c  mov     rax, [r15+10h]
0x1400fc290  cmp     r15, [rax+1868h]
0x1400fc297  jnz     short loc_1400FC2C6
0x1400fc299  mov     rax, [rax+0F8h]
0x1400fc2a0  mov     rcx, [rax+10h]
0x1400fc2a4  test    dword ptr [rcx+30h], 100h
0x1400fc2ab  jz      short loc_1400FC2C6
0x1400fc2ad  mov     al, cs:NtfsStatusDebugFlags
0x1400fc2b3  test    al, al
0x1400fc2b5  jz      loc_1400FD508
0x1400fc2bb  mov     r8d, 29038Fh
0x1400fc2c1  jmp     loc_1400FD4E6
0x1400fc2c6  mov     rcx, [r15+18h]
0x1400fc2ca  add     rcx, 390h; Resource
0x1400fc2d1  mov     r14d, 1
0x1400fc2d7  mov     dl, r14b; Wait
0x1400fc2da  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fc2e1  nop     dword ptr [rax+rax+00h]
0x1400fc2e6  lea     r9d, [r14+3]
0x1400fc2ea  mov     eax, r9d
0x1400fc2ed  lock cmpxchg [r15+84h], r9d
0x1400fc2f6  lea     r10d, [r14+1]
0x1400fc2fa  mov     rdx, [rsp+178h+var_C8]
0x1400fc302  cmp     eax, r10d
0x1400fc305  jz      short loc_1400FC341
0x1400fc307  test    dword ptr [rdx], 0FFFF3FFFh
0x1400fc30d  jz      short loc_1400FC339
0x1400fc30f  mov     al, cs:NtfsStatusDebugFlags
0x1400fc315  mov     ebx, 0C0190005h
0x1400fc31a  test    al, al
0x1400fc31c  jz      short loc_1400FC32D
0x1400fc31e  mov     r8d, 2903A6h
0x1400fc324  mov     edx, ebx
0x1400fc326  xor     ecx, ecx
0x1400fc328  call    NtfsStatusTraceAndDebugInternal
0x1400fc32d  mov     [rsp+178h+var_E4], ebx
0x1400fc334  jmp     loc_1400FD425
0x1400fc339  mov     [rsp+178h+var_DF], r14b
0x1400fc341  mov     rax, [rsp+178h+NewSizeInContainers]
0x1400fc349  mov     rax, [rax+60h]
0x1400fc34d  test    dword ptr [rax+4], 2000000h
0x1400fc354  jz      short loc_1400FC36D
0x1400fc356  mov     al, cs:NtfsStatusDebugFlags
0x1400fc35c  mov     ebx, 0C00000A2h
0x1400fc361  test    al, al
0x1400fc363  jz      short loc_1400FC32D
0x1400fc365  mov     r8d, 2903B8h
0x1400fc36b  jmp     short loc_1400FC324
0x1400fc36d  mov     eax, [rdx]
0x1400fc36f  bt      eax, 0Eh
0x1400fc373  mov     ecx, edi
0x1400fc375  mov     edx, 200000h
0x1400fc37a  cmovb   ecx, edx
0x1400fc37d  mov     [rsp+178h+var_D4], ecx
0x1400fc384  mov     [rsp+178h+var_80], ecx
0x1400fc38b  test    r12d, eax
0x1400fc38e  mov     r8d, edi
0x1400fc391  cmovnz  r8d, edx
0x1400fc395  mov     dword ptr [rsp+178h+var_DC+4], r8d
0x1400fc39d  mov     [rsp+178h+var_7C], r8d
0x1400fc3a5  bt      eax, 10h
0x1400fc3a9  jnb     short loc_1400FC3C6
0x1400fc3ab  mov     r13d, r9d
0x1400fc3ae  mov     dword ptr [rsp+178h+var_B8], r9d
0x1400fc3b6  mov     r12d, 8
0x1400fc3bc  mov     dword ptr [rsp+178h+var_DC], r12d
0x1400fc3c4  jmp     short loc_1400FC3CE
0x1400fc3c6  mov     r12d, dword ptr [rsp+178h+var_DC]
0x1400fc3ce  bt      eax, 11h
0x1400fc3d2  jnb     short loc_1400FC3EB
0x1400fc3d4  or      r13d, 8
0x1400fc3d8  mov     dword ptr [rsp+178h+var_B8], r13d
0x1400fc3e0  or      r12d, r9d
0x1400fc3e3  mov     dword ptr [rsp+178h+var_DC], r12d
0x1400fc3eb  test    ecx, ecx
0x1400fc3ed  jnz     short loc_1400FC3F8
0x1400fc3ef  test    r8d, r8d
0x1400fc3f2  jz      loc_1400FC53C
0x1400fc3f8  cmp     ebx, 0C0000188h
0x1400fc3fe  jnz     short loc_1400FC408
0x1400fc400  mov     rcx, rsi
0x1400fc403  call    NtfsCheckpointForLogFileFull
0x1400fc408  xor     r9d, r9d
0x1400fc40b  xor     r8d, r8d
0x1400fc40e  mov     rdx, [rsp+178h+NewSizeInContainers]
0x1400fc416  mov     rcx, rsi
0x1400fc419  call    NtfsAcquireExclusiveFcb
0x1400fc41e  mov     [rsp+178h+var_118], rdi; __int64
0x1400fc423  mov     [rsp+178h+var_120], rdi; __int64
0x1400fc428  mov     [rsp+178h+var_128], rdi; __int64
0x1400fc42d  mov     [rsp+178h+var_130], rdi; __int64
0x1400fc432  mov     [rsp+178h+var_138], rdi; __int64
0x1400fc437  mov     [rsp+178h+plsn1], rdi; __int64
0x1400fc43c  mov     eax, dword ptr [rsp+178h+var_DC+4]
0x1400fc443  mov     dword ptr [rsp+178h+var_148], eax; int
0x1400fc447  mov     eax, [rsp+178h+var_D4]
0x1400fc44e  mov     dword ptr [rsp+178h+CompletionRoutineData], eax; int
0x1400fc452  mov     rdx, [rsp+178h+NewSizeInContainers]; int
0x1400fc45a  mov     rcx, rsi; int
0x1400fc45d  call    TxfUpdateTxfDataAttributeMembers
0x1400fc462  cmp     [rsp+178h+var_DF], dil
0x1400fc46a  jnz     short loc_1400FC476
0x1400fc46c  test    r13d, r13d
0x1400fc46f  jnz     short loc_1400FC496
0x1400fc471  test    r12d, r12d
0x1400fc474  jnz     short loc_1400FC496
0x1400fc476  mov     rcx, rsi
0x1400fc479  call    NtfsCheckpointCurrentTransaction
0x1400fc47e  bts     dword ptr [rsi+4], 0Ah
0x1400fc483  xor     edx, edx
0x1400fc485  mov     rcx, rsi
0x1400fc488  call    NtfsCleanupIrpContext
0x1400fc48d  mov     ebx, edi
0x1400fc48f  mov     [rsp+178h+var_E4], ebx
0x1400fc496  mov     r10d, 2
0x1400fc49c  jmp     short loc_1400FC512
0x1400fc49e  mov     r8d, eax
0x1400fc4a1  xor     edx, edx
0x1400fc4a3  mov     rsi, [rsp+178h+var_A0]
0x1400fc4ab  mov     rcx, rsi
0x1400fc4ae  call    NtfsProcessException
0x1400fc4b3  mov     ebx, eax
0x1400fc4b5  mov     [rsp+178h+var_E4], eax
0x1400fc4bc  xor     edi, edi
0x1400fc4be  lea     r14d, [rdi+1]
0x1400fc4c2  lea     r10d, [rdi+2]
0x1400fc4c6  mov     r15, [rsp+178h+var_90]
0x1400fc4ce  mov     eax, [rsp+178h+var_80]
0x1400fc4d5  mov     [rsp+178h+var_D4], eax
0x1400fc4dc  mov     eax, [rsp+178h+var_7C]
0x1400fc4e3  mov     dword ptr [rsp+178h+var_DC+4], eax
0x1400fc4ea  mov     r13d, dword ptr [rsp+178h+var_B8]
0x1400fc4f2  mov     rax, qword ptr [rsp+178h+var_50]
0x1400fc4fa  mov     [rsp+178h+NewSizeInContainers], rax
0x1400fc502  mov     rdx, [rsp+178h+var_78]
0x1400fc50a  mov     [rsp+178h+var_C8], rdx
0x1400fc512  mov     rax, [rsi+90h]
0x1400fc519  mov     [rax+18h], edi
0x1400fc51c  cmp     ebx, 0C0000188h
0x1400fc522  mov     r12d, dword ptr [rsp+178h+var_DC]
0x1400fc52a  jz      loc_1400FC3F8
0x1400fc530  cmp     ebx, 0C00000D8h
0x1400fc536  jz      loc_1400FC3F8
0x1400fc53c  cmp     [rsp+178h+var_DF], dil
0x1400fc544  jnz     loc_1400FD425
0x1400fc54a  test    ebx, ebx
0x1400fc54c  js      loc_1400FD425
0x1400fc552  test    r13d, r13d
0x1400fc555  jnz     short loc_1400FC565
0x1400fc557  cmp     dword ptr [rsp+178h+var_DC], r13d
0x1400fc55f  jz      loc_1400FC67A
0x1400fc565  cmp     ebx, 0C0000188h
0x1400fc56b  jnz     short loc_1400FC575
0x1400fc56d  mov     rcx, rsi
0x1400fc570  call    NtfsCheckpointForLogFileFull
0x1400fc575  xor     r8d, r8d
0x1400fc578  mov     rdx, [r15+120h]
0x1400fc57f  mov     rcx, rsi
0x1400fc582  call    NtfsAcquireExclusiveScbEx
0x1400fc587  lea     rax, [rsp+178h+var_DC]
0x1400fc58f  mov     [rsp+178h+var_F8], rax; __int64
0x1400fc597  lea     rax, [rsp+178h+var_B8]
0x1400fc59f  mov     [rsp+178h+var_100], rax; __int64
0x1400fc5a4  mov     [rsp+178h+var_108], rdi; __int64
0x1400fc5a9  mov     [rsp+178h+var_110], rdi; __int64
0x1400fc5ae  mov     [rsp+178h+var_118], rdi; __int64
0x1400fc5b3  mov     [rsp+178h+var_120], rdi; __int64
0x1400fc5b8  mov     [rsp+178h+var_128], rdi; __int64
0x1400fc5bd  mov     [rsp+178h+var_130], rdi; __int64
0x1400fc5c2  mov     [rsp+178h+var_138], rdi; __int64
0x1400fc5c7  mov     [rsp+178h+plsn1], rdi; plsn1
0x1400fc5cc  mov     [rsp+178h+var_148], rdi; __int64
0x1400fc5d1  mov     [rsp+178h+CompletionRoutineData], rdi; __int64
0x1400fc5d6  mov     [rsp+178h+CompletionRoutine], rdi; __int64
0x1400fc5db  xor     r9d, r9d
0x1400fc5de  xor     r8d, r8d
0x1400fc5e1  mov     rdx, [r15+120h]
0x1400fc5e8  mov     rcx, rsi; int
0x1400fc5eb  call    TxfUpdateTopsMetadataStream
0x1400fc5f0  mov     rcx, rsi
0x1400fc5f3  call    NtfsCheckpointCurrentTransaction
0x1400fc5f8  bts     dword ptr [rsi+4], 0Ah
0x1400fc5fd  xor     edx, edx
0x1400fc5ff  mov     rcx, rsi
0x1400fc602  call    NtfsCleanupIrpContext
0x1400fc607  mov     ebx, edi
0x1400fc609  mov     [rsp+178h+var_E4], ebx
0x1400fc610  mov     r10d, 2
0x1400fc616  jmp     short loc_1400FC658
0x1400fc618  mov     r8d, eax
0x1400fc61b  xor     edx, edx
0x1400fc61d  mov     rsi, [rsp+178h+var_A0]
0x1400fc625  mov     rcx, rsi
0x1400fc628  call    NtfsProcessException
0x1400fc62d  mov     ebx, eax
0x1400fc62f  mov     [rsp+178h+var_E4], eax
0x1400fc636  xor     edi, edi
0x1400fc638  lea     r14d, [rdi+1]
0x1400fc63c  lea     r10d, [rdi+2]
0x1400fc640  mov     r15, [rsp+178h+var_90]
0x1400fc648  mov     rdx, [rsp+178h+var_78]
0x1400fc650  mov     [rsp+178h+var_C8], rdx
0x1400fc658  mov     rax, [rsi+90h]
0x1400fc65f  mov     [rax+18h], edi
  ... truncated ...
```
