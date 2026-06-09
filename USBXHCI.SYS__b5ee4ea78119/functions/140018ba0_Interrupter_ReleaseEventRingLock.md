# Interrupter_ReleaseEventRingLock

- ea: `0x140018ba0`
- end: `0x140018c73`
- name: `Interrupter_ReleaseEventRingLock`
- size: `211`
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

- `0x140010d40`
- `0x140018ba0`
- `0x140046070`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140018c20`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140018c20`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018c00`
- `ntoskrnl!KeGetCurrentIrql` at `0x140018c00`

## string_xrefs

- `0x140018c48`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Interrupter_ReleaseEventRingLock(__int64 a1, char a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d

  v2 = *(_QWORD *)(a1 + 224);
  if ( *(_DWORD *)v2 == 1 )
  {
    if ( KeGetCurrentIrql() )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, v6, v7, v8);
      if ( !KdRefreshDebuggerNotPresent() )
        __debugbreak();
    }
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2512))(
               WdfDriverGlobals,
               *(_QWORD *)(v2 + 8));
  }
  else
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 2536))(
               WdfDriverGlobals,
               *(_QWORD *)(v2 + 8));
  }
  if ( a2 )
    return Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
  return result;
}

```

## disassembly

```asm
0x140018ba0  mov     [rsp+arg_0], rbx
0x140018ba5  mov     [rsp+arg_8], rsi
0x140018baa  push    rdi
0x140018bab  sub     rsp, 40h
0x140018baf  mov     rbx, [rcx+0E0h]
0x140018bb6  movzx   edi, dl
0x140018bb9  mov     rsi, rcx
0x140018bbc  cmp     dword ptr [rbx], 1
0x140018bbf  jz      short loc_140018C00
0x140018bc1  mov     rax, cs:WdfFunctions_01033
0x140018bc8  mov     rax, [rax+9E8h]
0x140018bcf  mov     rdx, [rbx+8]
0x140018bd3  mov     rcx, cs:WdfDriverGlobals
0x140018bda  call    _guard_dispatch_icall
0x140018bdf  test    dil, dil
0x140018be2  jnz     short loc_140018BF5
0x140018be4  mov     rbx, [rsp+48h+arg_0]
0x140018be9  mov     rsi, [rsp+48h+arg_8]
0x140018bee  add     rsp, 40h
0x140018bf2  pop     rdi
0x140018bf3  retn
0x140018bf5  mov     rcx, [rsi+8]
0x140018bf9  call    Controller_RaiseAndTrackIrql
0x140018bfe  jmp     short loc_140018BE4
0x140018c00  call    cs:__imp_KeGetCurrentIrql
0x140018c07  nop     dword ptr [rax+rax+00h]
0x140018c0c  test    al, al
0x140018c0e  jz      short loc_140018C31
0x140018c10  lea     rax, WPP_RECORDER_INITIALIZED
0x140018c17  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018c1e  jnz     short loc_140018C41
0x140018c20  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140018c27  nop     dword ptr [rax+rax+00h]
0x140018c2c  test    al, al
0x140018c2e  jnz     short loc_140018C31
0x140018c30  int     3; Trap to Debugger
0x140018c31  mov     rax, cs:WdfFunctions_01033
0x140018c38  mov     rax, [rax+9D0h]
0x140018c3f  jmp     short loc_140018BCF
0x140018c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c48  lea     rax, aCodePathRequir; "Code Path Requires Passive Level"
0x140018c4f  mov     [rsp+48h+var_10], rax
0x140018c54  lea     rax, aOnecoreDrivers_15; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140018c5b  mov     [rsp+48h+var_18], 6Bh ; 'k'
0x140018c63  mov     [rsp+48h+var_20], rax
0x140018c68  mov     rcx, [rcx+40h]
0x140018c6c  call    WPP_RECORDER_SF_sds
0x140018c71  jmp     short loc_140018C20
```
