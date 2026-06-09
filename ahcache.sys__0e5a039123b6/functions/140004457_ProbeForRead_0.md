# ProbeForRead_0

- ea: `0x140004457`
- end: `0x14000445e`
- name: `ProbeForRead_0`
- size: `7`
- prototype: `void __stdcall(volatile void *Address, SIZE_T Length, ULONG Alignment)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1400045b0`
- `0x14002726c`
- `0x1400272d0`
- `0x140027344`
- `0x14002737c`
- `0x1400273b8`
- `0x1400273f4`
- `0x1400274cc`
- `0x140027514`
- `0x14002755c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140004457`

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
0x140004457  jmp     cs:__imp_ProbeForRead
```
