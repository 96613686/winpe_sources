# wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(void * &&,wil::process_heap_deleter &&)

- ea: `0x140008a40`
- end: `0x140008a4a`
- name: `??$?0PEAXUprocess_heap_deleter@wil@@@?$__compressed_pair@PEAXUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAPEAX$$QEAUprocess_heap_deleter@wil@@@Z`
- size: `10`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140008bc8`

## pseudocode

```c
_QWORD *__fastcall wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
        _QWORD *a1,
        _QWORD *a2)
{
  *a1 = *a2;
  return a1;
}

```

## disassembly

```asm
0x140008a40  mov     rax, [rdx]
0x140008a43  mov     [rcx], rax
0x140008a46  mov     rax, rcx
0x140008a49  retn
```
