# AfdSanFastTransferCtx

- ea: `0x14005ca20`
- end: `0x14005d27b`
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
- `0x14002fd7c`
- `0x1400368e8`
- `0x14003f99c`
- `0x140041a34`
- `0x1400445d8`
- `0x14005ac10`
- `0x14005ad28`
- `0x14005ca20`
- `0x140072840`
- `0x140072870`
- `0x140092008`
- `0x1400930cc`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005caf8`
- `ntoskrnl!ExRaiseStatus` at `0x14005cc5e`
- `ntoskrnl!ExRaiseStatus` at `0x14005ccbc`
- `ntoskrnl!ExRaiseStatus` at `0x14005ccd7`
- `ntoskrnl!ExRaiseStatus` at `0x14005cd78`
- `ntoskrnl!ExRaiseStatus` at `0x14005cf0a`
- `ntoskrnl!ExRaiseStatus` at `0x14005d1c6`
- `ntoskrnl!ExRaiseStatus` at `0x14005caf8`
- `ntoskrnl!ExRaiseStatus` at `0x14005cc5e`
- `ntoskrnl!ExRaiseStatus` at `0x14005ccbc`
- `ntoskrnl!ExRaiseStatus` at `0x14005ccd7`
- `ntoskrnl!ExRaiseStatus` at `0x14005cd78`
- `ntoskrnl!ExRaiseStatus` at `0x14005cf0a`
- `ntoskrnl!ExRaiseStatus` at `0x14005d1c6`
- `ntoskrnl!KeAttachProcess` at `0x14005d0f1`
- `ntoskrnl!KeAttachProcess` at `0x14005d0f1`
- `ntoskrnl!KeDetachProcess` at `0x14005d124`
- `ntoskrnl!KeDetachProcess` at `0x14005d178`
- `ntoskrnl!KeDetachProcess` at `0x14005d124`
- `ntoskrnl!KeDetachProcess` at `0x14005d178`
- `ntoskrnl!ProbeForRead` at `0x14005cbc9`
- `ntoskrnl!ProbeForRead` at `0x14005cbe8`
- `ntoskrnl!ProbeForRead` at `0x14005cd43`
- `ntoskrnl!ProbeForRead` at `0x14005cd62`
- `ntoskrnl!ProbeForRead` at `0x14005cbc9`
- `ntoskrnl!ProbeForRead` at `0x14005cbe8`
- `ntoskrnl!ProbeForRead` at `0x14005cd43`
- `ntoskrnl!ProbeForRead` at `0x14005cd62`
- `ntoskrnl!MmMapLockedPages` at `0x14005d007`
- `ntoskrnl!MmMapLockedPages` at `0x14005d044`
- `ntoskrnl!MmMapLockedPages` at `0x14005d007`
- `ntoskrnl!MmMapLockedPages` at `0x14005d044`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cb0e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cced`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cb0e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005cced`
- `ntoskrnl!IofCompleteRequest` at `0x14005d1f9`
- `ntoskrnl!IofCompleteRequest` at `0x14005d1f9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d21e`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cf3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d24a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cf3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d24a`
- `ntoskrnl!ExAllocatePool2` at `0x14005cc0e`
- `ntoskrnl!ExAllocatePool2` at `0x14005ce82`
- `ntoskrnl!ExAllocatePool2` at `0x14005cc0e`
- `ntoskrnl!ExAllocatePool2` at `0x14005ce82`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005cf95`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005cf95`
- `ntoskrnl!IoIs32bitProcess` at `0x14005caa6`
- `ntoskrnl!IoIs32bitProcess` at `0x14005caa6`

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
0x14005ca20  push    rbx
0x14005ca22  push    rdi
0x14005ca23  push    r12
0x14005ca25  push    r13
0x14005ca27  push    r14
0x14005ca29  push    r15
0x14005ca2b  sub     rsp, 1A8h
0x14005ca32  mov     rax, cs:__security_cookie
0x14005ca39  xor     rax, rsp
0x14005ca3c  mov     [rsp+1D8h+var_48], rax
0x14005ca44  mov     rbx, r9
0x14005ca47  mov     r12b, r8b
0x14005ca4a  mov     edi, edx
0x14005ca4c  mov     r14, rcx
0x14005ca4f  mov     rax, [rsp+1D8h+arg_38]
0x14005ca57  mov     [rsp+1D8h+var_160], rax
0x14005ca5c  xorps   xmm0, xmm0
0x14005ca5f  xor     ecx, ecx
0x14005ca61  movups  xmmword ptr [rsp+1D8h+Handle], xmm0
0x14005ca66  movups  xmmword ptr [rsp+1D8h+var_190], xmm0
0x14005ca6b  movups  xmmword ptr [rsp+1D8h+Size], xmm0
0x14005ca70  mov     [rsp+1D8h+var_170], rcx
0x14005ca75  mov     [rsp+1D8h+Object], rcx
0x14005ca7d  mov     r13b, r8b
0x14005ca80  mov     [rsp+1D8h+var_1A4], r8b
0x14005ca85  lea     rcx, [rsp+1D8h+var_C8]
0x14005ca8d  mov     [rsp+1D8h+P], rcx
0x14005ca95  mov     qword ptr [rax], 0
0x14005ca9c  mov     [rsp+1D8h+var_1A8], 0
0x14005caa4  xor     ecx, ecx; Irp
0x14005caa6  call    cs:__imp_IoIs32bitProcess
0x14005caad  nop     dword ptr [rax+rax+00h]
0x14005cab2  mov     r8d, 38h ; '8'; Size
0x14005cab8  test    al, al
0x14005caba  jz      loc_14005CCC8
0x14005cac0  xorps   xmm0, xmm0
0x14005cac3  xor     eax, eax
0x14005cac5  movups  [rsp+1D8h+var_118], xmm0
0x14005cacd  movups  xmmword ptr [rsp+1D8h+Address], xmm0
0x14005cad5  movups  xmmword ptr [rsp+1D8h+Length], xmm0
0x14005cadd  mov     [rsp+1D8h+var_E8], rax
0x14005cae5  mov     [rsp+1D8h+var_168], eax
0x14005cae9  cmp     [rsp+1D8h+arg_20], r8d
0x14005caf1  jnb     short loc_14005CB04
0x14005caf3  mov     ecx, 0C000000Dh; Status
0x14005caf8  call    cs:__imp_ExRaiseStatus
0x14005cb04  test    r12b, r12b
0x14005cb07  jz      short loc_14005CB31
0x14005cb09  test    bl, 3
0x14005cb0c  jz      short loc_14005CB1A
0x14005cb0e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005cb15  nop     dword ptr [rax+rax+00h]
0x14005cb1a  test    r12b, r12b
0x14005cb1d  jz      short loc_14005CB31
0x14005cb1f  mov     rdx, rbx; Src
0x14005cb22  lea     rcx, [rsp+1D8h+var_118]; void *
0x14005cb2a  call    RtlCopyFromUser
0x14005cb2f  jmp     short loc_14005CB41
0x14005cb31  mov     rdx, rbx; Src
0x14005cb34  lea     rcx, [rsp+1D8h+var_118]; void *
0x14005cb3c  call    RtlCopyVolatileMemory
0x14005cb41  mov     rax, qword ptr [rsp+1D8h+var_118]
0x14005cb49  mov     [rsp+1D8h+Handle], rax
0x14005cb4e  mov     rax, qword ptr [rsp+1D8h+var_118+8]
0x14005cb56  mov     [rsp+1D8h+Handle+8], rax
0x14005cb5b  mov     rax, [rsp+1D8h+Address]
0x14005cb63  mov     [rsp+1D8h+var_190], rax
0x14005cb68  mov     rcx, [rsp+1D8h+Address+8]; Address
0x14005cb70  mov     [rsp+1D8h+var_190+8], rcx
0x14005cb75  mov     r8d, dword ptr [rsp+1D8h+Length]
0x14005cb7d  mov     dword ptr [rsp+1D8h+Size], r8d
0x14005cb82  mov     rax, [rsp+1D8h+Length+8]
0x14005cb8a  mov     [rsp+1D8h+Size+8], rax
0x14005cb8f  mov     rdx, [rsp+1D8h+var_E8]
0x14005cb97  mov     dword ptr [rsp+1D8h+var_170], edx
0x14005cb9b  mov     eax, dword ptr [rsp+1D8h+var_E8+4]
0x14005cba2  mov     dword ptr [rsp+1D8h+var_170+4], eax
0x14005cba6  test    r12b, r12b
0x14005cba9  jz      short loc_14005CBF8
0x14005cbab  test    r8d, r8d
0x14005cbae  jz      loc_14005CC59
0x14005cbb4  cmp     edx, 1FFFFFFFh
0x14005cbba  ja      loc_14005CC59
0x14005cbc0  mov     edx, r8d; Length
0x14005cbc3  mov     r8d, 1; Alignment
0x14005cbc9  call    cs:__imp_ProbeForRead
0x14005cbd0  nop     dword ptr [rax+rax+00h]
0x14005cbd5  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cbd9  shl     rdx, 3; Length
0x14005cbdd  mov     r8d, 4; Alignment
0x14005cbe3  mov     rcx, [rsp+1D8h+Size+8]; Address
0x14005cbe8  call    cs:__imp_ProbeForRead
0x14005cbef  nop     dword ptr [rax+rax+00h]
0x14005cbf4  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cbf8  cmp     edx, 8
0x14005cbfb  jbe     short loc_14005CC26
0x14005cbfd  mov     edx, edx
0x14005cbff  shl     rdx, 4
0x14005cc03  mov     ecx, 61h ; 'a'
0x14005cc08  mov     r8d, 20646641h
0x14005cc0e  call    cs:__imp_ExAllocatePool2
0x14005cc15  nop     dword ptr [rax+rax+00h]
0x14005cc1a  mov     [rsp+1D8h+P], rax
0x14005cc22  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cc26  xor     ebx, ebx
0x14005cc28  lea     r15d, [rbx+10h]
0x14005cc2c  mov     [rsp+1D8h+var_168], ebx
0x14005cc30  cmp     ebx, edx
0x14005cc32  jnb     short loc_14005CC77
0x14005cc34  mov     ecx, ebx
0x14005cc36  shl     rcx, 4
0x14005cc3a  mov     rdx, [rsp+1D8h+Size+8]
0x14005cc3f  add     rdx, rcx; Src
0x14005cc42  add     rcx, [rsp+1D8h+P]; void *
0x14005cc4a  mov     r8, r15; Size
0x14005cc4d  test    r12b, r12b
0x14005cc50  jz      short loc_14005CC6A
0x14005cc52  call    RtlCopyFromUser
0x14005cc57  jmp     short loc_14005CC6F
0x14005cc59  mov     ecx, 0C000000Dh; Status
0x14005cc5e  call    cs:__imp_ExRaiseStatus
0x14005cc6a  call    RtlCopyVolatileMemory
0x14005cc6f  inc     ebx
0x14005cc71  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cc75  jmp     short loc_14005CC2C
0x14005cc77  mov     rax, [rsp+1D8h+P]
0x14005cc7f  mov     [rsp+1D8h+Size+8], rax
0x14005cc84  xor     r13b, r13b
0x14005cc87  mov     [rsp+1D8h+var_1A4], r13b
0x14005cc8c  cmp     [rsp+1D8h+Handle+8], 0
0x14005cc92  jnz     loc_14005CD85
0x14005cc98  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005cc9f  jz      short loc_14005CCB7
0x14005cca1  mov     edx, 27h ; '''
0x14005cca6  mov     ecx, 413h
0x14005ccab  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005ccb2  call    WPP_SF_
0x14005ccb7  mov     ecx, 0C000000Dh; Status
0x14005ccbc  call    cs:__imp_ExRaiseStatus
0x14005ccc8  cmp     [rsp+1D8h+arg_20], r8d
0x14005ccd0  jnb     short loc_14005CCE3
0x14005ccd2  mov     ecx, 0C000000Dh; Status
0x14005ccd7  call    cs:__imp_ExRaiseStatus
0x14005cce3  test    r12b, r12b
0x14005cce6  jz      short loc_14005CD0D
0x14005cce8  test    bl, 3
0x14005cceb  jz      short loc_14005CCF9
0x14005cced  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005ccf4  nop     dword ptr [rax+rax+00h]
0x14005ccf9  test    r12b, r12b
0x14005ccfc  jz      short loc_14005CD0D
0x14005ccfe  mov     rdx, rbx; Src
0x14005cd01  lea     rcx, [rsp+1D8h+Handle]; void *
0x14005cd06  call    RtlCopyFromUser
0x14005cd0b  jmp     short loc_14005CD1A
0x14005cd0d  mov     rdx, rbx; Src
0x14005cd10  lea     rcx, [rsp+1D8h+Handle]; void *
0x14005cd15  call    RtlCopyVolatileMemory
0x14005cd1a  test    r12b, r12b
0x14005cd1d  jz      loc_14005CC8C
0x14005cd23  cmp     dword ptr [rsp+1D8h+Size], 0
0x14005cd28  jz      short loc_14005CD73
0x14005cd2a  cmp     dword ptr [rsp+1D8h+var_170], 0FFFFFFFh
0x14005cd32  ja      short loc_14005CD73
0x14005cd34  mov     edx, dword ptr [rsp+1D8h+Size]; Length
0x14005cd38  mov     r8d, 1; Alignment
0x14005cd3e  mov     rcx, [rsp+1D8h+var_190+8]; Address
0x14005cd43  call    cs:__imp_ProbeForRead
0x14005cd4a  nop     dword ptr [rax+rax+00h]
0x14005cd4f  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005cd53  shl     rdx, 3; Length
0x14005cd57  mov     r8d, 4; Alignment
0x14005cd5d  mov     rcx, [rsp+1D8h+Size+8]; Address
0x14005cd62  call    cs:__imp_ProbeForRead
0x14005cd69  nop     dword ptr [rax+rax+00h]
0x14005cd6e  jmp     loc_14005CC8C
0x14005cd73  mov     ecx, 0C000000Dh; Status
0x14005cd78  call    cs:__imp_ExRaiseStatus
0x14005cd85  mov     al, byte ptr [rsp+1D8h+var_190]
0x14005cd89  and     al, 7
0x14005cd8b  cmp     al, 3
0x14005cd8d  jz      short loc_14005CD99
0x14005cd8f  mov     edi, 0C000000Dh
0x14005cd94  jmp     loc_14005D230
0x14005cd99  mov     ecx, dword ptr [rsp+1D8h+var_170+4]
0x14005cd9d  call    AfdValidateStatus
0x14005cda2  mov     dword ptr [rsp+1D8h+var_170+4], eax
0x14005cda6  mov     rcx, [r14+18h]
0x14005cdaa  mov     [rsp+1D8h+var_120], rcx
0x14005cdb2  shr     edi, 0Eh
0x14005cdb5  and     edi, 3
0x14005cdb8  lea     rax, [rsp+1D8h+Object]
0x14005cdc0  mov     [rsp+1D8h+var_1B0], rax; __int64
0x14005cdc5  mov     rax, [rsp+1D8h+Handle+8]
0x14005cdca  mov     qword ptr [rsp+1D8h+var_1B8], rax; __int64
0x14005cdcf  mov     r9, rcx
0x14005cdd2  mov     r8b, r12b; AccessMode
0x14005cdd5  mov     edx, edi; DesiredAccess
0x14005cdd7  mov     rcx, [rsp+1D8h+Handle]; Handle
0x14005cddc  call    AfdSanReferenceSwitchSocketByHandle
0x14005cde1  mov     edi, eax
0x14005cde3  mov     [rsp+1D8h+var_1A8], eax
0x14005cde7  test    eax, eax
0x14005cde9  js      loc_14005D230
0x14005cdef  mov     rax, [rsp+1D8h+Object]
0x14005cdf7  mov     r15, [rax+18h]
0x14005cdfb  mov     [rsp+1D8h+var_158], r15
0x14005ce03  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005ce0a  jz      short loc_14005CE25
0x14005ce0c  mov     edx, 28h ; '('
0x14005ce11  mov     ecx, 413h
0x14005ce16  mov     r9, r15
0x14005ce19  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x14005ce20  call    WPP_SF_q
0x14005ce25  mov     rdx, [rsp+1D8h+var_190]
0x14005ce2a  cmp     rdx, 3
0x14005ce2e  jnz     loc_14005CF4D
0x14005ce34  mov     edi, dword ptr [rsp+1D8h+var_170+4]
0x14005ce38  test    edi, edi
0x14005ce3a  js      loc_14005D20C
0x14005ce40  mov     [rsp+1D8h+var_138], 0
0x14005ce4c  xor     eax, eax
0x14005ce4e  mov     r14d, dword ptr [rsp+1D8h+Size]
0x14005ce53  mov     edx, dword ptr [rsp+1D8h+var_170]
0x14005ce57  test    edx, edx
0x14005ce59  jz      short loc_14005CE68
0x14005ce5b  mov     r8b, r13b
0x14005ce5e  mov     rcx, [rsp+1D8h+Size+8]
0x14005ce63  call    AfdCalcBufferArrayByteLength
0x14005ce68  lea     ecx, [rax+r14]
0x14005ce6c  cmp     ecx, r14d
0x14005ce6f  jb      loc_14005CF05
0x14005ce75  mov     edx, ecx
0x14005ce77  mov     ecx, 121h
0x14005ce7c  mov     r8d, 78646641h
0x14005ce82  call    cs:__imp_ExAllocatePool2
0x14005ce89  nop     dword ptr [rax+rax+00h]
0x14005ce8e  mov     rbx, rax
0x14005ce91  mov     [rsp+1D8h+var_138], rax
0x14005ce99  mov     r8d, dword ptr [rsp+1D8h+Size]; Size
0x14005ce9e  mov     rdx, [rsp+1D8h+var_190+8]; Src
0x14005cea3  mov     rcx, rax; void *
0x14005cea6  test    r12b, r12b
0x14005cea9  jz      short loc_14005CEB2
0x14005ceab  call    RtlCopyFromUser
0x14005ceb0  jmp     short loc_14005CEB7
0x14005ceb2  call    RtlCopyVolatileMemory
0x14005ceb7  mov     r9d, dword ptr [rsp+1D8h+var_170]
0x14005cebc  test    r9d, r9d
0x14005cebf  jz      short loc_14005CEDF
0x14005cec1  mov     edx, r14d
0x14005cec4  sub     edx, dword ptr [rsp+1D8h+Size]; Size
0x14005cec8  mov     ecx, dword ptr [rsp+1D8h+Size]
0x14005cecc  add     rcx, rbx; void *
0x14005cecf  mov     [rsp+1D8h+var_1B8], r13b; char
0x14005ced4  mov     r8, [rsp+1D8h+Size+8]; Src
0x14005ced9  call    AfdCopyBufferArrayToBuffer
0x14005cede  nop
0x14005cedf  mov     r8d, r14d
0x14005cee2  mov     rdx, rbx
0x14005cee5  mov     rcx, [rsp+1D8h+Object]; Object
0x14005ceed  call    AfdSanDupEndpointIntoServiceProcess
0x14005cef2  mov     edi, eax
0x14005cef4  test    eax, eax
0x14005cef6  js      short loc_14005CF2B
0x14005cef8  mov     rcx, [rsp+1D8h+var_160]
0x14005cefd  mov     [rcx], r14
0x14005cf00  jmp     loc_14005D216
0x14005cf05  mov     ecx, 0C000009Ah; Status
0x14005cf0a  call    cs:__imp_ExRaiseStatus
0x14005cf17  mov     edi, [rsp+1D8h+var_1A8]
0x14005cf1b  mov     rbx, [rsp+1D8h+var_138]
0x14005cf23  mov     r15, [rsp+1D8h+var_158]
0x14005cf2b  test    rbx, rbx
0x14005cf2e  jz      loc_14005D20C
0x14005cf34  mov     edx, 78646641h; Tag
0x14005cf39  mov     rcx, rbx; P
0x14005cf3c  call    cs:__imp_ExFreePoolWithTag
0x14005cf43  nop     dword ptr [rax+rax+00h]
0x14005cf48  jmp     loc_14005D20C
0x14005cf4d  mov     rcx, r15
0x14005cf50  call    AfdSanDequeueRequest
0x14005cf55  mov     r14, rax
0x14005cf58  mov     [rsp+1D8h+var_160], rax
0x14005cf5d  test    rax, rax
0x14005cf60  jz      loc_14005D207
0x14005cf66  mov     eax, dword ptr [rsp+1D8h+var_170+4]
0x14005cf6a  test    eax, eax
0x14005cf6c  js      loc_14005D1EA
0x14005cf72  mov     rbx, [r14+0B8h]
0x14005cf79  mov     [rsp+1D8h+var_140], rbx
0x14005cf81  xorps   xmm0, xmm0
0x14005cf84  xor     eax, eax
0x14005cf86  movups  [rsp+1D8h+Src], xmm0
0x14005cf8e  mov     [rsp+1D8h+var_D0], eax
0x14005cf95  call    cs:__imp_IoGetCurrentProcess
0x14005cf9c  nop     dword ptr [rax+rax+00h]
0x14005cfa1  mov     [rsp+1D8h+var_128], rax
0x14005cfa9  mov     rcx, [r14+90h]
0x14005cfb0  mov     rax, [rcx+30h]
  ... truncated ...
```
