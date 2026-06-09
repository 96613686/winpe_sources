# wil::details::FreeProcessHeap(void *)

- ea: `0x1400079c4`
- end: `0x1400079e7`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140004088`
- `0x140004728`
- `0x1400049f0`
- `0x140004d8c`
- `0x140007894`
- `0x14000807c`
- `0x140008120`
- `0x1400081e4`
- `0x140008348`
- `0x140008668`
- `0x1400087cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400079e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079cd`

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
0x1400079c4  push    rbx
0x1400079c6  sub     rsp, 20h
0x1400079ca  mov     rbx, rcx
0x1400079cd  call    cs:__imp_GetProcessHeap
0x1400079d3  mov     r8, rbx
0x1400079d6  xor     edx, edx
0x1400079d8  mov     rcx, rax
0x1400079db  add     rsp, 20h
0x1400079df  pop     rbx
0x1400079e0  jmp     cs:__imp_HeapFree
```
