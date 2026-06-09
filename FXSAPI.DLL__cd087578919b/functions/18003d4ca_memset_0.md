# memset_0

- ea: `0x18003d4ca`
- end: `0x18003d4d0`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `67`
- callee_count: `0`
- tags: ``

## callers

- `0x1800024bc`
- `0x180002738`
- `0x1800029e8`
- `0x180003648`
- `0x1800039f4`
- `0x180005294`
- `0x180006308`
- `0x180007cb4`
- `0x1800080d4`
- `0x18000931c`
- `0x1800099bc`
- `0x18000a140`
- `0x18000aa00`
- `0x180011640`
- `0x180013d30`
- `0x180015040`
- `0x180016424`
- `0x1800166c4`
- `0x180016de4`
- `0x180018a10`
- `0x1800190d0`
- `0x180019d54`
- `0x18001a82c`
- `0x18001ad28`
- `0x18001b010`
- `0x18001f640`
- `0x180020830`
- `0x180024520`
- `0x180024f94`
- `0x1800251c0`
- `0x1800254e0`
- `0x1800259ec`
- `0x180026ef0`
- `0x180027e30`
- `0x180028ef0`
- `0x18002a650`
- `0x18002bea8`
- `0x18002cb24`
- `0x18002cf00`
- `0x18002d0e4`
- `0x18002dff4`
- `0x18002e5ac`
- `0x18002f2c4`
- `0x18002f480`
- `0x18002ffb8`
- `0x180031c24`
- `0x1800321cc`
- `0x1800322bc`
- `0x180032688`
- `0x18003291c`

## import_xrefs

- `msvcrt!memset` at `0x18003d4ca`

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
0x18003d4ca  jmp     cs:__imp_memset
```
