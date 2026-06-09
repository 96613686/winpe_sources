# DynamicLock_Acquire

- ea: `0x1400218a0`
- end: `0x14002195e`
- name: `DynamicLock_Acquire`
- size: `190`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017890`
- `0x14001ca48`
- `0x1400216b8`
- `0x140021830`
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

- `0x1400218a0`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400218f3`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400218f3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400218d3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400218d3`

## string_xrefs

- `0x140021933`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall DynamicLock_Acquire(__int64 a1)
{
  int v3; // edx
  int v4; // r8d
  int v5; // r9d

  if ( *(_DWORD *)a1 != 1 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2528))(
             WdfDriverGlobals,
             *(_QWORD *)(a1 + 8));
  if ( KeGetCurrentIrql() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v3, v4, v5);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2504))(
           WdfDriverGlobals,
           *(_QWORD *)(a1 + 8),
           0);
}

```

## disassembly

```asm
0x1400218a0  push    rbx
0x1400218a2  sub     rsp, 40h
0x1400218a6  cmp     dword ptr [rcx], 1
0x1400218a9  mov     rbx, rcx
0x1400218ac  jz      short loc_1400218D3
0x1400218ae  mov     rax, cs:WdfFunctions_01033
0x1400218b5  mov     rdx, [rcx+8]
0x1400218b9  mov     rcx, cs:WdfDriverGlobals
0x1400218c0  mov     rax, [rax+9E0h]
0x1400218c7  call    _guard_dispatch_icall
0x1400218cc  add     rsp, 40h
0x1400218d0  pop     rbx
0x1400218d1  retn
0x1400218d3  call    cs:__imp_KeGetCurrentIrql
0x1400218da  nop     dword ptr [rax+rax+00h]
0x1400218df  test    al, al
0x1400218e1  jz      short loc_140021904
0x1400218e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400218ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400218f1  jnz     short loc_14002192C
0x1400218f3  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400218fa  nop     dword ptr [rax+rax+00h]
0x1400218ff  test    al, al
0x140021901  jnz     short loc_140021904
0x140021903  int     3; Trap to Debugger
0x140021904  mov     rax, cs:WdfFunctions_01033
0x14002190b  xor     r8d, r8d
0x14002190e  mov     rdx, [rbx+8]
0x140021912  mov     rcx, cs:WdfDriverGlobals
0x140021919  mov     rax, [rax+9C8h]
0x140021920  call    _guard_dispatch_icall
0x140021925  add     rsp, 40h
0x140021929  pop     rbx
0x14002192a  retn
0x14002192c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021933  lea     rax, aCodePathRequir; "Code Path Requires Passive Level"
0x14002193a  mov     [rsp+48h+var_10], rax
0x14002193f  lea     rax, aOnecoreDrivers_15; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140021946  mov     [rsp+48h+var_18], 58h ; 'X'
0x14002194e  mov     [rsp+48h+var_20], rax
0x140021953  mov     rcx, [rcx+40h]
0x140021957  call    WPP_RECORDER_SF_sds
0x14002195c  jmp     short loc_1400218F3
```
