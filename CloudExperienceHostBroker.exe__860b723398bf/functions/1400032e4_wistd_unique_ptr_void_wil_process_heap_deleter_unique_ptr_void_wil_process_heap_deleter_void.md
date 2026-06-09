# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1400032e4`
- end: `0x140003304`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046d4`

## callees

- `0x1400032e4`
- `0x1400037cc`

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
0x1400032e4  sub     rsp, 28h
0x1400032e8  mov     rax, [rcx]
0x1400032eb  mov     qword ptr [rcx], 0
0x1400032f2  test    rax, rax
0x1400032f5  jz      short loc_1400032FF
0x1400032f7  mov     rcx, rax; this
0x1400032fa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400032ff  add     rsp, 28h
0x140003303  retn
```
