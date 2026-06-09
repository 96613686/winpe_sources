# USBSTOR_AddDevice

- ea: `0x1400250c0`
- end: `0x140025352`
- name: `USBSTOR_AddDevice`
- size: `658`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140003630`
- `0x140010664`
- `0x140013d40`
- `0x1400250c0`
- `0x140025358`
- `0x140025630`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140025299`
- `ntoskrnl!KeInitializeDpc` at `0x140025299`
- `ntoskrnl!IoSetStartIoAttributes` at `0x140025176`
- `ntoskrnl!IoSetStartIoAttributes` at `0x140025176`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025238`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025238`
- `ntoskrnl!IoDeleteDevice` at `0x140025329`
- `ntoskrnl!IoDeleteDevice` at `0x140025329`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400251ed`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400251ed`
- `ntoskrnl!KeInitializeTimer` at `0x14002527b`
- `ntoskrnl!KeInitializeTimer` at `0x14002527b`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400251b4`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400251b4`
- `ntoskrnl!IoCreateDevice` at `0x140025154`
- `ntoskrnl!IoCreateDevice` at `0x140025154`
- `ntoskrnl!KeInitializeEvent` at `0x140025225`
- `ntoskrnl!KeInitializeEvent` at `0x140025250`
- `ntoskrnl!KeInitializeEvent` at `0x140025268`
- `ntoskrnl!KeInitializeEvent` at `0x140025225`
- `ntoskrnl!KeInitializeEvent` at `0x140025250`
- `ntoskrnl!KeInitializeEvent` at `0x140025268`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_AddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS result; // eax
  char *DeviceExtension; // rbx
  PDEVICE_OBJECT SourceDevice; // [rsp+70h] [rbp+30h] BYREF

  SourceDevice = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1145324609, DriverObject, TargetDevice, 0);
  result = IoCreateDevice(DriverObject, 0x800u, 0, 0x2Au, 0x180u, 0, &SourceDevice);
  if ( result >= 0 )
  {
    IoSetStartIoAttributes(SourceDevice, 1u, 0);
    DeviceExtension = (char *)SourceDevice->DeviceExtension;
    memset(DeviceExtension + 4, 0, 0x7FCu);
    *(_DWORD *)DeviceExtension = 558842950;
    *((_QWORD *)DeviceExtension + 1) = SourceDevice;
    *((_QWORD *)DeviceExtension + 2) = TargetDevice;
    *((_QWORD *)DeviceExtension + 3) = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
    *((_QWORD *)DeviceExtension + 5) = DeviceExtension + 32;
    *((_QWORD *)DeviceExtension + 4) = DeviceExtension + 32;
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), 0x53627355u, 0xAu, 0xFFFFFFFu, 0x20u);
    *((_DWORD *)DeviceExtension + 38) = 1;
    *((_DWORD *)DeviceExtension + 39) = 1;
    *((_DWORD *)DeviceExtension + 454) = 0x10000;
    *((_DWORD *)DeviceExtension + 455) = 17;
    KeInitializeEvent((PRKEVENT)DeviceExtension + 7, SynchronizationEvent, 0);
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 18);
    KeInitializeEvent((PRKEVENT)DeviceExtension + 14, SynchronizationEvent, 0);
    KeInitializeEvent((PRKEVENT)(DeviceExtension + 1936), SynchronizationEvent, 0);
    KeInitializeTimer((PKTIMER)DeviceExtension + 3);
    KeInitializeDpc((PRKDPC)DeviceExtension + 4, USBSTOR_TimeoutDpc, SourceDevice);
    USBSTOR_QueryFdoParams(SourceDevice);
    USBSTOR_GetWriteProtectSetting(DeviceExtension);
    DeviceExtension[1812] = 1;
    SourceDevice->Flags |= 0x10u;
    SourceDevice->Flags |= 0x2000u;
    SourceDevice->Flags &= ~0x80u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    USBSTOR_LogEntry(1684300897, SourceDevice, DeviceExtension, *((_QWORD *)DeviceExtension + 3));
    if ( *((_QWORD *)DeviceExtension + 3) )
    {
      return 0;
    }
    else
    {
      if ( SourceDevice )
        IoDeleteDevice(SourceDevice);
      return -1073741823;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400250c0  mov     [rsp-18h+arg_0], rbx
0x1400250c5  mov     [rsp-18h+arg_8], rsi
0x1400250ca  push    rbp
0x1400250cb  push    rdi
0x1400250cc  push    r12
0x1400250ce  mov     rbp, rsp
0x1400250d1  sub     rsp, 40h
0x1400250d5  mov     rdi, rdx
0x1400250d8  mov     [rbp+SourceDevice], 0
0x1400250e0  mov     rbx, rcx
0x1400250e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400250ea  lea     r12, WPP_GLOBAL_Control
0x1400250f1  cmp     rcx, r12
0x1400250f4  jz      short loc_14002511A
0x1400250f6  test    dword ptr [rcx+2Ch], 100h
0x1400250fd  jz      short loc_14002511A
0x1400250ff  cmp     byte ptr [rcx+29h], 4
0x140025103  jb      short loc_14002511A
0x140025105  mov     rcx, [rcx+18h]
0x140025109  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140025110  mov     edx, 0Fh
0x140025115  call    WPP_SF_
0x14002511a  xor     r9d, r9d
0x14002511d  mov     r8, rdi
0x140025120  mov     rdx, rbx
0x140025123  mov     ecx, 44444441h
0x140025128  call    USBSTOR_LogEntry
0x14002512d  lea     rax, [rbp+SourceDevice]
0x140025131  mov     r9d, 2Ah ; '*'; DeviceType
0x140025137  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x14002513c  xor     r8d, r8d; DeviceName
0x14002513f  mov     [rsp+40h+Exclusive], 0; Exclusive
0x140025144  mov     edx, 800h; DeviceExtensionSize
0x140025149  mov     rcx, rbx; DriverObject
0x14002514c  mov     [rsp+40h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x140025154  call    cs:__imp_IoCreateDevice
0x14002515b  nop     dword ptr [rax+rax+00h]
0x140025160  test    eax, eax
0x140025162  js      loc_14002533E
0x140025168  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14002516c  xor     r8d, r8d; NonCancelable
0x14002516f  lea     esi, [r8+1]
0x140025173  mov     dl, sil; DeferredStartIo
0x140025176  call    cs:__imp_IoSetStartIoAttributes
0x14002517d  nop     dword ptr [rax+rax+00h]
0x140025182  mov     rax, [rbp+SourceDevice]
0x140025186  xor     edx, edx; Val
0x140025188  mov     r8d, 7FCh; Size
0x14002518e  mov     rbx, [rax+40h]
0x140025192  lea     rcx, [rbx+4]; void *
0x140025196  call    memset
0x14002519b  mov     dword ptr [rbx], 214F4446h
0x1400251a1  mov     rdx, rdi; TargetDevice
0x1400251a4  mov     rax, [rbp+SourceDevice]
0x1400251a8  mov     [rbx+8], rax
0x1400251ac  mov     [rbx+10h], rdi
0x1400251b0  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x1400251b4  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400251bb  nop     dword ptr [rax+rax+00h]
0x1400251c0  lea     rcx, [rbx+728h]; Lock
0x1400251c7  mov     [rsp+40h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x1400251cf  mov     [rbx+18h], rax
0x1400251d3  lea     r8d, [rsi+9]; MaxLockedMinutes
0x1400251d7  lea     rax, [rbx+20h]
0x1400251db  mov     edx, 53627355h; AllocateTag
0x1400251e0  mov     r9d, 0FFFFFFFh; HighWatermark
0x1400251e6  mov     [rax+8], rax
0x1400251ea  mov     [rax], rax
0x1400251ed  call    cs:__imp_IoInitializeRemoveLockEx
0x1400251f4  nop     dword ptr [rax+rax+00h]
0x1400251f9  lea     rcx, [rbx+0A8h]; Event
0x140025200  mov     [rbx+98h], esi
0x140025206  xor     r8d, r8d; State
0x140025209  mov     [rbx+9Ch], esi
0x14002520f  mov     edx, esi; Type
0x140025211  mov     dword ptr [rbx+718h], 10000h
0x14002521b  mov     dword ptr [rbx+71Ch], 11h
0x140025225  call    cs:__imp_KeInitializeEvent
0x14002522c  nop     dword ptr [rax+rax+00h]
0x140025231  lea     rcx, [rbx+90h]; SpinLock
0x140025238  call    cs:__imp_KeInitializeSpinLock
0x14002523f  nop     dword ptr [rax+rax+00h]
0x140025244  lea     rcx, [rbx+150h]; Event
0x14002524b  xor     r8d, r8d; State
0x14002524e  mov     edx, esi; Type
0x140025250  call    cs:__imp_KeInitializeEvent
0x140025257  nop     dword ptr [rax+rax+00h]
0x14002525c  lea     rcx, [rbx+790h]; Event
0x140025263  xor     r8d, r8d; State
0x140025266  mov     edx, esi; Type
0x140025268  call    cs:__imp_KeInitializeEvent
0x14002526f  nop     dword ptr [rax+rax+00h]
0x140025274  lea     rcx, [rbx+0C0h]; Timer
0x14002527b  call    cs:__imp_KeInitializeTimer
0x140025282  nop     dword ptr [rax+rax+00h]
0x140025287  mov     r8, [rbp+SourceDevice]; DeferredContext
0x14002528b  lea     rcx, [rbx+100h]; Dpc
0x140025292  lea     rdx, USBSTOR_TimeoutDpc; DeferredRoutine
0x140025299  call    cs:__imp_KeInitializeDpc
0x1400252a0  nop     dword ptr [rax+rax+00h]
0x1400252a5  mov     rcx, [rbp+SourceDevice]
0x1400252a9  call    USBSTOR_QueryFdoParams
0x1400252ae  mov     rcx, rbx
0x1400252b1  call    USBSTOR_GetWriteProtectSetting
0x1400252b6  mov     [rbx+714h], sil
0x1400252bd  lea     edx, [rsi+0Fh]
0x1400252c0  mov     rax, [rbp+SourceDevice]
0x1400252c4  or      [rax+30h], edx
0x1400252c7  mov     rax, [rbp+SourceDevice]
0x1400252cb  bts     dword ptr [rax+30h], 0Dh
0x1400252d0  mov     rax, [rbp+SourceDevice]
0x1400252d4  btr     dword ptr [rax+30h], 7
0x1400252d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252e0  cmp     rcx, r12
0x1400252e3  jz      short loc_140025304
0x1400252e5  test    dword ptr [rcx+2Ch], 100h
0x1400252ec  jz      short loc_140025304
0x1400252ee  cmp     byte ptr [rcx+29h], 5
0x1400252f2  jb      short loc_140025304
0x1400252f4  mov     rcx, [rcx+18h]
0x1400252f8  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400252ff  call    WPP_SF_
0x140025304  mov     r9, [rbx+18h]
0x140025308  mov     r8, rbx
0x14002530b  mov     rdx, [rbp+SourceDevice]
0x14002530f  mov     ecx, 64646461h
0x140025314  call    USBSTOR_LogEntry
0x140025319  cmp     qword ptr [rbx+18h], 0
0x14002531e  jnz     short loc_14002533C
0x140025320  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140025324  test    rcx, rcx
0x140025327  jz      short loc_140025335
0x140025329  call    cs:__imp_IoDeleteDevice
0x140025330  nop     dword ptr [rax+rax+00h]
0x140025335  mov     eax, 0C0000001h
0x14002533a  jmp     short loc_14002533E
0x14002533c  xor     eax, eax
0x14002533e  mov     rbx, [rsp+40h+arg_0]
0x140025343  mov     rsi, [rsp+40h+arg_8]
0x140025348  add     rsp, 40h
0x14002534c  pop     r12
0x14002534e  pop     rdi
0x14002534f  pop     rbp
0x140025350  retn
```
