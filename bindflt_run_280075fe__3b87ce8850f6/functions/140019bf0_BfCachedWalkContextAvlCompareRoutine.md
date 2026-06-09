# BfCachedWalkContextAvlCompareRoutine

- ea: `0x140019bf0`
- end: `0x140019c0d`
- name: `BfCachedWalkContextAvlCompareRoutine`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140018b60`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140019bfb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019bfb`

## pseudocode

```c
LONG __fastcall BfCachedWalkContextAvlCompareRoutine(const UNICODE_STRING *a1, __int64 a2)
{
  return RtlCompareUnicodeString(a1, (PCUNICODE_STRING)(a2 + 40), 0);
}

```

## disassembly

```asm
0x140019bf0  sub     rsp, 28h
0x140019bf4  add     rdx, 28h ; '('; String2
0x140019bf8  xor     r8d, r8d; CaseInSensitive
0x140019bfb  call    cs:__imp_RtlCompareUnicodeString
0x140019c02  nop     dword ptr [rax+rax+00h]
0x140019c07  add     rsp, 28h
0x140019c0b  retn
```
