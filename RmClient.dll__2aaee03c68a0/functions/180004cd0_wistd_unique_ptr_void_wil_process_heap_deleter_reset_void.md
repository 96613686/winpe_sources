# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x180004cd0`
- end: `0x180004cfd`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `45`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180005590`
- `0x1800058c0`
- `0x180005cf0`
- `0x180005e60`
- `0x180005fb8`
- `0x180006130`
- `0x18000ba60`
- `0x18000ef38`
- `0x1800133c0`
- `0x180016a08`
- `0x180016b4c`

## callees

- `0x180004cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce7`

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
0x180004cd0  push    rbx
0x180004cd2  sub     rsp, 20h
0x180004cd6  mov     rbx, [rcx]
0x180004cd9  mov     [rcx], rdx
0x180004cdc  test    rbx, rbx
0x180004cdf  jnz     short loc_180004CE7
0x180004ce1  add     rsp, 20h
0x180004ce5  pop     rbx
0x180004ce6  retn
0x180004ce7  call    cs:__imp_GetProcessHeap
0x180004ced  mov     r8, rbx; lpMem
0x180004cf0  xor     edx, edx; dwFlags
0x180004cf2  mov     rcx, rax; hHeap
0x180004cf5  call    cs:__imp_HeapFree
0x180004cfb  jmp     short loc_180004CE1
```
