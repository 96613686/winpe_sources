# ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180003b90`
- end: `0x180003b98`
- name: `?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `8`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b98`
- `0x18000421c`
- `0x180005538`

## callees

- `0x18000bb08`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180003b90  mov     rcx, [rcx]; Block
0x180003b93  jmp     free
```
