# USBSTOR_RequestFdoFxPowerIrp

- ea: `0x14000e0e4`
- end: `0x14000e118`
- name: `USBSTOR_RequestFdoFxPowerIrp`
- size: `52`
- prototype: `__int64 __fastcall(PVOID Context, POWER_STATE PowerState)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000e060`
- `0x14000f280`
- `0x14000f320`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x14000e106`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000e106`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_RequestFdoFxPowerIrp(PDEVICE_OBJECT *Context, POWER_STATE PowerState)
{
  return PoRequestPowerIrp(
           Context[1],
           2u,
           PowerState,
           (PREQUEST_POWER_COMPLETE)USBSTOR_FdoFxPowerCompletion,
           Context,
           0);
}

```

## disassembly

```asm
0x14000e0e4  sub     rsp, 38h
0x14000e0e8  mov     r8d, edx; PowerState
0x14000e0eb  mov     [rsp+38h+Irp], 0; Irp
0x14000e0f4  mov     [rsp+38h+Context], rcx; Context
0x14000e0f9  lea     r9, USBSTOR_FdoFxPowerCompletion; CompletionFunction
0x14000e100  mov     rcx, [rcx+8]; DeviceObject
0x14000e104  mov     dl, 2; MinorFunction
0x14000e106  call    cs:__imp_PoRequestPowerIrp
0x14000e10d  nop     dword ptr [rax+rax+00h]
0x14000e112  add     rsp, 38h
0x14000e116  retn
```
