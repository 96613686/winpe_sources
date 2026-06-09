# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180004148`
- end: `0x180004174`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008334`
- `0x180009ef8`

## callees

- `0x180004148`
- `0x180004cbc`

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
0x180004148  push    rbx
0x18000414a  sub     rsp, 20h
0x18000414e  mov     rax, [rdx]
0x180004151  mov     rbx, rcx
0x180004154  mov     qword ptr [rdx], 0
0x18000415b  mov     rcx, [rcx]; this
0x18000415e  mov     [rbx], rax
0x180004161  test    rcx, rcx
0x180004164  jz      short loc_18000416B
0x180004166  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000416b  mov     rax, rbx
0x18000416e  add     rsp, 20h
0x180004172  pop     rbx
0x180004173  retn
```
