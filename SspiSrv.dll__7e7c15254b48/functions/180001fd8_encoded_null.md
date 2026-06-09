# _encoded_null

- ea: `0x180001fd8`
- end: `0x180001fe1`
- name: `_encoded_null`
- size: `9`
- prototype: `PVOID()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d80`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180001fda`

## pseudocode

```c
PVOID encoded_null()
{
  return EncodePointer(0);
}

```

## disassembly

```asm
0x180001fd8  xor     ecx, ecx
0x180001fda  jmp     cs:__imp_EncodePointer
```
