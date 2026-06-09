# ProbeForRead_0

- ea: `0x14000da43`
- end: `0x14000da4a`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x14000da78`
- `0x140022fcc`
- `0x140023030`
- `0x14002306c`
- `0x1400230a8`
- `0x140023108`
- `0x140023150`
- `0x140023198`
- `0x1400231dc`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000da43`

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
0x14000da43  jmp     cs:__imp_ProbeForRead
```
