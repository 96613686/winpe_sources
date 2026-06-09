# RfspThreadPoolNodeQueueWorkItem

- ea: `0x140012c30`
- end: `0x140012c95`
- name: `RfspThreadPoolNodeQueueWorkItem`
- size: `101`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140059008`
- `0x140068134`
- `0x140068c10`
- `0x140078f78`
- `0x140079c30`
- `0x14007e280`
- `0x1400809c0`
- `0x140082290`
- `0x140085ef0`
- `0x1400874c0`
- `0x14008d790`
- `0x1400901a0`
- `0x140092150`

## callees

- `0x140012c30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140012c87`
- `ntoskrnl!KeSetEvent` at `0x140012c87`
- `ntoskrnl!KeReadStateEvent` at `0x140012c67`
- `ntoskrnl!KeReadStateEvent` at `0x140012c67`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012c42`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140012c42`

## pseudocode

```c
char __fastcall RfspThreadPoolNodeQueueWorkItem(union _SLIST_HEADER *a1, struct _SLIST_ENTRY *a2, char a3)
{
  union _SLIST_HEADER *v3; // rbx
  LONG StateEvent; // eax

  v3 = a1;
  if ( !a3 )
    ++a1;
  LOBYTE(StateEvent) = ExpInterlockedPushEntrySList(a1, a2) == 0;
  if ( (_BYTE)StateEvent )
  {
    LOWORD(StateEvent) = *((_WORD *)&v3[4].Header8 + 1);
    if ( (_WORD)StateEvent )
    {
      StateEvent = KeReadStateEvent((PRKEVENT)((char *)&v3[4].HeaderX64 + 8));
      if ( !StateEvent )
        LOBYTE(StateEvent) = KeSetEvent((PRKEVENT)((char *)&v3[4].HeaderX64 + 8), 0, 0);
    }
  }
  return StateEvent;
}

```

## disassembly

```asm
0x140012c30  push    rbx
0x140012c32  sub     rsp, 20h
0x140012c36  mov     rbx, rcx
0x140012c39  test    r8b, r8b
0x140012c3c  jnz     short loc_140012C42
0x140012c3e  add     rcx, 10h; ListHead
0x140012c42  call    cs:__imp_ExpInterlockedPushEntrySList
0x140012c49  nop     dword ptr [rax+rax+00h]
0x140012c4e  test    rax, rax
0x140012c51  setz    al
0x140012c54  test    al, al
0x140012c56  jz      short loc_140012C77
0x140012c58  movzx   eax, word ptr [rbx+42h]
0x140012c5c  xor     ecx, ecx
0x140012c5e  cmp     cx, ax
0x140012c61  jz      short loc_140012C77
0x140012c63  lea     rcx, [rbx+48h]; Event
0x140012c67  call    cs:__imp_KeReadStateEvent
0x140012c6e  nop     dword ptr [rax+rax+00h]
0x140012c73  test    eax, eax
0x140012c75  jz      short loc_140012C7E
0x140012c77  add     rsp, 20h
0x140012c7b  pop     rbx
0x140012c7c  retn
0x140012c7e  xor     r8d, r8d; Wait
0x140012c81  lea     rcx, [rbx+48h]; Event
0x140012c85  xor     edx, edx; Increment
0x140012c87  call    cs:__imp_KeSetEvent
0x140012c8e  nop     dword ptr [rax+rax+00h]
0x140012c93  jmp     short loc_140012C77
```
