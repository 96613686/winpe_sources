# av_dict_copy

- ea: `0x18001bb7c`
- end: `0x18001bb82`
- name: `av_dict_copy`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007900`
- `0x18000a920`
- `0x180010da0`
- `0x180013478`

## import_xrefs

- `avutil_ms!av_dict_copy` at `0x18001bb7c`

## pseudocode

```c
// attributes: thunk
__int64 av_dict_copy()
{
  return __imp_av_dict_copy();
}

```

## disassembly

```asm
0x18001bb7c  jmp     cs:__imp_av_dict_copy
```
