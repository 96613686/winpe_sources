# operator new(unsigned __int64)

- ea: `0x1800070c8`
- end: `0x1800070ee`
- name: `??2@YAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dbc`
- `0x18000312c`
- `0x180003d28`
- `0x180004ba0`
- `0x180004ca0`
- `0x18000542c`
- `0x180005d3c`
- `0x18000636c`
- `0x18000ab81`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800070d1`
- `KERNEL32!GetProcessHeap` at `0x1800070d1`
- `KERNEL32!HeapAlloc` at `0x1800070e7`

## pseudocode

```c
LPVOID __fastcall operator new(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x1800070c8  push    rbx
0x1800070ca  sub     rsp, 20h
0x1800070ce  mov     rbx, rcx
0x1800070d1  call    cs:__imp_GetProcessHeap
0x1800070d7  mov     r8, rbx
0x1800070da  mov     edx, 8
0x1800070df  mov     rcx, rax
0x1800070e2  add     rsp, 20h
0x1800070e6  pop     rbx
0x1800070e7  jmp     cs:__imp_HeapAlloc
```
