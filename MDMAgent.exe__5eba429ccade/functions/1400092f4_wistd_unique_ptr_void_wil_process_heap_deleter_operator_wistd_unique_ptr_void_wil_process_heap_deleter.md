# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400092f4`
- end: `0x140009320`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cbb4`
- `0x14001041c`

## callees

- `0x1400051cc`
- `0x1400092f4`

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
0x1400092f4  push    rbx
0x1400092f6  sub     rsp, 20h
0x1400092fa  mov     rax, [rdx]
0x1400092fd  mov     rbx, rcx
0x140009300  mov     qword ptr [rdx], 0
0x140009307  mov     rcx, [rcx]; this
0x14000930a  mov     [rbx], rax
0x14000930d  test    rcx, rcx
0x140009310  jz      short loc_140009317
0x140009312  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140009317  mov     rax, rbx
0x14000931a  add     rsp, 20h
0x14000931e  pop     rbx
0x14000931f  retn
```
