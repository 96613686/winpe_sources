# operator delete(void *)

- ea: `0x180001620`
- end: `0x180001643`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800031f0`
- `0x180009fe0`
- `0x18000beb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000163c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001629`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001629`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180001620  push    rbx
0x180001622  sub     rsp, 20h
0x180001626  mov     rbx, rcx
0x180001629  call    cs:__imp_GetProcessHeap
0x18000162f  mov     r8, rbx
0x180001632  xor     edx, edx
0x180001634  mov     rcx, rax
0x180001637  add     rsp, 20h
0x18000163b  pop     rbx
0x18000163c  jmp     cs:__imp_HeapFree
```
