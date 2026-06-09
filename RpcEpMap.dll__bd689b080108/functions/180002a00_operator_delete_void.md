# operator delete(void *)

- ea: `0x180002a00`
- end: `0x180002a23`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `25`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002520`
- `0x1800029b8`
- `0x180002a2c`
- `0x180003288`
- `0x1800058d8`
- `0x180006a40`
- `0x180006ef0`
- `0x180007300`
- `0x1800073a0`
- `0x1800073e0`
- `0x180007410`
- `0x180007600`
- `0x1800078a0`
- `0x180007b30`
- `0x180007bc0`
- `0x180007c50`
- `0x180007cf0`
- `0x180009844`
- `0x1800098e4`
- `0x180009b54`
- `0x180009ba8`
- `0x180009d20`
- `0x180009df8`
- `0x18000a404`
- `0x18000a750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002a1c`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180002a00  push    rbx
0x180002a02  sub     rsp, 20h
0x180002a06  mov     rbx, rcx
0x180002a09  call    cs:__imp_GetProcessHeap
0x180002a0f  mov     r8, rbx
0x180002a12  xor     edx, edx
0x180002a14  mov     rcx, rax
0x180002a17  add     rsp, 20h
0x180002a1b  pop     rbx
0x180002a1c  jmp     cs:__imp_HeapFree
```
