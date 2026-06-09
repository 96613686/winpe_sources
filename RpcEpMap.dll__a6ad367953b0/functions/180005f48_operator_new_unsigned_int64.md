# operator new(unsigned __int64)

- ea: `0x180005f48`
- end: `0x180005f6e`
- name: `??2@YAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800058d8`
- `0x180005994`
- `0x180007b30`
- `0x180007bc0`
- `0x180007c50`
- `0x180007cf0`
- `0x180009844`
- `0x1800098e4`
- `0x180009df8`
- `0x18000a404`
- `0x18000a490`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f51`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005f67`

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
0x180005f48  push    rbx
0x180005f4a  sub     rsp, 20h
0x180005f4e  mov     rbx, rcx
0x180005f51  call    cs:__imp_GetProcessHeap
0x180005f57  mov     r8, rbx
0x180005f5a  mov     edx, 8
0x180005f5f  mov     rcx, rax
0x180005f62  add     rsp, 20h
0x180005f66  pop     rbx
0x180005f67  jmp     cs:__imp_HeapAlloc
```
