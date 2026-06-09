# USBSTOR_PdoFxPowerCompletion

- ea: `0x14000e060`
- end: `0x14000e0dc`
- name: `USBSTOR_PdoFxPowerCompletion`
- size: `124`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000dfac`

## callees

- `0x140003630`
- `0x14000e060`
- `0x14000e0e4`

## import_xrefs

- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14000e0b5`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14000e0b5`

## pseudocode

```c
void __fastcall USBSTOR_PdoFxPowerCompletion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        int *Context)
{
  USBSTOR_LogEntry(1131963504, DeviceObject, PowerState.SystemState, Context[491]);
  if ( _InterlockedExchangeAdd(Context + 491, 0xFFFFFFFF) == 1 )
  {
    if ( PowerState.SystemState == PowerSystemWorking )
    {
      USBSTOR_LogEntry(1919973478, Context, 0, 0);
      PoFxReportDevicePoweredOn(*((_QWORD *)Context + 246));
    }
    else
    {
      USBSTOR_RequestFdoFxPowerIrp(Context, (POWER_STATE)4);
    }
  }
}

```

## disassembly

```asm
0x14000e060  mov     [rsp+arg_0], rbx
0x14000e065  push    rdi
0x14000e066  sub     rsp, 20h
0x14000e06a  movsxd  rbx, r8d
0x14000e06d  mov     rdi, r9
0x14000e070  movsxd  r9, dword ptr [r9+7ACh]
0x14000e077  mov     rdx, rcx
0x14000e07a  mov     r8, rbx
0x14000e07d  mov     ecx, 43786470h
0x14000e082  call    USBSTOR_LogEntry
0x14000e087  or      eax, 0FFFFFFFFh
0x14000e08a  lock xadd [rdi+7ACh], eax
0x14000e092  cmp     eax, 1
0x14000e095  jnz     short loc_14000E0D0
0x14000e097  cmp     ebx, eax
0x14000e099  jnz     short loc_14000E0C3
0x14000e09b  xor     r9d, r9d
0x14000e09e  xor     r8d, r8d
0x14000e0a1  mov     rdx, rdi
0x14000e0a4  mov     ecx, 72707866h
0x14000e0a9  call    USBSTOR_LogEntry
0x14000e0ae  mov     rcx, [rdi+7B0h]
0x14000e0b5  call    cs:__imp_PoFxReportDevicePoweredOn
0x14000e0bc  nop     dword ptr [rax+rax+00h]
0x14000e0c1  jmp     short loc_14000E0D0
0x14000e0c3  mov     edx, 4; PowerState
0x14000e0c8  mov     rcx, rdi; Context
0x14000e0cb  call    USBSTOR_RequestFdoFxPowerIrp
0x14000e0d0  mov     rbx, [rsp+28h+arg_0]
0x14000e0d5  add     rsp, 20h
0x14000e0d9  pop     rdi
0x14000e0da  retn
```
