# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180008344`
- end: `0x180008370`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b60`
- `0x180005824`
- `0x1800095a8`

## callees

- `0x180006484`
- `0x180008344`

## pseudocode

```c
wil::details **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(
        wil::details **a1,
        wil::details **a2)
{
  wil::details *v2; // rax
  wil::details *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x180008344  push    rbx
0x180008346  sub     rsp, 20h
0x18000834a  mov     rax, [rdx]
0x18000834d  mov     rbx, rcx
0x180008350  mov     qword ptr [rdx], 0
0x180008357  mov     rcx, [rcx]; this
0x18000835a  mov     [rbx], rax
0x18000835d  test    rcx, rcx
0x180008360  jz      short loc_180008367
0x180008362  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008367  mov     rax, rbx
0x18000836a  add     rsp, 20h
0x18000836e  pop     rbx
0x18000836f  retn
```
