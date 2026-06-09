# AfdGetAddress

- ea: `0x140038ae0`
- end: `0x140039191`
- name: `AfdGetAddress`
- size: `1713`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140001bb4`
- `0x14000fcd0`
- `0x14001c708`
- `0x14001e7e0`
- `0x140026e80`
- `0x14002fd5c`
- `0x140032778`
- `0x140033678`
- `0x140033bdc`
- `0x140038ae0`
- `0x1400525d4`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`
- `0x1400931d0`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!MmMapLockedPages` at `0x140038fb9`
- `ntoskrnl!MmMapLockedPages` at `0x140038fb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038be0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038be0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039082`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039082`
- `ntoskrnl!IoFreeMdl` at `0x140039138`
- `ntoskrnl!IoFreeMdl` at `0x140039138`
- `ntoskrnl!MmUnlockPages` at `0x140039128`
- `ntoskrnl!MmUnlockPages` at `0x140039128`
- `ntoskrnl!ObfReferenceObject` at `0x140038e22`
- `ntoskrnl!ObfReferenceObject` at `0x14003905c`
- `ntoskrnl!ObfReferenceObject` at `0x140038e22`
- `ntoskrnl!ObfReferenceObject` at `0x14003905c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038ba6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038ba6`
- `ntoskrnl!IoAllocateMdl` at `0x140038b76`
- `ntoskrnl!IoAllocateMdl` at `0x140038b76`
- `ntoskrnl!IofCompleteRequest` at `0x140039159`
- `ntoskrnl!IofCompleteRequest` at `0x140039159`
- `ntoskrnl!IofCallDriver` at `0x1400390dc`
- `ntoskrnl!IofCallDriver` at `0x1400390dc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038f27`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140039018`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038f27`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140039018`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038eb9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038eb9`

## pseudocode

```c
__int64 __fastcall AfdGetAddress(PIRP Irp, __int64 a2)
{
  char v4; // r13
  __int64 v5; // rbx
  int CompartmentId; // edi
  ULONG v7; // edx
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  PMDL v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // r8
  signed __int64 v15; // rax
  bool v16; // cc
  signed __int64 v17; // rax
  IRP *v18; // rcx
  char v19; // cl
  __int64 ConnectionReferenceFromEndpoint; // rax
  __int64 v21; // r15
  struct _FILE_OBJECT *v22; // rdi
  struct _DEVICE_OBJECT *RelatedDeviceObject; // r12
  signed __int64 v24; // rcx
  signed __int64 v25; // rcx
  __int64 v26; // r15
  __int64 v27; // rcx
  PMDL v28; // rcx
  _DWORD *v29; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v31; // rax
  PMDL v32; // rcx
  _QWORD v34[2]; // [rsp+38h] [rbp-D0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v36[10]; // [rsp+60h] [rbp-A8h] BYREF
  int Src; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v38; // [rsp+B4h] [rbp-54h]
  __int128 v39; // [rsp+B6h] [rbp-52h]
  __int64 v40; // [rsp+C6h] [rbp-42h]

  v34[0] = Irp;
  v4 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v34[1] = v5;
  if ( (unsigned __int8)(*(_BYTE *)(v5 + 2) - 3) > 1u )
    goto LABEL_2;
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = 0;
  v7 = *(_DWORD *)(a2 + 8);
  if ( (*(_DWORD *)(v5 + 8) & 0x100) != 0 ? v7 < 2 : v7 < 0xC )
    goto LABEL_2;
  if ( !IoAllocateMdl(Irp->UserBuffer, v7, 0, 1u, Irp) )
  {
    CompartmentId = -1073741670;
    goto LABEL_84;
  }
  MmProbeAndLockPages(Irp->MdlAddress, Irp->RequestorMode, IoWriteAccess);
  MdlAddress = Irp->MdlAddress;
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u);
  if ( !MappedSystemVa )
  {
    CompartmentId = -1073741670;
    goto LABEL_84;
  }
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
  {
    if ( *(_WORD *)v5 != 0xAFD1
      && *(_WORD *)v5 != 6909
      && ((*(_BYTE *)(v5 + 5) & 0x10) == 0 || (*(_BYTE *)(v5 + 6) & 1) == 0)
      && (*(_DWORD *)(v5 + 8) & 1) == 0
      && *(_BYTE *)(v5 + 2) != 4 )
    {
      if ( !(unsigned __int8)AfdPreventUnbind(v5) )
        goto LABEL_29;
      v4 = 1;
    }
    v19 = *(_BYTE *)(v5 + 2);
    if ( v19 == 1 || v19 == 6 )
      goto LABEL_29;
    if ( *(_WORD *)(*(_QWORD *)(v5 + 240) + 6LL) != 17 && *(_WORD *)v5 == 0xAFD2 && v19 == 4 )
    {
      ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(v5);
      v21 = ConnectionReferenceFromEndpoint;
      if ( ConnectionReferenceFromEndpoint )
      {
        v22 = *(struct _FILE_OBJECT **)(ConnectionReferenceFromEndpoint + 16);
        RelatedDeviceObject = *(struct _DEVICE_OBJECT **)(ConnectionReferenceFromEndpoint + 24);
        ObfReferenceObject(v22);
        v24 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v21 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v16 = v24 <= 1;
        v25 = v24 - 1;
        if ( v16 )
        {
          if ( v25 )
            __fastfail(0xEu);
          AfdCloseConnection(v21);
        }
        goto LABEL_82;
      }
    }
    if ( *(_WORD *)v5 == 0xAFD1 )
    {
      if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x8000) == 0 && *(_BYTE *)(v5 + 2) == 4 )
      {
        v26 = *(_QWORD *)(v5 + 240);
        LODWORD(v34[0]) = 0;
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
        v27 = *(_QWORD *)(v5 + 184);
        if ( v27 && *(_WORD *)(v27 + 6) == 23 && *(_WORD *)(v27 + 4) == 26 )
        {
          Src = 1507354;
          v38 = *(_WORD *)(v27 + 8);
          v39 = *(_OWORD *)(v27 + 10);
          v40 = *(_QWORD *)(v27 + 26);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          CompartmentId = AfdQueryCompartmentId(v5, v34);
          if ( CompartmentId < 0 )
            goto LABEL_84;
          CompartmentId = AfdTcp6RoutingQuery(&Src, &Src, LODWORD(v34[0]));
          v38 = *(_WORD *)(v26 + 8);
          if ( CompartmentId < 0 )
          {
            if ( (xmmword_1400875E0 & 0x40) != 0 )
              WPP_SF_d(1030, 25, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids, (unsigned int)CompartmentId);
            goto LABEL_84;
          }
          if ( *(_DWORD *)(a2 + 8) >= 0x26u )
          {
            v28 = Irp->MdlAddress;
            if ( (v28->MdlFlags & 5) != 0 )
              v29 = v28->MappedSystemVa;
            else
              v29 = MmMapLockedPages(v28, 0);
            v29[1] = 1;
            RtlCopyVolatileMemory(v29 + 2, &Src, 0x1Eu);
            goto LABEL_84;
          }
          if ( (xmmword_1400875E0 & 0x40) != 0 )
            WPP_SF_(1030, 24, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids);
          goto LABEL_2;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( *(_WORD *)v5 == 0xAFD1
        && (*(_DWORD *)(v5 + 8) & 0x400000) != 0
        && ((*(_DWORD *)(v5 + 8) & 0x100) != 0 || (*(_DWORD *)(v5 + 16) & 0x8000) != 0)
        && (*(_DWORD *)(v5 + 192) & 0x20) != 0 )
      {
        v22 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v5 + 280) + 8LL);
        ObfReferenceObject(v22);
LABEL_81:
        RelatedDeviceObject = IoGetRelatedDeviceObject(v22);
LABEL_82:
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartGetAddress;
        CurrentStackLocation[-1].Context = v22;
        CurrentStackLocation[-1].Control = -32;
        v31 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v31[-1].MajorFunction = 3087;
        v31[-1].DeviceObject = RelatedDeviceObject;
        v31[-1].FileObject = v22;
        v31[-1].Parameters.Read.Length = 3;
        v31[-1].Parameters.QueryDirectory.FileName = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v5 + 248));
        CompartmentId = IofCallDriver(RelatedDeviceObject, Irp);
        if ( v4 )
          AfdReallowUnbind(v5);
        return (unsigned int)CompartmentId;
      }
    }
    if ( AfdGetAddressFileReference(v5) )
    {
      v22 = *(struct _FILE_OBJECT **)(v5 + 24);
      goto LABEL_81;
    }
LABEL_2:
    CompartmentId = -1073741811;
LABEL_84:
    if ( v4 )
      AfdReallowUnbind(v5);
    v32 = Irp->MdlAddress;
    if ( v32 )
    {
      if ( (v32->MdlFlags & 2) != 0 )
        MmUnlockPages(v32);
      IoFreeMdl(Irp->MdlAddress);
      Irp->MdlAddress = 0;
    }
    Irp->IoStatus.Status = CompartmentId;
    goto LABEL_91;
  }
  memset(v36, 0, sizeof(v36));
  v36[0] = AfdTLGetAddressComplete;
  v36[1] = Irp;
  v36[2] = 0xFFFD00000000LL;
  LODWORD(v36[3]) = 16;
  v11 = Irp->MdlAddress;
  v36[6] = v11->MappedSystemVa;
  v36[7] = v11->ByteCount;
  if ( *(_WORD *)v5 == 0xAFD2 && *(_BYTE *)(v5 + 2) == 4 )
  {
    v12 = AfdGetConnectionReferenceFromEndpoint(v5);
    v13 = v12;
    if ( v12 )
    {
      Irp->Tail.Overlay.DriverContext[2] = 0;
      CompartmentId = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v12 + 24) + 8LL), *(_QWORD *)(v12 + 16), v36, 0);
      v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 48), 0xFFFFFFFFFFFFFFFFuLL);
      v16 = v15 <= 1;
      v17 = v15 - 1;
      if ( v16 )
      {
        if ( v17 )
          __fastfail(0xEu);
        AfdCloseConnection(v13);
      }
      goto LABEL_33;
    }
  }
  if ( *(_WORD *)v5 != 0xAFD1
    && *(_WORD *)v5 != 6909
    && ((*(_BYTE *)(v5 + 5) & 0x10) == 0 || (*(_BYTE *)(v5 + 6) & 1) == 0)
    && (*(_DWORD *)(v5 + 8) & 1) == 0
    && *(_BYTE *)(v5 + 2) != 4 )
  {
    if ( !(unsigned __int8)AfdPreventUnbind(v5) )
    {
LABEL_29:
      CompartmentId = -1073741436;
      goto LABEL_84;
    }
    v4 = 1;
  }
  Irp->Tail.Overlay.DriverContext[2] = 0;
  _InterlockedIncrement64((volatile signed __int64 *)(v5 + 264));
  CompartmentId = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 8LL), *(_QWORD *)(v5 + 16), v36, v5);
  _InterlockedDecrement64((volatile signed __int64 *)(v5 + 264));
  if ( v4 )
    AfdReallowUnbind(v5);
LABEL_33:
  v18 = Irp;
  if ( CompartmentId != 259 )
  {
LABEL_92:
    IofCompleteRequest(v18, AfdPriorityBoost);
    return (unsigned int)CompartmentId;
  }
  LOBYTE(v14) = 1;
  if ( !(unsigned __int8)AfdTLPendRequest(Irp, v36[8], v14) )
  {
LABEL_91:
    v18 = Irp;
    goto LABEL_92;
  }
  return (unsigned int)CompartmentId;
}

```

## disassembly

```asm
0x140038ae0  mov     [rsp+arg_10], rbx
0x140038ae5  push    rdi
0x140038ae6  push    r12
0x140038ae8  push    r13
0x140038aea  push    r14
0x140038aec  push    r15
0x140038aee  sub     rsp, 0E0h
0x140038af5  mov     rax, cs:__security_cookie
0x140038afc  xor     rax, rsp
0x140038aff  mov     [rsp+108h+var_38], rax
0x140038b07  mov     r12, rdx
0x140038b0a  mov     r14, rcx
0x140038b0d  mov     [rsp+108h+var_D0], rcx
0x140038b12  xor     r13b, r13b
0x140038b15  mov     [rsp+108h+var_D8], r13b
0x140038b1a  mov     [rsp+108h+var_D4], 0
0x140038b22  mov     rax, [rdx+30h]
0x140038b26  mov     rbx, [rax+18h]
0x140038b2a  mov     [rsp+108h+var_C8], rbx
0x140038b2f  mov     al, [rbx+2]
0x140038b32  sub     al, 3
0x140038b34  cmp     al, 1
0x140038b36  jbe     short loc_140038B42
0x140038b38  mov     edi, 0C000000Dh
0x140038b3d  jmp     loc_14003910C
0x140038b42  mov     qword ptr [rcx+38h], 0
0x140038b4a  mov     dword ptr [rcx+30h], 0
0x140038b51  mov     eax, [rbx+8]
0x140038b54  mov     edx, [rdx+8]; Length
0x140038b57  mov     r15d, 100h
0x140038b5d  test    r15d, eax
0x140038b60  jz      short loc_140038BC2
0x140038b62  cmp     edx, 2
0x140038b65  jb      short loc_140038B38
0x140038b67  mov     [rsp+108h+Irp], r14; Irp
0x140038b6c  mov     r9b, 1; ChargeQuota
0x140038b6f  xor     r8d, r8d; SecondaryBuffer
0x140038b72  mov     rcx, [rcx+70h]; VirtualAddress
0x140038b76  call    cs:__imp_IoAllocateMdl
0x140038b7d  nop     dword ptr [rax+rax+00h]
0x140038b82  test    rax, rax
0x140038b85  jnz     short loc_140038B98
0x140038b87  mov     [rsp+108h+var_D4], 0C000009Ah
0x140038b8f  mov     edi, [rsp+108h+var_D4]
0x140038b93  jmp     loc_14003910C
0x140038b98  mov     r8d, 1; Operation
0x140038b9e  mov     dl, [r14+40h]; AccessMode
0x140038ba2  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038ba6  call    cs:__imp_MmProbeAndLockPages
0x140038bad  nop     dword ptr [rax+rax+00h]
0x140038bb2  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038bb6  test    byte ptr [rcx+0Ah], 5
0x140038bba  jz      short loc_140038BC7
0x140038bbc  mov     rax, [rcx+18h]
0x140038bc0  jmp     short loc_140038BEC
0x140038bc2  cmp     edx, 0Ch
0x140038bc5  jmp     short loc_140038B65
0x140038bc7  mov     [rsp+108h+Priority], 40000020h; Priority
0x140038bcf  mov     dword ptr [rsp+108h+Irp], 0; BugCheckOnFailure
0x140038bd7  xor     r9d, r9d; RequestedAddress
0x140038bda  xor     edx, edx; AccessMode
0x140038bdc  lea     r8d, [r9+1]; CacheType
0x140038be0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140038be7  nop     dword ptr [rax+rax+00h]
0x140038bec  test    rax, rax
0x140038bef  jnz     short loc_140038C02
0x140038bf1  mov     [rsp+108h+var_D4], 0C000009Ah
0x140038bf9  mov     edi, [rsp+108h+var_D4]
0x140038bfd  jmp     loc_14003910C
0x140038c02  mov     eax, [rbx+8]
0x140038c05  test    r15d, eax
0x140038c08  jz      loc_140038D92
0x140038c0e  xor     edx, edx; Val
0x140038c10  lea     r8d, [rdx+50h]; Size
0x140038c14  lea     rcx, [rsp+108h+var_A8]; void *
0x140038c19  call    memset
0x140038c1e  lea     rax, AfdTLGetAddressComplete
0x140038c25  mov     [rsp+108h+var_A8], rax
0x140038c2a  mov     [rsp+108h+var_A0], r14
0x140038c2f  mov     [rsp+108h+var_98], 0
0x140038c37  mov     [rsp+108h+var_94], 0FFFDh
0x140038c3f  mov     [rsp+108h+var_90], 10h
0x140038c47  mov     rcx, [r14+8]
0x140038c4b  mov     rax, [rcx+18h]
0x140038c4f  mov     [rsp+108h+var_78], rax
0x140038c57  mov     eax, [rcx+28h]
0x140038c5a  mov     [rsp+108h+var_70], rax
0x140038c62  mov     eax, 0AFD2h
0x140038c67  cmp     [rbx], ax
0x140038c6a  jnz     short loc_140038CDA
0x140038c6c  cmp     byte ptr [rbx+2], 4
0x140038c70  jnz     short loc_140038CDA
0x140038c72  mov     rcx, rbx
0x140038c75  call    AfdGetConnectionReferenceFromEndpoint
0x140038c7a  mov     r15, rax
0x140038c7d  test    rax, rax
0x140038c80  jz      short loc_140038CDA
0x140038c82  mov     qword ptr [r14+88h], 0
0x140038c8d  mov     rcx, [rax+18h]
0x140038c91  xor     r9d, r9d
0x140038c94  lea     r8, [rsp+108h+var_A8]
0x140038c99  mov     rdx, [rax+10h]
0x140038c9d  mov     rcx, [rcx+8]
0x140038ca1  call    AfdTLIoControl
0x140038ca6  mov     edi, eax
0x140038ca8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140038cac  lock xadd [r15+30h], rax
0x140038cb2  sub     rax, 1
0x140038cb6  jg      loc_140038D66
0x140038cbc  test    rax, rax
0x140038cbf  jz      short loc_140038CCD
0x140038cc1  mov     ecx, 0Eh
0x140038cc6  int     29h; Win8: RtlFailFast(ecx)
0x140038cc8  jmp     loc_140038D66
0x140038ccd  mov     rcx, r15
0x140038cd0  call    AfdCloseConnection
0x140038cd5  jmp     loc_140038D66
0x140038cda  movzx   ecx, word ptr [rbx]
0x140038cdd  mov     edi, 0AFD1h
0x140038ce2  cmp     cx, di
0x140038ce5  jz      short loc_140038D23
0x140038ce7  mov     eax, 1AFDh
0x140038cec  cmp     cx, ax
0x140038cef  jz      short loc_140038D23
0x140038cf1  test    byte ptr [rbx+5], 10h
0x140038cf5  jz      short loc_140038CFD
0x140038cf7  test    byte ptr [rbx+6], 1
0x140038cfb  jnz     short loc_140038D23
0x140038cfd  mov     eax, [rbx+8]
0x140038d00  test    al, 1
0x140038d02  jnz     short loc_140038D23
0x140038d04  cmp     byte ptr [rbx+2], 4
0x140038d08  jz      short loc_140038D23
0x140038d0a  mov     rcx, rbx
0x140038d0d  call    AfdPreventUnbind
0x140038d12  test    al, al
0x140038d14  jnz     short loc_140038D20
0x140038d16  mov     edi, 0C0000184h
0x140038d1b  jmp     loc_14003910C
0x140038d20  mov     r13b, 1
0x140038d23  mov     qword ptr [r14+88h], 0
0x140038d2e  lock inc qword ptr [rbx+108h]
0x140038d36  mov     rcx, [rbx+18h]
0x140038d3a  mov     r9, rbx
0x140038d3d  lea     r8, [rsp+108h+var_A8]
0x140038d42  mov     rdx, [rbx+10h]
0x140038d46  mov     rcx, [rcx+8]
0x140038d4a  call    AfdTLIoControl
0x140038d4f  mov     edi, eax
0x140038d51  lock dec qword ptr [rbx+108h]
0x140038d59  test    r13b, r13b
0x140038d5c  jz      short loc_140038D66
0x140038d5e  mov     rcx, rbx
0x140038d61  call    AfdReallowUnbind
0x140038d66  mov     rcx, r14
0x140038d69  cmp     edi, 103h
0x140038d6f  jnz     loc_140039153
0x140038d75  mov     r8b, 1
0x140038d78  mov     rdx, [rsp+108h+var_68]
0x140038d80  call    AfdTLPendRequest
0x140038d85  test    al, al
0x140038d87  jnz     loc_140039165
0x140038d8d  jmp     loc_140039150
0x140038d92  movzx   ecx, word ptr [rbx]
0x140038d95  mov     edi, 0AFD1h
0x140038d9a  cmp     cx, di
0x140038d9d  jz      short loc_140038DD5
0x140038d9f  mov     eax, 1AFDh
0x140038da4  cmp     cx, ax
0x140038da7  jz      short loc_140038DD5
0x140038da9  test    byte ptr [rbx+5], 10h
0x140038dad  jz      short loc_140038DB5
0x140038daf  test    byte ptr [rbx+6], 1
0x140038db3  jnz     short loc_140038DD5
0x140038db5  mov     eax, [rbx+8]
0x140038db8  test    al, 1
0x140038dba  jnz     short loc_140038DD5
0x140038dbc  cmp     byte ptr [rbx+2], 4
0x140038dc0  jz      short loc_140038DD5
0x140038dc2  mov     rcx, rbx
0x140038dc5  call    AfdPreventUnbind
0x140038dca  test    al, al
0x140038dcc  jz      loc_140038D16
0x140038dd2  mov     r13b, 1
0x140038dd5  mov     cl, [rbx+2]
0x140038dd8  cmp     cl, 1
0x140038ddb  jz      loc_140038D16
0x140038de1  cmp     cl, 6
0x140038de4  jz      loc_140038D16
0x140038dea  mov     rax, [rbx+0F0h]
0x140038df1  cmp     word ptr [rax+6], 11h
0x140038df6  jz      short loc_140038E66
0x140038df8  mov     eax, 0AFD2h
0x140038dfd  cmp     [rbx], ax
0x140038e00  jnz     short loc_140038E66
0x140038e02  cmp     cl, 4
0x140038e05  jnz     short loc_140038E66
0x140038e07  mov     rcx, rbx
0x140038e0a  call    AfdGetConnectionReferenceFromEndpoint
0x140038e0f  mov     r15, rax
0x140038e12  test    rax, rax
0x140038e15  jz      short loc_140038E60
0x140038e17  mov     rdi, [rax+10h]
0x140038e1b  mov     r12, [rax+18h]
0x140038e1f  mov     rcx, rdi; Object
0x140038e22  call    cs:__imp_ObfReferenceObject
0x140038e29  nop     dword ptr [rax+rax+00h]
0x140038e2e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140038e32  lock xadd [r15+30h], rcx
0x140038e38  sub     rcx, 1
0x140038e3c  jg      loc_140039091
0x140038e42  test    rcx, rcx
0x140038e45  jz      short loc_140038E53
0x140038e47  mov     ecx, 0Eh
0x140038e4c  int     29h; Win8: RtlFailFast(ecx)
0x140038e4e  jmp     loc_140039091
0x140038e53  mov     rcx, r15
0x140038e56  call    AfdCloseConnection
0x140038e5b  jmp     loc_140039091
0x140038e60  mov     r15d, 100h
0x140038e66  cmp     [rbx], di
0x140038e69  jnz     loc_14003906A
0x140038e6f  mov     eax, [rbx+8]
0x140038e72  test    r15d, eax
0x140038e75  jnz     loc_140039024
0x140038e7b  test    dword ptr [rbx+10h], 8000h
0x140038e82  jnz     loc_140039024
0x140038e88  cmp     byte ptr [rbx+2], 4
0x140038e8c  jnz     loc_140039024
0x140038e92  mov     r15, [rbx+0F0h]
0x140038e99  mov     dword ptr [rsp+108h+var_D0], 0
0x140038ea1  xorps   xmm0, xmm0
0x140038ea4  xor     eax, eax
0x140038ea6  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x140038eab  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rax
0x140038eb0  lea     rcx, [rbx+38h]; SpinLock
0x140038eb4  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x140038eb9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140038ec0  nop     dword ptr [rax+rax+00h]
0x140038ec5  mov     rcx, [rbx+0B8h]
0x140038ecc  test    rcx, rcx
0x140038ecf  jz      loc_140039013
0x140038ed5  mov     edx, 17h
0x140038eda  cmp     [rcx+6], dx
0x140038ede  jnz     loc_140039013
0x140038ee4  lea     eax, [rdx+3]
0x140038ee7  cmp     [rcx+4], ax
0x140038eeb  jnz     loc_140039013
0x140038ef1  mov     [rsp+108h+Src], 17001Ah
0x140038efc  movzx   eax, word ptr [rcx+8]
0x140038f00  mov     [rsp+108h+var_54], ax
0x140038f08  movups  xmm0, xmmword ptr [rcx+0Ah]
0x140038f0c  movups  [rsp+108h+var_52], xmm0
0x140038f14  movsd   xmm1, qword ptr [rcx+1Ah]
0x140038f19  movsd   [rsp+108h+var_42], xmm1
0x140038f22  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x140038f27  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140038f2e  nop     dword ptr [rax+rax+00h]
0x140038f33  lea     rdx, [rsp+108h+var_D0]
0x140038f38  mov     rcx, rbx
0x140038f3b  call    AfdQueryCompartmentId
0x140038f40  mov     edi, eax
0x140038f42  test    eax, eax
0x140038f44  js      loc_14003910C
0x140038f4a  mov     r8d, dword ptr [rsp+108h+var_D0]
0x140038f4f  lea     rdx, [rsp+108h+Src]
0x140038f57  lea     rcx, [rsp+108h+Src]
0x140038f5f  call    AfdTcp6RoutingQuery
0x140038f64  mov     edi, eax
0x140038f66  movzx   eax, word ptr [r15+8]
0x140038f6b  mov     [rsp+108h+var_54], ax
0x140038f73  test    edi, edi
0x140038f75  js      short loc_140038FE8
0x140038f77  cmp     dword ptr [r12+8], 26h ; '&'
0x140038f7d  jnb     short loc_140038FA7
0x140038f7f  test    byte ptr cs:xmmword_1400875E0, 40h
0x140038f86  jz      loc_140038B38
0x140038f8c  mov     edx, 18h
0x140038f91  mov     ecx, 406h
0x140038f96  lea     r8, WPP_654a54d5d1a93919ecbd46fb90bee823_Traceguids
0x140038f9d  call    WPP_SF_
0x140038fa2  jmp     loc_140038B38
0x140038fa7  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038fab  test    byte ptr [rcx+0Ah], 5
0x140038faf  jz      short loc_140038FB7
0x140038fb1  mov     rax, [rcx+18h]
0x140038fb5  jmp     short loc_140038FC5
0x140038fb7  xor     edx, edx; AccessMode
0x140038fb9  call    cs:__imp_MmMapLockedPages
0x140038fc0  nop     dword ptr [rax+rax+00h]
0x140038fc5  mov     dword ptr [rax+4], 1
0x140038fcc  lea     rcx, [rax+8]; void *
0x140038fd0  mov     r8d, 1Eh; Size
0x140038fd6  lea     rdx, [rsp+108h+Src]; Src
0x140038fde  call    RtlCopyVolatileMemory
0x140038fe3  jmp     loc_14003910C
0x140038fe8  test    byte ptr cs:xmmword_1400875E0, 40h
0x140038fef  jz      loc_14003910C
0x140038ff5  mov     edx, 19h
0x140038ffa  mov     ecx, 406h
  ... truncated ...
```
