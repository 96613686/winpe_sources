# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x140002c70`
- end: `0x140002ca1`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fd0`
- `0x140005074`
- `0x1400050cc`
- `0x140006e0c`
- `0x140006f70`
- `0x14000798c`
- `0x140007ca0`
- `0x14000852c`
- `0x140008d0c`
- `0x140009814`

## callees

- `0x140002c70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002c94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002c81`

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
0x140002c70  push    rbx
0x140002c72  sub     rsp, 20h
0x140002c76  mov     rbx, [rcx]
0x140002c79  mov     [rcx], rdx
0x140002c7c  test    rbx, rbx
0x140002c7f  jz      short loc_140002C9B
0x140002c81  call    cs:__imp_GetProcessHeap
0x140002c87  mov     r8, rbx
0x140002c8a  xor     edx, edx
0x140002c8c  mov     rcx, rax
0x140002c8f  add     rsp, 20h
0x140002c93  pop     rbx
0x140002c94  jmp     cs:__imp_HeapFree
0x140002c9b  add     rsp, 20h
0x140002c9f  pop     rbx
0x140002ca0  retn
```
