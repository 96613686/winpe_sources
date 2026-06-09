# USBSTOR_QueueAsyncNotification

- ea: `0x140012318`
- end: `0x1400123ad`
- name: `USBSTOR_QueueAsyncNotification`
- size: `149`
- prototype: `__int64 __fastcall(PVOID Object, PVOID Context)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400084c0`
- `0x140008590`
- `0x1400116a0`

## callees

- `0x140003630`
- `0x14000ca68`
- `0x140012318`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001235e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001235e`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_QueueAsyncNotification(PVOID Object, char *Context)
{
  NTSTATUS result; // eax

  USBSTOR_LogEntry(1229865297, Object, 0, 0);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(Context + 1832), USBSTOR_AsyncNotifyWorkItem, File, 1u, 0x20u);
  if ( result >= 0 )
  {
    result = *((_DWORD *)Context + 32);
    if ( (result & 0x80u) == 0 )
      return USBSTOR_QueueWorkItem(
               Object,
               *((PLIST_ENTRY *)Context + 47),
               USBSTOR_AsyncNotifyWorkItem,
               Context,
               Context[1876] == 0);
  }
  return result;
}

```

## disassembly

```asm
0x140012318  mov     [rsp+arg_0], rbx
0x14001231d  push    rdi
0x14001231e  sub     rsp, 30h
0x140012322  mov     rbx, rdx
0x140012325  mov     rdi, rcx
0x140012328  mov     rdx, rcx
0x14001232b  xor     r9d, r9d
0x14001232e  mov     ecx, 494E4151h
0x140012333  xor     r8d, r8d
0x140012336  call    USBSTOR_LogEntry
0x14001233b  lea     rcx, [rbx+728h]; RemoveLock
0x140012342  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14001234a  mov     r9d, 1; Line
0x140012350  lea     r8, File; File
0x140012357  lea     rdx, USBSTOR_AsyncNotifyWorkItem; Tag
0x14001235e  call    cs:__imp_IoAcquireRemoveLockEx
0x140012365  nop     dword ptr [rax+rax+00h]
0x14001236a  test    eax, eax
0x14001236c  js      short loc_1400123A1
0x14001236e  mov     eax, [rbx+80h]
0x140012374  test    al, al
0x140012376  js      short loc_1400123A1
0x140012378  cmp     byte ptr [rbx+754h], 0
0x14001237f  lea     r8, USBSTOR_AsyncNotifyWorkItem; WorkerRoutine
0x140012386  mov     rdx, [rbx+178h]; Entry
0x14001238d  mov     rcx, rdi; Object
0x140012390  setz    al
0x140012393  mov     [rsp+38h+var_10], al; char
0x140012397  mov     qword ptr [rsp+38h+RemlockSize], rbx; Context
0x14001239c  call    USBSTOR_QueueWorkItem
0x1400123a1  mov     rbx, [rsp+38h+arg_0]
0x1400123a6  add     rsp, 30h
0x1400123aa  pop     rdi
0x1400123ab  retn
```
