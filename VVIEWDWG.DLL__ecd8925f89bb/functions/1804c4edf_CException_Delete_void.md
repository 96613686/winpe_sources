# CException::Delete(void)

- ea: `0x1804c4edf`
- end: `0x1804c4ee5`
- name: `?Delete@CException@@QEAAXXZ`
- size: `6`
- prototype: `void(CException *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1804d5535`

## import_xrefs

- `mfc140u!__imp_?Delete@CException@@QEAAXXZ` at `0x1804c4edf`

## pseudocode

```c
// attributes: thunk
void __fastcall CException::Delete(CException *this)
{
  __imp_?Delete@CException@@QEAAXXZ(this);
}

```

## disassembly

```asm
0x1804c4edf  jmp     cs:__imp_?Delete@CException@@QEAAXXZ
```
