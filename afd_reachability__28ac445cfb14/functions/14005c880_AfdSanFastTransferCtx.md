# AfdSanFastTransferCtx

- ea: `0x14005c880`
- end: `0x14005d0db`
- name: `AfdSanFastTransferCtx`
- size: `2139`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c060`
- `0x14000cb20`
- `0x14000f390`
- `0x140019190`
- `0x1400191f0`
- `0x14002fd5c`
- `0x1400368c8`
- `0x14003f97c`
- `0x140041a14`
- `0x1400445b8`
- `0x14005aa70`
- `0x14005ab88`
- `0x14005c880`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092008`
- `0x1400930cc`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005c958`
- `ntoskrnl!ExRaiseStatus` at `0x14005cabe`
- `ntoskrnl!ExRaiseStatus` at `0x14005cb1c`
- `ntoskrnl!ExRaiseStatus` at `0x14005cb37`
- `ntoskrnl!ExRaiseStatus` at `0x14005cbd8`
- `ntoskrnl!ExRaiseStatus` at `0x14005cd6a`
- `ntoskrnl!ExRaiseStatus` at `0x14005d026`
- `ntoskrnl!ExRaiseStatus` at `0x14005c958`
- `ntoskrnl!ExRaiseStatus` at `0x14005cabe`
- `ntoskrnl!ExRaiseStatus` at `0x14005cb1c`
- `ntoskrnl!ExRaiseStatus` at `0x14005cb37`
- `ntoskrnl!ExRaiseStatus` at `0x14005cbd8`
- `ntoskrnl!ExRaiseStatus` at `0x14005cd6a`
- `ntoskrnl!ExRaiseStatus` at `0x14005d026`
- `ntoskrnl!KeAttachProcess` at `0x14005cf51`
- `ntoskrnl!KeAttachProcess` at `0x14005cf51`
- `ntoskrnl!KeDetachProcess` at `0x14005cf84`
- `ntoskrnl!KeDetachProcess` at `0x14005cfd8`
- `ntoskrnl!KeDetachProcess` at `0x14005cf84`
- `ntoskrnl!KeDetachProcess` at `0x14005cfd8`
- `ntoskrnl!ProbeForRead` at `0x14005ca29`
- `ntoskrnl!ProbeForRead` at `0x14005ca48`
- `ntoskrnl!ProbeForRead` at `0x14005cba3`
- `ntoskrnl!ProbeForRead` at `0x14005cbc2`
- `ntoskrnl!ProbeForRead` at `0x14005ca29`
- `ntoskrnl!ProbeForRead` at `0x14005ca48`
- `ntoskrnl!ProbeForRead` at `0x14005cba3`
- `ntoskrnl!ProbeForRead` at `0x14005cbc2`
- `ntoskrnl!MmMapLockedPages` at `0x14005ce67`
- `ntoskrnl!MmMapLockedPages` at `0x14005cea4`
- `ntoskrnl!MmMapLockedPages` at `0x14005ce67`
- `ntoskrnl!MmMapLockedPages` at `0x14005cea4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005c96e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cb4d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005c96e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cb4d`
- `ntoskrnl!IofCompleteRequest` at `0x14005d059`
- `ntoskrnl!IofCompleteRequest` at `0x14005d059`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d07e`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d07e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cd9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d0aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cd9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d0aa`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca6e`
- `ntoskrnl!ExAllocatePool2` at `0x14005cce2`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca6e`
- `ntoskrnl!ExAllocatePool2` at `0x14005cce2`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005cdf5`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005cdf5`
- `ntoskrnl!IoIs32bitProcess` at `0x14005c906`
- `ntoskrnl!IoIs32bitProcess` at `0x14005c906`

## pseudocode

```c
__int64 __fastcall AfdSanFastTransferCtx(
        __int64 a1,
        unsigned __int16 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        IRP *a8)
{
  char v12; // r13
  unsigned int v13; // edx
  unsigned int i; // ebx
  __int64 v15; // rcx
  void *v16; // rdx
  char *v17; // rcx
  int v18; // edi
  __int64 v19; // r8
  __int64 v20; // r15
  int v21; // eax
  __int64 v22; // r14
  char *Pool2; // rbx
  IRP *v24; // r14
  __int64 CurrentStackLocation; // rbx
  __int64 v26; // r8
  unsigned int v27; // ebx
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  PMDL v30; // rax
  struct _MDL *Next; // rcx
  PVOID v32; // rax
  void *v33; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  volatile signed __int64 *v35; // rax
  HANDLE Handle[2]; // [rsp+38h] [rbp-1A0h] BYREF
  volatile void *v38[2]; // [rsp+48h] [rbp-190h]
  SIZE_T Size[2]; // [rsp+58h] [rbp-180h]
  __int64 v40; // [rsp+68h] [rbp-170h]
  unsigned int v41; // [rsp+70h] [rbp-168h]
  IRP *v42; // [rsp+78h] [rbp-160h]
  __int64 v43; // [rsp+80h] [rbp-158h]
  PVOID Object; // [rsp+88h] [rbp-150h] BYREF
  PVOID P; // [rsp+90h] [rbp-148h]
  __int64 v46; // [rsp+98h] [rbp-140h]
  char *v47; // [rsp+A0h] [rbp-138h]
  struct _KPROCESS *v48; // [rsp+A8h] [rbp-130h]
  PEPROCESS CurrentProcess; // [rsp+B0h] [rbp-128h]
  __int64 v50; // [rsp+B8h] [rbp-120h]
  __int128 v51; // [rsp+C0h] [rbp-118h] BYREF
  volatile void *Address[2]; // [rsp+D0h] [rbp-108h]
  SIZE_T Length[2]; // [rsp+E0h] [rbp-F8h]
  __int64 v54; // [rsp+F0h] [rbp-E8h]
  __int128 Src; // [rsp+F8h] [rbp-E0h] BYREF
  int v56; // [rsp+108h] [rbp-D0h]
  _BYTE v57[128]; // [rsp+110h] [rbp-C8h] BYREF

  v42 = a8;
  *(_OWORD *)Handle = 0;
  *(_OWORD *)v38 = 0;
  *(_OWORD *)Size = 0;
  v40 = 0;
  Object = 0;
  v12 = a3;
  P = v57;
  *(_QWORD *)&a8->Type = 0;
  if ( IoIs32bitProcess(0) )
  {
    v51 = 0;
    *(_OWORD *)Address = 0;
    *(_OWORD *)Length = 0;
    v54 = 0;
    v41 = 0;
    if ( a5 < 0x38 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&v51, a4, 0x38u);
    }
    else
    {
      RtlCopyVolatileMemory(&v51, a4, 0x38u);
    }
    *(_OWORD *)Handle = v51;
    v38[0] = Address[0];
    v38[1] = Address[1];
    LODWORD(Size[0]) = Length[0];
    Size[1] = Length[1];
    v13 = v54;
    v40 = v54;
    if ( a3 )
    {
      if ( !LODWORD(Length[0]) || (unsigned int)v54 > 0x1FFFFFFF )
        ExRaiseStatus(-1073741811);
      ProbeForRead(Address[1], LODWORD(Length[0]), 1u);
      ProbeForRead((volatile void *)Size[1], 8LL * (unsigned int)v40, 4u);
      v13 = v40;
    }
    if ( v13 > 8 )
    {
      P = (PVOID)ExAllocatePool2(97, 16LL * v13, 543450689);
      v13 = v40;
    }
    for ( i = 0; ; ++i )
    {
      v41 = i;
      if ( i >= v13 )
        break;
      v15 = 16LL * i;
      v16 = (void *)(v15 + Size[1]);
      v17 = (char *)P + v15;
      if ( a3 )
        RtlCopyFromUser(v17, v16, 0x10u);
      else
        RtlCopyVolatileMemory(v17, v16, 0x10u);
      v13 = v40;
    }
    Size[1] = (SIZE_T)P;
    v12 = 0;
  }
  else
  {
    if ( a5 < 0x38 )
      ExRaiseStatus(-1073741811);
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Handle, a4, 0x38u);
    }
    else
    {
      RtlCopyVolatileMemory(Handle, a4, 0x38u);
    }
    if ( a3 )
    {
      if ( !LODWORD(Size[0]) || (unsigned int)v40 > 0xFFFFFFF )
        ExRaiseStatus(-1073741811);
      ProbeForRead(v38[1], LODWORD(Size[0]), 1u);
      ProbeForRead((volatile void *)Size[1], 8LL * (unsigned int)v40, 4u);
    }
  }
  if ( !Handle[1] )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 39, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( ((__int64)v38[0] & 7) != 3 )
  {
    v18 = -1073741811;
    goto LABEL_95;
  }
  HIDWORD(v40) = AfdValidateStatus(HIDWORD(v40));
  v50 = *(_QWORD *)(a1 + 24);
  v18 = AfdSanReferenceSwitchSocketByHandle(Handle[0], a2 >> 14, a3, (__int64)Handle[1], (__int64)&Object);
  if ( v18 >= 0 )
  {
    v20 = *((_QWORD *)Object + 3);
    v43 = v20;
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_q(1043, 40, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v20);
    if ( v38[0] == (volatile void *)3 )
    {
      v18 = HIDWORD(v40);
      if ( v40 >= 0 )
      {
        v47 = 0;
        v21 = 0;
        v22 = LODWORD(Size[0]);
        if ( (_DWORD)v40 )
        {
          LOBYTE(v19) = v12;
          v21 = AfdCalcBufferArrayByteLength(Size[1], (unsigned int)v40, v19);
        }
        if ( v21 + (int)v22 < (unsigned int)v22 )
          ExRaiseStatus(-1073741670);
        Pool2 = (char *)ExAllocatePool2(289, (unsigned int)(v21 + v22), 2019845697);
        v47 = Pool2;
        if ( a3 )
          RtlCopyFromUser(Pool2, (void *)v38[1], LODWORD(Size[0]));
        else
          RtlCopyVolatileMemory(Pool2, (const void *)v38[1], LODWORD(Size[0]));
        if ( (_DWORD)v40 )
          AfdCopyBufferArrayToBuffer(
            &Pool2[LODWORD(Size[0])],
            (unsigned int)(v22 - LODWORD(Size[0])),
            (void *)Size[1],
            v12);
        v18 = AfdSanDupEndpointIntoServiceProcess(Object);
        if ( v18 >= 0 )
        {
          *(_QWORD *)&v42->Type = v22;
LABEL_94:
          ObfDereferenceObject(Object);
          goto LABEL_95;
        }
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0x78646641u);
      }
LABEL_93:
      AfdSanRestartRequestProcessing(v20, (unsigned int)v18);
      goto LABEL_94;
    }
    v24 = (IRP *)AfdSanDequeueRequest(v20, v38[0]);
    v42 = v24;
    if ( !v24 )
    {
      v18 = -1073741811;
      goto LABEL_93;
    }
    if ( v40 < 0 )
    {
      v24->IoStatus.Status = HIDWORD(v40);
      v18 = 0;
LABEL_91:
      IofCompleteRequest(v24, AfdPriorityBoost);
      goto LABEL_93;
    }
    CurrentStackLocation = (__int64)v24->Tail.Overlay.CurrentStackLocation;
    v46 = CurrentStackLocation;
    Src = 0;
    v56 = 0;
    CurrentProcess = IoGetCurrentProcess();
    v48 = (struct _KPROCESS *)*((_QWORD *)v24->Tail.Overlay.DriverContext[3] + 6);
    if ( v24->MdlAddress->ByteCount == LODWORD(Size[0]) )
    {
      if ( !(_DWORD)v40 )
      {
LABEL_65:
        MdlAddress = v24->MdlAddress;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPages(MdlAddress, 0);
        RtlCopyVolatileMemory(MappedSystemVa, (const void *)v38[1], LODWORD(Size[0]));
        if ( (_DWORD)v40 )
        {
          v30 = v24->MdlAddress;
          Next = v30->Next;
          if ( (v30->Next->MdlFlags & 5) != 0 )
            v32 = Next->MappedSystemVa;
          else
            v32 = MmMapLockedPages(Next, 0);
          v24->IoStatus.Information = (unsigned int)AfdCopyBufferArrayToBuffer(
                                                      v32,
                                                      *(unsigned int *)(CurrentStackLocation + 8),
                                                      (void *)Size[1],
                                                      v12);
        }
        else
        {
          v24->IoStatus.Information = 0;
        }
        v46 = AfdLockEndpointContext(v20);
        if ( *(_WORD *)v20 == 6909 && *(_DWORD *)(v20 + 156) == 259 )
        {
          if ( CurrentProcess != v48 )
          {
            v33 = *(void **)(v20 + 112);
            if ( a3 )
              RtlCopyFromUser(&Src, v33, 0x14u);
            else
              RtlCopyVolatileMemory(&Src, v33, 0x14u);
            KeAttachProcess(*((PRKPROCESS *)v24->Tail.Overlay.DriverContext[3] + 6));
            Blink = v24->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
            if ( v24->RequestorMode )
              RtlCopyToUser(Blink, &Src, 0x14u);
            else
              RtlCopyVolatileMemory(Blink, &Src, 0x14u);
            KeDetachProcess();
            v35 = (volatile signed __int64 *)v24->Tail.Overlay.DriverContext[3];
            *(_QWORD *)(v20 + 96) = v35;
            if ( _InterlockedIncrement64(v35 + 8) <= 1 )
              __fastfail(0xEu);
            *(_QWORD *)(v20 + 112) = v24->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
            AfdDereferenceEndpoint(v50);
          }
          *(_BYTE *)(v20 + 160) = 0;
        }
        else
        {
          v18 = -1073741816;
        }
        AfdUnlockEndpointContext(v20, v46);
        v24->IoStatus.Status = v18;
        goto LABEL_91;
      }
      v27 = *(_DWORD *)(CurrentStackLocation + 8);
      LOBYTE(v26) = v12;
      if ( v27 >= (unsigned int)AfdCalcBufferArrayByteLength(Size[1], (unsigned int)v40, v26) )
      {
        CurrentStackLocation = v46;
        goto LABEL_65;
      }
    }
    ExRaiseStatus(-1073741811);
  }
LABEL_95:
  if ( P != v57 )
    ExFreePoolWithTag(P, 0x20646641u);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14005c880  push    rbx
0x14005c882  push    rdi
0x14005c883  push    r12
0x14005c885  push    r13
0x14005c887  push    r14
0x14005c889  push    r15
0x14005c88b  sub     rsp, 1A8h
0x14005c892  mov     rax, cs:__security_cookie
0x14005c899  xor     rax, rsp
0x14005c89c  mov     [rsp+1D8h+var_48], rax
0x14005c8a4  mov     rbx, r9
0x14005c8a7  mov     r12b, r8b
0x14005c8aa  mov     edi, edx
0x14005c8ac  mov     r14, rcx
0x14005c8af  mov     rax, [rsp+1D8h+arg_38]
0x14005c8b7  mov     [rsp+1D8h+var_160], rax
0x14005c8bc  xorps   xmm0, xmm0
0x14005c8bf  xor     ecx, ecx
0x14005c8c1  movups  xmmword ptr [rsp+1D8h+Handle], xmm0
0x14005c8c6  movups  xmmword ptr [rsp+1D8h+var_190], xmm0
0x14005c8cb  movups  xmmword ptr [rsp+1D8h+Size], xmm0
0x14005c8d0  mov     [rsp+1D8h+var_170], rcx
0x14005c8d5  mov     [rsp+1D8h+Object], rcx
0x14005c8dd  mov     r13b, r8b
0x14005c8e0  mov     [rsp+1D8h+var_1A4], r8b
0x14005c8e5  lea     rcx, [rsp+1D8h+var_C8]
0x14005c8ed  mov     [rsp+1D8h+P], rcx
0x14005c8f5  mov     qword ptr [rax], 0
0x14005c8fc  mov     [rsp+1D8h+var_1A8], 0
0x14005c904  xor     ecx, ecx; Irp
0x14005c906  call    cs:__imp_IoIs32bitProcess
0x14005c90d  nop     dword ptr [rax+rax+00h]
0x14005c912  mov     r8d, 38h ; '8'; Size
0x14005c918  test    al, al
0x14005c91a  jz      loc_14005CB28
0x14005c920  xorps   xmm0, xmm0
0x14005c923  xor     eax, eax
0x14005c925  movups  [rsp+1D8h+var_118], xmm0
0x14005c92d  movups  xmmword ptr [rsp+1D8h+Address], xmm0
0x14005c935  movups  xmmword ptr [rsp+1D8h+Length], xmm0
0x14005c93d  mov     [rsp+1D8h+var_E8], rax
0x14005c945  mov     [rsp+1D8h+var_168], eax
0x14005c949  cmp     [rsp+1D8h+arg_20], r8d
0x14005c951  jnb     short loc_14005C964
0x14005c953  mov     ecx, 0C000000Dh; Status
0x14005c958  call    cs:__imp_ExRaiseStatus
0x14005c964  test    r12b, r12b
0x14005c967  jz      short loc_14005C991
0x14005c969  test    bl, 3
0x14005c96c  jz      short loc_14005C97A
0x14005c96e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005c975  nop     dword ptr [rax+rax+00h]
0x14005c97a  test    r12b, r12b
0x14005c97d  jz      short loc_14005C991
0x14005c97f  mov     rdx, rbx; Src
0x14005c982  lea     rcx, [rsp+1D8h+var_118]; void *
0x14005c98a  call    RtlCopyFromUser
0x14005c98f  jmp     short loc_14005C9A1
0x14005c991  mov     rdx, rbx; Src
0x14005c994  lea     rcx, [rsp+1D8h+var_118]; void *
0x14005c99c  call    RtlCopyVolatileMemory
0x14005c9a1  mov     rax, qword ptr [rsp+1D8h+var_118]
0x14005c9a9  mov     [rsp+1D8h+Handle], rax
0x14005c9ae  mov     rax, qword ptr [rsp+1D8h+var_118+8]
0x14005c9b6  mov     [rsp+1D8h+Handle+8], rax
0x14005c9bb  mov     rax, [rsp+1D8h+Address]
0x14005c9c3  mov     [rsp+1D8h+var_190], rax
0x14005c9c8  mov     rcx, [rsp+1D8h+Address+8]; Address
0x14005c9d0  mov     [rsp+1D8h+var_190+8], rcx
0x14005c9d5  mov     r8d, dword ptr [rsp+1D8h+Length]
0x14005c9dd  mov     dword ptr [rsp+1D8h+Size], r8d
0x14005c9e2  mov     rax, [rsp+1D8h+Length+8]
0x14005c9ea  mov     [rsp+1D8h+Size+8], rax
0x14005c9ef  mov     rdx, [rsp+1D8h+var_E8]
0x14005c9f7  mov     dword ptr [rsp+1D8h+var_170], edx
0x14005c9fb  mov     eax, dword ptr [rsp+1D8h+var_E8+4]
0x14005ca02  mov     dword ptr [rsp+1D8h+var_170+4], eax
0x14005ca06  test    r12b, r12b
0x14005ca09  jz      short loc_14005CA58
0x14005ca0b  test    r8d, r8d
0x14005ca0e  jz      loc_14005CAB9
0x14005ca14  cmp     edx, 1FFFFFFFh
0x14005ca1a  ja      loc_14005CAB9
0x14005ca20  mov     edx, r8d; Length
0x14005ca23  mov     r8d, 1; Alignment
0x14005ca29  call    cs:__imp_ProbeForRead
0x14005ca30  nop     dword ptr [rax+rax+00h]
0x14005ca35  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005ca39  shl     rdx, 3; Length
0x14005ca3d  mov     r8d, 4; Alignment
0x14005ca43  mov     rcx, [rsp+1D8h+Size+8]; Address
0x14005ca48  call    cs:__imp_ProbeForRead
0x14005ca4f  nop     dword ptr [rax+rax+00h]
0x14005ca54  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005ca58  cmp     edx, 8
0x14005ca5b  jbe     short loc_14005CA86
0x14005ca5d  mov     edx, edx
0x14005ca5f  shl     rdx, 4
0x14005ca63  mov     ecx, 61h ; 'a'
0x14005ca68  mov     r8d, 20646641h
0x14005ca6e  call    cs:__imp_ExAllocatePool2
0x14005ca75  nop     dword ptr [rax+rax+00h]
0x14005ca7a  mov     [rsp+1D8h+P], rax
0x14005ca82  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005ca86  xor     ebx, ebx
0x14005ca88  lea     r15d, [rbx+10h]
0x14005ca8c  mov     [rsp+1D8h+var_168], ebx
0x14005ca90  cmp     ebx, edx
0x14005ca92  jnb     short loc_14005CAD7
0x14005ca94  mov     ecx, ebx
0x14005ca96  shl     rcx, 4
0x14005ca9a  mov     rdx, [rsp+1D8h+Size+8]
0x14005ca9f  add     rdx, rcx; Src
0x14005caa2  add     rcx, [rsp+1D8h+P]; void *
0x14005caaa  mov     r8, r15; Size
0x14005caad  test    r12b, r12b
0x14005cab0  jz      short loc_14005CACA
0x14005cab2  call    RtlCopyFromUser
0x14005cab7  jmp     short loc_14005CACF
0x14005cab9  mov     ecx, 0C000000Dh; Status
0x14005cabe  call    cs:__imp_ExRaiseStatus
0x14005caca  call    RtlCopyVolatileMemory
0x14005cacf  inc     ebx
0x14005cad1  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cad5  jmp     short loc_14005CA8C
0x14005cad7  mov     rax, [rsp+1D8h+P]
0x14005cadf  mov     [rsp+1D8h+Size+8], rax
0x14005cae4  xor     r13b, r13b
0x14005cae7  mov     [rsp+1D8h+var_1A4], r13b
0x14005caec  cmp     [rsp+1D8h+Handle+8], 0
0x14005caf2  jnz     loc_14005CBE5
0x14005caf8  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005caff  jz      short loc_14005CB17
0x14005cb01  mov     edx, 27h ; '''
0x14005cb06  mov     ecx, 413h
0x14005cb0b  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005cb12  call    WPP_SF_
0x14005cb17  mov     ecx, 0C000000Dh; Status
0x14005cb1c  call    cs:__imp_ExRaiseStatus
0x14005cb28  cmp     [rsp+1D8h+arg_20], r8d
0x14005cb30  jnb     short loc_14005CB43
0x14005cb32  mov     ecx, 0C000000Dh; Status
0x14005cb37  call    cs:__imp_ExRaiseStatus
0x14005cb43  test    r12b, r12b
0x14005cb46  jz      short loc_14005CB6D
0x14005cb48  test    bl, 3
0x14005cb4b  jz      short loc_14005CB59
0x14005cb4d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005cb54  nop     dword ptr [rax+rax+00h]
0x14005cb59  test    r12b, r12b
0x14005cb5c  jz      short loc_14005CB6D
0x14005cb5e  mov     rdx, rbx; Src
0x14005cb61  lea     rcx, [rsp+1D8h+Handle]; void *
0x14005cb66  call    RtlCopyFromUser
0x14005cb6b  jmp     short loc_14005CB7A
0x14005cb6d  mov     rdx, rbx; Src
0x14005cb70  lea     rcx, [rsp+1D8h+Handle]; void *
0x14005cb75  call    RtlCopyVolatileMemory
0x14005cb7a  test    r12b, r12b
0x14005cb7d  jz      loc_14005CAEC
0x14005cb83  cmp     dword ptr [rsp+1D8h+Size], 0
0x14005cb88  jz      short loc_14005CBD3
0x14005cb8a  cmp     dword ptr [rsp+1D8h+var_170], 0FFFFFFFh
0x14005cb92  ja      short loc_14005CBD3
0x14005cb94  mov     edx, dword ptr [rsp+1D8h+Size]; Length
0x14005cb98  mov     r8d, 1; Alignment
0x14005cb9e  mov     rcx, [rsp+1D8h+var_190+8]; Address
0x14005cba3  call    cs:__imp_ProbeForRead
0x14005cbaa  nop     dword ptr [rax+rax+00h]
0x14005cbaf  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cbb3  shl     rdx, 3; Length
0x14005cbb7  mov     r8d, 4; Alignment
0x14005cbbd  mov     rcx, [rsp+1D8h+Size+8]; Address
0x14005cbc2  call    cs:__imp_ProbeForRead
0x14005cbc9  nop     dword ptr [rax+rax+00h]
0x14005cbce  jmp     loc_14005CAEC
0x14005cbd3  mov     ecx, 0C000000Dh; Status
0x14005cbd8  call    cs:__imp_ExRaiseStatus
0x14005cbe5  mov     al, byte ptr [rsp+1D8h+var_190]
0x14005cbe9  and     al, 7
0x14005cbeb  cmp     al, 3
0x14005cbed  jz      short loc_14005CBF9
0x14005cbef  mov     edi, 0C000000Dh
0x14005cbf4  jmp     loc_14005D090
0x14005cbf9  mov     ecx, dword ptr [rsp+1D8h+var_170+4]
0x14005cbfd  call    AfdValidateStatus
0x14005cc02  mov     dword ptr [rsp+1D8h+var_170+4], eax
0x14005cc06  mov     rcx, [r14+18h]
0x14005cc0a  mov     [rsp+1D8h+var_120], rcx
0x14005cc12  shr     edi, 0Eh
0x14005cc15  and     edi, 3
0x14005cc18  lea     rax, [rsp+1D8h+Object]
0x14005cc20  mov     [rsp+1D8h+var_1B0], rax; __int64
0x14005cc25  mov     rax, [rsp+1D8h+Handle+8]
0x14005cc2a  mov     qword ptr [rsp+1D8h+var_1B8], rax; __int64
0x14005cc2f  mov     r9, rcx
0x14005cc32  mov     r8b, r12b; AccessMode
0x14005cc35  mov     edx, edi; DesiredAccess
0x14005cc37  mov     rcx, [rsp+1D8h+Handle]; Handle
0x14005cc3c  call    AfdSanReferenceSwitchSocketByHandle
0x14005cc41  mov     edi, eax
0x14005cc43  mov     [rsp+1D8h+var_1A8], eax
0x14005cc47  test    eax, eax
0x14005cc49  js      loc_14005D090
0x14005cc4f  mov     rax, [rsp+1D8h+Object]
0x14005cc57  mov     r15, [rax+18h]
0x14005cc5b  mov     [rsp+1D8h+var_158], r15
0x14005cc63  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005cc6a  jz      short loc_14005CC85
0x14005cc6c  mov     edx, 28h ; '('
0x14005cc71  mov     ecx, 413h
0x14005cc76  mov     r9, r15
0x14005cc79  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005cc80  call    WPP_SF_q
0x14005cc85  mov     rdx, [rsp+1D8h+var_190]
0x14005cc8a  cmp     rdx, 3
0x14005cc8e  jnz     loc_14005CDAD
0x14005cc94  mov     edi, dword ptr [rsp+1D8h+var_170+4]
0x14005cc98  test    edi, edi
0x14005cc9a  js      loc_14005D06C
0x14005cca0  mov     [rsp+1D8h+var_138], 0
0x14005ccac  xor     eax, eax
0x14005ccae  mov     r14d, dword ptr [rsp+1D8h+Size]
0x14005ccb3  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005ccb7  test    edx, edx
0x14005ccb9  jz      short loc_14005CCC8
0x14005ccbb  mov     r8b, r13b
0x14005ccbe  mov     rcx, [rsp+1D8h+Size+8]
0x14005ccc3  call    AfdCalcBufferArrayByteLength
0x14005ccc8  lea     ecx, [rax+r14]
0x14005cccc  cmp     ecx, r14d
0x14005cccf  jb      loc_14005CD65
0x14005ccd5  mov     edx, ecx
0x14005ccd7  mov     ecx, 121h
0x14005ccdc  mov     r8d, 78646641h
0x14005cce2  call    cs:__imp_ExAllocatePool2
0x14005cce9  nop     dword ptr [rax+rax+00h]
0x14005ccee  mov     rbx, rax
0x14005ccf1  mov     [rsp+1D8h+var_138], rax
0x14005ccf9  mov     r8d, dword ptr [rsp+1D8h+Size]; Size
0x14005ccfe  mov     rdx, [rsp+1D8h+var_190+8]; Src
0x14005cd03  mov     rcx, rax; void *
0x14005cd06  test    r12b, r12b
0x14005cd09  jz      short loc_14005CD12
0x14005cd0b  call    RtlCopyFromUser
0x14005cd10  jmp     short loc_14005CD17
0x14005cd12  call    RtlCopyVolatileMemory
0x14005cd17  mov     r9d, dword ptr [rsp+1D8h+var_170]
0x14005cd1c  test    r9d, r9d
0x14005cd1f  jz      short loc_14005CD3F
0x14005cd21  mov     edx, r14d
0x14005cd24  sub     edx, dword ptr [rsp+1D8h+Size]; Size
0x14005cd28  mov     ecx, dword ptr [rsp+1D8h+Size]
0x14005cd2c  add     rcx, rbx; void *
0x14005cd2f  mov     [rsp+1D8h+var_1B8], r13b; char
0x14005cd34  mov     r8, [rsp+1D8h+Size+8]; Src
0x14005cd39  call    AfdCopyBufferArrayToBuffer
0x14005cd3e  nop
0x14005cd3f  mov     r8d, r14d
0x14005cd42  mov     rdx, rbx
0x14005cd45  mov     rcx, [rsp+1D8h+Object]; Object
0x14005cd4d  call    AfdSanDupEndpointIntoServiceProcess
0x14005cd52  mov     edi, eax
0x14005cd54  test    eax, eax
0x14005cd56  js      short loc_14005CD8B
0x14005cd58  mov     rcx, [rsp+1D8h+var_160]
0x14005cd5d  mov     [rcx], r14
0x14005cd60  jmp     loc_14005D076
0x14005cd65  mov     ecx, 0C000009Ah; Status
0x14005cd6a  call    cs:__imp_ExRaiseStatus
0x14005cd77  mov     edi, [rsp+1D8h+var_1A8]
0x14005cd7b  mov     rbx, [rsp+1D8h+var_138]
0x14005cd83  mov     r15, [rsp+1D8h+var_158]
0x14005cd8b  test    rbx, rbx
0x14005cd8e  jz      loc_14005D06C
0x14005cd94  mov     edx, 78646641h; Tag
0x14005cd99  mov     rcx, rbx; P
0x14005cd9c  call    cs:__imp_ExFreePoolWithTag
0x14005cda3  nop     dword ptr [rax+rax+00h]
0x14005cda8  jmp     loc_14005D06C
0x14005cdad  mov     rcx, r15
0x14005cdb0  call    AfdSanDequeueRequest
0x14005cdb5  mov     r14, rax
0x14005cdb8  mov     [rsp+1D8h+var_160], rax
0x14005cdbd  test    rax, rax
0x14005cdc0  jz      loc_14005D067
0x14005cdc6  mov     eax, dword ptr [rsp+1D8h+var_170+4]
0x14005cdca  test    eax, eax
0x14005cdcc  js      loc_14005D04A
0x14005cdd2  mov     rbx, [r14+0B8h]
0x14005cdd9  mov     [rsp+1D8h+var_140], rbx
0x14005cde1  xorps   xmm0, xmm0
0x14005cde4  xor     eax, eax
0x14005cde6  movups  [rsp+1D8h+Src], xmm0
0x14005cdee  mov     [rsp+1D8h+var_D0], eax
0x14005cdf5  call    cs:__imp_IoGetCurrentProcess
0x14005cdfc  nop     dword ptr [rax+rax+00h]
0x14005ce01  mov     [rsp+1D8h+var_128], rax
0x14005ce09  mov     rcx, [r14+90h]
0x14005ce10  mov     rax, [rcx+30h]
  ... truncated ...
```
