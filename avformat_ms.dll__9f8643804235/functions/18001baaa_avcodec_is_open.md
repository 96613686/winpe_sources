# avcodec_is_open

- ea: `0x18001baaa`
- end: `0x18001bab0`
- name: `avcodec_is_open`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006390`
- `0x18000a920`
- `0x18000b4f8`

## import_xrefs

- `avcodec_ms!avcodec_is_open` at `0x18001baaa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall avcodec_is_open(__int64 a1)
{
  return __imp_avcodec_is_open(a1);
}

```

## disassembly

```asm
0x18001baaa  jmp     cs:__imp_avcodec_is_open
```
