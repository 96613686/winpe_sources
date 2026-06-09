# nullsub_32627

- ea: `0x188dfc0`
- end: `0x188dfc1`
- name: `nullsub_32627`
- size: `1`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 nullsub_32627()
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x188dfc0  retf
```
