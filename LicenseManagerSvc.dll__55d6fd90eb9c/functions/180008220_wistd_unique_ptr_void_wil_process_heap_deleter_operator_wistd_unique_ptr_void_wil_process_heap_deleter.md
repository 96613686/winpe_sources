# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180008220`
- end: `0x18000824c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e74`
- `0x18000ad54`

## callees

- `0x180002744`
- `0x180008220`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(void **a1, void **a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    MemoryFree(v4);
  return a1;
}

```

## disassembly

```asm
0x180008220  push    rbx
0x180008222  sub     rsp, 20h
0x180008226  mov     rax, [rdx]
0x180008229  mov     rbx, rcx
0x18000822c  mov     qword ptr [rdx], 0
0x180008233  mov     rcx, [rcx]; void *
0x180008236  mov     [rbx], rax
0x180008239  test    rcx, rcx
0x18000823c  jz      short loc_180008243
0x18000823e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180008243  mov     rax, rbx
0x180008246  add     rsp, 20h
0x18000824a  pop     rbx
0x18000824b  retn
```
