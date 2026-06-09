# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800029bc`
- end: `0x1800029e2`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180001510`
- `0x1800031a8`
- `0x180007500`
- `0x1800095b0`
- `0x180009f70`
- `0x18000b840`
- `0x18000dfc0`
- `0x18000e130`
- `0x18000e558`
- `0x18000e804`
- `0x18001023c`
- `0x180017f44`
- `0x18001bbb0`
- `0x18001c540`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800029c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800029db`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T a1, const struct std::nothrow_t *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x1800029bc  push    rbx
0x1800029be  sub     rsp, 20h
0x1800029c2  mov     rbx, rcx
0x1800029c5  call    cs:__imp_GetProcessHeap
0x1800029cb  mov     r8, rbx
0x1800029ce  mov     edx, 8
0x1800029d3  mov     rcx, rax
0x1800029d6  add     rsp, 20h
0x1800029da  pop     rbx
0x1800029db  jmp     cs:__imp_HeapAlloc
```
