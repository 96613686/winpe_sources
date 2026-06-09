# CDynLinkLibrary::CDynLinkLibrary(AFX_EXTENSION_MODULE &,int)

- ea: `0x1804c7b30`
- end: `0x1804c7b36`
- name: `??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z`
- size: `6`
- prototype: `CDynLinkLibrary *(CDynLinkLibrary *__hidden this, struct AFX_EXTENSION_MODULE *, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1804c53c0`

## import_xrefs

- `mfc140u!__imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z` at `0x1804c7b30`

## pseudocode

```c
// attributes: thunk
CDynLinkLibrary *__fastcall CDynLinkLibrary::CDynLinkLibrary(
        CDynLinkLibrary *this,
        struct AFX_EXTENSION_MODULE *a2,
        int a3)
{
  return __imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z(this, a2, a3);
}

```

## disassembly

```asm
0x1804c7b30  jmp     cs:__imp_??0CDynLinkLibrary@@QEAA@AEAUAFX_EXTENSION_MODULE@@H@Z
```
