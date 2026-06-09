# operator delete(void *,unsigned __int64)

- ea: `0x180002af0`
- end: `0x180002af5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004200`
- `0x180004260`
- `0x1800042a0`
- `0x1800081d0`
- `0x18000887c`
- `0x1800089d0`
- `0x180008b50`
- `0x180008c10`
- `0x180008c40`
- `0x180008c80`
- `0x180008cc0`
- `0x180008d20`
- `0x1800098d0`

## callees

- `0x180002b2c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002af0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
