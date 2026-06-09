# operator delete(void *,int const &,_NitsFaultMode)

- ea: `0x140002d7c`
- end: `0x140002d8e`
- name: `??3@YAXPEAXAEBHW4_NitsFaultMode@@@Z`
- size: `18`
- prototype: `void __fastcall(void *, _DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14000451a`

## import_xrefs

- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d82`
- `WsmSvc!?Free@WSManMemory@@SAXPEAXH@Z` at `0x140002d82`

## pseudocode

```c
void __fastcall operator delete(void *a1, _DWORD *a2)
{
  WSManMemory::Free(a1, *a2);
}

```

## disassembly

```asm
0x140002d7c  sub     rsp, 28h
0x140002d80  mov     edx, [rdx]
0x140002d82  call    cs:__imp_?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x140002d88  nop
0x140002d89  add     rsp, 28h
0x140002d8d  retn
```
