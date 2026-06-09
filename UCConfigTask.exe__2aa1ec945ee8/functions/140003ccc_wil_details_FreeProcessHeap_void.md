# wil::details::FreeProcessHeap(void *)

- ea: `0x140003ccc`
- end: `0x140003cef`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x1400030e0`
- `0x140003184`
- `0x140003214`
- `0x140003248`
- `0x1400032c8`
- `0x140004e38`
- `0x140004f68`
- `0x140005900`
- `0x140005c24`
- `0x1400061ac`
- `0x1400069d8`
- `0x14000740c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003cd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003ce8`

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
0x140003ccc  push    rbx
0x140003cce  sub     rsp, 20h
0x140003cd2  mov     rbx, rcx
0x140003cd5  call    cs:__imp_GetProcessHeap
0x140003cdb  mov     r8, rbx
0x140003cde  xor     edx, edx
0x140003ce0  mov     rcx, rax
0x140003ce3  add     rsp, 20h
0x140003ce7  pop     rbx
0x140003ce8  jmp     cs:__imp_HeapFree
```
