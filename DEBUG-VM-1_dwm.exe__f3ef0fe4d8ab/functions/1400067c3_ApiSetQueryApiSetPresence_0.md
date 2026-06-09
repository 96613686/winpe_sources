# ApiSetQueryApiSetPresence_0

- ea: `0x1400067c3`
- end: `0x1400067c9`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140006224`
- `0x140006304`
- `0x140006530`
- `0x1400065cc`
- `0x1400066e4`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1400067c3`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ApiSetQueryApiSetPresence_0(__int64 a1, __int64 a2)
{
  return ApiSetQueryApiSetPresence(a1, a2);
}

```

## disassembly

```asm
0x1400067c3  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
