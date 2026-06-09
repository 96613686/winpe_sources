# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x140002464`
- end: `0x140002490`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d6c`
- `0x1400023c0`

## callees

- `0x140002464`
- `0x14000469c`

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
0x140002464  push    rbx
0x140002466  sub     rsp, 20h
0x14000246a  mov     rax, [rdx]
0x14000246d  mov     rbx, rcx
0x140002470  mov     qword ptr [rdx], 0
0x140002477  mov     rcx, [rcx]; this
0x14000247a  mov     [rbx], rax
0x14000247d  test    rcx, rcx
0x140002480  jz      short loc_140002487
0x140002482  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140002487  mov     rax, rbx
0x14000248a  add     rsp, 20h
0x14000248e  pop     rbx
0x14000248f  retn
```
