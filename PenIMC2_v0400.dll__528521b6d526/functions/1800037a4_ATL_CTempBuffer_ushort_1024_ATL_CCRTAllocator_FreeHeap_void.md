# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1800037a4`
- end: `0x1800037ae`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800037b0`
- `0x180003ea0`
- `0x1800055ec`

## import_xrefs

- `ucrtbase_clr0400!free` at `0x1800037a7`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1800037a4  mov     rcx, [rcx]
0x1800037a7  jmp     cs:__imp_free
```
