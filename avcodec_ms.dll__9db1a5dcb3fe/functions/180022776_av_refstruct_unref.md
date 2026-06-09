# av_refstruct_unref

- ea: `0x180022776`
- end: `0x18002277c`
- name: `av_refstruct_unref`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800050a4`
- `0x1800072c8`
- `0x180007a44`
- `0x180007f60`
- `0x180008838`
- `0x1800088a8`
- `0x180008908`
- `0x18000c720`
- `0x18000e660`
- `0x1800104dc`
- `0x18001b510`

## import_xrefs

- `avutil_ms!av_refstruct_unref` at `0x180022776`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_refstruct_unref(__int64 a1)
{
  return __imp_av_refstruct_unref(a1);
}

```

## disassembly

```asm
0x180022776  jmp     cs:__imp_av_refstruct_unref
```
