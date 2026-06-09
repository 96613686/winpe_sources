# av_buffer_replace

- ea: `0x1800227dc`
- end: `0x1800227e2`
- name: `av_buffer_replace`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c38`
- `0x18000a908`
- `0x18000edf0`

## import_xrefs

- `avutil_ms!av_buffer_replace` at `0x1800227dc`

## pseudocode

```c
// attributes: thunk
__int64 av_buffer_replace()
{
  return __imp_av_buffer_replace();
}

```

## disassembly

```asm
0x1800227dc  jmp     cs:__imp_av_buffer_replace
```
