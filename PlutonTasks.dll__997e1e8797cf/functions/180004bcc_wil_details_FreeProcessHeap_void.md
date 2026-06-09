# wil::details::FreeProcessHeap(void *)

- ea: `0x180004bcc`
- end: `0x180004bef`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180003848`
- `0x1800038ec`
- `0x18000397c`
- `0x1800039d8`
- `0x180003a58`
- `0x180005d50`
- `0x180005e74`
- `0x180006a80`
- `0x180006d98`
- `0x1800076ac`
- `0x1800080c8`
- `0x180008cec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004be8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bd5`

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
0x180004bcc  push    rbx
0x180004bce  sub     rsp, 20h
0x180004bd2  mov     rbx, rcx
0x180004bd5  call    cs:__imp_GetProcessHeap
0x180004bdb  mov     r8, rbx
0x180004bde  xor     edx, edx
0x180004be0  mov     rcx, rax
0x180004be3  add     rsp, 20h
0x180004be7  pop     rbx
0x180004be8  jmp     cs:__imp_HeapFree
```
