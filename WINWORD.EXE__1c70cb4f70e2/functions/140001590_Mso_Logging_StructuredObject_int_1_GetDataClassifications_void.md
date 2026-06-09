# Mso::Logging::StructuredObject<int,1>::GetDataClassifications(void)

- ea: `0x140001590`
- end: `0x140001595`
- name: `?GetDataClassifications@?$StructuredObject@H$00@Logging@Mso@@UEBA?AW4DataClassifications@23@XZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall Mso::Logging::StructuredObject<int,1>::GetDataClassifications(__int64 a1)
{
  return *(unsigned __int16 *)(a1 + 20);
}

```

## disassembly

```asm
0x140001590  movzx   eax, word ptr [rcx+14h]
0x140001594  retn
```
