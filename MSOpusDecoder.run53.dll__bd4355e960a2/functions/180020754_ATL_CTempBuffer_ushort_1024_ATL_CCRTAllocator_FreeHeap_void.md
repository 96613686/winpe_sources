# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180020754`
- end: `0x18002075e`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ee3c`
- `0x18001f49c`
- `0x180021228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180020757`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180020754  mov     rcx, [rcx]
0x180020757  jmp     cs:__imp_free
```
