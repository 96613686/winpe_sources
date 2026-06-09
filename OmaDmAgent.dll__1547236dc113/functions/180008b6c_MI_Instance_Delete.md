# MI_Instance_Delete

- ea: `0x180008b6c`
- end: `0x180008b88`
- name: `MI_Instance_Delete`
- size: `28`
- prototype: `static MI_Result __stdcall(MI_Instance *self)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007edc`
- `0x180009304`

## callees

- `0x180008b6c`
- `0x180021010`

## pseudocode

```c
MI_Result __stdcall MI_Instance_Delete(MI_Instance *self)
{
  if ( self && self->ft )
    return ((unsigned int (__fastcall *)(MI_Instance *))self->ft->Delete)(self);
  else
    return 4;
}

```

## disassembly

```asm
0x180008b6c  test    rcx, rcx
0x180008b6f  jz      short loc_180008B82
0x180008b71  mov     rax, [rcx]
0x180008b74  test    rax, rax
0x180008b77  jz      short loc_180008B82
0x180008b79  mov     rax, [rax+10h]
0x180008b7d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180008b82  mov     eax, 4
0x180008b87  retn
```
