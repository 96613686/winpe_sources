# memmove_0

- ea: `0x18003f2ac`
- end: `0x18003f2b2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `25`
- callee_count: `0`
- tags: ``

## callers

- `0x180005a5c`
- `0x1800095e8`
- `0x18001cee4`
- `0x18001d490`
- `0x18001e6f4`
- `0x18001f1c0`
- `0x180020cb0`
- `0x1800221d0`
- `0x180024064`
- `0x1800241c8`
- `0x180024348`
- `0x180025fbc`
- `0x1800275bc`
- `0x18002773c`
- `0x180029190`
- `0x180029320`
- `0x18002a110`
- `0x18002d944`
- `0x18002fa04`
- `0x18002fd0c`
- `0x1800386a4`
- `0x1800388b0`
- `0x180039b64`
- `0x18003d80c`
- `0x18003e9a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18003f2ac`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18003f2ac  jmp     cs:__imp_memmove
```
