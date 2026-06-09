# av_packet_unref

- ea: `0x18001b9f6`
- end: `0x18001b9fc`
- name: `av_packet_unref`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18000219c`
- `0x180006060`
- `0x180006390`
- `0x180008cf4`
- `0x180009154`
- `0x180009380`
- `0x180009e98`
- `0x18000a378`
- `0x18000a920`
- `0x18000c988`
- `0x180012150`
- `0x1800121d0`
- `0x1800122a0`
- `0x180012cf4`
- `0x180013d48`
- `0x18001436c`
- `0x18001ae48`
- `0x18001b1e4`

## import_xrefs

- `avcodec_ms!av_packet_unref` at `0x18001b9f6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_packet_unref(__int64 a1)
{
  return __imp_av_packet_unref(a1);
}

```

## disassembly

```asm
0x18001b9f6  jmp     cs:__imp_av_packet_unref
```
