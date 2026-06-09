# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400096e4`
- end: `0x140009711`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d19c`
- `0x140010c4c`

## callees

- `0x140005344`
- `0x1400096e4`

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
0x1400096e4  push    rbx
0x1400096e6  sub     rsp, 20h
0x1400096ea  mov     rax, [rdx]
0x1400096ed  mov     rbx, rcx
0x1400096f0  mov     qword ptr [rdx], 0
0x1400096f7  mov     rcx, [rcx]; this
0x1400096fa  mov     [rbx], rax
0x1400096fd  test    rcx, rcx
0x140009700  jz      short loc_140009707
0x140009702  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140009707  mov     rax, rbx
0x14000970a  add     rsp, 20h
0x14000970e  pop     rbx
0x14000970f  retn
```
