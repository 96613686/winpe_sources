# SIPolicyFileRuleCompare

- ea: `0x180028dbc`
- end: `0x180028e33`
- name: `SIPolicyFileRuleCompare`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024bd0`

## callees

- `0x180028dbc`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180028de3`
- `ntdll!RtlCompareUnicodeString` at `0x180028df8`
- `ntdll!RtlCompareUnicodeString` at `0x180028e0d`
- `ntdll!RtlCompareUnicodeString` at `0x180028e22`
- `ntdll!RtlCompareUnicodeString` at `0x180028de3`
- `ntdll!RtlCompareUnicodeString` at `0x180028df8`
- `ntdll!RtlCompareUnicodeString` at `0x180028e0d`
- `ntdll!RtlCompareUnicodeString` at `0x180028e22`

## pseudocode

```c
int __fastcall SIPolicyFileRuleCompare(__int64 a1, __int64 a2)
{
  int result; // eax

  if ( *(_DWORD *)a1 != *(_DWORD *)a2 )
    return *(_DWORD *)a1 - *(_DWORD *)a2;
  result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 8), (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 24), (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
    {
      result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 40), (PCUNICODE_STRING)(a2 + 40), 1u);
      if ( !result )
        return RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 56), (PCUNICODE_STRING)(a2 + 56), 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028dbc  mov     [rsp+arg_0], rbx
0x180028dc1  push    rdi
0x180028dc2  sub     rsp, 20h
0x180028dc6  mov     rdi, rcx
0x180028dc9  mov     rbx, rdx
0x180028dcc  mov     ecx, [rdx]
0x180028dce  mov     eax, [rdi]
0x180028dd0  cmp     eax, ecx
0x180028dd2  jz      short loc_180028DD8
0x180028dd4  sub     eax, ecx
0x180028dd6  jmp     short loc_180028E28
0x180028dd8  add     rdx, 8; String2
0x180028ddc  lea     rcx, [rdi+8]; String1
0x180028de0  mov     r8b, 1; CaseInsensitive
0x180028de3  call    cs:__imp_RtlCompareUnicodeString
0x180028de9  test    eax, eax
0x180028deb  jnz     short loc_180028E28
0x180028ded  lea     rdx, [rbx+18h]; String2
0x180028df1  mov     r8b, 1; CaseInsensitive
0x180028df4  lea     rcx, [rdi+18h]; String1
0x180028df8  call    cs:__imp_RtlCompareUnicodeString
0x180028dfe  test    eax, eax
0x180028e00  jnz     short loc_180028E28
0x180028e02  lea     rdx, [rbx+28h]; String2
0x180028e06  mov     r8b, 1; CaseInsensitive
0x180028e09  lea     rcx, [rdi+28h]; String1
0x180028e0d  call    cs:__imp_RtlCompareUnicodeString
0x180028e13  test    eax, eax
0x180028e15  jnz     short loc_180028E28
0x180028e17  lea     rdx, [rbx+38h]; String2
0x180028e1b  mov     r8b, 1; CaseInsensitive
0x180028e1e  lea     rcx, [rdi+38h]; String1
0x180028e22  call    cs:__imp_RtlCompareUnicodeString
0x180028e28  mov     rbx, [rsp+28h+arg_0]
0x180028e2d  add     rsp, 20h
0x180028e31  pop     rdi
0x180028e32  retn
```
