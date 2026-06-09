# USBSTOR_MediaChangeNotifyWorkItem

- ea: `0x140011fb0`
- end: `0x140012312`
- name: `USBSTOR_MediaChangeNotifyWorkItem`
- size: `866`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140011fb0`
- `0x140013950`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001227b`
- `ntoskrnl!IoFreeIrp` at `0x14001227b`
- `ntoskrnl!IofCallDriver` at `0x140012227`
- `ntoskrnl!IofCallDriver` at `0x140012227`
- `ntoskrnl!KeInitializeEvent` at `0x1400121c5`
- `ntoskrnl!KeInitializeEvent` at `0x1400121c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012253`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012253`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400122df`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400122df`
- `ntoskrnl!ObfDereferenceObject` at `0x140012267`
- `ntoskrnl!ObfDereferenceObject` at `0x140012267`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012189`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012189`
- `ntoskrnl!IoAllocateIrp` at `0x1400121a1`
- `ntoskrnl!IoAllocateIrp` at `0x1400121a1`

## pseudocode

```c
void __fastcall USBSTOR_MediaChangeNotifyWorkItem(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  NTSTATUS v4; // r15d
  __int64 v5; // rdi
  unsigned __int8 v6; // bl
  _QWORD *v7; // rsi
  _QWORD *i; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edx
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rbp
  PIRP Irp; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v16; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF
  __int128 v18; // [rsp+48h] [rbp-40h] BYREF

  v4 = -1073741811;
  v18 = 0;
  memset(&Event, 0, sizeof(Event));
  USBSTOR_LogEntry(1464746829, IoObject, 0, 0);
  v5 = IoObject[8];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  if ( (*(_DWORD *)(v5 + 132) & 0x800) != 0 )
  {
    v6 = 0;
    goto LABEL_7;
  }
  if ( (*(_BYTE *)(v5 + 661) & 0xF0) != 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    v9 = 810435405;
    v10 = (unsigned __int64)*(unsigned __int8 *)(v5 + 661) >> 4;
LABEL_14:
    v11 = 0;
    goto LABEL_15;
  }
  v12 = *(unsigned __int8 *)(v5 + 1864);
  v6 = *(_BYTE *)(v5 + 661) & 0xF;
  if ( v6 > (unsigned __int8)v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, v6, v12);
    }
    v11 = *(unsigned __int8 *)(v5 + 1864);
    v9 = 827212621;
    v10 = v6;
LABEL_15:
    USBSTOR_LogEntry(v9, IoObject, v10, v11);
    goto LABEL_38;
  }
LABEL_7:
  v7 = 0;
  for ( i = *(_QWORD **)(v5 + 32); i != (_QWORD *)(v5 + 32); i = (_QWORD *)*i )
  {
    v7 = i - 3;
    if ( v6 == *((_BYTE *)i + 47) )
      goto LABEL_31;
  }
  if ( v6 != *((_BYTE *)v7 + 71) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    v10 = v6;
    v9 = 843989837;
    goto LABEL_14;
  }
LABEL_31:
  *((_QWORD *)&v18 + 1) |= 1uLL;
  *(_QWORD *)&v18 = 0x1000000001LL;
  AttachedDeviceReference = IoGetAttachedDeviceReference((PDEVICE_OBJECT)v7[1]);
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v5 + 24) + 76LL), 0);
  if ( Irp )
  {
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].DeviceObject = (PDEVICE_OBJECT)v7[1];
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2956432;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = 16;
    Irp->AssociatedIrp.MasterIrp = (struct _IRP *)&v18;
    v16 = Irp->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = USBSTOR_SyncCompletionRoutine;
    v16[-1].Context = &Event;
    v16[-1].Control = -32;
    v4 = IofCallDriver(AttachedDeviceReference, Irp);
    if ( v4 == 259 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  if ( AttachedDeviceReference )
    ObfDereferenceObject(AttachedDeviceReference);
  if ( Irp )
    IoFreeIrp(Irp);
LABEL_38:
  USBSTOR_LogEntry(2003723117, IoObject, v4, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 1832), USBSTOR_MediaChangeNotifyWorkItem, 0x20u);
}

```

## disassembly

```asm
0x140011fb0  mov     [rsp+arg_8], rbx
0x140011fb5  mov     [rsp+arg_10], rbp
0x140011fba  push    rsi
0x140011fbb  push    rdi
0x140011fbc  push    r13
0x140011fbe  push    r14
0x140011fc0  push    r15
0x140011fc2  sub     rsp, 60h
0x140011fc6  mov     rax, cs:__security_cookie
0x140011fcd  xor     rax, rsp
0x140011fd0  mov     [rsp+88h+var_30], rax
0x140011fd5  mov     r14, rcx
0x140011fd8  xorps   xmm0, xmm0
0x140011fdb  xorps   xmm1, xmm1
0x140011fde  xor     eax, eax
0x140011fe0  mov     rdx, rcx
0x140011fe3  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140011fe8  mov     ecx, 574E434Dh
0x140011fed  xor     r9d, r9d
0x140011ff0  xor     r8d, r8d
0x140011ff3  mov     r15d, 0C000000Dh
0x140011ff9  movups  [rsp+88h+var_40], xmm0
0x140011ffe  movups  xmmword ptr [rsp+88h+Event.Header], xmm1
0x140012003  call    USBSTOR_LogEntry
0x140012008  mov     rdi, [r14+40h]
0x14001200c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012013  lea     r8, WPP_GLOBAL_Control
0x14001201a  lea     r13, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140012021  cmp     rcx, r8
0x140012024  jz      short loc_14001204B
0x140012026  mov     eax, [rcx+2Ch]
0x140012029  test    al, 1
0x14001202b  jz      short loc_14001204B
0x14001202d  cmp     byte ptr [rcx+29h], 5
0x140012031  jb      short loc_14001204B
0x140012033  mov     rcx, [rcx+18h]
0x140012037  mov     edx, 89h
0x14001203c  mov     r8, r13
0x14001203f  call    WPP_SF_
0x140012044  lea     r8, WPP_GLOBAL_Control
0x14001204b  test    dword ptr [rdi+84h], 800h
0x140012055  jz      short loc_140012067
0x140012057  xor     bl, bl
0x140012059  lea     rcx, [rdi+20h]
0x14001205d  xor     esi, esi
0x14001205f  mov     rax, [rcx]
0x140012062  jmp     loc_140012129
0x140012067  movzx   ebx, byte ptr [rdi+295h]
0x14001206e  mov     al, bl
0x140012070  and     al, 0F0h
0x140012072  cmp     al, 10h
0x140012074  jz      short loc_1400120C8
0x140012076  mov     rcx, cs:WPP_GLOBAL_Control
0x14001207d  cmp     rcx, r8
0x140012080  jz      short loc_1400120A7
0x140012082  mov     eax, [rcx+2Ch]
0x140012085  test    al, 1
0x140012087  jz      short loc_1400120A7
0x140012089  cmp     byte ptr [rcx+29h], 2
0x14001208d  jb      short loc_1400120A7
0x14001208f  mov     rcx, [rcx+18h]
0x140012093  mov     r9d, ebx
0x140012096  shr     r9d, 4
0x14001209a  mov     edx, 8Ah
0x14001209f  mov     r8, r13
0x1400120a2  call    WPP_SF_d
0x1400120a7  movzx   r8d, byte ptr [rdi+295h]
0x1400120af  mov     ecx, 304E434Dh
0x1400120b4  shr     r8, 4
0x1400120b8  xor     r9d, r9d
0x1400120bb  mov     rdx, r14
0x1400120be  call    USBSTOR_LogEntry
0x1400120c3  jmp     loc_140012287
0x1400120c8  movzx   edx, byte ptr [rdi+748h]
0x1400120cf  and     bl, 0Fh
0x1400120d2  cmp     bl, dl
0x1400120d4  jbe     short loc_140012059
0x1400120d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120dd  cmp     rcx, r8
0x1400120e0  jz      short loc_14001210A
0x1400120e2  mov     eax, [rcx+2Ch]
0x1400120e5  test    al, 1
0x1400120e7  jz      short loc_14001210A
0x1400120e9  cmp     byte ptr [rcx+29h], 2
0x1400120ed  jb      short loc_14001210A
0x1400120ef  mov     rcx, [rcx+18h]
0x1400120f3  mov     eax, edx
0x1400120f5  mov     edx, 8Bh
0x1400120fa  movzx   r9d, bl
0x1400120fe  mov     r8, r13
0x140012101  mov     dword ptr [rsp+88h+Timeout], eax
0x140012105  call    WPP_SF_DD
0x14001210a  movzx   r9d, byte ptr [rdi+748h]
0x140012112  mov     ecx, 314E434Dh
0x140012117  movzx   r8d, bl
0x14001211b  jmp     short loc_1400120BB
0x14001211d  lea     rsi, [rax-18h]
0x140012121  cmp     bl, [rsi+47h]
0x140012124  jz      short loc_14001216F
0x140012126  mov     rax, [rax]
0x140012129  cmp     rax, rcx
0x14001212c  jnz     short loc_14001211D
0x14001212e  cmp     bl, [rsi+47h]
0x140012131  jz      short loc_14001216F
0x140012133  mov     rcx, cs:WPP_GLOBAL_Control
0x14001213a  cmp     rcx, r8
0x14001213d  jz      short loc_140012161
0x14001213f  mov     eax, [rcx+2Ch]
0x140012142  test    al, 1
0x140012144  jz      short loc_140012161
0x140012146  cmp     byte ptr [rcx+29h], 2
0x14001214a  jb      short loc_140012161
0x14001214c  mov     rcx, [rcx+18h]
0x140012150  mov     edx, 8Ch
0x140012155  movzx   r9d, bl
0x140012159  mov     r8, r13
0x14001215c  call    WPP_SF_d
0x140012161  movzx   r8d, bl
0x140012165  mov     ecx, 324E434Dh
0x14001216a  jmp     loc_1400120B8
0x14001216f  or      qword ptr [rsp+88h+var_40+8], 1
0x140012175  mov     dword ptr [rsp+88h+var_40], 1
0x14001217d  mov     dword ptr [rsp+88h+var_40+4], 10h
0x140012185  mov     rcx, [rsi+8]; DeviceObject
0x140012189  call    cs:__imp_IoGetAttachedDeviceReference
0x140012190  nop     dword ptr [rax+rax+00h]
0x140012195  mov     rcx, [rdi+18h]
0x140012199  xor     edx, edx; ChargeQuota
0x14001219b  mov     rbp, rax
0x14001219e  mov     cl, [rcx+4Ch]; StackSize
0x1400121a1  call    cs:__imp_IoAllocateIrp
0x1400121a8  nop     dword ptr [rax+rax+00h]
0x1400121ad  mov     rbx, rax
0x1400121b0  test    rax, rax
0x1400121b3  jz      loc_14001225F
0x1400121b9  xor     r8d, r8d; State
0x1400121bc  lea     rcx, [rsp+88h+Event]; Event
0x1400121c1  lea     edx, [r8+1]; Type
0x1400121c5  call    cs:__imp_KeInitializeEvent
0x1400121cc  nop     dword ptr [rax+rax+00h]
0x1400121d1  mov     rcx, [rbx+0B8h]
0x1400121d8  mov     rdx, rbx; Irp
0x1400121db  mov     byte ptr [rcx-48h], 0Eh
0x1400121df  mov     rax, [rsi+8]
0x1400121e3  mov     [rcx-20h], rax
0x1400121e7  lea     rax, [rsp+88h+var_40]
0x1400121ec  mov     dword ptr [rcx-30h], 2D1C90h
0x1400121f3  mov     dword ptr [rcx-40h], 0
0x1400121fa  mov     dword ptr [rcx-38h], 10h
0x140012201  lea     rcx, USBSTOR_SyncCompletionRoutine
0x140012208  mov     [rbx+18h], rax
0x14001220c  mov     rax, [rbx+0B8h]
0x140012213  mov     [rax-10h], rcx
0x140012217  lea     rcx, [rsp+88h+Event]
0x14001221c  mov     [rax-8], rcx
0x140012220  mov     rcx, rbp; DeviceObject
0x140012223  mov     byte ptr [rax-45h], 0E0h
0x140012227  call    cs:__imp_IofCallDriver
0x14001222e  nop     dword ptr [rax+rax+00h]
0x140012233  mov     r15d, eax
0x140012236  cmp     eax, 103h
0x14001223b  jnz     short loc_14001225F
0x14001223d  xor     r9d, r9d; Alertable
0x140012240  mov     [rsp+88h+Timeout], 0; Timeout
0x140012249  xor     r8d, r8d; WaitMode
0x14001224c  lea     rcx, [rsp+88h+Event]; Object
0x140012251  xor     edx, edx; WaitReason
0x140012253  call    cs:__imp_KeWaitForSingleObject
0x14001225a  nop     dword ptr [rax+rax+00h]
0x14001225f  test    rbp, rbp
0x140012262  jz      short loc_140012273
0x140012264  mov     rcx, rbp; Object
0x140012267  call    cs:__imp_ObfDereferenceObject
0x14001226e  nop     dword ptr [rax+rax+00h]
0x140012273  test    rbx, rbx
0x140012276  jz      short loc_140012287
0x140012278  mov     rcx, rbx; Irp
0x14001227b  call    cs:__imp_IoFreeIrp
0x140012282  nop     dword ptr [rax+rax+00h]
0x140012287  movsxd  r8, r15d
0x14001228a  xor     r9d, r9d
0x14001228d  mov     rdx, r14
0x140012290  mov     ecx, 776E636Dh
0x140012295  call    USBSTOR_LogEntry
0x14001229a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122a1  lea     rax, WPP_GLOBAL_Control
0x1400122a8  cmp     rcx, rax
0x1400122ab  jz      short loc_1400122CB
0x1400122ad  mov     eax, [rcx+2Ch]
0x1400122b0  test    al, 1
0x1400122b2  jz      short loc_1400122CB
0x1400122b4  cmp     byte ptr [rcx+29h], 5
0x1400122b8  jb      short loc_1400122CB
0x1400122ba  mov     rcx, [rcx+18h]
0x1400122be  mov     edx, 8Dh
0x1400122c3  mov     r8, r13
0x1400122c6  call    WPP_SF_
0x1400122cb  lea     rcx, [rdi+728h]; RemoveLock
0x1400122d2  mov     r8d, 20h ; ' '; RemlockSize
0x1400122d8  lea     rdx, USBSTOR_MediaChangeNotifyWorkItem; Tag
0x1400122df  call    cs:__imp_IoReleaseRemoveLockEx
0x1400122e6  nop     dword ptr [rax+rax+00h]
0x1400122eb  mov     rcx, [rsp+88h+var_30]
0x1400122f0  xor     rcx, rsp; StackCookie
0x1400122f3  call    __security_check_cookie
0x1400122f8  lea     r11, [rsp+88h+var_28]
0x1400122fd  mov     rbx, [r11+38h]
0x140012301  mov     rbp, [r11+40h]
0x140012305  mov     rsp, r11
0x140012308  pop     r15
0x14001230a  pop     r14
0x14001230c  pop     r13
0x14001230e  pop     rdi
0x14001230f  pop     rsi
0x140012310  retn
```
