# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x180005950`
- end: `0x180005981`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b60`
- `0x1800056fc`
- `0x180005824`
- `0x1800058d4`
- `0x1800095a8`
- `0x180009698`
- `0x18000983c`
- `0x180009990`
- `0x18000bff0`
- `0x18000cc9c`

## callees

- `0x180005950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005961`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005974`

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
0x180005950  push    rbx
0x180005952  sub     rsp, 20h
0x180005956  mov     rbx, [rcx]
0x180005959  mov     [rcx], rdx
0x18000595c  test    rbx, rbx
0x18000595f  jz      short loc_18000597B
0x180005961  call    cs:__imp_GetProcessHeap
0x180005967  mov     r8, rbx
0x18000596a  xor     edx, edx
0x18000596c  mov     rcx, rax
0x18000596f  add     rsp, 20h
0x180005973  pop     rbx
0x180005974  jmp     cs:__imp_HeapFree
0x18000597b  add     rsp, 20h
0x18000597f  pop     rbx
0x180005980  retn
```
