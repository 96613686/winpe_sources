# ApiSetQueryApiSetPresence_0

- ea: `0x1800058d4`
- end: `0x1800058da`
- name: `ApiSetQueryApiSetPresence_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800054d8`
- `0x180005540`
- `0x1800056ac`
- `0x18000578c`
- `0x180005880`

## import_xrefs

- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1800058d4`

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
0x1800058d4  jmp     cs:__imp_ApiSetQueryApiSetPresence
```
