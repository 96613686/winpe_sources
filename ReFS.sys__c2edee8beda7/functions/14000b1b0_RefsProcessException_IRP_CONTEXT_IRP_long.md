# RefsProcessException(_IRP_CONTEXT *,_IRP *,long)

- ea: `0x14000b1b0`
- end: `0x14000c17a`
- name: `?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z`
- size: `4042`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct _IRP *, int)`
- caller_count: `24`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d0c0`
- `0x140099db0`
- `0x1400b9530`
- `0x1400bc5b0`
- `0x1400bd090`
- `0x1400e64e0`
- `0x1400f6460`
- `0x1400f88e0`
- `0x1400f966c`
- `0x140298510`
- `0x1402cead0`
- `0x1402d2a20`
- `0x1402e7210`
- `0x1403053a0`
- `0x14030cd80`
- `0x14030d160`
- `0x140316100`
- `0x140318cb0`
- `0x1403235e0`
- `0x140323940`
- `0x14032b430`
- `0x14032d490`
- `0x14033b510`
- `0x14033db20`

## callees

- `0x140008640`
- `0x140009e40`
- `0x140009ecc`
- `0x14000b1b0`
- `0x14000c180`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140063b10`
- `0x1400801d0`
- `0x1400862c0`
- `0x1400ab7ac`
- `0x1400adddc`
- `0x1400d0fd8`
- `0x1400ebe74`
- `0x1400fe778`
- `0x1400fe808`
- `0x140100550`
- `0x14011afec`
- `0x14028e0ec`
- `0x140302dc0`
- `0x140315bb4`
- `0x140332ce0`
- `0x14033a424`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000ba97`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bad8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bb3b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bb4e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000be18`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bf37`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c03c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000ba97`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bad8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bb3b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bb4e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000be18`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000bf37`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c03c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b77d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14000b77d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000b919`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000b919`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14000ba12`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x14000ba12`
- `ntoskrnl!CcMdlWriteAbort` at `0x14000b24e`
- `ntoskrnl!CcMdlWriteAbort` at `0x14000bde5`
- `ntoskrnl!CcMdlWriteAbort` at `0x14000b24e`
- `ntoskrnl!CcMdlWriteAbort` at `0x14000bde5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000bb9c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000bb9c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000bbaf`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000bbaf`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f4aa6`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401f4aa6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bbea`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bbea`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000bbf6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000bbf6`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b36f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b703`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b36f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14000b703`
- `ntoskrnl!ExReleaseFastResource` at `0x14000b7c1`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f4a84`
- `ntoskrnl!ExReleaseFastResource` at `0x14000b7c1`
- `ntoskrnl!ExReleaseFastResource` at `0x1401f4a84`

## pseudocode

```c
__int64 __fastcall RefsProcessException(struct _IRP_CONTEXT *a1, struct _IRP *a2, __int64 a3)
{
  unsigned int v3; // esi
  struct _IRP *v4; // r14
  struct _IRP_CONTEXT *v5; // rbx
  struct _IRP_CONTEXT *v6; // rdi
  __int64 v7; // r15
  __int64 v8; // rax
  struct _MDL *MdlAddress; // rdx
  __int64 v10; // rcx
  struct _LIST_ENTRY *v11; // rdx
  unsigned int v12; // r8d
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *i; // rax
  struct _FCB *v17; // r13
  unsigned __int8 v18; // al
  char v19; // r13
  int *v20; // r8
  char v21; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  unsigned int v23; // r9d
  char v24; // al
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rax
  struct _MDL *v28; // rdx
  struct _IRP_CONTEXT *v29; // rcx
  struct _SmsTriageContext *v30; // rdi
  NTSTATUS v31; // edi
  char v32; // al
  __int64 v33; // rcx
  struct _IRP_CONTEXT *v34; // rcx
  __int64 v35; // rax
  struct _IRP_CONTEXT *v37[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 v38; // [rsp+C8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = 0;
  v37[0] = 0;
  if ( !a1 )
    goto LABEL_212;
  v7 = *((_QWORD *)a1 + 8);
  v37[1] = (struct _IRP_CONTEXT *)v7;
  if ( (_DWORD)a3 == -1073741432 )
  {
    RefsSqmLogFileFull(*((unsigned int *)a1 + 166), v7);
    if ( v7 )
    {
      v8 = *((int *)v5 + 166);
      if ( (unsigned int)v8 <= 0xE )
        _InterlockedIncrement64((volatile signed __int64 *)(v7 + 8 * v8 + 9984));
    }
  }
  v3 = *((_DWORD *)v5 + 4);
  if ( *((_BYTE *)v5 + 40) == 4 && (*((_BYTE *)v5 + 41) & 6) == 2 )
  {
    if ( v4 )
    {
      MdlAddress = v4->MdlAddress;
      if ( MdlAddress )
      {
        CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, MdlAddress);
        v4->MdlAddress = 0;
      }
    }
  }
  if ( v7 )
  {
    RefsRestoreScbSnapshots(v5, 1u);
    RefsAbortPendingUsnReasons(v5);
    v10 = *((_QWORD *)v5 + 3);
    if ( v10 )
    {
      if ( !*((_QWORD *)v5 + 43) )
        MsTriageGetContext(v10, (char *)v5 + 344);
      if ( *((_BYTE *)v5 + 40) == 4
        && (*(_DWORD *)(v7 + 24) & 1) != 0
        && (*(_DWORD *)(*(_QWORD *)(v7 + 112) + 3396LL) & 0x800000) != 0
        && (*((_DWORD *)v5 + 1) & 0x8000000) == 0 )
      {
        MsSetOkayToResyncSMRBands(*((_QWORD *)v5 + 3));
      }
      RefsAbortTransaction(v5);
    }
    else
    {
      v11 = (struct _LIST_ENTRY *)((char *)v5 + 640);
      if ( v11->Flink != v11 )
      {
        v12 = 4;
        if ( (v3 & 0x80000000) == 0 )
          v12 = 1;
        RefsProcessRollbackListPriv(0, v11, v12);
      }
      if ( (*((_DWORD *)v5 + 2) & 0x20000000) != 0 )
      {
        v13 = (_QWORD *)*((_QWORD *)v5 + 8);
        v13[116] = v13[124];
        v13[121] = v13[125];
        v13[122] = v13[126];
        *((_QWORD *)v5 + 1) &= ~0x20000000uLL;
      }
    }
    RefsRestoreScbSnapshots(v5, 0);
    if ( *(_QWORD *)(v7 + 240) != *(_QWORD *)(v7 + 264) )
    {
      v14 = *(_QWORD *)(v7 + 72);
      if ( v14 )
      {
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(*(_QWORD *)(v14 + 136) + 88LL) + 64LL) )
          *(_QWORD *)(v7 + 240) = *(_QWORD *)(v7 + 264);
      }
    }
  }
  else
  {
    if ( v3 == -1073741400 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 3221227528LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x64Eu);
      v3 = -1073739768;
    }
    v15 = *((_QWORD *)v5 + 3);
    if ( v15 && !*((_QWORD *)v5 + 43) )
      MsTriageGetContext(v15, (char *)v5 + 344);
    if ( *((_QWORD *)v5 + 43) )
      RefsDiscardTriageInfo(v5);
    if ( v3 == -1073741432 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v3 = -1073741697;
      }
      else
      {
        v3 = -1073741697;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 3221225599LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741697, 0, "NtfsData.c", 0x66Bu);
    }
  }
  if ( _bittest64((const signed __int64 *)v5 + 1, 0x25u) )
  {
    for ( i = (_QWORD *)*((_QWORD *)v5 + 14); i != (_QWORD *)((char *)v5 + 112); i = (_QWORD *)*i )
    {
      v17 = (struct _FCB *)(i - 8);
      if ( (*(_DWORD *)(i - 7) & 0x4000000) != 0 )
      {
        *((_QWORD *)v5 + 1) &= ~0x2000000000uLL;
        LOBYTE(a3) = 1;
        ExAcquireFastResourceExclusive(v7 + 624, 0, a3);
        v18 = 1;
        v38 = 1;
        if ( !v17->Header.AllocationSize.LowPart )
        {
          RefsDeleteFcb(v5, v17, &v38);
          v18 = v38;
        }
        if ( v18 )
          ExReleaseFastResource(v7 + 624, 0);
        break;
      }
    }
    *((_QWORD *)v5 + 1) &= ~0x2000000000uLL;
    MsReleaseFastResource(v7 + 1312, *((_QWORD *)v5 + 13) + 160LL);
  }
  v19 = 0;
  v38 = 0;
  v20 = (int *)*((_QWORD *)v5 + 13);
  if ( v5 != (struct _IRP_CONTEXT *)v20 )
  {
    v21 = *((_BYTE *)v5 + 40);
    if ( (v21 != 3
       || !*((_QWORD *)v5 + 84)
       && v4->Tail.Overlay.CurrentStackLocation->FileObject->FsContext != *(PVOID *)(*((_QWORD *)v5 + 8) + 40LL))
      && (v20[4] >= 0 || v3 == -1073741400) )
    {
      if ( v3 == -1073741740 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids,
            3221225688LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741608, 0, "NtfsData.c", 0x754u);
        *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = -1073741608;
        goto LABEL_100;
      }
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_100;
      if ( v4 )
      {
        if ( v21 == 4 )
        {
          CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
          if ( (v3 == -1073741670
             || v3 == -1073741663
             || v3 == -1073741801
             || CurrentStackLocation->Parameters.Read.Length > 0x1000 && !FsRtlIsTotalDeviceFailure(v3))
            && (v4->Flags & 2) != 0
            && CurrentStackLocation->Parameters.Read.Length > 0x1000 )
          {
            goto LABEL_100;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, v3);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
        {
LABEL_93:
          *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = v3;
          goto LABEL_100;
        }
        v23 = 1918;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, v3);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_93;
        v23 = 1924;
      }
      RefsStatusDebug(v3, 0, "NtfsData.c", v23);
      goto LABEL_93;
    }
  }
LABEL_100:
  if ( v3 != -1073741432
    && v3 != -1073741400
    && v3 != -1073741608
    && !(unsigned __int8)CcIsCacheManagerCallbackNeeded(v3) )
  {
    goto LABEL_141;
  }
  v24 = *((_BYTE *)v5 + 40);
  if ( v24 == 2 )
  {
    v19 = 1;
    v38 = 1;
    if ( (*((_DWORD *)v5 + 1) & 0x800) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 259);
      }
      v3 = 259;
    }
    goto LABEL_141;
  }
  if ( v24 == 3
    && (v5 != *((struct _IRP_CONTEXT **)v5 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type) || (v4->Flags & 2) != 0) )
  {
    if ( v3 == -1073741400 && v5 != *((struct _IRP_CONTEXT **)v5 + 13) )
      goto LABEL_141;
LABEL_117:
    v19 = 1;
    v38 = 1;
    goto LABEL_141;
  }
  if ( v5 == *((struct _IRP_CONTEXT **)v5 + 13) && LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    if ( (*((_DWORD *)v5 + 1) & 0x800) != 0 && !*((_QWORD *)v5 + 43) )
    {
      v6 = v5;
      v37[0] = v5;
      goto LABEL_141;
    }
    goto LABEL_117;
  }
  if ( v3 == -1073741432 )
  {
    ++*(_DWORD *)(v7 + 3496);
    if ( *((struct _IRP_CONTEXT **)v5 + 13) == v5 && (*(_DWORD *)(v7 + 560) & 1) == 0 )
    {
      if ( *((_BYTE *)v5 + 40) == 4 && IoGetTopLevelIrp()->MdlAddress == (PMDL)2 )
      {
        IoGetTopLevelIrp()->MdlAddress = (PMDL)2147483650LL;
      }
      else
      {
        v37[0] = 0;
        RefsInitializeIrpContext(0, 1u, 0, v37);
        v6 = v37[0];
        if ( v37[0] )
        {
          *((_QWORD *)v37[0] + 8) = v7;
          *((_DWORD *)v6 + 166) = *((_DWORD *)v5 + 166);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 568));
          v25 = *(_DWORD *)(v7 + 560);
          if ( (v25 & 1) != 0 )
          {
            RefsCleanupIrpContext(v6, 0);
            v6 = 0;
            v37[0] = 0;
          }
          else
          {
            *(_DWORD *)(v7 + 560) = v25 | 1;
          }
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 568));
          KeLeaveGuardedRegion();
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 3221225556LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741740, 0, "NtfsData.c", 0x823u);
  v3 = -1073741740;
LABEL_141:
  if ( !v6 )
    goto LABEL_146;
  *((_DWORD *)v6 + 4) = 0;
  v26 = RefsPostRequest(v6, *((struct _IRP **)v6 + 9), v6 == v5, 0);
  if ( v6 == v5 )
  {
    v4 = 0;
    v5 = 0;
    v3 = v26;
  }
  if ( !v5 )
  {
    if ( !v4 )
      return v3;
LABEL_146:
    if ( !v5 )
      goto LABEL_150;
  }
  v27 = *((_QWORD *)v5 + 1);
  if ( (v27 & 0x40) == 0 && (v27 & 2) != 0 )
  {
    v4 = 0;
    goto LABEL_156;
  }
LABEL_150:
  if ( v4 )
  {
    if ( !v19 && *((_BYTE *)v5 + 40) == 4 && (*((_BYTE *)v5 + 41) & 6) == 6 )
    {
      v28 = v4->MdlAddress;
      if ( v28 )
      {
        CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, v28);
        v4->MdlAddress = 0;
      }
    }
  }
LABEL_156:
  if ( !v5 || !*((_QWORD *)v5 + 43) )
    goto LABEL_166;
  if ( *((_BYTE *)v5 + 40) == 2 && (v5 != *((struct _IRP_CONTEXT **)v5 + 13) || !LOBYTE(IoGetTopLevelIrp()->Type)) )
  {
    v19 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 259);
    }
    v3 = 259;
    RefsDiscardTriageInfo(v5);
    goto LABEL_166;
  }
  v29 = (struct _IRP_CONTEXT *)*((_QWORD *)v5 + 13);
  if ( v5 != v29 )
  {
    *((_QWORD *)v29 + 43) = *((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    *(_DWORD *)(*((_QWORD *)v5 + 13) + 16LL) = -1073741400;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 3221227528LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x8C4u);
    v3 = -1073739768;
    goto LABEL_166;
  }
  if ( LOBYTE(IoGetTopLevelIrp()->Type) )
  {
    v30 = (struct _SmsTriageContext *)*((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    if ( (*((_DWORD *)v5 + 2) & 0x10000) == 0 )
      *((_DWORD *)v5 + 1) |= 0x400u;
    RefsCleanupIrpContext(v5, 1u);
    v31 = RefsPerformTriage(v5, v30);
    if ( v31 < 0 )
    {
      v32 = *((_BYTE *)v5 + 40);
      if ( v32 != 2 || (v33 = *((_QWORD *)v5 + 1), (v33 & 4) != 0) )
      {
        if ( v32 != 18 || v31 != -1073741202 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids,
              (unsigned int)v31);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v31, 0, "NtfsData.c", 0x957u);
          v3 = v31;
          if ( v31 != -1073741608 && v31 != -1073741432 )
            v19 = 0;
        }
      }
      else
      {
        *((_QWORD *)v5 + 1) = v33 | 4;
      }
    }
LABEL_166:
    if ( v19 )
    {
      *((_DWORD *)v5 + 1) |= 0x400u;
      *((_DWORD *)v5 + 4) = 0;
      a2 = 0;
LABEL_211:
      a1 = v5;
      LODWORD(a3) = v3;
LABEL_212:
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, a2, a3);
      return v3;
    }
    goto LABEL_206;
  }
  if ( IoGetTopLevelIrp()->MdlAddress == (PMDL)7
    || (*((_DWORD *)v5 + 2) & 0x400000) != 0
    || (RefsInitializeIrpContext(0, 1u, 0, v37), (v34 = v37[0]) == 0) )
  {
    RefsDiscardTriageInfo(v5);
  }
  else
  {
    *((_QWORD *)v37[0] + 8) = *((_QWORD *)v5 + 8);
    *((_QWORD *)v34 + 43) = *((_QWORD *)v5 + 43);
    *((_QWORD *)v5 + 43) = 0;
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v5 + 8) + 556LL));
    RefsPostSpecial(
      v34,
      *((struct _VCB **)v34 + 8),
      (void (*)(struct _IRP_CONTEXT *, void *))RefsPerformTriageWorkItem,
      *((void **)v34 + 43),
      1u,
      0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids, 3221227528LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073739768, 0, "NtfsData.c", 0x918u);
  v3 = -1073739768;
LABEL_206:
  if ( !v5 || !v4 || (v35 = *((_QWORD *)v5 + 1), (v35 & 0x100000000LL) == 0) )
  {
    a2 = v4;
    goto LABEL_211;
  }
  *((_QWORD *)v5 + 1) = v35 | 0x200000000LL;
  return v3;
}

```

## disassembly

```asm
0x14000b1b0  mov     [rsp+arg_8], rdx
0x14000b1b5  mov     [rsp+arg_0], rcx
0x14000b1ba  push    rbx
0x14000b1bb  push    rsi
0x14000b1bc  push    rdi
0x14000b1bd  push    r12
0x14000b1bf  push    r13
0x14000b1c1  push    r14
0x14000b1c3  push    r15
0x14000b1c5  sub     rsp, 70h
0x14000b1c9  mov     esi, r8d
0x14000b1cc  mov     r14, rdx
0x14000b1cf  mov     rbx, rcx
0x14000b1d2  xor     edi, edi
0x14000b1d4  mov     [rsp+0A8h+var_58], rdi
0x14000b1d9  test    rcx, rcx
0x14000b1dc  jz      loc_14000C162
0x14000b1e2  mov     r15, [rcx+40h]
0x14000b1e6  mov     [rsp+0A8h+var_50], r15
0x14000b1eb  cmp     esi, 0C0000188h
0x14000b1f1  jnz     short loc_14000B21B
0x14000b1f3  mov     rdx, r15
0x14000b1f6  mov     ecx, [rcx+298h]
0x14000b1fc  call    ?RefsSqmLogFileFull@@YAXW4_LF_REASON@@PEAU_VCB@@@Z; RefsSqmLogFileFull(_LF_REASON,_VCB *)
0x14000b201  test    r15, r15
0x14000b204  jz      short loc_14000B21B
0x14000b206  movsxd  rax, dword ptr [rbx+298h]
0x14000b20d  cmp     eax, 0Eh
0x14000b210  ja      short loc_14000B21B
0x14000b212  lock inc qword ptr [r15+rax*8+2700h]
0x14000b21b  mov     esi, [rbx+10h]
0x14000b21e  mov     [rsp+0A8h+arg_10], esi
0x14000b225  cmp     byte ptr [rbx+28h], 4
0x14000b229  jnz     short loc_14000B262
0x14000b22b  movzx   eax, byte ptr [rbx+29h]
0x14000b22f  and     al, 6
0x14000b231  cmp     al, 2
0x14000b233  jnz     short loc_14000B262
0x14000b235  test    r14, r14
0x14000b238  jz      short loc_14000B262
0x14000b23a  mov     rdx, [r14+8]; MdlChain
0x14000b23e  test    rdx, rdx
0x14000b241  jz      short loc_14000B262
0x14000b243  mov     rcx, [r14+0B8h]
0x14000b24a  mov     rcx, [rcx+30h]; FileObject
0x14000b24e  call    cs:__imp_CcMdlWriteAbort
0x14000b255  nop     dword ptr [rax+rax+00h]
0x14000b25a  mov     qword ptr [r14+8], 0
0x14000b262  test    r15, r15
0x14000b265  jz      loc_14000B396
0x14000b26b  mov     dl, 1; unsigned __int8
0x14000b26d  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b270  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14000b275  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b278  call    ?RefsAbortPendingUsnReasons@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortPendingUsnReasons(_IRP_CONTEXT *)
0x14000b27d  mov     rcx, [rbx+18h]; struct _IRP_CONTEXT *
0x14000b281  test    rcx, rcx
0x14000b284  jz      short loc_14000B2D2
0x14000b286  lea     rdx, [rbx+158h]
0x14000b28d  cmp     qword ptr [rdx], 0
0x14000b291  jnz     short loc_14000B298
0x14000b293  call    MsTriageGetContext
0x14000b298  cmp     byte ptr [rbx+28h], 4
0x14000b29c  jnz     short loc_14000B2C8
0x14000b29e  mov     eax, [r15+18h]
0x14000b2a2  test    al, 1
0x14000b2a4  jz      short loc_14000B2C8
0x14000b2a6  mov     rax, [r15+70h]
0x14000b2aa  test    dword ptr [rax+0D44h], 800000h
0x14000b2b4  jz      short loc_14000B2C8
0x14000b2b6  test    dword ptr [rbx+4], 8000000h
0x14000b2bd  jnz     short loc_14000B2C8
0x14000b2bf  mov     rcx, [rbx+18h]
0x14000b2c3  call    MsSetOkayToResyncSMRBands
0x14000b2c8  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b2cb  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x14000b2d0  jmp     short loc_14000B335
0x14000b2d2  lea     rdx, [rbx+280h]; struct _LIST_ENTRY *
0x14000b2d9  cmp     [rdx], rdx
0x14000b2dc  jz      short loc_14000B2F5
0x14000b2de  mov     r8d, 4
0x14000b2e4  mov     r12d, 1
0x14000b2ea  test    esi, esi
0x14000b2ec  cmovns  r8d, r12d; unsigned int
0x14000b2f0  call    ?RefsProcessRollbackListPriv@@YAXPEAU_IRP_CONTEXT@@PEAU_LIST_ENTRY@@K@Z; RefsProcessRollbackListPriv(_IRP_CONTEXT *,_LIST_ENTRY *,ulong)
0x14000b2f5  mov     eax, [rbx+8]
0x14000b2f8  bt      rax, 1Dh
0x14000b2fd  jnb     short loc_14000B335
0x14000b2ff  mov     rcx, [rbx+40h]
0x14000b303  mov     rax, [rcx+3E0h]
0x14000b30a  mov     [rcx+3A0h], rax
0x14000b311  mov     rax, [rcx+3E8h]
0x14000b318  mov     [rcx+3C8h], rax
0x14000b31f  mov     rax, [rcx+3F0h]
0x14000b326  mov     [rcx+3D0h], rax
0x14000b32d  and     qword ptr [rbx+8], 0FFFFFFFFDFFFFFFFh
0x14000b335  xor     edx, edx; unsigned __int8
0x14000b337  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b33a  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14000b33f  mov     rax, [r15+108h]
0x14000b346  cmp     [r15+0F0h], rax
0x14000b34d  jz      loc_14000B4CC
0x14000b353  mov     rax, [r15+48h]
0x14000b357  test    rax, rax
0x14000b35a  jz      loc_14000B4CC
0x14000b360  mov     rax, [rax+88h]
0x14000b367  mov     rcx, [rax+58h]
0x14000b36b  add     rcx, 40h ; '@'
0x14000b36f  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14000b376  nop     dword ptr [rax+rax+00h]
0x14000b37b  test    al, al
0x14000b37d  jz      loc_14000B4CC
0x14000b383  mov     rax, [r15+108h]
0x14000b38a  mov     [r15+0F0h], rax
0x14000b391  jmp     loc_14000B4CC
0x14000b396  cmp     esi, 0C00001A8h
0x14000b39c  jnz     short loc_14000B41B
0x14000b39e  lea     rdx, WPP_GLOBAL_Control
0x14000b3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b3ac  cmp     rcx, rdx
0x14000b3af  jz      short loc_14000B3E2
0x14000b3b1  test    dword ptr [rcx+2Ch], 100h
0x14000b3b8  jz      short loc_14000B3E2
0x14000b3ba  cmp     byte ptr [rcx+29h], 4
0x14000b3be  jb      short loc_14000B3E2
0x14000b3c0  mov     edx, 16h
0x14000b3c5  mov     r9d, 0C0000808h
0x14000b3cb  lea     r8, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids
0x14000b3d2  mov     rcx, [rcx+18h]
0x14000b3d6  call    WPP_SF_d
0x14000b3db  lea     rdx, WPP_GLOBAL_Control
0x14000b3e2  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14000b3e9  test    al, al
0x14000b3eb  jz      short loc_14000B40D
0x14000b3ed  mov     r9d, 64Eh; unsigned int
0x14000b3f3  lea     r8, aNtfsdataC; "NtfsData.c"
0x14000b3fa  xor     edx, edx; struct _IRP_CONTEXT *
0x14000b3fc  mov     ecx, 0C0000808h; Status
0x14000b401  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14000b406  lea     rdx, WPP_GLOBAL_Control
0x14000b40d  mov     esi, 0C0000808h
0x14000b412  mov     [rsp+0A8h+arg_10], esi
0x14000b419  jmp     short loc_14000B422
0x14000b41b  lea     rdx, WPP_GLOBAL_Control
0x14000b422  mov     rcx, [rbx+18h]
0x14000b426  test    rcx, rcx
0x14000b429  jz      short loc_14000B444
0x14000b42b  lea     rdx, [rbx+158h]
0x14000b432  cmp     qword ptr [rdx], 0
0x14000b436  jnz     short loc_14000B43D
0x14000b438  call    MsTriageGetContext
0x14000b43d  lea     rdx, WPP_GLOBAL_Control
0x14000b444  cmp     qword ptr [rbx+158h], 0
0x14000b44c  jz      short loc_14000B45D
0x14000b44e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b451  call    ?RefsDiscardTriageInfo@@YAXPEAU_IRP_CONTEXT@@@Z; RefsDiscardTriageInfo(_IRP_CONTEXT *)
0x14000b456  lea     rdx, WPP_GLOBAL_Control
0x14000b45d  cmp     esi, 0C0000188h
0x14000b463  jnz     short loc_14000B4CC
0x14000b465  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b46c  cmp     rcx, rdx
0x14000b46f  jz      short loc_14000B49F
0x14000b471  test    dword ptr [rcx+2Ch], 100h
0x14000b478  jz      short loc_14000B49F
0x14000b47a  cmp     byte ptr [rcx+29h], 4
0x14000b47e  jb      short loc_14000B49F
0x14000b480  mov     edx, 17h
0x14000b485  mov     esi, 0C000007Fh
0x14000b48a  mov     r9d, esi
0x14000b48d  lea     r8, WPP_0997378fd04b3223adb7f09f4a8c51da_Traceguids
0x14000b494  mov     rcx, [rcx+18h]
0x14000b498  call    WPP_SF_d
0x14000b49d  jmp     short loc_14000B4A4
0x14000b49f  mov     esi, 0C000007Fh
0x14000b4a4  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14000b4ab  test    al, al
0x14000b4ad  jz      short loc_14000B4C5
0x14000b4af  mov     r9d, 66Bh; unsigned int
0x14000b4b5  lea     r8, aNtfsdataC; "NtfsData.c"
0x14000b4bc  xor     edx, edx; struct _IRP_CONTEXT *
0x14000b4be  mov     ecx, esi; Status
0x14000b4c0  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14000b4c5  mov     [rsp+0A8h+arg_10], esi
0x14000b4cc  jmp     loc_14000B735
0x14000b4d1  inc     cs:?RefsFailedAborts@@3KA; ulong RefsFailedAborts
0x14000b4d7  lea     rdx, WPP_GLOBAL_Control; unsigned int
0x14000b4de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4e5  cmp     rcx, rdx
0x14000b4e8  jz      short loc_14000B528
0x14000b4ea  mov     edx, [rcx+2Ch]
0x14000b4ed  test    dl, 4
0x14000b4f0  jz      short loc_14000B528
0x14000b4f2  cmp     byte ptr [rcx+29h], 2
0x14000b4f6  jb      short loc_14000B528
0x14000b4f8  mov     dword ptr [rsp+0A8h+var_70], eax
0x14000b4fc  mov     rbx, [rsp+0A8h+arg_0]
0x14000b504  mov     rax, [rbx+40h]
0x14000b508  mov     qword ptr [rsp+0A8h+var_80], rax
0x14000b50d  mov     r14, [rsp+0A8h+arg_8]
0x14000b515  mov     qword ptr [rsp+0A8h+var_88], r14
0x14000b51a  mov     r9, rbx
0x14000b51d  mov     rcx, [rcx+18h]
0x14000b521  call    WPP_SF_qqqDd
0x14000b526  jmp     short loc_14000B538
0x14000b528  mov     r14, [rsp+0A8h+arg_8]
0x14000b530  mov     rbx, [rsp+0A8h+arg_0]
0x14000b538  lea     rcx, [rbx+280h]; struct _LIST_ENTRY *
0x14000b53f  xor     r8d, r8d; struct _ROLLBACK_STRUCT *
0x14000b542  call    ?RefsFindRollbackStructByType@@YAPEAU_ROLLBACK_STRUCT@@PEAU_LIST_ENTRY@@KPEAU1@@Z; RefsFindRollbackStructByType(_LIST_ENTRY *,ulong,_ROLLBACK_STRUCT *)
0x14000b547  mov     rsi, rax
0x14000b54a  test    rax, rax
0x14000b54d  jz      loc_14000B6CF
0x14000b553  mov     rdi, [rsi+30h]
0x14000b557  test    rdi, rdi
0x14000b55a  jz      loc_14000B6B4
0x14000b560  lea     rax, WPP_GLOBAL_Control
0x14000b567  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b56e  cmp     rcx, rax
0x14000b571  jz      short loc_14000B5C2
0x14000b573  mov     eax, [rcx+2Ch]
0x14000b576  test    al, 4
0x14000b578  jz      short loc_14000B5C2
0x14000b57a  cmp     byte ptr [rcx+29h], 2
0x14000b57e  jb      short loc_14000B5C2
0x14000b580  mov     rax, [rdi+88h]
0x14000b587  mov     rdx, [rax+58h]
0x14000b58b  mov     rax, [rdx+0F8h]
0x14000b592  mov     [rsp+0A8h+var_68], rax
0x14000b597  mov     rax, [rdx+100h]
0x14000b59e  mov     [rsp+0A8h+var_70], rax
0x14000b5a3  mov     [rsp+0A8h+var_78], rdi
0x14000b5a8  mov     rax, [rbx+40h]
0x14000b5ac  mov     qword ptr [rsp+0A8h+var_80], rax
0x14000b5b1  mov     qword ptr [rsp+0A8h+var_88], r14
0x14000b5b6  mov     r9, rbx
0x14000b5b9  mov     rcx, [rcx+18h]
0x14000b5bd  call    WPP_SF_qqqqii
0x14000b5c2  mov     rax, [rdi+88h]
0x14000b5c9  mov     ecx, [rax+8]
0x14000b5cc  test    rcx, 104h
0x14000b5d3  jnz     short loc_14000B651
0x14000b5d5  mov     eax, [rdi+98h]
0x14000b5db  test    eax, 220h
0x14000b5e0  jz      short loc_14000B5ED
0x14000b5e2  lock and dword ptr [rdi+98h], 0FFFFFDDFh
0x14000b5ed  mov     qword ptr [rdi+18h], 0
0x14000b5f5  mov     eax, 805h
0x14000b5fa  cmp     [rdi], ax
0x14000b5fd  jnz     short loc_14000B60A
0x14000b5ff  mov     qword ptr [rdi+1A8h], 0
0x14000b60a  mov     qword ptr [rdi+20h], 0
0x14000b612  mov     qword ptr [rdi+28h], 0
0x14000b61a  cmp     [rdi], ax
0x14000b61d  jnz     short loc_14000B634
0x14000b61f  cmp     qword ptr [rdi+1A8h], 0
0x14000b627  jge     short loc_14000B634
0x14000b629  mov     qword ptr [rdi+1A8h], 0
0x14000b634  cmp     qword ptr [rdi+0F0h], 0
0x14000b63c  jz      short loc_14000B6B0
0x14000b63e  mov     r8d, 1; unsigned int
0x14000b644  mov     rdx, rdi; struct _SCB *
0x14000b647  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000b64a  call    ?RefsDeleteInternalAttributeStream@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@KE@Z; RefsDeleteInternalAttributeStream(_IRP_CONTEXT *,_SCB *,ulong,uchar)
0x14000b64f  jmp     short loc_14000B6B0
0x14000b651  mov     rax, [rdi+18h]
0x14000b655  cmp     [rsi+18h], rax
0x14000b659  jge     short loc_14000B678
0x14000b65b  mov     rax, [rsi+18h]
0x14000b65f  mov     [rdi+18h], rax
0x14000b663  mov     eax, 805h
0x14000b668  cmp     [rdi], ax
0x14000b66b  jnz     short loc_14000B678
0x14000b66d  mov     rax, [rsi+18h]
0x14000b671  mov     [rdi+1A8h], rax
0x14000b678  mov     rax, [rdi+20h]
0x14000b67c  cmp     [rsi+20h], rax
0x14000b680  jge     short loc_14000B6B0
0x14000b682  mov     rax, [rsi+20h]
0x14000b686  mov     [rdi+20h], rax
0x14000b68a  mov     rax, [rsi+20h]
0x14000b68e  mov     [rdi+28h], rax
0x14000b692  mov     eax, 805h
0x14000b697  cmp     [rdi], ax
0x14000b69a  jnz     short loc_14000B6B0
0x14000b69c  mov     rax, [rsi+20h]
0x14000b6a0  cmp     [rdi+1A8h], rax
0x14000b6a7  jge     short loc_14000B6B0
0x14000b6a9  mov     [rdi+1A8h], rax
0x14000b6b0  mov     byte ptr [rdi+5], 0
0x14000b6b4  mov     r8, rsi; struct _ROLLBACK_STRUCT *
0x14000b6b7  lea     rcx, [rbx+280h]; struct _LIST_ENTRY *
0x14000b6be  call    ?RefsFindRollbackStructByType@@YAPEAU_ROLLBACK_STRUCT@@PEAU_LIST_ENTRY@@KPEAU1@@Z; RefsFindRollbackStructByType(_LIST_ENTRY *,ulong,_ROLLBACK_STRUCT *)
0x14000b6c3  mov     rsi, rax
0x14000b6c6  test    rax, rax
0x14000b6c9  jnz     loc_14000B553
0x14000b6cf  mov     r15, [rsp+0A8h+var_50]
0x14000b6d4  test    r15, r15
0x14000b6d7  jz      short loc_14000B721
0x14000b6d9  mov     rax, [r15+108h]
0x14000b6e0  cmp     [r15+0F0h], rax
  ... truncated ...
```
