# memset

- ea: `0x1400c7aa2`
- end: `0x1400c7aa8`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `44`
- callee_count: `0`
- tags: ``

## callers

- `0x140006e90`
- `0x1400075e0`
- `0x140007864`
- `0x140007b1c`
- `0x1400080c8`
- `0x14000aeb8`
- `0x14000cba4`
- `0x14000f2b0`
- `0x14000f4b8`
- `0x14000fd90`
- `0x1400133ac`
- `0x14001523c`
- `0x140015dec`
- `0x140016b9c`
- `0x14001c79c`
- `0x14001d1c8`
- `0x1400205e0`
- `0x140020770`
- `0x140020f50`
- `0x1400210e0`
- `0x140024578`
- `0x140024748`
- `0x1400328a8`
- `0x140032ec0`
- `0x140033d50`
- `0x140034080`
- `0x140035070`
- `0x1400353a0`
- `0x1400392d0`
- `0x140039bbc`
- `0x140039be8`
- `0x140072254`
- `0x140080650`
- `0x1400807cc`
- `0x14009d72c`
- `0x14009d984`
- `0x14009dc3c`
- `0x1400a3db8`
- `0x1400a42a4`
- `0x1400a4aec`
- `0x1400a6e50`
- `0x1400a7598`
- `0x1400c64b4`
- `0x1400c6b20`

## import_xrefs

- `msvcrt!memset` at `0x1400c7aa2`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x1400c7aa2  jmp     cs:__imp_memset
```
