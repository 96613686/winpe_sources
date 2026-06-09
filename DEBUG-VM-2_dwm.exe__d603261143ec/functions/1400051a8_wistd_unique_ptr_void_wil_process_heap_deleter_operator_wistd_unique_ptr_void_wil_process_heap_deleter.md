# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400051a8`
- end: `0x1400051d4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004dec`
- `0x140005104`

## callees

- `0x1400051a8`
- `0x14000886c`

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
0x1400051a8  push    rbx
0x1400051aa  sub     rsp, 20h
0x1400051ae  mov     rax, [rdx]
0x1400051b1  mov     rbx, rcx
0x1400051b4  mov     qword ptr [rdx], 0
0x1400051bb  mov     rcx, [rcx]; this
0x1400051be  mov     [rbx], rax
0x1400051c1  test    rcx, rcx
0x1400051c4  jz      short loc_1400051CB
0x1400051c6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400051cb  mov     rax, rbx
0x1400051ce  add     rsp, 20h
0x1400051d2  pop     rbx
0x1400051d3  retn
```
