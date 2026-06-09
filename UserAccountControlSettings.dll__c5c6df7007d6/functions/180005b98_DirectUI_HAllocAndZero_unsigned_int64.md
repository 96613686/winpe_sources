# DirectUI::HAllocAndZero(unsigned __int64)

- ea: `0x180005b98`
- end: `0x180005bbe`
- name: `?HAllocAndZero@DirectUI@@YAPEAX_K@Z`
- size: `38`
- prototype: `LPVOID __fastcall(DirectUI *this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180004f10`
- `0x1800050d0`
- `0x180009c94`
- `0x180009ec0`
- `0x180009f60`
- `0x18000a000`
- `0x18000ac30`
- `0x18000acd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ba1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bb7`

## pseudocode

```c
LPVOID __fastcall DirectUI::HAllocAndZero(DirectUI *this)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, (SIZE_T)this);
}

```

## disassembly

```asm
0x180005b98  push    rbx
0x180005b9a  sub     rsp, 20h
0x180005b9e  mov     rbx, rcx
0x180005ba1  call    cs:__imp_GetProcessHeap
0x180005ba7  mov     r8, rbx
0x180005baa  mov     edx, 8
0x180005baf  mov     rcx, rax
0x180005bb2  add     rsp, 20h
0x180005bb6  pop     rbx
0x180005bb7  jmp     cs:__imp_HeapAlloc
```
