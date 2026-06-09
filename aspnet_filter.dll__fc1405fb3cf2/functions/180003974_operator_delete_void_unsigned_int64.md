# operator delete(void *,unsigned __int64)

- ea: `0x180003974`
- end: `0x180003979`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800028d0`

## callees

- `0x1800030cc`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180003974  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
