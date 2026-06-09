# memcpy

- ea: `0x18006cc64`
- end: `0x18006cc6a`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `71`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a920`
- `0x1800161c0`
- `0x1800173d0`
- `0x18001757c`
- `0x18001d19c`
- `0x18001e870`
- `0x1800211f0`
- `0x180021330`
- `0x1800261ec`
- `0x180028790`
- `0x180029a80`
- `0x18002a93c`
- `0x18002be70`
- `0x18002c540`
- `0x18002c8bc`
- `0x18002eabc`
- `0x18002f460`
- `0x180030360`
- `0x180030510`
- `0x180030710`
- `0x180033220`
- `0x1800332d0`
- `0x180033650`
- `0x180034700`
- `0x180034aa4`
- `0x180034bec`
- `0x1800354bc`
- `0x1800356c0`
- `0x180038b8c`
- `0x180038ebc`
- `0x18003e260`
- `0x18003e63c`
- `0x18003fc2c`
- `0x18004a41c`
- `0x18004be30`
- `0x18004cadc`
- `0x18004d3f0`
- `0x18004d7c4`
- `0x18004d978`
- `0x180051a70`
- `0x180051dd0`
- `0x180052408`
- `0x180052880`
- `0x1800534ac`
- `0x1800537a0`
- `0x180053cc0`
- `0x180054010`
- `0x180054540`
- `0x180054650`
- `0x180054a70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18006cc64`

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
0x18006cc64  jmp     cs:__imp_memcpy
```
