# ProcessedPipelineEffect::CalculateAndSetWhiteBalance(void)

- ea: `0x180503030`
- end: `0x180503d55`
- name: `?CalculateAndSetWhiteBalance@ProcessedPipelineEffect@@AEAA_NXZ`
- size: `3365`
- prototype: `bool __fastcall(ProcessedPipelineEffect *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1804fc620`
- `0x1805011ac`
- `0x180503d60`
- `0x180504490`

## callees

- `0x18019a604`
- `0x1801a31b8`
- `0x18047ee78`
- `0x1804c6944`
- `0x180503030`
- `0x1805129ec`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180503062`
- `OLEAUT32!__imp_VariantInit` at `0x1805030a3`
- `OLEAUT32!__imp_VariantInit` at `0x1805032aa`
- `OLEAUT32!__imp_VariantInit` at `0x180503aa2`
- `OLEAUT32!__imp_VariantInit` at `0x180503062`
- `OLEAUT32!__imp_VariantInit` at `0x1805030a3`
- `OLEAUT32!__imp_VariantInit` at `0x1805032aa`
- `OLEAUT32!__imp_VariantInit` at `0x180503aa2`
- `OLEAUT32!__imp_VariantClear` at `0x180503a5e`
- `OLEAUT32!__imp_VariantClear` at `0x180503b10`
- `OLEAUT32!__imp_VariantClear` at `0x180503b36`
- `OLEAUT32!__imp_VariantClear` at `0x180503b40`
- `OLEAUT32!__imp_VariantClear` at `0x180503b69`
- `OLEAUT32!__imp_VariantClear` at `0x180503b73`
- `OLEAUT32!__imp_VariantClear` at `0x180503a5e`
- `OLEAUT32!__imp_VariantClear` at `0x180503b10`
- `OLEAUT32!__imp_VariantClear` at `0x180503b36`
- `OLEAUT32!__imp_VariantClear` at `0x180503b40`
- `OLEAUT32!__imp_VariantClear` at `0x180503b69`
- `OLEAUT32!__imp_VariantClear` at `0x180503b73`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180503108`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180503108`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180503a7d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180503b2b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180503a7d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180503b2b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050318a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805031e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050324a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503324`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503390`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805033ee`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050345d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805034bb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050352a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503589`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805035de`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503645`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503697`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805036f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050375e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805037b3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050381a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050386f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805038ba`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503919`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050397c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805039e3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050318a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805031e8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050324a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503324`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503390`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805033ee`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050345d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805034bb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050352a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503589`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805035de`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503645`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503697`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805036f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050375e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805037b3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050381a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050386f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805038ba`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180503919`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18050397c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1805039e3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050315e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805031c4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050321f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805032fd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503368`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805033c8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503437`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503495`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503504`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503562`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805035b8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050361d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503671`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805036cf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503737`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050378d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805037f2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503849`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503894`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805038f2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503956`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805039bd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050315e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805031c4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050321f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805032fd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503368`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805033c8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503437`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503495`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503504`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503562`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805035b8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050361d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503671`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805036cf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503737`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18050378d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805037f2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503849`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503894`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805038f2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180503956`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1805039bd`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180503124`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180503124`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180503a6e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180503b1e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180503a6e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180503b1e`

## string_xrefs

- `0x180503076`: `Temperature`

## pseudocode

```c

```
