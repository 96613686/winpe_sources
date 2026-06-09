# memmove_0

- ea: `0x18001dbfc`
- end: `0x18001dc02`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030c0`
- `0x1800040d0`
- `0x1800050a0`
- `0x180005ea0`
- `0x18000630c`
- `0x18000c6e8`
- `0x18000edc0`
- `0x18000f3b8`
- `0x180010eb4`
- `0x18001134c`
- `0x1800120d0`
- `0x1800128d8`
- `0x1800146d4`
- `0x180015270`
- `0x180016080`
- `0x18001a388`
- `0x18001ae24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18001dbfc`

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
0x18001dbfc  jmp     cs:__imp_memmove
```
