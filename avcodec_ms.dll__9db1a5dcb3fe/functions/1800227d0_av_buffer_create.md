# av_buffer_create

- ea: `0x1800227d0`
- end: `0x1800227d6`
- name: `av_buffer_create`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ef90`

## import_xrefs

- `avutil_ms!av_buffer_create` at `0x1800227d0`

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
0x1800227d0  jmp     cs:__imp_av_buffer_create
```
