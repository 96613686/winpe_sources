# DriverEntry

- ea: `0x14002890c`
- end: `0x140028b47`
- name: `DriverEntry`
- size: `571`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14002b010`

## callees

- `0x14000e974`
- `0x140010664`
- `0x140010694`
- `0x1400106c0`
- `0x14001f374`
- `0x14001f8d0`
- `0x140021c20`
- `0x14002890c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140028ae5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028ae5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028a2f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028a2f`
- `ntoskrnl!ExAllocatePool2` at `0x1400289d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400289d9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140028af6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140028af6`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  DestinationString = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_wppCtlGuid;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  USBSTOR_QueryBreakOnDeviceFailure();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogInit();
  ::DestinationString.MaximumLength = RegistryPath->Length + 2;
  ::DestinationString.Length = RegistryPath->Length;
  ::DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, ::DestinationString.MaximumLength, 1396788565);
  if ( ::DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&::DestinationString, RegistryPath);
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)USBSTOR_Unload;
    DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)USBSTOR_AddDevice;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&USBSTOR_Create;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&USBSTOR_Close;
    DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&USBSTOR_ReadWrite;
    DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&USBSTOR_ReadWrite;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)USBSTOR_DeviceControl;
    DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)USBSTOR_Scsi;
    DriverObject->DriverStartIo = (PDRIVER_STARTIO)USBSTOR_StartIo;
    DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)USBSTOR_Power;
    DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)USBSTOR_SystemControl;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)USBSTOR_Pnp;
    USBSTOR_PreInitializeEmergencyWorkerThread();
    RtlInitUnicodeString(&DestinationString, L"KseQueryDeviceFlags");
    *(_QWORD *)&WPP_MAIN_CB.DeviceType = MmGetSystemRoutineAddress(&DestinationString);
    McGenEventRegister_EtwRegister();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    return -1073741670;
  }
}

```

## disassembly

```asm
0x14002890c  push    rbx
0x14002890e  push    rbp
0x14002890f  push    rdi
0x140028910  push    r12
0x140028912  sub     rsp, 38h
0x140028916  xorps   xmm0, xmm0
0x140028919  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140028924  lea     rax, WPP_ThisDir_CTLGUID_wppCtlGuid
0x14002892b  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x140028936  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14002893b  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140028942  mov     rdi, rdx
0x140028945  mov     rbx, rcx
0x140028948  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140028953  mov     cs:WPP_MAIN_CB.Timer, 1
0x14002895e  call    WppLoadTracingSupport
0x140028963  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14002896e  call    WppInitKm
0x140028973  call    USBSTOR_QueryBreakOnDeviceFailure
0x140028978  mov     rcx, cs:WPP_GLOBAL_Control
0x14002897f  lea     r12, WPP_GLOBAL_Control
0x140028986  mov     ebp, 100h
0x14002898b  cmp     rcx, r12
0x14002898e  jz      short loc_1400289B0
0x140028990  test    [rcx+2Ch], ebp
0x140028993  jz      short loc_1400289B0
0x140028995  cmp     byte ptr [rcx+29h], 4
0x140028999  jb      short loc_1400289B0
0x14002899b  mov     rcx, [rcx+18h]
0x14002899f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400289a6  mov     edx, 0Ah
0x1400289ab  call    WPP_SF_
0x1400289b0  call    USBSTOR_LogInit
0x1400289b5  movzx   eax, word ptr [rdi]
0x1400289b8  mov     r8d, 53414D55h
0x1400289be  add     ax, 2
0x1400289c2  mov     rcx, rbp
0x1400289c5  movzx   edx, ax
0x1400289c8  mov     cs:DestinationString.MaximumLength, dx
0x1400289cf  movzx   eax, word ptr [rdi]
0x1400289d2  mov     cs:DestinationString.Length, ax
0x1400289d9  call    cs:__imp_ExAllocatePool2
0x1400289e0  nop     dword ptr [rax+rax+00h]
0x1400289e5  mov     cs:DestinationString.Buffer, rax
0x1400289ec  test    rax, rax
0x1400289ef  jnz     short loc_140028A25
0x1400289f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289f8  cmp     rcx, r12
0x1400289fb  jz      short loc_140028A1B
0x1400289fd  test    [rcx+2Ch], ebp
0x140028a00  jz      short loc_140028A1B
0x140028a02  cmp     byte ptr [rcx+29h], 4
0x140028a06  jb      short loc_140028A1B
0x140028a08  mov     rcx, [rcx+18h]
0x140028a0c  lea     edx, [rax+0Bh]
0x140028a0f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028a16  call    WPP_SF_
0x140028a1b  mov     eax, 0C000009Ah
0x140028a20  jmp     loc_140028B3C
0x140028a25  mov     rdx, rdi; SourceString
0x140028a28  lea     rcx, DestinationString; DestinationString
0x140028a2f  call    cs:__imp_RtlCopyUnicodeString
0x140028a36  nop     dword ptr [rax+rax+00h]
0x140028a3b  lea     rax, USBSTOR_Unload
0x140028a42  mov     [rbx+68h], rax
0x140028a46  lea     rcx, USBSTOR_AddDevice
0x140028a4d  mov     rax, [rbx+30h]
0x140028a51  mov     [rax+8], rcx
0x140028a55  lea     rax, USBSTOR_Create
0x140028a5c  mov     [rbx+70h], rax
0x140028a60  lea     rax, USBSTOR_Close
0x140028a67  mov     [rbx+80h], rax
0x140028a6e  lea     rax, USBSTOR_ReadWrite
0x140028a75  mov     [rbx+88h], rax
0x140028a7c  mov     [rbx+90h], rax
0x140028a83  lea     rax, USBSTOR_DeviceControl
0x140028a8a  mov     [rbx+0E0h], rax
0x140028a91  lea     rax, USBSTOR_Scsi
0x140028a98  mov     [rbx+0E8h], rax
0x140028a9f  lea     rax, USBSTOR_StartIo
0x140028aa6  mov     [rbx+60h], rax
0x140028aaa  lea     rax, USBSTOR_Power
0x140028ab1  mov     [rbx+120h], rax
0x140028ab8  lea     rax, USBSTOR_SystemControl
0x140028abf  mov     [rbx+128h], rax
0x140028ac6  lea     rax, USBSTOR_Pnp
0x140028acd  mov     [rbx+148h], rax
0x140028ad4  call    USBSTOR_PreInitializeEmergencyWorkerThread
0x140028ad9  lea     rdx, aKsequerydevice; "KseQueryDeviceFlags"
0x140028ae0  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140028ae5  call    cs:__imp_RtlInitUnicodeString
0x140028aec  nop     dword ptr [rax+rax+00h]
0x140028af1  lea     rcx, [rsp+58h+DestinationString]; SystemRoutineName
0x140028af6  call    cs:__imp_MmGetSystemRoutineAddress
0x140028afd  nop     dword ptr [rax+rax+00h]
0x140028b02  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140028b09  call    McGenEventRegister_EtwRegister
0x140028b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b15  cmp     rcx, r12
0x140028b18  jz      short loc_140028B3A
0x140028b1a  test    [rcx+2Ch], ebp
0x140028b1d  jz      short loc_140028B3A
0x140028b1f  cmp     byte ptr [rcx+29h], 4
0x140028b23  jb      short loc_140028B3A
0x140028b25  mov     rcx, [rcx+18h]
0x140028b29  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028b30  mov     edx, 0Ch
0x140028b35  call    WPP_SF_
0x140028b3a  xor     eax, eax
0x140028b3c  add     rsp, 38h
0x140028b40  pop     r12
0x140028b42  pop     rdi
0x140028b43  pop     rbp
0x140028b44  pop     rbx
0x140028b45  retn
```
