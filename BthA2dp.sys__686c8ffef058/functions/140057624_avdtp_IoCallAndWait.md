# avdtp_IoCallAndWait

- ea: `0x140057624`
- end: `0x1400576ef`
- name: `avdtp_IoCallAndWait`
- size: `203`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT, PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400576f8`

## callees

- `0x140057624`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400576ad`
- `ntoskrnl!IofCallDriver` at `0x1400576ad`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14005767f`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14005767f`
- `ntoskrnl!KeInitializeEvent` at `0x14005764f`
- `ntoskrnl!KeInitializeEvent` at `0x14005764f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400576d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400576d6`

## pseudocode

```c
__int64 __fastcall avdtp_IoCallAndWait(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT a2, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( IoSetCompletionRoutineEx(DeviceObject, Irp, OnRequestComplete, &Event, 1u, 1u, 1u) < 0 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = OnRequestComplete;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
  }
  if ( IofCallDriver(a2, Irp) == 259 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  return (unsigned int)Irp->IoStatus.Status;
}

```

## disassembly

```asm
0x140057624  push    rbx
0x140057626  push    rbp
0x140057627  push    rsi
0x140057628  push    rdi
0x140057629  sub     rsp, 68h
0x14005762d  mov     rdi, r8
0x140057630  mov     rsi, rdx
0x140057633  mov     rbx, rcx
0x140057636  xorps   xmm0, xmm0
0x140057639  xor     eax, eax
0x14005763b  lea     rcx, [rsp+88h+Event]; Event
0x140057640  xor     r8d, r8d; State
0x140057643  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140057648  xor     edx, edx; Type
0x14005764a  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14005764f  call    cs:__imp_KeInitializeEvent
0x140057656  nop     dword ptr [rax+rax+00h]
0x14005765b  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x140057660  lea     rbp, ?OnRequestComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; OnRequestComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x140057667  mov     r8, rbp; CompletionRoutine
0x14005766a  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14005766f  lea     r9, [rsp+88h+Event]; Context
0x140057674  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140057679  mov     rdx, rdi; Irp
0x14005767c  mov     rcx, rbx; DeviceObject
0x14005767f  call    cs:__imp_IoSetCompletionRoutineEx
0x140057686  nop     dword ptr [rax+rax+00h]
0x14005768b  test    eax, eax
0x14005768d  jns     short loc_1400576A7
0x14005768f  mov     rax, [rdi+0B8h]
0x140057696  lea     rcx, [rsp+88h+Event]
0x14005769b  mov     [rax-10h], rbp
0x14005769f  mov     [rax-8], rcx
0x1400576a3  mov     byte ptr [rax-45h], 0E0h
0x1400576a7  mov     rdx, rdi; Irp
0x1400576aa  mov     rcx, rsi; DeviceObject
0x1400576ad  call    cs:__imp_IofCallDriver
0x1400576b4  nop     dword ptr [rax+rax+00h]
0x1400576b9  cmp     eax, 103h
0x1400576be  jnz     short loc_1400576E2
0x1400576c0  xor     r9d, r9d; Alertable
0x1400576c3  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x1400576cc  xor     r8d, r8d; WaitMode
0x1400576cf  lea     rcx, [rsp+88h+Event]; Object
0x1400576d4  xor     edx, edx; WaitReason
0x1400576d6  call    cs:__imp_KeWaitForSingleObject
0x1400576dd  nop     dword ptr [rax+rax+00h]
0x1400576e2  mov     eax, [rdi+30h]
0x1400576e5  add     rsp, 68h
0x1400576e9  pop     rdi
0x1400576ea  pop     rsi
0x1400576eb  pop     rbp
0x1400576ec  pop     rbx
0x1400576ed  retn
```
