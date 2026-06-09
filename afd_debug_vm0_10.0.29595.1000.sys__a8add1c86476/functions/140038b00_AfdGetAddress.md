# AfdGetAddress

- ea: `0x140038b00`
- end: `0x1400391b1`
- name: `AfdGetAddress`
- size: `1713`
- prototype: `__int64 __fastcall(PIRP Irp)`
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
- `0x14002fd7c`
- `0x140032798`
- `0x140033698`
- `0x140033bfc`
- `0x140038b00`
- `0x140052674`
- `0x140072840`
- `0x140072870`
- `0x140072c80`
- `0x1400931d0`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!MmMapLockedPages` at `0x140038fd9`
- `ntoskrnl!MmMapLockedPages` at `0x140038fd9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038c00`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038c00`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400390a2`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400390a2`
- `ntoskrnl!IoFreeMdl` at `0x140039158`
- `ntoskrnl!IoFreeMdl` at `0x140039158`
- `ntoskrnl!MmUnlockPages` at `0x140039148`
- `ntoskrnl!MmUnlockPages` at `0x140039148`
- `ntoskrnl!ObfReferenceObject` at `0x140038e42`
- `ntoskrnl!ObfReferenceObject` at `0x14003907c`
- `ntoskrnl!ObfReferenceObject` at `0x140038e42`
- `ntoskrnl!ObfReferenceObject` at `0x14003907c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038bc6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140038bc6`
- `ntoskrnl!IoAllocateMdl` at `0x140038b96`
- `ntoskrnl!IoAllocateMdl` at `0x140038b96`
- `ntoskrnl!IofCompleteRequest` at `0x140039179`
- `ntoskrnl!IofCompleteRequest` at `0x140039179`
- `ntoskrnl!IofCallDriver` at `0x1400390fc`
- `ntoskrnl!IofCallDriver` at `0x1400390fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038f47`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140039038`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038f47`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140039038`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038ed9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140038ed9`

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
  __int64 v28; // r8
  PMDL v29; // rcx
  _DWORD *v30; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v32; // rax
  PMDL v33; // rcx
  _QWORD v35[2]; // [rsp+38h] [rbp-D0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v37[10]; // [rsp+60h] [rbp-A8h] BYREF
  int Src; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v39; // [rsp+B4h] [rbp-54h]
  __int128 v40; // [rsp+B6h] [rbp-52h]
  __int64 v41; // [rsp+C6h] [rbp-42h]

  v35[0] = Irp;
  v4 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v35[1] = v5;
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
        LODWORD(v35[0]) = 0;
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 56), &LockHandle);
        v27 = *(_QWORD *)(v5 + 184);
        if ( v27 && *(_WORD *)(v27 + 6) == 23 && *(_WORD *)(v27 + 4) == 26 )
        {
          Src = 1507354;
          v39 = *(_WORD *)(v27 + 8);
          v40 = *(_OWORD *)(v27 + 10);
          v41 = *(_QWORD *)(v27 + 26);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          CompartmentId = AfdQueryCompartmentId(v5, v35, v28);
          if ( CompartmentId < 0 )
            goto LABEL_84;
          CompartmentId = AfdTcp6RoutingQuery(&Src, &Src, LODWORD(v35[0]));
          v39 = *(_WORD *)(v26 + 8);
          if ( CompartmentId < 0 )
          {
            if ( (xmmword_1400875E0 & 0x40) != 0 )
              WPP_SF_d(1030, 25, WPP_43911188515d396c99d3028411eb93bd_Traceguids, (unsigned int)CompartmentId);
            goto LABEL_84;
          }
          if ( *(_DWORD *)(a2 + 8) >= 0x26u )
          {
            v29 = Irp->MdlAddress;
            if ( (v29->MdlFlags & 5) != 0 )
              v30 = v29->MappedSystemVa;
            else
              v30 = MmMapLockedPages(v29, 0);
            v30[1] = 1;
            RtlCopyVolatileMemory(v30 + 2, &Src, 0x1Eu);
            goto LABEL_84;
          }
          if ( (xmmword_1400875E0 & 0x40) != 0 )
            WPP_SF_(1030, 24, WPP_43911188515d396c99d3028411eb93bd_Traceguids);
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
        v32 = Irp->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v32[-1].MajorFunction = 3087;
        v32[-1].DeviceObject = RelatedDeviceObject;
        v32[-1].FileObject = v22;
        v32[-1].Parameters.Read.Length = 3;
        v32[-1].Parameters.QueryDirectory.FileName = 0;
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
    v33 = Irp->MdlAddress;
    if ( v33 )
    {
      if ( (v33->MdlFlags & 2) != 0 )
        MmUnlockPages(v33);
      IoFreeMdl(Irp->MdlAddress);
      Irp->MdlAddress = 0;
    }
    Irp->IoStatus.Status = CompartmentId;
    goto LABEL_91;
  }
  memset(v37, 0, sizeof(v37));
  v37[0] = AfdTLGetAddressComplete;
  v37[1] = Irp;
  v37[2] = 0xFFFD00000000LL;
  LODWORD(v37[3]) = 16;
  v11 = Irp->MdlAddress;
  v37[6] = v11->MappedSystemVa;
  v37[7] = v11->ByteCount;
  if ( *(_WORD *)v5 == 0xAFD2 && *(_BYTE *)(v5 + 2) == 4 )
  {
    v12 = AfdGetConnectionReferenceFromEndpoint(v5);
    v13 = v12;
    if ( v12 )
    {
      Irp->Tail.Overlay.DriverContext[2] = 0;
      CompartmentId = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v12 + 24) + 8LL), *(_QWORD *)(v12 + 16), v37, 0);
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
  CompartmentId = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 8LL), *(_QWORD *)(v5 + 16), v37, v5);
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
  if ( !(unsigned __int8)AfdTLPendRequest(Irp, v37[8], v14) )
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
0x140038b00  mov     [rsp+arg_10], rbx
0x140038b05  push    rdi
0x140038b06  push    r12
0x140038b08  push    r13
0x140038b0a  push    r14
0x140038b0c  push    r15
0x140038b0e  sub     rsp, 0E0h
0x140038b15  mov     rax, cs:__security_cookie
0x140038b1c  xor     rax, rsp
0x140038b1f  mov     [rsp+108h+var_38], rax
0x140038b27  mov     r12, rdx
0x140038b2a  mov     r14, rcx
0x140038b2d  mov     [rsp+108h+var_D0], rcx
0x140038b32  xor     r13b, r13b
0x140038b35  mov     [rsp+108h+var_D8], r13b
0x140038b3a  mov     [rsp+108h+var_D4], 0
0x140038b42  mov     rax, [rdx+30h]
0x140038b46  mov     rbx, [rax+18h]
0x140038b4a  mov     [rsp+108h+var_C8], rbx
0x140038b4f  mov     al, [rbx+2]
0x140038b52  sub     al, 3
0x140038b54  cmp     al, 1
0x140038b56  jbe     short loc_140038B62
0x140038b58  mov     edi, 0C000000Dh
0x140038b5d  jmp     loc_14003912C
0x140038b62  mov     qword ptr [rcx+38h], 0
0x140038b6a  mov     dword ptr [rcx+30h], 0
0x140038b71  mov     eax, [rbx+8]
0x140038b74  mov     edx, [rdx+8]; Length
0x140038b77  mov     r15d, 100h
0x140038b7d  test    r15d, eax
0x140038b80  jz      short loc_140038BE2
0x140038b82  cmp     edx, 2
0x140038b85  jb      short loc_140038B58
0x140038b87  mov     [rsp+108h+Irp], r14; Irp
0x140038b8c  mov     r9b, 1; ChargeQuota
0x140038b8f  xor     r8d, r8d; SecondaryBuffer
0x140038b92  mov     rcx, [rcx+70h]; VirtualAddress
0x140038b96  call    cs:__imp_IoAllocateMdl
0x140038b9d  nop     dword ptr [rax+rax+00h]
0x140038ba2  test    rax, rax
0x140038ba5  jnz     short loc_140038BB8
0x140038ba7  mov     [rsp+108h+var_D4], 0C000009Ah
0x140038baf  mov     edi, [rsp+108h+var_D4]
0x140038bb3  jmp     loc_14003912C
0x140038bb8  mov     r8d, 1; Operation
0x140038bbe  mov     dl, [r14+40h]; AccessMode
0x140038bc2  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038bc6  call    cs:__imp_MmProbeAndLockPages
0x140038bcd  nop     dword ptr [rax+rax+00h]
0x140038bd2  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038bd6  test    byte ptr [rcx+0Ah], 5
0x140038bda  jz      short loc_140038BE7
0x140038bdc  mov     rax, [rcx+18h]
0x140038be0  jmp     short loc_140038C0C
0x140038be2  cmp     edx, 0Ch
0x140038be5  jmp     short loc_140038B85
0x140038be7  mov     [rsp+108h+Priority], 40000020h; Priority
0x140038bef  mov     dword ptr [rsp+108h+Irp], 0; BugCheckOnFailure
0x140038bf7  xor     r9d, r9d; RequestedAddress
0x140038bfa  xor     edx, edx; AccessMode
0x140038bfc  lea     r8d, [r9+1]; CacheType
0x140038c00  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140038c07  nop     dword ptr [rax+rax+00h]
0x140038c0c  test    rax, rax
0x140038c0f  jnz     short loc_140038C22
0x140038c11  mov     [rsp+108h+var_D4], 0C000009Ah
0x140038c19  mov     edi, [rsp+108h+var_D4]
0x140038c1d  jmp     loc_14003912C
0x140038c22  mov     eax, [rbx+8]
0x140038c25  test    r15d, eax
0x140038c28  jz      loc_140038DB2
0x140038c2e  xor     edx, edx; Val
0x140038c30  lea     r8d, [rdx+50h]; Size
0x140038c34  lea     rcx, [rsp+108h+var_A8]; void *
0x140038c39  call    memset
0x140038c3e  lea     rax, AfdTLGetAddressComplete
0x140038c45  mov     [rsp+108h+var_A8], rax
0x140038c4a  mov     [rsp+108h+var_A0], r14
0x140038c4f  mov     [rsp+108h+var_98], 0
0x140038c57  mov     [rsp+108h+var_94], 0FFFDh
0x140038c5f  mov     [rsp+108h+var_90], 10h
0x140038c67  mov     rcx, [r14+8]
0x140038c6b  mov     rax, [rcx+18h]
0x140038c6f  mov     [rsp+108h+var_78], rax
0x140038c77  mov     eax, [rcx+28h]
0x140038c7a  mov     [rsp+108h+var_70], rax
0x140038c82  mov     eax, 0AFD2h
0x140038c87  cmp     [rbx], ax
0x140038c8a  jnz     short loc_140038CFA
0x140038c8c  cmp     byte ptr [rbx+2], 4
0x140038c90  jnz     short loc_140038CFA
0x140038c92  mov     rcx, rbx
0x140038c95  call    AfdGetConnectionReferenceFromEndpoint
0x140038c9a  mov     r15, rax
0x140038c9d  test    rax, rax
0x140038ca0  jz      short loc_140038CFA
0x140038ca2  mov     qword ptr [r14+88h], 0
0x140038cad  mov     rcx, [rax+18h]
0x140038cb1  xor     r9d, r9d
0x140038cb4  lea     r8, [rsp+108h+var_A8]
0x140038cb9  mov     rdx, [rax+10h]
0x140038cbd  mov     rcx, [rcx+8]
0x140038cc1  call    AfdTLIoControl
0x140038cc6  mov     edi, eax
0x140038cc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140038ccc  lock xadd [r15+30h], rax
0x140038cd2  sub     rax, 1
0x140038cd6  jg      loc_140038D86
0x140038cdc  test    rax, rax
0x140038cdf  jz      short loc_140038CED
0x140038ce1  mov     ecx, 0Eh
0x140038ce6  int     29h; Win8: RtlFailFast(ecx)
0x140038ce8  jmp     loc_140038D86
0x140038ced  mov     rcx, r15
0x140038cf0  call    AfdCloseConnection
0x140038cf5  jmp     loc_140038D86
0x140038cfa  movzx   ecx, word ptr [rbx]
0x140038cfd  mov     edi, 0AFD1h
0x140038d02  cmp     cx, di
0x140038d05  jz      short loc_140038D43
0x140038d07  mov     eax, 1AFDh
0x140038d0c  cmp     cx, ax
0x140038d0f  jz      short loc_140038D43
0x140038d11  test    byte ptr [rbx+5], 10h
0x140038d15  jz      short loc_140038D1D
0x140038d17  test    byte ptr [rbx+6], 1
0x140038d1b  jnz     short loc_140038D43
0x140038d1d  mov     eax, [rbx+8]
0x140038d20  test    al, 1
0x140038d22  jnz     short loc_140038D43
0x140038d24  cmp     byte ptr [rbx+2], 4
0x140038d28  jz      short loc_140038D43
0x140038d2a  mov     rcx, rbx
0x140038d2d  call    AfdPreventUnbind
0x140038d32  test    al, al
0x140038d34  jnz     short loc_140038D40
0x140038d36  mov     edi, 0C0000184h
0x140038d3b  jmp     loc_14003912C
0x140038d40  mov     r13b, 1
0x140038d43  mov     qword ptr [r14+88h], 0
0x140038d4e  lock inc qword ptr [rbx+108h]
0x140038d56  mov     rcx, [rbx+18h]
0x140038d5a  mov     r9, rbx
0x140038d5d  lea     r8, [rsp+108h+var_A8]
0x140038d62  mov     rdx, [rbx+10h]
0x140038d66  mov     rcx, [rcx+8]
0x140038d6a  call    AfdTLIoControl
0x140038d6f  mov     edi, eax
0x140038d71  lock dec qword ptr [rbx+108h]
0x140038d79  test    r13b, r13b
0x140038d7c  jz      short loc_140038D86
0x140038d7e  mov     rcx, rbx
0x140038d81  call    AfdReallowUnbind
0x140038d86  mov     rcx, r14
0x140038d89  cmp     edi, 103h
0x140038d8f  jnz     loc_140039173
0x140038d95  mov     r8b, 1
0x140038d98  mov     rdx, [rsp+108h+var_68]
0x140038da0  call    AfdTLPendRequest
0x140038da5  test    al, al
0x140038da7  jnz     loc_140039185
0x140038dad  jmp     loc_140039170
0x140038db2  movzx   ecx, word ptr [rbx]
0x140038db5  mov     edi, 0AFD1h
0x140038dba  cmp     cx, di
0x140038dbd  jz      short loc_140038DF5
0x140038dbf  mov     eax, 1AFDh
0x140038dc4  cmp     cx, ax
0x140038dc7  jz      short loc_140038DF5
0x140038dc9  test    byte ptr [rbx+5], 10h
0x140038dcd  jz      short loc_140038DD5
0x140038dcf  test    byte ptr [rbx+6], 1
0x140038dd3  jnz     short loc_140038DF5
0x140038dd5  mov     eax, [rbx+8]
0x140038dd8  test    al, 1
0x140038dda  jnz     short loc_140038DF5
0x140038ddc  cmp     byte ptr [rbx+2], 4
0x140038de0  jz      short loc_140038DF5
0x140038de2  mov     rcx, rbx
0x140038de5  call    AfdPreventUnbind
0x140038dea  test    al, al
0x140038dec  jz      loc_140038D36
0x140038df2  mov     r13b, 1
0x140038df5  mov     cl, [rbx+2]
0x140038df8  cmp     cl, 1
0x140038dfb  jz      loc_140038D36
0x140038e01  cmp     cl, 6
0x140038e04  jz      loc_140038D36
0x140038e0a  mov     rax, [rbx+0F0h]
0x140038e11  cmp     word ptr [rax+6], 11h
0x140038e16  jz      short loc_140038E86
0x140038e18  mov     eax, 0AFD2h
0x140038e1d  cmp     [rbx], ax
0x140038e20  jnz     short loc_140038E86
0x140038e22  cmp     cl, 4
0x140038e25  jnz     short loc_140038E86
0x140038e27  mov     rcx, rbx
0x140038e2a  call    AfdGetConnectionReferenceFromEndpoint
0x140038e2f  mov     r15, rax
0x140038e32  test    rax, rax
0x140038e35  jz      short loc_140038E80
0x140038e37  mov     rdi, [rax+10h]
0x140038e3b  mov     r12, [rax+18h]
0x140038e3f  mov     rcx, rdi; Object
0x140038e42  call    cs:__imp_ObfReferenceObject
0x140038e49  nop     dword ptr [rax+rax+00h]
0x140038e4e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140038e52  lock xadd [r15+30h], rcx
0x140038e58  sub     rcx, 1
0x140038e5c  jg      loc_1400390B1
0x140038e62  test    rcx, rcx
0x140038e65  jz      short loc_140038E73
0x140038e67  mov     ecx, 0Eh
0x140038e6c  int     29h; Win8: RtlFailFast(ecx)
0x140038e6e  jmp     loc_1400390B1
0x140038e73  mov     rcx, r15
0x140038e76  call    AfdCloseConnection
0x140038e7b  jmp     loc_1400390B1
0x140038e80  mov     r15d, 100h
0x140038e86  cmp     [rbx], di
0x140038e89  jnz     loc_14003908A
0x140038e8f  mov     eax, [rbx+8]
0x140038e92  test    r15d, eax
0x140038e95  jnz     loc_140039044
0x140038e9b  test    dword ptr [rbx+10h], 8000h
0x140038ea2  jnz     loc_140039044
0x140038ea8  cmp     byte ptr [rbx+2], 4
0x140038eac  jnz     loc_140039044
0x140038eb2  mov     r15, [rbx+0F0h]
0x140038eb9  mov     dword ptr [rsp+108h+var_D0], 0
0x140038ec1  xorps   xmm0, xmm0
0x140038ec4  xor     eax, eax
0x140038ec6  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x140038ecb  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rax
0x140038ed0  lea     rcx, [rbx+38h]; SpinLock
0x140038ed4  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x140038ed9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140038ee0  nop     dword ptr [rax+rax+00h]
0x140038ee5  mov     rcx, [rbx+0B8h]
0x140038eec  test    rcx, rcx
0x140038eef  jz      loc_140039033
0x140038ef5  mov     edx, 17h
0x140038efa  cmp     [rcx+6], dx
0x140038efe  jnz     loc_140039033
0x140038f04  lea     eax, [rdx+3]
0x140038f07  cmp     [rcx+4], ax
0x140038f0b  jnz     loc_140039033
0x140038f11  mov     [rsp+108h+Src], 17001Ah
0x140038f1c  movzx   eax, word ptr [rcx+8]
0x140038f20  mov     [rsp+108h+var_54], ax
0x140038f28  movups  xmm0, xmmword ptr [rcx+0Ah]
0x140038f2c  movups  [rsp+108h+var_52], xmm0
0x140038f34  movsd   xmm1, qword ptr [rcx+1Ah]
0x140038f39  movsd   [rsp+108h+var_42], xmm1
0x140038f42  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x140038f47  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140038f4e  nop     dword ptr [rax+rax+00h]
0x140038f53  lea     rdx, [rsp+108h+var_D0]
0x140038f58  mov     rcx, rbx
0x140038f5b  call    AfdQueryCompartmentId
0x140038f60  mov     edi, eax
0x140038f62  test    eax, eax
0x140038f64  js      loc_14003912C
0x140038f6a  mov     r8d, dword ptr [rsp+108h+var_D0]
0x140038f6f  lea     rdx, [rsp+108h+Src]
0x140038f77  lea     rcx, [rsp+108h+Src]
0x140038f7f  call    AfdTcp6RoutingQuery
0x140038f84  mov     edi, eax
0x140038f86  movzx   eax, word ptr [r15+8]
0x140038f8b  mov     [rsp+108h+var_54], ax
0x140038f93  test    edi, edi
0x140038f95  js      short loc_140039008
0x140038f97  cmp     dword ptr [r12+8], 26h ; '&'
0x140038f9d  jnb     short loc_140038FC7
0x140038f9f  test    byte ptr cs:xmmword_1400875E0, 40h
0x140038fa6  jz      loc_140038B58
0x140038fac  mov     edx, 18h
0x140038fb1  mov     ecx, 406h
0x140038fb6  lea     r8, WPP_43911188515d396c99d3028411eb93bd_Traceguids
0x140038fbd  call    WPP_SF_
0x140038fc2  jmp     loc_140038B58
0x140038fc7  mov     rcx, [r14+8]; MemoryDescriptorList
0x140038fcb  test    byte ptr [rcx+0Ah], 5
0x140038fcf  jz      short loc_140038FD7
0x140038fd1  mov     rax, [rcx+18h]
0x140038fd5  jmp     short loc_140038FE5
0x140038fd7  xor     edx, edx; AccessMode
0x140038fd9  call    cs:__imp_MmMapLockedPages
0x140038fe0  nop     dword ptr [rax+rax+00h]
0x140038fe5  mov     dword ptr [rax+4], 1
0x140038fec  lea     rcx, [rax+8]; void *
0x140038ff0  mov     r8d, 1Eh; Size
0x140038ff6  lea     rdx, [rsp+108h+Src]; Src
0x140038ffe  call    RtlCopyVolatileMemory
0x140039003  jmp     loc_14003912C
0x140039008  test    byte ptr cs:xmmword_1400875E0, 40h
0x14003900f  jz      loc_14003912C
0x140039015  mov     edx, 19h
0x14003901a  mov     ecx, 406h
  ... truncated ...
```
