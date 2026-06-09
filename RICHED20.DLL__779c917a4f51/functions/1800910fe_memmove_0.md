# memmove_0

- ea: `0x1800910fe`
- end: `0x180091104`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x1800049f0`
- `0x180009484`
- `0x18000fb24`
- `0x180018390`
- `0x1800194c0`
- `0x18001aa80`
- `0x18001ba08`
- `0x1800288d0`
- `0x180029a40`
- `0x18002a1e8`
- `0x18002cb28`
- `0x180031ff0`
- `0x180036ed0`
- `0x180037080`
- `0x180037468`
- `0x180037bd0`
- `0x18003c0bc`
- `0x18003c780`
- `0x180041494`
- `0x1800455e0`
- `0x180045cdc`
- `0x180047040`
- `0x180048cf8`
- `0x18004a778`
- `0x180050bac`
- `0x180050d3c`
- `0x180050f5c`
- `0x180051084`
- `0x1800512f8`
- `0x1800538fc`
- `0x18005952c`
- `0x18006d3d0`
- `0x18006d770`
- `0x180070074`
- `0x180087450`

## import_xrefs

- `msvcrt!memmove` at `0x1800910fe`

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
0x1800910fe  jmp     cs:__imp_memmove
```
