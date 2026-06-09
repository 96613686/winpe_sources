# USBSTOR_FdoFxPowerCompletion

- ea: `0x14000df00`
- end: `0x14000dfa4`
- name: `USBSTOR_FdoFxPowerCompletion`
- size: `164`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x14000df00`
- `0x14000dfac`

## import_xrefs

- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14000df87`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x14000df87`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x14000df5e`
- `ntoskrnl!PoFxCompleteDirectedPowerDown` at `0x14000df5e`

## pseudocode

```c
void __fastcall USBSTOR_FdoFxPowerCompletion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        PVOID Context)
{
  __int64 SystemState; // rbx

  SystemState = PowerState.SystemState;
  USBSTOR_LogEntry(1668315238, DeviceObject, Context, PowerState.SystemState);
  if ( (_DWORD)SystemState == 1 )
  {
    USBSTOR_RequestChildPdosFxPowerIrps(Context);
  }
  else if ( *((_BYTE *)Context + 1963) )
  {
    USBSTOR_LogEntry(1684306022, Context, SystemState, 0);
    PoFxCompleteDirectedPowerDown(*((_QWORD *)Context + 246));
    *((_BYTE *)Context + 1963) = 0;
  }
  else
  {
    USBSTOR_LogEntry(1852864614, Context, 0, 0);
    PoFxCompleteDevicePowerNotRequired(*((_QWORD *)Context + 246));
  }
}

```

## disassembly

```asm
0x14000df00  mov     [rsp+arg_0], rbx
0x14000df05  mov     [rsp+arg_8], rsi
0x14000df0a  push    rdi
0x14000df0b  sub     rsp, 20h
0x14000df0f  mov     rdi, r9
0x14000df12  movsxd  rbx, r8d
0x14000df15  mov     rdx, rcx
0x14000df18  mov     r9, rbx
0x14000df1b  mov     r8, rdi
0x14000df1e  mov     ecx, 63707866h
0x14000df23  call    USBSTOR_LogEntry
0x14000df28  mov     edx, 1
0x14000df2d  cmp     ebx, edx
0x14000df2f  jnz     short loc_14000DF3B
0x14000df31  mov     rcx, rdi; Context
0x14000df34  call    USBSTOR_RequestChildPdosFxPowerIrps
0x14000df39  jmp     short loc_14000DF93
0x14000df3b  xor     r9d, r9d
0x14000df3e  mov     rdx, rdi
0x14000df41  cmp     [rdi+7ABh], r9b
0x14000df48  jz      short loc_14000DF73
0x14000df4a  mov     r8, rbx
0x14000df4d  mov     ecx, 64647866h
0x14000df52  call    USBSTOR_LogEntry
0x14000df57  mov     rcx, [rdi+7B0h]
0x14000df5e  call    cs:__imp_PoFxCompleteDirectedPowerDown
0x14000df65  nop     dword ptr [rax+rax+00h]
0x14000df6a  mov     byte ptr [rdi+7ABh], 0
0x14000df71  jmp     short loc_14000DF93
0x14000df73  xor     r8d, r8d
0x14000df76  mov     ecx, 6E707866h
0x14000df7b  call    USBSTOR_LogEntry
0x14000df80  mov     rcx, [rdi+7B0h]
0x14000df87  call    cs:__imp_PoFxCompleteDevicePowerNotRequired
0x14000df8e  nop     dword ptr [rax+rax+00h]
0x14000df93  mov     rbx, [rsp+28h+arg_0]
0x14000df98  mov     rsi, [rsp+28h+arg_8]
0x14000df9d  add     rsp, 20h
0x14000dfa1  pop     rdi
0x14000dfa2  retn
```
