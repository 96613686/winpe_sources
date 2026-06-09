# SIPolicySecureSettingSearchCompare

- ea: `0x180024550`
- end: `0x1800245a5`
- name: `SIPolicySecureSettingSearchCompare`
- size: `85`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180024550`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002456a`
- `ntdll!RtlCompareUnicodeString` at `0x18002457f`
- `ntdll!RtlCompareUnicodeString` at `0x180024594`
- `ntdll!RtlCompareUnicodeString` at `0x18002456a`
- `ntdll!RtlCompareUnicodeString` at `0x18002457f`
- `ntdll!RtlCompareUnicodeString` at `0x180024594`

## pseudocode

```c
int __fastcall SIPolicySecureSettingSearchCompare(PCUNICODE_STRING *a1, char *a2)
{
  int result; // eax

  result = RtlCompareUnicodeString(*a1, (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString(a1[1], (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
      return RtlCompareUnicodeString(a1[2], (PCUNICODE_STRING)(a2 + 40), 1u);
  }
  return result;
}

```

## disassembly

```asm
0x180024550  mov     [rsp+arg_0], rbx
0x180024555  push    rdi
0x180024556  sub     rsp, 20h
0x18002455a  mov     rbx, rdx
0x18002455d  mov     rdi, rcx
0x180024560  mov     rcx, [rcx]; String1
0x180024563  add     rdx, 8; String2
0x180024567  mov     r8b, 1; CaseInsensitive
0x18002456a  call    cs:__imp_RtlCompareUnicodeString
0x180024570  test    eax, eax
0x180024572  jnz     short loc_18002459A
0x180024574  mov     rcx, [rdi+8]; String1
0x180024578  lea     rdx, [rbx+18h]; String2
0x18002457c  mov     r8b, 1; CaseInsensitive
0x18002457f  call    cs:__imp_RtlCompareUnicodeString
0x180024585  test    eax, eax
0x180024587  jnz     short loc_18002459A
0x180024589  mov     rcx, [rdi+10h]; String1
0x18002458d  lea     rdx, [rbx+28h]; String2
0x180024591  mov     r8b, 1; CaseInsensitive
0x180024594  call    cs:__imp_RtlCompareUnicodeString
0x18002459a  mov     rbx, [rsp+28h+arg_0]
0x18002459f  add     rsp, 20h
0x1800245a3  pop     rdi
0x1800245a4  retn
```
