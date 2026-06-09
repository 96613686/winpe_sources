# BfsCompareTableEntries

- ea: `0x140010900`
- end: `0x140010935`
- name: `BfsCompareTableEntries`
- size: `53`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, PCUNICODE_STRING *FirstStruct, PCUNICODE_STRING *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010900`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140010910`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010910`

## pseudocode

```c
__int64 __fastcall BfsCompareTableEntries(
        struct _RTL_AVL_TABLE *Table,
        PCUNICODE_STRING *FirstStruct,
        PCUNICODE_STRING *SecondStruct)
{
  LONG v3; // ecx

  v3 = RtlCompareUnicodeString(*FirstStruct, *SecondStruct, 1u);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x140010900  sub     rsp, 28h
0x140010904  mov     rcx, [rdx]; String1
0x140010907  mov     rax, r8
0x14001090a  mov     r8b, 1; CaseInSensitive
0x14001090d  mov     rdx, [rax]; String2
0x140010910  call    cs:__imp_RtlCompareUnicodeString
0x140010917  nop     dword ptr [rax+rax+00h]
0x14001091c  mov     ecx, eax
0x14001091e  test    eax, eax
0x140010920  jns     short loc_140010926
0x140010922  xor     eax, eax
0x140010924  jmp     short loc_14001092F
0x140010926  xor     eax, eax
0x140010928  test    ecx, ecx
0x14001092a  setle   al
0x14001092d  inc     eax
0x14001092f  add     rsp, 28h
0x140010933  retn
```
