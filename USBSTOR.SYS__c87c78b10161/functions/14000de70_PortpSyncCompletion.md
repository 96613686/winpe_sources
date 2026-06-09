# PortpSyncCompletion

- ea: `0x14000de70`
- end: `0x14000de8e`
- name: `PortpSyncCompletion`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140022cb0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000de7c`
- `ntoskrnl!KeSetEvent` at `0x14000de7c`

## pseudocode

```c
LONG __fastcall PortpSyncCompletion(__int64 a1, struct _KEVENT *a2)
{
  return KeSetEvent(a2, 0, 0);
}

```

## disassembly

```asm
0x14000de70  sub     rsp, 28h
0x14000de74  mov     rcx, rdx; Event
0x14000de77  xor     r8d, r8d; Wait
0x14000de7a  xor     edx, edx; Increment
0x14000de7c  call    cs:__imp_KeSetEvent
0x14000de83  nop     dword ptr [rax+rax+00h]
0x14000de88  add     rsp, 28h
0x14000de8c  retn
```
