# USBSTOR_PreInitializeEmergencyWorkerThread

- ea: `0x140010694`
- end: `0x1400106b9`
- name: `USBSTOR_PreInitializeEmergencyWorkerThread`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14002890c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400106a7`
- `ntoskrnl!KeInitializeEvent` at `0x1400106a7`

## pseudocode

```c
void USBSTOR_PreInitializeEmergencyWorkerThread()
{
  KeInitializeEvent(&EmergencyWorkerThreadEvent, SynchronizationEvent, 1u);
}

```

## disassembly

```asm
0x140010694  sub     rsp, 28h
0x140010698  mov     r8b, 1; State
0x14001069b  lea     rcx, EmergencyWorkerThreadEvent; Event
0x1400106a2  mov     edx, 1; Type
0x1400106a7  call    cs:__imp_KeInitializeEvent
0x1400106ae  nop     dword ptr [rax+rax+00h]
0x1400106b3  add     rsp, 28h
0x1400106b7  retn
```
