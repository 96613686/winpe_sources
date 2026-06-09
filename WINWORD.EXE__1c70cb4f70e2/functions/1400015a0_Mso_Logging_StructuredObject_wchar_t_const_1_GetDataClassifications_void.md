# Mso::Logging::StructuredObject<wchar_t const *,1>::GetDataClassifications(void)

- ea: `0x1400015a0`
- end: `0x1400015a5`
- name: `?GetDataClassifications@?$StructuredObject@PEB_W$00@Logging@Mso@@UEBA?AW4DataClassifications@23@XZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall Mso::Logging::StructuredObject<wchar_t const *,1>::GetDataClassifications(__int64 a1)
{
  return *(unsigned __int16 *)(a1 + 24);
}

```

## disassembly

```asm
0x1400015a0  movzx   eax, word ptr [rcx+18h]
0x1400015a4  retn
```
