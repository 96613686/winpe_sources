# BthEnumAddDevice

- ea: `0x14001ca00`
- end: `0x14001ccc2`
- name: `BthEnumAddDevice`
- size: `706`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001328`
- `0x140004520`
- `0x140007d00`
- `0x140008140`
- `0x14001ca00`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001cac2`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001cac2`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001caf2`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001caf2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001cb06`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001cb06`
- `ntoskrnl!IoCreateDevice` at `0x14001cb3a`
- `ntoskrnl!IoCreateDevice` at `0x14001cb3a`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001cb5d`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001cb5d`
- `ntoskrnl!KeInitializeEvent` at `0x14001cc80`
- `ntoskrnl!KeInitializeEvent` at `0x14001cc80`
- `ntoskrnl!IoDeleteDevice` at `0x14001cbb8`
- `ntoskrnl!IoDeleteDevice` at `0x14001cbb8`
- `ntoskrnl!ExFreePool` at `0x14001cb9f`
- `ntoskrnl!ExFreePool` at `0x14001cb9f`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca8e`
- `ntoskrnl!ExAllocatePool2` at `0x14001ca8e`

## pseudocode

```c
__int64 __fastcall BthEnumAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  wchar_t *Pool2; // rax
  wchar_t *v5; // rdi
  NTSTATUS v6; // ebx
  ULONG Next; // ecx
  PDEVICE_OBJECT v8; // rax
  int v9; // edx
  PDEVICE_OBJECT v10; // rsi
  char *DeviceExtension; // rbx
  PDEVICE_OBJECT SourceDevice; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING String; // [rsp+58h] [rbp-11h] BYREF
  char v16; // [rsp+68h] [rbp-1h] BYREF

  SourceDevice = 0;
  Destination = 0;
  String = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)TargetDevice,
      3,
      10,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
  Pool2 = (wchar_t *)ExAllocatePool2(256, 258, 1330467906);
  v5 = Pool2;
  if ( Pool2 )
  {
    Destination.Buffer = Pool2;
    *(_DWORD *)&Destination.Length = 0x800000;
    RtlAppendUnicodeToString(&Destination, L"\\Device\\BthEnum");
    Next = (ULONG)WPP_MAIN_CB.Dpc.DpcListEntry.Next;
    String.Buffer = (wchar_t *)&v16;
    *(_DWORD *)&String.Length = 2621440;
    ++LODWORD(WPP_MAIN_CB.Dpc.DpcListEntry.Next);
    RtlIntegerToUnicodeString(Next, 0xAu, &String);
    RtlAppendUnicodeStringToString(&Destination, &String);
    v6 = IoCreateDevice(DriverObject, 0x260u, &Destination, 0x15u, 0, 0, &SourceDevice);
    if ( v6 >= 0 )
    {
      v8 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
      v10 = v8;
      if ( v8 )
      {
        SourceDevice->Flags |= v8->Flags;
        SourceDevice->StackSize = v8->StackSize + 1;
        DeviceExtension = (char *)SourceDevice->DeviceExtension;
        memset(DeviceExtension + 4, 0, 0x25Cu);
        *(_DWORD *)DeviceExtension = 542065734;
        *((_QWORD *)DeviceExtension + 1) = SourceDevice;
        *((_QWORD *)DeviceExtension + 2) = TargetDevice;
        *((_QWORD *)DeviceExtension + 3) = v10;
        *((_QWORD *)DeviceExtension + 29) = 0;
        *((_QWORD *)DeviceExtension + 30) = 0;
        IrpList_InitEx(DeviceExtension + 64, DeviceExtension + 80);
        *(struct _UNICODE_STRING *)(DeviceExtension + 216) = Destination;
        *((_QWORD *)DeviceExtension + 17) = 0;
        *((_QWORD *)DeviceExtension + 18) = 0;
        *((_DWORD *)DeviceExtension + 38) = 1;
        *((_QWORD *)DeviceExtension + 20) = 0;
        *((_DWORD *)DeviceExtension + 42) = 0;
        KeInitializeEvent((PRKEVENT)(DeviceExtension + 176), SynchronizationEvent, 0);
        SourceDevice->Flags &= ~0x80u;
        return 0;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          11,
          (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids);
      v6 = -1073741670;
    }
    else
    {
      SourceDevice = 0;
    }
    ExFreePool(v5);
  }
  else
  {
    v6 = -1073741670;
  }
  if ( SourceDevice )
    IoDeleteDevice(SourceDevice);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001ca00  mov     [rsp-8+arg_10], rbx
0x14001ca05  mov     [rsp-8+arg_18], rsi
0x14001ca0a  push    rbp
0x14001ca0b  push    rdi
0x14001ca0c  push    r12
0x14001ca0e  push    r13
0x14001ca10  push    r14
0x14001ca12  lea     rbp, [rsp-37h]
0x14001ca17  sub     rsp, 0A0h
0x14001ca1e  mov     rax, cs:__security_cookie
0x14001ca25  xor     rax, rsp
0x14001ca28  mov     [rbp+57h+var_30], rax
0x14001ca2c  xorps   xmm0, xmm0
0x14001ca2f  mov     [rbp+57h+SourceDevice], 0
0x14001ca37  xorps   xmm1, xmm1
0x14001ca3a  mov     r14, rdx
0x14001ca3d  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14001ca41  mov     rbx, rcx
0x14001ca44  movups  xmmword ptr [rbp+57h+String.Length], xmm1
0x14001ca48  lea     r12, WPP_RECORDER_INITIALIZED
0x14001ca4f  mov     esi, 0Ah
0x14001ca54  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ca5b  lea     r13, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001ca62  jz      short loc_14001CA80
0x14001ca64  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca6b  lea     r8d, [rsi-7]
0x14001ca6f  mov     r9d, esi
0x14001ca72  mov     qword ptr [rsp+0C0h+DeviceCharacteristics], r13
0x14001ca77  mov     rcx, [rcx+40h]
0x14001ca7b  call    WPP_RECORDER_SF_
0x14001ca80  mov     edx, 102h
0x14001ca85  mov     r8d, 4F4D5442h
0x14001ca8b  lea     ecx, [rdx-2]
0x14001ca8e  call    cs:__imp_ExAllocatePool2
0x14001ca95  nop     dword ptr [rax+rax+00h]
0x14001ca9a  mov     rdi, rax
0x14001ca9d  test    rax, rax
0x14001caa0  jnz     short loc_14001CAAC
0x14001caa2  mov     ebx, 0C000009Ah
0x14001caa7  jmp     loc_14001CBAB
0x14001caac  lea     rdx, Source; "\\Device\\BthEnum"
0x14001cab3  mov     [rbp+57h+Destination.Buffer], rdi
0x14001cab7  lea     rcx, [rbp+57h+Destination]; Destination
0x14001cabb  mov     dword ptr [rbp+57h+Destination.Length], 800000h
0x14001cac2  call    cs:__imp_RtlAppendUnicodeToString
0x14001cac9  nop     dword ptr [rax+rax+00h]
0x14001cace  mov     ecx, dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next; Value
0x14001cad4  lea     rax, [rbp+57h+var_58]
0x14001cad8  mov     [rbp+57h+String.Buffer], rax
0x14001cadc  lea     r8, [rbp+57h+String]; String
0x14001cae0  mov     edx, esi; Base
0x14001cae2  mov     dword ptr [rbp+57h+String.Length], 280000h
0x14001cae9  lea     eax, [rcx+1]
0x14001caec  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, eax
0x14001caf2  call    cs:__imp_RtlIntegerToUnicodeString
0x14001caf9  nop     dword ptr [rax+rax+00h]
0x14001cafe  lea     rdx, [rbp+57h+String]; Source
0x14001cb02  lea     rcx, [rbp+57h+Destination]; Destination
0x14001cb06  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001cb0d  nop     dword ptr [rax+rax+00h]
0x14001cb12  lea     rax, [rbp+57h+SourceDevice]
0x14001cb16  mov     r9d, 15h; DeviceType
0x14001cb1c  mov     [rsp+0C0h+DeviceObject], rax; DeviceObject
0x14001cb21  lea     r8, [rbp+57h+Destination]; DeviceName
0x14001cb25  mov     [rsp+0C0h+Exclusive], 0; Exclusive
0x14001cb2a  mov     edx, 260h; DeviceExtensionSize
0x14001cb2f  mov     rcx, rbx; DriverObject
0x14001cb32  mov     [rsp+0C0h+DeviceCharacteristics], 0; DeviceCharacteristics
0x14001cb3a  call    cs:__imp_IoCreateDevice
0x14001cb41  nop     dword ptr [rax+rax+00h]
0x14001cb46  mov     ebx, eax
0x14001cb48  test    eax, eax
0x14001cb4a  jns     short loc_14001CB56
0x14001cb4c  mov     [rbp+57h+SourceDevice], 0
0x14001cb54  jmp     short loc_14001CB9C
0x14001cb56  mov     rcx, [rbp+57h+SourceDevice]; SourceDevice
0x14001cb5a  mov     rdx, r14; TargetDevice
0x14001cb5d  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14001cb64  nop     dword ptr [rax+rax+00h]
0x14001cb69  mov     rsi, rax
0x14001cb6c  test    rax, rax
0x14001cb6f  jnz     short loc_14001CBC9
0x14001cb71  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001cb78  jz      short loc_14001CB97
0x14001cb7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb81  lea     r9d, [rax+0Bh]
0x14001cb85  lea     r8d, [rax+1]
0x14001cb89  mov     qword ptr [rsp+0C0h+DeviceCharacteristics], r13
0x14001cb8e  mov     rcx, [rcx+40h]
0x14001cb92  call    WPP_RECORDER_SF_
0x14001cb97  mov     ebx, 0C000009Ah
0x14001cb9c  mov     rcx, rdi; P
0x14001cb9f  call    cs:__imp_ExFreePool
0x14001cba6  nop     dword ptr [rax+rax+00h]
0x14001cbab  mov     rcx, [rbp+57h+SourceDevice]; DeviceObject
0x14001cbaf  test    rcx, rcx
0x14001cbb2  jz      loc_14001CC97
0x14001cbb8  call    cs:__imp_IoDeleteDevice
0x14001cbbf  nop     dword ptr [rax+rax+00h]
0x14001cbc4  jmp     loc_14001CC97
0x14001cbc9  mov     rcx, [rbp+57h+SourceDevice]
0x14001cbcd  xor     edx, edx; Val
0x14001cbcf  mov     eax, [rax+30h]
0x14001cbd2  mov     r8d, 25Ch; Size
0x14001cbd8  or      [rcx+30h], eax
0x14001cbdb  mov     cl, [rsi+4Ch]
0x14001cbde  mov     rax, [rbp+57h+SourceDevice]
0x14001cbe2  inc     cl
0x14001cbe4  mov     [rax+4Ch], cl
0x14001cbe7  mov     rax, [rbp+57h+SourceDevice]
0x14001cbeb  mov     rbx, [rax+40h]
0x14001cbef  lea     rcx, [rbx+4]; void *
0x14001cbf3  call    memset
0x14001cbf8  mov     dword ptr [rbx], 204F4446h
0x14001cbfe  lea     rdx, [rbx+50h]
0x14001cc02  mov     rax, [rbp+57h+SourceDevice]
0x14001cc06  lea     rcx, [rbx+40h]
0x14001cc0a  mov     [rbx+8], rax
0x14001cc0e  mov     [rbx+10h], r14
0x14001cc12  mov     [rbx+18h], rsi
0x14001cc16  mov     qword ptr [rbx+0E8h], 0
0x14001cc21  mov     qword ptr [rbx+0F0h], 0
0x14001cc2c  call    IrpList_InitEx
0x14001cc31  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x14001cc35  xor     r8d, r8d; State
0x14001cc38  lea     rcx, [rbx+0B0h]; Event
0x14001cc3f  movdqu  xmmword ptr [rbx+0D8h], xmm0
0x14001cc47  mov     qword ptr [rbx+88h], 0
0x14001cc52  mov     qword ptr [rbx+90h], 0
0x14001cc5d  lea     edx, [r8+1]; Type
0x14001cc61  mov     dword ptr [rbx+98h], 1
0x14001cc6b  mov     qword ptr [rbx+0A0h], 0
0x14001cc76  mov     dword ptr [rbx+0A8h], 0
0x14001cc80  call    cs:__imp_KeInitializeEvent
0x14001cc87  nop     dword ptr [rax+rax+00h]
0x14001cc8c  mov     rax, [rbp+57h+SourceDevice]
0x14001cc90  btr     dword ptr [rax+30h], 7
0x14001cc95  xor     ebx, ebx
0x14001cc97  mov     eax, ebx
0x14001cc99  mov     rcx, [rbp+57h+var_30]
0x14001cc9d  xor     rcx, rsp; StackCookie
0x14001cca0  call    __security_check_cookie
0x14001cca5  lea     r11, [rsp+0C0h+var_20]
0x14001ccad  mov     rbx, [r11+40h]
0x14001ccb1  mov     rsi, [r11+48h]
0x14001ccb5  mov     rsp, r11
0x14001ccb8  pop     r14
0x14001ccba  pop     r13
0x14001ccbc  pop     r12
0x14001ccbe  pop     rdi
0x14001ccbf  pop     rbp
0x14001ccc0  retn
```
