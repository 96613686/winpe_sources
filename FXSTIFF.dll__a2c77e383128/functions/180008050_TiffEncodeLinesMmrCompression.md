# TiffEncodeLinesMmrCompression

- ea: `0x180008050`
- end: `0x180008055`
- name: `TiffEncodeLinesMmrCompression`
- size: `5`
- prototype: `__int64 __fastcall(__int64, char *, int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003704`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall TiffEncodeLinesMmrCompression(__int64 a1, char *a2, int a3, unsigned int a4, int *a5)
{
  return EncodeFaxLinesMmrCompression(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180008050  jmp     EncodeFaxLinesMmrCompression
```
