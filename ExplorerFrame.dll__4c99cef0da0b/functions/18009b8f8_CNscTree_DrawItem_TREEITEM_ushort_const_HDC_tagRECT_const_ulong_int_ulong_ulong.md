# CNscTree::_DrawItem(_TREEITEM *,ushort const *,HDC__ *,tagRECT const *,ulong,int,ulong,ulong)

- ea: `0x18009b8f8`
- end: `0x18009bcf2`
- name: `?_DrawItem@CNscTree@@AEAAXPEAU_TREEITEM@@PEBGPEAUHDC__@@PEBUtagRECT@@KHKK@Z`
- size: `1018`
- prototype: `void __usercall(CNscTree *__hidden this@<rcx>, struct _TREEITEM *@<rdx>, const unsigned __int16 *@<r8>, HDC@<r9>, const struct tagRECT *, unsigned int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800996f4`

## callees

- `0x18002c6b0`
- `0x180099660`
- `0x180099fe4`
- `0x18009b8f8`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801b78fc`
- `0x180208168`
- `0x180210010`

## import_xrefs

- `USER32!DrawTextW` at `0x18009bc7d`
- `USER32!DrawTextW` at `0x18009bc7d`
- `USER32!SendMessageW` at `0x18009b95b`
- `USER32!SendMessageW` at `0x18009b9eb`
- `USER32!SendMessageW` at `0x18009baa8`
- `USER32!SendMessageW` at `0x18009b95b`
- `USER32!SendMessageW` at `0x18009b9eb`
- `USER32!SendMessageW` at `0x18009baa8`
- `USER32!GetSysColor` at `0x18009b984`
- `USER32!GetSysColor` at `0x18009ba4c`
- `USER32!GetSysColor` at `0x18009b984`
- `USER32!GetSysColor` at `0x18009ba4c`
- `GDI32!SetTextColor` at `0x18009bc05`
- `GDI32!SetTextColor` at `0x18009bc05`
- `GDI32!GetTextExtentPoint32W` at `0x18009bb32`
- `GDI32!GetTextExtentPoint32W` at `0x18009bb32`
- `GDI32!DeleteObject` at `0x18009bccc`
- `GDI32!DeleteObject` at `0x18009bccc`
- `GDI32!SelectObject` at `0x18009bb00`
- `GDI32!SelectObject` at `0x18009bcbe`
- `GDI32!SelectObject` at `0x18009bb00`
- `GDI32!SelectObject` at `0x18009bcbe`
- `GDI32!CreateFontIndirectW` at `0x18009baea`
- `GDI32!CreateFontIndirectW` at `0x18009baea`
- `GDI32!SetBkColor` at `0x18009bbc5`
- `GDI32!SetBkColor` at `0x18009bbc5`
- `GDI32!GetObjectW` at `0x18009baba`
- `GDI32!GetObjectW` at `0x18009baba`
- `GDI32!ExtTextOutW` at `0x18009bbf4`
- `GDI32!ExtTextOutW` at `0x18009bbf4`

## pseudocode

```c

```
