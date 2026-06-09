# av_frame_move_ref

- ea: `0x1800227e8`
- end: `0x1800227ee`
- name: `av_frame_move_ref`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800082ac`
- `0x18000a624`
- `0x18000a8c0`
- `0x180010c30`

## import_xrefs

- `avutil_ms!av_frame_move_ref` at `0x1800227e8`

## pseudocode

```c
// attributes: thunk
__int64 av_frame_move_ref()
{
  return __imp_av_frame_move_ref();
}

```

## disassembly

```asm
0x1800227e8  jmp     cs:__imp_av_frame_move_ref
```
