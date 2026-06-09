# WaveFileReadData

- ea: `0x180006190`
- end: `0x18000619c`
- name: `WaveFileReadData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d1c8`

## pseudocode

```c
__int64 __fastcall WaveFileReadData(__int64 a1, int a2, void *a3, int *a4)
{
  return ReadExtra(a1 + 296, a2, a3, a4);
}

```

## disassembly

```asm
0x180006190  add     rcx, 128h
0x180006197  jmp     ReadExtra
```
