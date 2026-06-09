# ProbeForRead_0

- ea: `0x1400034af`
- end: `0x1400034b6`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400034c8`
- `0x14000f608`
- `0x14000f66c`
- `0x14000f6a4`
- `0x14000f6e0`
- `0x14000f71c`
- `0x14000f77c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400034af`

## pseudocode

```c
// attributes: thunk
void __stdcall ProbeForRead_0(volatile void *Address, SIZE_T Length, ULONG Alignment)
{
  ProbeForRead(Address, Length, Alignment);
}

```

## disassembly

```asm
0x1400034af  jmp     cs:__imp_ProbeForRead
```
