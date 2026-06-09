# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x140004b70`
- end: `0x140004b90`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400062dc`

## callees

- `0x140004b70`
- `0x14000517c`

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
0x140004b70  sub     rsp, 28h
0x140004b74  mov     rax, [rcx]
0x140004b77  mov     qword ptr [rcx], 0
0x140004b7e  test    rax, rax
0x140004b81  jz      short loc_140004B8B
0x140004b83  mov     rcx, rax; this
0x140004b86  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140004b8b  add     rsp, 28h
0x140004b8f  retn
```
