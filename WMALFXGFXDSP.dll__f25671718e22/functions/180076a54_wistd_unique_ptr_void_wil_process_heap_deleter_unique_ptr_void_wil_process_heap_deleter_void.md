# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180076a54`
- end: `0x180076a74`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180078694`

## callees

- `0x180076a54`
- `0x180077574`

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
0x180076a54  sub     rsp, 28h
0x180076a58  mov     rax, [rcx]
0x180076a5b  mov     qword ptr [rcx], 0
0x180076a62  test    rax, rax
0x180076a65  jz      short loc_180076A6F
0x180076a67  mov     rcx, rax; this
0x180076a6a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180076a6f  add     rsp, 28h
0x180076a73  retn
```
