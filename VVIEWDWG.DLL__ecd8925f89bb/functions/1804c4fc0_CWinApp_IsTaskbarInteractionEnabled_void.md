# CWinApp::IsTaskbarInteractionEnabled(void)

- ea: `0x1804c4fc0`
- end: `0x1804c4fc6`
- name: `?IsTaskbarInteractionEnabled@CWinApp@@UEAAHXZ`
- size: `6`
- prototype: `int(CWinApp *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `mfc140u!__imp_?IsTaskbarInteractionEnabled@CWinApp@@UEAAHXZ` at `0x1804c4fc0`

## pseudocode

```c
// attributes: thunk
int __fastcall CWinApp::IsTaskbarInteractionEnabled(CWinApp *this)
{
  return __imp_?IsTaskbarInteractionEnabled@CWinApp@@UEAAHXZ(this);
}

```

## disassembly

```asm
0x1804c4fc0  jmp     cs:__imp_?IsTaskbarInteractionEnabled@CWinApp@@UEAAHXZ
```
