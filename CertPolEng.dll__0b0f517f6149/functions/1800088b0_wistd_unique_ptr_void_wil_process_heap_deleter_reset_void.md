# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x1800088b0`
- end: `0x1800088e1`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b664`
- `0x18000dd00`
- `0x180010784`
- `0x1800108d4`
- `0x1800110fc`
- `0x18001164c`
- `0x1800129f4`

## callees

- `0x1800088b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088d4`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void **a1, void *a2)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x1800088b0  push    rbx
0x1800088b2  sub     rsp, 20h
0x1800088b6  mov     rbx, [rcx]
0x1800088b9  mov     [rcx], rdx
0x1800088bc  test    rbx, rbx
0x1800088bf  jz      short loc_1800088DB
0x1800088c1  call    cs:__imp_GetProcessHeap
0x1800088c7  mov     r8, rbx
0x1800088ca  xor     edx, edx
0x1800088cc  mov     rcx, rax
0x1800088cf  add     rsp, 20h
0x1800088d3  pop     rbx
0x1800088d4  jmp     cs:__imp_HeapFree
0x1800088db  add     rsp, 20h
0x1800088df  pop     rbx
0x1800088e0  retn
```
