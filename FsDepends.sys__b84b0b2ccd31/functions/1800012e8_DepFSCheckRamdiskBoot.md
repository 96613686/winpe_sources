# DepFSCheckRamdiskBoot

- ea: `0x1800012e8`
- end: `0x180001427`
- name: `DepFSCheckRamdiskBoot`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800090f8`

## callees

- `0x1800012e8`
- `0x180002060`
- `0x180002480`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18000133e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x18000133e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800013c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800013c2`
- `ntoskrnl!KeInitializeEvent` at `0x18000132e`
- `ntoskrnl!KeInitializeEvent` at `0x18000132e`
- `ntoskrnl!IofCallDriver` at `0x18000139a`
- `ntoskrnl!IofCallDriver` at `0x18000139a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180001383`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x180001383`
- `ntoskrnl!ObfDereferenceObject` at `0x180001402`
- `ntoskrnl!ObfDereferenceObject` at `0x180001402`

## pseudocode

```c
bool __fastcall DepFSCheckRamdiskBoot(__int64 a1)
{
  bool v2; // di
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rbx
  IRP *v4; // rax
  NTSTATUS Status; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  _KEVENT Event; // [rsp+60h] [rbp-9h] BYREF
  _DWORD OutputBuffer[16]; // [rsp+80h] [rbp+17h] BYREF

  memset(&Event, 0, sizeof(Event));
  v2 = 0;
  IoStatusBlock = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)(a1 + 8));
  v4 = IoBuildDeviceIoControlRequest(
         0x240008u,
         AttachedDeviceReference,
         0,
         0,
         OutputBuffer,
         0x40u,
         0,
         &Event,
         &IoStatusBlock);
  if ( v4 )
  {
    Status = IofCallDriver(AttachedDeviceReference, v4);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 && OutputBuffer[5] == 3 )
      v2 = memcmp(&OutputBuffer[1], RamdiskBootDiskGuid, 0x10u) == 0;
  }
  ObfDereferenceObject(AttachedDeviceReference);
  return v2;
}

```

## disassembly

```asm
0x1800012e8  mov     [rsp-8+arg_0], rbx
0x1800012ed  mov     [rsp-8+arg_8], rdi
0x1800012f2  push    rbp
0x1800012f3  lea     rbp, [rsp-57h]
0x1800012f8  sub     rsp, 0C0h
0x1800012ff  xor     eax, eax
0x180001301  xorps   xmm0, xmm0
0x180001304  mov     rbx, rcx
0x180001307  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18000130b  xor     edx, edx; Val
0x18000130d  lea     rcx, [rbp+57h+var_40]; void *
0x180001311  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x180001315  lea     r8d, [rax+40h]; Size
0x180001319  xor     dil, dil
0x18000131c  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180001320  call    memset
0x180001325  xor     r8d, r8d; State
0x180001328  lea     rcx, [rbp+57h+Event]; Event
0x18000132c  xor     edx, edx; Type
0x18000132e  call    cs:__imp_KeInitializeEvent
0x180001335  nop     dword ptr [rax+rax+00h]
0x18000133a  mov     rcx, [rbx+8]; DeviceObject
0x18000133e  call    cs:__imp_IoGetAttachedDeviceReference
0x180001345  nop     dword ptr [rax+rax+00h]
0x18000134a  xor     r9d, r9d; InputBufferLength
0x18000134d  xor     r8d, r8d; InputBuffer
0x180001350  mov     rbx, rax
0x180001353  mov     ecx, 240008h; IoControlCode
0x180001358  lea     rax, [rbp+57h+var_70]
0x18000135c  mov     rdx, rbx; DeviceObject
0x18000135f  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x180001364  lea     rax, [rbp+57h+Event]
0x180001368  mov     [rsp+0C0h+var_88], rax; Event
0x18000136d  lea     rax, [rbp+57h+var_40]
0x180001371  mov     [rsp+0C0h+InternalDeviceIoControl], dil; InternalDeviceIoControl
0x180001376  mov     [rsp+0C0h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x18000137e  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x180001383  call    cs:__imp_IoBuildDeviceIoControlRequest
0x18000138a  nop     dword ptr [rax+rax+00h]
0x18000138f  test    rax, rax
0x180001392  jz      short loc_1800013FF
0x180001394  mov     rdx, rax; Irp
0x180001397  mov     rcx, rbx; DeviceObject
0x18000139a  call    cs:__imp_IofCallDriver
0x1800013a1  nop     dword ptr [rax+rax+00h]
0x1800013a6  cmp     eax, 103h
0x1800013ab  jnz     short loc_1800013D1
0x1800013ad  xor     r9d, r9d; Alertable
0x1800013b0  mov     [rsp+0C0h+OutputBuffer], 0; Timeout
0x1800013b9  xor     r8d, r8d; WaitMode
0x1800013bc  lea     rcx, [rbp+57h+Event]; Object
0x1800013c0  xor     edx, edx; WaitReason
0x1800013c2  call    cs:__imp_KeWaitForSingleObject
0x1800013c9  nop     dword ptr [rax+rax+00h]
0x1800013ce  mov     eax, dword ptr [rbp+57h+var_70]
0x1800013d1  test    eax, eax
0x1800013d3  js      short loc_1800013FF
0x1800013d5  cmp     [rbp+57h+var_2C], 3
0x1800013d9  jnz     short loc_1800013FF
0x1800013db  mov     r8d, 10h; Size
0x1800013e1  lea     rdx, RamdiskBootDiskGuid; Buf2
0x1800013e8  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800013ec  call    memcmp
0x1800013f1  test    eax, eax
0x1800013f3  movzx   edi, dil
0x1800013f7  mov     ecx, 1
0x1800013fc  cmovz   edi, ecx
0x1800013ff  mov     rcx, rbx; Object
0x180001402  call    cs:__imp_ObfDereferenceObject
0x180001409  nop     dword ptr [rax+rax+00h]
0x18000140e  lea     r11, [rsp+0C0h+var_s0]
0x180001416  mov     al, dil
0x180001419  mov     rbx, [r11+10h]
0x18000141d  mov     rdi, [r11+18h]
0x180001421  mov     rsp, r11
0x180001424  pop     rbp
0x180001425  retn
```
