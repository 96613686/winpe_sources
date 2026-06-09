# NtfsNonCachedIo

- ea: `0x140175ad0`
- end: `0x140176eaa`
- name: `NtfsNonCachedIo`
- size: `5082`
- prototype: ``
- caller_count: `7`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400177d0`
- `0x140025210`
- `0x14002c840`
- `0x1401bcdc0`
- `0x140223ab0`
- `0x140245bf8`
- `0x14028371c`

## callees

- `0x140005810`
- `0x140005f40`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14001da30`
- `0x14001e2f0`
- `0x14001e9d0`
- `0x140021160`
- `0x140023250`
- `0x140024100`
- `0x1400241c0`
- `0x14002c400`
- `0x14003ad08`
- `0x14003c184`
- `0x1400592c0`
- `0x140059740`
- `0x140139f20`
- `0x140163fc8`
- `0x140175ad0`
- `0x140176eb0`
- `0x140177230`
- `0x1401775c0`
- `0x140177660`
- `0x140177c30`
- `0x1401c06b0`
- `0x14026ba88`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1402a9e35`
- `ntoskrnl!IoFreeIrp` at `0x1402a9e35`
- `ntoskrnl!IoSetActivityIdThread` at `0x140176905`
- `ntoskrnl!IoSetActivityIdThread` at `0x140176905`
- `ntoskrnl!IoClearActivityIdThread` at `0x140176927`
- `ntoskrnl!IoClearActivityIdThread` at `0x140176927`
- `ntoskrnl!IoFreeMdl` at `0x1402a9e1e`
- `ntoskrnl!IoFreeMdl` at `0x1402a9e1e`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140175fbf`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140176626`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140175fbf`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140176626`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140175e8a`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140175e8a`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x140176263`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x140176263`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140175f89`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1401765f6`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140175f89`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1401765f6`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140176310`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140176310`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14017632e`
- `ntoskrnl!IoSetDeviceToVerify` at `0x14017632e`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x1401761dd`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x1401761dd`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140176cc6`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140176cc6`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401768e5`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401768e5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140176887`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140176887`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140176ca3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140176ca3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140176b8d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x140176b8d`

## pseudocode

```c
__int64 __fastcall NtfsNonCachedIo(__int64 a1, PIRP Irp, __int64 a3, __int64 a4, unsigned int a5, int a6)
{
  int v6; // ebx
  unsigned int v10; // ecx
  __int64 v11; // rdi
  __int64 v12; // rax
  char v13; // r12
  unsigned int *v14; // rbx
  bool v15; // al
  bool v16; // al
  bool v17; // al
  char v18; // al
  bool v19; // al
  __int64 v20; // rdi
  NTSTATUS v21; // eax
  __int64 v22; // r9
  __int64 v23; // r10
  _QWORD *v24; // r8
  __int64 v25; // rax
  _QWORD *v26; // r8
  unsigned int v27; // edi
  __int64 v28; // rcx
  __int64 v29; // rdx
  struct _ERESOURCE *v30; // rcx
  NTSTATUS Status; // eax
  NTSTATUS v32; // eax
  __int64 v33; // rdx
  NTSTATUS v34; // eax
  __int64 v35; // rcx
  unsigned int v36; // ecx
  __int64 AssociatedIrp; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  _QWORD *v41; // rax
  _QWORD *v42; // rdi
  __int64 v43; // r8
  _QWORD *v44; // rdx
  _QWORD *ActivityIdThread; // rax
  char *v46; // rcx
  __int64 v47; // rdi
  __int64 v48; // r8
  __int64 v50; // r8
  const CLFS_LSN *v51; // rcx
  __int16 v52; // cx
  __int64 v53; // rax
  __int64 v54; // rax
  char v55; // dl
  int v56; // [rsp+68h] [rbp-1A8h]
  int v57; // [rsp+70h] [rbp-1A0h]
  bool v58; // [rsp+89h] [rbp-187h]
  char v59; // [rsp+92h] [rbp-17Eh]
  unsigned int v60; // [rsp+94h] [rbp-17Ch]
  __int64 v61; // [rsp+98h] [rbp-178h]
  _QWORD *v62; // [rsp+A8h] [rbp-168h]
  unsigned int v64; // [rsp+B0h] [rbp-160h]
  char v65; // [rsp+B8h] [rbp-158h]
  __int64 v66; // [rsp+C0h] [rbp-150h]
  PVOID v67; // [rsp+C0h] [rbp-150h]
  __int64 v68; // [rsp+D0h] [rbp-140h]
  NTSTATUS v69; // [rsp+E0h] [rbp-130h]
  struct _MDL *MemoryDescriptorList; // [rsp+100h] [rbp-110h]
  __int64 v71; // [rsp+110h] [rbp-100h]
  __int128 v72; // [rsp+130h] [rbp-E0h] BYREF
  __int64 v73; // [rsp+140h] [rbp-D0h]
  _BYTE v74[128]; // [rsp+148h] [rbp-C8h] BYREF

  v6 = a4;
  v10 = a5;
  v11 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 96LL);
  v62 = (_QWORD *)v11;
  v65 = 0;
  v12 = *(_QWORD *)(a1 + 192);
  v58 = v12 && (*(_QWORD *)(v12 + 32) != -1 || *(_QWORD *)(v12 + 72) != -1);
  v13 = *(_BYTE *)(a1 + 12) & 1;
  if ( NtfsDiskAccountingEnabled )
  {
    NtfsUpdateReadWriteDiskCounters(a1, (__int64)Irp, a5);
    v10 = a5;
  }
  if ( *(_BYTE *)(a1 + 32) == 4 )
  {
    v50 = *(_QWORD *)(a3 + 192);
    if ( a3 == *(_QWORD *)(v50 + 72)
      && (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
    {
      McTemplateU0ppd_EtwWriteTransfer(v10, (unsigned int)deviosup_c10106, v50, v6, v10);
    }
    if ( (*(_DWORD *)(a3 + 512) & 0x20) != 0 )
    {
      if ( (dword_1400956B8 & 0x200000) != 0 )
      {
        v65 = 12;
      }
      else
      {
        v65 = 8;
        if ( a3 == *(_QWORD *)(v11 + 64) && (*(_DWORD *)(v11 + 4) & 0x1000) != 0 )
        {
          v53 = *(_QWORD *)(v11 + 232);
          if ( v53 )
          {
            if ( *(_WORD *)v53 == 2049 )
            {
              v54 = *(_QWORD *)(v53 + 24);
              if ( v54 )
              {
                if ( *(_WORD *)v54 == 2051 )
                {
                  v55 = 8;
                  if ( (*(_DWORD *)(v54 + 428) & 0x1000) != 0 )
                    v55 = 12;
                  v65 = v55;
                }
              }
            }
          }
        }
      }
    }
    v51 = *(const CLFS_LSN **)(*(_QWORD *)(a3 + 184) + 328LL);
    if ( v51 && ((v51->offset.cidContainer & 1) != 0 || !ClfsLsnInvalid(v51 + 15)) )
      *(_DWORD *)(a1 + 12) |= 0x1000000u;
  }
  if ( (a6 & 6) == 0
    && *(_DWORD *)(a3 + 256) == 128
    && _bittest16((const signed __int16 *)(a3 + 460), 0xEu)
    && !*(_QWORD *)(a3 + 504)
    && *(_QWORD *)(a3 + 632) != -1 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221227536LL, 796629);
    NtfsRaiseStatusInternal(a1, -1073739760, 0, 0, 796629);
    __debugbreak();
  }
  MemoryDescriptorList = 0;
  v61 = 0;
  v69 = -1073741823;
  v59 = 0;
  v14 = (unsigned int *)NtfsAllocateFromPerProcessorLookasideList(NtfsCompressCtxLookasideList);
  if ( !v13 )
    *(_QWORD *)(*(_QWORD *)(a1 + 208) + 64LL) = v14;
  memset(v14, 0, 0xB8u);
  memset(v74, 0, sizeof(v74));
  *((_QWORD *)v14 + 10) = v74;
  v14[22] = 8;
  v15 = (*(_DWORD *)(a3 + 448) || (*(_WORD *)(a3 + 460) & 0x80FF) != 0)
     && *(_QWORD *)(a3 + 16)
     && !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(a3 + 184) + 112LL))
     && !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a3 + 184) + 104LL) + 64LL));
  *((_BYTE *)v14 + 104) = v15;
  v16 = *(_BYTE *)(a1 + 32) == 4
     && v13
     && (v52 = *(_WORD *)(a3 + 460), (v52 & 0x80FF) != 0)
     && ((dword_1400956B8 & 0x100) == 0 || !(_BYTE)v52)
     && *(_QWORD *)(a3 + 16)
     && !v58
     && (*(_DWORD *)(a1 + 16) & 0x40000) == 0;
  *((_BYTE *)v14 + 105) = v16;
  v17 = *(_BYTE *)(a1 + 32) == 4
     && *(_BYTE *)(a3 + 460)
     && (*(_DWORD *)(a3 + 200) & 0x80000) != 0
     && ((dword_1400956B8 & 0x200) != 0 || NtfsGetAttributeListSize(a1, *(_QWORD *)(a3 + 184)) <= qword_140095A98);
  *((_BYTE *)v14 + 106) = v17;
  v18 = *(_BYTE *)(a1 + 32);
  v19 = v18 == 4 && *(_DWORD *)(a3 + 452)
     || v18 == 3
     && (*(_BYTE *)(a3 + 460) && *(_DWORD *)(a3 + 452)
      || *(_QWORD *)(a3 + 504) && *(_DWORD *)(a3 + 256) == 128 && (a6 & 6) == 0 && *(int *)(a3 + 200) >= 0);
  *((_BYTE *)v14 + 108) = v19;
  Irp->AssociatedIrp.IrpCount = 0;
  if ( (a6 & 4) == 0
    && *(_BYTE *)(a1 + 32) == 4
    && *(_DWORD *)(a3 + 452)
    && *(_BYTE *)(a3 + 460)
    && (*(_DWORD *)(a3 + 512) & 0x4000) == 0
    && (Irp == *(PIRP *)(a1 + 112) || *(_QWORD *)(*(_QWORD *)(a3 + 288) + 24LL)) )
  {
    if ( !*(_QWORD *)(a3 + 280) )
    {
      NtfsCreateInternalAttributeStream(a1, a3, 0, 0, (__int64)&qword_1400620E0, 0);
      if ( !*(_DWORD *)(a3 + 208) && !*(_DWORD *)(*(_QWORD *)(a3 + 184) + 268LL) )
      {
        v72 = 0;
        v73 = 0;
        v41 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList);
        v42 = v41;
        v67 = v41;
        if ( v41 )
        {
          memset(v41, 0, 0x58u);
          v42[1] = v42;
          *v42 = v42;
          v42[3] = v42 + 2;
          v42[2] = v42 + 2;
          v42[4] = a3;
          *((_BYTE *)v42 + 56) = 5;
          LOBYTE(v43) = 1;
          NtfsIncrementCloseCounts(v42 + 2, a3, v43, 0);
          v44 = *(_QWORD **)(a1 + 120);
          if ( v44 )
          {
            *((_QWORD *)&v72 + 1) = *v44;
            v73 = v44[1];
            v46 = (char *)&v72 + 8;
          }
          else
          {
            ActivityIdThread = (_QWORD *)IoGetActivityIdThread();
            if ( ActivityIdThread )
            {
              *((_QWORD *)&v72 + 1) = *ActivityIdThread;
              v73 = ActivityIdThread[1];
              v46 = (char *)&v72 + 8;
            }
            else
            {
              v46 = 0;
            }
          }
          v47 = IoSetActivityIdThread(v46);
          LOBYTE(v48) = 1;
          NtfsQueueClose(a1, v67, v48);
          IoClearActivityIdThread(v47);
        }
      }
    }
    v20 = a4;
    MemoryDescriptorList = (struct _MDL *)NtfsLockFileRange(a1, a3, a4, a5, v56, v57);
  }
  else
  {
    v20 = a4;
  }
  if ( *(_BYTE *)(a1 + 32) == 3 && (*(_BYTE *)(a1 + 16) & 0x40) != 0 )
    v21 = 1073741877;
  else
    v21 = 0;
  v60 = v21;
  Irp->IoStatus.Status = v21;
  *(_QWORD *)v14 = v20;
  v14[2] = a5;
  *((_QWORD *)v14 + 2) = v20;
  *((_QWORD *)v14 + 3) = v20 + a5;
  while ( 1 )
  {
    v22 = *((_QWORD *)v14 + 2);
    if ( *((_QWORD *)v14 + 3) <= v22 )
      break;
    v64 = NtfsPrepareBuffers(a1, Irp, a3);
    v22 = v64 + *((_QWORD *)v14 + 2);
    v66 = v22;
    v23 = *((_QWORD *)v14 + 3);
    v68 = v23;
    if ( (Irp->Flags & 2) != 0 )
    {
      v24 = (_QWORD *)(v62[101] + 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors));
      if ( *(_DWORD *)(a3 + 256) != 128 || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 4LL) & 0x100) != 0 )
      {
        if ( a3 != v62[8] )
        {
          if ( *(_BYTE *)(a1 + 32) == 4 )
            v24[12] = v24[12];
          else
            v24[9] = v24[9];
        }
      }
      else if ( *(_BYTE *)(a1 + 32) == 4 )
      {
        v24[6] = v24[6];
      }
      else
      {
        v24[3] = v24[3];
      }
    }
    if ( v13 )
      goto LABEL_36;
    if ( v22 < v23 )
    {
      v25 = v61;
      if ( !v61 )
      {
        AssociatedIrp = IoMakeAssociatedIrpEx(
                          Irp,
                          Irp->Tail.Overlay.CurrentStackLocation->DeviceObject,
                          (unsigned __int8)(*(_BYTE *)(v62[28] + 76LL) + 1));
        v38 = AssociatedIrp;
        v61 = AssociatedIrp;
        if ( !AssociatedIrp )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 796917);
          NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 796917);
          if ( *(_BYTE *)(a1 + 32) != 4 || Irp == *(PIRP *)(a1 + 112) )
            NtfsFixDataError(a1, v64, v65, a6);
LABEL_58:
          if ( !v13 )
            goto LABEL_85;
          goto LABEL_59;
        }
        v39 = *(_QWORD *)(*(_QWORD *)(a1 + 208) + 88LL);
        v40 = *(_QWORD *)(AssociatedIrp + 184);
        *(_QWORD *)(v40 - 16) = NtfsAssociatedIrpCompletionRoutine;
        *(_QWORD *)(v40 - 8) = v39;
        *(_BYTE *)(v40 - 69) = 0;
        *(_BYTE *)(v40 - 69) = 64;
        *(_BYTE *)(v40 - 69) = -64;
        *(_BYTE *)(v40 - 69) = -32;
        --*(_BYTE *)(v38 + 67);
        *(_QWORD *)(v38 + 184) -= 72LL;
        NtfsPreProcessIo(a1, Irp, 1);
        v22 = v66;
        v23 = v68;
LABEL_36:
        v25 = v61;
      }
LABEL_37:
      v26 = v62;
      goto LABEL_39;
    }
    v25 = v61;
    if ( !v61 )
      goto LABEL_37;
    v28 = *(_QWORD *)(a1 + 208);
    if ( (*(_BYTE *)(v28 + 48) & 3) != 0 || (*(_DWORD *)v28 & 0x10000) != 0 )
      goto LABEL_36;
    IoGetIoPriorityHint(Irp);
    v29 = *(_QWORD *)(a1 + 208);
    v71 = v29;
    *(_QWORD *)(v29 + 48) |= 3uLL;
    v30 = *(struct _ERESOURCE **)(v29 + 40);
    if ( v30 )
    {
      ExSetResourceOwnerPointerEx(v30, *(PVOID *)(v29 + 48), 1u);
      v29 = v71;
    }
    v26 = v62;
    v22 = v66;
    v23 = v68;
    if ( (struct _KTHREAD *)qword_1400958C0 == KeGetCurrentThread() )
    {
      qword_1400958C0 = *(_QWORD *)(v29 + 48);
    }
    else if ( *(struct _KTHREAD **)(v62[689] + 8LL) == KeGetCurrentThread() )
    {
      *(_QWORD *)(v62[689] + 8LL) = *(_QWORD *)(v29 + 48);
      v25 = v61;
      goto LABEL_39;
    }
    v25 = v61;
LABEL_39:
    if ( v22 < v23 )
      goto LABEL_58;
    if ( v25 )
    {
      v27 = 259;
      goto LABEL_120;
    }
    v13 = 1;
LABEL_59:
    if ( Irp->IoStatus.Status < 0 )
      break;
    if ( *((_BYTE *)v14 + 108) )
    {
      v34 = NtfsFinishBuffers(a1, v64, 0, (__int64)v14);
      if ( v34 < 0 )
        Irp->IoStatus.Status = v34;
    }
    Status = Irp->IoStatus.Status;
    if ( Status < 0 || v66 >= v68 )
      break;
    if ( v59 )
    {
      Irp->IoStatus.Status = v69;
      IoSetMasterIrpStatus(Irp, (unsigned int)Status, v26);
    }
    else
    {
      v59 = 1;
      v69 = Irp->IoStatus.Status;
    }
LABEL_85:
    v35 = *((_QWORD *)v14 + 2) + v64;
    *((_QWORD *)v14 + 2) = v35;
    if ( v35 > *(_QWORD *)v14 )
    {
      v36 = v35 - *(_QWORD *)v14;
      if ( v36 >= v14[2] )
        v36 = v14[2];
      v14[16] = v36;
    }
  }
  v32 = Irp->IoStatus.Status;
  if ( ((unsigned int)v32 <= 0x40000009 || v32 >= 1073741836)
    && (*(_DWORD *)(a3 + 512) & 8) != 0
    && *(_BYTE *)(a1 + 32) == 3
    && !(unsigned __int8)NtfsVerifyAndRevertUsaBlock(a1, a3, (_DWORD)Irp, 0, 0, a5, *((_QWORD *)v14 + 2)) )
  {
    NtfsFixDataError(a1, a5, v65, a6);
  }
  v33 = (unsigned int)Irp->IoStatus.Status;
  if ( NtfsStatusDebugFlags
    && (_DWORD)v33
    && (_DWORD)v33 != 294
    && (unsigned int)(v33 - 298) > 1
    && (unsigned int)v33 < 0xFFFFFFED
    && (_DWORD)v33 != -1073741608
    && (_DWORD)v33 != -1073741802
    && (_DWORD)v33 != -1073741807
    && (unsigned int)(v33 + 2147483643) > 1
    && (_DWORD)v33 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(0, v33, 797399);
  }
  v27 = Irp->IoStatus.Status;
LABEL_120:
  if ( v61 )
  {
    if ( NtfsStatusDebugFlags && v60 && v60 - 298 > 1 && v60 + 2147483643 > 1 )
      NtfsStatusTraceAndDebugInternal(0, v60, 797470);
    LOBYTE(v22) = 1;
    NtfsExtendedCompleteRequestInternal(0, v61, v60, v22, (v60 & 0x80000000) == 0);
    if ( a1 && *(_QWORD *)(a1 + 112) == v61 )
      *(_QWORD *)(a1 + 112) = 0;
  }
  if ( MemoryDescriptorList )
    NtfsFreeMdl(MemoryDescriptorList);
  if ( !v58 )
    NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
  if ( v27 != 259 )
  {
    NtfsDeallocateCompressionBuffer(a1, Irp, v14, 0);
    NtfsFreeToPerProcessorLookasideList(NtfsCompressCtxLookasideList, v14);
  }
  if ( v13 && (v27 & 0x80000000) == 0 )
    Irp->IoStatus.Information = a5;
  if ( NtfsStatusDebugFlags
    && v27
    && v27 != 294
    && v27 - 298 > 1
    && v27 < 0xFFFFFFED
    && v27 != -1073741608
    && v27 != -1073741802
    && v27 != -1073741807
    && v27 + 2147483643 > 1
    && v27 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(0, v27, 797603);
  }
  return v27;
}

```

## disassembly

```asm
0x140175ad0  push    rbx
0x140175ad2  push    rsi
0x140175ad3  push    rdi
0x140175ad4  push    r12
0x140175ad6  push    r13
0x140175ad8  push    r14
0x140175ada  push    r15
0x140175adc  sub     rsp, 190h
0x140175ae3  mov     rax, cs:__security_cookie
0x140175aea  xor     rax, rsp
0x140175aed  mov     [rsp+1C8h+var_48], rax
0x140175af5  mov     rbx, r9
0x140175af8  mov     [rsp+1C8h+var_160], rbx
0x140175afd  mov     r14, r8
0x140175b00  mov     r15, rdx
0x140175b03  mov     rsi, rcx
0x140175b06  mov     [rsp+1C8h+var_128], rcx
0x140175b0e  mov     [rsp+1C8h+Irp], rdx
0x140175b16  mov     [rsp+1C8h+var_F0], r8
0x140175b1e  mov     ecx, [rsp+1C8h+arg_20]
0x140175b25  mov     [rsp+1C8h+var_170], ecx
0x140175b29  xor     r13d, r13d
0x140175b2c  mov     [rsp+1C8h+var_184], r13d
0x140175b31  mov     rax, [r8+0B8h]
0x140175b38  mov     rdi, [rax+60h]
0x140175b3c  mov     [rsp+1C8h+var_168], rdi
0x140175b41  mov     [rsp+1C8h+var_E8], rdi
0x140175b49  mov     byte ptr [rsp+1C8h+var_158], r13b
0x140175b4e  mov     rax, [rsi+0C0h]
0x140175b55  test    rax, rax
0x140175b58  jnz     loc_140176E85
0x140175b5e  mov     [rsp+1C8h+var_187], r13b
0x140175b63  movzx   r12d, byte ptr [rsi+0Ch]
0x140175b68  and     r12b, 1
0x140175b6c  mov     [rsp+1C8h+var_180], r12b
0x140175b71  cmp     cs:NtfsDiskAccountingEnabled, r13b
0x140175b78  jz      short loc_140175B89
0x140175b7a  mov     r8d, ecx
0x140175b7d  mov     rcx, rsi
0x140175b80  call    NtfsUpdateReadWriteDiskCounters
0x140175b85  mov     ecx, [rsp+1C8h+var_170]
0x140175b89  cmp     byte ptr [rsi+20h], 4
0x140175b8d  jz      loc_140176B4B
0x140175b93  mov     edi, [rsp+1C8h+arg_28]
0x140175b9a  and     edi, 6
0x140175b9d  jnz     short loc_140175BBC
0x140175b9f  cmp     dword ptr [r14+100h], 80h
0x140175baa  jnz     short loc_140175BBC
0x140175bac  bt      word ptr [r14+1CCh], 0Eh
0x140175bb6  jb      loc_140176D72
0x140175bbc  mov     [rsp+1C8h+var_154], r13d
0x140175bc1  mov     [rsp+1C8h+MemoryDescriptorList], r13
0x140175bc9  mov     [rsp+1C8h+var_178], r13
0x140175bce  mov     [rsp+1C8h+var_188], r13b
0x140175bd3  mov     [rsp+1C8h+var_17F], r13b
0x140175bd8  mov     eax, 0C0000001h
0x140175bdd  mov     [rsp+1C8h+var_130], eax
0x140175be4  mov     [rsp+1C8h+var_17C], eax
0x140175be8  mov     [rsp+1C8h+var_17E], r13b
0x140175bed  mov     eax, [rsp+1C8h+var_170]
0x140175bf1  mov     [rsp+1C8h+var_118], eax
0x140175bf8  mov     rcx, cs:NtfsCompressCtxLookasideList
0x140175bff  call    NtfsAllocateFromPerProcessorLookasideList
0x140175c04  mov     rbx, rax
0x140175c07  mov     [rsp+1C8h+var_120], rax
0x140175c0f  test    r12b, r12b
0x140175c12  jnz     short loc_140175C1F
0x140175c14  mov     rax, [rsi+0D0h]
0x140175c1b  mov     [rax+40h], rbx
0x140175c1f  xor     edx, edx; Val
0x140175c21  mov     r8d, 0B8h; Size
0x140175c27  mov     rcx, rbx; void *
0x140175c2a  call    memset
0x140175c2f  xor     edx, edx; Val
0x140175c31  mov     r8d, 80h; Size
0x140175c37  lea     rcx, [rsp+1C8h+var_C8]; void *
0x140175c3f  call    memset
0x140175c44  lea     rax, [rsp+1C8h+var_C8]
0x140175c4c  mov     [rbx+50h], rax
0x140175c50  mov     dword ptr [rbx+58h], 8
0x140175c57  cmp     [r14+1C0h], r13d
0x140175c5e  jnz     loc_140176C8E
0x140175c64  mov     ecx, 80FFh
0x140175c69  test    [r14+1CCh], cx
0x140175c71  jnz     loc_140176C8E
0x140175c77  xor     al, al
0x140175c79  mov     [rbx+68h], al
0x140175c7c  cmp     byte ptr [rsi+20h], 4
0x140175c80  jz      loc_140176BAD
0x140175c86  xor     al, al
0x140175c88  mov     [rbx+69h], al
0x140175c8b  cmp     byte ptr [rsi+20h], 4
0x140175c8f  jz      loc_140176AFE
0x140175c95  xor     al, al
0x140175c97  mov     [rbx+6Ah], al
0x140175c9a  movzx   eax, byte ptr [rsi+20h]
0x140175c9e  cmp     al, 4
0x140175ca0  jz      loc_140176AEA
0x140175ca6  cmp     al, 3
0x140175ca8  jnz     short loc_140175CC4
0x140175caa  cmp     [r14+1CCh], r13b
0x140175cb1  jnz     loc_140176D14
0x140175cb7  cmp     [r14+1F8h], r13
0x140175cbe  jnz     loc_140176D47
0x140175cc4  xor     al, al
0x140175cc6  mov     [rbx+6Ch], al
0x140175cc9  mov     [r15+18h], r13d
0x140175ccd  mov     r8d, [rsp+1C8h+arg_28]
0x140175cd5  test    r8b, 4
0x140175cd9  jnz     short loc_140175CE5
0x140175cdb  cmp     byte ptr [rsi+20h], 4
0x140175cdf  jz      loc_1401767C1
0x140175ce5  mov     rdi, [rsp+1C8h+var_160]
0x140175cea  cmp     byte ptr [rsi+20h], 3
0x140175cee  jz      loc_1401766A6
0x140175cf4  mov     eax, r13d
0x140175cf7  mov     [rsp+1C8h+var_17C], eax
0x140175cfb  mov     [r15+30h], eax
0x140175cff  mov     [rbx], rdi
0x140175d02  mov     eax, [rsp+1C8h+var_170]
0x140175d06  mov     [rbx+8], eax
0x140175d09  mov     [rbx+10h], rdi
0x140175d0d  add     rax, rdi
0x140175d10  mov     [rbx+18h], rax
0x140175d14  mov     edi, [rsp+1C8h+var_17C]
0x140175d18  mov     r10, 100000000h
0x140175d22  mov     r9, [rbx+10h]
0x140175d26  mov     rdx, [rbx+18h]
0x140175d2a  cmp     rdx, r9
0x140175d2d  jle     loc_1401760A0
0x140175d33  mov     rax, [rsp+1C8h+var_168]
0x140175d38  mov     eax, [rax+12C8h]
0x140175d3e  lea     ecx, [rax+rax]
0x140175d41  mov     rax, r10
0x140175d44  sub     rax, rcx
0x140175d47  sub     rdx, r9
0x140175d4a  cmp     rdx, rax
0x140175d4d  cmovg   rdx, rax
0x140175d51  mov     [rsp+1C8h+var_17F], 0
0x140175d56  mov     [rsp+1C8h+var_190], rbx
0x140175d5b  lea     rax, [rsp+1C8h+var_184]
0x140175d60  mov     [rsp+1C8h+var_198], rax
0x140175d65  mov     dword ptr [rsp+1C8h+var_1A0], r8d
0x140175d6a  mov     dword ptr [rsp+1C8h+var_1A8], edx
0x140175d6e  mov     r8, r14
0x140175d71  mov     rdx, r15
0x140175d74  mov     rcx, rsi
0x140175d77  call    NtfsPrepareBuffers
0x140175d7c  mov     dword ptr [rsp+1C8h+var_160], eax
0x140175d80  mov     [rsp+1C8h+var_188], 1
0x140175d85  mov     eax, eax
0x140175d87  mov     [rsp+1C8h+var_F8], rax
0x140175d8f  mov     r9, [rbx+10h]
0x140175d93  add     r9, rax
0x140175d96  mov     [rsp+1C8h+var_150], r9
0x140175d9b  mov     r10, [rbx+18h]
0x140175d9f  mov     [rsp+1C8h+var_140], r10
0x140175da7  mov     ecx, [r15+10h]
0x140175dab  mov     r11, [rsp+1C8h+var_168]
0x140175db0  test    cl, 2
0x140175db3  jz      short loc_140175E0C
0x140175db5  mov     eax, gs:1A4h
0x140175dbd  xor     edx, edx
0x140175dbf  div     cs:NtfsNumberProcessors
0x140175dc5  mov     ecx, edx
0x140175dc7  imul    r8, rcx, 2C0h
0x140175dce  add     r8, [r11+328h]
0x140175dd5  cmp     dword ptr [r14+100h], 80h
0x140175de0  jnz     loc_140175F34
0x140175de6  mov     rax, [r14+0B8h]
0x140175ded  test    dword ptr [rax+4], 100h
0x140175df4  jnz     loc_140175F34
0x140175dfa  mov     eax, [rsp+1C8h+var_184]
0x140175dfe  cmp     byte ptr [rsi+20h], 4
0x140175e02  jz      loc_14017602C
0x140175e08  add     [r8+18h], rax
0x140175e0c  test    r12b, r12b
0x140175e0f  jz      loc_140175F55
0x140175e15  mov     rax, [rsp+1C8h+var_178]
0x140175e1a  mov     r8, [rsp+1C8h+var_168]
0x140175e1f  cmp     [rsp+1C8h+var_184], 0
0x140175e24  jz      loc_140175F19
0x140175e2a  mov     rax, [rsi+0D0h]
0x140175e31  test    rax, rax
0x140175e34  jz      short loc_140175E42
0x140175e36  test    dword ptr [rax], 1000h
0x140175e3c  jnz     loc_1401762ED
0x140175e42  mov     rdx, [r8+0E0h]
0x140175e49  mov     rax, [rbx+50h]
0x140175e4d  mov     [rsp+1C8h+var_1A0], rax
0x140175e52  mov     eax, [rsp+1C8h+var_184]
0x140175e56  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x140175e5a  mov     r9, r15
0x140175e5d  mov     r8, r14
0x140175e60  mov     rcx, rsi
0x140175e63  call    NtfsMultipleAsync
0x140175e68  mov     [rsp+1C8h+var_17F], 1
0x140175e6d  cmp     cs:NtfsDiskAccountingEnabled, 0
0x140175e74  jz      short loc_140175E96
0x140175e76  mov     edx, r13d
0x140175e79  cmp     byte ptr [rsi+20h], 4
0x140175e7d  cmovz   edx, dword ptr [rsp+1C8h+var_160]
0x140175e82  mov     ecx, dword ptr [rsp+1C8h+var_160]
0x140175e86  cmovz   ecx, r13d
0x140175e8a  call    cs:__imp_FsRtlUpdateDiskCounters
0x140175e91  nop     dword ptr [rax+rax+00h]
0x140175e96  test    r12b, r12b
0x140175e99  jz      short loc_140175EF5
0x140175e9b  mov     r8, r14
0x140175e9e  mov     rdx, r15
0x140175ea1  mov     rcx, rsi
0x140175ea4  call    NtfsWaitOnIo
0x140175ea9  mov     rax, [rsi+0D0h]
0x140175eb0  mov     ecx, [rax]
0x140175eb2  and     ecx, 0C000h
0x140175eb8  cmp     ecx, 0C000h
0x140175ebe  jz      loc_1401763BE
0x140175ec4  mov     ecx, [r15+30h]
0x140175ec8  lea     eax, [rcx+3FFFFF5Eh]
0x140175ece  cmp     eax, 1
0x140175ed1  ja      loc_1401764BE
0x140175ed7  mov     rcx, [r15+98h]; Thread
0x140175ede  test    rcx, rcx
0x140175ee1  jnz     loc_140176310
0x140175ee7  mov     rcx, gs:188h
0x140175ef0  jmp     loc_14017632C
0x140175ef5  mov     rax, [rsp+1C8h+var_140]
0x140175efd  cmp     [rsp+1C8h+var_150], rax
0x140175f02  jl      loc_14017606B
0x140175f08  movzx   eax, cs:NtfsStatusDebugFlags
0x140175f0f  mov     edi, 103h
0x140175f14  jmp     loc_1401764EA
0x140175f19  cmp     r9, r10
0x140175f1c  jl      loc_14017606B
0x140175f22  test    rax, rax
0x140175f25  jnz     short loc_140175F08
0x140175f27  mov     r12b, 1
0x140175f2a  mov     [rsp+1C8h+var_180], r12b
0x140175f2f  jmp     loc_140176074
0x140175f34  cmp     r14, [r11+40h]
0x140175f38  jz      loc_140175E0C
0x140175f3e  mov     eax, [rsp+1C8h+var_184]
0x140175f42  cmp     byte ptr [rsi+20h], 4
0x140175f46  jnz     loc_140176035
0x140175f4c  add     [r8+60h], rax
0x140175f50  jmp     loc_140175E0C
0x140175f55  cmp     r9, r10
0x140175f58  jl      loc_140176238
0x140175f5e  cmp     [rsp+1C8h+var_184], 0
0x140175f63  jz      loc_1401762FD
0x140175f69  mov     rcx, [rsi+0D0h]
0x140175f70  test    byte ptr [rcx+30h], 3
0x140175f74  jnz     loc_140175E15
0x140175f7a  test    dword ptr [rcx], 10000h
0x140175f80  jnz     loc_140175E15
0x140175f86  mov     rcx, r15; Irp
0x140175f89  call    cs:__imp_IoGetIoPriorityHint
0x140175f90  nop     dword ptr [rax+rax+00h]
0x140175f95  mov     rdx, [rsi+0D0h]
0x140175f9c  mov     [rsp+1C8h+var_100], rdx
0x140175fa4  or      qword ptr [rdx+30h], 3
0x140175fa9  mov     rax, [rdx+30h]
0x140175fad  mov     rcx, [rdx+28h]; Resource
0x140175fb1  test    rcx, rcx
0x140175fb4  jz      short loc_140175FD3
0x140175fb6  mov     r8d, 1; Flags
0x140175fbc  mov     rdx, rax; OwnerPointer
0x140175fbf  call    cs:__imp_ExSetResourceOwnerPointerEx
0x140175fc6  nop     dword ptr [rax+rax+00h]
0x140175fcb  mov     rdx, [rsp+1C8h+var_100]
0x140175fd3  mov     rcx, cs:qword_1400958C0
0x140175fda  mov     rax, gs:188h
0x140175fe3  mov     r8, [rsp+1C8h+var_168]
0x140175fe8  mov     r9, [rsp+1C8h+var_150]
0x140175fed  mov     r10, [rsp+1C8h+var_140]
0x140175ff5  cmp     rcx, rax
0x140175ff8  jz      short loc_14017603E
0x140175ffa  mov     rax, [r8+1588h]
0x140176001  mov     rcx, [rax+8]
0x140176005  mov     rax, gs:188h
0x14017600e  cmp     rcx, rax
0x140176011  jnz     short loc_140176049
0x140176013  mov     rcx, [r8+1588h]
0x14017601a  mov     rax, [rdx+30h]
0x14017601e  mov     [rcx+8], rax
0x140176022  mov     rax, [rsp+1C8h+var_178]
0x140176027  jmp     loc_140175E1F
0x14017602c  add     [r8+30h], rax
0x140176030  jmp     loc_140175E0C
0x140176035  add     [r8+48h], rax
0x140176039  jmp     loc_140175E0C
0x14017603e  mov     rax, [rdx+30h]
0x140176042  mov     cs:qword_1400958C0, rax
0x140176049  mov     rax, [rsp+1C8h+var_178]
0x14017604e  jmp     loc_140175E1F
0x140176053  cmp     ecx, 0FFFFFFFFh
0x140176056  jle     loc_1401762AB
0x14017605c  lea     eax, [rcx-4000000Ah]
0x140176062  cmp     eax, 1
0x140176065  jbe     loc_1401762AB
  ... truncated ...
```
