# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180007fac`
- end: `0x180007fd8`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009844`
- `0x18000a508`

## callees

- `0x18000544c`
- `0x180007fac`

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
0x180007fac  push    rbx
0x180007fae  sub     rsp, 20h
0x180007fb2  mov     rax, [rdx]
0x180007fb5  mov     rbx, rcx
0x180007fb8  mov     qword ptr [rdx], 0
0x180007fbf  mov     rcx, [rcx]; this
0x180007fc2  mov     [rbx], rax
0x180007fc5  test    rcx, rcx
0x180007fc8  jz      short loc_180007FCF
0x180007fca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007fcf  mov     rax, rbx
0x180007fd2  add     rsp, 20h
0x180007fd6  pop     rbx
0x180007fd7  retn
```
