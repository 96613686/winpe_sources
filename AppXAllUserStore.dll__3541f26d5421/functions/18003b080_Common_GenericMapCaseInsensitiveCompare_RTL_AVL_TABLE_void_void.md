# Common::GenericMapCaseInsensitiveCompare(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x18003b080`
- end: `0x18003b0e5`
- name: `?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `101`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003b080`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003b0a1`
- `ntdll!RtlInitUnicodeString` at `0x18003b0af`
- `ntdll!RtlInitUnicodeString` at `0x18003b0a1`
- `ntdll!RtlInitUnicodeString` at `0x18003b0af`
- `ntdll!RtlCompareUnicodeString` at `0x18003b0c7`
- `ntdll!RtlCompareUnicodeString` at `0x18003b0c7`

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
0x18003b080  push    rbx
0x18003b082  sub     rsp, 40h
0x18003b086  mov     rdx, [rdx]; SourceString
0x18003b089  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18003b08e  mov     rbx, [r8]
0x18003b091  xorps   xmm0, xmm0
0x18003b094  xorps   xmm1, xmm1
0x18003b097  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18003b09c  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x18003b0a1  call    cs:__imp_RtlInitUnicodeString
0x18003b0a7  mov     rdx, rbx; SourceString
0x18003b0aa  lea     rcx, [rsp+48h+String2]; DestinationString
0x18003b0af  call    cs:__imp_RtlInitUnicodeString
0x18003b0b5  mov     ebx, 1
0x18003b0ba  lea     rdx, [rsp+48h+String2]; String2
0x18003b0bf  mov     r8b, bl; CaseInsensitive
0x18003b0c2  lea     rcx, [rsp+48h+DestinationString]; String1
0x18003b0c7  call    cs:__imp_RtlCompareUnicodeString
0x18003b0cd  test    eax, eax
0x18003b0cf  jg      short loc_18003B0DD
0x18003b0d1  xor     ecx, ecx
0x18003b0d3  mov     ebx, 2
0x18003b0d8  test    eax, eax
0x18003b0da  cmovs   ebx, ecx
0x18003b0dd  mov     eax, ebx
0x18003b0df  add     rsp, 40h
0x18003b0e3  pop     rbx
0x18003b0e4  retn
```
