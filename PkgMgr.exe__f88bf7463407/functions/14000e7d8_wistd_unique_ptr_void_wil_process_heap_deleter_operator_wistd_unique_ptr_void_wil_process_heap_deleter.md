# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x14000e7d8`
- end: `0x14000e804`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f988`
- `0x140010278`

## callees

- `0x14000438c`
- `0x14000e7d8`

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
0x14000e7d8  push    rbx
0x14000e7da  sub     rsp, 20h
0x14000e7de  mov     rax, [rdx]
0x14000e7e1  mov     rbx, rcx
0x14000e7e4  mov     qword ptr [rdx], 0
0x14000e7eb  mov     rcx, [rcx]; this
0x14000e7ee  mov     [rbx], rax
0x14000e7f1  test    rcx, rcx
0x14000e7f4  jz      short loc_14000E7FB
0x14000e7f6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000e7fb  mov     rax, rbx
0x14000e7fe  add     rsp, 20h
0x14000e802  pop     rbx
0x14000e803  retn
```
