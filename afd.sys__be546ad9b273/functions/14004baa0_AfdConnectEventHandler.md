# AfdConnectEventHandler

- ea: `0x14004baa0`
- end: `0x14004c520`
- name: `AfdConnectEventHandler`
- size: `2688`
- prototype: `__int64 __fastcall(__int64, ULONG, _OWORD *, int, __int64, int, __int64, __int64 *, PIRP *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002440`
- `0x14000271c`
- `0x140003670`
- `0x1400044fc`
- `0x140004848`
- `0x1400049b0`
- `0x140004c10`
- `0x140009fb0`
- `0x14000f390`
- `0x140013030`
- `0x140015990`
- `0x14001b5c4`
- `0x14001c708`
- `0x140044a30`
- `0x14004baa0`
- `0x14004dc7c`
- `0x14004e2f8`
- `0x14004f6d4`
- `0x1400504cc`
- `0x140072840`
- `0x140072880`
- `0x140072980`
- `0x1400930cc`
- `0x1400938a0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14004c2a9`
- `ntoskrnl!IoAllocateIrp` at `0x14004c2a9`
- `ntoskrnl!MmMapLockedPages` at `0x14004c0cf`
- `ntoskrnl!MmMapLockedPages` at `0x14004c10c`
- `ntoskrnl!MmMapLockedPages` at `0x14004c15c`
- `ntoskrnl!MmMapLockedPages` at `0x14004c0cf`
- `ntoskrnl!MmMapLockedPages` at `0x14004c10c`
- `ntoskrnl!MmMapLockedPages` at `0x14004c15c`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004c286`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004c286`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c266`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c457`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c266`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c457`
- `ntoskrnl!IoAllocateMdl` at `0x14004c080`
- `ntoskrnl!IoAllocateMdl` at `0x14004c080`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004bf9c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c22d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004bf9c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c22d`
- `ntoskrnl!IofCompleteRequest` at `0x14004bfb1`
- `ntoskrnl!IofCompleteRequest` at `0x14004c242`
- `ntoskrnl!IofCompleteRequest` at `0x14004bfb1`
- `ntoskrnl!IofCompleteRequest` at `0x14004c242`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004bf8c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c21d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004bf8c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c21d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc7b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bccd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd37`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd91`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bde0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c1c0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c3a2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc7b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bccd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd37`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd91`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bde0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c1c0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c3a2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bbfe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bca1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bd65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c192`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bbfe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bca1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bd65`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c192`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bef0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004bef0`

## pseudocode

```c
__int64 __fastcall AfdConnectEventHandler(
        __int64 a1,
        ULONG a2,
        _OWORD *a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 *a8,
        PIRP *a9)
{
  _OWORD *v9; // r12
  _OWORD *v11; // r14
  signed __int64 v13; // rax
  signed __int64 v14; // rcx
  signed __int64 v15; // rtt
  bool v16; // bl
  __int128 v17; // xmm0
  __int64 v18; // xmm1_8
  int v19; // ecx
  int v20; // esi
  ULONG v21; // ecx
  int v22; // edx
  __int64 v24; // rdx
  __int64 FreeConnection; // rax
  __int64 v26; // rsi
  void *v27; // rcx
  struct _DEVICE_OBJECT *v28; // r13
  signed int v29; // r14d
  unsigned int v30; // eax
  __int64 PoolPriority; // rax
  PIRP v32; // r14
  __int64 v33; // rcx
  volatile signed __int32 *v34; // rax
  signed __int64 v35; // rax
  bool v36; // cc
  signed __int64 v37; // rax
  PIRP v38; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _MDL *MdlAddress; // rcx
  int v41; // r13d
  struct _IO_STACK_LOCATION *v42; // r13
  ULONG LowPart; // edx
  PMDL v44; // rcx
  char *v45; // r13
  bool v46; // zf
  char *MappedSystemVa; // rax
  struct _IO_STACK_LOCATION *v48; // r9
  char *v49; // rdx
  PMDL v50; // rcx
  char *v51; // rax
  char *v52; // rax
  LARGE_INTEGER v53; // r13
  __int64 v54; // rcx
  PIRP v55; // rax
  struct _FILE_OBJECT *v56; // rcx
  struct _IO_STACK_LOCATION *v57; // rax
  struct _IO_STACK_LOCATION *v58; // rax
  size_t v59; // r8
  void *v60; // rdx
  char *v61; // rcx
  void *v62; // rcx
  struct _IO_STACK_LOCATION *v63; // rax
  struct _DEVICE_OBJECT *v64; // rcx
  __int64 v65; // rax
  int v66; // esi
  union _SLIST_HEADER *v67; // rcx
  USHORT DepthSList; // ax
  int v69; // r8d
  __int64 *v70; // rcx
  int v71; // edx
  KIRQL Irql[8]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v73; // [rsp+48h] [rbp-B8h]
  PIRP Irp; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STACK_LOCATION *v75; // [rsp+58h] [rbp-A8h]
  void *Src; // [rsp+60h] [rbp-A0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  char *v78; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER DefaultTimeout; // [rsp+88h] [rbp-78h]
  struct _FILE_OBJECT *v80; // [rsp+90h] [rbp-70h]
  char *v81; // [rsp+98h] [rbp-68h]
  __int64 Length; // [rsp+A0h] [rbp-60h]
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // [rsp+A8h] [rbp-58h]
  struct _DEVICE_OBJECT *v84; // [rsp+B0h] [rbp-50h]
  PIRP *v85; // [rsp+B8h] [rbp-48h]
  __int64 *v86; // [rsp+C0h] [rbp-40h]
  _OWORD v87[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v88; // [rsp+E8h] [rbp-18h]

  v9 = 0;
  v86 = a8;
  v11 = a3;
  v85 = a9;
  Src = a3;
  v88 = 0;
  v73 = a2;
  Irp = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v87, 0, sizeof(v87));
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
  {
    WPP_SF_q(1032, 12, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, a1);
    a2 = v73;
  }
  _m_prefetchw((const void *)(a1 + 64));
  v13 = *(_QWORD *)(a1 + 64);
  do
  {
    v14 = v13 + 1;
    if ( (unsigned __int64)(v13 + 1) <= 1 )
    {
      if ( v13 )
        __fastfail(0xEu);
      v71 = 6502;
      goto LABEL_124;
    }
    v15 = v13;
    v13 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v14, v13);
  }
  while ( v15 != v13 );
  if ( *(_BYTE *)(a1 + 2) == 6 || (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
  {
    AfdDereferenceEndpoint(a1);
    if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
      WPP_SF_q(776, 13, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, a1);
    v71 = 6503;
LABEL_124:
    AFDETW_TRACECONNECT_INDICATION(v14, v71, a1, -1073741670, (__int64)v11, 0);
    return 3221225626LL;
  }
  v16 = 0;
  if ( ((*(_DWORD *)(a1 + 8) & 0x400000) != 0 || (*(_DWORD *)(a1 + 8) & 0x200000) != 0)
    && a2 == 22
    && *((_WORD *)v11 + 3) == 2 )
  {
    v17 = *v11;
    *(_DWORD *)Irql = 34;
    v18 = *(_QWORD *)((char *)v11 + 14);
    v87[0] = v17;
    *(_QWORD *)((char *)v87 + 14) = v18;
    if ( (unsigned __int8)AfdTdi_TA4toTA6_InPlace(v87) )
    {
      v11 = v87;
      v16 = (*(_DWORD *)(a1 + 8) & 0x400000) != 0;
      v73 = *(_DWORD *)Irql;
      Src = v87;
    }
  }
  *(_QWORD *)Irql = 0;
  if ( *(_QWORD *)(a1 + 208) )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    if ( *(_QWORD *)(a1 + 208) )
    {
      *(_QWORD *)Irql = CopyConnectDataBuffers();
      v9 = *(_OWORD **)Irql;
      if ( !*(_QWORD *)Irql )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdDereferenceEndpoint(a1);
        if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
          WPP_SF_q(776, 14, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, a1);
        AFDETW_TRACECONNECT_INDICATION(v19, 6504, a1, -1073741670, (__int64)v11, 0);
        return 3221225626LL;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( a5 && a4 > 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    v20 = AfdSaveReceivedConnectData(Irql, 73803, a5, (unsigned int)a4);
    if ( v20 < 0 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      AfdDereferenceEndpoint(a1);
      v21 = *(_DWORD *)Irql;
      if ( *(_QWORD *)Irql )
        AfdFreeConnectDataBuffers(*(PVOID *)Irql);
      if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
        WPP_SF_q(776, 15, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, a1);
      v22 = 6504;
LABEL_29:
      AFDETW_TRACECONNECT_INDICATION(v21, v22, a1, v20, (__int64)v11, 0);
      return (unsigned int)v20;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = *(_OWORD **)Irql;
  }
  if ( a7 && a6 > 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    v20 = AfdSaveReceivedConnectData(Irql, 73807, a7, (unsigned int)a6);
    if ( v20 < 0 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      AfdDereferenceEndpoint(a1);
      v21 = *(_DWORD *)Irql;
      if ( *(_QWORD *)Irql )
        AfdFreeConnectDataBuffers(*(PVOID *)Irql);
      if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
        WPP_SF_q(776, 16, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, a1);
      v22 = 6505;
      goto LABEL_29;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = *(_OWORD **)Irql;
  }
  if ( v9 )
  {
    v9[8] = 0;
    v78 = (char *)(v9 + 8);
    v9[9] = 0;
    v9[10] = 0;
    *((_QWORD *)v9 + 17) = *(_QWORD *)v9;
    *((_DWORD *)v9 + 32) = *((_DWORD *)v9 + 2);
    *((_QWORD *)v9 + 19) = *((_QWORD *)v9 + 2);
    *((_DWORD *)v9 + 36) = *((_DWORD *)v9 + 6);
  }
  else
  {
    v78 = 0;
  }
  AFDETW_TRACECONNECT_INDICATION(v14, 6500, a1, 0, (__int64)v11, 0);
  while ( 2 )
  {
    LOBYTE(v24) = v16;
    FreeConnection = AfdGetFreeConnection(a1, v24, &Irp);
    v26 = FreeConnection;
    if ( FreeConnection )
    {
      if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1032, 17, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids, FreeConnection);
      v27 = *(void **)(v26 + 152);
      v28 = *(struct _DEVICE_OBJECT **)(v26 + 24);
      v29 = v73;
      v80 = *(struct _FILE_OBJECT **)(v26 + 16);
      v84 = v28;
      if ( v27 )
      {
        v30 = *(_DWORD *)(v26 + 160);
        if ( v30 < v73 )
        {
          if ( v30 > (unsigned int)AfdStandardAddressLength )
            ExFreePoolWithTag(v27, 0x52646641u);
          else
            PplFreeToLookasideList(PplAddressPool, v27);
          *(_QWORD *)(v26 + 152) = 0;
          goto LABEL_53;
        }
LABEL_69:
        *(_DWORD *)(v26 + 160) = v29;
        v38 = Irp;
        if ( Irp )
        {
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          v75 = CurrentStackLocation;
          if ( v73 > CurrentStackLocation->Parameters.Create.Options )
          {
            v41 = -1073741789;
          }
          else
          {
            MdlAddress = Irp->MdlAddress;
            Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
            DefaultTimeout = Parameters->DefaultTimeout;
            v41 = AfdMapMdlChain(MdlAddress);
            if ( v41 >= 0 )
            {
              v42 = v75;
              LowPart = v75->Parameters.Read.ByteOffset.LowPart;
              if ( !LowPart || IoAllocateMdl((char *)v38->UserBuffer + v75->Parameters.Read.Length, LowPart, 1u, 0, v38) )
              {
                v44 = v38->MdlAddress;
                if ( *(_BYTE *)(DefaultTimeout.QuadPart + 188) )
                {
                  v45 = (char *)Src;
                  v46 = (v44->MdlFlags & 5) == 0;
                  *(_WORD *)Irql = *((_WORD *)Src + 2) + 2;
                  if ( v46 )
                    MappedSystemVa = (char *)MmMapLockedPages(v44, 0);
                  else
                    MappedSystemVa = (char *)v44->MappedSystemVa;
                  v48 = v75;
                  v49 = &MappedSystemVa[v75->Parameters.Read.ByteOffset.LowPart + v75->Parameters.Create.Options];
                  Length = v75->Parameters.Read.Length;
                  v50 = v38->MdlAddress;
                  v81 = v49;
                  if ( (v50->MdlFlags & 5) != 0 )
                  {
                    v51 = (char *)v50->MappedSystemVa;
                  }
                  else
                  {
                    v51 = (char *)MmMapLockedPages(v50, 0);
                    v48 = v75;
                  }
                  RtlMoveVolatileMemory(
                    &v51[v48->Parameters.Read.ByteOffset.LowPart + v48->Parameters.Read.Length],
                    v45 + 6,
                    *(unsigned __int16 *)Irql);
                  *(_WORD *)&v81[Length - 2] = *(_WORD *)Irql;
                }
                else
                {
                  if ( (v44->MdlFlags & 5) != 0 )
                    v52 = (char *)v44->MappedSystemVa;
                  else
                    v52 = (char *)MmMapLockedPages(v44, 0);
                  RtlMoveVolatileMemory(
                    &v52[v42->Parameters.Read.ByteOffset.LowPart + v42->Parameters.Read.Length],
                    Src,
                    (int)v73);
                }
                v53 = DefaultTimeout;
                KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(DefaultTimeout.QuadPart + 56), &LockHandle);
                *(_QWORD *)(v26 + 8) = a1;
                v41 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))AfdSetupAcceptEndpoint)(
                        a1,
                        (LARGE_INTEGER)v53.QuadPart,
                        v26);
                if ( !v41 )
                {
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  v75->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)v38->MdlAddress;
                  v38->MdlAddress = 0;
                  v63 = v38->Tail.Overlay.CurrentStackLocation;
                  v63[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartSuperAccept;
                  v63[-1].Context = Parameters;
                  v64 = v84;
                  v63[-1].Control = -32;
                  v58 = v38->Tail.Overlay.CurrentStackLocation;
                  v58[-1].DeviceObject = v64;
                  v56 = v80;
                  goto LABEL_99;
                }
                KeReleaseInStackQueuedSpinLock(&LockHandle);
                *(_QWORD *)(v26 + 8) = 0;
              }
              else
              {
                v41 = -1073741670;
              }
            }
          }
          AFDETW_TRACEWAITLISTEN(1, 6209, a1, (unsigned int)v41);
          AFDETW_TRACEACCEPT_ERROR(v54, 6227, v38, (unsigned int)v41);
          AfdCleanupSuperAccept((__int64)v38, v41);
          if ( v38->Cancel )
          {
            Irql[0] = 0;
            IoAcquireCancelSpinLock(Irql);
            IoReleaseCancelSpinLock(Irql[0]);
          }
          IofCompleteRequest(v38, AfdPriorityBoost);
          if ( *(int *)(a1 + 176) >= 0 && v41 != -1073741670 && ExQueryDepthSList((PSLIST_HEADER)(a1 + 144)) < 0x7FFFu )
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), (PSLIST_ENTRY)(v26 + 176));
            continue;
          }
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 176));
          goto LABEL_66;
        }
        v55 = IoAllocateIrp(v28->StackSize, 0);
        Irp = v55;
        v38 = v55;
        if ( v55 )
        {
          v56 = v80;
          *(_QWORD *)(v26 + 8) = a1;
          v55->RequestorMode = 0;
          v55->Tail.Overlay.Thread = KeGetCurrentThread();
          v55->Tail.Overlay.OriginalFileObject = v56;
          v57 = v55->Tail.Overlay.CurrentStackLocation;
          v57[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartAccept;
          v57[-1].Context = (PVOID)v26;
          v57[-1].Control = -32;
          v58 = v38->Tail.Overlay.CurrentStackLocation;
          v58[-1].DeviceObject = v28;
LABEL_99:
          v59 = (int)v73;
          v60 = Src;
          v58[-1].FileObject = v56;
          v61 = v78;
          v58[-1].Parameters.QueryDirectory.FileName = 0;
          v58[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v61;
          *(_WORD *)&v58[-1].MajorFunction = 1295;
          --v38->CurrentLocation;
          --v38->Tail.Overlay.CurrentStackLocation;
          *v85 = v38;
          *v86 = v26;
          v62 = *(void **)(v26 + 152);
          *(_QWORD *)(v26 + 224) = v9;
          *(_WORD *)(v26 + 2) = 1;
          memmove(v62, v60, v59);
          AfdAddConnectedReference(v26);
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v26 + 48)) <= 1 )
            __fastfail(0xEu);
          _InterlockedAdd((volatile signed __int32 *)(a1 + 180), 1u);
          return 3221225494LL;
        }
      }
      else
      {
LABEL_53:
        if ( v29 > (unsigned int)AfdStandardAddressLength )
          PoolPriority = AfdAllocatePoolPriority(64, v29, 1382311489, 0);
        else
          PoolPriority = (__int64)AfdAllocateZeroedFromLookasideList((__int64)v27, v29);
        *(_QWORD *)(v26 + 152) = PoolPriority;
        if ( PoolPriority )
          goto LABEL_69;
        v32 = Irp;
        if ( Irp )
        {
          AFDETW_TRACEWAITLISTEN(1, 6208, *(_QWORD *)(v26 + 8), 3221225760LL);
          AFDETW_TRACEACCEPT_ERROR(v33, 6226, v32, 3221225760LL);
          AfdCleanupSuperAccept((__int64)v32, -1073741536);
          if ( v32->Cancel )
          {
            Irql[0] = 0;
            IoAcquireCancelSpinLock(Irql);
            IoReleaseCancelSpinLock(Irql[0]);
          }
          IofCompleteRequest(v32, AfdPriorityBoost);
        }
      }
      if ( (*(_DWORD *)(v26 + 4) & 2) != 0 && (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
        v34 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 280) + 48LL);
      else
        v34 = (volatile signed __int32 *)(a1 + 176);
      _InterlockedIncrement(v34);
LABEL_66:
      v35 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v26 + 48), 0xFFFFFFFFFFFFFFFFuLL);
      v36 = v35 <= 1;
      v37 = v35 - 1;
      if ( v36 )
      {
        if ( v37 )
          __fastfail(0xEu);
        AfdCloseConnection(v26);
      }
      continue;
    }
    break;
  }
  if ( v9 )
    AfdFreeConnectDataBuffers(v9);
  if ( *(int *)(a1 + 176) > 0 || (*(_DWORD *)(a1 + 8) & 0x400000) != 0 && *(int *)(*(_QWORD *)(a1 + 280) + 48LL) > 0 )
    AfdInitiateListenBacklogReplenish(a1);
  if ( (BYTE9(xmmword_1400875D0) & 1) != 0 )
  {
    if ( v16 )
    {
      v65 = *(_QWORD *)(a1 + 280);
      v66 = *(_DWORD *)(v65 + 48);
      v67 = (union _SLIST_HEADER *)(v65 + 32);
    }
    else
    {
      v66 = *(_DWORD *)(a1 + 176);
      v67 = (union _SLIST_HEADER *)(a1 + 144);
    }
    DepthSList = ExQueryDepthSList(v67);
    v70 = (__int64 *)"(DUAL) ";
    if ( !v16 )
      v70 = &qword_14007DC38;
    WPP_SF_qslll((_DWORD)v70, DepthSList, v69, a1, (__int64)v70, DepthSList, *(_DWORD *)(a1 + 180), v66);
  }
  AfdDereferenceEndpoint(a1);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004baa0  push    rbp
0x14004baa2  push    rbx
0x14004baa3  push    rsi
0x14004baa4  push    rdi
0x14004baa5  push    r12
0x14004baa7  push    r13
0x14004baa9  push    r14
0x14004baab  push    r15
0x14004baad  lea     rbp, [rsp-8]
0x14004bab2  sub     rsp, 108h
0x14004bab9  mov     rax, cs:__security_cookie
0x14004bac0  xor     rax, rsp
0x14004bac3  mov     [rbp+40h+var_50], rax
0x14004bac7  mov     rax, [rbp+40h+arg_38]
0x14004bace  xor     r12d, r12d
0x14004bad1  mov     r15, [rbp+40h+arg_20]
0x14004bad5  xorps   xmm1, xmm1
0x14004bad8  mov     r13, [rbp+40h+arg_30]
0x14004badf  xorps   xmm0, xmm0
0x14004bae2  mov     [rbp+40h+var_80], rax
0x14004bae6  mov     esi, r9d
0x14004bae9  mov     rax, [rbp+40h+arg_40]
0x14004baf0  mov     r14, r8
0x14004baf3  mov     [rbp+40h+var_88], rax
0x14004baf7  mov     rdi, rcx
0x14004bafa  xor     eax, eax
0x14004bafc  mov     [rsp+140h+Src], r8
0x14004bb01  mov     qword ptr [rsp+140h+LockHandle.OldIrql], rax
0x14004bb06  mov     [rbp+40h+var_58], ax
0x14004bb0a  mov     [rsp+140h+var_F8], edx
0x14004bb0e  mov     [rsp+140h+Irp], r12
0x14004bb13  movups  xmmword ptr [rsp+140h+LockHandle.LockQueue.Next], xmm0
0x14004bb18  movups  [rbp+40h+var_78], xmm1
0x14004bb1c  movups  [rbp+40h+var_68], xmm1
0x14004bb20  lea     ebx, [rax+1]
0x14004bb23  test    byte ptr cs:xmmword_1400875E0+1, bl
0x14004bb29  jz      short loc_14004BB46
0x14004bb2b  lea     edx, [rax+0Ch]
0x14004bb2e  mov     ecx, 408h
0x14004bb33  mov     r9, rdi
0x14004bb36  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004bb3d  call    WPP_SF_q
0x14004bb42  mov     edx, [rsp+140h+var_F8]
0x14004bb46  prefetchw byte ptr [rdi+40h]
0x14004bb4a  mov     rax, [rdi+40h]
0x14004bb4e  lea     rcx, [rax+1]
0x14004bb52  cmp     rcx, rbx
0x14004bb55  jbe     loc_14004C4D3
0x14004bb5b  lock cmpxchg [rdi+40h], rcx
0x14004bb61  jnz     short loc_14004BB4E
0x14004bb63  cmp     byte ptr [rdi+2], 6
0x14004bb67  jz      loc_14004C4A3
0x14004bb6d  mov     eax, [rdi+8]
0x14004bb70  bt      eax, 0Bh
0x14004bb74  jb      loc_14004C4A3
0x14004bb7a  mov     eax, [rdi+8]
0x14004bb7d  mov     bl, r12b
0x14004bb80  bt      eax, 16h
0x14004bb84  jb      short loc_14004BB8F
0x14004bb86  mov     eax, [rdi+8]
0x14004bb89  bt      eax, 15h
0x14004bb8d  jnb     short loc_14004BBE3
0x14004bb8f  cmp     edx, 16h
0x14004bb92  jnz     short loc_14004BBE3
0x14004bb94  cmp     word ptr [r14+6], 2
0x14004bb9a  jnz     short loc_14004BBE3
0x14004bb9c  movups  xmm0, xmmword ptr [r14]
0x14004bba0  lea     rdx, [rsp+140h+Irql]
0x14004bba5  mov     dword ptr [rsp+140h+Irql], 22h ; '"'
0x14004bbad  movsd   xmm1, qword ptr [r14+0Eh]
0x14004bbb3  lea     rcx, [rbp+40h+var_78]; void *
0x14004bbb7  movups  [rbp+40h+var_78], xmm0
0x14004bbbb  movsd   qword ptr [rbp+40h+var_78+0Eh], xmm1
0x14004bbc0  call    AfdTdi_TA4toTA6_InPlace
0x14004bbc5  test    al, al
0x14004bbc7  jz      short loc_14004BBE3
0x14004bbc9  mov     ebx, [rdi+8]
0x14004bbcc  lea     r14, [rbp+40h+var_78]
0x14004bbd0  mov     eax, dword ptr [rsp+140h+Irql]
0x14004bbd4  shr     ebx, 16h
0x14004bbd7  and     bl, 1
0x14004bbda  mov     [rsp+140h+var_F8], eax
0x14004bbde  mov     [rsp+140h+Src], r14
0x14004bbe3  mov     qword ptr [rsp+140h+Irql], r12
0x14004bbe8  cmp     [rdi+0D0h], r12
0x14004bbef  jz      loc_14004BC87
0x14004bbf5  lea     rcx, [rdi+38h]; SpinLock
0x14004bbf9  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bbfe  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bc05  nop     dword ptr [rax+rax+00h]
0x14004bc0a  mov     rcx, [rdi+0D0h]
0x14004bc11  test    rcx, rcx
0x14004bc14  jz      short loc_14004BC76
0x14004bc16  call    CopyConnectDataBuffers
0x14004bc1b  mov     qword ptr [rsp+140h+Irql], rax
0x14004bc20  mov     r12, rax
0x14004bc23  test    rax, rax
0x14004bc26  jnz     short loc_14004BC76
0x14004bc28  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bc2d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bc34  nop     dword ptr [rax+rax+00h]
0x14004bc39  mov     rcx, rdi
0x14004bc3c  call    AfdDereferenceEndpoint
0x14004bc41  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bc48  jz      short loc_14004BC63
0x14004bc4a  lea     edx, [r12+0Eh]
0x14004bc4f  mov     ecx, 308h
0x14004bc54  mov     r9, rdi
0x14004bc57  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004bc5e  call    WPP_SF_q
0x14004bc63  mov     [rsp+140h+var_118], 0
0x14004bc6c  mov     edx, 1968h
0x14004bc71  jmp     loc_14004C4E6
0x14004bc76  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bc7b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bc82  nop     dword ptr [rax+rax+00h]
0x14004bc87  test    r15, r15
0x14004bc8a  jz      loc_14004BD48
0x14004bc90  test    esi, esi
0x14004bc92  jle     loc_14004BD48
0x14004bc98  lea     rcx, [rdi+38h]; SpinLock
0x14004bc9c  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bca1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bca8  nop     dword ptr [rax+rax+00h]
0x14004bcad  mov     r9d, esi
0x14004bcb0  lea     rcx, [rsp+140h+Irql]
0x14004bcb5  mov     r8, r15
0x14004bcb8  mov     edx, 1204Bh
0x14004bcbd  call    AfdSaveReceivedConnectData
0x14004bcc2  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bcc7  mov     esi, eax
0x14004bcc9  test    eax, eax
0x14004bccb  jns     short loc_14004BD37
0x14004bccd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bcd4  nop     dword ptr [rax+rax+00h]
0x14004bcd9  mov     rcx, rdi
0x14004bcdc  call    AfdDereferenceEndpoint
0x14004bce1  mov     rcx, qword ptr [rsp+140h+Irql]; P
0x14004bce6  test    rcx, rcx
0x14004bce9  jz      short loc_14004BCF0
0x14004bceb  call    AfdFreeConnectDataBuffers
0x14004bcf0  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bcf7  jz      short loc_14004BD12
0x14004bcf9  mov     edx, 0Fh
0x14004bcfe  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004bd05  mov     ecx, 308h
0x14004bd0a  mov     r9, rdi
0x14004bd0d  call    WPP_SF_q
0x14004bd12  mov     edx, 1968h
0x14004bd17  mov     [rsp+140h+var_118], 0
0x14004bd20  mov     r8, rdi
0x14004bd23  mov     r9d, esi
0x14004bd26  mov     [rsp+140h+var_120], r14
0x14004bd2b  call    AFDETW_TRACECONNECT_INDICATION
0x14004bd30  mov     eax, esi
0x14004bd32  jmp     loc_14004C4FF
0x14004bd37  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bd3e  nop     dword ptr [rax+rax+00h]
0x14004bd43  mov     r12, qword ptr [rsp+140h+Irql]
0x14004bd48  test    r13, r13
0x14004bd4b  jz      loc_14004BDF1
0x14004bd51  mov     esi, [rbp+40h+arg_28]
0x14004bd54  test    esi, esi
0x14004bd56  jle     loc_14004BDF1
0x14004bd5c  lea     rcx, [rdi+38h]; SpinLock
0x14004bd60  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bd65  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bd6c  nop     dword ptr [rax+rax+00h]
0x14004bd71  mov     r9d, esi
0x14004bd74  lea     rcx, [rsp+140h+Irql]
0x14004bd79  mov     r8, r13
0x14004bd7c  mov     edx, 1204Fh
0x14004bd81  call    AfdSaveReceivedConnectData
0x14004bd86  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bd8b  mov     esi, eax
0x14004bd8d  test    eax, eax
0x14004bd8f  jns     short loc_14004BDE0
0x14004bd91  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bd98  nop     dword ptr [rax+rax+00h]
0x14004bd9d  mov     rcx, rdi
0x14004bda0  call    AfdDereferenceEndpoint
0x14004bda5  mov     rcx, qword ptr [rsp+140h+Irql]; P
0x14004bdaa  test    rcx, rcx
0x14004bdad  jz      short loc_14004BDB4
0x14004bdaf  call    AfdFreeConnectDataBuffers
0x14004bdb4  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bdbb  jz      short loc_14004BDD6
0x14004bdbd  mov     edx, 10h
0x14004bdc2  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004bdc9  mov     ecx, 308h
0x14004bdce  mov     r9, rdi
0x14004bdd1  call    WPP_SF_q
0x14004bdd6  mov     edx, 1969h
0x14004bddb  jmp     loc_14004BD17
0x14004bde0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bde7  nop     dword ptr [rax+rax+00h]
0x14004bdec  mov     r12, qword ptr [rsp+140h+Irql]
0x14004bdf1  test    r12, r12
0x14004bdf4  jz      short loc_14004BE39
0x14004bdf6  lea     r13, [r12+80h]
0x14004bdfe  xorps   xmm0, xmm0
0x14004be01  movups  xmmword ptr [r13+0], xmm0
0x14004be06  mov     [rbp+40h+var_C0], r13
0x14004be0a  movups  xmmword ptr [r13+10h], xmm0
0x14004be0f  movups  xmmword ptr [r13+20h], xmm0
0x14004be14  mov     rax, [r12]
0x14004be18  mov     [r13+8], rax
0x14004be1c  mov     eax, [r12+8]
0x14004be21  mov     [r13+0], eax
0x14004be25  mov     rax, [r12+10h]
0x14004be2a  mov     [r13+18h], rax
0x14004be2e  mov     eax, [r12+18h]
0x14004be33  mov     [r13+10h], eax
0x14004be37  jmp     short loc_14004BE41
0x14004be39  mov     [rbp+40h+var_C0], 0
0x14004be41  mov     [rsp+140h+var_118], 0
0x14004be4a  xor     r9d, r9d
0x14004be4d  mov     r8, rdi
0x14004be50  mov     [rsp+140h+var_120], r14
0x14004be55  mov     edx, 1964h
0x14004be5a  call    AFDETW_TRACECONNECT_INDICATION
0x14004be5f  mov     r15d, 0C000009Ah
0x14004be65  lea     r8, [rsp+140h+Irp]
0x14004be6a  mov     dl, bl
0x14004be6c  mov     rcx, rdi
0x14004be6f  call    AfdGetFreeConnection
0x14004be74  mov     rsi, rax
0x14004be77  test    rax, rax
0x14004be7a  jz      loc_14004C3F9
0x14004be80  test    byte ptr cs:xmmword_1400875E0+1, 1
0x14004be87  jz      short loc_14004BEA2
0x14004be89  mov     edx, 11h
0x14004be8e  lea     r8, WPP_41127cc3b3d83cc37a8c8bbc892e71ef_Traceguids
0x14004be95  mov     ecx, 408h
0x14004be9a  mov     r9, rax
0x14004be9d  call    WPP_SF_q
0x14004bea2  mov     rcx, [rsi+98h]; P
0x14004bea9  mov     rax, [rsi+10h]
0x14004bead  mov     r13, [rsi+18h]
0x14004beb1  mov     r14d, [rsp+140h+var_F8]
0x14004beb6  mov     [rbp+40h+var_B0], rax
0x14004beba  mov     [rbp+40h+var_90], r13
0x14004bebe  test    rcx, rcx
0x14004bec1  jz      short loc_14004BF07
0x14004bec3  mov     eax, [rsi+0A0h]
0x14004bec9  cmp     eax, r14d
0x14004becc  jnb     loc_14004C00E
0x14004bed2  cmp     eax, cs:AfdStandardAddressLength
0x14004bed8  ja      short loc_14004BEEB
0x14004beda  mov     rdx, rcx
0x14004bedd  mov     rcx, cs:PplAddressPool
0x14004bee4  call    PplFreeToLookasideList
0x14004bee9  jmp     short loc_14004BEFC
0x14004beeb  mov     edx, 52646641h; Tag
0x14004bef0  call    cs:__imp_ExFreePoolWithTag
0x14004bef7  nop     dword ptr [rax+rax+00h]
0x14004befc  mov     qword ptr [rsi+98h], 0
0x14004bf07  cmp     r14d, cs:AfdStandardAddressLength
0x14004bf0e  movsxd  rdx, r14d
0x14004bf11  ja      short loc_14004BF1A
0x14004bf13  call    AfdAllocateZeroedFromLookasideList
0x14004bf18  jmp     short loc_14004BF2C
0x14004bf1a  xor     r9d, r9d
0x14004bf1d  mov     r8d, 52646641h
0x14004bf23  lea     ecx, [r9+40h]
0x14004bf27  call    AfdAllocatePoolPriority
0x14004bf2c  mov     [rsi+98h], rax
0x14004bf33  test    rax, rax
0x14004bf36  jnz     loc_14004C00E
0x14004bf3c  mov     r14, [rsp+140h+Irp]
0x14004bf41  test    r14, r14
0x14004bf44  jz      short loc_14004BFBD
0x14004bf46  mov     r8, [rsi+8]
0x14004bf4a  lea     ecx, [rax+1]
0x14004bf4d  mov     r13d, 0C0000120h
0x14004bf53  mov     edx, 1840h
0x14004bf58  mov     r9d, r13d
0x14004bf5b  call    AFDETW_TRACEWAITLISTEN
0x14004bf60  mov     r9d, r13d
0x14004bf63  mov     r8, r14
0x14004bf66  mov     edx, 1852h
0x14004bf6b  call    AFDETW_TRACEACCEPT_ERROR
0x14004bf70  mov     edx, r13d
0x14004bf73  mov     rcx, r14
0x14004bf76  call    AfdCleanupSuperAccept
0x14004bf7b  cmp     byte ptr [r14+44h], 0
0x14004bf80  jz      short loc_14004BFA8
0x14004bf82  lea     rcx, [rsp+140h+Irql]; Irql
0x14004bf87  mov     [rsp+140h+Irql], 0
0x14004bf8c  call    cs:__imp_IoAcquireCancelSpinLock
0x14004bf93  nop     dword ptr [rax+rax+00h]
0x14004bf98  mov     cl, [rsp+140h+Irql]; Irql
0x14004bf9c  call    cs:__imp_IoReleaseCancelSpinLock
0x14004bfa3  nop     dword ptr [rax+rax+00h]
0x14004bfa8  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004bfae  mov     rcx, r14; Irp
0x14004bfb1  call    cs:__imp_IofCompleteRequest
0x14004bfb8  nop     dword ptr [rax+rax+00h]
0x14004bfbd  mov     eax, [rsi+4]
0x14004bfc0  test    al, 2
  ... truncated ...
```
