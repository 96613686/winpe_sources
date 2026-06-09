# nullsub_32644

- ea: `0x1dc53ec1`
- end: `0x1dc53ec2`
- name: `nullsub_32644`
- size: `1`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 nullsub_32644()
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x1dc53ec1  retf
```
