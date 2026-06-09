# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180006e9c`
- end: `0x180006ea6`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005370`
- `0x180005f60`
- `0x18000891c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006e9f`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180006e9c  mov     rcx, [rcx]
0x180006e9f  jmp     cs:__imp_free
```
