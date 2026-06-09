# USBSTOR_PdoStartDevice

- ea: `0x14000b0bc`
- end: `0x14000b2e0`
- name: `USBSTOR_PdoStartDevice`
- size: `548`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000b0bc`
- `0x14000b2e8`
- `0x14000b35c`
- `0x14000b4a0`
- `0x1400105e8`
- `0x140010664`
- `0x140013950`
- `0x140028628`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000b201`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b201`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000b1dd`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14000b1dd`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000b1a1`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000b1a1`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b234`
- `ntoskrnl!ZwQueryValueKey` at `0x14000b234`
- `ntoskrnl!IofCompleteRequest` at `0x14000b263`
- `ntoskrnl!IofCompleteRequest` at `0x14000b263`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoStartDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rbx
  __int64 v5; // rdi
  PIO_WORKITEM WorkItem; // rax
  NTSTATUS v7; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-58h] BYREF
  void *DeviceRegKey; // [rsp+38h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  _BYTE KeyValueInformation[24]; // [rsp+50h] [rbp-38h] BYREF

  DeviceRegKey = 0;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1381258064, Irp, 0, 0);
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v5 = *(_QWORD *)(*((_QWORD *)DeviceExtension + 2) + 64LL);
  if ( DeviceExtension != (char *)-72LL && (*(_DWORD *)(v5 + 132) & 0x40) == 0 && DeviceExtension[73] < 0 )
    DeviceObject->Characteristics |= 1u;
  UsbQueueUnFreeze(DeviceExtension + 368);
  *((_DWORD *)DeviceExtension + 10) = 3;
  if ( (unsigned __int8)USBSTOR_IsSelectiveSuspendEnabled(v5) && !*(_QWORD *)(v5 + 1968) )
    USBSTOR_EnableRuntimePowerManagement();
  if ( *((_QWORD *)DeviceExtension + 91)
    || (WorkItem = IoAllocateWorkItem(DeviceObject), (*((_QWORD *)DeviceExtension + 91) = WorkItem) != 0) )
  {
    DeviceExtension[816] = 0;
    if ( IoOpenDeviceRegistryKey(DeviceObject, 1u, 0x20019u, &DeviceRegKey) >= 0 )
    {
      ResultLength = 0;
      RtlInitUnicodeString(&DestinationString, L"EnableLogoETW");
      if ( ZwQueryValueKey(
             DeviceRegKey,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x14u,
             &ResultLength) >= 0 )
      {
        if ( ResultLength )
          DeviceExtension[816] = KeyValueInformation[12] != 0;
      }
    }
    v7 = 0;
  }
  else
  {
    v7 = -1073741670;
  }
  Irp->IoStatus.Status = v7;
  IofCompleteRequest(Irp, 0);
  UsbQueueRestart(DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1920234352, v7, 0, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000b0bc  mov     [rsp+arg_10], rbx
0x14000b0c1  mov     [rsp+arg_18], rbp
0x14000b0c6  push    rsi
0x14000b0c7  push    rdi
0x14000b0c8  push    r15
0x14000b0ca  sub     rsp, 70h
0x14000b0ce  mov     rax, cs:__security_cookie
0x14000b0d5  xor     rax, rsp
0x14000b0d8  mov     [rsp+88h+var_20], rax
0x14000b0dd  xorps   xmm0, xmm0
0x14000b0e0  mov     [rsp+88h+DeviceRegKey], 0
0x14000b0e9  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14000b0ee  mov     rbp, rdx
0x14000b0f1  mov     rsi, rcx
0x14000b0f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0fb  lea     r15, WPP_GLOBAL_Control
0x14000b102  cmp     rcx, r15
0x14000b105  jz      short loc_14000B129
0x14000b107  mov     eax, [rcx+2Ch]
0x14000b10a  test    al, 2
0x14000b10c  jz      short loc_14000B129
0x14000b10e  cmp     byte ptr [rcx+29h], 4
0x14000b112  jb      short loc_14000B129
0x14000b114  mov     rcx, [rcx+18h]
0x14000b118  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000b11f  mov     edx, 77h ; 'w'
0x14000b124  call    WPP_SF_
0x14000b129  xor     r9d, r9d
0x14000b12c  xor     r8d, r8d
0x14000b12f  mov     rdx, rbp
0x14000b132  mov     ecx, 52545350h
0x14000b137  call    USBSTOR_LogEntry
0x14000b13c  mov     rbx, [rsi+40h]
0x14000b140  mov     rax, [rbx+10h]
0x14000b144  lea     rcx, [rbx+48h]
0x14000b148  mov     rdi, [rax+40h]
0x14000b14c  test    rcx, rcx
0x14000b14f  jz      short loc_14000B166
0x14000b151  mov     eax, [rdi+84h]
0x14000b157  test    al, 40h
0x14000b159  jnz     short loc_14000B166
0x14000b15b  mov     al, [rcx+1]
0x14000b15e  test    al, al
0x14000b160  jns     short loc_14000B166
0x14000b162  or      dword ptr [rsi+34h], 1
0x14000b166  lea     rcx, [rbx+170h]
0x14000b16d  call    UsbQueueUnFreeze
0x14000b172  mov     rcx, rdi
0x14000b175  mov     dword ptr [rbx+28h], 3
0x14000b17c  call    USBSTOR_IsSelectiveSuspendEnabled
0x14000b181  test    al, al
0x14000b183  jz      short loc_14000B194
0x14000b185  cmp     qword ptr [rdi+7B0h], 0
0x14000b18d  jnz     short loc_14000B194
0x14000b18f  call    USBSTOR_EnableRuntimePowerManagement
0x14000b194  cmp     qword ptr [rbx+2D8h], 0
0x14000b19c  jnz     short loc_14000B1C3
0x14000b19e  mov     rcx, rsi; DeviceObject
0x14000b1a1  call    cs:__imp_IoAllocateWorkItem
0x14000b1a8  nop     dword ptr [rax+rax+00h]
0x14000b1ad  mov     [rbx+2D8h], rax
0x14000b1b4  test    rax, rax
0x14000b1b7  jnz     short loc_14000B1C3
0x14000b1b9  mov     ebx, 0C000009Ah
0x14000b1be  jmp     loc_14000B25B
0x14000b1c3  lea     r9, [rsp+88h+DeviceRegKey]; DeviceRegKey
0x14000b1c8  mov     byte ptr [rbx+330h], 0
0x14000b1cf  mov     edx, 1; DevInstKeyType
0x14000b1d4  mov     r8d, 20019h; DesiredAccess
0x14000b1da  mov     rcx, rsi; DeviceObject
0x14000b1dd  call    cs:__imp_IoOpenDeviceRegistryKey
0x14000b1e4  nop     dword ptr [rax+rax+00h]
0x14000b1e9  test    eax, eax
0x14000b1eb  js      short loc_14000B259
0x14000b1ed  lea     rdx, aEnablelogoetw; "EnableLogoETW"
0x14000b1f4  mov     [rsp+88h+var_58], 0
0x14000b1fc  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14000b201  call    cs:__imp_RtlInitUnicodeString
0x14000b208  nop     dword ptr [rax+rax+00h]
0x14000b20d  mov     rcx, [rsp+88h+DeviceRegKey]; KeyHandle
0x14000b212  lea     rax, [rsp+88h+var_58]
0x14000b217  mov     [rsp+88h+ResultLength], rax; ResultLength
0x14000b21c  lea     r9, [rsp+88h+KeyValueInformation]; KeyValueInformation
0x14000b221  mov     r8d, 2; KeyValueInformationClass
0x14000b227  mov     [rsp+88h+Length], 14h; Length
0x14000b22f  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x14000b234  call    cs:__imp_ZwQueryValueKey
0x14000b23b  nop     dword ptr [rax+rax+00h]
0x14000b240  test    eax, eax
0x14000b242  js      short loc_14000B259
0x14000b244  cmp     [rsp+88h+var_58], 0
0x14000b249  jbe     short loc_14000B259
0x14000b24b  cmp     [rsp+88h+var_2C], 0
0x14000b250  setnz   al
0x14000b253  mov     [rbx+330h], al
0x14000b259  xor     ebx, ebx
0x14000b25b  xor     edx, edx; PriorityBoost
0x14000b25d  mov     [rbp+30h], ebx
0x14000b260  mov     rcx, rbp; Irp
0x14000b263  call    cs:__imp_IofCompleteRequest
0x14000b26a  nop     dword ptr [rax+rax+00h]
0x14000b26f  mov     rcx, rsi
0x14000b272  call    UsbQueueRestart
0x14000b277  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b27e  cmp     rcx, r15
0x14000b281  jz      short loc_14000B2A8
0x14000b283  mov     eax, [rcx+2Ch]
0x14000b286  test    al, 2
0x14000b288  jz      short loc_14000B2A8
0x14000b28a  cmp     byte ptr [rcx+29h], 4
0x14000b28e  jb      short loc_14000B2A8
0x14000b290  mov     rcx, [rcx+18h]
0x14000b294  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000b29b  mov     edx, 78h ; 'x'
0x14000b2a0  mov     r9d, ebx
0x14000b2a3  call    WPP_SF_d
0x14000b2a8  movsxd  rdx, ebx
0x14000b2ab  xor     r9d, r9d
0x14000b2ae  xor     r8d, r8d
0x14000b2b1  mov     ecx, 72747370h
0x14000b2b6  call    USBSTOR_LogEntry
0x14000b2bb  mov     eax, ebx
0x14000b2bd  mov     rcx, [rsp+88h+var_20]
0x14000b2c2  xor     rcx, rsp; StackCookie
0x14000b2c5  call    __security_check_cookie
0x14000b2ca  lea     r11, [rsp+88h+var_18]
0x14000b2cf  mov     rbx, [r11+30h]
0x14000b2d3  mov     rbp, [r11+38h]
0x14000b2d7  mov     rsp, r11
0x14000b2da  pop     r15
0x14000b2dc  pop     rdi
0x14000b2dd  pop     rsi
0x14000b2de  retn
```
