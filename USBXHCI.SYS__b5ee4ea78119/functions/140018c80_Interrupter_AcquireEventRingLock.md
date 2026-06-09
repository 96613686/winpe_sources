# Interrupter_AcquireEventRingLock

- ea: `0x140018c80`
- end: `0x140018d85`
- name: `Interrupter_AcquireEventRingLock`
- size: `261`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140018ac8`
- `0x14002ed98`
- `0x140049644`
- `0x140049860`

## callees

- `0x1400110e0`
- `0x140018c80`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140018d11`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140018d11`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018cd3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018cf1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018cd3`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018cf1`

## string_xrefs

- `0x140018d5a`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Interrupter_AcquireEventRingLock(__int64 a1)
{
  unsigned __int8 v1; // di
  __int64 v3; // rbx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d

  v1 = 0;
  if ( *(_BYTE *)(a1 + 232) && KeGetCurrentIrql() == 2 )
  {
    Controller_LowerAndTrackIrql(*(_QWORD *)(a1 + 8));
    v1 = 1;
  }
  v3 = *(_QWORD *)(a1 + 224);
  if ( *(_DWORD *)v3 == 1 )
  {
    if ( KeGetCurrentIrql() )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v5, v6, v7);
      if ( !KdRefreshDebuggerNotPresent() )
        __debugbreak();
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2504))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 8),
      0);
    return v1;
  }
  else
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2528))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 8));
    return v1;
  }
}

```

## disassembly

```asm
0x140018c80  mov     [rsp+arg_0], rbx
0x140018c85  push    rdi
0x140018c86  sub     rsp, 40h
0x140018c8a  xor     dil, dil
0x140018c8d  mov     rbx, rcx
0x140018c90  cmp     [rcx+0E8h], dil
0x140018c97  jnz     short loc_140018CD3
0x140018c99  mov     rbx, [rbx+0E0h]
0x140018ca0  cmp     dword ptr [rbx], 1
0x140018ca3  jz      short loc_140018CF1
0x140018ca5  mov     rax, cs:WdfFunctions_01033
0x140018cac  mov     rdx, [rbx+8]
0x140018cb0  mov     rcx, cs:WdfDriverGlobals
0x140018cb7  mov     rax, [rax+9E0h]
0x140018cbe  call    _guard_dispatch_icall
0x140018cc3  movzx   eax, dil
0x140018cc7  mov     rbx, [rsp+48h+arg_0]
0x140018ccc  add     rsp, 40h
0x140018cd0  pop     rdi
0x140018cd1  retn
0x140018cd3  call    cs:__imp_KeGetCurrentIrql
0x140018cda  nop     dword ptr [rax+rax+00h]
0x140018cdf  cmp     al, 2
0x140018ce1  jnz     short loc_140018C99
0x140018ce3  mov     rcx, [rbx+8]
0x140018ce7  call    Controller_LowerAndTrackIrql
0x140018cec  mov     dil, 1
0x140018cef  jmp     short loc_140018C99
0x140018cf1  call    cs:__imp_KeGetCurrentIrql
0x140018cf8  nop     dword ptr [rax+rax+00h]
0x140018cfd  test    al, al
0x140018cff  jz      short loc_140018D22
0x140018d01  lea     rax, WPP_RECORDER_INITIALIZED
0x140018d08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018d0f  jnz     short loc_140018D53
0x140018d11  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140018d18  nop     dword ptr [rax+rax+00h]
0x140018d1d  test    al, al
0x140018d1f  jnz     short loc_140018D22
0x140018d21  int     3; Trap to Debugger
0x140018d22  mov     rcx, cs:WdfFunctions_01033
0x140018d29  xor     r8d, r8d
0x140018d2c  mov     rdx, [rbx+8]
0x140018d30  mov     rax, [rcx+9C8h]
0x140018d37  mov     rcx, cs:WdfDriverGlobals
0x140018d3e  call    _guard_dispatch_icall
0x140018d43  mov     rbx, [rsp+48h+arg_0]
0x140018d48  movzx   eax, dil
0x140018d4c  add     rsp, 40h
0x140018d50  pop     rdi
0x140018d51  retn
0x140018d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d5a  lea     rax, aCodePathRequir; "Code Path Requires Passive Level"
0x140018d61  mov     [rsp+48h+var_10], rax
0x140018d66  lea     rax, aOnecoreDrivers_15; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140018d6d  mov     [rsp+48h+var_18], 58h ; 'X'
0x140018d75  mov     [rsp+48h+var_20], rax
0x140018d7a  mov     rcx, [rcx+40h]
0x140018d7e  call    WPP_RECORDER_SF_sds
0x140018d83  jmp     short loc_140018D11
```
