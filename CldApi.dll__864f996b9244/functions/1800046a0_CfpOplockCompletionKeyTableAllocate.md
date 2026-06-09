# CfpOplockCompletionKeyTableAllocate

- ea: `0x1800046a0`
- end: `0x1800046c2`
- name: `CfpOplockCompletionKeyTableAllocate`
- size: `34`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800046bb`

## pseudocode

```c
PVOID __fastcall CfpOplockCompletionKeyTableAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, ByteSize);
}

```

## disassembly

```asm
0x1800046a0  push    rbx
0x1800046a2  sub     rsp, 20h
0x1800046a6  mov     ebx, edx
0x1800046a8  call    cs:__imp_GetProcessHeap
0x1800046ae  mov     r8d, ebx
0x1800046b1  xor     edx, edx
0x1800046b3  mov     rcx, rax
0x1800046b6  add     rsp, 20h
0x1800046ba  pop     rbx
0x1800046bb  jmp     cs:__imp_HeapAlloc
```
