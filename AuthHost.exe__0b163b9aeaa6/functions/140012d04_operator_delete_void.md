# operator delete(void *)

- ea: `0x140012d04`
- end: `0x140012d09`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002850`

## callees

- `0x140012d4c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  Common::GlobalHeap::Free(a1);
}

```

## disassembly

```asm
0x140012d04  jmp     ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
```
