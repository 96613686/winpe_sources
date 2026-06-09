# CWStringArray::Compress(void)

- ea: `0x180011b30`
- end: `0x180011b37`
- name: `?Compress@CWStringArray@@QEAAXXZ`
- size: `7`
- prototype: `void __fastcall(CWStringArray *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `wbemcomn!?Compress@CFlexArray@@QEAAXXZ` at `0x180011b30`

## pseudocode

```c
// attributes: thunk
void __fastcall CWStringArray::Compress(CWStringArray *this)
{
  CFlexArray::Compress(this);
}

```

## disassembly

```asm
0x180011b30  jmp     cs:__imp_?Compress@CFlexArray@@QEAAXXZ; CFlexArray::Compress(void)
```
