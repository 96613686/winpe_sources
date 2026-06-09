# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x140008120`
- end: `0x14000814c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004088`
- `0x14000807c`

## callees

- `0x1400079c4`
- `0x140008120`

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
0x140008120  push    rbx
0x140008122  sub     rsp, 20h
0x140008126  mov     rax, [rdx]
0x140008129  mov     rbx, rcx
0x14000812c  mov     qword ptr [rdx], 0
0x140008133  mov     rcx, [rcx]; this
0x140008136  mov     [rbx], rax
0x140008139  test    rcx, rcx
0x14000813c  jz      short loc_140008143
0x14000813e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140008143  mov     rax, rbx
0x140008146  add     rsp, 20h
0x14000814a  pop     rbx
0x14000814b  retn
```
