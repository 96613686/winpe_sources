# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1400095c4`
- end: `0x1400095f0`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f624`
- `0x14001109c`

## callees

- `0x14000438c`
- `0x1400095c4`

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
0x1400095c4  push    rbx
0x1400095c6  sub     rsp, 20h
0x1400095ca  mov     rax, [rdx]
0x1400095cd  mov     rbx, rcx
0x1400095d0  mov     qword ptr [rdx], 0
0x1400095d7  mov     rcx, [rcx]; this
0x1400095da  mov     [rbx], rax
0x1400095dd  test    rcx, rcx
0x1400095e0  jz      short loc_1400095E7
0x1400095e2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400095e7  mov     rax, rbx
0x1400095ea  add     rsp, 20h
0x1400095ee  pop     rbx
0x1400095ef  retn
```
