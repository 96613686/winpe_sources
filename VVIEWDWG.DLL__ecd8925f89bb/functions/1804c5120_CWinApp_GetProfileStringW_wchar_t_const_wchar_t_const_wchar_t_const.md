# CWinApp::GetProfileStringW(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1804c5120`
- end: `0x1804c5126`
- name: `?GetProfileStringW@CWinApp@@UEAA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_W00@Z`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `mfc140u!__imp_?GetProfileStringW@CWinApp@@UEAA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_W00@Z` at `0x1804c5120`

## pseudocode

```c
// attributes: thunk
__int64 CWinApp::GetProfileStringW()
{
  return __imp_?GetProfileStringW@CWinApp@@UEAA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_W00@Z();
}

```

## disassembly

```asm
0x1804c5120  jmp     cs:__imp_?GetProfileStringW@CWinApp@@UEAA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_W00@Z
```
