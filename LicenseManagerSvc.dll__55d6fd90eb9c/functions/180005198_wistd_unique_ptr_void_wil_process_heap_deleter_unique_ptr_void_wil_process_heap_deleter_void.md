# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180005198`
- end: `0x1800051b8`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006538`

## callees

- `0x180002744`
- `0x180005198`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    MemoryFree(v1);
}

```

## disassembly

```asm
0x180005198  sub     rsp, 28h
0x18000519c  mov     rax, [rcx]
0x18000519f  mov     qword ptr [rcx], 0
0x1800051a6  test    rax, rax
0x1800051a9  jz      short loc_1800051B3
0x1800051ab  mov     rcx, rax; void *
0x1800051ae  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800051b3  add     rsp, 28h
0x1800051b7  retn
```
