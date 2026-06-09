# AipIsPathMacroPrefix

- ea: `0x180005594`
- end: `0x1800055e8`
- name: `AipIsPathMacroPrefix`
- size: `84`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000423c`
- `0x1800051fc`

## callees

- `0x180005594`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x1800055da`
- `ntdll!RtlPrefixUnicodeString` at `0x1800055da`

## pseudocode

```c
__int64 __fastcall AipIsPathMacroPrefix(PCUNICODE_STRING String2, PCUNICODE_STRING String1)
{
  unsigned int Length; // eax
  __int64 result; // rax
  WCHAR v4; // r8

  Length = String2->Length;
  if ( (unsigned __int16)Length < String1->Length )
    return 0;
  if ( Length <= (unsigned int)String1->Length + 1 )
    return RtlPrefixUnicodeString(String1, String2, 1u);
  v4 = String2->Buffer[(unsigned __int64)String1->Length >> 1];
  if ( v4 == 92 )
    return RtlPrefixUnicodeString(String1, String2, 1u);
  result = 0;
  if ( !v4 )
    return RtlPrefixUnicodeString(String1, String2, 1u);
  return result;
}

```

## disassembly

```asm
0x180005594  sub     rsp, 28h
0x180005598  movzx   eax, word ptr [rcx]
0x18000559b  mov     r9, rdx
0x18000559e  mov     rdx, rcx; String2
0x1800055a1  cmp     ax, [r9]
0x1800055a5  jnb     short loc_1800055AB
0x1800055a7  xor     eax, eax
0x1800055a9  jmp     short loc_1800055E3
0x1800055ab  movzx   ecx, word ptr [r9]
0x1800055af  inc     ecx
0x1800055b1  cmp     eax, ecx
0x1800055b3  jbe     short loc_1800055D4
0x1800055b5  movzx   ecx, word ptr [r9]
0x1800055b9  mov     rax, [rdx+8]
0x1800055bd  shr     rcx, 1
0x1800055c0  movzx   r8d, word ptr [rax+rcx*2]
0x1800055c5  cmp     r8w, 5Ch ; '\'
0x1800055ca  jz      short loc_1800055D4
0x1800055cc  xor     eax, eax
0x1800055ce  test    r8w, r8w
0x1800055d2  jnz     short loc_1800055E3
0x1800055d4  mov     r8b, 1; CaseInsensitive
0x1800055d7  mov     rcx, r9; String1
0x1800055da  call    cs:__imp_RtlPrefixUnicodeString
0x1800055e0  movzx   eax, al
0x1800055e3  add     rsp, 28h
0x1800055e7  retn
```
