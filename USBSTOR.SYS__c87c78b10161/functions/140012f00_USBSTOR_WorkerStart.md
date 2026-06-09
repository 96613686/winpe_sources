# USBSTOR_WorkerStart

- ea: `0x140012f00`
- end: `0x140012f87`
- name: `USBSTOR_WorkerStart`
- size: `135`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140012f00`
- `0x140013990`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140012f4e`
- `ntoskrnl!ObfDereferenceObject` at `0x140012f4e`
- `ntoskrnl!KeRemoveQueue` at `0x140012f66`
- `ntoskrnl!KeRemoveQueue` at `0x140012f66`
- `ntoskrnl!IoInitializeWorkItem` at `0x140012f2e`
- `ntoskrnl!IoInitializeWorkItem` at `0x140012f2e`

## pseudocode

```c
void __fastcall USBSTOR_WorkerStart(PVOID StartContext)
{
  struct _LIST_ENTRY *Blink; // rsi
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v3; // rdi
  PLIST_ENTRY v4; // rax
  PLIST_ENTRY v5; // rbp

  while ( 1 )
  {
    v4 = KeRemoveQueue(&EmergencyWorkQueue, 0, 0);
    v5 = v4;
    if ( v4 == (PLIST_ENTRY)128 )
      break;
    Blink = v4[1].Blink;
    Flink = v4[2].Flink;
    v3 = v4[1].Flink;
    *v4 = 0;
    v4[1] = 0;
    v4[2].Flink = 0;
    IoInitializeWorkItem(Blink, (PIO_WORKITEM)v4);
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct _LIST_ENTRY *, PLIST_ENTRY))v3)(Blink, Flink, v5);
    ObfDereferenceObject(Blink);
  }
}

```

## disassembly

```asm
0x140012f00  push    rbx
0x140012f02  push    rbp
0x140012f03  push    rsi
0x140012f04  push    rdi
0x140012f05  sub     rsp, 28h
0x140012f09  jmp     short loc_140012F5A
0x140012f0b  mov     rsi, [rbp+18h]
0x140012f0f  xorps   xmm0, xmm0
0x140012f12  mov     rbx, [rbp+20h]
0x140012f16  xor     eax, eax
0x140012f18  mov     rdi, [rbp+10h]
0x140012f1c  mov     rdx, rbp; IoWorkItem
0x140012f1f  movups  xmmword ptr [rbp+0], xmm0
0x140012f23  mov     rcx, rsi; IoObject
0x140012f26  movups  xmmword ptr [rbp+10h], xmm0
0x140012f2a  mov     [rbp+20h], rax
0x140012f2e  call    cs:__imp_IoInitializeWorkItem
0x140012f35  nop     dword ptr [rax+rax+00h]
0x140012f3a  mov     r8, rbp
0x140012f3d  mov     rdx, rbx
0x140012f40  mov     rcx, rsi
0x140012f43  mov     rax, rdi
0x140012f46  call    _guard_dispatch_icall
0x140012f4b  mov     rcx, rsi; Object
0x140012f4e  call    cs:__imp_ObfDereferenceObject
0x140012f55  nop     dword ptr [rax+rax+00h]
0x140012f5a  xor     r8d, r8d; Timeout
0x140012f5d  lea     rcx, EmergencyWorkQueue; Queue
0x140012f64  xor     edx, edx; WaitMode
0x140012f66  call    cs:__imp_KeRemoveQueue
0x140012f6d  nop     dword ptr [rax+rax+00h]
0x140012f72  mov     rbp, rax
0x140012f75  cmp     rax, 80h
0x140012f7b  jnz     short loc_140012F0B
0x140012f7d  add     rsp, 28h
0x140012f81  pop     rdi
0x140012f82  pop     rsi
0x140012f83  pop     rbp
0x140012f84  pop     rbx
0x140012f85  retn
```
