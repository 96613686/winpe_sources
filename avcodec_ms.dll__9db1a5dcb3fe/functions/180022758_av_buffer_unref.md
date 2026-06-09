# av_buffer_unref

- ea: `0x180022758`
- end: `0x18002275e`
- name: `av_buffer_unref`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800050a4`
- `0x180006f40`
- `0x1800087a4`
- `0x18000edf0`
- `0x18000f0d0`
- `0x18000f940`
- `0x1800104dc`
- `0x180011810`

## import_xrefs

- `avutil_ms!av_buffer_unref` at `0x180022758`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_buffer_unref(__int64 a1)
{
  return __imp_av_buffer_unref(a1);
}

```

## disassembly

```asm
0x180022758  jmp     cs:__imp_av_buffer_unref
```
