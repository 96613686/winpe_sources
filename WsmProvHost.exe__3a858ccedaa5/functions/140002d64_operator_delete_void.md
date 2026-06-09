# operator delete(void *)

- ea: `0x140002d64`
- end: `0x140002d76`
- name: `??3@YAXPEAX@Z`
- size: `18`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140001160`
- `0x140001190`
- `0x1400011d0`
- `0x140001208`
- `0x140001308`
- `0x140001d50`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d6a`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d6a`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  WSManMemory::Free(a1, 0);
}

```

## disassembly

```asm
0x140002d64  sub     rsp, 28h
0x140002d68  xor     edx, edx
0x140002d6a  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002d70  nop
0x140002d71  add     rsp, 28h
0x140002d75  retn
```
