# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400050cc`
- end: `0x1400050f0`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000798c`
- `0x140008d0c`

## callees

- `0x140002c70`

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
0x1400050cc  push    rbx
0x1400050ce  sub     rsp, 20h
0x1400050d2  mov     rax, rdx
0x1400050d5  mov     rbx, rcx
0x1400050d8  mov     rdx, [rdx]
0x1400050db  mov     qword ptr [rax], 0
0x1400050e2  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x1400050e7  mov     rax, rbx
0x1400050ea  add     rsp, 20h
0x1400050ee  pop     rbx
0x1400050ef  retn
```
