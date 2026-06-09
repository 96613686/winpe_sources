# wil::details::FreeProcessHeap(void *)

- ea: `0x1400051cc`
- end: `0x1400051ef`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140004af0`
- `0x1400062e8`
- `0x140009160`
- `0x140009204`
- `0x140009238`
- `0x1400092f4`
- `0x14000bc54`
- `0x14000cbb4`
- `0x14000ce98`
- `0x14000fd24`
- `0x14001041c`
- `0x1400114dc`
- `0x14001775c`
- `0x140018060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400051e8`

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
0x1400051cc  push    rbx
0x1400051ce  sub     rsp, 20h
0x1400051d2  mov     rbx, rcx
0x1400051d5  call    cs:__imp_GetProcessHeap
0x1400051db  mov     r8, rbx
0x1400051de  xor     edx, edx
0x1400051e0  mov     rcx, rax
0x1400051e3  add     rsp, 20h
0x1400051e7  pop     rbx
0x1400051e8  jmp     cs:__imp_HeapFree
```
