# ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)

- ea: `0x180003ea4`
- end: `0x180003eae`
- name: `?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002468`
- `0x180002e4c`
- `0x1800050c0`

## import_xrefs

- `msvcrt!free` at `0x180003ea7`

## pseudocode

```c
void __fastcall ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void **a1)
{
  free(*a1);
}

```

## disassembly

```asm
0x180003ea4  mov     rcx, [rcx]
0x180003ea7  jmp     cs:__imp_free
```
