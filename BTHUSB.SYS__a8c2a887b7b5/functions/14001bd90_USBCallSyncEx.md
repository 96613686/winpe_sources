# USBCallSyncEx

- ea: `0x14001bd90`
- end: `0x14001c09e`
- name: `USBCallSyncEx`
- size: `782`
- prototype: `__int64 __fastcall(PVOID Tag)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ae54`
- `0x1400179ac`
- `0x14001a4a8`
- `0x14001a6e8`
- `0x14001b73c`
- `0x14001b840`

## callees

- `0x14000c60c`
- `0x14001bd90`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14001be77`
- `ntoskrnl!IoAllocateIrp` at `0x14001be77`
- `ntoskrnl!IoFreeIrp` at `0x14001c04b`
- `ntoskrnl!IoFreeIrp` at `0x14001c71a`
- `ntoskrnl!IoFreeIrp` at `0x14001c04b`
- `ntoskrnl!IoFreeIrp` at `0x14001c71a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001c037`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001c704`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001c037`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001c704`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001be22`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001be22`
- `ntoskrnl!IofCallDriver` at `0x14001bf12`
- `ntoskrnl!IofCallDriver` at `0x14001bf12`
- `ntoskrnl!KeInitializeEvent` at `0x14001be66`
- `ntoskrnl!KeInitializeEvent` at `0x14001be66`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf56`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf97`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf56`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001bf97`
- `ntoskrnl!IoCancelIrp` at `0x14001bf79`
- `ntoskrnl!IoCancelIrp` at `0x14001bf79`

## pseudocode

```c
__int64 __fastcall USBCallSyncEx(struct _DEVICE_OBJECT *Tag, unsigned __int64 a2, int a3, struct _IO_REMOVE_LOCK *a4)
{
  __int64 v5; // r13
  IRP *v8; // rdi
  char v9; // r14
  __int64 v10; // rdx
  NTSTATUS Status; // ebx
  PIRP Irp; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v14; // rax
  union _LARGE_INTEGER Timeout; // [rsp+38h] [rbp-50h] BYREF
  PIRP v17; // [rsp+40h] [rbp-48h]
  struct _KEVENT Event; // [rsp+48h] [rbp-40h] BYREF

  v5 = a3;
  v8 = 0;
  v17 = 0;
  memset(&Event, 0, sizeof(Event));
  v9 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, 0, 7, 10);
  Status = IoAcquireRemoveLockEx(
             a4,
             Tag,
             "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusbutil\\usbutil.c",
             0x64u,
             0x20u);
  if ( Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, v10, 4, 11);
  }
  else
  {
    v9 = 1;
    if ( Tag && a2 )
    {
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      Irp = IoAllocateIrp(Tag->StackSize, 0);
      v8 = Irp;
      v17 = Irp;
      if ( Irp )
      {
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
        CurrentStackLocation[-1].Parameters.WMI.ProviderId = a2;
        v14 = v8->Tail.Overlay.CurrentStackLocation;
        v14[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&USBCallSyncCompletionRoutine;
        v14[-1].Context = &Event;
        v14[-1].Control = 0;
        v14[-1].Control = 64;
        v14[-1].Control = -64;
        v14[-1].Control = -32;
        Status = IofCallDriver(Tag, v8);
        if ( Status == 259 )
        {
          Timeout.QuadPart = -10000 * v5;
          if ( KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout) == 258 )
          {
            Status = -1073741643;
            IoCancelIrp(v8);
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          }
          else
          {
            Status = v8->IoStatus.Status;
          }
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, v10, 4, 13);
        Status = -1073741670;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, v10, 4, 12);
      Status = -1073741811;
    }
  }
  if ( v9 )
    IoReleaseRemoveLockEx(a4, Tag, 0x20u);
  if ( v8 )
    IoFreeIrp(v8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(WPP_GLOBAL_Control->DeviceExtension, v10, 7, 14);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14001bd90  mov     r11, rsp
0x14001bd93  mov     [r11+10h], rbx
0x14001bd97  mov     [r11+18h], rsi
0x14001bd9b  mov     [r11+20h], r9
0x14001bd9f  mov     [r11+8], rcx
0x14001bda3  push    rdi
0x14001bda4  push    r12
0x14001bda6  push    r13
0x14001bda8  push    r14
0x14001bdaa  push    r15
0x14001bdac  sub     rsp, 60h
0x14001bdb0  mov     r12, r9
0x14001bdb3  movsxd  r13, r8d
0x14001bdb6  mov     r15, rdx
0x14001bdb9  mov     rsi, rcx
0x14001bdbc  xor     edx, edx
0x14001bdbe  mov     edi, edx
0x14001bdc0  mov     [r11-48h], rdx
0x14001bdc4  xorps   xmm0, xmm0
0x14001bdc7  xor     eax, eax
0x14001bdc9  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14001bdce  mov     [r11-30h], rax
0x14001bdd2  mov     r14b, dl
0x14001bdd5  mov     [rsp+88h+var_58], dl
0x14001bdd9  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001bde0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001bde7  jz      short loc_14001BE07
0x14001bde9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdf0  cmp     [rcx+48h], dx
0x14001bdf4  jz      short loc_14001BE07
0x14001bdf6  lea     r9d, [rdx+0Ah]
0x14001bdfa  lea     r8d, [rdx+7]
0x14001bdfe  mov     rcx, [rcx+40h]
0x14001be02  call    WPP_RECORDER_SF_
0x14001be07  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x14001be0f  mov     r9d, 64h ; 'd'; Line
0x14001be15  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001be1c  mov     rdx, rsi; Tag
0x14001be1f  mov     rcx, r12; RemoveLock
0x14001be22  call    cs:__imp_IoAcquireRemoveLockEx
0x14001be29  nop     dword ptr [rax+rax+00h]
0x14001be2e  mov     ebx, eax
0x14001be30  mov     [rsp+88h+var_54], eax
0x14001be34  test    eax, eax
0x14001be36  js      loc_14001BFEF
0x14001be3c  mov     r14d, 1
0x14001be42  mov     [rsp+88h+var_58], r14b
0x14001be47  xor     ebx, ebx
0x14001be49  test    rsi, rsi
0x14001be4c  jz      loc_14001BFB5
0x14001be52  test    r15, r15
0x14001be55  jz      loc_14001BFB5
0x14001be5b  xor     r8d, r8d; State
0x14001be5e  mov     edx, r14d; Type
0x14001be61  lea     rcx, [rsp+88h+Event]; Event
0x14001be66  call    cs:__imp_KeInitializeEvent
0x14001be6d  nop     dword ptr [rax+rax+00h]
0x14001be72  xor     edx, edx; ChargeQuota
0x14001be74  mov     cl, [rsi+4Ch]; StackSize
0x14001be77  call    cs:__imp_IoAllocateIrp
0x14001be7e  nop     dword ptr [rax+rax+00h]
0x14001be83  mov     rdi, rax
0x14001be86  mov     [rsp+88h+var_48], rax
0x14001be8b  test    rax, rax
0x14001be8e  jnz     short loc_14001BECC
0x14001be90  lea     r13, WPP_RECORDER_INITIALIZED
0x14001be97  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001be9e  jz      short loc_14001BEBE
0x14001bea0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bea7  cmp     [rcx+48h], bx
0x14001beab  jz      short loc_14001BEBE
0x14001bead  lea     r9d, [r14+0Ch]
0x14001beb1  lea     r8d, [r14+3]
0x14001beb5  mov     rcx, [rcx+40h]
0x14001beb9  call    WPP_RECORDER_SF_
0x14001bebe  mov     ebx, 0C000009Ah
0x14001bec3  mov     [rsp+88h+var_54], ebx
0x14001bec7  jmp     loc_14001C023
0x14001becc  mov     rax, [rax+0B8h]
0x14001bed3  mov     byte ptr [rax-48h], 0Fh
0x14001bed7  mov     dword ptr [rax-30h], 220003h
0x14001bede  mov     [rax-40h], r15
0x14001bee2  mov     rax, [rdi+0B8h]
0x14001bee9  lea     rcx, USBCallSyncCompletionRoutine
0x14001bef0  mov     [rax-10h], rcx
0x14001bef4  lea     rcx, [rsp+88h+Event]
0x14001bef9  mov     [rax-8], rcx
0x14001befd  mov     [rax-45h], bl
0x14001bf00  mov     byte ptr [rax-45h], 40h ; '@'
0x14001bf04  mov     byte ptr [rax-45h], 0C0h
0x14001bf08  mov     byte ptr [rax-45h], 0E0h
0x14001bf0c  mov     rdx, rdi; Irp
0x14001bf0f  mov     rcx, rsi; DeviceObject
0x14001bf12  call    cs:__imp_IofCallDriver
0x14001bf19  nop     dword ptr [rax+rax+00h]
0x14001bf1e  mov     ebx, eax
0x14001bf20  mov     [rsp+88h+var_54], eax
0x14001bf24  xor     r15d, r15d
0x14001bf27  cmp     eax, 103h
0x14001bf2c  jnz     short loc_14001BFAC
0x14001bf2e  mov     qword ptr [rsp+88h+Timeout], r15
0x14001bf33  imul    rcx, r13, 0FFFFFFFFFFFFD8F0h
0x14001bf3a  mov     qword ptr [rsp+88h+Timeout], rcx
0x14001bf3f  lea     rax, [rsp+88h+Timeout]
0x14001bf44  mov     qword ptr [rsp+88h+RemlockSize], rax; Timeout
0x14001bf49  xor     r9d, r9d; Alertable
0x14001bf4c  xor     r8d, r8d; WaitMode
0x14001bf4f  xor     edx, edx; WaitReason
0x14001bf51  lea     rcx, [rsp+88h+Event]; Object
0x14001bf56  call    cs:__imp_KeWaitForSingleObject
0x14001bf5d  nop     dword ptr [rax+rax+00h]
0x14001bf62  mov     [rsp+88h+var_54], eax
0x14001bf66  cmp     eax, 102h
0x14001bf6b  jnz     short loc_14001BFA5
0x14001bf6d  mov     ebx, 0C00000B5h
0x14001bf72  mov     [rsp+88h+var_54], ebx
0x14001bf76  mov     rcx, rdi; Irp
0x14001bf79  call    cs:__imp_IoCancelIrp
0x14001bf80  nop     dword ptr [rax+rax+00h]
0x14001bf85  mov     qword ptr [rsp+88h+RemlockSize], r15; Timeout
0x14001bf8a  xor     r9d, r9d; Alertable
0x14001bf8d  xor     r8d, r8d; WaitMode
0x14001bf90  xor     edx, edx; WaitReason
0x14001bf92  lea     rcx, [rsp+88h+Event]; Object
0x14001bf97  call    cs:__imp_KeWaitForSingleObject
0x14001bf9e  nop     dword ptr [rax+rax+00h]
0x14001bfa3  jmp     short loc_14001BFAC
0x14001bfa5  mov     ebx, [rdi+30h]
0x14001bfa8  mov     [rsp+88h+var_54], ebx
0x14001bfac  lea     r13, WPP_RECORDER_INITIALIZED
0x14001bfb3  jmp     short loc_14001C026
0x14001bfb5  lea     r13, WPP_RECORDER_INITIALIZED
0x14001bfbc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bfc3  jz      short loc_14001BFE5
0x14001bfc5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfcc  cmp     [rcx+48h], bx
0x14001bfd0  jz      short loc_14001BFE5
0x14001bfd2  mov     r9d, 0Ch
0x14001bfd8  lea     r8d, [r9-8]
0x14001bfdc  mov     rcx, [rcx+40h]
0x14001bfe0  call    WPP_RECORDER_SF_
0x14001bfe5  mov     ebx, 0C000000Dh
0x14001bfea  jmp     loc_14001BEC3
0x14001bfef  lea     r13, WPP_RECORDER_INITIALIZED
0x14001bff6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001bffd  jz      short loc_14001C023
0x14001bfff  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c006  xor     r15d, r15d
0x14001c009  cmp     [rcx+48h], r15w
0x14001c00e  jz      short loc_14001C026
0x14001c010  lea     r9d, [r15+0Bh]
0x14001c014  lea     r8d, [r15+4]
0x14001c018  mov     rcx, [rcx+40h]
0x14001c01c  call    WPP_RECORDER_SF_
0x14001c021  jmp     short loc_14001C026
0x14001c023  xor     r15d, r15d
0x14001c026  test    r14b, r14b
0x14001c029  jz      short loc_14001C043
0x14001c02b  mov     r8d, 20h ; ' '; RemlockSize
0x14001c031  mov     rdx, rsi; Tag
0x14001c034  mov     rcx, r12; RemoveLock
0x14001c037  call    cs:__imp_IoReleaseRemoveLockEx
0x14001c03e  nop     dword ptr [rax+rax+00h]
0x14001c043  test    rdi, rdi
0x14001c046  jz      short loc_14001C057
0x14001c048  mov     rcx, rdi; Irp
0x14001c04b  call    cs:__imp_IoFreeIrp
0x14001c052  nop     dword ptr [rax+rax+00h]
0x14001c057  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001c05e  jz      short loc_14001C081
0x14001c060  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c067  cmp     [rcx+48h], r15w
0x14001c06c  jz      short loc_14001C081
0x14001c06e  mov     r9d, 0Eh
0x14001c074  lea     r8d, [r9-7]
0x14001c078  mov     rcx, [rcx+40h]
0x14001c07c  call    WPP_RECORDER_SF_
0x14001c081  mov     eax, ebx
0x14001c083  lea     r11, [rsp+88h+var_28]
0x14001c088  mov     rbx, [r11+38h]
0x14001c08c  mov     rsi, [r11+40h]
0x14001c090  mov     rsp, r11
0x14001c093  pop     r15
0x14001c095  pop     r14
0x14001c097  pop     r13
0x14001c099  pop     r12
0x14001c09b  pop     rdi
0x14001c09c  retn
0x14001c6e1  push    rbp
0x14001c6e3  sub     rsp, 30h
0x14001c6e7  mov     rbp, rdx
0x14001c6ea  cmp     byte ptr [rbp+30h], 0
0x14001c6ee  jz      short loc_14001C711
0x14001c6f0  mov     r8d, 20h ; ' '; RemlockSize
0x14001c6f6  mov     rdx, [rbp+90h]; Tag
0x14001c6fd  mov     rcx, [rbp+0A8h]; RemoveLock
0x14001c704  call    cs:__imp_IoReleaseRemoveLockEx
0x14001c70b  nop     dword ptr [rax+rax+00h]
0x14001c710  nop
0x14001c711  mov     rcx, [rbp+40h]; Irp
0x14001c715  test    rcx, rcx
0x14001c718  jz      short loc_14001C727
0x14001c71a  call    cs:__imp_IoFreeIrp
0x14001c721  nop     dword ptr [rax+rax+00h]
0x14001c726  nop
0x14001c727  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001c72e  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x14001c735  cmp     rax, rcx
0x14001c738  jz      short loc_14001C75C
0x14001c73a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c741  cmp     word ptr [rcx+48h], 0
0x14001c746  jz      short loc_14001C75C
0x14001c748  mov     r9d, 0Eh
0x14001c74e  lea     r8d, [r9-7]
0x14001c752  mov     rcx, [rcx+40h]
0x14001c756  call    WPP_RECORDER_SF_
0x14001c75b  nop
0x14001c75c  add     rsp, 30h
0x14001c760  pop     rbp
0x14001c761  retn
```
