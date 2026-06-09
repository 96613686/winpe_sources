# BfsCompareTableEntries

- ea: `0x140010760`
- end: `0x140010795`
- name: `BfsCompareTableEntries`
- size: `53`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010760`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140010770`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010770`

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
0x140010760  sub     rsp, 28h
0x140010764  mov     rcx, [rdx]; String1
0x140010767  mov     rax, r8
0x14001076a  mov     r8b, 1; CaseInSensitive
0x14001076d  mov     rdx, [rax]; String2
0x140010770  call    cs:__imp_RtlCompareUnicodeString
0x140010777  nop     dword ptr [rax+rax+00h]
0x14001077c  mov     ecx, eax
0x14001077e  test    eax, eax
0x140010780  jns     short loc_140010786
0x140010782  xor     eax, eax
0x140010784  jmp     short loc_14001078F
0x140010786  xor     eax, eax
0x140010788  test    ecx, ecx
0x14001078a  setle   al
0x14001078d  inc     eax
0x14001078f  add     rsp, 28h
0x140010793  retn
```
