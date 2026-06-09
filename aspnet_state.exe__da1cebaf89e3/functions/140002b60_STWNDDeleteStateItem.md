# STWNDDeleteStateItem

- ea: `0x140002b60`
- end: `0x140002b65`
- name: `STWNDDeleteStateItem`
- size: `5`
- prototype: `unsigned int __fastcall(StateItem *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004760`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall STWNDDeleteStateItem(StateItem *a1)
{
  return StateItem::Release(a1);
}

```

## disassembly

```asm
0x140002b60  jmp     ?Release@StateItem@@QEAAKXZ; StateItem::Release(void)
```
