# _unlock_file

- ea: `0x14001b1f8`
- end: `0x14001b203`
- name: `_unlock_file`
- size: `11`
- prototype: `void __cdecl(FILE *File)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140016110`
- `0x140016704`
- `0x140016ec4`
- `0x14001baa8`
- `0x14001be2c`
- `0x14001bf5c`
- `0x14002b07a`
- `0x14002b0aa`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14001b1fc`

## pseudocode

```c
void __cdecl unlock_file(FILE *File)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)&File[1]);
}

```

## disassembly

```asm
0x14001b1f8  add     rcx, 30h ; '0'
0x14001b1fc  jmp     cs:__imp_LeaveCriticalSection
```
