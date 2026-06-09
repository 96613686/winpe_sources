# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180008bc8`
- end: `0x180008be8`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a60c`

## callees

- `0x180008bc8`
- `0x1800095cc`

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
0x180008bc8  sub     rsp, 28h
0x180008bcc  mov     rax, [rcx]
0x180008bcf  mov     qword ptr [rcx], 0
0x180008bd6  test    rax, rax
0x180008bd9  jz      short loc_180008BE3
0x180008bdb  mov     rcx, rax; this
0x180008bde  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008be3  add     rsp, 28h
0x180008be7  retn
```
