# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1800057f8`
- end: `0x180005818`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e70`

## callees

- `0x1800057f8`
- `0x18000680c`

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
0x1800057f8  sub     rsp, 28h
0x1800057fc  mov     rax, [rcx]
0x1800057ff  mov     qword ptr [rcx], 0
0x180005806  test    rax, rax
0x180005809  jz      short loc_180005813
0x18000580b  mov     rcx, rax; this
0x18000580e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005813  add     rsp, 28h
0x180005817  retn
```
