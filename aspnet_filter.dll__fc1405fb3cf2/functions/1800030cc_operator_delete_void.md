# operator delete(void *)

- ea: `0x1800030cc`
- end: `0x1800030d1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003974`

## callees

- `0x1800031fc`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  MemFree(a1);
}

```

## disassembly

```asm
0x1800030cc  jmp     ?MemFree@@YAXPEAX@Z; MemFree(void *)
```
