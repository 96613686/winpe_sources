# DynamicLock_Release

- ea: `0x1400219b0`
- end: `0x140021a6b`
- name: `DynamicLock_Release`
- size: `187`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017890`
- `0x14001ca48`
- `0x1400216b8`
- `0x140021964`
- `0x140021f3c`
- `0x1400224d0`
- `0x140022850`
- `0x140022b1c`
- `0x140023490`
- `0x14002390c`
- `0x14003d1f8`
- `0x14003d8a4`
- `0x14003d970`
- `0x14003de60`
- `0x1400409c0`
- `0x140040b90`
- `0x140040c6c`
- `0x1400412a4`
- `0x1400416f8`
- `0x140042bc0`
- `0x1400434e0`
- `0x140043750`

## callees

- `0x1400219b0`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140021a03`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140021a03`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400219e3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400219e3`

## string_xrefs

- `0x140021a40`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall DynamicLock_Release(__int64 a1)
{
  int v3; // edx
  int v4; // r8d
  int v5; // r9d

  if ( *(_DWORD *)a1 != 1 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2536))(
             WdfDriverGlobals,
             *(_QWORD *)(a1 + 8));
  if ( KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v3, v4, v5);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2512))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x1400219b0  push    rbx
0x1400219b2  sub     rsp, 40h
0x1400219b6  cmp     dword ptr [rcx], 1
0x1400219b9  mov     rbx, rcx
0x1400219bc  jz      short loc_1400219E3
0x1400219be  mov     rax, cs:WdfFunctions_01033
0x1400219c5  mov     rdx, [rcx+8]
0x1400219c9  mov     rcx, cs:WdfDriverGlobals
0x1400219d0  mov     rax, [rax+9E8h]
0x1400219d7  call    _guard_dispatch_icall
0x1400219dc  add     rsp, 40h
0x1400219e0  pop     rbx
0x1400219e1  retn
0x1400219e3  call    cs:__imp_KeGetCurrentIrql
0x1400219ea  nop     dword ptr [rax+rax+00h]
0x1400219ef  test    al, al
0x1400219f1  jz      short loc_140021A14
0x1400219f3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400219fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021a01  jnz     short loc_140021A39
0x140021a03  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140021a0a  nop     dword ptr [rax+rax+00h]
0x140021a0f  test    al, al
0x140021a11  jnz     short loc_140021A14
0x140021a13  int     3; Trap to Debugger
0x140021a14  mov     rax, cs:WdfFunctions_01033
0x140021a1b  mov     rdx, [rbx+8]
0x140021a1f  mov     rcx, cs:WdfDriverGlobals
0x140021a26  mov     rax, [rax+9D0h]
0x140021a2d  call    _guard_dispatch_icall
0x140021a32  add     rsp, 40h
0x140021a36  pop     rbx
0x140021a37  retn
0x140021a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a40  lea     rax, aCodePathRequir; "Code Path Requires Passive Level"
0x140021a47  mov     [rsp+48h+var_10], rax
0x140021a4c  lea     rax, aOnecoreDrivers_15; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140021a53  mov     [rsp+48h+var_18], 6Bh ; 'k'
0x140021a5b  mov     [rsp+48h+var_20], rax
0x140021a60  mov     rcx, [rcx+40h]
0x140021a64  call    WPP_RECORDER_SF_sds
0x140021a69  jmp     short loc_140021A03
```
