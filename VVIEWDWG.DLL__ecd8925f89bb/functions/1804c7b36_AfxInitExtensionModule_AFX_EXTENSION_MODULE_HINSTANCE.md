# AfxInitExtensionModule(AFX_EXTENSION_MODULE &,HINSTANCE__ *)

- ea: `0x1804c7b36`
- end: `0x1804c7b3c`
- name: `?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z`
- size: `6`
- prototype: `int(struct AFX_EXTENSION_MODULE *, HINSTANCE)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1804c53c0`

## import_xrefs

- `mfc140u!__imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z` at `0x1804c7b36`

## pseudocode

```c
// attributes: thunk
int __fastcall AfxInitExtensionModule(struct AFX_EXTENSION_MODULE *a1, HINSTANCE a2)
{
  return __imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z(a1, a2);
}

```

## disassembly

```asm
0x1804c7b36  jmp     cs:__imp_?AfxInitExtensionModule@@YAHAEAUAFX_EXTENSION_MODULE@@PEAUHINSTANCE__@@@Z
```
