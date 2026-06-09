# av_interleaved_write_uncoded_frame

- ea: `0x1800121c0`
- end: `0x1800121cb`
- name: `av_interleaved_write_uncoded_frame`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800144ac`

## pseudocode

```c
__int64 __fastcall av_interleaved_write_uncoded_frame(__int64 a1, __int64 a2, __int64 a3)
{
  return sub_1800144AC(a1, a2, a3, 1);
}

```

## disassembly

```asm
0x1800121c0  mov     r9d, 1
0x1800121c6  jmp     sub_1800144AC
```
