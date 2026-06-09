# CHXSmartScreen::__CssTemplateInfoActivationFactory::GetTargetClassName(void)

- ea: `0x1400064e0`
- end: `0x1400064e8`
- name: `?GetTargetClassName@__CssTemplateInfoActivationFactory@CHXSmartScreen@@SAPEB_WXZ`
- size: `8`
- prototype: `const wchar_t *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1400064e0`: `CHXSmartScreen.CssTemplateInfo`

## pseudocode

```c
const wchar_t *CHXSmartScreen::__CssTemplateInfoActivationFactory::GetTargetClassName(void)
{
  return L"CHXSmartScreen.CssTemplateInfo";
}

```

## disassembly

```asm
0x1400064e0  lea     rax, sourceString; "CHXSmartScreen.CssTemplateInfo"
0x1400064e7  retn
```
