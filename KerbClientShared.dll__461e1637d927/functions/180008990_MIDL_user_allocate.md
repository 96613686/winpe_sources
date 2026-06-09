# MIDL_user_allocate

- ea: `0x180008990`
- end: `0x18000899c`
- name: `MIDL_user_allocate`
- size: `12`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e30`
- `0x180008c60`
- `0x180009d60`
- `0x18000a920`
- `0x18000be90`
- `0x18000df4c`
- `0x18000e3dc`
- `0x180016680`
- `0x180016c20`
- `0x180017fbc`
- `0x18001806c`
- `0x180018280`

## callees

- `0x180029010`

## pseudocode

```c
void *__stdcall MIDL_user_allocate(size_t size)
{
  return (void *)((__int64 (__fastcall *)(size_t))qword_1800334A0)(size);
}

```

## disassembly

```asm
0x180008990  mov     rax, cs:qword_1800334A0
0x180008997  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
