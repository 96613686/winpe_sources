# AfdTliIoControl

- ea: `0x14002a1e0`
- end: `0x14002abcf`
- name: `AfdTliIoControl`
- size: `2543`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000fcd0`
- `0x14001c708`
- `0x14001e7e0`
- `0x140026e80`
- `0x140027470`
- `0x14002a1e0`
- `0x14002abe0`
- `0x14002ac10`
- `0x14002fd7c`
- `0x1400445d8`
- `0x140066c9c`
- `0x140066eb4`
- `0x140072840`
- `0x140072870`
- `0x140072920`
- `0x140072c80`
- `0x140092110`
- `0x14009214c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14002a6ae`
- `ntoskrnl!ProbeForRead` at `0x14002a6ae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a392`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a392`
- `ntoskrnl!IoFreeMdl` at `0x140078c94`
- `ntoskrnl!IoFreeMdl` at `0x140078c94`
- `ntoskrnl!MmUnlockPages` at `0x140078c84`
- `ntoskrnl!MmUnlockPages` at `0x140078c84`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a363`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a363`
- `ntoskrnl!IoAllocateMdl` at `0x14002a33e`
- `ntoskrnl!IoAllocateMdl` at `0x14002a33e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002a600`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002a600`
- `ntoskrnl!IofCompleteRequest` at `0x14002a9f2`
- `ntoskrnl!IofCompleteRequest` at `0x140078b1c`
- `ntoskrnl!IofCompleteRequest` at `0x140078bdb`
- `ntoskrnl!IofCompleteRequest` at `0x140078cf9`
- `ntoskrnl!IofCompleteRequest` at `0x14002a9f2`
- `ntoskrnl!IofCompleteRequest` at `0x140078b1c`
- `ntoskrnl!IofCompleteRequest` at `0x140078bdb`
- `ntoskrnl!IofCompleteRequest` at `0x140078cf9`
- `ntoskrnl!ObfDereferenceObject` at `0x140078cb3`
- `ntoskrnl!ObfDereferenceObject` at `0x140078cb3`
- `ntoskrnl!IofCallDriver` at `0x140078c4b`
- `ntoskrnl!IofCallDriver` at `0x140078c4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aa52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078cdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aa52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078cdc`
- `ntoskrnl!ExAllocatePool2` at `0x14002a2bb`
- `ntoskrnl!ExAllocatePool2` at `0x14002a3ff`
- `ntoskrnl!ExAllocatePool2` at `0x14002a51f`
- `ntoskrnl!ExAllocatePool2` at `0x14002a6d5`
- `ntoskrnl!ExAllocatePool2` at `0x14002a2bb`
- `ntoskrnl!ExAllocatePool2` at `0x14002a3ff`
- `ntoskrnl!ExAllocatePool2` at `0x14002a51f`
- `ntoskrnl!ExAllocatePool2` at `0x14002a6d5`
- `ntoskrnl!IoIs32bitProcess` at `0x14002a25e`
- `ntoskrnl!IoIs32bitProcess` at `0x14002a25e`

## pseudocode

```c
__int64 __fastcall AfdTliIoControl(PIRP Irp, __int64 a2)
{
  __int64 v2; // r12
  unsigned int *Pool2; // rdi
  __int64 v5; // rsi
  BOOLEAN v6; // al
  unsigned int v7; // ecx
  KPROCESSOR_MODE *p_RequestorMode; // r15
  void *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // ecx
  char v13; // r8
  __int64 v14; // rdx
  ULONG v15; // edx
  struct _MDL *Mdl; // rax
  __int64 v17; // rcx
  PVOID v18; // rax
  void *v19; // rax
  size_t v20; // r8
  void *v21; // rdx
  KPROCESSOR_MODE RequestorMode; // cl
  void *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  char v27; // r8
  __int64 ULong64FromUser; // rax
  _DWORD *v29; // r8
  int i; // eax
  signed int ULongFromUser; // eax
  unsigned __int64 v32; // r13
  __int64 v33; // r12
  _DWORD *v34; // rax
  int v35; // r12d
  int v36; // eax
  int v37; // eax
  signed __int32 v38; // edx
  __int64 ConnectionReferenceFromEndpoint; // r15
  __int64 v40; // rax
  unsigned int v41; // esi
  __int64 v42; // r8
  IRP *v43; // rcx
  void *v45; // rcx
  signed __int64 v46; // rax
  bool v47; // cc
  signed __int64 v48; // rax
  signed __int64 v49; // rax
  signed __int64 v50; // rax
  unsigned int v51; // eax
  __int64 v52; // r8
  __int64 v53; // rcx
  __int64 v54; // r8
  struct _DEVICE_OBJECT *v55; // rcx
  struct _FILE_OBJECT *v56; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  NTSTATUS v61; // [rsp+30h] [rbp-108h]
  char v62; // [rsp+34h] [rbp-104h]
  char v63; // [rsp+35h] [rbp-103h]
  int v64; // [rsp+38h] [rbp-100h]
  __int64 v65; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v66; // [rsp+48h] [rbp-F0h] BYREF
  __int128 v67; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v68; // [rsp+60h] [rbp-D8h]
  unsigned int *v69; // [rsp+70h] [rbp-C8h]
  _QWORD v70[10]; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+D0h] [rbp-68h]
  __int64 v72; // [rsp+D8h] [rbp-60h]
  _DWORD *v73; // [rsp+E0h] [rbp-58h]
  PIRP v74; // [rsp+E8h] [rbp-50h]
  __int128 v75; // [rsp+F0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+100h] [rbp-38h]

  v2 = a2;
  v71 = a2;
  v74 = Irp;
  v63 = 0;
  v62 = 0;
  v67 = 0;
  v68 = 0;
  v66 = 0;
  Pool2 = 0;
  v69 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 8) & 0x200) == 0 )
  {
    v61 = -1073741808;
    goto LABEL_114;
  }
  v6 = IoIs32bitProcess(Irp);
  v7 = *(_DWORD *)(v2 + 16);
  if ( v6 )
  {
    v75 = 0;
    v76 = 0;
    if ( v7 < 0x18 )
    {
      v61 = -1073741811;
      goto LABEL_114;
    }
    p_RequestorMode = &Irp->RequestorMode;
    RequestorMode = Irp->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(v2 + 32) & 3) != 0 )
LABEL_52:
      ExRaiseDatatypeMisalignment();
    v23 = *(void **)(v2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(&v75, v23, 0x18u);
    else
      RtlCopyVolatileMemory(&v75, v23, 0x18u);
    *(_QWORD *)&v67 = v75;
    DWORD2(v67) = DWORD2(v75);
    BYTE12(v67) = BYTE12(v75);
    *(_QWORD *)&v68 = (unsigned int)v76;
    *((_QWORD *)&v68 + 1) = HIDWORD(v76);
    if ( (_DWORD)v75 == 3 && (DWORD2(v75) == 1074033787 || DWORD2(v75) == 536900730) && BYTE12(v75) )
      return AfdHandleISBIoctls(&v67, Irp, v2);
    Pool2 = (unsigned int *)ExAllocatePool2(97, 88, 1281648193);
    v69 = Pool2;
    *(_OWORD *)Pool2 = v67;
    *((_OWORD *)Pool2 + 1) = v68;
    LOBYTE(v24) = *((_BYTE *)Pool2 + 12);
    if ( !(unsigned __int8)AfdAllowedUserIOControlRequest(*Pool2, Pool2[1], v24) )
    {
      v61 = -1073741811;
      goto LABEL_114;
    }
    if ( (_DWORD)v26 == 3 && v27 && Pool2[2] == -939524071 )
    {
      v32 = (unsigned int)v76;
      if ( !*p_RequestorMode )
        goto LABEL_65;
      if ( (v76 & 3) != 0 )
        goto LABEL_52;
      if ( *p_RequestorMode )
        ULongFromUser = RtlReadULongFromUser((unsigned int)v76);
      else
LABEL_65:
        ULongFromUser = *(_DWORD *)(unsigned int)v76;
      LODWORD(v65) = ULongFromUser;
      if ( (unsigned int)ULongFromUser > 0xFFFF )
      {
        v61 = -1073741811;
        goto LABEL_114;
      }
      v33 = ULongFromUser;
      if ( *p_RequestorMode )
        ProbeForRead((volatile void *)v32, 8LL * ULongFromUser + 4, 4u);
      v66 = 16 * v33 + 8;
      v34 = (_DWORD *)ExAllocatePool2(97, v66, 543450689);
      v73 = v34;
      *((_QWORD *)Pool2 + 10) = v34;
      v35 = v65;
      *v34 = v65;
      for ( i = 0; ; i = v64 + 1 )
      {
        v64 = i;
        if ( i >= v35 )
          break;
        v65 = 0;
        v72 = i;
        if ( Irp->RequestorMode )
        {
          ULong64FromUser = RtlReadULong64FromUser(v32 + 4 + 8LL * i);
          v65 = ULong64FromUser;
        }
        else
        {
          RtlCopyVolatileMemory(&v65, (const void *)(v32 + 4 + 8LL * i), 8u);
          LODWORD(ULong64FromUser) = v65;
        }
        v25 = 2 * v72;
        v29 = v73;
        v73[2 * v25 + 4] = HIDWORD(v65);
        v26 = (unsigned int)ULong64FromUser;
        *(_QWORD *)&v29[2 * v25 + 2] = (unsigned int)ULong64FromUser;
      }
      v2 = v71;
    }
    if ( *Pool2 == 3 )
    {
      if ( *((_BYTE *)Pool2 + 12) )
      {
        if ( Pool2[2] == -2013265909 )
        {
          v63 = 1;
          LOBYTE(v25) = *p_RequestorMode;
          LOBYTE(v26) = 1;
          v61 = AfdTliIoControlHandleSetQoS(v26, v25, Pool2, &v66);
          if ( v61 < 0 )
            goto LABEL_114;
        }
      }
      if ( *Pool2 == 3 )
      {
        if ( *((_BYTE *)Pool2 + 12) )
        {
          if ( Pool2[2] == -2013265894 )
          {
            v62 = 1;
            LOBYTE(v25) = *p_RequestorMode;
            LOBYTE(v26) = 1;
            v61 = AfdTliIoControlHandleAssociateQoS(v26, v25, Pool2, &v66);
            if ( v61 < 0 )
              goto LABEL_114;
          }
        }
      }
    }
    if ( *Pool2 != 1 || !*((_BYTE *)Pool2 + 12) || Pool2[2] != 12292 || !*(_QWORD *)(v5 + 88) )
      goto LABEL_11;
    v61 = -1073741436;
    goto LABEL_114;
  }
  if ( v7 < 0x20 )
  {
    v61 = -1073741811;
  }
  else
  {
    p_RequestorMode = &Irp->RequestorMode;
    v9 = *(void **)(v2 + 32);
    if ( Irp->RequestorMode )
      RtlCopyFromUser(&v67, v9, 0x20u);
    else
      RtlCopyVolatileMemory(&v67, v9, 0x20u);
    if ( (_DWORD)v67 == 3 && (DWORD2(v67) == 1074033787 || DWORD2(v67) == 536900730) && BYTE12(v67) )
      return AfdHandleISBIoctls(&v67, Irp, v2);
    Pool2 = (unsigned int *)ExAllocatePool2(97, 88, 1281648193);
    v69 = Pool2;
    *(_OWORD *)Pool2 = v67;
    *((_OWORD *)Pool2 + 1) = v68;
    LOBYTE(v10) = *((_BYTE *)Pool2 + 12);
    if ( (unsigned __int8)AfdAllowedUserIOControlRequest(*Pool2, Pool2[1], v10) )
    {
      if ( v12 == 3 )
      {
        if ( v13 )
        {
          if ( Pool2[2] == -2013265909 )
          {
            v63 = 1;
            LOBYTE(v11) = *p_RequestorMode;
            v36 = AfdTliIoControlHandleSetQoS(0, v11, Pool2, &v66);
            v61 = v36;
            if ( v36 < 0 )
              goto LABEL_114;
          }
        }
      }
      if ( *Pool2 == 3 )
      {
        if ( *((_BYTE *)Pool2 + 12) )
        {
          if ( Pool2[2] == -2013265894 )
          {
            v62 = 1;
            LOBYTE(v11) = *p_RequestorMode;
            v37 = AfdTliIoControlHandleAssociateQoS(0, v11, Pool2, &v66);
            v61 = v37;
            if ( v37 < 0 )
              goto LABEL_114;
          }
        }
      }
      if ( *Pool2 == 1 && *((_BYTE *)Pool2 + 12) && Pool2[2] == 12292 && *(_QWORD *)(v5 + 88) )
      {
        v61 = -1073741436;
        goto LABEL_114;
      }
LABEL_11:
      *((_QWORD *)Pool2 + 5) = Irp;
      v14 = *((_QWORD *)Pool2 + 3);
      if ( v14 )
      {
        v19 = (void *)ExAllocatePool2(97, v14, 1768187457);
        *((_QWORD *)Pool2 + 7) = v19;
        v20 = *((_QWORD *)Pool2 + 3);
        v21 = (void *)*((_QWORD *)Pool2 + 2);
        if ( *p_RequestorMode )
          RtlCopyFromUser(v19, v21, v20);
        else
          RtlCopyVolatileMemory(v19, v21, v20);
      }
      v15 = *(_DWORD *)(v2 + 8);
      if ( v15 )
      {
        Mdl = IoAllocateMdl(Irp->UserBuffer, v15, 0, 1u, 0);
        *((_QWORD *)Pool2 + 8) = Mdl;
        if ( !Mdl )
        {
          v61 = -1073741670;
          goto LABEL_114;
        }
        MmProbeAndLockPages(Mdl, *p_RequestorMode, IoWriteAccess);
        v17 = *((_QWORD *)Pool2 + 8);
        if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
          v18 = *(PVOID *)(v17 + 24);
        else
          v18 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000020u);
        *((_QWORD *)Pool2 + 9) = v18;
        if ( !v18 )
        {
          v61 = -1073741670;
          goto LABEL_114;
        }
      }
      Irp->IoStatus.Status = 0;
      Irp->IoStatus.Information = 0;
      if ( *((_BYTE *)Pool2 + 12) )
      {
        memset(v70, 0, sizeof(v70));
        do
        {
          v38 = *(_DWORD *)(v5 + 368);
          if ( v38 > 0 )
            goto LABEL_113;
        }
        while ( v38 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 368), v38 - 1, v38) );
        if ( (*(_WORD *)v5 & 0xAFD2) == 0xAFD2 && *(_BYTE *)(v5 + 2) == 4 )
        {
          ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v5);
          if ( !ConnectionReferenceFromEndpoint )
            goto LABEL_131;
        }
        else
        {
          if ( *(_BYTE *)(v5 + 2) != 2
            && ((*(_DWORD *)(v5 + 8) & 0x200) == 0 || *(_BYTE *)(v5 + 2) != 1)
            && (unsigned __int8)(*(_BYTE *)(v5 + 2) - 3) > 1u )
          {
LABEL_131:
            _InterlockedIncrement((volatile signed __int32 *)(v5 + 368));
LABEL_113:
            v61 = -1073741436;
            goto LABEL_114;
          }
          ConnectionReferenceFromEndpoint = 0;
        }
        *((_QWORD *)Pool2 + 4) = v5;
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v5 + 64)) <= 1 )
          __fastfail(0xEu);
        v70[0] = AfdCompleteTliIoControl;
        v70[1] = Pool2;
        v70[2] = *(_QWORD *)Pool2;
        LODWORD(v70[3]) = Pool2[2];
        if ( *((_QWORD *)Pool2 + 10) )
        {
          v70[4] = *((_QWORD *)Pool2 + 10);
          v70[5] = v66;
          if ( !v63 && !v62 )
          {
            v70[6] = *((_QWORD *)Pool2 + 10);
            v70[7] = v66;
LABEL_107:
            if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 )
            {
              Irp->Tail.Overlay.DriverContext[2] = 0;
              if ( ConnectionReferenceFromEndpoint )
              {
                v41 = AfdTLIoControl(
                        *(_QWORD *)(*(_QWORD *)(ConnectionReferenceFromEndpoint + 24) + 8LL),
                        *(_QWORD *)(ConnectionReferenceFromEndpoint + 16),
                        v70,
                        0);
                v46 = _InterlockedExchangeAdd64(
                        (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
                        0xFFFFFFFFFFFFFFFFuLL);
                v47 = v46 <= 1;
                v48 = v46 - 1;
                if ( v47 )
                {
                  if ( v48 )
                    __fastfail(0xEu);
                  AfdCloseConnection(ConnectionReferenceFromEndpoint);
                }
              }
              else
              {
                v41 = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 8LL), *(_QWORD *)(v5 + 16), v70, v5);
              }
              v43 = Irp;
              if ( v41 != 259 )
                goto LABEL_111;
              LOBYTE(v42) = 1;
              if ( !(unsigned __int8)AfdTLPendRequest(Irp, v70[8], v42) )
                goto LABEL_151;
            }
            else if ( *(_BYTE *)(v5 + 2) == 1 )
            {
              Irp->Tail.Overlay.DriverContext[2] = 0;
              v53 = *(_QWORD *)(v5 + 504);
              if ( !v53 )
              {
                v41 = -1073741436;
                AfdCompleteTliIoControl(v70[1], 3221225860LL, 0);
LABEL_151:
                v43 = Irp;
LABEL_111:
                IofCompleteRequest(v43, AfdPriorityBoost);
                return v41;
              }
              v41 = AfdTLIoControl(*(_QWORD *)(v53 + 8), *(_QWORD *)(v5 + 496), v70, 0);
              v43 = Irp;
              if ( v41 != 259 )
                goto LABEL_111;
              LOBYTE(v54) = 1;
              if ( !(unsigned __int8)AfdTLPendRequest(Irp, v70[8], v54) )
                IofCompleteRequest(Irp, AfdPriorityBoost);
              return 259;
            }
            else
            {
              if ( ConnectionReferenceFromEndpoint )
              {
                v55 = *(struct _DEVICE_OBJECT **)(ConnectionReferenceFromEndpoint + 24);
                v56 = *(struct _FILE_OBJECT **)(ConnectionReferenceFromEndpoint + 16);
              }
              else
              {
                v55 = *(struct _DEVICE_OBJECT **)(v5 + 40);
                v56 = *(struct _FILE_OBJECT **)(v5 + 24);
              }
              CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
              CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdTditlRestartControlRequest;
              CurrentStackLocation[-1].Context = Pool2;
              CurrentStackLocation[-1].Control = -32;
              v58 = Irp->Tail.Overlay.CurrentStackLocation;
              v58[-1].FileObject = v56;
              v58[-1].DeviceObject = v55;
              *(_WORD *)&v58[-1].MajorFunction = 20495;
              v58[-1].Parameters.QueryDirectory.FileName = (PUNICODE_STRING)v70;
              _InterlockedIncrement((volatile signed __int32 *)(v5 + 248));
              v41 = IofCallDriver(v55, Irp);
              if ( v41 == -1073741306 )
                v41 = -1073741789;
              if ( ConnectionReferenceFromEndpoint )
              {
                v49 = _InterlockedExchangeAdd64(
                        (volatile signed __int64 *)(ConnectionReferenceFromEndpoint + 48),
                        0xFFFFFFFFFFFFFFFFuLL);
                v47 = v49 <= 1;
                v50 = v49 - 1;
                if ( v47 )
                {
                  if ( v50 )
                    __fastfail(0xEu);
                  AfdCloseConnection(ConnectionReferenceFromEndpoint);
                }
              }
            }
            return v41;
          }
          v70[6] = *((_QWORD *)Pool2 + 9);
          v40 = *(unsigned int *)(v71 + 8);
        }
        else
        {
          v70[4] = *((_QWORD *)Pool2 + 7);
          v70[5] = *((_QWORD *)Pool2 + 3);
          v70[6] = *((_QWORD *)Pool2 + 9);
          v40 = *(unsigned int *)(v2 + 8);
        }
        v70[7] = v40;
        goto LABEL_107;
      }
      memset(v70, 0, 0x48u);
      v70[0] = AfdCompleteTliIoControl;
      v70[1] = Pool2;
      LODWORD(v70[2]) = Pool2[2];
      v70[3] = *((_QWORD *)Pool2 + 7);
      v70[4] = *((_QWORD *)Pool2 + 3);
      v70[5] = *((_QWORD *)Pool2 + 9);
      v70[6] = *(unsigned int *)(v2 + 8);
      Irp->Tail.Overlay.DriverContext[2] = 0;
      v51 = (**(__int64 (__fastcall ***)(_QWORD, _QWORD *))(*(_QWORD *)(v5 + 272) + 40LL))(
              *(_QWORD *)(*(_QWORD *)(v5 + 272) + 32LL),
              v70);
      v41 = v51;
      if ( v51 == 259 )
      {
        LOBYTE(v52) = 1;
        if ( (unsigned __int8)AfdTLPendRequest(Irp, v70[7], v52) )
          goto LABEL_146;
      }
      else
      {
        AfdCompleteTliIoControl(Pool2, v51, v70[8]);
      }
      IofCompleteRequest(Irp, AfdPriorityBoost);
LABEL_146:
      if ( v41 == -1073741306 )
        return (unsigned int)-1073741789;
      return v41;
    }
    v61 = -1073741811;
  }
LABEL_114:
  if ( Pool2 )
  {
    v45 = (void *)*((_QWORD *)Pool2 + 7);
    if ( v45 )
      ExFreePoolWithTag(v45, 0x69646641u);
    v59 = *((_QWORD *)Pool2 + 8);
    if ( v59 )
    {
      if ( (*(_BYTE *)(v59 + 10) & 2) != 0 )
        MmUnlockPages((PMDL)v59);
      IoFreeMdl(*((PMDL *)Pool2 + 8));
    }
    v60 = *((_QWORD *)Pool2 + 10);
    if ( v60 )
    {
      if ( v62 )
        ObfDereferenceObject(*(PVOID *)(v60 + 8));
      ExFreePoolWithTag(*((PVOID *)Pool2 + 10), 0x20646641u);
    }
    ExFreePoolWithTag(Pool2, 0x4C646641u);
  }
  Irp->IoStatus.Status = v61;
  IofCompleteRequest(Irp, AfdPriorityBoost);
  return (unsigned int)v61;
}

```

## disassembly

```asm
0x14002a1e0  mov     [rsp+arg_10], rbx
0x14002a1e5  mov     [rsp+arg_18], rsi
0x14002a1ea  push    rdi
0x14002a1eb  push    r12
0x14002a1ed  push    r13
0x14002a1ef  push    r14
0x14002a1f1  push    r15
0x14002a1f3  sub     rsp, 110h
0x14002a1fa  mov     rax, cs:__security_cookie
0x14002a201  xor     rax, rsp
0x14002a204  mov     [rsp+138h+var_30], rax
0x14002a20c  mov     r12, rdx
0x14002a20f  mov     [rsp+138h+var_68], rdx
0x14002a217  mov     r14, rcx
0x14002a21a  mov     [rsp+138h+var_50], rcx
0x14002a222  xor     ebx, ebx
0x14002a224  mov     [rsp+138h+var_103], bl
0x14002a228  mov     [rsp+138h+var_104], bl
0x14002a22c  xorps   xmm0, xmm0
0x14002a22f  movups  [rsp+138h+var_E8], xmm0
0x14002a234  movups  [rsp+138h+var_D8], xmm0
0x14002a239  mov     [rsp+138h+var_F0], rbx
0x14002a23e  mov     [rsp+138h+var_108], ebx
0x14002a242  mov     edi, ebx
0x14002a244  mov     [rsp+138h+var_C8], rbx
0x14002a249  mov     rax, [rdx+30h]
0x14002a24d  mov     rsi, [rax+18h]
0x14002a251  mov     eax, [rsi+8]
0x14002a254  bt      eax, 8
0x14002a258  jnb     loc_14002AAF9
0x14002a25e  call    cs:__imp_IoIs32bitProcess
0x14002a265  nop     dword ptr [rax+rax+00h]
0x14002a26a  mov     ecx, [r12+10h]
0x14002a26f  test    al, al
0x14002a271  jnz     loc_14002A476
0x14002a277  mov     r8d, 20h ; ' '; Size
0x14002a27d  cmp     ecx, r8d
0x14002a280  jb      loc_14002A7D5
0x14002a286  lea     r15, [r14+40h]
0x14002a28a  mov     rdx, [r12+20h]; Src
0x14002a28f  lea     rcx, [rsp+138h+var_E8]; void *
0x14002a294  cmp     [r15], bl
0x14002a297  jz      loc_14002A463
0x14002a29d  call    RtlCopyFromUser
0x14002a2a2  cmp     dword ptr [rsp+138h+var_E8], 3
0x14002a2a7  jz      loc_14002A3B0
0x14002a2ad  mov     edx, 58h ; 'X'
0x14002a2b2  lea     ecx, [rdx+9]
0x14002a2b5  mov     r8d, 4C646641h
0x14002a2bb  call    cs:__imp_ExAllocatePool2
0x14002a2c2  nop     dword ptr [rax+rax+00h]
0x14002a2c7  mov     rdi, rax
0x14002a2ca  mov     [rsp+138h+var_C8], rax
0x14002a2cf  movups  xmm0, [rsp+138h+var_E8]
0x14002a2d4  movups  xmmword ptr [rax], xmm0
0x14002a2d7  movups  xmm1, [rsp+138h+var_D8]
0x14002a2dc  movups  xmmword ptr [rax+10h], xmm1
0x14002a2e0  mov     r8b, [rax+0Ch]
0x14002a2e4  mov     ecx, [rax]
0x14002a2e6  mov     edx, [rax+4]
0x14002a2e9  call    AfdAllowedUserIOControlRequest
0x14002a2ee  test    al, al
0x14002a2f0  jz      loc_14002A7E2
0x14002a2f6  cmp     ecx, 3
0x14002a2f9  jz      loc_14002A42D
0x14002a2ff  cmp     dword ptr [rdi], 3
0x14002a302  jz      loc_14002A3D9
0x14002a308  cmp     dword ptr [rdi], 1
0x14002a30b  jz      loc_14002A448
0x14002a311  mov     [rdi+28h], r14
0x14002a315  mov     rdx, [rdi+18h]
0x14002a319  test    rdx, rdx
0x14002a31c  jnz     loc_14002A3F4
0x14002a322  mov     edx, [r12+8]; Length
0x14002a327  test    edx, edx
0x14002a329  jz      loc_14002A88B
0x14002a32f  mov     [rsp+138h+Irp], rbx; Irp
0x14002a334  mov     r9b, 1; ChargeQuota
0x14002a337  xor     r8d, r8d; SecondaryBuffer
0x14002a33a  mov     rcx, [r14+70h]; VirtualAddress
0x14002a33e  call    cs:__imp_IoAllocateMdl
0x14002a345  nop     dword ptr [rax+rax+00h]
0x14002a34a  mov     [rdi+40h], rax
0x14002a34e  test    rax, rax
0x14002a351  jz      loc_14002A871
0x14002a357  mov     r8d, 1; Operation
0x14002a35d  mov     dl, [r15]; AccessMode
0x14002a360  mov     rcx, rax; MemoryDescriptorList
0x14002a363  call    cs:__imp_MmProbeAndLockPages
0x14002a36a  nop     dword ptr [rax+rax+00h]
0x14002a36f  mov     rcx, [rdi+40h]; MemoryDescriptorList
0x14002a373  test    byte ptr [rcx+0Ah], 5
0x14002a377  jnz     loc_14002A46D
0x14002a37d  mov     [rsp+138h+Priority], 40000020h; Priority
0x14002a385  mov     dword ptr [rsp+138h+Irp], ebx; BugCheckOnFailure
0x14002a389  xor     r9d, r9d; RequestedAddress
0x14002a38c  xor     edx, edx; AccessMode
0x14002a38e  lea     r8d, [r9+1]; CacheType
0x14002a392  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002a399  nop     dword ptr [rax+rax+00h]
0x14002a39e  mov     [rdi+48h], rax
0x14002a3a2  test    rax, rax
0x14002a3a5  jz      loc_14002A87E
0x14002a3ab  jmp     loc_14002A88B
0x14002a3b0  cmp     dword ptr [rsp+138h+var_E8+8], 4004747Bh
0x14002a3b8  jnz     short loc_14002A3C9
0x14002a3ba  cmp     byte ptr [rsp+138h+var_E8+0Ch], bl
0x14002a3be  jz      loc_14002A2AD
0x14002a3c4  jmp     loc_14002AA64
0x14002a3c9  cmp     dword ptr [rsp+138h+var_E8+8], 2000747Ah
0x14002a3d1  jnz     loc_14002A2AD
0x14002a3d7  jmp     short loc_14002A3BA
0x14002a3d9  cmp     [rdi+0Ch], bl
0x14002a3dc  jz      loc_14002A308
0x14002a3e2  cmp     dword ptr [rdi+8], 8800001Ah
0x14002a3e9  jnz     loc_14002A308
0x14002a3ef  jmp     loc_14002A823
0x14002a3f4  mov     ecx, 61h ; 'a'
0x14002a3f9  mov     r8d, 69646641h
0x14002a3ff  call    cs:__imp_ExAllocatePool2
0x14002a406  nop     dword ptr [rax+rax+00h]
0x14002a40b  mov     [rdi+38h], rax
0x14002a40f  mov     r8, [rdi+18h]; Size
0x14002a413  mov     rdx, [rdi+10h]; Src
0x14002a417  mov     rcx, rax; void *
0x14002a41a  cmp     [r15], bl
0x14002a41d  jz      loc_14002A867
0x14002a423  call    RtlCopyFromUser
0x14002a428  jmp     loc_14002A322
0x14002a42d  test    r8b, r8b
0x14002a430  jz      loc_14002A2FF
0x14002a436  cmp     dword ptr [rdi+8], 8800000Bh
0x14002a43d  jnz     loc_14002A2FF
0x14002a443  jmp     loc_14002A7EF
0x14002a448  cmp     [rdi+0Ch], bl
0x14002a44b  jz      loc_14002A311
0x14002a451  cmp     dword ptr [rdi+8], 3004h
0x14002a458  jnz     loc_14002A311
0x14002a45e  jmp     loc_14002A84F
0x14002a463  call    RtlCopyVolatileMemory
0x14002a468  jmp     loc_14002A2A2
0x14002a46d  mov     rax, [rcx+18h]
0x14002a471  jmp     loc_14002A39E
0x14002a476  xorps   xmm0, xmm0
0x14002a479  xor     eax, eax
0x14002a47b  movups  [rsp+138h+var_48], xmm0
0x14002a483  mov     [rsp+138h+var_38], rax
0x14002a48b  lea     r8d, [rax+18h]; Size
0x14002a48f  cmp     ecx, r8d
0x14002a492  jb      loc_14002A621
0x14002a498  lea     r15, [r14+40h]
0x14002a49c  mov     cl, [r15]
0x14002a49f  test    cl, cl
0x14002a4a1  jnz     loc_14002A5F4
0x14002a4a7  mov     rdx, [r12+20h]; Src
0x14002a4ac  test    cl, cl
0x14002a4ae  lea     rcx, [rsp+138h+var_48]; void *
0x14002a4b6  jz      loc_14002A57A
0x14002a4bc  call    RtlCopyFromUser
0x14002a4c1  mov     rcx, qword ptr [rsp+138h+var_48]
0x14002a4c9  mov     dword ptr [rsp+138h+var_E8], ecx
0x14002a4cd  mov     eax, dword ptr [rsp+138h+var_48+4]
0x14002a4d4  mov     dword ptr [rsp+138h+var_E8+4], eax
0x14002a4d8  mov     edx, dword ptr [rsp+138h+var_48+8]
0x14002a4df  mov     dword ptr [rsp+138h+var_E8+8], edx
0x14002a4e3  mov     r8b, byte ptr [rsp+138h+var_48+0Ch]
0x14002a4eb  mov     byte ptr [rsp+138h+var_E8+0Ch], r8b
0x14002a4f0  mov     eax, dword ptr [rsp+138h+var_38]
0x14002a4f7  mov     qword ptr [rsp+138h+var_D8], rax
0x14002a4fc  mov     eax, dword ptr [rsp+138h+var_38+4]
0x14002a503  mov     qword ptr [rsp+138h+var_D8+8], rax
0x14002a508  cmp     ecx, 3
0x14002a50b  jz      loc_14002A62E
0x14002a511  mov     edx, 58h ; 'X'
0x14002a516  lea     ecx, [rdx+9]
0x14002a519  mov     r8d, 4C646641h
0x14002a51f  call    cs:__imp_ExAllocatePool2
0x14002a526  nop     dword ptr [rax+rax+00h]
0x14002a52b  mov     rdi, rax
0x14002a52e  mov     [rsp+138h+var_C8], rax
0x14002a533  movups  xmm0, [rsp+138h+var_E8]
0x14002a538  movups  xmmword ptr [rax], xmm0
0x14002a53b  movups  xmm1, [rsp+138h+var_D8]
0x14002a540  movups  xmmword ptr [rax+10h], xmm1
0x14002a544  mov     r8b, [rax+0Ch]
0x14002a548  mov     ecx, [rax]
0x14002a54a  mov     edx, [rax+4]
0x14002a54d  call    AfdAllowedUserIOControlRequest
0x14002a552  test    al, al
0x14002a554  jz      loc_14002A650
0x14002a55a  cmp     ecx, 3
0x14002a55d  jz      loc_14002A65D
0x14002a563  cmp     dword ptr [rdi], 3
0x14002a566  jz      loc_14002A71E
0x14002a56c  cmp     dword ptr [rdi], 1
0x14002a56f  jnz     loc_14002A311
0x14002a575  jmp     loc_14002A7A7
0x14002a57a  call    RtlCopyVolatileMemory
0x14002a57f  jmp     loc_14002A4C1
0x14002a584  mov     [rsp+138h+var_F8], rbx
0x14002a589  movsxd  rcx, eax
0x14002a58c  mov     [rsp+138h+var_60], rcx
0x14002a594  lea     rdx, [r13+4]
0x14002a598  lea     rdx, [rdx+rcx*8]; Src
0x14002a59c  cmp     [r14+40h], bl
0x14002a5a0  jz      short loc_14002A5DD
0x14002a5a2  mov     rcx, rdx
0x14002a5a5  call    RtlReadULong64FromUser
0x14002a5aa  mov     [rsp+138h+var_F8], rax
0x14002a5af  mov     rdx, [rsp+138h+var_60]
0x14002a5b7  add     rdx, rdx
0x14002a5ba  mov     ecx, dword ptr [rsp+138h+var_F8+4]
0x14002a5be  mov     r8, [rsp+138h+var_58]
0x14002a5c6  mov     [r8+rdx*8+10h], ecx
0x14002a5cb  mov     ecx, eax
0x14002a5cd  mov     [r8+rdx*8+8], rcx
0x14002a5d2  mov     eax, [rsp+138h+var_100]
0x14002a5d6  inc     eax
0x14002a5d8  jmp     loc_14002A6F7
0x14002a5dd  mov     r8d, 8; Size
0x14002a5e3  lea     rcx, [rsp+138h+var_F8]; void *
0x14002a5e8  call    RtlCopyVolatileMemory
0x14002a5ed  mov     rax, [rsp+138h+var_F8]
0x14002a5f2  jmp     short loc_14002A5AF
0x14002a5f4  test    byte ptr [r12+20h], 3
0x14002a5fa  jz      loc_14002A4A7
0x14002a600  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14002a607  nop     dword ptr [rax+rax+00h]
0x14002a60c  int     3; Trap to Debugger
0x14002a60d  test    r13b, 3
0x14002a611  jnz     short loc_14002A600
0x14002a613  test    al, al
0x14002a615  jz      short loc_14002A686
0x14002a617  mov     rcx, r13
0x14002a61a  call    RtlReadULongFromUser
0x14002a61f  jmp     short loc_14002A68A
0x14002a621  mov     [rsp+138h+var_108], 0C000000Dh
0x14002a629  jmp     loc_14002AA37
0x14002a62e  cmp     edx, 4004747Bh
0x14002a634  jz      short loc_14002A642
0x14002a636  cmp     edx, 2000747Ah
0x14002a63c  jnz     loc_14002A511
0x14002a642  test    r8b, r8b
0x14002a645  jz      loc_14002A511
0x14002a64b  jmp     loc_14002AA64
0x14002a650  mov     [rsp+138h+var_108], 0C000000Dh
0x14002a658  jmp     loc_14002AA37
0x14002a65d  test    r8b, r8b
0x14002a660  jz      loc_14002A563
0x14002a666  cmp     dword ptr [rdi+8], 0C8000019h
0x14002a66d  jnz     loc_14002A563
0x14002a673  mov     r13d, dword ptr [rsp+138h+var_38]
0x14002a67b  mov     [rsp+138h+var_100], ebx
0x14002a67f  mov     al, [r15]
0x14002a682  test    al, al
0x14002a684  jnz     short loc_14002A60D
0x14002a686  mov     eax, [r13+0]
0x14002a68a  mov     dword ptr [rsp+138h+var_F8], eax
0x14002a68e  cmp     eax, 0FFFFh
0x14002a693  ja      short loc_14002A711
0x14002a695  movsxd  r12, eax
0x14002a698  cmp     [r15], bl
0x14002a69b  jz      short loc_14002A6BA
0x14002a69d  lea     rdx, ds:4[r12*8]; Length
0x14002a6a5  mov     r8d, 4; Alignment
0x14002a6ab  mov     rcx, r13; Address
0x14002a6ae  call    cs:__imp_ProbeForRead
0x14002a6b5  nop     dword ptr [rax+rax+00h]
0x14002a6ba  shl     r12, 4
0x14002a6be  add     r12, 8
0x14002a6c2  mov     [rsp+138h+var_F0], r12
0x14002a6c7  mov     r8d, 20646641h
0x14002a6cd  mov     rdx, r12
0x14002a6d0  mov     ecx, 61h ; 'a'
0x14002a6d5  call    cs:__imp_ExAllocatePool2
0x14002a6dc  nop     dword ptr [rax+rax+00h]
0x14002a6e1  mov     [rsp+138h+var_58], rax
0x14002a6e9  mov     [rdi+50h], rax
0x14002a6ed  mov     r12d, dword ptr [rsp+138h+var_F8]
0x14002a6f2  mov     [rax], r12d
0x14002a6f5  mov     eax, ebx
0x14002a6f7  mov     [rsp+138h+var_100], eax
0x14002a6fb  cmp     eax, r12d
0x14002a6fe  jl      loc_14002A584
0x14002a704  mov     r12, [rsp+138h+var_68]
0x14002a70c  jmp     loc_14002A563
0x14002a711  mov     [rsp+138h+var_108], 0C000000Dh
0x14002a719  jmp     loc_14002AA37
0x14002a71e  cmp     [rdi+0Ch], bl
0x14002a721  jz      short loc_14002A75C
0x14002a723  cmp     dword ptr [rdi+8], 8800000Bh
0x14002a72a  jnz     short loc_14002A75C
0x14002a72c  mov     r13b, 1
0x14002a72f  mov     [rsp+138h+var_103], r13b
0x14002a734  mov     [rsp+138h+var_102], r13b
0x14002a739  lea     r9, [rsp+138h+var_F0]
0x14002a73e  mov     r8, rdi
0x14002a741  mov     dl, [r15]
0x14002a744  mov     cl, r13b
0x14002a747  call    AfdTliIoControlHandleSetQoS
  ... truncated ...
```
