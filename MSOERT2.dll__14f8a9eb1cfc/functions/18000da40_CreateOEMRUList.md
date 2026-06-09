# CreateOEMRUList

- ea: `0x18000da40`
- end: `0x18000da4d`
- name: `CreateOEMRUList`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000da60`

## pseudocode

```c
_QWORD *__fastcall CreateOEMRUList(__int64 a1)
{
  return CreateOEMRUListLazy(a1, 0, 0, 0);
}

```

## disassembly

```asm
0x18000da40  xor     r9d, r9d
0x18000da43  xor     r8d, r8d
0x18000da46  xor     edx, edx
0x18000da48  jmp     CreateOEMRUListLazy
```
