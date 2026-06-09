# WaveFileWriteData

- ea: `0x1800061d0`
- end: `0x1800061dc`
- name: `WaveFileWriteData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d36c`

## pseudocode

```c
__int64 __fastcall WaveFileWriteData(__int64 a1, int a2, const void *a3, int a4)
{
  return WriteExtra(a1 + 296, a2, a3, a4);
}

```

## disassembly

```asm
0x1800061d0  add     rcx, 128h
0x1800061d7  jmp     WriteExtra
```
