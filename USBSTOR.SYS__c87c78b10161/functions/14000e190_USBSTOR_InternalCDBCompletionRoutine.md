# USBSTOR_InternalCDBCompletionRoutine

- ea: `0x14000e190`
- end: `0x14000e1e8`
- name: `USBSTOR_InternalCDBCompletionRoutine`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003630`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000e1b7`
- `ntoskrnl!IoFreeIrp` at `0x14000e1b7`
- `ntoskrnl!KeSetEvent` at `0x14000e1cb`
- `ntoskrnl!KeSetEvent` at `0x14000e1cb`

## pseudocode

```c
__int64 __fastcall USBSTOR_InternalCDBCompletionRoutine(__int64 a1, IRP *a2, struct _KEVENT *a3)
{
  USBSTOR_LogEntry(1380139849, a1, (__int64)a2, a2->IoStatus.Status);
  IoFreeIrp(a2);
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000e190  mov     [rsp+arg_0], rbx
0x14000e195  push    rdi
0x14000e196  sub     rsp, 20h
0x14000e19a  movsxd  r9, dword ptr [rdx+30h]
0x14000e19e  mov     rdi, r8
0x14000e1a1  mov     r8, rdx
0x14000e1a4  mov     rbx, rdx
0x14000e1a7  mov     rdx, rcx
0x14000e1aa  mov     ecx, 52434349h
0x14000e1af  call    USBSTOR_LogEntry
0x14000e1b4  mov     rcx, rbx; Irp
0x14000e1b7  call    cs:__imp_IoFreeIrp
0x14000e1be  nop     dword ptr [rax+rax+00h]
0x14000e1c3  xor     r8d, r8d; Wait
0x14000e1c6  xor     edx, edx; Increment
0x14000e1c8  mov     rcx, rdi; Event
0x14000e1cb  call    cs:__imp_KeSetEvent
0x14000e1d2  nop     dword ptr [rax+rax+00h]
0x14000e1d7  mov     rbx, [rsp+28h+arg_0]
0x14000e1dc  mov     eax, 0C0000016h
0x14000e1e1  add     rsp, 20h
0x14000e1e5  pop     rdi
0x14000e1e6  retn
```
