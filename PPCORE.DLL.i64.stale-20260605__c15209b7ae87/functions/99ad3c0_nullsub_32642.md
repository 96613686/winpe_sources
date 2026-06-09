# nullsub_32642

- ea: `0x99ad3c0`
- end: `0x99ad3c1`
- name: `nullsub_32642`
- size: `1`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 nullsub_32642()
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x99ad3c0  retf
```
