# av_dict_get

- ea: `0x18001bb76`
- end: `0x18001bb7c`
- name: `av_dict_get`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023d8`
- `0x180003294`
- `0x1800035d4`
- `0x18000ca60`
- `0x18000d648`
- `0x18000e06c`
- `0x180011008`
- `0x180013478`
- `0x1800184fc`
- `0x1800198fc`

## import_xrefs

- `avutil_ms!av_dict_get` at `0x18001bb76`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_dict_get(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return __imp_av_dict_get(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001bb76  jmp     cs:__imp_av_dict_get
```
