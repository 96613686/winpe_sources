# WimpFSFGetCngExtensions

- ea: `0x140029758`
- end: `0x1400298c1`
- name: `WimpFSFGetCngExtensions`
- size: `361`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002e91c`

## callees

- `0x140029758`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140029855`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029855`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002980c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002980c`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400297aa`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1400297aa`
- `ntoskrnl!IofCallDriver` at `0x14002982b`
- `ntoskrnl!IofCallDriver` at `0x14002982b`
- `ntoskrnl!KeInitializeEvent` at `0x1400297c9`
- `ntoskrnl!KeInitializeEvent` at `0x1400297c9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400298a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400298a1`

## pseudocode

```c
__int64 WimpFSFGetCngExtensions()
{
  NTSTATUS DeviceObjectPointer; // ebx
  IRP *v1; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-20h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp+10h] BYREF
  __int64 OutputBuffer; // [rsp+98h] [rbp+18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp+20h] BYREF

  DeviceObject = 0;
  FileObject = 0;
  OutputBuffer = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(
                          (PUNICODE_STRING)&g_CngDeviceName,
                          0x1F01FFu,
                          &FileObject,
                          &DeviceObject);
  if ( DeviceObjectPointer >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v1 = IoBuildDeviceIoControlRequest(0x390064u, DeviceObject, 0, 0, &OutputBuffer, 8u, 0, &Event, &IoStatusBlock);
    if ( !v1 )
    {
      DeviceObjectPointer = -1073741823;
      goto LABEL_14;
    }
    DeviceObjectPointer = IofCallDriver(DeviceObject, v1);
    if ( DeviceObjectPointer == 259 )
    {
      DeviceObjectPointer = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( DeviceObjectPointer < 0 )
        goto LABEL_14;
      DeviceObjectPointer = IoStatusBlock.Status;
    }
    if ( DeviceObjectPointer >= 0 )
    {
      if ( OutputBuffer && *(_DWORD *)OutputBuffer && *(_QWORD *)(OutputBuffer + 8) && *(_QWORD *)(OutputBuffer + 16) )
        g_WimIntegrityCngExtensions = OutputBuffer;
      else
        DeviceObjectPointer = -1073741637;
    }
  }
LABEL_14:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x140029758  mov     [rsp-8+arg_18], rbx
0x14002975d  mov     [rsp-8+DeviceObject], rcx
0x140029762  push    rbp
0x140029763  mov     rbp, rsp
0x140029766  sub     rsp, 80h
0x14002976d  xorps   xmm0, xmm0
0x140029770  mov     [rbp+DeviceObject], 0
0x140029778  xor     eax, eax
0x14002977a  mov     [rbp+FileObject], 0
0x140029782  lea     r9, [rbp+DeviceObject]; DeviceObject
0x140029786  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14002978a  lea     r8, [rbp+FileObject]; FileObject
0x14002978e  mov     [rbp+arg_8], 0
0x140029796  mov     edx, 1F01FFh; DesiredAccess
0x14002979b  lea     rcx, g_CngDeviceName; ObjectName
0x1400297a2  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1400297a6  movups  xmmword ptr [rbp+var_30], xmm0
0x1400297aa  call    cs:__imp_IoGetDeviceObjectPointer
0x1400297b1  nop     dword ptr [rax+rax+00h]
0x1400297b6  mov     ebx, eax
0x1400297b8  test    eax, eax
0x1400297ba  js      loc_140029898
0x1400297c0  xor     r8d, r8d; State
0x1400297c3  lea     rcx, [rbp+Event]; Event
0x1400297c7  xor     edx, edx; Type
0x1400297c9  call    cs:__imp_KeInitializeEvent
0x1400297d0  nop     dword ptr [rax+rax+00h]
0x1400297d5  mov     rdx, [rbp+DeviceObject]; DeviceObject
0x1400297d9  lea     rax, [rbp+var_30]
0x1400297dd  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x1400297e2  xor     r9d, r9d; InputBufferLength
0x1400297e5  lea     rax, [rbp+Event]
0x1400297e9  xor     r8d, r8d; InputBuffer
0x1400297ec  mov     [rsp+80h+var_48], rax; Event
0x1400297f1  mov     ecx, 390064h; IoControlCode
0x1400297f6  mov     [rsp+80h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400297fb  lea     rax, [rbp+arg_8]
0x1400297ff  mov     [rsp+80h+OutputBufferLength], 8; OutputBufferLength
0x140029807  mov     [rsp+80h+OutputBuffer], rax; OutputBuffer
0x14002980c  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140029813  nop     dword ptr [rax+rax+00h]
0x140029818  test    rax, rax
0x14002981b  jnz     short loc_140029824
0x14002981d  mov     ebx, 0C0000001h
0x140029822  jmp     short loc_140029898
0x140029824  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x140029828  mov     rdx, rax; Irp
0x14002982b  call    cs:__imp_IofCallDriver
0x140029832  nop     dword ptr [rax+rax+00h]
0x140029837  mov     ebx, eax
0x140029839  cmp     eax, 103h
0x14002983e  jnz     short loc_14002986A
0x140029840  xor     r9d, r9d; Alertable
0x140029843  mov     [rsp+80h+OutputBuffer], 0; Timeout
0x14002984c  xor     r8d, r8d; WaitMode
0x14002984f  lea     rcx, [rbp+Event]; Object
0x140029853  xor     edx, edx; WaitReason
0x140029855  call    cs:__imp_KeWaitForSingleObject
0x14002985c  nop     dword ptr [rax+rax+00h]
0x140029861  mov     ebx, eax
0x140029863  test    eax, eax
0x140029865  js      short loc_140029898
0x140029867  mov     ebx, dword ptr [rbp+var_30]
0x14002986a  test    ebx, ebx
0x14002986c  js      short loc_140029898
0x14002986e  mov     rax, [rbp+arg_8]
0x140029872  test    rax, rax
0x140029875  jz      short loc_140029893
0x140029877  cmp     dword ptr [rax], 1
0x14002987a  jb      short loc_140029893
0x14002987c  cmp     qword ptr [rax+8], 0
0x140029881  jz      short loc_140029893
0x140029883  cmp     qword ptr [rax+10h], 0
0x140029888  jz      short loc_140029893
0x14002988a  mov     cs:g_WimIntegrityCngExtensions, rax
0x140029891  jmp     short loc_140029898
0x140029893  mov     ebx, 0C00000BBh
0x140029898  mov     rcx, [rbp+FileObject]; Object
0x14002989c  test    rcx, rcx
0x14002989f  jz      short loc_1400298AD
0x1400298a1  call    cs:__imp_ObfDereferenceObject
0x1400298a8  nop     dword ptr [rax+rax+00h]
0x1400298ad  mov     eax, ebx
0x1400298af  mov     rbx, [rsp+80h+arg_18]
0x1400298b7  add     rsp, 80h
0x1400298be  pop     rbp
0x1400298bf  retn
```
