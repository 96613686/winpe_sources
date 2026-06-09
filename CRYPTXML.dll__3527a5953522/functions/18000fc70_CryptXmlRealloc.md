# CryptXmlRealloc

- ea: `0x18000fc70`
- end: `0x18000fcb0`
- name: `CryptXmlRealloc`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180009a10`
- `0x18000f200`
- `0x180016e40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fc80`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000fca4`

## pseudocode

```c
LPVOID __fastcall CryptXmlRealloc(void *a1, __int64 a2, SIZE_T a3)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapReAlloc(ProcessHeap, 8u, a1, a3);
}

```

## disassembly

```asm
0x18000fc70  mov     [rsp+arg_0], rbx
0x18000fc75  push    rdi
0x18000fc76  sub     rsp, 20h
0x18000fc7a  mov     rdi, r8
0x18000fc7d  mov     rbx, rcx
0x18000fc80  call    cs:__imp_GetProcessHeap
0x18000fc87  nop     dword ptr [rax+rax+00h]
0x18000fc8c  mov     r9, rdi
0x18000fc8f  mov     r8, rbx
0x18000fc92  mov     rcx, rax
0x18000fc95  mov     edx, 8
0x18000fc9a  mov     rbx, [rsp+28h+arg_0]
0x18000fc9f  add     rsp, 20h
0x18000fca3  pop     rdi
0x18000fca4  jmp     cs:__imp_HeapReAlloc
```
