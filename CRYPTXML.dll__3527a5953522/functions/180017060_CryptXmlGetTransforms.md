# CryptXmlGetTransforms

- ea: `0x180017060`
- end: `0x18001706d`
- name: `CryptXmlGetTransforms`
- size: `13`
- prototype: `HRESULT __stdcall(const CRYPT_XML_TRANSFORM_CHAIN_CONFIG **ppConfig)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetTransforms(const CRYPT_XML_TRANSFORM_CHAIN_CONFIG **ppConfig)
{
  *ppConfig = &g_CHAIN_CONFIG;
  return 0;
}

```

## disassembly

```asm
0x180017060  lea     rax, ?g_CHAIN_CONFIG@@3U_CRYPT_XML_TRANSFORM_CHAIN_CONFIG@@A; _CRYPT_XML_TRANSFORM_CHAIN_CONFIG g_CHAIN_CONFIG
0x180017067  mov     [rcx], rax
0x18001706a  xor     eax, eax
0x18001706c  retn
```
