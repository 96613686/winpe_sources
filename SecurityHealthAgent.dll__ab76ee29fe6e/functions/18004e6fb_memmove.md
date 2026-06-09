# memmove

- ea: `0x18004e6fb`
- end: `0x18004e701`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `66`
- callee_count: `0`
- tags: ``

## callers

- `0x180009770`
- `0x18000b840`
- `0x18000c6d0`
- `0x18000c830`
- `0x18000d560`
- `0x18000dd40`
- `0x18000f7b0`
- `0x1800105f0`
- `0x180010930`
- `0x1800112e0`
- `0x180011a10`
- `0x180012120`
- `0x180012830`
- `0x180012f40`
- `0x1800136a0`
- `0x180013d90`
- `0x180014480`
- `0x180014be0`
- `0x1800179b0`
- `0x18001d2f0`
- `0x18001d4f0`
- `0x180022720`
- `0x180025590`
- `0x180025e30`
- `0x180026ca0`
- `0x180027cb0`
- `0x1800283c0`
- `0x1800288c0`
- `0x180028dd0`
- `0x18002b320`
- `0x180030cd0`
- `0x180032110`
- `0x180033250`
- `0x1800353f0`
- `0x180036790`
- `0x180037890`
- `0x1800380e0`
- `0x180039a50`
- `0x18003a6e0`
- `0x18003aae0`
- `0x18003b270`
- `0x18003b980`
- `0x18003c0b0`
- `0x18003c7c0`
- `0x18003ced0`
- `0x18003d600`
- `0x18003dd30`
- `0x18003e450`
- `0x18003eb90`
- `0x180041640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18004e6fb`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18004e6fb  jmp     cs:__imp_memmove
```
