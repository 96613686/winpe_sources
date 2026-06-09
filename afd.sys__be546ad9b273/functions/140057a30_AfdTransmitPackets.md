# AfdTransmitPackets

- ea: `0x140057a30`
- end: `0x14005853f`
- name: `AfdTransmitPackets`
- size: `2831`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001ebf4`
- `0x14002fd7c`
- `0x14003f8d8`
- `0x14003fc5c`
- `0x140042270`
- `0x14004290c`
- `0x1400436b8`
- `0x1400445d8`
- `0x140055870`
- `0x140055e08`
- `0x140056f20`
- `0x140057a30`
- `0x140058548`
- `0x140072840`
- `0x140072870`
- `0x1400921c4`
- `0x140094900`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x140057ed8`
- `ntoskrnl!IoQueryFileInformation` at `0x140057ed8`
- `ntoskrnl!ProbeForRead` at `0x140057cbf`
- `ntoskrnl!ProbeForRead` at `0x140057cbf`
- `ntoskrnl!ObfReferenceObject` at `0x140057ddb`
- `ntoskrnl!ObfReferenceObject` at `0x140057ddb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057bca`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057bca`
- `ntoskrnl!IofCompleteRequest` at `0x140058503`
- `ntoskrnl!IofCompleteRequest` at `0x140058503`
- `ntoskrnl!IoFileObjectType` at `0x140057df5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057e1e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057e1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400583fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400584e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400583fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400584e6`
- `ntoskrnl!ExAllocatePool2` at `0x140057ce2`
- `ntoskrnl!ExAllocatePool2` at `0x140057ce2`
- `ntoskrnl!IoIs32bitProcess` at `0x140057b1e`
- `ntoskrnl!IoIs32bitProcess` at `0x140057b1e`

## pseudocode

```c
__int64 __fastcall AfdTransmitPackets(PIRP Irp, unsigned __int64 a2)
{
  unsigned __int64 v2; // r15
  __int64 v4; // rsi
  unsigned int *Pool2; // r13
  __int16 *v6; // rdi
  __int16 v7; // ax
  struct _LIST_ENTRY **p_Blink; // r15
  KPROCESSOR_MODE RequestorMode; // cl
  void *v10; // rdx
  __int64 TpInfo; // rax
  size_t v12; // r8
  unsigned int v13; // r9d
  void *v14; // r10
  void *v15; // r11
  __int64 v16; // rax
  __int64 v17; // r15
  __int64 v18; // r12
  unsigned int v19; // r8d
  __int64 v20; // rax
  void *v21; // rcx
  _QWORD *v22; // r11
  KPROCESSOR_MODE v23; // r9
  NTSTATUS v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // ecx
  unsigned int v28; // r10d
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r11
  unsigned int v31; // r8d
  unsigned int v32; // eax
  __int64 v33; // r8
  unsigned int v34; // r12d
  unsigned int v35; // ecx
  unsigned int v36; // eax
  unsigned int v38; // ebx
  char v39; // [rsp+30h] [rbp-E8h] BYREF
  int v40; // [rsp+34h] [rbp-E4h]
  char v41[4]; // [rsp+38h] [rbp-E0h] BYREF
  int v42; // [rsp+3Ch] [rbp-DCh]
  unsigned int v43; // [rsp+40h] [rbp-D8h]
  unsigned __int64 v44; // [rsp+48h] [rbp-D0h]
  unsigned int v45; // [rsp+50h] [rbp-C8h]
  int v46; // [rsp+54h] [rbp-C4h]
  void *v47; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+60h] [rbp-B8h] BYREF
  volatile void *Address[2]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+78h] [rbp-A0h]
  unsigned __int64 v51; // [rsp+80h] [rbp-98h]
  PVOID i; // [rsp+88h] [rbp-90h]
  ULONG ReturnedLength; // [rsp+90h] [rbp-88h] BYREF
  void *v54; // [rsp+98h] [rbp-80h]
  unsigned int *v55; // [rsp+A0h] [rbp-78h]
  PVOID Object[4]; // [rsp+A8h] [rbp-70h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-50h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-40h]

  v2 = a2;
  v44 = a2;
  Object[2] = Irp;
  Object[3] = (PVOID)a2;
  v4 = 0;
  v48 = 0;
  v39 = 0;
  v43 = 0;
  LODWORD(v47) = 0;
  v41[0] = 0;
  Pool2 = 0;
  v55 = 0;
  v6 = *(__int16 **)(*(_QWORD *)(a2 + 48) + 24LL);
  Object[1] = v6;
  if ( (*((_BYTE *)v6 + 7) & 0x10) != 0 )
  {
    v40 = -1073741816;
    goto LABEL_164;
  }
  v7 = *v6;
  if ( *v6 == 6909 )
  {
    v40 = -1073741574;
    goto LABEL_164;
  }
  if ( v7 != -20526 && (v7 != -20527 || (*((_DWORD *)v6 + 2) & 0x100) == 0 && (*((_DWORD *)v6 + 4) & 0x8000) == 0)
    || *((_BYTE *)v6 + 2) != 4 )
  {
    v40 = -1073741504;
    goto LABEL_164;
  }
  if ( IoIs32bitProcess(Irp) )
  {
    v40 = AfdTransmitPackets32((_DWORD)Irp, v2, (unsigned int)&v48, (unsigned int)&v39, (__int64)v41, (__int64)&v47);
    v4 = v48;
    if ( v40 >= 0 )
    {
      p_Blink = &Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
      v43 = (unsigned int)v47;
      goto LABEL_98;
    }
    goto LABEL_164;
  }
  *(_OWORD *)Address = 0;
  v50 = 0;
  if ( *(_DWORD *)(v2 + 16) < 0x18u )
  {
    v40 = -1073741811;
    goto LABEL_164;
  }
  v40 = 0;
  i = 0;
  v54 = 0;
  v45 = 0;
  v46 = 0;
  RequestorMode = Irp->RequestorMode;
  if ( RequestorMode && (*(_BYTE *)(v2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  v10 = *(void **)(v2 + 32);
  if ( RequestorMode )
    RtlCopyFromUser(Address, v10, 0x18u);
  else
    RtlCopyVolatileMemory(Address, v10, 0x18u);
  if ( (v50 & 0xFFFFFFC8) != 0 || (a2 = v50 & 0x30, (_DWORD)a2 == 48) || *v6 == -20527 && (v50 & 3) != 0 )
  {
    v40 = -1073741811;
LABEL_164:
    if ( v39 && *(_DWORD *)(v2 + 8) )
    {
      if ( Irp->RequestorMode )
      {
        LOBYTE(a2) = 1;
        RtlWriteUCharToUser(Irp->UserBuffer, a2);
      }
      else
      {
        *(_BYTE *)Irp->UserBuffer = 1;
      }
    }
    if ( v4 )
      AfdReturnTpInfo((unsigned __int16 *)v4, BYTE1(*((_DWORD *)v6 + 2)) & 1);
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqD(1042, 10, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, Irp, v6, v40);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x46646641u);
    Irp->IoStatus.Information = 0;
    v38 = v40;
    Irp->IoStatus.Status = v40;
    IofCompleteRequest(Irp, 0);
    return v38;
  }
  if ( !Address[0] || (unsigned int)(LODWORD(Address[1]) - 1) > 0xAAAAAA9 )
  {
    v40 = -1073741811;
    goto LABEL_164;
  }
  if ( (v50 & 0x30) == 0 )
    LODWORD(v50) = AfdDefaultTransmitWorker | v50;
  if ( (*((_DWORD *)v6 + 2) & 0x100) != 0 )
    TpInfo = AfdTliGetTpInfo(LODWORD(Address[1]));
  else
    TpInfo = AfdTdiGetTpInfo(LODWORD(Address[1]));
  v4 = TpInfo;
  v48 = TpInfo;
  if ( !TpInfo )
  {
    v40 = -1073741670;
    goto LABEL_164;
  }
  *(_DWORD *)(TpInfo + 76) = 0;
  *(_DWORD *)(TpInfo + 92) = HIDWORD(Address[1]);
  if ( HIDWORD(Address[1]) )
    v41[0] = 1;
  else
    *(_DWORD *)(TpInfo + 92) = AfdTransmitIoLength;
  if ( Irp->RequestorMode )
    ProbeForRead(Address[0], 24LL * LODWORD(Address[1]), 4u);
  Pool2 = (unsigned int *)ExAllocatePool2(97, 24LL * LODWORD(Address[1]), 1180984897);
  v55 = Pool2;
  if ( !Pool2 )
  {
    v40 = -1073741670;
    goto LABEL_164;
  }
  v12 = 24LL * LODWORD(Address[1]);
  if ( Irp->RequestorMode )
    RtlCopyFromUser(Pool2, (void *)Address[0], v12);
  else
    RtlCopyVolatileMemory(Pool2, (const void *)Address[0], v12);
  v13 = 0;
  v45 = 0;
  v42 = 0;
  a2 = 0;
  v51 = 0;
  v46 = 0;
  *(_DWORD *)(v4 + 80) = 0;
  v14 = 0;
  v54 = 0;
  v15 = 0;
  for ( i = 0; ; v15 = i )
  {
    v16 = *(unsigned int *)(v4 + 76);
    if ( (unsigned int)v16 >= LODWORD(Address[1]) )
      break;
    v17 = 3 * v16;
    v18 = *(_QWORD *)(v4 + 64);
    a2 = Pool2[6 * v16];
    *(_DWORD *)(v18 + 24 * v16) = a2;
    if ( (a2 & 0xFFFFFFF8) != 0 || (a2 & 3) == 3 || (a2 & 3) == 0 )
    {
      v40 = -1073741811;
      v2 = v44;
      goto LABEL_164;
    }
    v19 = Pool2[6 * *(unsigned int *)(v4 + 76) + 1];
    *(_DWORD *)(v18 + 24 * v16 + 4) = v19;
    v20 = *(unsigned int *)(v4 + 76);
    if ( (a2 & 2) != 0 )
    {
      v21 = *(void **)&Pool2[6 * v20 + 4];
      v47 = v21;
      if ( v14 && v21 == v14 )
      {
        ObfReferenceObject(v15);
        v22 = i;
      }
      else
      {
        v23 = Irp->RequestorMode;
        Object[0] = 0;
        v24 = ObReferenceObjectByHandle(v21, 1u, (POBJECT_TYPE)IoFileObjectType, v23, Object, 0);
        v22 = Object[0];
        i = Object[0];
        v40 = v24;
        if ( v24 < 0 )
        {
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
      }
      *(_QWORD *)(v18 + 8 * v17 + 16) = v22;
      v25 = *(unsigned int *)(v4 + 76);
      *(_DWORD *)(v4 + 76) = v25 + 1;
      *(_QWORD *)(v18 + 8 * v17 + 8) = *(_QWORD *)&Pool2[6 * v25 + 2];
      --*(_DWORD *)(v4 + 76);
      if ( (v22[10] & 2) != 0 && !*(_QWORD *)(v18 + 8 * v17 + 8) )
        *(_QWORD *)(v18 + 8 * v17 + 8) = v22[13];
      v19 = *(_DWORD *)(v18 + 8 * v17 + 4);
      if ( v19 )
      {
        v26 = *(_QWORD *)(v18 + 8 * v17 + 8);
        if ( v26 < 0 )
        {
          ++*(_DWORD *)(v4 + 76);
          v40 = -1073741811;
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
      }
      else
      {
        FileInformation = 0;
        v58 = 0;
        ReturnedLength = 0;
        v40 = IoQueryFileInformation(
                *(PFILE_OBJECT *)(v18 + 8 * v17 + 16),
                FileStandardInformation,
                0x18u,
                &FileInformation,
                &ReturnedLength);
        if ( v40 < 0 )
        {
          ++*(_DWORD *)(v4 + 76);
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
        v26 = *(_QWORD *)(v18 + 8 * v17 + 8);
        if ( v26 < 0
          || v26 > *((__int64 *)&FileInformation + 1)
          || (v19 = DWORD2(FileInformation) - v26, *((_QWORD *)&FileInformation + 1) - v26 > 0x7FFFFFFF) )
        {
          ++*(_DWORD *)(v4 + 76);
          v40 = -1073741811;
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
        *(_DWORD *)(v18 + 8 * v17 + 4) = v19;
      }
      if ( 0x7FFFFFFFFFFFFFFFLL - v26 < v19 )
      {
        ++*(_DWORD *)(v4 + 76);
        v40 = -1073741811;
        v39 = 1;
        v2 = v44;
        goto LABEL_164;
      }
      v54 = v47;
      a2 = *(unsigned int *)(v18 + 8 * v17);
    }
    else
    {
      *(_QWORD *)(v18 + 8 * v17 + 8) = *(_QWORD *)&Pool2[6 * v20 + 2];
      if ( v19 <= AfdTPacketsCopyThreshold )
      {
        v27 = v42;
        if ( v13 && (v13 += v19, v45 = v13, v13 <= AfdTPacketsCopyThreshold) && v13 + v42 <= *(_DWORD *)(v4 + 92) )
        {
          *(_DWORD *)(v18 + 8 * v17 - 24) |= 0x40000000u;
        }
        else
        {
          v13 = v19;
          v45 = v19;
        }
        if ( (a2 & 4) == 0 )
          goto LABEL_82;
        goto LABEL_73;
      }
    }
    v27 = v42;
LABEL_73:
    v13 = 0;
    v45 = 0;
    if ( (a2 & 4) != 0 )
    {
      v42 = 0;
      goto LABEL_83;
    }
LABEL_82:
    a2 = (v19 + v27) % *(_DWORD *)(v4 + 92);
    v42 = a2;
LABEL_83:
    v28 = *(_DWORD *)(v4 + 80);
    if ( v28 != -1 )
    {
      v29 = v19 + (unsigned int)v51;
      v30 = *(unsigned int *)(v4 + 92);
      v31 = (unsigned int)v51 / (unsigned int)v30 + v28;
      a2 = (unsigned int)v29 % v30;
      v51 = a2;
      v46 = a2;
      if ( v29 <= v30 )
      {
        v32 = v43;
        if ( v43 < (unsigned int)a2 )
          v32 = a2;
      }
      else
      {
        v32 = v30;
      }
      LODWORD(v47) = v32;
      v43 = v32;
      if ( v31 < v28 || v31 == -1 )
      {
        *(_DWORD *)(v4 + 80) = -1;
      }
      else
      {
        *(_DWORD *)(v4 + 80) = v31;
        if ( (*(_DWORD *)(v18 + 8 * v17) & 4) != 0 && ((_DWORD)a2 || !*(_DWORD *)(v18 + 8 * v17 + 4)) )
        {
          *(_DWORD *)(v4 + 80) = v31 + 1;
          v51 = 0;
          v46 = 0;
        }
      }
    }
    ++*(_DWORD *)(v4 + 76);
    v14 = v54;
  }
  p_Blink = &Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  *((_DWORD *)&Irp->Tail.CompletionKey + 2) = v50;
LABEL_98:
  if ( *v6 != -20526 )
  {
    while ( 1 )
    {
      a2 = *((unsigned int *)v6 + 92);
      if ( (int)a2 > 0 )
        goto LABEL_101;
      if ( (_DWORD)a2 == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 92, a2 - 1, a2) )
      {
        if ( *v6 != -20527
          || *((_BYTE *)v6 + 2) != 4
          || (*((_DWORD *)v6 + 2) & 0x100) == 0 && (*((_DWORD *)v6 + 4) & 0x8000) == 0 )
        {
LABEL_120:
          _InterlockedIncrement((volatile signed __int32 *)v6 + 92);
          goto LABEL_101;
        }
        v33 = 0;
        _InterlockedIncrement((volatile signed __int32 *)v6 + 92);
        if ( (*((_DWORD *)v6 + 2) & 0x100) != 0 )
        {
          *(_QWORD *)v4 = Irp;
        }
        else if ( (*((_DWORD *)v6 + 2) & 0x400000) != 0 && (*((_DWORD *)v6 + 48) & 0x20) != 0 )
        {
          *(_QWORD *)v4 = *(_QWORD *)(*((_QWORD *)v6 + 35) + 8LL);
          *(_QWORD *)(v4 + 8) = *(_QWORD *)(*((_QWORD *)v6 + 35) + 16LL);
        }
        else
        {
          *(_QWORD *)v4 = *((_QWORD *)v6 + 3);
          *(_QWORD *)(v4 + 8) = *((_QWORD *)v6 + 5);
        }
        v34 = *((_DWORD *)v6 + 40);
        goto LABEL_134;
      }
    }
  }
  if ( (*(_DWORD *)p_Blink & 3) == 0 )
  {
    while ( 1 )
    {
      a2 = *((unsigned int *)v6 + 92);
      if ( (int)a2 > 0 )
        goto LABEL_101;
      if ( (_DWORD)a2 == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 92, a2 - 1, a2) )
      {
        if ( *v6 != -20526 || *((_BYTE *)v6 + 2) != 4 )
          goto LABEL_120;
        v33 = *((_QWORD *)v6 + 24);
        *(_QWORD *)(v4 + 16) = v33;
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v33 + 48)) <= 1 )
          __fastfail(0xEu);
        _InterlockedIncrement((volatile signed __int32 *)v6 + 92);
        goto LABEL_116;
      }
    }
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 92, *((unsigned __int8 *)v6 + 2), 0) )
    goto LABEL_101;
  if ( *v6 != -20526 || *((_BYTE *)v6 + 2) != 4 )
  {
    _InterlockedExchange((volatile __int32 *)v6 + 92, 0);
LABEL_101:
    v40 = -1073741504;
    v2 = v44;
    goto LABEL_164;
  }
  if ( (*(_DWORD *)p_Blink & 2) != 0 )
  {
    *(_DWORD *)p_Blink |= 1u;
    *((_BYTE *)v6 + 2) = 7;
  }
  v33 = *((_QWORD *)v6 + 24);
  *(_QWORD *)(v4 + 16) = v33;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v33 + 48)) <= 1 )
    __fastfail(0xEu);
LABEL_116:
  if ( (*((_DWORD *)v6 + 2) & 0x100) != 0 )
  {
    *(_QWORD *)v4 = Irp;
  }
  else
  {
    *(_QWORD *)v4 = *(_QWORD *)(v33 + 16);
    *(_QWORD *)(v4 + 8) = *(_QWORD *)(v33 + 24);
  }
  v34 = *(_DWORD *)(v33 + 148);
LABEL_134:
  if ( v33
    && !v41[0]
    && ((*(_DWORD *)(v4 + 80) + 1) & 0xFFFFFFFE) == 0
    && ((*((_DWORD *)v6 + 2) & 0x100) != 0 || (*((_DWORD *)v6 + 2) & 0x200) != 0)
    && (int)AfdCheckISBEvents(v33, (unsigned int)AfdTLSockOptEnable) >= 0 )
  {
    *(_DWORD *)p_Blink |= 0x40u;
  }
  v35 = v43;
  if ( !v43 )
  {
    v43 = *(_DWORD *)(v4 + 92);
    v35 = v43;
  }
  v36 = v34 / v35;
  if ( v34 / v35 > 2 )
  {
    if ( v36 <= 8 )
      *(_WORD *)(v4 + 84) = v36;
    else
      *(_WORD *)(v4 + 84) = 8;
  }
  if ( *v6 == -20527 && *(_DWORD *)(v4 + 80) <= (unsigned int)*(unsigned __int16 *)(v4 + 84) )
    *(_DWORD *)(v4 + 80) = -1;
  Irp->AssociatedIrp.MasterIrp = (struct _IRP *)v4;
  Irp->Tail.Overlay.ListEntry.Flink = 0;
  Irp->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)1;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  *((_DWORD *)&Irp->Tail.CompletionKey + 3) = 1;
  Irp->Tail.Overlay.DeviceQueueEntry.SortKey = 2;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)v6 + 45, (signed __int64)Irp, 0)
    || !(unsigned __int8)AfdEnqueueTPacketsIrp(v6, Irp) )
  {
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdCancelTPackets);
    if ( (*((_DWORD *)v6 + 2) & 0x800) != 0 || Irp->Cancel )
    {
      AfdAbortTPackets((__int64)Irp, -1073741536);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Irp->Tail.CompletionKey + 3, 0xFFFFFFFF) == 1 )
        AfdCompleteTPackets(Irp);
    }
    else if ( !AfdMaxActiveTransmitFileCount || !(unsigned __int8)AfdQueueTransmit(Irp) )
    {
      AfdTPacketsWorker(Irp);
    }
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x46646641u);
  return 259;
}

```

## disassembly

```asm
0x140057a30  mov     r11, rsp
0x140057a33  mov     [r11+18h], rbx
0x140057a37  mov     [r11+20h], rsi
0x140057a3b  push    rdi
0x140057a3c  push    r12
0x140057a3e  push    r13
0x140057a40  push    r14
0x140057a42  push    r15
0x140057a44  sub     rsp, 0F0h
0x140057a4b  mov     rax, cs:__security_cookie
0x140057a52  xor     rax, rsp
0x140057a55  mov     [rsp+118h+var_38], rax
0x140057a5d  mov     r15, rdx
0x140057a60  mov     [rsp+118h+var_D0], rdx
0x140057a65  mov     r14, rcx
0x140057a68  mov     [rsp+118h+var_60], rcx
0x140057a70  mov     [rsp+118h+var_58], rdx
0x140057a78  xor     ebx, ebx
0x140057a7a  mov     esi, ebx
0x140057a7c  mov     [rsp+118h+var_B8], rbx
0x140057a81  mov     [rsp+118h+var_E8], bl
0x140057a85  mov     [rsp+118h+var_D8], ebx
0x140057a89  mov     dword ptr [rsp+118h+var_C0], ebx
0x140057a8d  mov     [rsp+118h+var_E0], bl
0x140057a91  mov     r13d, ebx
0x140057a94  mov     [r11-78h], rbx
0x140057a98  mov     rax, [rdx+30h]
0x140057a9c  mov     rdi, [rax+18h]
0x140057aa0  mov     [rsp+118h+var_68], rdi
0x140057aa8  test    byte ptr [rdi+7], 10h
0x140057aac  jz      short loc_140057ABB
0x140057aae  mov     [rsp+118h+var_E4], 0C0000008h
0x140057ab6  jmp     loc_14005844D
0x140057abb  movzx   eax, word ptr [rdi]
0x140057abe  mov     ecx, 1AFDh
0x140057ac3  cmp     ax, cx
0x140057ac6  jnz     short loc_140057AD5
0x140057ac8  mov     [rsp+118h+var_E4], 0C00000FAh
0x140057ad0  jmp     loc_14005844D
0x140057ad5  mov     ecx, 0AFD2h
0x140057ada  cmp     ax, cx
0x140057add  jz      short loc_140057B02
0x140057adf  mov     ecx, 0AFD1h
0x140057ae4  cmp     ax, cx
0x140057ae7  jnz     short loc_140057B0E
0x140057ae9  mov     eax, [rdi+8]
0x140057aec  mov     r12d, 100h
0x140057af2  test    r12d, eax
0x140057af5  jnz     short loc_140057B08
0x140057af7  test    dword ptr [rdi+10h], 8000h
0x140057afe  jz      short loc_140057B0E
0x140057b00  jmp     short loc_140057B08
0x140057b02  mov     r12d, 100h
0x140057b08  cmp     byte ptr [rdi+2], 4
0x140057b0c  jz      short loc_140057B1B
0x140057b0e  mov     [rsp+118h+var_E4], 0C0000140h
0x140057b16  jmp     loc_14005844D
0x140057b1b  mov     rcx, r14; Irp
0x140057b1e  call    cs:__imp_IoIs32bitProcess
0x140057b25  nop     dword ptr [rax+rax+00h]
0x140057b2a  test    al, al
0x140057b2c  jz      short loc_140057B7C
0x140057b2e  lea     rax, [rsp+118h+var_C0]
0x140057b33  mov     [rsp+118h+HandleInformation], rax
0x140057b38  lea     rax, [rsp+118h+var_E0]
0x140057b3d  mov     [rsp+118h+Object], rax
0x140057b42  lea     r9, [rsp+118h+var_E8]
0x140057b47  lea     r8, [rsp+118h+var_B8]
0x140057b4c  mov     rdx, r15
0x140057b4f  mov     rcx, r14
0x140057b52  call    AfdTransmitPackets32
0x140057b57  mov     [rsp+118h+var_E4], eax
0x140057b5b  mov     rsi, [rsp+118h+var_B8]
0x140057b60  test    eax, eax
0x140057b62  js      loc_14005844D
0x140057b68  lea     r15, [r14+80h]
0x140057b6f  mov     eax, dword ptr [rsp+118h+var_C0]
0x140057b73  mov     [rsp+118h+var_D8], eax
0x140057b77  jmp     loc_1400580F0
0x140057b7c  xorps   xmm0, xmm0
0x140057b7f  xor     eax, eax
0x140057b81  movups  xmmword ptr [rsp+118h+Address], xmm0
0x140057b86  mov     [rsp+118h+var_A0], rax
0x140057b8b  cmp     dword ptr [r15+10h], 18h
0x140057b90  jnb     short loc_140057B9F
0x140057b92  mov     [rsp+118h+var_E4], 0C000000Dh
0x140057b9a  jmp     loc_14005844D
0x140057b9f  mov     [rsp+118h+var_E4], ebx
0x140057ba3  mov     [rsp+118h+var_90], rbx
0x140057bab  mov     [rsp+118h+var_80], rbx
0x140057bb3  mov     [rsp+118h+var_C8], ebx
0x140057bb7  mov     [rsp+118h+var_C4], ebx
0x140057bbb  mov     cl, [r14+40h]
0x140057bbf  test    cl, cl
0x140057bc1  jz      short loc_140057BD6
0x140057bc3  test    byte ptr [r15+20h], 3
0x140057bc8  jz      short loc_140057BD6
0x140057bca  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140057bd1  nop     dword ptr [rax+rax+00h]
0x140057bd6  mov     rdx, [r15+20h]; Src
0x140057bda  mov     r8d, 18h; Size
0x140057be0  test    cl, cl
0x140057be2  lea     rcx, [rsp+118h+Address]; void *
0x140057be7  jz      short loc_140057BF0
0x140057be9  call    RtlCopyFromUser
0x140057bee  jmp     short loc_140057BF5
0x140057bf0  call    RtlCopyVolatileMemory
0x140057bf5  mov     ecx, dword ptr [rsp+118h+var_A0]
0x140057bf9  test    ecx, 0FFFFFFC8h
0x140057bff  jnz     loc_14005841C
0x140057c05  mov     edx, ecx
0x140057c07  and     edx, 30h
0x140057c0a  cmp     edx, 30h ; '0'
0x140057c0d  jz      loc_14005841C
0x140057c13  mov     eax, 0AFD1h
0x140057c18  cmp     [rdi], ax
0x140057c1b  jnz     short loc_140057C26
0x140057c1d  test    cl, 3
0x140057c20  jnz     loc_14005841C
0x140057c26  cmp     [rsp+118h+Address], rbx
0x140057c2b  jz      loc_140058412
0x140057c31  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057c35  dec     eax
0x140057c37  cmp     eax, 0AAAAAA9h
0x140057c3c  ja      loc_140058412
0x140057c42  test    edx, edx
0x140057c44  jnz     short loc_140057C50
0x140057c46  or      ecx, cs:AfdDefaultTransmitWorker
0x140057c4c  mov     dword ptr [rsp+118h+var_A0], ecx
0x140057c50  mov     eax, [rdi+8]
0x140057c53  mov     ecx, dword ptr [rsp+118h+Address+8]
0x140057c57  test    r12d, eax
0x140057c5a  jz      short loc_140057C63
0x140057c5c  call    AfdTliGetTpInfo
0x140057c61  jmp     short loc_140057C68
0x140057c63  call    AfdTdiGetTpInfo
0x140057c68  mov     rsi, rax
0x140057c6b  mov     [rsp+118h+var_B8], rax
0x140057c70  test    rax, rax
0x140057c73  jnz     short loc_140057C82
0x140057c75  mov     [rsp+118h+var_E4], 0C000009Ah
0x140057c7d  jmp     loc_14005844D
0x140057c82  mov     [rsi+4Ch], ebx
0x140057c85  mov     eax, dword ptr [rsp+118h+Address+0Ch]
0x140057c89  mov     [rsi+5Ch], eax
0x140057c8c  cmp     dword ptr [rsp+118h+Address+0Ch], ebx
0x140057c90  jnz     short loc_140057C9D
0x140057c92  mov     eax, cs:AfdTransmitIoLength
0x140057c98  mov     [rsi+5Ch], eax
0x140057c9b  jmp     short loc_140057CA2
0x140057c9d  mov     [rsp+118h+var_E0], 1
0x140057ca2  cmp     [r14+40h], bl
0x140057ca6  jz      short loc_140057CCB
0x140057ca8  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057cac  lea     rdx, [rax+rax*2]
0x140057cb0  shl     rdx, 3; Length
0x140057cb4  mov     r8d, 4; Alignment
0x140057cba  mov     rcx, [rsp+118h+Address]; Address
0x140057cbf  call    cs:__imp_ProbeForRead
0x140057cc6  nop     dword ptr [rax+rax+00h]
0x140057ccb  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057ccf  lea     rdx, [rax+rax*2]
0x140057cd3  shl     rdx, 3
0x140057cd7  mov     ecx, 61h ; 'a'
0x140057cdc  mov     r8d, 46646641h
0x140057ce2  call    cs:__imp_ExAllocatePool2
0x140057ce9  nop     dword ptr [rax+rax+00h]
0x140057cee  mov     r13, rax
0x140057cf1  mov     [rsp+118h+var_78], rax
0x140057cf9  test    rax, rax
0x140057cfc  jnz     short loc_140057D0B
0x140057cfe  mov     [rsp+118h+var_E4], 0C000009Ah
0x140057d06  jmp     loc_14005844D
0x140057d0b  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057d0f  lea     r8, [rax+rax*2]
0x140057d13  shl     r8, 3; Size
0x140057d17  mov     rdx, [rsp+118h+Address]; Src
0x140057d1c  mov     rcx, r13; void *
0x140057d1f  cmp     [r14+40h], bl
0x140057d23  jz      short loc_140057D2C
0x140057d25  call    RtlCopyFromUser
0x140057d2a  jmp     short loc_140057D31
0x140057d2c  call    RtlCopyVolatileMemory
0x140057d31  mov     r9d, ebx
0x140057d34  mov     [rsp+118h+var_C8], ebx
0x140057d38  mov     [rsp+118h+var_DC], ebx
0x140057d3c  mov     edx, ebx
0x140057d3e  mov     [rsp+118h+var_98], rdx
0x140057d46  mov     [rsp+118h+var_C4], ebx
0x140057d4a  mov     [rsi+50h], ebx
0x140057d4d  mov     r10, rbx
0x140057d50  mov     [rsp+118h+var_80], rbx
0x140057d58  mov     r11, rbx
0x140057d5b  mov     [rsp+118h+var_90], rbx
0x140057d63  mov     eax, [rsi+4Ch]
0x140057d66  cmp     eax, dword ptr [rsp+118h+Address+8]
0x140057d6a  jnb     loc_1400580DC
0x140057d70  lea     r15, [rax+rax*2]
0x140057d74  mov     r12, [rsi+40h]
0x140057d78  mov     edx, [r13+r15*8+0]
0x140057d7d  mov     [r12+r15*8], edx
0x140057d81  test    edx, 0FFFFFFF8h
0x140057d87  jnz     loc_1400580CA
0x140057d8d  mov     eax, edx
0x140057d8f  and     eax, 3
0x140057d92  cmp     eax, 3
0x140057d95  jz      loc_1400580CA
0x140057d9b  test    eax, eax
0x140057d9d  jz      loc_1400580CA
0x140057da3  mov     eax, [rsi+4Ch]
0x140057da6  lea     rcx, [rax+rax*2]
0x140057daa  mov     r8d, [r13+rcx*8+4]
0x140057daf  mov     [r12+r15*8+4], r8d
0x140057db4  mov     eax, [rsi+4Ch]
0x140057db7  lea     rcx, [rax+rax*2]
0x140057dbb  test    dl, 2
0x140057dbe  jz      loc_140057FC0
0x140057dc4  mov     rcx, [r13+rcx*8+10h]; Handle
0x140057dc9  mov     [rsp+118h+var_C0], rcx
0x140057dce  test    r10, r10
0x140057dd1  jz      short loc_140057DF1
0x140057dd3  cmp     rcx, r10
0x140057dd6  jnz     short loc_140057DF1
0x140057dd8  mov     rcx, r11; Object
0x140057ddb  call    cs:__imp_ObfReferenceObject
0x140057de2  nop     dword ptr [rax+rax+00h]
0x140057de7  mov     r11, [rsp+118h+var_90]
0x140057def  jmp     short loc_140057E55
0x140057df1  mov     r9b, [r14+40h]; AccessMode
0x140057df5  mov     rax, cs:__imp_IoFileObjectType
0x140057dfc  mov     r8, [rax]; ObjectType
0x140057dff  mov     [rsp+118h+var_70], rbx
0x140057e07  mov     [rsp+118h+HandleInformation], rbx; HandleInformation
0x140057e0c  lea     rax, [rsp+118h+var_70]
0x140057e14  mov     [rsp+118h+Object], rax; Object
0x140057e19  mov     edx, 1; DesiredAccess
0x140057e1e  call    cs:__imp_ObReferenceObjectByHandle
0x140057e25  nop     dword ptr [rax+rax+00h]
0x140057e2a  mov     r11, [rsp+118h+var_70]
0x140057e32  mov     [rsp+118h+var_90], r11
0x140057e3a  mov     [rsp+118h+var_E4], eax
0x140057e3e  mov     eax, [rsp+118h+var_E4]
0x140057e42  test    eax, eax
0x140057e44  jns     short loc_140057E55
0x140057e46  mov     [rsp+118h+var_E8], 1
0x140057e4b  mov     r15, [rsp+118h+var_D0]
0x140057e50  jmp     loc_14005844D
0x140057e55  mov     [r12+r15*8+10h], r11
0x140057e5a  mov     ecx, [rsi+4Ch]
0x140057e5d  lea     eax, [rcx+1]
0x140057e60  mov     [rsi+4Ch], eax
0x140057e63  lea     rcx, [rcx+rcx*2]
0x140057e67  mov     rax, [r13+rcx*8+8]
0x140057e6c  mov     [r12+r15*8+8], rax
0x140057e71  dec     dword ptr [rsi+4Ch]
0x140057e74  mov     eax, [r11+50h]
0x140057e78  test    al, 2
0x140057e7a  jz      short loc_140057E8C
0x140057e7c  cmp     [r12+r15*8+8], rbx
0x140057e81  jnz     short loc_140057E8C
0x140057e83  mov     rax, [r11+68h]
0x140057e87  mov     [r12+r15*8+8], rax
0x140057e8c  mov     r8d, [r12+r15*8+4]
0x140057e91  test    r8d, r8d
0x140057e94  jnz     loc_140057F46
0x140057e9a  xorps   xmm0, xmm0
0x140057e9d  xor     eax, eax
0x140057e9f  movups  [rsp+118h+FileInformation], xmm0
0x140057ea7  mov     [rsp+118h+var_40], rax
0x140057eaf  mov     [rsp+118h+ReturnedLength], ebx
0x140057eb6  lea     rax, [rsp+118h+ReturnedLength]
0x140057ebe  mov     [rsp+118h+Object], rax; ReturnedLength
0x140057ec3  lea     r9, [rsp+118h+FileInformation]; FileInformation
0x140057ecb  lea     edx, [r8+5]; FileInformationClass
0x140057ecf  lea     r8d, [rdx+13h]; Length
0x140057ed3  mov     rcx, [r12+r15*8+10h]; FileObject
0x140057ed8  call    cs:__imp_IoQueryFileInformation
0x140057edf  nop     dword ptr [rax+rax+00h]
0x140057ee4  mov     [rsp+118h+var_E4], eax
0x140057ee8  mov     eax, [rsp+118h+var_E4]
0x140057eec  test    eax, eax
0x140057eee  jns     short loc_140057F02
0x140057ef0  inc     dword ptr [rsi+4Ch]
0x140057ef3  mov     [rsp+118h+var_E8], 1
0x140057ef8  mov     r15, [rsp+118h+var_D0]
0x140057efd  jmp     loc_14005844D
0x140057f02  mov     rax, [r12+r15*8+8]
0x140057f07  test    rax, rax
0x140057f0a  js      short loc_140057F2C
0x140057f0c  mov     r8, qword ptr [rsp+118h+FileInformation+8]
0x140057f14  cmp     rax, r8
0x140057f17  jg      short loc_140057F2C
0x140057f19  sub     r8, rax
0x140057f1c  cmp     r8, 7FFFFFFFh
0x140057f23  jg      short loc_140057F2C
0x140057f25  mov     [r12+r15*8+4], r8d
0x140057f2a  jmp     short loc_140057F6A
0x140057f2c  inc     dword ptr [rsi+4Ch]
0x140057f2f  mov     [rsp+118h+var_E4], 0C000000Dh
0x140057f37  mov     [rsp+118h+var_E8], 1
  ... truncated ...
```
