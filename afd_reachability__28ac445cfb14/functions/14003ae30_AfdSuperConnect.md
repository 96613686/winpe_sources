# AfdSuperConnect

- ea: `0x14003ae30`
- end: `0x14003b8f8`
- name: `AfdSuperConnect`
- size: `2760`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140002440`
- `0x140005b60`
- `0x14000cbe0`
- `0x14000d4b0`
- `0x14000dc90`
- `0x140010eb0`
- `0x140012610`
- `0x140019190`
- `0x1400191f0`
- `0x14001adf0`
- `0x14001b248`
- `0x14001c708`
- `0x140026e80`
- `0x14002fd5c`
- `0x140030950`
- `0x140036ca4`
- `0x140039198`
- `0x14003ae30`
- `0x1400445b8`
- `0x1400486b8`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072780`
- `0x140072800`
- `0x140072b00`
- `0x140093008`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003b077`
- `ntoskrnl!ExRaiseStatus` at `0x14003b096`
- `ntoskrnl!ExRaiseStatus` at `0x14003b843`
- `ntoskrnl!ExRaiseStatus` at `0x14003b077`
- `ntoskrnl!ExRaiseStatus` at `0x14003b096`
- `ntoskrnl!ExRaiseStatus` at `0x14003b843`
- `ntoskrnl!ProbeForRead` at `0x14003af01`
- `ntoskrnl!ProbeForRead` at `0x14003af21`
- `ntoskrnl!ProbeForRead` at `0x14003af01`
- `ntoskrnl!ProbeForRead` at `0x14003af21`
- `ntoskrnl!ObfReferenceObject` at `0x14003b58f`
- `ntoskrnl!ObfReferenceObject` at `0x14003b812`
- `ntoskrnl!ObfReferenceObject` at `0x14003b58f`
- `ntoskrnl!ObfReferenceObject` at `0x14003b812`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003af47`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003af47`
- `ntoskrnl!IofCompleteRequest` at `0x14003b8bb`
- `ntoskrnl!IofCompleteRequest` at `0x14003b8bb`
- `ntoskrnl!IofCallDriver` at `0x14003b82d`
- `ntoskrnl!IofCallDriver` at `0x14003b82d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b567`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b654`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b6e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b567`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b654`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b6e8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b54b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b639`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b6ba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b54b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b639`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b6ba`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003afa2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003afa2`

## pseudocode

```c
NTSTATUS __fastcall AfdSuperConnect(PIRP Irp, __int64 a2)
{
  ADDRESS_FAMILY **Buffer; // r14
  __int64 v5; // rdi
  SIZE_T v6; // rax
  __int64 v7; // rdx
  NTSTATUS v8; // r15d
  unsigned int v9; // eax
  char *v10; // rsi
  HANDLE CurrentProcessId; // rax
  int v12; // eax
  int v13; // eax
  void *v14; // rdx
  ADDRESS_FAMILY *v15; // rcx
  __int64 v16; // r9
  int v17; // eax
  void *v18; // rdx
  ADDRESS_FAMILY *v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // eax
  PVOID UserBuffer; // rdx
  ADDRESS_FAMILY *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  ADDRESS_FAMILY **v26; // rsi
  __int64 v27; // r15
  ADDRESS_FAMILY *v28; // rdx
  unsigned __int64 v29; // rcx
  __int64 (__fastcall **v30)(); // rax
  __int64 v31; // rcx
  signed __int64 v32; // rax
  bool v33; // cc
  signed __int64 v34; // rax
  __int64 v35; // r8
  signed __int64 v36; // rax
  signed __int64 v37; // rax
  struct _UNICODE_STRING *v38; // r8
  ADDRESS_FAMILY *v39; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v41; // rdx
  ADDRESS_FAMILY *v43; // [rsp+48h] [rbp-190h] BYREF
  ADDRESS_FAMILY **v44; // [rsp+50h] [rbp-188h] BYREF
  __int64 v45; // [rsp+58h] [rbp-180h]
  ADDRESS_FAMILY **v46; // [rsp+60h] [rbp-178h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-168h] BYREF
  __int64 v48; // [rsp+88h] [rbp-150h]
  PIRP v49; // [rsp+90h] [rbp-148h]
  __int64 v50; // [rsp+98h] [rbp-140h]
  ADDRESS_FAMILY *v51; // [rsp+A0h] [rbp-138h]
  _QWORD v52[16]; // [rsp+B0h] [rbp-128h] BYREF
  _QWORD v53[12]; // [rsp+130h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+190h] [rbp-48h] BYREF
  int v55; // [rsp+198h] [rbp-40h]
  char v56; // [rsp+19Ch] [rbp-3Ch]

  v45 = a2;
  v49 = Irp;
  v44 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  Buffer = 0;
  v46 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v50 = v5;
  v6 = *(unsigned int *)(a2 + 16);
  if ( (unsigned int)v6 < 0xC )
  {
    v7 = 5025;
LABEL_3:
    v8 = -1073741811;
    AFDETW_TRACECONNECTEX(0, v7, v5, 0, 0, -1073741811, 0);
LABEL_120:
    if ( Buffer )
      AfdReturnBuffer(Buffer, *(PEPROCESS *)(v5 + 48));
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v8;
LABEL_123:
    IofCompleteRequest(Irp, AfdPriorityBoost);
    return v8;
  }
  v48 = v5;
  if ( Irp->RequestorMode )
  {
    ProbeForRead(*(volatile void **)(a2 + 32), v6, 4u);
    v9 = *(_DWORD *)(a2 + 8);
    if ( v9 )
      ProbeForRead(Irp->UserBuffer, v9, 1u);
  }
  v10 = *(char **)(a2 + 32);
  if ( Irp->RequestorMode )
  {
    if ( ((unsigned __int8)v10 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v54, v10, 0x10u);
  }
  else
  {
    RtlCopyVolatileMemory(&v54, v10, 0x10u);
  }
  if ( !(_BYTE)v54 && AfdSanServiceHelper )
  {
    if ( SBYTE8(xmmword_1400875E0) < 0 )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      WPP_SF_q(1287, 16, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, CurrentProcessId);
    }
    AFDETW_TRACECONNECTEX(0, 5026, v5, 0, 0, -1073741574, 0);
    v8 = -1073741574;
    goto LABEL_120;
  }
  Buffer = (ADDRESS_FAMILY **)AfdGetBuffer(*(unsigned int *)(v45 + 8));
  v46 = Buffer;
  v43 = Buffer[5];
  v51 = v43;
  v12 = *(_DWORD *)(v45 + 16);
  if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
  {
    v13 = v12 - 10;
    *((_DWORD *)Buffer + 8) = v13;
    v14 = v10 + 10;
    v15 = Buffer[5];
    if ( Irp->RequestorMode )
      RtlCopyFromUser(v15, v14, v13);
    else
      RtlCopyVolatileMemory(v15, v14, v13);
    if ( *v43 >= 0x23u )
      ExRaiseStatus(-1073741503);
    if ( *((_DWORD *)Buffer + 8) < (int)SOCKADDR_SIZE(*v43) )
      ExRaiseStatus(-1073741503);
  }
  else
  {
    v17 = v12 - 4;
    *((_DWORD *)Buffer + 8) = v17;
    v18 = v10 + 4;
    v19 = Buffer[5];
    if ( Irp->RequestorMode )
      RtlCopyFromUser(v19, v18, v17);
    else
      RtlCopyVolatileMemory(v19, v18, v17);
    if ( *(_DWORD *)v43 != 1 || *((_DWORD *)Buffer + 8) < v43[2] + 8 )
      ExRaiseStatus(-1073741811);
  }
  v20 = v45;
  v21 = *(_DWORD *)(v45 + 8);
  if ( v21 )
  {
    UserBuffer = Irp->UserBuffer;
    v23 = Buffer[14];
    if ( Irp->RequestorMode )
      RtlCopyFromUser(v23, UserBuffer, v21);
    else
      RtlCopyVolatileMemory(v23, UserBuffer, v21);
    v20 = v45;
    *((_DWORD *)Buffer + 16) = *(_DWORD *)(v45 + 8);
  }
  else
  {
    *((_DWORD *)Buffer + 16) = 0;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), 4, 0) )
  {
    v7 = 5028;
    goto LABEL_3;
  }
  if ( (*(_BYTE *)(v5 + 6) & 1) != 0 )
  {
    v8 = -1073741811;
    AFDETW_TRACECONNECTEX(0, 5033, v5, 0, 0, -1073741811, 0);
LABEL_50:
    _InterlockedExchange((volatile __int32 *)(v5 + 368), 0);
    goto LABEL_120;
  }
  if ( *(_WORD *)v5 != 0xAFD0
    || *(_BYTE *)(v5 + 2) != 3
    || (*(_DWORD *)(v5 + 8) & 1) != 0
    || (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x200) != 0 && *(_DWORD *)(v20 + 8) )
  {
    v8 = -1073741253;
    if ( *(_BYTE *)(v5 + 2) != 4 )
      v8 = -1073741811;
    v24 = 5029;
    goto LABEL_49;
  }
  if ( (xmmword_1400875E0 & 0x80u) != 0LL )
    WPP_SF_q(1031, 17, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, v5);
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0
    && (*(_DWORD *)(v5 + 8) & 0x400000) != 0
    && (unsigned __int8)AfdTdi_IsTA6V4Mapped(v43, *((unsigned int *)Buffer + 8)) )
  {
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 || (LOBYTE(v16) = 1, (*(_DWORD *)(v5 + 16) & 0x200) == 0) )
      LOBYTE(v16) = 0;
    v25 = AfdCreateConnection(
            v5,
            *(_QWORD *)(*(_QWORD *)(v5 + 280) + 24LL),
            **(_QWORD **)(v5 + 280),
            v16,
            (*(_DWORD *)(v5 + 8) >> 8) & 1,
            (*(_DWORD *)(v5 + 8) >> 7) & 1,
            *(_QWORD *)(v5 + 48),
            &v44);
    v8 = v25;
    v26 = v44;
    if ( v25 < 0 )
      goto LABEL_66;
    *((_DWORD *)v44 + 1) |= 2u;
  }
  else
  {
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 || (LOBYTE(v16) = 1, (*(_DWORD *)(v5 + 16) & 0x200) == 0) )
      LOBYTE(v16) = 0;
    v25 = AfdCreateConnection(
            v5,
            *(_QWORD *)(v5 + 272),
            *(_QWORD *)(v5 + 256),
            v16,
            (*(_DWORD *)(v5 + 8) >> 8) & 1,
            (*(_DWORD *)(v5 + 8) >> 7) & 1,
            *(_QWORD *)(v5 + 48),
            &v44);
    v8 = v25;
    v26 = v44;
  }
  if ( v25 < 0 )
  {
LABEL_66:
    v24 = 5030;
LABEL_49:
    AFDETW_TRACECONNECTEX(0, v24, v5, 0, 0, v8, 0);
    goto LABEL_50;
  }
  if ( (*(_DWORD *)(v5 + 8) & 0x200000) != 0 )
    *((_DWORD *)v26 + 1) |= 2u;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 64)) <= 1 )
    __fastfail(0xEu);
  v26[1] = (ADDRESS_FAMILY *)v5;
  AFDETW_TRACECONNECTEX(0, 5031, v5, Buffer[14], *((_DWORD *)Buffer + 16), 0, Buffer[5]);
  *(_QWORD *)(v5 + 192) = v26;
  *(_WORD *)v5 = -20526;
  v8 = AfdAddConnectedReference(v26);
  if ( v8 < 0 )
    goto LABEL_50;
  AfdEnableFailedConnectEvent(v5);
  v27 = AfdLockEndpointContext(v5);
  if ( *(unsigned __int16 *)(v5 + 184) + (unsigned int)*(unsigned __int16 *)(v5 + 186) >= *(_DWORD *)(v5 + 232) )
  {
    if ( SBYTE8(xmmword_1400875D0) < 0 )
      WPP_SF_qq(775, 18, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids, v5, *(_QWORD *)(v5 + 48));
  }
  else
  {
    if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
    {
      v28 = v43;
      LODWORD(v29) = *((_DWORD *)Buffer + 8);
      if ( *(unsigned __int16 *)(v5 + 186) < (int)v29 )
        LODWORD(v29) = *(unsigned __int16 *)(v5 + 186);
    }
    else
    {
      v28 = v43 + 3;
      v29 = v43[2] + 2LL;
      if ( *(unsigned __int16 *)(v5 + 186) < v29 )
        LODWORD(v29) = *(unsigned __int16 *)(v5 + 186);
    }
    memmove((void *)(v27 + *(unsigned __int16 *)(v5 + 184)), v28, (unsigned int)v29);
  }
  AfdUnlockEndpointContext(v5, v27);
  if ( _InterlockedIncrement64((volatile signed __int64 *)v26 + 6) <= 1 )
    __fastfail(0xEu);
  if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
  {
    memset(v52, 0, sizeof(v52));
    memset(v53, 0, 0x58u);
    Buffer[6] = (ADDRESS_FAMILY *)Irp;
    v52[0] = AfdTLSuperConnectComplete;
    v52[1] = Buffer;
    LODWORD(v52[2]) = -1610612736;
    v52[3] = *(_QWORD *)(v5 + 16);
    v52[11] = v43;
    v52[12] = AfdInfiniteTimeout;
    v52[9] = v26;
    v30 = AfdTlClientConnectDispatch;
    if ( (*(_BYTE *)(v5 + 7) & 0x10) != 0 )
      v30 = AfdRioTlClientConnectDispatch;
    v52[14] = v30;
    if ( *((_DWORD *)Buffer + 16) )
    {
      v53[0] = AfdTLBufferedSendComplete;
      v53[2] = Buffer;
      LODWORD(v53[3]) = 0;
      v53[4] = Buffer[7];
      v53[6] = *((unsigned int *)Buffer + 16);
      v53[7] = Buffer;
      if ( _InterlockedIncrement64((volatile signed __int64 *)v26 + 6) <= 1 )
        __fastfail(0xEu);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
      *((_DWORD *)v26 + 30) += *((_DWORD *)Buffer + 16);
      ++*((_DWORD *)v26 + 31);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      *((_DWORD *)Buffer[7] + 10) = *((_DWORD *)Buffer + 16);
      Irp->IoStatus.Information = *((unsigned int *)Buffer + 16);
    }
    ObfReferenceObject(*(PVOID *)(v45 + 48));
    Irp->Tail.Overlay.DriverContext[2] = 0;
    if ( !(unsigned __int8)AfdRefTLBaseEndpoint(v5) )
    {
      v8 = -1073741816;
      goto LABEL_105;
    }
    v31 = *(_QWORD *)(v5 + 272);
    if ( *((_DWORD *)Buffer + 16) )
    {
      if ( *(_WORD *)(v31 + 20) < 2u )
        v8 = -1073741267;
      else
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD *))(*(_QWORD *)(v31 + 40) + 64LL))(
               *(_QWORD *)(v31 + 32),
               v52,
               v53);
      if ( v8 != -1073741267 )
      {
LABEL_104:
        AfdDerefTLBaseEndpoint(v5);
        if ( v8 == 259 )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
          if ( !v26[3] && (*((_DWORD *)v26 + 1) & 0x10) == 0 )
          {
            v26[3] = (ADDRESS_FAMILY *)v52[13];
            *((_DWORD *)v26 + 1) |= 8u;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          LOBYTE(v35) = 1;
          if ( (unsigned __int8)AfdTLPendRequest(Irp, v52[13], v35) )
            return v8;
          goto LABEL_110;
        }
LABEL_105:
        AfdTLSuperConnectComplete(Buffer);
LABEL_110:
        v36 = _InterlockedExchangeAdd64((volatile signed __int64 *)v26 + 6, 0xFFFFFFFFFFFFFFFFuLL);
        v33 = v36 <= 1;
        v37 = v36 - 1;
        if ( v33 )
        {
          if ( v37 )
            __fastfail(0xEu);
          AfdCloseConnection(v26);
        }
        goto LABEL_123;
      }
      v32 = _InterlockedExchangeAdd64((volatile signed __int64 *)v26 + 6, 0xFFFFFFFFFFFFFFFFuLL);
      v33 = v32 <= 1;
      v34 = v32 - 1;
      if ( v33 )
      {
        if ( v34 )
          __fastfail(0xEu);
        AfdCloseConnection(v26);
      }
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
      *((_DWORD *)v26 + 30) -= *((_DWORD *)Buffer + 16);
      --*((_DWORD *)v26 + 31);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v31 = *(_QWORD *)(v5 + 272);
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v31 + 40) + 40LL))(*(_QWORD *)(v31 + 32), v52);
    goto LABEL_104;
  }
  if ( (*((_DWORD *)v26 + 1) & 2) != 0 )
    AfdTdi_TA6toTA4_InPlace(Buffer[5], Buffer + 4);
  v38 = (struct _UNICODE_STRING *)Buffer;
  v44 = Buffer;
  *(_DWORD *)Buffer = 0;
  Buffer[1] = 0;
  *((_DWORD *)Buffer + 4) = 0;
  Buffer[3] = 0;
  v39 = (ADDRESS_FAMILY *)(*((_QWORD *)Buffer[13] + 23) - 72LL);
  v43 = v39;
  *(_OWORD *)v39 = 0;
  *((_OWORD *)v39 + 1) = 0;
  *((_OWORD *)v39 + 2) = 0;
  if ( *(_QWORD *)(v5 + 208) )
  {
    AfdSetupConnectDataBuffers(v5, v26, &v44, &v43);
    v38 = (struct _UNICODE_STRING *)v44;
    v39 = v43;
  }
  Buffer[6] = (ADDRESS_FAMILY *)v26;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartSuperConnect;
  CurrentStackLocation[-1].Context = Buffer;
  CurrentStackLocation[-1].Control = -32;
  v41 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v41[-1].MajorFunction = 783;
  v41[-1].DeviceObject = (PDEVICE_OBJECT)v26[3];
  v41[-1].FileObject = (PFILE_OBJECT)v26[2];
  v41[-1].Parameters.QueryDirectory.FileName = v38;
  v41[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)v39;
  v41[-1].Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)&AfdInfiniteTimeout;
  ObfReferenceObject(*(PVOID *)(v45 + 48));
  _InterlockedAdd((volatile signed __int32 *)(v5 + 248), 1u);
  return IofCallDriver((PDEVICE_OBJECT)v26[3], Irp);
}

```

## disassembly

```asm
0x14003ae30  mov     r11, rsp
0x14003ae33  mov     [r11+18h], rbx
0x14003ae37  mov     [r11+20h], rsi
0x14003ae3b  push    rdi
0x14003ae3c  push    r12
0x14003ae3e  push    r13
0x14003ae40  push    r14
0x14003ae42  push    r15
0x14003ae44  sub     rsp, 1B0h
0x14003ae4b  mov     rax, cs:__security_cookie
0x14003ae52  xor     rax, rsp
0x14003ae55  mov     [rsp+1D8h+var_38], rax
0x14003ae5d  mov     rsi, rdx
0x14003ae60  mov     [rsp+1D8h+var_180], rdx
0x14003ae65  mov     r13, rcx
0x14003ae68  mov     [rsp+1D8h+var_148], rcx
0x14003ae70  xor     ebx, ebx
0x14003ae72  mov     [rsp+1D8h+var_188], rbx
0x14003ae77  xor     eax, eax
0x14003ae79  mov     [r11-48h], rax
0x14003ae7d  mov     [r11-40h], eax
0x14003ae81  mov     [r11-3Ch], al
0x14003ae85  xorps   xmm0, xmm0
0x14003ae88  movups  xmmword ptr [rsp+1D8h+LockHandle.LockQueue.Next], xmm0
0x14003ae8d  mov     [r11-158h], rax
0x14003ae94  mov     r14d, ebx
0x14003ae97  mov     [rsp+1D8h+var_178], rbx
0x14003ae9c  mov     rax, [rdx+30h]
0x14003aea0  mov     rdi, [rax+18h]
0x14003aea4  mov     [rsp+1D8h+var_140], rdi
0x14003aeac  mov     eax, [rdx+10h]
0x14003aeaf  cmp     eax, 0Ch
0x14003aeb2  jnb     short loc_14003AEE0
0x14003aeb4  mov     edx, 13A1h
0x14003aeb9  mov     [rsp+1D8h+var_1A8], rbx
0x14003aebe  mov     ecx, 0C000000Dh
0x14003aec3  mov     [rsp+1D8h+var_1B0], ecx
0x14003aec7  mov     r8, rdi
0x14003aeca  xor     r9d, r9d
0x14003aecd  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003aed1  mov     r15d, ecx
0x14003aed4  xor     ecx, ecx
0x14003aed6  call    AFDETW_TRACECONNECTEX
0x14003aedb  jmp     loc_14003B899
0x14003aee0  mov     [rsp+1D8h+var_150], rdi
0x14003aee8  mov     [rsp+1D8h+var_198], ebx
0x14003aeec  mov     r15d, 4
0x14003aef2  cmp     [rcx+40h], bl
0x14003aef5  jz      short loc_14003AF2F
0x14003aef7  mov     rdx, rax; Length
0x14003aefa  mov     r8d, r15d; Alignment
0x14003aefd  mov     rcx, [rsi+20h]; Address
0x14003af01  call    cs:__imp_ProbeForRead
0x14003af08  nop     dword ptr [rax+rax+00h]
0x14003af0d  mov     eax, [rsi+8]
0x14003af10  lea     r12d, [r15-3]
0x14003af14  test    eax, eax
0x14003af16  jz      short loc_14003AF35
0x14003af18  mov     edx, eax; Length
0x14003af1a  mov     r8d, r12d; Alignment
0x14003af1d  mov     rcx, [r13+70h]; Address
0x14003af21  call    cs:__imp_ProbeForRead
0x14003af28  nop     dword ptr [rax+rax+00h]
0x14003af2d  jmp     short loc_14003AF35
0x14003af2f  mov     r12d, 1
0x14003af35  mov     rsi, [rsi+20h]
0x14003af39  mov     al, [r13+40h]
0x14003af3d  test    al, al
0x14003af3f  jz      short loc_14003AF6F
0x14003af41  test    sil, 3
0x14003af45  jz      short loc_14003AF53
0x14003af47  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14003af4e  nop     dword ptr [rax+rax+00h]
0x14003af53  test    al, al
0x14003af55  jz      short loc_14003AF6F
0x14003af57  mov     r8d, 10h; Size
0x14003af5d  mov     rdx, rsi; Src
0x14003af60  lea     rcx, [rsp+1D8h+var_48]; void *
0x14003af68  call    RtlCopyFromUser
0x14003af6d  jmp     short loc_14003AF85
0x14003af6f  mov     r8d, 10h; Size
0x14003af75  mov     rdx, rsi; Src
0x14003af78  lea     rcx, [rsp+1D8h+var_48]; void *
0x14003af80  call    RtlCopyVolatileMemory
0x14003af85  cmp     byte ptr [rsp+1D8h+var_48], bl
0x14003af8c  jnz     short loc_14003AFFC
0x14003af8e  cmp     cs:AfdSanServiceHelper, 0
0x14003af96  jz      short loc_14003AFFC
0x14003af98  mov     al, byte ptr cs:xmmword_1400875E0+8
0x14003af9e  test    al, al
0x14003afa0  jns     short loc_14003AFC7
0x14003afa2  call    cs:__imp_PsGetCurrentProcessId
0x14003afa9  nop     dword ptr [rax+rax+00h]
0x14003afae  mov     r9, rax
0x14003afb1  mov     edx, 10h
0x14003afb6  mov     ecx, 507h
0x14003afbb  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14003afc2  call    WPP_SF_q
0x14003afc7  mov     [rsp+1D8h+var_198], 0C00000FAh
0x14003afcf  mov     [rsp+1D8h+var_1A8], rbx
0x14003afd4  mov     eax, [rsp+1D8h+var_198]
0x14003afd8  mov     [rsp+1D8h+var_1B0], eax
0x14003afdc  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003afe0  xor     r9d, r9d
0x14003afe3  mov     r8, rdi
0x14003afe6  mov     edx, 13A2h
0x14003afeb  xor     ecx, ecx
0x14003afed  call    AFDETW_TRACECONNECTEX
0x14003aff2  mov     r15d, [rsp+1D8h+var_198]
0x14003aff7  jmp     loc_14003B899
0x14003affc  mov     rax, [rsp+1D8h+var_180]
0x14003b001  mov     edx, [rax+10h]
0x14003b004  sub     edx, r15d
0x14003b007  mov     r9d, r12d
0x14003b00a  mov     r8, [rdi+30h]
0x14003b00e  mov     ecx, [rax+8]; Length
0x14003b011  call    AfdGetBuffer
0x14003b016  mov     r14, rax
0x14003b019  mov     [rsp+1D8h+var_178], rax
0x14003b01e  mov     rax, [rax+28h]
0x14003b022  mov     [rsp+1D8h+var_190], rax
0x14003b027  mov     [rsp+1D8h+var_138], rax
0x14003b02f  mov     ecx, [rdi+8]
0x14003b032  mov     rax, [rsp+1D8h+var_180]
0x14003b037  mov     eax, [rax+10h]
0x14003b03a  bt      ecx, 8
0x14003b03e  jnb     short loc_14003B0A2
0x14003b040  add     eax, 0FFFFFFF6h
0x14003b043  mov     [r14+20h], eax
0x14003b047  lea     rdx, [rsi+0Ah]; Src
0x14003b04b  mov     rcx, [r14+28h]; void *
0x14003b04f  movsxd  r8, eax; Size
0x14003b052  cmp     [r13+40h], bl
0x14003b056  jz      short loc_14003B05F
0x14003b058  call    RtlCopyFromUser
0x14003b05d  jmp     short loc_14003B064
0x14003b05f  call    RtlCopyVolatileMemory
0x14003b064  mov     rcx, [rsp+1D8h+var_190]
0x14003b069  movzx   ecx, word ptr [rcx]; af
0x14003b06c  cmp     cx, 23h ; '#'
0x14003b070  jb      short loc_14003B083
0x14003b072  mov     ecx, 0C0000141h; Status
0x14003b077  call    cs:__imp_ExRaiseStatus
0x14003b083  call    SOCKADDR_SIZE
0x14003b088  movzx   edx, al
0x14003b08b  cmp     [r14+20h], edx
0x14003b08f  jge     short loc_14003B0E5
0x14003b091  mov     ecx, 0C0000141h; Status
0x14003b096  call    cs:__imp_ExRaiseStatus
0x14003b0a2  add     eax, 0FFFFFFFCh
0x14003b0a5  mov     [r14+20h], eax
0x14003b0a9  lea     rdx, [rsi+4]; Src
0x14003b0ad  mov     rcx, [r14+28h]; void *
0x14003b0b1  movsxd  r8, eax; Size
0x14003b0b4  cmp     [r13+40h], bl
0x14003b0b8  jz      short loc_14003B0C1
0x14003b0ba  call    RtlCopyFromUser
0x14003b0bf  jmp     short loc_14003B0C6
0x14003b0c1  call    RtlCopyVolatileMemory
0x14003b0c6  mov     rax, [rsp+1D8h+var_190]
0x14003b0cb  cmp     [rax], r12d
0x14003b0ce  jnz     loc_14003B83E
0x14003b0d4  movzx   eax, word ptr [rax+4]
0x14003b0d8  add     eax, 8
0x14003b0db  cmp     [r14+20h], eax
0x14003b0df  jl      loc_14003B83E
0x14003b0e5  mov     rcx, [rsp+1D8h+var_180]
0x14003b0ea  mov     eax, [rcx+8]
0x14003b0ed  test    eax, eax
0x14003b0ef  jz      short loc_14003B11C
0x14003b0f1  mov     rdx, [r13+70h]; Src
0x14003b0f5  mov     rcx, [r14+70h]; void *
0x14003b0f9  mov     r8d, eax; Size
0x14003b0fc  cmp     [r13+40h], bl
0x14003b100  jz      short loc_14003B109
0x14003b102  call    RtlCopyFromUser
0x14003b107  jmp     short loc_14003B10E
0x14003b109  call    RtlCopyVolatileMemory
0x14003b10e  mov     rcx, [rsp+1D8h+var_180]
0x14003b113  mov     eax, [rcx+8]
0x14003b116  mov     [r14+40h], eax
0x14003b11a  jmp     short loc_14003B120
0x14003b11c  mov     [r14+40h], ebx
0x14003b120  xor     eax, eax
0x14003b122  lock cmpxchg [rdi+170h], r15d
0x14003b12b  jz      short loc_14003B137
0x14003b12d  mov     edx, 13A4h
0x14003b132  jmp     loc_14003AEB9
0x14003b137  test    [rdi+6], r12b
0x14003b13b  jz      short loc_14003B155
0x14003b13d  mov     ecx, 0C000000Dh
0x14003b142  mov     r15d, ecx
0x14003b145  mov     [rsp+1D8h+var_1A8], rbx
0x14003b14a  mov     [rsp+1D8h+var_1B0], ecx
0x14003b14e  mov     edx, 13A9h
0x14003b153  jmp     short loc_14003B1B0
0x14003b155  mov     eax, 0AFD0h
0x14003b15a  cmp     [rdi], ax
0x14003b15d  jnz     short loc_14003B18E
0x14003b15f  cmp     byte ptr [rdi+2], 3
0x14003b163  jnz     short loc_14003B18E
0x14003b165  mov     eax, [rdi+8]
0x14003b168  test    r12b, al
0x14003b16b  jnz     short loc_14003B18E
0x14003b16d  mov     eax, [rdi+8]
0x14003b170  bt      eax, 8
0x14003b174  jb      short loc_14003B1CE
0x14003b176  mov     eax, [rdi+8]
0x14003b179  bt      eax, 8
0x14003b17d  jb      short loc_14003B1CE
0x14003b17f  mov     esi, 200h
0x14003b184  test    [rdi+10h], esi
0x14003b187  jz      short loc_14003B1D3
0x14003b189  cmp     [rcx+8], ebx
0x14003b18c  jz      short loc_14003B1D3
0x14003b18e  mov     ecx, 0C000000Dh
0x14003b193  mov     r15d, 0C000023Bh
0x14003b199  cmp     byte ptr [rdi+2], 4
0x14003b19d  cmovnz  r15d, ecx
0x14003b1a1  mov     edx, 13A5h
0x14003b1a6  mov     [rsp+1D8h+var_1A8], rbx
0x14003b1ab  mov     [rsp+1D8h+var_1B0], r15d
0x14003b1b0  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003b1b4  xor     r9d, r9d
0x14003b1b7  mov     r8, rdi
0x14003b1ba  xor     ecx, ecx
0x14003b1bc  call    AFDETW_TRACECONNECTEX
0x14003b1c1  mov     eax, ebx
0x14003b1c3  xchg    eax, [rdi+170h]
0x14003b1c9  jmp     loc_14003B899
0x14003b1ce  mov     esi, 200h
0x14003b1d3  mov     al, byte ptr cs:xmmword_1400875E0
0x14003b1d9  test    al, al
0x14003b1db  jns     short loc_14003B1F6
0x14003b1dd  mov     edx, 11h
0x14003b1e2  mov     ecx, 407h
0x14003b1e7  mov     r9, rdi
0x14003b1ea  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14003b1f1  call    WPP_SF_q
0x14003b1f6  mov     eax, [rdi+8]
0x14003b1f9  bt      eax, 8
0x14003b1fd  jb      loc_14003B28B
0x14003b203  mov     eax, [rdi+8]
0x14003b206  bt      eax, 16h
0x14003b20a  jnb     short loc_14003B28B
0x14003b20c  mov     edx, [r14+20h]
0x14003b210  mov     rcx, [rsp+1D8h+var_190]
0x14003b215  call    AfdTdi_IsTA6V4Mapped
0x14003b21a  test    al, al
0x14003b21c  jz      short loc_14003B28B
0x14003b21e  mov     eax, [rdi+8]
0x14003b221  bt      eax, 8
0x14003b225  jb      short loc_14003B22F
0x14003b227  test    [rdi+10h], esi
0x14003b22a  mov     r9b, r12b
0x14003b22d  jnz     short loc_14003B232
0x14003b22f  mov     r9b, bl
0x14003b232  mov     eax, [rdi+8]
0x14003b235  mov     ecx, [rdi+8]
0x14003b238  mov     rdx, [rdi+118h]
0x14003b23f  shr     eax, 7
0x14003b242  and     eax, r12d
0x14003b245  shr     ecx, 8
0x14003b248  and     ecx, r12d
0x14003b24b  lea     r8, [rsp+1D8h+var_188]
0x14003b250  mov     [rsp+1D8h+var_1A0], r8
0x14003b255  mov     r8, [rdi+30h]
0x14003b259  mov     [rsp+1D8h+var_1A8], r8
0x14003b25e  mov     [rsp+1D8h+var_1B0], eax
0x14003b262  mov     dword ptr [rsp+1D8h+var_1B8], ecx
0x14003b266  mov     r8, [rdx]
0x14003b269  mov     rdx, [rdx+18h]
0x14003b26d  mov     rcx, rdi
0x14003b270  call    AfdCreateConnection
0x14003b275  mov     r15d, eax
0x14003b278  mov     rsi, [rsp+1D8h+var_188]
0x14003b27d  mov     ecx, 2
0x14003b282  test    eax, eax
0x14003b284  js      short loc_14003B2F3
0x14003b286  or      [rsi+4], ecx
0x14003b289  jmp     short loc_14003B2EF
0x14003b28b  mov     eax, [rdi+8]
0x14003b28e  bt      eax, 8
0x14003b292  jb      short loc_14003B29C
0x14003b294  test    [rdi+10h], esi
0x14003b297  mov     r9b, r12b
0x14003b29a  jnz     short loc_14003B29F
0x14003b29c  mov     r9b, bl
0x14003b29f  mov     eax, [rdi+8]
0x14003b2a2  mov     ecx, [rdi+8]
0x14003b2a5  shr     eax, 7
0x14003b2a8  and     eax, r12d
0x14003b2ab  shr     ecx, 8
0x14003b2ae  and     ecx, r12d
0x14003b2b1  lea     rdx, [rsp+1D8h+var_188]
0x14003b2b6  mov     [rsp+1D8h+var_1A0], rdx
0x14003b2bb  mov     rdx, [rdi+30h]
0x14003b2bf  mov     [rsp+1D8h+var_1A8], rdx
0x14003b2c4  mov     [rsp+1D8h+var_1B0], eax
0x14003b2c8  mov     dword ptr [rsp+1D8h+var_1B8], ecx
  ... truncated ...
```
