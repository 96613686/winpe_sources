# CWinApp::OnDDECommand(wchar_t *)

- ea: `0x1804c5040`
- end: `0x1804c5046`
- name: `?OnDDECommand@CWinApp@@UEAAHPEA_W@Z`
- size: `6`
- prototype: `int(CWinApp *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `mfc140u!__imp_?OnDDECommand@CWinApp@@UEAAHPEA_W@Z` at `0x1804c5040`

## pseudocode

```c
// attributes: thunk
int __fastcall CWinApp::OnDDECommand(CWinApp *this, wchar_t *a2)
{
  return __imp_?OnDDECommand@CWinApp@@UEAAHPEA_W@Z(this, a2);
}

```

## disassembly

```asm
0x1804c5040  jmp     cs:__imp_?OnDDECommand@CWinApp@@UEAAHPEA_W@Z
```
