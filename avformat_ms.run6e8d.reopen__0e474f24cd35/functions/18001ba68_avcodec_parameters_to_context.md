# avcodec_parameters_to_context

- ea: `0x18001ba68`
- end: `0x18001ba6e`
- name: `avcodec_parameters_to_context`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006390`
- `0x180007dd8`
- `0x18000a920`
- `0x18000be8c`
- `0x18000e06c`
- `0x18000e598`
- `0x1800167b0`

## import_xrefs

- `avcodec_ms!avcodec_parameters_to_context` at `0x18001ba68`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall avcodec_parameters_to_context(__int64 a1, __int64 a2)
{
  return __imp_avcodec_parameters_to_context(a1, a2);
}

```

## disassembly

```asm
0x18001ba68  jmp     cs:__imp_avcodec_parameters_to_context
```
