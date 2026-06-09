# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x14000294c`
- end: `0x14000296c`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c80`

## callees

- `0x14000294c`
- `0x140002d7c`

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
0x14000294c  sub     rsp, 28h
0x140002950  mov     rax, [rcx]
0x140002953  mov     qword ptr [rcx], 0
0x14000295a  test    rax, rax
0x14000295d  jz      short loc_140002967
0x14000295f  mov     rcx, rax; this
0x140002962  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140002967  add     rsp, 28h
0x14000296b  retn
```
