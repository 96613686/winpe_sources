# USBSTOR_QueueResetPipe

- ea: `0x140012448`
- end: `0x1400124e1`
- name: `USBSTOR_QueueResetPipe`
- size: `153`
- prototype: `__int64 __fastcall(PVOID Object, PVOID Context)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400094b0`
- `0x14000f640`

## callees

- `0x140003630`
- `0x14000ca68`
- `0x140012448`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140012497`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140012497`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_QueueResetPipe(_QWORD *Object, PVOID Context)
{
  __int64 v4; // rbx
  NTSTATUS result; // eax

  USBSTOR_LogEntry(1347637841, Object, 0, 0);
  v4 = Object[8];
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 1832), USBSTOR_ResetPipeWorkItem, File, 1u, 0x20u);
  if ( result >= 0 )
    return USBSTOR_QueueWorkItem(
             Object,
             *(PLIST_ENTRY *)(v4 + 368),
             (PIO_WORKITEM_ROUTINE_EX)USBSTOR_ResetPipeWorkItem,
             Context,
             *(_BYTE *)(v4 + 1876) == 0);
  return result;
}

```

## disassembly

```asm
0x140012448  mov     [rsp+arg_0], rbx
0x14001244d  mov     [rsp+arg_8], rsi
0x140012452  push    rdi
0x140012453  sub     rsp, 30h
0x140012457  mov     rsi, rdx
0x14001245a  mov     rdi, rcx
0x14001245d  mov     rdx, rcx
0x140012460  xor     r9d, r9d
0x140012463  mov     ecx, 50535251h
0x140012468  xor     r8d, r8d
0x14001246b  call    USBSTOR_LogEntry
0x140012470  mov     rbx, [rdi+40h]
0x140012474  lea     r8, File; File
0x14001247b  mov     r9d, 1; Line
0x140012481  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x140012489  lea     rdx, USBSTOR_ResetPipeWorkItem; Tag
0x140012490  lea     rcx, [rbx+728h]; RemoveLock
0x140012497  call    cs:__imp_IoAcquireRemoveLockEx
0x14001249e  nop     dword ptr [rax+rax+00h]
0x1400124a3  test    eax, eax
0x1400124a5  js      short loc_1400124D0
0x1400124a7  cmp     byte ptr [rbx+754h], 0
0x1400124ae  lea     r8, USBSTOR_ResetPipeWorkItem; WorkerRoutine
0x1400124b5  mov     rdx, [rbx+170h]; Entry
0x1400124bc  mov     rcx, rdi; Object
0x1400124bf  setz    al
0x1400124c2  mov     [rsp+38h+var_10], al; char
0x1400124c6  mov     qword ptr [rsp+38h+RemlockSize], rsi; Context
0x1400124cb  call    USBSTOR_QueueWorkItem
0x1400124d0  mov     rbx, [rsp+38h+arg_0]
0x1400124d5  mov     rsi, [rsp+38h+arg_8]
0x1400124da  add     rsp, 30h
0x1400124de  pop     rdi
0x1400124df  retn
```
