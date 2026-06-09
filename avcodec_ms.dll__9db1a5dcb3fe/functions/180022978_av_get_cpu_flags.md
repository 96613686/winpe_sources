# av_get_cpu_flags

- ea: `0x180022978`
- end: `0x18002297e`
- name: `av_get_cpu_flags`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180021d2c`
- `0x180022480`
- `0x1800224d8`
- `0x1800224fc`

## import_xrefs

- `avutil_ms!av_get_cpu_flags` at `0x180022978`

## pseudocode

```c
// attributes: thunk
__int64 av_get_cpu_flags()
{
  return __imp_av_get_cpu_flags();
}

```

## disassembly

```asm
0x180022978  jmp     cs:__imp_av_get_cpu_flags
```
