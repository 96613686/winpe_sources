# AfxTermExtensionModule(AFX_EXTENSION_MODULE &,int)

- ea: `0x1804c7b3c`
- end: `0x1804c7b42`
- name: `?AfxTermExtensionModule@@YAXAEAUAFX_EXTENSION_MODULE@@H@Z`
- size: `6`
- prototype: `void(struct AFX_EXTENSION_MODULE *, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1804c53c0`

## import_xrefs

- `mfc140u!__imp_?AfxTermExtensionModule@@YAXAEAUAFX_EXTENSION_MODULE@@H@Z` at `0x1804c7b3c`

## pseudocode

```c
// attributes: thunk
void __fastcall AfxTermExtensionModule(struct AFX_EXTENSION_MODULE *a1, int a2)
{
  __imp_?AfxTermExtensionModule@@YAXAEAUAFX_EXTENSION_MODULE@@H@Z(a1, a2);
}

```

## disassembly

```asm
0x1804c7b3c  jmp     cs:__imp_?AfxTermExtensionModule@@YAXAEAUAFX_EXTENSION_MODULE@@H@Z
```
