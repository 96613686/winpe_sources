# Device_WdfEvtCleanupCallback

- ea: `0x140044940`
- end: `0x1400449ea`
- name: `Device_WdfEvtCleanupCallback`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140044940`
- `0x1400599b0`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x140044987`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140044987`

## pseudocode

```c
__int64 __fastcall Device_WdfEvtCleanupCallback(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 result; // rax
  __int64 v4; // rdx

  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C2C0);
  v2 = v1;
  if ( *(_QWORD *)(v1 + 96) )
    *(_QWORD *)(v1 + 96) = 0;
  result = imp_WppRecorderLogDelete(WPP_GLOBAL_Control, *(_QWORD *)(v1 + 16));
  v4 = *(_QWORD *)(v2 + 8);
  *(_QWORD *)(v2 + 16) = 0;
  if ( v4 )
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 (__fastcall *)(__int64, __int64), __int64, const char *))(WdfFunctions_01033 + 1648))(
               WdfDriverGlobals,
               *(_QWORD *)(v4 + 8),
               Controller_WdfEvtDeviceAdd,
               3503,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c");
    *(_QWORD *)(v2 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140044940  push    rbx
0x140044942  sub     rsp, 30h
0x140044946  mov     rax, cs:WdfFunctions_01033
0x14004494d  mov     rdx, rcx
0x140044950  mov     r8, cs:off_14006C2C0
0x140044957  mov     rcx, cs:WdfDriverGlobals
0x14004495e  mov     rax, [rax+650h]
0x140044965  call    _guard_dispatch_icall
0x14004496a  mov     rbx, rax
0x14004496d  cmp     qword ptr [rax+60h], 0
0x140044972  jz      short loc_14004497C
0x140044974  mov     qword ptr [rax+60h], 0
0x14004497c  mov     rdx, [rax+10h]
0x140044980  mov     rcx, cs:WPP_GLOBAL_Control
0x140044987  call    cs:__imp_imp_WppRecorderLogDelete
0x14004498e  nop     dword ptr [rax+rax+00h]
0x140044993  mov     rdx, [rbx+8]
0x140044997  mov     qword ptr [rbx+10h], 0
0x14004499f  test    rdx, rdx
0x1400449a2  jz      short loc_1400449E3
0x1400449a4  mov     rax, cs:WdfFunctions_01033
0x1400449ab  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400449b2  mov     rdx, [rdx+8]
0x1400449b6  lea     r8, Controller_WdfEvtDeviceAdd
0x1400449bd  mov     [rsp+38h+var_18], rcx
0x1400449c2  mov     r9d, 0DAFh
0x1400449c8  mov     rcx, cs:WdfDriverGlobals
0x1400449cf  mov     rax, [rax+670h]
0x1400449d6  call    _guard_dispatch_icall
0x1400449db  mov     qword ptr [rbx+8], 0
0x1400449e3  add     rsp, 30h
0x1400449e7  pop     rbx
0x1400449e8  retn
```
