# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180007440`
- end: `0x180007460`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087d8`

## callees

- `0x180007440`
- `0x180007b1c`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    wil::details::FreeProcessHeap(v2, a2);
}

```

## disassembly

```asm
0x180007440  sub     rsp, 28h
0x180007444  mov     rax, [rcx]
0x180007447  mov     qword ptr [rcx], 0
0x18000744e  test    rax, rax
0x180007451  jz      short loc_18000745B
0x180007453  mov     rcx, rax; this
0x180007456  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000745b  add     rsp, 28h
0x18000745f  retn
```
