# operator delete(void *,unsigned __int64)

- ea: `0x1800014a4`
- end: `0x1800014a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002270`
- `0x180002740`

## callees

- `0x180002220`

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
0x1800014a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
