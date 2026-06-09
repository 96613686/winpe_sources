# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1800056a8`
- end: `0x1800056b2`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b7c`
- `0x180004770`
- `0x1800070fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800056ab`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1800056a8  mov     rcx, [rcx]
0x1800056ab  jmp     cs:__imp_free
```
