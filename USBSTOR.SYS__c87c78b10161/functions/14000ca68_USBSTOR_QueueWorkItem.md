# USBSTOR_QueueWorkItem

- ea: `0x14000ca68`
- end: `0x14000cb19`
- name: `USBSTOR_QueueWorkItem`
- size: `177`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PLIST_ENTRY Entry@<rdx>, PIO_WORKITEM_ROUTINE_EX WorkerRoutine@<r8>, PVOID Context, char)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x14000c830`
- `0x14000c96c`
- `0x140012318`
- `0x1400123b4`
- `0x140012448`

## callees

- `0x14000ca68`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14000cae2`
- `ntoskrnl!ObfReferenceObject` at `0x14000cae2`
- `ntoskrnl!KeInsertQueue` at `0x14000cb0b`
- `ntoskrnl!KeInsertQueue` at `0x14000cb0b`
- `ntoskrnl!IoSizeofWorkItem` at `0x14000cace`
- `ntoskrnl!IoSizeofWorkItem` at `0x14000cace`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14000cab4`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14000cab4`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000ca92`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000ca92`

## pseudocode

```c
void __fastcall USBSTOR_QueueWorkItem(
        struct _LIST_ENTRY *Object,
        struct _IO_WORKITEM *Entry,
        PIO_WORKITEM_ROUTINE_EX WorkerRoutine,
        __int64 a4,
        struct _LIST_ENTRY *Context,
        char a6)
{
  if ( a6 )
  {
LABEL_2:
    IoQueueWorkItemEx(Entry, WorkerRoutine, CriticalWorkQueue, Context);
    return;
  }
  if ( !(unsigned __int8)IoTryQueueWorkItem(Entry, WorkerRoutine, 0, Context) )
  {
    if ( EmergencyWorkerThread && IoSizeofWorkItem() >= 0x28 )
    {
      ObfReferenceObject(Object);
      *((_QWORD *)Entry + 3) = Object;
      *((_QWORD *)Entry + 2) = WorkerRoutine;
      *((_QWORD *)Entry + 4) = Context;
      *((_QWORD *)Entry + 1) = Entry;
      *(_QWORD *)Entry = Entry;
      KeInsertQueue(&EmergencyWorkQueue, (PLIST_ENTRY)Entry);
      return;
    }
    goto LABEL_2;
  }
}

```

## disassembly

```asm
0x14000ca68  push    rbx
0x14000ca6a  push    rbp
0x14000ca6b  push    rsi
0x14000ca6c  push    rdi
0x14000ca6d  sub     rsp, 28h
0x14000ca71  cmp     [rsp+48h+arg_28], 0
0x14000ca76  mov     rdi, r8
0x14000ca79  mov     rsi, [rsp+48h+Context]
0x14000ca7e  mov     rbx, rdx
0x14000ca81  mov     rbp, rcx
0x14000ca84  jz      short loc_14000CAA8
0x14000ca86  mov     r9, rsi; Context
0x14000ca89  xor     r8d, r8d; QueueType
0x14000ca8c  mov     rdx, rdi; WorkerRoutine
0x14000ca8f  mov     rcx, rbx; IoWorkItem
0x14000ca92  call    cs:__imp_IoQueueWorkItemEx
0x14000ca99  nop     dword ptr [rax+rax+00h]
0x14000ca9e  add     rsp, 28h
0x14000caa2  pop     rdi
0x14000caa3  pop     rsi
0x14000caa4  pop     rbp
0x14000caa5  pop     rbx
0x14000caa6  retn
0x14000caa8  mov     r9, rsi
0x14000caab  xor     r8d, r8d
0x14000caae  mov     rdx, rdi
0x14000cab1  mov     rcx, rbx
0x14000cab4  call    cs:__imp_IoTryQueueWorkItem
0x14000cabb  nop     dword ptr [rax+rax+00h]
0x14000cac0  test    al, al
0x14000cac2  jnz     short loc_14000CA9E
0x14000cac4  cmp     cs:EmergencyWorkerThread, 0
0x14000cacc  jz      short loc_14000CA86
0x14000cace  call    cs:__imp_IoSizeofWorkItem
0x14000cad5  nop     dword ptr [rax+rax+00h]
0x14000cada  cmp     eax, 28h ; '('
0x14000cadd  jb      short loc_14000CA86
0x14000cadf  mov     rcx, rbp; Object
0x14000cae2  call    cs:__imp_ObfReferenceObject
0x14000cae9  nop     dword ptr [rax+rax+00h]
0x14000caee  mov     [rbx+18h], rbp
0x14000caf2  lea     rcx, EmergencyWorkQueue; Queue
0x14000caf9  mov     [rbx+10h], rdi
0x14000cafd  mov     rdx, rbx; Entry
0x14000cb00  mov     [rbx+20h], rsi
0x14000cb04  mov     [rbx+8], rbx
0x14000cb08  mov     [rbx], rbx
0x14000cb0b  call    cs:__imp_KeInsertQueue
0x14000cb12  nop     dword ptr [rax+rax+00h]
0x14000cb17  jmp     short loc_14000CA9E
```
