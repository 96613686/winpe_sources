# CryptXmlAlloc

- ea: `0x18000b1a0`
- end: `0x18000b1d1`
- name: `CryptXmlAlloc`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800013a0`
- `0x180001d00`
- `0x180006150`
- `0x1800094a0`
- `0x180009a10`
- `0x180009f80`
- `0x18000a310`
- `0x18000b1e0`
- `0x18000b3b0`
- `0x18000f200`
- `0x18000fe50`
- `0x180016e40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b1c5`

## pseudocode

```c
LPVOID __fastcall CryptXmlAlloc(__int64 a1, SIZE_T a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 8u, a2);
}

```

## disassembly

```asm
0x18000b1a0  push    rbx
0x18000b1a2  sub     rsp, 20h
0x18000b1a6  mov     rbx, rdx
0x18000b1a9  call    cs:__imp_GetProcessHeap
0x18000b1b0  nop     dword ptr [rax+rax+00h]
0x18000b1b5  mov     r8, rbx
0x18000b1b8  mov     edx, 8
0x18000b1bd  mov     rcx, rax
0x18000b1c0  add     rsp, 20h
0x18000b1c4  pop     rbx
0x18000b1c5  jmp     cs:__imp_HeapAlloc
```
