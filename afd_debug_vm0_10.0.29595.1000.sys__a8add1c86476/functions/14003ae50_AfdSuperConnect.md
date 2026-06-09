# AfdSuperConnect

- ea: `0x14003ae50`
- end: `0x14003b918`
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
- `0x14002fd7c`
- `0x140030970`
- `0x140036cc4`
- `0x1400391b8`
- `0x14003ae50`
- `0x1400445d8`
- `0x140048738`
- `0x140072840`
- `0x140072870`
- `0x140072920`
- `0x140072980`
- `0x140072c80`
- `0x140093008`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14003b097`
- `ntoskrnl!ExRaiseStatus` at `0x14003b0b6`
- `ntoskrnl!ExRaiseStatus` at `0x14003b863`
- `ntoskrnl!ExRaiseStatus` at `0x14003b097`
- `ntoskrnl!ExRaiseStatus` at `0x14003b0b6`
- `ntoskrnl!ExRaiseStatus` at `0x14003b863`
- `ntoskrnl!ProbeForRead` at `0x14003af21`
- `ntoskrnl!ProbeForRead` at `0x14003af41`
- `ntoskrnl!ProbeForRead` at `0x14003af21`
- `ntoskrnl!ProbeForRead` at `0x14003af41`
- `ntoskrnl!ObfReferenceObject` at `0x14003b5af`
- `ntoskrnl!ObfReferenceObject` at `0x14003b832`
- `ntoskrnl!ObfReferenceObject` at `0x14003b5af`
- `ntoskrnl!ObfReferenceObject` at `0x14003b832`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003af67`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003af67`
- `ntoskrnl!IofCompleteRequest` at `0x14003b8db`
- `ntoskrnl!IofCompleteRequest` at `0x14003b8db`
- `ntoskrnl!IofCallDriver` at `0x14003b84d`
- `ntoskrnl!IofCallDriver` at `0x14003b84d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b587`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b674`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b708`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b587`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b674`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b708`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b56b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b659`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b6da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b56b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b659`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b6da`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003afc2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003afc2`

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
0x14003ae50  mov     r11, rsp
0x14003ae53  mov     [r11+18h], rbx
0x14003ae57  mov     [r11+20h], rsi
0x14003ae5b  push    rdi
0x14003ae5c  push    r12
0x14003ae5e  push    r13
0x14003ae60  push    r14
0x14003ae62  push    r15
0x14003ae64  sub     rsp, 1B0h
0x14003ae6b  mov     rax, cs:__security_cookie
0x14003ae72  xor     rax, rsp
0x14003ae75  mov     [rsp+1D8h+var_38], rax
0x14003ae7d  mov     rsi, rdx
0x14003ae80  mov     [rsp+1D8h+var_180], rdx
0x14003ae85  mov     r13, rcx
0x14003ae88  mov     [rsp+1D8h+var_148], rcx
0x14003ae90  xor     ebx, ebx
0x14003ae92  mov     [rsp+1D8h+var_188], rbx
0x14003ae97  xor     eax, eax
0x14003ae99  mov     [r11-48h], rax
0x14003ae9d  mov     [r11-40h], eax
0x14003aea1  mov     [r11-3Ch], al
0x14003aea5  xorps   xmm0, xmm0
0x14003aea8  movups  xmmword ptr [rsp+1D8h+LockHandle.LockQueue.Next], xmm0
0x14003aead  mov     [r11-158h], rax
0x14003aeb4  mov     r14d, ebx
0x14003aeb7  mov     [rsp+1D8h+var_178], rbx
0x14003aebc  mov     rax, [rdx+30h]
0x14003aec0  mov     rdi, [rax+18h]
0x14003aec4  mov     [rsp+1D8h+var_140], rdi
0x14003aecc  mov     eax, [rdx+10h]
0x14003aecf  cmp     eax, 0Ch
0x14003aed2  jnb     short loc_14003AF00
0x14003aed4  mov     edx, 13A1h
0x14003aed9  mov     [rsp+1D8h+var_1A8], rbx
0x14003aede  mov     ecx, 0C000000Dh
0x14003aee3  mov     [rsp+1D8h+var_1B0], ecx
0x14003aee7  mov     r8, rdi
0x14003aeea  xor     r9d, r9d
0x14003aeed  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003aef1  mov     r15d, ecx
0x14003aef4  xor     ecx, ecx
0x14003aef6  call    AFDETW_TRACECONNECTEX
0x14003aefb  jmp     loc_14003B8B9
0x14003af00  mov     [rsp+1D8h+var_150], rdi
0x14003af08  mov     [rsp+1D8h+var_198], ebx
0x14003af0c  mov     r15d, 4
0x14003af12  cmp     [rcx+40h], bl
0x14003af15  jz      short loc_14003AF4F
0x14003af17  mov     rdx, rax; Length
0x14003af1a  mov     r8d, r15d; Alignment
0x14003af1d  mov     rcx, [rsi+20h]; Address
0x14003af21  call    cs:__imp_ProbeForRead
0x14003af28  nop     dword ptr [rax+rax+00h]
0x14003af2d  mov     eax, [rsi+8]
0x14003af30  lea     r12d, [r15-3]
0x14003af34  test    eax, eax
0x14003af36  jz      short loc_14003AF55
0x14003af38  mov     edx, eax; Length
0x14003af3a  mov     r8d, r12d; Alignment
0x14003af3d  mov     rcx, [r13+70h]; Address
0x14003af41  call    cs:__imp_ProbeForRead
0x14003af48  nop     dword ptr [rax+rax+00h]
0x14003af4d  jmp     short loc_14003AF55
0x14003af4f  mov     r12d, 1
0x14003af55  mov     rsi, [rsi+20h]
0x14003af59  mov     al, [r13+40h]
0x14003af5d  test    al, al
0x14003af5f  jz      short loc_14003AF8F
0x14003af61  test    sil, 3
0x14003af65  jz      short loc_14003AF73
0x14003af67  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14003af6e  nop     dword ptr [rax+rax+00h]
0x14003af73  test    al, al
0x14003af75  jz      short loc_14003AF8F
0x14003af77  mov     r8d, 10h; Size
0x14003af7d  mov     rdx, rsi; Src
0x14003af80  lea     rcx, [rsp+1D8h+var_48]; void *
0x14003af88  call    RtlCopyFromUser
0x14003af8d  jmp     short loc_14003AFA5
0x14003af8f  mov     r8d, 10h; Size
0x14003af95  mov     rdx, rsi; Src
0x14003af98  lea     rcx, [rsp+1D8h+var_48]; void *
0x14003afa0  call    RtlCopyVolatileMemory
0x14003afa5  cmp     byte ptr [rsp+1D8h+var_48], bl
0x14003afac  jnz     short loc_14003B01C
0x14003afae  cmp     cs:AfdSanServiceHelper, 0
0x14003afb6  jz      short loc_14003B01C
0x14003afb8  mov     al, byte ptr cs:xmmword_1400875E0+8
0x14003afbe  test    al, al
0x14003afc0  jns     short loc_14003AFE7
0x14003afc2  call    cs:__imp_PsGetCurrentProcessId
0x14003afc9  nop     dword ptr [rax+rax+00h]
0x14003afce  mov     r9, rax
0x14003afd1  mov     edx, 10h
0x14003afd6  mov     ecx, 507h
0x14003afdb  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14003afe2  call    WPP_SF_q
0x14003afe7  mov     [rsp+1D8h+var_198], 0C00000FAh
0x14003afef  mov     [rsp+1D8h+var_1A8], rbx
0x14003aff4  mov     eax, [rsp+1D8h+var_198]
0x14003aff8  mov     [rsp+1D8h+var_1B0], eax
0x14003affc  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003b000  xor     r9d, r9d
0x14003b003  mov     r8, rdi
0x14003b006  mov     edx, 13A2h
0x14003b00b  xor     ecx, ecx
0x14003b00d  call    AFDETW_TRACECONNECTEX
0x14003b012  mov     r15d, [rsp+1D8h+var_198]
0x14003b017  jmp     loc_14003B8B9
0x14003b01c  mov     rax, [rsp+1D8h+var_180]
0x14003b021  mov     edx, [rax+10h]
0x14003b024  sub     edx, r15d
0x14003b027  mov     r9d, r12d
0x14003b02a  mov     r8, [rdi+30h]
0x14003b02e  mov     ecx, [rax+8]; Length
0x14003b031  call    AfdGetBuffer
0x14003b036  mov     r14, rax
0x14003b039  mov     [rsp+1D8h+var_178], rax
0x14003b03e  mov     rax, [rax+28h]
0x14003b042  mov     [rsp+1D8h+var_190], rax
0x14003b047  mov     [rsp+1D8h+var_138], rax
0x14003b04f  mov     ecx, [rdi+8]
0x14003b052  mov     rax, [rsp+1D8h+var_180]
0x14003b057  mov     eax, [rax+10h]
0x14003b05a  bt      ecx, 8
0x14003b05e  jnb     short loc_14003B0C2
0x14003b060  add     eax, 0FFFFFFF6h
0x14003b063  mov     [r14+20h], eax
0x14003b067  lea     rdx, [rsi+0Ah]; Src
0x14003b06b  mov     rcx, [r14+28h]; void *
0x14003b06f  movsxd  r8, eax; Size
0x14003b072  cmp     [r13+40h], bl
0x14003b076  jz      short loc_14003B07F
0x14003b078  call    RtlCopyFromUser
0x14003b07d  jmp     short loc_14003B084
0x14003b07f  call    RtlCopyVolatileMemory
0x14003b084  mov     rcx, [rsp+1D8h+var_190]
0x14003b089  movzx   ecx, word ptr [rcx]; af
0x14003b08c  cmp     cx, 23h ; '#'
0x14003b090  jb      short loc_14003B0A3
0x14003b092  mov     ecx, 0C0000141h; Status
0x14003b097  call    cs:__imp_ExRaiseStatus
0x14003b0a3  call    SOCKADDR_SIZE
0x14003b0a8  movzx   edx, al
0x14003b0ab  cmp     [r14+20h], edx
0x14003b0af  jge     short loc_14003B105
0x14003b0b1  mov     ecx, 0C0000141h; Status
0x14003b0b6  call    cs:__imp_ExRaiseStatus
0x14003b0c2  add     eax, 0FFFFFFFCh
0x14003b0c5  mov     [r14+20h], eax
0x14003b0c9  lea     rdx, [rsi+4]; Src
0x14003b0cd  mov     rcx, [r14+28h]; void *
0x14003b0d1  movsxd  r8, eax; Size
0x14003b0d4  cmp     [r13+40h], bl
0x14003b0d8  jz      short loc_14003B0E1
0x14003b0da  call    RtlCopyFromUser
0x14003b0df  jmp     short loc_14003B0E6
0x14003b0e1  call    RtlCopyVolatileMemory
0x14003b0e6  mov     rax, [rsp+1D8h+var_190]
0x14003b0eb  cmp     [rax], r12d
0x14003b0ee  jnz     loc_14003B85E
0x14003b0f4  movzx   eax, word ptr [rax+4]
0x14003b0f8  add     eax, 8
0x14003b0fb  cmp     [r14+20h], eax
0x14003b0ff  jl      loc_14003B85E
0x14003b105  mov     rcx, [rsp+1D8h+var_180]
0x14003b10a  mov     eax, [rcx+8]
0x14003b10d  test    eax, eax
0x14003b10f  jz      short loc_14003B13C
0x14003b111  mov     rdx, [r13+70h]; Src
0x14003b115  mov     rcx, [r14+70h]; void *
0x14003b119  mov     r8d, eax; Size
0x14003b11c  cmp     [r13+40h], bl
0x14003b120  jz      short loc_14003B129
0x14003b122  call    RtlCopyFromUser
0x14003b127  jmp     short loc_14003B12E
0x14003b129  call    RtlCopyVolatileMemory
0x14003b12e  mov     rcx, [rsp+1D8h+var_180]
0x14003b133  mov     eax, [rcx+8]
0x14003b136  mov     [r14+40h], eax
0x14003b13a  jmp     short loc_14003B140
0x14003b13c  mov     [r14+40h], ebx
0x14003b140  xor     eax, eax
0x14003b142  lock cmpxchg [rdi+170h], r15d
0x14003b14b  jz      short loc_14003B157
0x14003b14d  mov     edx, 13A4h
0x14003b152  jmp     loc_14003AED9
0x14003b157  test    [rdi+6], r12b
0x14003b15b  jz      short loc_14003B175
0x14003b15d  mov     ecx, 0C000000Dh
0x14003b162  mov     r15d, ecx
0x14003b165  mov     [rsp+1D8h+var_1A8], rbx
0x14003b16a  mov     [rsp+1D8h+var_1B0], ecx
0x14003b16e  mov     edx, 13A9h
0x14003b173  jmp     short loc_14003B1D0
0x14003b175  mov     eax, 0AFD0h
0x14003b17a  cmp     [rdi], ax
0x14003b17d  jnz     short loc_14003B1AE
0x14003b17f  cmp     byte ptr [rdi+2], 3
0x14003b183  jnz     short loc_14003B1AE
0x14003b185  mov     eax, [rdi+8]
0x14003b188  test    r12b, al
0x14003b18b  jnz     short loc_14003B1AE
0x14003b18d  mov     eax, [rdi+8]
0x14003b190  bt      eax, 8
0x14003b194  jb      short loc_14003B1EE
0x14003b196  mov     eax, [rdi+8]
0x14003b199  bt      eax, 8
0x14003b19d  jb      short loc_14003B1EE
0x14003b19f  mov     esi, 200h
0x14003b1a4  test    [rdi+10h], esi
0x14003b1a7  jz      short loc_14003B1F3
0x14003b1a9  cmp     [rcx+8], ebx
0x14003b1ac  jz      short loc_14003B1F3
0x14003b1ae  mov     ecx, 0C000000Dh
0x14003b1b3  mov     r15d, 0C000023Bh
0x14003b1b9  cmp     byte ptr [rdi+2], 4
0x14003b1bd  cmovnz  r15d, ecx
0x14003b1c1  mov     edx, 13A5h
0x14003b1c6  mov     [rsp+1D8h+var_1A8], rbx
0x14003b1cb  mov     [rsp+1D8h+var_1B0], r15d
0x14003b1d0  mov     dword ptr [rsp+1D8h+var_1B8], ebx
0x14003b1d4  xor     r9d, r9d
0x14003b1d7  mov     r8, rdi
0x14003b1da  xor     ecx, ecx
0x14003b1dc  call    AFDETW_TRACECONNECTEX
0x14003b1e1  mov     eax, ebx
0x14003b1e3  xchg    eax, [rdi+170h]
0x14003b1e9  jmp     loc_14003B8B9
0x14003b1ee  mov     esi, 200h
0x14003b1f3  mov     al, byte ptr cs:xmmword_1400875E0
0x14003b1f9  test    al, al
0x14003b1fb  jns     short loc_14003B216
0x14003b1fd  mov     edx, 11h
0x14003b202  mov     ecx, 407h
0x14003b207  mov     r9, rdi
0x14003b20a  lea     r8, WPP_10158ebb263e3734eee7b4c76a3678b5_Traceguids
0x14003b211  call    WPP_SF_q
0x14003b216  mov     eax, [rdi+8]
0x14003b219  bt      eax, 8
0x14003b21d  jb      loc_14003B2AB
0x14003b223  mov     eax, [rdi+8]
0x14003b226  bt      eax, 16h
0x14003b22a  jnb     short loc_14003B2AB
0x14003b22c  mov     edx, [r14+20h]
0x14003b230  mov     rcx, [rsp+1D8h+var_190]
0x14003b235  call    AfdTdi_IsTA6V4Mapped
0x14003b23a  test    al, al
0x14003b23c  jz      short loc_14003B2AB
0x14003b23e  mov     eax, [rdi+8]
0x14003b241  bt      eax, 8
0x14003b245  jb      short loc_14003B24F
0x14003b247  test    [rdi+10h], esi
0x14003b24a  mov     r9b, r12b
0x14003b24d  jnz     short loc_14003B252
0x14003b24f  mov     r9b, bl
0x14003b252  mov     eax, [rdi+8]
0x14003b255  mov     ecx, [rdi+8]
0x14003b258  mov     rdx, [rdi+118h]
0x14003b25f  shr     eax, 7
0x14003b262  and     eax, r12d
0x14003b265  shr     ecx, 8
0x14003b268  and     ecx, r12d
0x14003b26b  lea     r8, [rsp+1D8h+var_188]
0x14003b270  mov     [rsp+1D8h+var_1A0], r8
0x14003b275  mov     r8, [rdi+30h]
0x14003b279  mov     [rsp+1D8h+var_1A8], r8
0x14003b27e  mov     [rsp+1D8h+var_1B0], eax
0x14003b282  mov     dword ptr [rsp+1D8h+var_1B8], ecx
0x14003b286  mov     r8, [rdx]
0x14003b289  mov     rdx, [rdx+18h]
0x14003b28d  mov     rcx, rdi
0x14003b290  call    AfdCreateConnection
0x14003b295  mov     r15d, eax
0x14003b298  mov     rsi, [rsp+1D8h+var_188]
0x14003b29d  mov     ecx, 2
0x14003b2a2  test    eax, eax
0x14003b2a4  js      short loc_14003B313
0x14003b2a6  or      [rsi+4], ecx
0x14003b2a9  jmp     short loc_14003B30F
0x14003b2ab  mov     eax, [rdi+8]
0x14003b2ae  bt      eax, 8
0x14003b2b2  jb      short loc_14003B2BC
0x14003b2b4  test    [rdi+10h], esi
0x14003b2b7  mov     r9b, r12b
0x14003b2ba  jnz     short loc_14003B2BF
0x14003b2bc  mov     r9b, bl
0x14003b2bf  mov     eax, [rdi+8]
0x14003b2c2  mov     ecx, [rdi+8]
0x14003b2c5  shr     eax, 7
0x14003b2c8  and     eax, r12d
0x14003b2cb  shr     ecx, 8
0x14003b2ce  and     ecx, r12d
0x14003b2d1  lea     rdx, [rsp+1D8h+var_188]
0x14003b2d6  mov     [rsp+1D8h+var_1A0], rdx
0x14003b2db  mov     rdx, [rdi+30h]
0x14003b2df  mov     [rsp+1D8h+var_1A8], rdx
0x14003b2e4  mov     [rsp+1D8h+var_1B0], eax
0x14003b2e8  mov     dword ptr [rsp+1D8h+var_1B8], ecx
  ... truncated ...
```
