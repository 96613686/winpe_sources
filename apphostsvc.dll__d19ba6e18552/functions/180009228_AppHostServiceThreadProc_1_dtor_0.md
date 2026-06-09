# _AppHostServiceThreadProc_::_1_::dtor$0

- ea: `0x180009228`
- end: `0x180009234`
- name: `_AppHostServiceThreadProc_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x180001048`

## pseudocode

```c
void __fastcall AppHostServiceThreadProc_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x180009228  mov     rcx, [rdx+38h]; Block
0x18000922f  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
