# av_calloc

- ea: `0x1800227ac`
- end: `0x1800227b2`
- name: `av_calloc`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180006848`
- `0x18000c3e8`
- `0x180010740`
- `0x180012950`
- `0x18001726c`
- `0x18001794c`
- `0x18001826c`
- `0x180018b20`
- `0x18001c760`

## import_xrefs

- `avutil_ms!av_calloc` at `0x1800227ac`

## pseudocode

```c
// attributes: thunk
__int64 av_calloc()
{
  return __imp_av_calloc();
}

```

## disassembly

```asm
0x1800227ac  jmp     cs:__imp_av_calloc
```
