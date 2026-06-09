# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x1400061dc`
- end: `0x1400061e6`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400035ec`

## import_xrefs

- `msvcrt!free` at `0x1400061df`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x1400061dc  mov     rcx, [rcx]
0x1400061df  jmp     cs:__imp_free
```
