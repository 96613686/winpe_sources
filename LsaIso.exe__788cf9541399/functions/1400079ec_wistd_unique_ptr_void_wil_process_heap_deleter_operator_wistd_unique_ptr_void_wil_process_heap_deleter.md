# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400079ec`
- end: `0x140007a10`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b888`
- `0x14000ca24`

## callees

- `0x140002040`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(void **a1, void **a2)
{
  void *v4; // rdx

  v4 = *a2;
  *a2 = 0;
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(a1, v4);
  return a1;
}

```

## disassembly

```asm
0x1400079ec  push    rbx
0x1400079ee  sub     rsp, 20h
0x1400079f2  mov     rax, rdx
0x1400079f5  mov     rbx, rcx
0x1400079f8  mov     rdx, [rdx]
0x1400079fb  mov     qword ptr [rax], 0
0x140007a02  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x140007a07  mov     rax, rbx
0x140007a0a  add     rsp, 20h
0x140007a0e  pop     rbx
0x140007a0f  retn
```
