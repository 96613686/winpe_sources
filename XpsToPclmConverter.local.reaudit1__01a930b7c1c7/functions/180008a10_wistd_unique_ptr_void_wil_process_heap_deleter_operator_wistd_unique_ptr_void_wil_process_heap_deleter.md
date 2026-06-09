# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180008a10`
- end: `0x180008a3c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b0b0`
- `0x18000c310`

## callees

- `0x180008a10`
- `0x1800093fc`

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
0x180008a10  push    rbx
0x180008a12  sub     rsp, 20h
0x180008a16  mov     rax, [rdx]
0x180008a19  mov     rbx, rcx
0x180008a1c  mov     qword ptr [rdx], 0
0x180008a23  mov     rcx, [rcx]; this
0x180008a26  mov     [rbx], rax
0x180008a29  test    rcx, rcx
0x180008a2c  jz      short loc_180008A33
0x180008a2e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008a33  mov     rax, rbx
0x180008a36  add     rsp, 20h
0x180008a3a  pop     rbx
0x180008a3b  retn
```
