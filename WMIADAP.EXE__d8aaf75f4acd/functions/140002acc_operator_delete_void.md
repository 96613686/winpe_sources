# operator delete(void *)

- ea: `0x140002acc`
- end: `0x140002adc`
- name: `??3@YAXPEAX@Z`
- size: `16`
- prototype: `void __fastcall(void *)`
- caller_count: `9`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001550`
- `0x140001fa0`
- `0x140001fd0`
- `0x140002010`
- `0x140002048`
- `0x140002148`
- `0x1400152d6`
- `0x1400152fa`
- `0x140015bc7`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140002ad0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140002ad0`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  CWin32DefaultArena::WbemMemFree(a1);
}

```

## disassembly

```asm
0x140002acc  sub     rsp, 28h
0x140002ad0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140002ad6  nop
0x140002ad7  add     rsp, 28h
0x140002adb  retn
```
