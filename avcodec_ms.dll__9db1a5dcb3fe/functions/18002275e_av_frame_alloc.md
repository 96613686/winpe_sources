# av_frame_alloc

- ea: `0x18002275e`
- end: `0x180022764`
- name: `av_frame_alloc`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004150`
- `0x180006a98`
- `0x180008af0`
- `0x18000a670`
- `0x180010e30`

## import_xrefs

- `avutil_ms!av_frame_alloc` at `0x18002275e`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_alloc(__int64 a1)
{
  return __imp_av_frame_alloc(a1);
}

```

## disassembly

```asm
0x18002275e  jmp     cs:__imp_av_frame_alloc
```
