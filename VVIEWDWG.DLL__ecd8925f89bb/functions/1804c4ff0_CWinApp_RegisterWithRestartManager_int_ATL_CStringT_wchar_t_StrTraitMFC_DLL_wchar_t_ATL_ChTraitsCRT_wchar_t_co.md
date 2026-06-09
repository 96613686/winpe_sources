# CWinApp::RegisterWithRestartManager(int,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)

- ea: `0x1804c4ff0`
- end: `0x1804c4ff6`
- name: `?RegisterWithRestartManager@CWinApp@@UEAAJHAEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `mfc140u!__imp_?RegisterWithRestartManager@CWinApp@@UEAAJHAEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z` at `0x1804c4ff0`

## pseudocode

```c
// attributes: thunk
__int64 CWinApp::RegisterWithRestartManager()
{
  return __imp_?RegisterWithRestartManager@CWinApp@@UEAAJHAEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z();
}

```

## disassembly

```asm
0x1804c4ff0  jmp     cs:__imp_?RegisterWithRestartManager@CWinApp@@UEAAJHAEBV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z
```
