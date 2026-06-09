# Command_Initialize

- ea: `0x14001bac8`
- end: `0x14001bb70`
- name: `Command_Initialize`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001b8ac`
- `0x14003d1f8`

## callees

- `0x14001bac8`
- `0x14001bb78`
- `0x14001bbd0`
- `0x14001fb30`
- `0x140039674`
- `0x140057de4`

## string_xrefs

- `0x14001bae0`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\command.c`
- `0x14001bb10`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\command.c`
- `0x14001bb25`: `WaitingList is not empty on re-initialization of the command ring.`
- `0x14001baf5`: `PendingList is not empty on re-initialization of the command ring.`

## pseudocode

```c
__int64 __fastcall Command_Initialize(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 80) != a1 + 80 )
  {
    Debug_FreAssertMsg("PendingList must be empty", 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\command.c", 413);
    MicrosoftTelemetryAssertTriggeredMsgKM("PendingList is not empty on re-initialization of the command ring.");
  }
  if ( *(_QWORD *)(a1 + 96) != a1 + 96 )
  {
    Debug_FreAssertMsg("WaitingList must be empty", 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\command.c", 419);
    MicrosoftTelemetryAssertTriggeredMsgKM("WaitingList is not empty on re-initialization of the command ring.");
  }
  result = Controller_IsControllerAccessible(*(_QWORD *)(a1 + 8));
  if ( (_BYTE)result )
  {
    if ( *(_BYTE *)(a1 + 136) )
      result = XilCommand_InitializeSecureResources();
    else
      result = XilCoreCommand_Initialize(a1 + 168);
    *(_QWORD *)(a1 + 40) = 0;
    *(_DWORD *)(a1 + 64) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x14001bac8  push    rbx
0x14001baca  sub     rsp, 20h
0x14001bace  lea     rax, [rcx+50h]
0x14001bad2  mov     rbx, rcx
0x14001bad5  cmp     [rax], rax
0x14001bad8  jz      short loc_14001BB01
0x14001bada  mov     r9d, 19Dh
0x14001bae0  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14001bae7  xor     edx, edx
0x14001bae9  lea     rcx, aPendinglistMus; "PendingList must be empty"
0x14001baf0  call    Debug_FreAssertMsg
0x14001baf5  lea     rcx, aPendinglistIsN; __annotation("Debug", "TelemetryAssert", "FALSE", "PendingList is not empty on re-initialization of the command ring.")
0x14001bafc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bb01  lea     rax, [rbx+60h]
0x14001bb05  cmp     [rax], rax
0x14001bb08  jz      short loc_14001BB31
0x14001bb0a  mov     r9d, 1A3h
0x14001bb10  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14001bb17  xor     edx, edx
0x14001bb19  lea     rcx, aWaitinglistMus; "WaitingList must be empty"
0x14001bb20  call    Debug_FreAssertMsg
0x14001bb25  lea     rcx, aWaitinglistIsN; __annotation("Debug", "TelemetryAssert", "FALSE", "WaitingList is not empty on re-initialization of the command ring.")
0x14001bb2c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bb31  mov     rcx, [rbx+8]
0x14001bb35  call    Controller_IsControllerAccessible
0x14001bb3a  test    al, al
0x14001bb3c  jz      short loc_14001BB62
0x14001bb3e  lea     rcx, [rbx+88h]
0x14001bb45  cmp     byte ptr [rcx], 0
0x14001bb48  jnz     short loc_14001BB69
0x14001bb4a  add     rcx, 20h ; ' '
0x14001bb4e  call    XilCoreCommand_Initialize
0x14001bb53  mov     qword ptr [rbx+28h], 0
0x14001bb5b  mov     dword ptr [rbx+40h], 1
0x14001bb62  add     rsp, 20h
0x14001bb66  pop     rbx
0x14001bb67  retn
0x14001bb69  call    XilCommand_InitializeSecureResources
0x14001bb6e  jmp     short loc_14001BB53
```
