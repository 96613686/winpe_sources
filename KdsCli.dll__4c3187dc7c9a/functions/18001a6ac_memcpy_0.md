# memcpy_0

- ea: `0x18001a6ac`
- end: `0x18001a6b2`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bf0`
- `0x180003160`
- `0x18000398c`
- `0x180003b1c`
- `0x180004624`
- `0x180005a24`
- `0x180007354`
- `0x180008240`
- `0x180008570`
- `0x18000a878`
- `0x18000aef0`
- `0x18000b960`
- `0x18000bb30`
- `0x18000bd0c`
- `0x18000be6c`
- `0x18000c1fc`
- `0x18000ce40`
- `0x18000d6a0`
- `0x18000da88`
- `0x18000dfc0`
- `0x18000eab8`
- `0x18000fe30`
- `0x1800107e0`
- `0x180010dcc`
- `0x180016b30`
- `0x1800173d8`
- `0x180018c7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18001a6ac`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x18001a6ac  jmp     cs:__imp_memcpy
```
