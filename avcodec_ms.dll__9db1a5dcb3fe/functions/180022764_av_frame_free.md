# av_frame_free

- ea: `0x180022764`
- end: `0x18002276a`
- name: `av_frame_free`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800050a4`
- `0x180008ad0`
- `0x18000e660`
- `0x18001048c`

## import_xrefs

- `avutil_ms!av_frame_free` at `0x180022764`

## pseudocode

```c
// attributes: thunk
__int64 av_frame_free()
{
  return __imp_av_frame_free();
}

```

## disassembly

```asm
0x180022764  jmp     cs:__imp_av_frame_free
```
