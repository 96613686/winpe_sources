# MemoryFree(void *)

- ea: `0x180002744`
- end: `0x180002767`
- name: `?MemoryFree@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b24`
- `0x180005198`
- `0x180006538`
- `0x180008010`
- `0x1800080c0`
- `0x180008164`
- `0x18000818c`
- `0x1800081c0`
- `0x180008220`
- `0x1800093e0`
- `0x180009e74`
- `0x18000a198`
- `0x18000a928`
- `0x18000ad54`
- `0x18000b478`
- `0x18000cc78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000274d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000274d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002760`

## pseudocode

```c
void __fastcall MemoryFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180002744  push    rbx
0x180002746  sub     rsp, 20h
0x18000274a  mov     rbx, rcx
0x18000274d  call    cs:__imp_GetProcessHeap
0x180002753  mov     r8, rbx
0x180002756  xor     edx, edx
0x180002758  mov     rcx, rax
0x18000275b  add     rsp, 20h
0x18000275f  pop     rbx
0x180002760  jmp     cs:__imp_HeapFree
```
