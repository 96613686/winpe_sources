# HttpExtensionProc$dtor$0

- ea: `0x18000fe68`
- end: `0x18000fe74`
- name: `HttpExtensionProc$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x180002118`

## pseudocode

```c
void __fastcall HttpExtensionProc_dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x18000fe68  mov     rcx, [rdx+38h]; void *
0x18000fe6f  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
