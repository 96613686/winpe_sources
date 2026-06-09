# USBSTOR_IsDeviceConnected

- ea: `0x14000a08c`
- end: `0x14000a208`
- name: `USBSTOR_IsDeviceConnected`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400090e0`
- `0x14002877c`

## callees

- `0x14000a08c`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000a1a7`
- `ntoskrnl!IoFreeIrp` at `0x14000a1a7`
- `ntoskrnl!IofCallDriver` at `0x14000a16a`
- `ntoskrnl!IofCallDriver` at `0x14000a16a`
- `ntoskrnl!KeInitializeEvent` at `0x14000a11d`
- `ntoskrnl!KeInitializeEvent` at `0x14000a11d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a195`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a195`
- `ntoskrnl!IoAllocateIrp` at `0x14000a0f3`
- `ntoskrnl!IoAllocateIrp` at `0x14000a0f3`

## pseudocode

```c
__int64 __fastcall USBSTOR_IsDeviceConnected(__int64 a1)
{
  __int64 v2; // rbx
  PIRP Irp; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v6; // rax
  NTSTATUS Status; // ebx
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+60h] [rbp+8h] BYREF

  memset(&Event, 0, sizeof(Event));
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xB4u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v2 = *(_QWORD *)(a1 + 64);
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(v2 + 24) + 76LL), 0);
  if ( !Irp )
    return 3221225626LL;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)&v9;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228243;
  v6 = Irp->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_SyncCompletionRoutine;
  v6[-1].Context = &Event;
  v6[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 24), Irp);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = Irp->IoStatus.Status;
  }
  IoFreeIrp(Irp);
  if ( Status >= 0 && (v9 & 2) == 0 )
    Status = -1073741632;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xB5u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000a08c  mov     [rsp+arg_8], rbx
0x14000a091  mov     [rsp+arg_10], rsi
0x14000a096  push    rdi
0x14000a097  sub     rsp, 50h
0x14000a09b  xor     eax, eax
0x14000a09d  xorps   xmm0, xmm0
0x14000a0a0  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x14000a0a5  mov     [rsp+58h+Event.Header.WaitListHead.Blink], rax
0x14000a0aa  mov     rbx, rcx
0x14000a0ad  mov     [rsp+58h+arg_0], eax
0x14000a0b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0b8  lea     rsi, WPP_GLOBAL_Control
0x14000a0bf  cmp     rcx, rsi
0x14000a0c2  jz      short loc_14000A0E6
0x14000a0c4  mov     eax, [rcx+2Ch]
0x14000a0c7  test    al, 1
0x14000a0c9  jz      short loc_14000A0E6
0x14000a0cb  cmp     byte ptr [rcx+29h], 5
0x14000a0cf  jb      short loc_14000A0E6
0x14000a0d1  mov     rcx, [rcx+18h]
0x14000a0d5  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000a0dc  mov     edx, 0B4h
0x14000a0e1  call    WPP_SF_
0x14000a0e6  mov     rbx, [rbx+40h]
0x14000a0ea  xor     edx, edx; ChargeQuota
0x14000a0ec  mov     rcx, [rbx+18h]
0x14000a0f0  mov     cl, [rcx+4Ch]; StackSize
0x14000a0f3  call    cs:__imp_IoAllocateIrp
0x14000a0fa  nop     dword ptr [rax+rax+00h]
0x14000a0ff  mov     rdi, rax
0x14000a102  test    rax, rax
0x14000a105  jnz     short loc_14000A111
0x14000a107  mov     eax, 0C000009Ah
0x14000a10c  jmp     loc_14000A1F7
0x14000a111  xor     r8d, r8d; State
0x14000a114  lea     rcx, [rsp+58h+Event]; Event
0x14000a119  lea     edx, [r8+1]; Type
0x14000a11d  call    cs:__imp_KeInitializeEvent
0x14000a124  nop     dword ptr [rax+rax+00h]
0x14000a129  mov     rax, [rdi+0B8h]
0x14000a130  lea     rcx, [rsp+58h+arg_0]
0x14000a135  mov     rdx, rdi; Irp
0x14000a138  mov     [rax-40h], rcx
0x14000a13c  lea     rcx, USBSTOR_SyncCompletionRoutine
0x14000a143  mov     byte ptr [rax-48h], 0Fh
0x14000a147  mov     dword ptr [rax-30h], 220013h
0x14000a14e  mov     rax, [rdi+0B8h]
0x14000a155  mov     [rax-10h], rcx
0x14000a159  lea     rcx, [rsp+58h+Event]
0x14000a15e  mov     [rax-8], rcx
0x14000a162  mov     byte ptr [rax-45h], 0E0h
0x14000a166  mov     rcx, [rbx+18h]; DeviceObject
0x14000a16a  call    cs:__imp_IofCallDriver
0x14000a171  nop     dword ptr [rax+rax+00h]
0x14000a176  mov     ebx, eax
0x14000a178  cmp     eax, 103h
0x14000a17d  jnz     short loc_14000A1A4
0x14000a17f  xor     r9d, r9d; Alertable
0x14000a182  mov     [rsp+58h+Timeout], 0; Timeout
0x14000a18b  xor     r8d, r8d; WaitMode
0x14000a18e  lea     rcx, [rsp+58h+Event]; Object
0x14000a193  xor     edx, edx; WaitReason
0x14000a195  call    cs:__imp_KeWaitForSingleObject
0x14000a19c  nop     dword ptr [rax+rax+00h]
0x14000a1a1  mov     ebx, [rdi+30h]
0x14000a1a4  mov     rcx, rdi; Irp
0x14000a1a7  call    cs:__imp_IoFreeIrp
0x14000a1ae  nop     dword ptr [rax+rax+00h]
0x14000a1b3  test    ebx, ebx
0x14000a1b5  js      short loc_14000A1C4
0x14000a1b7  test    byte ptr [rsp+58h+arg_0], 2
0x14000a1bc  mov     eax, 0C00000C0h
0x14000a1c1  cmovz   ebx, eax
0x14000a1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1cb  cmp     rcx, rsi
0x14000a1ce  jz      short loc_14000A1F5
0x14000a1d0  mov     eax, [rcx+2Ch]
0x14000a1d3  test    al, 1
0x14000a1d5  jz      short loc_14000A1F5
0x14000a1d7  cmp     byte ptr [rcx+29h], 5
0x14000a1db  jb      short loc_14000A1F5
0x14000a1dd  mov     rcx, [rcx+18h]
0x14000a1e1  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000a1e8  mov     edx, 0B5h
0x14000a1ed  mov     r9d, ebx
0x14000a1f0  call    WPP_SF_d
0x14000a1f5  mov     eax, ebx
0x14000a1f7  mov     rbx, [rsp+58h+arg_8]
0x14000a1fc  mov     rsi, [rsp+58h+arg_10]
0x14000a201  add     rsp, 50h
0x14000a205  pop     rdi
0x14000a206  retn
```
