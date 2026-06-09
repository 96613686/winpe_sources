# wil::details::FreeProcessHeap(void *)

- ea: `0x14000469c`
- end: `0x1400046bf`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140001684`
- `0x140001780`
- `0x140001988`
- `0x140001d6c`
- `0x1400023c0`
- `0x140002464`
- `0x140003d98`
- `0x140005484`
- `0x1400055a8`
- `0x140005da4`
- `0x1400063cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400046a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400046a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400046b8`

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
0x14000469c  push    rbx
0x14000469e  sub     rsp, 20h
0x1400046a2  mov     rbx, rcx
0x1400046a5  call    cs:__imp_GetProcessHeap
0x1400046ab  mov     r8, rbx
0x1400046ae  xor     edx, edx
0x1400046b0  mov     rcx, rax
0x1400046b3  add     rsp, 20h
0x1400046b7  pop     rbx
0x1400046b8  jmp     cs:__imp_HeapFree
```
