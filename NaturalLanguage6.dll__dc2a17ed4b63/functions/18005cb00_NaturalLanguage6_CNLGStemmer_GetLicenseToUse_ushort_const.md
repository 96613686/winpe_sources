# NaturalLanguage6::CNLGStemmer::GetLicenseToUse(ushort const * *)

- ea: `0x18005cb00`
- end: `0x18005cb18`
- name: `?GetLicenseToUse@CNLGStemmer@NaturalLanguage6@@UEAAJPEAPEBG@Z`
- size: `24`
- prototype: `__int64 __fastcall(NaturalLanguage6::CNLGStemmer *__hidden this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18005cb00`

## string_xrefs

- `0x18005cb0b`: `Copyright © Microsoft Corporation. All rights reserved.`

## pseudocode

```c
__int64 __fastcall NaturalLanguage6::CNLGStemmer::GetLicenseToUse(
        NaturalLanguage6::CNLGStemmer *this,
        const unsigned __int16 **a2)
{
  if ( !a2 )
    return 2147942487LL;
  *a2 = L"Copyright © Microsoft Corporation. All rights reserved.";
  return 0;
}

```

## disassembly

```asm
0x18005cb00  test    rdx, rdx
0x18005cb03  jnz     short loc_18005CB0B
0x18005cb05  mov     eax, 80070057h
0x18005cb0a  retn
0x18005cb0b  lea     rax, aCopyrightMicro; "Copyright © Microsoft Corporation. All "...
0x18005cb12  mov     [rdx], rax
0x18005cb15  xor     eax, eax
0x18005cb17  retn
```
