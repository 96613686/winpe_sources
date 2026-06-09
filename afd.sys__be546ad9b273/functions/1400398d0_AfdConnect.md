# AfdConnect

- ea: `0x1400398d0`
- end: `0x14003a92a`
- name: `AfdConnect`
- size: `4186`
- prototype: `NTSTATUS __fastcall(PIRP Irp, __int64)`
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
- `0x14002fd7c`
- `0x140030970`
- `0x140036cc4`
- `0x1400391b8`
- `0x1400398d0`
- `0x14003a930`
- `0x1400445d8`
- `0x1400484ec`
- `0x140048738`
- `0x140072840`
- `0x140072870`
- `0x140072920`
- `0x140072c80`
- `0x14009214c`
- `0x140092254`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140039eca`
- `ntoskrnl!ExRaiseStatus` at `0x140039f15`
- `ntoskrnl!ExRaiseStatus` at `0x140039f64`
- `ntoskrnl!ExRaiseStatus` at `0x140039f86`
- `ntoskrnl!ExRaiseStatus` at `0x140039eca`
- `ntoskrnl!ExRaiseStatus` at `0x140039f15`
- `ntoskrnl!ExRaiseStatus` at `0x140039f64`
- `ntoskrnl!ExRaiseStatus` at `0x140039f86`
- `ntoskrnl!ProbeForRead` at `0x1400399f0`
- `ntoskrnl!ProbeForRead` at `0x140039b44`
- `ntoskrnl!ProbeForRead` at `0x1400399f0`
- `ntoskrnl!ProbeForRead` at `0x140039b44`
- `ntoskrnl!ObfReferenceObject` at `0x140039cb7`
- `ntoskrnl!ObfReferenceObject` at `0x140039cf6`
- `ntoskrnl!ObfReferenceObject` at `0x140039cb7`
- `ntoskrnl!ObfReferenceObject` at `0x140039cf6`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039a0b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039b5f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039a0b`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140039b5f`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8ed`
- `ntoskrnl!IofCompleteRequest` at `0x14003a8ed`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c79`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a00d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a04c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a07d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a1f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a816`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a831`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c79`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a00d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a04c`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a07d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a1f8`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a816`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a831`
- `ntoskrnl!IofCallDriver` at `0x14003a787`
- `ntoskrnl!IofCallDriver` at `0x14003a787`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a6f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003a6f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a6c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003a6c8`
- `ntoskrnl!IoFileObjectType` at `0x140039c29`
- `ntoskrnl!IoFileObjectType` at `0x140039fc3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039c33`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039fcd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039c33`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039fcd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039d81`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039d81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a288`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a288`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a8c9`
- `ntoskrnl!ExAllocatePool2` at `0x140039dd8`
- `ntoskrnl!ExAllocatePool2` at `0x140039dd8`
- `ntoskrnl!IoIs32bitProcess` at `0x140039967`
- `ntoskrnl!IoIs32bitProcess` at `0x140039967`

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
        PoolPriority = AfdAllocateZeroedFromLookasideList((__int64)v23, v6);
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
0x1400398d0  mov     r11, rsp
0x1400398d3  mov     [r11+18h], rbx
0x1400398d7  mov     [r11+20h], rsi
0x1400398db  push    rdi
0x1400398dc  push    r12
0x1400398de  push    r13
0x1400398e0  push    r14
0x1400398e2  push    r15
0x1400398e4  sub     rsp, 190h
0x1400398eb  mov     rax, cs:__security_cookie
0x1400398f2  xor     rax, rsp
0x1400398f5  mov     [rsp+1B8h+var_30], rax
0x1400398fd  mov     r14, rdx
0x140039900  mov     [rsp+1B8h+var_130], rdx
0x140039908  mov     r12, rcx
0x14003990b  mov     [rsp+1B8h+var_138], rcx
0x140039913  xor     edi, edi
0x140039915  mov     [r11-128h], rdi
0x14003991c  mov     [rsp+1B8h+var_160], edi
0x140039920  mov     al, [rdx+1]
0x140039923  mov     [rsp+1B8h+var_176], al
0x140039927  cmp     al, 2Eh ; '.'
0x140039929  setz    [rsp+1B8h+var_175]
0x14003992e  mov     rax, [rdx+30h]
0x140039932  mov     [rsp+1B8h+var_168], rax
0x140039937  mov     rsi, [rax+18h]
0x14003993b  mov     [rsp+1B8h+var_158], rsi
0x140039940  mov     bl, dil
0x140039943  mov     r13d, edi
0x140039946  mov     [rsp+1B8h+var_160], edi
0x14003994a  mov     r15d, edi
0x14003994d  mov     [rsp+1B8h+P], rdi
0x140039952  mov     [r11-110h], rdi
0x140039959  mov     eax, edi
0x14003995b  mov     [rsp+1B8h+var_148], rax
0x140039960  mov     [r11-118h], rax
0x140039967  call    cs:__imp_IoIs32bitProcess
0x14003996e  nop     dword ptr [rax+rax+00h]
0x140039973  mov     ecx, [r14+8]
0x140039977  test    al, al
0x140039979  lea     eax, [rcx-1]
0x14003997c  jz      loc_140039AEC
0x140039982  cmp     eax, 6
0x140039985  ja      short loc_1400399B2
0x140039987  mov     edx, 1388h
0x14003998c  mov     r14d, 0C000000Dh
0x140039992  mov     r15d, r14d
0x140039995  mov     r9d, r14d
0x140039998  mov     r8, rsi
0x14003999b  mov     [rsp+1B8h+Object], rdi
0x1400399a0  xor     ecx, ecx
0x1400399a2  call    AFDETW_TRACECONNECT
0x1400399a7  mov     rsi, rdi
0x1400399aa  mov     r14, rdi
0x1400399ad  jmp     loc_14003A883
0x1400399b2  mov     eax, [r14+10h]
0x1400399b6  cmp     eax, 0Ch
0x1400399b9  jnb     short loc_1400399C2
0x1400399bb  mov     edx, 1389h
0x1400399c0  jmp     short loc_14003998C
0x1400399c2  mov     [rsp+1B8h+var_174], edi
0x1400399c6  xorps   xmm0, xmm0
0x1400399c9  xor     ecx, ecx
0x1400399cb  movups  xmmword ptr [rsp+1B8h+LockHandle], xmm0
0x1400399d3  mov     qword ptr [rsp+1B8h+LockHandle+10h], rcx
0x1400399db  mov     r14, [r14+20h]
0x1400399df  cmp     [r12+40h], dil
0x1400399e4  jz      short loc_1400399FC
0x1400399e6  mov     rdx, rax; Length
0x1400399e9  lea     r8d, [rcx+4]; Alignment
0x1400399ed  mov     rcx, r14; Address
0x1400399f0  call    cs:__imp_ProbeForRead
0x1400399f7  nop     dword ptr [rax+rax+00h]
0x1400399fc  mov     al, [r12+40h]
0x140039a01  test    al, al
0x140039a03  jz      short loc_140039A33
0x140039a05  test    r14b, 3
0x140039a09  jz      short loc_140039A17
0x140039a0b  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140039a12  nop     dword ptr [rax+rax+00h]
0x140039a17  test    al, al
0x140039a19  jz      short loc_140039A33
0x140039a1b  mov     r8d, 0Ch; Size
0x140039a21  mov     rdx, r14; Src
0x140039a24  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039a2c  call    RtlCopyFromUser
0x140039a31  jmp     short loc_140039A49
0x140039a33  mov     r8d, 0Ch; Size
0x140039a39  mov     rdx, r14; Src
0x140039a3c  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039a44  call    RtlCopyVolatileMemory
0x140039a49  mov     al, [rsp+1B8h+LockHandle]
0x140039a50  mov     [rsp+1B8h+var_177], al
0x140039a54  mov     [rsp+1B8h+var_170], al
0x140039a58  movsxd  rcx, dword ptr [rsp+1B8h+LockHandle+8]
0x140039a60  mov     [rsp+1B8h+var_F0], rcx
0x140039a68  movsxd  rdx, dword ptr [rsp+1B8h+LockHandle+4]
0x140039a70  mov     [rsp+1B8h+var_F8], rdx
0x140039a78  lea     rax, [r14+0Ch]
0x140039a7c  mov     [rsp+1B8h+Src], rax
0x140039a84  mov     r14, [rsp+1B8h+var_130]
0x140039a8c  mov     r13d, [r14+10h]
0x140039a90  sub     r13d, 0Ch
0x140039a94  mov     [rsp+1B8h+var_150], r13d
0x140039a99  mov     [rsp+1B8h+var_160], r13d
0x140039a9e  jmp     loc_140039BF2
0x140039aa3  mov     [rsp+1B8h+Object], 0
0x140039aac  mov     r15d, [rsp+1B8h+var_174]
0x140039ab1  mov     r9d, r15d
0x140039ab4  mov     r8, [rsp+1B8h+var_158]
0x140039ab9  mov     edx, 138Ah
0x140039abe  xor     ecx, ecx
0x140039ac0  call    AFDETW_TRACECONNECT
0x140039ac5  xor     edi, edi
0x140039ac7  mov     r14, [rsp+1B8h+var_118]
0x140039acf  mov     r13d, [rsp+1B8h+var_160]
0x140039ad4  mov     rsi, [rsp+1B8h+var_110]
0x140039adc  mov     bl, dil
0x140039adf  mov     r12, [rsp+1B8h+var_138]
0x140039ae7  jmp     loc_14003A883
0x140039aec  cmp     eax, 0Eh
0x140039aef  ja      short loc_140039AFB
0x140039af1  mov     edx, 138Bh
0x140039af6  jmp     loc_14003998C
0x140039afb  mov     eax, [r14+10h]
0x140039aff  cmp     eax, 18h
0x140039b02  jnb     short loc_140039B0E
0x140039b04  mov     edx, 138Ch
0x140039b09  jmp     loc_14003998C
0x140039b0e  mov     [rsp+1B8h+var_174], edi
0x140039b12  xorps   xmm0, xmm0
0x140039b15  xor     ecx, ecx
0x140039b17  movups  xmmword ptr [rsp+1B8h+LockHandle], xmm0
0x140039b1f  movups  xmmword ptr [rsp+1B8h+LockHandle+10h], xmm0
0x140039b27  mov     [rsp+1B8h+var_38], rcx
0x140039b2f  mov     r14, [r14+20h]
0x140039b33  cmp     [r12+40h], dil
0x140039b38  jz      short loc_140039B50
0x140039b3a  mov     rdx, rax; Length
0x140039b3d  lea     r8d, [rcx+4]; Alignment
0x140039b41  mov     rcx, r14; Address
0x140039b44  call    cs:__imp_ProbeForRead
0x140039b4b  nop     dword ptr [rax+rax+00h]
0x140039b50  mov     al, [r12+40h]
0x140039b55  test    al, al
0x140039b57  jz      short loc_140039B87
0x140039b59  test    r14b, 3
0x140039b5d  jz      short loc_140039B6B
0x140039b5f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140039b66  nop     dword ptr [rax+rax+00h]
0x140039b6b  test    al, al
0x140039b6d  jz      short loc_140039B87
0x140039b6f  mov     r8d, 18h; Size
0x140039b75  mov     rdx, r14; Src
0x140039b78  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039b80  call    RtlCopyFromUser
0x140039b85  jmp     short loc_140039B9D
0x140039b87  mov     r8d, 18h; Size
0x140039b8d  mov     rdx, r14; Src
0x140039b90  lea     rcx, [rsp+1B8h+LockHandle]; void *
0x140039b98  call    RtlCopyVolatileMemory
0x140039b9d  mov     al, [rsp+1B8h+LockHandle]
0x140039ba4  mov     [rsp+1B8h+var_177], al
0x140039ba8  mov     [rsp+1B8h+var_170], al
0x140039bac  mov     rcx, qword ptr [rsp+1B8h+LockHandle+10h]; Handle
0x140039bb4  mov     [rsp+1B8h+var_F0], rcx
0x140039bbc  mov     rax, qword ptr [rsp+1B8h+LockHandle+8]
0x140039bc4  mov     [rsp+1B8h+var_F8], rax
0x140039bcc  lea     rax, [r14+18h]
0x140039bd0  mov     [rsp+1B8h+Src], rax
0x140039bd8  mov     r14, [rsp+1B8h+var_130]
0x140039be0  mov     r13d, [r14+10h]
0x140039be4  sub     r13d, 18h
0x140039be8  mov     [rsp+1B8h+var_150], r13d
0x140039bed  mov     [rsp+1B8h+var_160], r13d
0x140039bf2  mov     eax, 0AAFDh
0x140039bf7  cmp     [rsi], ax
0x140039bfa  jnz     loc_140039CA7
0x140039c00  mov     [rsp+1B8h+var_120], rdi
0x140039c08  mov     edx, [r14+18h]
0x140039c0c  shr     edx, 0Eh
0x140039c0f  and     edx, 3; DesiredAccess
0x140039c12  mov     [rsp+1B8h+HandleInformation], rdi; HandleInformation
0x140039c17  lea     rax, [rsp+1B8h+var_120]
0x140039c1f  mov     [rsp+1B8h+Object], rax; Object
0x140039c24  mov     r9b, [r12+40h]; AccessMode
0x140039c29  mov     r8, cs:__imp_IoFileObjectType
0x140039c30  mov     r8, [r8]; ObjectType
0x140039c33  call    cs:__imp_ObReferenceObjectByHandle
0x140039c3a  nop     dword ptr [rax+rax+00h]
0x140039c3f  mov     r15d, eax
0x140039c42  mov     [rsp+1B8h+var_174], eax
0x140039c46  test    eax, eax
0x140039c48  jns     short loc_140039C57
0x140039c4a  mov     r9d, eax
0x140039c4d  mov     edx, 138Eh
0x140039c52  jmp     loc_140039998
0x140039c57  mov     rcx, [rsp+1B8h+var_120]; Object
0x140039c5f  mov     [rsp+1B8h+var_168], rcx
0x140039c64  mov     [rsp+1B8h+var_108], rcx
0x140039c6c  mov     rax, cs:AfdDeviceObject
0x140039c73  cmp     [rcx+8], rax
0x140039c77  jz      short loc_140039C95
0x140039c79  call    cs:__imp_ObfDereferenceObject
0x140039c80  nop     dword ptr [rax+rax+00h]
0x140039c85  mov     r14d, 0C0000008h
0x140039c8b  mov     edx, 138Fh
0x140039c90  jmp     loc_140039992
0x140039c95  mov     rsi, [rcx+18h]
0x140039c99  mov     [rsp+1B8h+var_158], rsi
0x140039c9e  mov     [r14+30h], rcx
0x140039ca2  mov     r15, rdi
0x140039ca5  jmp     short loc_140039CC3
0x140039ca7  mov     rax, [rsp+1B8h+var_168]
0x140039cac  mov     [rsp+1B8h+var_108], rax
0x140039cb4  mov     rcx, rax; Object
0x140039cb7  call    cs:__imp_ObfReferenceObject
0x140039cbe  nop     dword ptr [rax+rax+00h]
0x140039cc3  mov     [rsp+1B8h+var_178], dil
0x140039cc8  mov     ebx, [rsi+8]
0x140039ccb  shr     ebx, 8
0x140039cce  and     bl, 1
0x140039cd1  mov     [rsp+1B8h+var_16F], bl
0x140039cd5  mov     eax, 0AFD1h
0x140039cda  cmp     [rsi], ax
0x140039cdd  jz      short loc_140039D07
0x140039cdf  cmp     byte ptr [r12+40h], 1
0x140039ce5  jnz     short loc_140039D07
0x140039ce7  cmp     [r12+70h], rdi
0x140039cec  jz      short loc_140039D07
0x140039cee  mov     rcx, [r12+98h]; Object
0x140039cf6  call    cs:__imp_ObfReferenceObject
0x140039cfd  nop     dword ptr [rax+rax+00h]
0x140039d02  mov     [rsp+1B8h+var_178], 1
0x140039d07  test    r13d, r13d
0x140039d0a  jns     short loc_140039D3C
0x140039d0c  mov     edx, 1390h
0x140039d11  mov     r14d, 0C000000Dh
0x140039d17  mov     r15d, r14d
0x140039d1a  mov     r9d, r14d
0x140039d1d  mov     r8, rsi
0x140039d20  mov     [rsp+1B8h+Object], rdi
0x140039d25  xor     ecx, ecx
0x140039d27  call    AFDETW_TRACECONNECT
0x140039d2c  mov     rsi, rdi
0x140039d2f  mov     r14, rdi
0x140039d32  mov     rcx, [rsp+1B8h+var_168]
0x140039d37  jmp     loc_14003A816
0x140039d3c  mov     eax, [rsi+8]
0x140039d3f  bt      eax, 8
0x140039d43  jnb     short loc_140039D52
0x140039d45  cmp     r13d, 2
0x140039d49  jnb     short loc_140039D5F
0x140039d4b  mov     edx, 1391h
0x140039d50  jmp     short loc_140039D11
0x140039d52  cmp     r13d, 8
0x140039d56  jnb     short loc_140039D5F
0x140039d58  mov     edx, 1392h
0x140039d5d  jmp     short loc_140039D11
0x140039d5f  cmp     [rsp+1B8h+var_177], dil
0x140039d64  jnz     short loc_140039DB9
0x140039d66  cmp     cs:AfdSanServiceHelper, 0
0x140039d6e  jz      short loc_140039DB9
0x140039d70  cmp     [rsp+1B8h+var_176], 2Eh ; '.'
0x140039d75  jz      short loc_140039DB9
0x140039d77  mov     al, byte ptr cs:xmmword_1400875E0+8
0x140039d7d  test    al, al
0x140039d7f  jns     short loc_140039DA6
0x140039d81  call    cs:__imp_PsGetCurrentProcessId
0x140039d88  nop     dword ptr [rax+rax+00h]
0x140039d8d  mov     r9, rax
0x140039d90  mov     edx, 0Ah
0x140039d95  mov     ecx, 507h
0x140039d9a  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x140039da1  call    WPP_SF_q
0x140039da6  mov     r15d, 0C00000FAh
0x140039dac  mov     r9d, r15d
0x140039daf  mov     edx, 1393h
0x140039db4  jmp     loc_140039D1D
0x140039db9  mov     eax, [rsi+8]
0x140039dbc  mov     r14d, r13d
0x140039dbf  bt      eax, 8
0x140039dc3  jb      loc_140039ED6
0x140039dc9  lea     edx, [r13+60h]
0x140039dcd  mov     ecx, 61h ; 'a'
0x140039dd2  mov     r8d, 49646641h
0x140039dd8  call    cs:__imp_ExAllocatePool2
0x140039ddf  nop     dword ptr [rax+rax+00h]
0x140039de4  mov     [rsp+1B8h+var_148], rax
0x140039de9  mov     [rsp+1B8h+var_118], rax
0x140039df1  mov     [r12+18h], rax
0x140039df6  add     rax, 60h ; '`'
0x140039dfa  mov     [rsp+1B8h+var_100], rax
0x140039e02  mov     r8d, r14d; Size
0x140039e05  mov     rdx, [rsp+1B8h+Src]; Src
0x140039e0d  mov     rcx, rax; void *
0x140039e10  cmp     [r12+40h], dil
0x140039e15  jz      short loc_140039E1E
0x140039e17  call    RtlCopyFromUser
0x140039e1c  jmp     short loc_140039E23
  ... truncated ...
```
