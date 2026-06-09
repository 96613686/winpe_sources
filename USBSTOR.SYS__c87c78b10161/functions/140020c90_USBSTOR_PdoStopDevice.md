# USBSTOR_PdoStopDevice

- ea: `0x140020c90`
- end: `0x140020d7d`
- name: `USBSTOR_PdoStopDevice`
- size: `237`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000b4a0`
- `0x14000cba8`
- `0x1400105e8`
- `0x140010664`
- `0x140020c90`

## import_xrefs

- `ntoskrnl!PoRegisterDeviceForIdleDetection` at `0x140020cf7`
- `ntoskrnl!PoRegisterDeviceForIdleDetection` at `0x140020cf7`
- `ntoskrnl!IofCompleteRequest` at `0x140020d22`
- `ntoskrnl!IofCompleteRequest` at `0x140020d22`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoStopDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _QWORD *DeviceExtension; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( (unsigned __int8)USBSTOR_IsSelectiveSuspendEnabled(*(_QWORD *)(DeviceExtension[2] + 64LL)) )
    PoRegisterDeviceForIdleDetection(DeviceObject, 0, 0, PowerDeviceD3);
  UsbQueueFreeze(DeviceExtension + 46);
  *((_DWORD *)DeviceExtension + 10) = 5;
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 126, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1886679920, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140020c90  push    rbx
0x140020c92  push    rbp
0x140020c93  push    rsi
0x140020c94  push    rdi
0x140020c95  sub     rsp, 28h
0x140020c99  mov     rsi, rdx
0x140020c9c  mov     rdi, rcx
0x140020c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ca6  lea     rbp, WPP_GLOBAL_Control
0x140020cad  cmp     rcx, rbp
0x140020cb0  jz      short loc_140020CD4
0x140020cb2  mov     eax, [rcx+2Ch]
0x140020cb5  test    al, 2
0x140020cb7  jz      short loc_140020CD4
0x140020cb9  cmp     byte ptr [rcx+29h], 4
0x140020cbd  jb      short loc_140020CD4
0x140020cbf  mov     rcx, [rcx+18h]
0x140020cc3  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020cca  mov     edx, 7Dh ; '}'
0x140020ccf  call    WPP_SF_
0x140020cd4  mov     rbx, [rdi+40h]
0x140020cd8  mov     rcx, [rbx+10h]
0x140020cdc  mov     rcx, [rcx+40h]
0x140020ce0  call    USBSTOR_IsSelectiveSuspendEnabled
0x140020ce5  test    al, al
0x140020ce7  jz      short loc_140020D03
0x140020ce9  mov     r9d, 4; State
0x140020cef  xor     r8d, r8d; PerformanceIdleTime
0x140020cf2  xor     edx, edx; ConservationIdleTime
0x140020cf4  mov     rcx, rdi; DeviceObject
0x140020cf7  call    cs:__imp_PoRegisterDeviceForIdleDetection
0x140020cfe  nop     dword ptr [rax+rax+00h]
0x140020d03  lea     rcx, [rbx+170h]
0x140020d0a  call    UsbQueueFreeze
0x140020d0f  mov     dword ptr [rbx+28h], 5
0x140020d16  xor     edx, edx; PriorityBoost
0x140020d18  mov     rcx, rsi; Irp
0x140020d1b  mov     dword ptr [rsi+30h], 0
0x140020d22  call    cs:__imp_IofCompleteRequest
0x140020d29  nop     dword ptr [rax+rax+00h]
0x140020d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d35  cmp     rcx, rbp
0x140020d38  jz      short loc_140020D5F
0x140020d3a  mov     eax, [rcx+2Ch]
0x140020d3d  test    al, 2
0x140020d3f  jz      short loc_140020D5F
0x140020d41  cmp     byte ptr [rcx+29h], 4
0x140020d45  jb      short loc_140020D5F
0x140020d47  mov     rcx, [rcx+18h]
0x140020d4b  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020d52  mov     edx, 7Eh ; '~'
0x140020d57  xor     r9d, r9d
0x140020d5a  call    WPP_SF_d
0x140020d5f  xor     r9d, r9d
0x140020d62  xor     r8d, r8d
0x140020d65  xor     edx, edx
0x140020d67  mov     ecx, 70747370h
0x140020d6c  call    USBSTOR_LogEntry
0x140020d71  xor     eax, eax
0x140020d73  add     rsp, 28h
0x140020d77  pop     rdi
0x140020d78  pop     rsi
0x140020d79  pop     rbp
0x140020d7a  pop     rbx
0x140020d7b  retn
```
