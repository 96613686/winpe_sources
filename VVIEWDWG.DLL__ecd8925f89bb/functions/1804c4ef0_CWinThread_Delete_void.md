# CWinThread::Delete(void)

- ea: `0x1804c4ef0`
- end: `0x1804c4ef6`
- name: `?Delete@CWinThread@@UEAAXXZ`
- size: `6`
- prototype: `void(CWinThread *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `mfc140u!__imp_?Delete@CWinThread@@UEAAXXZ` at `0x1804c4ef0`

## pseudocode

```c
// attributes: thunk
void __fastcall CWinThread::Delete(CWinThread *this)
{
  __imp_?Delete@CWinThread@@UEAAXXZ(this);
}

```

## disassembly

```asm
0x1804c4ef0  jmp     cs:__imp_?Delete@CWinThread@@UEAAXXZ
```
