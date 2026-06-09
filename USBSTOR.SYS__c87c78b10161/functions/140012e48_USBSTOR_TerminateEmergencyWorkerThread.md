# USBSTOR_TerminateEmergencyWorkerThread

- ea: `0x140012e48`
- end: `0x140012eed`
- name: `USBSTOR_TerminateEmergencyWorkerThread`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400297b0`

## callees

- `0x140012e48`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140012edb`
- `ntoskrnl!KeSetEvent` at `0x140012edb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012e64`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012ea5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012e64`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012ea5`
- `ntoskrnl!ObfDereferenceObject` at `0x140012eb8`
- `ntoskrnl!ObfDereferenceObject` at `0x140012eb8`
- `ntoskrnl!KeRundownQueue` at `0x140012e81`
- `ntoskrnl!KeRundownQueue` at `0x140012e81`

## pseudocode

```c
LONG USBSTOR_TerminateEmergencyWorkerThread()
{
  KeWaitForSingleObject(&EmergencyWorkerThreadEvent, Executive, 0, 0, 0);
  if ( EmergencyWorkerThread )
  {
    KeRundownQueue(&EmergencyWorkQueue);
    KeWaitForSingleObject(EmergencyWorkerThread, Executive, 0, 0, 0);
    ObfDereferenceObject(EmergencyWorkerThread);
    EmergencyWorkerThread = 0;
  }
  return KeSetEvent(&EmergencyWorkerThreadEvent, 0, 0);
}

```

## disassembly

```asm
0x140012e48  sub     rsp, 38h
0x140012e4c  xor     r9d, r9d; Alertable
0x140012e4f  mov     [rsp+38h+Timeout], 0; Timeout
0x140012e58  xor     r8d, r8d; WaitMode
0x140012e5b  lea     rcx, EmergencyWorkerThreadEvent; Object
0x140012e62  xor     edx, edx; WaitReason
0x140012e64  call    cs:__imp_KeWaitForSingleObject
0x140012e6b  nop     dword ptr [rax+rax+00h]
0x140012e70  cmp     cs:EmergencyWorkerThread, 0
0x140012e78  jz      short loc_140012ECF
0x140012e7a  lea     rcx, EmergencyWorkQueue; Queue
0x140012e81  call    cs:__imp_KeRundownQueue
0x140012e88  nop     dword ptr [rax+rax+00h]
0x140012e8d  mov     rcx, cs:EmergencyWorkerThread; Object
0x140012e94  xor     r9d, r9d; Alertable
0x140012e97  xor     r8d, r8d; WaitMode
0x140012e9a  mov     [rsp+38h+Timeout], 0; Timeout
0x140012ea3  xor     edx, edx; WaitReason
0x140012ea5  call    cs:__imp_KeWaitForSingleObject
0x140012eac  nop     dword ptr [rax+rax+00h]
0x140012eb1  mov     rcx, cs:EmergencyWorkerThread; Object
0x140012eb8  call    cs:__imp_ObfDereferenceObject
0x140012ebf  nop     dword ptr [rax+rax+00h]
0x140012ec4  mov     cs:EmergencyWorkerThread, 0
0x140012ecf  xor     r8d, r8d; Wait
0x140012ed2  lea     rcx, EmergencyWorkerThreadEvent; Event
0x140012ed9  xor     edx, edx; Increment
0x140012edb  call    cs:__imp_KeSetEvent
0x140012ee2  nop     dword ptr [rax+rax+00h]
0x140012ee7  add     rsp, 38h
0x140012eeb  retn
```
