# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x140003d60`
- end: `0x140003d6a`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002708`
- `0x140002bec`
- `0x140004eb8`

## import_xrefs

- `msvcrt!free` at `0x140003d63`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x140003d60  mov     rcx, [rcx]
0x140003d63  jmp     cs:__imp_free
```
