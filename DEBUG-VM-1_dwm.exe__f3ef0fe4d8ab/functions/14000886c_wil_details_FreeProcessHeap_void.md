# wil::details::FreeProcessHeap(void *)

- ea: `0x14000886c`
- end: `0x14000888f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140003f50`
- `0x140004164`
- `0x14000443c`
- `0x1400047c8`
- `0x14000492c`
- `0x140004dec`
- `0x140005104`
- `0x1400051a8`
- `0x1400077cc`
- `0x14000a1b0`
- `0x14000aa9c`
- `0x14000baec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008875`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008888`

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
0x14000886c  push    rbx
0x14000886e  sub     rsp, 20h
0x140008872  mov     rbx, rcx
0x140008875  call    cs:__imp_GetProcessHeap
0x14000887b  mov     r8, rbx
0x14000887e  xor     edx, edx
0x140008880  mov     rcx, rax
0x140008883  add     rsp, 20h
0x140008887  pop     rbx
0x140008888  jmp     cs:__imp_HeapFree
```
