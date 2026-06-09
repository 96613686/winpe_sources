# MbbReqMgrDrainCompleteCallback(void *)

- ea: `0x14001a210`
- end: `0x14001a22b`
- name: `?MbbReqMgrDrainCompleteCallback@@YAXPEAX@Z`
- size: `27`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001a219`
- `ntoskrnl!KeSetEvent` at `0x14001a219`

## pseudocode

```c
void __fastcall MbbReqMgrDrainCompleteCallback(struct _KEVENT *a1)
{
  KeSetEvent(a1, 0, 0);
}

```

## disassembly

```asm
0x14001a210  sub     rsp, 28h
0x14001a214  xor     r8d, r8d; Wait
0x14001a217  xor     edx, edx; Increment
0x14001a219  call    cs:__imp_KeSetEvent
0x14001a220  nop     dword ptr [rax+rax+00h]
0x14001a225  add     rsp, 28h
0x14001a229  retn
```
