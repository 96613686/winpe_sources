# USBD_SyncCompletionRoutine

- ea: `0x14000f1f0`
- end: `0x14000f213`
- name: `USBD_SyncCompletionRoutine`
- size: `35`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000f1fc`
- `ntoskrnl!KeSetEvent` at `0x14000f1fc`

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
0x14000f1f0  sub     rsp, 28h
0x14000f1f4  mov     rcx, r8; Event
0x14000f1f7  xor     edx, edx; Increment
0x14000f1f9  xor     r8d, r8d; Wait
0x14000f1fc  call    cs:__imp_KeSetEvent
0x14000f203  nop     dword ptr [rax+rax+00h]
0x14000f208  mov     eax, 0C0000016h
0x14000f20d  add     rsp, 28h
0x14000f211  retn
```
