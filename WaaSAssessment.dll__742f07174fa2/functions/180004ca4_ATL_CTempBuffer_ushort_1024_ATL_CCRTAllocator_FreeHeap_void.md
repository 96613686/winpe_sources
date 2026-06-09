# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180004ca4`
- end: `0x180004cae`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003084`
- `0x18000369c`
- `0x1800056b8`

## import_xrefs

- `msvcrt!free` at `0x180004ca7`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180004ca4  mov     rcx, [rcx]
0x180004ca7  jmp     cs:__imp_free
```
