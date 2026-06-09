# CInplaceRename::_PaintComposition(HWND__ *)

- ea: `0x18008444c`
- end: `0x18008462b`
- name: `?_PaintComposition@CInplaceRename@@AEAAXPEAUHWND__@@@Z`
- size: `479`
- prototype: `void(CInplaceRename *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800846ac`

## callees

- `0x1800236e8`
- `0x18008444c`
- `0x18013f7d0`

## import_xrefs

- `IMM32!ImmReleaseContext` at `0x1800844ce`
- `IMM32!ImmReleaseContext` at `0x1800844ce`
- `IMM32!ImmGetContext` at `0x180084480`
- `IMM32!ImmGetContext` at `0x180084480`
- `IMM32!ImmGetCompositionStringW` at `0x1800844a7`
- `IMM32!ImmGetCompositionStringW` at `0x1800844c2`
- `IMM32!ImmGetCompositionStringW` at `0x1800844a7`
- `IMM32!ImmGetCompositionStringW` at `0x1800844c2`
- `USER32!ValidateRect` at `0x1800845f9`
- `USER32!ValidateRect` at `0x1800845f9`
- `USER32!GetDC` at `0x180084539`
- `USER32!GetDC` at `0x180084539`
- `USER32!SendMessageW` at `0x180084505`
- `USER32!SendMessageW` at `0x18008456c`
- `USER32!SendMessageW` at `0x180084580`
- `USER32!SendMessageW` at `0x180084597`
- `USER32!SendMessageW` at `0x180084505`
- `USER32!SendMessageW` at `0x18008456c`
- `USER32!SendMessageW` at `0x180084580`
- `USER32!SendMessageW` at `0x180084597`
- `USER32!ReleaseDC` at `0x1800845ee`
- `USER32!ReleaseDC` at `0x1800845ee`
- `USER32!GetPropW` at `0x1800844ee`
- `USER32!GetPropW` at `0x1800844ee`
- `USER32!GetWindowTextLengthW` at `0x180084515`
- `USER32!GetWindowTextLengthW` at `0x180084515`

## string_xrefs

- `0x1800844e4`: `IMECompPos`

## pseudocode

```c

```
