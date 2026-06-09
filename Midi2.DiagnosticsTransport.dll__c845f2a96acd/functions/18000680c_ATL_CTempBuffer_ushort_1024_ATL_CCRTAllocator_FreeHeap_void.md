# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x18000680c`
- end: `0x180006816`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004cdc`
- `0x1800058d0`
- `0x18000824c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000680f`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x18000680c  mov     rcx, [rcx]
0x18000680f  jmp     cs:__imp_free
```
