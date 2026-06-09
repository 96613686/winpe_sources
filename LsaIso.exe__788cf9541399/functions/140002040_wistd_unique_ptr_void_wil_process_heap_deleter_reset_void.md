# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x140002040`
- end: `0x140002071`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140007940`
- `0x1400079b4`
- `0x1400079ec`
- `0x14000af14`
- `0x14000b058`
- `0x14000b888`
- `0x14000bb58`
- `0x14000c174`
- `0x14000ca24`
- `0x14000db64`

## callees

- `0x140002040`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002051`

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
0x140002040  push    rbx
0x140002042  sub     rsp, 20h
0x140002046  mov     rbx, [rcx]
0x140002049  mov     [rcx], rdx
0x14000204c  test    rbx, rbx
0x14000204f  jz      short loc_14000206B
0x140002051  call    cs:__imp_GetProcessHeap
0x140002057  mov     r8, rbx
0x14000205a  xor     edx, edx
0x14000205c  mov     rcx, rax
0x14000205f  add     rsp, 20h
0x140002063  pop     rbx
0x140002064  jmp     cs:__imp_HeapFree
0x14000206b  add     rsp, 20h
0x14000206f  pop     rbx
0x140002070  retn
```
