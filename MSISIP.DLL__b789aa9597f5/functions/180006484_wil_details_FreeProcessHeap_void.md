# wil::details::FreeProcessHeap(void *)

- ea: `0x180006484`
- end: `0x1800064a7`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006370`
- `0x180006450`
- `0x180008344`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000648d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000648d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064a0`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x180006484  push    rbx
0x180006486  sub     rsp, 20h
0x18000648a  mov     rbx, rcx
0x18000648d  call    cs:__imp_GetProcessHeap
0x180006493  mov     r8, rbx
0x180006496  xor     edx, edx
0x180006498  mov     rcx, rax
0x18000649b  add     rsp, 20h
0x18000649f  pop     rbx
0x1800064a0  jmp     cs:__imp_HeapFree
```
