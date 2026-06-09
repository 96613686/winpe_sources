# USBD_SyncCompletionRoutine

- ea: `0x140006050`
- end: `0x140006073`
- name: `USBD_SyncCompletionRoutine`
- size: `35`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000605c`
- `ntoskrnl!KeSetEvent` at `0x14000605c`

## pseudocode

```c
__int64 __fastcall USBD_SyncCompletionRoutine(PDEVICE_OBJECT DeviceObject, PIRP Irp, struct _KEVENT *Context)
{
  KeSetEvent(Context, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140006050  sub     rsp, 28h
0x140006054  mov     rcx, r8; Event
0x140006057  xor     edx, edx; Increment
0x140006059  xor     r8d, r8d; Wait
0x14000605c  call    cs:__imp_KeSetEvent
0x140006063  nop     dword ptr [rax+rax+00h]
0x140006068  mov     eax, 0C0000016h
0x14000606d  add     rsp, 28h
0x140006071  retn
```
