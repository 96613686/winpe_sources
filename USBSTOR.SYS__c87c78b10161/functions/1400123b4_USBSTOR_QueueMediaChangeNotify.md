# USBSTOR_QueueMediaChangeNotify

- ea: `0x1400123b4`
- end: `0x14001243f`
- name: `USBSTOR_QueueMediaChangeNotify`
- size: `139`
- prototype: `__int64 __fastcall(PVOID Object, PVOID Context)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004910`
- `0x1400116a0`

## callees

- `0x140003630`
- `0x14000ca68`
- `0x1400123b4`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400123fa`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400123fa`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_QueueMediaChangeNotify(PVOID Object, char *Context)
{
  NTSTATUS result; // eax

  USBSTOR_LogEntry(1229865297, Object, 0, 0);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(Context + 1832), USBSTOR_MediaChangeNotifyWorkItem, File, 1u, 0x20u);
  if ( result >= 0 )
    return USBSTOR_QueueWorkItem(
             Object,
             *((PLIST_ENTRY *)Context + 48),
             (PIO_WORKITEM_ROUTINE_EX)USBSTOR_MediaChangeNotifyWorkItem,
             Context,
             Context[1876] == 0);
  return result;
}

```

## disassembly

```asm
0x1400123b4  mov     [rsp+arg_0], rbx
0x1400123b9  push    rdi
0x1400123ba  sub     rsp, 30h
0x1400123be  mov     rbx, rdx
0x1400123c1  mov     rdi, rcx
0x1400123c4  mov     rdx, rcx
0x1400123c7  xor     r9d, r9d
0x1400123ca  mov     ecx, 494E4151h
0x1400123cf  xor     r8d, r8d
0x1400123d2  call    USBSTOR_LogEntry
0x1400123d7  lea     rcx, [rbx+728h]; RemoveLock
0x1400123de  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x1400123e6  mov     r9d, 1; Line
0x1400123ec  lea     r8, File; File
0x1400123f3  lea     rdx, USBSTOR_MediaChangeNotifyWorkItem; Tag
0x1400123fa  call    cs:__imp_IoAcquireRemoveLockEx
0x140012401  nop     dword ptr [rax+rax+00h]
0x140012406  test    eax, eax
0x140012408  js      short loc_140012433
0x14001240a  cmp     byte ptr [rbx+754h], 0
0x140012411  lea     r8, USBSTOR_MediaChangeNotifyWorkItem; WorkerRoutine
0x140012418  mov     rdx, [rbx+180h]; Entry
0x14001241f  mov     rcx, rdi; Object
0x140012422  setz    al
0x140012425  mov     [rsp+38h+var_10], al; char
0x140012429  mov     qword ptr [rsp+38h+RemlockSize], rbx; Context
0x14001242e  call    USBSTOR_QueueWorkItem
0x140012433  mov     rbx, [rsp+38h+arg_0]
0x140012438  add     rsp, 30h
0x14001243c  pop     rdi
0x14001243d  retn
```
