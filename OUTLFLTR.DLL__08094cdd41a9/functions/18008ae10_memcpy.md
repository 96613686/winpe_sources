# memcpy

- ea: `0x18008ae10`
- end: `0x18008ae16`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x180023b64`
- `0x180023c44`
- `0x18002a6a8`
- `0x18002a768`
- `0x18002f960`
- `0x180033fe8`
- `0x180037a74`
- `0x180037af4`
- `0x18003e300`
- `0x180043bb0`
- `0x180044b7c`
- `0x180045e24`
- `0x18004fbc0`
- `0x180052518`
- `0x180056d88`
- `0x18005a7b0`
- `0x18005a930`
- `0x18005ab44`
- `0x18005ac6c`
- `0x18005ad60`
- `0x18005f300`
- `0x18005fa5c`
- `0x18005fadc`
- `0x180063960`
- `0x180065f10`
- `0x180068c5c`
- `0x18007c35c`
- `0x18007dcbc`
- `0x18007f784`
- `0x18008366c`
- `0x180083ec0`
- `0x180084740`
- `0x180085d74`
- `0x18008a0fc`
- `0x18008a78c`

## import_xrefs

- `MSVCR90!memcpy` at `0x18008ae10`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18008ae10  jmp     cs:__imp_memcpy
```
