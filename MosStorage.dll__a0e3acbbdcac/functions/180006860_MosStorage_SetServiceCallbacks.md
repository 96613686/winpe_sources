# MosStorage_SetServiceCallbacks

- ea: `0x180006860`
- end: `0x180006868`
- name: `MosStorage_SetServiceCallbacks`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall MosStorage_SetServiceCallbacks(__int64 a1)
{
  qword_1800184A8 = a1;
}

```

## disassembly

```asm
0x180006860  mov     cs:qword_1800184A8, rcx
0x180006867  retn
```
