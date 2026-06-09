# MIDL_user_free

- ea: `0x180007e10`
- end: `0x180007e22`
- name: `MIDL_user_free`
- size: `18`
- prototype: `void __stdcall(void *)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c10`
- `0x180009d60`
- `0x180009fa0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000bdf8`
- `0x18000c2d0`
- `0x18000c6ac`
- `0x18000c8c0`
- `0x18000cd3c`
- `0x18000d514`
- `0x18000df4c`
- `0x180016190`
- `0x180016c20`
- `0x180016ff0`
- `0x180017fbc`
- `0x18001806c`

## callees

- `0x180007e10`
- `0x180029010`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  if ( a1 )
    ((void (*)(void))qword_1800334A8)();
}

```

## disassembly

```asm
0x180007e10  test    rcx, rcx
0x180007e13  jz      short locret_180007E21
0x180007e15  mov     rax, cs:qword_1800334A8
0x180007e1c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180007e21  retn
```
