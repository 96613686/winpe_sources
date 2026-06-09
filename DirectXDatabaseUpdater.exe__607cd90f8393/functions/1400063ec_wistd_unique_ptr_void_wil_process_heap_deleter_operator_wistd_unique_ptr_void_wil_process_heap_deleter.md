# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400063ec`
- end: `0x140006418`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400099ec`
- `0x14000cf30`

## callees

- `0x1400063ec`
- `0x14000704c`

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
0x1400063ec  push    rbx
0x1400063ee  sub     rsp, 20h
0x1400063f2  mov     rax, [rdx]
0x1400063f5  mov     rbx, rcx
0x1400063f8  mov     qword ptr [rdx], 0
0x1400063ff  mov     rcx, [rcx]; this
0x140006402  mov     [rbx], rax
0x140006405  test    rcx, rcx
0x140006408  jz      short loc_14000640F
0x14000640a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000640f  mov     rax, rbx
0x140006412  add     rsp, 20h
0x140006416  pop     rbx
0x140006417  retn
```
