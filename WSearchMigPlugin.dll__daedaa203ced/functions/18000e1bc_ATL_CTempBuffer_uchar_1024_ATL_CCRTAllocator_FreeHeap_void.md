# ATL::CTempBuffer<uchar,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x18000e1bc`
- end: `0x18000e1c6`
- name: `?FreeHeap@?$CTempBuffer@E$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cae4`
- `0x180012b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e1bf`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x18000e1bc  mov     rcx, [rcx]
0x18000e1bf  jmp     cs:__imp_free
```
