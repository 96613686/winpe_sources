# operator delete(void *,unsigned __int64)

- ea: `0x180003f6c`
- end: `0x180003f71`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001cc0`
- `0x180001e40`
- `0x180001f80`
- `0x180003f40`

## callees

- `0x180001be0`

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
0x180003f6c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
