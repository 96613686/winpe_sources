# wil::details::FreeProcessHeap(void *)

- ea: `0x14000438c`
- end: `0x1400043af`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140005280`
- `0x14000e6a0`
- `0x14000e744`
- `0x14000e778`
- `0x14000e7d8`
- `0x14000f180`
- `0x14000f988`
- `0x14000fca4`
- `0x14000ff98`
- `0x140010278`
- `0x140010870`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004395`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043a8`

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
0x14000438c  push    rbx
0x14000438e  sub     rsp, 20h
0x140004392  mov     rbx, rcx
0x140004395  call    cs:__imp_GetProcessHeap
0x14000439b  mov     r8, rbx
0x14000439e  xor     edx, edx
0x1400043a0  mov     rcx, rax
0x1400043a3  add     rsp, 20h
0x1400043a7  pop     rbx
0x1400043a8  jmp     cs:__imp_HeapFree
```
