# av_write_uncoded_frame

- ea: `0x180012440`
- end: `0x180012448`
- name: `av_write_uncoded_frame`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800144ac`

## pseudocode

```c
__int64 __fastcall av_write_uncoded_frame(__int64 a1, __int64 a2, __int64 a3)
{
  return sub_1800144AC(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x180012440  xor     r9d, r9d
0x180012443  jmp     sub_1800144AC
```
