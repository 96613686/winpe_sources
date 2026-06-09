# USBSTOR_SetWmiDataBlock

- ea: `0x140020d90`
- end: `0x140020f3a`
- name: `USBSTOR_SetWmiDataBlock`
- size: `426`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140020d90`
- `0x140028628`

## import_xrefs

- `ntoskrnl!PoFxUnregisterDevice` at `0x140020e6a`
- `ntoskrnl!PoFxUnregisterDevice` at `0x140020e6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020eaf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020eaf`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140020e94`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140020e94`
- `ntoskrnl!ZwClose` at `0x140020efb`
- `ntoskrnl!ZwClose` at `0x140020efb`
- `ntoskrnl!ZwSetValueKey` at `0x140020eda`
- `ntoskrnl!ZwSetValueKey` at `0x140020eda`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020e1f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020e1f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020e35`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020e35`
- `WMILIB!WmiCompleteRequest` at `0x140020f18`
- `WMILIB!WmiCompleteRequest` at `0x140020f18`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_SetWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        __int64 a4,
        int a5,
        char *a6)
{
  NTSTATUS v8; // r8d
  PVOID DeviceExtension; // rdi
  char v10; // cl
  __int64 v11; // rax
  int v12; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-20h] BYREF
  void *DeviceRegKey; // [rsp+80h] [rbp+20h] BYREF
  BOOL Data; // [rsp+90h] [rbp+30h] BYREF

  DeviceRegKey = 0;
  Data = 0;
  DestinationString = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a3 == 1 )
  {
    if ( !a5 )
    {
      v8 = -1073741789;
      return WmiCompleteRequest(DeviceObject, Irp, v8, 0, 0);
    }
    DeviceExtension = DeviceObject->DeviceExtension;
    v10 = *a6;
    Data = *a6 != 0;
    v11 = *((_QWORD *)DeviceExtension + 246);
    if ( v10 )
    {
      if ( !v11 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
        v12 = *((_DWORD *)DeviceExtension + 32);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( v12 )
        {
          v8 = -2147483631;
          return WmiCompleteRequest(DeviceObject, Irp, v8, 0, 0);
        }
        if ( (int)USBSTOR_EnableRuntimePowerManagement(DeviceExtension) < 0 )
        {
LABEL_17:
          v8 = 0;
          return WmiCompleteRequest(DeviceObject, Irp, v8, 0, 0);
        }
      }
    }
    else if ( v11 )
    {
      PoFxUnregisterDevice(*((_QWORD *)DeviceExtension + 246));
      *((_QWORD *)DeviceExtension + 246) = 0;
    }
    if ( IoOpenDeviceRegistryKey(*((PDEVICE_OBJECT *)DeviceExtension + 2), 1u, 0x20006u, &DeviceRegKey) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"EnableSelectiveSuspend");
      if ( ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, &Data, 4u) >= 0 )
        *((_BYTE *)DeviceExtension + 2041) = Data;
      ZwClose(DeviceRegKey);
    }
    goto LABEL_17;
  }
  v8 = -1073741163;
  return WmiCompleteRequest(DeviceObject, Irp, v8, 0, 0);
}

```

## disassembly

```asm
0x140020d90  mov     [rsp-18h+arg_8], rbx
0x140020d95  mov     [rsp-18h+arg_18], rsi
0x140020d9a  push    rbp
0x140020d9b  push    rdi
0x140020d9c  push    r14
0x140020d9e  mov     rbp, rsp
0x140020da1  sub     rsp, 60h
0x140020da5  xor     eax, eax
0x140020da7  mov     [rbp+DeviceRegKey], 0
0x140020daf  mov     [rbp+arg_10], 0
0x140020db6  xorps   xmm0, xmm0
0x140020db9  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140020dbd  xorps   xmm1, xmm1
0x140020dc0  mov     r14, rdx
0x140020dc3  mov     rsi, rcx
0x140020dc6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140020dca  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm1
0x140020dce  cmp     r8d, 1
0x140020dd2  jz      short loc_140020DDF
0x140020dd4  mov     r8d, 0C0000295h
0x140020dda  jmp     loc_140020F0A
0x140020ddf  cmp     [rbp+arg_20], 1
0x140020de3  jnb     short loc_140020DF0
0x140020de5  mov     r8d, 0C0000023h
0x140020deb  jmp     loc_140020F0A
0x140020df0  mov     rax, [rbp+arg_28]
0x140020df4  mov     rdi, [rcx+40h]
0x140020df8  mov     cl, [rax]
0x140020dfa  xor     eax, eax
0x140020dfc  test    cl, cl
0x140020dfe  setnz   al
0x140020e01  mov     [rbp+arg_10], eax
0x140020e04  mov     rax, [rdi+7B0h]
0x140020e0b  test    cl, cl
0x140020e0d  jz      short loc_140020E62
0x140020e0f  test    rax, rax
0x140020e12  jnz     short loc_140020E81
0x140020e14  lea     rcx, [rdi+90h]; SpinLock
0x140020e1b  lea     rdx, [rbp+LockHandle]; LockHandle
0x140020e1f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140020e26  nop     dword ptr [rax+rax+00h]
0x140020e2b  mov     ebx, [rdi+80h]
0x140020e31  lea     rcx, [rbp+LockHandle]; LockHandle
0x140020e35  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020e3c  nop     dword ptr [rax+rax+00h]
0x140020e41  test    ebx, ebx
0x140020e43  jz      short loc_140020E50
0x140020e45  mov     r8d, 80000011h
0x140020e4b  jmp     loc_140020F0A
0x140020e50  mov     rcx, rdi
0x140020e53  call    USBSTOR_EnableRuntimePowerManagement
0x140020e58  test    eax, eax
0x140020e5a  js      loc_140020F07
0x140020e60  jmp     short loc_140020E81
0x140020e62  test    rax, rax
0x140020e65  jz      short loc_140020E81
0x140020e67  mov     rcx, rax
0x140020e6a  call    cs:__imp_PoFxUnregisterDevice
0x140020e71  nop     dword ptr [rax+rax+00h]
0x140020e76  mov     qword ptr [rdi+7B0h], 0
0x140020e81  mov     rcx, [rdi+10h]; DeviceObject
0x140020e85  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140020e89  mov     edx, 1; DevInstKeyType
0x140020e8e  mov     r8d, 20006h; DesiredAccess
0x140020e94  call    cs:__imp_IoOpenDeviceRegistryKey
0x140020e9b  nop     dword ptr [rax+rax+00h]
0x140020ea0  test    eax, eax
0x140020ea2  js      short loc_140020F07
0x140020ea4  lea     rdx, aEnableselectiv; "EnableSelectiveSuspend"
0x140020eab  lea     rcx, [rbp+DestinationString]; DestinationString
0x140020eaf  call    cs:__imp_RtlInitUnicodeString
0x140020eb6  nop     dword ptr [rax+rax+00h]
0x140020ebb  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140020ebf  lea     rax, [rbp+arg_10]
0x140020ec3  mov     r9d, 4; Type
0x140020ec9  lea     rdx, [rbp+DestinationString]; ValueName
0x140020ecd  mov     [rsp+60h+DataSize], r9d; DataSize
0x140020ed2  xor     r8d, r8d; TitleIndex
0x140020ed5  mov     [rsp+60h+Data], rax; Data
0x140020eda  call    cs:__imp_ZwSetValueKey
0x140020ee1  nop     dword ptr [rax+rax+00h]
0x140020ee6  test    eax, eax
0x140020ee8  js      short loc_140020EF7
0x140020eea  cmp     [rbp+arg_10], 0
0x140020eee  setnz   al
0x140020ef1  mov     [rdi+7F9h], al
0x140020ef7  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140020efb  call    cs:__imp_ZwClose
0x140020f02  nop     dword ptr [rax+rax+00h]
0x140020f07  xor     r8d, r8d; Status
0x140020f0a  xor     r9d, r9d; BufferUsed
0x140020f0d  mov     byte ptr [rsp+60h+Data], 0; PriorityBoost
0x140020f12  mov     rdx, r14; Irp
0x140020f15  mov     rcx, rsi; DeviceObject
0x140020f18  call    cs:__imp_WmiCompleteRequest
0x140020f1f  nop     dword ptr [rax+rax+00h]
0x140020f24  lea     r11, [rsp+60h+var_s0]
0x140020f29  mov     rbx, [r11+28h]
0x140020f2d  mov     rsi, [r11+38h]
0x140020f31  mov     rsp, r11
0x140020f34  pop     r14
0x140020f36  pop     rdi
0x140020f37  pop     rbp
0x140020f38  retn
```
