# IoCompletionSetEvent

- ea: `0x140002930`
- end: `0x140002953`
- name: `IoCompletionSetEvent`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000293c`
- `ntoskrnl!KeSetEvent` at `0x14000293c`

## pseudocode

```c
__int64 __fastcall IoCompletionSetEvent(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140002930  sub     rsp, 28h
0x140002934  mov     rcx, r8; Event
0x140002937  xor     edx, edx; Increment
0x140002939  xor     r8d, r8d; Wait
0x14000293c  call    cs:__imp_KeSetEvent
0x140002943  nop     dword ptr [rax+rax+00h]
0x140002948  mov     eax, 0C0000016h
0x14000294d  add     rsp, 28h
0x140002951  retn
```
