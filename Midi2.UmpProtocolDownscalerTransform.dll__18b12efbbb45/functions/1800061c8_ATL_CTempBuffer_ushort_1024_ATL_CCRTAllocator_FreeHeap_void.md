# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1800061c8`
- end: `0x1800061d2`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046a0`
- `0x180005290`
- `0x180007c0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800061cb`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1800061c8  mov     rcx, [rcx]
0x1800061cb  jmp     cs:__imp_free
```
