# CloseDbgSection(void *,void *)

- ea: `0x180009990`
- end: `0x1800099b1`
- name: `?CloseDbgSection@@YAXPEAX0@Z`
- size: `33`
- prototype: `void(void *, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007440`
- `0x180009d20`
- `0x180009df8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099aa`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000999c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000999c`

## pseudocode

```c
void __fastcall CloseDbgSection(void *a1, void *a2)
{
  UnmapViewOfFile(a2);
  CloseHandle(a1);
}

```

## disassembly

```asm
0x180009990  push    rbx
0x180009992  sub     rsp, 20h
0x180009996  mov     rbx, rcx
0x180009999  mov     rcx, rdx; lpBaseAddress
0x18000999c  call    cs:__imp_UnmapViewOfFile
0x1800099a2  mov     rcx, rbx
0x1800099a5  add     rsp, 20h
0x1800099a9  pop     rbx
0x1800099aa  jmp     cs:__imp_CloseHandle
```
