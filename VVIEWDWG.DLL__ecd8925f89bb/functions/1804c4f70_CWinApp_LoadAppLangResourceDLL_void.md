# CWinApp::LoadAppLangResourceDLL(void)

- ea: `0x1804c4f70`
- end: `0x1804c4f76`
- name: `?LoadAppLangResourceDLL@CWinApp@@UEAAPEAUHINSTANCE__@@XZ`
- size: `6`
- prototype: `HINSTANCE(CWinApp *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `mfc140u!__imp_?LoadAppLangResourceDLL@CWinApp@@UEAAPEAUHINSTANCE__@@XZ` at `0x1804c4f70`

## pseudocode

```c
// attributes: thunk
HINSTANCE __fastcall CWinApp::LoadAppLangResourceDLL(CWinApp *this)
{
  return __imp_?LoadAppLangResourceDLL@CWinApp@@UEAAPEAUHINSTANCE__@@XZ(this);
}

```

## disassembly

```asm
0x1804c4f70  jmp     cs:__imp_?LoadAppLangResourceDLL@CWinApp@@UEAAPEAUHINSTANCE__@@XZ
```
