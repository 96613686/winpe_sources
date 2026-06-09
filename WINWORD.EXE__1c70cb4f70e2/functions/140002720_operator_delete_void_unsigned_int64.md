# operator delete(void *,unsigned __int64)

- ea: `0x140002720`
- end: `0x140002725`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001cc0`

## callees

- `0x14000449c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(Mso::Memory *a1, void *a2)
{
  ??3@YAXPEAX@Z(a1, a2);
}

```

## disassembly

```asm
0x140002720  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
