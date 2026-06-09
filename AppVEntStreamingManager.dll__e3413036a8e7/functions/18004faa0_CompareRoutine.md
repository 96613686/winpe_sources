# CompareRoutine

- ea: `0x18004faa0`
- end: `0x18004face`
- name: `CompareRoutine`
- size: `46`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, const UNICODE_STRING *FirstStruct, const UNICODE_STRING *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18004faa0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004fab0`
- `ntdll!RtlCompareUnicodeString` at `0x18004fab0`

## pseudocode

```c
__int64 __fastcall CompareRoutine(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  LONG v3; // ecx

  v3 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x18004faa0  sub     rsp, 28h
0x18004faa4  mov     rax, r8
0x18004faa7  mov     rcx, rdx; String1
0x18004faaa  mov     rdx, rax; String2
0x18004faad  mov     r8b, 1; CaseInsensitive
0x18004fab0  call    cs:RtlCompareUnicodeString
0x18004fab6  mov     ecx, eax
0x18004fab8  test    eax, eax
0x18004faba  jns     short loc_18004FAC0
0x18004fabc  xor     eax, eax
0x18004fabe  jmp     short loc_18004FAC9
0x18004fac0  xor     eax, eax
0x18004fac2  test    ecx, ecx
0x18004fac4  setle   al
0x18004fac7  inc     eax
0x18004fac9  add     rsp, 28h
0x18004facd  retn
```
