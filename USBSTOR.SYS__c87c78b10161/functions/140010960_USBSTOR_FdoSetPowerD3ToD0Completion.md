# USBSTOR_FdoSetPowerD3ToD0Completion

- ea: `0x140010960`
- end: `0x1400109d1`
- name: `USBSTOR_FdoSetPowerD3ToD0Completion`
- size: `113`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x1400103a4`
- `0x140010664`
- `0x140010960`

## pseudocode

```c
void __fastcall USBSTOR_FdoSetPowerD3ToD0Completion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        struct _DEVICE_OBJECT *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 179, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(809775940, Context, DeviceObject, IoStatus->Status);
  USBSTOR_FdoSetPowerSx(Context);
}

```

## disassembly

```asm
0x140010960  mov     [rsp+arg_0], rbx
0x140010965  push    rdi
0x140010966  sub     rsp, 20h
0x14001096a  mov     rbx, r9
0x14001096d  mov     rdi, rcx
0x140010970  mov     rcx, cs:WPP_GLOBAL_Control
0x140010977  lea     rax, WPP_GLOBAL_Control
0x14001097e  cmp     rcx, rax
0x140010981  jz      short loc_1400109A5
0x140010983  mov     eax, [rcx+2Ch]
0x140010986  test    al, 4
0x140010988  jz      short loc_1400109A5
0x14001098a  cmp     byte ptr [rcx+29h], 4
0x14001098e  jb      short loc_1400109A5
0x140010990  mov     rcx, [rcx+18h]
0x140010994  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001099b  mov     edx, 0B3h
0x1400109a0  call    WPP_SF_
0x1400109a5  mov     rax, [rsp+28h+IoStatus]
0x1400109aa  mov     r8, rdi
0x1400109ad  mov     rdx, rbx
0x1400109b0  mov     ecx, 30443344h
0x1400109b5  movsxd  r9, dword ptr [rax]
0x1400109b8  call    USBSTOR_LogEntry
0x1400109bd  mov     rcx, rbx; DeviceObject
0x1400109c0  call    USBSTOR_FdoSetPowerSx
0x1400109c5  mov     rbx, [rsp+28h+arg_0]
0x1400109ca  add     rsp, 20h
0x1400109ce  pop     rdi
0x1400109cf  retn
```
