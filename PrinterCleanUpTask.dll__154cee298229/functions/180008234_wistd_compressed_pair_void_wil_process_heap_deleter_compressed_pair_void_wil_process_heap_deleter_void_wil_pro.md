# wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(void * &&,wil::process_heap_deleter &&)

- ea: `0x180008234`
- end: `0x18000823e`
- name: `??$?0PEAXUprocess_heap_deleter@wil@@@?$__compressed_pair@PEAXUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAPEAX$$QEAUprocess_heap_deleter@wil@@@Z`
- size: `10`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800099bc`
- `0x18000b308`
- `0x18001137c`

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
0x180008234  mov     rax, [rdx]
0x180008237  mov     [rcx], rax
0x18000823a  mov     rax, rcx
0x18000823d  retn
```
