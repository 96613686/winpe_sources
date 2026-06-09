# DepFSSendIoctl

- ea: `0x18000f5f8`
- end: `0x18000f734`
- name: `DepFSSendIoctl`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb48`
- `0x18000e88c`
- `0x18000fc50`

## callees

- `0x18000f5f8`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18000f620`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18000f620`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f714`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f714`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000f6d0`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000f6d0`
- `ntoskrnl!KeInitializeEvent` at `0x18000f639`
- `ntoskrnl!KeInitializeEvent` at `0x18000f639`
- `ntoskrnl!IofCallDriver` at `0x18000f6a5`
- `ntoskrnl!IofCallDriver` at `0x18000f6a5`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000f687`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x18000f687`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f708`
- `ntoskrnl!ObfDereferenceObject` at `0x18000f708`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000f6f9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000f6f9`

## pseudocode

```c
__int64 __fastcall DepFSSendIoctl(
        struct _DEVICE_OBJECT *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        _DWORD *a7)
{
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rdi
  IRP *v9; // rax
  unsigned int Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  AttachedDeviceReference = IoGetAttachedDeviceReference(a1);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = IoBuildDeviceIoControlRequest(
         0x2D118Cu,
         AttachedDeviceReference,
         a3,
         4u,
         OutputBuffer,
         OutputBufferLength,
         0,
         &Event,
         &IoStatusBlock);
  if ( v9 )
  {
    Status = IofCallDriver(AttachedDeviceReference, v9);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( IoStatusBlock.Information )
      *a7 = IoStatusBlock.Information;
  }
  else
  {
    Status = -1073741670;
  }
  if ( AttachedDeviceReference )
  {
    KeEnterCriticalRegion();
    ObfDereferenceObject(AttachedDeviceReference);
    KeLeaveCriticalRegion();
  }
  return Status;
}

```

## disassembly

```asm
0x18000f5f8  mov     r11, rsp
0x18000f5fb  mov     [r11+8], rbx
0x18000f5ff  push    rdi
0x18000f600  sub     rsp, 80h
0x18000f607  xor     eax, eax
0x18000f609  xorps   xmm0, xmm0
0x18000f60c  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x18000f611  mov     [r11-18h], rax
0x18000f615  mov     rbx, r8
0x18000f618  mov     [r11-38h], rax
0x18000f61c  mov     [r11-30h], rax
0x18000f620  call    cs:__imp_IoGetAttachedDeviceReference
0x18000f627  nop     dword ptr [rax+rax+00h]
0x18000f62c  xor     r8d, r8d; State
0x18000f62f  lea     rcx, [rsp+88h+Event]; Event
0x18000f634  xor     edx, edx; Type
0x18000f636  mov     rdi, rax
0x18000f639  call    cs:__imp_KeInitializeEvent
0x18000f640  nop     dword ptr [rax+rax+00h]
0x18000f645  mov     ecx, [rsp+88h+arg_28]
0x18000f64c  lea     rax, [rsp+88h+var_38]
0x18000f651  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x18000f656  mov     r9d, 4; InputBufferLength
0x18000f65c  lea     rax, [rsp+88h+Event]
0x18000f661  mov     r8, rbx; InputBuffer
0x18000f664  mov     [rsp+88h+var_50], rax; Event
0x18000f669  mov     rdx, rdi; DeviceObject
0x18000f66c  mov     [rsp+88h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x18000f671  mov     [rsp+88h+OutputBufferLength], ecx; OutputBufferLength
0x18000f675  mov     rcx, [rsp+88h+arg_20]
0x18000f67d  mov     [rsp+88h+OutputBuffer], rcx; OutputBuffer
0x18000f682  mov     ecx, 2D118Ch; IoControlCode
0x18000f687  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000f68e  nop     dword ptr [rax+rax+00h]
0x18000f693  test    rax, rax
0x18000f696  jnz     short loc_18000F69F
0x18000f698  mov     ebx, 0C000009Ah
0x18000f69d  jmp     short loc_18000F6F4
0x18000f69f  mov     rdx, rax; Irp
0x18000f6a2  mov     rcx, rdi; DeviceObject
0x18000f6a5  call    cs:__imp_IofCallDriver
0x18000f6ac  nop     dword ptr [rax+rax+00h]
0x18000f6b1  mov     ebx, eax
0x18000f6b3  cmp     eax, 103h
0x18000f6b8  jnz     short loc_18000F6E0
0x18000f6ba  xor     r9d, r9d; Alertable
0x18000f6bd  mov     [rsp+88h+OutputBuffer], 0; Timeout
0x18000f6c6  xor     r8d, r8d; WaitMode
0x18000f6c9  lea     rcx, [rsp+88h+Event]; Object
0x18000f6ce  xor     edx, edx; WaitReason
0x18000f6d0  call    cs:__imp_KeWaitForSingleObject
0x18000f6d7  nop     dword ptr [rax+rax+00h]
0x18000f6dc  mov     ebx, dword ptr [rsp+88h+var_38]
0x18000f6e0  mov     rcx, [rsp+88h+var_38.Information]
0x18000f6e5  test    rcx, rcx
0x18000f6e8  jz      short loc_18000F6F4
0x18000f6ea  mov     rax, [rsp+88h+arg_30]
0x18000f6f2  mov     [rax], ecx
0x18000f6f4  test    rdi, rdi
0x18000f6f7  jz      short loc_18000F720
0x18000f6f9  call    cs:__imp_KeEnterCriticalRegion
0x18000f700  nop     dword ptr [rax+rax+00h]
0x18000f705  mov     rcx, rdi; Object
0x18000f708  call    cs:__imp_ObfDereferenceObject
0x18000f70f  nop     dword ptr [rax+rax+00h]
0x18000f714  call    cs:__imp_KeLeaveCriticalRegion
0x18000f71b  nop     dword ptr [rax+rax+00h]
0x18000f720  mov     eax, ebx
0x18000f722  mov     rbx, [rsp+88h+arg_0]
0x18000f72a  add     rsp, 80h
0x18000f731  pop     rdi
0x18000f732  retn
```
