# KbdLayerDescriptor

- ea: `0x180001010`
- end: `0x180001018`
- name: `KbdLayerDescriptor`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 ***KbdLayerDescriptor()
{
  return &off_180002000;
}

```

## disassembly

```asm
0x180001010  lea     rax, off_180002000
0x180001017  retn
```
