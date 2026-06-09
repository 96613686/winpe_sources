# AfdTransmitPackets

- ea: `0x140057940`
- end: `0x14005844f`
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
- `0x14002fd5c`
- `0x14003f8b8`
- `0x14003fc3c`
- `0x140042250`
- `0x1400428ec`
- `0x140043698`
- `0x1400445b8`
- `0x1400557d0`
- `0x140055d68`
- `0x140056e80`
- `0x140057940`
- `0x140058458`
- `0x1400726a0`
- `0x1400726d0`
- `0x1400921c4`
- `0x140094900`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x140057de8`
- `ntoskrnl!IoQueryFileInformation` at `0x140057de8`
- `ntoskrnl!ProbeForRead` at `0x140057bcf`
- `ntoskrnl!ProbeForRead` at `0x140057bcf`
- `ntoskrnl!ObfReferenceObject` at `0x140057ceb`
- `ntoskrnl!ObfReferenceObject` at `0x140057ceb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057ada`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057ada`
- `ntoskrnl!IofCompleteRequest` at `0x140058413`
- `ntoskrnl!IofCompleteRequest` at `0x140058413`
- `ntoskrnl!IoFileObjectType` at `0x140057d05`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057d2e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057d2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005830c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400583f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005830c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400583f6`
- `ntoskrnl!ExAllocatePool2` at `0x140057bf2`
- `ntoskrnl!ExAllocatePool2` at `0x140057bf2`
- `ntoskrnl!IoIs32bitProcess` at `0x140057a2e`
- `ntoskrnl!IoIs32bitProcess` at `0x140057a2e`

## pseudocode

```c
__int64 __fastcall AfdTransmitPackets(PIRP Irp, unsigned __int64 a2)
{
  unsigned __int64 v2; // r15
  struct _IRP *v4; // rsi
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
  __int64 UserIosb_high; // rax
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
  unsigned int UserEvent; // r10d
  unsigned __int64 v29; // rcx
  unsigned __int64 HighPart; // r11
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
  struct _IRP *v48; // [rsp+60h] [rbp-B8h] BYREF
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
      AfdReturnTpInfo(v4);
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqD(1042, 10, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, Irp, v6, v40);
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
  v4 = (struct _IRP *)TpInfo;
  v48 = (struct _IRP *)TpInfo;
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
  LODWORD(v4->UserEvent) = 0;
  v14 = 0;
  v54 = 0;
  v15 = 0;
  for ( i = 0; ; v15 = i )
  {
    UserIosb_high = HIDWORD(v4->UserIosb);
    if ( (unsigned int)UserIosb_high >= LODWORD(Address[1]) )
      break;
    v17 = 3 * UserIosb_high;
    v18 = *(_QWORD *)&v4->RequestorMode;
    a2 = Pool2[6 * UserIosb_high];
    *(_DWORD *)(v18 + 24 * UserIosb_high) = a2;
    if ( (a2 & 0xFFFFFFF8) != 0 || (a2 & 3) == 3 || (a2 & 3) == 0 )
    {
      v40 = -1073741811;
      v2 = v44;
      goto LABEL_164;
    }
    v19 = Pool2[6 * HIDWORD(v4->UserIosb) + 1];
    *(_DWORD *)(v18 + 24 * UserIosb_high + 4) = v19;
    v20 = HIDWORD(v4->UserIosb);
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
      v25 = HIDWORD(v4->UserIosb);
      HIDWORD(v4->UserIosb) = v25 + 1;
      *(_QWORD *)(v18 + 8 * v17 + 8) = *(_QWORD *)&Pool2[6 * v25 + 2];
      --HIDWORD(v4->UserIosb);
      if ( (v22[10] & 2) != 0 && !*(_QWORD *)(v18 + 8 * v17 + 8) )
        *(_QWORD *)(v18 + 8 * v17 + 8) = v22[13];
      v19 = *(_DWORD *)(v18 + 8 * v17 + 4);
      if ( v19 )
      {
        v26 = *(_QWORD *)(v18 + 8 * v17 + 8);
        if ( v26 < 0 )
        {
          ++HIDWORD(v4->UserIosb);
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
          ++HIDWORD(v4->UserIosb);
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
        v26 = *(_QWORD *)(v18 + 8 * v17 + 8);
        if ( v26 < 0
          || v26 > *((__int64 *)&FileInformation + 1)
          || (v19 = DWORD2(FileInformation) - v26, *((_QWORD *)&FileInformation + 1) - v26 > 0x7FFFFFFF) )
        {
          ++HIDWORD(v4->UserIosb);
          v40 = -1073741811;
          v39 = 1;
          v2 = v44;
          goto LABEL_164;
        }
        *(_DWORD *)(v18 + 8 * v17 + 4) = v19;
      }
      if ( 0x7FFFFFFFFFFFFFFFLL - v26 < v19 )
      {
        ++HIDWORD(v4->UserIosb);
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
        if ( v13
          && (v13 += v19, v45 = v13, v13 <= AfdTPacketsCopyThreshold)
          && v13 + v42 <= v4->Overlay.AllocationSize.HighPart )
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
    a2 = (v19 + v27) % v4->Overlay.AllocationSize.HighPart;
    v42 = a2;
LABEL_83:
    UserEvent = (unsigned int)v4->UserEvent;
    if ( UserEvent != -1 )
    {
      v29 = v19 + (unsigned int)v51;
      HighPart = (unsigned int)v4->Overlay.AllocationSize.HighPart;
      v31 = (unsigned int)v51 / (unsigned int)HighPart + UserEvent;
      a2 = (unsigned int)v29 % HighPart;
      v51 = a2;
      v46 = a2;
      if ( v29 <= HighPart )
      {
        v32 = v43;
        if ( v43 < (unsigned int)a2 )
          v32 = a2;
      }
      else
      {
        v32 = HighPart;
      }
      LODWORD(v47) = v32;
      v43 = v32;
      if ( v31 < UserEvent || v31 == -1 )
      {
        LODWORD(v4->UserEvent) = -1;
      }
      else
      {
        LODWORD(v4->UserEvent) = v31;
        if ( (*(_DWORD *)(v18 + 8 * v17) & 4) != 0 && ((_DWORD)a2 || !*(_DWORD *)(v18 + 8 * v17 + 4)) )
        {
          LODWORD(v4->UserEvent) = v31 + 1;
          v51 = 0;
          v46 = 0;
        }
      }
    }
    ++HIDWORD(v4->UserIosb);
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
          *(_QWORD *)&v4->Type = Irp;
        }
        else if ( (*((_DWORD *)v6 + 2) & 0x400000) != 0 && (*((_DWORD *)v6 + 48) & 0x20) != 0 )
        {
          *(_QWORD *)&v4->Type = *(_QWORD *)(*((_QWORD *)v6 + 35) + 8LL);
          v4->MdlAddress = *(PMDL *)(*((_QWORD *)v6 + 35) + 16LL);
        }
        else
        {
          *(_QWORD *)&v4->Type = *((_QWORD *)v6 + 3);
          v4->MdlAddress = (PMDL)*((_QWORD *)v6 + 5);
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
        *(_QWORD *)&v4->Flags = v33;
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
  *(_QWORD *)&v4->Flags = v33;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v33 + 48)) <= 1 )
    __fastfail(0xEu);
LABEL_116:
  if ( (*((_DWORD *)v6 + 2) & 0x100) != 0 )
  {
    *(_QWORD *)&v4->Type = Irp;
  }
  else
  {
    *(_QWORD *)&v4->Type = *(_QWORD *)(v33 + 16);
    v4->MdlAddress = *(PMDL *)(v33 + 24);
  }
  v34 = *(_DWORD *)(v33 + 148);
LABEL_134:
  if ( v33
    && !v41[0]
    && ((LODWORD(v4->UserEvent) + 1) & 0xFFFFFFFE) == 0
    && ((*((_DWORD *)v6 + 2) & 0x100) != 0 || (*((_DWORD *)v6 + 2) & 0x200) != 0)
    && (int)AfdCheckISBEvents(v33, (unsigned int)AfdTLSockOptEnable) >= 0 )
  {
    *(_DWORD *)p_Blink |= 0x40u;
  }
  v35 = v43;
  if ( !v43 )
  {
    v43 = v4->Overlay.AllocationSize.HighPart;
    v35 = v43;
  }
  v36 = v34 / v35;
  if ( v34 / v35 > 2 )
  {
    if ( v36 <= 8 )
      WORD2(v4->UserEvent) = v36;
    else
      WORD2(v4->UserEvent) = 8;
  }
  if ( *v6 == -20527 && LODWORD(v4->UserEvent) <= WORD2(v4->UserEvent) )
    LODWORD(v4->UserEvent) = -1;
  Irp->AssociatedIrp.MasterIrp = v4;
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
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelTPackets);
    if ( (*((_DWORD *)v6 + 2) & 0x800) != 0 || Irp->Cancel )
    {
      AfdAbortTPackets(Irp, 3221225760LL);
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
0x140057940  mov     r11, rsp
0x140057943  mov     [r11+18h], rbx
0x140057947  mov     [r11+20h], rsi
0x14005794b  push    rdi
0x14005794c  push    r12
0x14005794e  push    r13
0x140057950  push    r14
0x140057952  push    r15
0x140057954  sub     rsp, 0F0h
0x14005795b  mov     rax, cs:__security_cookie
0x140057962  xor     rax, rsp
0x140057965  mov     [rsp+118h+var_38], rax
0x14005796d  mov     r15, rdx
0x140057970  mov     [rsp+118h+var_D0], rdx
0x140057975  mov     r14, rcx
0x140057978  mov     [rsp+118h+var_60], rcx
0x140057980  mov     [rsp+118h+var_58], rdx
0x140057988  xor     ebx, ebx
0x14005798a  mov     esi, ebx
0x14005798c  mov     [rsp+118h+var_B8], rbx
0x140057991  mov     [rsp+118h+var_E8], bl
0x140057995  mov     [rsp+118h+var_D8], ebx
0x140057999  mov     dword ptr [rsp+118h+var_C0], ebx
0x14005799d  mov     [rsp+118h+var_E0], bl
0x1400579a1  mov     r13d, ebx
0x1400579a4  mov     [r11-78h], rbx
0x1400579a8  mov     rax, [rdx+30h]
0x1400579ac  mov     rdi, [rax+18h]
0x1400579b0  mov     [rsp+118h+var_68], rdi
0x1400579b8  test    byte ptr [rdi+7], 10h
0x1400579bc  jz      short loc_1400579CB
0x1400579be  mov     [rsp+118h+var_E4], 0C0000008h
0x1400579c6  jmp     loc_14005835D
0x1400579cb  movzx   eax, word ptr [rdi]
0x1400579ce  mov     ecx, 1AFDh
0x1400579d3  cmp     ax, cx
0x1400579d6  jnz     short loc_1400579E5
0x1400579d8  mov     [rsp+118h+var_E4], 0C00000FAh
0x1400579e0  jmp     loc_14005835D
0x1400579e5  mov     ecx, 0AFD2h
0x1400579ea  cmp     ax, cx
0x1400579ed  jz      short loc_140057A12
0x1400579ef  mov     ecx, 0AFD1h
0x1400579f4  cmp     ax, cx
0x1400579f7  jnz     short loc_140057A1E
0x1400579f9  mov     eax, [rdi+8]
0x1400579fc  mov     r12d, 100h
0x140057a02  test    r12d, eax
0x140057a05  jnz     short loc_140057A18
0x140057a07  test    dword ptr [rdi+10h], 8000h
0x140057a0e  jz      short loc_140057A1E
0x140057a10  jmp     short loc_140057A18
0x140057a12  mov     r12d, 100h
0x140057a18  cmp     byte ptr [rdi+2], 4
0x140057a1c  jz      short loc_140057A2B
0x140057a1e  mov     [rsp+118h+var_E4], 0C0000140h
0x140057a26  jmp     loc_14005835D
0x140057a2b  mov     rcx, r14; Irp
0x140057a2e  call    cs:__imp_IoIs32bitProcess
0x140057a35  nop     dword ptr [rax+rax+00h]
0x140057a3a  test    al, al
0x140057a3c  jz      short loc_140057A8C
0x140057a3e  lea     rax, [rsp+118h+var_C0]
0x140057a43  mov     [rsp+118h+HandleInformation], rax
0x140057a48  lea     rax, [rsp+118h+var_E0]
0x140057a4d  mov     [rsp+118h+Object], rax
0x140057a52  lea     r9, [rsp+118h+var_E8]
0x140057a57  lea     r8, [rsp+118h+var_B8]
0x140057a5c  mov     rdx, r15
0x140057a5f  mov     rcx, r14
0x140057a62  call    AfdTransmitPackets32
0x140057a67  mov     [rsp+118h+var_E4], eax
0x140057a6b  mov     rsi, [rsp+118h+var_B8]
0x140057a70  test    eax, eax
0x140057a72  js      loc_14005835D
0x140057a78  lea     r15, [r14+80h]
0x140057a7f  mov     eax, dword ptr [rsp+118h+var_C0]
0x140057a83  mov     [rsp+118h+var_D8], eax
0x140057a87  jmp     loc_140058000
0x140057a8c  xorps   xmm0, xmm0
0x140057a8f  xor     eax, eax
0x140057a91  movups  xmmword ptr [rsp+118h+Address], xmm0
0x140057a96  mov     [rsp+118h+var_A0], rax
0x140057a9b  cmp     dword ptr [r15+10h], 18h
0x140057aa0  jnb     short loc_140057AAF
0x140057aa2  mov     [rsp+118h+var_E4], 0C000000Dh
0x140057aaa  jmp     loc_14005835D
0x140057aaf  mov     [rsp+118h+var_E4], ebx
0x140057ab3  mov     [rsp+118h+var_90], rbx
0x140057abb  mov     [rsp+118h+var_80], rbx
0x140057ac3  mov     [rsp+118h+var_C8], ebx
0x140057ac7  mov     [rsp+118h+var_C4], ebx
0x140057acb  mov     cl, [r14+40h]
0x140057acf  test    cl, cl
0x140057ad1  jz      short loc_140057AE6
0x140057ad3  test    byte ptr [r15+20h], 3
0x140057ad8  jz      short loc_140057AE6
0x140057ada  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140057ae1  nop     dword ptr [rax+rax+00h]
0x140057ae6  mov     rdx, [r15+20h]; Src
0x140057aea  mov     r8d, 18h; Size
0x140057af0  test    cl, cl
0x140057af2  lea     rcx, [rsp+118h+Address]; void *
0x140057af7  jz      short loc_140057B00
0x140057af9  call    RtlCopyFromUser
0x140057afe  jmp     short loc_140057B05
0x140057b00  call    RtlCopyVolatileMemory
0x140057b05  mov     ecx, dword ptr [rsp+118h+var_A0]
0x140057b09  test    ecx, 0FFFFFFC8h
0x140057b0f  jnz     loc_14005832C
0x140057b15  mov     edx, ecx
0x140057b17  and     edx, 30h
0x140057b1a  cmp     edx, 30h ; '0'
0x140057b1d  jz      loc_14005832C
0x140057b23  mov     eax, 0AFD1h
0x140057b28  cmp     [rdi], ax
0x140057b2b  jnz     short loc_140057B36
0x140057b2d  test    cl, 3
0x140057b30  jnz     loc_14005832C
0x140057b36  cmp     [rsp+118h+Address], rbx
0x140057b3b  jz      loc_140058322
0x140057b41  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057b45  dec     eax
0x140057b47  cmp     eax, 0AAAAAA9h
0x140057b4c  ja      loc_140058322
0x140057b52  test    edx, edx
0x140057b54  jnz     short loc_140057B60
0x140057b56  or      ecx, cs:AfdDefaultTransmitWorker
0x140057b5c  mov     dword ptr [rsp+118h+var_A0], ecx
0x140057b60  mov     eax, [rdi+8]
0x140057b63  mov     ecx, dword ptr [rsp+118h+Address+8]
0x140057b67  test    r12d, eax
0x140057b6a  jz      short loc_140057B73
0x140057b6c  call    AfdTliGetTpInfo
0x140057b71  jmp     short loc_140057B78
0x140057b73  call    AfdTdiGetTpInfo
0x140057b78  mov     rsi, rax
0x140057b7b  mov     [rsp+118h+var_B8], rax
0x140057b80  test    rax, rax
0x140057b83  jnz     short loc_140057B92
0x140057b85  mov     [rsp+118h+var_E4], 0C000009Ah
0x140057b8d  jmp     loc_14005835D
0x140057b92  mov     [rsi+4Ch], ebx
0x140057b95  mov     eax, dword ptr [rsp+118h+Address+0Ch]
0x140057b99  mov     [rsi+5Ch], eax
0x140057b9c  cmp     dword ptr [rsp+118h+Address+0Ch], ebx
0x140057ba0  jnz     short loc_140057BAD
0x140057ba2  mov     eax, cs:AfdTransmitIoLength
0x140057ba8  mov     [rsi+5Ch], eax
0x140057bab  jmp     short loc_140057BB2
0x140057bad  mov     [rsp+118h+var_E0], 1
0x140057bb2  cmp     [r14+40h], bl
0x140057bb6  jz      short loc_140057BDB
0x140057bb8  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057bbc  lea     rdx, [rax+rax*2]
0x140057bc0  shl     rdx, 3; Length
0x140057bc4  mov     r8d, 4; Alignment
0x140057bca  mov     rcx, [rsp+118h+Address]; Address
0x140057bcf  call    cs:__imp_ProbeForRead
0x140057bd6  nop     dword ptr [rax+rax+00h]
0x140057bdb  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057bdf  lea     rdx, [rax+rax*2]
0x140057be3  shl     rdx, 3
0x140057be7  mov     ecx, 61h ; 'a'
0x140057bec  mov     r8d, 46646641h
0x140057bf2  call    cs:__imp_ExAllocatePool2
0x140057bf9  nop     dword ptr [rax+rax+00h]
0x140057bfe  mov     r13, rax
0x140057c01  mov     [rsp+118h+var_78], rax
0x140057c09  test    rax, rax
0x140057c0c  jnz     short loc_140057C1B
0x140057c0e  mov     [rsp+118h+var_E4], 0C000009Ah
0x140057c16  jmp     loc_14005835D
0x140057c1b  mov     eax, dword ptr [rsp+118h+Address+8]
0x140057c1f  lea     r8, [rax+rax*2]
0x140057c23  shl     r8, 3; Size
0x140057c27  mov     rdx, [rsp+118h+Address]; Src
0x140057c2c  mov     rcx, r13; void *
0x140057c2f  cmp     [r14+40h], bl
0x140057c33  jz      short loc_140057C3C
0x140057c35  call    RtlCopyFromUser
0x140057c3a  jmp     short loc_140057C41
0x140057c3c  call    RtlCopyVolatileMemory
0x140057c41  mov     r9d, ebx
0x140057c44  mov     [rsp+118h+var_C8], ebx
0x140057c48  mov     [rsp+118h+var_DC], ebx
0x140057c4c  mov     edx, ebx
0x140057c4e  mov     [rsp+118h+var_98], rdx
0x140057c56  mov     [rsp+118h+var_C4], ebx
0x140057c5a  mov     [rsi+50h], ebx
0x140057c5d  mov     r10, rbx
0x140057c60  mov     [rsp+118h+var_80], rbx
0x140057c68  mov     r11, rbx
0x140057c6b  mov     [rsp+118h+var_90], rbx
0x140057c73  mov     eax, [rsi+4Ch]
0x140057c76  cmp     eax, dword ptr [rsp+118h+Address+8]
0x140057c7a  jnb     loc_140057FEC
0x140057c80  lea     r15, [rax+rax*2]
0x140057c84  mov     r12, [rsi+40h]
0x140057c88  mov     edx, [r13+r15*8+0]
0x140057c8d  mov     [r12+r15*8], edx
0x140057c91  test    edx, 0FFFFFFF8h
0x140057c97  jnz     loc_140057FDA
0x140057c9d  mov     eax, edx
0x140057c9f  and     eax, 3
0x140057ca2  cmp     eax, 3
0x140057ca5  jz      loc_140057FDA
0x140057cab  test    eax, eax
0x140057cad  jz      loc_140057FDA
0x140057cb3  mov     eax, [rsi+4Ch]
0x140057cb6  lea     rcx, [rax+rax*2]
0x140057cba  mov     r8d, [r13+rcx*8+4]
0x140057cbf  mov     [r12+r15*8+4], r8d
0x140057cc4  mov     eax, [rsi+4Ch]
0x140057cc7  lea     rcx, [rax+rax*2]
0x140057ccb  test    dl, 2
0x140057cce  jz      loc_140057ED0
0x140057cd4  mov     rcx, [r13+rcx*8+10h]; Handle
0x140057cd9  mov     [rsp+118h+var_C0], rcx
0x140057cde  test    r10, r10
0x140057ce1  jz      short loc_140057D01
0x140057ce3  cmp     rcx, r10
0x140057ce6  jnz     short loc_140057D01
0x140057ce8  mov     rcx, r11; Object
0x140057ceb  call    cs:__imp_ObfReferenceObject
0x140057cf2  nop     dword ptr [rax+rax+00h]
0x140057cf7  mov     r11, [rsp+118h+var_90]
0x140057cff  jmp     short loc_140057D65
0x140057d01  mov     r9b, [r14+40h]; AccessMode
0x140057d05  mov     rax, cs:__imp_IoFileObjectType
0x140057d0c  mov     r8, [rax]; ObjectType
0x140057d0f  mov     [rsp+118h+var_70], rbx
0x140057d17  mov     [rsp+118h+HandleInformation], rbx; HandleInformation
0x140057d1c  lea     rax, [rsp+118h+var_70]
0x140057d24  mov     [rsp+118h+Object], rax; Object
0x140057d29  mov     edx, 1; DesiredAccess
0x140057d2e  call    cs:__imp_ObReferenceObjectByHandle
0x140057d35  nop     dword ptr [rax+rax+00h]
0x140057d3a  mov     r11, [rsp+118h+var_70]
0x140057d42  mov     [rsp+118h+var_90], r11
0x140057d4a  mov     [rsp+118h+var_E4], eax
0x140057d4e  mov     eax, [rsp+118h+var_E4]
0x140057d52  test    eax, eax
0x140057d54  jns     short loc_140057D65
0x140057d56  mov     [rsp+118h+var_E8], 1
0x140057d5b  mov     r15, [rsp+118h+var_D0]
0x140057d60  jmp     loc_14005835D
0x140057d65  mov     [r12+r15*8+10h], r11
0x140057d6a  mov     ecx, [rsi+4Ch]
0x140057d6d  lea     eax, [rcx+1]
0x140057d70  mov     [rsi+4Ch], eax
0x140057d73  lea     rcx, [rcx+rcx*2]
0x140057d77  mov     rax, [r13+rcx*8+8]
0x140057d7c  mov     [r12+r15*8+8], rax
0x140057d81  dec     dword ptr [rsi+4Ch]
0x140057d84  mov     eax, [r11+50h]
0x140057d88  test    al, 2
0x140057d8a  jz      short loc_140057D9C
0x140057d8c  cmp     [r12+r15*8+8], rbx
0x140057d91  jnz     short loc_140057D9C
0x140057d93  mov     rax, [r11+68h]
0x140057d97  mov     [r12+r15*8+8], rax
0x140057d9c  mov     r8d, [r12+r15*8+4]
0x140057da1  test    r8d, r8d
0x140057da4  jnz     loc_140057E56
0x140057daa  xorps   xmm0, xmm0
0x140057dad  xor     eax, eax
0x140057daf  movups  [rsp+118h+FileInformation], xmm0
0x140057db7  mov     [rsp+118h+var_40], rax
0x140057dbf  mov     [rsp+118h+ReturnedLength], ebx
0x140057dc6  lea     rax, [rsp+118h+ReturnedLength]
0x140057dce  mov     [rsp+118h+Object], rax; ReturnedLength
0x140057dd3  lea     r9, [rsp+118h+FileInformation]; FileInformation
0x140057ddb  lea     edx, [r8+5]; FileInformationClass
0x140057ddf  lea     r8d, [rdx+13h]; Length
0x140057de3  mov     rcx, [r12+r15*8+10h]; FileObject
0x140057de8  call    cs:__imp_IoQueryFileInformation
0x140057def  nop     dword ptr [rax+rax+00h]
0x140057df4  mov     [rsp+118h+var_E4], eax
0x140057df8  mov     eax, [rsp+118h+var_E4]
0x140057dfc  test    eax, eax
0x140057dfe  jns     short loc_140057E12
0x140057e00  inc     dword ptr [rsi+4Ch]
0x140057e03  mov     [rsp+118h+var_E8], 1
0x140057e08  mov     r15, [rsp+118h+var_D0]
0x140057e0d  jmp     loc_14005835D
0x140057e12  mov     rax, [r12+r15*8+8]
0x140057e17  test    rax, rax
0x140057e1a  js      short loc_140057E3C
0x140057e1c  mov     r8, qword ptr [rsp+118h+FileInformation+8]
0x140057e24  cmp     rax, r8
0x140057e27  jg      short loc_140057E3C
0x140057e29  sub     r8, rax
0x140057e2c  cmp     r8, 7FFFFFFFh
0x140057e33  jg      short loc_140057E3C
0x140057e35  mov     [r12+r15*8+4], r8d
0x140057e3a  jmp     short loc_140057E7A
0x140057e3c  inc     dword ptr [rsi+4Ch]
0x140057e3f  mov     [rsp+118h+var_E4], 0C000000Dh
0x140057e47  mov     [rsp+118h+var_E8], 1
  ... truncated ...
```
