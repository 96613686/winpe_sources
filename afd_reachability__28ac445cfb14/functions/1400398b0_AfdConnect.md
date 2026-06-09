# AfdConnect

- ea: `0x1400398b0`
- end: `0x14003a90a`
- name: `AfdConnect`
- size: `4186`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140002440`
- `0x140003670`
- `0x140005b60`
- `0x14000d4b0`
- `0x14000dc90`
- `0x1400109e0`
- `0x140010cc0`
- `0x140013030`
- `0x140015990`
- `0x14001adf0`
- `0x14001b0f8`
- `0x140026e80`
- `0x14002fd5c`
- `0x140030950`
- `0x140036ca4`
- `0x140039198`
- `0x1400398b0`
- `0x14003a910`
- `0x1400445b8`
- `0x14004846c`
- `0x1400486b8`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072780`
- `0x140072b00`
- `0x14009214c`
- `0x140092254`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140039eaa`
- `ntoskrnl!ExRaiseStatus` at `0x140039ef5`
- `ntoskrnl!ExRaiseStatus` at `0x140039f44`
- `ntoskrnl!ExRaiseStatus` at `0x140039f66`
- `ntoskrnl!ExRaiseStatus` at `0x140039eaa`
- `ntoskrnl!ExRaiseStatus` at `0x140039ef5`
- `ntoskrnl!ExRaiseStatus` at `0x140039f44`
- `ntoskrnl!ExRaiseStatus` at `0x140039f66`
- `ntoskrnl!ProbeForRead` at `0x1400399d0`
- `ntoskrnl!ProbeForRead` at `0x140039b24`
- `ntoskrnl!ProbeForRead` at `0x1400399d0`
- `ntoskrnl!ProbeForRead` at `0x140039b24`
- `ntoskrnl!ObfReferenceObject` at `0x140039c97`
- `ntoskrnl!ObfReferenceObject` at `0x140039cd6`
- `ntoskrnl!ObfReferenceObject` at `0x140039c97`
- `ntoskrnl!ObfReferenceObject` at `0x140039cd6`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400399eb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039b3f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400399eb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039b3f`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8cd`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8cd`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c59`
- `ntoskrnl!ObfDereferenceObject` at `0x140039fed`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a02c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a05d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a1d8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a7f6`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a811`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c59`
- `ntoskrnl!ObfDereferenceObject` at `0x140039fed`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a02c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a05d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a1d8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a7f6`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a811`
- `ntoskrnl!IofCallDriver` at `0x14003a767`
- `ntoskrnl!IofCallDriver` at `0x14003a767`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a6d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a6d3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a6a8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a6a8`
- `ntoskrnl!IoFileObjectType` at `0x140039c09`
- `ntoskrnl!IoFileObjectType` at `0x140039fa3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039c13`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039fad`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039c13`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039fad`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039d61`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039d61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a268`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a655`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a88e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a268`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a655`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a88e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8a9`
- `ntoskrnl!ExAllocatePool2` at `0x140039db8`
- `ntoskrnl!ExAllocatePool2` at `0x140039db8`
- `ntoskrnl!IoIs32bitProcess` at `0x140039947`
- `ntoskrnl!IoIs32bitProcess` at `0x140039947`

## pseudocode

```c
NTSTATUS __fastcall AfdConnect(PIRP Irp, __int64 a2)
{
  __int64 v4; // rsi
  char v5; // bl
  unsigned int v6; // r13d
  ADDRESS_FAMILY *v7; // r15
  bool v8; // zf
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // r14d
  NTSTATUS v12; // r15d
  __int64 v13; // r9
  PVOID v14; // rsi
  struct _IRP *v15; // r14
  SIZE_T v16; // rax
  __int64 v17; // r14
  void *v18; // rcx
  __int64 v19; // r14
  SIZE_T v20; // rax
  __int64 v21; // r14
  NTSTATUS v22; // eax
  PVOID v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  HANDLE CurrentProcessId; // rax
  struct _IRP *Pool2; // rax
  void *v28; // rcx
  ADDRESS_FAMILY *v29; // r8
  struct _IRP *v30; // rcx
  PVOID UserBuffer; // rcx
  unsigned int ULongFromUser; // eax
  __int64 v33; // rdx
  unsigned int v34; // r14d
  __int64 v35; // r9
  void *PoolPriority; // rax
  NTSTATUS v37; // eax
  PVOID v38; // rdx
  __int64 v39; // r14
  __int64 v40; // r9
  __int64 v41; // rdx
  volatile __int32 *v42; // r14
  __int64 v43; // r13
  int v44; // r14d
  int v45; // ebx
  __int64 v47; // r9
  int v48; // eax
  int v49; // eax
  struct _UNICODE_STRING *v50; // r14
  struct _UNICODE_STRING *v51; // rbx
  __int64 (__fastcall **v52)(); // rax
  PVOID v53; // rbx
  unsigned int v54; // r14d
  __int64 v55; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v57; // rcx
  int Object; // [rsp+20h] [rbp-198h]
  char v59; // [rsp+40h] [rbp-178h]
  char v60; // [rsp+41h] [rbp-177h]
  char v61; // [rsp+42h] [rbp-176h]
  _QWORD *v62; // [rsp+50h] [rbp-168h]
  __int64 v63; // [rsp+60h] [rbp-158h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-150h]
  struct _IRP *v65; // [rsp+70h] [rbp-148h]
  PVOID P; // [rsp+78h] [rbp-140h]
  PVOID v67; // [rsp+80h] [rbp-138h] BYREF
  __int64 v68; // [rsp+88h] [rbp-130h]
  void *Src; // [rsp+90h] [rbp-128h]
  PVOID v70; // [rsp+98h] [rbp-120h] BYREF
  struct _IRP *v71; // [rsp+A0h] [rbp-118h]
  void *v72; // [rsp+A8h] [rbp-110h]
  PVOID v73; // [rsp+B0h] [rbp-108h]
  ADDRESS_FAMILY *v74; // [rsp+B8h] [rbp-100h]
  HANDLE v75; // [rsp+C0h] [rbp-F8h]
  __int64 v76; // [rsp+C8h] [rbp-F0h]
  ADDRESS_FAMILY *v77; // [rsp+D0h] [rbp-E8h]
  _QWORD v78[16]; // [rsp+E0h] [rbp-D8h] BYREF
  _BYTE LockHandle[32]; // [rsp+160h] [rbp-58h] BYREF
  __int64 v80; // [rsp+180h] [rbp-38h]

  v68 = a2;
  v67 = Irp;
  Src = 0;
  v61 = *(_BYTE *)(a2 + 1);
  v62 = *(_QWORD **)(a2 + 48);
  v4 = v62[3];
  v63 = v4;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  P = 0;
  v72 = 0;
  v65 = 0;
  v71 = 0;
  v8 = IoIs32bitProcess(Irp) == 0;
  v9 = *(_DWORD *)(a2 + 8) - 1;
  if ( v8 )
  {
    if ( v9 <= 0xE )
    {
      v10 = 5003;
      goto LABEL_4;
    }
    v20 = *(unsigned int *)(a2 + 16);
    if ( (unsigned int)v20 < 0x18 )
    {
      v10 = 5004;
      goto LABEL_4;
    }
    memset(LockHandle, 0, sizeof(LockHandle));
    v80 = 0;
    v21 = *(_QWORD *)(a2 + 32);
    if ( Irp->RequestorMode )
      ProbeForRead((volatile void *)v21, v20, 4u);
    if ( Irp->RequestorMode )
    {
      if ( (v21 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(LockHandle, (void *)v21, 0x18u);
    }
    else
    {
      RtlCopyVolatileMemory(LockHandle, (const void *)v21, 0x18u);
    }
    v60 = LockHandle[0];
    v18 = *(void **)&LockHandle[16];
    v76 = *(_QWORD *)&LockHandle[16];
    v75 = *(HANDLE *)&LockHandle[8];
    Src = (void *)(v21 + 24);
    v19 = v68;
    v6 = *(_DWORD *)(v68 + 16) - 24;
    v64 = v6;
    goto LABEL_29;
  }
  if ( v9 > 6 )
  {
    v16 = *(unsigned int *)(a2 + 16);
    if ( (unsigned int)v16 < 0xC )
    {
      v10 = 5001;
      goto LABEL_4;
    }
    memset(LockHandle, 0, 24);
    v17 = *(_QWORD *)(a2 + 32);
    if ( Irp->RequestorMode )
      ProbeForRead((volatile void *)v17, v16, 4u);
    if ( Irp->RequestorMode )
    {
      if ( (v17 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(LockHandle, (void *)v17, 0xCu);
    }
    else
    {
      RtlCopyVolatileMemory(LockHandle, (const void *)v17, 0xCu);
    }
    v60 = LockHandle[0];
    v18 = (void *)*(int *)&LockHandle[8];
    v76 = *(int *)&LockHandle[8];
    v75 = (HANDLE)*(int *)&LockHandle[4];
    Src = (void *)(v17 + 12);
    v19 = v68;
    v6 = *(_DWORD *)(v68 + 16) - 12;
    v64 = v6;
LABEL_29:
    if ( *(_WORD *)v4 == 0xAAFD )
    {
      v70 = 0;
      v22 = ObReferenceObjectByHandle(
              v18,
              (unsigned __int8)HIBYTE(*(_WORD *)(v19 + 24)) >> 6,
              (POBJECT_TYPE)IoFileObjectType,
              Irp->RequestorMode,
              &v70,
              0);
      v12 = v22;
      if ( v22 < 0 )
      {
        v13 = (unsigned int)v22;
        v10 = 5006;
        goto LABEL_6;
      }
      v23 = v70;
      v62 = v70;
      v73 = v70;
      if ( *((PVOID *)v70 + 1) != AfdDeviceObject )
      {
        ObfDereferenceObject(v70);
        v11 = -1073741816;
        v10 = 5007;
        goto LABEL_5;
      }
      v4 = *((_QWORD *)v70 + 3);
      v63 = v4;
      *(_QWORD *)(v19 + 48) = v70;
      v7 = 0;
    }
    else
    {
      v73 = v62;
      ObfReferenceObject(v62);
    }
    v59 = 0;
    v5 = BYTE1(*(_DWORD *)(v4 + 8)) & 1;
    if ( *(_WORD *)v4 != 0xAFD1 && Irp->RequestorMode == 1 && Irp->UserBuffer )
    {
      ObfReferenceObject(Irp->Tail.Overlay.Thread);
      v59 = 1;
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      v24 = 5008;
LABEL_42:
      v12 = -1073741811;
      v25 = 3221225485LL;
LABEL_43:
      AFDETW_TRACECONNECT(0, v24, v4, v25, 0);
      v14 = 0;
      v15 = 0;
LABEL_44:
      ObfDereferenceObject(v62);
      if ( v59 )
        ObfDereferenceObject(Irp->Tail.Overlay.Thread);
      goto LABEL_187;
    }
    if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 )
    {
      if ( v6 < 2 )
      {
        v24 = 5009;
        goto LABEL_42;
      }
    }
    else if ( v6 < 8 )
    {
      v24 = 5010;
      goto LABEL_42;
    }
    if ( !v60 && AfdSanServiceHelper && v61 != 46 )
    {
      if ( SBYTE8(xmmword_1400875E0) < 0 )
      {
        CurrentProcessId = PsGetCurrentProcessId();
        WPP_SF_q(1287, 10, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, CurrentProcessId);
      }
      v12 = -1073741574;
      v25 = 3221225722LL;
      v24 = 5011;
      goto LABEL_43;
    }
    if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 )
    {
      if ( v6 > (unsigned int)AfdStandardAddressLength )
        PoolPriority = (void *)AfdAllocatePoolPriority(64, v6, 1382311489, 0);
      else
        PoolPriority = (void *)AfdAllocateZeroedFromLookasideList(v23, v6);
      P = PoolPriority;
      v7 = (ADDRESS_FAMILY *)PoolPriority;
      v72 = PoolPriority;
      if ( !PoolPriority )
        ExRaiseStatus(-1073741670);
      if ( Irp->RequestorMode )
        RtlCopyFromUser(PoolPriority, Src, v6);
      else
        RtlCopyVolatileMemory(PoolPriority, Src, v6);
      v74 = v7;
      v77 = v7;
      if ( *v7 >= 0x23u )
        ExRaiseStatus(-1073741503);
      if ( v6 < SOCKADDR_SIZE(*v7) )
        ExRaiseStatus(-1073741503);
    }
    else
    {
      Pool2 = (struct _IRP *)ExAllocatePool2(97, v6 + 96, 1231316545);
      v65 = Pool2;
      v71 = Pool2;
      Irp->AssociatedIrp.MasterIrp = Pool2;
      v74 = (ADDRESS_FAMILY *)(&Pool2->Overlay.AllocationSize + 1);
      v28 = &Pool2->Overlay.AllocationSize + 1;
      if ( Irp->RequestorMode )
        RtlCopyFromUser(v28, Src, v6);
      else
        RtlCopyVolatileMemory(v28, Src, v6);
      v29 = v74;
      if ( *(_DWORD *)v74 != 1
        || (v30 = v65, v6 < (unsigned int)*((unsigned __int16 *)&v65->Overlay.AllocationSize + 6) + 8) )
      {
        ExRaiseStatus(-1073741811);
      }
      v65->ThreadListEntry.Blink = (struct _LIST_ENTRY *)v74;
      LODWORD(v30->ThreadListEntry.Flink) = v6;
      v77 = v29;
    }
    UserBuffer = Irp->UserBuffer;
    if ( UserBuffer && Irp->RequestorMode == 1 )
    {
      ULongFromUser = RtlReadULongFromUser(UserBuffer);
      RtlWriteULongToUser(Irp->UserBuffer, ULongFromUser);
    }
    if ( !v75 )
    {
      if ( *(_WORD *)v4 == 0xAFD1 )
      {
        LOBYTE(Object) = v61 == 46;
        if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
          return AfdDoDatagramConnect(v62, Irp, 0, 0, Object);
        v45 = AfdDoDatagramConnect(v62, Irp, v7, v6, Object);
        if ( v6 > (unsigned int)AfdStandardAddressLength )
          ExFreePoolWithTag(v7, 0x52646641u);
        else
          PplFreeToLookasideList(PplAddressPool, v7);
        return v45;
      }
      v42 = (volatile __int32 *)(v4 + 368);
      v68 = v4 + 368;
      v47 = 4;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 368), 4, 0) )
      {
        v33 = 5018;
        goto LABEL_69;
      }
      if ( ((*(_WORD *)v4 + 20528) & 0xFFFD) != 0 )
      {
        v41 = 5019;
        goto LABEL_95;
      }
      if ( (*(_DWORD *)(v4 + 8) & 1) != 0 || *(_BYTE *)(v4 + 2) != 3 )
      {
        v12 = -1073741811;
        AFDETW_TRACECONNECT(0, 5020, v4, 3221225485LL, 0);
        goto LABEL_183;
      }
      v63 = 0;
      if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0
        && (*(_DWORD *)(v4 + 8) & 0x400000) != 0
        && (unsigned __int8)AfdTdi_IsTA6V4Mapped(v65->ThreadListEntry.Blink, LODWORD(v65->ThreadListEntry.Flink)) )
      {
        if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 || (LOBYTE(v47) = 1, (*(_DWORD *)(v4 + 16) & 0x200) == 0) )
          LOBYTE(v47) = 0;
        v48 = AfdCreateConnection(
                v4,
                *(_QWORD *)(*(_QWORD *)(v4 + 280) + 24LL),
                **(_QWORD **)(v4 + 280),
                v47,
                (*(_DWORD *)(v4 + 8) >> 8) & 1,
                (*(_DWORD *)(v4 + 8) >> 7) & 1,
                *(_QWORD *)(v4 + 48),
                &v63);
        v12 = v48;
        if ( v48 < 0 )
        {
          v43 = v63;
        }
        else
        {
          AFDETW_TRACECONNECT(0, 5021, v4, (unsigned int)v48, 0);
          v43 = v63;
          *(_DWORD *)(v63 + 4) |= 2u;
        }
        v49 = v12;
      }
      else
      {
        if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 || (LOBYTE(v47) = 1, (*(_DWORD *)(v4 + 16) & 0x200) == 0) )
          LOBYTE(v47) = 0;
        v49 = AfdCreateConnection(
                v4,
                *(_QWORD *)(v4 + 272),
                *(_QWORD *)(v4 + 256),
                v47,
                (*(_DWORD *)(v4 + 8) >> 8) & 1,
                (*(_DWORD *)(v4 + 8) >> 7) & 1,
                *(_QWORD *)(v4 + 48),
                &v63);
        v12 = v49;
        v43 = v63;
      }
      if ( v49 < 0 )
      {
        AFDETW_TRACECONNECT(0, 5022, v4, (unsigned int)v12, 0);
        goto LABEL_149;
      }
      if ( (*(_DWORD *)(v4 + 8) & 0x200000) != 0 )
        *(_DWORD *)(v43 + 4) |= 2u;
LABEL_152:
      if ( (xmmword_1400875E0 & 0x80u) != 0LL )
        WPP_SF_q(1031, 11, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, v4);
      AFDETW_TRACECONNECT(0, 5023, v4, 0, v74);
      if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 64)) <= 1 )
        __fastfail(0xEu);
      *(_QWORD *)(v43 + 8) = v4;
      *(_QWORD *)(v4 + 192) = v43;
      *(_WORD *)v4 = -20526;
      v12 = AfdAddConnectedReference(v43);
      if ( v12 >= 0 )
      {
        if ( (*(_DWORD *)(v4 + 8) & 0x100) != 0 )
        {
          v50 = 0;
          v51 = 0;
        }
        else
        {
          v50 = (struct _UNICODE_STRING *)v65;
          if ( (*(_DWORD *)(v43 + 4) & 2) != 0 )
            AfdTdi_TA6toTA4_InPlace(v65->ThreadListEntry.Blink, &v65->ThreadListEntry);
          v70 = v50;
          v51 = v50 + 3;
          v67 = &v50[3];
          if ( *(_QWORD *)(v4 + 208) )
          {
            AfdSetupConnectDataBuffers(v4, v43, &v70, &v67);
            v50 = (struct _UNICODE_STRING *)v70;
            v51 = (struct _UNICODE_STRING *)v67;
          }
        }
        AfdEnableFailedConnectEvent(v4);
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v43 + 48)) <= 1 )
          __fastfail(0xEu);
        if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
        {
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartConnect;
          CurrentStackLocation[-1].Context = (PVOID)v43;
          CurrentStackLocation[-1].Control = -32;
          v57 = Irp->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v57[-1].MajorFunction = 783;
          v57[-1].DeviceObject = *(PDEVICE_OBJECT *)(v43 + 24);
          v57[-1].FileObject = *(PFILE_OBJECT *)(v43 + 16);
          v57[-1].Parameters.QueryDirectory.FileName = v50;
          v57[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v51;
          v57[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&AfdInfiniteTimeout;
          _InterlockedAdd((volatile signed __int32 *)(v4 + 248), 1u);
          return IofCallDriver(*(PDEVICE_OBJECT *)(v43 + 24), Irp);
        }
        memset(v78, 0, sizeof(v78));
        v78[0] = AfdTLConnectComplete;
        v78[1] = Irp;
        LODWORD(v78[2]) = -1610612736;
        v78[3] = *(_QWORD *)(v4 + 16);
        v78[12] = AfdInfiniteTimeout;
        v78[9] = v43;
        v52 = AfdTlClientConnectDispatch;
        if ( (*(_BYTE *)(v4 + 7) & 0x10) != 0 )
          v52 = AfdRioTlClientConnectDispatch;
        v78[14] = v52;
        v53 = P;
        v78[11] = P;
        Irp->Tail.Overlay.DriverContext[2] = 0;
        if ( (unsigned __int8)AfdRefTLBaseEndpoint(v4) )
        {
          v54 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(*(_QWORD *)(v4 + 272) + 40LL) + 40LL))(
                  *(_QWORD *)(*(_QWORD *)(v4 + 272) + 32LL),
                  v78);
          AfdDerefTLBaseEndpoint(v4);
        }
        else
        {
          v54 = -1073741816;
        }
        if ( v64 > (unsigned int)AfdStandardAddressLength )
          ExFreePoolWithTag(v53, 0x52646641u);
        else
          PplFreeToLookasideList(PplAddressPool, v53);
        if ( v54 == 259 )
        {
          memset(LockHandle, 0, 24);
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), (PKLOCK_QUEUE_HANDLE)LockHandle);
          if ( !*(_QWORD *)(v43 + 24) )
          {
            *(_QWORD *)(v43 + 24) = v78[13];
            *(_DWORD *)(v43 + 4) |= 8u;
          }
          KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
          LOBYTE(v55) = 1;
          if ( (unsigned __int8)AfdTLPendRequest(Irp, v78[13], v55) )
            return v54;
        }
        else
        {
          AfdTLConnectComplete(Irp, v54, v78[10], v78[15]);
        }
        AfdTLConnectComplete2((PVOID)v4);
        return v54;
      }
LABEL_149:
      v6 = v64;
      goto LABEL_184;
    }
    if ( v61 != 46 )
    {
      v33 = 5013;
LABEL_69:
      v34 = -1073741811;
LABEL_70:
      v35 = v34;
      v12 = v34;
LABEL_71:
      AFDETW_TRACECONNECT(0, v33, v4, v35, 0);
LABEL_72:
      v14 = P;
      v15 = v65;
      goto LABEL_44;
    }
    v67 = 0;
    v37 = ObReferenceObjectByHandle(
            v75,
            (unsigned __int8)HIBYTE(*(_WORD *)(v68 + 24)) >> 6,
            (POBJECT_TYPE)IoFileObjectType,
            Irp->RequestorMode,
            &v67,
            0);
    v12 = v37;
    if ( v37 < 0 )
    {
      v35 = (unsigned int)v37;
      v33 = 5014;
      goto LABEL_71;
    }
    v38 = v67;
    v73 = v67;
    if ( *((PVOID *)v67 + 1) != AfdDeviceObject )
    {
      ObfDereferenceObject(v67);
      v34 = -1073741816;
      v33 = 5015;
      goto LABEL_70;
    }
    v39 = *((_QWORD *)v67 + 3);
    v68 = v4 + 368;
    v40 = 4;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 368), 4, 0) )
    {
      ObfDereferenceObject(v38);
      v33 = 5016;
      goto LABEL_69;
    }
    if ( *(_WORD *)v4 != 0xAFD1 && (unsigned __int8)(*(_BYTE *)(v4 + 2) - 3) > 1u )
    {
      ObfDereferenceObject(v38);
      v41 = 5508;
LABEL_95:
      v12 = -1073741811;
      AFDETW_TRACECONNECT(0, v41, v4, 3221225485LL, 0);
      v42 = (volatile __int32 *)v68;
LABEL_184:
      _InterlockedExchange(v42, 0);
      goto LABEL_72;
    }
    if ( ((*(_WORD *)v39 + 20528) & 0xFFF9) != 0
      || (*(_BYTE *)(v39 + 6) & 1) == 0
      || (*(_BYTE *)(v4 + 6) & 1) != 0
      || *(_BYTE *)(v39 + 2) != 4
      || ((*(_WORD *)v4 + 20528) & 0xFFFD) != 0
      || *(_QWORD *)(v4 + 272) != *(_QWORD *)(v39 + 272)
      || ((*(_DWORD *)(v4 + 8) & 0x100) == 0 || *(_BYTE *)(v4 + 2) != 2)
      && ((*(_DWORD *)(v4 + 8) & 0x100) != 0 || *(_BYTE *)(v4 + 2) != 1) )
    {
      v43 = 0;
      v44 = -1073741811;
      v12 = -1073741811;
      goto LABEL_117;
    }
    v63 = 0;
    if ( (*(_DWORD *)(v39 + 8) & 0x100) != 0 || (LOBYTE(v40) = 1, (*(_DWORD *)(v39 + 16) & 0x200) == 0) )
      LOBYTE(v40) = 0;
    v12 = AfdCreateConnection(
            v4,
            *(_QWORD *)(v39 + 272),
            *(_QWORD *)(v39 + 256),
            v40,
            (*(_DWORD *)(v39 + 8) >> 8) & 1,
            (*(_DWORD *)(v4 + 8) >> 7) & 1,
            *(_QWORD *)(v4 + 48),
            &v63);
    v43 = v63;
    if ( v63 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v39 + 368), *(unsigned __int8 *)(v39 + 2), 0) )
      {
        v44 = -1073741811;
        v12 = -1073741811;
LABEL_115:
        v38 = v73;
LABEL_117:
        ObfDereferenceObject(v38);
        if ( v44 < 0 )
        {
          AFDETW_TRACECONNECT(0, 5017, v4, (unsigned int)v12, 0);
          v6 = v64;
LABEL_183:
          v42 = (volatile __int32 *)(v4 + 368);
          goto LABEL_184;
        }
        v42 = (volatile __int32 *)(v4 + 368);
        goto LABEL_152;
      }
      AfdJoinInviteSetup(v39, v4);
    }
    else
    {
      v12 = -1073741670;
    }
    v44 = v12;
    goto LABEL_115;
  }
  v10 = 5000;
LABEL_4:
  v11 = -1073741811;
LABEL_5:
  v12 = v11;
  v13 = v11;
LABEL_6:
  AFDETW_TRACECONNECT(0, v10, v4, v13, 0);
  v14 = 0;
  v15 = 0;
LABEL_187:
  if ( v5 )
  {
    if ( v14 )
    {
      if ( v6 > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(v14, 0x52646641u);
      else
        PplFreeToLookasideList(PplAddressPool, v14);
    }
  }
  else if ( v15 )
  {
    ExFreePoolWithTag(v15, 0x49646641u);
    Irp->AssociatedIrp.MasterIrp = 0;
  }
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = v12;
  IofCompleteRequest(Irp, AfdPriorityBoost);
  return v12;
}

```

## disassembly

```asm
0x1400398b0  mov     r11, rsp
0x1400398b3  mov     [r11+18h], rbx
0x1400398b7  mov     [r11+20h], rsi
0x1400398bb  push    rdi
0x1400398bc  push    r12
0x1400398be  push    r13
0x1400398c0  push    r14
0x1400398c2  push    r15
0x1400398c4  sub     rsp, 190h
0x1400398cb  mov     rax, cs:__security_cookie
0x1400398d2  xor     rax, rsp
0x1400398d5  mov     [rsp+1B8h+var_30], rax
0x1400398dd  mov     r14, rdx
0x1400398e0  mov     [rsp+1B8h+var_130], rdx
0x1400398e8  mov     r12, rcx
0x1400398eb  mov     [rsp+1B8h+var_138], rcx
0x1400398f3  xor     edi, edi
0x1400398f5  mov     [r11-128h], rdi
0x1400398fc  mov     [rsp+1B8h+var_160], edi
0x140039900  mov     al, [rdx+1]
0x140039903  mov     [rsp+1B8h+var_176], al
0x140039907  cmp     al, 2Eh ; '.'
0x140039909  setz    [rsp+1B8h+var_175]
0x14003990e  mov     rax, [rdx+30h]
0x140039912  mov     [rsp+1B8h+var_168], rax
0x140039917  mov     rsi, [rax+18h]
0x14003991b  mov     [rsp+1B8h+var_158], rsi
0x140039920  mov     bl, dil
0x140039923  mov     r13d, edi
0x140039926  mov     [rsp+1B8h+var_160], edi
0x14003992a  mov     r15d, edi
0x14003992d  mov     [rsp+1B8h+P], rdi
0x140039932  mov     [r11-110h], rdi
0x140039939  mov     eax, edi
0x14003993b  mov     [rsp+1B8h+var_148], rax
0x140039940  mov     [r11-118h], rax
0x140039947  call    cs:__imp_IoIs32bitProcess
0x14003994e  nop     dword ptr [rax+rax+00h]
0x140039953  mov     ecx, [r14+8]
0x140039957  test    al, al
0x140039959  lea     eax, [rcx-1]
0x14003995c  jz      loc_140039ACC
0x140039962  cmp     eax, 6
0x140039965  ja      short loc_140039992
0x140039967  mov     edx, 1388h
0x14003996c  mov     r14d, 0C000000Dh
0x140039972  mov     r15d, r14d
0x140039975  mov     r9d, r14d
0x140039978  mov     r8, rsi
0x14003997b  mov     [rsp+1B8h+Object], rdi
0x140039980  xor     ecx, ecx
0x140039982  call    AFDETW_TRACECONNECT
0x140039987  mov     rsi, rdi
0x14003998a  mov     r14, rdi
0x14003998d  jmp     loc_14003A863
0x140039992  mov     eax, [r14+10h]
0x140039996  cmp     eax, 0Ch
0x140039999  jnb     short loc_1400399A2
0x14003999b  mov     edx, 1389h
0x1400399a0  jmp     short loc_14003996C
0x1400399a2  mov     [rsp+1B8h+var_174], edi
0x1400399a6  xorps   xmm0, xmm0
0x1400399a9  xor     ecx, ecx
0x1400399ab  movups  xmmword ptr [rsp+1B8h+LockHandle], xmm0
0x1400399b3  mov     qword ptr [rsp+1B8h+LockHandle+10h], rcx
0x1400399bb  mov     r14, [r14+20h]
0x1400399bf  cmp     [r12+40h], dil
0x1400399c4  jz      short loc_1400399DC
0x1400399c6  mov     rdx, rax; Length
0x1400399c9  lea     r8d, [rcx+4]; Alignment
0x1400399cd  mov     rcx, r14; Address
0x1400399d0  call    cs:__imp_ProbeForRead
0x1400399d7  nop     dword ptr [rax+rax+00h]
0x1400399dc  mov     al, [r12+40h]
0x1400399e1  test    al, al
0x1400399e3  jz      short loc_140039A13
0x1400399e5  test    r14b, 3
0x1400399e9  jz      short loc_1400399F7
0x1400399eb  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400399f2  nop     dword ptr [rax+rax+00h]
0x1400399f7  test    al, al
0x1400399f9  jz      short loc_140039A13
0x1400399fb  mov     r8d, 0Ch; Size
0x140039a01  mov     rdx, r14; Src
0x140039a04  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039a0c  call    RtlCopyFromUser
0x140039a11  jmp     short loc_140039A29
0x140039a13  mov     r8d, 0Ch; Size
0x140039a19  mov     rdx, r14; Src
0x140039a1c  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039a24  call    RtlCopyVolatileMemory
0x140039a29  mov     al, [rsp+1B8h+LockHandle]
0x140039a30  mov     [rsp+1B8h+var_177], al
0x140039a34  mov     [rsp+1B8h+var_170], al
0x140039a38  movsxd  rcx, dword ptr [rsp+1B8h+LockHandle+8]
0x140039a40  mov     [rsp+1B8h+var_F0], rcx
0x140039a48  movsxd  rdx, dword ptr [rsp+1B8h+LockHandle+4]
0x140039a50  mov     [rsp+1B8h+var_F8], rdx
0x140039a58  lea     rax, [r14+0Ch]
0x140039a5c  mov     [rsp+1B8h+Src], rax
0x140039a64  mov     r14, [rsp+1B8h+var_130]
0x140039a6c  mov     r13d, [r14+10h]
0x140039a70  sub     r13d, 0Ch
0x140039a74  mov     [rsp+1B8h+var_150], r13d
0x140039a79  mov     [rsp+1B8h+var_160], r13d
0x140039a7e  jmp     loc_140039BD2
0x140039a83  mov     [rsp+1B8h+Object], 0
0x140039a8c  mov     r15d, [rsp+1B8h+var_174]
0x140039a91  mov     r9d, r15d
0x140039a94  mov     r8, [rsp+1B8h+var_158]
0x140039a99  mov     edx, 138Ah
0x140039a9e  xor     ecx, ecx
0x140039aa0  call    AFDETW_TRACECONNECT
0x140039aa5  xor     edi, edi
0x140039aa7  mov     r14, [rsp+1B8h+var_118]
0x140039aaf  mov     r13d, [rsp+1B8h+var_160]
0x140039ab4  mov     rsi, [rsp+1B8h+var_110]
0x140039abc  mov     bl, dil
0x140039abf  mov     r12, [rsp+1B8h+var_138]
0x140039ac7  jmp     loc_14003A863
0x140039acc  cmp     eax, 0Eh
0x140039acf  ja      short loc_140039ADB
0x140039ad1  mov     edx, 138Bh
0x140039ad6  jmp     loc_14003996C
0x140039adb  mov     eax, [r14+10h]
0x140039adf  cmp     eax, 18h
0x140039ae2  jnb     short loc_140039AEE
0x140039ae4  mov     edx, 138Ch
0x140039ae9  jmp     loc_14003996C
0x140039aee  mov     [rsp+1B8h+var_174], edi
0x140039af2  xorps   xmm0, xmm0
0x140039af5  xor     ecx, ecx
0x140039af7  movups  xmmword ptr [rsp+1B8h+LockHandle], xmm0
0x140039aff  movups  xmmword ptr [rsp+1B8h+LockHandle+10h], xmm0
0x140039b07  mov     [rsp+1B8h+var_38], rcx
0x140039b0f  mov     r14, [r14+20h]
0x140039b13  cmp     [r12+40h], dil
0x140039b18  jz      short loc_140039B30
0x140039b1a  mov     rdx, rax; Length
0x140039b1d  lea     r8d, [rcx+4]; Alignment
0x140039b21  mov     rcx, r14; Address
0x140039b24  call    cs:__imp_ProbeForRead
0x140039b2b  nop     dword ptr [rax+rax+00h]
0x140039b30  mov     al, [r12+40h]
0x140039b35  test    al, al
0x140039b37  jz      short loc_140039B67
0x140039b39  test    r14b, 3
0x140039b3d  jz      short loc_140039B4B
0x140039b3f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140039b46  nop     dword ptr [rax+rax+00h]
0x140039b4b  test    al, al
0x140039b4d  jz      short loc_140039B67
0x140039b4f  mov     r8d, 18h; Size
0x140039b55  mov     rdx, r14; Src
0x140039b58  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039b60  call    RtlCopyFromUser
0x140039b65  jmp     short loc_140039B7D
0x140039b67  mov     r8d, 18h; Size
0x140039b6d  mov     rdx, r14; Src
0x140039b70  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039b78  call    RtlCopyVolatileMemory
0x140039b7d  mov     al, [rsp+1B8h+LockHandle]
0x140039b84  mov     [rsp+1B8h+var_177], al
0x140039b88  mov     [rsp+1B8h+var_170], al
0x140039b8c  mov     rcx, qword ptr [rsp+1B8h+LockHandle+10h]; Handle
0x140039b94  mov     [rsp+1B8h+var_F0], rcx
0x140039b9c  mov     rax, qword ptr [rsp+1B8h+LockHandle+8]
0x140039ba4  mov     [rsp+1B8h+var_F8], rax
0x140039bac  lea     rax, [r14+18h]
0x140039bb0  mov     [rsp+1B8h+Src], rax
0x140039bb8  mov     r14, [rsp+1B8h+var_130]
0x140039bc0  mov     r13d, [r14+10h]
0x140039bc4  sub     r13d, 18h
0x140039bc8  mov     [rsp+1B8h+var_150], r13d
0x140039bcd  mov     [rsp+1B8h+var_160], r13d
0x140039bd2  mov     eax, 0AAFDh
0x140039bd7  cmp     [rsi], ax
0x140039bda  jnz     loc_140039C87
0x140039be0  mov     [rsp+1B8h+var_120], rdi
0x140039be8  mov     edx, [r14+18h]
0x140039bec  shr     edx, 0Eh
0x140039bef  and     edx, 3; DesiredAccess
0x140039bf2  mov     [rsp+1B8h+HandleInformation], rdi; HandleInformation
0x140039bf7  lea     rax, [rsp+1B8h+var_120]
0x140039bff  mov     [rsp+1B8h+Object], rax; Object
0x140039c04  mov     r9b, [r12+40h]; AccessMode
0x140039c09  mov     r8, cs:__imp_IoFileObjectType
0x140039c10  mov     r8, [r8]; ObjectType
0x140039c13  call    cs:__imp_ObReferenceObjectByHandle
0x140039c1a  nop     dword ptr [rax+rax+00h]
0x140039c1f  mov     r15d, eax
0x140039c22  mov     [rsp+1B8h+var_174], eax
0x140039c26  test    eax, eax
0x140039c28  jns     short loc_140039C37
0x140039c2a  mov     r9d, eax
0x140039c2d  mov     edx, 138Eh
0x140039c32  jmp     loc_140039978
0x140039c37  mov     rcx, [rsp+1B8h+var_120]; Object
0x140039c3f  mov     [rsp+1B8h+var_168], rcx
0x140039c44  mov     [rsp+1B8h+var_108], rcx
0x140039c4c  mov     rax, cs:AfdDeviceObject
0x140039c53  cmp     [rcx+8], rax
0x140039c57  jz      short loc_140039C75
0x140039c59  call    cs:__imp_ObfDereferenceObject
0x140039c60  nop     dword ptr [rax+rax+00h]
0x140039c65  mov     r14d, 0C0000008h
0x140039c6b  mov     edx, 138Fh
0x140039c70  jmp     loc_140039972
0x140039c75  mov     rsi, [rcx+18h]
0x140039c79  mov     [rsp+1B8h+var_158], rsi
0x140039c7e  mov     [r14+30h], rcx
0x140039c82  mov     r15, rdi
0x140039c85  jmp     short loc_140039CA3
0x140039c87  mov     rax, [rsp+1B8h+var_168]
0x140039c8c  mov     [rsp+1B8h+var_108], rax
0x140039c94  mov     rcx, rax; Object
0x140039c97  call    cs:__imp_ObfReferenceObject
0x140039c9e  nop     dword ptr [rax+rax+00h]
0x140039ca3  mov     [rsp+1B8h+var_178], dil
0x140039ca8  mov     ebx, [rsi+8]
0x140039cab  shr     ebx, 8
0x140039cae  and     bl, 1
0x140039cb1  mov     [rsp+1B8h+var_16F], bl
0x140039cb5  mov     eax, 0AFD1h
0x140039cba  cmp     [rsi], ax
0x140039cbd  jz      short loc_140039CE7
0x140039cbf  cmp     byte ptr [r12+40h], 1
0x140039cc5  jnz     short loc_140039CE7
0x140039cc7  cmp     [r12+70h], rdi
0x140039ccc  jz      short loc_140039CE7
0x140039cce  mov     rcx, [r12+98h]; Object
0x140039cd6  call    cs:__imp_ObfReferenceObject
0x140039cdd  nop     dword ptr [rax+rax+00h]
0x140039ce2  mov     [rsp+1B8h+var_178], 1
0x140039ce7  test    r13d, r13d
0x140039cea  jns     short loc_140039D1C
0x140039cec  mov     edx, 1390h
0x140039cf1  mov     r14d, 0C000000Dh
0x140039cf7  mov     r15d, r14d
0x140039cfa  mov     r9d, r14d
0x140039cfd  mov     r8, rsi
0x140039d00  mov     [rsp+1B8h+Object], rdi
0x140039d05  xor     ecx, ecx
0x140039d07  call    AFDETW_TRACECONNECT
0x140039d0c  mov     rsi, rdi
0x140039d0f  mov     r14, rdi
0x140039d12  mov     rcx, [rsp+1B8h+var_168]
0x140039d17  jmp     loc_14003A7F6
0x140039d1c  mov     eax, [rsi+8]
0x140039d1f  bt      eax, 8
0x140039d23  jnb     short loc_140039D32
0x140039d25  cmp     r13d, 2
0x140039d29  jnb     short loc_140039D3F
0x140039d2b  mov     edx, 1391h
0x140039d30  jmp     short loc_140039CF1
0x140039d32  cmp     r13d, 8
0x140039d36  jnb     short loc_140039D3F
0x140039d38  mov     edx, 1392h
0x140039d3d  jmp     short loc_140039CF1
0x140039d3f  cmp     [rsp+1B8h+var_177], dil
0x140039d44  jnz     short loc_140039D99
0x140039d46  cmp     cs:AfdSanServiceHelper, 0
0x140039d4e  jz      short loc_140039D99
0x140039d50  cmp     [rsp+1B8h+var_176], 2Eh ; '.'
0x140039d55  jz      short loc_140039D99
0x140039d57  mov     al, byte ptr cs:xmmword_1400875E0+8
0x140039d5d  test    al, al
0x140039d5f  jns     short loc_140039D86
0x140039d61  call    cs:__imp_PsGetCurrentProcessId
0x140039d68  nop     dword ptr [rax+rax+00h]
0x140039d6d  mov     r9, rax
0x140039d70  mov     edx, 0Ah
0x140039d75  mov     ecx, 507h
0x140039d7a  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x140039d81  call    WPP_SF_q
0x140039d86  mov     r15d, 0C00000FAh
0x140039d8c  mov     r9d, r15d
0x140039d8f  mov     edx, 1393h
0x140039d94  jmp     loc_140039CFD
0x140039d99  mov     eax, [rsi+8]
0x140039d9c  mov     r14d, r13d
0x140039d9f  bt      eax, 8
0x140039da3  jb      loc_140039EB6
0x140039da9  lea     edx, [r13+60h]
0x140039dad  mov     ecx, 61h ; 'a'
0x140039db2  mov     r8d, 49646641h
0x140039db8  call    cs:__imp_ExAllocatePool2
0x140039dbf  nop     dword ptr [rax+rax+00h]
0x140039dc4  mov     [rsp+1B8h+var_148], rax
0x140039dc9  mov     [rsp+1B8h+var_118], rax
0x140039dd1  mov     [r12+18h], rax
0x140039dd6  add     rax, 60h ; '`'
0x140039dda  mov     [rsp+1B8h+var_100], rax
0x140039de2  mov     r8d, r14d; Size
0x140039de5  mov     rdx, [rsp+1B8h+Src]; Src
0x140039ded  mov     rcx, rax; void *
0x140039df0  cmp     [r12+40h], dil
0x140039df5  jz      short loc_140039DFE
0x140039df7  call    RtlCopyFromUser
0x140039dfc  jmp     short loc_140039E03
  ... truncated ...
```
