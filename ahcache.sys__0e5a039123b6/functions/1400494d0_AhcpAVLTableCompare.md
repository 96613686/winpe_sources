# AhcpAVLTableCompare

- ea: `0x1400494d0`
- end: `0x140049511`
- name: `AhcpAVLTableCompare`
- size: `65`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400494d0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400494e2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400494e2`

## pseudocode

```c
__int64 __fastcall AhcpAVLTableCompare(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)
{
  LONG v3; // eax
  unsigned int v4; // ecx

  v3 = RtlCompareUnicodeString((PCUNICODE_STRING)(FirstStruct + 24), (PCUNICODE_STRING)(SecondStruct + 24), 1u);
  if ( v3 < 0 )
    return 0;
  v4 = 2;
  if ( v3 > 0 )
    return 1;
  return v4;
}

```

## disassembly

```asm
0x1400494d0  sub     rsp, 28h
0x1400494d4  mov     rcx, rdx
0x1400494d7  lea     rdx, [r8+18h]; String2
0x1400494db  add     rcx, 18h; String1
0x1400494df  mov     r8b, 1; CaseInSensitive
0x1400494e2  call    cs:__imp_RtlCompareUnicodeString
0x1400494e9  nop     dword ptr [rax+rax+00h]
0x1400494ee  test    eax, eax
0x1400494f0  js      short loc_140049509
0x1400494f2  test    eax, eax
0x1400494f4  mov     edx, 1
0x1400494f9  mov     ecx, 2
0x1400494fe  cmovg   ecx, edx
0x140049501  mov     eax, ecx
0x140049503  add     rsp, 28h
0x140049507  retn
0x140049509  xor     eax, eax
0x14004950b  add     rsp, 28h
0x14004950f  retn
```
