# memmove

- ea: `0x18007c4fa`
- end: `0x18007c500`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180006040`
- `0x180015c60`
- `0x180019bd0`
- `0x18004c144`
- `0x18004c228`
- `0x18004c414`
- `0x1800603d0`
- `0x18007876c`
- `0x18007949c`
- `0x18007a000`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18007c4fa`

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
0x18007c4fa  jmp     cs:__imp_memmove
```
