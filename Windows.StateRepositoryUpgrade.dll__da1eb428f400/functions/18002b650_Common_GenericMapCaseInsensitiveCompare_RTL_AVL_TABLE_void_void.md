# Common::GenericMapCaseInsensitiveCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x18002b650`
- end: `0x18002b6b5`
- name: `?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `101`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b650`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002b671`
- `ntdll!RtlInitUnicodeString` at `0x18002b67f`
- `ntdll!RtlInitUnicodeString` at `0x18002b671`
- `ntdll!RtlInitUnicodeString` at `0x18002b67f`
- `ntdll!RtlCompareUnicodeString` at `0x18002b697`
- `ntdll!RtlCompareUnicodeString` at `0x18002b697`

## pseudocode

```c
__int64 __fastcall Common::GenericMapCaseInsensitiveCompare(
        struct _RTL_AVL_TABLE *Table,
        const WCHAR **FirstStruct,
        const WCHAR **SecondStruct)
{
  const WCHAR *v3; // rdx
  const WCHAR *v4; // rbx
  unsigned int v5; // ebx
  LONG v6; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, v3);
  RtlInitUnicodeString(&String2, v4);
  v5 = 1;
  v6 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
  if ( v6 <= 0 )
  {
    v5 = 2;
    if ( v6 < 0 )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18002b650  push    rbx
0x18002b652  sub     rsp, 40h
0x18002b656  mov     rdx, [rdx]; SourceString
0x18002b659  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18002b65e  mov     rbx, [r8]
0x18002b661  xorps   xmm0, xmm0
0x18002b664  xorps   xmm1, xmm1
0x18002b667  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18002b66c  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x18002b671  call    cs:__imp_RtlInitUnicodeString
0x18002b677  mov     rdx, rbx; SourceString
0x18002b67a  lea     rcx, [rsp+48h+String2]; DestinationString
0x18002b67f  call    cs:__imp_RtlInitUnicodeString
0x18002b685  mov     ebx, 1
0x18002b68a  lea     rdx, [rsp+48h+String2]; String2
0x18002b68f  mov     r8b, bl; CaseInsensitive
0x18002b692  lea     rcx, [rsp+48h+DestinationString]; String1
0x18002b697  call    cs:__imp_RtlCompareUnicodeString
0x18002b69d  test    eax, eax
0x18002b69f  jg      short loc_18002B6AD
0x18002b6a1  xor     ecx, ecx
0x18002b6a3  mov     ebx, 2
0x18002b6a8  test    eax, eax
0x18002b6aa  cmovs   ebx, ecx
0x18002b6ad  mov     eax, ebx
0x18002b6af  add     rsp, 40h
0x18002b6b3  pop     rbx
0x18002b6b4  retn
```
