# memset_0

- ea: `0x18001bcba`
- end: `0x18001bcc0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `82`
- callee_count: `0`
- tags: ``

## callers

- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x1800033b0`
- `0x180003920`
- `0x1800045b0`
- `0x180004824`
- `0x180004940`
- `0x180004bc0`
- `0x180004d10`
- `0x180004ef4`
- `0x180005280`
- `0x180005560`
- `0x180005920`
- `0x180005d50`
- `0x1800063a0`
- `0x180006b64`
- `0x1800073d8`
- `0x180007944`
- `0x180007a84`
- `0x1800093ac`
- `0x180009a00`
- `0x180009c7c`
- `0x180009dd8`
- `0x18000a0d4`
- `0x18000a270`
- `0x18000a35c`
- `0x18000a448`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b2e0`
- `0x18000b9fc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000c788`
- `0x18000c8d0`
- `0x18000cba4`
- `0x18000cdd8`
- `0x18000cec8`
- `0x18000d1a0`
- `0x18000d324`
- `0x18000df30`
- `0x18000e9a0`
- `0x18000efb0`
- `0x18000f974`
- `0x18000ff74`
- `0x1800101dc`

## import_xrefs

- `msvcrt!memset` at `0x18001bcba`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18001bcba  jmp     cs:__imp_memset
```
