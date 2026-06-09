# nullsub_32649

- ea: `0x25cadf95`
- end: `0x25cadf96`
- name: `nullsub_32649`
- size: `1`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 nullsub_32649()
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x25cadf95  retf
```
