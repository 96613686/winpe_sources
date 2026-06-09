# USBSTOR_GetDumpPointers

- ea: `0x14000ed10`
- end: `0x14000f1e1`
- name: `USBSTOR_GetDumpPointers`
- size: `1233`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x14000ed10`
- `0x1400105e8`
- `0x140010664`
- `0x140011a60`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000f01f`
- `ntoskrnl!IoFreeIrp` at `0x14000f177`
- `ntoskrnl!IoFreeIrp` at `0x14000f01f`
- `ntoskrnl!IoFreeIrp` at `0x14000f177`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee2a`
- `ntoskrnl!ExAllocatePool2` at `0x14000f069`
- `ntoskrnl!ExAllocatePool2` at `0x14000ee2a`
- `ntoskrnl!ExAllocatePool2` at `0x14000f069`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000efbd`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000efbd`
- `ntoskrnl!IofCallDriver` at `0x14000efde`
- `ntoskrnl!IofCallDriver` at `0x14000efde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f153`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f192`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f153`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f192`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f1a3`
- `ntoskrnl!KeInitializeEvent` at `0x14000ef5c`
- `ntoskrnl!KeInitializeEvent` at `0x14000ef5c`
- `ntoskrnl!IofCompleteRequest` at `0x14000f0f7`
- `ntoskrnl!IofCompleteRequest` at `0x14000f1b7`
- `ntoskrnl!IofCompleteRequest` at `0x14000f0f7`
- `ntoskrnl!IofCompleteRequest` at `0x14000f1b7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f004`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f004`
- `ntoskrnl!IoAllocateIrp` at `0x14000ef39`
- `ntoskrnl!IoAllocateIrp` at `0x14000ef39`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetDumpPointers(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  __int64 v4; // r13
  NTSTATUS Status; // ebx
  unsigned int v6; // ebx
  struct _IRP *MasterIrp; // r15
  __int64 Pool2; // r12
  __int64 v9; // rax
  PVOID *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdi
  PIRP Irp; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v16; // rax
  char v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+44h] [rbp-25h]
  char v20; // [rsp+48h] [rbp-21h]
  int v21; // [rsp+4Ch] [rbp-1Dh]
  struct _KEVENT Event; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v23[64]; // [rsp+68h] [rbp-1h] BYREF
  PDEVICE_OBJECT DeviceObjecta; // [rsp+D0h] [rbp+67h]
  __int64 v26; // [rsp+D8h] [rbp+6Fh]

  memset(v23, 0, 28);
  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 206, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v4 = *(_QWORD *)(*((_QWORD *)a1->DeviceExtension + 2) + 64LL);
  v26 = v4;
  a2->IoStatus.Information = 0;
  if ( a2->RequestorMode )
  {
    Status = -1073741808;
LABEL_37:
    a2->IoStatus.Status = Status;
    IofCompleteRequest(a2, 0);
    return (unsigned int)Status;
  }
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x68 )
  {
LABEL_12:
    Status = -1073741789;
    goto LABEL_37;
  }
  v6 = 0;
  while ( *(_QWORD *)(v4 + 8LL * v6 + 1896) )
  {
    if ( ++v6 >= 2 )
    {
      if ( v6 == 2 )
        goto LABEL_12;
      break;
    }
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  *(_QWORD *)&v23[8] = &v18;
  *(_QWORD *)v23 = 2;
  *(_OWORD *)&v23[16] = 0;
  v18 = *(_BYTE *)(*(_QWORD *)(v4 + 96) + 2LL);
  v19 = 81920;
  v20 = *(_BYTE *)(*(_QWORD *)(v4 + 104) + 2LL);
  v21 = 81920;
  *(_WORD *)&v23[16] = 1;
  v23[18] = 0;
  Pool2 = ExAllocatePool2(64, 304, 7368036);
  if ( !Pool2 )
  {
    Status = -1073741670;
    goto LABEL_37;
  }
  v9 = *(_QWORD *)(v4 + 96);
  v10 = 0;
  *(_OWORD *)(Pool2 + 32) = *(_OWORD *)v9;
  *(_QWORD *)(Pool2 + 48) = *(_QWORD *)(v9 + 16);
  v11 = *(_QWORD *)(v4 + 104);
  *(_OWORD *)(Pool2 + 56) = *(_OWORD *)v11;
  *(_QWORD *)(Pool2 + 72) = *(_QWORD *)(v11 + 16);
  *(_OWORD *)(Pool2 + 80) = *(_OWORD *)(v4 + 392);
  *(_OWORD *)(Pool2 + 96) = *(_OWORD *)(v4 + 408);
  *(_OWORD *)(Pool2 + 112) = *(_OWORD *)(v4 + 424);
  *(_OWORD *)(Pool2 + 128) = *(_OWORD *)(v4 + 440);
  *(_OWORD *)(Pool2 + 144) = *(_OWORD *)(v4 + 456);
  *(_OWORD *)(Pool2 + 160) = *(_OWORD *)(v4 + 472);
  *(_OWORD *)(Pool2 + 176) = *(_OWORD *)(v4 + 488);
  *(_OWORD *)(Pool2 + 192) = *(_OWORD *)(v4 + 504);
  v12 = *(_QWORD *)(v4 + 520);
  *(_BYTE *)(Pool2 + 300) = 0;
  *(_QWORD *)(Pool2 + 208) = v12;
  *(_WORD *)Pool2 = 304;
  *(_DWORD *)(Pool2 + 296) = 31;
  v13 = v6;
  *(_QWORD *)(v4 + 8LL * v6 + 1896) = Pool2;
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v4 + 24) + 76LL), 0);
  if ( !Irp )
    goto LABEL_30;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4789252;
  CurrentStackLocation[-1].Parameters.Create.Options = 32;
  CurrentStackLocation[-1].Parameters.Read.Length = 88;
  Irp->AssociatedIrp.MasterIrp = (struct _IRP *)v23;
  Irp->UserBuffer = (PVOID)(Pool2 + 216);
  Status = IoSetCompletionRoutineEx(a1, Irp, USBSTOR_SyncCompletionRoutine, &Event, 1u, 1u, 1u);
  if ( Status < 0 )
    goto LABEL_31;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v26 + 24), Irp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  if ( Status < 0 )
    goto LABEL_31;
  IoFreeIrp(Irp);
  Irp = 0;
  if ( !*(_QWORD *)(Pool2 + 280)
    || !*(_QWORD *)(Pool2 + 288)
    || (v10 = (PVOID *)USBSTOR_DeviceBuildDumpDriverList()) == 0
    || (v16 = ExAllocatePool2(64, 152, 7368036), (DeviceObjecta = (PDEVICE_OBJECT)v16) == 0) )
  {
LABEL_30:
    Status = -1073741670;
LABEL_31:
    ExFreePoolWithTag((PVOID)Pool2, 0);
    *(_QWORD *)(v26 + 8 * v13 + 1896) = 0;
    if ( Irp )
      IoFreeIrp(Irp);
    if ( v10 )
    {
      if ( *v10 )
        ExFreePoolWithTag(*v10, 0);
      ExFreePoolWithTag(v10, 0);
    }
    goto LABEL_37;
  }
  *(_DWORD *)v16 = 152;
  *(_DWORD *)(v16 + 8) = 15;
  *(_DWORD *)(v16 + 24) = 81920;
  *(_QWORD *)(v16 + 64) = Pool2;
  *(_QWORD *)(v26 + 8 * v13 + 1912) = v16;
  memset(MasterIrp, 0, 0x68u);
  MasterIrp->MdlAddress = (PMDL)DeviceObjecta;
  *(_DWORD *)&MasterIrp->Type = 3;
  *(_DWORD *)(&MasterIrp->Size + 1) = 104;
  BYTE4(MasterIrp->AssociatedIrp.SystemBuffer) = 1;
  MasterIrp->ThreadListEntry.Blink = (struct _LIST_ENTRY *)v10;
  HIDWORD(MasterIrp->IoStatus.Information) = 81920;
  if ( *(_BYTE *)(Pool2 + 300) == 1 )
    MasterIrp->IoStatus.Status |= 4u;
  a2->IoStatus.Information = 104;
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 207, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000ed10  mov     [rsp-8+arg_10], rbx
0x14000ed15  mov     [rsp-8+DeviceObject], rcx
0x14000ed1a  push    rbp
0x14000ed1b  push    rsi
0x14000ed1c  push    rdi
0x14000ed1d  push    r12
0x14000ed1f  push    r13
0x14000ed21  push    r14
0x14000ed23  push    r15
0x14000ed25  lea     rbp, [rsp-27h]
0x14000ed2a  sub     rsp, 90h
0x14000ed31  xorps   xmm0, xmm0
0x14000ed34  xor     eax, eax
0x14000ed36  movups  [rbp+57h+var_58], xmm0
0x14000ed3a  mov     rsi, rdx
0x14000ed3d  mov     rbx, rcx
0x14000ed40  movups  [rbp+57h+var_58+0Ch], xmm0
0x14000ed44  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14000ed48  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14000ed4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed53  lea     rax, WPP_GLOBAL_Control
0x14000ed5a  cmp     rcx, rax
0x14000ed5d  jz      short loc_14000ED81
0x14000ed5f  mov     eax, [rcx+2Ch]
0x14000ed62  test    al, 1
0x14000ed64  jz      short loc_14000ED81
0x14000ed66  cmp     byte ptr [rcx+29h], 5
0x14000ed6a  jb      short loc_14000ED81
0x14000ed6c  mov     rcx, [rcx+18h]
0x14000ed70  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000ed77  mov     edx, 0CEh
0x14000ed7c  call    WPP_SF_
0x14000ed81  mov     rax, [rbx+40h]
0x14000ed85  xor     edi, edi
0x14000ed87  mov     rcx, [rax+10h]
0x14000ed8b  mov     r13, [rcx+40h]
0x14000ed8f  mov     [rbp+57h+arg_8], r13
0x14000ed93  mov     [rsi+38h], rdi
0x14000ed97  cmp     [rsi+40h], dil
0x14000ed9b  jz      short loc_14000EDA7
0x14000ed9d  mov     ebx, 0C0000010h
0x14000eda2  jmp     loc_14000F1AF
0x14000eda7  mov     rax, [rsi+0B8h]
0x14000edae  cmp     dword ptr [rax+8], 68h ; 'h'
0x14000edb2  jb      short loc_14000EDCB
0x14000edb4  mov     ebx, edi
0x14000edb6  mov     eax, ebx
0x14000edb8  cmp     [r13+rax*8+768h], rdi
0x14000edc0  jz      short loc_14000EDD5
0x14000edc2  inc     ebx
0x14000edc4  cmp     ebx, 2
0x14000edc7  jb      short loc_14000EDB6
0x14000edc9  jnz     short loc_14000EDD5
0x14000edcb  mov     ebx, 0C0000023h
0x14000edd0  jmp     loc_14000F1AF
0x14000edd5  mov     r15, [rsi+18h]
0x14000edd9  lea     rax, [rbp+57h+var_80]
0x14000eddd  mov     qword ptr [rbp+57h+var_58+8], rax
0x14000ede1  mov     edx, 14000h
0x14000ede6  mov     qword ptr [rbp+57h+var_58], 2
0x14000edee  xorps   xmm0, xmm0
0x14000edf1  movdqu  [rbp+57h+var_48], xmm0
0x14000edf6  mov     rax, [r13+60h]
0x14000edfa  mov     r8d, 706D64h
0x14000ee00  mov     cl, [rax+2]
0x14000ee03  mov     [rbp+57h+var_80], cl
0x14000ee06  mov     [rbp+57h+var_7C], edx
0x14000ee09  mov     rax, [r13+68h]
0x14000ee0d  mov     cl, [rax+2]
0x14000ee10  mov     [rbp+57h+var_78], cl
0x14000ee13  mov     ecx, 40h ; '@'
0x14000ee18  mov     [rbp+57h+var_74], edx
0x14000ee1b  mov     edx, 130h
0x14000ee20  mov     word ptr [rbp+57h+var_48], 1
0x14000ee26  mov     byte ptr [rbp+57h+var_48+2], dil
0x14000ee2a  call    cs:__imp_ExAllocatePool2
0x14000ee31  nop     dword ptr [rax+rax+00h]
0x14000ee36  mov     r12, rax
0x14000ee39  test    rax, rax
0x14000ee3c  jnz     short loc_14000EE48
0x14000ee3e  mov     ebx, 0C000009Ah
0x14000ee43  jmp     loc_14000F1AF
0x14000ee48  mov     rax, [r13+60h]
0x14000ee4c  mov     r14, rdi
0x14000ee4f  xor     edx, edx; ChargeQuota
0x14000ee51  movups  xmm0, xmmword ptr [rax]
0x14000ee54  movups  xmmword ptr [r12+20h], xmm0
0x14000ee5a  movsd   xmm1, qword ptr [rax+10h]
0x14000ee5f  movsd   qword ptr [r12+30h], xmm1
0x14000ee66  mov     rax, [r13+68h]
0x14000ee6a  movups  xmm0, xmmword ptr [rax]
0x14000ee6d  movups  xmmword ptr [r12+38h], xmm0
0x14000ee73  movsd   xmm1, qword ptr [rax+10h]
0x14000ee78  movsd   qword ptr [r12+48h], xmm1
0x14000ee7f  movups  xmm0, xmmword ptr [r13+188h]
0x14000ee87  movups  xmmword ptr [r12+50h], xmm0
0x14000ee8d  movups  xmm1, xmmword ptr [r13+198h]
0x14000ee95  movups  xmmword ptr [r12+60h], xmm1
0x14000ee9b  movups  xmm0, xmmword ptr [r13+1A8h]
0x14000eea3  movups  xmmword ptr [r12+70h], xmm0
0x14000eea9  movups  xmm1, xmmword ptr [r13+1B8h]
0x14000eeb1  movups  xmmword ptr [r12+80h], xmm1
0x14000eeba  movups  xmm0, xmmword ptr [r13+1C8h]
0x14000eec2  movups  xmmword ptr [r12+90h], xmm0
0x14000eecb  movups  xmm1, xmmword ptr [r13+1D8h]
0x14000eed3  movups  xmmword ptr [r12+0A0h], xmm1
0x14000eedc  movups  xmm0, xmmword ptr [r13+1E8h]
0x14000eee4  movups  xmmword ptr [r12+0B0h], xmm0
0x14000eeed  movups  xmm1, xmmword ptr [r13+1F8h]
0x14000eef5  movups  xmmword ptr [r12+0C0h], xmm1
0x14000eefe  mov     rax, [r13+208h]
0x14000ef05  mov     [r12+12Ch], dil
0x14000ef0d  mov     [r12+0D0h], rax
0x14000ef15  mov     word ptr [r12], 130h
0x14000ef1c  mov     dword ptr [r12+128h], 1Fh
0x14000ef28  mov     edi, ebx
0x14000ef2a  mov     [r13+rdi*8+768h], r12
0x14000ef32  mov     rcx, [r13+18h]
0x14000ef36  mov     cl, [rcx+4Ch]; StackSize
0x14000ef39  call    cs:__imp_IoAllocateIrp
0x14000ef40  nop     dword ptr [rax+rax+00h]
0x14000ef45  mov     r13, rax
0x14000ef48  test    rax, rax
0x14000ef4b  jz      loc_14000F149
0x14000ef51  xor     r8d, r8d; State
0x14000ef54  lea     rcx, [rbp+57h+Event]; Event
0x14000ef58  lea     edx, [r8+1]; Type
0x14000ef5c  call    cs:__imp_KeInitializeEvent
0x14000ef63  nop     dword ptr [rax+rax+00h]
0x14000ef68  mov     rax, [r13+0B8h]
0x14000ef6f  lea     r9, [rbp+57h+Event]; Context
0x14000ef73  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14000ef77  lea     r8, USBSTOR_SyncCompletionRoutine; CompletionRoutine
0x14000ef7e  mov     [rsp+0C0h+InvokeOnCancel], 1; InvokeOnCancel
0x14000ef83  mov     rdx, r13; Irp
0x14000ef86  mov     [rsp+0C0h+InvokeOnError], 1; InvokeOnError
0x14000ef8b  mov     byte ptr [rax-48h], 0Fh
0x14000ef8f  mov     dword ptr [rax-30h], 491404h
0x14000ef96  mov     dword ptr [rax-38h], 20h ; ' '
0x14000ef9d  mov     dword ptr [rax-40h], 58h ; 'X'
0x14000efa4  lea     rax, [rbp+57h+var_58]
0x14000efa8  mov     [r13+18h], rax
0x14000efac  lea     rax, [r12+0D8h]
0x14000efb4  mov     [r13+70h], rax
0x14000efb8  mov     [rsp+0C0h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000efbd  call    cs:__imp_IoSetCompletionRoutineEx
0x14000efc4  nop     dword ptr [rax+rax+00h]
0x14000efc9  mov     ebx, eax
0x14000efcb  test    eax, eax
0x14000efcd  js      loc_14000F14E
0x14000efd3  mov     rax, [rbp+57h+arg_8]
0x14000efd7  mov     rdx, r13; Irp
0x14000efda  mov     rcx, [rax+18h]; DeviceObject
0x14000efde  call    cs:__imp_IofCallDriver
0x14000efe5  nop     dword ptr [rax+rax+00h]
0x14000efea  mov     ebx, eax
0x14000efec  cmp     eax, 103h
0x14000eff1  jnz     short loc_14000F014
0x14000eff3  xor     r9d, r9d; Alertable
0x14000eff6  mov     qword ptr [rsp+0C0h+InvokeOnSuccess], r14; Timeout
0x14000effb  xor     r8d, r8d; WaitMode
0x14000effe  lea     rcx, [rbp+57h+Event]; Object
0x14000f002  xor     edx, edx; WaitReason
0x14000f004  call    cs:__imp_KeWaitForSingleObject
0x14000f00b  nop     dword ptr [rax+rax+00h]
0x14000f010  mov     ebx, [r13+30h]
0x14000f014  test    ebx, ebx
0x14000f016  js      loc_14000F14E
0x14000f01c  mov     rcx, r13; Irp
0x14000f01f  call    cs:__imp_IoFreeIrp
0x14000f026  nop     dword ptr [rax+rax+00h]
0x14000f02b  xor     r13d, r13d
0x14000f02e  cmp     [r12+118h], r13
0x14000f036  jz      loc_14000F149
0x14000f03c  cmp     [r12+120h], r13
0x14000f044  jz      loc_14000F149
0x14000f04a  call    USBSTOR_DeviceBuildDumpDriverList
0x14000f04f  mov     r14, rax
0x14000f052  test    rax, rax
0x14000f055  jz      loc_14000F149
0x14000f05b  mov     edx, 98h
0x14000f060  mov     r8d, 706D64h
0x14000f066  lea     ecx, [rdx-58h]
0x14000f069  call    cs:__imp_ExAllocatePool2
0x14000f070  nop     dword ptr [rax+rax+00h]
0x14000f075  mov     [rbp+57h+DeviceObject], rax
0x14000f079  test    rax, rax
0x14000f07c  jz      loc_14000F149
0x14000f082  mov     rcx, [rbp+57h+arg_8]
0x14000f086  mov     r13d, 14000h
0x14000f08c  mov     dword ptr [rax], 98h
0x14000f092  xor     edx, edx; Val
0x14000f094  mov     dword ptr [rax+8], 0Fh
0x14000f09b  mov     [rax+18h], r13d
0x14000f09f  mov     [rax+40h], r12
0x14000f0a3  mov     [rcx+rdi*8+778h], rax
0x14000f0ab  mov     edi, 68h ; 'h'
0x14000f0b0  mov     r8d, edi; Size
0x14000f0b3  mov     rcx, r15; void *
0x14000f0b6  call    memset
0x14000f0bb  mov     rax, [rbp+57h+DeviceObject]
0x14000f0bf  mov     [r15+8], rax
0x14000f0c3  mov     dword ptr [r15], 3
0x14000f0ca  mov     [r15+4], edi
0x14000f0ce  mov     byte ptr [r15+1Ch], 1
0x14000f0d3  mov     [r15+28h], r14
0x14000f0d7  mov     [r15+3Ch], r13d
0x14000f0db  cmp     byte ptr [r12+12Ch], 1
0x14000f0e4  jnz     short loc_14000F0EB
0x14000f0e6  or      dword ptr [r15+30h], 4
0x14000f0eb  xor     edx, edx; PriorityBoost
0x14000f0ed  mov     [rsi+38h], rdi
0x14000f0f1  mov     rcx, rsi; Irp
0x14000f0f4  mov     [rsi+30h], ebx
0x14000f0f7  call    cs:__imp_IofCompleteRequest
0x14000f0fe  nop     dword ptr [rax+rax+00h]
0x14000f103  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f10a  lea     rax, WPP_GLOBAL_Control
0x14000f111  cmp     rcx, rax
0x14000f114  jz      loc_14000F1C3
0x14000f11a  mov     eax, [rcx+2Ch]
0x14000f11d  test    al, 1
0x14000f11f  jz      loc_14000F1C3
0x14000f125  cmp     byte ptr [rcx+29h], 5
0x14000f129  jb      loc_14000F1C3
0x14000f12f  mov     rcx, [rcx+18h]
0x14000f133  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000f13a  mov     edx, 0CFh
0x14000f13f  mov     r9d, ebx
0x14000f142  call    WPP_SF_d
0x14000f147  jmp     short loc_14000F1C3
0x14000f149  mov     ebx, 0C000009Ah
0x14000f14e  xor     edx, edx; Tag
0x14000f150  mov     rcx, r12; P
0x14000f153  call    cs:__imp_ExFreePoolWithTag
0x14000f15a  nop     dword ptr [rax+rax+00h]
0x14000f15f  mov     rax, [rbp+57h+arg_8]
0x14000f163  mov     qword ptr [rax+rdi*8+768h], 0
0x14000f16f  test    r13, r13
0x14000f172  jz      short loc_14000F183
0x14000f174  mov     rcx, r13; Irp
0x14000f177  call    cs:__imp_IoFreeIrp
0x14000f17e  nop     dword ptr [rax+rax+00h]
0x14000f183  test    r14, r14
0x14000f186  jz      short loc_14000F1AF
0x14000f188  mov     rcx, [r14]; P
0x14000f18b  test    rcx, rcx
0x14000f18e  jz      short loc_14000F19E
0x14000f190  xor     edx, edx; Tag
0x14000f192  call    cs:__imp_ExFreePoolWithTag
0x14000f199  nop     dword ptr [rax+rax+00h]
0x14000f19e  xor     edx, edx; Tag
0x14000f1a0  mov     rcx, r14; P
0x14000f1a3  call    cs:__imp_ExFreePoolWithTag
0x14000f1aa  nop     dword ptr [rax+rax+00h]
0x14000f1af  xor     edx, edx; PriorityBoost
0x14000f1b1  mov     [rsi+30h], ebx
0x14000f1b4  mov     rcx, rsi; Irp
0x14000f1b7  call    cs:__imp_IofCompleteRequest
0x14000f1be  nop     dword ptr [rax+rax+00h]
0x14000f1c3  mov     eax, ebx
0x14000f1c5  mov     rbx, [rsp+0C0h+arg_10]
0x14000f1cd  add     rsp, 90h
0x14000f1d4  pop     r15
0x14000f1d6  pop     r14
0x14000f1d8  pop     r13
0x14000f1da  pop     r12
0x14000f1dc  pop     rdi
0x14000f1dd  pop     rsi
0x14000f1de  pop     rbp
0x14000f1df  retn
```
