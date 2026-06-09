# memset_0

- ea: `0x140002fcc`
- end: `0x140002fd2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1400037e4`
- `0x140004034`
- `0x140004978`
- `0x140004c40`
- `0x140005f2c`
- `0x1400068c0`
- `0x140007634`
- `0x1400080f4`
- `0x14000835c`
- `0x140008f9c`
- `0x14000936c`
- `0x14000acb4`
- `0x14000c1ac`
- `0x14000c67c`
- `0x14000e2a8`
- `0x14000e8c4`
- `0x14000fdd8`
- `0x140010b70`
- `0x140010e14`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x140002fcc`

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
0x140002fcc  jmp     cs:__imp_memset
```
