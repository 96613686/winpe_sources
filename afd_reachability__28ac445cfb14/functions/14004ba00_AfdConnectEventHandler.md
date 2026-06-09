# AfdConnectEventHandler

- ea: `0x14004ba00`
- end: `0x14004c480`
- name: `AfdConnectEventHandler`
- size: `2688`
- prototype: ``
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
- `0x140044a10`
- `0x14004ba00`
- `0x14004dbdc`
- `0x14004e258`
- `0x14004f634`
- `0x14005042c`
- `0x1400726a0`
- `0x1400726e0`
- `0x140072800`
- `0x1400930cc`
- `0x1400938a0`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14004c209`
- `ntoskrnl!IoAllocateIrp` at `0x14004c209`
- `ntoskrnl!MmMapLockedPages` at `0x14004c02f`
- `ntoskrnl!MmMapLockedPages` at `0x14004c06c`
- `ntoskrnl!MmMapLockedPages` at `0x14004c0bc`
- `ntoskrnl!MmMapLockedPages` at `0x14004c02f`
- `ntoskrnl!MmMapLockedPages` at `0x14004c06c`
- `ntoskrnl!MmMapLockedPages` at `0x14004c0bc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004c1e6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004c1e6`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c1c6`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c3b7`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c1c6`
- `ntoskrnl!ExQueryDepthSList` at `0x14004c3b7`
- `ntoskrnl!IoAllocateMdl` at `0x14004bfe0`
- `ntoskrnl!IoAllocateMdl` at `0x14004bfe0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004befc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c18d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004befc`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14004c18d`
- `ntoskrnl!IofCompleteRequest` at `0x14004bf11`
- `ntoskrnl!IofCompleteRequest` at `0x14004c1a2`
- `ntoskrnl!IofCompleteRequest` at `0x14004bf11`
- `ntoskrnl!IofCompleteRequest` at `0x14004c1a2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004beec`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c17d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004beec`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14004c17d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bb8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bbdb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc97`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bcf1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd40`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c120`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c302`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bb8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bbdb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bc97`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bcf1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004bd40`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c120`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004c302`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bb5e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bc01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bcc5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c0f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bb5e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bc01`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004bcc5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004c0f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004be50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004be50`

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
        PSLIST_ENTRY *a8,
        PIRP *a9)
{
  _OWORD *v9; // r12
  _OWORD *v11; // r14
  signed __int64 v13; // rax
  signed __int64 v14; // rcx
  signed __int64 v15; // rtt
  char v16; // bl
  __int128 v17; // xmm0
  __int64 v18; // xmm1_8
  int v19; // ecx
  int v20; // esi
  ULONG v21; // ecx
  int v22; // edx
  PSLIST_ENTRY FreeConnection; // rax
  PSLIST_ENTRY v25; // rsi
  void *v26; // rcx
  struct _DEVICE_OBJECT *v27; // r13
  signed int v28; // r14d
  unsigned int v29; // eax
  __int64 PoolPriority; // rax
  PIRP v31; // r14
  __int64 v32; // rcx
  volatile signed __int32 *v33; // rax
  signed __int64 v34; // rax
  bool v35; // cc
  signed __int64 v36; // rax
  PIRP v37; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _MDL *MdlAddress; // rcx
  unsigned int v40; // r13d
  struct _IO_STACK_LOCATION *v41; // r13
  ULONG LowPart; // edx
  PMDL v43; // rcx
  char *v44; // r13
  bool v45; // zf
  char *MappedSystemVa; // rax
  struct _IO_STACK_LOCATION *v47; // r9
  char *v48; // rdx
  PMDL v49; // rcx
  char *v50; // rax
  char *v51; // rax
  LARGE_INTEGER v52; // r13
  __int64 v53; // rcx
  PIRP v54; // rax
  struct _FILE_OBJECT *v55; // rcx
  struct _IO_STACK_LOCATION *v56; // rax
  struct _IO_STACK_LOCATION *v57; // rax
  size_t v58; // r8
  void *v59; // rdx
  char *v60; // rcx
  void *v61; // rcx
  struct _IO_STACK_LOCATION *v62; // rax
  struct _DEVICE_OBJECT *v63; // rcx
  __int64 v64; // rax
  int v65; // esi
  union _SLIST_HEADER *v66; // rcx
  USHORT DepthSList; // ax
  int v68; // r8d
  __int64 *v69; // rcx
  int v70; // edx
  KIRQL Irql[8]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v72; // [rsp+48h] [rbp-B8h]
  PIRP Irp; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STACK_LOCATION *v74; // [rsp+58h] [rbp-A8h]
  void *Src; // [rsp+60h] [rbp-A0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  char *v77; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER DefaultTimeout; // [rsp+88h] [rbp-78h]
  struct _FILE_OBJECT *Next; // [rsp+90h] [rbp-70h]
  char *v80; // [rsp+98h] [rbp-68h]
  __int64 Length; // [rsp+A0h] [rbp-60h]
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // [rsp+A8h] [rbp-58h]
  struct _DEVICE_OBJECT *v83; // [rsp+B0h] [rbp-50h]
  PIRP *v84; // [rsp+B8h] [rbp-48h]
  PSLIST_ENTRY *v85; // [rsp+C0h] [rbp-40h]
  _OWORD v86[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v87; // [rsp+E8h] [rbp-18h]

  v9 = 0;
  v85 = a8;
  v11 = a3;
  v84 = a9;
  Src = a3;
  v87 = 0;
  v72 = a2;
  Irp = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v86, 0, sizeof(v86));
  if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
  {
    WPP_SF_q(1032, 12, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
    a2 = v72;
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
      v70 = 6502;
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
      WPP_SF_q(776, 13, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
    v70 = 6503;
LABEL_124:
    AFDETW_TRACECONNECT_INDICATION(v14, v70, a1, -1073741670, (__int64)v11, 0);
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
    v86[0] = v17;
    *(_QWORD *)((char *)v86 + 14) = v18;
    if ( (unsigned __int8)AfdTdi_TA4toTA6_InPlace(v86) )
    {
      v11 = v86;
      v16 = (*(_DWORD *)(a1 + 8) & 0x400000) != 0;
      v72 = *(_DWORD *)Irql;
      Src = v86;
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
          WPP_SF_q(776, 14, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
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
        WPP_SF_q(776, 15, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
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
        WPP_SF_q(776, 16, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, a1);
      v22 = 6505;
      goto LABEL_29;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v9 = *(_OWORD **)Irql;
  }
  if ( v9 )
  {
    v9[8] = 0;
    v77 = (char *)(v9 + 8);
    v9[9] = 0;
    v9[10] = 0;
    *((_QWORD *)v9 + 17) = *(_QWORD *)v9;
    *((_DWORD *)v9 + 32) = *((_DWORD *)v9 + 2);
    *((_QWORD *)v9 + 19) = *((_QWORD *)v9 + 2);
    *((_DWORD *)v9 + 36) = *((_DWORD *)v9 + 6);
  }
  else
  {
    v77 = 0;
  }
  AFDETW_TRACECONNECT_INDICATION(v14, 6500, a1, 0, (__int64)v11, 0);
  while ( 2 )
  {
    FreeConnection = AfdGetFreeConnection(a1, v16, (__int64 *)&Irp);
    v25 = FreeConnection;
    if ( FreeConnection )
    {
      if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1032, 17, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids, FreeConnection);
      v26 = (void *)*((_QWORD *)&v25[9].Next + 1);
      v27 = (struct _DEVICE_OBJECT *)*((_QWORD *)&v25[1].Next + 1);
      v28 = v72;
      Next = (struct _FILE_OBJECT *)v25[1].Next;
      v83 = v27;
      if ( v26 )
      {
        v29 = (unsigned int)v25[10].Next;
        if ( v29 < v72 )
        {
          if ( v29 > (unsigned int)AfdStandardAddressLength )
            ExFreePoolWithTag(v26, 0x52646641u);
          else
            PplFreeToLookasideList(PplAddressPool, v26);
          *((_QWORD *)&v25[9].Next + 1) = 0;
          goto LABEL_53;
        }
LABEL_69:
        LODWORD(v25[10].Next) = v28;
        v37 = Irp;
        if ( Irp )
        {
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          v74 = CurrentStackLocation;
          if ( v72 > CurrentStackLocation->Parameters.Create.Options )
          {
            v40 = -1073741789;
          }
          else
          {
            MdlAddress = Irp->MdlAddress;
            Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
            DefaultTimeout = Parameters->DefaultTimeout;
            v40 = AfdMapMdlChain(MdlAddress);
            if ( (v40 & 0x80000000) == 0 )
            {
              v41 = v74;
              LowPart = v74->Parameters.Read.ByteOffset.LowPart;
              if ( !LowPart || IoAllocateMdl((char *)v37->UserBuffer + v74->Parameters.Read.Length, LowPart, 1u, 0, v37) )
              {
                v43 = v37->MdlAddress;
                if ( *(_BYTE *)(DefaultTimeout.QuadPart + 188) )
                {
                  v44 = (char *)Src;
                  v45 = (v43->MdlFlags & 5) == 0;
                  *(_WORD *)Irql = *((_WORD *)Src + 2) + 2;
                  if ( v45 )
                    MappedSystemVa = (char *)MmMapLockedPages(v43, 0);
                  else
                    MappedSystemVa = (char *)v43->MappedSystemVa;
                  v47 = v74;
                  v48 = &MappedSystemVa[v74->Parameters.Read.ByteOffset.LowPart + v74->Parameters.Create.Options];
                  Length = v74->Parameters.Read.Length;
                  v49 = v37->MdlAddress;
                  v80 = v48;
                  if ( (v49->MdlFlags & 5) != 0 )
                  {
                    v50 = (char *)v49->MappedSystemVa;
                  }
                  else
                  {
                    v50 = (char *)MmMapLockedPages(v49, 0);
                    v47 = v74;
                  }
                  RtlMoveVolatileMemory(
                    &v50[v47->Parameters.Read.ByteOffset.LowPart + v47->Parameters.Read.Length],
                    v44 + 6,
                    *(unsigned __int16 *)Irql);
                  *(_WORD *)&v80[Length - 2] = *(_WORD *)Irql;
                }
                else
                {
                  if ( (v43->MdlFlags & 5) != 0 )
                    v51 = (char *)v43->MappedSystemVa;
                  else
                    v51 = (char *)MmMapLockedPages(v43, 0);
                  RtlMoveVolatileMemory(
                    &v51[v41->Parameters.Read.ByteOffset.LowPart + v41->Parameters.Read.Length],
                    Src,
                    (int)v72);
                }
                v52 = DefaultTimeout;
                KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(DefaultTimeout.QuadPart + 56), &LockHandle);
                *((_QWORD *)&v25->Next + 1) = a1;
                v40 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))AfdSetupAcceptEndpoint)(
                        a1,
                        (LARGE_INTEGER)v52.QuadPart,
                        v25);
                if ( !v40 )
                {
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  v74->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)v37->MdlAddress;
                  v37->MdlAddress = 0;
                  v62 = v37->Tail.Overlay.CurrentStackLocation;
                  v62[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartSuperAccept;
                  v62[-1].Context = Parameters;
                  v63 = v83;
                  v62[-1].Control = -32;
                  v57 = v37->Tail.Overlay.CurrentStackLocation;
                  v57[-1].DeviceObject = v63;
                  v55 = Next;
                  goto LABEL_99;
                }
                KeReleaseInStackQueuedSpinLock(&LockHandle);
                *((_QWORD *)&v25->Next + 1) = 0;
              }
              else
              {
                v40 = -1073741670;
              }
            }
          }
          AFDETW_TRACEWAITLISTEN(1, 6209, a1, v40);
          AFDETW_TRACEACCEPT_ERROR(v53, 6227, v37, v40);
          AfdCleanupSuperAccept(v37, v40);
          if ( v37->Cancel )
          {
            Irql[0] = 0;
            IoAcquireCancelSpinLock(Irql);
            IoReleaseCancelSpinLock(Irql[0]);
          }
          IofCompleteRequest(v37, AfdPriorityBoost);
          if ( *(int *)(a1 + 176) >= 0 && v40 != -1073741670 && ExQueryDepthSList((PSLIST_HEADER)(a1 + 144)) < 0x7FFFu )
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), v25 + 11);
            continue;
          }
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 176));
          goto LABEL_66;
        }
        v54 = IoAllocateIrp(v27->StackSize, 0);
        Irp = v54;
        v37 = v54;
        if ( v54 )
        {
          v55 = Next;
          *((_QWORD *)&v25->Next + 1) = a1;
          v54->RequestorMode = 0;
          v54->Tail.Overlay.Thread = KeGetCurrentThread();
          v54->Tail.Overlay.OriginalFileObject = v55;
          v56 = v54->Tail.Overlay.CurrentStackLocation;
          v56[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartAccept;
          v56[-1].Context = v25;
          v56[-1].Control = -32;
          v57 = v37->Tail.Overlay.CurrentStackLocation;
          v57[-1].DeviceObject = v27;
LABEL_99:
          v58 = (int)v72;
          v59 = Src;
          v57[-1].FileObject = v55;
          v60 = v77;
          v57[-1].Parameters.QueryDirectory.FileName = 0;
          v57[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v60;
          *(_WORD *)&v57[-1].MajorFunction = 1295;
          --v37->CurrentLocation;
          --v37->Tail.Overlay.CurrentStackLocation;
          *v84 = v37;
          *v85 = v25;
          v61 = (void *)*((_QWORD *)&v25[9].Next + 1);
          v25[14].Next = (struct _SLIST_ENTRY *)v9;
          WORD1(v25->Next) = 1;
          memmove(v61, v59, v58);
          AfdAddConnectedReference(v25);
          if ( _InterlockedIncrement64((volatile signed __int64 *)&v25[3]) <= 1 )
            __fastfail(0xEu);
          _InterlockedAdd((volatile signed __int32 *)(a1 + 180), 1u);
          return 3221225494LL;
        }
      }
      else
      {
LABEL_53:
        if ( v28 > (unsigned int)AfdStandardAddressLength )
          PoolPriority = AfdAllocatePoolPriority(64, v28, 1382311489, 0);
        else
          PoolPriority = AfdAllocateZeroedFromLookasideList(v26, v28);
        *((_QWORD *)&v25[9].Next + 1) = PoolPriority;
        if ( PoolPriority )
          goto LABEL_69;
        v31 = Irp;
        if ( Irp )
        {
          AFDETW_TRACEWAITLISTEN(1, 6208, *((_QWORD *)&v25->Next + 1), 3221225760LL);
          AFDETW_TRACEACCEPT_ERROR(v32, 6226, v31, 3221225760LL);
          AfdCleanupSuperAccept(v31, 3221225760LL);
          if ( v31->Cancel )
          {
            Irql[0] = 0;
            IoAcquireCancelSpinLock(Irql);
            IoReleaseCancelSpinLock(Irql[0]);
          }
          IofCompleteRequest(v31, AfdPriorityBoost);
        }
      }
      if ( (HIDWORD(v25->Next) & 2) != 0 && (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
        v33 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 280) + 48LL);
      else
        v33 = (volatile signed __int32 *)(a1 + 176);
      _InterlockedIncrement(v33);
LABEL_66:
      v34 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v25[3], 0xFFFFFFFFFFFFFFFFuLL);
      v35 = v34 <= 1;
      v36 = v34 - 1;
      if ( v35 )
      {
        if ( v36 )
          __fastfail(0xEu);
        AfdCloseConnection(v25);
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
      v64 = *(_QWORD *)(a1 + 280);
      v65 = *(_DWORD *)(v64 + 48);
      v66 = (union _SLIST_HEADER *)(v64 + 32);
    }
    else
    {
      v65 = *(_DWORD *)(a1 + 176);
      v66 = (union _SLIST_HEADER *)(a1 + 144);
    }
    DepthSList = ExQueryDepthSList(v66);
    v69 = (__int64 *)"(DUAL) ";
    if ( !v16 )
      v69 = &qword_14007DC38;
    WPP_SF_qslll((_DWORD)v69, DepthSList, v68, a1, (__int64)v69, DepthSList, *(_DWORD *)(a1 + 180), v65);
  }
  AfdDereferenceEndpoint(a1);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004ba00  push    rbp
0x14004ba02  push    rbx
0x14004ba03  push    rsi
0x14004ba04  push    rdi
0x14004ba05  push    r12
0x14004ba07  push    r13
0x14004ba09  push    r14
0x14004ba0b  push    r15
0x14004ba0d  lea     rbp, [rsp-8]
0x14004ba12  sub     rsp, 108h
0x14004ba19  mov     rax, cs:__security_cookie
0x14004ba20  xor     rax, rsp
0x14004ba23  mov     [rbp+40h+var_50], rax
0x14004ba27  mov     rax, [rbp+40h+arg_38]
0x14004ba2e  xor     r12d, r12d
0x14004ba31  mov     r15, [rbp+40h+arg_20]
0x14004ba35  xorps   xmm1, xmm1
0x14004ba38  mov     r13, [rbp+40h+arg_30]
0x14004ba3f  xorps   xmm0, xmm0
0x14004ba42  mov     [rbp+40h+var_80], rax
0x14004ba46  mov     esi, r9d
0x14004ba49  mov     rax, [rbp+40h+arg_40]
0x14004ba50  mov     r14, r8
0x14004ba53  mov     [rbp+40h+var_88], rax
0x14004ba57  mov     rdi, rcx
0x14004ba5a  xor     eax, eax
0x14004ba5c  mov     [rsp+140h+Src], r8
0x14004ba61  mov     qword ptr [rsp+140h+LockHandle.OldIrql], rax
0x14004ba66  mov     [rbp+40h+var_58], ax
0x14004ba6a  mov     [rsp+140h+var_F8], edx
0x14004ba6e  mov     [rsp+140h+Irp], r12
0x14004ba73  movups  xmmword ptr [rsp+140h+LockHandle.LockQueue.Next], xmm0
0x14004ba78  movups  [rbp+40h+var_78], xmm1
0x14004ba7c  movups  [rbp+40h+var_68], xmm1
0x14004ba80  lea     ebx, [rax+1]
0x14004ba83  test    byte ptr cs:xmmword_1400875E0+1, bl
0x14004ba89  jz      short loc_14004BAA6
0x14004ba8b  lea     edx, [rax+0Ch]
0x14004ba8e  mov     ecx, 408h
0x14004ba93  mov     r9, rdi
0x14004ba96  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004ba9d  call    WPP_SF_q
0x14004baa2  mov     edx, [rsp+140h+var_F8]
0x14004baa6  prefetchw byte ptr [rdi+40h]
0x14004baaa  mov     rax, [rdi+40h]
0x14004baae  lea     rcx, [rax+1]
0x14004bab2  cmp     rcx, rbx
0x14004bab5  jbe     loc_14004C433
0x14004babb  lock cmpxchg [rdi+40h], rcx
0x14004bac1  jnz     short loc_14004BAAE
0x14004bac3  cmp     byte ptr [rdi+2], 6
0x14004bac7  jz      loc_14004C403
0x14004bacd  mov     eax, [rdi+8]
0x14004bad0  bt      eax, 0Bh
0x14004bad4  jb      loc_14004C403
0x14004bada  mov     eax, [rdi+8]
0x14004badd  mov     bl, r12b
0x14004bae0  bt      eax, 16h
0x14004bae4  jb      short loc_14004BAEF
0x14004bae6  mov     eax, [rdi+8]
0x14004bae9  bt      eax, 15h
0x14004baed  jnb     short loc_14004BB43
0x14004baef  cmp     edx, 16h
0x14004baf2  jnz     short loc_14004BB43
0x14004baf4  cmp     word ptr [r14+6], 2
0x14004bafa  jnz     short loc_14004BB43
0x14004bafc  movups  xmm0, xmmword ptr [r14]
0x14004bb00  lea     rdx, [rsp+140h+Irql]
0x14004bb05  mov     dword ptr [rsp+140h+Irql], 22h ; '"'
0x14004bb0d  movsd   xmm1, qword ptr [r14+0Eh]
0x14004bb13  lea     rcx, [rbp+40h+var_78]; void *
0x14004bb17  movups  [rbp+40h+var_78], xmm0
0x14004bb1b  movsd   qword ptr [rbp+40h+var_78+0Eh], xmm1
0x14004bb20  call    AfdTdi_TA4toTA6_InPlace
0x14004bb25  test    al, al
0x14004bb27  jz      short loc_14004BB43
0x14004bb29  mov     ebx, [rdi+8]
0x14004bb2c  lea     r14, [rbp+40h+var_78]
0x14004bb30  mov     eax, dword ptr [rsp+140h+Irql]
0x14004bb34  shr     ebx, 16h
0x14004bb37  and     bl, 1
0x14004bb3a  mov     [rsp+140h+var_F8], eax
0x14004bb3e  mov     [rsp+140h+Src], r14
0x14004bb43  mov     qword ptr [rsp+140h+Irql], r12
0x14004bb48  cmp     [rdi+0D0h], r12
0x14004bb4f  jz      loc_14004BBE7
0x14004bb55  lea     rcx, [rdi+38h]; SpinLock
0x14004bb59  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bb5e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bb65  nop     dword ptr [rax+rax+00h]
0x14004bb6a  mov     rcx, [rdi+0D0h]
0x14004bb71  test    rcx, rcx
0x14004bb74  jz      short loc_14004BBD6
0x14004bb76  call    CopyConnectDataBuffers
0x14004bb7b  mov     qword ptr [rsp+140h+Irql], rax
0x14004bb80  mov     r12, rax
0x14004bb83  test    rax, rax
0x14004bb86  jnz     short loc_14004BBD6
0x14004bb88  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bb8d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bb94  nop     dword ptr [rax+rax+00h]
0x14004bb99  mov     rcx, rdi
0x14004bb9c  call    AfdDereferenceEndpoint
0x14004bba1  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bba8  jz      short loc_14004BBC3
0x14004bbaa  lea     edx, [r12+0Eh]
0x14004bbaf  mov     ecx, 308h
0x14004bbb4  mov     r9, rdi
0x14004bbb7  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004bbbe  call    WPP_SF_q
0x14004bbc3  mov     [rsp+140h+var_118], 0
0x14004bbcc  mov     edx, 1968h
0x14004bbd1  jmp     loc_14004C446
0x14004bbd6  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bbdb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bbe2  nop     dword ptr [rax+rax+00h]
0x14004bbe7  test    r15, r15
0x14004bbea  jz      loc_14004BCA8
0x14004bbf0  test    esi, esi
0x14004bbf2  jle     loc_14004BCA8
0x14004bbf8  lea     rcx, [rdi+38h]; SpinLock
0x14004bbfc  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bc01  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bc08  nop     dword ptr [rax+rax+00h]
0x14004bc0d  mov     r9d, esi
0x14004bc10  lea     rcx, [rsp+140h+Irql]
0x14004bc15  mov     r8, r15
0x14004bc18  mov     edx, 1204Bh
0x14004bc1d  call    AfdSaveReceivedConnectData
0x14004bc22  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bc27  mov     esi, eax
0x14004bc29  test    eax, eax
0x14004bc2b  jns     short loc_14004BC97
0x14004bc2d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bc34  nop     dword ptr [rax+rax+00h]
0x14004bc39  mov     rcx, rdi
0x14004bc3c  call    AfdDereferenceEndpoint
0x14004bc41  mov     rcx, qword ptr [rsp+140h+Irql]; P
0x14004bc46  test    rcx, rcx
0x14004bc49  jz      short loc_14004BC50
0x14004bc4b  call    AfdFreeConnectDataBuffers
0x14004bc50  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bc57  jz      short loc_14004BC72
0x14004bc59  mov     edx, 0Fh
0x14004bc5e  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004bc65  mov     ecx, 308h
0x14004bc6a  mov     r9, rdi
0x14004bc6d  call    WPP_SF_q
0x14004bc72  mov     edx, 1968h
0x14004bc77  mov     [rsp+140h+var_118], 0
0x14004bc80  mov     r8, rdi
0x14004bc83  mov     r9d, esi
0x14004bc86  mov     [rsp+140h+var_120], r14
0x14004bc8b  call    AFDETW_TRACECONNECT_INDICATION
0x14004bc90  mov     eax, esi
0x14004bc92  jmp     loc_14004C45F
0x14004bc97  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bc9e  nop     dword ptr [rax+rax+00h]
0x14004bca3  mov     r12, qword ptr [rsp+140h+Irql]
0x14004bca8  test    r13, r13
0x14004bcab  jz      loc_14004BD51
0x14004bcb1  mov     esi, [rbp+40h+arg_28]
0x14004bcb4  test    esi, esi
0x14004bcb6  jle     loc_14004BD51
0x14004bcbc  lea     rcx, [rdi+38h]; SpinLock
0x14004bcc0  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x14004bcc5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004bccc  nop     dword ptr [rax+rax+00h]
0x14004bcd1  mov     r9d, esi
0x14004bcd4  lea     rcx, [rsp+140h+Irql]
0x14004bcd9  mov     r8, r13
0x14004bcdc  mov     edx, 1204Fh
0x14004bce1  call    AfdSaveReceivedConnectData
0x14004bce6  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x14004bceb  mov     esi, eax
0x14004bced  test    eax, eax
0x14004bcef  jns     short loc_14004BD40
0x14004bcf1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bcf8  nop     dword ptr [rax+rax+00h]
0x14004bcfd  mov     rcx, rdi
0x14004bd00  call    AfdDereferenceEndpoint
0x14004bd05  mov     rcx, qword ptr [rsp+140h+Irql]; P
0x14004bd0a  test    rcx, rcx
0x14004bd0d  jz      short loc_14004BD14
0x14004bd0f  call    AfdFreeConnectDataBuffers
0x14004bd14  test    byte ptr cs:xmmword_1400875D0+9, 1
0x14004bd1b  jz      short loc_14004BD36
0x14004bd1d  mov     edx, 10h
0x14004bd22  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004bd29  mov     ecx, 308h
0x14004bd2e  mov     r9, rdi
0x14004bd31  call    WPP_SF_q
0x14004bd36  mov     edx, 1969h
0x14004bd3b  jmp     loc_14004BC77
0x14004bd40  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004bd47  nop     dword ptr [rax+rax+00h]
0x14004bd4c  mov     r12, qword ptr [rsp+140h+Irql]
0x14004bd51  test    r12, r12
0x14004bd54  jz      short loc_14004BD99
0x14004bd56  lea     r13, [r12+80h]
0x14004bd5e  xorps   xmm0, xmm0
0x14004bd61  movups  xmmword ptr [r13+0], xmm0
0x14004bd66  mov     [rbp+40h+var_C0], r13
0x14004bd6a  movups  xmmword ptr [r13+10h], xmm0
0x14004bd6f  movups  xmmword ptr [r13+20h], xmm0
0x14004bd74  mov     rax, [r12]
0x14004bd78  mov     [r13+8], rax
0x14004bd7c  mov     eax, [r12+8]
0x14004bd81  mov     [r13+0], eax
0x14004bd85  mov     rax, [r12+10h]
0x14004bd8a  mov     [r13+18h], rax
0x14004bd8e  mov     eax, [r12+18h]
0x14004bd93  mov     [r13+10h], eax
0x14004bd97  jmp     short loc_14004BDA1
0x14004bd99  mov     [rbp+40h+var_C0], 0
0x14004bda1  mov     [rsp+140h+var_118], 0
0x14004bdaa  xor     r9d, r9d
0x14004bdad  mov     r8, rdi
0x14004bdb0  mov     [rsp+140h+var_120], r14
0x14004bdb5  mov     edx, 1964h
0x14004bdba  call    AFDETW_TRACECONNECT_INDICATION
0x14004bdbf  mov     r15d, 0C000009Ah
0x14004bdc5  lea     r8, [rsp+140h+Irp]
0x14004bdca  mov     dl, bl
0x14004bdcc  mov     rcx, rdi
0x14004bdcf  call    AfdGetFreeConnection
0x14004bdd4  mov     rsi, rax
0x14004bdd7  test    rax, rax
0x14004bdda  jz      loc_14004C359
0x14004bde0  test    byte ptr cs:xmmword_1400875E0+1, 1
0x14004bde7  jz      short loc_14004BE02
0x14004bde9  mov     edx, 11h
0x14004bdee  lea     r8, WPP_58dc946983e836cc04e1d78c7f3ffd40_Traceguids
0x14004bdf5  mov     ecx, 408h
0x14004bdfa  mov     r9, rax
0x14004bdfd  call    WPP_SF_q
0x14004be02  mov     rcx, [rsi+98h]; P
0x14004be09  mov     rax, [rsi+10h]
0x14004be0d  mov     r13, [rsi+18h]
0x14004be11  mov     r14d, [rsp+140h+var_F8]
0x14004be16  mov     [rbp+40h+var_B0], rax
0x14004be1a  mov     [rbp+40h+var_90], r13
0x14004be1e  test    rcx, rcx
0x14004be21  jz      short loc_14004BE67
0x14004be23  mov     eax, [rsi+0A0h]
0x14004be29  cmp     eax, r14d
0x14004be2c  jnb     loc_14004BF6E
0x14004be32  cmp     eax, cs:AfdStandardAddressLength
0x14004be38  ja      short loc_14004BE4B
0x14004be3a  mov     rdx, rcx
0x14004be3d  mov     rcx, cs:PplAddressPool
0x14004be44  call    PplFreeToLookasideList
0x14004be49  jmp     short loc_14004BE5C
0x14004be4b  mov     edx, 52646641h; Tag
0x14004be50  call    cs:__imp_ExFreePoolWithTag
0x14004be57  nop     dword ptr [rax+rax+00h]
0x14004be5c  mov     qword ptr [rsi+98h], 0
0x14004be67  cmp     r14d, cs:AfdStandardAddressLength
0x14004be6e  movsxd  rdx, r14d
0x14004be71  ja      short loc_14004BE7A
0x14004be73  call    AfdAllocateZeroedFromLookasideList
0x14004be78  jmp     short loc_14004BE8C
0x14004be7a  xor     r9d, r9d
0x14004be7d  mov     r8d, 52646641h
0x14004be83  lea     ecx, [r9+40h]
0x14004be87  call    AfdAllocatePoolPriority
0x14004be8c  mov     [rsi+98h], rax
0x14004be93  test    rax, rax
0x14004be96  jnz     loc_14004BF6E
0x14004be9c  mov     r14, [rsp+140h+Irp]
0x14004bea1  test    r14, r14
0x14004bea4  jz      short loc_14004BF1D
0x14004bea6  mov     r8, [rsi+8]
0x14004beaa  lea     ecx, [rax+1]
0x14004bead  mov     r13d, 0C0000120h
0x14004beb3  mov     edx, 1840h
0x14004beb8  mov     r9d, r13d
0x14004bebb  call    AFDETW_TRACEWAITLISTEN
0x14004bec0  mov     r9d, r13d
0x14004bec3  mov     r8, r14
0x14004bec6  mov     edx, 1852h
0x14004becb  call    AFDETW_TRACEACCEPT_ERROR
0x14004bed0  mov     edx, r13d
0x14004bed3  mov     rcx, r14
0x14004bed6  call    AfdCleanupSuperAccept
0x14004bedb  cmp     byte ptr [r14+44h], 0
0x14004bee0  jz      short loc_14004BF08
0x14004bee2  lea     rcx, [rsp+140h+Irql]; Irql
0x14004bee7  mov     [rsp+140h+Irql], 0
0x14004beec  call    cs:__imp_IoAcquireCancelSpinLock
0x14004bef3  nop     dword ptr [rax+rax+00h]
0x14004bef8  mov     cl, [rsp+140h+Irql]; Irql
0x14004befc  call    cs:__imp_IoReleaseCancelSpinLock
0x14004bf03  nop     dword ptr [rax+rax+00h]
0x14004bf08  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14004bf0e  mov     rcx, r14; Irp
0x14004bf11  call    cs:__imp_IofCompleteRequest
0x14004bf18  nop     dword ptr [rax+rax+00h]
0x14004bf1d  mov     eax, [rsi+4]
0x14004bf20  test    al, 2
  ... truncated ...
```
