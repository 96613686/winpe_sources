# wil::details::FreeProcessHeap(void *)

- ea: `0x180004cbc`
- end: `0x180004cdf`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180003e88`
- `0x180003f38`
- `0x180003fdc`
- `0x18000406c`
- `0x1800040c8`
- `0x180004148`
- `0x180007534`
- `0x180007698`
- `0x180008334`
- `0x180008618`
- `0x1800095ec`
- `0x180009ef8`
- `0x18000ad78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cc5`

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
0x180004cbc  push    rbx
0x180004cbe  sub     rsp, 20h
0x180004cc2  mov     rbx, rcx
0x180004cc5  call    cs:__imp_GetProcessHeap
0x180004ccb  mov     r8, rbx
0x180004cce  xor     edx, edx
0x180004cd0  mov     rcx, rax
0x180004cd3  add     rsp, 20h
0x180004cd7  pop     rbx
0x180004cd8  jmp     cs:__imp_HeapFree
```
