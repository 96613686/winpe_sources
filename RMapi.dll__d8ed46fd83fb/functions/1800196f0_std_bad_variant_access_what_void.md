# std::bad_variant_access::what(void)

- ea: `0x1800196f0`
- end: `0x1800196f8`
- name: `?what@bad_variant_access@std@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(std::bad_variant_access *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x1800196f0`: `bad variant access`

## pseudocode

```c
const char *__fastcall std::bad_variant_access::what(std::bad_variant_access *this)
{
  return "bad variant access";
}

```

## disassembly

```asm
0x1800196f0  lea     rax, aBadVariantAcce; "bad variant access"
0x1800196f7  retn
```
