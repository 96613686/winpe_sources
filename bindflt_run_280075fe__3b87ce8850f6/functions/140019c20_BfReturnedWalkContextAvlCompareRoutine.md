# BfReturnedWalkContextAvlCompareRoutine

- ea: `0x140019c20`
- end: `0x140019c3d`
- name: `BfReturnedWalkContextAvlCompareRoutine`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140018b60`
- `0x14001ad80`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140019c2b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140019c2b`

## pseudocode

```c
LONG __fastcall BfReturnedWalkContextAvlCompareRoutine(const UNICODE_STRING *a1, const UNICODE_STRING *a2)
{
  return RtlCompareUnicodeString(a1, a2 + 4, 0);
}

```

## disassembly

```asm
0x140019c20  sub     rsp, 28h
0x140019c24  add     rdx, 40h ; '@'; String2
0x140019c28  xor     r8d, r8d; CaseInSensitive
0x140019c2b  call    cs:__imp_RtlCompareUnicodeString
0x140019c32  nop     dword ptr [rax+rax+00h]
0x140019c37  add     rsp, 28h
0x140019c3b  retn
```
