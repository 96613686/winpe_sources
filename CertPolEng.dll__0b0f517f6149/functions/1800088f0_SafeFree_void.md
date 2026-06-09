# SafeFree(void *)

- ea: `0x1800088f0`
- end: `0x180008923`
- name: `?SafeFree@@YAHPEAX@Z`
- size: `51`
- prototype: `BOOL __fastcall(void *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000ab5c`
- `0x18000b3c4`
- `0x180018f50`
- `0x180019024`
- `0x1800191fc`
- `0x180019a54`

## callees

- `0x1800088f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008909`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008909`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891c`

## pseudocode

```c
BOOL __fastcall SafeFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  if ( !a1 )
    return 1;
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1800088f0  push    rbx
0x1800088f2  sub     rsp, 20h
0x1800088f6  mov     rbx, rcx
0x1800088f9  test    rcx, rcx
0x1800088fc  jnz     short loc_180008909
0x1800088fe  mov     eax, 1
0x180008903  add     rsp, 20h
0x180008907  pop     rbx
0x180008908  retn
0x180008909  call    cs:__imp_GetProcessHeap
0x18000890f  mov     r8, rbx
0x180008912  xor     edx, edx
0x180008914  mov     rcx, rax
0x180008917  add     rsp, 20h
0x18000891b  pop     rbx
0x18000891c  jmp     cs:__imp_HeapFree
```
