# av_malloc_array

- ea: `0x180022954`
- end: `0x18002295a`
- name: `av_malloc_array`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180014834`
- `0x180015af8`
- `0x18001726c`
- `0x18001826c`
- `0x180019240`
- `0x18001c760`

## import_xrefs

- `avutil_ms!av_malloc_array` at `0x180022954`

## pseudocode

```c
// attributes: thunk
__int64 av_malloc_array()
{
  return __imp_av_malloc_array();
}

```

## disassembly

```asm
0x180022954  jmp     cs:__imp_av_malloc_array
```
