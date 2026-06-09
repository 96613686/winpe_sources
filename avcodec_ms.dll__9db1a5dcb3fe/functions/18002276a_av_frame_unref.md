# av_frame_unref

- ea: `0x18002276a`
- end: `0x180022770`
- name: `av_frame_unref`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180004010`
- `0x180004800`
- `0x1800072c8`
- `0x180007460`
- `0x1800082ac`
- `0x180008340`
- `0x1800084a8`
- `0x180008b30`
- `0x18000a278`
- `0x18000a3cc`
- `0x18000a5f8`
- `0x18000aa50`
- `0x18000c3e8`
- `0x18000ca24`
- `0x180010a18`
- `0x180010e30`
- `0x18001bd00`

## import_xrefs

- `avutil_ms!av_frame_unref` at `0x18002276a`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_frame_unref(__int64 a1)
{
  return __imp_av_frame_unref(a1);
}

```

## disassembly

```asm
0x18002276a  jmp     cs:__imp_av_frame_unref
```
