# avcodec_open2

- ea: `0x18001ba6e`
- end: `0x18001ba74`
- name: `avcodec_open2`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006390`
- `0x18000b4f8`

## import_xrefs

- `avcodec_ms!avcodec_open2` at `0x18001ba6e`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall avcodec_open2(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_avcodec_open2(a1, a2, a3);
}

```

## disassembly

```asm
0x18001ba6e  jmp     cs:__imp_avcodec_open2
```
