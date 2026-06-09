# XilUsbDevice_GetDeviceContextBufferSize

- ea: `0x14003c488`
- end: `0x14003c4ff`
- name: `XilUsbDevice_GetDeviceContextBufferSize`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140025048`

## callees

- `0x14003c488`
- `0x140046070`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14003c4d5`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14003c4d5`

## string_xrefs

- `0x14003c4ac`: `Cannot access device context directly when in secure mode`

## pseudocode

```c
__int64 __fastcall XilUsbDevice_GetDeviceContextBufferSize(__int64 a1, int a2, int a3, int a4)
{
  __int64 v5; // rax

  if ( *(_BYTE *)(a1 + 665) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
    if ( !KdRefreshDebuggerNotPresent() )
      __debugbreak();
    return 0;
  }
  v5 = *(_QWORD *)(a1 + 640);
  if ( !v5 )
    return 0;
  return *(unsigned int *)(v5 + 44);
}

```

## disassembly

```asm
0x14003c488  sub     rsp, 48h
0x14003c48c  cmp     byte ptr [rcx+299h], 0
0x14003c493  jz      short loc_14003C4EE
0x14003c495  lea     rax, WPP_RECORDER_INITIALIZED
0x14003c49c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003c4a3  jz      short loc_14003C4D5
0x14003c4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c4ac  lea     rax, aCannotAccessDe; "Cannot access device context directly w"...
0x14003c4b3  mov     [rsp+48h+var_10], rax
0x14003c4b8  lea     rax, aOnecoreDrivers_10; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003c4bf  mov     [rsp+48h+var_18], 1AAh
0x14003c4c7  mov     [rsp+48h+var_20], rax
0x14003c4cc  mov     rcx, [rcx+40h]
0x14003c4d0  call    WPP_RECORDER_SF_sds
0x14003c4d5  call    cs:__imp_KdRefreshDebuggerNotPresent
0x14003c4dc  nop     dword ptr [rax+rax+00h]
0x14003c4e1  test    al, al
0x14003c4e3  jnz     short loc_14003C4E6
0x14003c4e5  int     3; Trap to Debugger
0x14003c4e6  xor     eax, eax
0x14003c4e8  add     rsp, 48h
0x14003c4ec  retn
0x14003c4ee  mov     rax, [rcx+280h]
0x14003c4f5  test    rax, rax
0x14003c4f8  jz      short loc_14003C4E6
0x14003c4fa  mov     eax, [rax+2Ch]
0x14003c4fd  jmp     short loc_14003C4E8
```
