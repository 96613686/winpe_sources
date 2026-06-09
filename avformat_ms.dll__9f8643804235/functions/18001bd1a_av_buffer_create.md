# av_buffer_create

- ea: `0x18001bd1a`
- end: `0x18001bd20`
- name: `av_buffer_create`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f4c4`
- `0x1800144ac`

## import_xrefs

- `avutil_ms!av_buffer_create` at `0x18001bd1a`

## pseudocode

```c
// attributes: thunk
__int64 av_buffer_create()
{
  return __imp_av_buffer_create();
}

```

## disassembly

```asm
0x18001bd1a  jmp     cs:__imp_av_buffer_create
```
