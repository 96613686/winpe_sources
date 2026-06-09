# operator new(unsigned __int64)

- ea: `0x180002a90`
- end: `0x180002ab6`
- name: `??2@YAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002570`
- `0x1800028ec`
- `0x180002b48`
- `0x180008770`
- `0x18000cc44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002aaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a99`

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
0x180002a90  push    rbx
0x180002a92  sub     rsp, 20h
0x180002a96  mov     rbx, rcx
0x180002a99  call    cs:__imp_GetProcessHeap
0x180002a9f  mov     r8, rbx
0x180002aa2  mov     edx, 8
0x180002aa7  mov     rcx, rax
0x180002aaa  add     rsp, 20h
0x180002aae  pop     rbx
0x180002aaf  jmp     cs:__imp_HeapAlloc
```
