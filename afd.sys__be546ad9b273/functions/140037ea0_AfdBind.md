# AfdBind

- ea: `0x140037ea0`
- end: `0x140038af6`
- name: `AfdBind`
- size: `3158`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140002440`
- `0x140005b60`
- `0x14001b0d0`
- `0x1400250a0`
- `0x14002c3e0`
- `0x14002fd7c`
- `0x140031720`
- `0x140032798`
- `0x140033bfc`
- `0x14003576c`
- `0x140037394`
- `0x140037ea0`
- `0x1400391b8`
- `0x14003f19c`
- `0x1400445d8`
- `0x140046114`
- `0x140072870`
- `0x14009214c`
- `0x14009304c`
- `0x14009327c`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14003885d`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14003885d`
- `ntoskrnl!ProbeForRead` at `0x140038040`
- `ntoskrnl!ProbeForRead` at `0x140038040`
- `ntoskrnl!ZwClose` at `0x1400389f7`
- `ntoskrnl!ZwClose` at `0x1400389f7`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140038a4e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140038a4e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140038a2e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140038a2e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003831d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003831d`
- `ntoskrnl!IoFreeMdl` at `0x140038a99`
- `ntoskrnl!IoFreeMdl` at `0x140038a99`
- `ntoskrnl!MmUnlockPages` at `0x140038a89`
- `ntoskrnl!MmUnlockPages` at `0x140038a89`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400382ed`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400382ed`
- `ntoskrnl!IoAllocateMdl` at `0x14003829d`
- `ntoskrnl!IoAllocateMdl` at `0x14003829d`
- `ntoskrnl!IofCompleteRequest` at `0x140038ad4`
- `ntoskrnl!IofCompleteRequest` at `0x140038ad4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400389ce`
- `ntoskrnl!ObfDereferenceObject` at `0x1400389ce`
- `ntoskrnl!IofCallDriver` at `0x1400388fe`
- `ntoskrnl!IofCallDriver` at `0x1400388fe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038590`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400386e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400389b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038590`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400386e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400389b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038575`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038693`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038995`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038575`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038693`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038995`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a62`
- `ntoskrnl!ExAllocatePool2` at `0x14003805d`
- `ntoskrnl!ExAllocatePool2` at `0x14003805d`

## pseudocode

```c
__int64 __fastcall AfdBind(PIRP Irp, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  unsigned int v8; // r12d
  int v9; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  int v11; // r9d
  int v12; // esi
  unsigned int v13; // eax
  unsigned int v14; // ecx
  int v15; // edx
  ADDRESS_FAMILY *Pool2; // rcx
  unsigned int *v17; // rsi
  unsigned int v18; // eax
  void *v19; // rdx
  __int64 v20; // rsi
  ADDRESS_FAMILY *v21; // r12
  __int64 v22; // r15
  unsigned int ULongFromUser; // eax
  void *v24; // rdx
  PMDL v25; // rcx
  PVOID MappedSystemVa; // rax
  const UNICODE_STRING **v28; // r15
  int TransportInfo; // eax
  int v30; // r9d
  int v31; // edx
  int v32; // ecx
  __int64 *v33; // r15
  int v34; // esi
  char v35; // cl
  ULONG v36; // r12d
  ULONG v37; // ecx
  int v38; // eax
  int AO; // eax
  char v40; // r12
  __int64 v41; // rdx
  __int64 v42; // r9
  __int16 v43; // cx
  int v44; // eax
  PIRP v45; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v47; // rcx
  void *v48; // rcx
  void *v49; // rcx
  PMDL MdlAddress; // rcx
  ULONG Priority; // [rsp+28h] [rbp-C0h]
  int v52; // [rsp+30h] [rbp-B8h]
  ADDRESS_FAMILY *P; // [rsp+58h] [rbp-90h]
  __int64 v54; // [rsp+60h] [rbp-88h]
  void *v55; // [rsp+70h] [rbp-78h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-70h] BYREF
  volatile __int32 *v57; // [rsp+90h] [rbp-58h]
  __int64 v58; // [rsp+98h] [rbp-50h]
  __int64 v59; // [rsp+A0h] [rbp-48h]
  __int64 v60; // [rsp+A8h] [rbp-40h]
  PIRP v61; // [rsp+F0h] [rbp+8h] BYREF
  __int64 v62; // [rsp+F8h] [rbp+10h]
  unsigned int v63; // [rsp+100h] [rbp+18h]
  unsigned int v64; // [rsp+108h] [rbp+20h]

  v62 = a2;
  v61 = Irp;
  v3 = a2;
  v55 = 0;
  v60 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v5 = v60;
  Irp->IoStatus.Information = 0;
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
  {
    v6 = *(_DWORD *)(a2 + 16);
    if ( v6 < 8 || (v7 = *(_DWORD *)(a2 + 8), v7 < 0xC) || (v8 = v6 - 4, v64 = v6 - 4, v7 - 4 < v6 - 4) )
    {
      v9 = 7000;
LABEL_162:
      v12 = -1073741811;
      v11 = -1073741811;
      goto LABEL_163;
    }
    v55 = 0;
LABEL_19:
    v57 = (volatile __int32 *)(v5 + 368);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), 3, 0) )
    {
      v9 = 7002;
      goto LABEL_162;
    }
    if ( (unsigned __int8)(*(_BYTE *)(v5 + 2) - 1) > 1u )
    {
      v15 = 7003;
LABEL_23:
      v12 = -1073741256;
      AFDETW_TRACEBIND(0, v15, v5, -1073741256, 0);
LABEL_157:
      _InterlockedExchange(v57, 0);
      MdlAddress = Irp->MdlAddress;
      if ( MdlAddress )
      {
        if ( (MdlAddress->MdlFlags & 2) != 0 )
          MmUnlockPages(MdlAddress);
        IoFreeMdl(Irp->MdlAddress);
        Irp->MdlAddress = 0;
      }
      goto LABEL_164;
    }
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && *(_QWORD *)(v5 + 24) )
    {
      v15 = 7024;
      goto LABEL_23;
    }
    v58 = v5;
    v54 = *(_QWORD *)(v5 + 40);
    v59 = v54;
    if ( Irp->RequestorMode )
      ProbeForRead(*(volatile void **)(v3 + 32), *(unsigned int *)(v3 + 16), 4u);
    Pool2 = (ADDRESS_FAMILY *)ExAllocatePool2(97, v8, 1818519105);
    P = Pool2;
    v17 = *(unsigned int **)(v62 + 32);
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
    {
      if ( v8 < 2 )
      {
        AFDETW_TRACEBIND(0, 7020, v5, -1073741503, 0);
        v12 = -1073741503;
        v21 = P;
        v22 = v54;
        goto LABEL_144;
      }
      if ( Irp->RequestorMode )
      {
        ULongFromUser = RtlReadULongFromUser(*(_QWORD *)(v62 + 32));
        Pool2 = P;
      }
      else
      {
        ULongFromUser = *v17;
      }
      v63 = ULongFromUser;
      v24 = v17 + 1;
      if ( Irp->RequestorMode )
        RtlCopyFromUser(Pool2, v24, v8);
      else
        RtlCopyVolatileMemory(Pool2, v24, v8);
      v20 = (__int64)P;
      if ( *P >= 0x23u )
      {
        AFDETW_TRACEBIND(0, 7005, v5, -1073741503, 0);
        v12 = -1073741503;
        v21 = P;
        v22 = v54;
        goto LABEL_144;
      }
      if ( v8 < SOCKADDR_SIZE(*P) )
      {
        AFDETW_TRACEBIND(0, 7006, v5, -1073741503, 0);
        v12 = -1073741503;
        v21 = P;
        v22 = v54;
        goto LABEL_144;
      }
    }
    else
    {
      if ( Irp->RequestorMode )
      {
        v18 = RtlReadULongFromUser(*(_QWORD *)(v62 + 32));
        Pool2 = P;
      }
      else
      {
        v18 = *v17;
      }
      v63 = v18;
      v19 = v17 + 1;
      if ( Irp->RequestorMode )
        RtlCopyFromUser(Pool2, v19, v8);
      else
        RtlCopyVolatileMemory(Pool2, v19, v8);
      if ( v8 < 4 || (v20 = (__int64)P, *(_DWORD *)P != 1) )
      {
        AFDETW_TRACEBIND(0, 7018, v5, -1073741811, 0);
        v12 = -1073741811;
        v21 = P;
        v22 = v54;
        goto LABEL_144;
      }
      if ( v8 < 6uLL )
      {
        AFDETW_TRACEBIND(0, 7019, v5, -1073741811, 0);
        v12 = -1073741811;
        v21 = P;
        v22 = v54;
LABEL_144:
        if ( (*(_DWORD *)(v5 + 8) & 0x8000000) != 0 )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
          *(_DWORD *)(v5 + 8) &= ~0x8000000u;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
        {
          v48 = *(void **)(v5 + 24);
          if ( v48 )
          {
            ObfDereferenceObject(v48);
            *(_QWORD *)(v5 + 24) = 0;
          }
        }
        *(_QWORD *)(v5 + 40) = v22;
        if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
        {
          v49 = *(void **)(v5 + 256);
          if ( v49 )
          {
            ZwClose(v49);
            *(_QWORD *)(v5 + 256) = 0;
          }
        }
        if ( v21 )
        {
          if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
          {
            *(_QWORD *)(v5 + 240) = 0;
            *(_DWORD *)(v5 + 236) = 0;
          }
          else
          {
            ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
            *(_QWORD *)(v5 + 240) = 0;
            *(_DWORD *)(v5 + 236) = 0;
            ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
          }
          ExFreePoolWithTag(v21, 0x6C646641u);
        }
        goto LABEL_157;
      }
      if ( v8 < (unsigned int)P[2] + 8 )
      {
        AFDETW_TRACEBIND(0, 7004, v5, -1073741811, 0);
        v12 = -1073741811;
        v21 = P;
        v22 = v54;
        goto LABEL_144;
      }
    }
    if ( !IoAllocateMdl(Irp->UserBuffer, *(_DWORD *)(v62 + 8), 0, 1u, Irp) )
    {
      AFDETW_TRACEBIND(0, 7007, v5, -1073741670, 0);
      v12 = -1073741670;
      v21 = P;
      v22 = v54;
      goto LABEL_144;
    }
    MmProbeAndLockPages(Irp->MdlAddress, Irp->RequestorMode, IoWriteAccess);
    v25 = Irp->MdlAddress;
    if ( (v25->MdlFlags & 5) != 0 )
      MappedSystemVa = v25->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v25, 0, MmCached, 0, 0, 0x40000020u);
    if ( !MappedSystemVa )
    {
      AFDETW_TRACEBIND(0, 7008, v5, -1073741670, 0);
      v12 = -1073741670;
      v21 = P;
      v22 = v54;
      goto LABEL_144;
    }
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
    {
      *(_QWORD *)(v5 + 240) = v20;
      *(_DWORD *)(v5 + 236) = v8;
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      AFDETW_TRACEBIND(0, 7010, v5, 0, v20);
      AfdTLBindSecurity(Irp, v5, v63);
      return 259;
    }
    v28 = (const UNICODE_STRING **)(v5 + 272);
    if ( !*(_BYTE *)(*(_QWORD *)(v5 + 272) + 24LL) )
    {
      TransportInfo = AfdGetTransportInfo(*v28 + 2);
      v12 = TransportInfo;
      if ( TransportInfo < 0 )
      {
        v30 = TransportInfo;
        v31 = 7011;
LABEL_67:
        v32 = 0;
LABEL_68:
        AFDETW_TRACEBIND(v32, v31, v5, v30, 0);
LABEL_142:
        v21 = P;
        goto LABEL_143;
      }
    }
    *(_DWORD *)(v5 + 16) = (*v28)[4].Buffer;
    *(_QWORD *)(v5 + 240) = P;
    *(_DWORD *)(v5 + 236) = v8;
    if ( ((*(_DWORD *)(v5 + 8) & 0x100) != 0 || (*(_DWORD *)(v5 + 16) & 0x100000) != 0)
      && (v33 = *(__int64 **)(v5 + 40)) != 0 )
    {
      v34 = v63;
    }
    else
    {
      v33 = 0;
      v34 = v63;
      if ( v63 )
      {
        switch ( v63 )
        {
          case 1u:
            if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 || (v35 = 0, (*(_DWORD *)(v5 + 16) & 0x100000) != 0) )
              v35 = 1;
            v36 = 3;
            break;
          case 2u:
            if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 || (v35 = 0, (*(_DWORD *)(v5 + 16) & 0x100000) != 0) )
              v35 = 1;
            v36 = v35 == 0 ? 3 : 0;
            break;
          case 3u:
            goto LABEL_93;
          default:
            v12 = -1073741811;
            v30 = -1073741811;
            v31 = 7012;
            goto LABEL_67;
        }
        v33 = (__int64 *)((unsigned __int64)AfdEmptySd & -(__int64)(v35 != 0));
        goto LABEL_94;
      }
      if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x100000) == 0 )
      {
        if ( (unsigned __int8)AfdIsAddressInUse(v5) )
        {
          v12 = -1073741757;
          goto LABEL_142;
        }
        v36 = 3;
LABEL_94:
        AFDETW_TRACEBIND(0, 7016, v5, 0, (__int64)P);
        if ( (*(_DWORD *)(v5 + 16) & 0x10000) == 0 )
        {
          v37 = 256;
          LODWORD(v61) = 256;
          if ( (*(_BYTE *)(v5 + 5) & 1) != 0 )
          {
            if ( !AfdDisableRawSecurity && !*(_BYTE *)(v5 + 3) )
            {
              v30 = -1073741790;
              v12 = -1073741790;
              v31 = 7013;
LABEL_99:
              v32 = 1;
              goto LABEL_68;
            }
LABEL_103:
            v38 = AfdTdiCreateAO(v5, P, v64, v33, v34, v36, v37, Irp->RequestorMode, 0, &v55);
            v12 = v38;
            if ( v38 < 0 )
            {
              v30 = v38;
              v31 = 7014;
              goto LABEL_99;
            }
            if ( (*(_DWORD *)(v5 + 8) & 0x400000) != 0 )
            {
              Priority = v36;
              v21 = P;
              AO = AfdTdiCreateAO(v5, P, v64, v33, v63, Priority, (ULONG)v61, Irp->RequestorMode, 1, 0);
              v12 = AO;
              if ( AO < 0 )
              {
                AFDETW_TRACEBIND(1, 7015, v5, AO, 0);
LABEL_143:
                v22 = v54;
                goto LABEL_144;
              }
            }
            v40 = 0;
            if ( *(_WORD *)v5 == 0xAFD1 )
            {
              memset(&LockHandle, 0, sizeof(LockHandle));
              KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
              *(_DWORD *)(v5 + 72) = 4;
              AfdNotifySockEventsChangedUnderLock(v5, 4, 0);
              if ( (xmmword_1400875E0 & 0x20) != 0 )
                WPP_SF_qD(1029, 20, WPP_43911188515d396c99d3028411eb93bd_Traceguids, v5, *(_DWORD *)(v5 + 72));
              KeReleaseInStackQueuedSpinLock(&LockHandle);
            }
            AfdTdiSetEventHandlers(v5, 0);
            if ( (*(_DWORD *)(v5 + 8) & 0x400000) != 0 )
            {
              LOBYTE(v41) = 1;
              AfdTdiSetEventHandlers(v5, v41);
            }
            v43 = *(_WORD *)v5;
            if ( *(_WORD *)v5 != 0xAFD1 )
            {
              if ( (*(_BYTE *)(v5 + 5) & 0x10) != 0 && (*(_BYTE *)(v5 + 6) & 1) != 0 )
              {
                v61 = 0;
                if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 || (LOBYTE(v42) = 1, (*(_DWORD *)(v5 + 16) & 0x200) == 0) )
                  LOBYTE(v42) = 0;
                v44 = AfdCreateConnection(
                        v5,
                        *(_QWORD *)(v5 + 272),
                        *(_QWORD *)(v5 + 256),
                        v42,
                        0,
                        (*(_DWORD *)(v5 + 8) >> 7) & 1,
                        *(_QWORD *)(v5 + 48),
                        &v61);
                v12 = v44;
                if ( v44 < 0 )
                {
                  v21 = P;
                  AFDETW_TRACEBIND(1, 7017, v5, v44, (__int64)P);
                  goto LABEL_143;
                }
                if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 64)) <= 1 )
                  __fastfail(0xEu);
                v45 = v61;
                v61->MdlAddress = (PMDL)v5;
                *(_QWORD *)(v5 + 192) = v45;
                *(_WORD *)v5 = -20526;
                v12 = AfdAddConnectedReference(v45);
                if ( v12 < 0 )
                  goto LABEL_142;
                *(_BYTE *)(v5 + 2) = 4;
                v45->Size = 3;
LABEL_136:
                _InterlockedExchange(v57, 0);
                if ( v54 )
                  ObDereferenceSecurityDescriptor(v54, 1);
                CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
                CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartBindGetAddress;
                CurrentStackLocation[-1].Context = (PVOID)v5;
                CurrentStackLocation[-1].Control = -32;
                v47 = Irp->Tail.Overlay.CurrentStackLocation;
                *(_WORD *)&v47[-1].MajorFunction = 3087;
                v47[-1].DeviceObject = *(PDEVICE_OBJECT *)(v5 + 40);
                v47[-1].FileObject = *(PFILE_OBJECT *)(v5 + 24);
                v47[-1].Parameters.Read.Length = 3;
                v47[-1].Parameters.QueryDirectory.FileName = 0;
                *(_QWORD *)(v62 + 32) = v55;
                if ( (xmmword_1400875E0 & 0x40) != 0 )
                  WPP_SF_qqq(
                    1030,
                    21,
                    WPP_43911188515d396c99d3028411eb93bd_Traceguids,
                    v5,
                    *(_QWORD *)(v5 + 240),
                    *(_QWORD *)(v5 + 24),
                    v52);
                _InterlockedAdd((volatile signed __int32 *)(v5 + 248), 1u);
                v12 = IofCallDriver(*(PDEVICE_OBJECT *)(v5 + 40), Irp);
                if ( v40 )
                  AfdReallowUnbind(v5);
                return (unsigned int)v12;
              }
              if ( v43 != -20527
                && v43 != 6909
                && ((*(_BYTE *)(v5 + 5) & 0x10) == 0 || (*(_BYTE *)(v5 + 6) & 1) == 0)
                && (*(_DWORD *)(v5 + 8) & 1) == 0
                && *(_BYTE *)(v5 + 2) != 4 )
              {
                if ( !(unsigned __int8)AfdPreventUnbind(v5) )
                {
                  v12 = -1073741436;
                  goto LABEL_142;
                }
                v40 = 1;
              }
            }
            *(_BYTE *)(v5 + 2) = 3;
            goto LABEL_136;
          }
          if ( !Irp->RequestorMode )
            goto LABEL_103;
          memset(&LockHandle, 0, sizeof(LockHandle));
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
          *(_DWORD *)(v5 + 8) |= 0x8000000u;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        v37 = 257;
        LODWORD(v61) = 257;
        goto LABEL_103;
      }
      v33 = AfdEmptySd;
    }
LABEL_93:
    v36 = 0;
    goto LABEL_94;
  }
  if ( (*(_BYTE *)(v5 + 5) & 0x10) == 0 || (*(_BYTE *)(v5 + 6) & 1) == 0 )
  {
    if ( (Feature_TCPIP_AfdFuzzingFix__private_featureState & 0x10) != 0 )
    {
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_AfdFuzzingFix__private_featureState & 1;
    }
    else
    {
      IsEnabledDeviceUsageNoInline = Feature_TCPIP_AfdFuzzingFix__private_IsEnabledDeviceUsageNoInline(Irp, a2, a3, a2);
      v3 = v62;
    }
    if ( !IsEnabledDeviceUsageNoInline || (*(_BYTE *)(v5 + 5) & 0x10) == 0 || (*(_BYTE *)(v5 + 6) & 1) == 0 )
    {
      v13 = *(_DWORD *)(v3 + 16);
      if ( v13 < 6 || (v14 = *(_DWORD *)(v3 + 8), v14 < 2) || (v8 = v13 - 4, v64 = v13 - 4, v14 < v13 - 4) )
      {
        v9 = 7001;
        goto LABEL_162;
      }
      goto LABEL_19;
    }
  }
  v11 = -1073741790;
  v12 = -1073741790;
  v9 = 7044;
LABEL_163:
  AFDETW_TRACEBIND(0, v9, v5, v11, 0);
LABEL_164:
  Irp->IoStatus.Status = v12;
  IofCompleteRequest(Irp, AfdPriorityBoost);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140037ea0  mov     r11, rsp
0x140037ea3  mov     [r11+10h], rdx
0x140037ea7  mov     [r11+8], rcx
0x140037eab  push    rbx
0x140037eac  push    rsi
0x140037ead  push    rdi
0x140037eae  push    r12
0x140037eb0  push    r13
0x140037eb2  push    r14
0x140037eb4  push    r15
0x140037eb6  sub     rsp, 0B0h
0x140037ebd  mov     r9, rdx
0x140037ec0  mov     r13, rcx
0x140037ec3  xor     edi, edi
0x140037ec5  mov     [r11-78h], rdi
0x140037ec9  mov     rax, [rdx+30h]
0x140037ecd  mov     rbx, [rax+18h]
0x140037ed1  mov     [rsp+0E8h+var_40], rbx
0x140037ed9  mov     [rcx+38h], rdi
0x140037edd  mov     eax, [rbx+8]
0x140037ee0  bt      eax, 8
0x140037ee4  jb      short loc_140037F21
0x140037ee6  mov     eax, [rdx+10h]
0x140037ee9  cmp     eax, 8
0x140037eec  jb      short loc_140037F17
0x140037eee  mov     ecx, [rdx+8]
0x140037ef1  cmp     ecx, 0Ch
0x140037ef4  jb      short loc_140037F17
0x140037ef6  lea     r12d, [rax-4]
0x140037efa  mov     [rsp+0E8h+arg_18], r12d
0x140037f02  lea     eax, [rcx-4]
0x140037f05  cmp     eax, r12d
0x140037f08  jb      short loc_140037F17
0x140037f0a  mov     [r11-78h], rdi
0x140037f0e  lea     r14d, [rdi+1]
0x140037f12  jmp     loc_140037FA1
0x140037f17  mov     edx, 1B58h
0x140037f1c  jmp     loc_140038AB0
0x140037f21  mov     r14d, 1
0x140037f27  test    byte ptr [rbx+5], 10h
0x140037f2b  jz      short loc_140037F33
0x140037f2d  test    [rbx+6], r14b
0x140037f31  jnz     short loc_140037F5F
0x140037f33  mov     eax, cs:Feature_TCPIP_AfdFuzzingFix__private_featureState
0x140037f39  test    al, 10h
0x140037f3b  jz      short loc_140037F42
0x140037f3d  and     eax, r14d
0x140037f40  jmp     short loc_140037F4F
0x140037f42  call    Feature_TCPIP_AfdFuzzingFix__private_IsEnabledDeviceUsageNoInline
0x140037f47  mov     r9, [rsp+0E8h+arg_8]
0x140037f4f  test    eax, eax
0x140037f51  jz      short loc_140037F72
0x140037f53  test    byte ptr [rbx+5], 10h
0x140037f57  jz      short loc_140037F72
0x140037f59  test    [rbx+6], r14b
0x140037f5d  jz      short loc_140037F72
0x140037f5f  mov     r9d, 0C0000022h
0x140037f65  mov     esi, r9d
0x140037f68  mov     edx, 1B84h
0x140037f6d  jmp     loc_140038AB8
0x140037f72  mov     eax, [r9+10h]
0x140037f76  cmp     eax, 6
0x140037f79  jb      loc_140038AAB
0x140037f7f  mov     ecx, [r9+8]
0x140037f83  cmp     ecx, 2
0x140037f86  jb      loc_140038AAB
0x140037f8c  lea     r12d, [rax-4]
0x140037f90  mov     [rsp+0E8h+arg_18], r12d
0x140037f98  cmp     ecx, r12d
0x140037f9b  jb      loc_140038AAB
0x140037fa1  lea     rcx, [rbx+170h]
0x140037fa8  mov     [rsp+0E8h+var_58], rcx
0x140037fb0  mov     edx, 3
0x140037fb5  xor     eax, eax
0x140037fb7  lock cmpxchg [rcx], edx
0x140037fbb  jz      short loc_140037FC7
0x140037fbd  mov     edx, 1B5Ah
0x140037fc2  jmp     loc_140038AB0
0x140037fc7  mov     al, [rbx+2]
0x140037fca  sub     al, r14b
0x140037fcd  cmp     al, r14b
0x140037fd0  jbe     short loc_140037FF4
0x140037fd2  mov     edx, 1B5Bh
0x140037fd7  mov     r9d, 0C0000238h
0x140037fdd  mov     r8, rbx
0x140037fe0  mov     [rsp+0E8h+Irp], rdi
0x140037fe5  mov     esi, r9d
0x140037fe8  xor     ecx, ecx
0x140037fea  call    AFDETW_TRACEBIND
0x140037fef  jmp     loc_140038A6E
0x140037ff4  mov     eax, [rbx+8]
0x140037ff7  bt      eax, 8
0x140037ffb  jb      short loc_14003800A
0x140037ffd  cmp     [rbx+18h], rdi
0x140038001  jz      short loc_14003800A
0x140038003  mov     edx, 1B70h
0x140038008  jmp     short loc_140037FD7
0x14003800a  mov     [rsp+0E8h+var_50], rbx
0x140038012  mov     [rsp+0E8h+P], rdi
0x140038017  mov     rax, [rbx+28h]
0x14003801b  mov     [rsp+0E8h+var_88], rax
0x140038020  mov     [rsp+0E8h+var_48], rax
0x140038028  mov     [rsp+0E8h+var_98], edi
0x14003802c  cmp     [r13+40h], dil
0x140038030  jz      short loc_14003804C
0x140038032  mov     edx, [r9+10h]; Length
0x140038036  mov     r8d, 4; Alignment
0x14003803c  mov     rcx, [r9+20h]; Address
0x140038040  call    cs:__imp_ProbeForRead
0x140038047  nop     dword ptr [rax+rax+00h]
0x14003804c  mov     r15d, r12d
0x14003804f  mov     r8d, 6C646641h
0x140038055  mov     edx, r12d
0x140038058  mov     ecx, 61h ; 'a'
0x14003805d  call    cs:__imp_ExAllocatePool2
0x140038064  nop     dword ptr [rax+rax+00h]
0x140038069  mov     rcx, rax; void *
0x14003806c  mov     [rsp+0E8h+P], rax
0x140038071  mov     eax, [rbx+8]
0x140038074  mov     rdx, [rsp+0E8h+arg_8]
0x14003807c  mov     rsi, [rdx+20h]
0x140038080  bt      eax, 8
0x140038084  jb      loc_14003818B
0x14003808a  cmp     [r13+40h], dil
0x14003808e  jz      short loc_14003809F
0x140038090  mov     rcx, rsi
0x140038093  call    RtlReadULongFromUser
0x140038098  mov     rcx, [rsp+0E8h+P]
0x14003809d  jmp     short loc_1400380A1
0x14003809f  mov     eax, [rsi]
0x1400380a1  mov     [rsp+0E8h+arg_10], eax
0x1400380a8  mov     [rsp+0E8h+var_80], eax
0x1400380ac  lea     rdx, [rsi+4]; Src
0x1400380b0  mov     r8, r15; Size
0x1400380b3  cmp     [r13+40h], dil
0x1400380b7  jz      short loc_1400380C0
0x1400380b9  call    RtlCopyFromUser
0x1400380be  jmp     short loc_1400380C5
0x1400380c0  call    RtlCopyVolatileMemory
0x1400380c5  cmp     r12d, 4
0x1400380c9  jb      loc_140038157
0x1400380cf  mov     rsi, [rsp+0E8h+P]
0x1400380d4  cmp     [rsi], r14d
0x1400380d7  jnz     short loc_140038157
0x1400380d9  cmp     r15, 6
0x1400380dd  jnb     short loc_140038113
0x1400380df  mov     [rsp+0E8h+var_98], 0C000000Dh
0x1400380e7  mov     [rsp+0E8h+Irp], rdi
0x1400380ec  mov     r9d, [rsp+0E8h+var_98]
0x1400380f1  mov     r8, rbx
0x1400380f4  mov     edx, 1B6Bh
0x1400380f9  xor     ecx, ecx
0x1400380fb  call    AFDETW_TRACEBIND
0x140038100  mov     esi, [rsp+0E8h+var_98]
0x140038104  mov     r12, [rsp+0E8h+P]
0x140038109  mov     r15, [rsp+0E8h+var_88]
0x14003810e  jmp     loc_140038971
0x140038113  movzx   eax, word ptr [rsi+4]
0x140038117  add     eax, 8
0x14003811a  cmp     r12d, eax
0x14003811d  jnb     loc_140038283
0x140038123  mov     [rsp+0E8h+var_98], 0C000000Dh
0x14003812b  mov     [rsp+0E8h+Irp], rdi
0x140038130  mov     r9d, [rsp+0E8h+var_98]
0x140038135  mov     r8, rbx
0x140038138  mov     edx, 1B5Ch
0x14003813d  xor     ecx, ecx
0x14003813f  call    AFDETW_TRACEBIND
0x140038144  mov     esi, [rsp+0E8h+var_98]
0x140038148  mov     r12, [rsp+0E8h+P]
0x14003814d  mov     r15, [rsp+0E8h+var_88]
0x140038152  jmp     loc_140038971
0x140038157  mov     [rsp+0E8h+var_98], 0C000000Dh
0x14003815f  mov     [rsp+0E8h+Irp], rdi
0x140038164  mov     r9d, [rsp+0E8h+var_98]
0x140038169  mov     r8, rbx
0x14003816c  mov     edx, 1B6Ah
0x140038171  xor     ecx, ecx
0x140038173  call    AFDETW_TRACEBIND
0x140038178  mov     esi, [rsp+0E8h+var_98]
0x14003817c  mov     r12, [rsp+0E8h+P]
0x140038181  mov     r15, [rsp+0E8h+var_88]
0x140038186  jmp     loc_140038971
0x14003818b  cmp     r12d, 2
0x14003818f  jnb     short loc_1400381C5
0x140038191  mov     [rsp+0E8h+var_98], 0C0000141h
0x140038199  mov     [rsp+0E8h+Irp], rdi
0x14003819e  mov     r9d, [rsp+0E8h+var_98]
0x1400381a3  mov     r8, rbx
0x1400381a6  mov     edx, 1B6Ch
0x1400381ab  xor     ecx, ecx
0x1400381ad  call    AFDETW_TRACEBIND
0x1400381b2  mov     esi, [rsp+0E8h+var_98]
0x1400381b6  mov     r12, [rsp+0E8h+P]
0x1400381bb  mov     r15, [rsp+0E8h+var_88]
0x1400381c0  jmp     loc_140038971
0x1400381c5  cmp     [r13+40h], dil
0x1400381c9  jz      short loc_1400381DA
0x1400381cb  mov     rcx, rsi
0x1400381ce  call    RtlReadULongFromUser
0x1400381d3  mov     rcx, [rsp+0E8h+P]
0x1400381d8  jmp     short loc_1400381DC
0x1400381da  mov     eax, [rsi]
0x1400381dc  mov     [rsp+0E8h+arg_10], eax
0x1400381e3  mov     [rsp+0E8h+var_80], eax
0x1400381e7  lea     rdx, [rsi+4]; Src
0x1400381eb  mov     r8, r15; Size
0x1400381ee  cmp     [r13+40h], dil
0x1400381f2  jz      short loc_1400381FB
0x1400381f4  call    RtlCopyFromUser
0x1400381f9  jmp     short loc_140038200
0x1400381fb  call    RtlCopyVolatileMemory
0x140038200  mov     rsi, [rsp+0E8h+P]
0x140038205  movzx   ecx, word ptr [rsi]; af
0x140038208  cmp     cx, 23h ; '#'
0x14003820c  jb      short loc_140038242
0x14003820e  mov     [rsp+0E8h+var_98], 0C0000141h
0x140038216  mov     [rsp+0E8h+Irp], rdi
0x14003821b  mov     r9d, [rsp+0E8h+var_98]
0x140038220  mov     r8, rbx
0x140038223  mov     edx, 1B5Dh
0x140038228  xor     ecx, ecx
0x14003822a  call    AFDETW_TRACEBIND
0x14003822f  mov     esi, [rsp+0E8h+var_98]
0x140038233  mov     r12, [rsp+0E8h+P]
0x140038238  mov     r15, [rsp+0E8h+var_88]
0x14003823d  jmp     loc_140038971
0x140038242  call    SOCKADDR_SIZE
0x140038247  movzx   edx, al
0x14003824a  cmp     r12d, edx
0x14003824d  jnb     short loc_140038283
0x14003824f  mov     [rsp+0E8h+var_98], 0C0000141h
0x140038257  mov     [rsp+0E8h+Irp], rdi
0x14003825c  mov     r9d, [rsp+0E8h+var_98]
0x140038261  mov     r8, rbx
0x140038264  mov     edx, 1B5Eh
0x140038269  xor     ecx, ecx
0x14003826b  call    AFDETW_TRACEBIND
0x140038270  mov     esi, [rsp+0E8h+var_98]
0x140038274  mov     r12, [rsp+0E8h+P]
0x140038279  mov     r15, [rsp+0E8h+var_88]
0x14003827e  jmp     loc_140038971
0x140038283  mov     [rsp+0E8h+Irp], r13; Irp
0x140038288  mov     r9b, r14b; ChargeQuota
0x14003828b  xor     r8d, r8d; SecondaryBuffer
0x14003828e  mov     rax, [rsp+0E8h+arg_8]
0x140038296  mov     edx, [rax+8]; Length
0x140038299  mov     rcx, [r13+70h]; VirtualAddress
0x14003829d  call    cs:__imp_IoAllocateMdl
0x1400382a4  nop     dword ptr [rax+rax+00h]
0x1400382a9  test    rax, rax
0x1400382ac  jnz     short loc_1400382E2
0x1400382ae  mov     [rsp+0E8h+var_98], 0C000009Ah
0x1400382b6  mov     [rsp+0E8h+Irp], rdi
0x1400382bb  mov     r9d, [rsp+0E8h+var_98]
0x1400382c0  mov     r8, rbx
0x1400382c3  mov     edx, 1B5Fh
0x1400382c8  xor     ecx, ecx
0x1400382ca  call    AFDETW_TRACEBIND
0x1400382cf  mov     esi, [rsp+0E8h+var_98]
0x1400382d3  mov     r12, [rsp+0E8h+P]
0x1400382d8  mov     r15, [rsp+0E8h+var_88]
0x1400382dd  jmp     loc_140038971
0x1400382e2  mov     r8d, r14d; Operation
0x1400382e5  mov     dl, [r13+40h]; AccessMode
0x1400382e9  mov     rcx, [r13+8]; MemoryDescriptorList
0x1400382ed  call    cs:__imp_MmProbeAndLockPages
0x1400382f4  nop     dword ptr [rax+rax+00h]
0x1400382f9  mov     rcx, [r13+8]; MemoryDescriptorList
0x1400382fd  test    byte ptr [rcx+0Ah], 5
0x140038301  jz      short loc_140038309
0x140038303  mov     rax, [rcx+18h]
0x140038307  jmp     short loc_140038329
0x140038309  mov     [rsp+0E8h+Priority], 40000020h; Priority
0x140038311  mov     dword ptr [rsp+0E8h+Irp], edi; BugCheckOnFailure
0x140038315  xor     r9d, r9d; RequestedAddress
0x140038318  mov     r8d, r14d; CacheType
0x14003831b  xor     edx, edx; AccessMode
0x14003831d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140038324  nop     dword ptr [rax+rax+00h]
0x140038329  test    rax, rax
0x14003832c  jnz     short loc_140038362
0x14003832e  mov     [rsp+0E8h+var_98], 0C000009Ah
0x140038336  mov     [rsp+0E8h+Irp], rdi
0x14003833b  mov     r9d, [rsp+0E8h+var_98]
0x140038340  mov     r8, rbx
0x140038343  mov     edx, 1B60h
0x140038348  xor     ecx, ecx
0x14003834a  call    AFDETW_TRACEBIND
0x14003834f  mov     esi, [rsp+0E8h+var_98]
0x140038353  mov     r12, [rsp+0E8h+P]
0x140038358  mov     r15, [rsp+0E8h+var_88]
0x14003835d  jmp     loc_140038971
0x140038362  mov     eax, [rbx+8]
0x140038365  mov     edx, 100h
0x14003836a  test    edx, eax
0x14003836c  jz      short loc_1400383BB
0x14003836e  mov     [rbx+0F0h], rsi
0x140038375  mov     [rbx+0ECh], r12d
0x14003837c  mov     rax, [r13+0B8h]
  ... truncated ...
```
