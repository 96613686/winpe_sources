# CryptXmlFree

- ea: `0x1800113d0`
- end: `0x180011401`
- name: `CryptXmlFree`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180012838`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113f5`

## pseudocode

```c
BOOL __fastcall CryptXmlFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x1800113d0  push    rbx
0x1800113d2  sub     rsp, 20h
0x1800113d6  mov     rbx, rcx
0x1800113d9  call    cs:__imp_GetProcessHeap
0x1800113e0  nop     dword ptr [rax+rax+00h]
0x1800113e5  mov     r8, rbx
0x1800113e8  mov     edx, 8
0x1800113ed  mov     rcx, rax
0x1800113f0  add     rsp, 20h
0x1800113f4  pop     rbx
0x1800113f5  jmp     cs:__imp_HeapFree
```
