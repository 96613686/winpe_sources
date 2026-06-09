# CCmdTarget::GetCommandMap(void)

- ea: `0x1804c51e0`
- end: `0x1804c51e6`
- name: `?GetCommandMap@CCmdTarget@@MEBAPEBUAFX_OLECMDMAP@@XZ`
- size: `6`
- prototype: `const struct AFX_OLECMDMAP *(CCmdTarget *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `mfc140u!__imp_?GetCommandMap@CCmdTarget@@MEBAPEBUAFX_OLECMDMAP@@XZ` at `0x1804c51e0`

## pseudocode

```c
// attributes: thunk
const struct AFX_OLECMDMAP *__fastcall CCmdTarget::GetCommandMap(CCmdTarget *this)
{
  return __imp_?GetCommandMap@CCmdTarget@@MEBAPEBUAFX_OLECMDMAP@@XZ(this);
}

```

## disassembly

```asm
0x1804c51e0  jmp     cs:__imp_?GetCommandMap@CCmdTarget@@MEBAPEBUAFX_OLECMDMAP@@XZ
```
