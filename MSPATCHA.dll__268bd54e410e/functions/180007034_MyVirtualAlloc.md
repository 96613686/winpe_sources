# MyVirtualAlloc

- ea: `0x180007034`
- end: `0x18000704c`
- name: `MyVirtualAlloc`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d10`
- `0x18000541c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180007045`

## pseudocode

```c
LPVOID __fastcall MyVirtualAlloc(SIZE_T a1)
{
  return VirtualAlloc(0, a1, 0x1000u, 4u);
}

```

## disassembly

```asm
0x180007034  mov     rdx, rcx
0x180007037  mov     r9d, 4
0x18000703d  xor     ecx, ecx
0x18000703f  mov     r8d, 1000h
0x180007045  jmp     cs:__imp_VirtualAlloc
```
