# NaturalLanguage6::CNLGSentenceSeparator::GetLicenseToUse(ushort const * *)

- ea: `0x180033190`
- end: `0x1800331a8`
- name: `?GetLicenseToUse@CNLGSentenceSeparator@NaturalLanguage6@@UEAAJPEAPEBG@Z`
- size: `24`
- prototype: `__int64 __fastcall(NaturalLanguage6::CNLGSentenceSeparator *__hidden this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180033190`

## string_xrefs

- `0x180033195`: `Copyright © Microsoft Corporation. All rights reserved.`

## pseudocode

```c
__int64 __fastcall NaturalLanguage6::CNLGSentenceSeparator::GetLicenseToUse(
        NaturalLanguage6::CNLGSentenceSeparator *this,
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
0x180033190  test    rdx, rdx
0x180033193  jz      short loc_1800331A2
0x180033195  lea     rax, aCopyrightMicro; "Copyright © Microsoft Corporation. All "...
0x18003319c  mov     [rdx], rax
0x18003319f  xor     eax, eax
0x1800331a1  retn
0x1800331a2  mov     eax, 80070057h
0x1800331a7  retn
```
