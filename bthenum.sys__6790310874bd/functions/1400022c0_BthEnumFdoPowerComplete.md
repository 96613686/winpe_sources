# BthEnumFdoPowerComplete

- ea: `0x1400022c0`
- end: `0x140002320`
- name: `BthEnumFdoPowerComplete`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400022c0`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x1400022fc`
- `ntoskrnl!PoSetPowerState` at `0x1400022fc`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000230b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000230b`

## pseudocode

```c
__int64 __fastcall BthEnumFdoPowerComplete(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  $77775CA9583EF2DE25120AC31E027D8D *v2; // r8
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  POWER_STATE v5; // r8d

  v2 = &a2->Tail.Overlay.64;
  if ( a2->PendingReturned )
    v2->CurrentStackLocation->Control |= 1u;
  CurrentStackLocation = v2->CurrentStackLocation;
  if ( CurrentStackLocation->MinorFunction == 2 && CurrentStackLocation->Parameters.Create.Options == 1 )
  {
    v5.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
    *((POWER_STATE *)a1->DeviceExtension + 9) = v5;
    PoSetPowerState(a1, DevicePowerState, v5);
  }
  PoStartNextPowerIrp(a2);
  return 0;
}

```

## disassembly

```asm
0x1400022c0  push    rbx
0x1400022c2  sub     rsp, 20h
0x1400022c6  cmp     byte ptr [rdx+41h], 0
0x1400022ca  lea     r8, [rdx+0B8h]
0x1400022d1  mov     rbx, rdx
0x1400022d4  jz      short loc_1400022DD
0x1400022d6  mov     rax, [r8]
0x1400022d9  or      byte ptr [rax+3], 1
0x1400022dd  mov     r8, [r8]
0x1400022e0  cmp     byte ptr [r8+1], 2
0x1400022e5  jnz     short loc_140002308
0x1400022e7  mov     edx, [r8+10h]; Type
0x1400022eb  cmp     edx, 1
0x1400022ee  jnz     short loc_140002308
0x1400022f0  mov     rax, [rcx+40h]
0x1400022f4  mov     r8d, [r8+18h]; State
0x1400022f8  mov     [rax+24h], r8d
0x1400022fc  call    cs:__imp_PoSetPowerState
0x140002303  nop     dword ptr [rax+rax+00h]
0x140002308  mov     rcx, rbx; Irp
0x14000230b  call    cs:__imp_PoStartNextPowerIrp
0x140002312  nop     dword ptr [rax+rax+00h]
0x140002317  xor     eax, eax
0x140002319  add     rsp, 20h
0x14000231d  pop     rbx
0x14000231e  retn
```
